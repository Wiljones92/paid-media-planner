Paid Media Planner
A single-file browser app for planning paid social campaigns: brief, budget split, KPI forecast and an exportable media plan.
Current version: v4 (locked master, 5 Oct 2026)
Live app: https://wiljones92.github.io/paid-media-planner/ (once GitHub Pages is enabled)
> ⚠️ **Dummy data only.** GitHub Pages sites are publicly reachable. Do not enter real client names, budgets, POs or plans until use has been approved by IT. Data you enter is stored only in your own browser, never in this repository.
---
Contents
Setup
Updating to a new version
Using the app
How the numbers are calculated
Saving, backup and restore
Plan checks
Known limitations
Troubleshooting
---
Setup
Option A – Run locally (no setup)
Download `index.html`.
Double-click it to open in Edge or Chrome.
Option B – Publish on GitHub Pages
Create a repository called `paid-media-planner`.
Upload these files to the repository root (not inside a folder):
`index.html`
`README.md`
`CHANGELOG.md`
Go to Settings → Pages.
Under Build and deployment, set Source to Deploy from a branch, then choose main and / (root). Click Save.
Wait 1–2 minutes, then open `https://<your-username>.github.io/paid-media-planner/`.
Repository structure
```
paid-media-planner/
├── index.html      # the app (the only file needed to run it)
├── README.md       # this file
└── CHANGELOG.md    # version history
```
---
Updating to a new version
In the repo, click `index.html` → ⋯ → Delete file, or simply upload the new file with the same name to overwrite it (Add file → Upload files).
Commit with a clear message, e.g. `v5 – add audience planner`.
Add an entry to `CHANGELOG.md`.
Pages republishes automatically within a couple of minutes. Hard-refresh (Ctrl + F5) if you still see the old version.
Your saved campaigns survive updates, because they live in your browser rather than in the file.
---
Using the app
The screen has three areas:
Area	Purpose
Left – Campaigns	Campaign library grouped by status: Draft, In Planning, Approved, Live, Completed. Click a campaign to open it; + New campaign creates one.
Centre – Workspace	Tabs for building the plan (below).
Right – Live Summary	Headline totals, platform split and plan checks for the selected campaign. Updates as you edit.
On screens narrower than 1000px the three areas stack vertically.
1. Brief
Enter client, brand, campaign name, market, start/end dates, objective, primary and secondary KPI, gross budget, currency (GBP/EUR), status, PO number, target audience and creative formats.
Changing Status moves the campaign to that group in the library. Delete campaign asks for confirmation and cannot be undone.
2. Budget
Platform Allocation – tick the platforms (Meta, TikTok, LinkedIn, YouTube, Pinterest, Snapchat) and enter a % for each. Must total 100%. Split evenly divides it equally.
Funnel Weighting – % of budget for Awareness, Consideration and Conversion, with the £/€ value shown.
Monthly Phasing – months are generated from the campaign dates and start evenly split. Editing one month rebalances the others so the total stays at 100%. Reset to even phasing restores the even split. Phasing also resets automatically if the campaign dates change.
3. Forecast
Per-platform and total: gross, net media, impressions, estimated reach, clicks, views, conversions, CPM and CPC.
4. Media Plan
One line per platform × funnel stage × month. Export CSV (Excel) downloads the plan with brief fields (client, brand, market, PO, KPI, audience, creative) on every line. If the plan is empty, the tab tells you why.
Benchmarks & Fees
Benchmarks – CPM, CTR %, VTR %, CPA and frequency per platform. Shipped values are placeholders; replace them with your own historical benchmarks. Reset to defaults restores the placeholders.
Fees – agency commission %, digital services tax %, and flat verification and data fees.
Benchmarks and fees are global: they apply to every campaign.
Keyboard: Tab moves to the next field, Enter commits a value, Esc closes pop-ups.
---
How the numbers are calculated
Output	Formula
Platform gross	Budget × platform %
Net media	(Platform gross − share of flat fees) ÷ (1 + commission % + DST %)
Fees	Platform gross − net media
Impressions	Net media ÷ CPM × 1,000
Clicks	Impressions × CTR %
Views	Impressions × VTR %
Conversions	Net media ÷ CPA
Estimated reach	Impressions ÷ frequency
CPC	Net media ÷ clicks
Fees are treated as charged on top of net media. If your agreement charges commission as a % of gross, net media figures will differ slightly.
In the media plan, each line = platform values × month % × funnel stage %. Funnel and phasing splits are normalised, so plan totals always equal the platform totals even if a split doesn't add to exactly 100% (the plan checks still flag it).
---
Saving, backup and restore
Auto-save: every change is saved in the browser's local storage. Data is tied to that browser on that device – it does not sync between computers or browsers, and clearing browser data deletes it.
Backup JSON: downloads all campaigns, benchmarks and fees as one file. Do this regularly.
Restore JSON: loads a backup file and replaces all current data. Invalid files are rejected, and incorrect values in a backup are reset to safe defaults.
If the app shows a Not saving warning, the current view blocks browser storage (e.g. an in-app preview). Open the file directly in Edge/Chrome or via GitHub Pages instead.
---
Plan checks
The Live Summary flags each item as OK or Missing:
Dates valid (end date on or after start date)
Flight ≤ 36 months
Budget > 0
Allocation = 100%
Audience defined
Creative defined
PO entered
Phasing = 100%
Funnel = 100%
---
Known limitations
Benchmarks are placeholders, not real platform data.
Total reach is summed across platforms and does not remove cross-platform duplication.
One set of benchmarks and fees applies to all campaigns.
Phasing is capped at 36 months.
The CSV covers core fields only and does not yet match client media plan templates column-for-column.
No multi-user access or shared storage – each person's data stays in their own browser.
---
Troubleshooting
Problem	Fix
Page shows 404 or the README instead of the app	Check `index.html` is in the repo root and Pages is set to main / (root).
Old version still showing after an update	Wait 2 minutes, then Ctrl + F5.
Campaigns disappeared	Different browser/device, or browser data was cleared. Restore from your latest backup JSON.
Download doesn't start	Some previews block downloads; the app shows the content in a pop-up to copy. Or open the app in a normal browser tab.
Media plan is empty	Read the message on the Media Plan tab – usually no platforms selected, invalid dates or all funnel stages at 0%.
---
Version
v4 – see `CHANGELOG.md` for full history.# paid-media-planner
Test sand box for a new media planning solution
