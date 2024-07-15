##### 3D-Rotate-On-Hover-Effect:

# This Website Development Learnings:

This repository contains a collection of concepts and techniques I learned while developing a website. Below are the key points I covered, with explanations and code snippets for better understanding.

## Table of Contents
1. [Counter-Reset Property](#counter-reset-property)
2. [Will-Change Property](#will-change-property)
3. [Using CSS Variables with JavaScript](#using-css-variables-with-javascript)

## Counter-Reset Property

The `counter-reset` property in CSS is used to create or reset one or more CSS counters. These counters are primarily used with the `counter-increment` property to automatically number elements in a document.

### Why We Need It
CSS counters are useful for creating automatic numbering in lists, headings, or any elements where a sequential number is required without manually incrementing the value.

### Properties
- **Initial Value:** none
- **Applies to:** All elements
- **Inherited:** No
- **Media:** Visual

### Syntax
```css
/* Reset the counter named 'section' */
counter-reset: section;

/* Increment the counter named 'section' */
counter-increment: section;
```

### Example
```css
/* Reset the 'section' counter */
body {
    counter-reset: section;
}

/* Use the counter in a heading */
h2::before {
    counter-increment: section;
    content: "Section " counter(section) ". ";
}
```

## Will-Change Property

The `will-change` property in CSS provides a hint to browsers about what properties of an element are likely to change. This allows the browser to optimize performance by preparing for these changes ahead of time.

### Why We Need It
Using `will-change` can improve performance in animations and interactions by allowing the browser to make optimizations that enhance the smoothness and responsiveness of the changes.

### Properties
- **Initial Value:** auto
- **Applies to:** All elements
- **Inherited:** No
- **Media:** Visual

### Syntax
```css
/* Hints that the 'transform' property will change */
.element {
    will-change: transform;
}

/* Hints that the 'opacity' property will change */
.element {
    will-change: opacity;
}
```

### Example
```css
/* Optimize performance for upcoming transformations */
.button:hover {
    will-change: transform;
    transform: scale(1.1);
    transition: transform 0.3s ease;
}
```

## Using CSS Variables with JavaScript

CSS variables (custom properties) can be dynamically set and modified using JavaScript, which allows for flexible and responsive styling. Below is an example of how to set a variable and use it in a CSS property.

### Transition Delay with CSS Variables
In this example, the CSS variable `--index` is set by JavaScript. Each line is treated as an array element, and the `transition-delay` is applied to every single character with a 0.05-second multiple.

### CSS
```css
/* Define the transition delay using the --index variable */
.character {
    transition-delay: calc(0.05s * var(--index));
}
```

### JavaScript
```javascript
// Example JavaScript to set the --index variable
const elements = document.querySelectorAll('.character');
elements.forEach((element, index) => {
    element.style.setProperty('--index', index);
});
```

---
