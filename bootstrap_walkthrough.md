# Adhoc Bootstrap Walkthrough & Explanation

This document explains what Bootstrap is, how we used it in the Adhoc project, and what the various classes mean. This guide will help you understand the language of Bootstrap so you can confidently make changes in the future!

## What is Bootstrap?

Bootstrap is an open-source CSS framework created to make front-end web development faster and easier. Instead of writing custom CSS from scratch for every element, Bootstrap provides pre-defined "utility classes" that you can apply directly to your HTML elements. 

By simply adding classes like `class="text-center"`, Bootstrap applies the necessary CSS behind the scenes. It's especially famous for being **responsive** (mobile-first), meaning it helps your website look great on phones, tablets, and desktop computers alike.

---

## The Bootstrap Grid System

Bootstrap uses a 12-column grid system to align content. 
- **`container`**: The main wrapper that centers your content and gives it some horizontal padding.
- **`row`**: A horizontal wrapper for columns.
- **`col`**: A column inside a row.

### Breakpoints and Sizing
Bootstrap uses abbreviations for screen sizes:
- (none): extra small screens (phones)
- **`sm`**: small screens
- **`md`**: medium screens (tablets)
- **`lg`**: large screens (laptops)

**Example from our code:**
```html
<div class="col-8 col-md-4">
```
- `col-8`: On extra small and small screens, this column takes up 8 out of 12 available slots (2/3 of the screen width).
- `col-md-4`: On medium and larger screens, this column takes up 4 out of 12 slots (1/3 of the screen width, allowing 3 cards to sit side-by-side).

**Alignment:**
We also used `justify-content-center` on the row holding the cards to ensure that when the columns wrap on smaller screens, they stay centered.

---

## Spacing Utilities (Margins & Padding)

Bootstrap has a shorthand for adding margins (space outside an element) and padding (space inside an element).

**Syntax:** `{property}{sides}-{size}`
- **Property**: `m` for margin, `p` for padding.
- **Sides**: `t` (top), `b` (bottom), `l` (left), `r` (right), `x` (left and right), `y` (top and bottom).
- **Size**: `0` to `5` (where 0 is none, and 5 is the largest amount of space).

**Example from our code:**
- `my-5`: Adds a large Margin on the Y-axis (Top and Bottom). We used this on rows to create breathing room between different sections.
- `py-0`: Sets Padding on the Y-axis to 0. We used this on the carousel captions to remove extra vertical space.

---

## Typography and Text Styling

Instead of writing CSS to change fonts, we used typography utility classes:

- **Alignment**: `text-center` (centers text), `text-right` (aligns text to the right).
- **Font Weights**: `font-weight-bold`, `font-weight-light`, `font-weight-normal`.
- **Italics**: `font-italic`.
- **Colors**: `text-white` (makes text white).

**Display Headings:**
Bootstrap provides special heading classes (`display-1` through `display-4`) that look bigger and slightly more opinionated than standard `<h1>` or `<h2>` tags. We used `display-3` for the Jumbotron, and `display-4` for our section headers ("Why Adhoc?" and "Meet the Team").

---

## Colors and Backgrounds

- **`bg-dark`**: Applies a dark grey/almost black background. We used this inside the jumbotron, the carousel captions, and the "Meet the Team" background.
- **`bg-light`**: Applies a light grey background (used by the default navbar).

---

## Components

Bootstrap comes with pre-built components that combine HTML layout and CSS styling:

1. **Navbar**: The navigation bar at the top. We used a standard layout and just swapped out links and added the Adhoc logo.
2. **Jumbotron**: (`jumbotron jumbotron-fluid`) A large, prominent box used to showcase key content or a hero image.
3. **Cards**: (`card`) A flexible content container. We removed the borders using `border-0`, placed an image on top (`card-img-top`), and centered the text inside the `card-body`.
4. **Carousel**: (`carousel slide`) A slideshow component for cycling through elements like images. 

---

## Borders and Sizing

- **Borders**: 
  - `rounded-top`: Rounds the top-left and top-right corners (used on the "Meet the Team" header row).
  - `rounded-bottom`: Rounds the bottom-left and bottom-right corners (used on the carousel row).
  - `rounded-pill`: Creates a pill-like curved border (used on the carousel captions).
  - `border-0`: Removes all borders.
- **Sizing**: 
  - `w-50`: Forces an element to take up exactly 50% of its parent's width. We used this alongside `mx-auto` (margin X-axis auto) to center the carousel horizontally!

By mixing and matching these classes, we were able to quickly build out the entire layout and styling of the Adhoc landing page without having to write a single line of custom CSS!
