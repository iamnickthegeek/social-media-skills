---
name: facebook
description: >-
  Write Facebook content across 7 formats: status posts, image posts, albums/carousels, Reels, native video, link posts, and Facebook Live. Optimized for Facebook's algorithm using deep engagement data (10 sources, 52M+ posts). Use this skill whenever the user says "write a Facebook post", "facebook content", "facebook Reel", "facebook carousel", "facebook Live", "FB post", "facebook status", or wants help writing any Facebook content. Also trigger when the user has content that needs to be adapted for Facebook's format.
---

# Facebook Content

## CRITICAL: Auto-start on load

The moment this skill triggers, go straight to Step 1. Do not summarise the skill. Do not explain what makes a good Facebook post. Jump to input gathering immediately.

## Step 0. Load format reference

Before writing, read `references/bleeding-edge-formats.md` from the social-media-skills directory. Use the Facebook section (7 formats) to inform:

- **Algorithm priorities:** Meaningful interactions (comments > likes) > relationship strength > content type preference > recency > completion rate > engagement velocity > page quality score
- **Format spread:** Less than 1pp between all formats (Buffer) — format matters less than content quality
- **Reels are the exception:** Only format to avoid the Q1 2026 engagement decline; 135% more reach than other formats
- **Status posts win on engagement:** 0.20% avg ER — highest of any format
- **Live wins on reach:** 35–50% organic reach, 6× engagement
- **Pages vs Groups:** 10–15× reach multiplier for Groups; use hybrid strategy
- **Reply effect:** +9.5% engagement lift when you respond to comments
- **Best posting time:** 8–11 a.m. weekdays
- **Engagement bait penalty:** Explicitly penalized since 2018, penalties increased
- **Link penalty:** External links suppressed by default; use comments
- **Format ER ranking:** Status (0.20%) > Albums (0.18%) > Images (0.15%) ≈ Reels (0.15%) ≈ Native Video > Live (6×) > Link (0.05%)
- **Key algorithm signals:** Comment velocity, swipe-through rate (carousels), watch time + completion (video), early engagement (first hour)

## Step 1. Gather inputs

If the user already pasted content or a topic in their message, use it and skip to Step 2.

Otherwise ask:

> What do you want to post about? Paste your topic, a link, notes, or raw ideas.

Wait for the input.

Then ask:

> What's the goal — engagement (comments), reach, clicks, or community building?

Wait for the answer.

Then ask:

> What format do you want, or should I recommend one?

## Step 2. Choose the format

Based on the topic, goal, and user's answer, recommend one of these 7 formats:

### Format A: Status Post (Text Update)

Best for: sparking conversation, asking opinions, sharing quick insights. Highest engagement rate on Facebook (0.20% avg). Generates the most comments per post.

```
[Hook — opinion, contrarian take, or question] (1–2 sentences)
[Context or personal experience] (1–3 sentences)
[Call to conversation — specific question or prompt]
```

**Rules:**
- 80–200 characters optimal; max 500
- Must end with a question or prompt (drives comments)
- No links in the post itself
- No engagement bait ("Like if you agree!")
- Conversational tone — feels like a person, not a brand

### Format B: Image Post (Single Photo)

Best for: stopping the scroll, likes, saves. Stable format — not declining like on other platforms. 44.8% of all high-performing Facebook content is images.

```
[Image: 1080×1080px or 1080×1350px (4:5 portrait)]

Caption:
[1–3 sentence hook adding context to the image]
[Optional: data point, story, or insight]
[Question or conversation prompt]
```

**Rules:**
- High-quality, original image (no generic stock)
- Caption adds context the image can't provide alone
- Include a question or CTA to drive engagement
- Lo-fi, authentic imagery outperforms polished brand visuals

### Format C: Album / Carousel (Multi-Image)

Best for: shares, dwell time, step-by-step content. Highest shares and views across all page sizes. Education vertical pulls 5.2% engagement.

```
[Image 1: Cover/hero — the most compelling visual]
[Image 2–4: Supporting details or steps]
[Image 5: CTA or summary]

Caption:
[Hook: "Here's what I learned from [experience]:" or "The complete guide to [topic]"]
[Brief context: 1–2 sentences]
[CTA: "Save this for later" or "Which step surprised you most? 👇"]
```

**Rules:**
- 3–7 images optimal (2 minimum, 10 maximum)
- Image 1 is the cover — must stop the scroll
- Each swipe counts as an engagement signal
- Mix photos, graphics, and short video clips within the same post
- End with a save or share prompt

### Format D: Reel (Short-Form Video, 15–90 seconds)

Best for: reach, discovery, new audience growth. Only format to avoid the Q1 2026 engagement decline. 135% more reach than other formats. 48% of consumers say Reels are #1 content type they interact with.

```
[0–1s: Text overlay with hook — bold claim or surprising statement]
[1–3s: "Here's why this matters..."]
[3–25s: Value delivery — one point per 3–5 seconds. Jump cuts, no dead air.]
[25–30s: CTA — "Save this" or "Follow for more"]
```

**Rules:**
- 9:16 vertical format (1080×1920)
- Text overlays mandatory (85% watched without sound)
- Hook in first 1–3 seconds — no intro
- Lo-fi, mobile-shot > polished brand video
- Same-day upload gets 50% more distribution
- No external links in Reels

### Format E: Native Video (Long-Form, 1–60 minutes)

Best for: deepening relationships with existing followers, tutorials, case studies. 25–40% organic reach. Completion rate is the dominant algorithm signal.

```
[0–3s: "In the next [X] minutes, you'll learn [specific outcome]"]
[3–30s: Context — why this matters, who it's for]
[30s–5min: Main content — 3–5 key points with examples]
[5–6min: Deeper dive or case study]
[Final 30s: Summary + CTA]
```

**Rules:**
- Upload natively (no YouTube links)
- 3–15 minutes optimal
- Custom thumbnail increases click-through 30–50%
- Captions mandatory
- Over 10 minutes needs chapter markers

### Format F: Link Post

Best for: driving external traffic (when clicks are the priority over engagement). Lowest engagement format (0.05% avg) — use strategically, not as default.

```
Caption:
[1–2 sentences: Why this link matters + what the reader will get]
["I'll drop the link in the comments 👇" — avoids algorithm penalty]
[Post link as first comment]
```

**Rules:**
- Links in caption get suppressed — use comments instead
- Custom Open Graph image (1200×630px) required
- Specific, quantified curiosity hook in caption
- Broken or slow-loading links get penalized

### Format G: Facebook Live (Real-Time Video)

Best for: real-time engagement, community building. Highest organic reach of any format (35–50%). 6× engagement vs non-live video. Members receive notifications.

```
[Pre-post: 1–2 hours before — "Going live at [time] to talk about [topic]"]

[0–2min: Greet early arrivals, set the agenda]
[2–10min: Main content — first key point with live examples]
[10–15min: Q&A break — read and answer comments]
[15–25min: Second key point or demonstration]
[25–30min: More Q&A, wrap-up, CTA]
[Post-live: Pin a comment with key resources]
```

**Rules:**
- Always pre-promote 1–2 hours before
- 20–40 minutes optimal (minimum 10, max 60)
- Respond to comments by name in real-time
- Bad audio kills live faster than bad video — invest in a microphone
- Save and repost the replay — it generates engagement for days

Tell the user which format you recommend and why. Let them pick or confirm.

## Step 3. Write the content

Write the post following the chosen format.

**Global rules for all Facebook content:**

- **Conversational tone** — feels like a person, not a marketing team
- **Always end with a question or CTA** — every format should drive engagement
- **No engagement bait** — "Like if you agree!" / "Share if you..." — explicitly penalized
- **No external links in post body** — use comments for links
- **Reply to comments** — +9.5% engagement lift; first hour is critical
- **Post when audience is active** — 8–11 a.m. weekdays baseline; check your own data
- **High-quality visuals** — blurry/low-res triggers double penalty
- **Authentic > polished** — lo-fi content outperforms over-produced brand content
- **Consider Groups** — 10–15× reach multiplier vs Pages for organic content
- **Native upload** — never post YouTube or external video links
- **Saves matter** — create reference-quality content users want to return to

**Character limits:**
- Status posts: 80–200 characters optimal, 500 max
- Captions: 120–350 characters optimal
- Reel captions: 100–200 characters
- Hashtags: 3–5 maximum (declining effectiveness)

Output the finished content inside a code block:

```
[FORMAT: Status Post / Image / Carousel / Reel / Native Video / Link / Live]

[content]

---

ENGAGEMENT STRATEGY:
- Primary signal this targets: [comments / saves / shares / watch time / reach]
- Best posting time: [time]
- Reply strategy: [how to engage in first hour]
- Cross-post to Groups: [yes/no + which groups]
```

## Step 4. Offer the next move

After the draft, ask:

> Want me to score this against Facebook performance benchmarks, adapt it for Groups, or ship it?

## Rules

- Always read the format reference (Step 0) before writing.
- Never use engagement bait ("Like if you agree!", "Share if you...").
- Never post external links in the post body — use comments.
- Every post must end with a question or CTA.
- British English unless voice.md specifies otherwise.
- No em dashes.
- If voice.md exists, match the user's tone and banned words.
- Plan before writing. Never skip Step 2.
