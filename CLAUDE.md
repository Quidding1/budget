# Budget app (repo: budget)

French PWA to track personal payments, hosted on GitHub Pages (quidding1.github.io/budget/),
to be wrapped later with PWABuilder. Same setup as the Gymnase app (repo `grades`).
No server, no bank connection. Currency CHF.

## Files
- `index.html`: the whole app (HTML, CSS, JS). No build step.
- `sw.js`: service worker. **Bump `CACHE` (`budget-v1` → `budget-v2`) on every change.**
- `manifest.json`, `icon-*.png`.

## Rules
- All UI text in French. Black/minimal style, light/dark/system theme via CSS variables.
- Data lives in `localStorage` key `budget-v1`. Never break existing data: add a migration in
  `migrate()` (bump `d.v`) whenever the format changes.
- User-typed text must go through `esc()` before going into innerHTML.
- Tabs: Accueil, Transactions, Budgets, Plus. One round + button on every tab.

## Roadmap
- V1: add/edit/delete transactions, categories, home summary, search/filters, month arrows. (done)
- V2: recurring payments (auto-added on open), monthly budgets per category, custom month start day. (done)
- V3: charts (donut + 6 months), savings goals, JSON/CSV export + import, optional 4-digit PIN. (done)
