# 📁 FOLDER 03 — JAVASCRIPT CORE ⭐ HIGH PRIORITY

---

## 🧠 CONCEPT OVERVIEW

JavaScript is a **dynamic, interpreted language** that runs in the browser and Node.js. It controls behavior, manipulates the DOM, and handles events.

---

## ❓ QUESTIONS + SOLUTIONS

---

### Q1. Difference between `var`, `let`, and `const` ⭐ 🔥 MUST KNOW

| Feature | `var` | `let` | `const` |
|---------|-------|-------|---------|
| Scope | Function-scoped | Block-scoped | Block-scoped |
| Hoisting | Hoisted (initialized as `undefined`) | Hoisted (NOT initialized — TDZ) | Hoisted (NOT initialized — TDZ) |
| Reassignable | Yes | Yes | No (primitive) |
| Re-declarable | Yes | No | No |
| Global object property | Yes (`window.x`) | No | No |

**Final Answer:**
> Use `const` by default. Use `let` when reassignment is needed. Avoid `var` — it has function scope and confusing hoisting behavior.

**🧠 Remember:** "var is old and weird, let/const are modern and safe"

---

### Q2. What is hoisting? ⭐

**Definition:** JavaScript moves variable and function **declarations** to the top of their scope during compilation (before code runs).

**var hoisting:**
```javascript
console.log(x); // undefined (NOT error — var is hoisted and initialized as undefined)
var x = 5;
```

**let/const hoisting:**
```javascript
console.log(y); // ReferenceError: Cannot access 'y' before initialization
let y = 5;
```

**Function declaration hoisting:**
```javascript
greet(); // Works! "Hello"
function greet() { console.log("Hello"); }
```

**Final Answer:**
> Hoisting moves declarations (not initializations) to the top. `var` is hoisted and initialized as `undefined`. `let`/`const` are hoisted but not initialized (TDZ). Function declarations are fully hoisted.

---

### Q3. What is the Temporal Dead Zone (TDZ)? ⭐

**Definition:** The period between when a `let`/`const` variable is hoisted and when it's initialized. Accessing it in this zone throws a `ReferenceError`.

```javascript
// TDZ starts here for x
console.log(x); // ReferenceError: Cannot access 'x' before initialization
let x = 10; // TDZ ends here
```

**🧠 Remember:** TDZ = "let/const exists but can't be touched yet"

---

### Q4. What are primitive data types in JavaScript? ⭐

**7 Primitives:**

| Type | Example |
|------|---------|
| `string` | `"hello"` |
| `number` | `42`, `3.14` |
| `boolean` | `true`, `false` |
| `null` | `null` |
| `undefined` | `let x;` → x is `undefined` |
| `symbol` | `Symbol('id')` |
| `bigint` | `9007199254740991n` |

**Reference types:** Objects, Arrays, Functions (stored by reference, not by value)

---

### Q5. Difference between `null` and `undefined`? ⭐

| Feature | `null` | `undefined` |
|---------|--------|-------------|
| Meaning | Intentionally empty/no value | Variable declared but not assigned |
| Type | `typeof null === "object"` (historical bug!) | `typeof undefined === "undefined"` |
| Who sets it? | Developer | JavaScript engine |

```javascript
let a;         // undefined (JS default)
let b = null;  // null (developer set intentionally)
```

**🧠 Remember:** null = "I deliberately set this to nothing" | undefined = "JS doesn't know what this is yet"

---

### Q6. Difference between `==` and `===`? ⭐

| Operator | Type coercion | Use |
|----------|--------------|-----|
| `==` | YES — converts types | Avoid |
| `===` | NO — strict equality | Always use |

```javascript
0 == "0"   // true  (coercion happens)
0 === "0"  // false (different types)
null == undefined  // true
null === undefined // false
```

**Final Answer:**
> Always use `===`. It checks both value AND type without coercion.

---

### Q7. What is type coercion?

- JavaScript automatically converts one type to another when using `==` or arithmetic with mixed types
```javascript
"5" + 3      // "53"  (number becomes string — concatenation)
"5" - 3      // 2     (string becomes number — subtraction)
true + 1     // 2     (true = 1)
false + 1    // 1     (false = 0)
```

---

### Q8. What is NaN? How do you check for it?

- `NaN` = Not a Number — result of invalid math operations
```javascript
"abc" * 2    // NaN
0 / 0        // NaN
```

- **Checking NaN:**
```javascript
isNaN("abc")       // true (converts to number first — unreliable)
Number.isNaN("abc") // false (strict — only true if value IS NaN)
Number.isNaN(NaN)   // true ✅
```

**🧠 Remember:** Use `Number.isNaN()` not `isNaN()` for reliable checking.

---

### Q9. What is truthy/falsy? ⭐

**Falsy values (exactly 7):**
```javascript
false, 0, -0, 0n, "", null, undefined, NaN
```

**Everything else is truthy** (including `"0"`, `[]`, `{}`, `" "`)

```javascript
if ([])  { /* runs — empty array is TRUTHY! */ }
if ("")  { /* skipped — empty string is FALSY */ }
if ("0") { /* runs — non-empty string is TRUTHY */ }
```

**🧠 Remember:** "0, empty, nothing, NaN" = falsy. Everything else = truthy.

**⚠️ Common mistake:** Thinking `[]` or `{}` are falsy — they are TRUTHY!

---

### Q10. Function Declaration vs Function Expression ⭐

```javascript
// Declaration — HOISTED (can call before definition)
function greet() { return "Hello"; }
greet(); // ✅ Works before definition too

// Expression — NOT hoisted
const greet = function() { return "Hello"; };
// greet before this line → ReferenceError (TDZ for const)
```

**Arrow Function:**
```javascript
const greet = () => "Hello";
const add = (a, b) => a + b;
const double = x => x * 2; // no parens needed for single param
```

---

### Q11. Differences: Arrow Function vs Regular Function ⭐

| Feature | Regular Function | Arrow Function |
|---------|-----------------|----------------|
| `this` binding | Dynamic (depends on caller) | Lexical (inherits from surrounding scope) |
| `arguments` object | Has it | Does NOT |
| Can be constructor | Yes (`new Func()`) | No |
| Hoisting | Yes (declaration) | No |
| Syntax | Verbose | Concise |

**🧠 Remember:** Arrow functions = "no own `this`, no own `arguments`"

---

### Q12. Array Methods ⭐ 🔥

| Method | Returns | Mutates? | Use case |
|--------|---------|---------|---------|
| `push()` | new length | ✅ | Add to end |
| `pop()` | removed element | ✅ | Remove from end |
| `shift()` | removed element | ✅ | Remove from start |
| `unshift()` | new length | ✅ | Add to start |
| `slice(start, end)` | new array | ❌ | Extract portion |
| `splice(start, count)` | removed items | ✅ | Remove/insert at position |
| `map(fn)` | **new array** (same length) | ❌ | Transform each element |
| `filter(fn)` | **new array** (shorter) | ❌ | Select matching elements |
| `reduce(fn, init)` | **single value** | ❌ | Aggregate |
| `find(fn)` | **first match** (or undefined) | ❌ | Find one item |
| `includes(val)` | **boolean** | ❌ | Check existence |
| `forEach(fn)` | **undefined** | ❌ | Iterate (no return) |

```javascript
const nums = [1, 2, 3, 4, 5];

// map — transform
nums.map(x => x * 2);       // [2, 4, 6, 8, 10]

// filter — select
nums.filter(x => x > 2);   // [3, 4, 5]

// reduce — accumulate
nums.reduce((acc, x) => acc + x, 0); // 15

// find — first match
nums.find(x => x > 3);     // 4
```

**🧠 Remember:**
- map → same length, transformed
- filter → shorter, filtered
- reduce → one value

**⚠️ Common mistake:** `map()` vs `forEach()` — map RETURNS a new array, forEach RETURNS undefined.

---

### Q13. Object Properties — Dot vs Bracket Notation

```javascript
const obj = { name: "Alice", "first-name": "Alice" };

// Dot notation — cleaner, but key must be valid identifier
obj.name;          // "Alice" ✅

// Bracket notation — needed for dynamic keys or special chars
obj["first-name"]; // "Alice" ✅
const key = "name";
obj[key];          // "Alice" ✅ (dynamic key)
```

**Iterating over objects:**
```javascript
for (const key in obj) { console.log(key, obj[key]); }
Object.keys(obj);    // array of keys
Object.values(obj);  // array of values
Object.entries(obj); // array of [key, value] pairs
```

---

### Q14. Shallow Copy vs Deep Copy

| Type | Shares nested references? | Methods |
|------|--------------------------|---------|
| Shallow | YES — nested objects are shared | `Object.assign()`, spread `{...obj}` |
| Deep | NO — fully independent copy | `JSON.parse(JSON.stringify(obj))`, `structuredClone()` |

```javascript
const orig = { a: 1, b: { c: 2 } };
const shallow = { ...orig };
shallow.b.c = 99;      // ALSO changes orig.b.c! (shared reference)

const deep = structuredClone(orig);
deep.b.c = 99;         // orig.b.c still 2 ✅
```

---

### Q15. DOM Manipulation ⭐

```javascript
// Select elements
document.getElementById("myId");
document.querySelector(".myClass");       // first match
document.querySelectorAll(".myClass");    // NodeList of all

// Change text
element.innerText = "New text";           // visible text only
element.textContent = "New text";         // all text including hidden
element.innerHTML = "<b>Bold</b>";        // parses HTML (⚠️ XSS risk)

// Change CSS
element.style.color = "red";
element.classList.add("active");
element.classList.remove("active");
element.classList.toggle("active");

// Create element
const div = document.createElement("div");
div.textContent = "Hello";
document.body.appendChild(div);

// Events
element.addEventListener("click", function(event) {
  console.log("Clicked!", event.target);
});
```

**innerText vs textContent vs innerHTML:**
| Property | What it returns |
|----------|----------------|
| `innerText` | Visible text only (respects CSS) |
| `textContent` | All text including hidden (faster) |
| `innerHTML` | HTML as string (can inject HTML — XSS risk) |

---

### Q16. Event Bubbling & Event Delegation ⭐

**Event Bubbling:** When an event fires on an element, it **bubbles up** through its ancestors.
```
Click on <button> → triggers button, then div, then body, then html
```

**Event Delegation:** Instead of attaching listeners to each child, attach ONE listener to the parent. Uses bubbling.
```javascript
document.getElementById("list").addEventListener("click", function(e) {
  if (e.target.tagName === "LI") {
    console.log("Clicked:", e.target.textContent);
  }
});
```

**Benefits of delegation:** Better performance, works for dynamically added elements.

---

## 🔑 QUICK MEMORY TRICKS

- **var/let/const:** var=function scope+hoisted, let=block+TDZ, const=block+no reassign
- **Falsy 7:** `false, 0, -0, 0n, "", null, undefined, NaN`
- **map/filter/reduce:** transform / select / accumulate
- **== vs ===:** avoid == (coercion), use === (strict)
- **Event delegation:** "one listener for many children using bubbling"

---

## ⚠️ COMMON MISTAKES

1. Saying `typeof null === "null"` — it's `"object"` (historical bug)
2. Using `==` instead of `===`
3. Confusing `map()` (returns array) with `forEach()` (returns undefined)
4. Thinking `[]` and `{}` are falsy — they are TRUTHY
5. Using `isNaN()` instead of `Number.isNaN()` for strict check
