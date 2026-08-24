# DSA — DATA STRUCTURES & ALGORITHMS
## Tech Passport Phase 1 + Phase 2

---

# PART 1 — TIME COMPLEXITY

## What is Time Complexity?
Time complexity measures how the running time of an algorithm grows as input size (n) grows. We use Big-O notation.

## Big-O Complexity Table

| Notation | Name | Example | 1000 elements |
|----------|------|---------|---------------|
| O(1) | Constant | Array access by index | 1 operation |
| O(log n) | Logarithmic | Binary search | ~10 operations |
| O(n) | Linear | Linear search | 1000 operations |
| O(n log n) | Linearithmic | Merge sort | ~10000 operations |
| O(n²) | Quadratic | Bubble sort | 1,000,000 operations |
| O(2^n) | Exponential | Recursive subsets | Huge! |

## Intuitive Examples

**O(1):** Looking up element at `arr[5]`. No matter how big the array is, it's always one step.

**O(log n):** Binary search. Each step halves the search space. For 1024 elements, takes only 10 steps.

**O(n):** Linear search. Worst case: check every element.

**O(n log n):** Merge sort. Divides and merges.

**O(n²):** Nested loops. Bubble sort — for each of n elements, compare with n others.

## Algorithm Complexity Reference

| Algorithm | Best | Average | Worst | Space |
|-----------|------|---------|-------|-------|
| Linear Search | O(1) | O(n) | O(n) | O(1) |
| Binary Search | O(1) | O(log n) | O(log n) | O(1) |
| Bubble Sort | O(n) | O(n²) | O(n²) | O(1) |
| Selection Sort | O(n²) | O(n²) | O(n²) | O(1) |
| Insertion Sort | O(n) | O(n²) | O(n²) | O(1) |
| Merge Sort | O(n log n) | O(n log n) | O(n log n) | O(n) |
| Quick Sort | O(n log n) | O(n log n) | O(n²) | O(log n) |

> EXAM TIP: Bubble sort worst case = O(n²). Binary search requires SORTED array. Merge sort is always O(n log n).

---

# PART 2 — ARRAYS

## Linear Search

```java
static int linearSearch(int[] arr, int target) {
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == target) return i;  // found at index i
    }
    return -1;  // not found
}
// Time: O(n), Space: O(1)
```

## Binary Search (SORTED array only)

```java
static int binarySearch(int[] arr, int target) {
    int low = 0, high = arr.length - 1;
    while (low <= high) {
        int mid = low + (high - low) / 2;  // prevents overflow
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}
// Time: O(log n), Space: O(1)
```

> COMMON TRAP: Binary search ONLY works on sorted arrays. Using on unsorted array gives wrong results.

> EXAM TIP: Use `mid = low + (high - low) / 2` NOT `(low + high) / 2` to avoid integer overflow.

## Reverse an Array

```java
static void reverse(int[] arr) {
    int left = 0, right = arr.length - 1;
    while (left < right) {
        int temp = arr[left];
        arr[left] = arr[right];
        arr[right] = temp;
        left++;
        right--;
    }
}
// Time: O(n), Space: O(1)
```

## Find Maximum and Minimum

```java
static int findMax(int[] arr) {
    int max = arr[0];  // NOT 0! Could miss negative numbers
    for (int i = 1; i < arr.length; i++) {
        if (arr[i] > max) max = arr[i];
    }
    return max;
}
```

## Frequency Count (using array)

```java
int[] arr = {1, 2, 2, 3, 3, 3, 4};
int[] freq = new int[10];  // assuming values 0-9
for (int x : arr) {
    freq[x]++;
}
// freq[1]=1, freq[2]=2, freq[3]=3, freq[4]=1
```

## Detect Duplicates

```java
// Method 1: O(n²) brute force
for (int i = 0; i < arr.length; i++) {
    for (int j = i + 1; j < arr.length; j++) {
        if (arr[i] == arr[j]) {
            System.out.println("Duplicate: " + arr[i]);
        }
    }
}

// Method 2: Sort first, then check adjacent O(n log n)
Arrays.sort(arr);
for (int i = 0; i < arr.length - 1; i++) {
    if (arr[i] == arr[i+1]) System.out.println("Duplicate: " + arr[i]);
}
```

## Array Rotation

```java
// Left rotate by 1 position
static void leftRotate(int[] arr) {
    int first = arr[0];
    for (int i = 0; i < arr.length - 1; i++) {
        arr[i] = arr[i+1];
    }
    arr[arr.length - 1] = first;
}
// {1,2,3,4,5} -> {2,3,4,5,1}
```

---

# PART 3 — SORTING ALGORITHMS

## Bubble Sort

**Concept:** Compare adjacent elements. Swap if in wrong order. After each pass, largest element bubbles to end.

```java
static void bubbleSort(int[] arr) {
    int n = arr.length;
    for (int i = 0; i < n - 1; i++) {       // n-1 passes
        for (int j = 0; j < n - 1 - i; j++) {  // reduce range each pass
            if (arr[j] > arr[j+1]) {
                // swap
                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }
}
```

**Trace:** {5, 3, 8, 1}
- Pass 1: {3,5,1,8} — 8 goes to end
- Pass 2: {3,1,5,8} — 5 goes to position
- Pass 3: {1,3,5,8} — sorted!

> EXAM TIP: Number of passes = n-1. After k passes, last k elements are in correct position.

## Selection Sort

**Concept:** Find minimum in remaining array, swap to current position.

```java
static void selectionSort(int[] arr) {
    int n = arr.length;
    for (int i = 0; i < n - 1; i++) {
        int minIdx = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIdx]) {
                minIdx = j;
            }
        }
        // Swap arr[i] with arr[minIdx]
        int temp = arr[minIdx];
        arr[minIdx] = arr[i];
        arr[i] = temp;
    }
}
```

## Insertion Sort

**Concept:** Take each element and insert it into correct position in already-sorted portion.

```java
static void insertionSort(int[] arr) {
    for (int i = 1; i < arr.length; i++) {
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j+1] = arr[j];
            j--;
        }
        arr[j+1] = key;
    }
}
```

**Best case:** O(n) — when array is already sorted (no inner loop iterations).

## Merge Sort (Concept + Code)

**Concept:** Divide array in half, sort each half, merge them back.

```java
static void mergeSort(int[] arr, int left, int right) {
    if (left < right) {
        int mid = (left + right) / 2;
        mergeSort(arr, left, mid);       // sort left half
        mergeSort(arr, mid + 1, right);  // sort right half
        merge(arr, left, mid, right);    // merge
    }
}

static void merge(int[] arr, int left, int mid, int right) {
    // Create temp arrays
    int n1 = mid - left + 1;
    int n2 = right - mid;
    int[] L = new int[n1];
    int[] R = new int[n2];
    
    for (int i = 0; i < n1; i++) L[i] = arr[left + i];
    for (int j = 0; j < n2; j++) R[j] = arr[mid + 1 + j];
    
    int i = 0, j = 0, k = left;
    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) arr[k++] = L[i++];
        else arr[k++] = R[j++];
    }
    while (i < n1) arr[k++] = L[i++];
    while (j < n2) arr[k++] = R[j++];
}
// Time: O(n log n) always. Space: O(n)
```

## Quick Sort (Concept)

**Concept:** Pick a pivot. Put elements smaller than pivot on left, larger on right. Recurse.
- Average: O(n log n)
- Worst: O(n²) when pivot is always min/max (sorted array)

---

# PART 4 — STRINGS

## Palindrome Check

```java
static boolean isPalindrome(String s) {
    int left = 0, right = s.length() - 1;
    while (left < right) {
        if (s.charAt(left) != s.charAt(right)) return false;
        left++;
        right--;
    }
    return true;
}
// "racecar" -> true, "hello" -> false
```

## Anagram Check

```java
static boolean isAnagram(String a, String b) {
    if (a.length() != b.length()) return false;
    int[] count = new int[26];
    for (char c : a.toCharArray()) count[c - 'a']++;
    for (char c : b.toCharArray()) count[c - 'a']--;
    for (int x : count) if (x != 0) return false;
    return true;
}
// "listen", "silent" -> true
```

## Character Frequency

```java
static void charFrequency(String s) {
    int[] freq = new int[26];
    for (char c : s.toLowerCase().toCharArray()) {
        if (c >= 'a' && c <= 'z') freq[c - 'a']++;
    }
    for (int i = 0; i < 26; i++) {
        if (freq[i] > 0) {
            System.out.println((char)('a' + i) + ": " + freq[i]);
        }
    }
}
```

## Find Duplicate Characters

```java
static void findDuplicates(String s) {
    int[] freq = new int[26];
    for (char c : s.toCharArray()) freq[c - 'a']++;
    for (int i = 0; i < 26; i++) {
        if (freq[i] > 1) System.out.print((char)('a' + i) + " ");
    }
}
```

---

# PART 5 — STACK

## Concept
LIFO — Last In, First Out.
Think: a stack of plates. Last plate placed is first to be removed.

## Operations
- **push(x):** Add element to top
- **pop():** Remove and return top element
- **peek()/top():** View top element without removing
- **isEmpty():** Check if stack is empty
- **size():** Number of elements

```java
import java.util.Stack;

Stack<Integer> stack = new Stack<>();
stack.push(1);    // [1]
stack.push(2);    // [1, 2]
stack.push(3);    // [1, 2, 3]
stack.peek();     // 3 (doesn't remove)
stack.pop();      // 3 is removed → [1, 2]
stack.isEmpty();  // false
stack.size();     // 2
```

## Stack Applications
- Undo operation in editors
- Browser back button
- Balanced parentheses checking
- Function call stack

## Balanced Parentheses (classic stack problem)

```java
static boolean isBalanced(String s) {
    Stack<Character> stack = new Stack<>();
    for (char c : s.toCharArray()) {
        if (c == '(' || c == '[' || c == '{') {
            stack.push(c);
        } else {
            if (stack.isEmpty()) return false;
            char top = stack.pop();
            if (c == ')' && top != '(') return false;
            if (c == ']' && top != '[') return false;
            if (c == '}' && top != '{') return false;
        }
    }
    return stack.isEmpty();
}
```

---

# PART 6 — QUEUE

## Concept
FIFO — First In, First Out.
Think: a line at a ticket counter. First person in line gets served first.

## Operations
- **enqueue(x) / add(x):** Add to back
- **dequeue() / remove():** Remove from front
- **peek()/front():** View front without removing
- **isEmpty():** Check if empty

```java
import java.util.Queue;
import java.util.LinkedList;

Queue<Integer> queue = new LinkedList<>();
queue.add(1);      // [1]
queue.add(2);      // [1, 2]
queue.add(3);      // [1, 2, 3]
queue.peek();      // 1 (front, doesn't remove)
queue.remove();    // 1 removed → [2, 3]
queue.isEmpty();   // false
```

## Queue Applications
- Print queue
- Task scheduling
- BFS (Breadth-First Search)
- Customer service systems

---

# PART 7 — 20 DSA MCQs

**Q1:** What is the time complexity of binary search on a sorted array of n elements?
A) O(n)   B) O(log n)   C) O(n log n)   D) O(1)

**Q2:** Which data structure follows LIFO principle?
A) Queue   B) Stack   C) Array   D) Linked List

**Q3:** What is the worst-case time complexity of bubble sort?
A) O(n)   B) O(log n)   C) O(n²)   D) O(n log n)

**Q4:** Binary search requires the array to be:
A) Sorted   B) Unsorted   C) Reversed   D) Has no requirement

**Q5:** What is the time complexity of accessing an element by index in an array?
A) O(n)   B) O(log n)   C) O(1)   D) O(n²)

**Q6:** Which sorting algorithm has best-case complexity of O(n)?
A) Bubble Sort   B) Selection Sort   C) Insertion Sort   D) Both A and C

**Q7:** The space complexity of merge sort is:
A) O(1)   B) O(log n)   C) O(n)   D) O(n²)

**Q8:** In a stack, which operation adds an element?
A) pop   B) push   C) peek   D) enqueue

**Q9:** What happens when you call pop() on an empty stack?
A) Returns 0   B) Returns null   C) Throws EmptyStackException   D) Does nothing

**Q10:** Selection sort always makes exactly how many swaps?
A) n   B) n-1   C) n²   D) n log n

**Q11:** What is the output if we search for 5 in {1,3,5,7,9} using binary search?
First mid: index 2 = 5. Found at:
A) index 1   B) index 2   C) index 3   D) -1

**Q12:** Which is NOT an application of stack?
A) Undo operation   B) Function calls   C) CPU scheduling   D) Parsing expressions

**Q13:** Time complexity of finding maximum in unsorted array:
A) O(1)   B) O(log n)   C) O(n)   D) O(n²)

**Q14:** After 2 passes of bubble sort on {5,3,1,4,2}, which elements are definitely in place?
A) Largest 1   B) Largest 2   C) All   D) None

**Q15:** Which data structure is used for BFS (breadth-first search)?
A) Stack   B) Queue   C) Array   D) Tree

**Q16:** Merge sort divides the array until:
A) All elements are 0   B) Each subarray has 1 element   C) It finds the pivot   D) Array is sorted

**Q17:** The number of comparisons in binary search for n=16 (worst case) is:
A) 16   B) 8   C) 4   D) 5 (log₂16 = 4, need 1 more)

**Q18:** Insertion sort performs well when:
A) Array is reverse sorted   B) Array is nearly sorted   C) Array has duplicates   D) Array is large

**Q19:** In queue using array, enqueue adds to:
A) Front   B) Back   C) Random position   D) Middle

**Q20:** Which sort is called "in-place" and has O(1) extra space?
A) Merge sort   B) Bubble sort   C) Quick sort (avg)   D) Both B and C

## ANSWERS — DSA MCQs

| Q | A | Explanation |
|---|---|-------------|
| 1 | B | Binary search halves search space each time |
| 2 | B | Stack = LIFO |
| 3 | C | Bubble sort is O(n²) worst and average |
| 4 | A | Binary search requires sorted array |
| 5 | C | Array index access is always O(1) |
| 6 | D | Both bubble (with optimization) and insertion are O(n) best case |
| 7 | C | Merge sort needs O(n) extra space for merging |
| 8 | B | push() adds to stack |
| 9 | C | EmptyStackException thrown |
| 10 | B | Selection sort makes exactly n-1 swaps |
| 11 | B | Found at index 2 (0-indexed) |
| 12 | C | CPU scheduling uses queue |
| 13 | C | Must check all n elements |
| 14 | B | After k passes, last k elements are placed |
| 15 | B | BFS uses Queue |
| 16 | B | Merge sort divides until single elements |
| 17 | D | log₂16 = 4, but 0-indexed gives 4 comparisons max |
| 18 | B | Insertion sort shines on nearly-sorted data |
| 19 | B | Enqueue = add to back (rear) |
| 20 | D | Bubble and quick sort are in-place |

---

# PART 8 — 15 DSA LOGIC/OUTPUT QUESTIONS

**L1:** Trace bubble sort on {4, 2, 7, 1, 3}. Show array after Pass 1.
**Answer:** Compare 4>2: swap → {2,4,7,1,3}. Compare 4<7: no. Compare 7>1: swap → {2,4,1,7,3}. Compare 7>3: swap → {2,4,1,3,7}. **After Pass 1: {2,4,1,3,7}**

**L2:** How many times does binary search divide before finding 3 in {1,2,3,4,5,6,7}?
**Answer:** n=7. mid=3 (index 3)=4. 3<4, so high=2. mid=1=2. 3>2, so low=2. mid=2=3. Found! **3 divisions.**

**L3:** What does this code print?
```java
Stack<Integer> s = new Stack<>();
s.push(1); s.push(2); s.push(3);
System.out.println(s.pop());
System.out.println(s.peek());
```
**Answer:** 3 (pop), 2 (peek — doesn't remove)

**L4:** Is "madam" a palindrome? Show the pointer movements.
**Answer:** left=0('m'), right=4('m'): match. left=1('a'), right=3('a'): match. left=right=2('d'): loop ends. YES, palindrome.

**L5:** Find frequency of each character in "banana":
**Answer:** b:1, a:3, n:2

**L6:** How many passes does bubble sort need to fully sort {3,1,2}?
**Answer:** Pass 1: {1,2,3} — done in 1 pass! (2 passes at most for n=3)

**L7:** Binary search on {2,4,6,8,10}: search for 7. Steps?
**Answer:** low=0, high=4. mid=2, arr[2]=6 < 7, low=3. mid=3, arr[3]=8 > 7, high=2. low>high. **Return -1 (not found).**

**L8:** Stack operations: push(5), push(3), pop(), push(7), peek(). What is top?
**Answer:** push(5):[5], push(3):[5,3], pop():[5], push(7):[5,7], peek()=**7**

**L9:** After selection sort Pass 2 on {5,3,1,4,2}?
After Pass 1: min is 1, swap with index 0 → {1,3,5,4,2}
After Pass 2: min of {3,5,4,2} is 2, swap → {1,2,5,4,3}
**Answer: {1,2,5,4,3}**

**L10:** What is O(n + n²) simplified?
**Answer:** O(n²) — highest term dominates.

**L11:** What is the complexity of printing all elements of a 2D n×n matrix?
**Answer:** O(n²) — n rows × n columns.

**L12:** Queue operations: enqueue(1), enqueue(2), dequeue(), enqueue(3), peek(). Front is?
**Answer:** enqueue(1):[1], enqueue(2):[1,2], dequeue():[2], enqueue(3):[2,3], peek()=**2**

**L13:** Array {1,5,2,8,3}. After one linear search for 8, return value?
**Answer:** Index **3** (0-indexed)

**L14:** What is the space complexity of linear search?
**Answer:** O(1) — only uses a few variables

**L15:** Is {2,4,6,8,5} sorted? Can binary search be used correctly?
**Answer:** NO. It is NOT sorted (5 breaks the order). Binary search would give WRONG results.

---

# PART 9 — 15 DSA CODING QUESTIONS

**DC1:** Find second largest in array {3,7,1,9,4}
```java
static int secondLargest(int[] arr) {
    int max = Integer.MIN_VALUE, second = Integer.MIN_VALUE;
    for (int x : arr) {
        if (x > max) { second = max; max = x; }
        else if (x > second && x != max) second = x;
    }
    return second;  // 7
}
```

**DC2:** Count occurrences of element k in array
```java
static int countOccurrences(int[] arr, int k) {
    int count = 0;
    for (int x : arr) if (x == k) count++;
    return count;
}
```

**DC3:** Check if array is sorted
```java
static boolean isSorted(int[] arr) {
    for (int i = 0; i < arr.length - 1; i++) {
        if (arr[i] > arr[i+1]) return false;
    }
    return true;
}
```

**DC4:** Sum of digits
```java
static int digitSum(int n) {
    int sum = 0;
    while (n > 0) { sum += n % 10; n /= 10; }
    return sum;  // digitSum(123) = 6
}
```

**DC5:** Find all pairs with given sum
```java
static void pairsWithSum(int[] arr, int target) {
    for (int i = 0; i < arr.length; i++) {
        for (int j = i+1; j < arr.length; j++) {
            if (arr[i] + arr[j] == target) {
                System.out.println(arr[i] + " + " + arr[j]);
            }
        }
    }
}
```

**DC6:** Count vowels in string
```java
static int countVowels(String s) {
    int count = 0;
    for (char c : s.toLowerCase().toCharArray()) {
        if ("aeiou".indexOf(c) != -1) count++;
    }
    return count;
}
```

**DC7:** Remove duplicates from sorted array (in-place)
```java
static int removeDuplicates(int[] arr) {
    if (arr.length == 0) return 0;
    int pos = 1;
    for (int i = 1; i < arr.length; i++) {
        if (arr[i] != arr[i-1]) arr[pos++] = arr[i];
    }
    return pos;  // new length
}
```

**DC8:** Prefix sum array
```java
static int[] prefixSum(int[] arr) {
    int[] prefix = new int[arr.length];
    prefix[0] = arr[0];
    for (int i = 1; i < arr.length; i++) {
        prefix[i] = prefix[i-1] + arr[i];
    }
    return prefix;
    // {1,2,3,4,5} -> {1,3,6,10,15}
}
```

**DC9:** Merge two sorted arrays
```java
static int[] mergeSorted(int[] a, int[] b) {
    int[] result = new int[a.length + b.length];
    int i = 0, j = 0, k = 0;
    while (i < a.length && j < b.length) {
        if (a[i] <= b[j]) result[k++] = a[i++];
        else result[k++] = b[j++];
    }
    while (i < a.length) result[k++] = a[i++];
    while (j < b.length) result[k++] = b[j++];
    return result;
}
```

**DC10:** Count inversions (brute force)
```java
static int countInversions(int[] arr) {
    int count = 0;
    for (int i = 0; i < arr.length; i++)
        for (int j = i+1; j < arr.length; j++)
            if (arr[i] > arr[j]) count++;
    return count;
}
```

**DC11:** Move all zeros to end
```java
static void moveZeros(int[] arr) {
    int pos = 0;
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] != 0) arr[pos++] = arr[i];
    }
    while (pos < arr.length) arr[pos++] = 0;
}
// {1,0,2,0,3} -> {1,2,3,0,0}
```

**DC12:** Implement Stack using array
```java
class ArrayStack {
    int[] arr;
    int top = -1;
    ArrayStack(int size) { arr = new int[size]; }
    void push(int x) { if (top < arr.length-1) arr[++top] = x; }
    int pop() { if (top >= 0) return arr[top--]; return -1; }
    int peek() { return top >= 0 ? arr[top] : -1; }
    boolean isEmpty() { return top == -1; }
}
```

**DC13:** Implement Queue using array
```java
class ArrayQueue {
    int[] arr;
    int front = 0, rear = -1, size = 0;
    ArrayQueue(int capacity) { arr = new int[capacity]; }
    void enqueue(int x) { arr[++rear] = x; size++; }
    int dequeue() { size--; return arr[front++]; }
    int peek() { return arr[front]; }
    boolean isEmpty() { return size == 0; }
}
```

**DC14:** Two-pointer: Check if sum of two elements equals target
```java
// For SORTED array
static boolean hasPairWithSum(int[] arr, int target) {
    int left = 0, right = arr.length - 1;
    while (left < right) {
        int sum = arr[left] + arr[right];
        if (sum == target) return true;
        else if (sum < target) left++;
        else right--;
    }
    return false;
}
// Time: O(n), Space: O(1)
```

**DC15:** Maximum subarray sum (Kadane's algorithm)
```java
static int maxSubarraySum(int[] arr) {
    int maxSum = arr[0], currentSum = arr[0];
    for (int i = 1; i < arr.length; i++) {
        currentSum = Math.max(arr[i], currentSum + arr[i]);
        maxSum = Math.max(maxSum, currentSum);
    }
    return maxSum;
    // {-2,1,-3,4,-1,2,1,-5,4} -> 6 ({4,-1,2,1})
}
```

---

# PART 10 — 10 COMPLEXITY QUESTIONS

**CX1:** What is the complexity of this code?
```java
for (int i = 0; i < n; i++) {
    System.out.println(i);
}
```
**Answer: O(n)**

**CX2:** What is the complexity?
```java
for (int i = 0; i < n; i++)
    for (int j = 0; j < n; j++)
        System.out.println(i + " " + j);
```
**Answer: O(n²)**

**CX3:** What is the complexity of accessing `arr[5]`?
**Answer: O(1)**

**CX4:** What is the complexity of binary search?
**Answer: O(log n)**

**CX5:** Which is faster: O(n log n) or O(n²) for large n?
**Answer: O(n log n)** — grows much slower.

**CX6:** What is the total complexity?
```java
// Part 1: O(n²) sort
// Part 2: O(n) search
```
**Answer: O(n²)** — dominant term wins.

**CX7:** Is O(2n) = O(n)?
**Answer: YES** — constants are dropped in Big-O.

**CX8:** What is the complexity of printing 1 to n using recursion?
**Answer: O(n)** — n recursive calls.

**CX9:** Arrange in increasing order: O(n²), O(n), O(1), O(n log n), O(log n)
**Answer: O(1) < O(log n) < O(n) < O(n log n) < O(n²)**

**CX10:** If algorithm A takes O(n) and B takes O(log n), which is better?
**Answer: B is better** — logarithmic grows much slower than linear.
