# 📁 FOLDER 06 — DSA BASICS ⭐ HIGH PRIORITY

---

## 🧠 CONCEPT OVERVIEW

Data Structures and Algorithms are the backbone of coding interviews. This folder covers foundational concepts and the most commonly tested problems.

---

## 📋 BIG-O CHEAT SHEET

| Complexity | Name | Example |
|------------|------|---------|
| O(1) | Constant | Array access, HashMap lookup |
| O(log n) | Logarithmic | Binary search |
| O(n) | Linear | Linear search, single loop |
| O(n log n) | Linearithmic | Merge sort, Quick sort (avg) |
| O(n²) | Quadratic | Bubble sort, nested loops |

**Rule of thumb:**
- O(1) < O(log n) < O(n) < O(n log n) < O(n²) < O(2ⁿ) < O(n!)

---

## ❓ QUESTIONS + SOLUTIONS

---

### Q1. What is an Array? ⭐

**Definition:** A fixed-size, ordered collection of elements of the **same type** stored in **contiguous memory**.

**Advantages:** O(1) random access by index.
**Limitations:** Fixed size, expensive insertion/deletion in middle (O(n) shift).

**Difference: Array vs ArrayList (Java):**
| Feature | Array | ArrayList |
|---------|-------|-----------|
| Size | Fixed | Dynamic |
| Type | Primitives/objects | Objects only |
| Methods | None | `.add()`, `.remove()`, `.size()` |
| Syntax | `int[] arr = new int[5]` | `ArrayList<Integer> list = new ArrayList<>()` |

---

### Q2. Linear Search vs Binary Search ⭐

| Feature | Linear Search | Binary Search |
|---------|--------------|---------------|
| Requirement | None | **Array must be sorted** |
| Time complexity | O(n) | O(log n) |
| Best case | O(1) | O(1) |
| Strategy | Check each element | Divide and conquer |

**Binary Search implementation:**
```java
int binarySearch(int[] arr, int target) {
  int left = 0, right = arr.length - 1;
  while (left <= right) {
    int mid = left + (right - left) / 2;  // avoid overflow
    if (arr[mid] == target) return mid;
    else if (arr[mid] < target) left = mid + 1;
    else right = mid - 1;
  }
  return -1; // not found
}
```

**🧠 Remember:** Binary search halves the search space each time → O(log n).
**⚠️ Common mistake:** Using `(left + right) / 2` → can overflow for large arrays. Use `left + (right - left) / 2`.

---

### Q3. Sorting Algorithms ⭐

| Algorithm | Best | Average | Worst | Stable? | Space |
|-----------|------|---------|-------|---------|-------|
| Bubble Sort | O(n) | O(n²) | O(n²) | Yes | O(1) |
| Selection Sort | O(n²) | O(n²) | O(n²) | No | O(1) |
| Insertion Sort | O(n) | O(n²) | O(n²) | Yes | O(1) |
| Merge Sort | O(n log n) | O(n log n) | O(n log n) | Yes | O(n) |
| Quick Sort | O(n log n) | O(n log n) | O(n²) | No | O(log n) |

**Bubble Sort — logic:**
```java
// Compare adjacent elements, swap if out of order. Repeat.
for (int i = 0; i < n - 1; i++) {
  for (int j = 0; j < n - i - 1; j++) {
    if (arr[j] > arr[j + 1]) {
      int temp = arr[j]; arr[j] = arr[j+1]; arr[j+1] = temp;
    }
  }
}
```

**Selection Sort — logic:**
Find minimum in unsorted portion, swap with first unsorted element.

**Insertion Sort — logic:**
Pick element, insert it in correct position in sorted left portion.

**Merge Sort — Divide & Conquer:**
Split array in half, sort each half, merge. Always O(n log n). Stable.

**Quick Sort — Divide & Conquer:**
Pick pivot, partition (smaller left, larger right), recurse. Avg O(n log n), worst O(n²).

**Which is stable?** Bubble, Insertion, Merge Sort = stable. Selection, Quick = unstable.

**🧠 Remember:** "Stable sorts don't change relative order of equal elements"

---

### Q4. Stack ⭐

**Definition:** LIFO (Last In, First Out) data structure.

```
Push 1, Push 2, Push 3
Stack: [1, 2, 3] → Top = 3
Pop → 3 (last in, first out)
```

**Operations:** push, pop, peek, isEmpty — all O(1)

**Use cases:** Function call stack, undo operations, balanced parentheses, backtracking

---

### Q5. Queue ⭐

**Definition:** FIFO (First In, First Out) data structure.

```
Enqueue 1, 2, 3
Queue: [1, 2, 3] → Front = 1
Dequeue → 1 (first in, first out)
```

**Operations:** enqueue, dequeue, front, isEmpty — all O(1)

**Use cases:** BFS, task scheduling, printer queue

**🧠 Remember:** Stack = plates (last plate on = first off), Queue = line/queue (first in = first out)

---

### Q6. Linked List ⭐

**Definition:** A sequence of nodes, each containing data + pointer to next node.

**Singly:** Node → Node → Node → null
**Doubly:** null ← Node ↔ Node ↔ Node → null

**Array vs Linked List:**
| Feature | Array | Linked List |
|---------|-------|-------------|
| Access | O(1) | O(n) |
| Insert (head) | O(n) — shift needed | O(1) |
| Insert (tail) | O(1) | O(n) (singly) / O(1) (with tail pointer) |
| Memory | Contiguous | Non-contiguous (pointer overhead) |
| Size | Fixed | Dynamic |

---

### Q7. HashMap ⭐ 🔥

**Definition:** Key-value store using hashing for O(1) average lookup.

**How it works:**
1. Take key → apply hash function → get bucket index
2. Store value at that bucket (array index)
3. Collision handling: chaining (Java) — linked list at each bucket

**Collision:** Two keys hash to the same bucket.
**How Java handles it:** **Separate chaining** (linked list, then tree if > 8 entries in Java 8+).

**HashMap vs HashSet:**
| Feature | HashMap | HashSet |
|---------|---------|---------|
| Stores | Key-value pairs | Only keys |
| Backed by | Hash table | HashMap internally |
| Duplicates | Keys unique, values can repeat | No duplicates |

**Average case:** O(1) lookup. **Worst case:** O(n) — all keys collide.

---

### Q8. DSA Array Problems — Section 02 ⭐

#### Find Largest Element
```java
int max = arr[0];
for (int x : arr) if (x > max) max = x;
```

#### Find Second Largest (without sorting) ⭐
```java
int first = Integer.MIN_VALUE, second = Integer.MIN_VALUE;
for (int x : arr) {
  if (x > first) { second = first; first = x; }
  else if (x > second && x != first) second = x;
}
```

#### Reverse an Array In-place ⭐
```java
int left = 0, right = arr.length - 1;
while (left < right) {
  int temp = arr[left]; arr[left] = arr[right]; arr[right] = temp;
  left++; right--;
}
```

#### Missing Number from 1...n ⭐ (Q601)
```java
// Formula: sum of 1..n = n*(n+1)/2
int n = arr.length + 1;
int expected = n * (n + 1) / 2;
int actual = 0;
for (int x : arr) actual += x;
return expected - actual;
// Time: O(n), Space: O(1) ✅
```

#### Maximum Subarray Sum (Kadane's Algorithm) ⭐
```java
int maxSum = arr[0], currentSum = arr[0];
for (int i = 1; i < arr.length; i++) {
  currentSum = Math.max(arr[i], currentSum + arr[i]);
  maxSum = Math.max(maxSum, currentSum);
}
```

**🧠 Remember:** Kadane's = "at each step, either extend current subarray or start fresh"

#### Two Sum ⭐ 🔥
```java
// Using HashMap — O(n) time
Map<Integer, Integer> map = new HashMap<>();
for (int i = 0; i < nums.length; i++) {
  int complement = target - nums[i];
  if (map.containsKey(complement)) {
    return new int[]{map.get(complement), i};
  }
  map.put(nums[i], i);
}
```

#### Move All Zeroes to End
```java
int insertPos = 0;
for (int x : arr) if (x != 0) arr[insertPos++] = x;
while (insertPos < arr.length) arr[insertPos++] = 0;
```

#### Find Maximum Profit (Stock) ⭐
```java
// Buy low, sell high — one transaction
int minPrice = arr[0], maxProfit = 0;
for (int price : arr) {
  minPrice = Math.min(minPrice, price);
  maxProfit = Math.max(maxProfit, price - minPrice);
}
```

---

### Q9. Recursion ⭐

**Definition:** A function that calls itself with a smaller subproblem until it reaches a **base case**.

**Required:** Every recursive function MUST have a base case. Without it → **StackOverflowError / infinite recursion**.

```java
// Factorial
int factorial(int n) {
  if (n <= 1) return 1;         // base case
  return n * factorial(n - 1); // recursive case
}

// Fibonacci
int fib(int n) {
  if (n <= 1) return n;
  return fib(n-1) + fib(n-2);
}
```

**Space complexity of recursion:** O(n) — call stack depth = n.

**Recursion vs Iteration:**
| Feature | Recursion | Iteration |
|---------|-----------|-----------|
| Readability | Often cleaner | More explicit |
| Space | O(n) stack | O(1) |
| Risk | Stack overflow | None |

---

## 🔑 QUICK MEMORY TRICKS

- **Big-O:** 1 < log n < n < n log n < n² (small to large)
- **Binary search:** MUST be sorted. Halves space = log n
- **Stack = LIFO** (plates), **Queue = FIFO** (line)
- **Missing number:** Expected sum - Actual sum = missing
- **Two Sum:** HashMap stores "what we've seen so far" → complement check
- **Kadane's:** "extend or restart" at every element

---

## ⚠️ COMMON MISTAKES

1. Using `(left + right) / 2` in binary search — can overflow
2. Forgetting sorted condition for binary search
3. Confusing Stack (LIFO) with Queue (FIFO)
4. Not handling base case in recursion
5. HashMap: Forgetting it handles collision — doesn't mean unique buckets
