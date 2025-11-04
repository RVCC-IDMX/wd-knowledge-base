---
title: CSS Stacking Context - Understanding z-index and Layer Creation
date: 2025-11-04
category: css-advanced
difficulty: advanced
source: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout/Understanding_z-index/Stacking_context
author: oliviad118
---

# CSS Stacking Context: Understanding z-index and Layer Creation

A stacking context is a three-dimensional conceptualization of HTML elements along an imaginary z-axis. Elements within a stacking context layer according to specific rules, with z-index values controlling their vertical order. The root element creates the base stacking context, but many CSS properties trigger new ones.

Common properties creating stacking contexts: positioned elements with z-index other than auto, flex/grid items with z-index other than auto, opacity less than 1, transform/filter/perspective properties, and isolation: isolate. Each stacking context is completely independent—child elements cannot escape their context regardless of z-index values.

Within a stacking context, elements stack in order: backgrounds/borders, negative z-index, non-positioned blocks, floats, inline elements, z-index auto/0, then positive z-index. Understanding this prevents frustrations where high z-index values fail because elements belong to different contexts.

Key insight: z-index only works on positioned elements within the same stacking context. A child with z-index: 9999 cannot appear above its parent's sibling with z-index: 1 if the parent created a new context.

## Example

```css
/* Parent creates stacking context with opacity */
.modal-container {
  position: relative;
  opacity: 0.99; /* Creates new stacking context */
  z-index: 1;
}

/* This z-index only compares within .modal-container */
.modal-backdrop {
  position: absolute;
  z-index: 1;
  background: rgba(0, 0, 0, 0.5);
}

.modal-content {
  position: absolute;
  z-index: 2; /* Appears above backdrop */
  background: white;
  padding: 2rem;
}

/* Separate stacking context for header */
.site-header {
  position: sticky;
  top: 0;
  z-index: 100; /* Independent from modal z-indexes */
  background: white;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

/* Debug: Isolate element to create stacking context */
.debug-layer {
  isolation: isolate; /* Creates context without side effects */
}

/* Transform creates stacking context */
.animated-card {
  transform: translateZ(0); /* Forces GPU acceleration and new context */
  z-index: 10;
}
```

## When to Use

Use stacking context understanding when debugging z-index issues, especially when elements don't stack as expected despite high z-index values. Create intentional stacking contexts with `isolation: isolate` to contain complex layering within components. Essential for modal overlays, dropdown menus, tooltips, and sticky headers where elements need predictable layering. Check if parent elements unintentionally create stacking contexts through opacity, transforms, or filters when child z-index values seem ineffective.

**Source**: [MDN: Understanding CSS z-index: Stacking Context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout/Understanding_z-index/Stacking_context)
