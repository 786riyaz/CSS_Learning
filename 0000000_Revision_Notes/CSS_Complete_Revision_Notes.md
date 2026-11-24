# CSS Complete Revision Notes (Basic → Advanced)

> A consolidated revision guide combining both supplied CSS notes. Repeated topics have been merged, while distinct examples and details have been retained. Additional explanations and commonly used CSS concepts are marked **Additional** where useful.

## Table of Contents

1. [What is CSS?](#1-what-is-css)
2. [CSS Syntax and Comments](#2-css-syntax-and-comments)
3. [Ways to Add CSS](#3-ways-to-add-css)
4. [CSS Selectors](#4-css-selectors)
5. [Colors](#5-colors-in-css)
6. [CSS Units](#6-css-units)
7. [Text and Font Styling](#7-text-and-font-styling)
8. [Backgrounds](#8-backgrounds)
9. [Borders and Outlines](#9-borders-and-outlines)
10. [CSS Reset](#10-css-reset)
11. [The CSS Box Model](#11-the-css-box-model)
12. [Padding and Margin](#12-padding-and-margin)
13. [Width and Height](#13-width-and-height)
14. [Display](#14-display)
15. [Overflow](#15-overflow)
16. [Margin Collapse](#16-margin-collapse)
17. [Positioning and z-index](#17-positioning-and-z-index)
18. [Float and Clear](#18-float-and-clear)
19. [Flexbox](#19-flexbox)
20. [CSS Grid](#20-css-grid)
21. [Responsive Design](#21-responsive-design)
22. [Pseudo-classes](#22-pseudo-classes)
23. [Pseudo-elements](#23-pseudo-elements)
24. [Transitions](#24-transitions)
25. [Transforms](#25-transforms)
26. [Animations](#26-animations)
27. [CSS Variables](#27-css-variables-custom-properties)
28. [Dark Mode](#28-dark-mode)
29. [Cascade, Specificity and Inheritance](#29-cascade-specificity-and-inheritance)
30. [Advanced CSS Functions](#30-advanced-css-functions)
31. [Container Queries](#31-container-queries)
32. [Custom Scrollbars](#32-custom-scrollbars)
33. [Print Styles](#33-print-styles)
34. [CSS Architecture and BEM](#34-css-architecture-and-bem)
35. [Performance and Anti-patterns](#35-performance-and-anti-patterns)
36. [DOM and CSS in Browser DevTools](#36-dom-and-css-in-browser-devtools)
37. [Interview Revision Checklist](#37-interview-revision-checklist)

---

## 1. What is CSS?

**CSS = Cascading Style Sheets.**

CSS is a stylesheet language used to describe how HTML elements should look and be laid out.

CSS is used to:

- Control page and component layouts.
- Apply colors.
- Set fonts and text styles.
- Add spacing.
- Create responsive designs for mobile, tablet and desktop.
- Add animations and transitions.
- Improve the visual presentation and usability (UI/UX) of a website.

The basic responsibilities of web technologies:

```text
HTML        = Structure and content
CSS         = Presentation and layout
JavaScript  = Behaviour and interactivity
```

**Example:** HTML creates a button; CSS controls its color, size, border and spacing; JavaScript can define what happens when the button is clicked.

## 2. CSS Syntax and Comments

A CSS rule consists of a selector and a declaration block.

```css
selector {
  property: value;
}
```

- **Selector:** identifies the HTML element(s) to style.
- **Property:** identifies what aspect to change.
- **Value:** specifies the style to apply.
- A declaration is written as `property: value;`.

Example with multiple declarations:

```css
p {
  color: red;
  font-size: 16px;
}
```

A compact rule is also valid:

```css
p { color: red; font-size: 16px; }
```

### CSS comments

Comments are ignored by the browser and are useful for documenting styles.

```css
/* This is a CSS comment */
```

## 3. Ways to Add CSS

There are three common ways to apply CSS to an HTML document.

### 3.1 Inline CSS

CSS is written directly in an element's `style` attribute.

```html
<p style="color: red;">Text</p>
```

Useful for a quick, one-off style, but difficult to maintain when used extensively.

### 3.2 Internal CSS

CSS is written inside a `<style>` element, usually in the HTML document's `<head>`.

```html
<head>
  <style>
    p {
      color: blue;
    }
  </style>
</head>
```

Useful when styles are specific to a single HTML page.

### 3.3 External CSS

CSS is kept in a separate `.css` file and linked to the HTML document.

HTML:

```html
<head>
  <link rel="stylesheet" href="style.css">
</head>
```

`style.css`:

```css
p {
  color: green;
}
```

**External CSS is generally the best practice** for maintainable projects because it is clean, reusable and scalable.

## 4. CSS Selectors

Selectors target the HTML elements to which CSS declarations should apply.

### 4.1 Basic selectors

| Selector type | Syntax | Example |
|---|---|---|
| Element/type | `element` | `p {}` |
| Class | `.className` | `.card {}` |
| ID | `#idName` | `#header {}` |
| Universal | `*` | `* {}` |
| Grouping | comma-separated selectors | `h1, h2 {}` |

#### Element selector

Selects all elements of a given HTML type.

```css
p, h1, ul, table, td {
  color: navy;
}
```

#### Class selector

A class can be reused on multiple elements.

```css
.card {
  border: 1px solid black;
}
```

```html
<div class="card"></div>
```

#### ID selector

Targets an element with a particular ID. An ID is intended to be unique within a page.

```css
#header {
  background: gray;
}
```

```html
<div id="header"></div>
```

Remember:

- `class` → reusable; multiple elements can share a class.
- `id` → intended to identify one unique element on the page.

#### Universal selector

Selects all elements.

```css
* {
  color: red;
}
```

#### Group selector

Applies the same declarations to several selectors.

```css
h1, h2, h3 {
  color: red;
}
```

### 4.2 Combinators

Combinators describe relationships between selectors.

| Combinator | Name | Meaning |
|---|---|---|
| `A B` | Descendant | Selects matching `B` elements anywhere inside `A`. |
| `A > B` | Child | Selects matching `B` elements that are direct children of `A`. |
| `A + B` | Adjacent sibling | Selects the first `B` immediately following `A` under the same parent. |
| `A ~ B` | General sibling | Selects matching `B` siblings that appear after `A` under the same parent. |

```css
div p {
  color: red;       /* Any p inside a div */
}

div > p {
  color: blue;      /* Direct child p only */
}

div + p {
  margin-top: 20px; /* p immediately after div */
}

div ~ p {
  color: green;     /* Later p siblings */
}
```

### 4.3 Attribute selectors

Select elements based on the presence or value of an attribute.

```css
input[type="text"] {
  border: 1px solid #333;
}

a[href^="https"] {
  color: green;       /* Attribute value starts with https */
}

a[href$=".pdf"] {
  color: red;         /* Attribute value ends with .pdf */
}

a[href*="blog"] {
  font-weight: bold;  /* Attribute value contains blog */
}
```

Common operators:

- `[attr]` — attribute exists.
- `[attr="value"]` — exact value.
- `[attr^="value"]` — starts with value.
- `[attr$="value"]` — ends with value.
- `[attr*="value"]` — contains value.

### 4.4 Selector list and logical pseudo-classes

```css
button:not(.primary) {
  opacity: 0.7;
}

:is(h1, h2, h3) {
  font-family: sans-serif;
}
```

- `:not(...)` selects elements that do not match the selector inside it.
- `:is(...)` matches an element if it matches any selector in the list.
- `:where(...)` works similarly to `:is(...)`, but contributes zero specificity.
- `:has(...)` selects an element based on whether it contains or is related to elements matching the argument. It is often described as a relational pseudo-class.

### 4.5 Pseudo-classes

Pseudo-classes select elements based on a state, position or condition. Examples include:

```css
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
:has()
```

More details and examples appear in [Pseudo-classes](#22-pseudo-classes).

### 4.6 Pseudo-elements

Pseudo-elements style a specific part of an element or create a generated part.

```css
::before
::after
::first-letter
::first-line
::selection
::placeholder
::backdrop
::marker
::slotted()
```

More details and examples appear in [Pseudo-elements](#23-pseudo-elements).

## 5. Colors in CSS

CSS supports several color formats.

### Named colors

```css
color: red;
color: lightblue;
```

### Hexadecimal

```css
color: #ff0000;
```

Hex colors commonly use `#RRGGBB`; shorthand `#RGB` is also supported when each channel can be represented by a repeated digit.

### RGB

```css
color: rgb(255, 0, 0);
```

The channels represent red, green and blue.

### RGBA

RGBA is RGB with an alpha (opacity) channel.

```css
color: rgba(255, 0, 0, 0.5);
```

An alpha value of `0` is fully transparent; `1` is fully opaque.

### HSL and HSLA

```css
color: hsl(0, 100%, 50%);
color: hsla(0, 100%, 50%, 0.5);
```

HSL represents hue, saturation and lightness. HSLA adds an alpha channel. Modern CSS also permits alpha in the newer `rgb()` and `hsl()` syntaxes.

## 6. CSS Units

CSS units specify dimensions, spacing, font sizes and other measurements.

### 6.1 Absolute units

Common absolute units:

| Unit | Meaning |
|---|---|
| `px` | CSS pixel |
| `cm` | Centimetre |
| `mm` | Millimetre |
| `in` | Inch |
| `pt` | Point |

`px` is the most commonly used absolute CSS unit for screen layouts. CSS pixels are not necessarily the same as physical device pixels.

### 6.2 Relative units

| Unit | Relative to |
|---|---|
| `%` | A context-dependent reference, often a containing dimension |
| `em` | The computed font size of the element for font-relative sizing; in inherited values it can compound through ancestors |
| `rem` | The root (`html`) element's font size |
| `vw` | 1% of viewport width |
| `vh` | 1% of viewport height |
| `vmin` | 1% of the smaller viewport dimension |
| `vmax` | 1% of the larger viewport dimension |
| `ch` | Width of the `0` glyph in the relevant font |
| `ex` | x-height of the relevant font |

**Important interview distinction:**

- `rem` → relative to the root (`html`) font size.
- `em` → relative to the relevant element/parent font-size context; nested `em` font sizing can compound.
- `%` → relative to the property-specific reference, not always the parent width.

Example:

```css
html {
  font-size: 16px;
}

p {
  font-size: 1rem; /* 16px when root font size is 16px */
}

.child {
  font-size: 1.5em; /* 1.5 times its inherited/computed font-size context */
}
```

## 7. Text and Font Styling

Example:

```css
p {
  font-size: 16px;
  font-weight: 400;
  font-family: Arial, sans-serif;
  font-style: normal;
  text-align: center;
  line-height: 1.5;
  letter-spacing: 1px;
  word-spacing: 2px;
  text-transform: uppercase;
  text-decoration: underline;
}
```

Common properties:

| Property | Purpose |
|---|---|
| `font-size` | Text size |
| `font-weight` | Thickness/boldness |
| `font-family` | Typeface and fallback fonts |
| `font-style` | Normal, italic or oblique |
| `font-variant` | Alternate font forms, such as small caps |
| `text-align` | Horizontal alignment of inline content |
| `line-height` | Height of a line box |
| `letter-spacing` | Space between characters |
| `word-spacing` | Space between words |
| `text-transform` | Uppercase, lowercase, capitalize, etc. |
| `text-decoration` | Underline, overline, line-through, etc. |
| `white-space` | How whitespace and line wrapping are handled |
| `text-overflow` | How clipped inline overflow is indicated |
| `text-shadow` | Shadow behind text |

Example of truncating a single line:

```css
.title {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

## 8. Backgrounds

### Background color

```css
div {
  background-color: lightblue;
}
```

### Background image

```css
div {
  background-image: url("bg.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: fixed;
}
```

Common background properties:

- `background-color`
- `background-image`
- `background-size`
- `background-position`
- `background-repeat`
- `background-attachment`

Shorthand:

```css
div {
  background: red url("img.png") no-repeat center / cover;
}
```

`cover` scales the image to cover the background area; some cropping may occur. `contain` scales it so the whole image fits; empty space may remain.

## 9. Borders and Outlines

### Border

```css
div {
  border: 2px solid black;
  border-radius: 8px;
}
```

Border longhands:

```css
border-width: 2px;
border-style: solid;
border-color: black;
```

Common border styles:

- `none`
- `solid`
- `dashed`
- `dotted`
- `double`
- `groove`
- `ridge`
- `inset`
- `outset`

`border-radius` rounds corners.

### Outline — Additional

An outline is drawn outside an element's border and does not take up layout space. It is commonly used for keyboard focus indicators.

```css
button:focus-visible {
  outline: 2px solid blue;
  outline-offset: 3px;
}
```

## 10. CSS Reset

Browsers apply default styles to many HTML elements. A reset or normalization strategy helps make styling more predictable.

A simple commonly used reset:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

This removes default margin and padding and applies `border-box` sizing to all elements. Real projects may use a more carefully designed reset rather than removing every default style.

## 11. The CSS Box Model

Every HTML element is laid out as a rectangular box.

The layers from inside to outside are:

```text
Content → Padding → Border → Margin
```

Conceptual diagram:

```text
+----------------------------------+
|              margin              |
|   +--------------------------+   |
|   |          border          |   |
|   |   +------------------+   |   |
|   |   |     padding      |   |   |
|   |   |  +------------+  |   |   |
|   |   |  |  content   |  |   |   |
|   |   |  +------------+  |   |   |
|   |   +------------------+   |   |
|   +--------------------------+   |
+----------------------------------+
```

Parts:

- **Content:** text, image or other actual content.
- **Padding:** space between content and border (inside the border).
- **Border:** line surrounding the padding and content.
- **Margin:** space outside the border, separating the element from other elements.

### `box-sizing`

#### `content-box` (default)

```css
box-sizing: content-box;
```

With `content-box`, the declared `width` and `height` apply to the content box only. Padding and border are added outside those dimensions.

#### `border-box` (commonly recommended)

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}
```

With `border-box`, the declared width and height include content, padding and border. Margin remains outside.

**Example:** If an element has `width: 200px`, `padding: 20px` on both sides and `border: 2px`, its total width is 244px with `content-box`, but 200px with `border-box` (assuming the declared width can contain the content).

## 12. Padding and Margin

### Padding

Padding creates space inside the border, between the content and border.

```css
div {
  padding: 20px;
}
```

Individual sides:

```css
div {
  padding-top: 10px;
  padding-right: 15px;
  padding-bottom: 10px;
  padding-left: 15px;
}
```

Shorthand examples:

```css
padding: 10px;              /* all four sides */
padding: 10px 15px;          /* top/bottom, left/right */
padding: 10px 15px 20px;     /* top, left/right, bottom */
padding: 10px 15px 20px 25px;/* top, right, bottom, left */
```

### Margin

Margin creates space outside the border.

```css
div {
  margin: 20px;
}
```

Individual sides: `margin-top`, `margin-right`, `margin-bottom`, `margin-left`.

Shorthand follows the same one-, two-, three- and four-value order as padding.

### Horizontal centering with `margin: 0 auto`

```css
.container {
  width: 300px;
  margin: 0 auto;
}
```

For a block-level element with a constrained width, `margin-left: auto` and `margin-right: auto` distribute the available horizontal space equally and centre it. This does not vertically centre the element.

## 13. Width and Height

```css
.box {
  width: 200px;
  height: 100px;
  min-width: 150px;
  max-width: 500px;
  min-height: 80px;
  max-height: 400px;
}
```

Common properties:

- `width`, `height`
- `min-width`, `max-width`
- `min-height`, `max-height`

By default (`content-box`), width and height do not include padding and border. With `border-box`, they do.

## 14. Display

The `display` property determines how an element participates in layout.

### `block`

```css
div {
  display: block;
}
```

- Starts on a new line.
- Normally occupies the available inline width of its containing block.
- `width` and `height` can be set.

Examples of elements that are block-level by default include `div`, `p` and headings.

### `inline`

```css
span {
  display: inline;
}
```

- Flows within a line with surrounding text.
- Does not start a new line.
- `width` and `height` do not work in the usual way on non-replaced inline elements.
- Horizontal padding and margins work; vertical effects do not push surrounding lines in the same way as block layout.

Examples include `span`, `a` and `strong` by default.

### `inline-block`

```css
.box {
  display: inline-block;
}
```

- Flows alongside inline content.
- `width` and `height` can be set.
- Behaves like an inline-level box externally and a block container internally.

### `none` vs `visibility: hidden`

```css
.hidden {
  display: none;       /* Not rendered; takes no layout space */
}

.invisible {
  visibility: hidden;  /* Invisible, but its layout space remains */
}
```

`display: none` removes the element from layout. `visibility: hidden` keeps its layout space.

### Other display values

- `flex` — creates a flex container.
- `grid` — creates a grid container.
- `flow-root` — creates a block formatting context.
- `table`, `list-item`, etc. — provide other layout behaviours.

## 15. Overflow

Controls what happens when content does not fit inside an element's box.

```css
.container {
  overflow: hidden;
}
```

Common values:

- `visible` — default; overflowing content can be visible.
- `hidden` — clips overflowing content; no user-facing scrollbar.
- `scroll` — provides scrolling mechanism even if content fits.
- `auto` — browser provides scrolling when needed.

Axis-specific properties:

```css
overflow-x: auto;
overflow-y: hidden;
```

## 16. Margin Collapse

Vertical margins of certain block-level elements in normal flow can collapse into one margin instead of adding together.

Example:

```css
.first {
  margin-bottom: 20px;
}

.second {
  margin-top: 30px;
}
```

In a typical margin-collapsing situation, the resulting gap is 30px, not 50px.

Key points:

- Vertical margins can collapse.
- Horizontal margins do not collapse.
- Margin collapse applies in specific block formatting contexts and normal-flow situations; it does not happen in flex or grid containers.
- Parent/child vertical margins can also collapse in certain circumstances.

This is a common CSS interview topic.

## 17. Positioning and z-index

The `position` property controls how an element is positioned.

### `static`

```css
.box {
  position: static;
}
```

- Default positioning for elements.
- Remains in normal document flow.
- `top`, `right`, `bottom` and `left` do not offset a statically positioned element.

### `relative`

```css
.box {
  position: relative;
  top: 10px;
  left: 20px;
}
```

- Offset relative to the element's normal position.
- Its original space remains reserved in normal flow.
- Commonly establishes the containing block/reference for absolutely positioned descendants.

### `absolute`

```css
.parent {
  position: relative;
}

.child {
  position: absolute;
  top: 0;
  right: 0;
}
```

- Removed from normal document flow.
- Positioned relative to its nearest ancestor that establishes an absolute-positioning containing block (commonly a positioned ancestor).
- If no such ancestor exists, it is generally positioned relative to the initial containing block.

**Common mistake:** expecting an absolutely positioned child to be positioned relative to a particular parent when that parent has no positioning/containing-block setup. A common solution is to set `position: relative` on the parent.

### `fixed`

```css
.header {
  position: fixed;
  top: 0;
}
```

- Removed from normal flow.
- Usually positioned relative to the viewport.
- Stays in place while the page scrolls.
- Certain ancestor properties, such as transforms, can establish a containing block for fixed descendants.

### `sticky`

```css
.nav {
  position: sticky;
  top: 0;
}
```

- Behaves like relative positioning until a scroll threshold is reached, then sticks within its scroll container.
- Requires an inset threshold such as `top: 0`.
- Can be affected by the scrolling ancestor and container dimensions.

### Offsets

Common inset properties:

```css
top: 0;
right: 0;
bottom: 0;
left: 0;
```

Logical alternatives include `inset-block` and `inset-inline`.

### z-index (stacking order)

```css
.box1 {
  position: relative;
  z-index: 1;
}

.box2 {
  position: relative;
  z-index: 10;
}
```

- Controls stacking order within the relevant stacking context.
- A larger `z-index` generally paints above a smaller one in the same stacking context.
- `z-index` is not simply a global layer number: stacking contexts can constrain descendants.
- It applies to positioned elements and also to certain flex/grid items and other cases.

## 18. Float and Clear

Float was commonly used for layouts before Flexbox and Grid. It is still useful for wrapping text around images.

```css
.image {
  float: left;
}

.sidebar {
  float: right;
}

.footer {
  clear: both;
}
```

- `float: left` or `float: right` moves an element to a side and allows inline content to wrap around it.
- `clear: both` prevents an element from sitting alongside floats on either side.
- Prefer Flexbox or Grid for modern page and component layouts.

## 19. Flexbox

Flexbox is a **one-dimensional layout system**. It lays items out along one main axis at a time: a row or a column.

Common uses: navigation bars, rows of cards, alignment and component layouts.

### Flex container

```css
.container {
  display: flex;
}
```

- The parent becomes the flex container.
- Its direct children become flex items.

### Main axis and cross axis

- `flex-direction: row` → main axis is horizontal (inline direction in the usual writing mode); cross axis is vertical.
- `flex-direction: column` → main axis is vertical; cross axis is horizontal.

### `flex-direction`

```css
.container {
  flex-direction: row;
  /* row | row-reverse | column | column-reverse */
}
```

### `flex-wrap`

```css
.container {
  flex-wrap: wrap;
}
```

Controls whether flex items stay on one line or wrap onto multiple lines. Values include `nowrap`, `wrap` and `wrap-reverse`.

### `justify-content` — main axis

```css
.container {
  justify-content: center;
}
```

Common values:

- `flex-start`
- `flex-end`
- `center`
- `space-between`
- `space-around`
- `space-evenly`

### `align-items` — cross axis

```css
.container {
  align-items: center;
}
```

Common values:

- `stretch`
- `center`
- `flex-start`
- `flex-end`
- `baseline`

### `align-content`

Controls the distribution of multiple flex lines along the cross axis when wrapping creates extra space.

```css
.container {
  flex-wrap: wrap;
  align-content: center;
}
```

It does not replace `align-items`; `align-items` aligns items within a line, while `align-content` distributes the lines.

### `gap`

```css
.container {
  gap: 16px;
}
```

Adds spacing between flex items without adding margins to the outer edges.

### Flex item properties

#### `flex-grow`

Controls how flex items share positive free space.

```css
.item {
  flex-grow: 1;
}
```

#### `flex-shrink`

Controls how flex items shrink when there is insufficient space.

```css
.item {
  flex-shrink: 0;
}
```

#### `flex-basis`

Sets an item's initial main-size before free space is distributed.

```css
.item {
  flex-basis: 200px;
}
```

#### `order`

Changes the visual order of flex items without changing their DOM order.

```css
.item {
  order: 2;
}
```

#### `align-self`

Overrides the container's `align-items` value for an individual item.

```css
.item {
  align-self: flex-end;
}
```

#### `flex` shorthand

```css
.item {
  flex: 1 0 200px;
}
```

The three values represent `flex-grow`, `flex-shrink` and `flex-basis`.

### Perfect centering

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}
```

### Navbar example

```css
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

## 20. CSS Grid

CSS Grid is a **two-dimensional layout system**: it handles rows and columns together.

- Flexbox = 1D (row or column).
- Grid = 2D (rows and columns).

Grid is useful for full-page layouts, dashboards and card grids.

### Create a grid container

```css
.container {
  display: grid;
}
```

### Define columns and rows

```css
.container {
  display: grid;
  grid-template-columns: 200px 1fr 200px;
  grid-template-rows: auto 1fr auto;
}
```

`fr` is a fractional unit that distributes available grid space.

### Gap

```css
.container {
  gap: 20px;
  /* row-gap and column-gap can also be set separately */
}
```

### Place items using grid lines

```css
.item {
  grid-column: 1 / 3;
  grid-row: 1 / 2;
}
```

Grid line numbers identify the boundaries of grid tracks.

### Grid template areas

```css
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar content"
    "footer footer";
}

.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.content { grid-area: content; }
.footer  { grid-area: footer; }
```

Named areas make page layouts easier to read and maintain. Each row in the template must describe a valid rectangular arrangement of named areas.

### Auto-fit, auto-fill and minmax

```css
.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}
```

- `repeat()` repeats a track pattern.
- `minmax(200px, 1fr)` gives each track a minimum size of 200px and allows it to grow.
- `auto-fit` fits the available tracks and collapses empty tracks so existing items can expand.
- `auto-fill` preserves the available track slots, including empty ones.

Both are useful for responsive grids. Their difference is most visible when there are fewer items than the number of tracks that could fit.

## 21. Responsive Design

Responsive design makes a website adapt to different viewport sizes and device contexts, such as mobile, tablet and desktop.

### Media queries

```css
@media (max-width: 768px) {
  body {
    background: lightgray;
  }
}

@media (min-width: 768px) {
  /* Styles at this width and above */
}
```

Media queries apply CSS when a condition (such as viewport width) matches.

### Mobile-first approach

Write the base styles for smaller screens first, then add enhancements for larger screens.

```css
/* Mobile-first base style */
.card {
  width: 100%;
}

/* Larger screens */
@media (min-width: 768px) {
  .card {
    width: 300px;
  }
}
```

Start small, then scale up.

### Viewport units

```css
.hero {
  min-height: 100vh;
  width: 100vw;
}
```

- `vw` → 1% of viewport width.
- `vh` → 1% of viewport height.
- `vmin` → 1% of the smaller viewport dimension.
- `vmax` → 1% of the larger viewport dimension.

**Additional:** On mobile devices, newer viewport units such as `svh`, `lvh` and `dvh` can help account for browser interface changes. Use them where appropriate and provide fallbacks if needed.

### Responsive images

```css
img {
  max-width: 100%;
  height: auto;
}
```

This prevents an image from exceeding its containing block while preserving its aspect ratio.

### Grid vs Flexbox

| Use case | Common choice |
|---|---|
| Navbar | Flexbox |
| Single row of cards | Flexbox |
| Full page layout | Grid |
| Dashboard with rows and columns | Grid |
| Aligning items along one axis | Flexbox |
| Coordinating rows and columns | Grid |

These are guidelines, not strict rules; both systems can be combined.

## 22. Pseudo-classes

Pseudo-classes style an element based on its state, position or relationship.

Interaction examples:

```css
button:hover {
  background: blue;
}

button:active {
  background: orange;
}

button:focus {
  outline: 2px solid blue;
}
```

Common pseudo-classes:

| Pseudo-class | Purpose |
|---|---|
| `:hover` | Pointer is over the element |
| `:focus` | Element has focus |
| `:focus-visible` | Focus should be visibly indicated, commonly for keyboard interaction |
| `:active` | Element is being activated |
| `:visited` | Link has been visited |
| `:checked` | Checkbox/radio or applicable option is checked |
| `:disabled` | Form control is disabled |
| `:first-child` | Element is the first child of its parent |
| `:last-child` | Element is the last child of its parent |
| `:nth-child()` | Element matches a position/pattern among siblings |
| `:not()` | Element does not match the supplied selector |
| `:is()` | Element matches at least one selector in the supplied list |
| `:has()` | Element matches based on a relative selector |

Accessibility tip: provide a clear `:focus` or `:focus-visible` style so keyboard users can identify the focused element. Do not remove focus indicators without an accessible replacement.

## 23. Pseudo-elements

Pseudo-elements style a specific part of an element or create generated content.

### `::before` and `::after`

```css
.button::after {
  content: "→";
}
```

`content` is generally required for generated `::before` and `::after` content to appear.

### Other common pseudo-elements

- `::first-letter` — first typographic letter/character of a block.
- `::first-line` — first formatted line.
- `::selection` — portion of text selected by the user.
- `::placeholder` — placeholder text in supported form controls.
- `::backdrop` — backdrop behind elements such as a dialog shown modally.
- `::marker` — marker box of a list item.
- `::slotted()` — targets elements assigned to a slot in a web component's shadow tree.

Example:

```css
p::first-letter {
  font-size: 32px;
}

::selection {
  background: yellow;
}
```

Pseudo-classes use one colon in their modern syntax (for example, `:hover`); pseudo-elements generally use two (for example, `::before`).

## 24. Transitions

Transitions make changes in CSS property values occur smoothly over time.

```css
button {
  background: blue;
  transition: background 0.3s ease;
}

button:hover {
  background: red;
}
```

Longhand properties:

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

Common timing functions:

- `ease`
- `linear`
- `ease-in`
- `ease-out`
- `ease-in-out`
- `cubic-bezier(...)` — custom timing curve.
- `steps(...)` — step-based transition.

Prefer transitioning specific properties instead of `all` when possible, for more predictable behaviour.

## 25. Transforms

Transforms change an element's visual position, size, rotation or skew without changing normal document flow.

### 2D transforms

```css
.box {
  transform: rotate(45deg);
  transform: scale(2);
  transform: translateX(50px);
  transform: skew(10deg);
}
```

Common transform functions:

- `translate()`, `translateX()`, `translateY()`
- `rotate()`
- `scale()`, `scaleX()`, `scaleY()`
- `skew()`, `skewX()`, `skewY()`

Only one `transform` declaration applies at a time; combine multiple functions in one declaration:

```css
.box {
  transform: translateX(50px) rotate(45deg) scale(1.1);
}
```

### 3D transforms

```css
.box {
  transform: rotateX(45deg);
  /* rotateY(), rotateZ(), translateZ(), scaleZ() */
}
```

`perspective` can provide depth for 3D transformed elements.

## 26. Animations

CSS animations allow styles to change through keyframes.

### Define keyframes

```css
@keyframes rotation {
  0% {
    left: 10px;
  }

  50% {
    left: 50px;
  }

  100% {
    left: 200px;
  }
}
```

For `left` to move an element, it needs an applicable positioning mode. Many animations can instead use `transform: translateX(...)`, which is often more performant.

Another example:

```css
@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

.box {
  animation: fadeIn 1s ease;
}
```

### Animation properties

```css
.box {
  animation-name: rotation;
  animation-duration: 4s;
  animation-timing-function: ease-in-out;
  animation-delay: 0s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
```

Other useful properties include:

- `animation-fill-mode` — controls styles before/after animation.
- `animation-play-state` — `running` or `paused`.
- `animation-composition` — controls how effects combine where supported.

Shorthand:

```css
.box {
  animation: rotation 4s ease-in-out 0s infinite alternate;
}
```

Use animations purposefully. Respect users' reduced-motion preferences where appropriate:

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

## 27. CSS Variables (Custom Properties)

CSS custom properties store reusable values. They are often declared in `:root` so they can be used throughout the document.

```css
:root {
  --primary-color: #3498db;
  --spacing: 16px;
}

button {
  background: var(--primary-color);
  padding: var(--spacing);
}
```

Benefits:

- Central control of repeated values.
- Easier theming and maintenance.
- Values can be overridden in narrower scopes.
- They participate in the cascade and can be changed at runtime.

Fallback example:

```css
color: var(--text-color, black);
```

## 28. Dark Mode

CSS can respond to the operating system or browser's preferred color scheme.

```css
@media (prefers-color-scheme: dark) {
  body {
    background: #111;
    color: #fff;
  }
}
```

This detects the user's preference; it does not by itself create a manual theme toggle. A manual toggle generally uses a class, attribute or theme value controlled by application code.

## 29. Cascade, Specificity and Inheritance

### Cascade

When multiple CSS declarations apply to the same element and property, the browser resolves them through the CSS cascade. Origin, importance, cascade layers, specificity and source order all matter.

A useful beginner rule: when declarations have the same cascade priority and specificity, the later declaration generally wins.

### Specificity

A simplified specificity order:

```text
Inline style > ID selector > Class/attribute/pseudo-class > Element/pseudo-element
```

Example:

```css
#box {
  color: red;
}

.box {
  color: blue;
}
```

If both rules apply and no other cascade factor changes the result, the ID selector wins, so the text is red.

Specificity is often represented as a tuple:

```text
(ID, class/attribute/pseudo-class, element/pseudo-element)
```

For example:

- `#header` → `(1, 0, 0)`
- `.card` → `(0, 1, 0)`
- `p` → `(0, 0, 1)`

Universal selector `*` and combinators do not add specificity. `:where()` has zero specificity; `:is()`, `:not()` and `:has()` take specificity from their argument selectors.

### `!important`

```css
color: red !important;
```

`!important` changes cascade priority. Avoid using it routinely because it makes styles harder to override and maintain. It is not accurate to think of it as simply another specificity level.

### Inheritance

Some properties inherit from the parent; others do not.

Common inherited properties include:

- `color`
- `font-family`
- `font-size`
- `line-height`

Common non-inherited properties include:

- `margin`
- `padding`
- `border`
- `width`

Inheritance can be controlled with values such as `inherit`, `initial`, `unset` and `revert`.

## 30. Advanced CSS Functions

### `clamp()`

Sets a responsive value with a minimum, preferred and maximum.

```css
h1 {
  font-size: clamp(1.5rem, 4vw, 3rem);
}
```

Meaning:

- Minimum: `1.5rem`
- Preferred/fluid value: `4vw`
- Maximum: `3rem`

### `min()`

Returns the smallest value in the provided calculation list.

```css
.container {
  width: min(100%, 1200px);
}
```

This allows the container to use the available width but not exceed 1200px.

### `max()`

Returns the largest value in the provided list.

```css
.box {
  width: max(50%, 300px);
}
```

### `calc()`

Performs calculations using compatible CSS values.

```css
.container {
  width: calc(100% - 50px);
}
```

Whitespace around `+` and `-` operators is required in `calc()` expressions.

## 31. Container Queries

Media queries commonly respond to viewport conditions. Container queries allow a component to respond to the size or characteristics of a containing context.

```css
.card-wrapper {
  container-type: inline-size;
}

@container (min-width: 400px) {
  .card {
    flex-direction: row;
  }
}
```

Important points:

- Define a query container (for example, with `container-type`).
- The query responds to the container, not the overall viewport.
- Useful for reusable components placed in different layout regions.

## 32. Custom Scrollbars

Example using WebKit/Blink scrollbar pseudo-elements:

```css
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-thumb {
  background: #888;
}
```

This approach is browser-specific and scrollbar styling support differs across browsers. A more widely supported basic option is:

```css
* {
  scrollbar-width: thin;
  scrollbar-color: #888 transparent;
}
```

Avoid making scrollbars difficult to see or use.

## 33. Print Styles

Use the `print` media query to adapt pages for printing, such as invoices and reports.

```css
@media print {
  nav,
  footer {
    display: none;
  }
}
```

You can also control page breaks, margins and print-specific colors where needed.

## 34. CSS Architecture and BEM

A simple CSS folder structure:

```text
css/
├── base.css
├── layout.css
├── components.css
└── theme.css
```

Possible responsibilities:

- `base.css` — resets, typography and foundational element styles.
- `layout.css` — page-level layout rules.
- `components.css` — reusable component styles.
- `theme.css` — colors, design tokens and themes.

Common CSS methodologies:

- **BEM** — Block Element Modifier.
- **OOCSS** — Object-Oriented CSS.
- **SMACSS** — Scalable and Modular Architecture for CSS.

### BEM

BEM naming pattern:

```text
Block__Element--Modifier
```

Example:

```css
.card {}
.card__title {}
.card--active {}
```

- **Block:** standalone component, such as `card`.
- **Element:** a part of the block, such as `card__title`.
- **Modifier:** a variation or state, such as `card--active`.

BEM helps make class names predictable, scalable and team-friendly.

## 35. Performance and Anti-patterns

### Best practices

- Prefer external CSS for maintainability and reuse.
- Avoid unnecessarily deep or overly complex selectors.
- Avoid routine use of `!important`.
- Reuse classes and component styles.
- Use CSS variables for repeated design values.
- Use shorthand properties where they improve clarity.
- Minify CSS for production when appropriate.
- Avoid animating layout-heavy properties when a transform or opacity animation can achieve the same effect.
- Keep styles organized and remove unused CSS.
- Use responsive sizing rather than fixed widths everywhere.

### Common anti-patterns

- Overusing `!important`.
- Deeply nested selectors.
- Excessive inline styles.
- Fixed widths everywhere.
- Repeating the same declarations in many places.
- Removing keyboard focus indicators without replacements.

## 36. DOM and CSS in Browser DevTools

**DOM = Document Object Model.**

The browser parses HTML and represents the document as a tree of objects/nodes. CSS selectors match elements in this document tree and the browser calculates styles and layout.

Simplified HTML/DOM structure:

```text
document
└── html
    ├── head
    │   └── title
    │       └── "My Title" (text node)
    └── body
        ├── h1
        │   └── "Heading" (text node)
        └── a
            └── "Link" (text node)
```

Important distinction:

- The **DOM** is the object/tree representation of the document.
- A **node** is a general item in that tree (for example, a document node, element node, text node or comment node).
- An **element** is a specific kind of node representing an HTML/XML element, such as `div`, `p` or `a`.
- Therefore, every element is a node, but not every node is an element.

### Browser DevTools

Using the browser's Inspect/Developer Tools, you can:

- Inspect a particular HTML element.
- View its DOM position and attributes.
- See matched CSS rules and computed styles.
- Edit CSS values live to test changes.
- Inspect layout information such as box model dimensions.
- Debug responsive layouts and element positioning.

Changes made directly in DevTools are generally temporary and do not automatically update your source files.

## 37. Interview Revision Checklist

Be ready to explain and demonstrate:

- What CSS stands for and what it does.
- HTML vs CSS vs JavaScript responsibilities.
- Inline, internal and external CSS.
- Element, class, ID and universal selectors.
- Descendant vs child vs adjacent sibling vs general sibling combinators.
- Attribute selectors and pseudo-classes vs pseudo-elements.
- Block vs inline vs inline-block.
- `display: none` vs `visibility: hidden`.
- CSS box model and `content-box` vs `border-box`.
- Padding vs margin; margin collapse.
- `rem` vs `em`; absolute vs relative units.
- `position: relative` vs `absolute` vs `fixed` vs `sticky`.
- `z-index` and stacking contexts.
- Flexbox main axis vs cross axis.
- `justify-content` vs `align-items` vs `align-content`.
- `flex-grow`, `flex-shrink`, `flex-basis` and `flex` shorthand.
- Flexbox (1D) vs Grid (2D).
- Grid `auto-fit` vs `auto-fill`; `minmax()`.
- Media queries and mobile-first design.
- Responsive images and viewport units.
- CSS transitions vs transforms vs animations.
- CSS variables and dark mode.
- Cascade, specificity, inheritance and `!important`.
- `clamp()`, `min()`, `max()` and `calc()`.
- Container queries.
- BEM and maintainable CSS architecture.
- CSS performance best practices.
- DOM, node and element differences.
- Inspecting and editing CSS through browser DevTools.

---

## Quick Reference: Common CSS Properties

| Category | Properties |
|---|---|
| Color | `color`, `opacity` |
| Text | `font-size`, `font-weight`, `font-family`, `text-align`, `line-height`, `text-transform`, `text-decoration` |
| Background | `background`, `background-color`, `background-image`, `background-size`, `background-position`, `background-repeat` |
| Box model | `width`, `height`, `padding`, `border`, `margin`, `box-sizing` |
| Display/overflow | `display`, `visibility`, `overflow`, `overflow-x`, `overflow-y` |
| Positioning | `position`, `top`, `right`, `bottom`, `left`, `inset`, `z-index` |
| Flexbox | `flex-direction`, `flex-wrap`, `justify-content`, `align-items`, `align-content`, `gap`, `flex`, `order`, `align-self` |
| Grid | `grid-template-columns`, `grid-template-rows`, `grid-template-areas`, `grid-column`, `grid-row`, `grid-area`, `gap` |
| Effects | `transition`, `transform`, `animation`, `box-shadow`, `text-shadow` |
| Responsive | `@media`, `@container`, `min-width`, `max-width`, `clamp()` |
| Theming | `--custom-properties`, `var()`, `prefers-color-scheme` |

---

**Revision advice:** Understand the box model, display, positioning, Flexbox, Grid, responsive design, selectors and specificity especially well. Practise each concept in a small HTML/CSS page rather than memorising property names alone.
