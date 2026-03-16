# Catalyst Intelligence — Expenditure Tracker

Internal expenditure tracker for Wes & Shane. Tracks business expenses out of the Catalyst account with per-person attribution, categories, client/project tagging, budget monitoring, and monthly reporting.

---

## Files

```
index.html   ← The entire app (single file, no dependencies)
README.md    ← This guide
```

---

## Step 1 — Push to GitHub

You've already created the repo. Drop both files in and push:

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME

# Copy index.html and README.md into this folder, then:
git add .
git commit -m "init: catalyst expenditure tracker"
git push origin main
```

---

## Step 2 — Enable GitHub Pages

1. Go to your repo on GitHub
2. Click **Settings** (top nav)
3. Scroll to **Pages** in the left sidebar
4. Under **Source**, select **Deploy from a branch**
5. Branch: `main` / Folder: `/ (root)`
6. Click **Save**

GitHub will give you a URL in about 60 seconds — it'll look like:

```
https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/
```

That's your live URL. Bookmark it. Both you and Shane hit that same URL and the data saves locally per-browser via localStorage.

> **Important note on shared data:** localStorage is per-device/per-browser, meaning Wes's laptop and Shane's laptop each store their own copy. The simplest workaround is one of these two options:
>
> **Option A (recommended for now):** Whoever logs expenses first exports a CSV at the end of each month from Settings → Export CSV and shares it with the other. Takes 30 seconds.
>
> **Option B (real-time sync):** Hook it up to a free Google Sheets backend via Apps Script — takes about 20 minutes and gives you live shared state. Let Claude know when you're ready for that upgrade.

---

## Step 3 — Embed in GoHighLevel

### As a Custom Menu Tab (recommended)

1. In GHL, go to **Settings → Custom Menu Links**
2. Click **Add Link**
3. Fill in:
   - **Name:** Expenditure Tracker
   - **URL:** `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`
   - **Open in:** New tab ← simplest, works perfectly
4. Save and the link appears in your GHL sidebar

### As an Iframe inside a GHL Page (embedded view)

If you want it embedded inside a GHL custom page rather than opening a new tab:

1. In GHL, go to **Sites → Funnels** or **Websites**
2. Create a new blank page
3. Add a **Custom Code** element
4. Paste this iframe:

```html
<iframe
  src="https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/"
  width="100%"
  height="900px"
  frameborder="0"
  style="border:none; border-radius:10px;"
  allowfullscreen>
</iframe>
```

5. Adjust `height` as needed (900px works well on most screens)

---

## Updating the App

Any time you want to change something (add a category, update the budget default, tweak the UI):

1. Edit `index.html` locally (or directly on GitHub)
2. Commit and push to `main`
3. GitHub Pages auto-deploys in ~30–60 seconds
4. Refresh the browser — changes are live

---

## Features

| Feature | Details |
|---|---|
| Dashboard | Totals, Wes/Shane split, budget bar, last 8 expenses |
| Add expense | Date, amount, category, paid by, description, client/project, notes |
| Log | Full expense table, filter by category or person, delete |
| Reports | Monthly tabs, category bars, person bars, monthly breakdown table |
| Settings | Set monthly budget, export CSV, clear all data |
| Export | One-click CSV download of all expenses |

---

## Categories

| Category | Use for |
|---|---|
| Ads | Meta, Google, any paid advertising |
| Tools / Software | GHL, ClickUp, Figma, any tool subscriptions |
| Hosting / Infrastructure | Domains, servers, GitHub, any hosting |
| Contractors | Freelancers, VAs, any paid help |
| Subscriptions | Recurring SaaS not covered above |
| Operations | Office, travel, misc business ops |
| Misc | Anything that doesn't fit |

---

## Questions / Upgrades

Built by Claude for Catalyst Intelligence LLC. To request changes — new categories, Google Sheets sync, additional fields, UI tweaks — just ask Claude with this file open.
