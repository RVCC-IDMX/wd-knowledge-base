---
title: "Form Accessibility: Labels, Fieldsets, and Error Messages"
date: 2025-09-25
category: Accessibility
difficulty: starter
source: https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Attributes/form
author: Sahar Naz
---

## Form Accessibility - Labels, Fieldsets and Error Messages

Form accesssibility is important for inclusivity, clarity and a better user experience:

- Labels will tell users what an input is for; not having labeles will prevent people using assistive tech from knowing what to type. All textboxes, dropdowns and check boxes should have labels.
- Fieldsets group related inputs together which helps users understand that the choices belong together.
- Error messages will tell users when something went wrong. It is essential that error messages are clear and connected to the right input.

## Code examples

Labels:

```html
<!-- every input has a clear label -->
<label for="username">Username:</label>
<input type="text" id="username" name="username">

<label for="email">Email:</label>
<input type="email" id="email" name="email">

<label for="password">Password:</label>
<input type="password" id="password" name="password">

<!--Label wraps the input -->
<label>
  Your Name:
  <input type="text" name="name">
</label>
```

Here is an example of a missing labels:

```html
<!-- Missing labels (screen readers can't understand) -->
<input type="text" placeholder="Enter username">
<input type="email" placeholder="Enter email">
<input type="password" placeholder="Enter password">
```

Error messages:

```html
<!-- Input with accessible error message -->
<label for="email">Email:</label>
<input type="email" 
       id="email" 
       aria-describedby="email-error"  <!-- Links to error message -->
       aria-invalid="true">            <!-- Tells screen readers there's an error -->
<div id="email-error" class="error">   <!-- Error message with matching ID -->
  Please enter a valid email
</div>
```

```css
/* Style for error messages */
.error {
  color: red;
  font-size: 0.9em;
}

/* Visual indicator for inputs with errors */
input[aria-invalid="true"] {
  border: 2px solid red;  /* Red border shows error state */
}
```

## When to use

Labels are used for every single form input, error messages are used for when form validation fails and fieldsets are used for grouping related form controls.

**Source**: [MDN: label](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/label)
**Also referenced**: [MDN: HTML Attribute: Form](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Attributes/form)
