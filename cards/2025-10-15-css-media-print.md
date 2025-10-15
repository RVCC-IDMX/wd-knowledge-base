---
title: "CSS @media print: Optimizing Styles for Printed Pages"
date: 2025-10-15
category: interactive
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/@media
author: Emily Lubonty
---

# CSS @media print: Optimizing Styles for Printed Pages

`@media` is a CSS at-rule that can apply part of a style sheet from one or more media queries. This at-rule can be placed at the top of the code, or nested within other conditional group's at-rules. `@media` can also be used to target certain devices, such as printers or audio-based screen readers. The `@media` rule can also be used to target multiple devices at once. `@media` can also set up how webpages can appear as a PDF for wanting to print on paper, or how it is displayed on a screen. This will allow the webpage to appear differently and fit properly on a piece of paper rather than appearing as-is on the screen.

## Example

```css
@media print{
    \*...*\ 
}
```

## When to Use

Use when wanting to create pages that are meant to be printed, such as recipes or flyers. Also use when page needs to be converted or downloaded as a PDF.

**Source**: [MDN: @media](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)

**Additional Source** [MDN: Using media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries)

**Additional Source** [MDN: Printing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Printing)
