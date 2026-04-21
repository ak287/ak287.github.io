# ak287.github.io

Personal portfolio and blog, built with plain HTML, CSS, and JavaScript. Hosted on GitHub Pages. Developed by Claude.

## Structure

```
.
├── index.html          # Main SPA — About, Blog, Contact sections
├── style.css           # All styles
├── posts/
│   ├── index.json      # Blog post manifest (title, date, excerpt, slug)
│   └── *.md            # Individual post files with front matter
└── README.md
```

## Personalising the site

### index.html
- Replace `Your Name` / `YN` in the nav logo
- Update the bio, meta items (location, availability), and social links
- Edit or add project cards in the Projects section
- Update the Contact section with your real email and links

### style.css
- All colours are CSS variables at the top of the file under `:root {}`
- Change `--accent` to customise the highlight colour

## Writing a new blog post

**1. Create the markdown file**

Add a new file to `posts/` with the slug as the filename:
```
posts/my-new-post.md
```

Start the file with front matter:
```markdown
---
title: "My New Post"
date: "2025-05-01"
tags: ["Tag1", "Tag2"]
readingTime: "3 min read"
---

Your post content here...
```

**2. Register the post in the manifest**

Add an entry to `posts/index.json`:
```json
{
  "slug": "my-new-post",
  "title": "My New Post",
  "date": "2025-05-01",
  "excerpt": "A short description shown on the blog listing page.",
  "readingTime": "3 min read",
  "tags": ["Tag1", "Tag2"]
}
```

**3. Push to GitHub** — the post is live immediately.

## Local development

Because blog posts are fetched via `fetch()`, you need a local server (not just opening the HTML file directly in a browser). The easiest way:

```bash
# Python 3
python3 -m http.server 8080

# Node.js (npx)
npx serve .
```

Then visit `http://localhost:8080`.
