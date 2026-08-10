# 📁 FOLDER 11 — REST API & FETCH 🟡 MEDIUM PRIORITY

---

## ❓ QUESTIONS + SOLUTIONS

---

### Q1. What is an API? REST? RESTful API? ⭐

**API:** Application Programming Interface — a contract for how systems communicate.

**REST:** Representational State Transfer — an **architectural style** for building web services using HTTP.

**RESTful API:** An API that follows REST constraints:
- **Stateless** — each request contains all info needed (no session on server)
- **Client-Server** — separation of concerns
- **Uniform Interface** — consistent endpoints (nouns, not verbs)
- **Resource-based** — everything is a resource (`/users`, `/products`)

---

### Q2. HTTP Methods ⭐ 🔥

| Method | Purpose | Idempotent? | Body? |
|--------|---------|-------------|-------|
| GET | Read/retrieve data | Yes | No |
| POST | Create new resource | No | Yes |
| PUT | Replace entire resource | Yes | Yes |
| PATCH | Update part of resource | Yes | Yes |
| DELETE | Remove resource | Yes | No |

**Idempotent:** Calling multiple times has the same effect as once.

---

### Q3. HTTP Status Codes ⭐ 🔥 MUST KNOW

| Code | Meaning |
|------|---------|
| **200** | OK — success |
| **201** | Created — resource created (POST) |
| **400** | Bad Request — invalid client input |
| **401** | Unauthorized — **not authenticated** (login required) |
| **403** | Forbidden — **authenticated but not permitted** |
| **404** | Not Found — resource doesn't exist |
| **500** | Internal Server Error — server-side bug |

**401 vs 403:**
- 401 = "Who are you?" (not logged in)
- 403 = "I know who you are, but you can't do this" (no permission)

**🧠 Remember:** 2xx = success, 4xx = client error, 5xx = server error

---

### Q4. Fetch API — JavaScript ⭐

```javascript
// Basic fetch
async function getUser(id) {
  try {
    const response = await fetch(`/api/users/${id}`);

    if (!response.ok) {
      throw new Error(`HTTP error: ${response.status}`);
    }

    const data = await response.json();
    return data;
  } catch (error) {
    console.error('Fetch failed:', error);
  }
}

// POST request
async function createUser(userData) {
  const response = await fetch('/api/users', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify(userData)
  });
  return response.json();
}
```

---

### Q5. Synchronous vs Asynchronous API Calls ⭐

| Sync | Async |
|------|-------|
| Blocks until complete | Doesn't block |
| Can't do other work | Other code runs while waiting |
| `fetch` is always async | Use `async/await` or `.then()` |

---

### Q6. What is CORS? Why do CORS errors occur? ⭐

**CORS:** Cross-Origin Resource Sharing — a browser security mechanism that **blocks requests** from one origin to another unless the server explicitly allows it.

**Origin =** protocol + domain + port (e.g., `https://mysite.com:3000`)

**CORS error in browser:**
- `localhost:3000` tries to fetch from `api.external.com`
- Browser blocks it unless API response includes `Access-Control-Allow-Origin: *`

**Fix:** Server must add CORS headers:
```
Access-Control-Allow-Origin: https://mysite.com
```

Note: CORS is a **browser restriction**, not a server restriction. Server-to-server calls are never blocked by CORS.

---

### Q7. Loading/Error/Success States ⭐

```javascript
const [data, setData] = useState(null);
const [loading, setLoading] = useState(false);
const [error, setError] = useState(null);

async function fetchData() {
  setLoading(true);
  setError(null);
  try {
    const res = await fetch('/api/data');
    if (!res.ok) throw new Error(res.status);
    setData(await res.json());
  } catch (err) {
    setError(err.message);
  } finally {
    setLoading(false);
  }
}

// Render:
if (loading) return <Spinner />;
if (error)   return <Error message={error} />;
return <DataView data={data} />;
```

---

### Q8. Prevent Unnecessary API Calls ⭐ (Q605)

1. **Debouncing** — for search inputs (wait until typing stops)
2. **Abort Controller** — cancel in-flight requests
3. **Caching** — store previous results
4. **Dependency arrays in useEffect** — only fetch when relevant data changes

```javascript
// AbortController — cancel stale request
useEffect(() => {
  const controller = new AbortController();
  fetch(url, { signal: controller.signal })
    .then(res => res.json())
    .then(setData);
  return () => controller.abort(); // cleanup on unmount or re-run
}, [url]);
```

---

### Q9. What Happens if API Takes 10 Seconds to Respond?

- Without timeout: request hangs, UI appears frozen/loading
- **Good practice:** Set a timeout, show loading indicator, allow cancellation

```javascript
const controller = new AbortController();
const timeoutId = setTimeout(() => controller.abort(), 5000); // 5s timeout
try {
  const res = await fetch(url, { signal: controller.signal });
} catch (e) {
  if (e.name === 'AbortError') console.log('Request timed out');
} finally {
  clearTimeout(timeoutId);
}
```

---

## 🔑 QUICK MEMORY TRICKS

- **GET=read, POST=create, PUT=replace, PATCH=update, DELETE=remove**
- **401** = not authenticated, **403** = authenticated but forbidden
- **CORS** = browser blocks cross-origin unless server allows
- **fetch()** always async — must `await` or `.then()`
- **Debounce** prevents search from hammering the API on every keystroke

---

## ⚠️ COMMON MISTAKES

1. Not checking `response.ok` before calling `.json()` — `.json()` doesn't throw on 4xx/5xx
2. Confusing 401 and 403
3. Thinking CORS is a server-side issue — it's a browser restriction
4. Not providing cleanup in useEffect for fetch (memory leaks)
