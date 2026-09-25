# HTML Elements

HTML elements are the building blocks of an HTML webpage.

An HTML element generally consists of:

```html
<tag>Content</tag>
```

Example:

```html
<h1>Hello World</h1>
```

---

## 1. Element Anatomy

```html
<p class="text">
    Hello World
</p>
```

Here:

* `<p>` → Opening tag
* `class="text"` → Attribute
* `Hello World` → Content
* `</p>` → Closing tag
* Complete structure → Element

---

## 2. Block-Level Elements

Block-level elements normally start on a new line and take the available width.

Common examples:

```html
<div></div>
<p></p>
<h1></h1>
<section></section>
<article></article>
<header></header>
<footer></footer>
<nav></nav>
<main></main>
<ul></ul>
<ol></ol>
<table></table>
<form></form>
```

Example:

```html
<h1>Heading</h1>
<p>Paragraph</p>
<div>Container</div>
```

Each element occupies its own block in normal document flow.

---

## 3. Inline Elements

Inline elements normally stay within the same line.

Common examples:

```html
<span></span>
<a></a>
<strong></strong>
<em></em>
<b></b>
<i></i>
<mark></mark>
<small></small>
<code></code>
```

Example:

```html
<p>
    Learn <strong>HTML</strong> and
    <em>CSS</em>.
</p>
```

---

## 4. `<div>` Element

`<div>` is a generic block-level container.

It is commonly used to group content.

```html
<div class="card">

    <h2>Product</h2>

    <p>
        Product description.
    </p>

</div>
```

Use `<div>` when no more meaningful semantic element fits.

---

## 5. `<span>` Element

`<span>` is a generic inline container.

```html
<p>
    My favorite color is
    <span>blue</span>.
</p>
```

It is commonly used when styling or manipulating a small part of text.

---

## 6. Line Break

The `<br>` element creates a line break.

```html
<p>
    Hello<br>
    World
</p>
```

`<br>` is a void element, so it does not need a closing tag.

---

## 7. Horizontal Rule

The `<hr>` element represents a thematic break.

```html
<h2>Chapter 1</h2>

<p>
    Introduction to HTML.
</p>

<hr>

<h2>Chapter 2</h2>
```

---

## 8. Comments

HTML comments are ignored by the browser.

```html
<!-- This is an HTML comment -->
```

Comments are useful for documenting code.

```html
<!-- Navigation section -->
<nav>
    ...
</nav>
```

---

# 9. Common Structural Elements

## `<header>`

Represents introductory content or a header for a page or section.

```html
<header>

    <h1>My Website</h1>

</header>
```

---

## `<nav>`

Represents navigation links.

```html
<nav>

    <a href="/">Home</a>
    <a href="/about">About</a>
    <a href="/contact">Contact</a>

</nav>
```

---

## `<main>`

Represents the main content of the document.

```html
<main>

    <h1>Products</h1>

    <p>
        Browse our products.
    </p>

</main>
```

A document should generally have one main content area.

---

## `<section>`

Represents a thematic section of content.

```html
<section>

    <h2>Our Services</h2>

    <p>
        We provide web development services.
    </p>

</section>
```

---

## `<article>`

Represents self-contained content that can stand independently.

Examples:

* Blog post
* News article
* Product card
* Forum post

```html
<article>

    <h2>Learning HTML</h2>

    <p>
        HTML is the foundation of webpages.
    </p>

</article>
```

---

## `<aside>`

Represents content related to the surrounding content but not part of its main flow.

```html
<aside>

    <h3>Related Articles</h3>

    <a href="#">HTML Basics</a>

</aside>
```

---

## `<footer>`

Represents footer information for a page or section.

```html
<footer>

    <p>
        © 2026 My Website
    </p>

</footer>
```

---

# 10. `<figure>` and `<figcaption>`

Used for self-contained media or illustrations with a caption.

```html
<figure>

    <img
        src="image.jpg"
        alt="Mountain landscape"
    >

    <figcaption>
        Mountain landscape
    </figcaption>

</figure>
```

---

# 11. `<details>` and `<summary>`

Used to create expandable content.

```html
<details>

    <summary>
        What is HTML?
    </summary>

    <p>
        HTML structures webpage content.
    </p>

</details>
```

---

# 12. `<dialog>`

Represents a dialog box or interactive modal.

```html
<dialog open>

    <p>
        Welcome!
    </p>

</dialog>
```

The `open` attribute makes the dialog visible.

---

# 13. `<time>`

Represents a specific time or date.

```html
<time datetime="2026-09-25">
    September 25, 2026
</time>
```

This provides machine-readable date information.

---

# 14. `<code>`

Represents a short piece of computer code.

```html
<p>
    Use <code>console.log()</code> in JavaScript.
</p>
```

For multiple lines of code, `<pre>` can be used.

```html
<pre>
const name = "Rabindra";
console.log(name);
</pre>
```

---

# 15. `<blockquote>`

Used for a longer quotation.

```html
<blockquote>
    The future depends on what you do today.
</blockquote>
```

For a short quotation, use `<q>`.

```html
<p>
    He said <q>Hello</q>.
</p>
```

---

# 16. `<abbr>`

Represents an abbreviation.

```html
<p>
    <abbr title="HyperText Markup Language">
        HTML
    </abbr>
</p>
```

The `title` attribute provides the full meaning.

---

# 17. `<address>`

Represents contact information.

```html
<address>

    Written by Rabindra Kumar.<br>
    Email: example@gmail.com

</address>
```

---

# 18. Media Elements

## Audio

```html
<audio controls>

    <source
        src="audio.mp3"
        type="audio/mpeg"
    >

</audio>
```

---

## Video

```html
<video
    controls
    width="640"
>

    <source
        src="video.mp4"
        type="video/mp4"
    >

</video>
```

---

## Track

Used to provide subtitles or captions for video.

```html
<video controls>

    <source
        src="video.mp4"
        type="video/mp4"
    >

    <track
        src="subtitles.vtt"
        kind="subtitles"
        srclang="en"
        label="English"
    >

</video>
```

---

# 19. `<iframe>`

Embeds another webpage or external content.

```html
<iframe
    src="https://example.com"
    title="Example website"
>
</iframe>
```

Common uses include:

* Maps
* Videos
* External pages
* Embedded applications

---

# 20. HTML Entities

Some characters have special meanings in HTML.

Common entities:

| Entity   | Character          |
| -------- | ------------------ |
| `&lt;`   | `<`                |
| `&gt;`   | `>`                |
| `&amp;`  | `&`                |
| `&quot;` | `"`                |
| `&apos;` | `'`                |
| `&nbsp;` | Non-breaking space |
| `&copy;` | ©                  |

Example:

```html
<p>
    5 &lt; 10
</p>
```

Output:

```text
5 < 10
```

---

# 21. Global Attributes

Global attributes can be used on many HTML elements.

## `id`

Provides a unique identifier.

```html
<p id="intro">
    Introduction
</p>
```

An `id` should generally be unique within the document.

---

## `class`

Groups elements for styling or JavaScript.

```html
<p class="text">
    Hello
</p>
```

Multiple elements can have the same class.

---

## `title`

Provides additional information, often shown as a tooltip.

```html
<p title="Additional information">
    Hover over me
</p>
```

---

## `hidden`

Hides an element.

```html
<p hidden>
    This content is hidden.
</p>
```

---

## `lang`

Specifies the language of content.

```html
<html lang="en">
```

---

## `dir`

Specifies text direction.

```html
<p dir="rtl">
    Text
</p>
```

Common values:

```text
ltr
rtl
auto
```

---

## `data-*`

Stores custom data on an element.

```html
<button
    data-product-id="101"
>
    Buy
</button>
```

Custom data attributes are commonly accessed using JavaScript.

---

# 22. Void Elements

Void elements do not have closing tags.

Common examples:

```html
<img>
<br>
<hr>
<input>
<meta>
<link>
<source>
<track>
<area>
<base>
<col>
<embed>
<param>
<wbr>
```

Example:

```html
<img
    src="profile.jpg"
    alt="Profile photo"
>
```

Do not write:

```html
<img></img>
```

---

# 23. Nesting Elements

HTML elements can be nested inside other elements.

Correct:

```html
<p>
    This is
    <strong>important</strong>
    text.
</p>
```

The elements should be properly nested.

Incorrect:

```html
<p>
    This is
    <strong>important
    </p>
    </strong>
```

Correct nesting keeps the document structure predictable.

---

# 24. Attributes

Attributes provide additional information about an element.

Basic syntax:

```html
<tag attribute="value">
    Content
</tag>
```

Example:

```html
<a
    href="https://example.com"
    target="_blank"
>
    Visit Website
</a>
```

Here:

```text
href   → attribute
target → attribute
```

---

# 25. Boolean Attributes

Boolean attributes represent true/false states.

Examples:

```html
<input required>

<input disabled>

<input readonly>

<input checked>

<option selected>
```

When the attribute exists, its state is enabled.

---

# 26. HTML Character Encoding

UTF-8 is commonly specified in HTML documents.

```html
<meta charset="UTF-8">
```

It allows the document to correctly represent a wide range of characters.

---

# 27. HTML Element Categories

```text
HTML Elements
│
├── Structure
│   ├── header
│   ├── nav
│   ├── main
│   ├── section
│   ├── article
│   ├── aside
│   └── footer
│
├── Content
│   ├── h1-h6
│   ├── p
│   ├── div
│   ├── span
│   └── blockquote
│
├── Media
│   ├── img
│   ├── audio
│   ├── video
│   ├── source
│   └── track
│
├── Interactive
│   ├── details
│   ├── summary
│   └── dialog
│
└── Utility
    ├── br
    ├── hr
    ├── code
    ├── time
    └── abbr
```

---

# 28. Professional HTML Structure

A typical webpage can combine many of these elements:

```html
<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <title>My Website</title>

</head>

<body>

    <header>

        <nav>
            <a href="/">Home</a>
            <a href="/about">About</a>
            <a href="/contact">Contact</a>
        </nav>

    </header>

    <main>

        <section>

            <h1>Welcome</h1>

            <p>
                Welcome to my website.
            </p>

        </section>

        <section>

            <article>

                <h2>Latest Article</h2>

                <p>
                    This is an article.
                </p>

            </article>

        </section>

    </main>

    <footer>

        <p>
            © 2026 My Website
        </p>

    </footer>

</body>

</html>
```

---

# Quick Reference

| Element        | Purpose                      |
| -------------- | ---------------------------- |
| `<div>`        | Generic block container      |
| `<span>`       | Generic inline container     |
| `<header>`     | Header content               |
| `<nav>`        | Navigation                   |
| `<main>`       | Main content                 |
| `<section>`    | Thematic section             |
| `<article>`    | Independent content          |
| `<aside>`      | Related content              |
| `<footer>`     | Footer content               |
| `<figure>`     | Self-contained media/content |
| `<figcaption>` | Figure caption               |
| `<details>`    | Expandable content           |
| `<summary>`    | Details heading              |
| `<audio>`      | Audio                        |
| `<video>`      | Video                        |
| `<iframe>`     | Embedded content             |
| `<code>`       | Code                         |
| `<pre>`        | Preformatted content         |
| `<blockquote>` | Long quotation               |
| `<abbr>`       | Abbreviation                 |
| `<time>`       | Date/time                    |
| `<br>`         | Line break                   |
| `<hr>`         | Thematic break               |

---

# Key Takeaways

* HTML elements define webpage structure and content.
* Elements can contain other elements.
* Attributes provide additional information.
* Block and inline elements behave differently in normal document flow.
* Semantic elements such as `header`, `nav`, `main`, `section`, `article`, `aside`, and `footer` describe the meaning of content.
* `div` and `span` are generic containers.
* Void elements do not have closing tags.
* Global attributes such as `id`, `class`, `title`, and `data-*` are widely used.
* HTML entities represent special characters.
* Proper nesting creates a clean and predictable document structure.
