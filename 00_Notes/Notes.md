font-family = Arial
background-color = gray
padding = 20px
border-radius = 20px

font-weight = bold
font-size = 20px
color = blue

font-style = italic
margin-bottom = 20px
height = 30px

background-color = yellow
width = 225px
border = 1px solid yellow


=====================================================================================
* {
    font-family: Arial, sans-serif;
}

.highlight {
    background-color: yellow;
    color: red;
}

#unique {
    color: darkgreen;
    background-color: lightblue;
}

h2 {
    text-align: center;
    color: blue;
}

p {
    font-size: 18px;
    line-height: 1.5;
}
=====================================================================================
*{
    font-family: Arial, sans-serif;
    margin:0;
    padding:0;
}

.highlight{
    background-color: yellow;
    color: red;
    padding: 10px;
    margin:10px 0;
}

#unique{
    color: darkgreen;
    background-color: lightblue;
    padding: 15px;
    margin-top: 20px;
}

h2{
    text-align: center;
    color: blue;
    margin-bottom: 15px;
}

p{
    font-size: 18px;
    margin-bottom: 10px;
    padding: 5px;
}
=====================================================================================
Descendant Selector (parent child) – Targets all elements inside a specified parent.
Child Selector (parent > child) – Targets only the direct children of a specified parent.
Attribute Selector ([attribute="value"]) – Targets elements based on specific attributes.

/* 1️⃣ Descendant Selector: Selects ALL <p> inside .descendant (even deeply nested ones)  <div class="descendant"> */
.descendant p {
    color: blue;
    font-style: italic;
}

/* 2️⃣ Child Selector: Selects ONLY direct <p> children of .child 
*/
.child>p {
    color: red;
    font-weight: bold;
}


/* 3️⃣ Attribute Selector: Selects input elements with type="text" */
input[type="text"]{
    border: 2px solid green;
    padding: 5px;
}

/* Attribute Selector: Selects elements with data-type="special" <button data-type="special"> */
button[data-type="special"]{
    background-color: yellow;
    font-size: 18px;
}
=====================================================================================
Pseudo-classes – Special states of elements, like hover, focus, or first-child.
Pseudo-elements – Styling specific parts of an element, like first-letter or before/after content.

button:hover{
    background-color: lightblue;
}

input:focus{
    border: 2px solid red;
}

.container::first-letter{
    font-size: 2em;
    font-weight: bold;
}

.container::first-line{
    font-weight: bold;
}

.container::selection{
    background-color: yellow;
    color:black;
}
=====================================================================================
Grouping Selector (,) → Targets multiple elements with the same styles.
Adjacent Sibling Selector (+) → Targets the immediate next sibling element.
General Sibling Selector (~) → Targets all siblings after a specific element.
h1, h2{
    color: darkblue;
    text-align: center;
}

h1 + p {
    color: green;
    font-weight: bold;
}

h2~p {
    color: red;
}

button~span {
    font-size: 18px;
    color: purple;
}
=====================================================================================
1. Box Model
The CSS box model is a fundamental concept that describes how elements
are structured on a webpage. It consists of four main parts:
• Content: The actual text or image inside the element.
• Padding: Space between the content and the border.
• Border: The edge surrounding the padding (optional).
• Margin: Space between the element and surrounding elements.

Margin → Controls the space outside the element.
Padding → Controls the space inside the element, between content and border.
Border → Defines the outer boundary of an element.
Content → The actual content inside an element.
Box-Sizing → Determines how width and height are calculated (content-box vs. border-box).
Margin Collapse → Understand how adjacent margins interact.
=====================================================================================
Content Box
=====================================================================================
CSS Flexbox ::
Display → Enables flexbox by setting display: flex on a container.
Main Axis → The main axis is determined by flex-direction and defines the primary direction of content flow.
Cross Axis → The cross axis is perpendicular to the main axis and controls the secondary alignment.
Flex Direction → Defines the main axis (row, row-reverse, column, column-reverse).
Justify Content → Controls alignment along the main axis (flex-start, center, space-between, etc.).
Align Items → Aligns items along the cross axis (stretch, center, flex-start, etc.).
Flex Wrap → Defines whether items should wrap to a new line (nowrap, wrap, wrap-reverse).
Align Self → Adjusts alignment of a single item within the flex container.
Gap → Defines space between flex items.
Flex Grow, Shrink & Basis → Controls item size behavior within a flex container.

display: flex → Defines a flex container.
flex-direction → Determines the main axis direction (row or column).
justify-content → Aligns items along the main axis.
align-items → Aligns items along the cross axis.
align-content → Controls alignment for multiple flex lines.
flex-wrap → Determines if items should wrap.
gap → Controls spacing between items.
flex → A shorthand for flex-grow, flex-shrink, and flex-basis.
order → Defines the order of items in a flex container.
align-self → Allows individual items to override align-items.
=====================================================================================
CSS Grid ::
Display → Enables grid by setting display: grid or display: inline-grid on a container.
Grid Container & Grid Items → The parent element is the grid container, and its children are grid items.
Grid Template Columns & Rows → Defines the number and size of columns and rows (grid-template-columns, grid-template-rows).
Gap → Defines spacing between rows and columns (row-gap, column-gap, gap).
Grid Lines → Invisible lines dividing the grid into sections.
Tracks & Cells → The space between two grid lines (rows and columns).
Grid Cells: The intersection of a row and a column.
Grid Area → Defines a specific area in the grid using grid-area.
Justify & Align Content → Controls alignment of the entire grid within the container (justify-content, align-content).
Justify & Align Items → Controls alignment of individual items inside grid cells (justify-items, align-items).
Justify & Align Self → Adjusts alignment of a single item within its cell (justify-self, align-self).
Grid Auto Flow → Defines how items are placed in the grid (row, column, dense).
Auto-Fit & Auto-Fill → Helps in responsive design by adjusting grid tracks dynamically.
Fractional Units (fr) & Minmax → Allows flexible sizing of grid items (fr units, minmax() function).

display: grid → Defines a grid container.
grid-template-columns → Defines the number and size of columns.
grid-template-rows → Defines the number and size of rows.
gap → Controls the spacing between rows and columns.
justify-items → Aligns grid items along the inline axis.
align-items → Aligns grid items along the block axis.
place-items → A shorthand for justify-items and align-items.
grid-column → Controls how many columns an item spans.
grid-row → Controls how many rows an item spans.
=====================================================================================
display: block
display: inline
display: inline-block
display: none

You will focus on:
Block: Element takes the full width and starts on a new line.
Inline: Element takes only the necessary width and flows with text.
Inline-block: Behaves like inline but supports width and height.
=====================================================================================
Positioning Property
Static: Default. Element stays in the normal document flow.
Relative: Element is positioned relative to its normal position using top/right/bottom/left.
Absolute: Positioned relative to the nearest positioned ancestor. Removed from normal flow.
Fixed: Positioned relative to the viewport. Stays fixed during scroll.
Sticky: A hybrid of relative and fixed. Sticks at a defined position during scrolling.

Float Property
Float: left: Element floats to the left.
Float: right: Element floats to the right.
Float: none: Default. Element does not float.
=====================================================================================

=====================================================================================
=====================================================================================
=====================================================================================
=====================================================================================
=====================================================================================
=====================================================================================
=====================================================================================