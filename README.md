# ✋ Hand-Controlled Drawing Canvas

A browser-based drawing canvas you control entirely with your **hand and webcam** — no plugins, no installs. Point with your index finger to paint; switch tools with gestures.

## 🖼️ Features

| Gesture | Action |
|---|---|
| ☝️ Index finger up | **Draw** — moves the brush |
| ✌️ Two fingers up | **Erase** — rubs out paint |
| ✊ Fist | **Clear** the whole canvas |
| 🖐️ Open hand | **Pause** — lifts the pen |
| 👍 Thumbs-up | **Save** the drawing as PNG |
| 🤏 Pinch (index + thumb) | **Resize brush** — open/close to grow/shrink |
| 🖱️ Mouse / touch | Fallback drawing when no camera is available |

Additional controls in the toolbar:
- **Colour palette** — 10 colours, click any swatch
- **Brush-size slider** — 1 – 40 px
- **Draw / Erase / Clear / Save** buttons

## 🛠️ Technology

| Layer | Library |
|---|---|
| Hand tracking | [MediaPipe Hands](https://google.github.io/mediapipe/solutions/hands) (runs fully in the browser — no server) |
| Rendering | HTML5 Canvas API |
| Skeleton overlay | MediaPipe `drawing_utils` |

Inspired by:
- [Depth and Skeleton-Based Dynamic Hand Gesture Recognition](https://github.com/tasnim7ahmed/Depth-and-Skeleton-Based-Dynamic-Hand-Gesture-Recognition)
- [BodySkeletonTracker](https://github.com/derzu/BodySkeletonTracker)

## 🚀 Running Locally

Because the page uses a webcam via `getUserMedia`, it must be served over **HTTPS or localhost** — opening the file directly (`file://`) will not work.

```bash
# Python 3
python -m http.server 8080
# then open http://localhost:8080
```

```bash
# Node (npx)
npx serve .
```

## 🌐 Free Hosting Options

### 1. GitHub Pages (recommended — zero effort)
1. Push this repository to GitHub.
2. Go to **Settings → Pages**.
3. Under **Source**, choose `main` branch / `/ (root)`.
4. Click **Save** — your site will be live at `https://<username>.github.io/<repo>/`.

### 2. Netlify
1. Drag-and-drop the folder onto [app.netlify.com/drop](https://app.netlify.com/drop).
2. Instant HTTPS URL, no account required for quick deploys.

### 3. Vercel
```bash
npm i -g vercel
vercel
```
Follow the prompts — you get a free `*.vercel.app` URL with HTTPS.

### 4. Cloudflare Pages
Connect your GitHub repo at [pages.cloudflare.com](https://pages.cloudflare.com) — free tier, fast CDN, HTTPS.

### 5. Surge.sh
```bash
npm i -g surge
surge .
```
Creates a free `*.surge.sh` URL in seconds.

---

> **Privacy note:** The webcam feed is processed entirely on-device by MediaPipe. No video data is ever uploaded to any server.
