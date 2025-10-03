---
title: "CSS Display Property: block, inline, inline-block, and none"
date: 2025-10-03
category: CSS Core 
difficulty: starter
source: https://developer.mozilla.org/en-US/docs/Web/CSS/display
author: Sahar Naz
---

## CSS Display Property - block, inline, inline-block, and none

**Block elements:**

- Take up the full width available
- Start on a new line
- Examples: `<div>`, `<h1>`, `<p>`

**Inline elements:**

- Only take up as much width as needed
- Stay on the same line with other elements  
- Examples: `<span>`, `<a>`, `<strong>`

**Inline-block elements:**

- Best of both worlds - stay inline but can have width/height
- Useful for buttons, navigation items

**None:**

- Completely hides the element from the page

## Code examples

```html
<div>I'm a block element</div>
<div>I'm also a block element</div>

<span>I'm inline</span>
<span>Me too!</span>
<span>We're all on the same line</span>

<div style="display: inline-block; width: 80px; background: pink;">Box 1</div>
<div style="display: inline-block; width: 80px; background: lightblue;">Box 2</div>

<div style="display: none;">You can't see me!</div>
<div>But you can see me!</div>
```

## When to use

**Use `display: block` when:**

- You want elements to stack vertically
- Making navigation menus
- Creating page sections

**Use `display: inline` when:**

- Styling text within paragraphs
- Small elements that should flow with text
- Links within sentences

**Use `display: inline-block` when:**

- Creating button rows
- Making image galleries
- Navigation items that need specific sizing

**Use `display: none` when:**

- Hiding elements with JavaScript
- Creating show/hide functionality
- Responsive design (hide on mobile)

**Source**: [MDN Web Docs - Display Property](https://developer.mozilla.org/en-US/docs/Web/CSS/display)

**Also referenced**: [CSS-Tricks - Display Property](https://css-tricks.com/almanac/properties/d/display/)
