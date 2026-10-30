# Customer payment summary – GitHub Pages

Customers enter their **MPL No.** and **mobile number** and see their payment summary, read live from your Google Sheet (tab `MPL-ACS`, plus `MPL-SLR` / `MPL-STR` for the product category).

## Deploy
1. Create a GitHub repo, upload `index.html` and `.nojekyll`.
2. Repo **Settings → Pages → Deploy from branch → main / (root)** → Save.
3. Open `https://<your-user>.github.io/<repo>/`.

## Google Sheet setup
- **Share → General access → Anyone with the link → Viewer.**
- Optional but most reliable: **File → Share → Publish to web**, choose each tab (MPL-ACS, MPL-SLR, MPL-STR) as **CSV**, publish, and paste each link into `CONFIG.PUBLISHED` in `index.html`.
- Product category: MPL No. (ACS) → `MPL-SLR` col A, take Batch No. (col D) → `MPL-STR` Ref (A) + number (B) → Category (G).
- Warranty (from invoice date, edit `CONFIG.WARRANTY`): Standard/Super = full 3 months, service until 6 months; Value = full 1 month, service until 3 months; Budget = no warranty.

## Notes
- Do not rename the tabs or move columns A–AQ in `MPL-ACS` without updating `C` in `index.html`.
- Internal notes (columns H, AF, AG) are never displayed.

## Files to upload
`index.html`, `logo.png`, `support.png`, `.nojekyll` (all in the repo root).

## Sharing a result
After a search, **Share link** copies (or opens the phone's share sheet for) a link like
`https://<user>.github.io/<repo>/#mpl=MPLNCC1015&mobile=0771234567`. Opening it shows that customer's summary straight away.
The details sit after the `#`, so they are not sent to GitHub's servers, but anyone holding the link can view that summary.
