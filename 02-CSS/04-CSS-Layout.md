# CSS Layout

> Important concepts + organized reference.

---

## 1. What is CSS Layout?

CSS layout controls **how elements are positioned, sized, aligned, and arranged** on a webpage.

Main layout concepts:

```text
display
position
flexbox
grid
float
z-index
```

---

## 2. `display`

The `display` property controls how an element participates in layout.

### Block

```css
.box {
    display: block;
}
```

A block element normally starts on a new line and takes available width.

### Inline

```css
.text {
    display: inline;
}
```

An inline element flows within surrounding text.

### Inline-Block

```css
.button {
    display: inline-block;
}
```

Combines inline flow with the ability to control width and height.

### None

```css
.hidden {
    display: none;
}
```

The element is removed from the layout.

---

## 3. `position`

Controls how an element is positioned.

Common values:

```text
static
relative
absolute
fixed
sticky
```

---

## 4. `position: static`

Default positioning.

```css
.box {
    position: static;
}
```

The element follows the normal document flow.

---

## 5. `position: relative`

The element remains in the normal flow but can be visually offset.

```css
.box {
    position: relative;
    top: 10px;
    left: 20px;
}
```

It also provides a positioning reference for absolutely positioned descendants.

---

## 6. `position: absolute`

The element is removed from the normal document flow.

```css
.child {
    position: absolute;
    top: 0;
    right: 0;
}
```

An absolutely positioned element is positioned relative to its nearest positioned ancestor.

Example:

```css
.parent {
    position: relative;
}

.child {
    position: absolute;
    top: 0;
    right: 0;
}
```

---

## 7. `position: fixed`

The element is positioned relative to the viewport.

```css
.navbar {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
}
```

It stays in the same viewport position while scrolling.

Common uses:

* Fixed navigation
* Floating buttons
* Fixed controls

---

## 8. `position: sticky`

The element behaves normally until a scroll threshold is reached.

```css
.sidebar {
    position: sticky;
    top: 20px;
}
```

Useful for:

* Sticky navigation
* Sidebars
* Section headers

---

## 9. Positioning Properties

These properties work with positioned elements:

```text
top
right
bottom
left
```

Example:

```css
.box {
    position: absolute;
    top: 20px;
    right: 30px;
}
```

---

## 10. Flexbox

Flexbox is designed for **one-dimensional layouts**.

It is useful for arranging items in:

```text
row
column
```

Example:

```css
.container {
    display: flex;
}
```

HTML:

```html
<div class="container">

    <div>One</div>
    <div>Two</div>
    <div>Three</div>

</div>
```

---

## 11. `flex-direction`

Controls the main axis.

### Row

```css
.container {
    display: flex;
    flex-direction: row;
}
```

Items are arranged horizontally.

### Column

```css
.container {
    display: flex;
    flex-direction: column;
}
```

Items are arranged vertically.

---

## 12. Main Axis and Cross Axis

With:

```css
flex-direction: row;
```

```text
Main axis   → horizontal
Cross axis  → vertical
```

With:

```css
flex-direction: column;
```

```text
Main axis   → vertical
Cross axis  → horizontal
```

This distinction is important for understanding alignment.

---

## 13. `justify-content`

Controls alignment along the **main axis**.

```css
.container {
    display: flex;
    justify-content: center;
}
```

Common values:

```text
flex-start
center
flex-end
space-between
space-around
space-evenly
```

Example:

```css
.container {
    display: flex;
    justify-content: space-between;
}
```

---

## 14. `align-items`

Controls alignment along the **cross axis**.

```css
.container {
    display: flex;
    align-items: center;
}
```

Common values:

```text
stretch
flex-start
center
flex-end
```

---

## 15. Centering with Flexbox

A common pattern:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

This centers items horizontally and vertically when the flex direction is the default row.

---

## 16. `gap`

Creates space between flex or grid items.

```css
.container {
    display: flex;
    gap: 20px;
}
```

This is often cleaner than adding margins to individual children.

---

## 17. `flex-wrap`

Controls whether flex items can move onto multiple lines.

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

Without wrapping, items generally remain on a single flex line.

---

## 18. `flex` Property

Controls how a flex item grows and shrinks.

```css
.item {
    flex: 1;
}
```

Example:

```css
.container {
    display: flex;
}

.item {
    flex: 1;
}
```

The available space can be distributed among the items.

---

## 19. `align-self`

Overrides the cross-axis alignment for an individual flex item.

```css
.item {
    align-self: flex-end;
}
```

---

## 20. CSS Grid

Grid is designed for **two-dimensional layouts**.

It works with:

```text
rows
columns
```

Example:

```css
.container {
    display: grid;
}
```

---

## 21. Grid Columns

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

Creates three equal columns.

Another example:

```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr 200px;
}
```

---

## 22. Grid Rows

```css
.container {
    display: grid;
    grid-template-rows: 100px 200px;
}
```

Defines row sizes.

---

## 23. `gap` in Grid

```css
.container {
    display: grid;
    gap: 20px;
}
```

You can also use:

```css
.container {
    row-gap: 20px;
    column-gap: 30px;
}
```

---

## 24. `repeat()`

Makes repeated grid tracks easier to write.

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

Equivalent conceptually to:

```text
1fr 1fr 1fr
```

---

## 25. `minmax()`

Defines a minimum and maximum size for a grid track.

```css
.container {
    display: grid;
    grid-template-columns:
        repeat(3, minmax(200px, 1fr));
}
```

Useful for flexible layouts.

---

## 26. `grid-column`

Controls where a grid item starts and ends across columns.

```css
.featured {
    grid-column: 1 / 3;
}
```

The item spans from grid column line 1 to line 3.

---

## 27. `grid-row`

Controls where a grid item starts and ends across rows.

```css
.featured {
    grid-row: 1 / 3;
}
```

---

## 28. Float

`float` was historically used for layouts and is still useful in specific cases, especially for text wrapping around images.

Example:

```css
img {
    float: left;
    margin-right: 20px;
}
```

For modern page layouts, Flexbox and Grid are generally more suitable.

---

## 29. `clear`

Controls whether an element can sit beside floated elements.

```css
.footer {
    clear: both;
}
```

Common values:

```text
none
left
right
both
```

---

## 30. `z-index`

Controls the stacking order of positioned elements.

```css
.modal {
    position: fixed;
    z-index: 1000;
}
```

A larger stacking value generally places the element above elements with lower stacking levels when they participate in the same stacking context.

---

## 31. Centering with Grid

Grid can also center content easily.

```css
.container {
    display: grid;
    place-items: center;
}
```

This centers grid items along both axes.

---

## 32. `place-items`

Shorthand for aligning grid items on both axes.

```css
.container {
    display: grid;
    place-items: center;
}
```

---

## 33. `place-content`

Controls alignment of the grid content as a whole.

```css
.container {
    display: grid;
    place-content: center;
}
```

---

## 34. Flexbox vs Grid

| Feature            | Flexbox                  | Grid                   |
| ------------------ | ------------------------ | ---------------------- |
| Main purpose       | One-dimensional layout   | Two-dimensional layout |
| Direction          | Row or column            | Rows and columns       |
| Best for           | Components and alignment | Page/section layouts   |
| Alignment          | Excellent                | Excellent              |
| Responsive layouts | Yes                      | Yes                    |

### Simple Rule

```text
One dimension → Flexbox
Two dimensions → Grid
```

---

## 35. Responsive Grid Example

```css
.projects {
    display: grid;

    grid-template-columns:
        repeat(
            auto-fit,
            minmax(250px, 1fr)
        );

    gap: 20px;
}
```

This allows the number of columns to adapt to the available width.

---

## 36. Complete Flexbox Example

HTML:

```html
<div class="navbar">

    <div class="logo">
        MySite
    </div>

    <nav>

        <a href="/">Home</a>
        <a href="/projects">Projects</a>
        <a href="/contact">Contact</a>

    </nav>

</div>
```

CSS:

```css
.navbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
}

.navbar nav {
    display: flex;
    gap: 20px;
}
```

---

## 37. Complete Grid Example

HTML:

```html
<div class="projects">

    <article class="card">
        Project 1
    </article>

    <article class="card">
        Project 2
    </article>

    <article class="card">
        Project 3
    </article>

    <article class="card">
        Project 4
    </article>

</div>
```

CSS:

```css
.projects {
    display: grid;

    grid-template-columns:
        repeat(3, 1fr);

    gap: 20px;
}
```

---

# Layout Quick Reference

| Concept              | Property                         |
| -------------------- | -------------------------------- |
| Display mode         | `display`                        |
| Positioning          | `position`                       |
| Position offset      | `top`, `right`, `bottom`, `left` |
| Flex direction       | `flex-direction`                 |
| Main-axis alignment  | `justify-content`                |
| Cross-axis alignment | `align-items`                    |
| Individual alignment | `align-self`                     |
| Flex wrapping        | `flex-wrap`                      |
| Flex spacing         | `gap`                            |
| Grid columns         | `grid-template-columns`          |
| Grid rows            | `grid-template-rows`             |
| Grid spacing         | `gap`                            |
| Grid repetition      | `repeat()`                       |
| Flexible grid size   | `minmax()`                       |
| Grid item columns    | `grid-column`                    |
| Grid item rows       | `grid-row`                       |
| Stacking             | `z-index`                        |
| Float                | `float`                          |
| Clear float          | `clear`                          |

---

# Key Takeaways

```text
1. display controls how elements participate in layout.
2. position controls element positioning.
3. Flexbox is mainly for one-dimensional layouts.
4. Grid is mainly for two-dimensional layouts.
5. justify-content controls the main axis in Flexbox.
6. align-items controls the cross axis in Flexbox.
7. gap creates spacing between layout items.
8. Grid uses rows and columns.
9. z-index controls stacking order.
10. Use Flexbox and Grid for modern layouts.
```
