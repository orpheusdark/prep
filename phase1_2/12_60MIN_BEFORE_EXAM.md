# 60 MINUTES BEFORE THE EXAM
## + 15-MINUTE FINAL CHECKLIST

---

# THE LAST 60 MINUTES — STRUCTURED REVISION

## Minute 0–10: Java Core Traps (MUST REVIEW)

```
== vs .equals()       → ALWAYS use .equals() for String comparison
String immutability   → toUpperCase() returns new string, original unchanged
arr.length            → field, no parentheses (vs String s.length())
(int) 9.9 = 9         → truncates, does NOT round
10 / 3 = 3            → integer division, NOT 3.33
x++ vs ++x            → post uses then increments; pre increments then uses
finally               → ALWAYS runs, even after return
super()               → MUST be first statement in child constructor
```

## Minute 10–20: OOP in 10 Minutes

```
Polymorphism:  Animal a = new Dog(); a.sound() → calls Dog's sound()
Overloading:   same class, same name, DIFFERENT parameters (compile time)
Overriding:    child class, same name, SAME parameters (runtime)
this           → current object (cannot use in static methods)
super          → parent class

abstract class → extends, can have constructors/fields
interface      → implements, no constructors (Java 7)

Access: private < default < protected < public
```

## Minute 20–30: DSA Quick Reference

```
Linear Search:  O(n), works on any array
Binary Search:  O(log n), REQUIRES SORTED array
Bubble Sort:    O(n²) worst, O(n) best, Space O(1)
Selection Sort: O(n²) always, exactly n-1 swaps
Insertion Sort: O(n) best (nearly sorted), O(n²) worst
Merge Sort:     O(n log n) always, Space O(n)
Quick Sort:     O(n log n) avg, O(n²) worst (sorted with bad pivot)

Stack: LIFO → push(top), pop(top), peek(top)
Queue: FIFO → enqueue(back), dequeue(front), peek(front)

O(1) < O(log n) < O(n) < O(n log n) < O(n²)
```

## Minute 30–40: Pattern + Loop Mental Trace

Practice tracing these in your head:

**Right triangle (n=3):**
```
i=1: j goes 1 to 1 → *
i=2: j goes 1 to 2 → * *
i=3: j goes 1 to 3 → * * *
```

**Pyramid (n=3):**
```
i=1: spaces=2, stars=1 →   *
i=2: spaces=1, stars=2 →  * *
i=3: spaces=0, stars=3 → * * *
```

**Key insight:** Outer loop = rows. Inner loop = what's in each row. Always analyze row-by-row.

## Minute 40–50: JavaScript + HTML + CSS Traps

```javascript
// JS TRAPS:
typeof null === "object"          // bug!
"5" + 3 === "53"                  // string concat
"5" - 3 === 2                     // numeric subtraction
0 == false   // true
0 === false  // false
[1,2,3].sort() // sorts as strings — use comparator!
var: hoisted (undefined); let/const: TDZ (ReferenceError)
```

```css
/* CSS TRAPS: */
Specificity: #id > .class > element
Margin = OUTSIDE border (transparent, can collapse vertically)
Padding = INSIDE border (shows background color)
display:none removes element; visibility:hidden keeps space
position:absolute → relative to nearest positioned ancestor
position:fixed → relative to VIEWPORT
justify-content → main axis; align-items → cross axis
```

```html
<!-- HTML TRAPS: -->
img uses src not href
label for="x" must match input id="x"
GET puts data in URL; POST in request body
Only ONE h1 per page
Semantic: nav, header, main, section, article, footer
```

## Minute 50–60: Git Commands

```bash
git init                    # new repo
git status                  # check state
git add .                   # stage all
git commit -m "msg"         # commit
git push                    # push to remote
git pull                    # pull from remote (fetch + merge)
git fetch                   # download only (no merge)

git branch feature          # create branch
git switch feature          # go to branch
git checkout -b feature     # create + switch
git merge feature           # merge into current

git clone <url>             # copy remote repo
origin = default remote name
.gitignore = list files to not track
GitHub Pages = free static site hosting
```

---

# THE 15-MINUTE FINAL CHECKLIST
## Only HIGH-VALUE facts — memorize these before entering the hall

### Java
- [ ] `String.equals()` NOT `==`
- [ ] Strings are immutable — methods return new strings
- [ ] `arr.length` (no parentheses)
- [ ] Integer division: `10/3 = 3` (not 3.33)
- [ ] `(int)9.9 = 9` (truncates)
- [ ] `x++` prints then increments; `++x` increments then prints
- [ ] `finally` always runs
- [ ] `super()` must be FIRST statement
- [ ] Default values: int→0, boolean→false, String→null
- [ ] `Animal a = new Dog(); a.method()` → calls Dog's method (polymorphism)
- [ ] Overloading=compile time, Overriding=runtime
- [ ] switch without break → falls through!
- [ ] do-while runs at least once
- [ ] No `this` in static methods
- [ ] Abstract class uses `extends`; Interface uses `implements`

### DSA
- [ ] Binary search → SORTED array, O(log n)
- [ ] Linear search → any array, O(n)
- [ ] Bubble sort → O(n²) worst, O(n) best
- [ ] Merge sort → O(n log n) always
- [ ] Stack = LIFO; Queue = FIFO
- [ ] O(1) < O(log n) < O(n) < O(n log n) < O(n²)
- [ ] mid = low + (high-low)/2 (not (low+high)/2)

### JavaScript
- [ ] `typeof null === "object"` (bug)
- [ ] `typeof [] === "object"` (arrays are objects)
- [ ] `0 == false` is true; `0 === false` is false
- [ ] `"5" + 3 = "53"` (concat); `"5" - 3 = 2` (numeric)
- [ ] `[10,9,2].sort()` gives [10,2,9] NOT [2,9,10]!
- [ ] `var` hoisted as undefined; `let` hoisted but TDZ
- [ ] `const` can't reassign, but can modify properties
- [ ] `arr.map()`, `arr.filter()` → return NEW arrays
- [ ] Truthy: [], {}, "0", -1. Falsy: 0, "", null, undefined

### HTML
- [ ] `<img src="...">` NOT href
- [ ] `alt` attribute = accessibility
- [ ] `label for` = `input id`
- [ ] GET = data in URL; POST = data in body
- [ ] Semantic tags: nav, header, main, section, article, footer, aside

### CSS
- [ ] Specificity: inline > #id > .class > element
- [ ] Last rule wins when equal specificity
- [ ] margin = OUTSIDE; padding = INSIDE
- [ ] `display:none` removes element; `visibility:hidden` keeps space
- [ ] `justify-content` = main axis; `align-items` = cross axis
- [ ] `position:fixed` = viewport; `position:absolute` = positioned ancestor
- [ ] `box-sizing:border-box` → width includes padding + border

### Git
- [ ] `git add .` → `git commit -m "msg"` → `git push`
- [ ] `git fetch` = download only; `git pull` = download + merge
- [ ] `git checkout -b name` = create + switch branch
- [ ] `git merge branch` = merge into current branch
- [ ] origin = default remote name
- [ ] HEAD = current position in repo
- [ ] .gitignore = files to not track

### Pattern Programming
- [ ] Outer loop = number of rows
- [ ] Inner loop range = what's in each row (function of i)
- [ ] Floyd's triangle = counter OUTSIDE outer loop
- [ ] Alphabet: `(char)('A' + j)` — must cast!
- [ ] Hollow shapes: print * only at first/last row/column

---

# EXAM DAY MINDSET

**BEFORE ENTERING:**
- Eat something light
- Sleep was more important than extra study
- Arrive early, settle your nerves

**DURING EXAM:**
- Read each question fully before answering
- For output questions: trace manually on paper
- For coding questions: write pseudocode first, then code
- Don't leave questions blank — write your logic/approach
- Skip hard questions, come back at the end
- Check array bounds in every loop
- Check for off-by-one errors

**TIME MANAGEMENT:**
- MCQs: 1 min each
- Output prediction: 2 min each
- Coding: 5-10 min each
- If stuck >5 min: skip and return

**COMMON PITFALLS TO AVOID:**
- Don't second-guess correct answers you were confident about
- Avoid changing answers unless you're sure you made an error
- If you see "which option is NOT..." — read carefully!

---

# GOOD LUCK!

You've prepared thoroughly.
Trust your preparation.
Read carefully.
Think before you write.

**YOU CAN DO THIS. 🚀**
