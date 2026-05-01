# Adding Blog Posts

The blog system has been removed from the live site (no real posts yet). This guide covers everything needed to write a post and put the blog back on the homepage when ready.

## Writing a new post

1. Create a folder for the post: `content/blog/your-post-slug/`  
   Use kebab-case for the slug (it becomes the URL).
2. Inside that folder, create `index.md` with the frontmatter below.
3. Optionally add a `featured.png` (or `.jpg`) in the same folder for the card thumbnail. Recommended size: 1200x630 px.

### Frontmatter schema

```yaml
---
title: "Post Title Here"
date: 2026-05-01
summary: "One or two sentences shown on the blog card and used for SEO."
tags:
  - Tag One
  - Tag Two
  - Tag Three
authors:
  - me
featured: true   # set to false for older / less prominent posts
---
```

After the frontmatter (closing `---`), write the post body in markdown. Headings, code blocks, images, lists, and links all work as expected.

### Image references in the body

Images placed in the post folder can be referenced relative to the post:

```markdown
![Description of image](image-name.png)
```

## Putting the blog back on the homepage

Once at least one post exists in `content/blog/`, restore the homepage section by pasting the block below into `content/_index.md`. It belongs after the Experience Timeline block and before the Contact Section block (search for `# Contact Section` to find the correct spot).

```yaml
  # Recent Blog Posts
  - block: collection
    id: blog
    content:
      title: Recent Posts
      subtitle: ''
      text: ''
      filters:
        folders:
          - blog
        exclude_featured: false
      count: 3
      order: desc
    design:
      view: card
      columns: 3
      background:
        color:
          light: "#f5f5f5"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
```

Tweak before pasting:
- Update `subtitle` to something that fits the blog (e.g., "Notes on data, ops, and the AI age").
- `count: 3` shows the three most recent posts. Increase or decrease to taste.
- `columns: 3` sets the grid width. Use `2` for a wider card layout, `1` for a single column.

## Deploying

After saving any new post or homepage edit:

```bash
git add -A
git commit -m "Add blog post: <title>"
git push origin main
```

GitHub Actions builds and deploys automatically. The post appears on the live site within 2 to 3 minutes.

## Reference: a minimal post example

```markdown
---
title: "Why Domain Knowledge Beats Model Tuning"
date: 2026-05-15
summary: "Reflections from the car price prediction project on why feature engineering carried more weight than algorithm choice."
tags:
  - Machine Learning
  - Feature Engineering
  - Reflection
authors:
  - me
featured: true
---

The first time I trained a regression model end to end, I expected the model choice to matter most. It didn't.

## What actually moved the needle

The features I added based on what I knew about the data carried more predictive weight than any tweak to the algorithm. PyCaret's automated comparison confirmed it: the same engineered features outperformed the raw inputs across every model family I tried.
```

That's the full lifecycle: create folder, write markdown, push.
