# linyinyi.github.io — personal academic website of Dr. Yinyi Lin

Academic website built on the [al-folio](https://github.com/alshedivat/al-folio) v1.x template
(Jekyll + plugin gems), deployed automatically to GitHub Pages.

**Live site:** <https://linyinyi.github.io> · **Owner:** Yinyi Lin (<yinyilin@hku.hk>)

---

## How the site is organized

| What                 | Where                                           | Notes                                                 |
| -------------------- | ----------------------------------------------- | ----------------------------------------------------- |
| Site identity & SEO  | `_config.yml`                                   | name, description, keywords, URL, feature flags       |
| Homepage             | `_pages/about.md`                               | hero, focus cards, featured research, collaboration   |
| Research themes      | `_data/research.yml`                            | single source for homepage cards **and** `/research/` |
| Publications         | `_bibliography/papers.bib`                      | BibTeX is the authoritative record                    |
| Projects             | `_projects/*.md`                                | one file per project, `importance` sets order         |
| News                 | `_news/YYYY-MM-DD-slug.md`                      | shown on homepage (latest 5) and `/news/`             |
| Teaching             | `_teachings/geog7142.md` + `_pages/teaching.md` | course pages                                          |
| CV                   | `_data/cv.yml`                                  | RenderCV format; drives web CV **and** the PDF        |
| Social/profile links | `_data/socials.yml`                             | email, Scholar, GitHub, ORCID, LinkedIn…              |
| Metrics (optional)   | `_data/metrics.yml`                             | hidden until `enabled: true` with verified values     |
| Brand styling        | `_sass/_brand.scss`                             | palette (light/dark), typography, cards, diagram      |
| Images               | `assets/img/{profile,research,projects}/`       | replace the placeholder SVGs with real figures        |

## Common tasks

### Edit the biography / homepage

Edit `_pages/about.md`. The intro paragraph, buttons, and section order all live there.
The four research-focus cards come from `_data/research.yml`.

### Add a publication

1. Append a BibTeX entry to `_bibliography/papers.bib` (newest entries can go anywhere; grouping is automatic).
2. Recommended custom fields:
   - `abbr = {JournalAbbr}` — venue badge (link it in `_data/venues.yml`)
   - `keywords = {geoai, urban-health, climate-resilience, urbanization}` — theme tags (used by `/research/`)
   - `selected = {true}` — shows it under "selected publications" on the homepage
   - `doi`, `html`, `pdf`, `code`, `data`, `website` — action buttons (omit what you don't have; never upload publisher PDFs unless licensing permits)
   - `preview = {file.png}` — thumbnail, placed in `assets/img/publication_preview/`
3. Author annotation: "Lin, Yinyi / Y." is underlined automatically (`scholar:` section of `_config.yml`).

### Mark a publication as selected

Add `selected = {true}` to the entry. Keep the homepage list to ~5 papers.

### Add a project

Copy any file in `_projects/`, update the front matter (`title`, `description`, `img`,
`importance`) and body. Use the status badge markup at the top
(`yl-status-published` / `yl-status-ongoing`) and keep status labels truthful —
never label under-review work as published.

### Add news

Create `_news/YYYY-MM-DD-short-slug.md` with front matter
(`layout: post`, `date:`, `inline: true`, `category:`) and one or two factual sentences.

### Update the CV

Edit `_data/cv.yml` (RenderCV format — see the comments at the top for which entry
shapes to use). On push, the `render-cv` workflow regenerates
`assets/rendercv/rendercv_output/Yinyi_Lin_CV.pdf` automatically and commits it.
Update the "Last updated" date in `_pages/cv.md`'s `description`.

### Replace images

- Portrait: add e.g. `assets/img/profile/prof-pic.jpg` and update `profile.image` in `_pages/about.md`.
- Research/project figures: drop images into `assets/img/research/` or `assets/img/projects/`
  and update the paths in `_data/research.yml` / `_projects/*.md`. JPG/PNG files get
  responsive WebP variants automatically at build time. Use meaningful filenames and update alt text.
- Only use images you have the right to publish.

### Update metrics ("research by the numbers")

Edit `_data/metrics.yml`: fill in **verified** values, set `source` and `last_updated`,
then set `enabled: true`. The homepage section stays hidden while disabled.
Citation counts on publication entries are refreshed by the scheduled
`update-citations` workflow (Mon/Wed/Fri); its failure never blocks deployment.

## Preview locally

```bash
# prerequisites: Ruby ≥ 3.3, Bundler, ImageMagick, Node 20+
bundle install
npm ci
bundle exec jekyll serve   # http://localhost:4000
```

Or with Docker: `docker compose up` (see `docs/INSTALL.md`).

Before pushing, run the same checks CI runs:

```bash
npx prettier --check .
bundle exec al-folio upgrade audit --no-fail
JEKYLL_ENV=production bundle exec jekyll build
```

## Deploy

Pushing to `main` triggers `.github/workflows/deploy.yml`, which builds the site and
publishes `_site/` to the `gh-pages` branch. One-time repository setup:

1. GitHub → Settings → Pages → Source: **Deploy from a branch** → Branch: **gh-pages** / root.
2. Push to `main`; the first deploy creates the `gh-pages` branch.

Other workflows: `prettier` (format check), `broken-links-site` (lychee check of
every internal link in the rendered site, after each deploy), `render-cv` (CV PDF),
`update-citations` (scheduled Scholar refresh, isolated from deploys), `axe`
(manual accessibility audit), `upgrade-check` (template drift audit).

Note: the deploy workflow only triggers when files matching its `paths:` filter
change (`.md`, `.yml`, `.liquid`, `.svg`, `.scss`, `.bib`, `assets/**`, …). If you
add a new file type and a push doesn't deploy, extend the filter in
`.github/workflows/deploy.yml` or trigger it manually via Actions → Deploy site
→ Run workflow.

### Custom domain

To serve at `[CUSTOM_DOMAIN]`: add a `CNAME` file containing the domain, set
`url: https://[CUSTOM_DOMAIN]` in `_config.yml`, configure DNS (CNAME → `linyinyi.github.io`),
and enable HTTPS under Settings → Pages.

## Troubleshooting a failed build

1. Open the failed run under the repo's **Actions** tab and read the first red step.
2. YAML errors: check the last file you edited (indentation, unclosed quotes) —
   `python3 -c "import yaml; yaml.safe_load(open('_config.yml'))"`.
3. BibTeX errors: an unclosed brace in `papers.bib` breaks the publications page.
4. CV PDF errors: run `rendercv render _data/cv.yml --settings assets/rendercv/settings.yaml`
   locally; RenderCV prints which field is invalid.
5. Prettier failures: `npx prettier --write <file>`.
6. More: `docs/TROUBLESHOOTING.md` and `docs/FAQ.md`.

## Content integrity rules

- Never invent publications, co-authors, dates, awards, grants, or metrics.
- Mark unverified information with `TODO:` comments instead of guessing
  (search the repo for `TODO:` to see what still needs confirmation).
- Distinguish published / under review / ongoing work explicitly.
- Keep private data (phone, address, IDs) off the site.

## Template upkeep

This repo tracks al-folio v1.x. `bundle exec al-folio upgrade audit` reports drift.
One intentional local override exists (`assets/css/main.scss`, registered in
`.al-folio-overrides.yml`) — after a gem update, run
`bundle exec al-folio upgrade overrides audit` and re-sync if flagged.
Site-specific styling lives in `_sass/_brand.scss`.
