---
title: "CSS backdrop-filter: Glassmorphism and Background Effects"
date: 2025-10-30
category: visual effects
difficulty: advanced
source: https://developer.mozilla.org/en-US/docs/Web/CSS/backdrop-filter
author: Emily Lubonty
---

# CSS backdrop-filter: Glassmorphism and Background Effects

The `backdrop-filter` property applies visual effects to the area behind an element, creating the glassmorphism design trend. Unlike `filter`, which affects the element itself, `backdrop-filter` affects only what's visible through the element's background, creating a frosted glass effect. Common functions include `blur()`, `brightness()`, `contrast()`, and `saturate()`. The element requires a semi-transparent background for the effect to be visible.

Glassmorphism combines `backdrop-filter: blur()` with semi-transparent backgrounds, subtle borders, and shadows to create depth and hierarchy. This technique works best on elements overlaying colorful backgrounds. Performance is GPU-accelerated but can be expensive on low-end devices, so use sparingly. Modern browsers support it well.

## Example

```css
/* Basic glassmorphism card */
.glass-card {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px) saturate(180%);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 12px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
}

/* Navigation bar with frosted glass */
.navbar {
  position: fixed;
  top: 0;
  background: rgba(0, 0, 0, 0.5);
  backdrop-filter: blur(20px) brightness(1.2);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

/* Modal overlay with blur */
.modal-backdrop {
  background: rgba(0, 0, 0, 0.3);
  backdrop-filter: blur(8px);
}
```

## When to Use

Use backdrop-filter for navigation bars, modals, cards, and popovers overlaying dynamic content. It creates visual separation while maintaining context. Ideal for modern app interfaces and hero sections where the background adds visual interest. Avoid on low-end devices or over static backgrounds.

**Source**: [MDN: backdrop-filter](https://developer.mozilla.org/en-US/docs/Web/CSS/backdrop-filter)
