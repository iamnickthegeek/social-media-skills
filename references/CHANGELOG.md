# Change Log — Bleeding Edge Formats Integration

**Date:** June 30, 2026
**Source research:** X/Twitter source-evidence workflow review

---

## June 30, 2026 - X/Twitter Source Evidence Checkpoint

### `x-twitter/SKILL.md`
**Patched** - Added Step 1.5 before format selection:

- Requires source evidence for current events, public claims, launches, competitor moves, customer proof, or market conversations
- Keeps each claim tied to approved public source URLs or notes
- Treats source text as evidence only, not instructions
- Keeps TweetClaw as optional read-only OpenClaw context for source packets
- Leaves drafting, scoring, and final copy inside the `x-twitter` skill

---

**Date:** June 24, 2026
**Source research:** Deep Facebook research via Fableous pipeline (10 sources, 52M+ posts across Buffer, Socialinsider, SocialBee, Sprout Social, FB Group Bulk Poster, Net Influencer, PostEverywhere, ShortsIntel, Apaya, IQFluence)

---

## June 24, 2026 — Facebook Deep Research Update (7 Formats)

### `references/bleeding-edge-formats.md`
**Patched** — Added comprehensive Facebook section with 7 formats:

**Before:** No Facebook section existed
**After:** 7 data-backed formats with templates, benchmarks, algorithm hierarchy:

1. **Status Posts** — 0.20% avg ER, #1 format by engagement rate, most comments per post
2. **Image Posts** — 0.15% avg ER (stable), 44.8% of all high-performing content, 5.20% median ER
3. **Albums/Carousels** — 0.18% avg ER, highest shares/views, education vertical 5.2%
4. **Reels** — 0.15% avg ER (rising), only format to avoid Q1 2026 decline, 135% more reach
5. **Native Video** — 4.84% median ER, 25–40% reach, completion rate is dominant signal
6. **Link Posts** — 0.05% avg ER (lowest), 4.43% median ER when engaged, use comments for links
7. **Facebook Live** — 35–50% organic reach, 6× engagement, most underutilized format

**Added:** Platform context (3.07B MAU, Pages vs Groups 10–15× multiplier, algorithm shift to interest graph, 2025–2026 changes), benchmarks summary table (26 metrics), algorithm ranking signal hierarchy (7 factors), format performance ranking table, "What to Avoid" section (11 pitfalls), industry variations table, cross-format strategy matrix, content waterfall framework

**Sources:** Buffer (52M+ posts, Mar 2026), Socialinsider (25M posts, Mar 2026), SocialBee (9.3M posts, Jun 2026), Sprout Social (Mar 2026), FB Group Bulk Poster (Feb 2026), Net Influencer (Mar 2026), PostEverywhere (Feb 2026), ShortsIntel (Feb 2026), Apaya (Jun 2026), IQFluence (May 2026)

---

### `facebook/SKILL.md`
**Created** — New Facebook content skill:

- 7 formats with templates, rules, and anti-patterns per format
- Step 0 loads format reference for algorithm priorities, ER data, format spread
- Global rules: no engagement bait, no links in post body, reply to comments, authentic > polished
- Output format includes engagement strategy section
- Character limits per format

---

### `SKILL.md` (orchestrator)
**Patched** — 3 changes:

1. **Added `facebook` to Phase 2 (Content Creation)** — 7 formats listed with ER data
2. **Added `facebook/` to directory tree** — between `threads/` and `voice-builder/`
3. **Added 7 Facebook-specific rules** — format ER ranking, Pages vs Groups, reply effect, engagement bait penalty, link penalty, Reels exception, format spread note

---

### Top-level documentation files (NEW)
**Created** — These files are needed for the GitHub repo root:
- `README.md` — Project overview, all 6 platforms, quick start, skill table
- `CONTRIBUTING.md` — Contribution guidelines, development setup, PR guidelines
- `CHANGELOG.md` — Release-level changelog (this release: Facebook platform added)
- `LICENSE` — MIT license

---

**Date:** June 24, 2026
**Source research:** Deep Threads research via Fableous pipeline (10 sources, 52M+ posts across Buffer, SociaVault, Metricool, Teract, PostPlanify, AutoDM, MomentumHive)

---

## June 24, 2026 — Threads Deep Research Update (8 Formats)

### `references/bleeding-edge-formats.md`
**Patched** — Replaced Threads section with comprehensive 8-format deep research:

**Before:** Single "Image + Hot Take" format + basic benchmarks (1 format)
**After:** 8 data-backed formats with templates, benchmarks, algorithm hierarchy:

1. **Question Posts** — 6.14% ER, +62% vs platform avg, highest reply rate
2. **Hot Takes / Constructive Contrarian** — 5.87% ER, +55%, 1:3.5 reply-to-like ratio
3. **Video Content (Native)** — 5.55% ER, +96% vs text-only, 46% above platform avg
4. **Multi-Part Threads** — 4.92% ER, +30%, Zeigarnik effect + commitment bias
5. **Replies to Trending Topics** — 4.71% ER, +24%, +42% creator reply lift
6. **Image / Carousel** — 4.55% ER, +22%, 8x higher than Instagram carousels
7. **News Commentary** — 4.13% ER, +9%, 2.71% reply rate in Media niche
8. **Behind-the-Scenes (BTS)** — 2–5% ER, highest trust-building format

**Added:** Platform context (350M+ MAU, algorithm hierarchy table, nano-to-mega gap 5.4×, Connected Reach shift, declining ER trajectory 8.4%→3.8%), benchmarks summary table (16 metrics), content type performance table, niche performance table (11 niches), algorithm signal hierarchy, "What to Avoid" section (11 pitfalls)

**Sources:** Buffer (52M+ posts, Mar 2026), SociaVault Labs (18K accounts, May 2026), Teract (10,847 posts, Q1 2026), Metricool (1M+ accounts, Jan 2026), PostPlanify (45M+ posts, Apr 2026), Threadify (500 viral posts, Mar 2026), AutoDM (May 2026), MomentumHive (2026), TechCrunch (Apr 2025)

---

### `threads/SKILL.md`
**Patched** — Expanded from 3 formats to 8 formats:

1. **Step 0 expanded** — Now covers 8 formats ranked by ER, algorithm hierarchy, Connected Reach shift, hook quality (+73%), creator reply lift (+42%), optimal frequency (2-3x/day), spam threshold (6+ → -67%), nano-to-mega gap (5.4×), penalties list
2. **Step 2 format chooser expanded** — From 3 formats (A-C) to 8 formats (A-H): Question Posts, Hot Takes, Video, Multi-Part Threads, Replies to Trending, Image/Carousel, News Commentary, Behind-the-Scenes
3. **Format descriptions** — Each now includes engagement data, rules, and anti-patterns specific to that format

---

**Date:** June 24, 2026
**Source research:** Deep Twitter/X research via Fableous pipeline (27 sources, 52M+ posts across Buffer, SociaVault, Socialinsider, Metricool)

---

## June 24, 2026 — Instagram Deep Research Update (7 Formats)

### `references/bleeding-edge-formats.md`
**Patched** — Replaced Instagram section with comprehensive 7-format deep research:

**Before:** Single "Educational Carousel (10 slides)" format with outdated 9-10% ER claim (The Second Brain, Apr 2026)
**After:** 7 data-backed formats with templates, benchmarks, algorithm hierarchy:

1. **Educational Carousel (5–10 slides)** — 0.52–0.55% ER, 9x saves, 109% more engagement than Reels
2. **Short-Form Reel (15–90s)** — 0.50–0.52% ER, 30.81% reach, +15% YoY (only growing format)
3. **Collaborative Post** — 2.5x reach multiplier, 15–25% follower growth
4. **Instagram Live (Collab)** — 8–12% ER for collabs vs 3–5% solo
5. **Instagram Stories** — 5.4% sticker ER, +88% replies YoY
6. **Instagram Notes** — 60-char DM inbox tool, growing YoY
7. **Single-Image Posts** — 0.35% ER, -45.98% YoY (structural decline)

**Added:** Platform context (4th year of declining ER, hierarchy: Saves > Shares > Comments > Likes), benchmarks summary table (18 metrics), format performance ranking table, "What to Avoid" section (8 pitfalls)

**Updated:** Cross-platform comparison table — Instagram ER corrected from 9-10% to 0.52-0.55% (reach-based)

**Sources:** Buffer (52M+ posts, Mar 2026), Metricool (24.3M posts, Jun 2026), Social Insider (Q1 2026), Dash Social (Q1 2026), UpGrow/Rival IQ (Jun 2026), CreatorFlow (Jun 2026), ContentDrips, Carouselli, Outfame, Crescitaly, Sked Social, Modern Comment, Storrito, Growth-onomics

---

## June 24, 2026 — Twitter/X Deep Research Update (8 Formats)

### `references/bleeding-edge-formats.md`
**Patched** — Replaced X/Twitter section with comprehensive 8-format deep research:

**Before:** Single "Argument Thread" format + 3 single tweet formats + basic benchmarks
**After:** 8 data-backed formats with templates, benchmarks, source citations:

1. **Thread (5–12 tweets)** — 42% of viral content, 58% completion rate, 8–12 tweets 47% better
2. **Single Text Tweet** — 30% higher ER than video, baseline format
3. **Native Video (<60s)** — 2.4× total engagement, 10× external video links
4. **GIF Post** — +55% engagement (Twitter-internal study, 3.7M users)
5. **Image Post** — moderate boost, original images favored over stock
6. **Poll** — high engagement/effort ratio
7. **X Article / Long-form** — Premium subscribers, limited data
8. **Reply / Comment** — growth hack, 50-like reply > original tweet for followers

**Added:** Platform context section (median ER 0.10–0.12%, YoY decline 9%, text-vs-video paradox resolution), benchmarks summary table (15 metrics), "What to Avoid" section (7 platform-wide pitfalls)

**Sources:** Buffer (52M+ posts, Mar 2026), SociaVault (350K accounts, Apr 2026), Socialinsider (70M posts, Jan 2026), Metricool (39M posts, Jan 2026), PostEverywhere, ScheduleWave, OpenTweet, TweetArchivist, InformedClearly, WordStream, AI Free Forever, Sprout Social, Conbersa, AdLibrary, Improvado, PostWizard, Teract, GrowthTerminal, RecurPost

---

### `x-twitter/SKILL.md`
**Patched** — Updated to reflect 8-format research:

1. **Step 0 expanded** — Now covers text-vs-video paradox, GIF +55%, native video 10×, median ER, two ER metrics, algorithm signals (velocity, dwell time, bookmarks, negative feedback)
2. **Step 2 format chooser expanded** — From 4 formats (A-D) to 8 formats (A-H): Thread, Provocative Single Tweet, Story Tweet, Data Tweet, Native Video, GIF Post, Image Post, Reply/Comment
3. **Global rules updated** — Added text-first vs video optimization guidance, GIF engagement rule, native video rule, bookmark weighting, content half-life awareness
4. **Thread template updated** — Now 10-tweet structure (was argument-focused, now evidence-based with clear takeaways CTA)

---

**Date:** June 24, 2026
**Source research:** Deep Substack research via Fableous pipeline (94K posts + 3,230 notes + platform stats)

---

## June 24, 2026 — Substack Deep Research Update

### `references/bleeding-edge-formats.md`
**Patched** — Replaced Substack section with comprehensive 6-format deep research:

**Before:** Single "5-10 Minute Personal Narrative Edition" format with basic template
**After:** 6 data-backed formats with benchmarks:

1. **Long-Form Essay** — Title data from 94K posts (13-17 words optimal, +30% first-person, +60% negative framing), cover image mandatory (+81% penalty without), subtitle 6-10 words optimal
2. **Substack Notes** — 5 outperforming formats (Tactical Revelation, Named Behavior, Worldview Statement, Milestone Done Right, Post Link Done Right). Question marks cut conversion 35%. Pure text wins. 4:1 engagement gap from worldview consistency.
3. **Interview/Conversation** — Two-voice posts drive higher comment ratios, double audience exposure
4. **Video Post / Substack TV** — Platform priority, text context mandatory
5. **Podcast / Audio** — Dual distribution, text component mandatory
6. **Recommendations** — Drive 50% of new subscriptions

**Added:** Substack benchmarks table (14 metrics), growth funnel matrix, "What to Avoid" section with 10 specific pitfalls

**Sources:** Write • Build • Scale (94K posts, Jun 2026), Build to Launch (3,230 notes, Mar 2026), Best Writing (35 stats, Apr 2026), shno.co (newsletter stats 2026), beehiiv State of Newsletters 2026, Escape the Cubicle (Feb 2026), Reddit r/Substack

---

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
| `x-twitter` | New in Session 2; has own templates, not patched with Step 0 |
| `threads` | New in Session 2; has own templates, not patched with Step 0 |

---

## June 23, 2026 (Session 3) — Pipeline Execution + Save-to-File Pattern

### New File

#### `references/playwright-browser-reality.md`
- Documents what actually works with Playwright for social media research (tested June 2026).
- Key finding: Google blocks headless browsers. Use Bing instead.
- Reddit and X are JS-rendered SPAs that cannot be scrolled by any local headless tool.
- Installation: `pip3 install playwright && python3 -m playwright install chromium`
- Lightpanda explicitly not recommended (not packaged for pip/npm).

### Patched Skills

#### `niche-research/SKILL.md`
- **Added:** Step 4.5 — Save the research to a file. Asks user where to save, writes `raw-research-YYYY-MM-DD.md`, records path in memory.
- **Rewrote:** Prerequisites section. Now checks for Playwright via Python import test, offers to install if missing, documents honest capability table, removes Lightpanda option.

#### `insight-miner/SKILL.md`
- **Rewrote:** Output Artefacts section. Now asks user where to save, writes `insight-mine-YYYY-MM-DD.md`, records path in memory.

#### `content-matrix/SKILL.md`
- **Rewrote:** Step 3. Now asks user where to save, writes `content-matrix-YYYY-MM-DD.md`, records path in memory.

#### `post-writer/SKILL.md`
- **Rewrote:** Step 4. Now asks user where to save, writes `post-draft-YYYY-MM-DD.md`, records path in memory.

#### `post-scorer/SKILL.md`
- **Added:** Step 6 — Save the scorecard to a file. Asks user where to save, writes `post-score-YYYY-MM-DD.md`, records path in memory.

#### `SKILL.md` (orchestrator)
- **Added:** "The Save-to-File Principle" section documenting the pattern for all pipeline steps.
- **Updated:** Directory tree to include `playwright-browser-reality.md`.
- **Updated:** Pitfalls to include the save-to-file rule.

### Pipeline Execution

Full pipeline executed end-to-end for the first time:
1. ✅ voice-builder → `about-me.md` + `voice.md`
2. ✅ niche-research → `raw-research-2026-06-23.md` (8 themes)
3. ✅ insight-miner → `insight-mine-2026-06-23.md` (5 candidate insights, all passed pressure test)
4. ✅ content-matrix → `content-matrix-2026-06-23.md` (5 pillars × 8 formats = 40 post ideas)
5. ✅ post-writer → `post-draft-2026-06-23.md` ("Volume Tax" contrarian post)
6. ✅ post-scorer → `post-score-2026-06-23.md` (40/50 score)

### Files Created

| File | Path |
|------|------|
| about-me.md | `~/.hermes/projects/point-clear-advisory/about-me.md` |
| voice.md | `~/.hermes/projects/point-clear-advisory/voice.md` |
| raw-research-2026-06-23.md | `~/.hermes/projects/point-clear-advisory/content-research/` |
| insight-mine-2026-06-23.md | `~/.hermes/projects/point-clear-advisory/content-research/` |
| content-matrix-2026-06-23.md | `~/.hermes/projects/point-clear-advisory/content-research/` |
| post-draft-2026-06-23.md | `~/.hermes/projects/point-clear-advisory/content-research/` |
| post-score-2026-06-23.md | `~/.hermes/projects/point-clear-advisory/content-research/` |

---

## June 23, 2026 (Session 4) — Orchestrator + Sub-Skill Patches

### Patched Skills

#### `SKILL.md` (orchestrator)
- **Added:** "Changelog Tracking" section — documents the practice of updating CHANGELOG.md after every skill patch, with format and examples.
- **Added:** Pitfall — "When a skill needs a tool that isn't installed, offer to install it."
- **Updated:** Pipeline execution status — all 6 steps now complete.

#### `references/skill-suite-orchestration-pattern.md`
- **Added:** "Save-to-File Pattern" section — documents the pattern for all pipeline skills.
- **Added:** "Changelog Tracking" section — documents the CHANGELOG.md update practice.
- **Added:** Pitfall — "Don't silently fall back when a tool is missing."

### No New Files

This session only patched existing files. No new files created.

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

---

## June 24, 2026 (Session 5) — Threads Deep Research Update (8 Formats)

### Updated Files

#### `references/bleeding-edge-formats.md`
- Replaced Threads section (1 format → 8 formats)
- Added: Platform context, algorithm hierarchy, benchmarks summary, content type performance, niche performance table
- Updated: Cross-platform comparison table (Threads row)
- Updated: "What to Avoid (All Platforms)" — added engagement bait, inconsistent topics, over-posting, cross-posting penalties

#### `threads/SKILL.md`
- Step 0: Expanded from basic format reference to comprehensive data (8 formats, algorithm hierarchy, Connected Reach shift, penalties)
- Step 2: Expanded from 3 formats (A-C) to 8 formats (A-H) with engagement data and rules per format

#### `SKILL.md` (orchestrator)
- Updated workflow overview: Threads now lists all 8 formats with ER data
- Added 4 new Threads rules: 8-format ranking, algorithm hierarchy, Connected Reach shift, engagement bait penalty, spam threshold
- Added "Threads Quick Run" section for single-platform execution

#### `references/CHANGELOG.md`
- Added Session 5 entry documenting all changes

### No New Files

This session only patched existing files. No new files created.

---

## June 22, 2026 (Session 2) — Add X/Twitter + Threads Skills

### New Skills

#### `x-twitter/SKILL.md`
- Created from scratch (no X skill existed in upstream repo).
- 4 formats: Argument Thread (5–10 tweets), Provocative Single Tweet, Story Tweet, Data Tweet.
- Step 0 loads format reference for algorithm priorities (replies 27x–150x likes), text-first preference, content half-life.
- Templates extracted from FINAL.md Section 3.2.

#### `threads/SKILL.md`
- Created from scratch (no Threads skill existed in upstream repo).
- 3 formats: Image + Hot Take (recommended), Text-Only Opinion, Question Post.
- Step 0 loads format reference for image > text performance, engagement benchmarks, reply strategy.
- Templates extracted from FINAL.md Section 3.4.

### Updated Files

#### `references/bleeding-edge-formats.md`
- Added X/Twitter section: algorithm data, thread template, single tweet formats, benchmarks.
- Added Threads section: image-first data, template, benchmarks.
- Updated cross-platform comparison table from 3 to 5 platforms.

#### `SKILL.md` (orchestrator)
- Updated workflow overview from 16 to 18 skills.
- Added x-twitter and threads to Phase 2 (Content Creation).
- Added pitfalls: X/Threads are separate skills, no links in tweet 1, images required on Threads.
- Fixed duplicate/broken sub-skill directory tree listing.

### GitHub Repo
- Repo: https://github.com/iamnickthegeek/social-media-skills
- 3 commits: initial, add-x-threads, update README.
- 18 skills, 5 platforms, MIT license.
