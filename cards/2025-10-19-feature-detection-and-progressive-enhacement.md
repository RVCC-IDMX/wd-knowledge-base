---
title: "CSS @supports: Feature Detection and Progressive Enhancement"
date: 2025-10-19
category: css-layout
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/@supports
author: William Harvey
---

# CSS @supports: Feature Detection and Progressive Enhancement

@supports is a rule in CSS that makes sure that a browser knows how to utilize certain features before using them, think of it as a checklist, and if something doesn't meet a requirement, it is ignored and falls back on a set element. Here's an example, lets say you want to display a picture that will play a video when you hover over it, but some browsers might not support this feature. So instead of coding it to make it to where it'll try to play the video no matter what even if the element might break the website, you can add an @supports rule to make it to where it'll not try to make the video play while hovering over it if it's not supported

## Example

```css
@supports (property: value) {
  /* CSS rules that will only apply if supported */
}

/* Apply only if both features are supported */
@supports (display: grid) and (aspect-ratio: 1 / 1) {
  .item {
    aspect-ratio: 1 / 1;
    display: grid;
  }
}

/* Apply if the browser does NOT support variable fonts */
@supports not (font-variation-settings: normal) {
  body {
    font-family: 'Arial', sans-serif;
  }
}

```

## When to use

-If you don't want your website to potentially break
-To organize and optimize your code better
-To try experimental features that are supported on some websites, but not others

**Source**: [MDN: @supports](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Testing/Feature_detection)
