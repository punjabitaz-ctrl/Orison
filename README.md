# Orison International General Trading — website

Static one-page site for Orison International General Trading (Al Satwa, Dubai).
New & used mobiles, laptops, accessories, networking gear, phone/laptop repairs, and B2B/wholesale trading.

**Design:** light, photo-led layout (Manrope; white header, dark announcement bar, Dubai skyline
hero). Available in **English, Arabic (RTL) and Urdu (RTL, Nastaliq)** with a language switcher.

## Hosting

- **GitHub Pages** serves the site by branch deployment (no Actions workflow). Every push to
  `main` redeploys.
- **Cloudflare** sits in front as CDN / DNS for the custom domain (proxied).

## Structure

Single HTML file plus a folder of photos — no build step, no dependencies except Google Fonts (CDN):

- `index.html` — the entire site (inline CSS + inline SVG + vanilla JS for the mobile menu,
  language switcher and footer year). All translations live in the `I18N` object in the script.
- `assets/` — product and repair photos used in the hero and category tiles (JPG, ~1.4 MB total).
- Favicons — `favicon.svg`, `favicon.ico`, `favicon-16.png`, `favicon-32.png`, `apple-touch-icon.png`.
- `.nojekyll` — tells Pages to serve the files as-is (no Jekyll processing).
- `.gitattributes` — normalizes line endings to LF.
- `CNAME` — present only once a custom domain is configured; holds the apex domain.

## Editing

Open `index.html` and edit directly. Key spots:

- **Contact details** — WhatsApp number (`wa.me/971563480513`), email
  (`salesorison@gmail.com`), address, and **business hours** (open daily 12:00 PM – 12:00 AM).
- **Social links** — TikTok, Instagram, WhatsApp in the contact section.
- **Products / B2B copy** — the category tiles and the B2B band.
- **Languages** — the `LANGS` list and `I18N` dictionary in the script. Every `data-i18n*`
  attribute in the markup maps to a key. A Hindi option is written but disabled (commented out
  in `LANGS`) until its strings are reviewed. The chosen language is remembered in
  `localStorage` (`orison_lang`).
- **Photos** — replace files in `assets/` keeping the same names (or update the `<img src>`).

Commit and push to `main`; the site redeploys automatically.
