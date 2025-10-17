---
title: "CSS Multi-Column Layout: Newspaper-Style Text Flow"
date: 2025-10-17
category: Layout
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout
author: Sahar Naz
---

## CSS Multi-Column Layout: Newspaper-Style Text Flow

CSS Multi-Column Layout lets you flow text into newspaper-style columns so long blocks of text become easier to scan. It’s a simple way to break content into columns without using floats or complex grid code.

- Use column-count to set how many columns (e.g., 2 or 3).
- Use column-gap to control space between columns.
- Content flows automatically from one column to the next.
- Use column-span for elements that should stretch across all columns (like a heading).
- Good for articles, long text blocks; avoid for UI controls or where reading order matters.

## Code examples

```html

<style>
.article {
  column-count: 2;      /* two columns */
  column-gap: 24px;    /* space between columns */
  line-height: 1.6;
}
.heading-wide {
  column-span: all;    /* make this element span both columns */
}
</style>

<article class="article">
  <h2 class="heading-wide">Article title</h2>
  <p>Long paragraph of text that will automatically flow into the next column when it reaches the bottom of the first column.</p>
  <p>Another paragraph continues the flow across columns.</p>
</article>

```

## When to use

Use multi-column layout when you have long, linear text that benefits from a newspaper/magazine reading flow like articles, long blog posts, newslettrs, or printable/print-like pages.

**Source**: [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout)
