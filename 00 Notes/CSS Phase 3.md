# 📐 CSS PHASE 3 – POSITIONING & FLEXBOX

![Image](https://dillionmegida.com/post-covers/86-positioning-styles.png)

![Image](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Positioned_layout/Stacking_context/Example_1/understanding_zindex_05a.png)

![Image](https://web.dev/static/learn/css/flexbox/image/a-labelled-diagram-the-a-a9bf061b5d5b2.svg)

![Image](https://dev-to-uploads.s3.amazonaws.com/i/hy2oqjvsbk60ef92nktg.png)

![Image](https://www.tutorialspoint.com/css/images/flexbox.png)

---

## 1️⃣ CSS Positioning (CORE CONCEPT)

### Default Position

```css
position: static;
```

* Default for all elements
* `top`, `left` don’t work

---

## 2️⃣ `position: relative`

```css
.box {
  position: relative;
  top: 10px;
  left: 20px;
}
```

📌 Moves **relative to itself**
📌 Creates reference for `absolute` children

---

## 3️⃣ `position: absolute`

```css
.child {
  position: absolute;
  top: 0;
  right: 0;
}
```

📌 Positioned relative to **nearest positioned ancestor**
📌 Removed from normal document flow

---

## 4️⃣ `position: fixed`

```css
.header {
  position: fixed;
  top: 0;
}
```

📌 Stays fixed on scroll
📌 Relative to viewport

---

## 5️⃣ `position: sticky`

```css
.nav {
  position: sticky;
  top: 0;
}
```

📌 Acts like relative → fixed on scroll
📌 Needs a `top` value

---

## 6️⃣ `z-index` (Stacking Order)

```css
.box1 { z-index: 1; }
.box2 { z-index: 10; }
```

Rules:

* Works only on positioned elements
* Higher number = on top

---

## 7️⃣ Common Positioning Mistake

❌ Expecting `absolute` to work without parent positioned

✅ Correct:

```css
.parent { position: relative; }
.child  { position: absolute; }
```

---

# 🔥 FLEXBOX (MOST IMPORTANT PART)

---

## 8️⃣ What is Flexbox?

Flexbox is a **1-D layout system**:

* Row OR column
* Perfect for navbars, cards, alignment

---

## 9️⃣ Flex Container

```css
.container {
  display: flex;
}
```

📌 Parent becomes flex container
📌 Children become flex items

---

## 🔟 Main Axis vs Cross Axis

* `flex-direction: row` → main axis = horizontal
* `flex-direction: column` → main axis = vertical

---

## 1️⃣1️⃣ `justify-content` (Main Axis)

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

## 1️⃣2️⃣ `align-items` (Cross Axis)

```css
align-items: center;
```

Values:

* `stretch`
* `center`
* `flex-start`
* `flex-end`

---

## 1️⃣3️⃣ `flex-direction`

```css
flex-direction: row;
flex-direction: column;
```

---

## 1️⃣4️⃣ `gap` (Spacing Between Items)

```css
.container {
  gap: 16px;
}
```

---

## 1️⃣5️⃣ Flex Item Properties

### `flex-grow`

```css
.item {
  flex-grow: 1;
}
```

### `flex-shrink`

```css
.item {
  flex-shrink: 0;
}
```

### `flex-basis`

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

## 1️⃣6️⃣ Perfect Centering (INTERVIEW GOLD)

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

---

## 1️⃣7️⃣ Navbar Example (Real World)

```css
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

---

## 🧪 Practice Tasks (MANDATORY)

### Task 1

Create a **sticky navbar**:

* Logo left
* Menu right

### Task 2

Create **3 cards** using Flexbox:

* Equal height
* Space between

---

## ✅ Phase 3 Completion Checklist

✔ Position types
✔ z-index
✔ Flexbox basics
✔ Axis understanding
✔ Centering
