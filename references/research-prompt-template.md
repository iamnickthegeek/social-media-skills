# Research Prompt: [PLATFORM] Top 10 Content Formats — June 2026

## Context

**Researcher profile:** Premium LinkedIn/X ghostwriter for digital marketing agency owners and senior professionals (G20 nations, $1M–$10M revenue). Brand new venture — zero previous clients, no anecdotal data. All format recommendations must be backed by real engagement data, not personal experience.

**Content methodology:** Newsletter-first (Substack), then atomize into LinkedIn, X, Threads, Facebook. The primary content engine is a weekly Substack newsletter that gets broken down into platform-native formats.

**Target audience:** Digital marketing agency owners and senior professionals. G20 nations. $1M–$10M annual revenue. They're busy, skeptical, results-oriented. They don't have time to write but have deep expertise worth sharing.

**What to research:** The TOP 10 highest-performing content formats on [PLATFORM] as of mid-2026. Focus on formats that:
- Work for B2B / professional services / agency owners
- Can be derived from or inspired by newsletter content
- Don't require a large existing following to gain traction
- Are backed by real engagement data (not theory)

## Per Format — Required Data

For EACH of the 10 formats, provide:

### 1. Format Name and Description
- What does this format look like in practice?
- What's the ideal structure/template?
- How long should it be (duration, word count, slide count)?
- Can this format be atomized from a newsletter? (yes/no + how)

### 2. Engagement Data
- Average engagement rate / impressions / saves / shares / reach
- How it compares to other formats on the same platform (rank it)
- Source citations (dated, from 2025–2026)
- Data specific to B2B / professional services if available

### 3. Why It Works (Algorithmic / Psychological / Behavioural)
- What signals does the algorithm reward for this format?
- What psychological principle makes it effective?
- What behaviour from viewers does it trigger?
- Why would this work specifically for a $1M–$10M agency owner's audience?

### 4. Template / Fill-in-the-Blanks
- A reusable template the user can fill in with their own content
- Include specific character counts, timing, structure
- Show how to adapt this from a newsletter section

### 5. 3 Real Examples
- Link to or describe real posts that crushed with this format
- Why specifically did they work?
- Are these from B2B / professional services creators? (preferred)

### 6. What to Avoid
- Common mistakes that kill performance
- Format-specific pitfalls
- What doesn't work for B2B / agency owner audiences

## Output Format

Number all 10 formats. Rank them by engagement performance (highest first). Use structured markdown with clear sections, data tables where possible, and source URLs.

At the top, include a **"Strategic Insights"** subsection with:
- Non-obvious patterns across the top 10 formats
- How these formats connect to the newsletter-first methodology
- Which formats are easiest to atomize from a Substack edition
- Any format combinations that amplify each other

## Search Sources

Prioritise: Buffer State of Social 2026, platform algorithm updates 2025–2026, [PLATFORM] engagement benchmarks 2026, top performing [PLATFORM] posts analysis, Socialinsider [PLATFORM] 2026, Metricool [PLATFORM] 2026, platform official engineering/blog posts, Hootsuite annual report 2026, Sprout Social index 2026.

Prioritise: data over opinions, recent sources (2025–2026), large-scale analyses over anecdotal, B2B-specific data over general consumer data.

Focus ONLY on [PLATFORM]. Go deep, not broad.

## Fableous Orchestration Instructions

This research task runs through the Fableous 6-stage pipeline:

**Deliverable Type:** Reference Document (comprehensive, structured, personalised per platform)

**Model:** Single-model flatline — all stages run on the same model (the user's active model). No config cycling needed.

**Pipeline:**
1. **Research** (async) — Run the search prompt above. Gather sources, extract claims, verify URLs. Save raw research to `research-[platform]-raw.md`.
2. **Plan** (async) — Classify the top 10 formats, identify which fit the user's niche (B2B agency owners), plan the output structure. Save plan to `plan-[platform].md`.
3. **Implement** (sync) — Write the full formatted output with all 10 formats, templates, examples, and strategic insights. Save to `implement-[platform].md`.
4. **Verify** (sync) — Check all claims have sources, all 10 formats are present, templates are complete, data is dated 2025–2026. Save corrections to `verify-[platform].md`.
5. **Critique** (sync) — Independent review: Are the top 10 actually the top 10? Are recommendations specific enough for a $1M–$10M agency owner? Are newsletter-atomization paths clear? Save critique to `critique-[platform].md`.
6. **Consolidate** (sync) — Read all stage outputs. Apply fixes. Produce single canonical `formats-[platform]-2026.md`.

**Verification Gates:**
- Stage 1: Minimum 5 sources fetched and read, all URLs verified
- Stage 2: Deliverable type classified, all 10 formats identified with niche-fit rationale
- Stage 3: All 10 formats have complete data (engagement, template, examples, pitfalls)
- Stage 4: Every claim has a source citation, no undated data
- Stage 5: Critique addresses niche-fit, newsletter-atomization, and actionability
- Stage 6: Single canonical file, all fixes applied, "Version & Caveats" header present

**Replanning Triggers:**
- T1: Fewer than 3 sources found → add extended research stage
- T3: Task more complex than expected (e.g., platform has 15+ viable formats) → expand to top 15
- T6: Critique finds more than 3 critical weaknesses → add fix stage before consolidate

**Work Log:** Maintain `WORK_LOG.md` in the project directory. Read it at the start of any continuation session.
