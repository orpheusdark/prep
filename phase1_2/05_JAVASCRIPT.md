# JAVASCRIPT COMPLETE PREPARATION
## Tech Passport Phase 1 + Phase 2

---

# PART 1 — VARIABLES: var, let, const

## The Critical Differences

| Feature | var | let | const |
|---------|-----|-----|-------|
| Scope | Function | Block | Block |
| Hoisting | YES (undefined) | YES (TDZ error) | YES (TDZ error) |
| Re-declare | YES | NO | NO |
| Re-assign | YES | YES | NO |
| Available before declaration | YES (undefined) | NO (ReferenceError) | NO (ReferenceError) |

> MUST REMEMBER: Use `const` for everything by default. Use `let` when you need to change the value. Avoid `var`.

### Hoisting Example — VERY HIGH PROBABILITY TRAP

```javascript
console.log(x);   // undefined (not ReferenceError!)
var x = 5;
console.log(x);   // 5

// JavaScript hoists var to top as:
// var x;          (declaration hoisted)
// console.log(x); // undefined
// x = 5;          (assignment NOT hoisted)

console.log(y);   // ReferenceError — let is NOT usable before declaration
let y = 10;
```

### Scope Example

```javascript
var a = 1;
let b = 2;

if (true) {
    var a = 100;   // modifies outer a! (function-scoped)
    let b = 200;   // NEW b, block-scoped
    console.log(a); // 100
    console.log(b); // 200
}

console.log(a);  // 100 (modified by if block!)
console.log(b);  // 2 (original b, unchanged)
```

---

# PART 2 — DATA TYPES

```javascript
// Primitive types
typeof 42          // "number"
typeof "hello"     // "string"
typeof true        // "boolean"
typeof undefined   // "undefined"
typeof null        // "object"  ← FAMOUS TRAP!
typeof Symbol()    // "symbol"
typeof 42n         // "bigint"

// Reference types
typeof {}          // "object"
typeof []          // "object"  ← Arrays are objects!
typeof function(){} // "function"
```

> EXAM TIP: `typeof null === "object"` is a famous JavaScript bug that has been kept for compatibility. It is NOT null!

---

# PART 3 — == vs === (MOST IMPORTANT TRAP)

```javascript
// == (loose equality) — converts types before comparing
0 == false        // true (false converts to 0)
"" == false       // true ("" converts to 0, false to 0)
null == undefined // true (special rule)
1 == "1"          // true ("1" converts to 1)
0 == ""           // true ("" converts to 0)

// === (strict equality) — NO type conversion
0 === false       // false (number vs boolean)
1 === "1"         // false (number vs string)
null === undefined // false (different types)
```

> MUST REMEMBER: ALWAYS use === in professional code. == causes unexpected bugs.

---

# PART 4 — TRUTHY AND FALSY

**Falsy values** (evaluate to false in conditions):
```javascript
false, 0, "", '', ``, null, undefined, NaN
```

**Everything else is truthy:**
```javascript
"0"     // truthy! (non-empty string)
[]      // truthy! (empty array)
{}      // truthy! (empty object)
-1      // truthy! (non-zero number)
"false" // truthy! (non-empty string)
```

```javascript
if ("") console.log("runs");    // doesn't run
if ("0") console.log("runs");   // RUNS! "0" is truthy
if (0) console.log("runs");     // doesn't run
if ([]) console.log("runs");    // RUNS! [] is truthy
```

---

# PART 5 — OPERATORS

```javascript
// Arithmetic
5 + 2 = 7
5 - 2 = 3
5 * 2 = 10
5 / 2 = 2.5        // JS does NOT do integer division!
5 % 2 = 1          // remainder
2 ** 3 = 8         // exponentiation (2 to the power 3)
"Hi" + "!" = "Hi!" // string concatenation

// String + Number = String (concatenation, NOT addition!)
"5" + 3 = "53"     // TRAP!
5 + "3" = "53"     // TRAP!
"5" - 3 = 2        // subtraction converts to number
"5" * "2" = 10     // both converted to numbers
```

---

# PART 6 — FUNCTIONS

```javascript
// Function declaration (hoisted)
function greet(name) {
    return "Hello, " + name;
}
greet("Alice"); // "Hello, Alice"

// Function expression (NOT hoisted)
const add = function(a, b) {
    return a + b;
};

// Arrow function
const multiply = (a, b) => a * b;       // implicit return
const square = x => x * x;             // one param, no parens needed
const noParam = () => console.log("hi"); // no params, need parens

// Default parameters
function greet(name = "World") {
    return "Hello, " + name;
}
greet();        // "Hello, World"
greet("Alice"); // "Hello, Alice"
```

> EXAM TIP: Arrow functions don't have their own `this`. They inherit `this` from surrounding scope.

---

# PART 7 — ARRAYS

```javascript
let arr = [1, 2, 3, 4, 5];

// Basic access
arr[0]           // 1
arr[arr.length-1]// 5 (last element)
arr.length       // 5

// Adding/Removing
arr.push(6)      // add to END → [1,2,3,4,5,6]
arr.pop()        // remove from END → returns 6
arr.unshift(0)   // add to START → [0,1,2,3,4,5]
arr.shift()      // remove from START → returns 0

// Searching
arr.indexOf(3)   // 2 (index of 3)
arr.includes(3)  // true
arr.find(x => x > 3)  // 4 (first element > 3)
arr.findIndex(x => x > 3)  // 3 (index of first element > 3)

// Transformation (returns NEW array)
arr.map(x => x * 2)          // [2,4,6,8,10]
arr.filter(x => x % 2 === 0) // [2,4]
arr.reduce((sum, x) => sum + x, 0) // 15 (sum)
arr.slice(1, 3)               // [2,3] (from index 1 to 2)

// Sorting
arr.sort()                   // sorts as strings by default!
[10,9,2].sort()              // [10,2,9] WRONG for numbers!
[10,9,2].sort((a,b) => a-b)  // [2,9,10] CORRECT numeric sort

// Other
arr.reverse()                // [5,4,3,2,1] (mutates original)
arr.join(", ")               // "1, 2, 3, 4, 5"
arr.concat([6,7])            // [1,2,3,4,5,6,7] (new array)
arr.splice(1, 2)             // removes 2 elements starting at index 1
```

> COMMON TRAP: `arr.sort()` sorts lexicographically (as strings), not numerically. Always pass a comparator for numbers.

---

# PART 8 — OBJECTS

```javascript
const person = {
    name: "Alice",
    age: 25,
    greet: function() {
        return "Hi, I'm " + this.name;
    }
};

// Access
person.name         // "Alice" (dot notation)
person["age"]       // 25 (bracket notation)
person.greet()      // "Hi, I'm Alice"

// Add property
person.city = "Delhi";

// Delete property
delete person.city;

// Check property exists
"name" in person    // true
person.hasOwnProperty("name")  // true

// Object methods
Object.keys(person)   // ["name", "age", "greet"]
Object.values(person) // ["Alice", 25, function...]
```

---

# PART 9 — STRINGS

```javascript
let s = "Hello World";

s.length           // 11
s.charAt(0)        // "H"
s[0]               // "H" (same thing)
s.indexOf("o")     // 4
s.lastIndexOf("o") // 7
s.includes("World")// true
s.startsWith("He") // true
s.endsWith("ld")   // true
s.slice(0, 5)      // "Hello" (end exclusive)
s.substring(6)     // "World"
s.toUpperCase()    // "HELLO WORLD"
s.toLowerCase()    // "hello world"
s.trim()           // removes whitespace
s.replace("Hello", "Hi") // "Hi World"
s.split(" ")       // ["Hello", "World"]
s.padStart(15, "*") // "****Hello World"

// Template literals
let name = "Alice";
console.log(`Hello, ${name}!`); // "Hello, Alice!"
```

---

# PART 10 — SCOPE & CLOSURE

```javascript
// Global scope
let x = "global";

function outer() {
    let x = "outer";    // shadows global x
    
    function inner() {
        let x = "inner";  // shadows outer x
        console.log(x);   // "inner"
    }
    inner();
    console.log(x);  // "outer"
}

outer();
console.log(x);  // "global"
```

```javascript
// Closure example
function counter() {
    let count = 0;
    return function() {
        count++;
        return count;
    };
}

const increment = counter();
increment();  // 1
increment();  // 2
increment();  // 3
```

---

# PART 11 — DOM BASICS

```javascript
// Selecting elements
document.getElementById("myId")           // by ID
document.getElementsByClassName("myClass") // by class (HTMLCollection)
document.getElementsByTagName("p")         // by tag (HTMLCollection)
document.querySelector(".myClass")         // first match (CSS selector)
document.querySelectorAll("p.highlight")   // all matches (NodeList)

// Changing content
element.textContent = "New text";          // plain text
element.innerHTML = "<b>Bold</b>";         // HTML content

// Changing attributes
element.setAttribute("src", "new.jpg");
element.getAttribute("src");
element.removeAttribute("disabled");

// Changing styles
element.style.color = "red";
element.style.fontSize = "20px";
element.classList.add("active");
element.classList.remove("active");
element.classList.toggle("active");

// Creating elements
const div = document.createElement("div");
div.textContent = "New element";
document.body.appendChild(div);
parent.removeChild(child);
```

---

# PART 12 — EVENTS

```javascript
// Method 1: HTML attribute (avoid in production)
<button onclick="myFunction()">Click</button>

// Method 2: DOM property
document.getElementById("btn").onclick = function() {
    alert("Clicked!");
};

// Method 3: addEventListener (BEST PRACTICE)
document.getElementById("btn").addEventListener("click", function(event) {
    console.log("Clicked!");
    console.log(event.target); // the element that was clicked
});

// Common events
click, dblclick
mouseover, mouseout, mousemove
keydown, keyup, keypress
submit, change, input, focus, blur
load, resize, scroll

// Prevent default behavior
form.addEventListener("submit", function(e) {
    e.preventDefault();  // stops form from submitting
});
```

---

# PART 13 — 25 JAVASCRIPT OUTPUT PREDICTION QUESTIONS

**JS1:**
```javascript
console.log(typeof null);
```
A) null   B) "object"   C) "null"   D) undefined
**Answer: B — typeof null = "object" (famous JS bug)**

**JS2:**
```javascript
console.log(1 + "2" + 3);
```
A) 6   B) "123"   C) "33"   D) Error
**Answer: B — "12" + 3 = "123"**

**JS3:**
```javascript
console.log(1 + 2 + "3");
```
A) "123"   B) 6   C) "33"   D) Error
**Answer: C — 1+2=3 first (numbers), then 3+"3"="33"**

**JS4:**
```javascript
var x = 1;
var x = 2;
console.log(x);
```
A) 1   B) 2   C) Error   D) undefined
**Answer: B — var can be re-declared, second declaration wins**

**JS5:**
```javascript
console.log(x);
var x = 5;
```
A) 5   B) ReferenceError   C) undefined   D) null
**Answer: C — var is hoisted but not initialized**

**JS6:**
```javascript
console.log(0 == false);
console.log(0 === false);
```
A) true,true   B) false,false   C) true,false   D) false,true
**Answer: C — == converts types; === does not**

**JS7:**
```javascript
let arr = [1, 2, 3];
arr.push(4);
arr.pop();
console.log(arr);
```
A) [1,2,3,4]   B) [1,2,3]   C) [2,3]   D) [4]
**Answer: B — push adds 4, pop removes it**

**JS8:**
```javascript
console.log([10,9,2].sort());
```
A) [2,9,10]   B) [10,9,2]   C) [10,2,9]   D) Error
**Answer: C — sort() converts to strings: "10" < "2" < "9"**

**JS9:**
```javascript
let a = 5;
let b = a;
b = 10;
console.log(a);
```
A) 5   B) 10   C) undefined   D) Error
**Answer: A — primitives are copied by value**

**JS10:**
```javascript
function test() {
    console.log(x);
    let x = 5;
}
test();
```
A) undefined   B) 5   C) ReferenceError   D) null
**Answer: C — let is in TDZ before declaration**

**JS11:**
```javascript
const obj = {x: 1};
obj.x = 2;
console.log(obj.x);
```
A) 1   B) 2   C) Error   D) undefined
**Answer: B — const prevents reassignment of obj, but properties can change**

**JS12:**
```javascript
console.log("5" - 3);
```
A) "53"   B) 2   C) "5-3"   D) Error
**Answer: B — subtraction converts "5" to number 5; 5-3=2**

**JS13:**
```javascript
let arr = [1,2,3,4,5];
let result = arr.filter(x => x % 2 === 0);
console.log(result);
```
A) [1,3,5]   B) [2,4]   C) [1,2,3,4,5]   D) []
**Answer: B — filter keeps even numbers**

**JS14:**
```javascript
let arr = [1,2,3];
let doubled = arr.map(x => x * 2);
console.log(arr);
console.log(doubled);
```
A) [2,4,6], [2,4,6]   B) [1,2,3], [2,4,6]   C) [2,4,6], [1,2,3]   D) Error
**Answer: B — map returns NEW array; original unchanged**

**JS15:**
```javascript
console.log(null == undefined);
console.log(null === undefined);
```
A) true,true   B) false,false   C) true,false   D) false,true
**Answer: C**

**JS16:**
```javascript
function greet(name = "World") {
    return `Hello, ${name}!`;
}
console.log(greet());
console.log(greet("Alice"));
```
A) "Hello, !", "Hello, Alice!"
B) "Hello, World!", "Hello, Alice!"
C) Error
D) "Hello, undefined!", "Hello, Alice!"
**Answer: B — default parameter used when no argument provided**

**JS17:**
```javascript
let x = 10;
if (true) {
    let x = 20;
    console.log(x);
}
console.log(x);
```
A) 20,20   B) 10,10   C) 20,10   D) Error
**Answer: C — let is block-scoped; inner x shadows outer x**

**JS18:**
```javascript
let arr = [1,2,3];
arr.splice(1, 1);
console.log(arr);
```
A) [1,2,3]   B) [1,3]   C) [2,3]   D) [1,2]
**Answer: B — splice(1,1) removes 1 element at index 1 (which is 2)**

**JS19:**
```javascript
let str = "hello";
str[0] = "H";
console.log(str);
```
A) "Hello"   B) "hello"   C) Error   D) undefined
**Answer: B — strings are immutable in JS; assignment is silently ignored**

**JS20:**
```javascript
console.log(typeof []);
console.log(Array.isArray([]));
```
A) "array", true   B) "object", true   C) "array", false   D) "object", false
**Answer: B — arrays are objects; use Array.isArray() to check**

**JS21:**
```javascript
for (var i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 100);
}
```
A) 0, 1, 2   B) 3, 3, 3   C) 0, 0, 0   D) Error
**Answer: B — var is function-scoped, i is 3 by the time timeouts run. Use let to get 0,1,2.**

**JS22:**
```javascript
let a = [];
console.log(a == false);
console.log(!!a);
```
A) true,false   B) true,true   C) false,true   D) false,false
**Answer: B — [] == false is true (coercion); !![] is true ([] is truthy)**

**JS23:**
```javascript
function add(a, b) { return a + b; }
const result = add(1, 2, 3, 4);
console.log(result);
```
A) Error   B) 10   C) 3   D) undefined
**Answer: C — extra arguments are ignored; only a=1,b=2 used; 1+2=3**

**JS24:**
```javascript
const obj1 = {x: 1};
const obj2 = {x: 1};
console.log(obj1 == obj2);
console.log(obj1 === obj2);
```
A) true,true   B) false,false   C) true,false   D) false,true
**Answer: B — objects compared by reference, not value; different objects**

**JS25:**
```javascript
let result = [1,2,3].reduce((acc, curr) => acc + curr, 0);
console.log(result);
```
A) 0   B) [1,2,3]   C) 6   D) 3
**Answer: C — 0+1=1, 1+2=3, 3+3=6**

---

# PART 14 — DOM MINI TASK

Write JavaScript to:
1. Get the element with id "message"
2. Change its text to "Hello!"
3. Change its color to blue
4. Add a click event that shows an alert

```javascript
const msg = document.getElementById("message");
msg.textContent = "Hello!";
msg.style.color = "blue";

msg.addEventListener("click", function() {
    alert("You clicked the message!");
});
```

---

# PART 15 — JS COMMON TRAPS SUMMARY

| Trap | Explanation |
|------|-------------|
| `typeof null === "object"` | Bug in JS, been there forever |
| `"1" + 1 === "11"` | String + Number = String |
| `"1" - 1 === 0` | String - Number = Number |
| `[].sort()` | Sorts as strings, not numbers |
| `var` hoisting | Accessible before declaration (undefined) |
| `let/const` TDZ | ReferenceError if accessed before declaration |
| `== vs ===` | == does type coercion |
| `null == undefined` | True with ==, false with === |
| `[] == false` | True (empty array is falsy when coerced?) |
| `!![]` | True (array is truthy) |
| Objects by reference | `{} == {}` is false |
| Strings immutable | `str[0] = 'X'` does nothing |
| `arr.sort()` | Needs comparator for numbers |
| `const` objects | Properties can be changed |
| `setTimeout` + `var` | Gets final value, not loop value |
