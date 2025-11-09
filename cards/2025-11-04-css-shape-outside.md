---
title: "CSS shape-outside: Wrapping Text Around Complex Shapes"
date: 2025-11-04
category: css-layout
difficulty: advanced
source: https://developer.mozilla.org/en-US/docs/Web/CSS/shape-outside
author: oliviad118
---

# CSS shape-outside: Wrapping Text Around Complex Shapes

The `shape-outside` CSS property enables text to wrap around non-rectangular shapes, creating magazine-style layouts and visually engaging designs. It works with floated elements and accepts values like `circle()`, `ellipse()`, `polygon()`, and `url()` for image-based shapes. The property defines the float area's shape, allowing inline content to flow naturally around custom geometries.

When using `shape-outside`, you must also apply `float` (left or right) to the element. The `shape-margin` property adds spacing between the shape and surrounding text. For image-based shapes using `url()`, combine with `shape-image-threshold` to control which alpha channel values define the shape boundary. Browser support is excellent in modern browsers (Chrome 37+, Safari 7.1+, Firefox 62+), though Edge requires version 79+.

## Example

```css
/* Circle shape with floated image */
.profile-image {
  width: 200px;
  height: 200px;
  float: left;
  shape-outside: circle(50%);
  shape-margin: 20px;
  margin: 0 20px 20px 0;
}

/* Polygon for custom geometric shape */
.diagonal-element {
  width: 300px;
  height: 300px;
  float: right;
  shape-outside: polygon(0 0, 100% 0, 100% 100%);
  clip-path: polygon(0 0, 100% 0, 100% 100%);
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  margin: 0 0 20px 20px;
}

/* Image alpha channel shape */
.organic-shape {
  width: 250px;
  height: 250px;
  float: left;
  shape-outside: url('shape-image.png');
  shape-image-threshold: 0.5;
  shape-margin: 15px;
}
```

## When to Use

Use `shape-outside` for editorial layouts with circular profile images, magazine-style text wrapping, or creative hero sections. Perfect for product showcases where text flows around product images, or artistic portfolio layouts. Combine with `clip-path` to make the element itself match the shape visually. Avoid for critical content layouts as it requires `float`, which removes elements from normal document flow.

**Source**: [MDN: CSS shape-outside](https://developer.mozilla.org/en-US/docs/Web/CSS/shape-outside)
