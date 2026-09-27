# CSS Box Model

> Important concepts + organized reference.

---

## 1. What is the CSS Box Model?

Every HTML element is treated as a rectangular box.

The CSS box model consists of:

```text
┌──────────────────────────────┐
│            Margin            │
│  ┌────────────────────────┐  │
│  │         Border         │  │
│  │  ┌──────────────────┐  │  │
│  │  │     Padding      │  │  │
│  │  │  ┌────────────┐  │  │  │
│  │  │  │  Content   │  │  │  │
│  │  │  └────────────┘  │  │  │
│  │  └──────────────────┘  │  │
│  └────────────────────────┘  │
└──────────────────────────────┘
```

Order:

```text
Content
   ↓
Padding
   ↓
Border
   ↓
Margin
```

---

## 2. Content

The content is the actual area inside an element.

Example:

```css id="b5jvkl"
.box {
    width: 300px;
    height: 200px;
}
```

Here:

```text
width  → content width
height → content height
```

---

## 3. Padding

Padding is the space **between the content and border**.

```css id="yq3z1h"
.box {
    padding: 20px;
}
```

All four sides:

```text
top
right
bottom
left
```

---

## 4. Padding Individual Sides

```css id="d3m4gf"
.box {
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 30px;
    padding-left: 40px;
}
```

---

## 5. Padding Shorthand

### One Value

```css id="6z5s5h"
.box {
    padding: 20px;
}
```

Applies to all four sides.

```text
top    = 20px
right  = 20px
bottom = 20px
left   = 20px
```

### Two Values

```css id="5d6lkk"
.box {
    padding: 10px 20px;
}
```

```text
top/bottom = 10px
left/right = 20px
```

### Three Values

```css id="u4w0a9"
.box {
    padding: 10px 20px 30px;
}
```

```text
top    = 10px
left/right = 20px
bottom = 30px
```

### Four Values

```css id="6x9xdt"
.box {
    padding: 10px 20px 30px 40px;
}
```

Order:

```text
top → right → bottom → left
```

Remember:

**TRBL = Top Right Bottom Left**

---

## 6. Border

Border surrounds the padding and content.

Basic syntax:

```css id="rj7u6e"
.box {
    border: 1px solid black;
}
```

Structure:

```text
border-width
border-style
border-color
```

---

## 7. Border Width

```css id="2e0c4y"
.box {
    border-width: 2px;
}
```

Individual sides:

```css id="xwz8eq"
.box {
    border-top-width: 2px;
    border-right-width: 3px;
    border-bottom-width: 4px;
    border-left-width: 5px;
}
```

---

## 8. Border Style

Common values:

```text
solid
dashed
dotted
double
none
```

Example:

```css id="v5h13d"
.box {
    border: 2px dashed black;
}
```

---

## 9. Border Color

```css id="l3kg8g"
.box {
    border-color: blue;
}
```

Complete:

```css id="9m4t10"
.box {
    border: 2px solid blue;
}
```

---

## 10. Border Radius

Creates rounded corners.

```css id="0l8yko"
.box {
    border-radius: 10px;
}
```

Circle:

```css id="2w4e3d"
.avatar {
    width: 100px;
    height: 100px;
    border-radius: 50%;
}
```

---

## 11. Margin

Margin is the space **outside the border**.

```css id="u7z3ph"
.box {
    margin: 20px;
}
```

Margin creates space between an element and surrounding elements.

---

## 12. Margin Individual Sides

```css id="r4eh70"
.box {
    margin-top: 10px;
    margin-right: 20px;
    margin-bottom: 30px;
    margin-left: 40px;
}
```

---

## 13. Margin Shorthand

### One Value

```css id="o9y6de"
.box {
    margin: 20px;
}
```

All sides = `20px`.

### Two Values

```css id="k5w5o9"
.box {
    margin: 10px 20px;
}
```

```text
top/bottom = 10px
left/right = 20px
```

### Three Values

```css id="2o8q1k"
.box {
    margin: 10px 20px 30px;
}
```

```text
top = 10px
left/right = 20px
bottom = 30px
```

### Four Values

```css id="0w8kqm"
.box {
    margin: 10px 20px 30px 40px;
}
```

Order:

```text
top → right → bottom → left
```

---

## 14. `margin: auto`

`auto` can be used to center a block element horizontally when it has a defined width.

```css id="0f3b92"
.container {
    width: 800px;
    margin: 0 auto;
}
```

Meaning:

```text
top/bottom → 0
left/right → automatic
```

---

## 15. Width and Height

```css id="ksx2o4"
.box {
    width: 300px;
    height: 200px;
}
```

Other sizing properties:

```css id="r1o0v2"
.box {
    min-width: 200px;
    max-width: 800px;

    min-height: 100px;
    max-height: 500px;
}
```

---

## 16. `box-sizing`

`box-sizing` controls how the declared width and height are calculated.

### `content-box`

This is the default.

```css id="e3b5si"
.box {
    box-sizing: content-box;
}
```

The declared width applies to the content area.

Padding and border are added outside that content size.

---

### `border-box`

```css id="g0ymvl"
.box {
    box-sizing: border-box;
}
```

The declared width includes:

```text
Content
+ Padding
+ Border
```

This is commonly used in modern layouts.

---

## 17. Global `border-box`

A common CSS setup:

```css id="1r9c8z"
* {
    box-sizing: border-box;
}
```

This makes sizing more predictable across elements.

---

## 18. Content Box vs Border Box

Suppose:

```css id="b6p4t1"
.box {
    width: 300px;
    padding: 20px;
    border: 5px solid black;
}
```

### `content-box`

Actual outer width:

```text
300
+ 20 + 20 padding
+ 5 + 5 border
= 350px
```

### `border-box`

Total outer width remains:

```text
300px
```

The content area becomes smaller to accommodate padding and border.

---

## 19. `overflow`

Controls content that exceeds the element's box.

```css id="q7k2zz"
.box {
    width: 200px;
    height: 100px;
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

### `overflow-x`

Controls horizontal overflow.

```css id="c0f4eq"
.box {
    overflow-x: auto;
}
```

### `overflow-y`

Controls vertical overflow.

```css id="w6n6m8"
.box {
    overflow-y: auto;
}
```

---

## 20. Box Shadow

Creates a shadow around an element.

```css id="q0t4cg"
.card {
    box-shadow:
        0 5px 20px rgba(0, 0, 0, 0.15);
}
```

Basic structure:

```text
horizontal offset
vertical offset
blur radius
spread radius
color
```

---

## 21. Outline

An outline is drawn outside the border.

```css id="5p5gby"
input:focus {
    outline: 2px solid blue;
}
```

Unlike borders, outlines generally do not affect the element's layout size.

---

## 22. Box Model Example

HTML:

```html id="0p84nq"
<div class="card">

    <h2>Project</h2>

    <p>
        My project description.
    </p>

</div>
```

CSS:

```css id="j7k9vb"
.card {
    width: 300px;

    padding: 20px;

    border: 2px solid #ddd;

    margin: 30px;

    border-radius: 12px;

    box-sizing: border-box;

    box-shadow:
        0 5px 20px rgba(0, 0, 0, 0.1);
}
```

Box structure:

```text
Margin
  ↓
Border
  ↓
Padding
  ↓
Content
```

---

# Quick Reference

| Property        | Purpose                       |
| --------------- | ----------------------------- |
| `width`         | Element width                 |
| `height`        | Element height                |
| `min-width`     | Minimum width                 |
| `max-width`     | Maximum width                 |
| `min-height`    | Minimum height                |
| `max-height`    | Maximum height                |
| `padding`       | Space inside border           |
| `margin`        | Space outside border          |
| `border`        | Border around element         |
| `border-radius` | Rounded corners               |
| `box-sizing`    | Controls box size calculation |
| `overflow`      | Controls overflowing content  |
| `box-shadow`    | Adds shadow                   |
| `outline`       | Draws outline outside border  |

---

# Key Takeaways

```text
1. Every HTML element behaves like a box.
2. Box model = Content + Padding + Border + Margin.
3. Padding creates internal space.
4. Margin creates external space.
5. Border surrounds content and padding.
6. Use box-sizing: border-box for predictable sizing.
7. margin: 0 auto can center a fixed-width block.
8. overflow controls content outside the box.
9. border-radius creates rounded corners.
10. box-shadow adds visual depth.
```
