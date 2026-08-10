# 📁 FOLDER 09 — REACT ⭐ HIGH PRIORITY 🔥

---

## 🧠 CONCEPT OVERVIEW

React is a **JavaScript library** for building UI using **components**. It uses a **Virtual DOM** to efficiently update the real DOM.

---

## 📋 KEY RULES TO REMEMBER

| Concept | Key Fact |
|---------|----------|
| Component | A reusable piece of UI (function returning JSX) |
| Props | Data passed from parent to child (read-only) |
| State | Internal component data that causes re-render when changed |
| Virtual DOM | React's in-memory copy of the real DOM — diffs to find minimal changes |
| JSX | JavaScript + XML syntax — compiled to `React.createElement()` |
| Re-render triggers | State change, props change, parent re-render |

---

## ❓ QUESTIONS + SOLUTIONS

---

### Q1. What is React? Why use it? ⭐

**Final Answer:**
> React is a JavaScript library for building component-based UIs. It uses a Virtual DOM for efficient updates — instead of re-rendering the whole page, React only updates the changed parts.

**Advantages over manual DOM manipulation:**
- Declarative (describe what UI should look like, not how to update it)
- Reusable components
- Efficient updates via Virtual DOM + diffing algorithm
- Large ecosystem

---

### Q2. What is JSX? ⭐

```jsx
// JSX
const element = <h1 className="title">Hello, {name}!</h1>;

// What JSX compiles to (under the hood):
const element = React.createElement('h1', { className: 'title' }, `Hello, ${name}!`);
```

**Why can't browsers understand JSX directly?**
- Browsers only understand standard JS. JSX must be **transpiled** by **Babel** before it can run.

---

### Q3. What is the Virtual DOM? How does React update the UI? ⭐ 🔥

**Process:**
1. State/props change → React creates a **new Virtual DOM tree**
2. React **diffs** (reconciles) new vDOM vs old vDOM
3. Only the **minimal set of changes** is applied to the real DOM

**Final Answer:**
> The Virtual DOM is React's in-memory JavaScript representation of the real DOM. When state changes, React diffs the old and new virtual DOMs and applies only the necessary updates to the real DOM, making it efficient.

---

### Q4. Props vs State ⭐ 🔥

| Feature | Props | State |
|---------|-------|-------|
| Ownership | Passed from **parent** | Managed inside the **component** |
| Mutability | **Read-only** (immutable by child) | **Mutable** (via setter) |
| Re-renders | Yes, when parent re-renders | Yes, when setState called |
| Use for | Configuration/data from parent | Component's own changing data |

```jsx
// Props
function Greeting({ name }) {
  return <h1>Hello, {name}!</h1>;  // name is a prop — read-only
}

// State
function Counter() {
  const [count, setCount] = useState(0);  // state — can change
  return <button onClick={() => setCount(count + 1)}>{count}</button>;
}
```

---

### Q5. useState() ⭐ 🔥

```jsx
const [value, setValue] = useState(initialValue);

// Rules:
// 1. Only call at top level of component (not inside loops/conditions)
// 2. Setting state triggers re-render
// 3. State updates are ASYNCHRONOUS (batched)

function Counter() {
  const [count, setCount] = useState(0);
  return (
    <div>
      <p>{count}</p>
      <button onClick={() => setCount(count + 1)}>+</button>
      <button onClick={() => setCount(prev => prev - 1)}>-</button>
      {/* Use functional update when new state depends on old state */}
    </div>
  );
}
```

**⚠️ Common mistake:** Using `count + 1` instead of `prev => prev + 1` when calling setState multiple times in the same render.

---

### Q6. useEffect() ⭐ 🔥 MUST KNOW

```jsx
useEffect(() => {
  // Side effect code here
  return () => { /* cleanup */ }; // optional cleanup
}, [dependencies]); // dependency array
```

**Dependency array behavior:**

| Dependency Array | When useEffect runs |
|-----------------|---------------------|
| `[]` (empty) | **Once** after first render (like componentDidMount) |
| `[a, b]` | After first render + whenever a or b changes |
| Omitted | After **every** render |

```jsx
// Run once on mount — fetch data
useEffect(() => {
  fetch('/api/data')
    .then(res => res.json())
    .then(data => setData(data));
}, []); // [] = only on mount

// Run when userId changes
useEffect(() => {
  fetchUser(userId);
}, [userId]);

// What happens with []?
useEffect(() => {
  console.log("Hello"); // logs ONCE after first render
}, []);
```

**What if dependency array is omitted?**
```jsx
useEffect(() => {
  console.log("runs after EVERY render"); // infinite re-renders if state is set here!
});
```

---

### Q7. useRef() ⭐

**Two use cases:**
1. Access a DOM element directly
2. Store a mutable value that does NOT cause re-render

```jsx
// Access DOM element
const inputRef = useRef(null);
<input ref={inputRef} />
inputRef.current.focus(); // works!

// Store value without re-render (e.g., timer ID)
const timerRef = useRef(null);
timerRef.current = setTimeout(() => {}, 1000);
```

**useRef vs useState:**
| Feature | useRef | useState |
|---------|--------|---------|
| Causes re-render | ❌ No | ✅ Yes |
| Persists across renders | ✅ Yes | ✅ Yes |
| Access | `.current` property | Direct value |
| Use for | DOM access, timer IDs | UI data |

---

### Q8. What causes a React component to re-render? ⭐

1. **State** changes (`setState` called)
2. **Props** change (parent passes different values)
3. **Parent** re-renders (even if props are the same)
4. **Context** changes

---

### Q9. Prop Drilling & Context API ⭐

**Prop drilling:** Passing props through many nested components just to reach a deeply nested child.

```
App → Header → Nav → UserIcon → Avatar (needs user data)
     ↑  passes user  ↑  passes user  ↑  passes user
```

**How to avoid:** Context API or state management library.

**Context API:**
```jsx
// 1. Create context
const ThemeContext = createContext('light');

// 2. Provide it
<ThemeContext.Provider value="dark">
  <App />
</ThemeContext.Provider>

// 3. Consume it anywhere
const theme = useContext(ThemeContext);
```

**Context API vs Redux:**
| Feature | Context API | Redux |
|---------|------------|-------|
| Complexity | Simple | Complex |
| Performance | Re-renders all consumers | Optimized |
| Best for | Theme, auth, locale | Large complex state |

---

### Q10. Keys in Lists ⭐ 🔥

```jsx
// Wrong — using index as key
{items.map((item, index) => <li key={index}>{item.name}</li>)}

// Correct — use unique stable ID
{items.map(item => <li key={item.id}>{item.name}</li>)}
```

**Why are keys required?**
React uses keys to identify which items changed, added, or removed during reconciliation.

**What happens with array index as key?**
If items are reordered or deleted, React may incorrectly reuse DOM elements, causing UI bugs.

---

### Q11. Controlled vs Uncontrolled Components ⭐

| Feature | Controlled | Uncontrolled |
|---------|-----------|--------------|
| Input value managed by | React state | DOM (ref) |
| How to read value | state variable | `ref.current.value` |
| Best practice | ✅ Preferred | For simple cases |

```jsx
// Controlled
const [value, setValue] = useState('');
<input value={value} onChange={e => setValue(e.target.value)} />

// Uncontrolled
const ref = useRef();
<input ref={ref} />
// ref.current.value to read
```

---

### Q12. Lifting State Up ⭐

**Problem:** Two sibling components need to share the same state.

**Solution:** Move the state to their **common parent** and pass it down via props.

```jsx
function Parent() {
  const [count, setCount] = useState(0);
  return (
    <>
      <Display count={count} />
      <Controls onIncrement={() => setCount(count + 1)} />
    </>
  );
}
```

---

### Q13. React Practical Problems ⭐ 🔥

**Counter (useState):**
```jsx
function Counter() {
  const [count, setCount] = useState(0);
  return (
    <div>
      <h2>{count}</h2>
      <button onClick={() => setCount(c => c + 1)}>+</button>
      <button onClick={() => setCount(c => c - 1)}>-</button>
      <button onClick={() => setCount(0)}>Reset</button>
    </div>
  );
}
```

**Fetch data + loading/error states:**
```jsx
function UserCard({ username }) {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    setLoading(true);
    fetch(`https://api.github.com/users/${username}`)
      .then(res => {
        if (!res.ok) throw new Error('Not found');
        return res.json();
      })
      .then(data => { setUser(data); setLoading(false); })
      .catch(err => { setError(err.message); setLoading(false); });
  }, [username]);

  if (loading) return <p>Loading...</p>;
  if (error) return <p>Error: {error}</p>;
  return <div><h1>{user.name}</h1></div>;
}
```

**Debounced search:**
```jsx
const [query, setQuery] = useState('');
const [debouncedQuery, setDebouncedQuery] = useState('');

useEffect(() => {
  const timer = setTimeout(() => setDebouncedQuery(query), 500);
  return () => clearTimeout(timer); // cleanup!
}, [query]);

useEffect(() => {
  if (debouncedQuery) fetchResults(debouncedQuery);
}, [debouncedQuery]);
```

---

### Q14. Why Component Keeps Re-rendering Indefinitely? ⭐ (Q610)

**Causes:**
1. Setting state inside `useEffect` without proper dependencies
2. Updating state with a new object/array reference every render (`[] !== []`)
3. `useEffect` dependency includes a function/object recreated every render

```jsx
// BUG: infinite loop
useEffect(() => {
  setData([]); // state change → re-render → useEffect runs again → loop!
}, [data]);   // data depends on itself

// FIX: correct dependency
useEffect(() => {
  setData([]);
}, []); // only run once
```

---

### Q15. How to Optimize React for Unnecessary Re-renders?

- `React.memo` — memoize component, skip re-render if props unchanged
- `useMemo` — memoize expensive computed value
- `useCallback` — memoize callback function
- Move state closer to where it's used (avoid lifting too high)
- Use stable keys in lists

---

## 🔑 QUICK MEMORY TRICKS

- **Props = parent data** (read-only), **State = own data** (mutable)
- **useEffect `[]`** = runs once on mount
- **useEffect omitted deps** = runs every render (dangerous!)
- **Virtual DOM** = diff → apply minimal real DOM changes
- **Key = stable unique ID**, never use array index for mutable lists
- **Closure stale state bug** = use `prev => prev + 1` pattern

---

## ⚠️ COMMON MISTAKES

1. Setting state inside `useEffect` without empty deps → infinite loop
2. Using array index as key for dynamic lists
3. Not cleaning up timers/subscriptions in useEffect return
4. Calling hooks inside conditions or loops (breaks Rules of Hooks)
5. Mutating state directly (`state.count++`) instead of calling setter
