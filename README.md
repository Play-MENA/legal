# PlayMENA Legal

Static site hosting PlayMENA's **Privacy Policy** and **Terms & Conditions**, served via GitHub Pages.

## Structure

| File | Purpose |
| --- | --- |
| `index.html` | Landing page (Legal Center) linking to both documents |
| `privacy.html` | Privacy Policy |
| `terms.html` | Terms & Conditions |
| `styles.css` | Shared styles for all pages |
| `.nojekyll` | Tells GitHub Pages to serve files as-is (no Jekyll build) |

## Before publishing: fill in placeholders

The documents contain template text with placeholders wrapped in brackets and
highlighted on the page, e.g. `[COMPANY LEGAL NAME]`, `[PRIVACY CONTACT EMAIL]`,
`[MINIMUM AGE]`, `[GOVERNING JURISDICTION]`. Search the HTML files for `[` to
find them all and replace with real values. Also update the `Last updated` date
and the footer email/copyright as needed.

> ⚠️ These templates are a starting point, not legal advice. Have the final
> wording reviewed by qualified legal counsel before publishing.

## Enable GitHub Pages

1. Push this repo to `github.com/Play-MENA/playmena-legal`.
2. Go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Select branch `main` and folder `/ (root)`, then **Save**.
5. After a minute, the site will be live at:
   `https://play-mena.github.io/playmena-legal/`

### Direct links

- Privacy Policy: `https://play-mena.github.io/playmena-legal/privacy.html`
- Terms & Conditions: `https://play-mena.github.io/playmena-legal/terms.html`

## Local preview

Open `index.html` directly in a browser, or run a local server:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```
