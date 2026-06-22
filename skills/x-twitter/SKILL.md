---
name: x-twitter
description: >-
  Write X/Twitter content — conversation threads, provocative single tweets, and reply-driven posts optimized for X's algorithm. Uses the Argument Thread template and current engagement data. Use this skill whenever the user says "write an X thread", "twitter thread", "tweet about", "X post", "tweet draft", "twitter content", or wants help writing any X/Twitter content. Also trigger when the user has content that needs to be adapted for X's format.
---

# X/Twitter Content

## CRITICAL: Auto-start on load

The moment this skill triggers, go straight to Step 1. Do not summarise the skill. Do not explain what makes a good tweet. Jump to input gathering immediately.

## Step 0. Load format reference

Before writing, read `references/bleeding-edge-formats.md` from the social-media-skills directory. Use the X/Twitter section to inform:
- Algorithm priorities (replies weighted 27x–150x more than likes)
- Text-first content outperforms video by 30% in distribution
- Optimal thread length (5–10 tweets)
- Content half-life (50% visibility lost every 6 hours)
- Grok sentiment analysis rewards constructive, nuanced content

## Step 1. Gather inputs

If the user already pasted content or a topic in their message, use it and skip to Step 2.

Otherwise ask:

> What do you want to tweet about? Paste your topic, a link, notes, or raw ideas.

Wait for the input.

Then ask:

> Thread or single tweet?

Wait for the answer.

## Step 2. Choose the format

Based on the topic and user's goal, recommend one of these formats:

### Format A: The Argument Thread (5–10 tweets)

Best for: contrarian takes, industry analysis, correcting misconceptions, thought leadership.

```
TWEET 1 — THE PROVOCATIVE OPENING (NO link, NO image, NO video)
  "[Strong, specific claim]. Here's why:"
  or
  "I've [done X / studied Y] for [Z years]. What nobody tells you:"
  → Must be a statement someone will want to agree with OR argue with. Neutral takes die.

TWEET 2 — NAME THE MISCONCEPTION
  "Most people think [common belief]. Here's why that's wrong:"
  → Frames the thread as correcting a widespread error.

TWEETS 3–7 — THE EVIDENCE (one point per tweet)
  Each tweet:
  • States one piece of evidence, example, or story
  • Is self-contained (readable on its own)
  • Builds toward the conclusion
  • Alternates between data/example and personal experience

TWEET 8 — THE COUNTERARGUMENT
  "Now, the counterargument: [acknowledge the other side]. And here's where it's right: [one point]. But here's where it falls short: [one limitation]."
  → Builds trust. Invites opposing views to engage.

TWEET 9 — THE SYNTHESIS
  "The real insight isn't [surface take]. It's [deeper principle]."
  → This is the quotable tweet. The one people screenshot.

TWEET 10 — THE REPLY BAIT
  "What's your experience with [topic]? I'm genuinely curious — especially if you disagree."
  → Explicit invitation to reply. Replies are the #1 algorithmic signal.
```

### Format B: The Provocative Single Tweet

Best for: hot takes, bold claims, conversation starters.

```
"[Specific, arguable claim]."

Rules:
- No links in the tweet (kills distribution)
- No hashtags (kills distribution)
- Must be something someone would quote-tweet to agree OR disagree with
- 280 characters max, but shorter is better (under 100 chars for max retweetability)
- End with a statement, not a question (questions dilute the claim)
```

### Format C: The Story Tweet

Best for: personal anecdotes, case studies, lessons learned.

```
"[Specific moment] — [time/place context]."

"[What happened. 2–3 sentences, present tense, cinematic.]"

"[The unexpected twist or realization.]"

"[The lesson, stated as a universal principle. One sentence.]"

Rules:
- First line is the hook — must create a "wait, what happens next?" feeling
- Write in present tense for immediacy
- The lesson at the end must be earned by the story, not tacked on
```

### Format D: The Data Tweet

Best for: research findings, statistics, industry data.

```
"[Surprising data point]."

"[Context for why this matters — 1–2 sentences.]"

"[Source citation — link or named source.]"

"[One sentence: what this means for the reader.]"

Rules:
- Lead with the most surprising number
- Always cite the source
- Make the implication explicit — don't make the reader do the work
```

Tell the user which format you recommend and why. Let them pick or confirm.

## Step 3. Write the content

Write the thread or tweet following the chosen format.

**Global rules for all X content:**
- No links in tweet 1 of a thread (kills distribution)
- No hashtags (they don't help on X)
- Every tweet in a thread must be readable on its own
- Alternate between short punchy tweets and slightly longer ones for rhythm
- The first tweet is everything — if it doesn't stop the scroll, nothing else matters
- Reply bait is not optional — every thread needs a reply-driving final tweet
- Text-first: do not suggest images or video unless the user specifically asks

**Character limits:**
- Single tweet: 280 characters max (aim for under 100 for retweetability)
- Thread tweets: 280 characters each, but vary length for readability

Output the finished content inside a code block:

```
TWEET 1:
[content]

TWEET 2:
[content]

...

---

TOTAL: [X] tweets
ESTIMATED READ TIME: [X] minutes
```

For single tweets, output just the tweet text in a code block.

## Step 4. Offer the next move

After the draft, ask:

> Want me to score this against X performance benchmarks, adapt it for Threads, or ship it?

## Rules

- Always read the format reference (Step 0) before writing.
- Never put links in the first tweet of a thread.
- Never use hashtags on X.
- Every thread must end with reply bait.
- British English unless voice.md specifies otherwise.
- No em dashes.
- If voice.md exists, match the user's tone and banned words.
- Plan before writing. Never skip Step 2.
