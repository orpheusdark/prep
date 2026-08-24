# MOST LIKELY QUESTIONS TOMORROW
## 100+ High-Probability Questions

### Probability Legend:
- 🔥🔥🔥 Very High Probability
- 🔥🔥 High Probability
- 🔥 Medium Probability

---

# JAVA QUESTIONS (35 Questions)

## Output Prediction

**J1** 🔥🔥🔥 What is the output?
```java
int x = 5;
System.out.println(x++);
System.out.println(++x);
```
**Answer:** 5, 7 (post: print 5 then x=6; pre: x=7 then print 7)

**Why likely:** Pre/post increment is THE most classic Java output trap.

---

**J2** 🔥🔥🔥 What is the output?
```java
String a = "Java";
String b = "Java";
String c = new String("Java");
System.out.println(a == b);
System.out.println(a == c);
System.out.println(a.equals(c));
```
**Answer:** true, false, true
**Why likely:** String pool vs heap is tested in every Java exam.

---

**J3** 🔥🔥🔥 What is the output?
```java
class Animal {
    void eat() { System.out.println("Animal eating"); }
}
class Dog extends Animal {
    void eat() { System.out.println("Dog eating"); }
}
Animal a = new Dog();
a.eat();
```
**Answer:** Dog eating
**Why likely:** Runtime polymorphism is THE core OOP concept for exams.

---

**J4** 🔥🔥🔥 What is the output?
```java
int x = 2;
switch(x) {
    case 1: System.out.println("One");
    case 2: System.out.println("Two");
    case 3: System.out.println("Three");
    default: System.out.println("Default");
}
```
**Answer:** Two, Three, Default (fall-through — no break!)

---

**J5** 🔥🔥🔥 What is the output?
```java
try {
    System.out.println("try");
    if (true) throw new RuntimeException();
    System.out.println("try end");
} catch (Exception e) {
    System.out.println("catch");
} finally {
    System.out.println("finally");
}
```
**Answer:** try, catch, finally

---

**J6** 🔥🔥🔥 What is output?
```java
class A {
    A() { System.out.print("A "); }
}
class B extends A {
    B() { System.out.print("B "); }
}
new B();
```
**Answer:** A B (parent constructor called first)

---

**J7** 🔥🔥 What is the output?
```java
String s = "Hello World";
s.toUpperCase();
System.out.println(s);
```
**Answer:** Hello World (Strings are immutable — must reassign)

---

**J8** 🔥🔥 What is the output?
```java
int[] arr = new int[5];
System.out.println(arr[0]);
```
**Answer:** 0 (default value for int array)

---

**J9** 🔥🔥 Output?
```java
int a = 10, b = 3;
System.out.println(a / b);
System.out.println(a % b);
```
**Answer:** 3, 1

---

**J10** 🔥🔥 Output?
```java
static int sum(int n) {
    if (n == 0) return 0;
    return n + sum(n - 1);
}
System.out.println(sum(5));
```
**Answer:** 15 (5+4+3+2+1+0)

---

## Java MCQs

**J11** 🔥🔥🔥 Which is NOT a primitive type?
A) int B) String C) boolean D) char
**Answer: B**

**J12** 🔥🔥🔥 `finally` block runs:
A) Only on exception B) Never C) Always D) Only when no exception
**Answer: C**

**J13** 🔥🔥🔥 `==` vs `.equals()` for String:
A) Same B) == checks content, equals checks reference C) equals checks content, == checks reference D) Neither works
**Answer: C**

**J14** 🔥🔥🔥 Method overriding requires:
A) Same name, different params B) Same name, same params, child class C) Different name, same params D) Different everything
**Answer: B**

**J15** 🔥🔥🔥 `super()` in child constructor must be:
A) Last statement B) Anywhere C) First statement D) Not needed
**Answer: C**

**J16** 🔥🔥 `static` methods cannot use:
A) Parameters B) return C) this keyword D) Other static methods
**Answer: C**

**J17** 🔥🔥 Abstract class vs Interface:
A) Both can be instantiated B) Abstract can have constructors; interface cannot C) Interface can have constructors D) No difference
**Answer: B**

**J18** 🔥🔥 Array `arr.length` gives:
A) Method that returns length B) Property (field) C) Error D) Number of dimensions
**Answer: B** (no parentheses!)

**J19** 🔥🔥 Which exception is thrown by `arr[-1]`?
A) NullPointerException B) IllegalArgumentException C) ArrayIndexOutOfBoundsException D) ArithmeticException
**Answer: C**

**J20** 🔥🔥 `int x = (int) 9.9;` gives:
A) 10 B) 9 C) 9.9 D) Error
**Answer: B** (truncates, doesn't round)

---

## Java Coding

**J21** 🔥🔥🔥 Write a method to find if a number is prime.
**J22** 🔥🔥🔥 Write a method to reverse a string.
**J23** 🔥🔥🔥 Write a method to check palindrome.
**J24** 🔥🔥🔥 Write factorial using recursion.
**J25** 🔥🔥 Write a class Student with name, grade, and method to check if passed.

---

# DSA QUESTIONS (20 Questions)

**D1** 🔥🔥🔥 Time complexity of binary search?
**Answer:** O(log n)

**D2** 🔥🔥🔥 Binary search requires array to be?
**Answer:** Sorted

**D3** 🔥🔥🔥 Bubble sort worst case?
**Answer:** O(n²)

**D4** 🔥🔥🔥 Which is LIFO?
**Answer:** Stack

**D5** 🔥🔥🔥 Which is FIFO?
**Answer:** Queue

**D6** 🔥🔥🔥 Array element access by index?
**Answer:** O(1)

**D7** 🔥🔥🔥 Arrange: O(1), O(n), O(log n), O(n²), O(n log n)
**Answer:** O(1) < O(log n) < O(n) < O(n log n) < O(n²)

**D8** 🔥🔥 Space complexity of merge sort?
**Answer:** O(n)

**D9** 🔥🔥 Space complexity of bubble sort?
**Answer:** O(1)

**D10** 🔥🔥 Insertion sort best case?
**Answer:** O(n) (nearly sorted array)

**D11** 🔥🔥🔥 What does push() do on a Stack?
**Answer:** Adds element to top

**D12** 🔥🔥🔥 What does dequeue() do on a Queue?
**Answer:** Removes element from front

**D13** 🔥🔥 Output: `Stack s; s.push(1); s.push(2); s.push(3); s.pop(); s.peek();`
**Answer:** pop returns 3; peek shows 2 (top)

**D14** 🔥🔥 How many comparisons does binary search make for n=8 worst case?
**Answer:** log₂8 = 3 comparisons

**D15** 🔥🔥 What is the most common algorithm for finding an element without sorting?
**Answer:** Linear search

**D16** 🔥🔥 Write linear search in Java.

**D17** 🔥🔥 Write bubble sort in Java.

**D18** 🔥🔥 Write code to find maximum in array.

**D19** 🔥🔥 What is the output of ONE pass of bubble sort on {5,3,1,4,2}?
**Answer:** {3,1,4,2,5} — 5 bubbles to end

**D20** 🔥 Selection sort always makes exactly n-1 swaps. True or False?
**Answer:** True

---

# PATTERN QUESTIONS (10 Questions)

**P1** 🔥🔥🔥 What is the output?
```java
for(int i=1;i<=4;i++){
    for(int j=1;j<=i;j++) System.out.print("*");
    System.out.println();
}
```
**Answer:** *, **, ***, ****

**P2** 🔥🔥🔥 Write code to print this (n=5):
```
*****
****
***
**
*
```
**Answer:** outer i from 5 to 1, inner j from 1 to i

**P3** 🔥🔥🔥 What does this produce?
```java
for(int i=1;i<=4;i++){
    for(int j=1;j<=i;j++) System.out.print(j+" ");
    System.out.println();
}
```
**Answer:** 1 / 1 2 / 1 2 3 / 1 2 3 4

**P4** 🔥🔥🔥 Write code for pyramid (centered stars, n=4)
**Answer:** Spaces + stars pattern

**P5** 🔥🔥 Write code for Floyd's triangle (4 rows)
**Answer:** Running counter, print then increment

**P6** 🔥🔥 Write code for same number in each row:
```
1
22
333
```
**Answer:** Outer i; inner j<=i; print i

**P7** 🔥🔥 Write alphabet triangle:
```
A
AB
ABC
```
**Answer:** (char)('A'+j) for j from 0 to i

**P8** 🔥 What is output?
```java
int count=1;
for(int i=1;i<=3;i++)
    for(int j=1;j<=i;j++)
        System.out.print(count+++" ");
```
**Answer:** 1 / 2 3 / 4 5 6 (Floyd's triangle numbers)

**P9** 🔥 Write hollow rectangle (4×5)
**Answer:** print * when i==1||i==rows||j==1||j==cols

**P10** 🔥 What is the inner loop range for inverted triangle row i (n=5)?
**Answer:** j goes from 1 to (n - i + 1)

---

# HTML QUESTIONS (10 Questions)

**H1** 🔥🔥🔥 What does `<!DOCTYPE html>` declare?
**Answer:** HTML5 document

**H2** 🔥🔥🔥 Which tag is the MOST important heading?
**Answer:** `<h1>` (only one per page)

**H3** 🔥🔥🔥 What does `alt` in `<img>` do?
**Answer:** Describes image for accessibility/screen readers

**H4** 🔥🔥🔥 `method="GET"` vs `method="POST"` in forms?
**Answer:** GET puts data in URL; POST sends in request body

**H5** 🔥🔥🔥 Which is semantic HTML?
`<div>`, `<span>`, `<article>`, `<b>` — Answer: `<article>`

**H6** 🔥🔥 Difference between `<ul>` and `<ol>`:
**Answer:** ul = unordered (bullets); ol = ordered (numbered)

**H7** 🔥🔥 What is `target="_blank"` in `<a>` tag?
**Answer:** Opens link in new tab

**H8** 🔥🔥 `<th>` vs `<td>` in tables?
**Answer:** th = header (bold, centered), td = data cell

**H9** 🔥🔥 What attribute links a `<label>` to an `<input>`?
**Answer:** `for` in label, `id` in input — must match

**H10** 🔥 What is the difference between `<strong>` and `<b>`?
**Answer:** strong = semantic importance; b = just visual bold

---

# CSS QUESTIONS (10 Questions)

**C1** 🔥🔥🔥 Specificity order (highest to lowest)?
**Answer:** inline > #id > .class > element

**C2** 🔥🔥🔥 Box model layers (outside to inside)?
**Answer:** margin → border → padding → content

**C3** 🔥🔥🔥 `display: none` vs `visibility: hidden`?
**Answer:** none removes element and space; hidden hides but keeps space

**C4** 🔥🔥🔥 `justify-content` vs `align-items` in flexbox?
**Answer:** justify-content = main axis (horizontal in row); align-items = cross axis (vertical in row)

**C5** 🔥🔥🔥 Which selector wins: `#box` or `.box`?
**Answer:** `#box` (ID has higher specificity)

**C6** 🔥🔥 `position: absolute` is positioned relative to?
**Answer:** Nearest ancestor with position other than static

**C7** 🔥🔥 `position: fixed` stays relative to?
**Answer:** Viewport (stays in place while scrolling)

**C8** 🔥🔥 `box-sizing: border-box` means?
**Answer:** width includes padding + border

**C9** 🔥🔥 Flexbox shorthand for align on both axes to center?
**Answer:** `justify-content: center; align-items: center;`

**C10** 🔥 `em` vs `rem`:
**Answer:** em = relative to parent; rem = relative to root (html)

---

# JAVASCRIPT QUESTIONS (10 Questions)

**JS1** 🔥🔥🔥 `typeof null`?
**Answer:** "object" (famous JS bug)

**JS2** 🔥🔥🔥 `0 == false` vs `0 === false`?
**Answer:** true vs false

**JS3** 🔥🔥🔥 `var` vs `let` — hoisting behavior?
**Answer:** var is hoisted (undefined); let is hoisted but in TDZ (ReferenceError if accessed early)

**JS4** 🔥🔥🔥 `"5" + 3 = ?` and `"5" - 3 = ?`
**Answer:** "53" (string concat) and 2 (numeric subtraction)

**JS5** 🔥🔥🔥 `[10,9,2].sort()` output?
**Answer:** [10,2,9] — sorts as strings!

**JS6** 🔥🔥 Truthy or falsy: `[]`, `""`, `0`, `"0"`, `null`?
**Answer:** truthy, falsy, falsy, truthy, falsy

**JS7** 🔥🔥 What does `arr.map(x => x*2)` do?
**Answer:** Returns a NEW array with each element doubled; original unchanged

**JS8** 🔥🔥 `arr.filter(x => x > 3)` on [1,2,3,4,5]?
**Answer:** [4,5]

**JS9** 🔥🔥 `const obj = {x:1}; obj.x = 2;` — error?
**Answer:** No error! const prevents reassigning obj, not changing its properties

**JS10** 🔥 `typeof []`?
**Answer:** "object" (arrays are objects; use Array.isArray())

---

# GIT/GITHUB QUESTIONS (10 Questions)

**G1** 🔥🔥🔥 Initialize a new repo?
**Answer:** `git init`

**G2** 🔥🔥🔥 Stage ALL files?
**Answer:** `git add .`

**G3** 🔥🔥🔥 Commit with message?
**Answer:** `git commit -m "message"`

**G4** 🔥🔥🔥 Push to remote?
**Answer:** `git push` or `git push origin main`

**G5** 🔥🔥🔥 `git fetch` vs `git pull`?
**Answer:** fetch downloads without merging; pull = fetch + merge

**G6** 🔥🔥🔥 Create new branch "feature"?
**Answer:** `git branch feature`

**G7** 🔥🔥🔥 Create AND switch in one command?
**Answer:** `git checkout -b feature` or `git switch -c feature`

**G8** 🔥🔥 What is origin?
**Answer:** Default name for the main remote repository

**G9** 🔥🔥 What is a merge conflict?
**Answer:** When two branches modify the same lines of the same file

**G10** 🔥🔥 What is GitHub Pages?
**Answer:** Free static website hosting from a GitHub repository

---

# OUTPUT PREDICTION (10 Extra)

**O1** 🔥🔥🔥
```java
int i = 0;
do {
    System.out.print(i + " ");
    i++;
} while(i < 0);
```
**Answer:** 0 (do-while runs body at least once even if condition false)

**O2** 🔥🔥🔥
```javascript
console.log(1 + 2 + "3");
console.log("1" + 2 + 3);
```
**Answer:** "33", "123"

**O3** 🔥🔥🔥
```java
String s = "Hello";
System.out.println(s.substring(1, 3));
```
**Answer:** "el" (index 1 to 2, end exclusive)

**O4** 🔥🔥
```java
int[] arr = {1,2,3};
System.out.println(arr.length);
```
**Answer:** 3 (NOT arr.length() — no parentheses!)

**O5** 🔥🔥
```java
for(int i=0; i<5; i++) {
    if(i == 3) break;
    System.out.print(i + " ");
}
```
**Answer:** 0 1 2

**O6** 🔥🔥
```java
for(int i=0; i<5; i++) {
    if(i % 2 == 0) continue;
    System.out.print(i + " ");
}
```
**Answer:** 1 3

**O7** 🔥🔥
```javascript
let x = 5;
let y = x;
y = 10;
console.log(x);
```
**Answer:** 5 (primitives are copied by value)

**O8** 🔥🔥
```java
System.out.println("abc".charAt(1));
System.out.println("abc".indexOf('c'));
```
**Answer:** b, 2

**O9** 🔥🔥
```java
int x = 10;
int y = x++ + ++x;
System.out.println(y);
```
**Answer:** 22 (x++ gives 10, x=11; ++x=12; 10+12=22)

**O10** 🔥
```javascript
const arr = [1, 2, 3];
arr.push(4);
console.log(arr.length);
```
**Answer:** 4

---

# DEBUGGING QUESTIONS (10 Questions)

**BUG1** 🔥🔥🔥 Find bug:
```java
String s = "Hello";
if (s == "Hello") System.out.println("Match");
```
**Bug:** Use `s.equals("Hello")` not `==`

**BUG2** 🔥🔥🔥 Find bug:
```java
int[] arr = {1,2,3,4,5};
for(int i = 0; i <= arr.length; i++) {
    System.out.println(arr[i]);
}
```
**Bug:** `i <= arr.length` should be `i < arr.length` (causes ArrayIndexOutOfBoundsException)

**BUG3** 🔥🔥🔥 Find bug:
```java
double d = 10 / 3;
System.out.println(d);
```
**Bug:** 10/3 is integer division (=3), then assigned to double (3.0). Should be `10.0/3` or `(double)10/3`

**BUG4** 🔥🔥 Find bug:
```java
class Dog extends Animal {
    Dog() {
        System.out.println("Dog");
        super();   // Bug!
    }
}
```
**Bug:** `super()` must be FIRST statement in constructor

**BUG5** 🔥🔥 Find bug:
```javascript
const arr = [5, 3, 1, 4, 2];
arr.sort();
console.log(arr[0]);  // Expects 1
```
**Bug:** `arr.sort()` sorts as strings → "1","2","3","4","5" happens to be correct for single digits, but for multi-digit: `[10,9,2].sort()` → `[10,2,9]`. Must use `arr.sort((a,b) => a-b)`.

**BUG6** 🔥🔥 Find bug in CSS:
```css
.flex-container {
    display: flex;
    justify-items: center;
}
```
**Bug:** `justify-items` is for grid, not flexbox. Use `justify-content: center`.

**BUG7** 🔥🔥 Find bug:
```java
static int factorial(int n) {
    return n * factorial(n - 1);  // Bug!
}
```
**Bug:** No base case → infinite recursion → StackOverflowError. Add: `if(n<=1) return 1;`

**BUG8** 🔥 Find bug:
```html
<img src="photo.jpg">
```
**Bug:** Missing `alt` attribute (required for accessibility)

**BUG9** 🔥 Find bug:
```java
int max = 0;  // Bug for negative arrays
for(int x : arr) {
    if(x > max) max = x;
}
```
**Bug:** Initializing max=0 fails if all elements are negative. Use `max = arr[0]` or `Integer.MIN_VALUE`.

**BUG10** 🔥 Find bug:
```java
String s = "hello";
s[0] = 'H';  // Bug
```
**Bug:** Strings are immutable in Java; cannot change characters. Use StringBuilder or reassign.

---

# CODING PROBLEMS (10 Questions)

**CP1** 🔥🔥🔥 Write Java code to print Fibonacci series up to n terms.

**CP2** 🔥🔥🔥 Write Java code to check if a number is prime.

**CP3** 🔥🔥🔥 Write Java code to reverse an array.

**CP4** 🔥🔥🔥 Write Java code to find max and min in array.

**CP5** 🔥🔥🔥 Write Java code to count frequency of each element in array.

**CP6** 🔥🔥 Write Java code to remove duplicates from an array (print unique elements).

**CP7** 🔥🔥 Write a Java class with inheritance: Animal → Dog with overridden speak() method.

**CP8** 🔥🔥 Write Java code to count vowels in a given string.

**CP9** 🔥🔥 Write JavaScript to find the largest number in an array.

**CP10** 🔥 Write a Java program with try-catch-finally that handles division by zero.
