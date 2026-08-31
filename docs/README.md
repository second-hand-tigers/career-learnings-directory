# What This Folder Is

This `docs/` folder is the **source for this repo's GitHub Pages website** —
Jekyll configuration and site pages that GitHub builds automatically into
a live site. It is *not* a place for project documentation, Word/Excel
files, or other reference material — despite the folder's name, which is
required as-is (see "Why It's Called `docs`" below).

If you're looking for documentation *about* this repo's subject matter,
check the repo's main README, its Wiki, or a `/slides` folder if one
exists — not here.

## Why It's Called `docs`

GitHub Pages, when set to "Deploy from a branch," only allows two source
locations: the repo root, or a folder named exactly `docs`. There is no
way to rename it without switching to a GitHub Actions-based build
instead — a bigger, higher-maintenance setup this project deliberately
avoids in favor of GitHub's automatic build-on-push. If you're copying
this pattern for your own site, `docs` isn't optional; the name is a
platform requirement, not a choice.

## Files Currently In Use Here

| File | Purpose |
|---|---|
| `_config.yml` | Site-wide settings: title, description, and which built-in theme to use (`theme: jekyll-theme-cayman`, etc.). One of GitHub's 13 supported themes — changing themes is a one-line edit here, no other files need to change. |
| `index.md` | The site's home page. Front matter at the top (`layout: default`, `title: ...`) plus the page content in Markdown below it. |
| `about.md` *(where present)* | An additional standalone page, reached at its own URL via `permalink: /about/` in its front matter. Any additional page follows this same pattern — front matter + Markdown content, in its own `.md` file. |

Every page here that isn't `_config.yml` needs `layout: default` in its
front matter — that's the one layout name guaranteed to exist across
all of GitHub's supported themes, so pages keep working correctly if the
theme in `_config.yml` ever changes.

## Other Files You Might Add Later

None of these exist yet, but they're standard parts of a Jekyll/GitHub
Pages site and may show up here as this site grows:

| File / Folder | Purpose |
|---|---|
| `assets/css/style.scss` | Custom CSS overrides layered on top of the chosen theme (e.g. shrinking a banner's padding) without abandoning the theme itself. Must start with an empty `---` front-matter block, then `@import "{{ site.theme }}";`, then your overrides. |
| `assets/images/`, `assets/` (general) | Images or other static files the site references — logos, screenshots, downloadable files linked from a page. |
| `_layouts/` | Custom page layouts, if the built-in theme layouts (`default`, etc.) stop being enough. |
| `_includes/` | Reusable snippets of HTML/Markdown pulled into multiple pages (a shared header, footer, or nav block), instead of copy-pasting the same content everywhere. |
| `_data/` | Structured data (YAML/JSON/CSV) a page can loop over — e.g. a contributors list or a table of contents rendered from data instead of hand-written Markdown. |
| Additional `.md` pages | Each new top-level page (a Slides index, a Contact page, etc.) is just another `.md` file here with its own front matter and `permalink`. |
| `favicon.ico` | The small icon shown in a browser tab for this site. |
| `CNAME` | Only needed if this site is ever pointed at a custom domain instead of its default `github.io` URL. |

## Navigation Convention Used On This Site

Pages here follow a consistent navigation pattern established across
this organization's sites: an italicized breadcrumb line (or lines) at
the top of each page, above the main heading, using `<br>` to stack
multiple links on separate lines when needed — one to go "up" a level
(staying in the same website vs. GitHub-repo context you're already in),
and, where a direct GitHub-repo equivalent of this same page exists, a
labeled "Toggle to Repo View" / "Toggle to Page View" link to switch
between the two. New pages added here should follow the same pattern for
consistency.
