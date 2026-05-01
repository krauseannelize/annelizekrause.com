# Customizing Tech Stack Icons

The Tech Stack section uses icons from [devicon](https://devicon.dev/) by default, with custom SVGs filling the gaps for tools devicon doesn't cover.

This guide explains how the icon system works and how to add or replace icons.

## Current state

| Tool | Icon source | Notes |
|---|---|---|
| Python | `devicon/python` | |
| SQL | `custom/sql` | Generic SQL icon (no official SQL logo exists) |
| R | `devicon/r` | |
| PostgreSQL | `devicon/postgresql` | |
| BigQuery | `custom/bigquery` | |
| Airtable | `custom/airtable` | |
| Excel | `custom/excel` | |
| Google Sheets | `custom/google-sheets` | |
| pandas | `devicon/pandas` | |
| NumPy | `devicon/numpy` | |
| scikit-learn | `devicon/scikitlearn` | |
| Tidyverse | `custom/tidyverse` | Hex sticker from rstudio/hex-stickers |
| Tableau | `custom/tableau` | |
| Matplotlib | `devicon/matplotlib` | |
| Seaborn | `custom/seaborn` | |
| Plotly | `devicon/plotly` | |
| VS Code | `devicon/vscode` | |
| Google Colab | `devicon/googlecolab` | |
| Git | `devicon/git` | |
| GitHub | `devicon/github` | |
| Notion | `devicon/notion` | |

Custom SVGs live at `assets/media/icons/custom/<name>.svg`.

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
