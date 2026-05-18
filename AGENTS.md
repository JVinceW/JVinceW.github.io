# Repository Guidelines

## Project Structure & Module Organization

This repository is a Jekyll-powered GitHub Pages site based on the Thinkspace theme. Root-level Jekyll configuration lives in `_config.yml`, with the main entry page in `index.html`. Layout templates are in `_layouts/`, reusable Liquid partials are in `_includes/`, and site data is in `_data/`. Content pages live in `contents/`; draft blog posts live in `_drafts/`. Static assets are grouped under `assets/`: Sass sources in `assets/scss/`, generated or standalone CSS in `assets/css/`, images in `assets/images/`, documents in `assets/docs/`, and icon fonts in `assets/icons/`.

## Build, Test, and Development Commands

- `bundle install`: install Ruby gems from `Gemfile` and `thinkspace.gemspec`.
- `bundle exec jekyll serve`: run the site locally, usually at `http://127.0.0.1:4000`.
- `bundle exec jekyll build`: generate the static site into `_site/`.
- `./script/cibuild.sh`: build the site and run `htmlproofer` with external link checks disabled; use this before publishing larger changes.

## Coding Style & Naming Conventions

Use existing Jekyll and Liquid conventions. Keep layouts in `_layouts` named by purpose, such as `page.html` or `post.html`, and includes in `_includes` named for the fragment they render. Markdown content should use YAML front matter and lowercase, hyphenated file names when adding posts or drafts. SCSS partials use leading underscores and are imported through `assets/scss/main.scss`. Match the existing two-space style in YAML and Liquid-heavy templates where practical.

## Testing Guidelines

There is no dedicated unit test suite. Validation is build-focused: run `bundle exec jekyll build` for quick checks and `./script/cibuild.sh` before handing off changes that affect links, templates, or generated pages. Inspect `_site/` output only as a generated artifact; do not commit it unless the publishing flow explicitly requires it.

## Commit & Pull Request Guidelines

Recent history uses short, informal imperative summaries such as `update resume` and `add download link and add my social medium`. Keep commits concise and focused on one change. Pull requests should describe the visible site impact, list validation commands run, link related issues when available, and include screenshots for layout, styling, image, or resume/CV updates.

## Agent-Specific Instructions

When changing code, prefer the repository knowledge graph tools for code discovery first. Fall back to `rg` or direct file reads for configuration, content, and other non-code assets.
