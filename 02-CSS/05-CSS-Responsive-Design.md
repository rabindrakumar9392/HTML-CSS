# CSS Responsive Design

> Important concepts + organized reference.

---

## 1. What is Responsive Design?

Responsive design means creating websites that **adapt to different screen sizes and devices**.

A responsive website should work properly on:

```text
Desktop
Laptop
Tablet
Mobile
```

Main CSS tools:

```text
Flexible units
Media queries
Flexbox
Grid
Responsive images
Mobile-first design
```

---

## 2. Viewport Meta Tag

Responsive websites should include the viewport meta tag.

```html
<meta
    name="viewport"
    content="width=device-width, initial-scale=1.0"
>
```

It tells the browser to use the device's width as the viewport width.

---

## 3. Fixed vs Flexible Units

### Fixed

```css
.box {
    width: 500px;
}
```

The width stays fixed.

### Flexible

```css
.box {
    width: 80%;
}
```

The width can change according to the available space.

Common responsive units:

```text
%
rem
em
vw
vh
```

---

## 4. Percentage `%`

Percentage values are relative to a relevant containing dimension.

```css
.container {
    width: 80%;
}
```

Useful for creating flexible layouts.

---

## 5. Viewport Units

### `vw`

`vw` = viewport width.

```css
.hero {
    width: 80vw;
}
```

### `vh`

`vh` = viewport height.

```css
.hero {
    min-height: 100vh;
}
```

---

## 6. `rem`

`rem` is relative to the root (`html`) font size.

```css
html {
    font-size: 16px;
}

.title {
    font-size: 2rem;
}
```

With a 16px root size:

```text
2rem = 32px
```

---

## 7. `em`

`em` is relative to the font size of the relevant parent/current context.

```css
.container {
    font-size: 20px;
}

.title {
    font-size: 1.5em;
}
```

This can be useful for component-relative sizing.

---

## 8. `max-width`

Prevents an element from becoming too wide.

```css
.container {
    width: 100%;
    max-width: 1200px;
}
```

Common pattern:

```css
.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
}
```

---

## 9. Responsive Images

Images should normally scale within their containers.

```css
img {
    max-width: 100%;
    height: auto;
}
```

This prevents an image from overflowing its container in many common layouts.

---

## 10. Media Queries

Media queries apply CSS based on conditions such as viewport width.

Basic syntax:

```css
@media (max-width: 768px) {

    .container {
        width: 100%;
    }

}
```

The styles inside the media query apply when the condition matches.

---

## 11. Common Breakpoint Concept

Breakpoints are widths where the layout changes.

Example:

```css
@media (max-width: 768px) {

    .navbar {
        flex-direction: column;
    }

}
```

Do not choose breakpoints only because they are traditional device sizes. Choose them based on where your actual layout needs to change.

---

## 12. Mobile-First Design

Mobile-first means starting with the smaller-screen layout and then adding styles for larger screens.

Base CSS:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

Larger screens:

```css
@media (min-width: 768px) {

    .container {
        flex-direction: row;
    }

}
```

Basic idea:

```text
Mobile
  ↓
Tablet
  ↓
Desktop
```

---

## 13. Desktop-First Design

Desktop-first starts with the larger layout and adds changes for smaller screens.

```css
.container {
    display: flex;
    flex-direction: row;
}

@media (max-width: 768px) {

    .container {
        flex-direction: column;
    }

}
```

Both approaches are possible, but mobile-first is commonly useful when the mobile experience is a priority.

---

## 14. Responsive Flexbox

Flexbox can automatically adapt layouts.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}
```

Children can move onto additional lines when there is not enough space.

---

## 15. Responsive Grid

CSS Grid can create responsive columns.

```css
.projects {
    display: grid;

    grid-template-columns:
        repeat(3, 1fr);

    gap: 20px;
}
```

Then change the number of columns:

```css
@media (max-width: 768px) {

    .projects {
        grid-template-columns: 1fr;
    }

}
```

---

## 16. `auto-fit` + `minmax()`

A powerful responsive Grid pattern:

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

The browser can automatically adjust the number of columns according to available space.

---

## 17. Responsive Typography

Font sizes can change at different screen sizes.

```css
h1 {
    font-size: 48px;
}

@media (max-width: 768px) {

    h1 {
        font-size: 36px;
    }

}
```

---

## 18. `clamp()`

`clamp()` can create fluid values with a minimum, preferred, and maximum.

Syntax:

```css
font-size: clamp(
    minimum,
    preferred,
    maximum
);
```

Example:

```css
h1 {
    font-size: clamp(
        2rem,
        5vw,
        4rem
    );
}
```

This allows the font size to adapt while remaining within defined limits.

---

## 19. Responsive Spacing

Spacing can also be responsive.

```css
.section {
    padding: 40px 20px;
}

@media (max-width: 768px) {

    .section {
        padding: 25px 15px;
    }

}
```

---

## 20. Responsive Navigation

Desktop:

```css
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
```

Mobile:

```css
@media (max-width: 768px) {

    .navbar {
        flex-direction: column;
        gap: 15px;
    }

}
```

For more complex navigation, JavaScript may be used to open and close a mobile menu.

---

## 21. Hide and Show Elements

An element can be hidden at specific screen sizes.

```css
.desktop-only {
    display: block;
}

@media (max-width: 768px) {

    .desktop-only {
        display: none;
    }

}
```

Use this carefully. Hiding important content can create usability and accessibility problems.

---

## 22. Responsive Container

A common website container:

```css
.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
}
```

This provides:

```text
Flexible width
+
Maximum readable width
+
Automatic horizontal centering
```

---

## 23. Prevent Horizontal Overflow

A common first check when a page unexpectedly scrolls horizontally is to find the element wider than the viewport.

Images can be constrained:

```css
img {
    max-width: 100%;
    height: auto;
}
```

Containers should also avoid unnecessary fixed widths.

---

## 24. Responsive Card Layout

HTML:

```html
<div class="cards">

    <article class="card">
        <h2>Project 1</h2>
        <p>Project description.</p>
    </article>

    <article class="card">
        <h2>Project 2</h2>
        <p>Project description.</p>
    </article>

    <article class="card">
        <h2>Project 3</h2>
        <p>Project description.</p>
    </article>

</div>
```

CSS:

```css
.cards {
    display: grid;

    grid-template-columns:
        repeat(
            auto-fit,
            minmax(250px, 1fr)
        );

    gap: 20px;
}

.card {
    padding: 20px;
}
```

The grid can adapt the number of columns to available space.

---

## 25. Responsive Hero Section

```css
.hero {
    min-height: 70vh;

    display: flex;

    align-items: center;
    justify-content: center;

    padding: 40px 20px;

    text-align: center;
}
```

Responsive heading:

```css
.hero h1 {
    font-size: clamp(
        2rem,
        6vw,
        5rem
    );
}
```

---

## 26. Responsive Layout Example

```css
.page {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
}

.content {
    display: grid;

    grid-template-columns:
        2fr 1fr;

    gap: 30px;
}

@media (max-width: 768px) {

    .content {
        grid-template-columns: 1fr;
    }

}
```

Desktop:

```text
┌──────────────────────────────┐
│          Main      │ Sidebar │
│                    │         │
└──────────────────────────────┘
```

Mobile:

```text
┌─────────────────────┐
│        Main         │
├─────────────────────┤
│       Sidebar       │
└─────────────────────┘
```

---

## 27. Responsive Design Checklist

Before considering a page responsive, check:

```text
✓ Viewport meta tag
✓ Flexible containers
✓ max-width where appropriate
✓ Responsive images
✓ Flexbox/Grid
✓ Media queries where needed
✓ Mobile navigation
✓ Responsive typography
✓ Responsive spacing
✓ No unnecessary horizontal scrolling
✓ Buttons and links usable on small screens
```

---

# Quick Reference

| Concept                 | Main Tool         |
| ----------------------- | ----------------- |
| Flexible width          | `%`               |
| Root-relative size      | `rem`             |
| Component-relative size | `em`              |
| Viewport width          | `vw`              |
| Viewport height         | `vh`              |
| Maximum width           | `max-width`       |
| Responsive images       | `max-width: 100%` |
| Breakpoints             | `@media`          |
| Flexible layout         | Flexbox           |
| Responsive columns      | Grid              |
| Automatic grid          | `auto-fit`        |
| Minimum/maximum size    | `minmax()`        |
| Fluid value             | `clamp()`         |

---

# Key Takeaways

```text
1. Responsive design adapts to different screen sizes.
2. Use flexible units instead of unnecessary fixed widths.
3. Use max-width for readable containers.
4. Make images responsive.
5. Use media queries when the layout needs to change.
6. Flexbox and Grid are important responsive layout tools.
7. auto-fit + minmax() is useful for responsive grids.
8. clamp() is useful for fluid typography.
9. Test the actual layout at different widths.
10. Build mobile-friendly layouts from the beginning.
```
