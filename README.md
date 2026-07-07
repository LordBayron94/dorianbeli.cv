# Dorian Beli — personal CV website

A single-page CV / portfolio site built with plain HTML and CSS, hosted on GitHub Pages.

## Publish on GitHub Pages

1. Create a public GitHub repository named exactly `LordBayron94.github.io`
   (while logged in as **LordBayron94**).
2. Push this folder to it:

   ```
   git remote add origin https://github.com/LordBayron94/LordBayron94.github.io.git
   git push -u origin main
   ```

3. Done — the site appears at `https://lordbayron94.github.io` within a minute or two.
   (For a repo with this exact name, GitHub Pages is enabled automatically from the `main` branch.)

## Editing content

Everything lives in [index.html](index.html).

- **Photo:** drop your picture at `assets/photo.jpg` (square, ~400×400px or larger).
  Until then a "DB" monogram is shown automatically.
- **CV download:** the "Download CV" button serves `assets/DorianBeli-CV.pdf` —
  replace that file whenever you update your CV.
- **Colors and fonts:** design tokens are at the top of [styles.css](styles.css).
