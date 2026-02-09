# 📱 CSS PHASE 4 – GRID & RESPONSIVE DESIGN

![Image](https://www.freecodecamp.org/news/content/images/2022/05/CSS-GRID-3.png)

![Image](https://ishadeed.com/assets/grid-area/grid-areas-0.png)

![Image](https://www.seobility.net/en/wiki/images/6/6f/Media-Queries.png)

![Image](https://miro.medium.com/v2/resize%3Afit%3A1400/1%2AwbzR91Dii_SN9_GBEKeg1Q.png)

![Image](https://www.freecodecamp.org/news/content/images/2021/05/image-56.png)

---

## 1️⃣ What is CSS Grid?

CSS Grid is a **2-dimensional layout system**:

* Rows **and** columns
* Best for full-page layouts

📌 Flexbox = 1D
📌 Grid = 2D

---

## 2️⃣ Creating a Grid Container

```css
.container {
  display: grid;
}
```

---

## 3️⃣ Defining Columns & Rows

```css
.container {
  grid-template-columns: 200px 1fr 200px;
  grid-template-rows: auto 1fr auto;
}
```

📌 `fr` = fractional unit (remaining space)

---

## 4️⃣ Grid Gap

```css
.container {
  gap: 20px;
}
```

---

## 5️⃣ Placing Items Using Line Numbers

```css
.item {
  grid-column: 1 / 3;
  grid-row: 1 / 2;
}
```

---

## 6️⃣ Grid Template Areas (VERY IMPORTANT)

### CSS

```css
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar content"
    "footer footer";
}
```

### Assign Areas

```css
.header { grid-area: header; }
.sidebar { grid-area: sidebar; }
.content { grid-area: content; }
.footer { grid-area: footer; }
```

📌 Best for page layouts

---

## 7️⃣ Auto-Fit & Auto-Fill

```css
.container {
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}
```

📌 Creates responsive grids automatically

---

## 8️⃣ Responsive Design Basics

Responsive design = works on:

* Mobile
* Tablet
* Desktop

---

## 9️⃣ Media Queries

```css
@media (max-width: 768px) {
  body {
    background: lightgray;
  }
}
```

📌 Apply CSS based on screen size

---

## 🔟 Mobile-First Approach (INTERVIEW FAVORITE)

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

## 1️⃣1️⃣ Viewport Units

```css
height: 100vh;
width: 100vw;
```

Units:

* `vw` → viewport width
* `vh` → viewport height

---

## 1️⃣2️⃣ Responsive Images (CSS)

```css
img {
  max-width: 100%;
  height: auto;
}
```

---

## 1️⃣3️⃣ When to Use Grid vs Flexbox?

| Use Case    | Best    |
| ----------- | ------- |
| Navbar      | Flexbox |
| Cards row   | Flexbox |
| Page layout | Grid    |
| Dashboard   | Grid    |

---

## 🧪 Practice Tasks (MANDATORY)

### Task 1

Create a **page layout** using Grid:

* Header
* Sidebar
* Content
* Footer

### Task 2

Make it **responsive**:

* Sidebar below content on mobile

---

## ✅ Phase 4 Completion Checklist

✔ Grid fundamentals
✔ Template areas
✔ Responsive layout
✔ Media queries
✔ Mobile-first
