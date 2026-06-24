---
name: niche-research
description: >
  Surface the 20 most relevant stories in a niche from the last 7 days using Claude for Chrome. Verified dates, real links, shareable angles. Claude drives the browser to scroll Reddit, X and run Google searches — exactly like a human researcher would. Use this skill whenever the user says "research my niche", "what's trending", "find stories", "this week's news", "content research", or drops a niche and asks what's happening in it. Requires the Claude for Chrome extension to be enabled for live browsing.
---

# Niche Research

## CRITICAL: Auto-start on load

When this skill triggers, go straight to Step 1. Do not summarise the research method.

## Prerequisites

This skill needs live browsing for the best research. Check what's available and offer to install if missing.

### Check browsing tools

Run these checks in order:

1. **Claude for Chrome extension** (preferred for Reddit/X). Check if the extension is available. If yes, use it. If not, skip to step 2.

2. **Playwright** (Python). Check if installed:
   ```
   python3 -c "from playwright.sync_api import sync_playwright; print('OK')"
   ```
   If this fails, offer to install:
   > I can install Playwright for better web research. It handles Google/Bing searches in a real browser and works well for most news sites. Reddit and X need login sessions, but everything else works. Install it? (Takes about 2 minutes, downloads ~115MB.)
   >
   > If yes, run: `pip3 install playwright && python3 -m playwright install chromium`
   >
   > Lightpanda is not recommended — it's not packaged for pip/npm and has limited site compatibility.

3. **WebSearch tool** (always available fallback). Use when neither Chrome extension nor Playwright is available. Works well for Google/Bing searches. Cannot scroll Reddit/X feeds.

### What each tool can actually do

| Tool | Google/Bing | Reddit | X/Twitter | News sites | Login required? |
|------|------------|--------|-----------|------------|-----------------|
| Claude for Chrome | ✓ | ✓ | ✓ | ✓ | For Reddit/X |
| Playwright | ✓ (use Bing — Google blocks headless) | ✗ (JS-rendered, needs login) | ✗ (needs login) | ✓ | No |
| WebSearch tool | ✓ | ✗ | ✗ | Partial | No |

**Key reality:** Reddit and X are JS-rendered SPAs that block headless browsers and require login. No local tool can scroll them anonymously. The Claude for Chrome extension is the only option for those sites. For everything else, Playwright + Bing or the WebSearch tool works well.

Pick the best available path and continue. If only WebSearch is available, tell the user:
> I'm using Google search only — no live Reddit/X scrolling. The research will be solid on news and trends, but I'll miss the social conversation.

## Step 1. Gather the niche

Call AskUserQuestion:

```json
[
  {
    "question": "What niche do you want to research?",
    "header": "Niche",
    "multiSelect": false,
    "options": [
      {"label": "I will type my niche", "description": "Type the exact niche phrase after this"},
      {"label": "Pull from about-me.md", "description": "Use the niche and audience already in my voice files"}
    ]
  }
]
```

If the user picks "Pull from about-me.md", read the file from the project root. If the file does not exist or does not name a clear niche, fall back to asking the user to type it.

## Step 2. Browse like a human researcher

Drive the browser through these actions in order. Verify publish dates on every item. Exclude anything older than 7 days from today without exception.

### 2a. Reddit feed scanning

1. Navigate to https://www.reddit.com/ (home feed).
2. Scroll the feed. Load more posts.
3. Open niche-relevant posts. On each post, check the "posted X days ago" timestamp.
4. Discard posts older than 7 days.
5. Repeat with https://www.reddit.com/r/popular/.
6. Also search any niche-specific subreddits that come up while scrolling.

### 2b. X (Twitter) feed scanning

1. Navigate to https://x.com/home (For You feed).
2. Scroll multiple screens.
3. Open full threads for niche-relevant tweets.
4. Check the post timestamp on each thread.
5. Discard posts older than 7 days, even if engagement is high.

### 2c. Google web search

Run these searches one by one, open the top results, verify publish dates.

- `[niche] news` (set Tools → Any time → Past week)
- `[niche] launch` (past week)
- `[niche] controversy` (past week)
- `[niche] research` (past week)
- `[niche] regulation` (past week)

For each promising result:

1. Open the page.
2. Locate the visible publish date.
3. Verify it is within the last 7 days.
4. If the date is missing, unclear, or older than 7 days, exclude it.

## Step 3. Synthesise into themes

Collect a broad pool of verified, in-window items. Group related items into themes. Each theme may combine social discussion and news coverage.

Select themes that show at least two of:

- Strong attention or discussion
- Clear disagreement or debate
- Novel insight or new information
- Real-world implications for the niche

Target 20 themes. Fewer is acceptable if genuinely limited.

## Step 4. Output

First line before the table:

```
As of [DD/MM/YYYY]
```

Then a markdown table with these exact columns:

```
| Theme / Emerging Story | Platforms (Reddit, X, News) | Key Communities / Accounts / Sources | Representative Links | Attention Signals | What's Happening or Being Debated | Why It Matters for [NICHE] | Shareable Angle |
```

No prose outside the table.

## Step 4.5. Save the research to a file

After outputting the table, save the full research output to a markdown file. Use this conversation to determine the save location:

1. Check if a project directory already exists (e.g. `~/.hermes/projects/<project-name>/content-research/`). If found, ask:

   > I found a content-research directory at `<path>`. Should I save this as `raw-research-YYYY-MM-DD.md` there, or somewhere else?

2. If no project directory exists, ask:

   > Where should I save this research? Give me a directory path and I'll create it if needed. The filename will be `raw-research-YYYY-MM-DD.md`.

3. Once the user confirms the path, write the file immediately. The file must include:
   - The niche being researched
   - The date (DD/MM/YYYY)
   - The method used (e.g. "Google search only — no live feed scrolling")
   - All themes in table format
   - Any notes or caveats from the research

4. After saving, confirm the full file path to the user.

5. Record the save location in memory so future niche-research runs default to the same directory. Use the memory target `memory` with a note like: "niche-research save path: `<full path>`"

## Step 5. Offer the next move

After the table, ask:

> Any row here you want me to dig into? I can:
> - **Mine it for insights** — run `insight-miner` on this row to extract hidden assumptions, pressure-test the claims, and find angles most people would miss
> - **Write a post** — hand it to `post-writer` to draft directly (skip the insight step)
> - **Map angles** — feed it to `content-matrix` to build a full calendar around it

Choose "mine it for insights" when the story has genuine substance worth digging into. Choose "write a post" for quick turnaround on straightforward topics.

## Saving research output

After the table is delivered, save it to a markdown file in the project. Use this convention:

- **Directory:** `content-research/` (create if it doesn't exist)
- **Filename:** `raw-research-YYYY-MM-DD.md`
- **Format:** Markdown with metadata header (date, niche, method, researcher) followed by the table and any notes

This ensures the research is available for downstream skills (insight-miner, content-matrix) and future reference without re-running the search.

## Rules

- Never invent links, metrics, or dates.
- For browser tooling reality (what works on headless servers vs. desktop), see `references/browser-tooling-reality.md`.
- Exclude anything older than 7 days without exception.
- Verify every publish date before including an item. No shortcuts.
- Table only at the end. No commentary, no summary paragraph.
- If fewer than 20 themes pass the filter, say so. Do not pad with weak items.
- If Claude for Chrome is not available and neither Playwright MCP nor WebFetch can cover feed scrolling properly (Reddit and X), tell the user what is missing rather than faking the scan.
- When only Google search is available (no feed scrolling), note the limitation in the Method field of the saved file. Research is still valid but represents the top of the iceberg.
- British English throughout. DD/MM/YYYY date format.
- Never use em dashes.
- **web_extract fails on Substack, paywalled sites, and any DuckDuckGo-backend URL.** Fix: use `browser_navigate` + `browser_console` with `document.querySelector('article').innerText.substring(0,15000)` in chunks. Always have this fallback ready.
- **Prioritise large-scale data-backed analyses over anecdotal advice.** When researching what works on a platform, cite Buffer (52M+ posts), Socialinsider (70M+ posts), or similar large datasets. Flag single-source or anecdotal claims as "unverified."
