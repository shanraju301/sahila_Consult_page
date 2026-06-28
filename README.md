# Wellness with Sahila — $39 Discovery Consultation Landing Page

Single static page promoting Dr. Sahila's $39 discovery consultation.
No build step — plain HTML, CSS, and a small inline script for the click-to-load video embed.

## Structure

```
index.html       — the entire page (styles + markup + script)
assets/          — photos used on the page
```

## Booking link

All CTA buttons point to: `https://pages.sahila.me/consult_sahila`
To change it, find/replace that URL across `index.html` (5 occurrences).

## Video embed

The Vimeo intro video uses a click-to-load pattern: a static thumbnail
(`assets/dr-sahila-intro-thumb.jpg`) loads instantly, and the real Vimeo
iframe is only injected into the page when the visitor clicks play. This
keeps the page fast since the Vimeo player script never loads until needed.

Vimeo video ID and privacy hash are set in the `data-vimeo-id` and
`data-vimeo-hash` attributes on the `.video-tile-vertical` element.

## Deploying

### First-time setup (GitHub → Vercel)

1. Push this folder to a new GitHub repo (see commands below).
2. Go to vercel.com → **Add New Project** → **Import Git Repository**.
3. Select this repo. Framework preset: **Other** (no build step needed).
4. Leave build/output settings blank — it's a static site, Vercel will
   serve `index.html` as-is.
5. Click **Deploy**. You'll get a live URL in under a minute.

### Custom domain

In Vercel → Project → Settings → Domains, add something like
`consult.wellnesswithsahila.com`, then add the CNAME record Vercel gives
you to your domain's DNS.

### Future updates

Once connected, every `git push` to the main branch auto-deploys to
Vercel — no manual redeploy needed.

## Push to GitHub (first time)

```bash
git init
git add .
git commit -m "Initial commit: $39 consultation landing page"
git branch -M main
git remote add origin https://github.com/shanraju301/YOUR_REPO_NAME.git
git push -u origin main
```
