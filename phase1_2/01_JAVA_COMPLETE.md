# JAVA COMPLETE PREPARATION
## Tech Passport Phase 1 + Phase 2

---

# PART 1 — JAVA FUNDAMENTALS

## 1.1 Variables and Data Types

### Concept
Java is statically typed — every variable must declare its type before use.

### Primitive Data Types — MUST MEMORIZE

| Type | Size | Range | Example |
|------|------|-------|---------|
| byte | 1 byte | -128 to 127 | byte b = 10; |
| short | 2 bytes | -32768 to 32767 | short s = 1000; |
| int | 4 bytes | -2^31 to 2^31-1 | int x = 5; |
| long | 8 bytes | very large | long l = 100L; |
| float | 4 bytes | ~7 decimal digits | float f = 3.14f; |
| double | 8 bytes | ~15 decimal digits | double d = 3.14; |
| char | 2 bytes | Unicode character | char c = 'A'; |
| boolean | 1 bit | true / false | boolean b = true; |

> EXAM TIP: int is default for integers, double is default for decimals. 
> If you write 3.14 without 'f', Java treats it as double, NOT float.

### Type Casting

```java
// Widening (automatic — smaller to larger)
int x = 10;
double d = x;   // OK, automatic

// Narrowing (manual — larger to smaller)
double d = 9.99;
int x = (int) d;   // x = 9, decimal is CUT (not rounded)
```

> COMMON TRAP: (int) 9.99 gives 9, NOT 10. It truncates, not rounds.

---

## 1.2 Input and Output

```java
import java.util.Scanner;

public class InputDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        
        int n = sc.nextInt();           // reads int
        double d = sc.nextDouble();     // reads double
        String s = sc.next();           // reads one word
        String line = sc.nextLine();    // reads full line
        
        System.out.println("Hello");    // print + newline
        System.out.print("Hello");      // print only
        System.out.printf("%.2f", d);  // formatted print
    }
}
```

> COMMON TRAP: After nextInt(), if you use nextLine(), it reads the leftover newline character. Always add an extra sc.nextLine() to consume it.

---

## 1.3 Operators

### Arithmetic
```java
int a = 10, b = 3;
a + b  = 13
a - b  = 7
a * b  = 30
a / b  = 3     // INTEGER DIVISION (no decimal!)
a % b  = 1     // modulo (remainder)
```

> COMMON TRAP: 10 / 3 = 3 in Java (integer division). To get 3.33, use 10.0/3 or (double)10/3

### Increment/Decrement — OUTPUT TRAP

```java
int x = 5;
System.out.println(x++);  // prints 5, THEN increments (post-increment)
System.out.println(x);    // prints 6

int y = 5;
System.out.println(++y);  // increments FIRST, THEN prints 6 (pre-increment)
```

### Bitwise (less common but possible MCQ)
```
& (AND), | (OR), ^ (XOR), ~ (NOT), << (left shift), >> (right shift)
5 & 3 = 1 (101 & 011 = 001)
```

---

## 1.4 Control Flow

### if / else if / else

```java
int score = 75;
if (score >= 90) {
    System.out.println("A");
} else if (score >= 75) {
    System.out.println("B");   // This prints
} else {
    System.out.println("C");
}
```

### switch — IMPORTANT: FALL-THROUGH TRAP

```java
int day = 2;
switch (day) {
    case 1:
        System.out.println("Monday");
        break;          // MUST have break to stop fall-through
    case 2:
        System.out.println("Tuesday");
        // NO break here!
    case 3:
        System.out.println("Wednesday");  // This ALSO prints!
        break;
    default:
        System.out.println("Other");
}
// Output: Tuesday, Wednesday
```

> EXAM TIP: If there is no break, execution falls through to the next case. This is a very common output prediction trap.

---

## 1.5 Loops — HIGH PRIORITY

### for loop

```java
for (int i = 0; i < 5; i++) {
    System.out.print(i + " ");
}
// Output: 0 1 2 3 4
```

### while loop

```java
int i = 1;
while (i <= 5) {
    System.out.print(i + " ");
    i++;
}
// Output: 1 2 3 4 5
```

### do-while loop — EXECUTES AT LEAST ONCE

```java
int i = 10;
do {
    System.out.println(i);   // prints 10 even though condition is false
    i++;
} while (i < 5);
// Output: 10
```

> EXAM TIP: do-while always executes the body at least once. This is tested with conditions that are false from the start.

### break and continue

```java
// break: exits loop immediately
for (int i = 0; i < 10; i++) {
    if (i == 5) break;
    System.out.print(i + " ");
}
// Output: 0 1 2 3 4

// continue: skips current iteration
for (int i = 0; i < 10; i++) {
    if (i % 2 == 0) continue;
    System.out.print(i + " ");
}
// Output: 1 3 5 7 9
```

---

# PART 2 — JAVA STRINGS

## 2.1 String Basics

```java
String s = "Hello";
String s2 = new String("Hello");

// == vs .equals()
System.out.println(s == s2);         // false (compares references)
System.out.println(s.equals(s2));    // true (compares content)
```

> MUST REMEMBER: ALWAYS use .equals() to compare String content, NEVER ==

## 2.2 Important String Methods

```java
String s = "Hello World";

s.length()              // 11
s.charAt(0)             // 'H'
s.charAt(6)             // 'W'
s.indexOf('o')          // 4 (first occurrence)
s.lastIndexOf('o')      // 7
s.substring(6)          // "World"
s.substring(0, 5)       // "Hello" (0 to 4, end is exclusive)
s.toLowerCase()         // "hello world"
s.toUpperCase()         // "HELLO WORLD"
s.trim()                // removes leading/trailing spaces
s.replace('l', 'r')     // "Herro Worrd"
s.contains("World")     // true
s.startsWith("He")      // true
s.endsWith("ld")        // true
s.split(" ")            // ["Hello", "World"]
s.toCharArray()         // char array
```

> COMMON TRAP: substring(start, end) — end is EXCLUSIVE. "Hello".substring(1,3) = "el", not "ell"

## 2.3 String Immutability

```java
String s = "Hello";
s.toUpperCase();                    // Does NOT change s!
System.out.println(s);             // Still "Hello"

s = s.toUpperCase();               // Must reassign
System.out.println(s);             // Now "HELLO"
```

> MUST REMEMBER: Strings are immutable. Methods return NEW strings. Original is unchanged.

## 2.4 StringBuilder vs String

```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World");    // modifies in place
sb.reverse();           // reverses
sb.toString();          // converts to String
```

> EXAM TIP: Use StringBuilder when you need to modify strings in a loop. String concatenation in loops is inefficient.

---

# PART 3 — JAVA ARRAYS

## 3.1 1D Arrays

```java
// Declaration
int[] arr = new int[5];           // default values: all 0
int[] arr2 = {1, 2, 3, 4, 5};   // initialization

// Access
arr[0] = 10;
System.out.println(arr.length);   // 5 (NOT arr.length())

// Traversal
for (int i = 0; i < arr.length; i++) {
    System.out.print(arr[i] + " ");
}

// Enhanced for loop
for (int x : arr2) {
    System.out.print(x + " ");
}
```

> COMMON TRAP: arr.length (no parentheses!) — it is a field, not a method.

## 3.2 2D Arrays

```java
int[][] matrix = {{1,2,3},{4,5,6},{7,8,9}};

// Rows
System.out.println(matrix.length);       // 3 (rows)
// Columns
System.out.println(matrix[0].length);    // 3 (columns)

// Traversal
for (int i = 0; i < matrix.length; i++) {
    for (int j = 0; j < matrix[i].length; j++) {
        System.out.print(matrix[i][j] + " ");
    }
    System.out.println();
}
```

## 3.3 Find Maximum / Minimum

```java
int[] arr = {3, 7, 1, 9, 4};
int max = arr[0];  // start with first element
for (int i = 1; i < arr.length; i++) {
    if (arr[i] > max) {
        max = arr[i];
    }
}
System.out.println("Max: " + max);  // 9
```

> COMMON TRAP: Start max = Integer.MIN_VALUE or max = arr[0]. Never max = 0 (what if all elements are negative?)

## 3.4 Array Sorting (using Arrays.sort)

```java
import java.util.Arrays;
int[] arr = {5, 3, 1, 4, 2};
Arrays.sort(arr);  // {1, 2, 3, 4, 5}
System.out.println(Arrays.toString(arr));  // [1, 2, 3, 4, 5]
```

---

# PART 4 — JAVA OOP — VERY HIGH PRIORITY

## 4.1 Class and Object

```java
class Dog {
    // Fields (instance variables)
    String name;
    int age;
    
    // Constructor
    Dog(String name, int age) {
        this.name = name;    // 'this' refers to current object
        this.age = age;
    }
    
    // Method
    void bark() {
        System.out.println(name + " says: Woof!");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog("Rex", 3);  // creating object
        d.bark();                    // calling method
        System.out.println(d.name); // accessing field
    }
}
```

## 4.2 Constructors

```java
class Person {
    String name;
    int age;
    
    // Default constructor (no parameters)
    Person() {
        name = "Unknown";
        age = 0;
    }
    
    // Parameterized constructor
    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    // Copy constructor
    Person(Person p) {
        this.name = p.name;
        this.age = p.age;
    }
}
```

> MUST REMEMBER: If you define any constructor, Java no longer provides the default constructor automatically.

## 4.3 this keyword

```java
class Box {
    int width;
    
    Box(int width) {
        this.width = width;  // this.width = parameter called width
        // Without 'this', both sides refer to the parameter
    }
    
    void show() {
        System.out.println(this.width);  // refers to object's field
    }
}
```

## 4.4 static keyword

```java
class Counter {
    static int count = 0;  // shared across ALL objects
    int id;
    
    Counter() {
        count++;           // increments shared counter
        id = count;
    }
    
    static void showCount() {   // can be called without an object
        System.out.println(count);
    }
}

Counter.showCount();  // valid — no object needed
```

> EXAM TIP: static methods cannot use 'this' keyword. Static members belong to the class, not to objects.

## 4.5 Inheritance

```java
class Animal {
    String name;
    
    Animal(String name) {
        this.name = name;
    }
    
    void eat() {
        System.out.println(name + " is eating");
    }
    
    void sound() {
        System.out.println("Some sound");
    }
}

class Dog extends Animal {
    Dog(String name) {
        super(name);  // calls parent constructor
    }
    
    // Method Overriding
    @Override
    void sound() {
        System.out.println(name + " says Woof");
    }
}

class Cat extends Animal {
    Cat(String name) {
        super(name);
    }
    
    @Override
    void sound() {
        System.out.println(name + " says Meow");
    }
}
```

> EXAM TIP: super() calls parent constructor. Must be FIRST statement in child constructor.

## 4.6 Polymorphism — HIGH PROBABILITY OUTPUT QUESTIONS

```java
Animal a = new Dog("Rex");  // Dog object stored in Animal reference
a.sound();   // Output: "Rex says Woof" — calls DOG's version!
// This is runtime polymorphism (dynamic dispatch)

a.eat();     // Output: "Rex is eating" — inherited from Animal
```

> MUST REMEMBER: The method that runs depends on the ACTUAL object type (Dog), not the reference type (Animal). This is the core of polymorphism.

## 4.7 Method Overloading vs Overriding

| Feature | Overloading | Overriding |
|---------|------------|------------|
| Where | Same class | Parent + Child class |
| Method name | Same | Same |
| Parameters | DIFFERENT | SAME |
| Return type | Can differ | Same (or covariant) |
| When resolved | Compile time | Runtime |
| Keyword | None needed | @Override |

```java
// Overloading — same class, different params
class Math {
    int add(int a, int b) { return a + b; }
    double add(double a, double b) { return a + b; }  // overloaded
    int add(int a, int b, int c) { return a+b+c; }   // overloaded
}

// Overriding — child class, same signature
class Parent {
    void show() { System.out.println("Parent"); }
}
class Child extends Parent {
    @Override
    void show() { System.out.println("Child"); }  // overridden
}
```

## 4.8 Encapsulation

```java
class BankAccount {
    private double balance;  // private — cannot access directly
    
    public double getBalance() {     // getter
        return balance;
    }
    
    public void deposit(double amount) {  // setter with validation
        if (amount > 0) {
            balance += amount;
        }
    }
}
```

## 4.9 Abstract Classes and Interfaces

```java
// Abstract class — cannot be instantiated directly
abstract class Shape {
    abstract double area();    // abstract method — no body
    
    void display() {           // concrete method — has body
        System.out.println("Area: " + area());
    }
}

class Circle extends Shape {
    double radius;
    Circle(double r) { radius = r; }
    
    @Override
    double area() {
        return Math.PI * radius * radius;  // must implement
    }
}

// Interface — all methods are abstract by default
interface Drawable {
    void draw();        // implicitly public abstract
    void resize();      // implicitly public abstract
}

class Square implements Drawable {
    public void draw() { System.out.println("Drawing square"); }
    public void resize() { System.out.println("Resizing square"); }
}
```

> MUST REMEMBER:
> - abstract class: use extends, can have constructors, can have fields, partial implementation
> - interface: use implements, no constructors, all methods abstract (Java 7), can implement multiple

---

# PART 5 — EXCEPTION HANDLING

```java
try {
    int result = 10 / 0;              // throws ArithmeticException
    System.out.println(result);       // this line is SKIPPED
} catch (ArithmeticException e) {
    System.out.println("Error: " + e.getMessage());  // "/ by zero"
} finally {
    System.out.println("This ALWAYS runs");  // always executes
}
```

> MUST REMEMBER: finally always runs — even if there is a return statement in try or catch.

### Common Exceptions

| Exception | Cause |
|-----------|-------|
| ArithmeticException | Division by zero |
| NullPointerException | Using null reference |
| ArrayIndexOutOfBoundsException | Accessing index that doesn't exist |
| ClassCastException | Invalid type cast |
| NumberFormatException | parseInt("abc") |
| StackOverflowError | Infinite recursion |

### throw vs throws

```java
// throw: used to manually throw an exception
throw new ArithmeticException("Custom error");

// throws: declares that a method MAY throw an exception
void myMethod() throws IOException {
    // ...
}
```

---

# PART 6 — 30 JAVA OUTPUT PREDICTION QUESTIONS

## Easy Level (Q1–Q10)

**Q1:**
```java
int x = 5;
System.out.println(x++);
System.out.println(x);
```
What is the output?
A) 5, 5   B) 5, 6   C) 6, 6   D) 6, 5

---

**Q2:**
```java
String s1 = "Hello";
String s2 = "Hello";
System.out.println(s1 == s2);
System.out.println(s1.equals(s2));
```
A) false, false   B) true, true   C) false, true   D) true, false

---

**Q3:**
```java
int i = 0;
while (i < 3) {
    System.out.print(i + " ");
    i++;
}
```
A) 0 1 2 3   B) 1 2 3   C) 0 1 2   D) infinite loop

---

**Q4:**
```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) continue;
    System.out.print(i + " ");
}
```
A) 1 2 3 4 5   B) 1 2 4 5   C) 1 2   D) 3 4 5

---

**Q5:**
```java
int x = 10;
System.out.println(x / 3);
System.out.println(x % 3);
```
A) 3.33, 1   B) 3, 1   C) 3, 0   D) 3, 3

---

**Q6:**
```java
String s = "Hello";
s.toUpperCase();
System.out.println(s);
```
A) HELLO   B) Hello   C) hello   D) Compilation error

---

**Q7:**
```java
int[] arr = {1, 2, 3, 4, 5};
System.out.println(arr[arr.length - 1]);
```
A) 4   B) 5   C) IndexOutOfBoundsException   D) 6

---

**Q8:**
```java
int a = 5, b = 10;
int c = a++ + ++b;
System.out.println(a + " " + b + " " + c);
```
A) 5 11 16   B) 6 11 16   C) 6 10 16   D) 5 10 15

---

**Q9:**
```java
int x = 10;
do {
    System.out.println(x);
    x++;
} while (x < 5);
```
A) Nothing   B) 10   C) Infinite loop   D) Error

---

**Q10:**
```java
double d = (int) 9.99;
System.out.println(d);
```
A) 9.99   B) 10   C) 9.0   D) 9

---

## Medium Level (Q11–Q20)

**Q11:**
```java
class Animal {
    void sound() { System.out.println("Animal"); }
}
class Dog extends Animal {
    void sound() { System.out.println("Woof"); }
}
public class Main {
    public static void main(String[] args) {
        Animal a = new Dog();
        a.sound();
    }
}
```
A) Animal   B) Woof   C) Compilation error   D) Runtime error

---

**Q12:**
```java
class A {
    A() { System.out.println("A created"); }
}
class B extends A {
    B() { System.out.println("B created"); }
}
public class Main {
    public static void main(String[] args) {
        B obj = new B();
    }
}
```
A) B created   B) A created, B created   C) B created, A created   D) Error

---

**Q13:**
```java
int x = 2;
switch (x) {
    case 1: System.out.println("One");
    case 2: System.out.println("Two");
    case 3: System.out.println("Three");
    default: System.out.println("Other");
}
```
A) Two   B) Two, Three   C) Two, Three, Other   D) Two, Other

---

**Q14:**
```java
try {
    System.out.println("Try");
    int x = 1/0;
    System.out.println("After");
} catch (Exception e) {
    System.out.println("Catch");
} finally {
    System.out.println("Finally");
}
```
A) Try, Catch, Finally   B) Try, After, Finally   C) Try, Finally   D) Catch, Finally

---

**Q15:**
```java
String s = "Hello World";
System.out.println(s.substring(6));
System.out.println(s.substring(0, 5));
```
A) World, Hello   B) World, Hello   C) orld, Hell   D) Error

---

**Q16:**
```java
static int count = 0;
class Test {
    Test() { count++; }
}
public class Main {
    public static void main(String[] args) {
        Test t1 = new Test();
        Test t2 = new Test();
        Test t3 = new Test();
        System.out.println(count);
    }
}
```
A) 0   B) 1   C) 3   D) Compilation error

---

**Q17:**
```java
public class Main {
    static void method(int x) {
        if (x == 0) return;
        System.out.print(x + " ");
        method(x - 1);
    }
    public static void main(String[] args) {
        method(3);
    }
}
```
A) 1 2 3   B) 3 2 1   C) 3 2 1 0   D) 0 1 2 3

---

**Q18:**
```java
int[] arr = new int[3];
System.out.println(arr[0] + " " + arr[1] + " " + arr[2]);
```
A) null null null   B) 0 0 0   C) Error   D) undefined undefined undefined

---

**Q19:**
```java
String s = "abcde";
System.out.println(s.charAt(2));
System.out.println(s.indexOf('c'));
```
A) c, 2   B) b, 2   C) c, 3   D) b, 1

---

**Q20:**
```java
int x = 5;
int y = x++ + ++x;
System.out.println(x + " " + y);
```
A) 7, 12   B) 6, 11   C) 7, 13   D) 6, 12

---

## Hard Level (Q21–Q30)

**Q21:**
```java
class Parent {
    int x = 10;
    void show() { System.out.println("Parent: " + x); }
}
class Child extends Parent {
    int x = 20;
    void show() { System.out.println("Child: " + x); }
}
public class Main {
    public static void main(String[] args) {
        Parent p = new Child();
        p.show();
        System.out.println(p.x);
    }
}
```
A) Child: 20, 20   B) Parent: 10, 10   C) Child: 20, 10   D) Child: 10, 10

---

**Q22:**
```java
try {
    try {
        throw new RuntimeException("inner");
    } finally {
        System.out.println("inner finally");
    }
} catch (RuntimeException e) {
    System.out.println("outer catch: " + e.getMessage());
} finally {
    System.out.println("outer finally");
}
```
A) inner finally, outer catch: inner, outer finally
B) outer catch: inner, inner finally, outer finally
C) inner finally, outer finally
D) Error

---

**Q23:**
```java
public class Main {
    static int factorial(int n) {
        if (n == 1) return 1;
        return n * factorial(n - 1);
    }
    public static void main(String[] args) {
        System.out.println(factorial(5));
    }
}
```
A) 24   B) 120   C) 15   D) 5

---

**Q24:**
```java
String a = "Java";
String b = a;
b = "Python";
System.out.println(a);
System.out.println(b);
```
A) Java, Python   B) Python, Python   C) Java, Java   D) Error

---

**Q25:**
```java
interface A { void show(); }
interface B { void display(); }
class C implements A, B {
    public void show() { System.out.println("Show"); }
    public void display() { System.out.println("Display"); }
}
public class Main {
    public static void main(String[] args) {
        A obj = new C();
        obj.show();
        // obj.display();   // This line would cause what?
    }
}
```
What happens if the commented line is uncommented?
A) Runs fine   B) Compilation error   C) Runtime error   D) display() prints

---

**Q26:**
```java
for (int i = 0; i < 3; i++) {
    for (int j = 0; j <= i; j++) {
        System.out.print("* ");
    }
    System.out.println();
}
```
What is the output?

---

**Q27:**
```java
int[] arr = {5, 3, 8, 1, 9};
for (int i = 0; i < arr.length - 1; i++) {
    if (arr[i] > arr[i+1]) {
        int temp = arr[i];
        arr[i] = arr[i+1];
        arr[i+1] = temp;
    }
}
System.out.println(arr[0]);
```
A) 5   B) 3   C) 1   D) 9

---

**Q28:**
```java
class Box {
    static int count = 0;
    Box() { count++; }
    static void display() {
        System.out.println("Count: " + count);
    }
}
public class Main {
    public static void main(String[] args) {
        new Box();
        new Box();
        Box.display();
    }
}
```
A) Count: 0   B) Count: 1   C) Count: 2   D) Error

---

**Q29:**
```java
public class Main {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3};
        System.out.println(arr[-1]);
    }
}
```
A) 0   B) -1   C) ArrayIndexOutOfBoundsException   D) Compilation error

---

**Q30:**
```java
abstract class Vehicle {
    abstract void start();
    void stop() { System.out.println("Stopping"); }
}
class Car extends Vehicle {
    void start() { System.out.println("Car starting"); }
}
public class Main {
    public static void main(String[] args) {
        Vehicle v = new Car();
        v.start();
        v.stop();
    }
}
```
A) Error — cannot instantiate abstract class
B) Car starting, Stopping
C) Car starting only
D) Stopping only

---

# ANSWERS TO OUTPUT QUESTIONS

| Q# | Answer | Key Concept |
|----|--------|-------------|
| Q1 | B: 5, 6 | Post-increment prints THEN increments |
| Q2 | B: true, true | String literals are pooled in Java |
| Q3 | C: 0 1 2 | Condition i < 3, stops at 3 |
| Q4 | B: 1 2 4 5 | continue skips i==3 |
| Q5 | B: 3, 1 | Integer division; 10/3=3, 10%3=1 |
| Q6 | B: Hello | Strings are immutable; must reassign |
| Q7 | B: 5 | arr.length is 5, index 4 is last element with value 5 |
| Q8 | B: 6, 11, 16 | a++ gives 5 then becomes 6; ++b gives 11; 5+11=16 |
| Q9 | B: 10 | do-while executes body at least once |
| Q10 | C: 9.0 | Cast to int truncates to 9, then assigned to double = 9.0 |
| Q11 | B: Woof | Runtime polymorphism — actual object is Dog |
| Q12 | B: A created, B created | Parent constructor called first via implicit super() |
| Q13 | C: Two, Three, Other | No break = fall-through |
| Q14 | A: Try, Catch, Finally | Exception caught; finally always runs |
| Q15 | A: World, Hello | substring(6)="World", substring(0,5)="Hello" |
| Q16 | C: 3 | Static count shared across all objects |
| Q17 | B: 3 2 1 | Recursion prints BEFORE recursive call |
| Q18 | B: 0 0 0 | Default value for int[] is 0 |
| Q19 | A: c, 2 | charAt(2) = 'c'; indexOf('c') = 2 |
| Q20 | A: 7, 12 | x++ gives 5 (x becomes 6); ++x increments to 7 gives 7; 5+7=12; x=7 |
| Q21 | C: Child: 20, 10 | Methods resolved dynamically; FIELDS resolved statically |
| Q22 | A: inner finally, outer catch, outer finally | Finally runs before exception propagates |
| Q23 | B: 120 | 5! = 5*4*3*2*1 = 120 |
| Q24 | A: Java, Python | b reassigned; a still points to "Java" |
| Q25 | B: Compilation error | obj is type A, which doesn't have display() |
| Q26 | * / ** / *** (triangle pattern) | Inner loop j <= i |
| Q27 | B: 3 | One pass of bubble sort: 3 bubbles to position 0 |
| Q28 | C: Count: 2 | Two Box objects created, count = 2 |
| Q29 | C: ArrayIndexOutOfBoundsException | Negative index not valid |
| Q30 | B: Car starting, Stopping | new Car() is valid; Vehicle ref can hold Car |

---

# PART 7 — 20 JAVA CODING QUESTIONS

## CQ1: Find Sum of Array
**Problem:** Given an array of n integers, find the sum.
**Input:** n=5, arr={1,2,3,4,5}
**Output:** 15
**Hint:** Initialize sum=0, traverse and add each element.

```java
public class SumArray {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5};
        int sum = 0;
        for (int x : arr) {
            sum += x;
        }
        System.out.println("Sum: " + sum);  // 15
    }
}
```

---

## CQ2: Reverse a String
**Problem:** Reverse the string "Hello"
**Output:** "olleH"

```java
public class ReverseString {
    public static void main(String[] args) {
        String s = "Hello";
        StringBuilder sb = new StringBuilder(s);
        System.out.println(sb.reverse().toString());  // olleH
        
        // Manual approach (good for exams):
        for (int i = s.length() - 1; i >= 0; i--) {
            System.out.print(s.charAt(i));
        }
    }
}
```

---

## CQ3: Check Palindrome
**Problem:** Check if "racecar" is a palindrome.
**Output:** true

```java
public class Palindrome {
    static boolean isPalindrome(String s) {
        int left = 0, right = s.length() - 1;
        while (left < right) {
            if (s.charAt(left) != s.charAt(right)) return false;
            left++;
            right--;
        }
        return true;
    }
    public static void main(String[] args) {
        System.out.println(isPalindrome("racecar"));  // true
        System.out.println(isPalindrome("hello"));    // false
    }
}
```

---

## CQ4: Find Factorial (Recursion)
**Problem:** Find factorial of 5
**Output:** 120

```java
public class Factorial {
    static int factorial(int n) {
        if (n == 0 || n == 1) return 1;  // base case
        return n * factorial(n - 1);      // recursive case
    }
    public static void main(String[] args) {
        System.out.println(factorial(5));  // 120
    }
}
```

---

## CQ5: Check Prime Number
**Problem:** Check if 17 is prime.
**Output:** Prime

```java
public class Prime {
    static boolean isPrime(int n) {
        if (n <= 1) return false;
        for (int i = 2; i <= Math.sqrt(n); i++) {  // O(sqrt(n))
            if (n % i == 0) return false;
        }
        return true;
    }
    public static void main(String[] args) {
        System.out.println(isPrime(17) ? "Prime" : "Not Prime");
    }
}
```

---

## CQ6: Fibonacci Series
**Problem:** Print first 10 Fibonacci numbers.
**Output:** 0 1 1 2 3 5 8 13 21 34

```java
public class Fibonacci {
    public static void main(String[] args) {
        int a = 0, b = 1;
        int n = 10;
        for (int i = 0; i < n; i++) {
            System.out.print(a + " ");
            int temp = a + b;
            a = b;
            b = temp;
        }
    }
}
```

---

## CQ7: Count Character Frequency
**Problem:** Count frequency of each character in "hello"

```java
public class CharFrequency {
    public static void main(String[] args) {
        String s = "hello";
        int[] freq = new int[26];
        for (char c : s.toCharArray()) {
            freq[c - 'a']++;
        }
        for (int i = 0; i < 26; i++) {
            if (freq[i] > 0) {
                System.out.println((char)(i + 'a') + ": " + freq[i]);
            }
        }
    }
}
// Output: e:1, h:1, l:2, o:1
```

---

## CQ8: Check Anagram
**Problem:** Check if "listen" and "silent" are anagrams.

```java
import java.util.Arrays;
public class Anagram {
    static boolean isAnagram(String a, String b) {
        char[] ca = a.toCharArray();
        char[] cb = b.toCharArray();
        Arrays.sort(ca);
        Arrays.sort(cb);
        return Arrays.equals(ca, cb);
    }
    public static void main(String[] args) {
        System.out.println(isAnagram("listen", "silent"));  // true
    }
}
```

---

## CQ9: Linear Search
**Problem:** Find if 7 exists in {3,7,1,9,4}

```java
public class LinearSearch {
    static int search(int[] arr, int target) {
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == target) return i;
        }
        return -1;
    }
    public static void main(String[] args) {
        int[] arr = {3, 7, 1, 9, 4};
        System.out.println(search(arr, 7));  // 1 (index)
        System.out.println(search(arr, 5));  // -1 (not found)
    }
}
```

---

## CQ10: Binary Search
**Problem:** Find 7 in sorted array {1,3,5,7,9,11}

```java
public class BinarySearch {
    static int binarySearch(int[] arr, int target) {
        int low = 0, high = arr.length - 1;
        while (low <= high) {
            int mid = low + (high - low) / 2;  // avoids overflow
            if (arr[mid] == target) return mid;
            else if (arr[mid] < target) low = mid + 1;
            else high = mid - 1;
        }
        return -1;
    }
    public static void main(String[] args) {
        int[] arr = {1, 3, 5, 7, 9, 11};
        System.out.println(binarySearch(arr, 7));   // 3
        System.out.println(binarySearch(arr, 4));   // -1
    }
}
```

---

## CQ11: Bubble Sort
**Problem:** Sort {5,3,8,1,2} using bubble sort.

```java
public class BubbleSort {
    static void bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {          // passes
            for (int j = 0; j < n - 1 - i; j++) {  // comparisons
                if (arr[j] > arr[j+1]) {
                    int temp = arr[j];
                    arr[j] = arr[j+1];
                    arr[j+1] = temp;
                }
            }
        }
    }
    public static void main(String[] args) {
        int[] arr = {5, 3, 8, 1, 2};
        bubbleSort(arr);
        for (int x : arr) System.out.print(x + " ");
        // Output: 1 2 3 5 8
    }
}
```

---

## CQ12: Count Duplicates
**Problem:** Find duplicates in {1,2,3,2,4,3,5}

```java
public class FindDuplicates {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 2, 4, 3, 5};
        System.out.print("Duplicates: ");
        for (int i = 0; i < arr.length; i++) {
            for (int j = i + 1; j < arr.length; j++) {
                if (arr[i] == arr[j]) {
                    System.out.print(arr[i] + " ");
                    break;
                }
            }
        }
        // Output: Duplicates: 2 3
    }
}
```

---

## CQ13: Matrix Multiplication (2x2)
**Problem:** Multiply two 2x2 matrices.

```java
public class MatrixMultiply {
    public static void main(String[] args) {
        int[][] A = {{1,2},{3,4}};
        int[][] B = {{5,6},{7,8}};
        int[][] C = new int[2][2];
        
        for (int i = 0; i < 2; i++) {
            for (int j = 0; j < 2; j++) {
                for (int k = 0; k < 2; k++) {
                    C[i][j] += A[i][k] * B[k][j];
                }
            }
        }
        // C = {{19,22},{43,50}}
    }
}
```

---

## CQ14: Selection Sort
**Problem:** Sort using selection sort.

```java
public class SelectionSort {
    static void selectionSort(int[] arr) {
        for (int i = 0; i < arr.length - 1; i++) {
            int minIdx = i;
            for (int j = i + 1; j < arr.length; j++) {
                if (arr[j] < arr[minIdx]) minIdx = j;
            }
            int temp = arr[minIdx];
            arr[minIdx] = arr[i];
            arr[i] = temp;
        }
    }
}
```

---

## CQ15: Remove Vowels from String

```java
public class RemoveVowels {
    public static void main(String[] args) {
        String s = "Hello World";
        String result = s.replaceAll("[aeiouAEIOU]", "");
        System.out.println(result);  // Hll Wrld
    }
}
```

---

## CQ16: Simple Bank Account (OOP)

```java
class BankAccount {
    private String owner;
    private double balance;
    
    BankAccount(String owner, double initialBalance) {
        this.owner = owner;
        this.balance = initialBalance;
    }
    
    void deposit(double amount) {
        if (amount > 0) balance += amount;
    }
    
    void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
        } else {
            System.out.println("Insufficient funds");
        }
    }
    
    void display() {
        System.out.println(owner + " Balance: " + balance);
    }
}
```

---

## CQ17: Fibonacci using Recursion

```java
static int fib(int n) {
    if (n <= 1) return n;
    return fib(n-1) + fib(n-2);
}
// fib(0)=0, fib(1)=1, fib(5)=5
```

---

## CQ18: Count Words in String

```java
String s = "Hello World Java";
String[] words = s.split(" ");
System.out.println("Word count: " + words.length);  // 3
```

---

## CQ19: Check Armstrong Number

```java
// A number where sum of cubes of digits equals the number
// 153 = 1^3 + 5^3 + 3^3 = 1 + 125 + 27 = 153
static boolean isArmstrong(int n) {
    int original = n, sum = 0;
    while (n > 0) {
        int digit = n % 10;
        sum += digit * digit * digit;
        n /= 10;
    }
    return sum == original;
}
```

---

## CQ20: Insertion Sort

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

---

# PART 8 — JAVA CHEAT SHEET (Quick Reference)

```
PRIMITIVE TYPES:
byte(1) < short(2) < int(4) < long(8) < float(4) < double(8)
char(2) boolean(1 bit)

DEFAULT VALUES IN ARRAYS:
int[] -> 0      boolean[] -> false      String[] -> null

STRING METHODS (memorize these):
length()  charAt(i)  substring(s,e)  indexOf(c)  
equals()  equalsIgnoreCase()  contains()  split()
toUpperCase()  toLowerCase()  trim()  replace()

IMPORTANT RULES:
- == compares references for objects
- .equals() compares content
- Strings are IMMUTABLE
- Arrays: length (no parentheses)
- ArrayList: size() (with parentheses)
- finally ALWAYS runs
- super() must be FIRST in constructor
- static methods cannot use 'this'

ACCESS MODIFIERS:
private < default < protected < public
```
