# 📐 CSS `corner-shape` Property

## 📌 Overview

The `corner-shape` property is part of the **CSS Borders and Box Decorations Module Level 4**.
It allows developers to control the **shape of element corners**, extending beyond the traditional `border-radius`.

While `border-radius` defines *how large* the corner curve is, `corner-shape` defines *how the corner is drawn*.

---

## 🎯 Key Concept

* `border-radius` → controls **size**
* `corner-shape` → controls **geometry/style**

---

## 🧱 Basic Syntax

```css
.element {
  border-radius: 20px;
  corner-shape: round;
}
```

---

## 🔄 Multiple Corner Values

You can define different shapes for each corner:

```css
.element {
  border-radius: 20px;
  corner-shape: round bevel notch squircle;
}
```

### Value Order

```
top-left | top-right | bottom-right | bottom-left
```

---

## 🔷 Supported Values

### 1. `round` (Default)

Standard rounded corners (same as current behavior).

```css
corner-shape: round;
```

---

### 2. `bevel`

Cuts the corner diagonally.

```css
corner-shape: bevel;
```

---

### 3. `notch`

Creates an inward cut at the corner.

```css
corner-shape: notch;
```

---

### 4. `squircle`

Smooth, superellipse-style corners (popular in modern UI like mobile apps).

```css
corner-shape: squircle;
```

---

## 💡 Example

```css
.card {
  width: 200px;
  height: 120px;
  background: teal;
  border-radius: 30px;
  corner-shape: squircle;
}
```

---

## ⚠️ Browser Support

🚧 **Experimental Feature**

* Not widely supported across browsers
* May require flags in some browsers
* Not recommended for production use yet

---

## 🔁 Fallback / Alternatives (Production Use)

Since `corner-shape` is not fully supported, use these alternatives:

### 🔹 Using `clip-path`

```css
.element {
  clip-path: polygon(
    10% 0%, 90% 0%, 100% 10%,
    100% 90%, 90% 100%,
    10% 100%, 0% 90%, 0% 10%
  );
}
```

---

### 🔹 Using SVG

* Create custom shapes
* Use `<clipPath>` or `<mask>`
* More control but slightly complex

---

## 🧠 When to Use (Future Scope)

Once supported, `corner-shape` will be useful for:

* Modern UI components (cards, buttons)
* Neumorphism design
* Custom design systems
* Reducing dependency on SVG and `clip-path`

---

## 📚 Summary

* `corner-shape` defines **how corners look**
* Works alongside `border-radius`
* Supports shapes like:

  * `round`
  * `bevel`
  * `notch`
  * `squircle`
* 🚧 Currently experimental → avoid in production