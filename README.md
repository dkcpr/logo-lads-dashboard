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

## Monthly routine (about 15 minutes, first Wednesday of the month)

### 1. Download the exports

Pick the longest date range each time. Overlapping dates are fine.

| Platform | Where | Files |
|---|---|---|
| **Instagram** | business.facebook.com/latest/insights/results → platform box: **Instagram** → date: **Last 90 days** → **Export → CSV** on each card. Then **Insights → Content** → platform box: **Instagram** → longest range → **Export** | Views, Viewers, Follows, Visits, Interactions, Link clicks (6 CSVs), plus the Content export (one row per post; this is what fills Top posts) |
| **Facebook** | Same pages → platform box: **Facebook** → same 6 cards, then the same Content export | Same 6 CSVs + Content export |
| **LinkedIn** | Company page, admin view → **Analytics → Content → Export**, then **Analytics → Followers → Export** (longest range) | `…_content_….xls` and `…_followers_….xls` |
| **TikTok** | tiktok.com/tiktokstudio → **Analytics** → longest range → **Download data** on the Overview, Content and Followers tabs | `Overview.csv`, `Content.csv`, and from the Followers download only `FollowerHistory.csv` |

Instagram and Facebook files download with the same names. Do one platform at a time, renaming and uploading it before you start the next.

Skip TikTok's FollowerActivity, FollowerGender and FollowerTopTerritories files. They're usually empty.

### 2. Rename

Put the date at the start of each file name, e.g. `2026-10-18 Views.csv`. Where two files cover the same day, the newer name wins.

### 3. Upload

Open the platform's folder upload page, drag the files in, and click the green **Commit changes** button at the bottom. Nothing is saved until you click it.

- Instagram: github.com/dkcpr/logo-lads-dashboard/upload/main/data/instagram
- Facebook: github.com/dkcpr/logo-lads-dashboard/upload/main/data/facebook
- LinkedIn: github.com/dkcpr/logo-lads-dashboard/upload/main/data/linkedin
- TikTok: github.com/dkcpr/logo-lads-dashboard/upload/main/data/tiktok

### 4. Check

Wait about 5 minutes, then reload the dashboard. If anything looks stale, press Cmd+Shift+R. Each platform's status box turns green when its data is current and yellow when it's more than 35 days old. A yellow box at the top lists any file that couldn't be read.

Not sure a file will work? Drag it onto the dashboard page first. It previews the file in your browser without uploading anything.

## Numbers no export gives you

TikTok's FollowerHistory gives a follower total automatically. Instagram, Facebook and LinkedIn exports only give *new* followers. For their totals, check each profile page about once a month, then open `data/manual/weekly.csv` in GitHub (click the file, then the pencil icon) and add one line per week:

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
