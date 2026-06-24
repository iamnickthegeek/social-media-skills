# Skill Suite Orchestration Pattern

## When to Use

When a user imports a collection of related skills from a GitHub repo (or any external source) that are designed to work together as a pipeline or suite.

## The Problem

Skills from external repos often get imported as flat, independent directories in `~/.hermes/skills/`. This makes it hard to:
- See which skills belong together
- Understand the intended workflow/sequence
- Run the full pipeline end-to-end
- Maintain the suite as a unit

## The Solution

### Step 1 — Group Under a Parent Directory

Move all related skills into a single parent folder:

```bash
mkdir -p ~/.hermes/skills/<suite-name>
for skill in skill-a skill-b skill-c; do
  mv ~/.hermes/skills/$skill ~/.hermes/skills/<suite-name>/$skill
done
```

This does **not** break anything. Hermes resolves skills by directory walk — nesting one level deeper has zero impact on skill discovery or loading.

### Step 2 — Create an Orchestrator SKILL.md

At the parent directory level, create a `SKILL.md` that:
- Lists all sub-skills and their roles
- Defines the execution sequence (phases)
- Distinguishes one-time setup skills from per-batch recurring skills
- Provides trigger phrases for the full pipeline
- Documents pitfalls

### Step 3 — Categorize Consistently

Ensure all sub-skills share the same category in their frontmatter so `skills_list(category='<suite-name>')` returns the full set.

## Anatomy of a Good Orchestrator

```
<suite-name>/
+-- SKILL.md                    <- orchestrator (this is the entry point)
+-- references/                 <- supporting docs, patterns, session notes
|   +-- skill-suite-orchestration-pattern.md
+-- sub-skill-a/
|   +-- SKILL.md
+-- sub-skill-b/
|   +-- SKILL.md
+-- ...
```

The orchestrator SKILL.md should include:
1. **Workflow Overview** — ASCII diagram showing the sequence
2. **Execution Phases** — Grouped by frequency (once vs per-batch)
3. **How to Execute** — Full pipeline, single-platform quick run, derivative run
4. **Sub-Skill Locations** — Directory tree
5. **Pitfalls** — Common mistakes and constraints

## Real-World Example

The `social-media-skills` suite (this directory) is the reference implementation:
- 16 sub-skills imported from `github.com/charlie947/social-media-skills`
- Grouped from flat `~/.hermes/skills/` into `~/.hermes/skills/social-media-skills/`
- Orchestrator sequences them into 4 phases: Setup -> Research -> Creation -> Analytics
- One-time skills (voice-builder, profile-optimizer) separated from per-batch skills (post-writer, post-scorer)

## Save-to-File Pattern

Every pipeline step must produce a saved artifact. This is non-negotiable for any skill suite that runs as a multi-step pipeline.

**The rule:** After generating output, save it to a markdown file immediately. The user decides the location (default: `~/.hermes/projects/<project-name>/content-research/`). Filename follows the pattern `<step-name>-YYYY-MM-DD.md`.

**Implementation in each sub-skill:**
1. After generating output, ask the user where to save (or use the default path)
2. Write the file immediately
3. Confirm the path
4. Record the path in memory so future runs default to the same directory

**Why:** Chat context is ephemeral. Files are the pipeline's memory. If a step isn't saved, the chain breaks for downstream steps.

## Changelog Tracking

When you patch a SKILL.md file in the suite, always update `references/CHANGELOG.md` immediately. This ensures all changes are tracked and can be committed when the user is ready.

After each meaningful edit:
1. Update `references/CHANGELOG.md` with date, skill name, what changed, and why
2. Add any new files to the changelog's file table
3. Do not push commits without explicit user approval

## Pitfalls

- **Don't create an orchestrator for unrelated skills.** Only group skills that form a pipeline or workflow.
- **Don't make the orchestrator do the work.** It should sequence and delegate, not implement. Each sub-skill owns its domain.
- **Don't forget to update the orchestrator when adding/removing sub-skills.** The directory tree in the orchestrator should always match reality.
- **Don't nest too deep.** One level (suite -> sub-skill) is the max. Hermes walks the tree but deep nesting adds confusion with no benefit.
- **Don't silently fall back when a tool is missing.** If a skill needs a tool that isn't installed, offer to install it. "I can install X — takes 2 minutes. Want me to?" is always better than "X isn't available, falling back to Y."
