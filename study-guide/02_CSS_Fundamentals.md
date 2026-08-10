# 📁 FOLDER 02 — CSS FUNDAMENTALS ⭐ HIGH PRIORITY

---

## 🧠 CONCEPT OVERVIEW

CSS (Cascading Style Sheets) controls the **visual presentation** of HTML elements — colors, layout, spacing, typography, and responsiveness.

---

## 📋 KEY RULES TO REMEMBER

| Concept | Key Fact |
|---------|----------|
| Three ways to apply CSS | Inline > Internal > External (priority) |
| Specificity order | `!important` > inline > ID > class > element |
| Box model | content → padding → border → margin (inside-out) |
| `box-sizing: border-box` | padding + border included IN the width |
| `display: none` | removes from layout | `visibility: hidden` | hides but keeps space |
| Flexbox main axis | direction of `flex-direction` |
| Flexbox cross axis | perpendicular to main axis |

---

## ❓ QUESTIONS + SOLUTIONS

---

### Q1. What is CSS? / Three ways to apply CSS?

**Three ways:**

| Method | Example | Priority |
|--------|---------|----------|
| Inline | `style="color:red"` | Highest |
| Internal | `<style>` in `<head>` | Medium |
| External | `<link rel="stylesheet">` | Lowest |

**🧠 Remember:** "I In Ex" — Inline > Internal > External (priority)

---

### Q2. What is a CSS selector?

- Selects HTML elements to apply styles
- Types:

| Selector | Syntax | Specificity |
|----------|--------|-------------|
| Element | `p {}` | 0-0-1 |
| Class | `.box {}` | 0-1-0 |
| ID | `#nav {}` | 1-0-0 |
| Universal | `* {}` | 0-0-0 |
| Attribute | `[type="text"]` | 0-1-0 |

---

### Q3. What is specificity? Calculate: `#container .box p` ⭐

**Specificity scoring:** `(IDs, Classes, Elements)`

- `#container` → 1 ID → **1-0-0**
- `.box` → 1 class → **0-1-0**
- `p` → 1 element → **0-0-1**
- **Total: 1-1-1 = 111**

**Rule:** Higher number wins. `!important` overrides everything.

**Final Answer:**
> Specificity of `#container .box p` = **1-1-1** (one ID, one class, one element).

**🧠 Remember:** Count **IDs first, then Classes, then Elements** (left to right priority)

**⚠️ Common mistake:** Adding specificity as 1+1+1=3. It's positional, not additive. 0-0-10 loses to 0-1-0.

---

### Q4. What is the CSS Box Model? ⭐

**Every HTML element is a box with 4 layers (inside-out):**

```
+---------------------------+
|        MARGIN             |  ← outside space (from other elements)
|  +---------------------+  |
|  |      BORDER         |  |  ← visible border
|  |  +---------------+  |  |
|  |  |    PADDING    |  |  |  ← inner space (between content & border)
|  |  |  +---------+  |  |  |
|  |  |  | CONTENT |  |  |  |  ← actual text/image
|  |  |  +---------+  |  |  |
|  |  +---------------+  |  |
|  +---------------------+  |
+---------------------------+
```

**Margin vs Padding:**
| Feature | Padding | Margin |
|---------|---------|--------|
| Location | Inside border | Outside border |
| Background color | Shows through | Transparent |
| Use | Inner spacing | Outer spacing from other elements |

**Final Answer:**
> The CSS box model is content + padding + border + margin. Padding is inside the border (space between content and border); margin is outside (space between elements).

**🧠 Remember:** **C-P-B-M** → "Can Pandas Bear Mountains" (Content, Padding, Border, Margin)

---

### Q5. What is `box-sizing: border-box`? ⭐

**Problem without it:**
```css
.box { width: 300px; padding: 20px; } 
/* Actual width = 300 + 20 + 20 = 340px — SURPRISE! */
```

**With `border-box`:**
```css
.box { box-sizing: border-box; width: 300px; padding: 20px; }
/* Actual width = exactly 300px — padding included inside */
```

**Final Answer:**
> `box-sizing: border-box` makes padding and border included within the declared width, preventing layout surprises.

**🧠 Remember:** border-box = "what I declare is what I get"

---

### Q6. Display: block vs inline vs inline-block ⭐

| Property | Block | Inline | Inline-block |
|----------|-------|--------|--------------|
| Takes full width | Yes | No | No |
| New line | Yes | No | No |
| Width/Height settable | Yes | No | Yes |
| Examples | `<div>`, `<p>` | `<span>`, `<a>` | `<button>`, `<img>` |

**`display: none`** → Element completely removed from layout + not visible
**`visibility: hidden`** → Element invisible BUT still takes space in layout

---

### Q7. CSS Positioning ⭐

| Value | Behavior |
|-------|----------|
| `static` | Default. Flows normally |
| `relative` | Positioned relative to its normal position. Still in flow |
| `absolute` | Removed from flow. Positioned relative to nearest `position: relative` ancestor |
| `fixed` | Removed from flow. Stays fixed relative to viewport (doesn't scroll) |
| `sticky` | Like relative until you scroll past it — then sticks |

**z-index:** Controls stacking order. Higher z-index = on top. Only works on positioned elements (not static).

**🧠 Remember:**
- `relative` = "I moved but I still own my space"
- `absolute` = "I escaped — position relative to parent"
- `fixed` = "I'm glued to the screen"
- `sticky` = "I follow until a point, then stick"

---

### Q8. What is Flexbox? ⭐

**Concept:**
- 1D layout system (one row OR one column at a time)
- Parent = flex container (`display: flex`)
- Children = flex items

**Key properties:**

| Property | What it does | Values |
|----------|-------------|--------|
| `flex-direction` | Main axis direction | `row` (default), `column` |
| `justify-content` | Aligns items along **main axis** | `flex-start`, `center`, `space-between`, `space-around` |
| `align-items` | Aligns items along **cross axis** | `flex-start`, `center`, `stretch` |
| `flex-wrap` | Allows wrapping to next line | `wrap`, `nowrap` |
| `gap` | Space between items | `10px`, etc. |
| `align-content` | Aligns **rows** when wrapped | (like align-items but for multiple lines) |

**Main axis vs Cross axis:**
- `flex-direction: row` → Main = horizontal, Cross = vertical
- `flex-direction: column` → Main = vertical, Cross = horizontal

**🧠 Remember:** justify = **J**ust going along the main direction | align = **A**cross the cross

---

### Q9. How to center an element using Flexbox? ⭐

```css
.container {
  display: flex;
  justify-content: center;  /* horizontal center */
  align-items: center;      /* vertical center */
  height: 100vh;
}
```

**Final Answer:**
> Set `display: flex`, `justify-content: center`, and `align-items: center` on the parent container.

---

### Q10. CSS Grid vs Flexbox ⭐

| Feature | Flexbox | Grid |
|---------|---------|------|
| Dimensions | 1D (row or column) | 2D (rows AND columns) |
| Best for | Nav bars, card rows, single axis | Full page layouts, complex grids |
| Child placement | Automatic | Precise placement |

**`grid-template-columns`:**
```css
grid-template-columns: 1fr 1fr 1fr;   /* 3 equal columns */
grid-template-columns: repeat(3, 1fr); /* same thing */
grid-template-columns: 200px auto;     /* fixed + flexible */
```

---

### Q11. What is a media query? ⭐

```css
@media (max-width: 768px) {
  .container { flex-direction: column; }
}
```

- Used to apply different styles at different screen sizes
- **Mobile-first design:** Start with mobile styles, then add media queries for larger screens (`min-width`)
- **Desktop-first:** Start with desktop, use `max-width` for smaller screens

---

### Q12. CSS Units ⭐

| Unit | Meaning | Best for |
|------|---------|---------|
| `px` | Fixed pixels | Borders, shadows |
| `%` | Relative to parent | Widths, heights |
| `em` | Relative to parent font-size | Padding, margin (can cascade) |
| `rem` | Relative to root (html) font-size | Typography (consistent, no cascade) |
| `vh` | % of viewport height | Full-height sections |
| `vw` | % of viewport width | Full-width layouts |

**Why rem > px for typography?**
- User can increase browser font size → rem scales → px does NOT
- Accessible and consistent

---

### Q13. Pseudo-classes and Pseudo-elements

| Type | Syntax | Example |
|------|--------|---------|
| Pseudo-class | `:hover` | `a:hover {}` — styles on state |
| Pseudo-element | `::before` | `p::before {}` — inserts content before element |

**🧠 Remember:** `:` = state (class), `::` = element (inserts something)

---

## 🔑 QUICK MEMORY TRICKS

- Box model: **C-P-B-M** (Content Padding Border Margin)
- Specificity: Count IDs > Classes > Elements (never add them as plain numbers)
- Flexbox: justify = main axis, align = cross axis
- Center with flex: **justify + align = center, height needed**
- rem > px for fonts because rem respects browser settings
- `display: none` = gone from layout; `visibility: hidden` = invisible but space remains

---

## ⚠️ COMMON MISTAKES

1. Confusing `margin` and `padding` (margin = outside, padding = inside)
2. Not setting `height` on flex container when trying to vertically center
3. Using `position: absolute` without a `position: relative` parent
4. Adding specificity as plain numbers (0-10 beats 0-9, not 10 beats 9)
5. Forgetting `box-sizing: border-box` → unexpected layout widths
