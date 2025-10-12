---
title: "CSS aspect-ratio: Maintaining Proportions Without Hacks"
date: 2025-10-10
category: css-layout
difficulty: starter
source: https://developer.mozilla.org/en-US/docs/Web/CSS/aspect-ratio
author: William Harvey
---

# CSS aspect-ratio: Maintaining Proportions Without Hacks

The aspect-ratio is used as a way to fit around the screen of whatever the user is using, whether that be a phone, laptop, computer, tv, etc. You can't just have a set aspect-ratio, and even a few set aspect ratios since there are so many different devices with different aspect-ratios, so you need the website to be flexible for hundreds of different aspect-ratios. You can still do that, but it's much easier to set the aspect-ratio to auto, as seen below.

## Example

```css
.element {
  aspect-ratio: auto;
  width: 100%;
  height: auto;
}
```

## When to use

-When you want to not add each different kind of aspect-ratio.
-You might actually not want to use the auto setting if you want your website to have a specific feel to the website

**Source**: [MDN: aspect-ratio](https://developer.mozilla.org/en-US/docs/Web/CSS/aspect-ratio)
