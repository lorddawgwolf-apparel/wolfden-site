# wolfdenrecords.ca

Static site for **LordDawgWolf / Wolf Den Records**. Plain HTML + CSS + a few lines of vanilla JS.
No build step, no frameworks, no server code. It is hosted on GitHub Pages.

## Structure
- `index.html` (Home), `music.html`, `about.html`, `faq.html`, `store.html`, `contact.html`, `404.html`
- `faqs-1.html`, `lorddawgwolfs-store.html`, `cart.html`, `home.html`: redirect stubs for the old Squarespace URLs
- `assets/css/style.css`: all styles
- `assets/js/main.js`: mobile menu + album/single filter on the Music page
- `assets/img/covers/`: release artwork (600px WebP)
- `assets/img/photos/`, `assets/img/merch/`: photos and merch previews (WebP, max 1600px wide)
- `assets/fonts/`: self-hosted Rye + Oswald (SIL Open Font License)
- `CNAME`: custom domain (`wolfdenrecords.ca`)

## Adding a new release
1. Save the cover as `assets/img/covers/<slug>.webp` (600x600).
2. In `music.html`, copy an existing `<article class="card">` block, paste it at the **top** of the grid, and update the title, date, and Spotify/Apple/Deezer links.
3. Optionally swap it into the "Latest Releases" section of `index.html`.

## Preview locally
    python3 -m http.server 8000
    # open http://localhost:8000

## Deploy (GitHub Pages)
1. Push this folder to a GitHub repo, then go to Settings → Pages → Deploy from branch → `main` / root.
2. Custom domain: `wolfdenrecords.ca` (already in `CNAME`). Turn on "Enforce HTTPS" after the certificate is issued.
3. DNS at the registrar: four `A` records for `@` → 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153,
   and a `CNAME` for `www` → `<username>.github.io`. **Keep the existing MX records** so `info@wolfdenrecords.ca` keeps working.
