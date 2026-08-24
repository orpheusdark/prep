# DON'T MAKE THESE MISTAKES
## The Complete Guide to Exam Errors

---

# JAVA MISTAKES

## 1. String Comparison with ==
```java
// WRONG:
if (s1 == s2) { }      // compares memory addresses!

// RIGHT:
if (s1.equals(s2)) { } // compares content
if (s1.equalsIgnoreCase(s2)) { } // case-insensitive
```
**Why it trips students:** == works for primitives (int, char), so they assume it works for String too. It does NOT.

---

## 2. Forgetting Strings Are Immutable
```java
String s = "hello";
s.toUpperCase();           // WRONG — this does nothing to s
System.out.println(s);    // still "hello"

s = s.toUpperCase();      // RIGHT — reassign
```
**Why it trips students:** String methods LOOK like they modify the string. They return new strings.

---

## 3. Off-By-One in Array Loops
```java
int[] arr = {1, 2, 3, 4, 5};
// WRONG:
for (int i = 0; i <= arr.length; i++) { // i <= 5 causes exception at i=5
    System.out.println(arr[i]);
}
// RIGHT:
for (int i = 0; i < arr.length; i++) {  // i < 5
```
**Why it trips students:** Valid indices are 0 to length-1. Using <= length accesses index 5 which doesn't exist.

---

## 4. Initializing Max with 0
```java
int[] arr = {-5, -3, -1, -8};
// WRONG:
int max = 0;  // All elements are negative, max stays 0 — WRONG!

// RIGHT:
int max = arr[0];          // or Integer.MIN_VALUE
```

---

## 5. Integer Division Surprise
```java
double result = 10 / 3;  // result = 3.0 NOT 3.33!
// Because 10/3 is evaluated as INTEGER division first

// RIGHT:
double result = 10.0 / 3;  // or (double)10 / 3
```

---

## 6. switch Fall-Through
```java
switch(x) {
    case 1: System.out.println("One");  // NO BREAK!
    case 2: System.out.println("Two");  // Falls through!
    case 3: System.out.println("Three");
    default: System.out.println("Other");
}
// If x=1, prints: One, Two, Three, Other (all of them!)
```
**Why it trips students:** They expect only the matching case to run.

---

## 7. Confusing Overloading and Overriding
```
Overloading = SAME class, SAME name, DIFFERENT parameters
Overriding = CHILD class, SAME name, SAME parameters

Overloading resolved at COMPILE time
Overriding resolved at RUNTIME
```

---

## 8. super() Position in Constructor
```java
// WRONG:
class Dog extends Animal {
    Dog() {
        System.out.println("Dog");
        super();   // MUST be first! This causes compilation error
    }
}
// RIGHT:
class Dog extends Animal {
    Dog() {
        super();  // First line
        System.out.println("Dog");
    }
}
```

---

## 9. Using this in Static Methods
```java
class Test {
    static void method() {
        System.out.println(this.x);  // COMPILE ERROR! No 'this' in static
    }
}
```

---

## 10. Array.length vs ArrayList.size()
```java
int[] arr = new int[5];
arr.length        // field — NO parentheses
arr.length()      // COMPILE ERROR

ArrayList<Integer> list = new ArrayList<>();
list.size()       // method — WITH parentheses
list.size         // COMPILE ERROR
```

---

## 11. substring() End is Exclusive
```java
"Hello".substring(1, 3) // "el" (index 1 and 2, NOT 3)
"Hello".substring(0, 5) // "Hello" (all 5 chars: 0,1,2,3,4)
```

---

## 12. Post vs Pre Increment in Expressions
```java
int x = 5;
int y = x++ + ++x;
// x++ gives 5 (then x=6), ++x gives 7 (x becomes 7), y = 5+7 = 12, x = 7
```

---

## 13. finally Always Runs
```java
try {
    return "try";   // Doesn't prevent finally!
} finally {
    System.out.println("finally");  // This STILL runs before return
}
```

---

## 14. Default Array Values
```java
int[] arr = new int[5];
// All values are 0, NOT undefined or null

String[] names = new String[3];
// All values are null, NOT ""

boolean[] flags = new boolean[3];
// All values are false
```

---

## 15. Recursion Without Base Case
```java
// WRONG:
static int factorial(int n) {
    return n * factorial(n-1);  // Infinite recursion! StackOverflowError
}

// RIGHT:
static int factorial(int n) {
    if (n <= 1) return 1;    // Base case!
    return n * factorial(n-1);
}
```

---

# DSA MISTAKES

## 16. Binary Search on Unsorted Array
```
Binary search ONLY works on sorted arrays.
On unsorted: may find wrong index or return -1 incorrectly.
```

## 17. Wrong Mid Calculation
```java
// WRONG for large values:
int mid = (low + high) / 2;  // low + high can overflow for large indices

// RIGHT:
int mid = low + (high - low) / 2;  // safe, no overflow
```

## 18. Sorting Algorithm Complexity Confusion
```
Bubble sort: O(n²) — NOT O(n log n)
Merge sort: O(n log n) — always, never O(n²)
Quick sort: O(n log n) average, O(n²) worst case
Insertion sort: O(n) BEST case (nearly sorted)
Selection sort: ALWAYS O(n²) regardless
```

## 19. Stack vs Queue Confusion
```
Stack = LIFO = Last In First Out (like plates)
Queue = FIFO = First In First Out (like a line)

Stack: push to top, pop from top
Queue: add to back, remove from front
```

---

# CSS MISTAKES

## 20. Margin vs Padding Confusion
```
MARGIN = OUTSIDE border = space between elements
PADDING = INSIDE border = space between border and content

Background color shows in PADDING (not margin)
Margin is transparent
```

## 21. CSS Specificity Wrong Order
```
WRONG assumption: "My class overrides the id because it comes after"

CORRECT: #id ALWAYS beats .class regardless of order
Specificity: ID(100) > class(10) > element(1)
Last rule wins ONLY when specificity is EQUAL
```

## 22. display: none vs visibility: hidden
```
display: none     → element is GONE, takes NO space
visibility: hidden → element is INVISIBLE but KEEPS its space
```

## 23. justify-content vs align-items
```
In flex-direction: row (default):
  justify-content → horizontal axis
  align-items → vertical axis

In flex-direction: column:
  justify-content → vertical axis
  align-items → horizontal axis
```

## 24. Box Model Width Calculation
```
Default: width = content width only
Total visual size = content + padding + border

box-sizing: border-box → width includes padding + border (recommended!)
```

---

# JAVASCRIPT MISTAKES

## 25. typeof null is "object"
```javascript
typeof null === "object"  // true — this is a bug in JS, kept for compatibility
// To check for null: use === null
if (value === null) { }
```

## 26. == vs ===
```javascript
// == does TYPE COERCION (converts types before comparing)
0 == false   // true
"" == false  // true
null == undefined  // true

// === does NOT convert types
0 === false  // false
"" === false  // false
```

## 27. sort() Without Comparator
```javascript
[10, 9, 2, 21].sort()   // [10, 2, 21, 9] WRONG! Sorted as strings
[10, 9, 2, 21].sort((a, b) => a - b)  // [2, 9, 10, 21] CORRECT
```

## 28. var Hoisting
```javascript
console.log(x);  // undefined (NOT ReferenceError for var)
var x = 5;

console.log(y);  // ReferenceError (let is in TDZ)
let y = 5;
```

## 29. const Objects Can Be Modified
```javascript
const obj = { x: 1 };
obj = { x: 2 };  // ERROR! Cannot reassign const
obj.x = 2;       // OK! Can change properties
obj.y = 3;       // OK! Can add properties
```

## 30. Array is an Object
```javascript
typeof []       // "object" (not "array"!)
typeof {}       // "object"
Array.isArray([]) // true — correct way to check
```

---

# GIT MISTAKES

## 31. Forgetting git add Before commit
```bash
# WRONG:
git commit -m "my changes"  # commits NOTHING if nothing staged

# RIGHT:
git add .
git commit -m "my changes"
```

## 32. Confusing fetch and pull
```
git fetch → downloads changes, does NOT modify your working files
git pull  → downloads AND merges into your current branch
```

## 33. Using Wrong Branch
```bash
# Before making changes, check what branch you're on:
git status   # shows current branch
git branch   # lists all branches, * = current
```

## 34. Not Writing Meaningful Commit Messages
```bash
# WRONG:
git commit -m "changes"
git commit -m "fix"
git commit -m "update"

# RIGHT:
git commit -m "Add user login form with validation"
git commit -m "Fix ArrayIndexOutOfBounds in search method"
```

## 35. Pushing to Wrong Branch
```bash
git push origin main    # pushes local commits to remote main
# Make sure you're on the right local branch first
```

---

# PATTERN MISTAKES

## 36. Wrong Inner Loop Bound
```java
// For right triangle, row i should have i stars:
for (int j = 1; j <= i; j++)    // CORRECT: i stars
for (int j = 1; j < i; j++)     // WRONG: i-1 stars
```

## 37. Printing After newline vs Before
```java
// WRONG order:
System.out.println();           // newline first
System.out.print("* ");         // then content

// RIGHT:
System.out.print("* ");         // content first
System.out.println();           // then newline
```

## 38. Floyd's Triangle Counter Reset
```java
// WRONG:
for (int i = 1; i <= n; i++) {
    int count = 1;          // resets every row!
    for (int j = 1; j <= i; j++) System.out.print(count++ + " ");
}

// RIGHT:
int count = 1;              // outside loops!
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= i; j++) System.out.print(count++ + " ");
    System.out.println();
}
```

## 39. Alphabet Pattern Cast Mistake
```java
// WRONG:
System.out.print('A' + j + " ");  // prints numbers! char + int = int

// RIGHT:
System.out.print((char)('A' + j) + " ");  // cast to char first
```

---

# EXAM TECHNIQUE MISTAKES

## 40. Not Reading the Question Carefully
- Check if they ask for index or value
- Check if output includes spaces or newlines
- Check if they say "sorted array" before using binary search
- Check base cases for recursive questions

## 41. Rushing Through Output Questions
For every output question:
1. Trace through the code manually
2. Write down variable values at each step
3. Only then write the final output

## 42. Confusing Complexity for Different Operations
```
Array[i] access: O(1)
Array traversal: O(n)
Nested loop: O(n²)
Binary search: O(log n)
Sort (comparison): O(n log n) or O(n²)
```
