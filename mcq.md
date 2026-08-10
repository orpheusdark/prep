# TECH PASSPORT — MASTER MCQ + CODING QUESTION BANK

## Sections

* Section 1 — Tech Rookie
* Section 2 — Tech Pro
* Section 3 — Tech Elite
* Section 4 — Integrated Challenge Problems

---

# SECTION 1 — TECH ROOKIE

# PART A — HTML MCQs

### Q1. What is the purpose of `<!DOCTYPE html>`?

A. Defines the page title
B. Tells the browser to use HTML5 standards mode
C. Imports CSS
D. Creates the root HTML element

**Answer: B**

---

### Q2. Which is a semantic HTML element?

A. `<div>`
B. `<span>`
C. `<section>`
D. `<b>`

**Answer: C**

---

### Q3. Which attribute provides alternative text for an image?

A. `src`
B. `href`
C. `alt`
D. `title`

**Answer: C**

---

### Q4. Which element is most appropriate for the main navigation of a website?

A. `<navigation>`
B. `<nav>`
C. `<menu>`
D. `<links>`

**Answer: B**

---

### Q5. Which statement about IDs is correct?

A. Multiple elements should normally share the same ID
B. An ID should uniquely identify an element
C. IDs can only be used in JavaScript
D. IDs have lower CSS specificity than classes

**Answer: B**

---

### Q6. Which element associates descriptive text with a form input?

A. `<caption>`
B. `<label>`
C. `<description>`
D. `<text>`

**Answer: B**

---

### Q7. What does the `required` attribute do?

A. Makes an input read-only
B. Prevents the form from submitting if the field is empty
C. Automatically fills the input
D. Encrypts the input

**Answer: B**

---

### Q8. Which HTTP method is normally used when retrieving data?

A. POST
B. PUT
C. GET
D. DELETE

**Answer: C**

---

### Q9. Which element represents the most important heading?

A. `<heading>`
B. `<h6>`
C. `<h1>`
D. `<head>`

**Answer: C**

---

### Q10. Which is generally better for accessibility and SEO?

A. Using only `<div>` elements
B. Semantic HTML
C. Using inline styles
D. Using JavaScript for all content

**Answer: B**

---

# PART B — CSS MCQs

### Q11. Which property controls space inside an element's border?

A. margin
B. padding
C. spacing
D. gap

**Answer: B**

---

### Q12. Which property controls space outside an element's border?

A. padding
B. margin
C. border-spacing
D. outside

**Answer: B**

---

### Q13. What does this do?

```css
* {
    box-sizing: border-box;
}
```

A. Removes borders
B. Makes width/height include padding and border
C. Makes every element inline
D. Removes margin

**Answer: B**

---

### Q14. Which has the highest specificity?

A. `p`
B. `.text`
C. `#text`
D. `*`

**Answer: C**

---

### Q15. What does `display: none` do?

A. Makes the element transparent
B. Removes the element from the layout
C. Moves it behind other elements
D. Makes it invisible but preserves layout space

**Answer: B**

---

### Q16. What does `visibility: hidden` do?

A. Removes the element from layout
B. Hides the element while preserving its layout space
C. Deletes the element
D. Changes its opacity to 50%

**Answer: B**

---

### Q17. Which property is primarily used to control the main-axis alignment in Flexbox?

A. align-items
B. justify-content
C. align-content
D. place-items

**Answer: B**

---

### Q18. Which property controls the cross-axis alignment in a normal row Flexbox?

A. justify-content
B. align-items
C. flex-direction
D. flex-wrap

**Answer: B**

---

### Q19. What happens here?

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

A. Only horizontal centering
B. Only vertical centering
C. Centering along both axes
D. No centering

**Answer: C**

---

### Q20. Which unit is relative to the root element's font size?

A. em
B. rem
C. vh
D. %

**Answer: B**

---

### Q21. `1vh` represents:

A. 1% of element width
B. 1% of viewport height
C. 1% of viewport width
D. 1px

**Answer: B**

---

### Q22. Which CSS feature is primarily used for responsive layouts based on screen conditions?

A. Variables
B. Media queries
C. Pseudo-elements
D. Transforms

**Answer: B**

---

### Q23. What does `position: absolute` position an element relative to?

A. Always the viewport
B. Its nearest positioned ancestor
C. The browser window only
D. The `<body>` regardless of ancestors

**Answer: B**

---

### Q24. Which property controls stacking order?

A. stack
B. layer
C. z-index
D. order-index

**Answer: C**

---

### Q25. Which is best suited for two-dimensional layouts?

A. Flexbox
B. CSS Grid
C. Float
D. Inline-block

**Answer: B**

---

# PART C — JAVASCRIPT FUNDAMENTALS

### Q26. Which declaration creates a block-scoped variable that can be reassigned?

A. var
B. let
C. const
D. static

**Answer: B**

---

### Q27. Which cannot normally be reassigned?

A. var
B. let
C. const
D. function

**Answer: C**

---

### Q28. What is the output?

```javascript
console.log(5 == "5");
console.log(5 === "5");
```

A.

```text
true
true
```

B.

```text
false
false
```

C.

```text
true
false
```

D.

```text
false
true
```

**Answer: C**

---

### Q29. Which is NOT falsy?

A. `0`
B. `""`
C. `null`
D. `[]`

**Answer: D**

---

### Q30. What is `typeof null`?

A. `"null"`
B. `"undefined"`
C. `"object"`
D. `"empty"`

**Answer: C**

---

### Q31. What is `NaN`?

A. Null value
B. Not-a-Number value
C. Undefined variable
D. Empty string

**Answer: B**

---

### Q32. Which method creates a new array by transforming every element?

A. filter
B. map
C. reduce
D. forEach

**Answer: B**

---

### Q33. Which method selects elements satisfying a condition?

A. map
B. filter
C. reduce
D. every

**Answer: B**

---

### Q34. Which method is commonly used to accumulate an array into one value?

A. map
B. reduce
C. filter
D. find

**Answer: B**

---

### Q35. What does `forEach()` return?

A. A transformed array
B. The first matching element
C. Normally `undefined`
D. A Promise

**Answer: C**

---

### Q36. What is the output?

```javascript
const arr = [1, 2, 3];

const result = arr.map(x => x * 2);

console.log(result);
```

A. `[1,2,3]`
B. `[2,4,6]`
C. `[1,4,9]`
D. `6`

**Answer: B**

---

### Q37. What does `push()` do?

A. Adds to beginning
B. Adds to end
C. Removes from beginning
D. Removes from end

**Answer: B**

---

### Q38. What does `shift()` do?

A. Adds to beginning
B. Removes from beginning
C. Adds to end
D. Removes from end

**Answer: B**

---

### Q39. Which method does NOT mutate the original array?

A. splice
B. push
C. pop
D. slice

**Answer: D**

---

### Q40. Which operator checks both value and type?

A. `=`
B. `==`
C. `===`
D. `!=`

**Answer: C**

---

# PART D — JAVASCRIPT OUTPUT QUESTIONS

### Q41.

```javascript
let x = 10;

if (true) {
    let x = 20;
}

console.log(x);
```

A. 10
B. 20
C. undefined
D. Error

**Answer: A**

---

### Q42.

```javascript
var x = 10;

if (true) {
    var x = 20;
}

console.log(x);
```

A. 10
B. 20
C. undefined
D. Error

**Answer: B**

---

### Q43.

```javascript
console.log(typeof undefined);
```

A. null
B. undefined
C. `"undefined"`
D. object

**Answer: C**

---

### Q44.

```javascript
console.log([] == false);
```

A. true
B. false
C. undefined
D. error

**Answer: A**

---

### Q45.

```javascript
const a = [1, 2, 3];
const b = a;

b.push(4);

console.log(a);
```

A. `[1,2,3]`
B. `[4]`
C. `[1,2,3,4]`
D. Error

**Answer: C**

---

# PART E — DOM

### Q46. Which method selects the first matching CSS selector?

A. `getElement()`
B. `querySelector()`
C. `querySelectorAll()`
D. `select()`

**Answer: B**

---

### Q47. What does `querySelectorAll()` return?

A. One element
B. A collection of matching elements
C. A string
D. JSON

**Answer: B**

---

### Q48. Which is used to attach an event handler?

A. `addEventListener()`
B. `attachEventOnly()`
C. `eventHandler()`
D. `listen()`

**Answer: A**

---

### Q49. Event bubbling means:

A. Event moves from parent to child only
B. Event propagates from target toward ancestors
C. Event disappears
D. Event is converted to JSON

**Answer: B**

---

# PART F — JAVA BASICS

### Q50. Which component executes Java bytecode?

A. JDK
B. JVM
C. JRE compiler
D. javac only

**Answer: B**

---

### Q51. Which compiles Java source code into bytecode?

A. JVM
B. JRE
C. javac
D. JIT only

**Answer: C**

---

### Q52. Which is NOT a primitive Java type?

A. int
B. char
C. boolean
D. String

**Answer: D**

---

### Q53. Which is the default value of an instance `int` field?

A. null
B. 0
C. -1
D. undefined

**Answer: B**

---

### Q54. What does `static` mean for a field?

A. Each object gets its own copy
B. It belongs to the class rather than individual instances
C. It cannot change
D. It is private

**Answer: B**

---

### Q55. What is method overloading?

A. Same method name with different parameter lists
B. Same method in parent and child class
C. Multiple classes with same name
D. Calling a method recursively

**Answer: A**

---

### Q56. What is method overriding?

A. Same method signature redefined in a subclass
B. Same method with different parameters
C. Creating multiple constructors
D. Hiding a variable

**Answer: A**

---

# PART G — OOP

### Q57. Which OOP principle hides implementation details?

A. Inheritance
B. Encapsulation
C. Abstraction
D. Polymorphism

**Answer: C**

---

### Q58. Which principle allows one interface to represent different implementations?

A. Encapsulation
B. Polymorphism
C. Composition
D. Aggregation

**Answer: B**

---

### Q59. Which keyword refers to the current object?

A. super
B. this
C. self
D. current

**Answer: B**

---

### Q60. Which keyword accesses members of a parent class?

A. parent
B. base
C. super
D. extends

**Answer: C**

---

### Q61. Can Java classes extend multiple classes?

A. Yes
B. No
C. Only abstract classes
D. Only interfaces

**Answer: B**

---

# PART H — BASIC DSA

### Q62. Array access by index is generally:

A. O(n)
B. O(log n)
C. O(1)
D. O(n²)

**Answer: C**

---

### Q63. Binary search requires:

A. A linked list
B. A sorted search space
C. A HashMap
D. A stack

**Answer: B**

---

### Q64. Binary search complexity is:

A. O(n)
B. O(log n)
C. O(n²)
D. O(1)

**Answer: B**

---

### Q65. Stack follows:

A. FIFO
B. LIFO
C. Random order
D. Sorted order

**Answer: B**

---

### Q66. Queue follows:

A. FIFO
B. LIFO
C. FILO
D. Random order

**Answer: A**

---

### Q67. HashMap average lookup complexity is approximately:

A. O(n²)
B. O(log n)
C. O(1)
D. O(n!)

**Answer: C**

---

# PART I — GIT/GITHUB

### Q68. Git is:

A. A programming language
B. A distributed version control system
C. A database
D. A hosting provider

**Answer: B**

---

### Q69. GitHub is primarily:

A. A compiler
B. A cloud platform for hosting/collaborating on repositories
C. A programming language
D. A database

**Answer: B**

---

### Q70. What does `git add` do?

A. Uploads code
B. Stages changes
C. Creates GitHub repository
D. Deletes changes

**Answer: B**

---

### Q71. What does `git commit` do?

A. Creates a snapshot in local Git history
B. Uploads files to GitHub
C. Deletes the repository
D. Downloads changes

**Answer: A**

---

### Q72. What does `git push` do?

A. Downloads remote changes
B. Uploads local commits to a remote repository
C. Creates a branch only
D. Deletes commits

**Answer: B**

---

### Q73. What does `.gitignore` do?

A. Deletes Git
B. Specifies files Git should ignore
C. Prevents commits
D. Encrypts the repository

**Answer: B**

---

# SECTION 2 — TECH PRO

# PART J — ARRAYS

### Q74. Which approach is best for moving zeroes to the end while maintaining relative order?

A. Sort the array
B. Two pointers
C. Nested loops only
D. Binary search

**Answer: B**

---

### Q75. To find the second-largest element in one pass, you should generally maintain:

A. Only minimum
B. Largest and second-largest
C. A queue
D. A tree only

**Answer: B**

---

### Q76. What is the optimal time complexity for finding the maximum element?

A. O(n²)
B. O(log n)
C. O(n)
D. O(1)

**Answer: C**

---

### Q77. Kadane's algorithm solves:

A. Binary search
B. Maximum subarray sum
C. Sorting
D. Graph traversal

**Answer: B**

---

### Q78. Which technique is commonly used for Two Sum in an unsorted array?

A. HashMap
B. Binary search without sorting
C. DFS
D. Stack only

**Answer: A**

---

# PART K — HASHING

### Q79. Why do we check `containsKey()` before inserting in Two Sum?

A. To sort the map
B. To determine whether the required complement has already been seen
C. To delete the current value
D. To prevent Java compilation

**Answer: B**

---

### Q80. Given:

```java
HashMap<Integer, Integer> map = new HashMap<>();
```

What does `map.get(key)` return if the key doesn't exist?

A. 0
B. -1
C. null
D. false

**Answer: C**

---

### Q81. What does this do?

```java
map.getOrDefault(x, 0) + 1
```

A. Deletes x
B. Reads x's count or uses 0, then increments it
C. Sorts x
D. Inserts only if x exists

**Answer: B**

---

### Q82. What is a hash collision?

A. Two keys produce the same hash bucket/index
B. Two maps merge
C. A key becomes null
D. A map becomes sorted

**Answer: A**

---

# PART L — STRINGS

### Q83. Why is Java `String` immutable?

A. Strings cannot be stored in memory
B. Once created, their contents cannot be changed
C. Strings are always final variables
D. Strings cannot be compared

**Answer: B**

---

### Q84. Which is best for repeated string modifications?

A. String
B. StringBuilder
C. Integer
D. Character

**Answer: B**

---

### Q85. To check whether two strings are anagrams efficiently, a common approach is:

A. Compare their first characters only
B. Character frequency counting
C. Binary search directly
D. Stack only

**Answer: B**

---

# PART M — TWO POINTERS / SLIDING WINDOW

### Q86. Two-pointer techniques are especially useful when:

A. A problem has no structure
B. We can exploit ordering or boundaries to avoid nested loops
C. We always need recursion
D. We need SQL

**Answer: B**

---

### Q87. Sliding window is particularly useful for:

A. Contiguous subarrays/substrings
B. Tree construction only
C. Sorting objects
D. Git operations

**Answer: A**

---

### Q88. Longest substring without repeating characters is commonly solved using:

A. Sliding window + HashSet/HashMap
B. Bubble sort
C. DFS only
D. Stack only

**Answer: A**

---

# PART N — LINKED LIST

### Q89. Which pointer technique finds the middle of a linked list?

A. Binary search
B. Slow and fast pointers
C. HashMap only
D. Sorting

**Answer: B**

---

### Q90. Floyd's algorithm is commonly used to:

A. Sort linked lists
B. Detect cycles
C. Find maximum values
D. Build arrays

**Answer: B**

---

### Q91. Reversing a singly linked list requires maintaining:

A. Previous, current, and next references
B. Only one pointer
C. A binary tree
D. SQL query

**Answer: A**

---

# PART O — STACK / QUEUE

### Q92. Balanced parentheses is naturally solved using:

A. Queue
B. Stack
C. HashSet only
D. Binary search

**Answer: B**

---

### Q93. Which data structure is commonly used for BFS?

A. Stack
B. Queue
C. Heap only
D. HashMap only

**Answer: B**

---

### Q94. Which data structure is naturally associated with DFS recursion?

A. Queue
B. Stack
C. Heap
D. Array only

**Answer: B**

---

# PART P — SORTING

### Q95. Average-case complexity of quicksort is:

A. O(1)
B. O(log n)
C. O(n log n)
D. O(n²) always

**Answer: C**

---

### Q96. Worst-case quicksort complexity can be:

A. O(1)
B. O(log n)
C. O(n log n)
D. O(n²)

**Answer: D**

---

### Q97. Merge sort has:

A. O(n²) guaranteed time
B. O(n log n) time
C. O(log n) time
D. O(1) time

**Answer: B**

---

### Q98. Which sorting algorithm repeatedly swaps adjacent out-of-order elements?

A. Selection sort
B. Bubble sort
C. Merge sort
D. Heap sort

**Answer: B**

---

# PART Q — RECURSION

### Q99. Every recursive function must have:

A. A loop
B. A base case
C. A HashMap
D. A class

**Answer: B**

---

### Q100. Missing a base case can result in:

A. Faster execution
B. Infinite recursion / stack overflow
C. Automatic optimization
D. Compilation into SQL

**Answer: B**

---

# PART R — JAVA COLLECTIONS

### Q101. Which maintains insertion order and allows duplicates?

A. HashSet
B. ArrayList
C. TreeSet
D. HashMap

**Answer: B**

---

### Q102. Which collection does not allow duplicate elements?

A. ArrayList
B. HashSet
C. LinkedList
D. Vector

**Answer: B**

---

### Q103. Which map maintains sorted key order?

A. HashMap
B. TreeMap
C. LinkedHashMap only
D. Hashtable only

**Answer: B**

---

### Q104. Which maintains insertion order for map entries?

A. HashMap
B. LinkedHashMap
C. TreeMap
D. HashSet

**Answer: B**

---

# PART S — EXCEPTIONS

### Q105. Which is a checked exception?

A. NullPointerException
B. ArithmeticException
C. IOException
D. ArrayIndexOutOfBoundsException

**Answer: C**

---

### Q106. Which block generally executes whether or not an exception occurs?

A. catch
B. finally
C. throw
D. throws

**Answer: B**

---

### Q107. `throw` is used to:

A. Declare possible exceptions
B. Explicitly throw an exception
C. Catch exceptions
D. Ignore errors

**Answer: B**

---

### Q108. `throws` is used to:

A. Declare exceptions a method may propagate
B. Create an exception object only
C. Catch an exception
D. Delete an exception

**Answer: A**

---

# PART T — SQL

### Q109. Which clause filters rows before grouping?

A. HAVING
B. WHERE
C. GROUP BY
D. ORDER BY

**Answer: B**

---

### Q110. Which clause filters groups after aggregation?

A. WHERE
B. HAVING
C. ORDER BY
D. SELECT

**Answer: B**

---

### Q111. Which JOIN returns matching rows from both tables?

A. INNER JOIN
B. LEFT JOIN
C. RIGHT JOIN only
D. CROSS JOIN

**Answer: A**

---

### Q112. Which JOIN returns all rows from the left table?

A. INNER JOIN
B. LEFT JOIN
C. RIGHT JOIN
D. CROSS JOIN

**Answer: B**

---

### Q113. Which function counts rows?

A. SUM
B. COUNT
C. TOTAL
D. SIZE

**Answer: B**

---

### Q114. What does `GROUP BY` do?

A. Deletes duplicates
B. Groups rows for aggregation
C. Sorts rows
D. Joins tables

**Answer: B**

---

### Q115. What is a primary key?

A. A column that uniquely identifies rows
B. Any nullable column
C. A foreign table
D. An index only

**Answer: A**

---

# PART U — GIT ADVANCED

### Q116. `git fetch`:

A. Downloads remote information without automatically merging it
B. Deletes remote branches
C. Uploads local code
D. Commits changes

**Answer: A**

---

### Q117. `git pull` generally performs:

A. fetch + integration
B. commit + push
C. reset + delete
D. branch + merge only

**Answer: A**

---

### Q118. `git revert`:

A. Deletes Git history
B. Creates a new commit that reverses a previous commit
C. Deletes the repository
D. Removes remote branches

**Answer: B**

---

### Q119. A merge conflict occurs when:

A. Git cannot automatically reconcile conflicting changes
B. Internet is unavailable
C. The repository has no README
D. GitHub is offline

**Answer: A**

---

# SECTION 3 — TECH ELITE

# PART V — ADVANCED DSA

### Q120. Which algorithm is appropriate for shortest paths in a graph with non-negative edge weights?

A. DFS
B. BFS always
C. Dijkstra
D. Binary search

**Answer: C**

---

### Q121. BFS is particularly useful for shortest path when:

A. The graph is unweighted
B. All edges have arbitrary negative weights
C. The graph is sorted
D. There are no vertices

**Answer: A**

---

### Q122. Which traversal naturally explores a tree level by level?

A. DFS
B. BFS
C. Binary search
D. Backtracking only

**Answer: B**

---

### Q123. Which data structure is commonly used to implement Dijkstra efficiently?

A. Min-heap / priority queue
B. Stack only
C. Queue only
D. String

**Answer: A**

---

### Q124. Topological sorting applies to:

A. Any undirected graph
B. Directed acyclic graphs
C. Arrays
D. Binary heaps only

**Answer: B**

---

### Q125. Number of Islands is commonly solved using:

A. BFS/DFS
B. Binary search
C. Bubble sort
D. HashMap only

**Answer: A**

---

# PART W — TREES

### Q126. Inorder traversal of a BST produces:

A. Random order
B. Sorted order
C. Reverse insertion order
D. Level order

**Answer: B**

---

### Q127. Which traversal is Root → Left → Right?

A. Inorder
B. Postorder
C. Preorder
D. Level-order

**Answer: C**

---

### Q128. Which traversal is Left → Root → Right?

A. Inorder
B. Preorder
C. Postorder
D. BFS

**Answer: A**

---

### Q129. Which traversal is Left → Right → Root?

A. Inorder
B. Preorder
C. Postorder
D. Level order

**Answer: C**

---

### Q130. What is the height of a tree?

A. Number of nodes at root
B. Longest path from root to a leaf, according to the chosen edge/node convention
C. Number of leaves only
D. Number of children of root

**Answer: B**

---

# PART X — DYNAMIC PROGRAMMING

### Q131. DP is generally useful when a problem has:

A. Overlapping subproblems and optimal substructure
B. Only one input
C. No repeated work
D. Only strings

**Answer: A**

---

### Q132. Memoization is:

A. Bottom-up DP
B. Top-down DP with caching
C. Sorting
D. Hashing only

**Answer: B**

---

### Q133. Tabulation is generally:

A. Top-down recursion
B. Bottom-up computation
C. Graph traversal only
D. Backtracking only

**Answer: B**

---

### Q134. Which is a classic DP problem?

A. Climbing Stairs
B. Printing Hello World
C. Reading input
D. Git commit

**Answer: A**

---

# PART Y — ADVANCED JAVASCRIPT

### Q135. What is a closure?

A. A closed HTML tag
B. A function retaining access to variables from its lexical scope
C. A deleted variable
D. A Promise state

**Answer: B**

---

### Q136. What is the event loop responsible for?

A. Compiling Java
B. Coordinating asynchronous callbacks/tasks with the call stack
C. Rendering CSS only
D. Sorting arrays

**Answer: B**

---

### Q137. Which generally executes before timer callbacks after the current synchronous work completes?

A. Microtasks such as Promise callbacks
B. `setTimeout` callbacks always
C. HTML parsing
D. CSS

**Answer: A**

---

### Q138. What is the output?

```javascript
console.log("A");

setTimeout(() => console.log("B"), 0);

Promise.resolve().then(() => console.log("C"));

console.log("D");
```

A.

```text
A
B
C
D
```

B.

```text
A
D
C
B
```

C.

```text
C
A
D
B
```

D.

```text
A
C
D
B
```

**Answer: B**

---

### Q139. Debouncing is useful when:

A. You want an action after the user stops triggering events for a period
B. You want to execute every event immediately
C. You need sorting
D. You need database normalization

**Answer: A**

---

### Q140. Throttling means:

A. Delaying an event forever
B. Limiting how frequently an operation executes
C. Removing events
D. Converting events to promises

**Answer: B**

---

# PART Z — PROMISES / ASYNC

### Q141. A Promise can be:

A. Pending, fulfilled, rejected
B. Open, closed
C. Started, stopped
D. True, false

**Answer: A**

---

### Q142. `async` functions return:

A. Always a Promise
B. Always a string
C. Always undefined
D. A callback

**Answer: A**

---

### Q143. `await` is used to:

A. Pause the surrounding async function until a Promise settles
B. Stop JavaScript permanently
C. Create a thread
D. Compile Java

**Answer: A**

---

# PART AA — API / REST

### Q144. Which status code indicates successful retrieval?

A. 200
B. 301
C. 404
D. 500

**Answer: A**

---

### Q145. Which indicates unauthorized/missing valid authentication?

A. 200
B. 401
C. 403
D. 500

**Answer: B**

---

### Q146. Which indicates the server understood the request but refuses authorization?

A. 401
B. 403
C. 404
D. 500

**Answer: B**

---

### Q147. Which method is generally used to partially update a resource?

A. GET
B. POST
C. PATCH
D. DELETE

**Answer: C**

---

### Q148. What is JSON?

A. A database
B. A lightweight data-interchange format
C. A CSS framework
D. A compiler

**Answer: B**

---

### Q149. CORS is primarily a browser security mechanism related to:

A. Cross-origin requests
B. Database indexing
C. Java compilation
D. Git commits

**Answer: A**

---

# PART AB — REACT

### Q150. React components should generally be:

A. Reusable units of UI
B. SQL queries
C. Git branches
D. Database tables

**Answer: A**

---

### Q151. Props are:

A. Data passed from parent to child
B. Global database variables
C. CSS selectors
D. Browser events only

**Answer: A**

---

### Q152. State represents:

A. Data managed by a component/application that can influence rendering
B. HTML tags
C. Git history
D. API endpoints only

**Answer: A**

---

### Q153. Which Hook manages local state?

A. useEffect
B. useState
C. useRef only
D. useMemo only

**Answer: B**

---

### Q154. Which Hook is commonly used for side effects?

A. useState
B. useEffect
C. useContext only
D. useReducer only

**Answer: B**

---

### Q155. What happens with:

```javascript
useEffect(() => {
    console.log("Hello");
}, []);
```

A. Runs after every render
B. Runs after the initial mount in typical client-side usage
C. Never runs
D. Runs only when props change

**Answer: B**

---

### Q156. Why are keys used in React lists?

A. For database authentication
B. To help React identify list elements across renders
C. To encrypt elements
D. To create CSS classes

**Answer: B**

---

### Q157. What is prop drilling?

A. Passing props through intermediate components unnecessarily
B. Deleting props
C. Converting props into state
D. Calling an API

**Answer: A**

---

### Q158. Which can help avoid prop drilling?

A. Context API
B. HTML
C. CSS Grid
D. Git

**Answer: A**

---

# PART AC — AI FUNDAMENTALS

### Q159. What is an LLM?

A. Large Language Model
B. Local Logic Machine
C. Language Link Manager
D. Linear Learning Method

**Answer: A**

---

### Q160. What is prompt engineering?

A. Designing prompts to obtain more useful/reliable model behavior
B. Building a CPU
C. Writing CSS
D. Training a database

**Answer: A**

---

### Q161. Zero-shot prompting means:

A. Providing no examples for the task
B. Providing exactly zero tokens
C. Training a model from scratch
D. Disabling the model

**Answer: A**

---

### Q162. Few-shot prompting means:

A. Giving a small number of examples
B. Giving no instructions
C. Using a smaller model
D. Using fewer tokens than one

**Answer: A**

---

### Q163. Hallucination means:

A. An AI model produces unsupported or fabricated information
B. A server crashes
C. A browser renders HTML incorrectly
D. A Git conflict

**Answer: A**

---

### Q164. Increasing temperature generally makes generation:

A. More deterministic
B. More varied/random
C. Impossible
D. Faster in all cases

**Answer: B**

---

### Q165. An AI agent differs from a simple chatbot because an agent can:

A. Potentially reason through tasks and use tools/actions
B. Only generate HTML
C. Only answer yes/no
D. Never interact with external systems

**Answer: A**

---

# PART AD — SQL ELITE

### Q166. Which function assigns a unique sequential number to rows within a window?

A. COUNT
B. ROW_NUMBER
C. GROUP_NUMBER
D. INDEX_NUMBER

**Answer: B**

---

### Q167. Difference between `RANK()` and `DENSE_RANK()`?

A. They are identical
B. RANK can leave gaps after ties; DENSE_RANK does not
C. DENSE_RANK sorts strings only
D. RANK cannot handle numbers

**Answer: B**

---

### Q168. A CTE is:

A. Common Table Expression
B. Common Transaction Engine
C. Column Table Entity
D. Cached Table Element

**Answer: A**

---

### Q169. Which property guarantees that a transaction's changes persist after commit?

A. Atomicity
B. Consistency
C. Isolation
D. Durability

**Answer: D**

---

# SECTION 4 — CODING PROGRAMS

## LEVEL 1 — BASIC PROGRAMS

### Program 1 — Largest Element

Given an integer array, find the largest element.

Example:

```text
Input:
5
10 5 20 8 15

Output:
20
```

Target: `O(n)`

---

### Program 2 — Smallest Element

Find the minimum element without sorting.

---

### Program 3 — Second Largest

Find the second-largest distinct element in one pass.

---

### Program 4 — Reverse Array

Reverse an array in-place.

Example:

```text
Input:
1 2 3 4 5

Output:
5 4 3 2 1
```

---

### Program 5 — Check Sorted

Determine whether an array is sorted in non-decreasing order.

---

### Program 6 — Linear Search

Return the index of a target element.

---

### Program 7 — Count Frequencies

Given:

```text
1 2 2 3 3 3 4
```

Output:

```text
1 -> 1
2 -> 2
3 -> 3
4 -> 1
```

Use HashMap.

---

### Program 8 — Move Zeroes

Input:

```text
0 1 0 3 12
```

Output:

```text
1 3 12 0 0
```

Maintain relative order.

Target: `O(n)`.

---

### Program 9 — Remove Duplicates

Given a sorted array, remove duplicates in-place.

---

### Program 10 — Rotate Array

Rotate an array right by `k`.

Example:

```text
Input:
1 2 3 4 5
k = 2

Output:
4 5 1 2 3
```

---

# LEVEL 2 — HASHING

### Program 11 — Two Sum

Given an array and target, return indices of two numbers whose sum equals target.

Target: `O(n)`.

---

### Program 12 — First Non-Repeating Character

Input:

```text
swiss
```

Output:

```text
w
```

---

### Program 13 — Duplicate Number

Find whether an array contains duplicates.

---

### Program 14 — Majority Element

Find an element appearing more than `n/2` times.

Bonus: solve using Boyer-Moore Voting Algorithm.

---

### Program 15 — Longest Consecutive Sequence

Input:

```text
100 4 200 1 3 2
```

Output:

```text
4
```

Target: `O(n)` average.

---

# LEVEL 3 — STRINGS

### Program 16 — Reverse String

Do not use built-in reverse functions.

---

### Program 17 — Palindrome

Check whether a string is a palindrome.

---

### Program 18 — Valid Anagram

Determine whether two strings contain the same characters with the same frequencies.

---

### Program 19 — Remove Duplicate Characters

Input:

```text
programming
```

Return a string containing each character once.

---

### Program 20 — Reverse Words

Input:

```text
"I love programming"
```

Output:

```text
"programming love I"
```

---

### Program 21 — Longest Common Prefix

Input:

```text
flower
flow
flight
```

Output:

```text
fl
```

---

### Program 22 — First Unique Character

Return the index of the first non-repeating character.

---

# LEVEL 4 — TWO POINTERS / SLIDING WINDOW

### Program 23 — Two Sum Sorted

Given a sorted array, solve Two Sum using two pointers.

Target: `O(n)`.

---

### Program 24 — Container With Most Water

Given heights, find the maximum water area.

Target: `O(n)`.

---

### Program 25 — 3Sum

Find all unique triplets whose sum is zero.

Target: approximately `O(n²)`.

---

### Program 26 — Maximum Sum Subarray of Size K

Input:

```text
2 1 5 1 3 2
k = 3
```

Output:

```text
9
```

---

### Program 27 — Longest Substring Without Repeating Characters

Input:

```text
abcabcbb
```

Output:

```text
3
```

---

### Program 28 — Minimum Window Substring

Given strings `s` and `t`, find the smallest substring of `s` containing all characters of `t`.

---

# LEVEL 5 — LINKED LIST

### Program 29 — Reverse Linked List

Reverse a singly linked list iteratively.

---

### Program 30 — Middle of Linked List

Use slow/fast pointers.

---

### Program 31 — Detect Cycle

Implement Floyd's cycle detection.

---

### Program 32 — Remove Nth Node From End

Solve using two pointers.

---

### Program 33 — Merge Two Sorted Lists

Merge two sorted linked lists.

---

### Program 34 — Palindrome Linked List

Determine whether a linked list is a palindrome.

---

# LEVEL 6 — STACK / QUEUE

### Program 35 — Valid Parentheses

Input:

```text
{[()]}
```

Output:

```text
true
```

---

### Program 36 — Implement Stack

Implement stack using an array.

Operations:

```text
push
pop
peek
isEmpty
```

---

### Program 37 — Implement Queue

Implement queue using an array.

---

### Program 38 — Queue Using Two Stacks

Implement:

```text
enqueue()
dequeue()
```

using two stacks.

---

### Program 39 — Next Greater Element

Input:

```text
4 5 2 10
```

Output:

```text
5 10 10 -1
```

---

# LEVEL 7 — BINARY SEARCH

### Program 40 — Binary Search

Implement iterative binary search.

---

### Program 41 — First Occurrence

Find the first occurrence of a target in a sorted array.

---

### Program 42 — Last Occurrence

Find the last occurrence.

---

### Program 43 — Search Rotated Sorted Array

Input:

```text
4 5 6 7 0 1 2
```

Target:

```text
0
```

Output:

```text
4
```

---

### Program 44 — Find Peak Element

Return an index of a peak element.

---

### Program 45 — Integer Square Root

Find `floor(sqrt(x))` using binary search.

---

# LEVEL 8 — SORTING

### Program 46 — Bubble Sort

Implement without built-in sorting.

---

### Program 47 — Selection Sort

Implement selection sort.

---

### Program 48 — Insertion Sort

Implement insertion sort.

---

### Program 49 — Merge Sort

Implement merge sort.

Requirement:

```text
O(n log n)
```

---

### Program 50 — Quick Sort

Implement quicksort and explain its worst case.

---

# LEVEL 9 — RECURSION / BACKTRACKING

### Program 51 — Factorial

Implement recursively.

---

### Program 52 — Fibonacci

Implement:

1. naive recursion
2. memoization
3. tabulation

Compare complexity.

---

### Program 53 — Generate Subsets

For:

```text
[1,2,3]
```

generate all subsets.

---

### Program 54 — Generate Permutations

Generate every permutation of an array/string.

---

### Program 55 — Combination Sum

Find combinations whose values sum to a target.

---

# LEVEL 10 — TREES

### Program 56 — Inorder Traversal

Implement recursively and iteratively.

---

### Program 57 — Preorder Traversal

Implement recursively and iteratively.

---

### Program 58 — Postorder Traversal

Implement recursively and iteratively.

---

### Program 59 — Level Order Traversal

Use BFS.

---

### Program 60 — Maximum Depth

Find maximum depth of a binary tree.

---

### Program 61 — Check Balanced Tree

Determine whether a binary tree is height-balanced.

---

### Program 62 — Diameter of Binary Tree

Return the diameter.

---

### Program 63 — Validate BST

Determine whether a binary tree satisfies BST rules.

---

### Program 64 — Lowest Common Ancestor

Find LCA of two nodes.

---

# LEVEL 11 — GRAPHS

### Program 65 — BFS

Implement BFS for an adjacency list.

---

### Program 66 — DFS

Implement recursive DFS.

---

### Program 67 — Number of Islands

Given a grid of `0`s and `1`s, count connected islands.

---

### Program 68 — Detect Cycle

Detect a cycle in an undirected graph.

---

### Program 69 — Detect Cycle in Directed Graph

Use DFS or Kahn's algorithm.

---

### Program 70 — Shortest Path

Find shortest path in an unweighted graph using BFS.

---

### Program 71 — Dijkstra

Find shortest distances from a source in a weighted graph with non-negative weights.

---

### Program 72 — Topological Sort

Implement Kahn's algorithm.

---

# LEVEL 12 — DYNAMIC PROGRAMMING

### Program 73 — Climbing Stairs

Find the number of ways to climb `n` stairs using 1 or 2 steps.

---

### Program 74 — House Robber

Maximum amount without robbing adjacent houses.

---

### Program 75 — Coin Change

Find the minimum number of coins required for a target amount.

---

### Program 76 — 0/1 Knapsack

Solve using dynamic programming.

---

### Program 77 — Longest Common Subsequence

Find LCS length between two strings.

---

### Program 78 — Longest Increasing Subsequence

Find LIS length.

---

### Program 79 — Edit Distance

Find minimum operations required to convert one string into another.

---

# LEVEL 13 — JAVA PROGRAMS

### Program 80 — Frequency Map

Implement character frequency counting using `HashMap`.

---

### Program 81 — Custom Comparator

Sort objects by:

1. salary descending
2. name ascending when salaries are equal

---

### Program 82 — Student Management

Create:

```text
Student
    id
    name
    marks
```

Store students in an `ArrayList` and:

* add students
* remove students
* search by ID
* sort by marks
* find highest scorer

---

### Program 83 — Exception Handling

Create a program that safely handles:

* division by zero
* invalid array index
* invalid numeric input

---

### Program 84 — HashMap Word Counter

Read a sentence and output word frequencies.

---

# LEVEL 14 — SQL PROGRAMS

Use tables:

```text
Employee(
    id,
    name,
    department_id,
    salary,
    manager_id
)

Department(
    id,
    name
)
```

### SQL 1

Find the highest salary.

### SQL 2

Find the second-highest salary.

### SQL 3

Find the third-highest salary.

### SQL 4

Find employees earning more than the average salary.

### SQL 5

Find the highest-paid employee in every department.

### SQL 6

Find departments having more than 5 employees.

### SQL 7

Find employees who earn more than their manager.

### SQL 8

Find duplicate employee names.

### SQL 9

Use `ROW_NUMBER()` to rank employees by salary within each department.

### SQL 10

Use `DENSE_RANK()` to find the second-highest salary per department.

### SQL 11

Find employees who have no manager.

### SQL 12

Find departments with no employees.

---

# LEVEL 15 — JAVASCRIPT PRACTICAL PROGRAMS

### Program 85 — Debounced Search

Implement:

```javascript
searchUsers(query)
```

so the API isn't called on every keystroke.

---

### Program 86 — Throttle Scroll Handler

Create a throttled scroll event handler that executes at most once every specified interval.

---

### Program 87 — Fetch API

Fetch users from an API and display:

* loading
* success
* error

states.

---

### Program 88 — Search API

Create a search interface that:

1. accepts username
2. calls API
3. displays profile
4. handles invalid username
5. handles network failure
6. handles loading

---

### Program 89 — Promise Chain

Create a sequence:

```text
getUser()
    ↓
getPosts()
    ↓
getComments()
```

using Promises.

---

# LEVEL 16 — REACT PROGRAMS

### Program 90 — Counter

Build a counter using `useState`.

Features:

* increment
* decrement
* reset

---

### Program 91 — Todo Application

Features:

* add
* delete
* mark complete
* filter
* count remaining

---

### Program 92 — API User Finder

Build a React application that:

1. accepts username
2. calls GitHub API
3. displays avatar
4. displays name
5. displays bio
6. displays repositories
7. displays followers
8. handles loading
9. handles errors

---

### Program 93 — Debounced React Search

Implement a search box that waits until the user stops typing before making the API request.

---

### Program 94 — Multi-Component Dashboard

Create:

```text
App
├── Navbar
├── Search
├── UserCard
├── RepositoryList
├── RepositoryCard
└── Footer
```

Use state appropriately and avoid unnecessary prop drilling.

---

# LEVEL 17 — AI PRACTICAL QUESTIONS

### AI 1

Write a prompt that asks an LLM to explain binary search to a beginner but forces it to provide:

* intuition
* algorithm
* Java code
* complexity
* dry run
* edge cases

---

### AI 2

Create a prompt that makes an LLM review Java code and return:

```text
Bug
Why it happens
Fix
Time Complexity
Space Complexity
Improved Code
```

---

### AI 3

Design an AI-agent workflow for:

```text
User Question
      ↓
Understand request
      ↓
Choose tool
      ↓
Execute tool
      ↓
Evaluate result
      ↓
Respond
```

Explain where a loop could occur and how you would prevent infinite execution.

---

# LEVEL 18 — PROJECT / DEBUGGING CHALLENGES

### Challenge 1 — React Infinite Rendering

Given a component that continuously re-renders, identify the likely causes and fix them.

---

### Challenge 2 — API Failure

Your API works locally but fails after deployment.

Investigate:

* environment variables
* CORS
* HTTPS
* API URL
* build configuration
* network requests

---

### Challenge 3 — Slow Search

A search API is called 20 times while the user types:

```text
g
gi
git
gith
githu
github
```

Redesign the implementation using debouncing.

---

### Challenge 4 — Git Secret Leak

An API key was committed and pushed to GitHub.

Explain:

1. Why deleting it from the latest file is insufficient.
2. Why the key should be considered compromised.
3. What should be done with the key.
4. How Git history should be cleaned if necessary.
5. How future secrets should be managed.

---

### Challenge 5 — DSA Optimization

This algorithm is:

```text
for i = 0 to n
    for j = 0 to n
        if arr[i] == arr[j]
            ...
```

Tasks:

1. Determine complexity.
2. Identify the bottleneck.
3. Replace it with a HashMap/HashSet solution.
4. Explain the tradeoff.

---

# FINAL 30 HIGH-PRIORITY QUESTIONS

These are the questions I would absolutely expect a strong candidate to be able to solve or explain.

### 1.

Explain Big-O and determine the complexity of:

```java
for(int i = 0; i < n; i++) {
    for(int j = i; j < n; j++) {
        System.out.println(i + j);
    }
}
```

### 2.

Solve Two Sum in O(n).

### 3.

Move zeroes to the end in O(n).

### 4.

Reverse a linked list.

### 5.

Detect a linked-list cycle.

### 6.

Find the middle of a linked list.

### 7.

Check balanced parentheses.

### 8.

Implement binary search.

### 9.

Find first and last occurrence of a target.

### 10.

Find maximum subarray sum.

### 11.

Solve longest substring without repeating characters.

### 12.

Explain HashMap internally.

### 13.

Explain HashMap collision.

### 14.

Explain String immutability.

### 15.

Explain ArrayList vs LinkedList.

### 16.

Explain HashMap vs HashSet vs TreeMap.

### 17.

Explain method overloading vs overriding.

### 18.

Explain abstraction vs encapsulation.

### 19.

Explain checked vs unchecked exceptions.

### 20.

Write SQL for second-highest salary.

### 21.

Write SQL for highest salary per department.

### 22.

Explain WHERE vs HAVING.

### 23.

Explain INNER JOIN vs LEFT JOIN.

### 24.

Explain Promise and async/await.

### 25.

Predict event-loop output.

### 26.

Explain closure.

### 27.

Explain debounce vs throttle.

### 28.

Explain React state vs props.

### 29.

Explain `useEffect()` and dependency arrays.

### 30.

Build a React application consuming a real API with loading/error/success handling.
