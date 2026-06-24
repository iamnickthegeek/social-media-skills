# Browser Tooling Reality — What Actually Works for Web Research

> **Last verified:** June 2026
> **Environment:** Linux (x86_64), headless server, no GUI browser

## The honest picture

Most "browser-based research" advice assumes you have a Chrome extension or a full desktop browser. On a headless Linux server (VPS, cloud instance, CI environment), the options are limited. Here's what actually works.

## Tools ranked

### 1. Playwright (Python) — Best available option

**Install:**
```bash
pip3 install playwright
python3 -m playwright install chromium
```

**What works:**
- ✅ Bing search results (server-rendered HTML)
- ✅ Hacker News, Lobsters, and similar lightweight sites
- ✅ Most news sites (BBC, TechCrunch, The Verge, etc.)
- ✅ Static blogs and documentation

**What doesn't work:**
- ❌ Google search — blocks headless browsers (shows URL as title, 0 results)
- ❌ Reddit — JS-rendered SPA, doesn't load posts in headless mode
- ❌ X/Twitter — requires login, JS-rendered
- ❌ Any site behind Cloudflare/CAPTCHA

**Key insight:** Use Bing instead of Google when running Playwright. Bing returns server-rendered HTML that parses cleanly.

### 2. WebSearch tool (API-level) — Reliable fallback

**What works:**
- ✅ Google search results (via API, not browser)
- ✅ Returns titles, URLs, and snippets
- ✅ Date filtering works

**What doesn't work:**
- ❌ Cannot scroll feeds (Reddit, X)
- ❌ Cannot extract full article content (use web_extract for that, but it may fail on JS-heavy sites)
- ❌ No access to social media posts or comments

### 3. Claude for Chrome extension — Only option for Reddit/X

**Requirements:**
- Desktop Chrome with the extension installed
- User must be logged into Reddit/X
- Claude drives the actual browser

**What works:**
- ✅ Reddit (with login)
- ✅ X/Twitter (with login)
- ✅ Everything else

**What doesn't work:**
- ❌ Not available on headless servers
- ❌ Requires manual user setup

### 4. Lightpanda — Not recommended

- Not packaged for pip/npm
- Limited site compatibility
- No advantage over Playwright for research tasks
- Only consider if you need a lightweight headless browser and can build from source

## Decision tree

```
Need Reddit or X?
├── Yes → Claude for Chrome extension (only option)
└── No → Need full article content?
    ├── Yes → Try Playwright + Bing
    │   ├── Works? Use it.
    │   └── Blocked? Fall back to WebSearch + web_extract
    └── No → WebSearch tool is enough
```

## What this means for niche-research

The skill's Step 2 (Reddit/X/Google browsing) is aspirational. In practice on a headless server:
- You'll almost always fall through to the WebSearch fallback
- That's fine — WebSearch covers the news and trend layer well
- The social conversation (Reddit/X) is genuinely missed
- Be honest with the user about this limitation rather than pretending to scroll feeds
