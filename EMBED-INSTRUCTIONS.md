# Infros Demo Animation — Webflow Embed Instructions

## File
- `infros-demo.js` — fully self-contained Shadow DOM widget (all assets inlined, zero external dependencies)

---

## How to Embed in Webflow

### Step 1 — Host the JS file
Upload `infros-demo.js` to any static host (Netlify, Vercel, GitHub Pages, Cloudflare Pages, etc.)

Quick option — [Netlify Drop](https://app.netlify.com/drop):
1. Drag and drop `infros-demo.js`
2. Copy the generated URL (e.g. `https://your-site.netlify.app/infros-demo.js`)

### Step 2 — Add to Webflow
1. In Webflow, add an **Embed** element (`</> Embed`) wherever you want the demo
2. Paste this code (replace the URL with your hosted file URL):

```html
<script src="https://YOUR-URL/infros-demo.js"></script>
```

That's it. The widget auto-inserts itself where the script tag sits and sizes to 16:9.

### Optional: Control the size
Wrap it in a div to constrain the width:

```html
<div style="width:100%;max-width:1280px;margin:0 auto;">
  <script src="https://YOUR-URL/infros-demo.js"></script>
</div>
```

---

## Why Shadow DOM?

The widget uses Shadow DOM so its styles are **fully isolated** from Webflow's styles — no leaking in either direction. Webflow's fonts, colors, resets, and layout rules will not affect the animation.

---

## Animation Details

- **Loop duration:** ~35–40 seconds per full cycle, then auto-restarts
- **Scenes:**
  1. Drift Detected mobile notification
  2. Email inbox with infrastructure alert
  3. Infros platform — AI chat with Clio
  4. Architecture comparison table
  5. Deploy pipeline with live steps
  6. AWS architecture diagram pan
- **No user interaction required** — fully automatic
- **No external JS libraries** — everything is self-contained
