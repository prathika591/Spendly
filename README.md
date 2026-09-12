# Spendly

A personal expense tracker built after researching seven competing money-tracking apps (Money Manager, Axio, Splitwise, Spendee, PocketGuard, and others) to find real, review-backed gaps to design around — rather than guessing at features.

**Live demo:** _add your GitHub Pages link here after deploying (see below)_

## Features

- **Dashboard** — total spent, a zero-based "safe to spend" number, and spending broken down by category and by account, for this month, the full year, or a custom date range.
- **Add expense** — full form or a one-field quick-entry mode, plus a one-tap "repeat last entry" shortcut for recurring identical purchases.
- **Activity** — every entry, searchable and filterable by category, account, or tag, with inline editing.
- **Tags** — label any expense (e.g. "Goa trip") and get an automatic mini-report: total spent and category breakdown for just that label.
- **Budgets** — set a monthly limit per category with live progress and status (on track / near limit / over budget), plus overall "committed vs. safe to spend."
- **Recurring expenses** — set up rent, subscriptions, or bills once; they log themselves automatically whenever they come due.
- **Custom categories & accounts** — user-defined categories with a picked icon and color, and user-defined accounts (cash, card, bank, or anything else).
- Fully responsive, with light/dark theme support and a colorblind-aware category palette.

## Tech

Plain HTML, CSS, and JavaScript — no build step, no framework, no dependencies. Data is stored in the browser via `localStorage` when run standalone (as on GitHub Pages); the same codebase also runs inside a Claude artifact, where it transparently syncs through a realtime cloud document store instead — the app detects which environment it's in and switches automatically.

## Running locally

No install needed — it's a single static file.

```bash
git clone https://github.com/<your-username>/spendly.git
cd spendly
python3 -m http.server 8000
# open http://localhost:8000
```

Or just open `index.html` directly in a browser.

## Deploying (for a public link)

1. Push this repo to GitHub.
2. In the repo, go to **Settings → Pages**.
3. Under "Build and deployment," set **Source** to "Deploy from a branch," branch `main`, folder `/ (root)`.
4. Save — GitHub gives you a live URL at `https://<your-username>.github.io/spendly/` within a minute or two.

## Design process

Rather than starting from a blank feature list, this project began by reading real user reviews of established expense trackers to find specific, recurring complaints and feature requests — things like hidden date filters, SMS-parsing bugs causing duplicate transactions, aggressive free-tier paywalls, and the lack of tag-scoped spending reports. Those findings shaped which features made it into v1 and which engineering pitfalls (single source of truth for all totals, reliable manual fallback, no artificial usage caps) were treated as non-negotiable from the start.

## License

MIT
