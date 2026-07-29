# Ledger — deployment guide

This folder is a complete, installable web app (a "PWA"). Once it's hosted
somewhere, you can open the link on your phone and use your browser's
"Add to Home Screen" option — it'll get its own icon and open full-screen,
just like a regular app.

## What's in here
- `index.html` — the app itself
- `manifest.json` — tells the phone the app's name, icon, and colors
- `service-worker.js` — lets the app keep working offline
- `icon-192.png` / `icon-512.png` — the app icon
- `README.md` — this file

## Important: where your data lives
This version stores everything **in your phone's/browser's local storage** —
there's no server, no account, no sync between devices. That means:
- Your data stays completely private on your device
- If you clear your browser's site data, or switch browsers/devices, it won't carry over
- Use **History → Backup & restore** to download a backup file periodically, and
  to restore from one if you ever switch devices or clear site data

## Option A — Netlify Drop (easiest, no account strictly required)
1. Go to **https://app.netlify.com/drop**
2. Drag this whole folder onto the page
3. You'll get a live URL in a few seconds (something like `random-name-123.netlify.app`)
4. Open that URL on your phone and use "Add to Home Screen"

**To redeploy after changes:** if you claim the site with a free Netlify
account (one click, right after your first drop), you can drag the updated
folder onto the same site's dashboard any time and it replaces the old
version at the same URL. Without an account, dropping the folder again
creates a brand-new URL each time.

## Option B — GitHub Pages (best if you're comfortable with git)
1. Create a new repository on GitHub (public or private both work)
2. Upload all the files in this folder to the repo (or `git push` them)
3. In the repo, go to **Settings → Pages**, set the source to your main
   branch (root folder), and save
4. GitHub gives you a URL like `https://yourname.github.io/repo-name/`
5. Open that URL on your phone and use "Add to Home Screen"

**To redeploy after changes:** just commit and push the updated files —
GitHub Pages rebuilds automatically within a minute or two.

## Updating the app later
Come back to this conversation (or a new one with Claude) and describe what
you'd like changed. You'll get an updated version of this same folder back —
drop it into Netlify again, or `git push` it to your GitHub repo, and the
live app updates. If you bump the version number at the top of
`service-worker.js` (e.g. `ledger-cache-v2`) when you redeploy, it guarantees
people's phones pick up the new version right away instead of showing a
cached copy.

## Add to Home Screen
- **iPhone (Safari):** open the link → tap the Share icon → "Add to Home Screen"
- **Android (Chrome):** open the link → tap the ⋮ menu → "Add to Home Screen" or "Install app"
