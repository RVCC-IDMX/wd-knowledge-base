---
title: "CSS: focus-within: Parent Styling Based on Child Focus"
date: 2025-10-26
category: css-focus
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/:focus
author: William Harvey
---

# CSS: focus-within: Parent Styling Based on Child Focus

This refers to the ability for an element to change the way it looks based on if the user is interacting with the element. For example, lets say I have a button, but nothing happens to its physical form when I hover over it or click it, with the focus input, you can make such changes. You can change the way it looks with putting the (input:focus) code to tell what should be changed and when.

## Example

```html
<div class="input-box">
  <label>Name</label>
  <input type="text" placeholder="Enter your name">
</div>
```

```css
.input-box {
  border: 2px solid #ccc;
  border-radius: 8px;
  padding: 12px;
  transition: border-color 0.3s, box-shadow 0.3s;
}

.input-box:has(input:focus) {
  border-color: #007bff;
  box-shadow: 0 0 6px rgba(0, 123, 255, 0.5);
}
```

## When to use

-When you want to change the look/color of an element when the user is focusing on it
-To add more interactivity to an element

**Source**: [MDN: CSS focus](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus)
