# PHASE 1 MOCK EXAMINATION — TECH ROOKIE
## Time: 75 Minutes | Total Marks: 100

### INSTRUCTIONS
- Attempt ALL questions
- Do NOT look at answers until you have attempted every question
- Write your answers, then check the ANSWER KEY at the bottom
- Score yourself honestly

---

# SECTION A — JAVA (30 marks)

## Part A1: Output Prediction (2 marks each)

**JA1:** What is the output?
```java
int x = 5;
int y = x++;
System.out.println(x + " " + y);
```
Your answer: _____________

---

**JA2:** What is the output?
```java
String s1 = new String("hello");
String s2 = new String("hello");
System.out.println(s1 == s2);
System.out.println(s1.equals(s2));
```
Your answer: _____________

---

**JA3:** What is the output?
```java
int x = 3;
switch (x) {
    case 1: System.out.println("One");
    case 2: System.out.println("Two");
    case 3: System.out.println("Three");
    case 4: System.out.println("Four");
    default: System.out.println("Default");
}
```
Your answer: _____________

---

**JA4:** What is the output?
```java
class Animal {
    void speak() { System.out.println("Animal speaks"); }
}
class Cat extends Animal {
    void speak() { System.out.println("Meow"); }
}
public class Test {
    public static void main(String[] args) {
        Animal a = new Cat();
        a.speak();
    }
}
```
Your answer: _____________

---

**JA5:** What is the output?
```java
try {
    System.out.println("A");
    int x = 10 / 0;
    System.out.println("B");
} catch (ArithmeticException e) {
    System.out.println("C");
} finally {
    System.out.println("D");
}
```
Your answer: _____________

---

## Part A2: MCQ (1 mark each)

**JM1:** Which of the following is NOT a primitive data type in Java?
A) int   B) String   C) double   D) boolean

**JM2:** What does `this` keyword refer to in Java?
A) The parent class   B) The current object   C) A static member   D) The main method

**JM3:** Which access modifier makes a member visible only within the same class?
A) public   B) protected   C) default   D) private

**JM4:** What is the output of `10 / 3` in Java?
A) 3.33   B) 3   C) 3.0   D) Error

**JM5:** Which is the correct way to compare Strings in Java?
A) s1 == s2   B) s1.compare(s2)   C) s1.equals(s2)   D) s1.same(s2)

**JM6:** What happens if a child class doesn't have a constructor?
A) Error   B) Java uses parent's constructor   C) Java creates a default constructor   D) Nothing happens

**JM7:** Arrays in Java are:
A) Dynamic in size   B) Fixed in size   C) Linked to each other   D) Always sorted

**JM8:** `finally` block in Java:
A) Runs only on exceptions   B) Never runs   C) Always runs   D) Runs only when no exception

**JM9:** Method overloading means:
A) Same name, same parameters   B) Same name, different parameters   C) Different name, same parameters   D) Different everything

**JM10:** Which is correct for a 5-element int array?
A) int arr[] = new int(5)   B) int arr = new int[5]   C) int[] arr = new int[5]   D) int[] arr = int[5]

---

## Part A3: Coding (5 marks)

**JAC1:** Write a Java method that takes an integer array and returns the sum of all even numbers.

```java
// Your code here:
static int sumOfEvens(int[] arr) {
    // fill this
}
```

---

# SECTION B — PATTERN PROGRAMMING (15 marks)

**P1:** Write Java code to produce (n=4): (5 marks)
```
*
* *
* * *
* * * *
```

**P2:** What is the output of this code? (5 marks)
```java
for (int i = 1; i <= 4; i++) {
    for (int j = 4; j >= i; j--) {
        System.out.print("* ");
    }
    System.out.println();
}
```

**P3:** Write code to produce (n=4): (5 marks)
```
1
2 2
3 3 3
4 4 4 4
```

---

# SECTION C — DSA (20 marks)

## Part C1: MCQ (1 mark each)

**DM1:** What is the time complexity of binary search?
A) O(n)   B) O(log n)   C) O(n²)   D) O(1)

**DM2:** Which data structure is LIFO?
A) Queue   B) Array   C) Stack   D) Linked List

**DM3:** Bubble sort worst case:
A) O(n)   B) O(n log n)   C) O(n²)   D) O(log n)

**DM4:** Binary search requires:
A) Any array   B) Sorted array   C) Reverse sorted   D) Array with no duplicates

**DM5:** Array access by index is:
A) O(n)   B) O(log n)   C) O(1)   D) O(n²)

**DM6:** Merge sort space complexity:
A) O(1)   B) O(log n)   C) O(n)   D) O(n²)

**DM7:** Which is NOT a sorting algorithm?
A) Bubble sort   B) Binary sort   C) Selection sort   D) Insertion sort

**DM8:** Queue follows:
A) LIFO   B) FIFO   C) Random   D) Priority

**DM9:** `O(1) < O(?) < O(n) < O(n log n) < O(n²)` — what fills the blank?
A) O(2n)   B) O(n/2)   C) O(log n)   D) O(n-1)

**DM10:** Selection sort always makes how many swaps for n elements?
A) n   B) n²   C) n-1   D) n log n

## Part C2: Coding (10 marks)

**DC1:** Write Java code for linear search. Return index if found, -1 if not. (5 marks)

**DC2:** Write Java code to check if a string is a palindrome. (5 marks)

---

# SECTION D — HTML + CSS (20 marks)

## Part D1: HTML MCQ (1 mark each)

**HM1:** Which tag creates an ordered list?
A) `<ul>` B) `<ol>` C) `<list>` D) `<dl>`

**HM2:** Which attribute is required for `<img>`?
A) src   B) alt   C) href   D) Both A and B

**HM3:** Which form method sends data in URL?
A) POST   B) PUT   C) GET   D) DELETE

**HM4:** `<strong>` is different from `<b>` because:
A) Strong is bigger   B) Strong is semantic (important)   C) Strong is colored   D) No difference

**HM5:** Which is a semantic HTML5 tag?
A) `<div>` B) `<span>` C) `<nav>` D) `<br>`

## Part D2: CSS MCQ (1 mark each)

**CM1:** Which selector has highest specificity?
A) `p` B) `.class` C) `#id` D) `* `

**CM2:** The box model outer-to-inner order is:
A) content-padding-border-margin
B) margin-border-padding-content
C) padding-margin-border-content
D) border-padding-content-margin

**CM3:** `display: none` vs `visibility: hidden`:
A) Same   B) none keeps space, hidden removes element   C) none removes element, hidden keeps space   D) Both keep space

**CM4:** Flexbox `justify-content: space-between`:
A) Centers items   B) Equal gaps between items   C) Items at start   D) Items at end

**CM5:** `position: fixed` is relative to:
A) Parent element   B) Document   C) Viewport (browser window)   D) Next sibling

## Part D3: Find the Bug (5 marks each)

**HBug1:** Find all bugs in this HTML:
```html
<form method=post action="/submit">
    <input type=text name="username">
    <img href="logo.png">
    <button>Submit</form>
</button>
```

**CBug1:** Find the bug in this CSS:
```css
.container {
    display: flex;
    justify-items: center;
    align-content: middle;
}
```

---

# SECTION E — JAVASCRIPT (15 marks)

## Part E1: Output Prediction (2 marks each)

**JO1:**
```javascript
console.log(typeof null);
console.log(typeof undefined);
```

**JO2:**
```javascript
console.log(1 + "2" + 3);
console.log(1 + 2 + "3");
```

**JO3:**
```javascript
let arr = [5, 3, 1, 4, 2];
arr.sort();
console.log(arr[0]);
```

**JO4:**
```javascript
var x = 1;
function test() {
    console.log(x);
    var x = 2;
    console.log(x);
}
test();
```

**JO5:**
```javascript
const obj = { a: 1 };
obj.a = 100;
obj.b = 200;
console.log(obj.a + obj.b);
```

## Part E2: Coding (5 marks)

**EC1:** Write JavaScript to count the number of vowels in a string "Hello World".

---

# SECTION F — GIT & GITHUB (10 marks)

## Part F1: Command Questions (1 mark each)

**GQ1:** What command initializes a git repo? ___________
**GQ2:** What command stages a specific file "app.java"? ___________
**GQ3:** What command commits staged changes with message "Initial commit"? ___________
**GQ4:** What command pushes to remote? ___________
**GQ5:** What command creates a new branch "feature"? ___________
**GQ6:** What command switches to an existing branch "dev"? ___________
**GQ7:** What command downloads remote changes WITHOUT merging? ___________
**GQ8:** What is the difference between git fetch and git pull? ___________
**GQ9:** What does .gitignore do? ___________
**GQ10:** What is GitHub Pages used for? ___________

---

# ============ ANSWER KEY ============
# READ ONLY AFTER COMPLETING THE EXAM

---

## Section A — Java

### A1 Answers:
**JA1:** `6 5` — y=5 (post-increment: use then increment), x becomes 6

**JA2:** `false` then `true` — `==` compares references (different objects), `.equals()` compares content

**JA3:** `Three`, `Four`, `Default` — No break → fall-through from case 3

**JA4:** `Meow` — Runtime polymorphism: actual object is Cat

**JA5:** `A`, `C`, `D` — Exception caught → B skipped → finally always runs

### A2 Answers:
| Q | A | Reason |
|---|---|--------|
| JM1 | B | String is a class, not primitive |
| JM2 | B | this = current object |
| JM3 | D | private = only within same class |
| JM4 | B | Integer division: 10/3 = 3 |
| JM5 | C | Always use .equals() for String comparison |
| JM6 | C | Java provides default (no-arg) constructor automatically |
| JM7 | B | Arrays are fixed size |
| JM8 | C | finally always runs |
| JM9 | B | Overloading = same name, different parameters |
| JM10 | C | Correct Java array declaration syntax |

### A3 Coding Solution:
```java
static int sumOfEvens(int[] arr) {
    int sum = 0;
    for (int x : arr) {
        if (x % 2 == 0) sum += x;
    }
    return sum;
}
```

---

## Section B — Patterns

**P1:**
```java
int n = 4;
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print("* ");
    }
    System.out.println();
}
```

**P2 Output:**
```
* * * *
* * *
* *
*
```
(j starts at 4, goes down to i — inverted triangle)

**P3:**
```java
for (int i = 1; i <= 4; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print(i + " ");
    }
    System.out.println();
}
```

---

## Section C — DSA

### C1 Answers:
DM1:B, DM2:C, DM3:C, DM4:B, DM5:C, DM6:C, DM7:B, DM8:B, DM9:C, DM10:C

### C2 Solutions:
```java
// Linear Search
static int linearSearch(int[] arr, int target) {
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == target) return i;
    }
    return -1;
}

// Palindrome
static boolean isPalindrome(String s) {
    int left = 0, right = s.length() - 1;
    while (left < right) {
        if (s.charAt(left) != s.charAt(right)) return false;
        left++;
        right--;
    }
    return true;
}
```

---

## Section D — HTML + CSS

### D1 Answers: HM1:B, HM2:D, HM3:C, HM4:B, HM5:C
### D2 Answers: CM1:C, CM2:B, CM3:C, CM4:B, CM5:C

### HBug1 Bugs:
1. `method=post` → `method="post"` (values need quotes)
2. `type=text` → `type="text"` (values need quotes)
3. `href="logo.png"` → `src="logo.png"` (img uses src not href)
4. `<button>Submit</form></button>` → `<button type="submit">Submit</button>` (mismatched tags)

### CBug1 Bugs:
1. `justify-items: center` → `justify-content: center` (wrong property in flexbox)
2. `align-content: middle` → `align-items: center` ("middle" is not a valid value)

---

## Section E — JavaScript

### E1 Answers:

**JO1:** `"object"`, `"undefined"` — typeof null is "object" (famous bug)

**JO2:** `"123"`, `"33"`
- 1 + "2" = "12", "12" + 3 = "123"
- 1 + 2 = 3, 3 + "3" = "33"

**JO3:** First element is `1` — `sort()` without comparator sorts as strings: "1","2","3","4","5" → sorted, arr[0]=1

**JO4:** `undefined`, `2` — var inside function is hoisted to top of function; console.log sees hoisted-but-uninitialized x (undefined), then x=2

**JO5:** `300` — const obj itself can't be reassigned, but properties can; a=100, b=200, 100+200=300

### E2 Coding:
```javascript
function countVowels(str) {
    let count = 0;
    for (let char of str.toLowerCase()) {
        if ("aeiou".includes(char)) count++;
    }
    return count;
}
console.log(countVowels("Hello World")); // 3 (e, o, o)
```

---

## Section F — Git

**GQ1:** `git init`
**GQ2:** `git add app.java`
**GQ3:** `git commit -m "Initial commit"`
**GQ4:** `git push` or `git push origin main`
**GQ5:** `git branch feature`
**GQ6:** `git switch dev` or `git checkout dev`
**GQ7:** `git fetch`
**GQ8:** fetch downloads without merging; pull = fetch + merge
**GQ9:** Tells Git which files/folders to not track (ignore)
**GQ10:** Hosting static websites for free from a GitHub repo

---

# SCORING

| Section | Max Marks | Your Score |
|---------|-----------|------------|
| A: Java Output | 10 | /10 |
| A: Java MCQ | 10 | /10 |
| A: Java Coding | 5 | /5 |
| B: Patterns | 15 | /15 |
| C: DSA MCQ | 10 | /10 |
| C: DSA Coding | 10 | /10 |
| D: HTML MCQ | 5 | /5 |
| D: CSS MCQ | 5 | /5 |
| D: Bug Finding | 10 | /10 |
| E: JS Output | 10 | /10 |
| E: JS Coding | 5 | /5 |
| F: Git | 10 | /10 |
| **TOTAL** | **100** | **/100** |

**Score Interpretation:**
- 85–100: Excellent! Ready for exam.
- 70–84: Good, revise weak sections.
- 55–69: Need focused revision tonight.
- Below 55: Go back to fundamentals in weak areas.
