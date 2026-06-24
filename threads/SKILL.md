---
name: threads
description: >-
  Write Threads content across 8 formats ranked by engagement: Question Posts (6.14% ER), Hot Takes (5.87%), Video (5.55%), Multi-Part Threads (4.92%), Replies to Trending (4.71%), Image/Carousel (4.55%), News Commentary (4.13%), and Behind-the-Scenes (2-5%). Uses current algorithm hierarchy and engagement data from bleeding-edge-formats.md. Use this skill when the user says "write a threads post", "threads content", "post on threads", "threads hot take", or wants help writing any Threads content. Also trigger when the user has content that needs to be adapted for Threads' format, or when they ask what content types perform best on Threads.
---

# Threads Content

## CRITICAL: Auto-start on load

The moment this skill triggers, go straight to Step 1. Do not summarise the skill. Do not explain what makes a good Threads post. Jump to input gathering immediately.

## Step 0. Load format reference

Before writing, read `references/bleeding-edge-formats.md` from the social-media-skills directory. Use the Threads section to inform:
- **8 formats** ranked by ER: Questions (6.14%), Hot Takes (5.87%), Video (5.55%), Multi-Part Threads (4.92%), Replies (4.71%), Image/Carousel (4.55%), News Commentary (4.13%), BTS (2-5%)
- **Algorithm hierarchy:** Replies (5/5) > Profile Views (5/5) > Reposts (4/4) > DM Sends (4/4) > Saves (3-4) > Likes (2) > Views (1)
- **Connected Reach shift:** Algorithm prioritizes existing followers + topic clustering over cold discovery
- **Hook quality:** +73% engagement for strong hooks (contradictions, specific numbers, direct challenges)
- **Creator reply lift:** +42% — highest of any platform; first 60 min determines distribution
- **Optimal frequency:** 2–3x/day; 6+ triggers spam detection (-67% reach)
- **Optimal times:** Tue–Thu, 8–10 AM & 6–8 PM local
- **Nano-to-mega gap:** 5.4× — largest across any platform; small accounts have massive advantage
- **Penalties:** Engagement bait, X-style negativity (-58%), external links, over-posting, inconsistent topics

## Step 1. Gather inputs

If the user already pasted content or a topic in their message, use it and skip to Step 2.

Otherwise ask:

> What do you want to post about? Paste your topic, a link, notes, or raw ideas.

Wait for the input.

## Step 2. Choose the format

Based on the topic and user's goal, recommend one of these 8 formats (ranked by engagement):

### Format A: Question Posts (Recommended — 6.14% ER)

Best for: driving replies, community engagement, starting conversations.

```
[One line of context or stakes that makes the question matter]

[Specific question — NOT yes/no, NOT too broad]

[Optional: "Here's what I've seen: [short take]" — as reply to yourself]
```

Rules: 50–200 chars. Must invite personal experience or a position. No hashtags. No links. NOT for B2B/SaaS audiences.

### Format B: Hot Takes / Constructive Contrarian (5.87% ER)

Best for: opinions, thought leadership, sparking debate.

```
Hot take: [specific, defensible claim]

[One piece of evidence or experience that grounds it]

[Optional: "Change my mind" — only if genuine]
```

Rules: 100–300 chars. Must be constructive (add evidence/angle), NOT negative or combative. No engagement bait.

### Format C: Video Content (5.55% ER)

Best for: education, demos, storytelling, visual proof.

```
[3-second hook: bold claim or visual surprise]
[Core content: 15–180 seconds of value]
[End: optional CTA]
```

Rules: Native upload only (no Reels cross-posts with watermarks). Captions mandatory. 30–90s optimal. MP4, 9:16 or 1:1.

### Format D: Multi-Part Threads (4.92% ER)

Best for: storytelling, frameworks, step-by-step guides.

```
Part 1: "[Number] [things] from [experience] 🧵 1/[N]: [insight]"
Middle: "[N]/[N]: [insight] [tension line for next part]"
Final: "[N]/[N]: [payoff] [specific question]"
```

Rules: 3–7 parts optimal. 100–300 chars per part. Each part must be scannable in 10–15s. No generic endings.

### Format E: Reply to Trending Topics (4.71% ER)

Best for: timely commentary, expertise signaling, follower acquisition.

```
[Your unique take — NOT "Great post!"]
[data point or experience that adds value]
[Optional: question]
```

Rules: 50–300 chars. Must add genuine substance. Post within 1–4 hours of trending topic. Reply to replies.

### Format F: Image / Carousel (4.55% ER)

Best for: data visualization, before/after, visual storytelling.

```
Single: [striking visual] + [50-200 char caption]
Carousel: [Hook slide] + [3-5 idea slides] + [CTA slide] + [caption]
```

Rules: 1:1 or 4:5 ratio. Cover slide determines swipe. Max 5 slides. 1080×1080px minimum.

### Format G: News Commentary (4.13% ER)

Best for: timely analysis, industry reactions, expertise positioning.

```
[News] just happened. Here's what [audience] needs to know:
[Your analysis]
[Implication — what next?]
```

Rules: 100–400 chars. Must be posted within 1–4 hours. Add analysis, don't just share news.

### Format H: Behind-the-Scenes (BTS) (2–5% ER)

Best for: authenticity, trust-building, follower connection.

```
[Photo/video of real moment]
[What's happening + why it matters]
[Optional: question]
```

Rules: 50–200 chars. Visual does the heavy lifting. Must feel authentic, not staged.

---

Tell the user which format you recommend and why. Let them pick or confirm.

## Step 3. Write the content

Write the post following the chosen format.

**Global rules for all Threads content:**
- Images are strongly preferred — text-only consistently ranks last
- Keep text under 200 characters (shorter = better)
- No hashtags (they don't help on Threads)
- No links in the post (kills distribution)
- Must feel spontaneous, even when planned
- Opinionated > neutral (neutral gets ignored)
- The post should feel like a DM to a friend, not a broadcast

**Image guidelines:**
- If the user doesn't have an image, suggest one of the 5 types from Format A
- Quote graphics with the user's own words perform well
- Behind-the-scenes photos build authenticity
- Screenshots of tweets/articles create "reactivity" signals

Output the finished content inside a code block:

```
IMAGE: [description of suggested image]

TEXT:
[the post text — 50–200 characters]

---

FORMAT: [Image + Hot Take / Text-Only Opinion / Question]
CHARACTER COUNT: [X]
```

## Step 4. Offer the reply strategy

After the draft, add:

> **Reply strategy:** Spend 10–15 minutes replying to other Threads posts in your niche today. Substantive replies (not "Great take!") build more visibility than original posts. 5–10 genuine replies per day is the real growth lever on Threads.

Then ask:

> Want me to adapt this for X/Twitter, score it, or ship it?

## Rules

- Always read the format reference (Step 0) before writing.
- Images outperform text — always suggest an image option.
- No hashtags on Threads.
- No links in posts.
- Keep text under 200 characters.
- British English unless voice.md specifies otherwise.
- No em dashes.
- If voice.md exists, match the user's tone and banned words.
- Always include the reply strategy reminder in Step 4.
- **Hot takes must be constructive** — add evidence/angle, not outrage. X-style dunking is penalized.
- **Engagement bait is penalized** — never use "Double post if you agree!" / "Tag someone" phrasing.
- **Posting frequency cap:** 2–3x/day optimal. 6+ triggers spam detection (-67% reach).
- **Reply velocity matters:** Be present for first 60 minutes after posting.
