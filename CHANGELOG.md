# Changelog — social-media-skills

All notable changes to this project will be documented in this file.

## [Unreleased] — 2026-06-25

### Added

- **Source lens system for niche-research** — new tagging layer that classifies every research item into one of six source lenses:
  - **Current News** — industry events, market moves, new data, regulation changes
  - **Historical Parallel** — past events/figures with clear modern resonance
  - **Viral Social** — high-engagement posts revealing structural tensions
  - **Community Candor** — honest practitioner language from Reddit/forums
  - **Thinker Framework** — named researchers explaining *why* patterns exist structurally
  - **Pure Insight** — patterns visible across sources that no single source states directly
- **Lens-aware synthesis** — themes are now scored by lens depth (3+ lenses = strongest). Community Candor + Thinker Framework pairing flagged as highest-value input.
- **Insight Potential column** — output table now rates themes High/Medium/Low based on lens composition
- **Filter by lens** — new post-research option to show only specific lenses or High Insight Potential themes
- **Expanded Google search queries** — added `[niche] failure`, `[niche] counterintuitive`, `[niche] debate` to the existing news/launch/controversy/research/regulation set

### Changed

- `niche-research` — Step 2d added (source lens tagging). Step 3 updated with lens-aware synthesis rules. Step 4 table updated with Source Lenses and Insight Potential columns. Step 5 updated with "Filter by lens" option. Rules section updated with two new rules (mandatory tagging, multi-lens prioritisation).

## [Previous] — 2026-06-24

### Added

- **Facebook platform support** — new `facebook/` skill with 7 formats:
  - Status Posts (0.20% ER — highest engagement rate)
  - Image Posts (0.15% ER, stable, 44.8% of high-performing content)
  - Albums/Carousels (0.18% ER, highest shares/views)
  - Reels (0.15% ER rising, 135% more reach, only format avoiding Q1 2026 decline)
  - Native Video (4.84% median ER, 25–40% reach)
  - Link Posts (0.05% ER — lowest, use comments for links)
  - Facebook Live (35–50% organic reach, 6× engagement)

### Changed

- `references/bleeding-edge-formats.md` — added Facebook section (7 formats, 10 sources, benchmarks table, algorithm hierarchy, format performance ranking)
- `SKILL.md` — added Facebook to Phase 2 (Content Creation), directory tree, 7 Facebook-specific rules, "Facebook Quick Run" section
- `references/bleeding-edge-formats.md` header — updated scope to include Facebook (7 formats)
- Cross-platform comparison table — added Facebook row

### Documentation

- Created `README.md` — full project documentation including all 6 platforms, quick start guide, Facebook section
- Created `CONTRIBUTING.md` — contribution guidelines, development setup, PR guidelines
- `references/CHANGELOG.md` — added Session 6 entry documenting all Facebook changes

### Data Sources

- Buffer State of Social Media Engagement 2026 (52M+ posts)
- Socialinsider 2026 Organic Facebook Engagement Benchmarks (25M posts, 130K pages)
- Sprout Social 9 Facebook Trends 2026
- SocialBee Facebook Algorithm Analysis 2026
- FB Group Bulk Poster Facebook Organic Reach 2026
- Net Influencer Buffer data analysis 2026
- PostEverywhere Facebook viral content 2026
- ShortsIntel Social Media Benchmarks 2026
- Apaya Social Media Benchmarks 2026
- IQFluence Social Media Benchmarks 2026
