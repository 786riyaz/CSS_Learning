# 📦 CSS PHASE 2 – BOX MODEL, DISPLAY & LAYOUT BASICS

![Image](https://media.gcflearnfree.org/content/5ef2084faaf0ac46dc9c10be_06_23_2020/box_model.png)

![Image](https://miro.medium.com/1%2AM1rrBjfUxoPNsda6s-V5MA.png)

![Image](https://i.sstatic.net/mGTYI.png)

![Image](https://miro.medium.com/1%2AAb2FsBXuCzEMsBdWnH7tjQ.png)

![Image](https://miro.medium.com/1%2AD0uqaxtdKymJZhYEz59rxg.gif)

---

## 1️⃣ CSS Box Model (CORE CONCEPT)

Every HTML element is a **box** made of:

```
+----------------------+
|      margin          |
|  +---------------+  |
|  |   border      |  |
|  |  +---------+  |  |
|  |  | padding |  |  |
|  |  | content |  |  |
|  |  +---------+  |  |
|  +---------------+  |
+----------------------+
```

### Box Model Parts

* **Content** → text / image
* **Padding** → space inside
* **Border** → outline
* **Margin** → space outside

---

## 2️⃣ Padding

```css
div {
  padding: 20px;
}
```

### Individual Sides

```css
padding-top: 10px;
padding-right: 15px;
padding-bottom: 10px;
padding-left: 15px;
```

### Shorthand

```css
padding: 10px 15px;
```

---

## 3️⃣ Margin

```css
div {
  margin: 20px;
}
```

### Auto Centering (IMPORTANT)

```css
div {
  width: 300px;
  margin: 0 auto;
}
```

📌 `auto` centers horizontally.

---

## 4️⃣ Border

```css
div {
  border: 2px solid black;
}
```

---

## 5️⃣ Width & Height

```css
div {
  width: 200px;
  height: 100px;
}
```

⚠️ Width does NOT include padding & border (by default).

---

## 6️⃣ `box-sizing` (VERY IMPORTANT)

### Default (content-box)

```css
box-sizing: content-box;
```

### Best Practice

```css
* {
  box-sizing: border-box;
}
```

📌 `border-box` includes padding & border in width.

---

## 7️⃣ Display Property

### block

```css
div {
  display: block;
}
```

* Full width
* New line

### inline

```css
span {
  display: inline;
}
```

* No width/height
* Same line

### inline-block

```css
div {
  display: inline-block;
}
```

* Width + height allowed
* Same line

---

## 8️⃣ `display: none` vs `visibility: hidden`

```css
display: none;       /* removed from layout */
visibility: hidden;  /* space remains */
```

---

## 9️⃣ Overflow

```css
div {
  overflow: hidden;
}
```

Values:

* `hidden`
* `scroll`
* `auto`

---

## 🔟 Margin Collapse (INTERVIEW FAVORITE)

```css
p {
  margin: 20px;
}
```

Vertical margins **collapse**, horizontal do not.

📌 Only affects **block elements**

---

## 1️⃣1️⃣ Practical Example (Card)

```css
.card {
  width: 300px;
  padding: 16px;
  border: 1px solid #ccc;
  margin: 20px auto;
  box-sizing: border-box;
}
```

---

## 🧪 Practice Tasks (MANDATORY)

### Task 1

Create **3 cards**:

* Equal width
* Padding inside
* Space between cards

### Task 2

Test:

* `display: none`
* `visibility: hidden`

---

## ✅ Phase 2 Completion Checklist

✔ Box model
✔ Padding & margin
✔ Border
✔ box-sizing
✔ Display types
✔ Overflow
