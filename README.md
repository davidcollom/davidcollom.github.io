# `davidcollom.github.io`

The source for my GitHub Pages site, published at [davidcollom.github.io](https://davidcollom.github.io).

This is a static site served from the `master` branch as the GitHub Pages source, using the classic
GitHub Pages static site layout.

## Contents

| Path | Description |
| ---- | ----------- |
| `index.html` | The site landing page — the content that is actually published. |
| `params.json` | Leftover page metadata from the retired GitHub Pages automatic page generator. |
| `stylesheets/` | Stylesheets for screen, mobile, print and non-screen rendering. |
| `javascripts/` | Client-side scripts (`modernizr.js`, `headsmart.min.js`, `main.js`). |
| `images/` | Site imagery. |
| `fonts/` | Open Sans web fonts in multiple formats. |

## Local preview

The site is static HTML, CSS and JavaScript, so it can be served directly:

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

Note that the page loads jQuery 1.7.1 from `ajax.googleapis.com` and then the `headsmart` jQuery
plugin from `javascripts/headsmart.min.js`, so the preview needs network access for jQuery.

## Editing the content

The page body is static HTML in `index.html`, under the `<section id="main_content">` element.
GitHub Pages serves `master` as-is (`build_type: legacy`, source path `/`), so editing
`index.html` and pushing is what changes the published site:

```bash
git add index.html
git commit -m "Update site content"
git push origin master
```

`params.json` is a leftover from the retired automatic page generator — it holds a `name`, a
`tagline`, a `body` and a `note`, but nothing in the repository reads it. Its `note` field warns
that the file is "used internally to help with page regeneration"; that referred to the old
`github.com/pages` generator, which wrote its output to a separate `gh-pages` branch. Pages now
serves `master` directly, so editing `params.json` has no effect on the live site.

## Customising the styling

`index.html` loads three stylesheets:

| Stylesheet | Description |
| ---------- | ----------- |
| `stylesheets/core.css` | Loaded for `media="screen"`. A small `@import` shim that pulls in `screen.css` for screen devices and `non-screen.css` for handheld and narrow screens. |
| `stylesheets/mobile.css` | Loaded separately for `media="handheld, only screen and (max-device-width:640px)"`. A complete standalone mobile layout, not an override of `core.css`. |
| `stylesheets/pygment_trac.css` | Styles for Pygments-generated markup. Every rule is scoped to a `.highlight` class, which the page's `<pre><code>` block does not use, so it has no effect on the published page. |

The main visual rules live in `stylesheets/screen.css`. `stylesheets/print.css` also exists, but it
is not referenced by `index.html` or any other stylesheet, so the print rules are currently dead
code.

## License

No licence file is included in this repository.
