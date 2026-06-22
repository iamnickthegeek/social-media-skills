---
name: format-researcher
description: >-
  Research the top 10 highest-performing content formats per platform, filtered through the user's specific niche, ICP, and business context. Produces a personalised format guide (my-formats.md) that all content skills reference. Use this skill whenever the user says "research my formats", "find what's working on [platform]", "what content should I post", "format research", "what formats work for my niche", or wants data-backed format recommendations tailored to their business. This is an optional Phase 0.5 step — run before the regular content workflow.
---

# Format Researcher

## CRITICAL: Auto-start on load

The moment this skill triggers, go straight to Step 1. Do not summarise the skill. Do not explain the research methodology. Jump to input gathering immediately.

## Step 1. Gather business context

Before researching anything, you need to understand the user's business. Ask these questions in order:

### 1a. Niche and positioning

> What's your niche or industry? Be specific — "B2B SaaS marketing" not just "marketing."

> What's your unique angle or positioning in that niche? What makes your perspective different?

> Who's your ideal customer/audience? Describe them — role, company size, what they care about, what problem they're trying to solve.

### 1b. Platforms

> Which platforms are you actively posting on or planning to post on? (LinkedIn, X/Twitter, Instagram, Threads, Substack, TikTok, YouTube, Pinterest, other)

> For each platform, what's your current following size and posting frequency?

### 1c. Content goals

> What's the primary goal of your content? (Lead generation, authority building, audience growth, community building, direct sales, newsletter growth, other)

> What type of content do you currently create? What's working? What isn't?

Wait for all answers before proceeding.

## Step 2. Confirm and scope

Summarise what you've learned:

> Here's what I've got:
> - **Niche:** [their niche]
> - **ICP:** [their audience]
> - **Platforms:** [list]
> - **Goal:** [their goal]
>
> I'll research the top 10 content formats for each platform, then filter them to recommend the 3–5 best fits for YOUR niche and audience. This will take a few minutes per platform.
>
> Ready to start?

Wait for confirmation.

## Step 3. Research each platform

For EACH platform the user selected, run a deep research pass using this exact prompt:

```
Deep research task: I need a comprehensive, data-backed analysis of the TOP 10 highest-performing content formats on [PLATFORM] as of mid-2026.

For EACH of the 10 formats, provide:

1. FORMAT NAME and DESCRIPTION
   - What does this format look like in practice?
   - What's the ideal structure/template?
   - How long should it be (duration, word count, slide count)?

2. ENGAGEMENT DATA
   - Average engagement rate / impressions / saves / shares
   - How it compares to other formats on the same platform (rank it)
   - Source citations (dated, from 2025–2026)

3. WHY IT WORKS (algorithmic / psychological / behavioural)
   - What signals does the algorithm reward?
   - What psychological principle makes it effective?
   - What viewer behaviour does it trigger?

4. TEMPLATE / FILL-IN-THE-BLANKS
   - A reusable template with specific character counts, timing, structure

5. 3 REAL EXAMPLES (if available)
   - Link to or describe real posts that crushed with this format
   - Why specifically did they work?

6. WHAT TO AVOID
   - Common mistakes that kill performance
   - Format-specific pitfalls

Rank all 10 formats by engagement performance (highest first). Use structured markdown with clear sections, data tables where possible, and source URLs.

Search sources: Buffer State of Social 2026, platform algorithm updates 2025–2026, [PLATFORM] engagement benchmarks 2026, Socialinsider [PLATFORM] 2026, Metricool [PLATFORM] 2026, platform official engineering/blog posts.

Prioritise: data over opinions, recent sources (2025–2026), large-scale analyses over anecdotal. Focus ONLY on [PLATFORM]. Go deep, not broad.
```

Save each platform's raw research to `research-[platform]-formats.md` in the project.

## Step 4. Filter and recommend

For each platform, review the top 10 formats through the lens of the user's specific niche, ICP, and goals. Recommend the **top 3–5 formats** that are the best fit.

For each recommended format, explain:
- **Why it fits their niche:** How does this format align with their industry/audience?
- **Why it fits their ICP:** What does their ideal customer engage with?
- **Why it fits their goal:** How does this format drive leads/authority/growth for their specific situation?
- **Effort vs. reward:** How much production effort does it require vs. expected return?

For formats that DON'T make the cut, briefly explain why (e.g., "Requires video production — skip until you have a creator" or "Better for B2C audiences — your ICP is B2B").

## Step 5. Write my-formats.md

Create `my-formats.md` in the project root. This is the user's personalised format guide that all content skills will reference.

Structure:

```markdown
# My Content Formats — [Niche]

> **Niche:** [their niche]
> **ICP:** [their audience description]
> **Goal:** [their goal]
> **Platforms:** [list]
> **Last researched:** [date]
> **Next review:** [date + 3 months]

---

## LinkedIn

### Recommended Formats (ranked)

#### 1. [Format Name]
- **Why it fits:** [specific to their niche/ICP]
- **Engagement:** [data]
- **Effort:** [low/medium/high]
- **Template:** [link to full template below]
- **Frequency:** [how often to post this]

[Repeat for each recommended format]

### Full Templates

[Detailed template for each recommended format]

### Formats to Avoid (and why)

[Formats from the top 10 that don't fit, with reasons]

---

## X/Twitter

[Same structure]

---

## Instagram

[Same structure]

---

## Threads

[Same structure]

---

## Substack

[Same structure]

---

## How to Update This File

1. Re-run the format-researcher skill every quarter (or when platform algorithms change significantly)
2. Add your own formats as you discover what works for your audience
3. Remove formats that stop performing
4. Update engagement data as you gather your own analytics
```

## Step 6. Hand off to the workflow

After saving `my-formats.md`, tell the user:

> Your personalised format guide is ready at `my-formats.md`. Here's the summary:
>
> **LinkedIn:** [X] recommended formats — top pick: [format name]
> **X/Twitter:** [X] recommended formats — top pick: [format name]
> **Instagram:** [X] recommended formats — top pick: [format name]
> **Threads:** [X] recommended formats — top pick: [format name]
> **Substack:** [X] recommended formats — top pick: [format name]
>
> All content skills will now reference this guide when generating content for you.
>
> **Next step:** Run `niche-research` to find trending stories in your niche, then `content-matrix` to generate post ideas. Or say "run my social media workflow" to start the full pipeline.

## Rules

- Always gather full business context (Step 1) before researching. Never skip this.
- Research each platform separately for maximum depth.
- Filter recommendations through the user's specific niche/ICP — generic "top 10" lists are not enough.
- Save raw research files (`research-[platform]-formats.md`) for reference.
- `my-formats.md` is the deliverable — everything else is working files.
- Recommend 3–5 formats per platform, not all 10. Quality over quantity.
- Update the "Next review" date to 3 months from today.
- British English unless voice.md specifies otherwise.
- No em dashes.
