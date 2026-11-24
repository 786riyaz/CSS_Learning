# CSS Revision Notes

==================================================================

# CSS

**CSS :: Cascading Style Sheets**

CSS is used to:

* Control layout
* Apply colors
* Set fonts
* Add spacing
* Make websites visually appealing

```
HTML = Structure
CSS  = Presentation
```

==================================================================

# CSS Syntax

```css
selector { property: value; }
selector { property1: value1; property2: value2; }

p { color: red; font-size: 16px; }
```

==================================================================

# Types of CSS

## 1️⃣ Inline CSS

```html
<p style="color:red">Text</p>
```

---

## 2️⃣ Internal CSS

```html
<style>
  p { color: blue; }
</style>
```

---

## 3️⃣ External CSS

```html
<link rel="stylesheet" href="style.css">
```

**CSS (`style.css`)**

```css
p {
  color: green;
}
```

✔ Clean
✔ Scalable
✔ Reusable

==================================================================

# CSS Selectors

## Element Selector

Examples:

```
p, h1, ul, table, td
```

---

## Class Selector

```css
.card { border: 1px solid black; }
```

HTML:

```html
<div class="card"></div>
```

---

## ID Selector

```css
#header { background: gray; }
```

HTML:

```html
<div id="header"></div>
```

📌 Rule:

* `class` → reusable
* `id` → unique

## Universal Selector

```css
* {
  color:red;
}
```

## Group Selector

```css
h1, h2, h3 {
  color:red;
}
```

## Descendant Selector

```css
div p {
  color:red;
}
```
---

==================================================================

# Colors in CSS

## Named Colors

```css
color: red;
```

## Hex

```css
color: #ff0000;
```

## RGB

```css
color: rgb(255, 0, 0);
```

## RGBA (with opacity) :: RGB with Alpha Channel

```css
color: rgba(255, 0, 0, 0.5);
```

==================================================================

# Units in CSS

## Absolute

* `px`

## Relative (IMPORTANT)

* `%`
* `em`
* `rem`

📌 Interview Tip:

`rem` is relative to root (`html`) font size.

Example:

```css
p {
  font-size: 1rem;
}
```

==================================================================

# Text Styling

```css
p {
  font-size: 16px;
  font-weight: 400;
  font-family: Arial, sans-serif;
  text-align: center;
  line-height: 1.5;
}
```

Common Properties:

* `font-size`
* `font-weight`
* `font-family`
* `text-align`
* `line-height`
* `text-transform`

---

==================================================================

# Background

## Background Color

```css
div {
  background-color: lightblue;
}
```

---

## Background Image

```css
div {
  background-image: url("bg.jpg");
  background-size: cover;
  background-position: center;
}
```

==================================================================

# Borders

```css
div {
  border: 2px solid black;
  border-radius: 8px;
}
```

✔ `solid`
✔ `dashed`
✔ `dotted`
✔ Rounded corners with `border-radius`

==================================================================

# Comments in CSS

```css
/* This is a comment */
```

---

==================================================================

# CSS Reset (Intro)

Browsers apply default styles.

Simple reset:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

📌 You’ll use this in almost every project.

==================================================================

# CSS Box Model (CORE CONCEPT)

Every HTML element is a **box** made of:

```
+----------------------+
|      margin          |
|  +---------------+   |
|  |   border      |   |
|  |  +---------+  |   |
|  |  | padding |  |   |
|  |  | content |  |   |
|  |  +---------+  |   |
|  +---------------+   |
+----------------------+
```

## Box Model Parts

* **Content** → text / image
* **Padding** → space inside
* **Border** → outline
* **Margin** → space outside

==================================================================

# Padding

```css
div {
  padding: 20px;
}
```

## Individual Sides

```css
padding-top: 10px;
padding-right: 15px;
padding-bottom: 10px;
padding-left: 15px;
```

## Shorthand

```css
padding: 10px 15px;
```

==================================================================

# Margin

```css
div {
  margin: 20px;
}
```

## Auto Centering (IMPORTANT)

```css
div {
  width: 300px;
  margin: 0 auto;
}
```

📌 `auto` centers horizontally.

==================================================================

# Border (Again for emphasis)

```css
div {
  border: 2px solid black;
}
```

==================================================================

# Width & Height

```css
div {
  width: 200px;
  height: 100px;
}
```

⚠️ Width does NOT include padding & border (by default).

==================================================================

# box-sizing (VERY IMPORTANT)

## Default (content-box)

```css
box-sizing: content-box;
```

## Best Practice

```css
* {
  box-sizing: border-box;
}
```

📌 `border-box` includes padding & border in width.

==================================================================

# Display Property

## block

```css
div {
  display: block;
}
```

* Full width
* New line

---

## inline

```css
span {
  display: inline;
}
```

* No width/height
* Same line

---

## inline-block

```css
div {
  display: inline-block;
}
```

* Width + height allowed
* Same line

---

## `display: none` vs `visibility: hidden`

```css
display: none;       /* removed from layout */
visibility: hidden;  /* space remains */
```

---

## Overflow

```css
div {
  overflow: hidden;
}
```

Values:

* `hidden`
* `scroll`
* `auto`

==================================================================

# Margin Collapse (INTERVIEW FAVORITE)

```css
p {
  margin: 20px;
}
```

* Vertical margins collapse
* Horizontal margins do NOT collapse
* Only affects block elements

==================================================================

# CSS Positioning (CORE CONCEPT)

## Default Position

```css
position: static;
```

* Default for all elements
* `top`, `left` don’t work

---

## position: relative

```css
.box {
  position: relative;
  top: 10px;
  left: 20px;
}
```

📌 Moves relative to itself
📌 Creates reference for absolute children

---

## position: absolute

```css
.child {
  position: absolute;
  top: 0;
  right: 0;
}
```

📌 Positioned relative to nearest positioned ancestor
📌 Removed from normal document flow

---

## position: fixed

```css
.header {
  position: fixed;
  top: 0;
}
```

📌 Stays fixed on scroll
📌 Relative to viewport

---

## position: sticky

```css
.nav {
  position: sticky;
  top: 0;
}
```

📌 Acts like relative → fixed on scroll
📌 Needs a `top` value

---

## z-index (Stacking Order)

```css
.box1 { z-index: 1; }
.box2 { z-index: 10; }
```

Rules:

* Works only on positioned elements
* Higher number = on top

---

## Common Positioning Mistake

❌ Expecting `absolute` to work without parent positioned

✅ Correct:

```css
.parent { position: relative; }
.child  { position: absolute; }
```

==================================================================

# 🔥 FLEXBOX (MOST IMPORTANT PART)

Flexbox is a **1-D layout system**:

* Row OR column
* Perfect for navbars, cards, alignment

---

## Flex Container

```css
.container {
  display: flex;
}
```

📌 Parent becomes flex container
📌 Children become flex items

---

## Main Axis vs Cross Axis

* `flex-direction: row` → main axis = horizontal
* `flex-direction: column` → main axis = vertical

---

## justify-content (Main Axis)

```css
justify-content: space-between;
```

Values:

* `flex-start`
* `center`
* `space-between`
* `space-around`
* `space-evenly`

---

## align-items (Cross Axis)

```css
align-items: center;
```

Values:

* `stretch`
* `center`
* `flex-start`
* `flex-end`

---

## flex-direction

```css
flex-direction: row;
flex-direction: column;
```

---

## gap (Spacing Between Items)

```css
.container {
  gap: 16px;
}
```

---

## Flex Item Properties

### flex-grow

```css
.item {
  flex-grow: 1;
}
```

### flex-shrink

```css
.item {
  flex-shrink: 0;
}
```

### flex-basis

```css
.item {
  flex-basis: 200px;
}
```

### Shorthand

```css
flex: 1 0 200px;
```

---

## Perfect Centering (INTERVIEW GOLD)

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

---

## Navbar Example (Real World)

```css
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

==================================================================

# CSS Grid

CSS Grid is a **2-dimensional layout system**:

* Rows AND columns
* Best for full-page layouts

📌 Flexbox = 1D
📌 Grid = 2D

---

## Creating a Grid Container

```css
.container {
  display: grid;
}
```

---

## Defining Columns & Rows

```css
.container {
  grid-template-columns: 200px 1fr 200px;
  grid-template-rows: auto 1fr auto;
}
```

📌 `fr` = fractional unit (remaining space)

---

## Grid Gap

```css
.container {
  gap: 20px;
}
```

---

## Placing Items Using Line Numbers

```css
.item {
  grid-column: 1 / 3;
  grid-row: 1 / 2;
}
```

---

## Grid Template Areas (VERY IMPORTANT)

```css
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar content"
    "footer footer";
}
```

Assign Areas:

```css
.header { grid-area: header; }
.sidebar { grid-area: sidebar; }
.content { grid-area: content; }
.footer { grid-area: footer; }
```

📌 Best for page layouts

---

## Auto-Fit & Auto-Fill

```css
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```

📌 Creates responsive grids automatically

==================================================================

# Responsive Design Basics

Responsive design works on:

* Mobile
* Tablet
* Desktop

---

## Media Queries

```css
@media (max-width: 768px) {
  body {
    background: lightgray;
  }
}
```

📌 Apply CSS based on screen size

---

## Mobile-First Approach (INTERVIEW FAVORITE)

```css
/* Mobile */
.card { width: 100%; }

/* Desktop */
@media (min-width: 768px) {
  .card { width: 300px; }
}
```

📌 Start small → scale up

---

## Viewport Units

```css
height: 100vh;
width: 100vw;
```

* `vw` → viewport width
* `vh` → viewport height

---

## Responsive Images (CSS)

```css
img {
  max-width: 100%;
  height: auto;
}
```

---

## When to Use Grid vs Flexbox?

| Use Case    | Best    |
| ----------- | ------- |
| Navbar      | Flexbox |
| Cards row   | Flexbox |
| Page layout | Grid    |
| Dashboard   | Grid    |

==================================================================

# Pseudo-Classes (User Interaction)

Used to style elements based on state.

```css
button:hover {
  background: blue;
}
button:active {
  background: orange;
}
```

Common pseudo-classes:

* `:hover`
* `:focus`
* `:active`
* `:visited`
* `:checked`
* `:disabled`

📌 Accessibility Tip:
Always style `:focus` for keyboard users.

---

# Pseudo-Elements (Virtual Elements)

Used to style parts of elements.

```css
p::first-letter {
  font-size: 32px;
}
```

Common:

* `::before`
* `::after`
* `::first-letter`
* `::first-line`
backdrop
placeholder
selection
slotted()

Example:

```css
.button::after {
  content: "→";
}
```

---

# CSS Transitions (Smooth Effects)

```css
button {
  transition: background 0.3s ease;
}
```

Multiple properties:

```css
transition: all 0.3s ease-in-out;
```

---

# CSS Animations (`@keyframes`)

```css
@keyframes fadeIn {
  from { opacity: 0; }
  to   { opacity: 1; }
}

.box {
  animation: fadeIn 1s ease;
}
```

📌 Use animations sparingly

---

# CSS Variables (Custom Properties)

```css
:root {
  --primary-color: #3498db;
}
```

Use:

```css
button {
  background: var(--primary-color);
}
```

✔ Easy theming
✔ Central control

---

# Dark Mode (CSS Only)

```css
@media (prefers-color-scheme: dark) {
  body {
    background: #111;
    color: #fff;
  }
}
```

---

# CSS Specificity (INTERVIEW FAVORITE)

Specificity Order:

```
Inline > ID > Class > Element
```

Example:

```css
#box { color: red; }
.box { color: blue; }
```

➡️ Red wins

---

# Cascade & Inheritance

* Later rules override earlier ones
* Some properties inherit (`color`, `font`)
* Some don’t (`margin`, `padding`)

---

# BEM Methodology (VERY IMPORTANT)

Block__Element--Modifier

```css
.card {}
.card__title {}
.card--active {}
```

✔ Scalable
✔ Team-friendly

---

# Performance Best Practices

✔ Avoid deep selectors
✔ Avoid `!important`
✔ Reuse classes
✔ Use CSS variables

==================================================================

# Advanced Selectors (Power Tools)

## Attribute Selectors

```css
input[type="text"] {
  border: 1px solid #333;
}
```

---

## Starts / Ends / Contains

```css
a[href^="https"] { color: green; }
a[href$=".pdf"] { color: red; }
a[href*="blog"] { font-weight: bold; }
```

---

## :not() and :is()

```css
button:not(.primary) {
  opacity: 0.7;
}
```

```css
:is(h1, h2, h3) {
  font-family: sans-serif;
}
```

📌 Cleaner & faster selectors

---

# clamp() – Responsive Without Media Queries

```css
h1 {
  font-size: clamp(1.5rem, 4vw, 3rem);
}
```

Meaning:

* Minimum: `1.5rem`
* Preferred: `4vw`
* Maximum: `3rem`

---

# min() & max()

```css
.container {
  width: min(100%, 1200px);
}
```

📌 Prevents overflow on large screens

---

# Container Queries (Modern CSS – Conceptual)

```css
@container (min-width: 400px) {
  .card {
    flex-direction: row;
  }
}
```

📌 Styles based on container size, not viewport
📌 New but powerful

---

# Custom Scrollbars

```css
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-thumb {
  background: #888;
}
```

⚠️ Mostly WebKit browsers

---

# Print Styles

```css
@media print {
  nav, footer {
    display: none;
  }
}
```

📌 Used for invoices, reports

---

# CSS Architecture (REAL WORLD)

## Folder Structure

```
css/
├─ base.css
├─ layout.css
├─ components.css
├─ theme.css
```

✔ Maintainable
✔ Scalable

---

# Common CSS Anti-Patterns

❌ Overusing `!important`
❌ Deep nested selectors
❌ Inline styles
❌ Fixed widths everywhere

---

DOM (Document of Object Model)
document
  html
    head
      title :: My Title
    body
      h1 :: heading
      a :: link :: href
      

We can inspect a particular element and edit the CSS live in browser inspect mode 
