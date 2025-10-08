---
title: "CSS Pointer Events: Controlling Mouse Interactions"
date: 2025-10-04
category: css-advanced
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events
author: Christopher Urban
---

# CSS Pointer Events: Controlling Mouse Interactions

Pointer events are restrictions you can add to elements through CSS that can alter or edit the way a users mouse interacts with them. In a more standard case, this can be seen through the use of `pointer-event: auto`. This automatically sets interactible elements to change the mouse on interact from the default cursor to the pointing hand. In that same breath, this is what allows users to set exactly what is interactible. There are a great many settings for SVG files, setting what portions and what layers of the SVG count as interactible. It can also be set to

## Example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <h1>Pointer Events</h1>

    <section>
      <h2>Pointer-events examples</h2>

      <!-- SVG pointer-events examples -->
      <div style="margin-top:1rem; display:flex; gap:1.5rem; flex-wrap:wrap;">
        <!-- visibleFill: only filled areas receive pointer events -->
        <div>
          <svg
            width="140"
            height="80"
            viewBox="0 0 140 80"
            xmlns="http://www.w3.org/2000/svg"
          >
            <rect
              x="5"
              y="5"
              width="60"
              height="70"
              fill="#8fd"
              stroke="#036"
              stroke-width="6"
              class="svg-visible-fill"
              pointer-events="visibleFill"
              onclick="handleSVGClick('visibleFill')"
            />
          </svg>
          <div>visibleFill (only filled area)</div>
        </div>

        <!-- visibleStroke: only strokes receive pointer events -->
        <div>
          <svg
            width="140"
            height="80"
            viewBox="0 0 140 80"
            xmlns="http://www.w3.org/2000/svg"
          >
            <rect
              x="5"
              y="5"
              width="60"
              height="70"
              fill="none"
              stroke="#f46"
              stroke-width="8"
              class="svg-visible-stroke"
              pointer-events="visibleStroke"
              onclick="handleSVGClick('visibleStroke')"
            />
          </svg>
          <div>visibleStroke (only stroke)</div>
        </div>

        <!-- visiblePainted: fill or stroke; deprecated name visiblePainted still supported -->
        <div>
          <svg
            width="140"
            height="80"
            viewBox="0 0 140 80"
            xmlns="http://www.w3.org/2000/svg"
          >
            <circle
              cx="40"
              cy="40"
              r="30"
              fill="#ffb"
              stroke="#a40"
              stroke-width="6"
              class="svg-visible-paint"
              pointer-events="visiblePainted"
              onclick="handleSVGClick('visiblePainted')"
            />
          </svg>
          <div>visiblePainted (fill or stroke)</div>
        </div>

        <!-- none: SVG won't capture pointer events -->
        <div>
          <svg
            width="140"
            height="80"
            viewBox="0 0 140 80"
            xmlns="http://www.w3.org/2000/svg"
          >
            <rect
              x="10"
              y="10"
              width="120"
              height="60"
              fill="#cce"
              class="svg-none"
              pointer-events="none"
            />
          </svg>
          <div>none (SVG ignores pointer events)</div>
        </div>

        <!-- all: SVG captures pointer events for entire bbox -->
        <div>
          <svg
            width="140"
            height="80"
            viewBox="0 0 140 80"
            xmlns="http://www.w3.org/2000/svg"
          >
            <ellipse
              cx="70"
              cy="40"
              rx="50"
              ry="30"
              fill="#def"
              class="svg-all"
              pointer-events="all"
              onclick="handleSVGClick('all')"
            />
          </svg>
          <div>all (entire element captures events)</div>
        </div>

        <!-- bounding-box: (SVG2) whole bbox acts as hit area -->
        <div>
          <svg
            width="140"
            height="80"
            viewBox="0 0 140 80"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M10 70 L70 10 L130 70 Z"
              fill="#ffd"
              stroke="#a60"
              stroke-width="4"
              class="svg-bbox"
              pointer-events="bounding-box"
              onclick="handleSVGClick('bounding-box')"
            />
          </svg>
          <div>bounding-box (SVG2 behaviour)</div>
        </div>
      </div>
    </section>
    <script>
      function handleSVGClick(name) {
        // simple visual feedback for the examples
        alert(name + " clicked");
        console.log("SVG clicked:", name);
      }
    </script>
  </body>
</html>
```

```css
/* Additional pointer-events examples */
.disabled {
  pointer-events: none; /* element won't receive mouse events */
  opacity: 0.6;
  cursor: not-allowed;
}

/* Overlay examples: pointer-events: none lets clicks pass through */
.svg-no-pointer {
  pointer-events: none;
}

/* SVG-specific pointer-events examples (SVG values) */
.svg-visible-paint {
  pointer-events: visiblePainted;
}
.svg-visible-fill {
  pointer-events: visibleFill;
}
.svg-visible-stroke {
  pointer-events: visibleStroke;
}
.svg-none {
  pointer-events: none;
}
.svg-all {
  pointer-events: all;
}
.svg-bbox {
  pointer-events: bounding-box; /* SVG2: treats bounding box as hit area */
}
```

## When to Use

This is great for nav menus where you don't want users to press buttons that just reload the page they are currently on. It can also be used to properly curate what elements can and cannot have mouse interactions. In the case of online exams that require answers be submitted before continuing, similar methods may have to be deployed to ensure users can't go back and change their answers.

**Source**: [MDN: Pointer-Events](https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events)
