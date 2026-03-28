# CS2 Util — Personal Lineup Tool

Your personal CS2 smoke/molly/flash/grenade lineup reference tool.  
Hosted at **cs2util.net**

---

## Setup Guide (one-time)

### Step 1: Push to GitHub

1. Go to [github.com/new](https://github.com/new) and create a repo called `cs2util` (public)
2. **Don't** check any boxes (no README, no .gitignore — we already have them)
3. On your computer, open Terminal and run:

```bash
cd ~/Downloads/cs2util          # wherever you unzipped this
git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/cs2util.git
git push -u origin main
```

Replace `YOUR_USERNAME` with your actual GitHub username.

### Step 2: Enable GitHub Pages

1. Go to your repo on GitHub → **Settings** → **Pages** (left sidebar)
2. Under **Source**, select **GitHub Actions**
3. That's it — the workflow file we included will auto-build and deploy on every push
4. Wait ~2 minutes, then check the **Actions** tab to see it building

### Step 3: Connect cs2util.net (Cloudflare DNS)

1. Log into [Cloudflare Dashboard](https://dash.cloudflare.com)
2. Click on **cs2util.net** → **DNS** → **Records**
3. Add these 4 **A records** (type: A, name: @):

| Type | Name | Content          | Proxy | TTL  |
|------|------|------------------|-------|------|
| A    | @    | 185.199.108.153  | DNS only | Auto |
| A    | @    | 185.199.109.153  | DNS only | Auto |
| A    | @    | 185.199.110.153  | DNS only | Auto |
| A    | @    | 185.199.111.153  | DNS only | Auto |

4. Also add a **CNAME** for www:

| Type  | Name | Content                           | Proxy | TTL  |
|-------|------|-----------------------------------|-------|------|
| CNAME | www  | YOUR_USERNAME.github.io           | DNS only | Auto |

5. **Important**: Set Cloudflare SSL/TLS mode to **Full** (not Full Strict) under SSL/TLS → Overview

### Step 4: Set custom domain in GitHub

1. Go to your repo → **Settings** → **Pages**
2. Under **Custom domain**, type `cs2util.net` and click Save
3. Check **Enforce HTTPS** once it's available (may take a few minutes)

### Step 5: Add to iPhone Home Screen

1. Open Safari on your iPhone
2. Go to **cs2util.net**
3. Tap the **Share** button (square with arrow)
4. Tap **Add to Home Screen**
5. It now launches fullscreen like a native app

---

## Updating

Any time you edit the code and push to GitHub, it auto-deploys in ~2 minutes:

```bash
git add .
git commit -m "updated lineups"
git push
```

## Local Development

```bash
npm install
npm run dev
```

Opens at http://localhost:5173
