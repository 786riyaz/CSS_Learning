# 🎯 CSS Complete Revision Notes (Basic → Advanced)

---

# 1️⃣ What is CSS?

**CSS = Cascading Style Sheets**

CSS is used to:

* Control layout
* Apply colors
* Set fonts
* Add spacing
* Create responsive designs
* Add animations & transitions
* Improve UI/UX

```
HTML = Structure
CSS  = Presentation
JavaScript = Behavior
```

---

# 2️⃣ CSS Syntax

```css
selector {
  property: value;
}
```

Multiple properties:

```css
p {
  color: red;
  font-size: 16px;
}
```

---

# 3️⃣ Types of CSS

## 1. Inline CSS

```html
<p style="color:red;">Text</p>
```

## 2. Internal CSS

```html
<style>
  p { color: blue; }
</style>
```

## 3. External CSS (Best Practice)

```html
<link rel="stylesheet" href="style.css">
```

```css
p { color: green; }
```

✔ Clean
✔ Reusable
✔ Scalable

---

# 4️⃣ CSS Selectors (Complete)

## Basic Selectors

| Selector  | Example      |
| --------- | ------------ |
| Element   | `p {}`       |
| Class     | `.card {}`   |
| ID        | `#header {}` |
| Universal | `* {}`       |
| Group     | `h1, h2 {}`  |

## Combinators

```css
div p {}        /* Descendant */
div > p {}      /* Child */
div + p {}      /* Adjacent sibling */
div ~ p {}      /* General sibling */
```

## Attribute Selectors

```css
input[type="text"] {}
a[href^="https"] {}
a[href$=".pdf"] {}
a[href*="blog"] {}
```

## Pseudo Classes

```
:hover
:focus
:active
:visited
:checked
:disabled
:first-child
:last-child
:nth-child()
:not()
:is()
:has() (modern)
```

## Pseudo Elements

```
::before
::after
::first-letter
::first-line
::selection
::placeholder
::backdrop
::marker
```

---

# 5️⃣ Colors in CSS

```css
color: red;
color: #ff0000;
color: rgb(255,0,0);
color: rgba(255,0,0,0.5);
color: hsl(0, 100%, 50%);
color: hsla(0, 100%, 50%, 0.5);
```

---

# 6️⃣ Units in CSS

## Absolute Units

```
px
cm
mm
in
pt
```

## Relative Units

```
%
em
rem
vh
vw
vmin
vmax
ch
ex
```

📌 `rem` → relative to root font size
📌 `em` → relative to parent

---

# 7️⃣ Text Styling

```css
p {
  font-size: 16px;
  font-weight: 400;
  font-family: Arial, sans-serif;
  text-align: center;
  line-height: 1.5;
  letter-spacing: 1px;
  word-spacing: 2px;
  text-transform: uppercase;
  text-decoration: underline;
}
```

Additional:

```
font-style
font-variant
white-space
text-overflow
text-shadow
```

---

# 8️⃣ Background

```css
background-color: red;
background-image: url("image.png");
background-size: cover;
background-position: center;
background-repeat: no-repeat;
background-attachment: fixed;
background: red url(img.png) no-repeat center/cover;
```

---

# 9️⃣ Border

```css
border: 2px solid black;
border-radius: 8px;
border-width
border-style
border-color
```

Styles:

```
solid
dashed
dotted
double
groove
ridge
inset
outset
```

---

# 🔟 Box Model (CORE)

Content → Padding → Border → Margin

```css
box-sizing: content-box; /* default */
box-sizing: border-box;  /* recommended */
```

---

# 1️⃣1️⃣ Width & Height

```css
width: 200px;
height: 100px;
min-width
max-width
min-height
max-height
```

---

# 1️⃣2️⃣ Display

```
block
inline
inline-block
none
flex
grid
```

Difference:

```
display: none → removed
visibility: hidden → space remains
```

---

# 1️⃣3️⃣ Overflow

```css
overflow: hidden;
overflow: scroll;
overflow: auto;
overflow-x
overflow-y
```

---

# 1️⃣4️⃣ Positioning

```
static
relative
absolute
fixed
sticky
```

```css
top
right
bottom
left
z-index
```

---

# 1️⃣5️⃣ Float & Clear

```css
float: left;
float: right;
clear: both;
```

Used before flexbox for layouts.

---

# 🔥 1️⃣6️⃣ Flexbox (1D Layout)

```css
display: flex;
flex-direction: row | column;
flex-wrap: wrap;
justify-content: center;
align-items: center;
align-content: center;
gap: 10px;
```

Flex Item Properties:

```
flex-grow
flex-shrink
flex-basis
order
align-self
```

Shorthand:

```css
flex: 1 0 200px;
```

---

# 🟦 1️⃣7️⃣ CSS Grid (2D Layout)

```css
display: grid;
grid-template-columns
grid-template-rows
gap
grid-column
grid-row
grid-area
```

```css
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```

---

# 1️⃣8️⃣ Responsive Design

## Media Queries

```css
@media (max-width: 768px) {}
@media (min-width: 768px) {}
```

## Viewport Units

```
vw
vh
vmin
vmax
```

## Mobile First Approach

Write mobile styles first → add larger screens later.

---

# 1️⃣9️⃣ Transitions

```css
transition-property: all;
transition-duration: 1s;
transition-timing-function: ease-in-out;
transition-delay: 1s;
```

Shorthand:

```css
transition: all 1s ease-in-out 1s;
```

Timing Functions:

```
ease
linear
ease-in
ease-out
ease-in-out
```

---

# 2️⃣0️⃣ Transform

```css
transform: rotate(45deg);
transform: scale(2);
transform: translateX(50px);
transform: skew(10deg);
```

3D:

```
rotateX
rotateY
rotateZ
```

---

# 2️⃣1️⃣ Animations

```css
@keyframes rotation {
  0% { left: 10px; }
  50% { left: 50px; }
  100% { left: 200px; }
}
```

```css
animation-name: rotation;
animation-duration: 4s;
animation-timing-function: ease-in-out;
animation-delay: 0s;
animation-iteration-count: infinite;
animation-direction: alternate;
```

Shorthand:

```css
animation: rotation 4s ease-in-out 0s infinite alternate;
```

---

# 2️⃣2️⃣ CSS Variables

```css
:root {
  --primary-color: #3498db;
}
```

Use:

```css
color: var(--primary-color);
```

---

# 2️⃣3️⃣ Dark Mode

```css
@media (prefers-color-scheme: dark) {
  body {
    background: #111;
    color: #fff;
  }
}
```

---

# 2️⃣4️⃣ Specificity

```
Inline > ID > Class > Element
```

Avoid:

```
!important
```

---

# 2️⃣5️⃣ Advanced Functions

```css
clamp()
min()
max()
calc()
```

Example:

```css
font-size: clamp(1.5rem, 4vw, 3rem);
width: min(100%, 1200px);
width: calc(100% - 50px);
```

---

# 2️⃣6️⃣ Container Queries

```css
@container (min-width: 400px) {}
```

---

# 2️⃣7️⃣ Custom Scrollbars

```css
::-webkit-scrollbar {}
::-webkit-scrollbar-thumb {}
```

---

# 2️⃣8️⃣ Print Styles

```css
@media print {}
```

---

# 2️⃣9️⃣ CSS Architecture

```
base.css
layout.css
components.css
theme.css
```

Methodologies:

```
BEM
OOCSS
SMACSS
```

---

# 3️⃣0️⃣ Performance Best Practices

✔ Use external CSS
✔ Avoid deep nesting
✔ Avoid !important
✔ Use variables
✔ Use shorthand properties
✔ Minify CSS for production

---

# 3️⃣1️⃣ DOM Structure

```
document
 └── html
      ├── head
      │    └── title
      └── body
           ├── h1
           └── a
```

Inspect elements using browser DevTools.

---

# 🎯 Interview Important Topics

* Box Model
* Specificity
* Flexbox
* Grid
* Positioning
* Mobile-first
* Difference between `display: none` and `visibility: hidden`
* Difference between `absolute` and `relative`
* `rem` vs `em`
* `auto-fit` vs `auto-fill`

---
