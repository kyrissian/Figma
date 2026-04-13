# Figma Project — Kathy Booth Personal Portfolio

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Google Fonts](https://img.shields.io/badge/Google_Fonts-4285F4?style=for-the-badge&logo=google&logoColor=white)
![Font Awesome](https://img.shields.io/badge/Font_Awesome-528DD7?style=for-the-badge&logo=fontawesome&logoColor=white)

---

## Project Overview

This project was built as part of a front-end development exercise: take a provided Figma design, rebrand it with personal content, and convert it into a fully functional, responsive website. The result is a polished personal landing page that serves as both a portfolio and a professional introduction.

**Figma Source:** Personal Portfolio Template

---

## Pages

### `index.html` — Home
The landing page introduces Kathy with a hero section featuring her name, a brief bio, a call-to-action button linking to Case Studies, and a headshot. Below the hero, a "Worked With" section displays logos of past clients and employers in styled, grayscale button cards.

### `casestudies.html` — Case Studies
Highlights three professional case studies — TechTarget (Advertising), Dynatrace (Software), and The Whiskey Store (Personal Goods). Each study is displayed in an alternating two-column layout with a project image, category tag, description, and a color-coded "View Case Study" button. All case study buttons link to the Contact page.

### `testimonials.html` — Testimonials
Displays four client testimonials in a 2×2 card grid. Each card features a gradient border, an opening quotation mark styled to sit on the border, the testimonial text, and a locally stored client photo with their name. Cards in the same row stretch to equal height, with the client info anchored to the bottom of each card.

### `recentwork.html` — Recent Work
Showcases two recent projects — Enterprise Software Sales and Whiskey Sales & Management — each with a locally stored photo, title, description, and a "Know More" button linking to the Contact page.

### `contact.html` — Get In Touch
A contact form with fields for email, mobile, and a message, plus a submit button. Includes a consistent footer matching all other pages.

---

## Features & Additions

The following features go beyond the base Figma-to-code requirements and were added to improve usability, polish, and professionalism.

### Navbar
All five pages share a consistent navbar built with two `<nav>` elements:
- **`.pages`** — navigation links to all five pages, correctly placed inside `<body>` on every page
- **`.social`** — icon links to LinkedIn, GitHub, and X (Twitter) using Font Awesome

The navbar is styled as a dark pill (`#1b1b1b`) centered on the page with `width: min(84%, 1280px)`, keeping it contained and clean on wide screens.

### Active Nav Link
Each page highlights its own link in the navbar using a manually applied `class="active-link"` on the corresponding `<a>` tag. The active link is styled in white with a subtle bottom border, making it easy for visitors to know which page they are on at a glance.

```css
.pages ul a.active-link {
  color: white;
  border-bottom: 2px solid #9c9c9c;
  padding-bottom: 3px;
}
```

### Hamburger Menu
On screens 498px and narrower, the navbar links collapse and are replaced by a hamburger icon (Font Awesome `fa-bars`). Clicking the icon toggles a `.active` class on `.pages`, which drops the menu down as a full-width vertical list. Clicking any nav link in the open menu automatically closes it via a JavaScript event listener present on every page.

### Consistent Footer
Every page includes a matching footer with a "Made with ❤️" credit and a copyright line:
```
© 2026 Kathy B. Productions. All rights reserved.
```
The footer uses `margin-top: auto` on pages with a flex column `<body>` to always sit at the bottom, even on short-content pages. On the Home page, the "Worked With" logos section serves as a secondary footer above the main footer.

### Smooth Scrolling
`scroll-behavior: smooth` is applied globally via the `*` selector, giving the site a polished feel when navigating between anchor points.

### Locally Stored Images
All client testimonial photos and recent work images have been downloaded and stored locally in the `/images` folder, replacing external URLs. This ensures the site does not break if an external source goes down and makes the project fully self-contained and portable.

### Responsive Design
The layout adapts across a wide range of screen sizes using multiple `@media` breakpoints:

| Breakpoint | Behavior |
|---|---|
| ≤ 1250px | Reduced navbar margins and button widths |
| ≤ 1050px | Navbar stacks vertically; adjusted cover padding |
| ≤ 790px | Testimonials grid switches to single column |
| ≤ 725px | Work container stacks vertically; contact form widens |
| ≤ 598px | Cover stacks vertically; header text narrows to 90% width |
| ≤ 560px | Logo buttons stack vertically and center |
| ≤ 498px | Hamburger menu replaces navbar links |
| ≤ 435px | Final spacing and button width adjustments for small phones |

### Testimonial Card Details
The testimonials page includes several custom styling touches:
- A CSS `::before` pseudo-element places a large opening quotation mark (`"`) on the top border of each card using `position: absolute` and `top: -21px`
- Cards in the same grid row are forced to equal height via `align-items: stretch` on the grid container
- Each card uses `display: flex; flex-direction: column; height: 100%` with `margin-top: auto` on `.client` to pin the client info to the bottom regardless of text length

---

## File Structure

```
/
├── index.html
├── casestudies.html
├── testimonials.html
├── recentwork.html
├── contact.html
├── styles.css
└── images/
    ├── IMG_7150.jpeg
    ├── bu-terrier-stencil.svg
    ├── TT_logo.png
    ├── tws_logo.png
    ├── house-stencil.svg
    ├── lukas-muller-ONZG-HRGKNQ-unsplash.jpg
    ├── cova-software-H2_sbPnk-YE-unsplash.jpg
    ├── casestudies3.avif
    ├── testjohndoe.avif
    ├── testjanedoes.avif
    ├── testjohndoesnt.avif
    ├── testjanedo.avif
    ├── recent1.avif
    └── recent2.avif
```

---

## Getting Started

No build tools or dependencies required. Simply open any `.html` file in a browser, or serve the folder with a local server:

```bash
npx serve .
```
