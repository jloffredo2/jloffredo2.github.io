# Project: joseph-loffredo.com

Personal academic website for Joe Loffredo (PhD candidate, MIT Political
Science; American political institutions, election policy, LLM methods).
Built with Quarto, hosted on GitHub Pages at <https://joseph-loffredo.com>.
Source repo: <https://github.com/jloffredo2/jloffredo2.github.io>.

## Working preferences

- Design is settled: MIT red (#750014), Roboto Serif headings via Google
  Fonts, Neue Haas Grotesk body via Typekit kit nck6fpm, social links as
  icons in the footer. Do not redesign; make design-only changes when asked.
- Keep `custom.scss` legible and commented.
- Match the local Quarto version to the GitHub Actions runner (latest
  release), or `quarto preview` layout diverges from the deployed site.

## Where things live

    _quarto.yml        site config, navbar, footer (social icons), resources
    custom.scss        ALL styling
    _includes/fonts.html   Google Fonts + Typekit <link> tags
    update-copyright.html  tiny script that sets the footer year
    index.qmd          bio + portrait
    research.qmd       publications, working papers, in progress
    data.qmd           datasets and code
    teaching.qmd, contact.qmd   rendered but NOT in the navbar
    CV/Loffredo_CV.pdf, CV/Loffredo_JMP.pdf   served as-is (see resources)
    profile.jpeg       headshot (no EXIF GPS; check again if replaced)
    CNAME              custom domain; must stay in `resources:`
    .github/workflows/publish.yml   render + deploy on push to main

## Making updates

    quarto preview     # live-reloading local server
    git push           # GitHub Actions renders and deploys; no manual publish

**Add a paper** — copy a `::: {.pub}` block in `research.qmd`. Abstract goes
in the `.abstract` div next to the `<details class="wp">` summary pill.

**Replace the CV or JMP** — overwrite the PDF in `CV/` and push. The navbar
"Job Market Paper" link points at `CV/Loffredo_JMP.pdf`; the Research page
links the SSRN version.

**Add a static file** — put it in `CV/` or add its folder to `resources:` in
`_quarto.yml`, or it will not be published and links to it will 404.

## Traps

- `quarto preview` does not re-copy changed PDFs or images. `touch
  _quarto.yml` to force a rebuild.
- Do not run `quarto render` while `quarto preview` is running; the preview
  can overwrite `_site/` with stale output. Kill preview, `rm -rf _site
  .quarto`, render, restart.
- The footer email is a plain `mailto:loffredo@mit.edu`. A percent-encoded
  address was tried and broke the link in some mail clients; keep it plain.
- `.RData`, `.Rhistory`, `.Rproj`, and macOS `Icon\r` files are ignored on
  purpose. Do not re-add them.
- `link-external-newwindow: true` is applied by Quarto's client-side script
  at page load, so `target="_blank"` will NOT appear in the rendered HTML.
  Check it in a browser, not with grep.
- `website: description` only feeds Open Graph / Twitter card tags, which
  need `open-graph: true` and `twitter-card: true`. The plain
  `<meta name="description">` comes from each page's own `description:`.
