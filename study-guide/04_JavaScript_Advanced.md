# 📁 FOLDER 04 — JAVASCRIPT ADVANCED ⭐ HIGH PRIORITY 🔥

---

## 🧠 CONCEPT OVERVIEW

This folder covers the hardest and most commonly tested JavaScript concepts:
- **Scope & Closures** — lexical scoping, how functions remember variables
- **Execution Context & Call Stack** — how JS runs code
- **Event Loop** — how async works
- **Promises & async/await** — handling async operations
- **ES6+ Features** — destructuring, spread, optional chaining

---

## ❓ QUESTIONS + SOLUTIONS

---

### Q1. What is Lexical Scope?

**Definition:** A function's scope is determined by **where it is written in the code**, not where it is called.

```javascript
function outer() {
  const x = 10;
  function inner() {
    console.log(x); // Can access x — lexical scope!
  }
  inner(); // 10
}
```

**🧠 Remember:** Lexical = "where you were born" determines what you can access.

---

### Q2. What is a Closure? ⭐ 🔥 MUST KNOW

**Definition:** A closure is when an **inner function remembers the variables of its outer function** even after the outer function has returned.

```javascript
function counter() {
  let count = 0;
  return function() {
    count++;
    return count;
  };
}

const increment = counter();
increment(); // 1
increment(); // 2
increment(); // 3 — count is "remembered"!
```

**Practical use case:**
- Private variables (encapsulation in JS)
- Factory functions
- Memoization

**Final Answer:**
> A closure is a function that retains access to its lexical scope (the variables of its enclosing function) even after that enclosing function has finished executing.

**🧠 Remember:** Closure = function + "backpack" of variables from its birthplace

**⚠️ Common mistake:** Thinking the outer variable is copied — it's the actual reference that's kept alive.

---

### Q3. What is the Execution Context? Call Stack?

**Execution Context:** The environment in which JS code runs. Contains:
- `this` value
- Variable environment
- Outer environment reference

**Types:**
- Global Execution Context (one per program)
- Function Execution Context (created for each function call)

**Call Stack:** A stack data structure that tracks which function is currently executing.

```
[main()] → calls greet() → [greet()] → returns → [main()] continues
```

---

### Q4. What is the Event Loop? ⭐ 🔥 MUST KNOW

**Key components:**
1. **Call Stack** — where code executes (synchronous)
2. **Web APIs** — handles async (setTimeout, fetch, DOM events)
3. **Callback Queue (Macrotask Queue)** — where setTimeout callbacks wait
4. **Microtask Queue** — where Promise callbacks wait (higher priority!)
5. **Event Loop** — moves tasks from queues to call stack when it's empty

**Order of execution:**
1. Synchronous code (call stack)
2. **Microtasks** (Promises, `queueMicrotask`) — ALL of them
3. **Macrotasks** (setTimeout, setInterval) — one at a time

---

### Q5. Predict the output — CLASSIC QUESTION ⭐ 🔥

```javascript
console.log("A");

setTimeout(() => {
  console.log("B");
}, 0);

Promise.resolve().then(() => {
  console.log("C");
});

console.log("D");
```

**Answer: A, D, C, B**

**Explanation:**
1. `console.log("A")` → Sync → **A** printed
2. `setTimeout` → Web API → callback goes to **Macrotask queue**
3. `Promise.resolve().then()` → Microtask → goes to **Microtask queue**
4. `console.log("D")` → Sync → **D** printed
5. Call stack empty → process **all microtasks** → **C** printed
6. Microtask queue empty → process **one macrotask** → **B** printed

**Final Answer: A → D → C → B**

**🧠 Remember:** Sync → Microtasks → Macrotasks | Promise > setTimeout

---

### Q6. What is a Promise? ⭐ 🔥 MUST KNOW

**Definition:** An object representing the eventual completion (or failure) of an asynchronous operation.

**Three states:**
| State | Meaning |
|-------|---------|
| `pending` | Still running |
| `fulfilled` | Completed successfully |
| `rejected` | Failed |

```javascript
const promise = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Done!"), 1000);
});

promise
  .then(result => console.log(result))  // "Done!"
  .catch(error => console.log(error));
```

**Promise vs async/await:**
```javascript
// Promise chain
fetch(url)
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(err => console.log(err));

// async/await — cleaner, same behavior
async function getData() {
  try {
    const res = await fetch(url);
    const data = await res.json();
    console.log(data);
  } catch (err) {
    console.log(err);
  }
}
```

**What does `await` actually do?**
- Pauses execution of the async function until the Promise resolves
- Does NOT block the main thread (other code can run)
- Returns the resolved value

**What happens when an async function returns a value?**
- It automatically wraps the value in a Promise

---

### Q7. What is callback hell? How to avoid?

**Callback hell:** Deeply nested callbacks that are hard to read/maintain
```javascript
getData(function(a) {
  processA(a, function(b) {
    processB(b, function(c) {
      processC(c, function(d) {
        // pyramid of doom
      });
    });
  });
});
```

**Solutions:**
1. Named functions (flatten the pyramid)
2. **Promises** (`.then()` chains)
3. **async/await** (cleanest)

---

### Q8. What is debouncing? What is throttling? ⭐

**Debouncing:**
- Delays function execution until after the user **stops triggering it**
- Only fires ONCE after the delay

```javascript
function debounce(fn, delay) {
  let timer;
  return function(...args) {
    clearTimeout(timer);
    timer = setTimeout(() => fn(...args), delay);
  };
}
// Use case: Search box — wait until user stops typing
```

**Throttling:**
- Limits function execution to once per time interval
- Fires **at most once** per interval regardless of how many calls

```javascript
// Use case: Scroll events — fire at most once every 200ms
```

| Feature | Debounce | Throttle |
|---------|---------|---------|
| When it fires | After activity stops | At fixed intervals |
| Use case | Search input, resize | Scroll events, button spam |

**🧠 Remember:**
- Debounce = "wait until calm" (search box)
- Throttle = "rate limiter" (scroll, resize)

---

### Q9. ES6 Features ⭐

**Destructuring:**
```javascript
// Array destructuring
const [a, b, c] = [1, 2, 3];

// Object destructuring
const { name, age } = { name: "Alice", age: 25 };
const { name: firstName } = { name: "Alice" }; // rename
```

**Spread operator (`...`):**
```javascript
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5]; // [1, 2, 3, 4, 5]

const obj1 = { a: 1 };
const obj2 = { ...obj1, b: 2 }; // { a: 1, b: 2 }
```

**Rest operator (`...`):**
```javascript
function sum(...nums) { // rest — collects remaining args
  return nums.reduce((a, b) => a + b, 0);
}
sum(1, 2, 3); // 6
```

**Optional chaining (`?.`):**
```javascript
const user = { profile: { name: "Alice" } };
user?.profile?.name;    // "Alice"
user?.address?.city;   // undefined (no error!)
```

**Nullish coalescing (`??`):**
```javascript
const val = null ?? "default";   // "default"
const val2 = 0 ?? "default";    // 0 (0 is not null/undefined!)
const val3 = 0 || "default";    // "default" (|| uses falsy check)
```

**🧠 Remember:** `??` = only null/undefined triggers fallback, `||` = any falsy triggers fallback

---

## 🔑 QUICK MEMORY TRICKS

- **Closure** = function + "backpack" of outer variables
- **Event loop order:** Sync → Microtasks (Promises) → Macrotasks (setTimeout)
- **Output order classic:** A, D, C, B — always!
- **Debounce** = wait for calm (search), **Throttle** = rate limit (scroll)
- **??** = null/undefined only, **||** = any falsy value

---

## ⚠️ COMMON MISTAKES

1. Thinking `setTimeout(fn, 0)` runs before Promises — it does NOT (microtasks first)
2. Using `||` instead of `??` when 0 or empty string are valid values
3. Not handling Promise rejection (no `.catch()` or `try/catch`)
4. Confusing spread and rest (same syntax, different contexts)
5. Thinking `await` blocks the main thread — it only pauses the async function
