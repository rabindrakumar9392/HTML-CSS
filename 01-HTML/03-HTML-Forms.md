# HTML Forms

> Important concepts + organized reference for HTML forms and user input.

---

## 1. What is an HTML Form?

An HTML form is used to collect information from users.

Common examples:

* Login
* Registration
* Search
* Contact form
* Feedback
* Checkout
* User profile

Basic structure:

```html
<form>
    ...
</form>
```

Example:

```html
<form>

    <label for="name">
        Name
    </label>

    <input
        type="text"
        id="name"
        name="name"
    >

    <button type="submit">
        Submit
    </button>

</form>
```

---

# 2. `<form>` Element

The `<form>` element contains form controls.

```html
<form>
    ...
</form>
```

Important attributes:

```text
action
method
autocomplete
novalidate
target
enctype
```

---

# 3. `action` Attribute

`action` specifies where form data should be sent.

```html
<form action="/register">
    ...
</form>
```

For example:

```html
<form action="/login">
    ...
</form>
```

When the form is submitted, the browser sends the form data to the specified URL.

---

# 4. `method` Attribute

`method` specifies how form data is submitted.

Common methods:

```text
GET
POST
```

### GET

```html
<form action="/search" method="get">
    ...
</form>
```

GET data is commonly included in the URL.

Example:

```text
/search?query=javascript
```

Useful for:

* Search
* Filtering
* Reading/retrieving information

### POST

```html
<form action="/register" method="post">
    ...
</form>
```

POST sends data in the request body.

Commonly used for:

* Login
* Registration
* Creating data
* Updating data

---

# 5. `<label>`

`label` describes a form control.

```html
<label for="email">
    Email
</label>

<input
    type="email"
    id="email"
>
```

The `for` attribute should match the input's `id`.

```text
label for → input id
```

This relationship improves usability and accessibility.

---

# 6. `<input>`

`input` is one of the most commonly used form elements.

Basic example:

```html
<input type="text">
```

The `type` attribute determines what kind of input is expected.

---

# 7. Text Input

```html
<label for="name">
    Name
</label>

<input
    type="text"
    id="name"
    name="name"
>
```

Used for:

* Names
* Usernames
* Short text

---

# 8. Password Input

```html
<label for="password">
    Password
</label>

<input
    type="password"
    id="password"
    name="password"
>
```

Characters are visually hidden while typing.

---

# 9. Email Input

```html
<label for="email">
    Email
</label>

<input
    type="email"
    id="email"
    name="email"
>
```

Browsers can provide basic validation for email input.

---

# 10. Number Input

```html
<label for="age">
    Age
</label>

<input
    type="number"
    id="age"
    name="age"
>
```

Useful attributes:

```text
min
max
step
```

Example:

```html
<input
    type="number"
    min="1"
    max="100"
    step="1"
>
```

---

# 11. Telephone Input

```html
<label for="phone">
    Phone
</label>

<input
    type="tel"
    id="phone"
    name="phone"
>
```

Useful for telephone numbers.

---

# 12. URL Input

```html
<label for="website">
    Website
</label>

<input
    type="url"
    id="website"
    name="website"
>
```

Used for website URLs.

---

# 13. Search Input

```html
<label for="search">
    Search
</label>

<input
    type="search"
    id="search"
    name="search"
>
```

Useful for search fields.

---

# 14. Date Input

```html
<label for="date">
    Date
</label>

<input
    type="date"
    id="date"
    name="date"
>
```

Browser provides a date picker in supported environments.

---

# 15. Time Input

```html
<label for="time">
    Time
</label>

<input
    type="time"
    id="time"
    name="time"
>
```

---

# 16. Date and Time

```html
<input
    type="datetime-local"
    name="meeting"
>
```

Allows users to select a local date and time.

---

# 17. Month Input

```html
<input
    type="month"
    name="month"
>
```

Allows selection of a month and year.

---

# 18. Week Input

```html
<input
    type="week"
    name="week"
>
```

Allows selection of a week.

---

# 19. Checkbox

Checkboxes allow users to select zero or more options.

```html
<label>
    <input
        type="checkbox"
        name="skills"
        value="java"
    >
    Java
</label>

<label>
    <input
        type="checkbox"
        name="skills"
        value="javascript"
    >
    JavaScript
</label>
```

Multiple checkboxes can be selected.

---

# 20. Radio Buttons

Radio buttons are used when the user should select one option from a group.

```html
<p>Gender</p>

<label>
    <input
        type="radio"
        name="gender"
        value="male"
    >
    Male
</label>

<label>
    <input
        type="radio"
        name="gender"
        value="female"
    >
    Female
</label>
```

Important:

Radio buttons in the same group should use the same `name`.

---

# 21. File Input

Used to select a file from the user's device.

```html
<label for="resume">
    Resume
</label>

<input
    type="file"
    id="resume"
    name="resume"
>
```

Useful attributes:

```text
accept
multiple
```

Example:

```html
<input
    type="file"
    accept=".pdf"
>
```

---

# 22. Hidden Input

Hidden inputs are not displayed to the user.

```html
<input
    type="hidden"
    name="userId"
    value="101"
>
```

They can be used to submit additional data with a form.

---

# 23. Range Input

Creates a slider.

```html
<label for="volume">
    Volume
</label>

<input
    type="range"
    id="volume"
    min="0"
    max="100"
>
```

---

# 24. Color Input

Allows the user to select a color.

```html
<label for="color">
    Color
</label>

<input
    type="color"
    id="color"
>
```

---

# 25. Submit Input

```html
<input
    type="submit"
    value="Submit"
>
```

Submits the form.

---

# 26. Reset Input

```html
<input
    type="reset"
    value="Reset"
>
```

Resets form controls to their initial values.

---

# 27. `<button>`

The `<button>` element creates a button.

```html
<button>
    Click Me
</button>
```

For forms, explicitly specify the button type.

### Submit Button

```html
<button type="submit">
    Submit
</button>
```

### Reset Button

```html
<button type="reset">
    Reset
</button>
```

### Normal Button

```html
<button type="button">
    Click Me
</button>
```

---

# 28. Button Types

```text
submit
reset
button
```

### Important

Inside a form, a `<button>` without an explicit `type` can behave as a submit button.

Prefer:

```html
<button type="button">
    Open
</button>
```

when the button should not submit the form.

---

# 29. `<textarea>`

Used for multi-line text.

```html
<label for="message">
    Message
</label>

<textarea
    id="message"
    name="message"
    rows="5"
    cols="30"
></textarea>
```

Common uses:

* Messages
* Feedback
* Comments
* Descriptions

---

# 30. `<select>`

Creates a dropdown menu.

```html
<label for="country">
    Country
</label>

<select
    id="country"
    name="country"
>

    <option value="india">
        India
    </option>

    <option value="usa">
        USA
    </option>

    <option value="uk">
        UK
    </option>

</select>
```

---

# 31. `<option>`

Defines an option inside `<select>`.

```html
<option value="java">
    Java
</option>
```

The `value` is the data submitted with the form.

---

# 32. `<optgroup>`

Groups related options.

```html
<select name="course">

    <optgroup label="Programming">

        <option value="java">
            Java
        </option>

        <option value="javascript">
            JavaScript
        </option>

    </optgroup>

    <optgroup label="Frontend">

        <option value="html">
            HTML
        </option>

        <option value="css">
            CSS
        </option>

    </optgroup>

</select>
```

---

# 33. `<datalist>`

Provides predefined suggestions for an input.

```html
<label for="browser">
    Browser
</label>

<input
    list="browsers"
    id="browser"
    name="browser"
>

<datalist id="browsers">

    <option value="Chrome">
    <option value="Firefox">
    <option value="Edge">
    <option value="Safari">

</datalist>
```

The user can select a suggestion or enter another value.

---

# 34. `<fieldset>`

Groups related form controls.

```html
<fieldset>

    <legend>
        Personal Information
    </legend>

    <label for="name">
        Name
    </label>

    <input
        type="text"
        id="name"
    >

</fieldset>
```

---

# 35. `<legend>`

Provides a caption for a `<fieldset>`.

```html
<fieldset>

    <legend>
        Account Information
    </legend>

    ...

</fieldset>
```

---

# 36. `name` Attribute

The `name` attribute identifies the form data when it is submitted.

```html
<input
    type="text"
    name="username"
>
```

Example:

```text
username=rabindra
```

Without an appropriate `name`, a form control may not contribute its value to form submission.

---

# 37. `value` Attribute

Specifies the value associated with a form control.

```html
<input
    type="text"
    name="username"
    value="Rabindra"
>
```

For buttons and options, `value` also determines submitted data.

---

# 38. `placeholder`

Provides a hint about expected input.

```html
<input
    type="text"
    placeholder="Enter your name"
>
```

Important:

`placeholder` is a hint, not a replacement for a `<label>`.

---

# 39. `required`

Makes a field required.

```html
<input
    type="email"
    name="email"
    required
>
```

The browser can prevent submission when the required field is empty.

---

# 40. `readonly`

Makes a field read-only.

```html
<input
    type="text"
    value="Rabindra"
    readonly
>
```

The user can usually select the value but cannot edit it.

---

# 41. `disabled`

Disables a form control.

```html
<input
    type="text"
    disabled
>
```

Disabled controls generally cannot be edited or focused and are not submitted with the form.

---

# 42. `checked`

Preselects a checkbox or radio button.

```html
<input
    type="checkbox"
    checked
>
```

Radio example:

```html
<input
    type="radio"
    name="gender"
    value="male"
    checked
>
```

---

# 43. `selected`

Preselects an option.

```html
<select>

    <option value="java">
        Java
    </option>

    <option
        value="javascript"
        selected
    >
        JavaScript
    </option>

</select>
```

---

# 44. `multiple`

Allows multiple values where supported.

### Multiple Files

```html
<input
    type="file"
    multiple
>
```

### Multiple Select

```html
<select
    name="skills"
    multiple
>

    <option value="java">
        Java
    </option>

    <option value="javascript">
        JavaScript
    </option>

    <option value="python">
        Python
    </option>

</select>
```

---

# 45. `min` and `max`

Used with numeric/date-related inputs.

```html
<input
    type="number"
    min="18"
    max="60"
>
```

---

# 46. `step`

Controls the allowed increment for suitable input types.

```html
<input
    type="number"
    min="0"
    max="100"
    step="5"
>
```

Possible values can follow increments such as:

```text
0
5
10
15
20
...
```

---

# 47. `minlength` and `maxlength`

Control text length.

```html
<input
    type="text"
    minlength="3"
    maxlength="20"
>
```

Useful for:

* Username
* Name
* Password
* Short text

---

# 48. `pattern`

Specifies a pattern that the input value should match.

```html
<input
    type="text"
    pattern="[A-Za-z]+"
>
```

The pattern uses a regular expression.

---

# 49. `autocomplete`

Provides browser hints for previously entered information.

```html
<input
    type="email"
    autocomplete="email"
>
```

Examples:

```text
name
email
username
current-password
new-password
tel
street-address
```

---

# 50. `autofocus`

Automatically focuses a form control when the page loads.

```html
<input
    type="text"
    autofocus
>
```

Use carefully because automatic focus can affect accessibility and user experience.

---

# 51. `multiple`

Used for multiple files or multiple selections.

```html
<input
    type="file"
    multiple
>
```

---

# 52. Form Validation

HTML provides built-in validation.

Common validation attributes:

```text
required
type
min
max
minlength
maxlength
pattern
```

Example:

```html
<form>

    <label for="email">
        Email
    </label>

    <input
        type="email"
        id="email"
        name="email"
        required
    >

    <label for="password">
        Password
    </label>

    <input
        type="password"
        id="password"
        name="password"
        minlength="8"
        required
    >

    <button type="submit">
        Register
    </button>

</form>
```

Browser validation provides a first layer of validation.

Server-side validation is still necessary for applications.

---

# 53. Complete Registration Form

```html
<form
    action="/register"
    method="post"
>

    <fieldset>

        <legend>
            Registration
        </legend>


        <div>

            <label for="name">
                Full Name
            </label>

            <input
                type="text"
                id="name"
                name="name"
                placeholder="Enter your name"
                autocomplete="name"
                required
            >

        </div>


        <div>

            <label for="email">
                Email
            </label>

            <input
                type="email"
                id="email"
                name="email"
                placeholder="Enter your email"
                autocomplete="email"
                required
            >

        </div>


        <div>

            <label for="password">
                Password
            </label>

            <input
                type="password"
                id="password"
                name="password"
                minlength="8"
                autocomplete="new-password"
                required
            >

        </div>


        <div>

            <label for="country">
                Country
            </label>

            <select
                id="country"
                name="country"
                required
            >

                <option value="">
                    Select Country
                </option>

                <option value="india">
                    India
                </option>

                <option value="usa">
                    USA
                </option>

            </select>

        </div>


        <div>

            <label for="message">
                About You
            </label>

            <textarea
                id="message"
                name="message"
                rows="5"
            ></textarea>

        </div>


        <div>

            <label>
                <input
                    type="checkbox"
                    name="terms"
                    required
                >

                I agree to the terms.

            </label>

        </div>


        <button type="submit">
            Register
        </button>

        <button type="reset">
            Reset
        </button>

    </fieldset>

</form>
```

---

# 54. Login Form

```html
<form
    action="/login"
    method="post"
>

    <label for="email">
        Email
    </label>

    <input
        type="email"
        id="email"
        name="email"
        autocomplete="username"
        required
    >


    <label for="password">
        Password
    </label>

    <input
        type="password"
        id="password"
        name="password"
        autocomplete="current-password"
        required
    >


    <button type="submit">
        Login
    </button>

</form>
```

---

# 55. Search Form

```html
<form
    action="/search"
    method="get"
>

    <label for="query">
        Search
    </label>

    <input
        type="search"
        id="query"
        name="q"
        placeholder="Search..."
    >

    <button type="submit">
        Search
    </button>

</form>
```

---

# 56. Contact Form

```html
<form
    action="/contact"
    method="post"
>

    <label for="name">
        Name
    </label>

    <input
        type="text"
        id="name"
        name="name"
        required
    >


    <label for="email">
        Email
    </label>

    <input
        type="email"
        id="email"
        name="email"
        required
    >


    <label for="message">
        Message
    </label>

    <textarea
        id="message"
        name="message"
        rows="6"
        required
    ></textarea>


    <button type="submit">
        Send Message
    </button>

</form>
```

---

# 57. Form Accessibility Basics

### Always associate labels with controls

Good:

```html
<label for="email">
    Email
</label>

<input
    id="email"
    type="email"
>
```

The `for` value matches the input `id`.

### Use meaningful labels

Avoid:

```html
<label>
    Enter
</label>
```

Prefer:

```html
<label for="email">
    Email Address
</label>
```

### Group related controls

Use:

```html
<fieldset>
    <legend>Gender</legend>
    ...
</fieldset>
```

### Do not rely only on placeholder text

Prefer:

```html
<label for="username">
    Username
</label>

<input
    id="username"
    placeholder="Enter username"
>
```

---

# 58. Important Input Types

```text
text
password
email
number
tel
url
search
date
time
datetime-local
month
week
checkbox
radio
file
hidden
range
color
submit
reset
button
```

---

# 59. Form Elements Quick Reference

| Element    | Purpose                 |
| ---------- | ----------------------- |
| `form`     | Form container          |
| `label`    | Label for control       |
| `input`    | Single-line/form input  |
| `textarea` | Multi-line input        |
| `select`   | Dropdown                |
| `option`   | Dropdown option         |
| `optgroup` | Groups options          |
| `datalist` | Input suggestions       |
| `button`   | Button                  |
| `fieldset` | Groups related controls |
| `legend`   | Fieldset caption        |

---

# 60. Important Form Attributes

| Attribute      | Purpose                    |
| -------------- | -------------------------- |
| `action`       | Submission destination     |
| `method`       | GET or POST                |
| `name`         | Identifies submitted data  |
| `value`        | Control value              |
| `placeholder`  | Input hint                 |
| `required`     | Required field             |
| `readonly`     | Prevents editing           |
| `disabled`     | Disables control           |
| `checked`      | Preselects checkbox/radio  |
| `selected`     | Preselects option          |
| `multiple`     | Allows multiple selections |
| `min`          | Minimum value              |
| `max`          | Maximum value              |
| `step`         | Allowed increment          |
| `minlength`    | Minimum text length        |
| `maxlength`    | Maximum text length        |
| `pattern`      | Validation pattern         |
| `autocomplete` | Browser autofill hint      |
| `autofocus`    | Initial focus              |

---

# Key Takeaways

1. `<form>` is the main container for user input.
2. `<label>` should be properly associated with form controls.
3. `<input>` supports many different input types.
4. `name` is important when submitting form data.
5. `GET` is commonly used for retrieving/searching data.
6. `POST` is commonly used when sending data to the server.
7. `required`, `minlength`, `maxlength`, `pattern`, and input types provide browser-side validation.
8. `<textarea>` is used for multi-line input.
9. `<select>`, `<option>`, and `<optgroup>` create dropdown controls.
10. `<fieldset>` and `<legend>` group related controls.
11. Use semantic labels and structure to make forms easier to use and more accessible.
12. Client-side validation is useful, but server-side validation is still required for real applications.
