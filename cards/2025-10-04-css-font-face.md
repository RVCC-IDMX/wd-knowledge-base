---
title: "CSS @font-face and Font Loading Strategies"
date: 2025-10-04
category: typography
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face
author: Emily Lubonty
---

# CSS @font-face and Font Loading Strategies

The `@font-face` at-rule defines specific or custom fonts to display text with. The font can be loaded either locally or from a remote server on the user's personal computer. `@font-face` allows customization of fonts rather than being restricted to locally-installed ones. Using the `local()` function with a font name searches for the font installed locally on the user's device, while `url()` downloads the font resource being used. Descriptors include `font-family`, `src`, `size-adjust`, and `unicode-range`. These descriptors make it possible to use customized fonts while also being adjusted so they display properly.

# Example

```css
@font-face {
  font-family: "Pixelify Sans";
  src:
    local("Pixelify Sans"),
    url(PixelifySans-Regular.ttf);
}

body {
  font-family: "Pixelify Sans", serif;
  font-size: 24px;
}
```

```html
<body>
    Pixelify Sans demo
</body>
```

## When to use

Use when including customized or specific fonts as an alternative to locally-installed ones.

**Source**: [MDN: @font-face](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face)
