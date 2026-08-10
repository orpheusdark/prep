# 📁 FOLDER 01 — HTML FUNDAMENTALS ⭐ HIGH PRIORITY

---

## 🧠 CONCEPT OVERVIEW

HTML (HyperText Markup Language) is the **skeleton** of every web page. It defines the structure and content using **elements/tags**.

- HTML5 is the current standard (adds semantic tags, video/audio, local storage).
- The browser parses HTML → builds the **DOM** → renders the page.

---

## 📋 KEY RULES TO REMEMBER

| Rule | Value |
|------|-------|
| `<!DOCTYPE html>` | Tells browser: use HTML5 |
| `id` | Unique per page. Used in CSS with `#`, JS with `getElementById` |
| `class` | Reusable. Multiple elements can share. CSS uses `.` |
| Block element | Takes full width. New line. Ex: `<div>`, `<p>`, `<h1>` |
| Inline element | Takes only content width. No new line. Ex: `<span>`, `<a>`, `<img>` |
| `alt` attribute | Shown if image fails; required for screen readers (accessibility) |
| Semantic tags | `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>` |

---

## ❓ QUESTIONS + SOLUTIONS

---

### Q1. What is HTML?

**What is being asked?** Define HTML simply.

**Solution:**
- HTML = HyperText Markup Language
- It structures content on the web using **tags/elements**
- Not a programming language — it's a **markup language**

**Final Answer:**
> HTML (HyperText Markup Language) is the standard markup language used to create and structure content on web pages using elements (tags).

**🧠 Remember:** HTML = **H**ow **T**ext **M**akes **L**ayout

**⚠️ Common mistake:** Saying HTML is a "programming language" — it is NOT.

---

### Q2. Difference between HTML and HTML5? ⭐

**Solution:**

| Feature | HTML | HTML5 |
|---------|------|-------|
| Semantic tags | No | Yes (`<header>`, `<nav>`, etc.) |
| Audio/Video | Plugin-based | Native `<audio>`, `<video>` |
| Local Storage | No | Yes |
| Form validation | No | Yes (required, email types) |
| DOCTYPE | Complex | Simple: `<!DOCTYPE html>` |

**Final Answer:**
> HTML5 adds semantic elements, native audio/video, local storage, form validation, and a simpler DOCTYPE declaration.

**🧠 Remember:** HTML5 = HTML + **semantics + storage + media**

---

### Q3. What is the purpose of `<!DOCTYPE html>`?

**Solution:**
- It declares the document type to the browser
- Tells the browser to use **HTML5 standard mode**
- Without it → browser may go into **quirks mode** (inconsistent rendering)

**Final Answer:**
> `<!DOCTYPE html>` is not a tag — it's a declaration that tells the browser to render the page in HTML5 standard mode.

**🧠 Remember:** DOCTYPE = "Dear browser, please use modern rules"

**⚠️ Common mistake:** Thinking it's an HTML tag — it's NOT (no closing tag, not case-sensitive in HTML5).

---

### Q4. What are semantic HTML elements? ⭐

**Solution:**
- Semantic elements **describe their meaning** to both the browser AND developer
- Examples: `<header>`, `<nav>`, `<main>`, `<footer>`, `<section>`, `<article>`, `<aside>`
- Benefits: **SEO** (search engines understand structure), **Accessibility** (screen readers), **Readability**

**Final Answer:**
> Semantic HTML elements are tags that clearly describe their purpose and content (e.g., `<header>`, `<article>`), improving SEO, accessibility, and code readability.

**🧠 Remember:** Semantic = has **meaning**, not just structure

---

### Q5. Difference between `<div>` and `<section>`?

| `<div>` | `<section>` |
|---------|-------------|
| Generic container | Semantic — represents a themed section |
| No meaning | Has meaning (a chapter/block of content) |
| Use for styling/JS hooks | Use for content grouping |

**🧠 Remember:** div = "dumb box", section = "smart block"

---

### Q6. Difference between `<section>` and `<article>`?

| `<section>` | `<article>` |
|-------------|-------------|
| Groups related content | Self-contained, independently publishable |
| Part of a page | Could live on its own (blog post, news article) |

**🧠 Remember:** article = "standalone content you could share elsewhere"

---

### Q7. Purpose of `<header>`, `<nav>`, `<main>`, `<footer>`?

| Tag | Purpose |
|-----|---------|
| `<header>` | Top of page/section: logo, title, heading |
| `<nav>` | Navigation links |
| `<main>` | Primary unique content (only ONE per page) |
| `<footer>` | Bottom: copyright, links, contact |

---

### Q8. Difference between `<b>` and `<strong>`?

| `<b>` | `<strong>` |
|-------|-----------|
| Visual — bold only | Semantic — important content |
| No meaning to screen readers | Screen readers emphasize it |

**🧠 Remember:** strong = **bold with meaning**

---

### Q9. Difference between `<i>` and `<em>`?

| `<i>` | `<em>` |
|-------|--------|
| Visual — italic only | Semantic — stressed emphasis |

**🧠 Remember:** em = **italic with stress**

---

### Q10. What is the purpose of the `alt` attribute? ⭐

**Solution:**
- Shows **descriptive text** if image fails to load
- Used by **screen readers** for visually impaired users
- Improves **SEO** (search engines read alt text)

**What happens without alt?**
- Screen readers say "image" — useless for accessibility
- SEO loses context

**Final Answer:**
> The `alt` attribute provides alternative text for images, displayed when the image cannot load and read by screen readers for accessibility.

---

### Q11. Difference between `id` and `class`? ⭐

| Feature | `id` | `class` |
|---------|------|---------|
| Uniqueness | Unique — one per page | Reusable — many elements |
| CSS selector | `#myId` | `.myClass` |
| JS access | `getElementById()` | `getElementsByClassName()` |
| Multiple on element | Only one id per element | Can have multiple classes |

**Final Answer:**
> `id` is unique per page; `class` is reusable across multiple elements. An element can have multiple classes but only one id.

**🧠 Remember:** id = **Identity card** (unique), class = **uniform** (many wear it)

---

### Q12. What is the purpose of the `<form>` element?

**Solution:**
- Container for user input elements
- Collects data and submits it to a server
- `action` attribute = where to send data
- `method` attribute = GET or POST

---

### Q13. Difference between GET and POST in forms? ⭐

| Feature | GET | POST |
|---------|-----|------|
| Data location | URL query string | Request body |
| Security | Less secure (visible in URL) | More secure |
| Use case | Search, filtering | Login, form submission |
| Bookmarkable | Yes | No |
| Data length | Limited | Unlimited |

**🧠 Remember:** GET = **G**et data (visible), POST = **P**ost data (hidden in body)

---

### Q14. Input type differences?

| Type | Purpose |
|------|---------|
| `text` | Plain text |
| `email` | Email format validation |
| `password` | Hidden text |
| `number` | Numeric input |
| `checkbox` | Multiple selection |

---

### Q15. What is the DOM? ⭐

**Solution:**
- DOM = Document Object Model
- Browser's **in-memory representation** of the HTML page as a tree
- JavaScript uses DOM to read, modify, add, delete elements
- Is the DOM the same as HTML? **NO** — DOM is JavaScript's live view of the page; HTML is the source file

**Final Answer:**
> The DOM is a tree-like data structure created by the browser from the HTML source. JavaScript uses it to dynamically read and manipulate page content.

**🧠 Remember:** DOM = the browser's **living, interactive version** of your HTML

---

### Q16. What is the difference between block and inline elements? ⭐

| Block | Inline |
|-------|--------|
| Takes full width | Takes content width only |
| Starts on new line | Stays on same line |
| `<div>`, `<p>`, `<h1>`, `<ul>` | `<span>`, `<a>`, `<img>`, `<strong>` |

---

## 🔑 QUICK MEMORY TRICKS

- **DOCTYPE** → "HTML5 please"
- **semantic** → "tag with a job title"
- **id = unique** (like your ID card), **class = shared** (like a team uniform)
- **GET = visible URL**, **POST = hidden body**
- **DOM** = browser's live interactive HTML tree
- **block = full width + new line**, **inline = fits content + same line**

---

## ⚠️ COMMON MISTAKES

1. Using `<div>` everywhere instead of semantic tags
2. Multiple elements with the same `id`
3. Saying HTML is a programming language
4. Confusing DOM with the HTML source file
5. Forgetting `alt` on `<img>` tags
