# Customer payment summary – GitHub Pages

Customers enter their **MPL No.** and **mobile number** and see their payment summary, read live from your Google Sheet (tab `MPL-ACS`, plus `MPL-SLR` / `MPL-STR` for the product category).

## Deploy
1. Create a GitHub repo, upload `index.html` and `.nojekyll`.
2. Repo **Settings → Pages → Deploy from branch → main / (root)** → Save.
3. Open `https://<your-user>.github.io/<repo>/`.

## Google Sheet setup
- **Share → General access → Anyone with the link → Viewer.**
- Optional but most reliable: **File → Share → Publish to web**, choose each tab (MPL-ACS, MPL-SLR, MPL-STR) as **CSV**, publish, and paste each link into `CONFIG.PUBLISHED` in `index.html`.
- Warranty: set `FULL_WARRANTY_MONTHS` / `SERVICE_WARRANTY_MONTHS` in `CONFIG` (months added to the invoice date). Until set, they show "—".

## Notes
- Do not rename the tabs or move columns A–AQ in `MPL-ACS` without updating `C` in `index.html`.
- Internal notes (columns H, AF, AG) are never displayed.
