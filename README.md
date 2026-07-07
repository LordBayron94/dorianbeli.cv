# Dorian Beli — personal CV website

A single-page CV / portfolio site built with plain HTML and CSS, hosted on GitHub Pages.

## Publish on GitHub Pages

1. Create a GitHub repository named exactly `<your-username>.github.io` (public).
2. Push this folder to it:

   ```
   git remote add origin https://github.com/<your-username>/<your-username>.github.io.git
   git push -u origin main
   ```

3. Done — the site appears at `https://<your-username>.github.io` within a minute or two.
   (For a repo with this exact name, GitHub Pages is enabled automatically from the `main` branch.)

## Editing content

Everything lives in [index.html](index.html). Search for `TODO` comments to find the spots
that still need real data (industry work history, BSc dates, GitHub username, skills).

- **Photo:** drop your picture at `assets/photo.jpg` (square, ~400×400px or larger).
  Until then a "DB" monogram is shown automatically.
- **CV download:** drop your PDF at `assets/DorianBeli-CV.pdf` to make the
  "Download CV" button work.
- **Colors and fonts:** design tokens are at the top of [styles.css](styles.css).
