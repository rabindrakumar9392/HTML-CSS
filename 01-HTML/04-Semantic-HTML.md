# Semantic HTML

> Important concepts + organized reference.

---

## 1. Semantic Elements

Semantic HTML elements clearly describe the **meaning and purpose** of the content.

### Main Semantic Elements

| Element     | Purpose                            |
| ----------- | ---------------------------------- |
| `<header>`  | Introductory/header content        |
| `<nav>`     | Navigation links                   |
| `<main>`    | Main content of the page           |
| `<section>` | Groups related content             |
| `<article>` | Independent/self-contained content |
| `<aside>`   | Related or sidebar content         |
| `<footer>`  | Footer information                 |

### Example

```html
<header>
    <h1>My Portfolio</h1>
</header>

<nav>
    <a href="/">Home</a>
    <a href="/projects">Projects</a>
</nav>

<main>

    <section>
        <h2>About Me</h2>
        <p>I am learning web development.</p>
    </section>

    <article>
        <h2>My Latest Project</h2>
        <p>A JavaScript project.</p>
    </article>

    <aside>
        <h2>Related Links</h2>
    </aside>

</main>

<footer>
    <p>© 2026 Rabindra Kumar</p>
</footer>
```

---

## 2. Semantic vs Non-Semantic Elements

### Semantic

These elements describe what the content means:

```html
<header></header>
<nav></nav>
<main></main>
<section></section>
<article></article>
<aside></aside>
<footer></footer>
```

### Non-Semantic

These elements do not describe the specific meaning of their content:

```html
<div></div>
<span></span>
```

### Example

Non-semantic:

```html
<div class="header">
    <h1>My Website</h1>
</div>
```

Semantic:

```html
<header>
    <h1>My Website</h1>
</header>
```

**Rule:** Use a semantic element when it accurately represents the purpose of the content. Use `div` or `span` when a generic container is appropriate.

---

## 3. Practical Page Structure

A common semantic website structure:

```text
<body>
│
├── header
│   └── Logo / Heading
│
├── nav
│   └── Navigation Links
│
├── main
│   │
│   ├── section
│   │   └── About
│   │
│   ├── section
│   │   └── Projects
│   │       ├── article
│   │       └── article
│   │
│   └── aside
│       └── Related Content
│
└── footer
    └── Copyright / Links
```

### Complete Example

```html
<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <title>Developer Portfolio</title>

</head>

<body>

    <header>

        <h1>Rabindra Kumar</h1>

    </header>

    <nav>

        <a href="/">Home</a>
        <a href="/projects">Projects</a>
        <a href="/contact">Contact</a>

    </nav>

    <main>

        <section>

            <h2>About Me</h2>

            <p>
                I am learning
```
