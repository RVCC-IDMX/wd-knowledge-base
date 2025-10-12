---
title: "CSS Grid DevTools: Debugging Grid Layouts"
date: 2025-10-10
category: css-layout
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout
author: William Harvey
---

# CSS Grid DevTools: Debugging Grid Layouts

When you want to debug a grid, it usually involves looking at how your elements are placed within the grid. The first thing you want to do is to make sure that the you have the proper elements like display: grid (this is very important to have). Now look at your grid-template-columns and grid template-rows to make sure that the number of tracks matches the number of items you want to be displayed. That's just one example of debugging grid layouts.

## Example

```css
.debug-grid {
  display: grid;
  outline: 2px solid red;
  background: rgba(255, 0, 0, 0.1);
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: auto;
  gap: 10px;
}

.debug-grid > * {
  border: 1px solid blue;
  background: rgba(0, 255, 0, 0.2);
  padding: 10px;
  position: relative;
}

.debug-grid > *::before {
  content: counter(item);
  counter-increment: item;
  position: absolute;
  top: 2px;
  left: 2px;
  background: yellow;
  padding: 2px 4px;
  font-size: 12px;
  font-weight: bold;
}

.debug-grid {
  counter-reset: item;
}

.debug-grid .problem-item {
  background: rgba(255, 0, 0, 0.5) !important;
  border: 2px solid red !important;
}

.debug-grid[data-areas] {
  grid-template-areas: 
    "header header header"
    "sidebar main aside"
    "footer footer footer";
}
```

## When to use

-When you want to build a new grid layout and items aren't positioned correctly
-When gaps don't look correct
-Don't use it as a permanent solution

**Source**: [MDN: Grid-layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout)
