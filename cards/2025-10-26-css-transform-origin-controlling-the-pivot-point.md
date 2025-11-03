---
title: "CSS transform-origin: Controlling the Pivot Point"
date: 2025-10-26
category: css-transform
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin
author: William Harvey
---

# CSS transform-origin: Controlling the Pivot Point

A pivot point is an area where elements are attached to, and when animated, they are seen as anchored to that point on the screen. Some examples of pivot points, in which they use the "transform-origin" property, use the phrases like "top left" "bottom right" "top center" and etc. With these phrases, you can make a pivot point to these specific locations, and when they are animated, they reflect their pivot points in the animation, like a swinging motion, or drop motion.

## Example

```html
<div class="box center"></div>
<div class="box top-left"></div>
<div class="box bottom-right"></div>

```

```css
.box {
  width: 100px;
  height: 100px;
  margin: 20px;
  background: tomato;
  display: inline-block;
  transition: transform 0.5s;
}

/* Default: center */
.center:hover {
  transform: rotate(45deg);
  transform-origin: center;
}

/* Pivot: top-left corner */
.top-left:hover {
  transform: rotate(45deg);
  transform-origin: top left;
}

/* Pivot: bottom-right corner */
.bottom-right:hover {
  transform: rotate(45deg);
  transform-origin: bottom right;
}

```

## When to use

-If you want something to move as if it is anchored to a certain side of the screen

**Source**: [MDN: CSS-transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin)
