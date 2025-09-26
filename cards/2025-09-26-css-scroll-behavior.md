---
title: "CSS Scroll-Behavior: Smooth Scrolling Without Javascript"
date: 2025-09-26
category: animation
difficulty: starter
source: https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior
author: Emily Lubonty
---

# CSS Scroll-Behavior: Smooth Scrolling Without Javascript

The CSS Scroll Behavior property sets the standard for how the scrollbar should act when scrolling is triggered.
Two values associated with the scroll-behavior property include `auto` and `smooth`.
The `auto` value allows the scroll box to scroll instantly, while the `smooth` value allows the scroll to execute seamlessly.
Scroll-behavior also lets the user specify in-page navigation such as `.scrollTO()`, or how links on the page are handled. Scroll-behavior can also be used for motion
preferences, including reduced motion, which can apply to those with accessibility concerns or needs.

# Example

## CSS

```css
scroll-behavior: auto;
```

```css
scroll-behavior: smooth;
```

## When to use

Use when creating a functional scroll box for navigation or scrolling APIs.

**Source**: [MDN: scroll-behavior](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior)

**Additonal Source**: [web.dev: Overflow](https://web.dev/learn/css/overflow)
