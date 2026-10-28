# Medical Malpractice Landing Page — GitHub Pages (static) version

The same Weltchek Mallahan & Weltchek medical-malpractice landing page as the PHP build, converted to plain static files for GitHub Pages. No PHP, no server-side code — just HTML + CSS, and the form loads from your provider's embed URL in an iframe.

## Files

```
github-malpractice-landing-page/
├── index.html          — the whole page (all content baked in)
└── css/style.css       — all styling, including the overflow form card
```

The PHP version's `form-handler.php` is intentionally omitted: GitHub Pages can't run it. The form itself is an iframe embed, so submissions still go through your form provider exactly as before.

## The overflow form container (unchanged from the PHP build)

- The white form card hangs **110px past the bottom of the hero** (`margin-bottom: -110px` in `.hero-form`), overlapping the section beneath it. That section carries matching top padding (`.section--after-hero`) so its text clears the card. On mobile the overlap shrinks to −70px.
- The form frame scrolls internally (`overflow: auto`, max height 72vh) if the embedded form runs tall.

## Before publishing — two placeholders, same as the PHP build

1. **Form embed URL** — in `index.html`, find the iframe and replace the `src` (`https://FORM-EMBED-URL.example.com/your-form`) with your form provider's embed URL.
2. **Phone number** — top bar and footer contact block, both marked `REPLACE` in comments.

## Publishing to GitHub Pages

1. Create a repo (e.g. `malpractice-landing`) and upload `index.html` and the `css/` folder, keeping the structure.
2. Repo → Settings → Pages → Deploy from a branch → pick your branch and `/ (root)`.
3. Your page will be live at `https://<username>.github.io/malpractice-landing/` within a minute or two.

Everything else — firm name, address, disclaimer, $700M+ results claim, section copy — is already filled in from the reference page.
