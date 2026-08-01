# 帳 Ledger

A yen-denominated household finance tracker styled after a Japanese account book (帳簿) — dark ink backdrop, a vermilion hanko seal as the mark, and tabular figures on ruled paper. Built as a single-page React app.

## Features

- **Monthly Income & Expenses** — set up recurring fixed figures (Salary, Rent, Service, Guarantor, Internet, Telecom by default). Add your own categories, edit amounts anytime. These sync automatically into the current month.
- **Current Month** — a read-only view of the active month (e.g. "Aug 2026") showing Income and Expenses broken into fixed categories (from your monthly config) plus flexible ones — Groceries, Investments, Transport, and Others — with totals and net income at the bottom.
- **Record Income / Expense** — a quick-entry sheet with colour-coded, icon-labelled category chips (green for income, vermilion for expense). Each entry adds straight into that category's running total for the month.
- **Projection** — a full-year outlook starting from the earliest recorded month (or the current month if no history exists yet) through December. Past months pull from History, the current month uses live totals, future months use your fixed monthly config. Includes an adjustable "Projected Expenses" line and a standalone **SGD Savings & Investments** tracker that doesn't affect any other total.
- **History** — closed months are archived automatically when a new month begins (kept for the trailing 12 months). Tap a month to see two pie charts — income and expense splits — plus that month's net income.
- **Persistence** — all data is saved to the browser's `localStorage`, so it survives page reloads and browser restarts on the same device.

## Tech stack

- [React](https://react.dev/) (function components + hooks)
- [Vite](https://vitejs.dev/) for bundling
- [Recharts](https://recharts.org/) for the History pie charts
- [Lucide](https://lucide.dev/) for icons
- Plain CSS (no framework) — custom design tokens for the ink/vermilion/gold palette, Shippori Mincho + Noto Sans JP + JetBrains Mono type

## Getting started (local development)

```bash
npm install
npm run dev
```

This starts a local dev server (Vite) with hot reload.

## Building for production

```bash
npm run build
```

Outputs a static, self-contained site to `dist/` — plain HTML/CSS/JS with no server required.

## Deploying to GitHub Pages

1. Run `npm run build`.
2. Upload the contents of `dist/` (`index.html`, `favicon.svg`, `favicon.ico`, `favicon-32.png`, `apple-touch-icon.png`, `icons.svg`, `assets/`) to your repo — either at the root or in a `/docs` folder.
3. In **Settings → Pages**, set **Source** to *Deploy from a branch*, pick the branch and folder you uploaded to, then save.
4. Your site goes live at `https://<username>.github.io/<repo>/`.

> Note: `vite.config.js` sets `base: './'` so the built assets resolve correctly whether the site is served from a repo subpath or a custom domain.

## Project structure

```
├── index.html          # Entry HTML, favicon links
├── public/
│   ├── favicon.svg      # Hanko-seal app icon (帳)
│   ├── favicon.ico
│   ├── favicon-32.png
│   └── apple-touch-icon.png
├── src/
│   ├── main.jsx         # React root
│   └── Ledger.jsx       # The entire app: state, screens, styling
└── vite.config.js
```

## Data & privacy

Everything is stored locally in your browser (`localStorage`) — there's no backend, no account, and no data ever leaves your device. Clearing your browser's site data for this page will reset the app.

## License

Personal project — use and adapt freely.
