# Adding your Power BI dashboards

The site is already wired up to show a mix of static screenshots and one live,
interactive report. Here's how to fill it in.

## 1. Screenshots (5 of the 6 project cards)

1. Open each report in Power BI Desktop or the Power BI Service.
2. Export/screenshot each page at a decent size (1600px wide is plenty).
   File → Export → Export to PDF, then screenshot the page, or just use
   Snipping Tool / Cmd+Shift+4 on the rendered report.
3. Save the images into `assets/projects/` next to `index.html`, using these
   exact filenames (already referenced in the code):
   - `assets/projects/supply-chain.png`
   - `assets/projects/yaatri.png`
   - `assets/projects/hr-workforce.png`
   - `assets/projects/financial-performance.png`
   - `assets/projects/customer-insights.png`
4. That's it — the project cards and the lightbox that opens on
   "View dashboard" will pick them up automatically. If a file is missing,
   the card just falls back to the animated placeholder, so nothing breaks.

## 2. One live, interactive report (Executive Sales Dashboard)

This one uses Power BI's own public embed, so no server is needed.

1. Open the report in **Power BI Service** (powerbi.com) — not Desktop.
2. **File → Embed report → Publish to web (public)**.
3. Confirm the warning (this makes the report viewable by anyone with the
   link — only use this on reports with sample/non-sensitive data).
4. Copy the link that looks like `https://app.powerbi.com/view?r=eXaMpLe123`.
5. In `index.html`, find this line near `const projects = [`:
   ```js
   embedUrl:'PASTE_YOUR_PUBLISH_TO_WEB_LINK_HERE'
   ```
   and replace it with your real link.
6. Save. The "Executive Sales Dashboard" card will now show a "Live report"
   badge, and clicking "Open live dashboard" opens the real, interactive
   report in a lightbox.

## 3. Hosting it all (no server needed)

Since your files already live on GitHub:

1. Push `index.html`, `POWER-BI-SETUP.md`, and the `assets/` folder to your repo.
2. Repo → **Settings → Pages** → set Source to your branch (e.g. `main`) and
   root folder.
3. GitHub gives you a free URL like `https://yourusername.github.io/repo-name/`.

Want me to swap in your real project names, industries, and KPI copy once the
screenshots are ready? Just paste them here.
