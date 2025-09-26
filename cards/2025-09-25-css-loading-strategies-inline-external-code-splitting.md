---
title: "CSS Loading Strategies: Inline, External, and Code Splitting."
date: 2025-09-21
category: css-core
difficulty: starter
source: https://web.dev/learn/performance/optimize-resource-loading, https://developer.mozilla.org/en-US/docs/Glossary/Code_splitting
author: Christopher Urban
---

# CSS Inline, External, and Code-Splitting

Inline refers to the use of `<style>` in your html to preload style choices for faster rendering or to prototype style choices. This reduces the amount of network requests for CSS resources. This is done in the `<head>` element to serve the purpose of faster loading or using the style attribute.

External refers to writing your CSS on an external file and using `<link>` or @import to bring that file in to style your page. External CSS files allows for more efficient loading and processing.

Code-splitting is a means of breaking up CSS into multiple scripts or bundles, so no one CSS file has all the styling for every part of the site. Adding a `media` query to the `<link>` ensures that CSS is only ever used when the query is met.

## Example

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>h1,h2{color:#ff0000}h1{font-size:2em}h2{font-size:1.5em}</style>
    <!-- Global styles, always load -->
    <link rel="stylesheet" href="style.css">

    <!-- Styling adjustments for mobile screens -->
    <link rel="stylesheet" href="mobile.css" media="(max-width:460px)">

    <!-- Styling adjustments for larger screens -->
    <link rel="stylesheet" href="large-screen.css" media="(min-width:900px)">
</head>
<body>
    <h1 style="color:blue;" class="content">Main Title</h1>
    <h2 class="content">Subtitle</h2>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent sit amet bibendum tortor. Aenean pellentesque, ante id convallis varius, odio est aliquet augue, ut tristique dui ligula tincidunt ante. Donec commodo risus sem, sagittis placerat augue dapibus ut. Curabitur non lacinia elit. Vestibulum vitae risus ac nisi viverra semper. Donec lobortis, lorem in pretium egestas, arcu ex feugiat sem, et iaculis ipsum dui id nisl. Vivamus finibus convallis finibus. Pellentesque ac purus neque.</p>
</body>
</html>
```

```CSS
/* mobile.css: Small screen adjustment for phone users */
.content {
    max-width: 42ch;
    padding: 0;
}

html {
    font-size: 16px;
}

p {
  line-height: 1.2;
  margin: 1rem;
}
```

```CSS
/* large-screen.css: Adjustments for large screen sizes */
.content {
    padding: 0 2rem;
}

p {
    line-height: 1.9;
}

h1, h2 {
    text-align: center;
    margin-left: 5rem;
    margin-right: 5rem;
}
```

## When to Use

Use `<style>` when you need to save time on initial loads for an HTML page that would not suffer from the added bytes of code to the base HTML file. This is primarily to make sure the aesthetic of your website can remain consistent and load faster for users.

External is used to avoid excessive styling in the HTML file. Using the `<link>` for external CSS files is also a great method of improving loading.

Code-Splitting is used widely to save on load times. This should be used if your webpage is extensive and requires a great deal of styling.

**Source**: [web.dev: Optimize Resource Loading](https://web.dev/learn/performance/optimize-resource-loading), [W3 Schools: HTML-CSS](https://www.w3schools.com/html/html_css.asp), [web.dev: Optimize Resource Loading](https://web.dev/learn/performance/optimize-resource-loading), [MDN: Code-Splitting](https://developer.mozilla.org/en-US/docs/Glossary/Code_splitting)
