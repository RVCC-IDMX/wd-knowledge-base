---
title: "CSS currentColor keyword: Dynamic color inheritance"
date: 2025-09-25
category: visual effects 
difficulty: starter
source: https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#currentcolor_keyword
author: Sahar Naz
---

## CurrenColor keyword - Dynamic color inheritance

The currentColor keyword is a CSS keyword that refers to the elements compounded color value (text color). This enables dynamic inheritance of that color across other properties. This can be used anywhere a color is accepted including, backgrounds, borders, shadows, svg fills, etc. If the text color changes, all properties using currentColor will update automatically. This color change could be a parent style or theme change (light mode/dark mode)

## When to use

-To eliminate the need to repeat the same color in multiple properties.

-Keeps all components consistent with theme changes (dark mode, light mode, and user preferences).

-Enables dynamic color inheritance; components will automaticallu adpat to when parent text colors update.

## Code example

```css
.button {
  color: #3b82f6; /* Blue text */
  border: 2px solid currentColor; /* Border inherits blue */
  background: transparent;
  padding: 8px 16px;
}

.button:hover {
  color: #ef4444; /* Text changes to red */
  /* Border automatically becomes red too! */
}
```

```html
<button class="button">Hover me!</button>
```

**Source**: [MDN currentColor keyword](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#currentcolor_keyword)
