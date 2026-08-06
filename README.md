# The Hearth Kitchen — Montclair History Center

An interactive 3D tour of the reconstructed Hearth Kitchen at the Israel
Crane House, built with Gaussian Splatting (Spark + Three.js) and a
scroll-driven camera.

## Structure

```
kitchen-splat/
  index.html          ← the live site
  README.md
  assets/
    MHC_Hearth_edited.ply
    MHC_Logo.png
  tools/
    calibrate.html     ← dev tool for picking/adjusting camera poses
```

## Run locally

Serve the folder over http:// (not file://) — e.g. VS Code's Live Server
extension (right-click index.html → Open with Live Server), or:

```bash
npx serve .
```

## Deploy to GitHub Pages

1. Create a new repository on GitHub (public, no README/gitignore needed
   — you already have files).
2. From this folder, run:

```bash
git init
git add .
git commit -m "Initial deploy"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

3. On GitHub: repo → **Settings → Pages** → under "Build and deployment",
   set Source to **Deploy from a branch**, Branch to **main** / **root** →
   Save.
4. Wait a minute or two, then your site is live at:
   `https://YOUR_USERNAME.github.io/YOUR_REPO/`


## Testing across devices

Once live, share the URL (GitHub's default `github.io` link works fine
for testing before a custom domain is set up). Worth explicitly asking
testers to check:

- Desktop: Chrome, Firefox, Safari, Edge
- Mobile: iOS Safari and Android Chrome specifically (WebGL/touch
  behavior differs most here)
- Both a strong connection and mobile data, to gauge real load time
- Whether the Low/Medium/High quality toggle actually helps on their
  device, and which setting they land on
- Whether the on-screen d-pad appears and works on their phone/tablet
- Whether scroll-triggered camera moves feel smooth on lower-end hardware
