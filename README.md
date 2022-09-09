# Frontend Mentor - Product preview card component solution

This is a solution to the [Product preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/product-preview-card-component-GO7UmttRfa). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#challenge)
  - [Screenshots](#screenshots)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)


## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover and focus states for interactive elements

### Screenshots

![webpage-screenshot-desktop](/images/webpage-screenshot-desktop.png)<br>
**Desktop**

<br>

![images/webpage-screenshot-mobile](/images/webpage-screenshot-mobile.png)<br>
**Mobile**

### Links

- Live Site URL: [https://zerescas.github.io/product-preview-card-component/](https://zerescas.github.io/product-preview-card-component/)

## My process

**in progress**

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox

### What I learned

CSS Custom properties is a really handy thing. Like a variables in programming languages but with [some limits because of CSS nature](https://css-tricks.com/the-big-gotcha-with-custom-properties/).

I use custom properies to contain colors, border-radius (for card component and image) and for margin-vertical(to make consistent space between some items)

```css
:root {
    --cream: hsl(30, 38%, 92%);
    --dark-cyan: hsl(158, 36%, 37%);
    --very-dark-cyan: hsl(156, 41%, 18%);
    --very-dark-blue: hsl(212, 21%, 14%);
    --dark-grayish-blue: hsl(228, 12%, 48%);

    --border-radius-round: .75rem;
    --margin-vertical: 1.3rem;
}
```

This way I can make round corners on a card and on some angles of image and most important control a value of roundness  in one place.

```css
.product-preview-card-container {
    /* ... */
    border-radius: var(--border-radius-round);
    /* ... */
}

.product-img-desktop {
    border-radius: var(--border-radius-round) 0 0 var(--border-radius-round);
}

.product-img-mobile {
    border-radius: var(--border-radius-round) var(--border-radius-round) 0 0;
    /* ... */
}
```

### Special question

What is the better way to define CSS classes?

<details>
<summary>First way - Define common classes and combine them in HTML
</summary>

```css
.flex-row {
  display: flex;
  flex-flow: row nowrap;
}

.flex-column {
  display: flex;
  flex-flow: column nowrap;
}

.flex-1 {
  flex: 1 0 0;
}

.align-items-center {
  align-items: center;
}

.justify-content-center {
  justify-content: center;
}
```

```HTML
<!-- ... -->
<div class="flex-column align-items-center justify-content-center">
  <div class="flex-1">
    <!-- ... -->
  </div>
  <div class="flex-1 flex-row align-items-center">
    <!-- ... -->
  </div>
</div>
<!-- ... -->
```

**Advantage** - More flexibile way

**Disadvantage** - HTML element's styles can contains so many items
</details>

<details>
<summary>Second way - Define specified classes</summary>

```css
.card-container {
  /* ... */
  background-color: white;
  color: black;
  padding: 1rem;
  /* ... */
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  justify-content: center;
  /* ... */
}

.product-img-container {
  flex: 1 0 0;
}

.product-info-container {
  /* ... */
  padding: 0.5rem;
  /* ... */
  flex: 1 0 0;
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
  /* ... */
}
```

```HTML
<!-- ... -->
<div class="card-container">
  <div class="product-img-container">
    <!-- ... -->
  </div>
  <div class="product-info-container">
    <!-- ... -->
  </div>
</div>
<!-- ... -->
```

**Advantage** - More logical way

**Disadvantage** - CSS file contains repeated properties in various selectors.
</details>

### Useful resources

- A Complete Guide to Custom Properties [https://css-tricks.com/a-complete-guide-to-custom-properties/](https://css-tricks.com/a-complete-guide-to-custom-properties/)

## Author

- Twitter - [https://twitter.com/zerescas](https://twitter.com/zerescas)
- Telegram - [https://t.me/zerescas](https://t.me/zerescas)