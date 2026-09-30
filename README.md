# Clear Air — installable web app

A calm companion for quitting smoking. Installs to your home screen, opens full screen, works offline. Your log is stored on your phone only.

## What's in this folder

| File | What it does |
|---|---|
| `index.html` | The whole app |
| `manifest.webmanifest` | Name, colours and icons used when you install it |
| `sw.js` | Service worker: keeps a copy on the phone so it opens offline |
| `icons/` | Home-screen icons (iPhone, Android, browser tab) |
| `fonts/` | Fraunces and Inter, bundled so nothing loads from the internet (SIL Open Font License, see the `OFL-*.txt` files) |

## Put it online (pick one)

It must be served over **https**. Opening `index.html` straight from Files won't install.

### Option A — GitHub Pages (free, permanent)
1. On github.com, create a new **public** repository, e.g. `clear-air`.
2. Click **Add file → Upload files**, drag in **everything inside this folder** (not the folder itself), and commit.
3. Go to **Settings → Pages**. Under "Build and deployment", pick **Deploy from a branch**, branch **main**, folder **/ (root)**, then **Save**.
4. After a minute or two it's live at `https://<your-username>.github.io/clear-air/`.

Prefer git? From inside this folder:
```
git init -b main
git add .
git commit -m "Clear Air web app"
git remote add origin https://github.com/<your-username>/clear-air.git
git push -u origin main
```
Then do step 3.

### Option B — Netlify Drop (fastest)
1. Go to https://app.netlify.com/drop and drag this whole folder onto the page.
2. Sign in (free) when asked, so the site isn't deleted after an hour.
3. You get an `https://<name>.netlify.app` link.

## Install on your phone

- **iPhone (Safari):** open the link → tap **Share** → **Add to Home Screen** → **Add**. It must be Safari, not Chrome, on iPhone.
- **Android (Chrome):** open the link → tap **Install** on the card in the app, or ⋮ menu → **Install app**.

Open it once from the home screen while online; after that it works with no signal.

## Your data

- Everything lives on the phone, in this app only. It is not synced and not sent anywhere.
- **Settings → Your data → Save a backup** makes a `.json` file (save it to Files, Drive or send it to yourself). **Restore from a backup** brings it back on a new phone or after reinstalling.
- Deleting the home-screen app, or clearing Safari's website data, deletes the log. Back up first.

## Updating the app later

Replace the files on GitHub/Netlify and change the version number at the top of `sw.js` (e.g. `clear-air-1.0.0` → `clear-air-1.0.1`). The app picks up the new version the next time it's opened with internet.
