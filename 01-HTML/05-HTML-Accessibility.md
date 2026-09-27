# HTML Accessibility

> Important concepts + organized reference.

---

## 1. What is Web Accessibility?

Web accessibility means designing websites so that **people with different abilities can use them effectively**.

HTML accessibility mainly focuses on:

* Meaningful HTML structure
* Keyboard access
* Screen readers
* Forms
* Images
* Links
* Headings

---

## 2. Use Semantic HTML

Semantic HTML gives browsers and assistive technologies meaningful information about the page structure.

Use:

```html
<header></header>
<nav></nav>
<main></main>
<section></section>
<article></article>
<aside></aside>
<footer></footer>
```

Instead of using `<div>` for everything.

Example:

```html
<nav>
    <a href="/">Home</a>
    <a href="/projects">Projects</a>
</nav>
```

---

## 3. Images and `alt`

Images should have meaningful alternative text when the image provides useful information.

```html
<img
    src="profile.jpg"
    alt="Rabindra Kumar profile photo"
>
```

For decorative images, empty `alt` can be used:

```html
<img
    src="decoration.png"
    alt=""
>
```

### Rule

```text
Informative image → meaningful alt
Decorative image  → alt=""
```

---

## 4. Use Proper Headings

Headings should represent the content hierarchy.

```html
<h1>My Portfolio</h1>

<h2>Projects</h2>

<h3>JavaScript Project</h3>

<h3>Weather App</h3>

<h2>Skills</h2>
```

### Basic hierarchy

```text
h1
└── h2
    ├── h3
    └── h3
```

Do not choose heading levels only because of their visual size. Use CSS when you need different visual styling.

---

## 5. Accessible Links

Links should clearly describe where they lead.

### Good

```html
<a href="/projects">
    View my projects
</a>
```

### Avoid unclear text

```html
<a href="/projects">
    Click here
</a>
```

Users should be able to understand the purpose of a link from its text.

---

## 6. Accessible Forms

Every important form control should have an associated label.

```html
<label for="email">
    Email
</label>

<input
    id="email"
    name="email"
    type="email"
>
```

The `for` value of the label should match the input's `id`.

### Group Related Controls

Use:

```html
<fieldset>

    <legend>
        Account Information
    </legend>

    ...

</fieldset>
```

---

## 7. Keyboard Accessibility

Important interactive elements should be usable with a keyboard.

Native HTML elements such as:

```html
<button>
    Submit
</button>

<a href="/projects">
    Projects
</a>
```

already provide standard keyboard behavior.

Avoid creating interactive controls using a plain `<div>` when a native element is appropriate.

---

## 8. Buttons vs Links

Use a **button** for an action.

```html
<button type="button">
    Delete
</button>
```

Use a **link** for navigation.

```html
<a href="/projects">
    View Projects
</a>
```

### Simple Rule

```text
Action     → button
Navigation → a
```

---

## 9. Language Attribute

Specify the page language.

```html
<html lang="en">
```

For a Hindi page:

```html
<html lang="hi">
```

This helps browsers and assistive technologies determine the language of the content.

---

## 10. Form Input Types

Use appropriate input types.

```html
<input type="email">

<input type="tel">

<input type="number">

<input type="date">

<input type="password">
```

The correct input type communicates the expected data and can provide better browser and device behavior.

---

## 11. Use Native HTML Before ARIA

Prefer native HTML elements whenever possible.

Good:

```html
<button>
    Submit
</button>
```

Instead of creating a custom button using a generic element.

ARIA can be useful when native HTML does not provide the required semantics, but it should not unnecessarily replace native HTML.

---

## 12. `aria-label`

`aria-label` can provide an accessible name when visible text is not available.

Example:

```html
<button aria-label="Close">
    ×
</button>
```

Use ARIA carefully and avoid adding it when normal HTML already provides the required accessible name.

---

## 13. Complete Accessible Example

```html
<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <title>Accessible Portfolio</title>

</head>

<body>

    <header>

        <h1>Rabindra Kumar</h1>

        <nav aria-label="Main navigation">

            <a href="/">Home</a>
            <a href="/projects">Projects</a>
            <a href="/contact">Contact</a>

        </nav>

    </header>

    <main>

        <section>

            <h2>About Me</h2>

            <img
                src="profile.jpg"
                alt="Rabindra Kumar profile photo"
            >

            <p>
                I am learning software development.
            </p>

        </section>

        <section>

            <h2>Contact</h2>

            <form>

                <label for="name">
                    Name
                </label>

                <input
                    id="name"
                    name="name"
                    type="text"
                    required
                >

                <label for="email">
                    Email
                </label>

                <input
                    id="email"
                    name="email"
                    type="email"
                    required
                >

                <button type="submit">
                    Send Message
                </button>

            </form>

        </section>

    </main>

    <footer>

        <p>
            © 2026 Rabindra Kumar
        </p>

    </footer>

</body>

</html>
```

---

## Quick Reference

| Concept       | Practice                        |
| ------------- | ------------------------------- |
| Semantic HTML | Use meaningful elements         |
| Images        | Provide appropriate `alt`       |
| Headings      | Maintain logical hierarchy      |
| Links         | Use descriptive link text       |
| Forms         | Associate labels with controls  |
| Keyboard      | Use native interactive elements |
| Buttons       | Use for actions                 |
| Links         | Use for navigation              |
| Language      | Set `lang`                      |
| Inputs        | Use appropriate input types     |
| ARIA          | Use when necessary              |

---

## Key Rules

```text
1. Use semantic HTML.
2. Give informative images meaningful alt text.
3. Keep heading hierarchy logical.
4. Use descriptive link text.
5. Associate labels with form controls.
6. Use native buttons and links.
7. Make interactive content keyboard accessible.
8. Set the correct page language.
9. Prefer native HTML over unnecessary ARIA.
10. Use ARIA only when it provides needed semantics.
```
