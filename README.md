# UCCL Asset Inspection - Windows EXE Builder

Converts `asset_inspect.html` into a standalone Windows `.exe` using Electron + GitHub Actions.

## How to Build the EXE

### Step 1 — Create a GitHub Repository

1. Go to [github.com](https://github.com) → **New repository**
2. Name it e.g. `uccl-asset-inspection`
3. Set to **Private**, click **Create repository**

### Step 2 — Upload these files

Upload all files in this folder maintaining the directory structure:

```
uccl-asset-inspection/
├── main.js
├── package.json
├── index.html          ← your asset_inspect.html (renamed)
├── icon.png            ← optional app icon (256x256 PNG)
└── .github/
    └── workflows/
        └── build.yml
```

You can drag-and-drop files in the GitHub web UI, or use Git:

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR_USERNAME/uccl-asset-inspection.git
git push -u origin main
```

### Step 3 — GitHub Actions builds automatically

Once pushed to `main`, the **Build Windows EXE** workflow runs automatically.

- Go to your repo → **Actions** tab
- Wait ~5 minutes for the build to complete
- Download the EXE from **Artifacts** → `UCCL-Asset-Inspection-Windows`

You'll get two files:
- **UCCL Asset Inspection Setup.exe** — installer (recommended)
- **UCCL Asset Inspection.exe** — portable (no install needed)

### Optional: Add an icon

Replace `icon.png` with a 256×256 PNG of your choice before pushing.
If no icon is provided, Electron uses its default icon.

## Local Build (if you have Node.js installed)

```bash
npm install
npm run build
# Output in ./dist/
```

## Notes

- The app runs fully **offline** — no internet required after install
- Window opens without a menu bar for a clean look
- Built for **Windows x64**
