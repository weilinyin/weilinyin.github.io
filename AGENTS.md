# Repository Guidelines

## Project Structure & Module Organization

This repository is a Jekyll-based academic website:

- Site configuration: `_config.yml`
- Content: `_pages/`, `_posts/`, `_publications/`, `_talks/`, `_teaching/`, `_portfolio/`, `_drafts/`
- Site data and navigation: `_data/`
- Templates and presentation: `_layouts/`, `_includes/`, `_sass/`, `assets/`
- Uploads and images: `files/`, `images/`
- Content generators: `markdown_generator/` (Python/notebook scripts for publications and talks)
- Helper scripts: `scripts/` (CV and content utilities)
- CI/CD: `.github/workflows/`

## Build, Test, and Development Commands

- `bundle install` - installs Ruby/Jekyll dependencies.
- `bundle exec jekyll serve -l -H localhost` - serves the site locally at `localhost:4000` with live reload.
- `bundle exec jekyll build --strict_front_matter` - validates front matter and builds the site; this is the CI check.
- `docker compose up --build` - runs the site in the provided Docker/DevContainer setup.
- `npm install` and `npm run build:js` - installs JS dependencies and regenerates `assets/js/main.min.js` from `assets/js/_main.js`, `theme.js`, and plugins.
- `python3 markdown_generator/talks.py markdown_generator/talks.tsv` and `python3 markdown_generator/publications.py markdown_generator/publications.tsv` - generate collection Markdown from structured data.

## Coding Style & Naming Conventions

- Use two-space indentation in YAML and SCSS.
- Use `YYYY-MM-DD-slug.md` for collection posts (e.g., `_publications/2025-06-08-paper-title.md`).
- Include valid YAML front matter (at minimum `title`, `date`, and the relevant `collection`/`layout`) in every content page.
- Match the surrounding style for HTML, SCSS, Ruby/Liquid, and Python; no formatter or linter is enforced.
- After editing JS sources, commit the regenerated `assets/js/main.min.js`.

## Testing Guidelines

There is no unit test framework or coverage threshold. The primary test is the strict Jekyll build: run `bundle exec jekyll build --strict_front_matter` before opening a PR, and manually verify changed pages, links, and layouts. The `talkmap.ipynb` workflow executes automatically when talk files change.

## Commit & Pull Request Guidelines

- Use short, imperative commit subjects. History uses conventional prefixes like `fix:`, `docs:`, `ci:`, and `feat:`, and references issue numbers where relevant (e.g., `#3138`).
- Create a descriptive branch off `master`, such as `fix/footer-overlap` or `docs/readme-wording`.
- Open PRs using `.github/PULL_REQUEST_TEMPLATE.md`: state the change type, summarize the change, link related issues, and include the commit hash you branched from.
- Add screenshots for visual changes and keep each PR focused on a single concern.

## Agent-Specific Instructions

Make only the requested edits, keep unrelated files unchanged, run the strict build after substantive changes, and do not commit generated artifacts (e.g., `_site/`, `Gemfile.lock`, `node_modules/`) unless the task explicitly requires them.
