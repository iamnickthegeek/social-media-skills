---
name: social-media-skills
description: >-
  Top-level orchestrator for the social-media-skills suite. Use this skill when the user wants to run a full social media content workflow — from voice onboarding through content generation to publishing and analytics. Trigger phrases: "social media workflow", "generate my social content", "run my social media", "create content for my platforms", "social media batch", or any request that involves multiple social platforms. This skill sequences sub-skills in the correct order and handles one-time-per-platform setup vs per-batch recurring work.
---

# Social Media Skills — Orchestrator

This is the top-level orchestrator for the social-media-skills suite. It sequences all sub-skills in the correct order for a "newsletter-first" content pipeline.

## Workflow Overview

```
0. FORMAT RESEARCH (once, optional) → format-researcher
1. VOICE (once)          → voice-builder
2. NICHE RESEARCH        → niche-research
3. CONTENT IDEATION      → content-matrix
4. POST WRITING          → post-writer
5. X/TWITTER CONTENT     → x-twitter
6. THREADS CONTENT       → threads
7. POST FORMATTING       → post-formatter
8. POST SCORING           → post-scorer
9. HOOK GENERATION       → hook-generator
10. QUOTE POST            → quote-post
11. PINNED COMMENT         → pinned-comment
12. CAROUSEL             → gemini-carousel
13. INFOGRAPHIC          → gemini-infographic
14. GRAPHIC DESIGN       → graphic-designer
15. PROFILE OPTIMIZER    → profile-optimizer (per-platform, periodic)
16. REELS SCRIPT         → reels-scripting (Instagram/TikTok)
17. NEWSLETTER VOICE     → newsletter-voice
18. ANALYTICS            → analytics-dashboard
```

## Execution Phases

### Phase 0.5 — Format Research (Optional, Once)

Run this **once** (or quarterly) to build a personalised format guide:

| Skill | What it does | When |
|-------|-------------|------|
| `format-researcher` | Researches top 10 formats per platform, filters through your niche/ICP/goals, produces `my-formats.md` | First time, or when platform algorithms change significantly |

**Trigger:** User says "research my formats" or "find what's working for my niche."

**Output:** `my-formats.md` in the project root — a personalised format guide that all content skills reference.

**Why this matters:** Generic format lists don't account for your specific niche, audience, or goals. A B2B SaaS founder and a fitness coach need completely different formats even on the same platform. This step tailors everything to YOUR business.

### Phase 0 — One-Time Per Platform Setup

Run these **once per platform** before any content batch:

| Skill | Platform | When |
|-------|----------|------|
| `voice-builder` | All | First time you use the suite on any platform |
| `newsletter-voice` | Newsletter/Substack | First time you publish a newsletter |
| `profile-optimizer` | LinkedIn | When you create or refresh your LinkedIn profile |

### Phase 1 — Per-Batch Research & Ideation

Run these **for each content batch** (e.g., weekly):

1. **`niche-research`** — Surface trending stories, competitor activity, audience questions in your niche.
2. **`content-matrix`** — Turn research into a content calendar of post ideas mapped to platforms.

### Phase 2 — Content Creation (per platform, per idea)

For each post idea from the matrix:

3. **`post-writer`** — Draft the post in your voice (LinkedIn, text posts).
4. **`x-twitter`** — Write X/Twitter threads, single tweets, story tweets, or data tweets.
5. **`threads`** — Write Threads posts (image-first hot takes, opinionated text).
6. **`post-formatter`** — Apply platform-specific formatting (line breaks, emoji placement, hashtags).
7. **`post-scorer`** — Score the draft against engagement heuristics. Iterate if below threshold.
8. **`hook-generator`** — Generate 6 hook variations for the post (for A/B testing on LinkedIn/Twitter).

### Phase 3 — Platform-Specific Derivatives

From a single post, generate:

7. **`quote-post`** — Turn a key insight into a quote card post.
8. **`pinned-comment`** — Write a pinned comment to drive engagement on LinkedIn posts.
9. **`gemini-carousel`** — Convert a post into a slide-by-slide LinkedIn carousel.
10. **`gemini-infographic`** — Convert a post into a hand-drawn whiteboard infographic.
11. **`graphic-designer`** — Generate a LinkedIn post graphic from the headline/visual concept.
12. **`reels-scripting`** — Convert a post into a script for Instagram Reels or TikTok.

### Phase 4 — Publishing & Analytics

13. **`analytics-dashboard`** — Review performance data from your social platforms, identify top-performing content, and feed insights back into Phase 1.

## How to Execute

### Full Pipeline (weekly batch)

When the user says "run my social media workflow" or "generate this week's content":

1. Check if `my-formats.md` exists. If not, offer to run `format-researcher` first.
2. Check if voice files exist. If not, invoke `voice-builder` first.
3. Run `niche-research` → `content-matrix` → loop Phase 2+3 for each post idea.
4. End with `analytics-dashboard` to review the previous week's performance.

### First-Time Setup

When the user says "set up my content system" or "I'm new to this":

1. Run `format-researcher` → produces `my-formats.md` (personalised format guide)
2. Run `voice-builder` → produces `about-me.md` and `voice.md`
3. Run `newsletter-voice` if they publish a newsletter
4. Run `profile-optimizer` for LinkedIn
5. Then proceed to the full pipeline

### Single-Platform Quick Run

When the user says "write a LinkedIn post about X" or "make a carousel from this article":

1. Load the relevant skill directly (e.g., `post-writer` → `post-formatter` → `post-scorer`).
2. Skip the research phase unless the user wants fresh ideas.

### Derivative Run

When the user says "turn this post into derivatives" or "make a carousel and infographic from this":

1. Take the source post content.
2. Run `gemini-carousel`, `gemini-infographic`, `graphic-designer`, `reels-scripting` in parallel.

## Sub-Skill Locations

All sub-skills live in this same directory (`social-media-skills/`):

```
social-media-skills/
├── SKILL.md                    ← this file (orchestrator)
├── analytics-dashboard/
├── content-matrix/
├── format-researcher/
├── gemini-carousel/
├── gemini-infographic/
├── graphic-designer/
├── hook-generator/
├── newsletter-voice/
├── niche-research/
├── pinned-comment/
├── post-formatter/
├── post-scorer/
├── post-writer/
├── profile-optimizer/
├── quote-post/
├── reels-scripting/
├── threads/
├── voice-builder/
├── x-twitter/
└── references/
    ├── bleeding-edge-formats.md
    ├── CHANGELOG.md
    ├── research-prompt-template.md
    └── skill-suite-orchestration-pattern.md
```

## Pitfalls

- **Don't skip `format-researcher` for first-time setup.** Generic formats won't fit your niche. Get personalised recommendations first.
- **Don't run `voice-builder` every batch.** It's a one-time setup. Check for existing voice files first.
- **Don't skip `post-scorer`.** It catches low-engagement drafts before publishing.
- **Don't create derivatives before the source post is scored above threshold.** Garbage in, garbage out.
- **`analytics-dashboard` requires an export file** from LinkedIn Analytics or equivalent. Have it ready.
- **`reels-scripting` is for short-form video only** — don't use it for LinkedIn text posts.
- **Keep `references/bleeding-edge-formats.md` current.** The 6 patched sub-skills load this file at runtime. Update it quarterly or when platform algorithms shift.
- **X/Twitter and Threads are separate skills.** Don't use `post-writer` for X/Threads content — use `x-twitter` and `threads` respectively.
- **X/Twitter: no links in tweet 1 of a thread.** It kills distribution. No hashtags either.
- **Threads: images outperform text.** Always suggest an image option. Text-only consistently ranks last.
- **`format-researcher` produces `my-formats.md` in the project root.** Don't move or rename it — content skills reference it automatically.
