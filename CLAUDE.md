# nathendel.com

Static personal site for Nat Hendel, hosted on GitHub Pages at www.nathendel.com.
Plain HTML + one shared `style.css` (colors are tokens at its top); no build step, no framework. Keep it that way
unless Nat asks otherwise.

- Each page is `<slug>/index.html` so URLs stay clean and match the old Google Sites paths.
- The `<head>`, header nav and footer are duplicated in every page. When adding a
  page, copy an existing one, set `aria-current="page"` on its nav link, and add the
  new link to the nav in **every** page (including `404.html`).
- Use root-absolute links (`/style.css`, `/music-movies/`), which work on GitHub Pages.
- Video embeds use `youtube-nocookie.com/embed/<id>` inside `<div class="embed">`.
  Don't add `loading="lazy"` to embeds: it left them blank in testing.
- Tabs (in this order): Home `/`, Science `/science/`, Music `/music/`, Movies `/movies/`.
  Publications go in the `<ul class="pubs">` list on `science/index.html`. The dissertation
  page stays at its old URL. `home/`, `music-movies/` and `scientific-writing-and-papers/`
  are redirect stubs for old Google Sites links; keep them.
- Preview: `.claude/launch.json` runs `ruby -run -e httpd`. This Mac has no python3 or node.
- Publishing = commit and `git push` to `main`; GitHub Pages deploys in about a minute.
  Show Nat the preview and get approval before pushing.
- `CNAME` must stay `www.nathendel.com`.
