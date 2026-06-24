---
name: insight-miner
description: >
  Extract genuine, non-obvious insights from source material (X posts, articles, newsletters,
  news stories), pressure-test them with research, and map them to awareness-stage × funnel-stage
  content angles. Slots between niche-research and content-matrix in the social-media-skills
  pipeline. Use when the user says "find the insight in this", "what's the real story here",
  "mine this for angles", "is this claim true", "pressure-test this idea", or when handing off
  from niche-research. Also trigger when the user pastes any source material and wants to find
  the insight worth writing about.
---

# Insight Miner

## CRITICAL: Auto-start on load

When this skill triggers, go straight to Step 1. Do not summarise the method. Do not explain the
theory. Start gathering input immediately.

## Purpose

Most content rehashes surface-level takes. This skill exists to find the insight BENEATH the
source material — the thing most readers would overlook but experts would notice — then verify
it holds up before anyone writes a word.

The pipeline:

```
Source Material → Extract Candidate Insights → Pressure-Test with Research →
Map to Awareness × Funnel Matrix → Output Verified Angles for content-matrix
```

## Frameworks Reference

### Schwartz's Stages of Awareness

| Stage | Description | Content Implication |
|-------|-------------|-------------------|
| Unaware | Doesn't know they have a problem | Lead with the problem, not the solution |
| Problem-aware | Knows they have a problem, not the solution | Diagnose, agitate, introduce category |
| Solution-aware | Knows solutions exist, not yours | Differentiate your approach |
| Product-aware | Knows you, hasn't bought | Overclose objections, prove ROI |
| Most-aware | Ready to buy, needs a nudge | Urgency, guarantee, direct CASHVERTISING |

### Life Force 8 (Cashvertising / Plsek)

Eight core motivational drivers:

1. Survival, enjoyment of life, life extension
2. Satisfaction of appetite
3. Freedom from fear and danger
4. Physical attractiveness
5. Comfort, luxury, ease
6. Social approval, status, pride
7. Protection and care of loved ones
8. Vicarious sexual experience / romantic success

These are the emotional entry points. Every insight should connect to at least one.

### Funnel Stages

| Stage | Question the prospect asks | Content type |
|-------|---------------------------|--------------|
| TOF (Top) | "Why should I care?" | Problem-awareness, trigger content |
| MOF (Middle) | "Why this solution?" | Comparison, differentiation, objection-handling |
| BOF (Bottom) | "Why should I trust you?" | Proof, case studies, guarantees, urgency |

## Step 1. Gather source material

Check what the user has:

- **If called from niche-research:** the source material is the research table. Ask the user
  which row(s) they want to mine for insights. Accept one or multiple rows.
- **If called directly:** ask the user to paste the source material (X post, article, newsletter,
  news story, or link). Accept URLs, raw text, or both.

If given a URL, fetch the full text using web_extract before proceeding.

## Step 2. Extract candidate insights

Run the following analysis on the source material. Output 3-5 candidate insights.

For EACH candidate insight, answer these questions:

### 2a. Hidden Assumption Extraction

Apply this prompt to the source material:

> "Read this text and point out the hidden assumptions, biases, or unspoken insights that most
> readers would overlook but experts would notice."

Be specific. Not "the author assumes X" but "the author assumes X, which is wrong/right
because Y, and the implication is Z."

### 2b. Insight Scoring

Score each candidate insight on three axes (1-5 each):

| Axis | What you're measuring | Score 1 | Score 5 |
|------|----------------------|---------|---------|
| **Novelty** | How overlooked is this? | Everyone says this | Almost nobody has noticed this |
| **Usefulness** | Can someone act on this? | Purely abstract | Immediately applicable |
| **Verifiability** | Can you prove or disprove it? | Purely opinion | Data-backed or falsifiable |

Minimum total score to proceed: **9/15**. Discard anything below that.

### 2b. Life Force Tagging

For each surviving insight, tag which Life Force driver(s) it connects to (1-8 from the
framework above). An insight can connect to multiple drivers. If it connects to none, it's
probably not emotionally resonant enough — flag this.

## Step 3. Pressure-test each surviving insight

For each insight that scored 9+, research whether it holds up:

### 3a. Evidence Search

Search for:
- Data or studies that support the claim
- Data or studies that contradict the claim
- Expert opinions on both sides
- Real-world examples that validate or invalidate it

Use web_search. Prioritise: data over opinions, recent sources (2024-2026), large-scale
analyses over anecdotal.

### 3b. Verdict

For each insight, assign one of:

| Verdict | Meaning | Action |
|---------|---------|--------|
| **CONFIRMED** | Evidence strongly supports it | Proceed to mapping |
| **PARTIAL** | Evidence supports some but not all | Proceed with caveats noted |
| **CONTESTED** | Genuine expert disagreement exists | Proceed — disagreement IS the content angle |
| **DEBUNKED** | Evidence contradicts it | Discard, or flip to "why people believe this" angle |
| **UNVERIFIABLE** | Insufficient data either way | Proceed only if novelty + usefulness are both 4+ |

Never present a debunked insight as true. If debunked, the content angle becomes "why this
common belief is wrong" — which is often more interesting anyway.

### 3c. Source Citation

Every insight that passes must have at least one source URL. No exceptions. If you can't
find a source, the insight doesn't pass.

## Step 4. Map to awareness × funnel matrix

For each verified insight, map it across the matrix. Not every cell needs filling — only the
cells where this insight genuinely produces a different angle.

Output a table:

```
| Funnel Stage | Unaware | Problem-Aware | Solution-Aware | Product-Aware | Most-Aware |
|---|---|---|---|---|---|
| TOF | [angle or —] | [angle or —] | [angle or —] | [angle or —] | [angle or —] |
| MOF | [angle or —] | [angle or —] | [angle or —] | [angle or —] | [angle or —] |
| BOF | [angle or —] | [angle or —] | [angle or —] | [angle or —] | [angle or —] |
```

Each cell that contains an angle should be a specific, concrete content idea — not a theme.
Good: "The 'best practice' that's actually costing you clients — and what to do instead."
Bad: "Challenge best practices."

Also tag each filled cell with its Life Force driver number(s).

## Step 5. Rank and recommend

From all the filled cells, rank the top 5 angles by:

1. Novelty score (from Step 2)
2. Emotional resonance (Life Force connection strength)
3. Funnel fit (does it match where the target audience actually is?)

For each top-5 angle, output:

```
### Angle [N]: [One-line headline]
- **Source insight:** [What the source material actually said]
- **Hidden assumption uncovered:** [What most readers miss]
- **Evidence:** [Verdict + key source]
- **Life Force driver(s):** [Number + name]
- **Awareness stage:** [Which stage this speaks to]
- **Funnel stage:** [TOF/MOF/BOF]
- **Content format suggestion:** [Carousel / text post / infographic / thread — based on
  bleeding-edge-formats.md if available]
```

## Step 6. Offer the next move

After presenting the top 5 angles, ask:

> Which angle do you want to develop? I can:
> - Hand it to **post-writer** to draft the full post
> - Feed it to **content-matrix** to build a full content calendar around it
> - Run **hook-generator** to create 6 hook variations for A/B testing
> - Run **insight-miner** again on a different source

## Output Artefacts

Save the full output (all steps) to a markdown file immediately after completing the analysis.

1. Check if a project directory already exists (e.g. `~/.hermes/projects/<project-name>/content-research/`). If found, ask:

   > I found a content-research directory at `<path>`. Should I save this as `insight-mine-YYYY-MM-DD.md` there, or somewhere else?

2. If no project directory exists, ask:

   > Where should I save this insight mine? Give me a directory path and I'll create it if needed. The filename will be `insight-mine-YYYY-MM-DD.md`.

3. Once the user confirms the path, write the file immediately. Include:
   - A "Source" section at the top with the original material or link
   - The date (DD/MM/YYYY)
   - All candidate insights and scores
   - Pressure test results with verdicts and source URLs
   - The awareness × funnel matrix
   - The top 5 ranked angles

4. After saving, confirm the full file path to the user.

5. Record the save location in memory so future insight-miner runs default to the same directory.

## Rules

- Never skip Step 3 (pressure-test). Unverified insights are just opinions.
- Never present a debunked claim as true. Flip it or discard it.
- Every surviving insight must have at least one source URL.
- If fewer than 3 insights score 9+ in Step 2, say so. Don't pad with weak material.
- If no insights pass the pressure test, tell the user directly: "This source doesn't hold
  up. Here's what I found instead..." and offer alternative angles from the debunked
  material.
- British English throughout. DD/MM/YYYY date format.
- Never use em dashes.
- Keep the repo generic. All niche/ICP/business-specific info comes from local voice files
  or the user's input, never hardcoded.
