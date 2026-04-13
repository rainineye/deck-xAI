# deck-xAI

Pitch deck viewer for xAI Exceptional Designer application.

**Live:** https://deck.0xmian.com

## Stack
- PDF.js (vector rendering, lossless zoom)
- GoatCounter analytics (privacy-friendly, no cookies)
- GitHub Pages + custom domain

## Deploy (first time)

1. **Push these files** to `main` branch of this repo.
2. **Enable GitHub Pages:** Settings → Pages → Source: `main` / root → Save.
3. **Custom domain:** Settings → Pages → Custom domain → `deck.0xmian.com` → Save. Tick "Enforce HTTPS" once the cert is issued (5–15 min).
4. **DNS:** Add CNAME record on `0xmian.com`:
   - Type: `CNAME`
   - Name: `deck`
   - Target: `rainineye.github.io`
   - Proxy (if Cloudflare): OFF initially. Turn on after HTTPS cert is issued.

## Update deck (future versions)

Replace `Mian_xAI_Pitch.pdf` with the new PDF (keep the same filename), regenerate `og-cover.png` from the new page 1, commit, push. Done.

To generate a new OG cover from page 1:
```bash
pdftoppm -png -r 200 -f 1 -l 1 Mian_xAI_Pitch.pdf cover
# then crop/resize to 1200x630 for og-cover.png
```

## Features
- Fullscreen immersive mode (press `F`)
- Keyboard: `← →` navigate, `Home/End` jump, `Space` next
- Click left/right quarter of screen to navigate
- Touch swipe on mobile
- Deep link to specific slide: `?page=9`
- Auto-hiding chrome (counter + byline) — appears on motion
