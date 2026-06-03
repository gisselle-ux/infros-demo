# Infros Demo Animation — Webflow Embed Instructions

## Files
- `infros-demo-standalone.html` — the fully self-contained animation (all assets inlined, no external dependencies)

---

## Option A: Iframe Embed (Recommended for Webflow)

This is the cleanest approach. Host the HTML file on any static server (Netlify, Vercel, GitHub Pages, Cloudflare Pages, etc.) and embed it via iframe.

### Step 1 — Host the file
Upload `infros-demo-standalone.html` to a static host. Example using Netlify Drop:
1. Go to [netlify.com/drop](https://app.netlify.com/drop)
2. Drag and drop `infros-demo-standalone.html`
3. Copy the generated URL (e.g. `https://your-site.netlify.app/infros-demo-standalone.html`)

### Step 2 — Add to Webflow
1. In Webflow, add an **Embed** element (`</> Embed`) to your page
2. Paste this code (replace the URL with your hosted file URL):

```html
<div style="width:100%;aspect-ratio:16/9;max-width:1280px;margin:0 auto;">
  <iframe
    src="https://YOUR-URL/infros-demo-standalone.html"
    style="width:100%;height:100%;border:none;border-radius:12px;"
    allowfullscreen
  ></iframe>
</div>
```

3. Adjust `max-width` and border-radius to match your site's design.

---

## Option B: Direct HTML Embed in Webflow

If you prefer not to use an iframe, you can paste the entire HTML file contents into a Webflow **Embed** block. However, note:

- The file is ~357 KB — Webflow's embed block has a size limit (~10 KB of *code*)
- This approach is **not recommended** — use Option A instead

---

## Animation Details

- **Loop duration:** ~35–40 seconds per full cycle, then auto-restarts
- **Scenes covered:**
  1. Drift Detected mobile notification
  2. Email inbox with infrastructure alert
  3. Infros platform — AI chat with Clio
  4. Architecture comparison table
  5. Deploy pipeline with live steps
  6. AWS architecture diagram pan
- **No user interaction required** — fully automatic

## Notes for the Developer

- The animation uses `window.location.reload()` to loop — this works correctly inside an iframe
- The animation is responsive and scales to fit its container via a `fitCanvas()` function
- Tested at 16:9 ratio; works at any size but looks best at 1280×720 or larger
- No external JavaScript libraries or CDN dependencies — everything is self-contained
