## lucaspolito.dev

My personal landing page: one static page with no build step or dependencies.

GitHub Pages serves it directly from `main`, with Cloudflare in front. Pushing to `main` deploys it.

### Running locally

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

### What's where

- `index.html`: the page, its metadata, and the scripts that pick a random gradient and build the email link on click
- `404.html`: not-found page, which uses root-relative paths because GitHub Pages serves it at any URL depth
- `css/styles.css`: styles and gradients
- `icons/`: link icons, used as CSS masks so they can fill with the gradient on hover
- `fonts/`: self-hosted Work Sans (weights 500 and 600, Latin subset) and its license
- `favicon.*`, `apple-touch-icon.png`, `og-image.png`: browser icons and the social preview image
- `CNAME`: custom domain for GitHub Pages

### Adding a gradient

1. Add a class to `css/styles.css` that sets `--gradientStops`.
2. Add its name to `gradientClasses` in `index.html`.
3. Keep every part of it at 3:1 contrast or better against `--background`.

### Caching

Cloudflare caches CSS for up to 4 hours, so returning visitors can see old styles for a while after a deploy.
