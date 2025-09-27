---
title: "CSS Position Property: static, relative. absolute fixed, and sticky"
date: 2025-09-26
category: css-layout
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Positioning
author: William Harvey
---

# CSS Position Porperty: static, relative, absolute, fixed, and sticky

Positioning allows you to control how elements are placed within a document. There are 5 different types of position properties. The first one is Static, which is the default that all elements start out with, it just means it stays in its default position. Next is Relative, similar to Static, but you can modify it with the "Top" "Bottom" "Left" and "Right" properties. Then there is Absolute, which allows the user to make a specific element its own layer. After that is Fixed, similar to absolute when making interactable UI items, but fixed positions are fixed to the website. Finally, there is Sticky, Unlike any of the other positions, sticky is more of a hybrid between relative and fixed, allowing elements to persist until a scroll threshold is reached, then it becomes fixed.

## Example

```css
.positioned {
  position: static;
  background: yellow;
}

.positioned {
  position: relative;
  background: yellow;
  top: 30px;
  left: 30pc;
}

.positioned {
  position: absolute;
  background: yellow;
  top: 10px;
  right; 30px;
  z-index: 1;
}

.positioned {
  position: fixed;
  background: yellow;
  top: 0;
  width: 500px;
  margin-top: 0;
  padding: 10px;
}

.positioned {
  position: sticky;
  top: 30px;
  left: 30px;
}
```

## When to use

-Static doesn't really do much, it doesn't change anything about the flow of the document.
-Relative should be used when you need to just make some micro adjustments to an element and nothing more
-Absolue should be used when you want to make an element interactable for the user on the website.
-Fixed should be used when you want to make an element persist no matter how much you scroll, an example would be a logo for the webiste.
-Sticky should be used when you only want an element to persist untl you've reached a certain scroll threshold on the document.

**Source**: [MDN: Positioning](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Positioning)
