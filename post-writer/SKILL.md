---
name: post-writer
description: >
  Write LinkedIn posts that match the user's voice system (about-me.md and voice.md). Use this skill whenever the user says "write a post", "draft a post", "LinkedIn post", "post about [topic]", "content idea", or wants help writing any LinkedIn content. Also trigger when the user pastes a context dump (notes, transcripts, bullet points) and wants it turned into a post. Always references the voice files in the project before writing. Always outputs the final post in a code block.
---

# Post Writer

## CRITICAL: Auto-start on load

The moment this skill triggers, go straight to Step 1. Do not summarise the skill. Do not explain what it does. Do not list the files it references. Jump to input gathering immediately.

## Step 0. Load format reference

Before writing, read `references/bleeding-edge-formats.md` from the social-media-skills directory. Use the LinkedIn section to inform:
- Current top-performing format (carousel is #1 — suggest it when appropriate)
- Hook type priorities (number-led, bold claim, contrarian)
- Optimal post length (180–250 words for text; 1,000–2,000 chars for conversational)
- Tone guidance (conversational/DM-like beats thought-leadership grandstanding)

## Step 1. Gather inputs

Check the project for about-me.md and voice.md. Read both. If either is missing, tell the user to run the Voice Builder skill first ("say build my voice"), then stop.

If both files exist, call AskUserQuestion with this exact JSON:

```json
[
  {
    "question": "What topic do you want to post about?",
    "header": "Topic",
    "multiSelect": false,
    "options": [
      {"label": "Paste a context dump", "description": "I have notes, transcripts, or raw ideas to turn into a post"},
      {"label": "I have a topic in mind", "description": "I will type the topic after this"},
      {"label": "Suggest topics for me", "description": "Based on my voice system, suggest 5 topics I should post about"}
    ]
  },
  {
    "question": "Do you have any reference posts you want me to use as structural inspiration?",
    "header": "References",
    "multiSelect": false,
    "options": [
      {"label": "No references", "description": "Write from scratch using my voice files only"},
      {"label": "I will paste examples", "description": "I have posts from other creators I want you to study first"},
      {"label": "Use my training posts", "description": "Reference the posts I used in the Voice Builder"}
    ]
  }
]
```

Based on the answers:
- "Paste a context dump": wait for the user to paste, extract the core idea, then proceed to Step 2
- "I have a topic in mind": wait for the user to type it, then proceed to Step 2
- "Suggest topics for me": read about-me.md topic pillars and voice.md, suggest 5 specific topics with a one-line angle for each, then use AskUserQuestion to let them pick one
- "I will paste examples": wait for reference posts, note the structural patterns, then proceed
- "Use my training posts": reference whatever posts are already in the project

## Step 2. Research and plan

Before writing, research the topic. Look for:
- Data points or statistics that support the angle
- Contrarian takes or surprising facts
- Real examples or case studies
- Common misconceptions to challenge

Then present a post plan. Call AskUserQuestion:

```json
[
  {
    "question": "Which angle works best for this post?",
    "header": "Angle",
    "multiSelect": false,
    "options": [
      {"label": "[Angle 1 name]", "description": "[One sentence describing the angle and hook]"},
      {"label": "[Angle 2 name]", "description": "[One sentence describing the angle and hook]"},
      {"label": "[Angle 3 name]", "description": "[One sentence describing the angle and hook]"}
    ]
  },
  {
    "question": "Which framework do you want?",
    "header": "Framework",
    "multiSelect": false,
    "options": [
      {"label": "PAS", "description": "Problem, Agitate, Solution"},
      {"label": "How-to list", "description": "Numbered steps or tips"},
      {"label": "Story to lesson", "description": "Personal story with a takeaway"},
      {"label": "Contrarian take", "description": "Challenge a common belief"}
    ]
  }
]
```

Fill in the actual angle options based on the topic research. Do not use placeholder text for the angle descriptions.

## Step 3. Write the draft

Write the post following these rules:
- Read voice.md for tone, rhythm, hook style, CTA style, and the absence patterns section (what the voice never does)
- Read about-me.md for audience and topic context
- Match the sentence length and paragraph rhythm from voice.md
- Avoid every banned word, structure, and pattern listed in voice.md's absence section
- Use the hook pattern that fits the chosen angle and aligns with the current top-performing hook types from the format reference
- End with the CTA style from voice.md
- When the topic suits a carousel, suggest it to the user (carousel is LinkedIn's #1 format)

Output the post inside a plain code block:

```
[The full post goes here with all line breaks and formatting exactly as it should appear on LinkedIn]
```

After the code block, add 2 to 3 sentences on why you chose this hook and structure, referencing specific patterns from voice.md.

## Step 3.5: Humanizer pass

After writing the draft (Step 3) and before presenting it to the user, run the draft through the `humanizer` skill. This strips AI-isms (significance inflation, promotional language, vague attributions, em dash overuse, filler phrases, signposting, etc.) and ensures the output reads as the practitioner wrote it, not as the LLM assembled it.

Use voice.md as the voice calibration sample when running the humanizer, so the rewrite matches the practitioner's documented register and cadence.

This is non-negotiable. No post is delivered to the user until it has been humanized.

## Step 4. Iterate and save

Ask the user:

> How does this feel? Tell me what to change, or say "ship it" and I will save the final version.

If the user gives feedback, revise and output a new code block. Maximum 3 revision rounds.

If the user says "ship it" or equivalent, save the final post to a markdown file:

1. Check if a `content-research/` directory already exists in the project (e.g. `~/.hermes/projects/<project-name>/content-research/`). If found, offer:
   > I found a content-research directory at `<path>`. Save the post there as `post-draft-YYYY-MM-DD.md`?

2. If no directory exists, ask:
   > Where should I save this post? Give me a directory path and I'll create it if needed. Filename will be `post-draft-YYYY-MM-DD.md`.

3. Once confirmed, write the file immediately with the full post content plus metadata (date, pillar, format, angle, source insight).

4. Confirm the file path to the user.

5. Record the save location in memory so future post-writer runs default to the same directory.

Then say:

> Post saved. Say "design a graphic" to create a visual, "build a carousel" to turn this into a carousel, or "score my post" to get feedback before publishing.

## Rules

- Always read about-me.md and voice.md before writing.
- Always read the format reference (Step 0) before writing.
- Always output posts in a plain code block.
- Never use em dashes in any post.
- British English unless voice.md says otherwise.
- Do not add hashtags unless voice.md explicitly uses them.
- Do not add engagement bait CTAs unless they appear in voice.md.
- Keep posts between 150 and 300 words unless the user requests otherwise.
- Plan before writing. Never skip Step 2.
- Always run the final draft through the humanizer skill before delivery (Step 3.5).
