Below is your **complete, structured, and corrected CSS Properties Revision Notes** in proper Markdown format.

You can save this file as:

```
css-properties-revision.md
```

---

# 🎨 CSS Properties – Complete Revision Notes

---

# 1️⃣ Visibility

```css
visibility: visible;
visibility: hidden;
visibility: collapse;   /* for table rows/columns */
```

* `visible` → Element is visible (default)
* `hidden` → Element hidden but space is preserved
* `collapse` → Used mainly in tables

---

# 2️⃣ Text Alignment

```css
text-align: left;
text-align: right;
text-align: center;
text-align: justify;
text-align: start;
text-align: end;
```

---

# 3️⃣ Background

### Background Color

```css
background-color: red;
background-color: #ff0000;
background-color: rgb(255,0,0);
background-color: rgba(255,0,0,0.5);
background-color: hsl(0,100%,50%);
```

### Background Image

```css
background-image: url("image.png");
background-repeat: repeat;
background-repeat: no-repeat;
background-repeat: repeat-x;
background-repeat: repeat-y;

background-size: auto;
background-size: cover;
background-size: contain;

background-position: left;
background-position: right;
background-position: center;
background-position: top;
background-position: bottom;

background-attachment: scroll;
background-attachment: fixed;
background-attachment: local;

background: red url("image.png") no-repeat center/cover;
```

---

# 4️⃣ Dimensions

```css
width: 50px;
height: 40px;

min-width: 100px;
max-width: 500px;

min-height: 100px;
max-height: 500px;
```

Units:

* px
* %
* em
* rem
* vw
* vh
* vmin
* vmax
* auto

---

# 5️⃣ Text Decoration

```css
text-decoration: underline;
text-decoration: overline;
text-decoration: line-through;
text-decoration: none;

text-decoration-style: solid;
text-decoration-style: double;
text-decoration-style: dotted;
text-decoration-style: dashed;
text-decoration-style: wavy;

text-decoration-color: red;
text-decoration-thickness: 2px;

text-decoration: underline dashed red 2px;
```

---

# 6️⃣ Text Transform

```css
text-transform: uppercase;
text-transform: lowercase;
text-transform: capitalize;
text-transform: none;
```

---

# 7️⃣ Line Height

```css
line-height: normal;
line-height: 30px;
line-height: 1.5;
```

---

# 8️⃣ Font Properties

```css
font-size: 16px;
font-size: small;
font-size: medium;
font-size: large;
font-size: x-large;

font-weight: normal;
font-weight: bold;
font-weight: 100; /* thin */
font-weight: 900; /* black */

font-style: normal;
font-style: italic;
font-style: oblique;

font-family: 'Dancing Script', cursive;
font-family: Arial, Helvetica, sans-serif;

font-variant: normal;
font-variant: small-caps;

font: italic bold 16px/1.5 Arial, sans-serif;
```

---

# 9️⃣ Display

```css
display: none;
display: block;
display: inline;
display: inline-block;
display: flex;
display: grid;
display: table;
display: table-row;
display: table-cell;
display: contents;
```

---

# 🔟 Position

```css
position: static;
position: relative;
position: absolute;
position: fixed;
position: sticky;
```

Offset properties:

```css
top: 20px;
left: 90px;
right: 10px;
bottom: 5px;
```

---

# 1️⃣1️⃣ Z-Index

```css
z-index: auto;
z-index: 1;
z-index: 99;
z-index: 999;
```

---

# 1️⃣2️⃣ Float & Clear

```css
float: left;
float: right;
float: none;

clear: left;
clear: right;
clear: both;
clear: none;
```

---

# 1️⃣3️⃣ Margin

```css
margin: 5px;
margin: 10px 20px;
margin: 10px 20px 30px 40px;

margin-top: 10px;
margin-right: 20px;
margin-bottom: 30px;
margin-left: 40px;

margin: auto;
```

---

# 1️⃣4️⃣ Padding

```css
padding: 5px;
padding: 10px 20px;
padding: 10px 20px 30px 40px;

padding-top: 10px;
padding-right: 20px;
padding-bottom: 30px;
padding-left: 40px;
```

---

# 1️⃣5️⃣ Border

```css
border: 1px solid black;

border-width: 2px;
border-style: solid;
border-style: dashed;
border-style: dotted;
border-style: double;
border-style: groove;
border-style: ridge;
border-style: inset;
border-style: outset;
border-style: none;

border-color: red;

border-radius: 10px;
border-radius: 50%;
```

---

# 1️⃣6️⃣ Flexbox

```css
display: flex;

flex-direction: row;
flex-direction: column;
flex-direction: row-reverse;
flex-direction: column-reverse;

justify-content: flex-start;
justify-content: flex-end;
justify-content: center;
justify-content: space-between;
justify-content: space-around;
justify-content: space-evenly;

align-items: stretch;
align-items: flex-start;
align-items: flex-end;
align-items: center;
align-items: baseline;

flex-wrap: nowrap;
flex-wrap: wrap;
flex-wrap: wrap-reverse;

align-content: center;

flex-grow: 1;
flex-shrink: 4;
flex-basis: 100px;

order: 1;

flex: 1 1 auto;
```

---

# 1️⃣7️⃣ Grid

```css
display: grid;

grid-template-columns: 50px 50px;
grid-template-columns: repeat(3, 1fr);

grid-template-rows: 50px 50px;

grid-column: 1 / 2;
grid-column: span 2;

grid-row: 1 / 2;

gap: 10px;
row-gap: 10px;
column-gap: 10px;

place-items: center;
place-content: center;
```

---

# 1️⃣8️⃣ Transition

```css
transition-property: all;
transition-duration: 1s;
transition-timing-function: ease;
transition-timing-function: ease-in;
transition-timing-function: ease-out;
transition-timing-function: ease-in-out;
transition-timing-function: linear;
transition-delay: 1s;

transition: all 1s ease-in-out 0s;
```

---

# 1️⃣9️⃣ Transform

```css
transform: rotate(45deg);
transform: rotateX(45deg);
transform: rotateY(180deg);
transform: rotateZ(180deg);

transform: scale(2);
transform: scaleX(5);
transform: scaleY(5);

transform: translate(50px);
transform: translateX(50px);
transform: translateY(50px);

transform: skew(20deg);
transform: skewX(20deg);
transform: skewY(20deg);

transform: matrix(1,0,0,1,0,0);
```

---

# 2️⃣0️⃣ Animation

```css
animation-name: rotation;
animation-duration: 4s;
animation-timing-function: ease;
animation-delay: 0s;
animation-iteration-count: 4;
animation-iteration-count: infinite;
animation-direction: normal;
animation-direction: alternate;
animation-direction: alternate-reverse;
animation-direction: reverse;
animation-fill-mode: forwards;
animation-fill-mode: backwards;
animation-play-state: running;
animation-play-state: paused;

animation: rotation 4s ease-in-out 0s infinite alternate;
```

### Keyframes (Correct Syntax)

```css
@keyframes rotation {
  0%   { left: 10px; }
  50%  { left: 50px; }
  60%  { left: 140px; }
  100% { left: 200px; }
}
```

---

# 2️⃣1️⃣ Overflow

```css
overflow: visible;
overflow: hidden;
overflow: scroll;
overflow: auto;

overflow-x: hidden;
overflow-y: scroll;
```

---

# 2️⃣2️⃣ Opacity

```css
opacity: 0;
opacity: 0.5;
opacity: 1;
```

---

# 2️⃣3️⃣ Cursor

```css
cursor: pointer;
cursor: default;
cursor: not-allowed;
cursor: text;
cursor: move;
cursor: grab;
cursor: crosshair;
```

---

# 2️⃣4️⃣ Box Shadow

```css
box-shadow: 5px 5px 10px gray;
box-shadow: inset 5px 5px 10px gray;
```

---

# 2️⃣5️⃣ Text Shadow

```css
text-shadow: 2px 2px 5px gray;
```

---

# 2️⃣6️⃣ List Style

```css
list-style-type: disc;
list-style-type: circle;
list-style-type: square;
list-style-type: none;

list-style-position: inside;
list-style-position: outside;

list-style: square inside;
```

---

# 2️⃣7️⃣ Object Fit

```css
object-fit: fill;
object-fit: contain;
object-fit: cover;
object-fit: none;
object-fit: scale-down;
```

---

# 2️⃣8️⃣ Important Rule

```css
color: red !important;
```

---

# 📌 Extra Important Concepts

* Box Model
* Specificity
* Inheritance
* Units (px, %, em, rem, vh, vw)
* Pseudo-classes (`:hover`, `:active`, `:focus`)
* Pseudo-elements (`::before`, `::after`)
* Media Queries
* CSS Variables (`--primary-color`)

---
