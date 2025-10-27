---
title: CSS nth-child() and nth-of-type(), Advanced Child Selection
date: 2025-10-16
category: intermediate
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child, https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-of-type
author: instructor
---

# CSS nth-child() and nth-of-type(), Advanced Child Selection

In CSS the `:nth-child()` and `:nth-of-type()` are tools to select specific elements on your webpage. `:nth-child()` matches elements based on their index among all children. So `:nth-child(2)` selects the second child. It can also take formulas too. `:nth-child(2n)` selects every even child and `:nth-child(2n+1)` every odd child.

`:nth-of-type()` only counts siblings of the same element type but functions the same as above.

## Example

```css
/* Basic visual grid for examples */
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 0.75rem;
}
.item {
  padding: 1rem;
  background: #fff;
  border: 1px solid #ddd;
  border-radius: 4px;
}

/* Style every even child */
.grid .item:nth-child(even) {
  background: #f0f8ff;
}

/* Style every 3rd item using formula */
.grid .item:nth-child(3n) {
  border-color: #2b7;
}

/* Select the 2nd <p> inside each .card using nth-of-type */
.card p:nth-of-type(2) {
  color: #a30;
  font-weight: 700;
}
```

```html
<div class="grid">
  <div class="item card">
    <p>Card A — p1</p>
    <p>Card A — p2 (nth-of-type target)</p>
  </div>
  <div class="item card">
    <p>Card B — p1</p>
    <p>Card B — p2 (nth-of-type target)</p>
  </div>
  <div class="item">Simple item</div>
  <div class="item card">
    <p>Card C — p1</p>
    <p>Card C — p2 (nth-of-type target)</p>
  </div>
  <div class="item">Another</div>
  <div class="item">Last one</div>
</div>
```

## When to Use

Can be used for patterned styling like alternating stripes. Also can be used for styling that repeats with nested elements. `nth-child()` is for more broad element selection, whereas `nth-of-type()` is used for more precise element selection.

**Source**: [MDN: nth-child](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child), [MDN: nth-of-type](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-of-type)
