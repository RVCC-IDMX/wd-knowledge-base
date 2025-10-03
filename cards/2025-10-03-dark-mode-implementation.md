---
title: "Dark Mode Implementation: prefers-color-scheme and Theme Switching"
date: 2025-10-03
category: Modern CSS
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme
author: Sahar Naz
---

## Dark Mode Implementation - prefers-color-scheme and Theme Switching

Dark mode gives users a darker color scheme that's easier on the eyes, especially in low light. There are two main ways to implement it:

**1. `prefers-color-scheme`**: Automatically detects if the user's device is set to dark mode

**2. Theme switching**: Let users manually toggle between light and dark themes with a button

Think of it like this: `prefers-color-scheme` is like automatically dimming lights when it gets dark outside, while theme switching is like having a light switch users can control themselves.

## Code examples

**Auto dark mode:**

```css
/* Light mode (default) */
body {
  background: white;
  color: black;
}

/* Auto dark mode when user's system is dark */
@media (prefers-color-scheme: dark) {
  body {
    background: #222;
    color: white;
  }
}
```

**Toggle button:**

```html
<button onclick="toggleDark()">Toggle Dark Mode</button>
```

```css
body.dark {
  background: #222;
  color: white;
}
```

```javascript
function toggleDark() {
  document.body.classList.toggle('dark');
}
```

## When to use

**`prefers-color-scheme`:**

- You want to respect user's system preferences
- Building simple websites without toggle buttons
- You want automatic dark mode that "just works"

**manual theme switching:**

- Users need control over the theme
- Building apps where theme preference should persist
- You want to offer multiple theme options (not just light/dark)

**both together:**

- You want the best user experience
- Default to system preference, but let users override it
- Building professional web applications

**Source**: [MDN Web Docs - prefers-color-scheme](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme)

**Also referenced**: [CSS-Tricks - Dark Mode](https://css-tricks.com/a-complete-guide-to-dark-mode-on-the-web/)
