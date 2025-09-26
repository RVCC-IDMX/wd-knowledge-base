---
title: "CSS Responsive Typography for Readability: Font Size and Line Length. "
date: 2025-09-21
category: css-advanced
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/@media, https://developer.mozilla.org/en-US/docs/Web/CSS/font-size
author: Christopher Urban
---

# CSS Font Size and Line Length

Font size and line length are crucial to the presentation of a webpage. They are important for denoting titles or headers, as well as being the key to responsive styling. You need to modify the size of your font and the length of your lines depending on the size of the screen you are using to view the webpage. Using @media, you can establish media queries that check for screen sizes beyond specific points to ensure that your font is always properly scaled. You can use `font-size` and the clamp keyword to create a variable font size for your screen, then use @media to increase or decrease the clamp variance. Line length does not inherently have a keyword or function. Instead, modifying the width of an element or adjusting the margins can create the desired effects. `max-width` specifically can be catered towards specific character amounts per line.

## Example

```css
/* Fluid root font-size: scales between ~14px and ~18px */
html {
  font-size: clamp(14px, 1.2vw + 0.5rem, 18px);
}

/* Content column with a comfortable measure (line length) */
.content {
  max-width: 60ch; /* keeps lines ~45-75 characters for readability */
  margin: 2rem auto;
  padding: 0 1rem;
}

h1 {
  font-size: clamp(1.6rem, 2.5vw, 2.4rem);
  line-height: 1.1;
  margin: 0 0 0.5rem;
}

h2 {
  font-size: clamp(1.3rem, 2.2vw, 2rem);
  line-height: 1.1;
  margin: 0 0 0.5rem;
}

p {
  font-size: 1rem; /* relative to root */
  line-height: 1.6; /* improves readability */
  margin: 0 0 1rem;
}

/* Slightly different spacing on large screens */
@media (min-width: 900px) {
  .content {
    padding: 0 2rem;
  }
  p { line-height: 1.75; }
}

/* Small screens: reduce measure for shorter lines */
@media (max-width: 420px) {
  .content { max-width: 42ch; }
  html { font-size: 14px; }
}
```

## When to Use

This should be used whenever you wish to make a responsive typography. If you want your text to scale with screen size or adjust to the size of the window, this is how you would go about doing it. Font size and line length are critical to filling out the space of your webpage and avoiding embarassing amounts of emptiness. This is a key part of accessibility and the "mobile-out" design philosophy.

**Source**: [MDN: Font Size](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size), [MDN: @media](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)
