# CSS Basics

> Important concepts + organized reference.

---

## 1. What is CSS?

CSS (Cascading Style Sheets) is used to **style and design HTML elements**.

CSS controls:

* Colors
* Fonts
* Spacing
* Borders
* Sizes
* Backgrounds
* Layout
* Responsive design

Example:

```html
<h1 class="title">Hello CSS</h1>
```

```css
.title {
    color: blue;
    font-size: 32px;
}
```

---

## 2. CSS Syntax

Basic CSS syntax:

```css
selector {
    property: value;
}
```

Example:

```css
h1 {
    color: blue;
    font-size: 32px;
}
```

* `h1` → selector
* `color` → property
* `blue` → value

---

## 3. Adding CSS to HTML

### Inline CSS

CSS directly inside an HTML element.

```html
<p style="color: red;">
    Hello
</p>
```

Useful for quick testing, but generally avoid for larger projects.

---

### Internal CSS

CSS inside the `<style>` element.

```html
<style>

    p {
        color: blue;
    }

</style>
```

---

### External CSS

CSS stored in a separate `.css` file.

HTML:

```html
<link
    rel="stylesheet"
    href="style.css"
>
```

CSS:

```css
p {
    color: blue;
}
```

### Recommended

For real projects, **external CSS** is generally preferred because it keeps HTML and CSS separate and easier to maintain.

---

## 4. CSS Comments

CSS comments are written using:

```css
/* This is a CSS comment */
```

Example:

```css
/* Main heading */

h1 {
    color: blue;
}
```

---

## 5. Colors

CSS supports different ways to define colors.

### Named Color

```css
color: red;
```

### HEX

```css
color: #ff0000;
```

### RGB

```css
color: rgb(255, 0, 0);
```

### RGBA

```css
color: rgba(255, 0, 0, 0.5);
```

### HSL

```css
color: hsl(0, 100%, 50%);
```

---

## 6. Background

### Background Color

```css
body {
    background-color: #f5f5f5;
}
```

### Background Image

```css
.hero {
    background-image: url("image.jpg");
}
```

### Background Size

```css
.hero {
    background-size: cover;
}
```

### Background Position

```css
.hero {
    background-position: center;
}
```

---

## 7. Text Styling

### Text Color

```css
p {
    color: #333;
}
```

### Text Alignment

```css
h1 {
    text-align: center;
}
```

Values:

```text
left
center
right
justify
```

### Text Decoration

```css
a {
    text-decoration: none;
}
```

### Text Transform

```css
h1 {
    text-transform: uppercase;
}
```

Values:

```text
uppercase
lowercase
capitalize
```

---

## 8. Fonts

### Font Family

```css
body {
    font-family: Arial, sans-serif;
}
```

### Font Size

```css
h1 {
    font-size: 40px;
}
```

### Font Weight

```css
h1 {
    font-weight: 700;
}
```

Common values:

```text
400 → normal
500 → medium
600 → semi-bold
700 → bold
```

### Font Style

```css
em {
    font-style: italic;
}
```

---

## 9. Units

### Absolute Unit

```css
width: 300px;
```

Common absolute unit:

```text
px
```

### Relative Units

```text
%
em
rem
vw
vh
```

Example:

```css
.container {
    width: 80%;
}

.title {
    font-size: 2rem;
}
```

---

## 10. Width and Height

```css
.box {
    width: 300px;
    height: 200px;
}
```

Maximum and minimum sizes:

```css
.box {
    max-width: 1000px;
    min-height: 200px;
}
```

---

## 11. Border

Basic border:

```css
.box {
    border: 1px solid black;
}
```

Individual properties:

```css
.box {
    border-width: 1px;
    border-style: solid;
    border-color: black;
}
```

---

## 12. Border Radius

Used to create rounded corners.

```css
.card {
    border-radius: 12px;
}
```

Circle:

```css
.avatar {
    border-radius: 50%;
}
```

---

## 13. Box Shadow

Creates a shadow around an element.

```css
.card {
    box-shadow:
        0 5px 20px rgba(0, 0, 0, 0.2);
}
```

Basic structure:

```text
horizontal
vertical
blur
spread
color
```

---

## 14. Opacity

Controls transparency.

```css
.image {
    opacity: 0.5;
}
```

Range:

```text
0   → completely transparent
1   → completely visible
```

---

## 15. CSS Variables

CSS variables allow reusable values.

```css
:root {
    --primary-color: #2563eb;
    --spacing: 20px;
}
```

Use them:

```css
button {
    background-color: var(--primary-color);
    padding: var(--spacing);
}
```

---

## 16. Basic Display Property

### Block

```css
div {
    display: block;
}
```

### Inline

```css
span {
    display: inline;
}
```

### Inline Block

```css
button {
    display: inline-block;
}
```

### None

```css
.hidden {
    display: none;
}
```

---

## 17. Visibility

```css
.box {
    visibility: hidden;
}
```

Difference:

```text
display: none
→ Element is removed from the layout.

visibility: hidden
→ Element is hidden but its space remains.
```

---

## 18. Cursor

Changes the mouse cursor.

```css
button {
    cursor: pointer;
}
```

Common values:

```text
pointer
default
not-allowed
grab
text
```

---

## 19. Overflow

Controls content that exceeds an element's dimensions.

```css
.box {
    overflow: hidden;
}
```

Common values:

```text
visible
hidden
scroll
auto
```

---

## 20. CSS Pseudo-Classes

Pseudo-classes represent a specific state of an element.

### Hover

```css
button:hover {
    background-color: black;
    color: white;
}
```

### Focus

```css
input:focus {
    border-color: blue;
}
```

### First Child

```css
li:first-child {
    color: red;
}
```

### Last Child

```css
li:last-child {
    color: blue;
}
```

---

## 21. CSS Pseudo-Elements

Pseudo-elements style a specific part of an element.

### `::before`

```css
.title::before {
    content: "→ ";
}
```

### `::after`

```css
.title::after {
    content: " ✓";
}
```

Common pseudo-elements:

```text
::before
::after
::first-letter
::first-line
::selection
```

---

## 22. CSS Specificity

When multiple CSS rules target the same element, specificity determines which rule has higher priority.

General order:

```text
Inline styles
    ↓
ID selector
    ↓
Class / attribute / pseudo-class
    ↓
Element selector
```

Example:

```css
p {
    color: blue;
}

.text {
    color: green;
}

#title {
    color: red;
}
```

The ID selector has higher specificity than the class and element selector.

---

## 23. The `!important` Rule

```css
.title {
    color: red !important;
}
```

`!important` increases the priority of a declaration.

Use it carefully. Avoid using it as a normal way to solve CSS conflicts.

---

## 24. Shorthand Properties

CSS provides shorthand properties to write related values more efficiently.

### Margin

```css
.box {
    margin: 10px 20px;
}
```

### Padding

```css
.box {
    padding: 10px 20px;
}
```

### Border

```css
.box {
    border: 1px solid black;
}
```

---

## 25. Basic CSS Reset

A simple reset:

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

This removes default margin and padding and makes sizing easier to manage.

---

## 26. `box-sizing`

### Content Box

```css
box-sizing: content-box;
```

Default behavior.

### Border Box

```css
box-sizing: border-box;
```

With `border-box`, the declared width and height include padding and border.

Common global setup:

```css
* {
    box-sizing: border-box;
}
```

---

## 27. CSS Cascade

CSS stands for **Cascading Style Sheets**.

When multiple rules apply, the browser considers:

```text
1. Importance
2. Specificity
3. Source order
```

Example:

```css
p {
    color: blue;
}

p {
    color: red;
}
```

The later rule wins when specificity and importance are equal.

---

## 28. Practical Example

### HTML

```html
<div class="card">

    <h2>JavaScript Project</h2>

    <p>
        A practical JavaScript project.
    </p>

    <button>
        View Project
    </button>

</div>
```

### CSS

```css
.card {
    width: 300px;
    padding: 20px;
    border-radius: 12px;
    background-color: white;
    box-shadow:
        0 5px 20px rgba(0, 0, 0, 0.15);
}

.card h2 {
    margin-bottom: 10px;
}

.card p {
    color: #666;
    margin-bottom: 15px;
}

.card button {
    padding: 10px 16px;
    border: none;
    border-radius: 8px;
    cursor: pointer;
}

.card button:hover {
    transform: translateY(-2px);
}
```

---

# Quick Reference

| Concept         | Main Property / Feature                 |
| --------------- | --------------------------------------- |
| Color           | `color`                                 |
| Background      | `background`                            |
| Text            | `font`, `text-align`, `text-decoration` |
| Size            | `width`, `height`                       |
| Spacing         | `margin`, `padding`                     |
| Border          | `border`                                |
| Rounded corners | `border-radius`                         |
| Shadow          | `box-shadow`                            |
| Transparency    | `opacity`                               |
| Layout          | `display`                               |
| Overflow        | `overflow`                              |
| Cursor          | `cursor`                                |
| State           | `:hover`, `:focus`                      |
| Pseudo-element  | `::before`, `::after`                   |
| Variables       | `--variable`, `var()`                   |
| Box sizing      | `box-sizing`                            |
| Priority        | specificity + cascade                   |

---

# Key Takeaways

```text
1. CSS controls the presentation of HTML.
2. Learn selector → property → value.
3. Prefer external CSS for projects.
4. Understand units and sizing.
5. Understand margin, padding and borders.
6. Understand box-sizing.
7. Learn display and overflow.
8. Understand pseudo-classes and pseudo-elements.
9. Understand specificity and cascade.
10. Use reusable CSS variables.
```
