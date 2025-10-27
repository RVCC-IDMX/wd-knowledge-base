---
title: CSS Grid Gap and Spacing, Modern Grid Gutters
date: 2025-10-12
category: css-starter
difficulty: starter
source: https://developer.mozilla.org/en-US/docs/Web/CSS/gap
author: Christopher Urban
---

# CSS Grid and Gutters

The CSS Grid Layout provides a two-dimensional grid-based layout system that gives designers precise control over rows, columns, and the spacing between them. The spacing between grid tracks (rows or columns) is commonly called the "gutter". In modern CSS this is implemented with the `gap` property. However, for greater control over instances, the `column-gap` and `row-gap` can be used to affect rows and columns of a grid specifically.

## Example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width,initial-scale=1" />
    <title>Grid & Gutters Example</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <main class="grid-demo">
      <div class="card">1. News</div>
      <div class="card">2. Feature</div>
      <div class="card">3. Sidebar</div>
      <div class="card">4. Gallery</div>
      <div class="card">5. More</div>
      <div class="card">6. Extras</div>
    </main>
  </body>
</html>
```

```css
/* style.css (grid example) */
.grid-demo {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 1.25rem; /* the gutter between rows and columns */
  padding: 1.25rem;
}

.card {
  background: linear-gradient(180deg, #fff, #f7f7f7);
  border: 1px solid #ddd;
  padding: 1rem;
  border-radius: 6px;
  box-shadow: 0 1px 0 rgba(0, 0, 0, 0.04);
}

/* Responsive tweak: increase gutter on wide screens */
@media (min-width: 900px) {
  .grid-demo {
    gap: 2rem;
    padding: 2rem;
  }
}
```

## When to Use

Use `gap` to define gutters — it's simpler and more robust than using margins on children because `gap` does not collapse and works with grid alignment features.

**Source**: [MDN: gap](https://developer.mozilla.org/en-US/docs/Web/CSS/gap)
