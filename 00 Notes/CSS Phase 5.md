# 🎨 CSS PHASE 5 – ADVANCED CSS (PROFESSIONAL SKILLS)

![Image](https://cdn.hashnode.com/res/hashnode/image/upload/v1630473155776/24_trQvtU.png)

![Image](https://i.sstatic.net/tSAXe.png)

![Image](https://codesweetly.com/_astro/css-animation-keyframes-illustration-codesweetly.DJm5xquz_Zl5i11.webp)

![Image](https://www.simplilearn.com/ice9/free_resources_article_thumb/keyframes-4.JPG)

![Image](https://miro.medium.com/1%2A4PrzhDebf80SQgygCIVNIw.gif)

---

## 1️⃣ Pseudo-Classes (User Interaction)

Used to style elements based on **state**.

```css
button:hover {
  background: blue;
}
```

Common pseudo-classes:

* `:hover`
* `:focus`
* `:active`
* `:visited`
* `:checked`
* `:disabled`

📌 Accessibility tip:
Always style `:focus` for keyboard users.

---

## 2️⃣ Pseudo-Elements (Virtual Elements)

Used to style **parts of elements**.

```css
p::first-letter {
  font-size: 32px;
}
```

Common ones:

* `::before`
* `::after`
* `::first-letter`
* `::first-line`

### Example

```css
.button::after {
  content: "→";
}
```

---

## 3️⃣ CSS Transitions (Smooth Effects)

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

## 4️⃣ CSS Animations (`@keyframes`)

```css
@keyframes fadeIn {
  from { opacity: 0; }
  to   { opacity: 1; }
}

.box {
  animation: fadeIn 1s ease;
}
```

📌 Use animations **sparingly**

---

## 5️⃣ CSS Variables (Custom Properties)

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

## 6️⃣ Dark Mode (CSS Only)

```css
@media (prefers-color-scheme: dark) {
  body {
    background: #111;
    color: #fff;
  }
}
```

---

## 7️⃣ CSS Specificity (INTERVIEW FAVORITE)

Specificity order:

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

## 8️⃣ Cascade & Inheritance

* Later rules override earlier ones
* Some properties inherit (`color`, `font`)
* Some don’t (`margin`, `padding`)

---

## 9️⃣ BEM Methodology (VERY IMPORTANT)

**Block__Element--Modifier**

```css
.card {}
.card__title {}
.card--active {}
```

✔ Scalable
✔ Team-friendly

---

## 🔟 Performance Best Practices

✔ Avoid deep selectors
✔ Avoid `!important`
✔ Reuse classes
✔ Use CSS variables

---

## 🧪 Practice Tasks (MANDATORY)

### Task 1

Create an **animated button**:

* Hover animation
* Pseudo-element arrow

### Task 2

Implement **dark mode** using CSS variables

---

## ✅ Phase 5 Completion Checklist

✔ Pseudo-classes
✔ Pseudo-elements
✔ Transitions
✔ Animations
✔ Variables
✔ Specificity
✔ BEM