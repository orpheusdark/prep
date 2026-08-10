# 📁 FOLDER 16 — PROJECT QUESTIONS ⭐ HIGH PRIORITY

---

> These are extremely important — the syllabus requires hosted projects and interviewers WILL ask about them.

---

## SECTION A: Vanilla JavaScript API Project

---

### Q1. Explain your project architecture ⭐

**Template answer:**
> My project follows a simple MVC-like structure for a Vanilla JS app. The `index.html` provides the structure, `style.css` handles presentation, and `app.js` contains the logic — API calls, DOM manipulation, and event handling.

**Key points to mention:**
- Separation of concerns (HTML / CSS / JS)
- Event-driven architecture (addEventListener)
- Async data fetching with `async/await` and Fetch API
- Error and loading state handling

---

### Q2. Why Vanilla JavaScript instead of React? ⭐

**Template answer:**
> This project's UI requirements were straightforward enough that a framework wasn't necessary. Vanilla JS avoids build toolchain complexity and is faster to deploy as a static site. It demonstrates that I understand the fundamentals without relying on abstractions.

---

### Q3. How does your application call the API? ⭐

```javascript
async function fetchData(query) {
  const response = await fetch(`https://api.example.com/data?q=${query}`);
  if (!response.ok) throw new Error(`Error ${response.status}`);
  return await response.json();
}
```

---

### Q4. How do you handle API errors? ⭐

```javascript
try {
  const data = await fetchData(query);
  displayResults(data);
} catch (error) {
  showError(error.message); // display error in UI
} finally {
  hideLoader();
}
```

**Also mention:** Checking `response.ok`, displaying user-friendly messages, not just `console.error`.

---

### Q5. How do you handle loading states? ⭐

```javascript
function showLoader() { document.getElementById('loader').style.display = 'block'; }
function hideLoader() { document.getElementById('loader').style.display = 'none'; }

async function search() {
  showLoader();
  try {
    const data = await fetchData(query);
    renderResults(data);
  } catch (e) {
    renderError(e.message);
  } finally {
    hideLoader(); // always hide
  }
}
```

---

### Q6. What happens when the API is unavailable? ⭐

**Template answer:**
> The `catch` block handles network failures. I display a user-friendly error message like "Unable to connect. Please try again." instead of showing a blank page. I also reset the loading state in `finally`.

---

### Q7. How do you validate user input? ⭐

```javascript
function validateInput(query) {
  if (!query || query.trim().length === 0) {
    showError("Please enter a search term.");
    return false;
  }
  if (query.length < 2) {
    showError("Please enter at least 2 characters.");
    return false;
  }
  return true;
}
```

---

### Q8. How do you prevent unnecessary API requests? ⭐

1. **Debouncing** — delay API call until user stops typing
2. **Minimum length check** — don't search for 1 character
3. **Cache previous results** — if same query searched again, use cache

```javascript
let debounceTimer;
searchInput.addEventListener('input', (e) => {
  clearTimeout(debounceTimer);
  debounceTimer = setTimeout(() => {
    if (validateInput(e.target.value)) fetchData(e.target.value);
  }, 500);
});
```

---

### Q9. What was the hardest bug you encountered? ⭐

**Template framework for answering:**
> The hardest bug was [describe specific situation]. I identified it by [describe debugging steps — console.log, Network tab, etc.]. The root cause was [technical reason]. I fixed it by [solution].

**Common real bugs:**
- Race condition in async requests (old request resolving after new one)
- CORS error when calling API directly (needed proxy or server-side)
- `innerHTML` XSS vulnerability from unescaped user input

---

### Q10. What would you improve with more time? ⭐

**Good answers:**
- Add pagination for large results
- Implement caching layer
- Add keyboard navigation
- Improve error messages with specific guidance
- Add unit tests

---

### Q11. How would you make it production-ready? ⭐

- Add error monitoring (Sentry)
- Add loading skeletons instead of spinners
- Implement rate limiting
- Move API key to backend proxy (hide from frontend)
- Add HTTPS
- Optimize assets (minify CSS/JS)
- Test across browsers

---

## SECTION B: React Project

---

### Q12. Why did you choose React? ⭐

> React's component model makes the UI modular and reusable. For an app with multiple interactive parts and complex state (e.g., search, filters, user data), React's declarative approach and hooks make state management cleaner than Vanilla JS.

---

### Q13. Explain your component hierarchy ⭐

**Template answer:**
```
App
├── Header (NavBar, search input)
├── Main
│   ├── SearchResults
│   │   └── ResultCard (×many)
│   └── ErrorMessage / LoadingSpinner
└── Footer
```

Key things to mention:
- Which components are **stateful** vs **presentational**
- Where state lives and why

---

### Q14. Where is state stored and why? ⭐

> State is stored at the **lowest common ancestor** of components that need it. For example, search query state lives in `App` because both `SearchBar` and `ResultsList` depend on it. Lifting state too high causes unnecessary re-renders; too low means you can't share it.

---

### Q15. How do components communicate? ⭐

1. **Parent → Child:** Props (data + callback functions)
2. **Child → Parent:** Callbacks passed as props, child calls them
3. **Siblings:** Lift state to common parent
4. **Deeply nested:** Context API or state management library

---

### Q16. Did you use Context API? Why/why not? ⭐

**If yes:** Context was used for [theme/auth/language] because it needed to be accessible globally without prop drilling.

**If no:** The component tree wasn't deep enough to warrant Context. Props were sufficient and kept the data flow explicit and traceable.

---

### Q17. Where do API calls happen? ⭐

> API calls happen in `useEffect` hooks within the component that owns the data. I avoid putting fetch logic in render — it only runs when relevant dependencies change.

```jsx
useEffect(() => {
  if (query) fetchResults(query);
}, [query]); // only when query changes
```

---

### Q18. How do you prevent unnecessary re-renders? ⭐

1. `React.memo` — wrap component to skip re-render if props unchanged
2. `useCallback` — memoize event handlers passed as props
3. `useMemo` — memoize expensive computations
4. Correct dependency arrays in `useEffect`
5. Move state closer to where it's needed

---

### Q19. How would you scale this to 100,000 users? ⭐

**What would break first:**
- Client-side filtering of 100K records → too slow
- Single API endpoint with no pagination → timeout/bandwidth

**Architectural changes:**
- Server-side search with indexed database queries
- Pagination / infinite scroll
- CDN for static assets
- Caching layer (Redis) for common queries
- Load balancer + multiple server instances
- Database replication for reads

---

## SECTION C: GitHub / Repository

---

### Q20. What should never be committed? ⭐

> Secrets: API keys, passwords, tokens, private credentials. Also: `.env` files, `node_modules/`, build artifacts, OS-specific files (`.DS_Store`).

---

### Q21. How do you review someone's code? ⭐

1. **Understand the purpose** — read the PR description
2. **Check logic correctness** — does it do what it says?
3. **Check edge cases** — null inputs, empty arrays, errors
4. **Check performance** — any obvious O(n²) where O(n) is possible?
5. **Check readability** — meaningful variable names, clear structure
6. **Check security** — no exposed secrets, input sanitization

---

## 🔑 QUICK ANSWERS TABLE

| Question | Exam-ready one-liner |
|---------|---------------------|
| Why Vanilla JS? | Simpler requirements, no build toolchain, demonstrates fundamentals |
| How handle loading? | Show loader on start, hide in `finally` block |
| How handle errors? | `try/catch`, user-friendly message, always hide loader |
| Prevent extra requests? | Debounce input, validate minimum length, cache results |
| Scale to 100K users? | Server-side search, pagination, indexing, caching, CDN |
| What not to commit? | API keys, .env, node_modules, build artifacts |

---

## ⚠️ COMMON MISTAKES IN PROJECT Q&A

1. Saying "I used `console.log` for error handling" — say you display user-friendly messages in the UI
2. Not having a specific bug story ready — prepare one before the interview
3. Saying the hardest part was "CSS" — point to something technical
4. Not knowing why you made architectural choices — be prepared to defend every decision
5. Saying "I'd add tests" without knowing what kind (unit, integration, e2e)
