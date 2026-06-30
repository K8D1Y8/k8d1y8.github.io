# Academic Homepage

A single-page academic homepage built with the Claude/Anthropic design system
(warm paper background, serif headings, terracotta accent). Pure HTML/CSS — no build step.

## Quick start

1. Open `index.html` in a browser to preview.
2. Edit the placeholders (see below).
3. Push to GitHub and enable Pages.

## Status

Filled in with Do Yeong Kang's details from the CV — intro, publications, awards, and teaching.
Page order: hero/intro → News → Publications → Awards → Teaching.

## Still to fill (in `index.html`)

Social links (GitHub, Google Scholar, LinkedIn, email) and `og:url` are wired up. Remaining:

| Item | Where | Note |
|---|---|---|
| `assets/photo.jpg` | hero photo (shows "DK" until added) | A square headshot — then swap the div for an `<img>` (see **Photo**) |
| Paper links | Publications `.lk` items (currently `#`) | Add PDF / arXiv / code URLs as they go live |
| News dates | News `<li>` | Approximate — adjust to the real months |

HTML comments (`<!-- ... -->`) mark every editable section.

### Photo

Drop a square image at `assets/photo.jpg`, then in the hero replace:

```html
<div class="photo" role="img" aria-label="Your Name — profile photo placeholder">YN</div>
```

with:

```html
<div class="photo"><img src="assets/photo.jpg" alt="Your Name"></div>
```

### News

The News section shows the **first 5 items**; the rest are hidden behind a subtle "··· show older"
toggle. To control what's hidden, mark the extra `<li>` items with `class="xnews" hidden`:

```html
<li><span class="date">2026.06</span><span class="what">A recent update.</span></li>
<li class="xnews" hidden><span class="date">2025.01</span><span class="what">An older update.</span></li>
```

### CV

`assets/cv.pdf` is your CV (the **CV** block in the hero links to it). It currently holds the **draft**
you provided — replace it with your final PDF when ready.

## Deploy to GitHub Pages

Your site will live at `https://K8D1Y8.github.io`:

1. Create a repo named exactly `K8D1Y8.github.io`.
2. Push these files to the `main` branch root:
   ```bash
   git init
   git add .
   git commit -m "Initial homepage"
   git branch -M main
   git remote add origin https://github.com/K8D1Y8/K8D1Y8.github.io.git
   git push -u origin main
   ```
3. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**,
   branch `main`, folder `/ (root)`. Save.
4. Wait ~1 minute, then visit `https://K8D1Y8.github.io`.

The `.nojekyll` file tells GitHub Pages to serve the files as-is (skip Jekyll processing).

## Notes

- `_plan/homepage-plan.html` is the design-planning artifact used to scope this site. It is listed in
  `.gitignore`, so it is **not committed or published** — it stays on your machine for reference.
  (This matters because `.nojekyll` disables Jekyll; without the ignore rule the `_plan/` folder would
  otherwise be served publicly.)
- Everything is in one `index.html` with the CSS inlined, so the site loads instantly and has no
  dependencies.
