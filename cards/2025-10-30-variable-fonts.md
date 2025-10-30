---
title: Variable Fonts - Dynamic Typography with Font Variations
date: 2025-10-30
category: typography
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide
author: Emily Lubonty
---

# Variable Fonts: Dynamic Typography with Font Variations

Variable fonts revolutionize web typography by packaging multiple font styles into a single file. Instead of loading separate files for bold, italic, or different weights, variable fonts use variation axes like weight (wght), width (wdth), slant, and optical size (opsz) to create infinite typographic variations. This dramatically reduces HTTP requests and file sizes while enabling fluid, responsive typography.

The `font-variation-settings` property provides low-level control over custom axes, while high-level properties like `font-weight` work seamlessly with variable fonts. Browser support is excellent (95%+), making variable fonts production-ready for modern web projects.

Key benefits include performance optimization through reduced file sizes, design flexibility with fine-grained control over typography, and animation capabilities for creative effects. Variable fonts support both standard registered axes (weight, width, slant, italic, optical-size) and custom axes defined by font designers.

## Example

```css
/* Using high-level properties (preferred) */
@font-face {
  font-family: 'InterVariable';
  src: url('Inter-Variable.woff2') format('woff2');
  font-weight: 100 900; /* Variable weight range */
}

.heading {
  font-family: 'InterVariable', sans-serif;
  font-weight: 750; /* Any value between 100-900 */
}

/* Low-level control with font-variation-settings */
.custom-style {
  font-family: 'InterVariable', sans-serif;
  font-variation-settings: 
    'wght' 650,     /* Weight */
    'wdth' 115,     /* Width */
    'slnt' -10;     /* Slant */
}

/* Animated variable font */
@keyframes weight-shift {
  0%, 100% { font-variation-settings: 'wght' 300; }
  50% { font-variation-settings: 'wght' 900; }
}

.animated-text {
  font-family: 'InterVariable', sans-serif;
  animation: weight-shift 3s ease-in-out infinite;
}

/* Responsive typography with variable fonts */
.responsive-heading {
  font-family: 'InterVariable', sans-serif;
  /* Fluid weight based on viewport */
  font-weight: clamp(400, 40vw, 900);
}
```

## When to Use

Use variable fonts when you need multiple font weights or styles across your design system. They're ideal for responsive typography that adapts to screen size, interactive animations, and performance-critical sites. Variable fonts excel in design systems requiring fine-tuned typographic control. Avoid them only if you need just one or two specific weights, where traditional static fonts might be smaller.

**Source**: [MDN: Variable Fonts Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
