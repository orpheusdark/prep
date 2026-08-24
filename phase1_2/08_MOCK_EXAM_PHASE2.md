# PHASE 2 MOCK EXAMINATION — TECH PRO
## Time: 90 Minutes | Total Marks: 100 | Difficulty: Medium-Hard

### INSTRUCTIONS
- Attempt ALL questions
- Write your answers before checking the key
- Time yourself strictly

---

# SECTION A — ADVANCED JAVA OUTPUT (20 marks | 2 marks each)

**Q1:** What is the output?
```java
public class Main {
    static int x = 10;
    
    static void modify() {
        x = 20;
    }
    
    public static void main(String[] args) {
        System.out.println(x);
        modify();
        System.out.println(x);
    }
}
```

---

**Q2:** What is the output?
```java
class A {
    A() { System.out.print("A "); }
}
class B extends A {
    B() { System.out.print("B "); }
}
class C extends B {
    C() { System.out.print("C "); }
}
public class Main {
    public static void main(String[] args) {
        new C();
    }
}
```

---

**Q3:** What is the output?
```java
public class Main {
    static int fib(int n) {
        if (n <= 1) return n;
        return fib(n-1) + fib(n-2);
    }
    public static void main(String[] args) {
        System.out.println(fib(6));
    }
}
```

---

**Q4:** What is the output?
```java
interface Shape {
    default void draw() { System.out.println("Drawing shape"); }
}
class Circle implements Shape {
    public void draw() { System.out.println("Drawing circle"); }
}
public class Main {
    public static void main(String[] args) {
        Shape s = new Circle();
        s.draw();
    }
}
```

---

**Q5:** What is the output?
```java
public class Main {
    public static void main(String[] args) {
        int[] arr = {5, 3, 8, 1, 9, 2};
        int max = arr[0];
        for (int i = 1; i < arr.length; i++) {
            if (arr[i] > max) max = arr[i];
        }
        System.out.println(max);
    }
}
```

---

**Q6:** What is the output?
```java
public class Main {
    static int count(int n) {
        if (n == 0) return 0;
        return 1 + count(n / 10);
    }
    public static void main(String[] args) {
        System.out.println(count(12345));
    }
}
```

---

**Q7:** What is the output?
```java
String s = "Hello";
StringBuilder sb = new StringBuilder(s);
sb.reverse();
sb.append("!");
System.out.println(sb);
System.out.println(s);
```

---

**Q8:** What is the output?
```java
class Vehicle {
    String type = "Vehicle";
    void show() { System.out.println("Type: " + type); }
}
class Car extends Vehicle {
    String type = "Car";
    void show() { System.out.println("Type: " + type); }
}
public class Main {
    public static void main(String[] args) {
        Vehicle v = new Car();
        v.show();
        System.out.println(v.type);
    }
}
```

---

**Q9:** What is the output?
```java
public class Main {
    public static void main(String[] args) {
        try {
            System.out.println(1);
            throw new RuntimeException("oops");
        } catch (RuntimeException e) {
            System.out.println(2);
            return;
        } finally {
            System.out.println(3);
        }
        System.out.println(4);
    }
}
```

---

**Q10:** What is the output?
```java
public class Main {
    static void swap(int a, int b) {
        int temp = a;
        a = b;
        b = temp;
    }
    public static void main(String[] args) {
        int x = 5, y = 10;
        swap(x, y);
        System.out.println(x + " " + y);
    }
}
```

---

# SECTION B — PROBLEM SOLVING (30 marks)

## B1: Array Problems (10 marks)

**BA1:** Given an array, find the second largest element. (5 marks)
Input: {3, 7, 1, 9, 4, 9}
Output: 7

Write the Java code:

---

**BA2:** Count how many times each number appears in the array. (5 marks)
Input: {1, 2, 3, 2, 1, 4, 3, 2}
Expected Output:
```
1 appears 2 times
2 appears 3 times
3 appears 2 times
4 appears 1 times
```

---

## B2: String Problems (10 marks)

**BS1:** Check if two strings are anagrams of each other. (5 marks)
Input: "listen", "silent"
Output: true

---

**BS2:** Find the most frequent character in a string. (5 marks)
Input: "programming"
Output: g (appears 2 times) or r (appears 2 times) — first with max frequency

---

## B3: Algorithm Implementation (10 marks)

**BB1:** Implement binary search. Return index if found, -1 if not. (5 marks)
Input: arr={1,3,5,7,9,11,13}, target=7
Output: 3

---

**BB2:** Implement selection sort. Show the sorted array. (5 marks)
Input: {64, 25, 12, 22, 11}
Output: 11 12 22 25 64

---

# SECTION C — DSA CONCEPTS (20 marks)

## Part C1: Advanced MCQ (1 mark each)

**CM1:** Two-pointer technique for finding a pair with target sum works in:
A) O(n²) on any array   B) O(n) on sorted array   C) O(n log n)   D) O(1)

**CM2:** What is Kadane's algorithm used for?
A) Sorting   B) Searching   C) Maximum subarray sum   D) Graph traversal

**CM3:** Which approach solves "find pair with given sum in sorted array" most efficiently?
A) Two nested loops   B) Two pointers   C) Hash map   D) Binary search for each element

**CM4:** Sliding window technique is best for:
A) Finding maximum in array   B) Subarray problems with fixed/variable window   C) Sorting   D) Tree traversal

**CM5:** Frequency counting using a hash map achieves:
A) O(n log n) lookup   B) O(n²) total   C) O(n) total, O(1) lookup   D) O(1) total

**CM6:** Which sorting algorithm is stable (maintains relative order of equal elements)?
A) Selection sort   B) Quick sort   C) Insertion sort   D) Heap sort

**CM7:** The worst case of quick sort occurs when:
A) Array is random   B) Array is already sorted (with bad pivot)   C) Array has duplicates   D) Array is very large

**CM8:** To count characters in O(n) time, best data structure is:
A) Array of size 26   B) Nested loops   C) Sorting   D) Binary search

**CM9:** What is the complexity of checking if two strings are anagrams (sort-based approach)?
A) O(n)   B) O(n log n)   C) O(n²)   D) O(1)

**CM10:** "Move all zeros to end while maintaining order" is best done using:
A) Sorting   B) Two-pointer or extra pointer   C) Stack   D) Queue

## Part C2: Complexity Analysis (10 marks, 2 marks each)

**CX1:** What is the complexity?
```java
for (int i = n; i > 0; i /= 2) {
    System.out.println(i);
}
```

**CX2:** What is the complexity?
```java
for (int i = 0; i < n; i++) {
    for (int j = i; j < n; j++) {
        System.out.println(i + " " + j);
    }
}
```

**CX3:** Which is more efficient for large n?
Algorithm A: O(n log n)
Algorithm B: O(n²)
Justify your answer.

**CX4:** What is the space complexity of bubble sort?

**CX5:** An algorithm runs in O(n) + O(n²) + O(log n). What is the overall complexity?

---

# SECTION D — CODE COMPREHENSION (15 marks)

## What does this code do?

**D1:** (5 marks) Read this code and explain:
1. What does it do?
2. What is the output for arr={5,2,8,1,9}?
3. What is its time complexity?

```java
static void mystery(int[] arr) {
    for (int i = 0; i < arr.length - 1; i++) {
        int idx = i;
        for (int j = i + 1; j < arr.length; j++) {
            if (arr[j] < arr[idx]) idx = j;
        }
        int temp = arr[idx];
        arr[idx] = arr[i];
        arr[i] = temp;
    }
}
```

---

**D2:** (5 marks) What does this code do? What is the output for "hello"?

```java
static String transform(String s) {
    StringBuilder result = new StringBuilder();
    int[] count = new int[26];
    for (char c : s.toCharArray()) count[c - 'a']++;
    for (int i = 0; i < 26; i++) {
        if (count[i] > 1) result.append((char)('a' + i));
    }
    return result.toString();
}
```

---

**D3:** (5 marks) What is the output? Explain the recursion:

```java
static void printReverse(int n) {
    if (n == 0) return;
    printReverse(n - 1);
    System.out.print(n + " ");
}
// called with printReverse(5)
```

---

# SECTION E — DEBUGGING (15 marks)

## Find and fix all bugs:

**E1:** (5 marks) This binary search has bugs:
```java
static int bSearch(int[] arr, int target) {
    int low = 0, high = arr.length;  // Bug 1
    while (low < high) {             // Bug 2
        int mid = (low + high) / 2;
        if (arr[mid] == target) return mid;
        if (arr[mid] < target) low = mid;  // Bug 3
        else high = mid;
    }
    return -1;
}
```

---

**E2:** (5 marks) This palindrome check has bugs:
```java
static boolean isPalin(String s) {
    for (int i = 0; i < s.length(); i++) {  // Bug 1
        if (s.charAt(i) != s.charAt(s.length() - i))  // Bug 2
            return false;
    }
    return true;
}
```

---

**E3:** (5 marks) This bubble sort has bugs:
```java
static void bubble(int[] arr) {
    for (int i = 0; i < arr.length; i++) {         // Bug 1
        for (int j = 0; j < arr.length; j++) {     // Bug 2
            if (arr[j] > arr[j+1]) {               // Bug 3
                arr[j] = arr[j+1];                 // Bug 4 (missing temp)
                arr[j+1] = arr[j];
            }
        }
    }
}
```

---

# ============ ANSWER KEY ============
# (Do NOT read until you've attempted everything)

---

## Section A — Java Output

**Q1:** 10, 20 — modify() changes static x, visible everywhere

**Q2:** A B C — parent constructors are called first (chain: A→B→C)

**Q3:** 8 — fib(6) = fib(5)+fib(4) = 5+3 = 8

**Q4:** Drawing circle — polymorphism: Circle overrides draw()

**Q5:** 9 — finds maximum in array

**Q6:** 5 — counts digits in 12345 recursively

**Q7:** olleH!, Hello — sb is modified (reversed + appended); s is unchanged (String immutability)

**Q8:** Type: Car, Vehicle
- show() is virtual → calls Car's version (polymorphism)
- Fields are NOT virtual → v.type uses Vehicle's field

**Q9:** 1, 2, 3 — NOT 4 (return exits after finally runs; 4 is unreachable)

**Q10:** 5 10 — Java passes primitives by VALUE; swap doesn't affect original x and y

---

## Section B — Solutions

### BA1:
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

### BA2:
```java
static void frequency(int[] arr) {
    int[] count = new int[100];  // assuming values < 100
    for (int x : arr) count[x]++;
    for (int i = 0; i < count.length; i++) {
        if (count[i] > 0)
            System.out.println(i + " appears " + count[i] + " times");
    }
}
```

### BS1:
```java
static boolean isAnagram(String a, String b) {
    if (a.length() != b.length()) return false;
    int[] count = new int[26];
    for (char c : a.toCharArray()) count[c-'a']++;
    for (char c : b.toCharArray()) count[c-'a']--;
    for (int x : count) if (x != 0) return false;
    return true;
}
```

### BS2:
```java
static char mostFrequent(String s) {
    int[] count = new int[26];
    for (char c : s.toCharArray()) count[c-'a']++;
    int maxIdx = 0;
    for (int i = 1; i < 26; i++) {
        if (count[i] > count[maxIdx]) maxIdx = i;
    }
    return (char)('a' + maxIdx);
}
```

### BB1:
```java
static int binarySearch(int[] arr, int target) {
    int low = 0, high = arr.length - 1;
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (arr[mid] == target) return mid;
        if (arr[mid] < target) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}
// Output: 3 (7 is at index 3)
```

### BB2:
```java
static void selectionSort(int[] arr) {
    for (int i = 0; i < arr.length - 1; i++) {
        int minIdx = i;
        for (int j = i+1; j < arr.length; j++)
            if (arr[j] < arr[minIdx]) minIdx = j;
        int temp = arr[minIdx]; arr[minIdx] = arr[i]; arr[i] = temp;
    }
}
// Output: 11 12 22 25 64
```

---

## Section C — DSA

### C1 Answers:
CM1:B, CM2:C, CM3:B, CM4:B, CM5:C, CM6:C, CM7:B, CM8:A, CM9:B, CM10:B

### C2 Complexity:
**CX1:** O(log n) — i halves each iteration
**CX2:** O(n²) — triangular sum ≈ n²/2
**CX3:** A is more efficient — O(n log n) grows much slower than O(n²)
**CX4:** O(1) — only uses a few variables
**CX5:** O(n²) — dominant term

---

## Section D — Comprehension

**D1:**
1. Selection sort — finds minimum in remaining array and swaps to current position
2. Output: 1 2 5 8 9 (sorted)
3. O(n²)

**D2:**
- Finds characters that appear MORE THAN ONCE in the string
- For "hello": l appears 2 times → output: "l"

**D3:**
- Output: 1 2 3 4 5
- Recursion goes deep until n=0, then prints on the WAY BACK UP (post-recursion)

---

## Section E — Debugging

**E1 Fixes:**
```java
static int bSearch(int[] arr, int target) {
    int low = 0, high = arr.length - 1;  // Fix 1: -1
    while (low <= high) {                 // Fix 2: <=
        int mid = low + (high - low) / 2;
        if (arr[mid] == target) return mid;
        if (arr[mid] < target) low = mid + 1;  // Fix 3: mid+1
        else high = mid - 1;                    // Fix 4: mid-1
    }
    return -1;
}
```

**E2 Fixes:**
```java
static boolean isPalin(String s) {
    for (int i = 0; i < s.length() / 2; i++) {  // Fix 1: only half
        if (s.charAt(i) != s.charAt(s.length() - 1 - i))  // Fix 2: -1-i
            return false;
    }
    return true;
}
```

**E3 Fixes:**
```java
static void bubble(int[] arr) {
    for (int i = 0; i < arr.length - 1; i++) {         // Fix 1: -1
        for (int j = 0; j < arr.length - 1 - i; j++) {  // Fix 2: -1-i
            if (arr[j] > arr[j+1]) {
                int temp = arr[j];    // Fix 3: add temp variable
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }
}
```

---

# SCORING PHASE 2

| Section | Max | Your Score |
|---------|-----|-----------|
| A: Java Output | 20 | /20 |
| B1: Array Problems | 10 | /10 |
| B2: String Problems | 10 | /10 |
| B3: Algorithm Impl | 10 | /10 |
| C: DSA MCQ | 10 | /10 |
| C: Complexity | 10 | /10 |
| D: Code Comprehension | 15 | /15 |
| E: Debugging | 15 | /15 |
| **TOTAL** | **100** | **/100** |

**Phase 2 Scoring:**
- 80–100: Excellent — strong problem solver
- 65–79: Good — ready for most questions
- 50–64: Need more practice on debugging and algorithms
- Below 50: Focus on fundamentals and pattern recognition
