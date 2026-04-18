# Expense Tracker

Single-file personal expense + income tracker with budgets, Excel import/export, and Google Drive sync. Installable as a PWA on iOS/Android.

## Features

- **Expenses & Income** — add, edit, delete; filter by date/category/source
- **Budget** — monthly per-category limits, progress bars, 80% / 100% alerts
- **Insights dashboard** — KPIs (total income, total spent, net, savings rate, avg/day, biggest expense, budget used) + category donut, monthly bars, income-vs-expenses mixed chart, 30-day daily trend
- **Excel import/export** — `.xlsx` with Expenses, Monthly Summary, Income, and Cash Flow sheets
- **Google Drive sync** — optional, auto-syncs across devices
- **PWA** — installable, works offline after first load
- **Dark / light mode**

## Stack

Vanilla HTML / CSS / JS. No backend, no build step. CDN: Chart.js 4, SheetJS 0.18.

## Google Drive setup (one-time, ~5 min)

Skip this if you only use one device.

1. Go to **https://console.cloud.google.com/** → create a new project (any name).
2. Left menu → **APIs & Services → Library** → search **"Google Drive API"** → click **Enable**.
3. Left menu → **APIs & Services → OAuth consent screen**:
   - User type: **External** → Create
   - App name, support email, developer email → save
   - On **Scopes**: skip (leave empty)
   - On **Test users**: add your own Google email → save
4. Left menu → **APIs & Services → Credentials → Create credentials → OAuth client ID**:
   - Application type: **Web application**
   - Authorized JavaScript origins: add your site URL (e.g. `https://<username>.github.io`)
     - For local testing, also add `http://localhost:8000`
   - Create → copy the **Client ID** (ends in `.apps.googleusercontent.com`)
5. In the app: **Import / Export** tab → paste the Client ID → **Save** → **Connect Google Drive** → sign in.

First connect creates `expense-tracker-data.json` in your Drive. Every change syncs automatically.

## Install on iPhone

1. Open the site URL in **Safari**.
2. Tap the **Share** button (square with arrow).
3. **Add to Home Screen** → Add.
4. Opens like an app, full-screen, offline-capable.

## Install on Android / Chrome

Chrome address bar will show an install icon, or use menu → **Install app**.

## Local dev

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```
