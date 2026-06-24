# Playwright & Headless Browser Reality for Social Media Research

## What Works

### Installation (verified June 2026)

```bash
pip3 install playwright
python3 -m playwright install chromium
```

Total download: ~115MB. Works on Ubuntu 22.04 x86_64.

### What Playwright Can Do

- Launch headless Chromium
- Navigate to URLs and extract rendered HTML
- Scroll pages, click buttons, fill forms
- Extract text content from server-rendered pages

### What Actually Works With Playwright (Tested June 2026)

| Site | Works? | Notes |
|------|--------|-------|
| Hacker News | ✅ | Server-rendered, 30 posts extracted |
| Bing search | ✅ | Returns 10 results with titles |
| Google search | ❌ | Blocks headless — shows URL as title, 0 results |
| Reddit | ❌ | JS-rendered SPA, 0 posts extracted |
| X/Twitter | ❌ | JS-rendered SPA, 0 tweets extracted |
| News sites (most) | ✅ | Server-rendered, works fine |

### Key Finding: Google Blocks Headless Browsers

Google detects headless Chromium and serves a non-rendering page. The title becomes the URL and search results are empty.

**Workaround:** Use Bing instead. Bing returns proper results with Playwright.

### Key Finding: Reddit and X Are JS-Rendered SPAs

Both Reddit and X (Twitter) are JavaScript-heavy single-page applications. Headless Chromium cannot render their content without:
1. Login sessions (cookies)
2. JavaScript execution that triggers API calls

No local tool can scroll Reddit or X feeds anonymously. The only option is the Claude for Chrome extension running in a logged-in browser.

### Recommendation for niche-research

Use this priority order:

1. **Claude for Chrome extension** (if available) — handles all sites including Reddit/X
2. **Playwright + Bing** — handles Google-equivalent search + news sites
3. **WebSearch tool** (built-in) — handles Google search via API, no browser needed

Don't attempt Playwright for Reddit/X. It wastes time and produces empty results.

## Pitfalls

- **Don't claim Playwright "doesn't work" when it actually can't render JS SPAs.** It works fine for server-rendered content. The limitation is specific to JS-heavy sites.
- **Don't offer Lightpanda as an alternative.** It's not packaged for pip/npm and has limited site compatibility (tested June 2026 — not installable via standard package managers).
- **Don't skip the `python3 -m playwright install chromium` step.** The pip package is just the Python bindings; the browser binary is a separate download.
