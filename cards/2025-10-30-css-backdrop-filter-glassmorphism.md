---
title: "CSS backdrop-filter: Glassmorphism and Background Effects"
date: 2025-10-30
category: visual effects
difficulty: advanced
source: https://developer.mozilla.org/en-US/docs/Web/CSS/backdrop-filter
author: Emily Lubonty
---

# CSS backdrop-filter: Glassmorphism and Background Effects

The `backdrop-filter` property applies visual effects like blur and color shifts to the area behind an element, creating the popular glassmorphism design trend. Unlike the `filter` property which affects the element itself, `backdrop-filter` only affects what's visible through the element's background. This creates a frosted glass effect where background content appears blurred and tinted while foreground content remains sharp. Common functions include `blur()`, `brightness()`, `contrast()`, and `saturate()`. The element needs a semi-transparent background for the effect to be visible.

Glassmorphism combines `backdrop-filter: blur()` with semi-transparent backgrounds, subtle borders, and shadows to create depth and hierarchy. This technique works best on elements overlaying colorful or complex backgrounds. Performance is GPU-accelerated but can be expensive on low-end devices, so use sparingly on critical UI elements. Browser support is excellent in modern browsers, though older versions may require fallbacks.

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

Use backdrop-filter for navigation bars, modals, cards, and popovers that overlay dynamic content. It creates visual separation and hierarchy while maintaining context of underlying content. Ideal for modern app interfaces, hero sections, and content overlays where the background adds visual interest. Avoid on low-end devices or when the element covers static, non-distracting backgrounds where transparency provides minimal benefit.

**Source**: [MDN: backdrop-filter](https://developer.mozilla.org/en-US/docs/Web/CSS/backdrop-filter)
