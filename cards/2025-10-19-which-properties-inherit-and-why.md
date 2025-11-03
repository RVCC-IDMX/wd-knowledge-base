---
title: "CSS Inheritance: Which Properties Inherit and Why"
date: 2025-10-19
category: css-layout
difficulty: starter
source: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance
author: William Harvey
---

# CSS Inheritance: Which Properties Inherit and Why

Inheritance is the process where an element inherits properties from other elements. We call the elements that inherits properties the "Child" whereas the element that originally had the property the "Parent". Only some elements are capable of inheritance, one example of elements that can inherit are the text elements, like font, font-family, color, font-size and etc. The reason these elements can inherit their properties is because they are related to text in general, so when something is typed out, the elements related to the text inherit the parents traits to keep in line with the style of the text.

## Example

```css
<style>
  p {
    color: blue;
  }
</style>

<p>It's now a <em>blue</em> sentence.</p>

<style>
  body {
    font-family: "Georgia", serif;
  }
</style>

<p>Any <strong>words here</strong> will use the same font.</p>
```

## When to use

-When you want to simplify your workload
-To avoid repeating code
-To keep consistency

**Source**: [MDN: CSS Inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance)
