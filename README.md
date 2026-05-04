# damianmathews.com

Personal site for Damian Mathews. Single-page static HTML.

## Stack

Plain HTML, CSS, and JS. No build step. No dependencies beyond Google Fonts (Fraunces + IBM Plex Mono) loaded via CDN.

## Files

- `index.html` — the whole site
- `netlify.toml` — Netlify config (security headers, cache rules)
- `.gitignore` — standard ignores

## Deploy to Netlify

Two paths.

### Path 1: GitHub → Netlify (recommended)

1. Create a new repo on GitHub (e.g. `damianmathews-site`)
2. From this folder:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/damianmathews-site.git
   git push -u origin main
   ```
3. In Netlify: **Add new site → Import from Git → GitHub → pick the repo**
4. Build settings: leave blank (it's a static site, Netlify auto-detects `index.html`)
5. Deploy. Add the custom domain `damianmathews.com` after the first deploy works.

### Path 2: Drag and drop

Drag this folder onto the Netlify dashboard. Done in 30 seconds. Doesn't connect to GitHub, so future updates need a redeploy.

## Things to swap before sending to a real lead

Search and replace inside `index.html`:

| Placeholder | Where it appears | Replace with |
|---|---|---|
| `hello@damianmathews.com` | 3 places (hero, contact, footer) | Your real email |
| `https://calendly.com/damianmathews/intro?...` | Calendly iframe in contact section | Your real Calendly event link |
| `href="#"` on LinkedIn footer link | Footer "LinkedIn" anchor | Your LinkedIn profile URL |

The Calendly iframe is themed with copper (`primary_color=db6f2c`) on the warm dark palette. Keep those query params on whatever URL you swap in and the embed will match the site.

## Custom domain

After the first Netlify deploy:
1. Site settings → Domain management → Add custom domain → `damianmathews.com`
2. Netlify will give you DNS records. Point your registrar at them.
3. Netlify auto-provisions an SSL cert via Let's Encrypt.

## Updating later

If you went the GitHub route, just push to `main`. Netlify rebuilds automatically.
