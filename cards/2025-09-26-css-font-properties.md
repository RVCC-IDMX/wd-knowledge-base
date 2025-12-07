---
title: CSS Font Properties:family, size, weight and style
date: 2025-09-26
category: css-layout
difficulty: starter
source: https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Text_styling/Fundamentals
author: Olivia Denton
---

# CSS Font Properties

To manage the typeface and sizing of your text, you use the font-family property to specify one or more preferred fonts for the browser to use, relying on system availability for rendering. Text size is controlled by the font-size property, which commonly uses units like px for absolute size, em for size relative to the parent element, or rem for size relative to the root (<html>) element—the latter being favored for scalable typography since 1rem usually corresponds to the default html size of 16px. The font size is inherited from the parent element unless explicitly overridden. Additionally, you can adjust the appearance using font-style to turn italics (or oblique simulation) on or off, and font-weight to control the boldness.

## Example

```css
/* font-family, font-size, font-weight, font-style example */
p {
  font-family: Arial, "Trebuchet MS", Verdana;
  font-size: 5rem;
  font-weight: bold;
  font-style: italic;
}
```

## When to Use

You should use the CSS font properties discussed (font-family, font-size, font-style, and font-weight) whenever you need to control the basic appearance, readability, and hierarchy of text on a web page. Use font-family to define the typeface of your text like for branding and design, readability and fallbacks. Use font-size to establish a visual hierarchy and ensure content is readable and for scaling. Use these properties to add emphasis, differentiate text, or adjust its visual impact.

**Source**: [MDN: Fundamental Text and Font Styling](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Text_styling/Fundamentals)
