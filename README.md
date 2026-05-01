# annelizekrause.com

Source for [annelizekrause.com](https://annelizekrause.com), the personal portfolio site of Annelize Krause, business and operations analyst.

## Stack

- **Static site generator:** [Hugo](https://gohugo.io) (extended)
- **Theme:** [HugoBlox dev-portfolio](https://github.com/HugoBlox/hugo-theme-developer-portfolio) loaded as a Hugo Module
- **Styling:** Tailwind CSS v4 (via the theme)
- **Search:** Pagefind (built at deploy time)
- **Hosting:** GitHub Pages with custom domain (DNS via Namecheap)
- **CI / CD:** GitHub Actions builds and deploys on every push to `main`

## Repo layout

```
annelizekrause.com/
├── assets/
│   └── media/icons/custom/    Custom Tech Stack SVGs (overrides devicon)
├── config/_default/           Hugo config (split across hugo.yaml, params.yaml, etc.)
├── content/
│   ├── _index.md              Homepage block configuration
│   ├── projects/              One folder per project (index.md + featured.jpg)
│   └── authors/me.yaml        (data file) Bio, links, experience, education
├── data/                      Hugo data files (used by the theme)
├── docs/                      Project docs and how-to guides (see below)
├── static/uploads/            Public assets: headshot, logos, resume.pdf
├── go.mod                     Hugo Module declarations
├── hugoblox.yaml              HugoBlox-specific config (deploy host, build version)
└── package.json               Tailwind / Pagefind dependencies (used in CI)
```

## How to make changes

Edit the relevant files, commit, and push to `main`:

```bash
git add -A
git commit -m "Describe what changed"
git push origin main
```

GitHub Actions builds and deploys automatically. Live in ~3 minutes.

No local tooling is required to ship changes. For local preview, install Hugo extended, Go, Node, and pnpm:

```bash
brew install hugo go node pnpm
pnpm install
pnpm dev
```

The dev server runs at `http://localhost:1313` with hot reload.

## Documentation

- [`docs/project-plan.md`](docs/project-plan.md) — original project plan
- [`docs/next-steps.md`](docs/next-steps.md) — what's parked for future iterations
- [`docs/adding-blog-posts.md`](docs/adding-blog-posts.md) — how to write new posts and re-enable the homepage Recent Posts block
- [`docs/customizing-tech-stack-icons.md`](docs/customizing-tech-stack-icons.md) — custom icon system, current icon mapping, where to find SVGs

## License

Site content (text, images, branding) is © Annelize Krause. The site infrastructure is built on the [HugoBlox dev-portfolio](https://github.com/HugoBlox/hugo-theme-developer-portfolio) template, which is MIT licensed.
