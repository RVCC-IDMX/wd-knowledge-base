---
title: CSS ::scroll-marker Pseudo-Element
date: 2025-09-21
category: css-advanced
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/::scroll-marker
author: instructor
---

# CSS ::scroll-marker Pseudo-Element

The `::scroll-marker` pseudo-element is a cutting-edge CSS feature that styles scroll position indicators without JavaScript. It targets marker elements automatically generated for scrollable containers, enabling custom scroll progress visualization. **Key benefit**: Pure CSS scroll indicators that update automatically as users scroll, eliminating the need for scroll event listeners and manual DOM updates.

This pseudo-element works in conjunction with the `scroll-marker-group` property on containers. When applied, it generates visual markers for each scrollable section or snap point. The markers automatically highlight based on scroll position, providing intuitive navigation feedback. Think of it as built-in scroll-spy functionality without the performance overhead of JavaScript observers.

## Example

```css
/* Container setup */
.gallery {
  scroll-marker-group: after;
  scroll-snap-type: x mandatory;
  overflow-x: auto;
}

.gallery img {
  scroll-snap-align: center;
}

/* Style the auto-generated markers */
.gallery::scroll-marker {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: #ccc;
  transition: background 0.3s;
}

/* Active marker when section is in view */
.gallery::scroll-marker:target-current {
  background: #0066cc;
  transform: scale(1.2);
}

/* Create custom pagination dots */
nav::scroll-marker {
  content: '';
  display: inline-block;
  margin: 0 4px;
  cursor: pointer;
}
```

## When to Use

Use `::scroll-marker` for image carousels, section-based navigation, reading progress indicators, or any scrollable interface needing position feedback. 
Perfect for creating accessible scroll indicators that work without JavaScript. Currently experimental (2024+) with 
limited browser support—check compatibility and provide JavaScript fallbacks for production use.

**Source**: [MDN: ::scroll-marker](https://developer.mozilla.org/en-US/docs/Web/CSS/::scroll-marker)
