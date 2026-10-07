# Logo Lads social dashboard

A web page that turns the export files from Instagram, Facebook, LinkedIn and TikTok into one dashboard. There are no logins, connectors or tokens to expire. The files you upload are the data.

## One-time setup (about 15 minutes)

1. **Create a free GitHub account** at github.com.
2. **Create the repository.** Click **+** (top right) → **New repository**.
   - Name: `logo-lads-dashboard`
   - Choose **Public**. Free GitHub Pages sites require it. The dashboard and the uploaded export files can be seen by anyone who has the link. No passwords or private messages are in these exports.
   - Click **Create repository**.
3. **Upload the files.** On the new repository's page, click **uploading an existing file**. Open the `logo-lads-dashboard` folder in Finder, select everything in it (`index.html`, `app.js`, `config.js`, `README.md` and the `data` folder), and drag it onto the page. Click **Commit changes**.
4. **Turn on the website.** Go to **Settings** → **Pages**. Under *Build and deployment*, set Source to **Deploy from a branch**, Branch to **main** and folder to **/ (root)**, then click **Save**.
5. After 1–2 minutes the dashboard is live at
   `https://YOUR-USERNAME.github.io/logo-lads-dashboard/`
   That's the link to bookmark and send to the client.

## Weekly routine (about 10 minutes)

1. **Download the exports** (steps below). Choose the longest date range each platform offers. Overlapping dates are fine.
2. **Put the date at the start of each file name**, e.g. `2026-10-05 Overview.csv`. Where two files cover the same day, the newer one wins.
3. In GitHub, open `data` → the platform's folder (e.g. `data/tiktok`) → **Add file** → **Upload files**. Drag the files in and click **Commit changes**.
4. Refresh the dashboard after a minute or two. The status boxes at the top turn green when a platform's data is current. They turn yellow when it's more than 10 days old.

Not sure a file will work? Drag it onto the dashboard page first. It previews the file in your browser without uploading anything.

## Which exports to download

Menu names change from time to time. If one has moved, look for **Export** or **Download data** in the platform's analytics area.

| Platform | Where | Files to get |
|---|---|---|
| Instagram | Meta Business Suite → Insights → choose Instagram → **Export data** | The overview metrics (Reach, Follows, Views, Interactions) as CSV, plus the **Content** export (one row per post) |
| Facebook | Meta Business Suite → Insights → choose Facebook → **Export data** | Same as Instagram: overview metrics and the Content export |
| LinkedIn | Your company page, admin view → **Analytics** → Content, then Followers → **Export** | The content export (daily impressions and engagement, plus all posts) and the followers export |
| TikTok | TikTok Studio on desktop → **Analytics** → **Download data** | Overview, Content and Followers |

## Numbers no export gives you

Some exports don't include a total follower count. Meta's overview, for example, only gives new follows, and LinkedIn only gives daily new followers. For those, open `data/manual/weekly.csv` in GitHub (click the file, then the pencil icon) and add one line per week:

```
week_start,platform,followers,new_followers,reach,impressions,engagements,posts
2026-09-28,instagram,3659,,,,,
```

`week_start` is that week's Monday. `platform` is `instagram`, `facebook`, `linkedin` or `tiktok`. Leave blanks for anything you don't have. Numbers in this file take priority over the exports.

## How the numbers are calculated

- Weeks run Monday to Sunday.
- **Engagements** use the platform's own total when the export has one. Otherwise they are likes/reactions + comments + shares/reposts + saves.
- **Engagement rate** = engagements ÷ reach. It uses impressions/views when there's no reach number.
- **Reach** is the sum of daily reach. People reached on several days count more than once, the same as adding up the platforms' daily figures.
- If a platform has only a posts export, its weekly engagements, reach and views are totals for the posts published that week. The platform's card says so.
- **Download CSV** gives you the weekly table for reports.
