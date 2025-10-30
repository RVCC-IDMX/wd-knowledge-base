---
title: "CSS Pseudo-elements: Styling with ::before, ::after, and ::marker"
date: 2025-10-30
category: css-core
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements
author: copilot
---

# CSS Pseudo-elements: Styling with ::before, ::after, and ::marker

CSS pseudo-elements let you style specific parts of an element without adding extra HTML. The `::before` and `::after` pseudo-elements insert content before or after an element's actual content, while `::marker` targets the bullet or number of list items. These use the double-colon (::) syntax to distinguish them from pseudo-classes.

The `::before` and `::after` pseudo-elements require the `content` property to display—even if it's just `content: ""` for decorative elements. They create inline elements by default and are commonly used for icons, decorative shapes, or clearfix techniques. The `::marker` pseudo-element specifically targets list markers, allowing you to style bullets, numbers, or custom list indicators without wrapping them in additional markup.

These pseudo-elements don't appear in the DOM but are treated as child elements for styling purposes. They inherit properties from their parent and can be positioned, transformed, and animated. Modern browsers support all three, with `::marker` being the newest addition (Chrome 86+, Firefox 68+, Safari 11.1+). They're powerful for creating visual effects while keeping HTML clean and semantic.

## Example

```css
/* Add decorative quotes around blockquotes */
blockquote::before {
  content: """;
  font-size: 3em;
  color: #ccc;
  position: absolute;
  left: -20px;
  top: -10px;
}

blockquote::after {
  content: """;
  font-size: 3em;
  color: #ccc;
}

/* Style list markers */
ul li::marker {
  content: "✓ ";
  color: #28a745;
  font-size: 1.2em;
}

ol li::marker {
  color: #0066cc;
  font-weight: bold;
}

/* Create icon before links */
a.external::before {
  content: "🔗 ";
  margin-right: 4px;
}

/* Add "NEW" badge */
.new-item::after {
  content: "NEW";
  background: #ff4444;
  color: white;
  padding: 2px 6px;
  border-radius: 3px;
  font-size: 0.75em;
  margin-left: 8px;
  vertical-align: super;
}

/* Clearfix using ::after */
.clearfix::after {
  content: "";
  display: table;
  clear: both;
}
```

## When to Use

Use `::before` and `::after` for decorative content, icons, or layout helpers that don't need to be in the HTML—especially when the content is purely visual and doesn't convey meaningful information to screen readers. They're perfect for adding quotes, badges, tooltips, or geometric shapes. Use `::marker` when customizing list bullets or numbers to maintain semantic HTML structure while achieving unique designs. Avoid using these for essential content as they're not accessible to assistive technologies.

**Source**: [MDN: CSS Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
