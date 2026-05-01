# Customizing Tech Stack Icons

The Tech Stack section uses icons from [devicon](https://devicon.dev/) by default. Several tools in our stack are missing from devicon entirely, and one (BigQuery) is using a placeholder.

This guide explains how to add custom SVG icons for the missing or incorrect ones.

## Current state

| Tool | Current icon | Status |
|---|---|---|
| Python | `devicon/python` | Correct |
| SQL | (none) | Devicon has no generic SQL icon. Currently text-only. |
| R | `devicon/r` | Correct |
| PostgreSQL | `devicon/postgresql` | Correct |
| **BigQuery** | `devicon/googlecloud` | **Wrong.** Renders as Google Cloud logo. BigQuery has its own logo that should be used. |
| Airtable | (none) | Devicon has no Airtable icon. Currently text-only. |
| pandas | `devicon/pandas` | Correct |
| NumPy | `devicon/numpy` | Correct |
| scikit-learn | `devicon/scikitlearn` | Correct |
| Tidyverse | `devicon/r` | Approximation. Tidyverse has its own logo (hex sticker). |
| Tableau | (none) | Devicon has no Tableau icon. Currently text-only. |
| Excel | (none) | Devicon has no Excel icon. Currently text-only. |
| Google Sheets | (none) | Devicon has no Google Sheets icon. Currently text-only. |
| Matplotlib | `devicon/matplotlib` | Correct |
| Seaborn | (none) | Devicon has no Seaborn icon. Currently text-only. |
| Plotly | `devicon/plotly` | Correct |
| VS Code | `devicon/vscode` | Correct |
| Google Colab | `devicon/googlecolab` | Correct |
| Git | `devicon/git` | Correct |
| GitHub | `devicon/github` | Correct |
| Notion | `devicon/notion` | Correct |

## Tools needing custom SVGs

Eight tools currently render without icons or with the wrong icon:

1. **SQL** (generic, no logo exists; could use a generic database icon)
2. **BigQuery** (replace Google Cloud icon)
3. **Airtable**
4. **Tidyverse** (replace approximation)
5. **Tableau**
6. **Excel**
7. **Google Sheets**
8. **Seaborn**

## How custom icons work

HugoBlox resolves icons in this priority order:
1. Built-in icon packs (devicon, brands, hero, hb)
2. **User-provided SVGs at `assets/media/icons/<pack>/<name>.svg`**

Custom SVGs in the assets folder override or supplement the built-in packs.

### File location convention

```
assets/media/icons/
  custom/
    bigquery.svg
    airtable.svg
    tableau.svg
    excel.svg
    google-sheets.svg
    seaborn.svg
    tidyverse.svg
    sql.svg
```

The `<pack>` folder name (`custom` here) can be anything. The filename without extension becomes the icon name.

### Reference in YAML

After dropping `bigquery.svg` into `assets/media/icons/custom/`, change the YAML in `content/_index.md`:

```yaml
- name: BigQuery
  icon: custom/bigquery
```

The path matches `<pack>/<filename-without-extension>`.

## Where to find SVGs

| Source | Notes |
|---|---|
| [Simple Icons](https://simpleicons.org/) | Brand logos for thousands of products. Has BigQuery, Airtable, Tableau, Microsoft Excel, Google Sheets, etc. SVGs are clean monochrome. |
| Official brand pages | Google Cloud has a dedicated brand asset library; Tableau, Microsoft, and others publish their logos for press use. Use these for "official" looking colored versions. |
| [Iconify search](https://icon-sets.iconify.design/) | Aggregates dozens of icon sets including Simple Icons. Good for browsing. |

## SVG format requirements

- **Format:** SVG (vector). Don't use PNG / JPG (will look blurry on retina).
- **Size:** doesn't matter; the block resizes to a fixed display size.
- **Colors:** monochrome (Simple Icons) renders cleanly in both light and dark mode. Multicolor brand SVGs work too but may look washed out on dark backgrounds.
- **No background:** the SVG should have a transparent background.

## Step-by-step: adding one icon

Example for BigQuery:

1. Visit [simpleicons.org](https://simpleicons.org/?q=bigquery) and search for `bigquery`.
2. Click the BigQuery result, then "Download SVG."
3. Rename the file to `bigquery.svg`.
4. Place it in `assets/media/icons/custom/bigquery.svg` (create the `custom` folder if it doesn't exist).
5. Open `content/_index.md`, find the BigQuery entry, change `icon: devicon/googlecloud` to `icon: custom/bigquery`.
6. Commit and push:

```bash
git add assets/media/icons/custom/bigquery.svg content/_index.md
git commit -m "Replace BigQuery placeholder icon with brand SVG"
git push origin main
```

CI rebuilds and deploys; new icon appears within a few minutes.

## Bulk replacement

To handle all eight at once:

1. Download all eight SVGs from Simple Icons into `assets/media/icons/custom/`.
2. Update each entry in `content/_index.md` to use `custom/<name>` paths.
3. Single commit, single push.

## License notes

Simple Icons SVGs are CC0 (public domain). No attribution required, no usage restrictions. Brand owners may have their own usage guidelines for their logos (typically: don't modify them, don't imply endorsement). Using a brand logo to indicate "I use this tool" is standard fair use and not problematic.
