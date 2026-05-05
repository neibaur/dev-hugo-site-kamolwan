# Isaac Neibaur Portfolio

Source for [isaacneibaur.com](https://isaacneibaur.com), a Hugo Blox portfolio focused on business intelligence, data engineering, automation, and technical leadership.

This repository builds the development source site. Production is published by GitHub Actions to [`neibaur/github.io`](https://github.com/neibaur/github.io), which serves `isaacneibaur.com`.

## Tech Stack

- Framework: Hugo Extended
- Theme/system: Hugo Blox
- Styling/assets: Hugo Blox assets plus local overrides in `assets/`
- Search indexing: Pagefind
- Hosting: GitHub Pages via cross-repo deploy

## Branches

- `main` is the production trunk branch. Changes merged to `main` are expected to be deployable.
- `dev` is for experiments and should not be treated as the release branch.
- Keep commits small and atomic so content, layout, and tooling changes can be reviewed independently.

## Local Development

Run the local Hugo server:

```bash
hugo server --disableFastRender
```

Then open <http://localhost:1313>.

Build the production site locally:

```bash
hugo --gc --minify
```

If Hugo has trouble pruning the default user cache on Windows, use a repo-local absolute cache directory:

```powershell
hugo --gc --minify --cacheDir "$PWD\.hugo-cache"
```

## Key Folders

- `content/`: Authored site pages and collections.
  - `content/_index.md`: Homepage landing page configuration.
  - `content/experience.md`: Experience page layout.
  - `content/education.md`: Education and certifications page layout.
  - `content/projects/`: Portfolio project pages.
  - `content/publications/`: Publication pages, if used.
  - `content/events/`: Talk/event pages, if used.
- `data/authors/me.yaml`: Primary profile, biography, education, experience, skills, awards, and certifications.
- `layouts/shortcodes/`: Custom local shortcodes used by portfolio content.
- `layouts/_partials/`: Local Hugo Blox partial overrides.
- `assets/css/custom.css`: Local CSS customizations.
- `assets/media/authors/me.png`: Profile image.
- `static/uploads/`: Resume, thesis, and other downloadable public files.
- `_drafts/`: Starter/template content kept out of the production Hugo content tree.

## Content Notes

This site uses custom shortcodes such as `display_list`, `bio_grid`, `landing_anchor`, `sidebar_button`, and `sidebar_title`. Preserve those shortcodes when editing content; they are part of the portfolio experience.

Avoid committing generated output such as `public/`, `resources/`, `.hugo_build.lock`, `hugo_stats.json`, and Pagefind output. These are ignored by `.gitignore`.

## Deployment

Pushing deployable work to `main` triggers GitHub Actions. The deploy workflow builds this Hugo site, publishes the generated `public/` output to [`neibaur/github.io`](https://github.com/neibaur/github.io), and updates [isaacneibaur.com](https://isaacneibaur.com).
