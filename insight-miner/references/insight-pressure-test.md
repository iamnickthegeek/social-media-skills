# Insight Pressure-Test Methodology

## The Core Prompt

The extraction prompt that drives the entire skill:

> "Read this text and point out the hidden assumptions, biases, or unspoken insights that most
> readers would overlook but experts would notice."

This works because it forces the LLM out of summarisation mode and into analysis mode. It's
looking for what's BETWEEN the lines, not what's on them.

## What Counts as a Genuine Insight

Not everything the prompt returns is actually insightful. Filter for:

### Genuine insights:
- Challenge a widely-held belief with evidence
- Reveal a causal mechanism that's usually hidden
- Connect two things that seem unrelated
- Expose a metric or data point that contradicts the narrative
- Identify a second-order consequence nobody's discussing

### Not insights (discard these):
- Restatements of the obvious with fancier words
- Generic advice dressed up as revelation
- "Hidden assumptions" that aren't actually hidden
- Anything that boils down to "do good work and be consistent"

## Pressure-Test Decision Tree

```
Insight extracted
  │
  ├─ Can you search for evidence? ──NO──► Tag UNVERIFABLE
  │                                         │
  │                                         ├─ Novelty 4+ AND Usefulness 4+? ──YES──► Proceed with caveat
  │                                         │
  │                                         └─ Otherwise? ──► Discard
  │
  └─ YES ──► Search for supporting AND contraditing evidence
                │
                ├─ Strong support, no contradiction ──► CONFIRMED
                │
                ├─ Support with caveats ──► PARTIAL
                │
                ├─ Genuine expert disagreement ──► CONTESTED (this is gold)
                │
                └─ Evidence contradicts ──► DEBUNKED (flip the angle)
```

## Life Force 8 — Quick Reference for Tagging

When tagging insights to Life Force drivers, use these shortcuts:

| # | Driver | Keywords to look for |
|---|--------|---------------------|
| 1 | Survival / life extension | Risk, threat, urgency, "before it's too late" |
| 2 | Appetite satisfaction | Results, revenue, growth, "more of X" |
| 3 | Freedom from fear | Anxiety, uncertainty, "stop worrying about" |
| 4 | Physical attractiveness | Image, brand perception, "look professional" |
| 5 | Comfort / luxury | Ease, automation, "without the hassle" |
| 6 | Social approval | Status, recognition, "be seen as" |
| 7 | Protection of loved ones | Team, family, clients, "protect what matters" |
| 8 | Romantic / sexual | Attraction, charisma, confidence (rare in B2B) |

Most B2B marketing insights connect to drivers 2, 3, 5, and 6. Driver 1 works for
urgency-based content. Driver 7 works for "protect your team/clients" angles. Driver 4
is niche but works for personal brand content. Driver 8 is almost never appropriate in
professional services.

## Awareness × Funnel Matrix — When to Fill Each Cell

Not every insight fills every cell. Use this guide:

### TOF (Why should I care?)
- **Unaware:** Lead with the problem they don't know they have
- **Problem-aware:** Amplify the pain, show it's worse than they thought
- **Solution-aware:** Introduce a new category or approach they haven't considered
- **Product-aware:** Show them a gap in their current solution
- **Most-aware:** Create urgency to act now

### MOF (Why this solution?)
- **Unaware:** Don't go here — they're not ready for solution comparison
- **Problem-aware:** Introduce the category of solution
- **Solution-aware:** Differentiate your approach from alternatives
- **Product-aware:** Direct comparison, feature differentiation
- **Most-aware:** Overcome final objections

### BOF (Why should I trust you?)
- **Unaware:** Don't go here yet
- **Problem-aware:** Establish credibility through diagnosis accuracy
- **Solution-aware:** Show proof your approach works
- **Product-aware:** Case studies, ROI data, testimonials
- **Most-aware:** Guarantee, risk reversal, urgency

## Common Failure Modes

1. **The insight is just a reframe.** "Actually, churn isn't a retention problem — it's an
   onboarding problem." This might be true, but if everyone in the niche already knows it,
   it's not an insight. Check novelty score.

2. **The pressure test is too shallow.** One supporting article doesn't make it CONFIRMED.
   Look for multiple independent sources. Look for contradicting evidence actively, not just
   supporting evidence.

3. **The matrix is overfilled.** If every cell has an angle, you're probably being generic.
   Strong insights typically fill 4-8 cells meaningfully, not all 15.

4. **The Life Force tag is forced.** If you're straining to connect an insight to a driver,
   the insight might not be emotionally resonant. That's fine for analytical content, but flag
   it — the content will need a different kind of hook.

5. **Skipping the debunk flip.** When evidence contradicts the source, the instinct is to
   discard. Resist. "Why [popular belief] is wrong" is one of the highest-performing content
   formats. The debunk IS the insight.
