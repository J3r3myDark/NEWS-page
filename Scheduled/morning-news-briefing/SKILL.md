---
name: morning-news-briefing
description: Fetch and save daily news briefing (World & Politics, Tech & Science) to workspace
---

Fetch the top 5 stories each in **World & Politics** and **Technology & Science** for today's date. Include the widest range of trustworthy sources: Reuters, AP, BBC, NPR, NY Times, Guardian, Financial Times, Bloomberg, Wired, Ars Technica, MIT Technology Review, Nature.

For each story, include:
- **Headline** (bold, punchy, 10 words or fewer)
- **Summary** (5-10 sentences covering what happened, who's involved, key background, why it matters, what to watch next)
- **Source name + publication time** (if available)
- **Read more link** (direct URL)
- **Tag** (use "BREAKING" for major unfolding stories, "DEVELOPING" for unverified facts, or empty string otherwise)

Also include a **Market Snapshot** with current figures for S&P 500, Nasdaq, and Bitcoin (with % change for each).

Return **valid JSON only** using this exact schema:

```json
{
  "date": "YYYY-MM-DD",
  "world": [
    {
      "headline": "",
      "summary": "",
      "source": "",
      "time": "",
      "url": "",
      "tag": ""
    }
  ],
  "tech": [
    {
      "headline": "",
      "summary": "",
      "source": "",
      "time": "",
      "url": "",
      "tag": ""
    }
  ],
  "markets": {
    "sp500": "",
    "nasdaq": "",
    "btc": ""
  }
}
```

Save the JSON file to `/Users/jeremy/Documents/Claude/Projects/news page/news-YYYY-MM-DD.json` (replace YYYY-MM-DD with today's date). Use neutral tone, no opinions, no editorializing. Strictly fact-based reporting.