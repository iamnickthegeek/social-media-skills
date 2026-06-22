---
name: threads
description: >-
  Write Threads content — image-first hot takes, opinionated text posts, and reply-driven content optimized for Threads' algorithm. Uses the Image + Short Text template and current engagement data. Use this skill whenever the user says "write a threads post", "threads content", "post on threads", "threads hot take", or wants help writing any Threads content. Also trigger when the user has content that needs to be adapted for Threads' format.
---

# Threads Content

## CRITICAL: Auto-start on load

The moment this skill triggers, go straight to Step 1. Do not summarise the skill. Do not explain what makes a good Threads post. Jump to input gathering immediately.

## Step 0. Load format reference

Before writing, read `references/bleeding-edge-formats.md` from the social-media-skills directory. Use the Threads section to inform:
- Images outperform text on Threads (counterintuitive for a "text-first" platform)
- Video: highest median engagement (5.55%), images: 4.55%, text-only: last
- Text-only posts consistently rank lowest
- Instagram-to-Threads cross-integration means Instagram audience sees Threads posts first
- Optimal posting frequency: 3–7x/week plus daily reply activity
- Reply strategy is as important as posting

## Step 1. Gather inputs

If the user already pasted content or a topic in their message, use it and skip to Step 2.

Otherwise ask:

> What do you want to post about? Paste your topic, a link, notes, or raw ideas.

Wait for the input.

## Step 2. Choose the format

Based on the topic and user's goal, recommend one of these formats:

### Format A: The Image + Hot Take (Recommended)

Best for: opinions, reactions, data commentary, behind-the-scenes.

```
THE IMAGE (one of these):
  • A data chart or graph with one clear takeaway
  • A behind-the-scenes photo (desk, whiteboard, coffee + notebook)
  • A quote graphic (your own words in clean typography)
  • A screenshot (tweet, article headline, email, DMs)
  • A meme-format image with text overlay (only if on-brand)

THE TEXT (50–200 characters):
  "[Opinionated statement about the image]."
  or
  "This [chart/moment/conversation] changed how I think about [topic]. Here's the one thing I realized:"
  or
  "Just [did/experienced/saw] [specific thing]. The lesson: [one sentence]."

  → Must feel spontaneous and reactive, even when planned.
  → No hashtags. No links. Pure, unfiltered thought.
```

### Format B: The Text-Only Opinion

Best for: quick takes, questions, observations (when no image is available).

```
"[Opinionated statement — 100–200 characters]."

Rules:
- Must be arguable — someone should want to agree OR disagree
- No hashtags
- No links
- Shorter is better (under 100 chars ideal)
- End with a statement, not a question
- This format underperforms images — only use when no image is possible
```

### Format C: The Question Post

Best for: driving replies, community engagement, research.

```
"[Specific, genuine question about a topic your audience cares about]?"

Rules:
- Must be a real question you'd want answers to
- Specific questions outperform broad ones
- "What's your experience with [specific thing]?" beats "What do you think about [broad topic]?"
- No hashtags
- Expect 5–10x more replies than other formats
```

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
