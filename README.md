# Social Media Skills

Bleeding-edge social media content skills for [Hermes AI agent](https://hermes-agent.nousresearch.com/). Automates content creation across LinkedIn, Instagram, and Substack using current best-performing formats and engagement data.

## What This Is

A collection of 18 AI agent skills that work together as a content pipeline:

1. **Research** → Find trending stories in your niche
2. **Ideate** → Generate 32+ post ideas mapped to platforms
3. **Write** → Draft posts in your voice
4. **Format** → Apply platform-specific frameworks
5. **Score** → Evaluate drafts against real engagement data
6. **Design** → Create carousels, infographics, and graphics
7. **Analyze** → Review performance and get recommendations

## Skills

| Skill | Purpose |
|-------|---------|
| `analytics-dashboard` | LinkedIn Analytics → interactive dashboard + strategic analysis |
| `content-matrix` | 32+ post ideas from your pillars × 8 formats |
| `format-researcher` | Research top 10 formats per platform, filtered through your niche/ICP |
| `gemini-carousel` | Slide-by-slide LinkedIn carousel via Gemini |
| `gemini-infographic` | Hand-drawn whiteboard infographic via Gemini |
| `graphic-designer` | HTML/CSS graphics or AI-generated visuals |
| `hook-generator` | 6 clickbait hook variations for any topic |
| `newsletter-voice` | Newsletter-specific voice profile |
| `niche-research` | Surface 20 trending stories from the last 7 days, with source lens tagging (Current News, Historical Parallel, Viral Social, Community Candor, Thinker Framework, Pure Insight) and Insight Potential scoring |
| `pinned-comment` | LinkedIn pinned comments + image prompts |
| `post-formatter` | Framework-based post formatting (PAS, AIDA, BAB, STAR, SLAY) |
| `post-scorer` | Score posts against real engagement data |
| `post-writer` | Draft posts in your voice |
| `profile-optimizer` | LinkedIn profile rebuild for conversions |
| `quote-post` | Quote graphic posts for LinkedIn |
| `reels-scripting` | Instagram Reel scripts from newsletter content |
| `facebook` | Facebook content — status posts, images, albums/carousels, Reels, native video, link posts, FB Live |
| `threads` | Threads content — image-first hot takes, opinionated text |
| `voice-builder` | Personalised voice profile from writing samples |
| `x-twitter` | X/Twitter content — threads, single tweets, stories, data |

## Quick Start

### Install

Copy the `skills/` directory into your Hermes skills folder:

```bash
cp -r skills/* ~/.hermes/skills/social-media-skills/
```

Or clone the repo into a subdirectory:

```bash
git clone https://github.com/iamnickthegeek/social-media-skills.git
cp -r social-media-skills/skills/* ~/.hermes/skills/social-media-skills/
```

### Required Setup (One-Time)

1. **Voice** — Run `voice-builder` to create your voice profile
2. **Newsletter Voice** — Run `newsletter-voice` if you publish a newsletter
3. **Profile** — Run `profile-optimizer` to rebuild your LinkedIn profile

### Weekly Content Batch

1. `niche-research` → Find trending stories (scans Reddit, X, Google across 8 query patterns, tags each item with source lenses)
2. `content-matrix` → Generate post ideas
3. `post-writer` or `post-formatter` → Draft posts
4. `post-scorer` → Evaluate before publishing
5. `gemini-carousel` or `graphic-designer` → Create visuals
6. `analytics-dashboard` → Review performance monthly

## Bleeding Edge Formats

Format data and engagement benchmarks are maintained in `skills/references/bleeding-edge-formats.md`. This single file is the source of truth — update it when new research comes out and all skills pick up the changes automatically.

Last research update: **June 2026**

## Platforms

| Platform | Formats | Primary Skill | Key Benchmark |
|----------|---------|---------------|---------------|
| **LinkedIn** | 3 | `post-writer`, `gemini-carousel` | PDF Carousel 6.60% ER |
| **Instagram** | 7 | `reels-scripting`, `graphic-designer` | Carousels 0.52% ER |
| **Facebook** | 7 | `facebook` | Status Posts 0.20% ER, Live 35–50% reach |
| **X/Twitter** | 8 | `x-twitter` | Threads 42% of viral content |
| **Threads** | 8 | `threads` | Questions 6.14% ER |
| **Substack** | 6 | `newsletter-voice` | 44% avg open rate |

## Based On
Originally forked from [charlie947/social-media-skills](https://github.com/charlie947/social-media-skills). Customised with:

- Shared reference file for format data (`references/bleeding-edge-formats.md`)
- Step 0 loading in each content-generation skill
- Facebook platform added (7 formats, 10 sources, 52M+ posts)
- Cross-platform comparison updated to 6 platforms

## License

MIT
