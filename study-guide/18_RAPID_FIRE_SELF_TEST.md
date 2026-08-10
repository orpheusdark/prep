# 📝 RAPID-FIRE SELF TEST

> Attempt ALL questions first. Answers are at the BOTTOM.

---

## ROUND 1 — HTML & CSS

1. What does `<!DOCTYPE html>` do?
2. What is the difference between `<section>` and `<article>`?
3. Why is the `alt` attribute important?
4. What is the specificity of `#nav .item a`?
5. What is the CSS box model? Name its 4 layers from inside to outside.
6. What is the difference between `display: none` and `visibility: hidden`?
7. In Flexbox, which property aligns items along the main axis?
8. In Flexbox, which property aligns items along the cross axis?
9. How do you center an element horizontally AND vertically with Flexbox?
10. What is the difference between `rem` and `px`?

---

## ROUND 2 — JavaScript Core

11. Name all 7 falsy values in JavaScript.
12. What is hoisting? How does it differ for `var` vs `let`?
13. What is the Temporal Dead Zone (TDZ)?
14. What does `map()` return? What does `forEach()` return?
15. What is the difference between `==` and `===`?
16. What does `typeof null` return?
17. What is the difference between shallow copy and deep copy? How do you deep copy?
18. What is event bubbling? What is event delegation?
19. What is the difference between `slice()` and `splice()`?
20. Is `[]` truthy or falsy?

---

## ROUND 3 — JavaScript Advanced

21. What is a closure? Give an example use case.
22. What is the output of: `console.log("A"); setTimeout(()=>console.log("B"),0); Promise.resolve().then(()=>console.log("C")); console.log("D");`
23. What is the difference between microtasks and macrotasks?
24. What does `await` actually do?
25. What is debouncing? When do you use it?
26. What is the difference between `??` and `||`?
27. What does optional chaining (`?.`) do?
28. How is an arrow function different from a regular function regarding `this`?
29. What are spread and rest operators? How are they different?
30. What does `async function` return?

---

## ROUND 4 — Java & OOP

31. Name the 4 pillars of OOP.
32. What is the difference between JDK, JRE, and JVM?
33. Why is Java platform-independent?
34. What is encapsulation?
35. What is the difference between method overloading and overriding?
36. What is the difference between `throw` and `throws`?
37. Does `finally` always execute?
38. Why is `String` immutable in Java?
39. What is the difference between `StringBuilder` and `StringBuffer`?
40. What is the difference between interface and abstract class?

---

## ROUND 5 — DSA

41. What is the time complexity of binary search?
42. What condition must be met before binary search?
43. What is the correct `mid` formula in binary search? Why?
44. What is the time complexity of Merge Sort? Is it stable?
45. Stack = LIFO or FIFO? Queue = LIFO or FIFO?
46. How would you find the missing number from 1...n in O(n) time and O(1) space?
47. What algorithm is used for the Two Sum problem in O(n)?
48. What is Kadane's algorithm used for?
49. What are Floyd's slow and fast pointers used for?
50. What does BFS use? What does DFS use? When is each preferred?

---

## ROUND 6 — React

51. What is the Virtual DOM and why does React use it?
52. What is the difference between props and state?
53. What does `useEffect(() => {}, [])` do?
54. What happens if you omit the dependency array in `useEffect`?
55. What is the difference between `useRef` and `useState`?
56. What is prop drilling? How do you solve it?
57. Why should you never use array index as a key in React lists?
58. What causes a React component to re-render?
59. What is the difference between controlled and uncontrolled components?
60. What is lifting state up?

---

## ROUND 7 — SQL

61. What is the difference between `WHERE` and `HAVING`?
62. Write a query to find the second highest salary.
63. What is the difference between `RANK()` and `DENSE_RANK()`?
64. What is a CTE? How do you write one?
65. What does `INNER JOIN` return vs `LEFT JOIN`?
66. What does `PARTITION BY` do in a window function?
67. What is a composite index? What is the leftmost rule?
68. What are ACID properties?
69. Write SQL to find duplicate records.
70. What is a correlated subquery?

---

## ROUND 8 — Mixed/Misc

71. What is the difference between `git pull` and `git fetch`?
72. What is the difference between `git reset` and `git revert`?
73. What should never be committed to a GitHub repository?
74. HTTP 401 vs 403 — what is the difference?
75. What is CORS and why do CORS errors occur?
76. What is temperature in an LLM?
77. What safeguards prevent an AI agent from looping indefinitely?
78. For 1M records, which data structure gives O(1) lookup?
79. You need to undo operations one by one. Which data structure?
80. How do you find the shortest path in an unweighted graph?

---

---

# ✅ ANSWERS

---

## ROUND 1 — HTML & CSS

1. Tells the browser to use HTML5 standard mode (not a tag itself)
2. `<section>` groups related content on the page; `<article>` is self-contained publishable content
3. Displayed when image fails; read by screen readers (accessibility); improves SEO
4. 1-1-1 (one ID + one class + one element)
5. Content → Padding → Border → Margin
6. `display: none` removes from layout entirely; `visibility: hidden` hides but keeps space
7. `justify-content`
8. `align-items`
9. `display: flex; justify-content: center; align-items: center;` on parent (must have a height)
10. `rem` is relative to root font size (scales with user browser settings); `px` is fixed

---

## ROUND 2 — JavaScript Core

11. `false, 0, -0, 0n, "", null, undefined, NaN`
12. Hoisting moves declarations to top. `var` is initialized as `undefined`. `let`/`const` are hoisted but NOT initialized (TDZ)
13. The period between `let`/`const` being hoisted and their declaration line — accessing in this period throws `ReferenceError`
14. `map()` returns a new array of same length; `forEach()` returns `undefined`
15. `==` performs type coercion; `===` checks type AND value strictly (always use `===`)
16. `"object"` (historical bug)
17. Shallow copy shares nested object references (`{...obj}`). Deep copy is fully independent (`structuredClone(obj)`)
18. Bubbling = event propagates up through ancestor elements. Delegation = one listener on parent uses bubbling to handle child events
19. `slice()` returns new array, doesn't mutate; `splice()` modifies original array, returns removed elements
20. Truthy (`[]` is an object reference — truthy)

---

## ROUND 3 — JavaScript Advanced

21. A function that retains access to outer scope variables even after outer function returns. Use case: counter with private state, memoization, factory functions
22. **A, D, C, B** — Sync first, then microtasks (Promise), then macrotasks (setTimeout)
23. Microtasks (Promise callbacks) execute before macrotasks (setTimeout, setInterval) after the call stack clears
24. Pauses the async function until the Promise resolves, then returns the value. Doesn't block the main thread
25. Debouncing delays a function until activity stops. Use for search boxes — wait until user stops typing
26. `??` only triggers fallback for `null`/`undefined`. `||` triggers for any falsy value (including `0`, `""`)
27. Returns `undefined` instead of throwing if the accessed property doesn't exist (safe property access)
28. Arrow functions have no own `this` — they inherit `this` from lexical scope. Regular functions' `this` depends on the caller
29. Spread (`...arr`) expands iterable into individual elements. Rest (`...args`) collects remaining arguments into an array
30. Always returns a Promise (wrapping the return value)

---

## ROUND 4 — Java & OOP

31. Encapsulation, Inheritance, Polymorphism, Abstraction
32. JVM executes bytecode; JRE = JVM + libraries; JDK = JRE + compiler + tools. JDK > JRE > JVM
33. Java compiles to bytecode (not machine code) which is platform-neutral; JVM on any OS runs it ("Write Once, Run Anywhere")
34. Bundling data and methods together; restricting access to internals via `private` fields and `public` getters/setters
35. Overloading: same class, different parameters, compile-time. Overriding: child redefines parent method, runtime
36. `throw` actually throws an exception; `throws` declares that a method may throw an exception
37. Yes — `finally` always executes even if there's a return, an exception, or no catch block
38. Thread safety, String Pool optimization, security (strings used in network/DB connections)
39. Both mutable. `StringBuilder` is NOT thread-safe (faster); `StringBuffer` IS thread-safe (synchronized, slower)
40. Interface: multiple implementation, all abstract by default, no fields except constants. Abstract class: single inheritance, mix of abstract and concrete methods, any fields

---

## ROUND 5 — DSA

41. O(log n) — halves search space each step
42. Array must be **sorted**
43. `left + (right - left) / 2` — avoids integer overflow with large values
44. O(n log n) for all cases (best/avg/worst); YES it is stable
45. Stack = LIFO; Queue = FIFO
46. `n*(n+1)/2 - sum(arr)` — expected sum minus actual sum = missing number
47. HashMap — store seen numbers, check if `target - current` exists in map
48. Finding the maximum subarray sum — "extend or restart at each element"
49. Detecting cycles in linked lists and finding the middle node
50. BFS uses a Queue → shortest path in unweighted graphs. DFS uses Stack/Recursion → cycle detection, connected components, depth-first exploration

---

## ROUND 6 — React

51. React's in-memory copy of the real DOM. React diffs old and new virtual DOMs to apply minimal real DOM changes efficiently
52. Props: from parent, read-only. State: internal, mutable, triggers re-render when changed
53. Runs once after the first render (like componentDidMount)
54. The effect runs after every render — can cause infinite loops if state is set inside
55. `useRef` does NOT trigger re-render; `useState` does. Both persist across renders. `useRef` accessed via `.current`
56. Passing props through many unnecessary intermediaries. Solve with Context API or state management library
57. When items reorder or are removed, React may incorrectly reuse DOM elements, causing UI bugs
58. State change, props change, parent re-render, context change
59. Controlled: value managed by React state (`value + onChange`). Uncontrolled: value managed by DOM (`ref`)
60. Moving state from child to their common parent so siblings can share it via props

---

## ROUND 7 — SQL

61. `WHERE` filters rows before grouping; `HAVING` filters groups after aggregation
62. `SELECT MAX(salary) FROM employees WHERE salary < (SELECT MAX(salary) FROM employees);`
63. `RANK()` skips numbers after ties (1,2,2,4). `DENSE_RANK()` doesn't skip (1,2,2,3)
64. `WITH name AS (SELECT ...) SELECT * FROM name;` — named temporary result set
65. INNER JOIN = only matching rows in both. LEFT JOIN = all left rows + matched right (NULL if no match)
66. Divides rows into groups for window function calculation (like GROUP BY but doesn't collapse rows)
67. Index on multiple columns. The leftmost rule: index used only if the query starts with the leftmost column
68. Atomicity (all or nothing), Consistency (valid state), Isolation (transactions don't interfere), Durability (committed = permanent)
69. `SELECT col, COUNT(*) FROM table GROUP BY col HAVING COUNT(*) > 1;`
70. A subquery that references the outer query and re-executes for every row of the outer query

---

## ROUND 8 — Mixed/Misc

71. `git fetch` downloads but doesn't merge. `git pull` = fetch + merge
72. `git reset` rewrites history (dangerous on shared branches). `git revert` creates a new commit to undo (safe)
73. API keys, passwords, tokens, `.env` files, `node_modules/`, build artifacts
74. 401 = not authenticated ("who are you?"). 403 = authenticated but no permission ("you can't do this")
75. Browser security policy blocking requests from one origin to another. Occurs when server doesn't send `Access-Control-Allow-Origin` header
76. Controls randomness of output. Low = predictable/factual. High = creative/diverse
77. Max iteration limit, tool call deduplication, timeout, explicit stopping condition, human-in-the-loop
78. HashMap — O(1) average lookup using hash function
79. Stack — LIFO, pop gives you the most recent operation first
80. BFS (Breadth-First Search) — explores level by level, first path found = shortest path
