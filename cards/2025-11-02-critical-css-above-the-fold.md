---
title: "Critical CSS: Optimizing Above-the-Fold Rendering"
date: 2025-11-02
category: Critical CSS
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Performance/Best_practices
author: William Harvey
---

## Optimizing Ablove-the-Fold Rendering

Above-the-fold rendering focuses on making the content visible in the user's initial viewport load as quickly as possible. This is important because users form first impressions rapidly, and delays can lead to higher bounce rates. To optimize above-the-fold performance, minimize render-blocking resources like CSS and JavaScript. Inline only the critical CSS needed for the visible content, and load additional styles asynchronously. Use resource hints such as preconnect and preload to speed up fetching key assets. Optimize images by compressing them and using modern formats, and defer loading images that are not immediately visible. For JavaScript, use async or defer attributes to prevent blocking the rendering of page content. By prioritizing what appears above the fold, you improve perceived performance, user experience, and even SEO, ensuring users see meaningful content as soon as possible.

## Code examples

```html
<header class="hero">
 <h1>Boost Your Productivity</h1>
 <p>Get started with our app and see instant results.</p>
 <a href="#signup" class="cta">Sign Up Free</a>
 <img src="hero.jpg" alt="App preview" width="400" height="250" loading="eager" />
</header>
```

```css
.hero {
 display: flex;
 flex-direction: column;
 align-items: center;
 justify-content: center;
 min-height: 60vh;
 background: #f5f7fa;
 text-align: center;
 padding: 2rem 1rem;
}
.hero h1 {
 font-size: 2.5rem;
 margin-bottom: 0.5rem;
}
.hero .cta {
 display: inline-block;
 margin-top: 1rem;
 padding: 0.75rem 2rem;
 background: #0078d4;
 color: #fff;
 border-radius: 4px;
 text-decoration: none;
 font-weight: bold;
 transition: background 0.2s;
}
.hero .cta:hover {
 background: #005fa3;
}
img[loading="eager"] {
 max-width: 100%;
 height: auto;
 display: block;
 margin: 1rem auto 0;
}
```

## When to use

- **Landing pages:** Where first impressions and fast engagement are critical for conversions.
- **E-commerce homepages:** To showcase featured products, sales, or CTAs immediately on load.
- **News and media sites:** To ensure headlines and top stories are visible and interactive right away.
- **Single-page applications (SPAs):** Where the initial view must load quickly to keep users engaged.
- **Mobile-first designs:** Where limited screen space and slower connections make fast, prioritized loading essential.

**Source**: [MDN: Web Performance best practices & tips](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Performance/Best_practices)
