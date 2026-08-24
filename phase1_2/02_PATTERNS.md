# PATTERN PROGRAMMING — COMPLETE GUIDE
## Tech Passport Phase 1

---

# THE GOLDEN RULE FOR ALL PATTERNS

Before writing any pattern, ask yourself:
1. How many ROWS does it have? (outer loop)
2. How many columns per row? (inner loop)
3. What is printed at each position? (star/number/space/letter)

**Template for every pattern:**
```java
for (int i = 1; i <= rows; i++) {       // outer = rows
    for (int j = 1; j <= ???; j++) {    // inner = columns
        System.out.print(???);           // what to print
    }
    System.out.println();               // newline after each row
}
```

---

# PATTERN 1 — Right Triangle (Stars)

```
*
* *
* * *
* * * *
* * * * *
```

**Logic:** Row i has i stars.

```java
int n = 5;
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print("* ");
    }
    System.out.println();
}
```

---

# PATTERN 2 — Inverted Right Triangle

```
* * * * *
* * * *
* * *
* *
*
```

**Logic:** Row i has (n - i + 1) stars.

```java
int n = 5;
for (int i = n; i >= 1; i--) {
    for (int j = 1; j <= i; j++) {
        System.out.print("* ");
    }
    System.out.println();
}
```

---

# PATTERN 3 — Pyramid (Centered)

```
    *
   * *
  * * *
 * * * *
* * * * *
```

**Logic:** Row i has (n-i) spaces then i stars.

```java
int n = 5;
for (int i = 1; i <= n; i++) {
    // Print spaces
    for (int j = 1; j <= n - i; j++) {
        System.out.print(" ");
    }
    // Print stars
    for (int j = 1; j <= i; j++) {
        System.out.print("* ");
    }
    System.out.println();
}
```

---

# PATTERN 4 — Inverted Pyramid

```
* * * * *
 * * * *
  * * *
   * *
    *
```

**Logic:** Row i has (i-1) spaces then (n-i+1) stars.

```java
int n = 5;
for (int i = 1; i <= n; i++) {
    for (int j = 1; j < i; j++) {
        System.out.print(" ");
    }
    for (int j = i; j <= n; j++) {
        System.out.print("* ");
    }
    System.out.println();
}
```

---

# PATTERN 5 — Diamond

```
    *
   * *
  * * *
 * * * *
* * * * *
 * * * *
  * * *
   * *
    *
```

**Logic:** Top half = pyramid (n rows), bottom half = inverted pyramid (n-1 rows).

```java
int n = 5;
// Top half
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= n - i; j++) System.out.print(" ");
    for (int j = 1; j <= i; j++) System.out.print("* ");
    System.out.println();
}
// Bottom half
for (int i = n - 1; i >= 1; i--) {
    for (int j = 1; j <= n - i; j++) System.out.print(" ");
    for (int j = 1; j <= i; j++) System.out.print("* ");
    System.out.println();
}
```

---

# PATTERN 6 — Number Triangle

```
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```

**Logic:** Row i prints numbers 1 to i.

```java
int n = 5;
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print(j + " ");
    }
    System.out.println();
}
```

---

# PATTERN 7 — Same Number Per Row

```
1
2 2
3 3 3
4 4 4 4
5 5 5 5 5
```

**Logic:** Row i prints the number i, i times.

```java
int n = 5;
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print(i + " ");
    }
    System.out.println();
}
```

---

# PATTERN 8 — Floyd's Triangle

```
1
2 3
4 5 6
7 8 9 10
```

**Logic:** Keep a running counter that never resets.

```java
int n = 4;
int count = 1;
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print(count + " ");
        count++;
    }
    System.out.println();
}
```

---

# PATTERN 9 — Alphabet Triangle

```
A
A B
A B C
A B C D
A B C D E
```

**Logic:** Row i prints letters A to (A + i - 1).

```java
int n = 5;
for (int i = 0; i < n; i++) {
    for (int j = 0; j <= i; j++) {
        System.out.print((char)('A' + j) + " ");
    }
    System.out.println();
}
```

---

# PATTERN 10 — Hollow Rectangle

```
* * * * *
*       *
*       *
* * * * *
```

**Logic:** Print * at first/last row OR first/last column, else space.

```java
int rows = 4, cols = 5;
for (int i = 1; i <= rows; i++) {
    for (int j = 1; j <= cols; j++) {
        if (i == 1 || i == rows || j == 1 || j == cols) {
            System.out.print("* ");
        } else {
            System.out.print("  ");
        }
    }
    System.out.println();
}
```

---

# PATTERN 11 — Number Pyramid

```
    1
   2 3
  4 5 6
 7 8 9 10
```

**Logic:** Combination of Floyd's triangle + pyramid spacing.

```java
int n = 4, count = 1;
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= n - i; j++) System.out.print(" ");
    for (int j = 1; j <= i; j++) {
        System.out.print(count + " ");
        count++;
    }
    System.out.println();
}
```

---

# PATTERN 12 — Inverted Number Triangle

```
1 2 3 4 5
1 2 3 4
1 2 3
1 2
1
```

```java
int n = 5;
for (int i = n; i >= 1; i--) {
    for (int j = 1; j <= i; j++) {
        System.out.print(j + " ");
    }
    System.out.println();
}
```

---

# PATTERN 13 — Zigzag / Descending Triangle

```
5 4 3 2 1
4 3 2 1
3 2 1
2 1
1
```

```java
int n = 5;
for (int i = n; i >= 1; i--) {
    for (int j = i; j >= 1; j--) {
        System.out.print(j + " ");
    }
    System.out.println();
}
```

---

# PATTERN 14 — Hollow Triangle

```
*
* *
*   *
*     *
* * * * *
```

**Logic:** Print * at first/last column of each row, OR at last row.

```java
int n = 5;
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= i; j++) {
        if (j == 1 || j == i || i == n) {
            System.out.print("* ");
        } else {
            System.out.print("  ");
        }
    }
    System.out.println();
}
```

---

# THE UNIVERSAL PATTERN-SOLVING TECHNIQUE

When you see any pattern in the exam, follow these 5 steps:

## Step 1: Count the rows
How many lines are there? That is your outer loop.
`for (int i = 1; i <= rows; i++)`

## Step 2: Analyze each row
What is on each row? Write it as a function of i.
- Row 1: 1 star → j goes 1 to 1
- Row 2: 2 stars → j goes 1 to 2
- Row i: i stars → j goes 1 to i

## Step 3: Identify leading spaces
Are there spaces before the content?
- Row 1: 4 spaces, Row 2: 3 spaces → spaces = n - i

## Step 4: Identify what to print
- Is it *? → `System.out.print("* ")`
- Is it the column number? → `System.out.print(j + " ")`
- Is it the row number? → `System.out.print(i + " ")`
- Is it a running counter? → separate counter variable

## Step 5: Write and test mentally
Trace through with rows=3 before finalizing.

---

# PATTERN QUICK REFERENCE TABLE

| Pattern | Outer Loop | Inner Loop (stars) | Inner Loop (spaces) | Print |
|---------|-----------|-------------------|---------------------|-------|
| Right Triangle | i: 1 to n | j: 1 to i | none | * |
| Inverted Triangle | i: n to 1 | j: 1 to i | none | * |
| Pyramid | i: 1 to n | j: 1 to i | j: 1 to n-i | spaces then * |
| Diamond | two halves | varies | varies | * |
| Number Triangle | i: 1 to n | j: 1 to i | none | j |
| Floyd's | i: 1 to n | j: 1 to i | none | counter++ |
| Alphabet | i: 0 to n-1 | j: 0 to i | none | 'A'+j |
| Hollow Rect | i: 1 to rows | j: 1 to cols | none | condition |

---

# EXAM-LEVEL PATTERN QUESTIONS

**Q1:** What is the output of this code?
```java
for (int i = 3; i >= 1; i--) {
    for (int j = 1; j <= i; j++) {
        System.out.print(j);
    }
    System.out.println();
}
```
**Answer:**
```
123
12
1
```

**Q2:** Write code to produce:
```
*****
****
***
**
*
```
**Answer:** Outer: i from 5 to 1 (decreasing). Inner: j from 1 to i.

**Q3:** Write code to produce:
```
1
22
333
4444
```
**Answer:** Outer: i from 1 to 4. Inner: j from 1 to i, print i each time.

**Q4 (Hollow Diamond — Hard):**
```
  *
 * *
*   *
 * *
  *
```
**Answer:** Requires careful space + star condition in both halves.

---

# COMMON PATTERN MISTAKES

1. **Off-by-one**: `j <= i` vs `j < i` changes the count by 1
2. **Space vs no space**: `"* "` vs `"*"` changes alignment
3. **Wrong loop direction**: Forgetting when to use `i--` vs `i++`
4. **Running counter in wrong place**: For Floyd's, counter must be outside outer loop
5. **Alphabet cast**: Must cast to `char` — `(char)('A' + j)`
