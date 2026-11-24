# CSS Interview Questions — Detailed Revision Notes

**Level:** Beginner to Intermediate  
**Purpose:** Understand common CSS interview questions with definitions, examples, comparisons, and practical notes.

---

## 1. What is a Media Query in CSS?

A **media query** is a CSS feature that applies styles only when a specified condition is true. It is commonly used to make a website responsive across mobile phones, tablets, laptops, and larger screens.

### Basic syntax

```css
@media media-type and (condition) {
  /* CSS rules applied when the condition matches */
}
```

A common example:

```css
/* Default styles */
.card {
  width: 100%;
}

/* Apply these styles when the viewport is 768px wide or narrower */
@media (max-width: 768px) {
  .card {
    background-color: lightblue;
  }
}
```

### `min-width` vs `max-width`

These conditions compare the **viewport width** with the given threshold.

| Query | Meaning |
|---|---|
| `@media (min-width: 768px)` | Applies when viewport width is **768 CSS pixels or greater**. |
| `@media (max-width: 768px)` | Applies when viewport width is **768 CSS pixels or smaller**. |
| `@media (width: 768px)` | Applies when viewport width is exactly 768 CSS pixels. |

The boundary is inclusive: at exactly `768px`, both `min-width: 768px` and `max-width: 768px` match.

### Does `px` in a media query mean a lower limit or upper limit?

**Neither by itself.** `px` is the unit. The media feature determines the comparison:

- `min-width` means a **lower boundary**.
- `max-width` means an **upper boundary**.
- `width` means an **exact match**.

For example:

```css
/* 768px and above */
@media (min-width: 768px) {
  body {
    font-size: 18px;
  }
}

/* 768px and below */
@media (max-width: 768px) {
  body {
    font-size: 14px;
  }
}
```

At exactly `768px`, both rules match. If both set the same property on the same element with equal specificity, the rule appearing later in the cascade wins.

### Combining conditions

```css
/* Between 768px and 1024px, inclusive */
@media (min-width: 768px) and (max-width: 1024px) {
  .container {
    padding: 24px;
  }
}
```

You can also use range syntax in modern browsers:

```css
@media (768px <= width <= 1024px) {
  .container {
    padding: 24px;
  }
}
```

### Other media query examples

```css
/* Only for screens */
@media screen {
  body {
    font-family: Arial, sans-serif;
  }
}

/* Print styles */
@media print {
  nav,
  footer {
    display: none;
  }
}

/* User prefers a dark color scheme */
@media (prefers-color-scheme: dark) {
  body {
    background: #111;
    color: #fff;
  }
}

/* User prefers reduced motion */
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms;
    transition-duration: 0.01ms;
    scroll-behavior: auto;
  }
}
```

### Mobile-first approach

In a mobile-first design, write the default styles for smaller screens, then add styles for wider screens using `min-width`.

```css
/* Base styles: mobile */
.container {
  width: 100%;
  padding: 12px;
}

/* Tablet and wider */
@media (min-width: 768px) {
  .container {
    max-width: 720px;
    margin-inline: auto;
  }
}

/* Desktop and wider */
@media (min-width: 1024px) {
  .container {
    max-width: 960px;
  }
}
```

**Interview answer:** A media query lets us conditionally apply CSS based on characteristics of the device or browsing environment, such as viewport width, screen type, color scheme, or motion preference. It is widely used for responsive design.

---

## 2. What are `px`, `%`, `em`, `rem`, `vh`, and `vw` in CSS?

These are CSS units. They define measurements such as font size, width, height, padding, and margins.

There are two broad groups:

- **Absolute units:** `px`, `cm`, `mm`, `in`, `pt`, etc.
- **Relative units:** `%`, `em`, `rem`, `vw`, `vh`, `vmin`, `vmax`, etc.

### 2.1 `px` — CSS pixel

`px` means **CSS pixel**. It is a fixed CSS length unit, not necessarily one physical screen pixel.

```css
.box {
  width: 200px;
  font-size: 16px;
}
```

A CSS pixel is a reference unit. The browser maps CSS pixels to physical display pixels according to device pixel ratio, zoom, and other display factors.

For example, on a display with a device pixel ratio of 2, one CSS pixel may be represented by two physical pixels in each dimension.

**Use it when:** You need a predictable CSS measurement, such as a thin border or a specific icon size. For layouts and typography, relative units can often adapt more naturally.

### 2.2 `%` — Percentage

`%` is relative to another value, usually a property-specific containing block or reference value. The exact reference depends on which CSS property is being used.

```css
.parent {
  width: 500px;
}

.child {
  width: 50%;
}
```

The child width is 50% of the relevant containing block's width, so in this example it is 250px.

Another example:

```css
.parent {
  font-size: 20px;
}

.child {
  font-size: 150%;
}
```

The child's font size is 30px because it is 150% of the inherited/computed parent font size.

**Important:** Do not assume every percentage is calculated from the parent's width. Percentage values have property-specific rules. For example, percentage heights depend on the containing block's height, and some percentage margins and paddings are resolved against the containing block's inline size.

### 2.3 `em` — Relative to font size

For the `font-size` property, `em` is relative to the inherited font size of the parent. For many other properties, `em` is relative to the computed font size of the element itself.

```css
.parent {
  font-size: 20px;
}

.child {
  font-size: 1.5em;
  padding: 1em;
}
```

Here:

- `.child` font size = `1.5 × 20px` = `30px`.
- `.child` padding = `1 × 30px` = `30px`.

This can be useful when you want spacing to scale with the component's text size.

**Common caution:** Nested `em` font sizes can compound.

```css
.parent {
  font-size: 20px;
}

.child {
  font-size: 1.5em; /* 30px */
}

.grandchild {
  font-size: 1.5em; /* 45px */
}
```

### 2.4 `rem` — Relative to root font size

`rem` means **root em**. It is relative to the computed font size of the root element, normally `<html>`.

```css
html {
  font-size: 16px;
}

h1 {
  font-size: 2rem; /* 32px */
}

p {
  font-size: 1rem; /* 16px */
}
```

Unlike `em`, `rem` does not compound because of nested parent font sizes.

**Use it when:** You want consistent, scalable typography and spacing across a website.

### 2.5 `vw` — Viewport width

`vw` is a percentage of the viewport width.

- `1vw` = 1% of the viewport width.
- `100vw` = 100% of the viewport width.

```css
.hero {
  width: 80vw;
}
```

If the viewport is 1200px wide, `80vw` is 960px.

### 2.6 `vh` — Viewport height

`vh` is a percentage of the viewport height.

- `1vh` = 1% of the viewport height.
- `100vh` = 100% of the viewport height.

```css
.hero {
  min-height: 100vh;
}
```

This makes the hero section at least as tall as the viewport under the traditional `vh` definition.

**Mobile browser note:** Browser interface bars can make viewport height behave unexpectedly on mobile. Modern CSS also provides:

- `svh` — small viewport height.
- `lvh` — large viewport height.
- `dvh` — dynamic viewport height, which responds to browser UI changes.

Example:

```css
.hero {
  min-height: 100dvh;
}
```

Use `dvh` when you want the element to follow the dynamic viewport height, while checking browser support for your target audience.

### 2.7 Other useful relative units

| Unit | Meaning |
|---|---|
| `vmin` | 1% of the smaller viewport dimension. |
| `vmax` | 1% of the larger viewport dimension. |
| `ch` | Based on the advance measure of the `0` (zero) glyph in the element's font; useful for controlling line length approximately. |
| `ex` | Based on the x-height of the element's font. |
| `svw`, `lvw`, `dvw` | Small, large, and dynamic viewport width units. |
| `svh`, `lvh`, `dvh` | Small, large, and dynamic viewport height units. |

### Quick comparison

| Unit | Relative to | Example |
|---|---|---|
| `px` | CSS reference pixel | `width: 200px` |
| `%` | A property-specific reference/containing block | `width: 50%` |
| `em` | Font size; for `font-size`, inherited parent size | `padding: 1em` |
| `rem` | Root (`html`) font size | `font-size: 2rem` |
| `vw` | Viewport width | `width: 50vw` |
| `vh` | Viewport height | `height: 100vh` |

### Practical example

```css
html {
  font-size: 16px;
}

.card {
  width: 80%;
  max-width: 600px;
  padding: 1.5rem;
  font-size: 1rem;
  border: 1px solid #ccc;
  margin-inline: auto;
}

.card-title {
  font-size: 1.5em;
}

.hero {
  min-height: 100vh;
}
```

### When should you use each unit?

- Use **`px`** for precise small measurements where a fixed CSS length is useful, such as borders.
- Use **`%`** for sizing relative to a containing block or other property-defined reference.
- Use **`em`** for component spacing that should scale with the component's font size.
- Use **`rem`** for consistent site-wide typography and spacing.
- Use **`vw` / `vh`** for sizing in relation to the viewport, but avoid relying on them alone for all content sizing.
- Use **`clamp()`** when you want a value to scale fluidly but stay within minimum and maximum limits.

Example:

```css
h1 {
  font-size: clamp(1.5rem, 4vw, 3rem);
}
```

---

## 3. What is the difference between `:focus` and `:active`?

`:focus` and `:active` are CSS pseudo-classes. They represent different interaction states.

### `:focus`

An element matches `:focus` when it has keyboard focus or otherwise receives focus.

For example, a user can move focus to a button using the Tab key, or focus an input by clicking it.

```css
input:focus {
  outline: 2px solid blue;
  border-color: blue;
}
```

Common focusable elements include:

- Text inputs and textareas.
- Buttons.
- Links.
- Select elements.
- Elements made focusable with `tabindex`.

### `:active`

An element matches `:active` while it is being activated, typically during the period when the user presses a mouse button or presses/holds an appropriate activation control.

```css
button:active {
  transform: scale(0.97);
  background-color: darkblue;
}
```

It is commonly used to show a pressed or clicked visual state.

### Main differences

| Feature | `:focus` | `:active` |
|---|---|---|
| Meaning | Element currently has focus | Element is currently being activated/pressed |
| Keyboard use | Commonly reached using Tab and keyboard interaction | Can match during keyboard activation as well |
| Duration | Can remain after the click or key press ends | Usually temporary during activation |
| Typical use | Focus outline, accessible focus styling | Pressed-button effect |

### Example showing both

```html
<button class="my-button">Click Me</button>
```

```css
.my-button {
  background: royalblue;
  color: white;
  padding: 12px 20px;
  border: none;
  cursor: pointer;
}

/* The button has keyboard or programmatic focus */
.my-button:focus {
  outline: 3px solid orange;
  outline-offset: 3px;
}

/* The button is currently being pressed/activated */
.my-button:active {
  transform: scale(0.95);
  background: navy;
}
```

### What is `:focus-visible`?

`:focus-visible` is a related pseudo-class. It styles focus when the browser determines that a visible focus indicator is appropriate, commonly for keyboard navigation.

```css
button:focus-visible {
  outline: 3px solid orange;
  outline-offset: 3px;
}
```

A common accessible pattern is:

```css
button:focus {
  outline: none;
}

button:focus-visible {
  outline: 3px solid orange;
  outline-offset: 3px;
}
```

Only remove the default focus indicator if you provide a clear replacement. Keyboard users must be able to see which element is focused.

**Interview answer:** `:focus` applies when an element has focus and can remain active after a click or key press. `:active` applies during the element's activation, such as while a button is being pressed. `:focus-visible` helps show focus indicators when they are most useful, especially for keyboard navigation.

---

## 4. What is the CSS `calc()` function?

`calc()` is a CSS function that performs calculations to determine a CSS property value. It can combine compatible units such as percentages, pixels, and `rem`.

### Syntax

```css
property: calc(expression);
```

### Example 1: Subtract pixels from a percentage

```css
.container {
  width: calc(100% - 40px);
}
```

The container's width is 40px less than the available percentage-based width.

### Example 2: Combine different units

```css
.main {
  width: calc(100% - 250px);
}
```

This is useful for layouts where a sidebar has a fixed width and the main content takes the remaining space.

### Example 3: Calculate height

```css
.content {
  height: calc(100vh - 80px);
}
```

If the viewport height is 900px, the calculated height is 820px.

### Example 4: Calculate font size

```css
h1 {
  font-size: calc(1rem + 2vw);
}
```

The font size increases as the viewport width increases.

For production typography, `clamp()` can prevent the result from becoming too small or too large:

```css
h1 {
  font-size: clamp(1.5rem, calc(1rem + 2vw), 3rem);
}
```

### Example 5: Equal-width columns with a gap

```css
.column {
  width: calc((100% - 40px) / 3);
}
```

This can create three columns with a total of 40px reserved for gaps, assuming the surrounding layout matches the calculation.

### Important rules

1. Put spaces around the `+` and `-` operators.

   ```css
   width: calc(100% - 20px); /* Correct */
   ```

   ```css
   width: calc(100%-20px); /* Invalid */
   ```

2. Parentheses can group calculations.

   ```css
   width: calc((100% - 40px) / 2);
   ```

3. The units must be compatible with the property and CSS calculation rules.

4. `calc()` can combine values with different units when CSS can resolve the expression.

### `calc()` vs `min()` vs `max()` vs `clamp()`

| Function | Purpose | Example |
|---|---|---|
| `calc()` | Performs a calculation | `calc(100% - 20px)` |
| `min()` | Chooses the smallest value | `min(100%, 1200px)` |
| `max()` | Chooses the largest value | `max(300px, 50%)` |
| `clamp()` | Keeps a value between a minimum and maximum | `clamp(16px, 4vw, 48px)` |

**Interview answer:** `calc()` allows us to calculate CSS values dynamically and combine units, for example `width: calc(100% - 250px)` to subtract a fixed sidebar width from the available space.

---

## 5. What is the CSS `cubic-bezier()` function?

`cubic-bezier()` defines a custom **timing function** for CSS transitions and animations. It controls how the animation progresses over time: whether it starts slowly, speeds up, slows down, or changes speed in another way.

It does not define the animated property or the duration. It defines the pacing of the change.

### Syntax

```css
transition-timing-function: cubic-bezier(x1, y1, x2, y2);
```

The function uses four control-point coordinates:

- `(x1, y1)` — first control point.
- `(x2, y2)` — second control point.

The curve begins at `(0, 0)` and ends at `(1, 1)`. The x-coordinates must be between `0` and `1`. The y-coordinates can be outside that range, allowing overshoot or anticipation effects.

### Example

```css
.box {
  width: 100px;
  height: 100px;
  background: royalblue;
  transition: transform 1s cubic-bezier(0.68, -0.55, 0.27, 1.55);
}

.box:hover {
  transform: translateX(200px);
}
```

When the user hovers over the box, it moves horizontally. The custom curve controls the speed and feel of that movement.

### Common built-in timing functions

```css
transition-timing-function: ease;
transition-timing-function: linear;
transition-timing-function: ease-in;
transition-timing-function: ease-out;
transition-timing-function: ease-in-out;
```

| Timing function | General behavior |
|---|---|
| `linear` | Constant speed from start to finish. |
| `ease` | Starts and ends gently, with faster movement in between. |
| `ease-in` | Starts slowly and speeds up. |
| `ease-out` | Starts quickly and slows down. |
| `ease-in-out` | Starts slowly, speeds up, then slows down. |
| `cubic-bezier(...)` | Lets you define a custom curve. |

### Using cubic-bezier with an animation

```css
@keyframes move {
  from {
    transform: translateX(0);
  }

  to {
    transform: translateX(300px);
  }
}

.box {
  animation: move 2s cubic-bezier(0.42, 0, 0.58, 1) infinite alternate;
}
```

### What do the four numbers mean?

For:

```css
cubic-bezier(0.42, 0, 0.58, 1)
```

- `0.42` = first control point's x-coordinate.
- `0` = first control point's y-coordinate.
- `0.58` = second control point's x-coordinate.
- `1` = second control point's y-coordinate.

Think of these values as handles that shape the animation's timing curve. They are not four duration values or four animation stages.

**Interview answer:** `cubic-bezier()` is a custom CSS timing function. It controls the acceleration and deceleration of transitions or animations by defining a cubic Bézier curve using four control-point coordinates.

---

## 6. Quick Interview Revision

| Question | Short answer |
|---|---|
| What is a media query? | A CSS rule that applies styles when a device or viewport condition matches. |
| What does `min-width` mean? | The condition matches at that width and above. |
| What does `max-width` mean? | The condition matches at that width and below. |
| Does `px` mean upper or lower limit in a media query? | No. `px` is the unit; `min-width` or `max-width` determines the comparison. |
| What is `em`? | A font-relative unit; for `font-size`, it is based on the parent's inherited font size. |
| What is `rem`? | A unit relative to the root element's computed font size. |
| What is `%`? | A percentage whose reference depends on the CSS property. |
| What is `vw`? | 1% of the viewport width. |
| What is `vh`? | 1% of the viewport height. |
| What is `:focus`? | Matches an element that currently has focus. |
| What is `:active`? | Matches an element while it is being activated. |
| What is `:focus-visible`? | Matches focus when the browser determines a visible focus indicator is appropriate. |
| What is `calc()`? | A CSS function for calculating property values using compatible units. |
| What is `cubic-bezier()`? | A custom timing function that controls animation or transition pacing. |

---

## 7. Common Interview Mistakes to Avoid

1. **Saying `px` always means one physical screen pixel.**  
   A CSS pixel is a reference unit and may map to multiple physical pixels.

2. **Saying `em` is always relative to the parent.**  
   For `font-size`, it is based on the parent's inherited font size. For many other properties, it is based on the element's own computed font size.

3. **Saying `%` is always relative to the parent's width.**  
   The reference depends on the property.

4. **Confusing `:focus` with `:active`.**  
   Focus can remain after interaction; active is generally temporary during activation.

5. **Assuming `max-width: 768px` means only below 768px.**  
   It also matches exactly 768px.

6. **Forgetting spaces around `+` and `-` in `calc()`.**  
   Write `calc(100% - 20px)`.

7. **Thinking `cubic-bezier()` controls animation duration.**  
   Duration is set separately with `transition-duration` or `animation-duration`; the Bézier function controls timing/progression.

---

## 8. Recommended Practice

Try these small exercises to check your understanding:

1. Write a media query that changes a card's background when the viewport is 600px or narrower.
2. Create a heading with `font-size: 2rem` and explain how its size changes if the root font size changes.
3. Create a button with different `:hover`, `:focus-visible`, and `:active` styles.
4. Make a content area whose width is `100% - 240px` using `calc()`.
5. Create a transition that uses `cubic-bezier()` and compare it with `ease-in-out`.

---

**End of CSS Interview Revision Notes**
