# 📁 FOLDER 14 — JAVA PATTERNS 🟢 LOW PRIORITY

---

## 🧠 CONCEPT OVERVIEW

Pattern questions test your ability to work with nested loops. The trick is:
- **Outer loop** = controls rows
- **Inner loop** = controls columns (what to print per row)

**Time complexity of ALL nested-loop patterns = O(n²)** (two loops, each up to n)

---

## ❓ QUESTIONS + SOLUTIONS

---

### Pattern 1: Square of * (n=4)
```
* * * *
* * * *
* * * *
* * * *
```
```java
for (int i = 0; i < n; i++) {
  for (int j = 0; j < n; j++) System.out.print("* ");
  System.out.println();
}
```

---

### Pattern 2: Right Triangle
```
*
* *
* * *
* * * *
```
```java
for (int i = 1; i <= n; i++) {
  for (int j = 1; j <= i; j++) System.out.print("* ");
  System.out.println();
}
```

---

### Pattern 3: Inverted Triangle
```
* * * *
* * *
* *
*
```
```java
for (int i = n; i >= 1; i--) {
  for (int j = 1; j <= i; j++) System.out.print("* ");
  System.out.println();
}
```

---

### Pattern 4: Pyramid
```
   *
  * *
 * * *
* * * *
```
```java
for (int i = 1; i <= n; i++) {
  for (int s = n; s > i; s--) System.out.print(" ");  // spaces
  for (int j = 1; j <= i; j++) System.out.print("* "); // stars
  System.out.println();
}
```

---

### Pattern 5: Number Triangle
```
1
1 2
1 2 3
1 2 3 4
```
```java
for (int i = 1; i <= n; i++) {
  for (int j = 1; j <= i; j++) System.out.print(j + " ");
  System.out.println();
}
```

---

### Pattern 6: Floyd's Triangle
```
1
2 3
4 5 6
7 8 9 10
```
```java
int num = 1;
for (int i = 1; i <= n; i++) {
  for (int j = 1; j <= i; j++) System.out.print(num++ + " ");
  System.out.println();
}
```

---

### Pattern 7: Hollow Square (n=4)
```
* * * *
*     *
*     *
* * * *
```
```java
for (int i = 1; i <= n; i++) {
  for (int j = 1; j <= n; j++) {
    if (i == 1 || i == n || j == 1 || j == n) System.out.print("* ");
    else System.out.print("  ");
  }
  System.out.println();
}
```

---

### Pattern 8: Diamond (n=4)
```
   *
  * *
 * * *
* * * *
* * * *
 * * *
  * *
   *
```
```java
// Upper half (pyramid)
for (int i = 1; i <= n; i++) {
  for (int s = n; s > i; s--) System.out.print(" ");
  for (int j = 1; j <= i; j++) System.out.print("* ");
  System.out.println();
}
// Lower half (inverted pyramid)
for (int i = n; i >= 1; i--) {
  for (int s = n; s > i; s--) System.out.print(" ");
  for (int j = 1; j <= i; j++) System.out.print("* ");
  System.out.println();
}
```

---

### Pattern 9: Number increment pattern
```
1
12
123
1234
```
```java
for (int i = 1; i <= n; i++) {
  for (int j = 1; j <= i; j++) System.out.print(j);
  System.out.println();
}
```

---

## 📋 PATTERN LOGIC CHEATSHEET

| Pattern | Outer loop | Inner loop logic |
|---------|-----------|-----------------|
| Square | `i: 1 to n` | `j: 1 to n` (always n) |
| Right triangle | `i: 1 to n` | `j: 1 to i` (increases) |
| Inverted triangle | `i: n to 1` | `j: 1 to i` (decreases) |
| Pyramid | `i: 1 to n` | spaces + stars |
| Hollow square | `i, j: 1 to n` | print if border |
| Floyd's | `i: 1 to n` | counter variable |

---

## 🔑 QUICK MEMORY TRICKS

- **All patterns = O(n²)** because of nested loops
- **Number of iterations = outer iterations × inner iterations**
- Right triangle: inner loop runs `i` times → 1+2+3+...+n = n(n+1)/2 iterations total
- For pyramid: add a spaces loop before stars loop

---

## ⚠️ COMMON MISTAKES

1. Forgetting `println()` at end of outer loop (new line for each row)
2. Off-by-one: using `<` vs `<=` in loop bounds
3. Floyd's triangle: forgetting the separate `num` counter
4. Diamond: not handling the lower half separately
