# CSS Selectors

> Important concepts + organized reference.

---

## 1. What is a CSS Selector?

A selector tells CSS **which HTML elements should receive the styles**.

Basic structure:

```css
selector {
    property: value;
}
```

Example:

```css
h1 {
    color: blue;
}
```

Here:

```text
h1 → selector
color → property
blue → value
```

---

## 2. Universal Selector

Selects **all elements**.

```css
* {
    margin: 0;
    padding: 0;
}
```

Commonly used for basic CSS resets.

---

## 3. Element Selector

Selects all elements of a particular HTML tag.

```css
p {
    color: #333;
}
```

This applies to every `<p>` element.

Another example:

```css
h1 {
    font-size: 40px;
}
```

---

## 4. Class Selector

Selects elements with a specific class.

CSS:

```css
.card {
    padding: 20px;
}
```

HTML:

```html
<div class="card">
    Project
</div>
```

A class can be reused:

```html
<div class="card">Project 1</div>

<div class="card">Project 2</div>
```

### Syntax

```css
.class-name {
    property: value;
}
```

---

## 5. ID Selector

Selects an element using its `id`.

HTML:

```html
<h1 id="title">
    My Portfolio
</h1>
```

CSS:

```css
#title {
    color: blue;
}
```

### Syntax

```css
#id-name {
    property: value;
}
```

IDs should generally be unique within a page.

---

## 6. Class vs ID

### Class

```html
<div class="card"></div>
<div class="card"></div>
```

Use when a style needs to be reused.

### ID

```html
<h1 id="main-title"></h1>
```

Use for a unique element or when an identifier is specifically required.

### Quick Rule

```text
Reusable style → class
Unique identifier → id
```

For normal styling, prefer classes for reusable components.

---

## 7. Grouping Selectors

Multiple selectors can share the same CSS rule.

```css
h1,
h2,
h3 {
    font-family: Arial, sans-serif;
}
```

Instead of writing:

```css
h1 {
    font-family: Arial, sans-serif;
}

h2 {
    font-family: Arial, sans-serif;
}

h3 {
    font-family: Arial, sans-serif;
}
```

---

## 8. Descendant Selector

Selects elements inside another element.

```css
.card p {
    color: gray;
}
```

HTML:

```html
<div class="card">

    <p>
        This paragraph is inside the card.
    </p>

</div>
```

The space means:

```text
.card → ancestor
p     → descendant
```

---

## 9. Child Selector

Selects only **direct children**.

```css
.card > p {
    color: blue;
}
```

Example:

```html
<div class="card">

    <p>Direct child</p>

    <div>
        <p>Nested paragraph</p>
    </div>

</div>
```

The selector `.card > p` targets only the first paragraph.

---

## 10. Adjacent Sibling Selector

Selects the element immediately following another element.

```css
h2 + p {
    margin-top: 10px;
}
```

HTML:

```html
<h2>Projects</h2>

<p>
    My projects are listed below.
</p>
```

`p` must come immediately after `h2`.

---

## 11. General Sibling Selector

Selects sibling elements that appear after another element.

```css
h2 ~ p {
    color: gray;
}
```

Example:

```html
<h2>Projects</h2>

<p>Project description.</p>

<p>More information.</p>
```

Both paragraphs can be selected.

---

## 12. Attribute Selector

Selects elements based on attributes.

### Has Attribute

```css
input[type] {
    border: 1px solid gray;
}
```

### Exact Value

```css
input[type="email"] {
    border-color: blue;
}
```

HTML:

```html
<input type="email">
```

---

## 13. Common Attribute Selectors

### Starts With

```css
a[href^="https"] {
    color: green;
}
```

`^=` means starts with.

---

### Ends With

```css
a[href$=".pdf"] {
    color: red;
}
```

`$=` means ends with.

---

### Contains

```css
a[href*="github"] {
    font-weight: bold;
}
```

`*=` means contains.

---

## 14. Pseudo-Class Selector

Pseudo-classes select an element based on its **state or position**.

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

### Active

```css
button:active {
    transform: scale(0.98);
}
```

---

## 15. Common Pseudo-Classes

```text
:hover
:focus
:active
:visited
:checked
:disabled
:required
:first-child
:last-child
:nth-child()
```

Example:

```css
li:first-child {
    font-weight: bold;
}

li:last-child {
    color: red;
}

li:nth-child(2) {
    color: blue;
}
```

---

## 16. `:nth-child()`

Selects an element based on its position among siblings.

```css
li:nth-child(2) {
    color: blue;
}
```

Selects the second `<li>`.

### Every Even Item

```css
li:nth-child(even) {
    background-color: #f5f5f5;
}
```

### Every Odd Item

```css
li:nth-child(odd) {
    background-color: white;
}
```

---

## 17. `:not()`

Selects elements that **do not match** a selector.

```css
button:not(.primary) {
    background-color: gray;
}
```

This selects buttons that don't have the `primary` class.

---

## 18. Pseudo-Elements

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

Other examples:

```text
::first-letter
::first-line
::selection
```

---

## 19. Multiple Classes

An element can have multiple classes.

HTML:

```html
<div class="card featured">
    Project
</div>
```

CSS:

```css
.card {
    padding: 20px;
}

.featured {
    border: 2px solid blue;
}
```

Both styles apply.

---

## 20. Combining Selectors

Selectors can be combined.

```css
.card.featured {
    border: 2px solid blue;
}
```

This targets an element that has **both** classes.

HTML:

```html
<div class="card featured">
    Project
</div>
```

---

## 21. Selector Specificity

When multiple rules target the same element, specificity helps determine which rule wins.

General order:

```text
Inline style
    ↓
ID
    ↓
Class / attribute / pseudo-class
    ↓
Element
```

Example:

```css
p {
    color: blue;
}

.text {
    color: green;
}

#intro {
    color: red;
}
```

HTML:

```html
<p id="intro" class="text">
    Hello
</p>
```

The ID selector has greater specificity than the class and element selectors.

---

## 22. Selector Specificity Example

```css
.card {
    color: blue;
}

.card.featured {
    color: green;
}

#main-card {
    color: red;
}
```

HTML:

```html
<div
    id="main-card"
    class="card featured"
>
    Project
</div>
```

The ID selector has higher specificity.

---

## 23. CSS Selector Combinations

### Element + Class

```css
button.primary {
    background-color: blue;
}
```

### Class + Pseudo-Class

```css
.button:hover {
    transform: translateY(-2px);
}
```

### Parent + Child

```css
.nav > a {
    text-decoration: none;
}
```

### Parent + Descendant

```css
.card p {
    color: gray;
}
```

---

## 24. Practical Example

HTML:

```html
<div class="projects">

    <article class="card featured">

        <h2>Portfolio</h2>

        <p>
            Personal developer portfolio.
        </p>

        <a href="/portfolio">
            View Project
        </a>

    </article>

    <article class="card">

        <h2>JavaScript App</h2>

        <p>
            JavaScript project.
        </p>

        <a href="/javascript">
            View Project
        </a>

    </article>

</div>
```

CSS:

```css
.projects {
    padding: 20px;
}

.card {
    padding: 20px;
    border: 1px solid #ddd;
}

.card p {
    color: #666;
}

.card > h2 {
    margin-bottom: 10px;
}

.card a:hover {
    text-decoration: underline;
}

.card.featured {
    border: 2px solid blue;
}
```

---

# Selector Quick Reference

| Selector           | Meaning               |
| ------------------ | --------------------- |
| `*`                | All elements          |
| `p`                | All `<p>` elements    |
| `.card`            | Class                 |
| `#title`           | ID                    |
| `h1, h2`           | Group                 |
| `.card p`          | Descendant            |
| `.card > p`        | Direct child          |
| `h2 + p`           | Next sibling          |
| `h2 ~ p`           | General siblings      |
| `[type]`           | Has attribute         |
| `[type="email"]`   | Exact attribute value |
| `[href^="https"]`  | Starts with           |
| `[href$=".pdf"]`   | Ends with             |
| `[href*="github"]` | Contains              |
| `:hover`           | Hover state           |
| `:focus`           | Focus state           |
| `:nth-child()`     | Child position        |
| `:not()`           | Excludes selector     |
| `::before`         | Before pseudo-element |
| `::after`          | After pseudo-element  |

---

# Key Takeaways

```text
1. Selectors target HTML elements.
2. Use classes for reusable styling.
3. Use IDs for unique identification.
4. Learn descendant and child selectors.
5. Learn sibling selectors.
6. Learn attribute selectors.
7. Learn pseudo-classes.
8. Learn pseudo-elements.
9. Understand selector specificity.
10. Combine selectors when needed.
```
