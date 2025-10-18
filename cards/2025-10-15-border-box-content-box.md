---
title: CSS box-sizing, border-box vs content-box
date: 2025-10-15
category: css-intermediate
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing
author: Christopher Urban
---

# CSS Box-Sizing, border-box vs content-box

In CSS Box-Sizing, you can assign two values to that property: `border-box` and `content-box`. `content-box` is the default option, the padding and borderwidth added after the final render of the elements size/position. `border-box` includes padding and border width in the render of the element. Meaning `content-box` may be larger then the pixel dimensions you set, but `border-box` will always be the pixel size you set.

## Example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width,initial-scale=1" />
    <title>box-sizing demo</title>
    <style>
      /* Demo styles included inline so students can paste-copy-run */
      .demo-wrap {
        display: flex;
        gap: 1rem;
        padding: 1rem;
      }
      .box {
        width: 200px;
        height: 80px;
        padding: 20px;
        border: 8px solid #2b7;
        background: #efe;
      }
      /* Left: content-box (default) */
      .content-box {
        box-sizing: content-box;
      }
      /* Right: border-box includes padding and border in the size */
      .border-box {
        box-sizing: border-box;
      }
      .label {
        font-weight: 700;
        margin-bottom: 0.5rem;
      }
    </style>
  </head>
  <body>
    <h1>box-sizing: content-box vs border-box</h1>
    <div class="demo-wrap">
      <div>
        <div class="label">content-box (default)</div>
        <div class="box content-box">
          Declared 200×80<br />(padding + border added)
        </div>
      </div>
      <div>
        <div class="label">border-box</div>
        <div class="box border-box">
          Declared 200×80<br />(includes padding & border)
        </div>
      </div>
    </div>
  </body>
</html>
```

## When to Use

In most cases, `border-box` is the better use for element positioning. It is inherently including padding and other border considerations. However, when using `position:relative` or `position:absolute` the `content-box` is superior as more relative element position, and independent of changes to border and padding sizes.

**Source**: [MDN: Box-Sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)
