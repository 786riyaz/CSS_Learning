# 🏆 CSS PHASE 6 – EXPERT CSS & REAL-WORLD PATTERNS

![Image](https://www.teaching-materials.org/_deprecated/css3-selectors/images/exercise_tables.png)

![Image](https://ishadeed.com/assets/comparison-css/css-clamp-1.jpg)

![Image](https://developer.mozilla.org/en-US/blog/getting-started-with-css-container-queries/container-queries-01.webp)

![Image](https://ishadeed.com/assets/container-queries-chrome/container-queries-vs-media-queries.png)

![Image](https://developer.mozilla.org/en-US/blog/getting-started-with-css-container-queries/container-queries-03.webp)

---

## 1️⃣ Advanced Selectors (Power Tools)

### Attribute Selectors

```css
input[type="text"] {
  border: 1px solid #333;
}
```

### Starts / Ends / Contains

```css
a[href^="https"] { color: green; }
a[href$=".pdf"] { color: red; }
a[href*="blog"] { font-weight: bold; }
```

---

## 2️⃣ `:not()` and `:is()`

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

## 3️⃣ `clamp()` – Responsive Without Media Queries

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

## 4️⃣ `min()` & `max()`

```css
.container {
  width: min(100%, 1200px);
}
```

📌 Prevents overflow on large screens

---

## 5️⃣ Container Queries (Modern CSS – Conceptual)

```css
@container (min-width: 400px) {
  .card {
    flex-direction: row;
  }
}
```

📌 Styles based on **container size**, not viewport
📌 New but powerful

---

## 6️⃣ Custom Scrollbars

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

## 7️⃣ Print Styles

```css
@media print {
  nav, footer {
    display: none;
  }
}
```

📌 Used for invoices, reports

---

## 8️⃣ CSS Architecture (REAL WORLD)

### Folder Structure

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

## 9️⃣ Common CSS Anti-Patterns

❌ Overusing `!important`
❌ Deep nested selectors
❌ Inline styles
❌ Fixed widths everywhere

---

## 🔟 Interview-Level Knowledge

Be ready to explain:

* Flexbox vs Grid
* Box model
* Specificity
* Mobile-first
* BEM
* clamp() use case

---

## 🧪 FINAL PROJECT (MANDATORY)

### Build a **Portfolio Website (HTML + CSS ONLY)**

Must include:
✔ Semantic HTML
✔ Flexbox + Grid
✔ Responsive layout
✔ Animations
✔ CSS variables
✔ Dark mode
✔ Print styles

---

## 🏁 FINAL CHECKLIST

✔ HTML (Phase 1–4)
✔ CSS (Phase 1–6)
✔ No frameworks
✔ Real-world skills