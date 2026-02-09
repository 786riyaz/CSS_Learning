# 🎨 CSS PHASE 1 – BASICS & STYLING (COMPLETE GUIDE)

![Image](https://www.w3schools.com/css/img_selector.gif)

![Image](https://www.bitdegree.org/learn/storage/media/images/8c4493d3-110c-4a95-8b70-7626ce2d2f4e.o.jpg)

![Image](https://developer.chrome.com/static/docs/css-ui/high-definition-css-color-guide/image/two-tables-color-are-sid-d7829619631b7.png)

![Image](https://tutorials.freshersnow.com/css/css-colors/attachment/css-color-1/)

![Image](https://marksheet.io/images/hsl-model.png)

---

## 1️⃣ What is CSS?

**CSS (Cascading Style Sheets)** is used to:

* Control **layout**
* Apply **colors**
* Set **fonts**
* Add **spacing**
* Make websites visually appealing

📌 HTML = structure
📌 CSS = presentation

---

## 2️⃣ CSS Syntax (VERY IMPORTANT)

```css
selector {
  property: value;
}
```

### Example

```css
p {
  color: red;
  font-size: 16px;
}
```

* `p` → selector
* `color` → property
* `red` → value

---

## 3️⃣ Ways to Apply CSS

### 1. Inline CSS ❌ (Avoid)

```html
<p style="color:red">Text</p>
```

### 2. Internal CSS ⚠️

```html
<style>
  p { color: blue; }
</style>
```

### 3. External CSS ✅ (BEST PRACTICE)

**HTML**

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

---

## 4️⃣ CSS Selectors (Core Concept)

### Element Selector

```css
p { color: red; }
```

### Class Selector

```css
.card { border: 1px solid black; }
```

HTML:

```html
<div class="card"></div>
```

### ID Selector

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

---

## 5️⃣ Colors in CSS

### Named Colors

```css
color: red;
```

### Hex

```css
color: #ff0000;
```

### RGB

```css
color: rgb(255, 0, 0);
```

### RGBA (with opacity)

```css
color: rgba(255, 0, 0, 0.5);
```

---

## 6️⃣ Units in CSS

### Absolute

* `px`

### Relative (IMPORTANT)

* `%`
* `em`
* `rem`

📌 Interview tip:

> `rem` is relative to root (`html`) font size.

Example:

```css
p {
  font-size: 1rem;
}
```

---

## 7️⃣ Text Styling

```css
p {
  font-size: 16px;
  font-weight: 400;
  font-family: Arial, sans-serif;
  text-align: center;
  line-height: 1.5;
}
```

### Common Properties

* `font-size`
* `font-weight`
* `font-family`
* `text-align`
* `line-height`
* `text-transform`

---

## 8️⃣ Background Properties

### Background Color

```css
div {
  background-color: lightblue;
}
```

### Background Image

```css
div {
  background-image: url("bg.jpg");
  background-size: cover;
  background-position: center;
}
```

---

## 9️⃣ Borders

```css
div {
  border: 2px solid black;
  border-radius: 8px;
}
```

✔ `solid`, `dashed`, `dotted`
✔ Rounded corners with `border-radius`

---

## 🔟 Comments in CSS

```css
/* This is a comment */
```

---

## 1️⃣1️⃣ CSS Reset (Intro)

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

---

## 🧪 Practice Tasks (MANDATORY)

### Task 1

Create:

* `index.html`
* `style.css`

Style:
✔ Heading color
✔ Paragraph font
✔ Background color
✔ Border on div

---

### Task 2

Create a **profile card**:

* Name
* Description
* Border
* Background
* Center text

---

## ✅ Phase 1 Completion Checklist

✔ CSS syntax
✔ External CSS
✔ Selectors
✔ Colors & units
✔ Text styling
✔ Background & borders
