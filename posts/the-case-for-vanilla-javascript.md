---
title: "The Case for Vanilla JavaScript"
date: "2025-03-28"
tags: ["JavaScript", "Opinion"]
readingTime: "6 min read"
---

Every few months I hear a variation of the same question: *"Why aren't you using a framework?"*

And every time, I find myself saying the same thing: because I don't need one here.

This isn't a polemic against React, Vue, or any other framework. They're excellent tools. But I've noticed a tendency — in myself and others — to reach for them reflexively, before asking whether they're actually necessary.

## What frameworks solve

Frameworks earn their weight when you have:

- **Complex reactive state** — data that changes frequently and drives UI updates across many components
- **Large teams** — shared conventions reduce friction when multiple developers work on the same codebase
- **Rich component ecosystems** — when you need a calendar picker, a data table, or a drag-and-drop interface and don't want to build it from scratch

If you're ticking two or three of these boxes, a framework probably makes sense.

## What vanilla JavaScript actually offers

The browser platform in 2025 is genuinely powerful. Consider what's available without installing anything:

```javascript
// Fetch data
const res  = await fetch('/api/posts');
const data = await res.json();

// Update the DOM
document.getElementById('list').innerHTML =
  data.map(p => `<li>${p.title}</li>`).join('');

// Handle routing with the History API
history.pushState({ page: 'about' }, '', '#about');
window.addEventListener('popstate', handleNavigation);
```

CSS custom properties handle theming. `IntersectionObserver` handles scroll effects. `fetch` handles data. `classList` handles state-driven styling. Template literals handle templating.

For a personal blog, a portfolio, a small tool — this is enough.

## The hidden cost of dependencies

Every dependency you add is a contract. Someone else's decisions, bugs, deprecation timelines, and breaking changes become your problem.

Vanilla code has none of that. It will run in a browser five years from now exactly as it does today. It has no `node_modules`. It has no build step. You can open the file and read it.

> Simplicity is not a limitation. It's an architectural decision.

## When I reach for a framework

To be clear: I use frameworks. For complex applications with shared state and large teams, they're the right call. The point isn't to avoid them — it's to *choose* them deliberately, rather than by default.

The next time you start a new project, ask: *what problem am I actually solving?* Sometimes the answer is a framework. Often, it's just a well-structured JavaScript file.
