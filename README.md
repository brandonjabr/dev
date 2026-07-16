# brandonjabr.dev

My personal developer website — a clean, single-page portfolio showcasing the iOS apps
I build. Home, Apps, and Contact pages with light & dark themes and subtle animations.

Built with **React** (loaded via CDN) and plain **HTML/CSS**, so there's **no build step** —
it runs straight from static files, which makes it instantly publishable on **GitHub Pages**.

## Structure

```
index.html      → the whole site (React app, styles, routing all inline)
favicon.svg     → site icon
assets/         → optimized app icons + screenshots
.nojekyll       → tells GitHub Pages to serve files as-is
```

The three pages are hash routes (`#/`, `#/apps`, `#/contact`), so deep links and refreshes
work on GitHub Pages with zero extra configuration.

## Publish on GitHub Pages

1. Commit and push to the `main` branch of `github.com/brandonjabr/dev`.
2. On GitHub: **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Choose branch **`main`** and folder **`/ (root)`**, then **Save**.
5. Wait ~1 minute — the site goes live at **https://brandonjabr.github.io/dev/**.

### Using the custom domain (optional)

To serve it at `brandonjabr.dev`:

1. In **Settings → Pages → Custom domain**, enter `brandonjabr.dev` and save
   (this adds a `CNAME` file to the repo).
2. At your domain registrar, add DNS records pointing to GitHub Pages:
   - Four `A` records for the apex domain → `185.199.108.153`, `185.199.109.153`,
     `185.199.110.153`, `185.199.111.153`
   - (or a `CNAME` for `www` → `brandonjabr.github.io`)
3. Back in Pages settings, enable **Enforce HTTPS** once the certificate is issued.

## Run locally

Just open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Updating app content

App names, descriptions, features, and screenshots live in the `APPS` array near the top of
the `<script type="text/babel">` block in `index.html`. Add or edit entries there; drop new
images into `assets/`.
