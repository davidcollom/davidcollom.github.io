# `davidcollom.github.io`

The source for my GitHub Pages site, published at [davidcollom.github.io](https://davidcollom.github.io).

This is a static site served from the `master` branch as the GitHub Pages source, using the classic
GitHub Pages static site layout.

## Contents

| Path | Description |
| ---- | ----------- |
| `index.html` | The site landing page. |
| `params.json` | Page content and metadata used by the GitHub Pages generator. |
| `stylesheets/` | Stylesheets for screen, mobile, print and non-screen rendering. |
| `javascripts/` | Client-side scripts (`modernizr.js`, `headsmart.min.js`, `main.js`). |
| `images/` | Site imagery. |
| `fonts/` | Open Sans web fonts in multiple formats. |

## Local preview

The site is plain HTML and CSS, so it can be served directly:

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Editing the content

The page body lives in `params.json` under the `body` key, and the site title under `name`. The
`note` field is used internally by GitHub for page regeneration and should not be removed.

After editing, commit and push to `master` — GitHub Pages will rebuild and publish the site.

```bash
git add params.json
git commit -m "Update site content"
git push origin master
```

## Customising the styling

The main stylesheet is `stylesheets/core.css`, with separate overrides for mobile (`mobile.css`),
print (`print.css`) and devices without a screen (`non-screen.css`). Code blocks are styled by
`pygment_trac.css`.

## License

See the repository for licensing details.
