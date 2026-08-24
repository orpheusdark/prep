# HTML + CSS COMPLETE PREPARATION
## Tech Passport Phase 1

---

# PART 1 — HTML FUNDAMENTALS

## 1.1 HTML Document Structure

```html
<!DOCTYPE html>          <!-- Declares HTML5 -->
<html lang="en">         <!-- Root element -->
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title</title>   <!-- Shows in browser tab -->
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <!-- Visible content goes here -->
    <h1>Hello World</h1>
</body>
</html>
```

> EXAM TIP: `<!DOCTYPE html>` is NOT a tag — it's a declaration. It tells the browser this is HTML5.

## 1.2 Tags vs Elements vs Attributes

```
Tag: <p>
Element: <p>This is text</p>   (opening tag + content + closing tag)
Attribute: <a href="url">Link</a>   (href is attribute, "url" is value)
Self-closing: <img src="x.jpg"> or <br> or <input>
```

## 1.3 Headings

```html
<h1>Biggest Heading</h1>   <!-- Only ONE per page (SEO rule) -->
<h2>Section Heading</h2>
<h3>Sub-section</h3>
<h4>...</h4>
<h5>...</h5>
<h6>Smallest Heading</h6>
```

## 1.4 Text Elements

```html
<p>Paragraph</p>
<br>          <!-- Line break (self-closing) -->
<hr>          <!-- Horizontal rule (line) -->
<strong>Bold</strong>    <!-- semantic: important -->
<b>Bold</b>             <!-- just visual bold -->
<em>Italic</em>          <!-- semantic: emphasis -->
<i>Italic</i>            <!-- just visual italic -->
<mark>Highlighted</mark>
<del>Strikethrough</del>
<sup>Superscript</sup>   <!-- 2<sup>3</sup> = 2³ -->
<sub>Subscript</sub>     <!-- H<sub>2</sub>O -->
<code>Code text</code>
<pre>Preformatted text</pre>
```

## 1.5 Lists

```html
<!-- Unordered list -->
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
</ul>

<!-- Ordered list -->
<ol>
    <li>First</li>
    <li>Second</li>
</ol>

<!-- Nested list -->
<ul>
    <li>Fruits
        <ul>
            <li>Apple</li>
            <li>Banana</li>
        </ul>
    </li>
</ul>

<!-- Definition list -->
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language</dd>
</dl>
```

## 1.6 Links

```html
<a href="https://www.example.com">Visit Example</a>
<a href="about.html">About Page</a>           <!-- relative -->
<a href="#section1">Jump to Section 1</a>     <!-- anchor link -->
<a href="mailto:test@email.com">Email</a>      <!-- email -->
<a href="tel:+1234567890">Call</a>             <!-- phone -->
<a href="page.html" target="_blank">Open in new tab</a>
```

> EXAM TIP: `target="_blank"` opens link in new tab. The `#` in href refers to an element's id.

## 1.7 Images

```html
<img src="image.jpg" alt="Description of image" width="300" height="200">
```

> MUST REMEMBER:
> - `alt` is required for accessibility (and SEO)
> - `src` is the image path
> - `width` and `height` prevent layout shift

## 1.8 Tables

```html
<table border="1">
    <thead>
        <tr>
            <th>Name</th>    <!-- th = table header (bold, centered) -->
            <th>Age</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Alice</td>   <!-- td = table data -->
            <td>25</td>
        </tr>
        <tr>
            <td>Bob</td>
            <td>30</td>
        </tr>
    </tbody>
</table>
```

**Spanning:**
```html
<td colspan="2">Spans 2 columns</td>
<td rowspan="2">Spans 2 rows</td>
```

## 1.9 Forms

```html
<form action="/submit" method="POST">

    <!-- Text input -->
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" placeholder="Enter name" required>

    <!-- Password -->
    <input type="password" name="pass">

    <!-- Email -->
    <input type="email" name="email">

    <!-- Number -->
    <input type="number" name="age" min="0" max="150">

    <!-- Radio buttons -->
    <input type="radio" name="gender" value="male" id="male">
    <label for="male">Male</label>
    <input type="radio" name="gender" value="female" id="female">
    <label for="female">Female</label>

    <!-- Checkbox -->
    <input type="checkbox" name="agree" id="agree">
    <label for="agree">I agree</label>

    <!-- Select dropdown -->
    <select name="country">
        <option value="us">USA</option>
        <option value="uk">UK</option>
        <option value="in" selected>India</option>
    </select>

    <!-- Textarea -->
    <textarea name="message" rows="4" cols="30">Default text</textarea>

    <!-- Submit button -->
    <button type="submit">Submit</button>
    <input type="submit" value="Submit">
    <input type="reset" value="Reset">

</form>
```

> EXAM TIP: `method="GET"` appends data to URL. `method="POST"` sends data in request body (more secure).
> `for` in `<label>` must match `id` in `<input>` for accessibility.

## 1.10 Semantic HTML

| Semantic Tag | Purpose |
|-------------|---------|
| `<header>` | Top of page/section |
| `<nav>` | Navigation links |
| `<main>` | Main content |
| `<section>` | Thematic section |
| `<article>` | Self-contained content |
| `<aside>` | Side content (sidebar) |
| `<footer>` | Bottom of page |
| `<figure>` | Image with caption |
| `<figcaption>` | Caption for figure |
| `<time>` | Date/time |
| `<mark>` | Highlighted text |

> EXAM TIP: Semantic tags improve accessibility and SEO. Using `<div>` everywhere is non-semantic.

## 1.11 div vs span

| | div | span |
|-|-----|------|
| Type | Block element | Inline element |
| Default display | Block (new line) | Inline (same line) |
| Purpose | Group block content | Style inline text |
| Example | `<div id="container">` | `<span style="color:red">` |

## 1.12 Block vs Inline Elements

**Block elements** (take full width, start on new line):
`<div>`, `<p>`, `<h1>-<h6>`, `<ul>`, `<ol>`, `<li>`, `<table>`, `<header>`, `<section>`, `<form>`

**Inline elements** (only take content width, no new line):
`<span>`, `<a>`, `<img>`, `<strong>`, `<em>`, `<input>`, `<button>`, `<label>`

## 1.13 id vs class

```html
<div id="main-container">   <!-- unique, used once -->
<p class="highlight">       <!-- can be reused multiple times -->
<p class="highlight large"> <!-- multiple classes with space -->
```

| | id | class |
|-|----|----|
| Symbol in CSS | # | . |
| Uniqueness | Must be unique per page | Can be reused |
| JavaScript | getElementById | getElementsByClassName |
| Specificity | Higher | Lower |

---

# PART 2 — CSS FUNDAMENTALS

## 2.1 CSS Selectors

```css
/* Element selector */
p { color: red; }

/* Class selector */
.highlight { background: yellow; }

/* ID selector */
#main { width: 100%; }

/* Universal selector */
* { margin: 0; padding: 0; }

/* Descendant selector */
div p { color: blue; }    /* p INSIDE div */

/* Child selector */
div > p { color: green; } /* p that is DIRECT child of div */

/* Adjacent sibling */
h1 + p { margin-top: 10px; }  /* p immediately after h1 */

/* Attribute selector */
input[type="text"] { border: 1px solid blue; }

/* Pseudo-class */
a:hover { color: red; }
li:first-child { font-weight: bold; }
li:last-child { color: gray; }
li:nth-child(2) { color: blue; }

/* Pseudo-element */
p::before { content: ">> "; }
p::after { content: " <<"; }
p::first-letter { font-size: 2em; }
```

## 2.2 CSS Specificity — MUST KNOW

Specificity determines which CSS rule wins when multiple rules apply to the same element.

**Specificity order (highest to lowest):**
1. `!important` (overrides everything — avoid using)
2. Inline styles: `style="..."` (1000 points)
3. ID selectors: `#id` (100 points)
4. Class, attribute, pseudo-class: `.class`, `[attr]`, `:hover` (10 points)
5. Element, pseudo-element: `p`, `::before` (1 point)

**Examples:**
```css
p { color: black; }           /* specificity: 0,0,1 */
.text { color: blue; }        /* specificity: 0,1,0 */
#main { color: green; }       /* specificity: 1,0,0 */
#main .text { color: red; }   /* specificity: 1,1,0 */
```

> EXAM TIP: When specificity is equal, the LAST rule in CSS wins (cascade).

## 2.3 The Box Model — CRITICAL

Every HTML element is a box with these layers (from inside out):

```
+------------------------------------------+
|              margin                       |
|   +----------------------------------+   |
|   |           border                 |   |
|   |   +--------------------------+   |   |
|   |   |        padding           |   |   |
|   |   |   +------------------+   |   |   |
|   |   |   |    content       |   |   |   |
|   |   |   +------------------+   |   |   |
|   |   +--------------------------+   |   |
|   +----------------------------------+   |
+------------------------------------------+
```

```css
div {
    width: 300px;      /* content width */
    padding: 20px;     /* inside border */
    border: 5px solid; /* the border */
    margin: 30px;      /* outside border */
}
/* Total width = 300 + 20*2 + 5*2 + 30*2 = 410px */
```

> MOST COMMON TRAP: By default, `width` = content width only. Border and padding add to total size.
> Use `box-sizing: border-box` to make width include padding + border.

```css
* {
    box-sizing: border-box;  /* width now includes padding + border */
}
```

## 2.4 Margin vs Padding

| | Margin | Padding |
|-|--------|---------|
| Position | Outside border | Inside border |
| Background color | Transparent (not affected) | Shows background color |
| Collapse | YES (vertical margins collapse) | No collapse |
| Auto | `margin: auto` centers elements | No auto centering |

```css
/* Shorthand */
margin: 10px;                   /* all 4 sides */
margin: 10px 20px;              /* top/bottom left/right */
margin: 10px 20px 30px 40px;    /* top right bottom left (clockwise) */

/* Individual */
margin-top: 10px;
margin-right: 20px;
margin-bottom: 10px;
margin-left: 20px;
```

## 2.5 Display Property

```css
display: block;         /* takes full width, new line */
display: inline;        /* only takes content width, same line */
display: inline-block;  /* same line BUT can set width/height */
display: none;          /* element gone, no space */
display: flex;          /* flexbox container */
display: grid;          /* grid container */
```

> COMMON TRAP: `display: none` removes element completely. `visibility: hidden` hides but KEEPS the space.

## 2.6 Position Property

```css
position: static;    /* default — normal flow */
position: relative;  /* moves relative to its normal position */
position: absolute;  /* moves relative to nearest positioned ancestor */
position: fixed;     /* stays fixed relative to viewport (scrolls with window = stays in place) */
position: sticky;    /* stays in position when scrolling reaches it */
```

```css
/* Example */
.box {
    position: relative;
    top: 20px;       /* moves 20px down from normal position */
    left: 50px;      /* moves 50px right from normal position */
}

.child {
    position: absolute;
    top: 0;
    right: 0;        /* top-right corner of nearest positioned parent */
}
```

> EXAM TIP: `position: absolute` is positioned relative to nearest ancestor that has `position` other than static.

## 2.7 z-index

```css
/* z-index only works on positioned elements (not static) */
.front { position: relative; z-index: 10; }   /* in front */
.back  { position: relative; z-index: 1; }    /* behind */
```

Higher z-index = appears in front.

## 2.8 Flexbox — HIGH PRIORITY

```css
/* Parent (flex container) */
.container {
    display: flex;

    /* Main axis direction */
    flex-direction: row;          /* default: left to right */
    flex-direction: column;       /* top to bottom */
    flex-direction: row-reverse;  /* right to left */

    /* Alignment on main axis */
    justify-content: flex-start;   /* default */
    justify-content: flex-end;
    justify-content: center;
    justify-content: space-between; /* equal gaps between items */
    justify-content: space-around;  /* equal space around items */
    justify-content: space-evenly;  /* equal space everywhere */

    /* Alignment on cross axis */
    align-items: stretch;    /* default */
    align-items: flex-start;
    align-items: flex-end;
    align-items: center;

    /* Wrapping */
    flex-wrap: nowrap;   /* default */
    flex-wrap: wrap;
}

/* Child (flex item) */
.item {
    flex: 1;             /* grow to fill available space */
    flex-grow: 2;        /* grow twice as much as others */
    align-self: center;  /* override align-items for this item */
    order: 2;            /* change order of items */
}
```

## 2.9 CSS Colors

```css
color: red;              /* named color */
color: #FF5733;          /* hex (RGB in hex) */
color: rgb(255, 87, 51); /* RGB */
color: rgba(255, 87, 51, 0.5); /* RGB + alpha (transparency) */
color: hsl(14, 100%, 60%);    /* hue, saturation, lightness */
```

## 2.10 CSS Fonts

```css
font-family: Arial, sans-serif;    /* with fallback */
font-size: 16px;                   /* in pixels */
font-size: 1.5rem;                 /* relative to root (usually 16px) */
font-size: 1.5em;                  /* relative to parent */
font-weight: bold;                 /* or 100-900 */
font-style: italic;
text-align: left | center | right | justify;
text-decoration: none | underline | line-through;
text-transform: uppercase | lowercase | capitalize;
line-height: 1.5;                  /* 1.5x font size */
letter-spacing: 2px;
```

## 2.11 CSS Units

| Unit | Type | Description |
|------|------|-------------|
| px | Absolute | Fixed pixels |
| % | Relative | Percentage of parent |
| em | Relative | Relative to parent font-size |
| rem | Relative | Relative to root (html) font-size |
| vw | Viewport | Percentage of viewport width |
| vh | Viewport | Percentage of viewport height |

> EXAM TIP: `rem` is safer than `em` because `em` compounds (nested elements multiply). `rem` always refers to root.

## 2.12 Basic Responsive Design

```css
/* Media query — applies CSS only at certain screen sizes */
@media (max-width: 768px) {
    .container {
        flex-direction: column;  /* stack items vertically on mobile */
    }
    .sidebar {
        display: none;           /* hide sidebar on small screens */
    }
}

/* Mobile-first approach */
/* Default: mobile styles */
.grid { display: block; }

/* At 768px and above (tablet/desktop) */
@media (min-width: 768px) {
    .grid { display: flex; }
}
```

---

# PART 3 — HTML MCQs

**H1:** Which tag is used for the MOST important heading?
A) `<h6>` B) `<heading>` C) `<h1>` D) `<head>`
**Answer: C**

**H2:** Which attribute specifies a link destination?
A) src B) href C) url D) link
**Answer: B**

**H3:** Which is a self-closing tag?
A) `<div>` B) `<p>` C) `<br>` D) `<span>`
**Answer: C**

**H4:** What does `colspan="2"` do in a table?
A) Spans 2 rows B) Spans 2 columns C) Makes 2 tables D) Error
**Answer: B**

**H5:** Which form method sends data in the URL?
A) POST B) PUT C) GET D) DELETE
**Answer: C**

**H6:** The `alt` attribute on `<img>` is used for:
A) Alternative image B) Accessibility/screen readers C) Image link D) Both A and B
**Answer: D**

**H7:** What does `target="_blank"` do in `<a>` tag?
A) Opens in same tab B) Opens in new tab C) Downloads file D) Disabled link
**Answer: B**

**H8:** Which is NOT a semantic HTML5 tag?
A) `<article>` B) `<div>` C) `<section>` D) `<aside>`
**Answer: B**

**H9:** `<label for="x">` connects to `<input id="x">`. This improves:
A) SEO B) Styling C) Accessibility D) Performance
**Answer: C**

**H10:** `<thead>`, `<tbody>`, `<tfoot>` are children of which tag?
A) `<tr>` B) `<td>` C) `<table>` D) `<div>`
**Answer: C**

---

# PART 4 — CSS MCQs and Output Questions

**C1:** Which has highest specificity?
A) `p { }` B) `.class { }` C) `#id { }` D) `* { }`
**Answer: C** (ID > class > element > universal)

**C2:** What is the total width of a box with: width=200px, padding=10px, border=5px, margin=20px?
A) 200px B) 230px C) 250px D) 270px
**Answer: C** (200 + 10*2 + 5*2 = 230px; margin doesn't count in box width)

> Wait — box width = 200 + 20 + 10 = 230. Total space taken = 230 + 40 (margin) = 270. Box itself = 230px.

**C3:** `display: none` vs `visibility: hidden`:
A) Same thing B) none removes space; hidden keeps space C) hidden removes space; none keeps it D) Both keep space
**Answer: B**

**C4:** In flexbox, `justify-content: space-between` means:
A) Items at start B) Items at end C) Equal gaps between items D) Items centered
**Answer: C**

**C5:** Which property makes an element positioned relative to viewport?
A) position: relative B) position: absolute C) position: fixed D) position: static
**Answer: C**

**C6:** What does `flex-direction: column` do?
A) Items go left to right B) Items go top to bottom C) Items wrap D) Items reverse
**Answer: B**

**C7:** CSS shorthand `padding: 10px 20px` means:
A) All sides 10px B) Top/bottom 10px, left/right 20px C) Left/right 10px, top/bottom 20px D) Error
**Answer: B**

**C8:** Which selector selects `<p>` elements inside `<div>` only?
A) `p div` B) `div p` C) `div + p` D) `p.div`
**Answer: B**

**C9:** `align-items: center` centers items on which axis in a flex row?
A) Main axis (horizontal) B) Cross axis (vertical) C) Both D) Neither
**Answer: B**

**C10:** What does `box-sizing: border-box` do?
A) Makes border visible B) Makes width include padding+border C) Removes border D) Centers the box
**Answer: B**

---

# PART 5 — FIND THE MISTAKE QUESTIONS

**BUG1:**
```html
<form action="/submit" method="post">
    <input type=text name="username">
    <input type="submit">
</form>
```
**Bug:** `type=text` — attribute value must be in quotes: `type="text"`

**BUG2:**
```html
<table>
    <tr>
        <td>Name</td>
        <td>Age</td>
    <tr>
        <td>Alice</td>
        <td>25</td>
    </tr>
</table>
```
**Bug:** First `<tr>` is not closed with `</tr>`

**BUG3:**
```html
<img href="photo.jpg" alt="My Photo">
```
**Bug:** `href` should be `src` for images.

**BUG4:**
```css
.box {
    margin: inside;
    padding: outside;
}
```
**Bug:** Margin is OUTSIDE, padding is INSIDE. Values are wrong.

**BUG5:**
```css
#header {
    display: flex;
    justify-items: center;   /* Bug! */
}
```
**Bug:** `justify-items` doesn't exist in flexbox. Use `justify-content: center`.

---

# PART 6 — SMALL HTML TASKS

**Task 1:** Create a simple form with Name, Email, and Submit button.
```html
<form action="/register" method="POST">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required><br>
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required><br>
    <button type="submit">Register</button>
</form>
```

**Task 2:** Create a 2-column, 3-row table.
```html
<table border="1">
    <tr><th>Product</th><th>Price</th></tr>
    <tr><td>Apple</td><td>$1</td></tr>
    <tr><td>Banana</td><td>$0.5</td></tr>
</table>
```

**Task 3:** Navigation bar with 3 links.
```html
<nav>
    <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/about">About</a></li>
        <li><a href="/contact">Contact</a></li>
    </ul>
</nav>
```
