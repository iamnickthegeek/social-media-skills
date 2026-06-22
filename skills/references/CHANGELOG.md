# Change Log — Bleeding Edge Formats Integration

**Date:** June 22, 2026
**Source research:** `~/.hermes/projects/june-2026-post-types/FINAL.md`
**Approach:** Single shared reference file + Step 0 load in each patched skill (no hardcoded format data in individual skills).

---

## New File

### `references/bleeding-edge-formats.md`
- Created as the single source of truth for current platform format data.
- Contains: LinkedIn carousel template + benchmarks, Instagram carousel template + benchmarks, Substack newsletter template + benchmarks, cross-platform engagement comparison table, "what to avoid" section.
- When this file is updated, all 6 patched skills pick up changes automatically.

---

## Patched Skills

### 1. `post-writer/SKILL.md`
- **Added:** Step 0 — loads format reference for hook priorities, optimal length, tone guidance.
- **Changed:** Step 3 (Write) — hook selection now aligns with top-performing types from reference; suggests carousel when topic suits it.
- **Changed:** Step 4 (Iterate) — added "build a carousel" to the post-save options.
- **Changed:** Rules — added "Always read the format reference (Step 0) before writing."

### 2. `post-formatter/SKILL.md`
- **Added:** Step 0 — loads format reference for hook type priorities, optimal length, tone, CTA patterns.
- **Changed:** Rules — added "Always read the format reference (Step 0) before formatting."

### 3. `hook-generator/SKILL.md`
- **Added:** Step 0 — loads format reference for hook type distribution (number-led 31%, bold claim 27%, contrarian 18%) and tone guidance.
- **Effect:** Hook variations now prioritize the angles that data shows perform best.

### 4. `gemini-carousel/SKILL.md`
- **Added:** Step 0 — loads format reference for carousel slide structure, optimal slide count, tone, CTA approach.
- **Changed:** Rules — added "Always read the format reference (Step 0) before building the brief."

### 5. `post-scorer/SKILL.md`
- **Added:** Step 0 — loads format reference for benchmark comparisons (hook types, length, CTA patterns, cross-platform table).
- **Changed:** Data source option renamed from "Use Charlie Hills data" → "Use benchmark data".
- **Changed:** Fallback benchmarks section — now notes that values come from the reference file and warns about staleness.
- **Effect:** Scoring now compares drafts against current platform benchmarks by default.

### 6. `analytics-dashboard/SKILL.md`
- **Added:** Step 0 — loads format reference for engagement rate benchmarks, format distribution comparisons, hook/CTA pattern evaluation, underperformer pattern detection.
- **Changed:** Rules — added "Always read the format reference (Step 0) before analyzing."

---

## Skills NOT Patched (and why)

| Skill | Reason |
|-------|--------|
| `content-matrix` | Ideation tool; format awareness not needed at matrix level |
| `niche-research` | Research tool; doesn't generate content |
| `newsletter-voice` | One-time voice setup; not content generation |
| `voice-builder` | One-time voice setup; not content generation |
| `profile-optimizer` | One-time profile setup; not content generation |
| `quote-post` | Derivative format; uses its own template |
| `pinned-comment` | Derivative format; uses Charlie Hills template |
| `reels-scripting` | Instagram/TikTok specific; uses its own Apify+Gemini pipeline |
| `gemini-infographic` | Image generation; uses its own prompt template |
| `graphic-designer` | Image generation; uses its own HTML/CSS or prompt templates |

---

## How to Update

1. Re-run deep research on current platform formats.
2. Replace the relevant section(s) in `references/bleeding-edge-formats.md`.
3. All 6 patched skills automatically use the new data on next run.
4. Update this change log with the date and what changed.

---

## Fork / PR Notes

- Original repo: `https://github.com/charlie947/social-media-skills`
- These changes are local customizations on top of the original.
- To fork: `gh repo fork charlie947/social-media-skills` (or create a new repo).
- The `references/` directory and all Step 0 additions are the delta from upstream.
- Skills not patched are unchanged from the original repo.
