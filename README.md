# Southern Timber Retrievers

A single-file website for Southern Timber Retrievers — field-bred Labrador Retrievers,
hunt tests, family companions. The whole site lives in `index.html` (HTML, CSS, and JS
in one file, logo embedded), so it deploys anywhere static.

---

## Deploy to GitHub Pages

### Option A — no command line (GitHub website)
1. On GitHub, click **New repository**. Name it e.g. `southern-timber` and create it.
2. Click **Add file → Upload files**. Drag in `index.html`, the `images/` folder,
   and `.nojekyll` (turn on "show hidden files" if you don't see it). Commit.
3. Go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source: Deploy from a branch**,
   **Branch: `main`**, folder **`/ (root)`**. Save.
5. Wait ~1 minute. Your site is live at:
   `https://<your-username>.github.io/southern-timber/`

### Option B — command line (git)
```bash
cd southern-timber-retrievers
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<your-username>/southern-timber.git
git push -u origin main
```
Then enable Pages under **Settings → Pages** as in Option A, step 3–4.

> Tip: name the repo exactly what you want in the URL. To update the site later,
> change `index.html` and push again (or re-upload) — Pages redeploys automatically.

---

## Swapping in real photos
Each photo is a normal `<img>` showing a placeholder until you replace it.
1. Drop your image into the `images/` folder (e.g. `images/kobe.jpg`).
2. In `index.html`, find the comment `<!-- REPLACE: ... -->` and change that
   `<img src="...">` to `src="images/kobe.jpg"`. That's it.

---

## Connecting your Instagram feed (optional)
The site already links to `@southerntimberretrievers` (nav, hero, contact, footer).
To show a live, auto-updating feed, the simplest path for a static site:
1. Switch your Instagram to a free **Creator** account (Settings → ~30 seconds, reversible).
   The old personal-feed API was shut down in Dec 2024, so a Creator/Business account is
   now required by the widget tools.
2. Create a feed at a widget service (Behold, SnapWidget, or LightWidget) and copy its snippet.
3. Paste the snippet into `index.html` where you want it. (Ask and a styled "From the Field"
   section can be added with a slot ready for the snippet.)

---

## Making the contact form deliver to your inbox (optional)
As shipped, submitting the form opens the visitor's email app pre-filled to
`info@southerntimberretrievers.com` — works with no backend, but relies on the visitor
having mail set up.

To receive messages directly:
1. Sign up at **formspree.io** and create a form to get an endpoint URL.
2. In `index.html`, on the `<form id="contactForm">` tag, add:
   `action="https://formspree.io/f/YOURID" method="POST"`
3. In the `<script>`, delete the line marked `e.preventDefault();` in the form handler.

---

## Custom domain (optional)
If you own `southerntimberretrievers.com`, add a file named `CNAME` (no extension) to the
repo containing just the domain, then set the domain under **Settings → Pages** and point
your DNS to GitHub Pages. Leave this out until the domain is registered.

---

## Files
- `index.html` — the entire site (edit this)
- `images/` — your photos go here
- `.nojekyll` — tells GitHub Pages to serve files as-is
