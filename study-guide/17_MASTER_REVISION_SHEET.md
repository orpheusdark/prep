# 🧠 MASTER REVISION SHEET — Revise in 15–20 Minutes

> Only the most critical definitions, formulas, rules, and differences.

---

## 📌 HTML

| Concept | Key Fact |
|---------|----------|
| `<!DOCTYPE html>` | HTML5 declaration — not a tag |
| Semantic tags | `<header>` `<nav>` `<main>` `<section>` `<article>` `<footer>` |
| `id` | Unique per page → CSS: `#id` |
| `class` | Reusable → CSS: `.class` |
| `alt` | Screen readers + SEO + fallback text |
| Block vs inline | Block = full width, new line. Inline = content width, same line |
| DOM | Browser's live JavaScript tree representation of HTML |

---

## 📌 CSS

| Concept | Key Fact |
|---------|----------|
| Specificity | !important > inline > ID > class > element |
| `#container .box p` specificity | 1-1-1 |
| Box model | Content → Padding → Border → Margin (inside out) |
| `box-sizing: border-box` | Padding included in declared width |
| `display: none` | Removed from layout |
| `visibility: hidden` | Hidden but keeps space |
| Flex: justify-content | Main axis alignment |
| Flex: align-items | Cross axis alignment |
| Center with flex | `justify-content: center` + `align-items: center` + `height` |
| rem vs px | rem = relative to root (scales with user settings) |
| Media query | `@media (max-width: 768px)` |
| pseudo-class | `:hover` (state) |
| pseudo-element | `::before` (inserts content) |

---

## 📌 JAVASCRIPT CORE

| Concept | Key Fact |
|---------|----------|
| `var` scope | Function-scoped, hoisted+initialized as `undefined` |
| `let`/`const` | Block-scoped, hoisted but TDZ (not initialized) |
| TDZ | Accessing `let`/`const` before declaration = ReferenceError |
| `==` vs `===` | `==` coerces types, `===` strict — always use `===` |
| `typeof null` | `"object"` (historical bug) |
| Falsy values (7) | `false, 0, -0, 0n, "", null, undefined, NaN` |
| `[]` and `{}` | TRUTHY |
| `map()` | Returns new array (same length) |
| `filter()` | Returns new array (shorter, filtered) |
| `reduce()` | Returns single accumulated value |
| `forEach()` | Returns **undefined** |
| `find()` | Returns first matching element or undefined |
| Arrow function | No own `this`, no `arguments` object |
| Shallow copy | `{...obj}` — nested objects are shared |
| Deep copy | `structuredClone(obj)` — fully independent |

---

## 📌 JAVASCRIPT ADVANCED

| Concept | Key Fact |
|---------|----------|
| Closure | Inner function remembers outer function's variables after outer returns |
| Lexical scope | Scope determined by where function is written, not called |
| Event loop order | Sync → Microtasks (Promises) → Macrotasks (setTimeout) |
| Classic output | `console.log("A"); setTimeout(→"B",0); Promise→"C"; console.log("D")` → **A, D, C, B** |
| Promise states | pending → fulfilled / rejected |
| `await` | Pauses async function until Promise resolves; doesn't block main thread |
| Debounce | Delays execution until activity stops (search box) |
| Throttle | Limits to once per interval (scroll events) |
| `??` | Null/undefined only triggers fallback |
| `\|\|` | Any falsy value triggers fallback |
| Optional chaining | `obj?.prop` — returns undefined instead of throwing |

---

## 📌 JAVA

| Concept | Key Fact |
|---------|----------|
| WORA | Write Once, Run Anywhere — bytecode → JVM |
| JDK > JRE > JVM | Developer tool > Runtime > VM |
| `int` vs `Integer` | Primitive vs wrapper class |
| Widening cast | Automatic (int → double) |
| Narrowing cast | Manual `(int) d` — may lose data |
| `++i` vs `i++` | Pre-increment (increment first) vs post-increment (use first) |
| `&&` | Short-circuit AND |
| OOP 4 pillars | Encapsulation, Inheritance, Polymorphism, Abstraction |
| Encapsulation | private fields + getters/setters |
| Overloading | Same class, different params — compile time |
| Overriding | Child redefines parent method — runtime |
| `throw` | Actually throws exception |
| `throws` | Declares method may throw |
| `finally` | Always runs (even with return or exception) |
| String immutable | New String object created on every modification |
| StringBuilder | Mutable, fast, not thread-safe |
| Interface vs Abstract | Interface=contract+multiple, Abstract=partial blueprint+single |

---

## 📌 DSA

| Concept | Key Fact |
|---------|----------|
| O(1) < O(log n) < O(n) < O(n log n) < O(n²) | Complexity order |
| Binary search | Sorted array required; O(log n) |
| `mid` formula | `left + (right - left) / 2` |
| Stack | LIFO — push/pop from same end |
| Queue | FIFO — enqueue back, dequeue front |
| HashMap | O(1) avg lookup; collision → chaining |
| Missing number | `expected - actual` = `n(n+1)/2 - sum(arr)` |
| Two Sum (HashMap) | Store seen numbers, check complement |
| Kadane's | `max(arr[i], curr+arr[i])` — extend or restart |
| Floyd's cycle | Slow + fast pointers; meet if cycle |
| Sliding window | Add right, remove left — avoid recomputation |
| Merge Sort | O(n log n), stable, O(n) space |
| Quick Sort | O(n log n) avg, O(n²) worst, unstable |
| BFS | Queue — shortest path unweighted |
| DFS | Stack/Recursion — depth, cycle detection |
| DP signs | Optimal + choices + overlapping subproblems |
| Coin Change | `dp[i] = min(dp[i], dp[i-coin]+1)` |
| LCS | `dp[i][j] = 1+dp[i-1][j-1]` if match, else `max(dp[i-1][j], dp[i][j-1])` |

---

## 📌 REACT

| Concept | Key Fact |
|---------|----------|
| Component | Reusable function returning JSX |
| Props | Parent → Child; read-only |
| State | Own data; triggers re-render |
| Virtual DOM | React's in-memory HTML tree; diffs for minimal real DOM updates |
| `useState` | `[value, setValue]` — setter triggers re-render |
| `useEffect([])` | Runs once after first render |
| `useEffect` no deps | Runs after every render (risky) |
| `useRef` | Access DOM; mutable value without re-render |
| Prop drilling | Passing props through unnecessary intermediaries |
| Context API | Global state without prop drilling |
| Keys | Unique stable IDs — never use array index for mutable lists |
| Controlled input | Value managed by React state |
| Lifting state | Move state to common parent for sibling communication |

---

## 📌 SQL

| Concept | Key Fact |
|---------|----------|
| INNER JOIN | Matching rows in BOTH tables |
| LEFT JOIN | All left + matched right (NULL if no match) |
| WHERE vs HAVING | WHERE = rows before group, HAVING = groups after aggregate |
| Second highest | `SELECT MAX(sal) WHERE sal < (SELECT MAX(sal) FROM ...)` |
| RANK() | Gaps on ties: 1, 2, 2, 4 |
| DENSE_RANK() | No gaps: 1, 2, 2, 3 |
| ROW_NUMBER() | Always unique: 1, 2, 3, 4 |
| PARTITION BY | Divide window function by groups |
| CTE | `WITH name AS (...)` — named temporary result set |
| ACID | Atomicity, Consistency, Isolation, Durability |
| Index hurt performance | Frequent writes; low cardinality columns; small tables |

---

## 📌 REST / HTTP

| Code | Meaning |
|------|---------|
| 200 | OK |
| 201 | Created |
| 400 | Bad Request |
| 401 | Unauthorized (not logged in) |
| 403 | Forbidden (logged in, no permission) |
| 404 | Not Found |
| 500 | Server Error |

| Method | Purpose |
|--------|---------|
| GET | Read |
| POST | Create |
| PUT | Replace |
| PATCH | Update |
| DELETE | Remove |

CORS = browser blocks cross-origin unless server sends `Access-Control-Allow-Origin` header.

---

## 📌 GIT

| Command | Effect |
|---------|--------|
| `git add` | Stage changes |
| `git commit` | Save snapshot |
| `git push` | Upload to remote |
| `git pull` | fetch + merge |
| `git fetch` | Download only, no merge |
| `git stash` | Temporarily save work |
| `git revert` | Safe undo — new commit |
| `git reset --hard` | Destructive undo — rewrites history |
| `git reflog` | Recovery tool — shows all HEAD changes |

Never commit: `.env`, API keys, passwords, `node_modules/`

---

## 📌 AI

| Term | One-line |
|------|---------|
| LLM | Predicts next token from trained data |
| Token | ≈¾ of a word |
| Hallucination | Confident but wrong output |
| Temperature | Low = deterministic, High = creative |
| Agent | LLM + tools + loop + memory |
| Tool-calling loop | Think → Act → Observe → Repeat |
| Hooks | Callback points for safety/logging |
| Safeguard | Max iteration limit + deduplication + timeout |

---

## 📌 MIXED HARD — KEY ANSWERS

| Q# | One-line Answer |
|----|----------------|
| Q601 | Missing number = n(n+1)/2 - actual sum |
| Q602 | HashSet O(n), Sort+Adjacent O(n log n), Brute O(n²) |
| Q605 | Debounce the search input (500ms) |
| Q607 | Revoke key immediately, scrub git history |
| Q611 | HashMap for O(1) lookup |
| Q612 | Queue (FIFO) |
| Q613 | Stack (LIFO) |
| Q614 | BFS (unweighted) |
| Q615 | Dijkstra (weighted, non-negative) |
| Q616 | Topological sort / DFS with 3 states |
| Q617 | Add base case; convert to iterative |
| Q618 | Check setState is called; no direct mutation |
| Q619 | Poor hashCode → all keys collide → O(n) |
| Q620 | Max iterations + deduplication + timeout |
