# FuelTrack PWA — Deployment Guide

Since Squarespace doesn't support hosting custom web apps (no arbitrary file uploads, no service worker support), here's how to get FuelTrack live for free using **Netlify** — the easiest option with zero coding required.

---

## Option 1: Netlify Drop (Easiest — 2 minutes)

### Step 1: Unzip the files
Unzip `fueltrack-pwa.zip` to a folder on your computer. You should see 5 files:
- `index.html` (the app)
- `manifest.json` (PWA config)
- `sw.js` (offline support)
- `icon-192.png` (app icon)
- `icon-512.png` (app icon)

### Step 2: Deploy to Netlify
1. Open your browser and go to **https://app.netlify.com/drop**
2. You do NOT need an account for this step (but create a free one to keep your site permanently)
3. **Drag and drop the entire unzipped folder** onto the page where it says "drag and drop your site"
4. Wait 5-10 seconds — done! Netlify gives you a live URL like `https://random-name-12345.netlify.app`

### Step 3: (Optional) Claim your site
1. Click "Claim this site" and create a free Netlify account
2. Go to **Site settings → Domain management → Change site name**
3. Set it to something memorable like `fueltrack-yourname` → your URL becomes `https://fueltrack-yourname.netlify.app`

### Step 4: Install on your Android phone
1. Open Chrome on your Android phone
2. Go to your Netlify URL (e.g. `https://fueltrack-yourname.netlify.app`)
3. Chrome will show a banner saying **"Add FuelTrack to Home screen"** — tap it
4. If no banner appears: tap the **three-dot menu (⋮)** in Chrome → tap **"Install app"** or **"Add to Home screen"**
5. FuelTrack now appears on your home screen with its own icon, just like a native app
6. It runs fullscreen with no browser toolbar

---

## Option 2: GitHub Pages (Also free, slightly more steps)

### Step 1: Create a GitHub account
Go to https://github.com and sign up (free).

### Step 2: Create a new repository
1. Click the **+** in the top right → **New repository**
2. Name it `fueltrack`
3. Set it to **Public**
4. Check **"Add a README file"**
5. Click **Create repository**

### Step 3: Upload your files
1. In your new repo, click **"Add file"** → **"Upload files"**
2. Drag all 5 files from the unzipped folder into the upload area
3. Click **"Commit changes"**

### Step 4: Enable GitHub Pages
1. Go to **Settings** → **Pages** (in the left sidebar)
2. Under **Source**, select **"Deploy from a branch"**
3. Under **Branch**, select **main** and **/ (root)**
4. Click **Save**
5. Wait 1-2 minutes. Your site will be live at: `https://yourusername.github.io/fueltrack/`

### Step 5: Install on Android
Same as Option 1, Step 4 — visit the URL in Chrome and install.

---

## Important Notes

### Where is my data stored?
All your food logs, weight entries, and profile data are stored **locally on your phone** using the browser's localStorage. This means:
- Your data is private — nothing is sent to any server
- Data persists between visits
- If you clear your browser data, you'll lose your tracking history
- Data is specific to each device (your phone and computer have separate data)

### Updating the app
If you want to make changes later, just re-upload the files to Netlify or GitHub. The service worker will update automatically.

### Custom domain (optional)
Both Netlify and GitHub Pages support connecting your own domain name if you ever want one. Check their docs for instructions.

---

## File Inventory

| File | Purpose |
|------|---------|
| `index.html` | The complete app (HTML + CSS + JavaScript all in one file) |
| `manifest.json` | Tells the browser this is an installable PWA |
| `sw.js` | Service worker for offline caching |
| `icon-192.png` | App icon (small) |
| `icon-512.png` | App icon (large) |
