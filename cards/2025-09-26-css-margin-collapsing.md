---
title: "CSS Margin Collapsing: Rules and Prevention Strategies"
date: 2025-09-26
category: css-layout
difficulty: starter
source: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Mastering_margin_collapsing
author: William Harvey
---

# CSS Margin Collapsing: Rules and Prevention Strategies

Margin Collapse happens when two margins on the y axis are next to each other, and the margin with a wider px count will collapse into the one they are next to, and they combine into one big margin. This can happen in three cases, the margins of adjacent siblings are collapsed, no content that is separating the parent and descendants, meaning that unless there is nothing extra in between the margins, they will collapse. Lastly, there are empty blocks, meaning no border, padding, or inline content like height or min-height to keep the the margin-top from its margin-bottom. To note, margin collapse isn't always bad, as it can be an intentional use, for creative reasons, but for the most part arent desirable.

## Example

```css
margin-collapsing 
.b {
  margin-top: 30px;
  border-top: 1px solid transparent; /* stops margin collapse with an invisible border*/
}

.b {
  margin-top: 30px;
  padding-top: 1px; /* Even just a little padding prevents collapse */
}

body {
  display: flex;
  flex-direction: column;
}
```

## When to use

-Use the first one when you only need a tiny fix.

-Use the second one when you want intentional spacing between the margin.

-Use the third one when you want a complete fix and no room for any margin collapse at all under any circumstance.

**Source**: [MDN: Mastering margin collapsing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Mastering_margin_collapsing)
