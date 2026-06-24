# Frontend Mentor - Bento Grid Solution

This is my solution to the [Bento grid challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/bento-grid-RMydElrlOj).

## Table of Contents

- [Overview](#overview)
  - [The Challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My Process](#my-process)
  - [Built With](#built-with)
  - [What I Learned](#what-i-learned)
  - [Useful Resources](#useful-resources)
- [Author](#author)

---

## Overview

### The Challenge

Users should be able to:

- View the optimal layout for the interface depending on their device's screen size

### Screenshot

![Bento Grid Solution](./screenshot.jpg)

### Links

- **Solution URL:** [Frontend Mentor Profile](https://www.frontendmentor.io/profile/yourusername)
- **Live Site URL:** [Live Site](https://purvajadhav-bento-grid.netlify.app/)

---

## My Process

### Built With

- Semantic HTML5 markup
- CSS Custom Properties (Variables)
- **CSS Grid** with `grid-template-areas`
- Flexbox
- Mobile-first workflow
- Responsive design using `clamp()`

---

### What I Learned

#### 🟣 CSS Grid Template Areas

The biggest thing I learned in this project was **`grid-template-areas`** — a powerful way to name and place grid items visually in your CSS.

Instead of dealing with confusing `grid-column` and `grid-row` numbers, you can literally draw your layout:

```css
main {
  display: grid;
  grid-template-areas:
    'seven one  one  four'
    'seven two  three four'
    'eight two  three four'
    'eight six  five  five';
}

.social_media    { grid-area: one; }
.manage_accounts { grid-area: two; }
/* ...and so on */
```

This made it super easy to rearrange the layout at different breakpoints — just rewrite the `grid-template-areas` string inside a `@media` query!

> 💡 **Huge credit to [Kevin Powell](https://www.youtube.com/@KevinPowell) on YouTube** — his videos on CSS Grid made this concept click for me. Highly recommend checking out his channel if you're learning CSS!

---

#### 🖼️ Fixing Images Inside Containers with `object-fit` & `object-position`

Another key thing I learned was how to properly fit images inside containers **without distorting them**.

The trick is using `object-fit: cover` along with `object-position` to control which part of the image shows:

```css
.img-container {
  width: 100%;
  height: 150px;
  overflow: hidden;
}

.img-container img {
  width: 100%;
  height: 100%;
  object-fit: cover;       /* crop, don't distort */
  object-position: top;    /* show top part of image */
}
```

| Value | What it does |
|---|---|
| `object-fit: cover` | Fills container, crops image — no distortion ✅ |
| `object-fit: contain` | Shows full image, leaves empty gaps |
| `object-fit: fill` | Stretches image — distorts it ❌ |
| `object-position: top` | Keeps top part of image visible when cropped |

---

#### 📐 Responsive Font Sizes with `clamp()`

Instead of writing multiple `@media` queries just for font sizes, I used **`clamp()`** to make fonts scale smoothly:

```css
font-size: clamp(1.25rem, 3vw, 2rem);
/*              min      fluid  max  */
```

This means:
- Never smaller than `1.25rem`
- Scales fluidly with viewport width (`3vw`)
- Never larger than `2rem`

Clean, readable, and no extra media queries needed!

---

### Useful Resources

- **[Kevin Powell – YouTube](https://www.youtube.com/@KevinPowell)** — Best CSS resource out there. His grid and layout videos helped me understand `grid-template-areas` properly.
- **[Frontend Mentor](https://www.frontendmentor.io)** — Great platform for practicing real-world UI challenges.
- **[MDN – object-fit](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)** — Clear docs on image fitting techniques.
- **[MDN – clamp()](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp)** — Reference for fluid typography.

---

## Author

- **GitHub** – [@purvjadh](https://github.com/purvjadh)
- **Frontend Mentor** – [@purvjadh](https://www.frontendmentor.io/profile/purvjadh)