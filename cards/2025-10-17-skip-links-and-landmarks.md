---
title: "Skip Links and Landmarks: Improving Navigation Efficiency"
date: 2025-10-17
category: Accessibility
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/landmark_role , https://webaim.org/techniques/skipnav/
author: Sahar Naz
---

## Skip Links and Landmarks - Improving Navigation Efficiency

Skip links and landmarks help keyboard and screen reader users move quickly to important parts of a page (like the main content), improving navigation speed and usability.

- Skip links: A hidden link at the top of the page that becomes visible when focused. Lets users jump straight to the main content, bypassing repeated navigation.
- Landmarks: Semantic HTML elements (or ARIA landmark roles) that identify page regions so assistive tech can list and jump to them (header, nav, main, aside, footer).

## Code examples

```html
<!-- Skip link (hidden until focused) -->
<a class="skip-link" href="#main">Skip to main content</a>

<header>
  <nav>Primary navigation</nav>
</header>

<main id="main">
  <h1>Article title</h1>
  <p>Start of the main content...</p>
</main>

<aside aria-label="Related">Related links</aside>

<footer>Site footer</footer>
```

```css
.skip-link {
  position: absolute;
  left: -999px; /* hide off-screen by default */
  top: 0;
  background: #000;
  color: #fff;
  padding: 8px;
  z-index: 1000;
}
.skip-link:focus {
  left: 8px;    /* reveal when focused */
}
```

## When to use

- Always include a skip link on pages with repeated navigation (especially multi-page layouts).
- Use landmarks for all pages so assistive tech can present page regions (header, nav, main, aside, footer).
- Use both: respect semantic HTML for landmarks and offer a skip link for keyboard users

**Source**: [MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/landmark_role)

**Also referenced**: [WebAIM](https://webaim.org/techniques/skipnav/)
