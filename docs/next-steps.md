# Next Steps

MVP shipped on 2026-05-01. The site at https://annelizekrause.com is live with full content (no demo placeholders remain visible). This document lists what's still parked, grouped by priority.

## High visibility (do before sharing widely)

Nothing in this category right now. The public-facing surface is complete and accurate.

## Repo housekeeping (low visitor impact, worth doing)

- [ ] **Replace `README.md`** — currently still the HugoBlox starter README. Should describe Annie's site briefly, link to the live URL, note the tech stack, and point to docs.
- [ ] **Decide on `LICENSE.md`** — currently HugoBlox's MIT license. For a personal portfolio site, options: keep MIT, switch to a personal-portfolio license (e.g., "code MIT, content CC-BY-NC"), or remove entirely.
- [ ] **Replace `.github/FUNDING.yml`** — currently links to HugoBlox sponsorship. Either remove or repoint to Annie's own funding source if one exists. Probably remove for now.
- [ ] **Update `docs/project-plan.md`** — the Tech Stack section still says "Hugo Profile"; update to HugoBlox dev-portfolio. The Decisions Log, Milestones, and Risks sections were planned but never written.

## Content additions (when ready, no rush)

- [ ] **Pre-2013 legal-secretary experience** — adding 2001-2013 legal secretary/researcher entries would substantiate the "18+ years" bio claim more concretely. Intentionally omitted from MVP to match the resume scope Masterschool approved.
- [ ] **New projects** — add to `content/projects/<slug>/index.md` with a `featured.jpg` thumbnail. The Featured Projects block on the homepage will pick them up automatically.
- [ ] **Blog posts** — see `docs/adding-blog-posts.md` for the schema and the homepage block to paste back. The blog system is fully removed for now; first post triggers re-enabling the section.
- [ ] **Google Data Analytics certification** — add to Education timeline (in `data/authors/me.yaml`) once the capstone project is done and there's a project to back it up. Until then it stays parked per the V2 deferred-until-after-internship plan.

## Optional enhancements

- [ ] **Enable author detail page** — currently disabled in `content/authors/_index.md` (`build: render: never`). Enabling it would render a dedicated `/author/me/` page using the data already in `data/authors/me.yaml`. Useful if any link starts pointing at the author profile.
- [ ] **Custom icons for new tools** — see `docs/customizing-tech-stack-icons.md`. Drop SVG into `assets/media/icons/custom/<name>.svg` and reference as `icon: custom/<name>` in the homepage YAML.
- [ ] **Iterate on Stef's feedback** — if any. Specific changes can be made incrementally; nothing structural needs revisiting.
- [ ] **Local dev environment** — install `brew install go node pnpm` if you want to preview changes locally before pushing. Currently every change is pushed straight to main and previewed live; faster but less safe for big edits.

## Related but outside this repo

- [ ] **Revise LinkedIn About** — the current LinkedIn copy is corporate-buzzword-heavy ("results-driven professional," "actionable insights," "drive efficiency"). The website bio is much sharper; consider updating LinkedIn to match the cleaner positioning.
- [ ] **Revise resume** — same shift in tone. Site bio's three sentences are a stronger opening than the current resume summary. Also consider genericizing past employer names on LinkedIn for the same reasons applied to the website.

## How to deploy any change

```bash
git add -A
git commit -m "Describe what changed"
git push origin main
```

GitHub Actions builds and deploys automatically. Live in ~3 minutes. No local tooling required.

## Reference docs in this repo

- `docs/project-plan.md` — original project plan (partially complete)
- `docs/adding-blog-posts.md` — full blog post workflow + homepage block to restore
- `docs/customizing-tech-stack-icons.md` — custom icon system, current icon mapping, sources for SVGs
