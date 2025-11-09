---
title: "CSS object-fit and object-position: Controlling Replaced Element Display"
date: 2025-11-02
category: CSS images
difficulty: intermediate
source: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_images/Replaced_element_properties
author: William Harvey
---

## Controlling Replaced Element Display

Controlling the display of replaced elements in CSS is essential for managing how images, videos, and other external resources appear within their containers. The properties object-fit and object-position provide powerful tools for this purpose. The object-fit property determines how the content of a replaced element, like an "img" or "video", is resized to fit its container. For example, object-fit: cover ensures the element fills the container while maintaining its aspect ratio, potentially cropping the content, while object-fit: contain makes the entire content visible but may leave empty space. The object-position property allows you to specify the alignment of the content within the container, such as centering or aligning to the top or left. By combining these properties, you can create responsive layouts where images and videos look consistent and visually appealing, regardless of their original dimensions. This approach is especially useful for galleries, cards, and hero sections where maintaining design integrity is important.

## Code examples

```html
<img src="landscape.jpg" alt="Landscape" style="width: 300px; height: 200px; object-fit: cover; object-position: center;" />

<video src="sample.mp4" controls style="width: 300px; height: 200px; object-fit: contain;"></video>
```

```css
.image-container {
 width: 300px;
 height: 200px;
 overflow: hidden;
}
.image-container img {
 width: 100%;
 height: 100%;
 object-fit: cover;
 object-position: top left;
}
```

## When to use

- **Image galleries:** Ensuring all thumbnails are uniform, even if source images have different dimensions.
- **Profile avatars:** Cropping user-uploaded photos to fit a square or circle without distortion.
- **Hero banners:** Making sure background images fill the space responsively while keeping the subject visible.
- **Product cards:** Displaying product images consistently in e-commerce grids.
- **Video previews:** Keeping video frames centered and scaled in a fixed-size player.

**Source**: [MDN: Replaced element properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_images/Replaced_element_properties)
