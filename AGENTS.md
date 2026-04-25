# Repository Guidelines

## Project Structure & Module Organization

This repository is a Jekyll site based on the al-folio theme. Main content lives in `_pages/`, `_posts/`, `_projects/`, and `_news/`. Shared templates are in `_layouts/` and `_includes/`; styles are in `_sass/` and compiled through `assets/css/`. Static files are organized under `assets/`, including `assets/img/`, `assets/pdf/`, `assets/js/`, and bibliography previews. Site data is stored in `_data/`, and publications are managed in `_bibliography/papers.bib`. Ruby plugins and helper scripts live in `_plugins/` and `bin/`.

## Build, Test, and Development Commands

- `bundle install`: install Ruby gems from `Gemfile`.
- `bundle exec jekyll serve`: run the site locally with Jekyll.
- `bundle exec jekyll build`: build the static site into `_site/`.
- `docker-compose up`: serve the site in the prebuilt Docker image on port `8080`.
- `docker-compose -f docker-local.yml up`: build and run a local Docker image.
- `pre-commit run --all-files`: run repository formatting and safety checks.

There is no separate unit test suite. Treat a successful Jekyll build and pre-commit run as the baseline validation.

## Coding Style & Naming Conventions

Use two-space indentation for YAML front matter and data files. Keep Markdown posts and pages readable with concise headings and valid front matter. Name posts with Jekyll dates, for example `_posts/2026-04-25-topic.md`. Keep includes and layouts lowercase with underscores when needed. Use SCSS partials in `_sass/` for styling changes instead of editing generated CSS. Pre-commit enforces trailing whitespace removal, final newlines, YAML validity, and large-file checks.

## Testing Guidelines

Before opening a PR, run `bundle exec jekyll build` and fix any Liquid, bibliography, or front matter errors. For visual changes, also run `bundle exec jekyll serve` or Docker and inspect affected pages locally. When editing `_data/*.yml`, run `pre-commit run check-yaml --all-files` or the full pre-commit suite.

## Commit & Pull Request Guidelines

Recent history uses short, imperative or descriptive messages such as `update intro`, `Update about.md`, and `sync`; keep commits focused and similarly concise. Pull requests should describe the changed pages or behavior, link related issues for features or bugs, and include screenshots for visible layout, image, or styling changes. Avoid committing generated `_site/` output, local caches, or large media unless they are intentional site assets.
