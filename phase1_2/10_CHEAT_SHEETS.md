# RAPID REVISION CHEAT SHEETS
## For Last-Minute Study Before the Exam

---

# JAVA CHEAT SHEET

## Data Types
```
byte(1B) < short(2B) < int(4B) < long(8B) < float(4B) < double(8B)
char(2B)  boolean(1bit)
Default values in arrays: int→0, double→0.0, boolean→false, String→null
```

## Operators Trap
```
10 / 3 = 3      (integer division, not 3.33!)
10 % 3 = 1      (remainder)
x++             (use x, then increment)
++x             (increment, then use)
(int) 9.9 = 9  (truncates, NOT rounds)
```

## String — CRITICAL
```java
s.equals(s2)       // compare content
s.length()         // length WITH ()
s.charAt(i)        // char at index i
s.substring(s,e)   // s to e-1 (END IS EXCLUSIVE)
s.indexOf('c')     // first occurrence
s.toUpperCase()    // returns NEW string (original unchanged!)
s.trim()           // removes spaces
s.split(" ")       // splits into array
```

## Array — CRITICAL
```java
arr.length          // NO parentheses (it's a field!)
arr[arr.length-1]   // last element
int[] arr = new int[5]; // default: all 0
Arrays.sort(arr)    // sorts in place
Arrays.toString(arr)// prints array as string
```

## Control Flow Traps
```
switch without break → falls through to next case!
do-while → runs body at least ONCE
```

## OOP Quick Reference
```
Overloading:  same class, same name, DIFFERENT params → compile time
Overriding:   child class, same name, SAME params → runtime (polymorphism)

Animal a = new Dog() → a.sound() calls DOG's sound (runtime polymorphism)
Fields are NOT polymorphic → a.field uses Animal's field

super() → must be FIRST statement in child constructor
this → current object; static methods CANNOT use this

abstract class → extends, has constructors, can have fields
interface → implements, no constructors, can implement multiple
```

## Exception Handling
```
finally ALWAYS runs (even after return!)
throw → throw new Exception("msg")
throws → declares method may throw

Common exceptions:
ArithmeticException     (divide by 0)
NullPointerException    (using null)
ArrayIndexOutOfBounds   (bad index)
NumberFormatException   (parseInt("abc"))
StackOverflowError      (infinite recursion)
```

## Access Modifiers
```
private < default < protected < public
private  = only same class
default  = same package
protected = package + subclasses
public   = everywhere
```

---

# DSA CHEAT SHEET

## Complexity Quick Reference
```
O(1)          Array index access, push/pop stack
O(log n)      Binary search, divide-and-conquer
O(n)          Linear search, single loop
O(n log n)    Merge sort, quick sort (avg)
O(n²)         Bubble/selection sort, nested loops
```

## Sorting Summary
```
Bubble Sort:
- Compare adjacent, swap if wrong
- Outer: n-1 passes, Inner: n-1-i
- Worst/Avg: O(n²), Best: O(n), Space: O(1)

Selection Sort:
- Find min, swap to current position
- Always O(n²), always n-1 swaps, Space: O(1)

Insertion Sort:
- Take element, insert into correct position
- Best: O(n) (nearly sorted), Worst: O(n²), Space: O(1)

Merge Sort:
- Divide, sort halves, merge
- Always O(n log n), Space: O(n)

Quick Sort:
- Pick pivot, partition
- Avg: O(n log n), Worst: O(n²) (sorted array with bad pivot)
```

## Search Summary
```
Linear Search:
- Check each element
- Time: O(n), Space: O(1)
- Works on ANY array

Binary Search:
- Compare mid, halve search space
- Time: O(log n), Space: O(1)
- REQUIRES SORTED array!
- mid = low + (high - low) / 2  [prevent overflow]
```

## Stack (LIFO) vs Queue (FIFO)
```
Stack: push (add top), pop (remove top), peek (view top)
Queue: enqueue/add (add back), dequeue/remove (remove front), peek (view front)

Stack apps: undo, browser back, function calls, brackets
Queue apps: scheduling, BFS, print queue
```

## Two-Pointer (Phase 2)
```
For sorted array: find pair with sum
left = 0, right = n-1
if arr[left]+arr[right] == target → found
if sum < target → left++
if sum > target → right--
Time: O(n), Space: O(1)
```

---

# JAVASCRIPT CHEAT SHEET

## var vs let vs const
```
var:   function scope, hoisted (undefined), can redeclare
let:   block scope, hoisted (TDZ error), cannot redeclare
const: block scope, hoisted (TDZ error), cannot reassign
```

## Type Coercion Traps
```
"5" + 3 = "53"      (string concat!)
"5" - 3 = 2         (numeric!)
0 == false = true   (coercion)
0 === false = false  (strict, no coercion)
null == undefined = true
null === undefined = false
typeof null = "object"  (bug!)
typeof [] = "object"    (arrays are objects)
```

## Truthy / Falsy
```
FALSY: false, 0, "", null, undefined, NaN
TRUTHY: everything else ([], {}, "0", -1, "false")
```

## Array Methods (return NEW array — original UNCHANGED)
```
map(fn)        → transforms each element
filter(fn)     → keeps elements where fn returns true
reduce(fn, 0)  → accumulates to single value
slice(s, e)    → returns portion (non-destructive)
find(fn)       → first element matching condition
```

## Array Methods (MUTATE original)
```
push(x)        → add to end
pop()          → remove from end
unshift(x)     → add to start
shift()        → remove from start
splice(i, n)   → remove n elements at index i
sort()         → sorts (use comparator for numbers!)
reverse()      → reverses in place
```

## Sort Trap
```
[10,9,2].sort()          // [10,2,9] WRONG for numbers!
[10,9,2].sort((a,b)=>a-b) // [2,9,10] CORRECT
```

---

# HTML CHEAT SHEET

## Document Structure
```html
<!DOCTYPE html>   <!-- declares HTML5 -->
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
</head>
<body>content</body>
</html>
```

## Essential Tags
```
Headings:    h1-h6 (only ONE h1 per page!)
Paragraph:   p
Bold:        strong (semantic) or b
Italic:      em (semantic) or i
Link:        a href="url"
Image:       img src="x.jpg" alt="desc"
Line break:  br (self-closing)
Divider:     hr (self-closing)
Division:    div (block), span (inline)
```

## Lists
```
<ul> → unordered (bullets)
<ol> → ordered (numbers)
<li> → list item (inside ul or ol)
<dl><dt><dd> → definition list
```

## Forms
```
<form action="/url" method="GET|POST">
input types: text, email, password, number, radio, checkbox, file
<select><option> → dropdown
<textarea> → multi-line
<button type="submit|reset|button">

label for="x" must match input id="x"
required → makes field mandatory
```

## Semantic Tags
```
header, nav, main, section, article, aside, footer
figure, figcaption, time, mark, details, summary
```

## Block vs Inline
```
Block: div, p, h1-h6, ul, ol, li, header, section, form
Inline: span, a, img, strong, em, input, button, label
```

---

# CSS CHEAT SHEET

## Selectors
```
p { }           element
.class { }      class
#id { }         ID
* { }           universal
div p { }       descendant
div > p { }     direct child
a:hover { }     pseudo-class
p::before { }   pseudo-element
input[type="text"] { } attribute
```

## Specificity (CRITICAL)
```
!important (avoid) > inline style (1000) > #id (100) > .class/:pseudo (10) > element (1)
Tie → LAST rule wins
```

## Box Model
```
Width = content
Box = content + padding + border
Space taken = box + margin

box-sizing: border-box → width includes padding+border
margin: top right bottom left (clockwise)
margin: 10px 20px → top/bottom 10, left/right 20
```

## Display
```
block       → full width, new line (div, p, h1)
inline      → content width, same line (span, a)
inline-block → same line BUT can set width/height
none        → removes element AND space
flex        → flexbox container
```

## Position
```
static   → default, normal flow
relative → moved relative to itself
absolute → relative to nearest positioned ancestor
fixed    → relative to viewport (stays on scroll)
sticky   → stays when scrolling reaches it
```

## Flexbox
```
Container:
  display: flex
  flex-direction: row | column | row-reverse | column-reverse
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly
  align-items: stretch | flex-start | flex-end | center

Item:
  flex: 1           (grow to fill space)
  align-self: center (override align-items)
  order: 2          (change order)
```

## Common Values
```
Colors: red, #FF0000, rgb(255,0,0), rgba(255,0,0,0.5), hsl(0,100%,50%)
Units: px (fixed), % (of parent), em (of parent font), rem (of root), vw/vh (of viewport)
```

---

# GIT CHEAT SHEET

## The Core Workflow
```
git init                    Start new repo
git status                  Check state
git add .                   Stage all
git add file.txt            Stage one file
git commit -m "message"     Save snapshot
git push                    Send to GitHub
git pull                    Get from GitHub
```

## Branches
```
git branch                  List branches
git branch feature          Create branch
git switch feature          Go to branch
git checkout -b feature     Create + switch (old way)
git switch -c feature       Create + switch (new way)
git merge feature           Merge into current
git branch -d feature       Delete branch
```

## Remote
```
git clone <url>             Copy remote repo
git remote -v               Show remotes
git remote add origin <url> Connect to remote
git fetch                   Download (no merge)
git pull                    fetch + merge
git push -u origin main     First push with tracking
```

## Key Facts
```
origin = default remote name
HEAD = current commit/branch pointer
fetch vs pull: fetch downloads, pull downloads AND merges
.gitignore = list files to not track
GitHub Pages = free static hosting from repo
```

---

# PATTERN PROGRAMMING CHEAT SHEET

## Universal Template
```java
for (int i = 1; i <= n; i++) {          // outer = rows
    // spaces (if needed)
    for (int j = 1; j <= spaces; j++) {
        System.out.print(" ");
    }
    // content
    for (int j = 1; j <= content; j++) {
        System.out.print(what_to_print + " ");
    }
    System.out.println();                // newline
}
```

## Pattern Reference
```
Right triangle:    inner j: 1 to i,     print *
Inverted triangle: inner j: 1 to n-i+1, print *
Pyramid:           spaces: n-i, stars: i
Floyd's triangle:  counter++, print counter
Number triangle:   print j
Same number/row:   print i
Alphabet triangle: print (char)('A'+j)
Hollow shapes:     condition on first/last row/column
```

## 5-Step Solving Method
```
1. Count rows → outer loop
2. Analyze each row → what's in row i?
3. Are there leading spaces? → spaces = n-i
4. What to print? → *, j, i, counter, char?
5. Test with n=3 mentally before writing
```
