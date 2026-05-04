# Morning News Builder — Artifact Prompt

## Goal

Build a live, self-refreshing dark-mode morning news page as a Cowork artifact.

---

## On Load

Auto-fetch today's top news immediately using `window.cowork.askClaude`, applying the instructions defined in `news-system-prompt.md`. No user interaction required to trigger the first load.

---

## Sections

- **World & Politics** — 5 stories
- **Technology & Science** — 5 stories
- **Market Snapshot** — S&P 500, Nasdaq, and Bitcoin with % change for the day

---

## Story Cards

- Each card displays the **headline** and a **one-line teaser** in its collapsed state
- Clicking a card **expands it inline** to reveal:
  - The full 5–10 sentence summary
  - A **"Read more →"** button that opens the source URL in a new tab
- Clicking again **collapses** the card

---

## Customization Bar

- A **text input at the top of the page** where the user can type preferences before fetching
- Examples of valid inputs:
  - `"focus on AI today"`
  - `"skip crypto"`
  - `"add a Sports section"`
  - `"make summaries shorter"`
- These instructions are **appended to the base system prompt** at fetch time
- The last-entered preferences are **saved to `localStorage`** and pre-filled on the next open
- Users can also send preferences via the Cowork chat — both methods work

---

## What Customization Can Change

- **Topic focus** — e.g. "more coverage on the Middle East"
- **Add a category** — e.g. "include a Sports section today"
- **Tone tweak** — e.g. "give me more context on each story" or "keep it very brief today"

---

## Manual Refresh

A **refresh button** triggers a new fetch using the current customization text. Useful for checking for updates later in the day.

---

## Design

- **Dark mode** throughout — dark background, light text
- Minimal and clean — typography-first layout
- Clear visual hierarchy between sections
- Cards have subtle hover states
- Breaking/Developing story tags are visually distinct:
  - 🔴 `BREAKING` — red chip
  - 🟡 `DEVELOPING` — yellow chip
- Market snapshot is compact, displayed at the bottom of the page

---

## Error Handling

If the fetch fails, display a friendly retry message with a retry button. Never show a blank page.
