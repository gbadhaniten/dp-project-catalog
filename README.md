# DE Project Catalog

Interactive Data Engineering Project Catalog — built as a static HTML report hosted on GitHub Pages, with CSV data files stored on SharePoint.

## Live Report
**https://[yourusername].github.io/de-catalog/**

## How it works
- `index.html` — the full interactive report (hosted on GitHub Pages, free)
- `data/PROJECTS.csv` — all project data (or link to SharePoint)
- `data/DOCUMENTS.csv` — document status and links (or link to SharePoint)

## Setup with SharePoint CSVs

Open `index.html` and find the `CSV_URLS` section near the top of the `<script>` tag:

```javascript
const CSV_URLS = {
  projects:  'data/PROJECTS.csv',    // ← replace with SharePoint URL
  documents: 'data/DOCUMENTS.csv'    // ← replace with SharePoint URL
};
```

Replace the values with your SharePoint direct download links:
```javascript
const CSV_URLS = {
  projects:  'https://YOURCOMPANY.sharepoint.com/sites/SITE/Shared%20Documents/DE-Catalog-Data/PROJECTS.csv?download=1',
  documents: 'https://YOURCOMPANY.sharepoint.com/sites/SITE/Shared%20Documents/DE-Catalog-Data/DOCUMENTS.csv?download=1'
};
```

## How to update data

| What to update | File to edit |
|---|---|
| Add / update / remove a project | `PROJECTS.csv` |
| Update project status or progress | `PROJECTS.csv` — edit `Status` or `ProgressPct` column |
| Add document links | `DOCUMENTS.csv` — paste SharePoint URL in `DocumentLink`, change `DocumentStatus` to Available |
| Update domain descriptions | Edit `DOMAINS` array in `index.html` (hardcoded — always visible) |

## Domain filter
All 17 domains are always visible on page 1 (hardcoded). Project counts update live from PROJECTS.csv.

## Deploying updates
1. Edit the CSV files in SharePoint (or locally and push to GitHub)
2. The report reflects changes instantly on next page load — no rebuild needed

## GitHub Pages deployment
1. Go to repo Settings → Pages
2. Source: Deploy from branch → main → / (root)
3. Save — your report is live in 1-2 minutes
