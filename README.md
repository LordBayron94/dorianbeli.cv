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

- **Photo:** one portrait photo, 2252×4000, in six files: `assets/photo-2252.*` (screens
  from 768px wide) and `assets/photo-1126.*` (phones), each as AVIF, WebP and JPG. The
  browser loads only the first format it supports. Home shows its full width, rows
  800–3040 (the crop is set on `.hero-bg` in [styles.css](styles.css)); the card on the
  left shows the whole photo. To replace it, export a 2252×4000 master (`master.png`)
  with the face inside that band, then:

  ```
  ffmpeg -i master.png -vf scale=1126:2000:flags=lanczos master-1126.png
  # for each size (2252 from master.png, 1126 from master-1126.png):
  ffmpeg -i master.png -vf "scale=out_color_matrix=bt709:out_range=full,format=yuv420p,setparams=color_primaries=bt709:color_trc=iec61966-2-1:colorspace=bt709:range=full" -c:v libaom-av1 -still-picture 1 -crf 30 -b:v 0 -cpu-used 3 -map_metadata -1 -frames:v 1 assets/photo-2252.avif
  ffmpeg -i master.png -c:v libwebp -preset photo -quality 82 -compression_level 6 -map_metadata -1 -frames:v 1 assets/photo-2252.webp
  ffmpeg -i master.png -q:v 3 -huffman optimal -pix_fmt yuvj420p -map_metadata -1 -frames:v 1 assets/photo-2252.jpg
  ```

  If a file is missing the photo is hidden and the green background shows instead.
- **CV download:** the "Download CV" button serves `assets/DorianBeli-CV.pdf` —
  replace that file whenever you update your CV.
- **Colors and fonts:** design tokens are at the top of [styles.css](styles.css).
