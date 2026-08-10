# 📁 FOLDER 15 — MIXED HARD QUESTIONS (Section 04) ⭐ HIGH PRIORITY

---

> These questions COMBINE multiple topics. They are scenario-based and test real engineering judgment.

---

### Q601. ⭐ 🔥 Missing Number — O(n) time, O(1) space

**Problem:** Array contains 1...n with one missing. Find it without extra space.

**Solution:**
```java
// Approach: Expected sum - Actual sum
int n = arr.length + 1;
int expected = n * (n + 1) / 2;  // sum of 1 to n
int actual = 0;
for (int x : arr) actual += x;
return expected - actual;
// Time: O(n), Space: O(1) ✅
```

**Final Answer:** Use the mathematical formula `n*(n+1)/2`. The difference is the missing number.

---

### Q602. ⭐ Find Duplicates — Three Approaches

**Problem:** Check if array contains duplicates. Give 3 approaches.

| Approach | Time | Space | Method |
|----------|------|-------|--------|
| Brute Force | O(n²) | O(1) | Nested loops — compare each pair |
| HashSet | O(n) | O(n) | Add each element; if already exists → duplicate |
| Sort + check adjacent | O(n log n) | O(1) | Sort; check if `arr[i] == arr[i+1]` |

```java
// HashSet approach (best):
Set<Integer> seen = new HashSet<>();
for (int x : arr) if (!seen.add(x)) return true;
return false;
```

---

### Q603. ⭐ 10,000 Users — Frontend Search Design

**Problem:** API returns 10,000 users. Design name-search in frontend.

**Solution:**

1. **Fetch all once** and store in memory (10,000 users ≈ small enough)
2. **Filter on client-side** using `.filter()` + `toLowerCase()` + `.includes()`
3. **Debounce** the search input (500ms delay)
4. **Virtualize the list** — only render visible rows (react-window)
5. If users grow: move search to server-side with query params (`/api/users?q=name`)

```javascript
// Client-side search
const results = users.filter(u =>
  u.name.toLowerCase().includes(query.toLowerCase())
);
```

---

### Q604. ⭐ React Making Same API Request Multiple Times

**Problem:** React app makes same API request multiple times. What causes this?

**Causes:**
1. `useEffect` missing/wrong dependency array → triggers on every render
2. Component unmounts and remounts (strict mode double-invocation in dev)
3. Parent re-renders → child re-mounts → useEffect re-runs
4. Multiple instances of the same component each making own request
5. State updates inside `useEffect` causing re-render → re-fetch loop

**Fixes:**
- Correct dependency array
- Lift fetch to parent and pass data as props
- Cache result with `useRef` or SWR/React Query

---

### Q605. ⭐ 🔥 Search Box Calling API on Every Keystroke — Optimize

**Problem:** Search box calls API on every key press. How to fix?

**Solution: Debouncing**

```javascript
// React implementation
const [query, setQuery] = useState('');

useEffect(() => {
  const timer = setTimeout(() => {
    if (query) fetchResults(query); // only call after 500ms of no typing
  }, 500);
  return () => clearTimeout(timer); // cancel if user types again
}, [query]);
```

**Also consider:**
- Cancel in-flight requests with `AbortController`
- Minimum query length (don't search for empty or single char)
- Server-side search for large datasets

---

### Q606. ⭐ Java Program Taking O(n²) — How to Improve?

**Problem:** Java program is O(n²) processing an array.

**Investigation steps:**
1. Identify the **nested loops** causing O(n²)
2. Check if the inner loop can be eliminated using:
   - **HashMap** → O(1) lookups instead of O(n) search
   - **Sorting** → enables binary search (O(log n))
   - **Two pointers** → eliminate inner loop
   - **Prefix sums** → precompute to answer range queries in O(1)

```java
// O(n²) — bad
for (int i = 0; i < n; i++)
  for (int j = 0; j < n; j++)
    if (arr[i] + arr[j] == target) ...

// O(n) — good (HashMap)
Map<Integer, Integer> map = new HashMap<>();
for (int i = 0; i < n; i++) {
  if (map.containsKey(target - arr[i])) // O(1) lookup
    return true;
  map.put(arr[i], i);
}
```

---

### Q607. ⭐ 🔥 API Key Accidentally Committed to GitHub

**What to do IMMEDIATELY:**
1. **Revoke the key immediately** from the API provider dashboard (GitHub, AWS, etc.)
2. **Generate a new key**
3. **Remove from code** — store in `.env` file
4. Add `.env` to `.gitignore`
5. **Scrub git history** — use `git filter-branch` or BFG Repo Cleaner
6. **Force push** the cleaned history
7. **Notify team** to pull fresh copy

**Prevention:**
```bash
# .gitignore
.env
secrets.json
config/credentials.yml
```

**🧠 Remember:** Deleting the file and committing does NOT remove it from git history. History must be scrubbed separately.

---

### Q608. API Returns 401 ⭐

**401 Unauthorized** = The request lacks valid **authentication credentials**.

- User is NOT logged in
- Token is expired or invalid
- No `Authorization` header sent

**Response:** Redirect to login page, refresh token, or prompt user to authenticate.

---

### Q609. API Returns 403 ⭐

**403 Forbidden** = User IS authenticated, but does NOT have **permission** for this action.

**Difference from 401:**
| 401 | 403 |
|-----|-----|
| Not logged in | Logged in, but no permission |
| "Who are you?" | "I know who you are, but NO" |
| Fix: authenticate | Fix: check user role/permissions |

---

### Q610. React Component Re-rendering Indefinitely ⭐

**What to inspect:**
1. `useEffect` without proper deps → state update in effect → re-render → effect runs again
2. Object/array created fresh on every render used as dependency (`[] !== []`)
3. Parent re-renders and passes new reference for object/function props

```jsx
// BUG
useEffect(() => {
  setData(fetchData()); // state change triggers re-render → loop!
}, [data]); // data depends on itself

// FIX
useEffect(() => {
  fetchData().then(setData);
}, []); // run once only
```

---

### Q611. 1 Million Records — Fast Lookup by ID ⭐

**Answer: HashMap (or database index)**

| Structure | Lookup | Why |
|-----------|--------|-----|
| Array | O(n) | Must scan all |
| Sorted Array | O(log n) | Binary search |
| HashMap | **O(1) avg** | Hash function → direct bucket |
| Database with index | O(log n) | B-Tree index |

**Best choice:** **HashMap** for in-memory, **Database index on ID column** for persistent data.

---

### Q612. Process Tasks in Exact Order They Arrive ⭐

**Data structure: Queue (FIFO)**

- Tasks arrive → enqueue
- Process → dequeue in same order
- Use `LinkedList` or `ArrayDeque` in Java

---

### Q613. Undo Last Operation Repeatedly ⭐

**Data structure: Stack (LIFO)**

- Every action → push to stack
- Undo → pop from stack
- Examples: Ctrl+Z in editors, browser back button (history stack)

---

### Q614. Shortest Path in Unweighted Graph ⭐

**Algorithm: BFS (Breadth-First Search)**

- BFS explores level by level → the first time it reaches a node = shortest path
- Time: O(V + E)

---

### Q615. Shortest Path with Non-Negative Weighted Edges ⭐

**Algorithm: Dijkstra's Algorithm**

- Greedy — always process the closest unvisited node
- Uses a min-heap (priority queue)
- Time: O((V + E) log V)
- **Cannot handle negative weights** — use Bellman-Ford for that

---

### Q616. Detect Cycle in Dependency Graph ⭐

**Answer: Topological Sort (Kahn's algorithm or DFS)**

- **DFS approach:** Track 3 states: unvisited, in-progress, done. If you visit an in-progress node → cycle.
- **Kahn's algorithm (BFS):** If any node still has in-degree > 0 after processing → cycle exists.

**Why it matters:** Build systems, task schedulers, package managers use this to detect circular dependencies.

---

### Q617. Recursive Algorithm Causes StackOverflowError ⭐

**Causes:**
1. No base case (infinite recursion)
2. Base case never reached
3. Very deep recursion (large n)

**Solutions:**
1. Add/fix the **base case**
2. Convert to **iterative** using an explicit stack
3. Use **tail recursion** (Java doesn't optimize tail calls, but the pattern is cleaner)
4. Use **memoization** to avoid redundant recursive calls (also reduces depth)

---

### Q618. React UI Doesn't Update After API Data Received ⭐

**What to check:**
1. Are you storing data in **state**? (`useState` or `setState`) — DOM doesn't update for regular variables
2. Is the component **re-rendering**? Check that `setData(newData)` is called
3. Are you **mutating state directly**? (`state.items.push(x)` doesn't trigger re-render)
4. Is the data structure correct? (check `console.log` after fetch)
5. Are you using `useEffect` correctly? Is it even running?

```jsx
// Wrong — mutation, no re-render
data.items.push(newItem);

// Correct — new reference triggers re-render
setData({ ...data, items: [...data.items, newItem] });
```

---

### Q619. Java HashMap Suddenly Performs Poorly ⭐

**Investigation:**
1. **Collision rate** — if many keys hash to same bucket → O(n) lookup
2. **Poor hash function** — keys produce same hash code
3. **Load factor exceeded** — too many entries → rehashing may be slow
4. **String interning** — if using custom objects as keys without proper `hashCode()`

**Root concepts:**
- Java HashMap uses **separate chaining** (linked list → balanced tree if > 8 entries per bucket)
- Average O(1), worst case O(n) when all keys collide
- Always override both `hashCode()` AND `equals()` for custom key objects

---

### Q620. AI Agent Calling Tool Indefinitely ⭐

**Safeguards:**
1. **Max iteration limit** — stop after N steps (e.g., 25)
2. **Tool call deduplication** — detect same tool + same args called twice
3. **Timeout** — wall-clock time limit per execution
4. **Explicit stopping condition** — check goal completion after each step
5. **Human-in-the-loop** — require human approval for repeated actions
6. **Exponential backoff** — increase delay between retries

---

## 🔑 QUICK MEMORY TRICKS

- Q601: **missing = expected sum - actual sum**
- Q602: **HashSet = O(n) duplicate detection**
- Q605: **debounce search = wait until typing stops**
- Q607: **API key leak = revoke immediately + scrub history**
- Q611: **1M records fast lookup = HashMap O(1)**
- Q612: **FIFO = Queue**, Q613: **LIFO = Stack**
- Q614: **unweighted shortest path = BFS**
- Q615: **weighted non-negative = Dijkstra**
- Q616: **cycle in graph = topological sort / DFS**

---

## ⚠️ COMMON MISTAKES

1. Thinking git delete removes from history — it doesn't
2. React mutation: `state.arr.push()` — does NOT trigger re-render
3. Using DFS instead of BFS for shortest path in unweighted graph
4. Not implementing both `hashCode()` AND `equals()` for custom HashMap keys
5. AI agent: not setting a max iteration safeguard
