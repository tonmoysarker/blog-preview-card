# Frontend Mentor - Blog preview card solution

This is a solution to the [Blog preview card challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/blog-preview-card-ckPaj01IcS). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- See hover and focus states for all interactive elements on the page

### Screenshot

![1440px](Screenshot%201.png)
![375px](Screenshot%202.png)

### Links

- Solution URL: [here](https://github.com/tonmoysarker/blog-preview-card)
- Live Site URL: [here](https://tonmoysarker.github.io/blog-preview-card/)

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow

### What I learned

I tried to implement different font-size for the same element on different screens without media query, and in the process I learned how to use clamp() function to set font-size in a range.

# Using `clamp()` for Responsive Typography

In this project, I used the CSS `clamp()` function to create responsive font sizes that scale fluidly between specific screen widths without using media queries.

## Scenario

For a design:

- On a **375px** viewport, the font size should be `12px`.
- On a **1440px** viewport, the font size should be `14px`.

## Solution

The `clamp()` function ensures:

1. A **minimum** font size (`12px`) for small screens.
2. A **maximum** font size (`14px`) for large screens.
3. A **dynamic scaling** based on viewport width for screens in between.

The CSS used:

````css
font-size: clamp(12px, calc(12px + (100vw - 375px) * 0.001878), 14px);


```markdown
## How the Calculation Works

### 1. Font Size Change Rate
We calculate the rate at which the font size changes as the viewport grows:
- **Font Size Range**: `14px - 12px = 2px`
- **Viewport Range**: `1440px - 375px = 1065px`
- **Change Rate**: `2px / 1065px ≈ 0.001878`

This means the font size increases by approximately `0.001878px` for every `1px` increase in the viewport width.

### 2. Dynamic Font Scaling
Using the rate of change, we calculate the dynamic portion of the font size:
```css
calc(12px + (100vw - 375px) * 0.001878)


```markdown
### 3. Combining with `clamp()`
Finally, we use `clamp()` to enforce a minimum (`12px`) and maximum (`14px`) size:
```css
font-size: clamp(12px, calc(12px + (100vw - 375px) * 0.001878), 14px);


## Author

- Frontend Mentor - [@tonmoysarker](https://www.frontendmentor.io/profile/tonmoysarker)
````
