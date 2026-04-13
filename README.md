# 🏋️ HERCULES — Deploy to Vercel

## Option A: Deploy via Vercel CLI (2 minutes)

```bash
# 1. Install dependencies
npm install

# 2. Install Vercel CLI globally (if not already installed)
npm i -g vercel

# 3. Deploy
vercel

# Follow the prompts:
#   Set up and deploy? → Y
#   Which scope? → your account
#   Link to existing project? → N
#   Project name? → hercules (or anything you like)
#   In which directory is your code? → ./  (just press Enter)
#   Override settings? → N
#
# Vercel will detect Vite automatically and deploy.
# You'll get a URL like: https://hercules-xyz.vercel.app
```

## Option B: Deploy via Vercel Dashboard (no CLI)

1. Push this folder to a **GitHub repo**:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   gh repo create hercules --public --push
   # or push to your existing GitHub manually
   ```

2. Go to **[vercel.com/new](https://vercel.com/new)**

3. Click **"Import Git Repository"** → select your repo

4. Vercel auto-detects Vite. Settings will be:
   - **Framework Preset:** Vite
   - **Build Command:** `vite build`
   - **Output Directory:** `dist`

5. Click **Deploy** → done in ~30 seconds

## Local Development

```bash
npm install
npm run dev
# Opens at http://localhost:5173
```

## Project Structure

```
hercules-vercel/
├── index.html          # Entry HTML
├── vite.config.js      # Vite config
├── vercel.json         # SPA routing fix
├── package.json
└── src/
    ├── main.jsx        # React root
    └── App.jsx         # Full app (all screens)
```

## Notes

- All data is stored in **localStorage** — no backend needed
- The app is a single-file React component — no database, no auth server
- Fully static → deploys instantly, free on Vercel's hobby tier
