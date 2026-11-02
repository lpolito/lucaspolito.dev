## lucaspolito.dev

My personal landing page: one static page with no build step or dependencies.

GitHub Pages serves it directly from `main`, with Cloudflare in front. Pushing to `main` deploys it.

### Running locally

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

### What's where

- `index.html`: the page, its metadata, and the script that picks a random title gradient
- `css/styles.css`: styles and gradients
- `css/reset.css`: CSS reset
- `fonts/`: self-hosted Work Sans (weight 600, Latin subset) and its license
- `favicon.*`, `apple-touch-icon.png`, `og-image.png`: browser icons and the social preview image
- `CNAME`: custom domain for GitHub Pages

### Adding a gradient

1. Add a class to `css/styles.css`.
2. Add its name to `gradientClasses` in `index.html`.
3. Keep every part of it at 3:1 contrast or better against `--background`.

### Caching

Cloudflare caches CSS for up to 4 hours, so returning visitors can see old styles for a while after a deploy.

Most edits done using GitHub app while laying in bed so plz don't judge commit history
