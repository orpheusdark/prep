# 🎯 TECH PASSPORT — MASTER MCQ + CODING BANK
### Structured for Fast Revision & Exam Prep

---

## 📋 NAVIGATION

| Section | Topics | Questions |
|---------|--------|-----------|
| [🟢 SECTION 1 — Tech Rookie](#section-1--tech-rookie) | HTML, CSS, JS Core, DOM, Java, OOP, DSA Basics, Git | Q1–Q73 |
| [🔵 SECTION 2 — Tech Pro](#section-2--tech-pro) | Arrays, Hashing, Strings, 2-Pointers, LL, Stack/Queue, Sorting, Recursion, Collections, Exceptions, SQL, Git Advanced | Q74–Q119 |
| [🔴 SECTION 3 — Tech Elite](#section-3--tech-elite) | Advanced DSA, Trees, DP, Advanced JS, Promises, REST, React, AI, SQL Elite | Q120–Q169 |
| [💻 SECTION 4 — Coding Programs](#section-4--coding-programs) | 94 Programs across 18 levels | Prog 1–94 |
| [🔥 FINAL 30 MUST-KNOW](#-final-30-high-priority-questions) | Top 30 most important exam questions | Top 30 |

---

---

# 🟢 SECTION 1 — TECH ROOKIE

---

## 📁 PART A — HTML (Q1–Q10)

> **Quick Concept:** HTML = structure. Semantic tags give meaning. `id` = unique, `class` = reusable.

| Q# | Question | A | B | C | D | ✅ Answer |
|----|---------|---|---|---|---|-----------|
| Q1 | Purpose of `<!DOCTYPE html>`? | Defines page title | **Tells browser: HTML5 mode** | Imports CSS | Creates root element | **B** |
| Q2 | Which is a semantic HTML element? | `<div>` | `<span>` | **`<section>`** | `<b>` | **C** |
| Q3 | Attribute for alt text on images? | `src` | `href` | **`alt`** | `title` | **C** |
| Q4 | Best element for main navigation? | `<navigation>` | **`<nav>`** | `<menu>` | `<links>` | **B** |
| Q5 | Which statement about IDs is correct? | Multiple elements can share an ID | **ID should uniquely identify an element** | IDs only work in JS | IDs have lower specificity than classes | **B** |
| Q6 | Element that associates text with a form input? | `<caption>` | **`<label>`** | `<description>` | `<text>` | **B** |
| Q7 | What does the `required` attribute do? | Makes input read-only | **Prevents submit if field is empty** | Auto-fills input | Encrypts input | **B** |
| Q8 | HTTP method for retrieving data? | POST | PUT | **GET** | DELETE | **C** |
| Q9 | Element for most important heading? | `<heading>` | `<h6>` | **`<h1>`** | `<head>` | **C** |
| Q10 | Better for accessibility and SEO? | Only `<div>` elements | **Semantic HTML** | Inline styles | JS for all content | **B** |

> 🧠 **Remember:** DOCTYPE=HTML5 declaration | Semantic=meaning | `id`=unique | `<nav>`=navigation | `required`=no-empty-submit | GET=retrieve

---

## 📁 PART B — CSS (Q11–Q25)

> **Quick Concept:** Box model = Content→Padding→Border→Margin. Flexbox=1D. Grid=2D. Specificity: ID > Class > Element.

| Q# | Question | A | B | C | D | ✅ Answer |
|----|---------|---|---|---|---|-----------|
| Q11 | Space INSIDE border? | margin | **padding** | spacing | gap | **B** |
| Q12 | Space OUTSIDE border? | padding | **margin** | border-spacing | outside | **B** |
| Q13 | What does `box-sizing: border-box` do? | Removes borders | **Width/height includes padding+border** | Makes elements inline | Removes margin | **B** |
| Q14 | Highest specificity? | `p` | `.text` | **`#text`** | `*` | **C** |
| Q15 | `display: none` does? | Makes transparent | **Removes from layout** | Moves behind | Hides but keeps space | **B** |
| Q16 | `visibility: hidden` does? | Removes from layout | **Hides but preserves space** | Deletes element | 50% opacity | **B** |
| Q17 | Flexbox main-axis alignment? | align-items | **justify-content** | align-content | place-items | **B** |
| Q18 | Flexbox cross-axis alignment? | justify-content | **align-items** | flex-direction | flex-wrap | **B** |
| Q19 | `justify-content: center` + `align-items: center`? | Horizontal only | Vertical only | **Both axes centered** | No centering | **C** |
| Q20 | Relative to root element's font size? | em | **rem** | vh | % | **B** |
| Q21 | `1vh` represents? | 1% of element width | **1% of viewport height** | 1% of viewport width | 1px | **B** |
| Q22 | Feature for responsive layouts? | Variables | **Media queries** | Pseudo-elements | Transforms | **B** |
| Q23 | `position: absolute` is relative to? | Always viewport | **Nearest positioned ancestor** | Browser window only | `<body>` always | **B** |
| Q24 | Controls stacking order? | stack | layer | **z-index** | order-index | **C** |
| Q25 | Best for two-dimensional layouts? | Flexbox | **CSS Grid** | Float | Inline-block | **B** |

> 🧠 **Remember:** padding=inside, margin=outside | `display:none`=gone | `visibility:hidden`=space kept | justify=main axis | align=cross axis | rem=root-relative | `position:absolute`=nearest positioned parent | `z-index`=stacking | Grid=2D

---

## 📁 PART C — JAVASCRIPT FUNDAMENTALS (Q26–Q40)

> **Quick Concept:** `var`=function scope, `let`=block scope reassignable, `const`=block scope no-reassign. `===` is strict. 7 falsy values.

| Q# | Question | A | B | C | D | ✅ Answer |
|----|---------|---|---|---|---|-----------|
| Q26 | Block-scoped, CAN be reassigned? | var | **let** | const | static | **B** |
| Q27 | CANNOT be reassigned? | var | let | **const** | function | **C** |
| Q28 | Output: `5=="5"` then `5==="5"`? | true/true | false/false | **true/false** | false/true | **C** |
| Q29 | Which is NOT falsy? | `0` | `""` | `null` | **`[]`** | **D** |
| Q30 | `typeof null` returns? | `"null"` | `"undefined"` | **`"object"`** | `"empty"` | **C** |
| Q31 | What is `NaN`? | Null value | **Not-a-Number** | Undefined variable | Empty string | **B** |
| Q32 | Creates new array by transforming every element? | filter | **map** | reduce | forEach | **B** |
| Q33 | Selects elements satisfying a condition? | map | **filter** | reduce | every | **B** |
| Q34 | Accumulates array into one value? | map | **reduce** | filter | find | **B** |
| Q35 | What does `forEach()` return? | Transformed array | First match | **`undefined`** | A Promise | **C** |
| Q36 | `[1,2,3].map(x => x*2)` = ? | `[1,2,3]` | **`[2,4,6]`** | `[1,4,9]` | `6` | **B** |
| Q37 | `push()` does? | Adds to beginning | **Adds to end** | Removes from beginning | Removes from end | **B** |
| Q38 | `shift()` does? | Adds to beginning | **Removes from beginning** | Adds to end | Removes from end | **B** |
| Q39 | Which does NOT mutate original array? | splice | push | pop | **slice** | **D** |
| Q40 | Checks both value AND type? | `=` | `==` | **`===`** | `!=` | **C** |

> 🧠 **Remember:** map=transform(new array), filter=select(shorter), reduce=accumulate(single value), forEach=undefined | `[]` is TRUTHY | `typeof null = "object"` (bug!)

---

## 📁 PART D — JAVASCRIPT OUTPUT QUESTIONS (Q41–Q45)

> **Quick Concept:** `var`=function scope (shared), `let`=block scope (separate). Arrays are reference types — `b = a` means same object.

| Q# | Code | Answer | Why |
|----|------|--------|-----|
| Q41 | `let x=10; if(true){let x=20;} console.log(x)` | **A → 10** | `let` is block-scoped — inner `x` is separate |
| Q42 | `var x=10; if(true){var x=20;} console.log(x)` | **B → 20** | `var` is function-scoped — same `x` overwritten |
| Q43 | `typeof undefined` | **C → `"undefined"`** | `typeof` of undefined is the string `"undefined"` |
| Q44 | `[] == false` | **A → true** | `[]` coerces to `""` which coerces to `0`; `false`→`0`. Equal. |
| Q45 | `const a=[1,2,3]; const b=a; b.push(4); console.log(a)` | **C → `[1,2,3,4]`** | `b=a` is reference copy — same array object |

> ⚠️ **Classic traps:** `var` leaks out of `if` blocks | Arrays are reference types | `[] == false` is true but `[] === false` is false

---

## 📁 PART E — DOM (Q46–Q49)

| Q# | Question | ✅ Answer | Key Reason |
|----|---------|-----------|------------|
| Q46 | Method that selects FIRST matching CSS selector? | **`querySelector()`** | Returns single element |
| Q47 | `querySelectorAll()` returns? | **A collection of matching elements** | NodeList — all matches |
| Q48 | Attach an event handler? | **`addEventListener()`** | Standard DOM event API |
| Q49 | Event bubbling means? | **Event propagates from target toward ancestors** | Fires on element → parent → grandparent |

---

## 📁 PART F — JAVA BASICS (Q50–Q56)

| Q# | Question | ✅ Answer | Key Reason |
|----|---------|-----------|------------|
| Q50 | Which component EXECUTES bytecode? | **JVM** | JVM = Java Virtual Machine |
| Q51 | Which COMPILES source code to bytecode? | **javac** | `javac` is the compiler |
| Q52 | Which is NOT a primitive Java type? | **String** | String is a class/object |
| Q53 | Default value of instance `int` field? | **0** | Numeric primitives default to 0 |
| Q54 | What does `static` mean for a field? | **Belongs to the class, not instances** | Shared across all objects |
| Q55 | Method overloading = ? | **Same name, different parameter lists** | Compile-time polymorphism |
| Q56 | Method overriding = ? | **Same method signature redefined in subclass** | Runtime polymorphism |

> 🧠 **Remember:** JVM=run, javac=compile, JDK>JRE>JVM | static=class-level | overload=same class+diff params | override=child redefines parent

---

## 📁 PART G — OOP (Q57–Q61)

| Q# | Question | ✅ Answer | Explanation |
|----|---------|-----------|-------------|
| Q57 | Which OOP principle hides implementation details? | **Abstraction** | Shows what, hides how |
| Q58 | One interface, different implementations? | **Polymorphism** | Many forms |
| Q59 | Keyword referring to current object? | **`this`** | Current instance |
| Q60 | Keyword to access parent class members? | **`super`** | Parent class |
| Q61 | Can Java classes extend multiple classes? | **No** | Diamond problem — single inheritance only |

> 🧠 **4 Pillars:** Encapsulation(protect data) | Inheritance(reuse) | Polymorphism(many forms) | Abstraction(hide complexity)

---

## 📁 PART H — BASIC DSA (Q62–Q67)

| Q# | Question | ✅ Answer | Complexity |
|----|---------|-----------|------------|
| Q62 | Array access by index? | **O(1)** | Direct memory address |
| Q63 | Binary search requires? | **A sorted search space** | Must be sorted |
| Q64 | Binary search complexity? | **O(log n)** | Halves space each step |
| Q65 | Stack follows? | **LIFO** | Last In, First Out |
| Q66 | Queue follows? | **FIFO** | First In, First Out |
| Q67 | HashMap average lookup? | **O(1)** | Hash function = direct bucket |

---

## 📁 PART I — GIT/GITHUB (Q68–Q73)

| Q# | Question | ✅ Answer |
|----|---------|-----------|
| Q68 | Git is? | **A distributed version control system** |
| Q69 | GitHub is primarily? | **A cloud platform for hosting/collaborating on repos** |
| Q70 | `git add` does? | **Stages changes** |
| Q71 | `git commit` does? | **Creates a snapshot in local Git history** |
| Q72 | `git push` does? | **Uploads local commits to remote repository** |
| Q73 | `.gitignore` does? | **Specifies files Git should ignore** |

> 🧠 **Git flow:** add (stage) → commit (snapshot) → push (upload)

---

---

# 🔵 SECTION 2 — TECH PRO

---

## 📁 PART J — ARRAYS (Q74–Q78)

| Q# | Question | ✅ Answer | Why |
|----|---------|-----------|-----|
| Q74 | Best approach to move zeroes to end while preserving order? | **Two pointers** | O(n), maintains relative order |
| Q75 | Find second-largest in one pass — maintain what? | **Largest and second-largest** | Track top-2 as you scan |
| Q76 | Optimal time complexity for finding maximum? | **O(n)** | Must check every element at least once |
| Q77 | Kadane's algorithm solves? | **Maximum subarray sum** | "Extend or restart" pattern |
| Q78 | Two Sum in unsorted array — best technique? | **HashMap** | O(n) — store complement lookups |

---

## 📁 PART K — HASHING (Q79–Q82)

| Q# | Question | ✅ Answer | Explanation |
|----|---------|-----------|-------------|
| Q79 | Why check `containsKey()` before inserting in Two Sum? | **Determine if complement has been seen** | O(1) lookup for the pair |
| Q80 | `map.get(key)` if key doesn't exist returns? | **`null`** | HashMap returns null for missing keys |
| Q81 | `map.getOrDefault(x, 0) + 1` does? | **Reads count or uses 0, then increments** | Pattern for frequency counting |
| Q82 | What is a hash collision? | **Two keys produce the same hash bucket** | Handled by chaining in Java |

---

## 📁 PART L — STRINGS (Q83–Q85)

| Q# | Question | ✅ Answer | Why |
|----|---------|-----------|-----|
| Q83 | Java `String` immutable means? | **Once created, contents cannot be changed** | Security, thread safety, String Pool |
| Q84 | Best for repeated string modifications? | **StringBuilder** | Mutable buffer — O(n) not O(n²) |
| Q85 | Efficient anagram check approach? | **Character frequency counting** | Count chars of both — compare |

---

## 📁 PART M — TWO POINTERS / SLIDING WINDOW (Q86–Q88)

| Q# | Question | ✅ Answer |
|----|---------|-----------|
| Q86 | Two-pointer useful when? | **Can exploit ordering/boundaries to avoid nested loops** |
| Q87 | Sliding window useful for? | **Contiguous subarrays/substrings** |
| Q88 | Longest substring without repeating chars solved with? | **Sliding window + HashSet/HashMap** |

---

## 📁 PART N — LINKED LIST (Q89–Q91)

| Q# | Question | ✅ Answer |
|----|---------|-----------|
| Q89 | Find middle of linked list? | **Slow and fast pointers** |
| Q90 | Floyd's algorithm used for? | **Detect cycles** |
| Q91 | Reversing singly linked list requires? | **Previous, current, and next references** |

---

## 📁 PART O — STACK / QUEUE (Q92–Q94)

| Q# | Question | ✅ Answer | Why |
|----|---------|-----------|-----|
| Q92 | Balanced parentheses solved with? | **Stack** | LIFO — push open, pop and match close |
| Q93 | BFS uses which data structure? | **Queue** | Level-by-level = FIFO |
| Q94 | DFS recursion naturally uses? | **Stack** | Call stack = LIFO |

---

## 📁 PART P — SORTING (Q95–Q98)

| Algorithm | Best | Average | Worst | Stable? | Q# Answer |
|-----------|------|---------|-------|---------|-----------|
| Quick Sort | O(n log n) | **O(n log n)** | **O(n²)** | No | Q95=C, Q96=D |
| Merge Sort | O(n log n) | **O(n log n)** | O(n log n) | Yes | Q97=B |
| Bubble Sort | O(n) | O(n²) | O(n²) | Yes | Q98=B (adjacent swaps) |

| Q# | Question | ✅ Answer |
|----|---------|-----------|
| Q95 | Average-case quicksort? | **O(n log n)** |
| Q96 | Worst-case quicksort? | **O(n²)** |
| Q97 | Merge sort time? | **O(n log n) guaranteed** |
| Q98 | Repeatedly swaps adjacent out-of-order elements? | **Bubble Sort** |

---

## 📁 PART Q — RECURSION (Q99–Q100)

| Q# | Question | ✅ Answer |
|----|---------|-----------|
| Q99 | Every recursive function must have? | **A base case** |
| Q100 | Missing base case results in? | **Infinite recursion / stack overflow** |

---

## 📁 PART R — JAVA COLLECTIONS (Q101–Q104)

| Q# | Question | ✅ Answer | Key Property |
|----|---------|-----------|--------------|
| Q101 | Maintains insertion order, allows duplicates? | **ArrayList** | Dynamic array |
| Q102 | Does NOT allow duplicate elements? | **HashSet** | Set = unique |
| Q103 | Maintains sorted key order? | **TreeMap** | Red-black tree |
| Q104 | Maintains insertion order for map entries? | **LinkedHashMap** | Linked + hashed |

> **Collections cheatsheet:**
> - `ArrayList` = ordered, duplicates allowed
> - `HashSet` = unordered, no duplicates
> - `TreeMap` = sorted by key
> - `LinkedHashMap` = insertion-order map
> - `HashMap` = unordered, fastest

---

## 📁 PART S — EXCEPTIONS (Q105–Q108)

| Q# | Question | ✅ Answer | Type |
|----|---------|-----------|------|
| Q105 | Which is a CHECKED exception? | **IOException** | Must handle at compile time |
| Q106 | Block that always executes? | **`finally`** | Runs regardless of exception |
| Q107 | `throw` is used to? | **Explicitly throw an exception** | `throw new Exception("msg")` |
| Q108 | `throws` is used to? | **Declare exceptions a method may propagate** | `void method() throws IOException` |

> 🧠 **throw = do it | throws = declare it | finally = always runs**

---

## 📁 PART T — SQL (Q109–Q115)

| Q# | Question | ✅ Answer | Rule |
|----|---------|-----------|------|
| Q109 | Filters rows BEFORE grouping? | **WHERE** | Pre-aggregation filter |
| Q110 | Filters groups AFTER aggregation? | **HAVING** | Post-aggregation filter |
| Q111 | Returns matching rows from BOTH tables? | **INNER JOIN** | Intersection |
| Q112 | Returns ALL rows from LEFT table? | **LEFT JOIN** | All left + matched right |
| Q113 | Function that counts rows? | **COUNT** | `COUNT(*)` or `COUNT(col)` |
| Q114 | `GROUP BY` does? | **Groups rows for aggregation** | Used with aggregate functions |
| Q115 | What is a primary key? | **A column that uniquely identifies rows** | Never null, never duplicate |

---

## 📁 PART U — GIT ADVANCED (Q116–Q119)

| Q# | Question | ✅ Answer | Key Detail |
|----|---------|-----------|------------|
| Q116 | `git fetch` does? | **Downloads remote info WITHOUT merging** | Safe inspection |
| Q117 | `git pull` performs? | **fetch + integration (merge)** | = fetch + merge |
| Q118 | `git revert` does? | **Creates new commit that reverses a previous commit** | Safe — no history rewrite |
| Q119 | Merge conflict occurs when? | **Git cannot automatically reconcile conflicting changes** | Same lines edited in both branches |

---

---

# 🔴 SECTION 3 — TECH ELITE

---

## 📁 PART V — ADVANCED DSA (Q120–Q125)

| Q# | Question | ✅ Answer | When to use |
|----|---------|-----------|-------------|
| Q120 | Shortest paths with non-negative weights? | **Dijkstra** | Weighted graph, no negatives |
| Q121 | BFS useful for shortest path when? | **Graph is unweighted** | Each edge = cost 1 |
| Q122 | Explores tree level by level? | **BFS** | Uses Queue |
| Q123 | Dijkstra implemented efficiently with? | **Min-heap / priority queue** | Always process lowest-cost node |
| Q124 | Topological sorting applies to? | **Directed Acyclic Graphs (DAG)** | No cycles |
| Q125 | Number of Islands solved using? | **BFS/DFS** | Flood fill on 2D grid |

---

## 📁 PART W — TREES (Q126–Q130)

| Traversal | Order | Output on BST | Q# |
|-----------|-------|---------------|----|
| Inorder | Left → Root → Right | **Sorted** | Q126=B, Q128=A |
| Preorder | Root → Left → Right | — | Q127=C |
| Postorder | Left → Right → Root | — | Q129=C |
| Level-order | BFS (level by level) | — | — |

| Q# | Question | ✅ Answer |
|----|---------|-----------|
| Q126 | Inorder traversal of BST produces? | **Sorted order** |
| Q127 | Root → Left → Right traversal? | **Preorder** |
| Q128 | Left → Root → Right traversal? | **Inorder** |
| Q129 | Left → Right → Root traversal? | **Postorder** |
| Q130 | Height of a tree? | **Longest path from root to a leaf** |

> 🧠 **Memory:** Pre=Root **first** | In=Root **in middle** | Post=Root **last** | Inorder BST = **sorted**

---

## 📁 PART X — DYNAMIC PROGRAMMING (Q131–Q134)

| Q# | Question | ✅ Answer | Key Point |
|----|---------|-----------|-----------|
| Q131 | DP useful when problem has? | **Overlapping subproblems + optimal substructure** | Both required |
| Q132 | Memoization is? | **Top-down DP with caching** | Recursion + cache |
| Q133 | Tabulation is? | **Bottom-up computation** | Fill table from base cases |
| Q134 | Classic DP problem? | **Climbing Stairs** | `dp[i] = dp[i-1] + dp[i-2]` |

---

## 📁 PART Y — ADVANCED JAVASCRIPT (Q135–Q140)

| Q# | Question | ✅ Answer | Explanation |
|----|---------|-----------|-------------|
| Q135 | What is a closure? | **Function retaining access to variables from its lexical scope** | Outer scope remembered after outer returns |
| Q136 | What does the event loop do? | **Coordinates async callbacks/tasks with call stack** | Sync → Microtasks → Macrotasks |
| Q137 | What executes before timer callbacks? | **Microtasks (Promise callbacks)** | Promise > setTimeout |
| Q138 | Output of A/setTimeout/Promise/D? | **A, D, C, B** | Sync→Microtask→Macrotask |
| Q139 | Debouncing useful when? | **Want action after user STOPS triggering events** | Search box |
| Q140 | Throttling means? | **Limiting how frequently an operation executes** | Scroll events |

#### Q138 — Classic Output Question 🔥

```javascript
console.log("A");           // 1. Sync → A
setTimeout(()=>log("B"),0); // 3. Macrotask → B last
Promise.resolve().then(()=>log("C")); // 2. Microtask → C before B
console.log("D");           // 1. Sync → D
```
**Output: A → D → C → B**

---

## 📁 PART Z — PROMISES / ASYNC (Q141–Q143)

| Q# | Question | ✅ Answer |
|----|---------|-----------|
| Q141 | Promise states? | **Pending, Fulfilled, Rejected** |
| Q142 | `async` functions return? | **Always a Promise** |
| Q143 | `await` is used to? | **Pause surrounding async function until Promise settles** |

---

## 📁 PART AA — API / REST (Q144–Q149)

| Code | Meaning | Q# |
|------|---------|-----|
| **200** | OK — success | Q144=A |
| **401** | Unauthorized — not authenticated | Q145=B |
| **403** | Forbidden — authenticated but no permission | Q146=B |
| **PATCH** | Partially update a resource | Q147=C |

| Q# | Question | ✅ Answer |
|----|---------|-----------|
| Q144 | Successful retrieval status code? | **200** |
| Q145 | Unauthorized / missing authentication? | **401** |
| Q146 | Understood but refuses authorization? | **403** |
| Q147 | Partially update a resource? | **PATCH** |
| Q148 | What is JSON? | **A lightweight data-interchange format** |
| Q149 | CORS is a browser security mechanism related to? | **Cross-origin requests** |

> 🧠 **401** = "Who are you?" (not logged in) | **403** = "I know you, but NO" (no permission)

---

## 📁 PART AB — REACT (Q150–Q158)

| Q# | Question | ✅ Answer | Key Detail |
|----|---------|-----------|------------|
| Q150 | React components should be? | **Reusable units of UI** | Functions returning JSX |
| Q151 | Props are? | **Data passed from parent to child** | Read-only |
| Q152 | State represents? | **Data managed by component that influences rendering** | Triggers re-render |
| Q153 | Hook that manages local state? | **useState** | `const [val, setVal] = useState(init)` |
| Q154 | Hook for side effects? | **useEffect** | Data fetching, subscriptions |
| Q155 | `useEffect(fn, [])` runs? | **After initial mount only** | `[]` = run once |
| Q156 | Why are keys used in React lists? | **Help React identify list elements across renders** | Enables efficient reconciliation |
| Q157 | What is prop drilling? | **Passing props through intermediate components unnecessarily** | Solution: Context API |
| Q158 | What avoids prop drilling? | **Context API** | Global state access |

---

## 📁 PART AC — AI FUNDAMENTALS (Q159–Q165)

| Q# | Question | ✅ Answer | Key Point |
|----|---------|-----------|-----------|
| Q159 | What is an LLM? | **Large Language Model** | Predicts next token |
| Q160 | Prompt engineering? | **Designing prompts for more useful model behavior** | Craft = better output |
| Q161 | Zero-shot prompting? | **Providing no examples for the task** | Model uses training |
| Q162 | Few-shot prompting? | **Giving a small number of examples** | 2-5 examples guide model |
| Q163 | Hallucination means? | **AI produces unsupported/fabricated info** | Confident but wrong |
| Q164 | Increasing temperature makes output? | **More varied/random** | Low=deterministic, High=creative |
| Q165 | AI agent differs from chatbot because? | **Can reason through tasks and use tools/actions** | Autonomous multi-step |

---

## 📁 PART AD — SQL ELITE (Q166–Q169)

| Q# | Question | ✅ Answer | Key Detail |
|----|---------|-----------|------------|
| Q166 | Assigns unique sequential row numbers within window? | **ROW_NUMBER()** | Always unique |
| Q167 | RANK() vs DENSE_RANK() difference? | **RANK leaves gaps after ties; DENSE_RANK doesn't** | 1,2,2,4 vs 1,2,2,3 |
| Q168 | CTE stands for? | **Common Table Expression** | `WITH name AS (...)` |
| Q169 | Which ACID property ensures changes persist after commit? | **Durability** | Once committed = permanent |

---

---

# 💻 SECTION 4 — CODING PROGRAMS

---

## 🔹 LEVEL 1 — Array Basics (Programs 1–10)

| # | Problem | Approach | Key Code Pattern |
|---|---------|----------|-----------------|
| 1 | **Largest Element** | Single scan | `int max = arr[0]; for(x:arr) max=Math.max(max,x);` |
| 2 | **Smallest Element** | Single scan | `int min = arr[0]; for(x:arr) min=Math.min(min,x);` |
| 3 | **Second Largest** ⭐ | Track top-2 | `if(x>first){second=first;first=x;} else if(x>second&&x!=first)second=x;` |
| 4 | **Reverse Array** ⭐ | Two pointers | `while(left<right){swap;left++;right--;}` |
| 5 | **Check Sorted** | Adjacent compare | `for(int i=1;i<n;i++) if(arr[i]<arr[i-1]) return false;` |
| 6 | **Linear Search** | Single scan | `for(int i=0;i<n;i++) if(arr[i]==target) return i;` |
| 7 | **Count Frequencies** | HashMap | `map.put(x, map.getOrDefault(x,0)+1);` |
| 8 | **Move Zeroes** ⭐ | Two pointers | `int pos=0; for(x:arr)if(x!=0)arr[pos++]=x; while(pos<n)arr[pos++]=0;` |
| 9 | **Remove Duplicates (Sorted)** | Two pointers | `int i=0; for(j=1;j<n;j++) if(arr[j]!=arr[i]) arr[++i]=arr[j];` |
| 10 | **Rotate Right by k** | Reverse trick | Reverse all → Reverse first k → Reverse rest |

---

## 🔹 LEVEL 2 — Hashing (Programs 11–15)

| # | Problem | Approach | Expected Output |
|---|---------|----------|----------------|
| 11 | **Two Sum** ⭐🔥 | HashMap O(n) | Indices of the pair |
| 12 | **First Non-Repeating Char** ⭐ | `freq map + scan` | `"swiss"` → `'w'` |
| 13 | **Duplicate Number** | HashSet | true/false |
| 14 | **Majority Element** | Boyer-Moore voting | Element appearing >n/2 times |
| 15 | **Longest Consecutive Sequence** ⭐ | HashSet + start-of-sequence check | `[100,4,200,1,3,2]` → `4` |

```java
// Two Sum — O(n)
Map<Integer,Integer> map = new HashMap<>();
for(int i=0;i<nums.length;i++){
  int comp = target - nums[i];
  if(map.containsKey(comp)) return new int[]{map.get(comp),i};
  map.put(nums[i],i);
}
```

---

## 🔹 LEVEL 3 — Strings (Programs 16–22)

| # | Problem | Key Approach |
|---|---------|-------------|
| 16 | **Reverse String** | Two pointers |
| 17 | **Palindrome Check** ⭐ | Two pointers (left/right compare) |
| 18 | **Valid Anagram** ⭐ | Freq count array `int[26]` OR sort both |
| 19 | **Remove Duplicate Characters** | LinkedHashSet (preserves order) |
| 20 | **Reverse Words** | `split(" ")` + reverse array + join |
| 21 | **Longest Common Prefix** | Column-by-column comparison |
| 22 | **First Unique Character** | freq map + first scan for count==1 |

---

## 🔹 LEVEL 4 — Two Pointers / Sliding Window (Programs 23–28)

| # | Problem | Technique | Complexity |
|---|---------|-----------|------------|
| 23 | **Two Sum (Sorted)** | Left+right pointers | O(n) |
| 24 | **Container With Most Water** ⭐ | Move shorter wall inward | O(n) |
| 25 | **3Sum** ⭐ | Sort + fix one + two pointers | O(n²) |
| 26 | **Max Sum Subarray Size K** ⭐ | Sliding window | O(n) |
| 27 | **Longest Substring No Repeats** ⭐🔥 | Sliding window + HashMap | O(n) |
| 28 | **Minimum Window Substring** | Sliding window + freq map | O(n) |

```java
// Longest Substring Without Repeating — O(n)
Map<Character,Integer> map = new HashMap<>();
int left=0, maxLen=0;
for(int right=0;right<s.length();right++){
  char c=s.charAt(right);
  if(map.containsKey(c)&&map.get(c)>=left) left=map.get(c)+1;
  map.put(c,right);
  maxLen=Math.max(maxLen,right-left+1);
}
```

---

## 🔹 LEVEL 5 — Linked List (Programs 29–34)

| # | Problem | Key Technique |
|---|---------|--------------|
| 29 | **Reverse Linked List** ⭐🔥 | 3 pointers: prev, curr, next |
| 30 | **Middle of List** ⭐ | Slow/fast pointers |
| 31 | **Detect Cycle** ⭐ | Floyd's cycle detection |
| 32 | **Remove Nth from End** | Two pointers (n apart) |
| 33 | **Merge Two Sorted Lists** ⭐ | Dummy head + merge |
| 34 | **Palindrome List** | Find middle → reverse second half → compare |

```java
// Reverse Linked List
ListNode prev=null, curr=head;
while(curr!=null){ ListNode next=curr.next; curr.next=prev; prev=curr; curr=next; }
return prev;
```

---

## 🔹 LEVEL 6 — Stack / Queue (Programs 35–39)

| # | Problem | Data Structure |
|---|---------|---------------|
| 35 | **Valid Parentheses** ⭐🔥 | Stack — push open, pop+match close |
| 36 | **Implement Stack** | Array with top pointer |
| 37 | **Implement Queue** | Array with front/rear |
| 38 | **Queue Using Two Stacks** | s1=input, s2=output (transfer when empty) |
| 39 | **Next Greater Element** ⭐ | Monotonic stack |

---

## 🔹 LEVEL 7 — Binary Search (Programs 40–45)

| # | Problem | Key Modification |
|---|---------|----------------|
| 40 | **Binary Search** ⭐ | `mid = left + (right-left)/2` |
| 41 | **First Occurrence** | When found: `result=mid; hi=mid-1` |
| 42 | **Last Occurrence** | When found: `result=mid; lo=mid+1` |
| 43 | **Search Rotated Sorted Array** ⭐ | Check which half is sorted |
| 44 | **Find Peak Element** | `if arr[mid]<arr[mid+1]` → go right |
| 45 | **Integer Square Root** | Binary search 1 to x |

---

## 🔹 LEVEL 8 — Sorting (Programs 46–50)

| # | Algorithm | Key Logic | Complexity |
|---|-----------|-----------|------------|
| 46 | **Bubble Sort** | Compare adjacent, swap if wrong order | O(n²) |
| 47 | **Selection Sort** | Find min in unsorted, swap with first | O(n²) |
| 48 | **Insertion Sort** | Pick element, insert in correct position | O(n²) |
| 49 | **Merge Sort** ⭐ | Divide → sort → merge | O(n log n) |
| 50 | **Quick Sort** ⭐ | Pivot → partition → recurse | O(n log n) avg |

---

## 🔹 LEVEL 9 — Recursion / Backtracking (Programs 51–55)

| # | Problem | Base Case | Recursive Case |
|---|---------|-----------|----------------|
| 51 | **Factorial** | `n<=1 → 1` | `n * fact(n-1)` |
| 52 | **Fibonacci** (3 ways) | `n<=1 → n` | `fib(n-1)+fib(n-2)` → then memoize → then tabulate |
| 53 | **Generate Subsets** ⭐ | Empty array | Include/exclude each element |
| 54 | **Generate Permutations** ⭐ | Length 1 | Swap + recurse + swap back |
| 55 | **Combination Sum** | Sum = target → add | Try each candidate + recurse |

```
Fibonacci complexity:
  Naive recursion  → O(2ⁿ)
  Memoization      → O(n)
  Tabulation       → O(n), O(1) space (optimized)
```

---

## 🔹 LEVEL 10 — Trees (Programs 56–64)

| # | Problem | Approach |
|---|---------|---------|
| 56–58 | **Inorder/Preorder/Postorder** ⭐ | Recursive (1 line each) + Iterative (Stack) |
| 59 | **Level Order (BFS)** ⭐ | Queue — offer root, poll+add children |
| 60 | **Maximum Depth** | `1 + max(height(left), height(right))` |
| 61 | **Check Balanced** | Height difference ≤ 1 for all nodes |
| 62 | **Diameter** | Max of (leftH + rightH) across all nodes |
| 63 | **Validate BST** | Pass min/max bounds down |
| 64 | **Lowest Common Ancestor** ⭐ | If both sides found → root is LCA |

---

## 🔹 LEVEL 11 — Graphs (Programs 65–72)

| # | Problem | Algorithm | Data Structure |
|---|---------|-----------|---------------|
| 65 | **BFS** ⭐ | Level by level | Queue |
| 66 | **DFS** ⭐ | Depth first | Stack / Recursion |
| 67 | **Number of Islands** ⭐🔥 | BFS/DFS flood fill | Queue / Recursion |
| 68 | **Detect Cycle (Undirected)** | DFS with parent tracking | — |
| 69 | **Detect Cycle (Directed)** | DFS with 3 states | visited[], inStack[] |
| 70 | **Shortest Path (Unweighted)** | BFS | Queue |
| 71 | **Dijkstra** ⭐ | Greedy with min-heap | Priority Queue |
| 72 | **Topological Sort** | Kahn's BFS algorithm | Queue + in-degree array |

---

## 🔹 LEVEL 12 — Dynamic Programming (Programs 73–79)

| # | Problem | DP Formula | Base Case |
|---|---------|-----------|-----------|
| 73 | **Climbing Stairs** ⭐ | `dp[i]=dp[i-1]+dp[i-2]` | dp[0]=1, dp[1]=1 |
| 74 | **House Robber** | `dp[i]=max(dp[i-1], dp[i-2]+nums[i])` | dp[0]=nums[0] |
| 75 | **Coin Change** ⭐ | `dp[i]=min(dp[i], dp[i-coin]+1)` | dp[0]=0 |
| 76 | **0/1 Knapsack** ⭐ | `dp[i][w]=max(dp[i-1][w], val[i-1]+dp[i-1][w-wt[i-1]])` | dp[0][x]=0 |
| 77 | **LCS** ⭐ | Match:`dp[i][j]=1+dp[i-1][j-1]` else `max(dp[i-1][j], dp[i][j-1])` | row/col 0 = 0 |
| 78 | **LIS** | `dp[i]=max(dp[j]+1)` for all j<i where nums[j]<nums[i] | dp[i]=1 |
| 79 | **Edit Distance** | Match:`dp[i-1][j-1]` else `1+min(dp[i-1][j], dp[i][j-1], dp[i-1][j-1])` | — |

---

## 🔹 LEVEL 13 — Java Programs (Programs 80–84)

| # | Problem | Key API |
|---|---------|---------|
| 80 | **Frequency Map** | `HashMap<Character,Integer>` + `getOrDefault` |
| 81 | **Custom Comparator** | `Comparator.comparingInt(Employee::getSalary).reversed()` |
| 82 | **Student Management** | `ArrayList<Student>` + `Comparator` + streams |
| 83 | **Exception Handling** | `try/catch(ArithmeticException e)`, `NumberFormatException`, `ArrayIndexOutOfBoundsException` |
| 84 | **HashMap Word Counter** | Split sentence on spaces → count frequency of each word |

---

## 🔹 LEVEL 14 — SQL Programs (SQL 1–12)

**Tables used:**
```sql
Employee(id, name, department_id, salary, manager_id)
Department(id, name)
```

| # | Problem | SQL Query |
|---|---------|-----------|
| SQL 1 | **Highest Salary** | `SELECT MAX(salary) FROM Employee;` |
| SQL 2 | **Second Highest** ⭐🔥 | `SELECT MAX(salary) FROM Employee WHERE salary < (SELECT MAX(salary) FROM Employee);` |
| SQL 3 | **Third Highest** | Use `DENSE_RANK()=3` or nested NOT IN |
| SQL 4 | **Earning > Average** | `WHERE salary > (SELECT AVG(salary) FROM Employee)` |
| SQL 5 | **Highest Per Dept** ⭐ | `MAX(salary) GROUP BY dept_id` OR `DENSE_RANK()=1 PARTITION BY dept_id` |
| SQL 6 | **Depts > 5 Employees** | `GROUP BY dept_id HAVING COUNT(*)>5` |
| SQL 7 | **Earn More Than Manager** ⭐ | `JOIN Employee m ON e.manager_id=m.id WHERE e.salary>m.salary` |
| SQL 8 | **Duplicate Names** | `GROUP BY name HAVING COUNT(*)>1` |
| SQL 9 | **ROW_NUMBER by salary per dept** | `ROW_NUMBER() OVER(PARTITION BY dept_id ORDER BY salary DESC)` |
| SQL 10 | **Second Highest per dept** ⭐ | `DENSE_RANK()=2 OVER(PARTITION BY dept_id ORDER BY salary DESC)` |
| SQL 11 | **No Manager** | `WHERE manager_id IS NULL` |
| SQL 12 | **Depts with no employees** | `LEFT JOIN Employee ON... WHERE e.id IS NULL` |

---

## 🔹 LEVEL 15 — JavaScript Practical (Programs 85–89)

| # | Problem | Key Pattern |
|---|---------|------------|
| 85 | **Debounced Search** ⭐🔥 | `clearTimeout(timer); timer=setTimeout(fn, 500)` |
| 86 | **Throttle Scroll Handler** | Track last call time; skip if too soon |
| 87 | **Fetch API (loading/success/error)** ⭐ | `try/catch` + `finally` for loading state |
| 88 | **Search API with all states** ⭐ | Validate input → fetch → handle 3 states |
| 89 | **Promise Chain** | `getUser().then(getPosts).then(getComments)` OR `async/await` |

---

## 🔹 LEVEL 16 — React Programs (Programs 90–94)

| # | Problem | Key Hooks Used |
|---|---------|---------------|
| 90 | **Counter** ⭐ | `useState` |
| 91 | **Todo App** ⭐🔥 | `useState` (array), filter, map |
| 92 | **API User Finder (GitHub)** ⭐🔥 | `useState` + `useEffect` + fetch |
| 93 | **Debounced React Search** ⭐ | `useState` + `useEffect` (cleanup = `clearTimeout`) |
| 94 | **Multi-Component Dashboard** ⭐ | Component hierarchy, lifted state, no prop drilling |

---

## 🔹 LEVEL 17 — AI Practical (AI 1–3)

| # | Problem | Key Concepts |
|---|---------|-------------|
| AI 1 | **Prompt for binary search explanation** | Structured output prompt: intuition+algorithm+code+complexity+dry-run+edge cases |
| AI 2 | **Prompt for code review** | Role prompting + structured output: Bug/Why/Fix/Complexity/Improved Code |
| AI 3 | **AI Agent Workflow Design** | Think→Act→Observe→Repeat; safeguard: max iterations + deduplication |

---

## 🔹 LEVEL 18 — Project / Debugging Challenges (Challenges 1–5)

| # | Challenge | Root Cause | Fix |
|---|-----------|-----------|-----|
| 1 | **React Infinite Rendering** | `useEffect` sets state with no/wrong deps | Fix dependency array; don't set state that triggers the effect |
| 2 | **API Fails After Deployment** | Env vars, CORS, HTTPS, wrong URL | Check `.env`, add CORS headers, use HTTPS |
| 3 | **Search Fires 20 Times** | No debounce | `clearTimeout+setTimeout(500ms)` |
| 4 | **Git Secret Leak** ⭐🔥 | File deleted but history contains it | Revoke key → BFG/filter-branch to scrub history → rotate key |
| 5 | **O(n²) DSA Optimization** | Nested loop for duplicate check | Replace inner loop with HashSet → O(n) |

---

---

# 🔥 FINAL 30 HIGH-PRIORITY QUESTIONS

> These are the **absolute must-know** questions for a strong candidate.

| # | Topic | Question | Key Answer |
|---|-------|---------|-----------|
| 1 | DSA | Big-O of nested loop `for(i=0..n) for(j=i..n)` | **O(n²)** — triangular iterations = n(n+1)/2 |
| 2 | DSA | Two Sum in O(n) | HashMap — store seen, check complement |
| 3 | DSA | Move zeroes O(n) | Two pointers — overwrite non-zeroes, fill rest with 0 |
| 4 | DSA | Reverse linked list | prev/curr/next — 3 pointer technique |
| 5 | DSA | Detect linked list cycle | Floyd's slow+fast — meet if cycle |
| 6 | DSA | Middle of linked list | Slow+fast — slow at middle when fast at end |
| 7 | DSA | Check balanced parentheses | Stack — push open, pop+match close |
| 8 | DSA | Implement binary search | `mid=left+(right-left)/2`; check sorted condition |
| 9 | DSA | First and last occurrence | Binary search — go left/right on match |
| 10 | DSA | Maximum subarray sum | Kadane's — `max(arr[i], curr+arr[i])` |
| 11 | DSA | Longest substring no repeats | Sliding window + HashMap |
| 12 | Java | Explain HashMap internally | Array of buckets; hash → index; collision → chaining |
| 13 | Java | Explain HashMap collision | Two keys → same bucket → linked list → tree (Java 8) |
| 14 | Java | String immutability | Once created, cannot change; modifications create new String |
| 15 | Java | ArrayList vs LinkedList | ArrayList=O(1) access; LinkedList=O(1) insert at head |
| 16 | Java | HashMap vs HashSet vs TreeMap | K-V / keys only / sorted keys |
| 17 | Java | Method overloading vs overriding | Same class+diff params / child redefines parent |
| 18 | Java | Abstraction vs encapsulation | Hide complexity / protect data |
| 19 | Java | Checked vs unchecked exceptions | Must handle at compile time / runtime only |
| 20 | SQL | Second-highest salary | `SELECT MAX(sal) WHERE sal < (SELECT MAX(sal) FROM ...)` |
| 21 | SQL | Highest salary per department | `MAX(salary) GROUP BY dept_id` |
| 22 | SQL | WHERE vs HAVING | WHERE=rows before group / HAVING=groups after aggregate |
| 23 | SQL | INNER JOIN vs LEFT JOIN | Intersection only / All left + matched right |
| 24 | JS | Promise + async/await | Promise=async object; await=pause async function |
| 25 | JS | Predict event-loop output | A→D→C→B (Sync→Microtask→Macrotask) |
| 26 | JS | Explain closure | Function retains access to outer scope after outer returns |
| 27 | JS | Debounce vs throttle | Wait for calm / rate limiter |
| 28 | React | State vs props | Props=parent data(read-only) / State=own data(triggers re-render) |
| 29 | React | useEffect + dependency array | `[]`=once | `[x]`=when x changes | omit=every render |
| 30 | React | React app with API + loading/error/success | `useState`(data,loading,error) + `useEffect`(fetch) + conditional render |

---

## ⚡ ANSWER QUICK-REFERENCE TABLE (All MCQs)

| Q# | Ans | Q# | Ans | Q# | Ans | Q# | Ans |
|----|-----|----|-----|----|-----|----|-----|
| Q1 | B | Q26 | B | Q51 | C | Q76 | C |
| Q2 | C | Q27 | C | Q52 | D | Q77 | B |
| Q3 | C | Q28 | C | Q53 | B | Q78 | A |
| Q4 | B | Q29 | D | Q54 | B | Q79 | B |
| Q5 | B | Q30 | C | Q55 | A | Q80 | C |
| Q6 | B | Q31 | B | Q56 | A | Q81 | B |
| Q7 | B | Q32 | B | Q57 | C | Q82 | A |
| Q8 | C | Q33 | B | Q58 | B | Q83 | B |
| Q9 | C | Q34 | B | Q59 | B | Q84 | B |
| Q10 | B | Q35 | C | Q60 | C | Q85 | B |
| Q11 | B | Q36 | B | Q61 | B | Q86 | B |
| Q12 | B | Q37 | B | Q62 | C | Q87 | A |
| Q13 | B | Q38 | B | Q63 | B | Q88 | A |
| Q14 | C | Q39 | D | Q64 | B | Q89 | B |
| Q15 | B | Q40 | C | Q65 | B | Q90 | B |
| Q16 | B | Q41 | A | Q66 | A | Q91 | A |
| Q17 | B | Q42 | B | Q67 | C | Q92 | B |
| Q18 | B | Q43 | C | Q68 | B | Q93 | B |
| Q19 | C | Q44 | A | Q69 | B | Q94 | B |
| Q20 | B | Q45 | C | Q70 | B | Q95 | C |
| Q21 | B | Q46 | B | Q71 | A | Q96 | D |
| Q22 | B | Q47 | B | Q72 | B | Q97 | B |
| Q23 | B | Q48 | A | Q73 | B | Q98 | B |
| Q24 | C | Q49 | B | Q74 | B | Q99 | B |
| Q25 | B | Q50 | B | Q75 | B | Q100 | B |
| Q101 | B | Q120 | C | Q139 | A | Q158 | A |
| Q102 | B | Q121 | A | Q140 | B | Q159 | A |
| Q103 | B | Q122 | B | Q141 | A | Q160 | A |
| Q104 | B | Q123 | A | Q142 | A | Q161 | A |
| Q105 | C | Q124 | B | Q143 | A | Q162 | A |
| Q106 | B | Q125 | A | Q144 | A | Q163 | A |
| Q107 | B | Q126 | B | Q145 | B | Q164 | B |
| Q108 | A | Q127 | C | Q146 | B | Q165 | A |
| Q109 | B | Q128 | A | Q147 | C | Q166 | B |
| Q110 | B | Q129 | C | Q148 | B | Q167 | B |
| Q111 | A | Q130 | B | Q149 | A | Q168 | A |
| Q112 | B | Q131 | A | Q150 | A | Q169 | D |
| Q113 | B | Q132 | B | Q151 | A | | |
| Q114 | B | Q133 | B | Q152 | A | | |
| Q115 | A | Q134 | A | Q153 | B | | |
| Q116 | A | Q135 | B | Q154 | B | | |
| Q117 | A | Q136 | B | Q155 | B | | |
| Q118 | B | Q137 | A | Q156 | B | | |
| Q119 | A | Q138 | B | Q157 | A | | |
