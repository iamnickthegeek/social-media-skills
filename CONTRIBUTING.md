# Contributing to Social Media Skills

Thanks for your interest. Here's how to contribute.

## Ways to Contribute

### 1. Update Format Data

The most valuable contribution is keeping `skills/references/bleeding-edge-formats.md` current. When new platform research comes out:

1. Update the relevant section in that file
2. Include source citations
3. Submit a PR with the date and what changed

### 2. Improve a Skill

Each skill lives in its own directory with a `SKILL.md`. To improve one:

1. Edit the `SKILL.md` in the relevant skill directory
2. Test it in your Hermes environment
3. Submit a PR describing the change and why

### 3. Add a New Skill

New skills should:
- Be self-contained in their own directory
- Include a `SKILL.md` with frontmatter (name, description)
- Follow the existing skill structure
- Load `references/bleeding-edge-formats.md` if generating content

### 4. Report Issues

Open an issue describing:
- Which skill
- What happened
- What you expected
- Steps to reproduce

## Code of Conduct

Be direct. Be honest. No filler, no corporate speak, no fake urgency.

## Development Setup

```bash
git clone https://github.com/iamnickthegeek/social-media-skills.git
cd social-media-skills
# Edit skills/ files
# Test in your Hermes environment
git commit -m "your change"
git push origin main
# Open a PR
```

## Pull Request Guidelines

- One change per PR
- Describe what and why
- Update `references/CHANGELOG.md` if you modify patched skills
- Include source citations for any new format/benchmark data
