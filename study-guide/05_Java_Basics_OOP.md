# 📁 FOLDER 05 — JAVA BASICS + OOP ⭐ HIGH PRIORITY

---

## 🧠 CONCEPT OVERVIEW

Java is a **statically typed, object-oriented, platform-independent** language. It compiles to **bytecode** which runs on the **JVM** (Java Virtual Machine).

---

## 📋 KEY RULES TO REMEMBER

| Concept | Key Fact |
|---------|----------|
| JDK | Java Development Kit — contains compiler + JRE |
| JRE | Java Runtime Environment — contains JVM + libraries |
| JVM | Java Virtual Machine — runs bytecode |
| Bytecode | Compiled Java (.class file) — platform-independent |
| main() is static | So JVM can call it without creating an object |
| Primitives | byte, short, int, long, float, double, char, boolean |
| int vs Integer | int = primitive, Integer = wrapper class (object) |

---

## ❓ QUESTIONS + SOLUTIONS

---

### Q1. Why is Java platform-independent? ⭐

**Solution:**
- Java source code → compiled by `javac` → produces **bytecode** (.class)
- Bytecode is NOT machine code — it's platform-neutral
- JVM (installed on each OS) interprets the bytecode
- Result: "Write Once, Run Anywhere" (WORA)

**Final Answer:**
> Java compiles to bytecode (not machine code). The JVM on any platform can execute the same bytecode, making Java platform-independent.

**🧠 Remember:** Java → bytecode → JVM → "Write Once, Run Anywhere"

---

### Q2. Difference between JDK, JRE, JVM? ⭐

```
JDK (biggest)
  └── JRE
        └── JVM (smallest)
```

| Tool | Purpose | Who uses it |
|------|---------|------------|
| JVM | Executes bytecode | Everyone (runtime) |
| JRE | JVM + standard libraries | Users running Java apps |
| JDK | JRE + compiler + debugger + tools | Developers |

**🧠 Remember:** JDK > JRE > JVM (nested, like Russian dolls)

---

### Q3. Java Primitive Data Types ⭐

| Type | Size | Range | Default |
|------|------|-------|---------|
| `byte` | 8-bit | -128 to 127 | 0 |
| `short` | 16-bit | -32,768 to 32,767 | 0 |
| `int` | 32-bit | ~-2B to 2B | 0 |
| `long` | 64-bit | Very large | 0L |
| `float` | 32-bit | Decimal | 0.0f |
| `double` | 64-bit | Decimal (precise) | 0.0 |
| `char` | 16-bit | Unicode character | '\u0000' |
| `boolean` | 1-bit | true/false | false |

**int vs Integer:**
| int | Integer |
|-----|---------|
| Primitive | Wrapper class (object) |
| Faster | Slower (boxing overhead) |
| Can't be null | Can be null |
| No methods | Has methods like `.parseInt()`, `.compareTo()` |

---

### Q4. Type Casting in Java ⭐

**Implicit (Widening):** smaller → larger (automatic)
```java
int x = 5;
double d = x;  // ✅ automatic (int → double)
```

**Explicit (Narrowing):** larger → smaller (manual, may lose data)
```java
double d = 9.99;
int x = (int) d;  // x = 9 — decimal lost!
```

**🧠 Remember:** Widening = safe and automatic | Narrowing = manual, lose data

---

### Q5. Operators ⭐

**`&&` vs `&`:**
| Operator | Short-circuit? | Use |
|----------|---------------|-----|
| `&&` | YES — stops if left is false | Logical AND (use this) |
| `&` | NO — evaluates both | Bitwise AND |

**`\|\|` vs `\|`:**
| Operator | Short-circuit? |
|----------|---------------|
| `\|\|` | YES — stops if left is true |
| `\|` | NO — evaluates both |

**`++i` vs `i++`:**
```java
int i = 5;
System.out.println(++i); // 6 — increment FIRST, then use
System.out.println(i++); // 6 — use FIRST, then increment
System.out.println(i);   // 7
```

---

### Q6. Loops ⭐

**Difference between for, while, do-while:**
| Loop | Use when |
|------|---------|
| `for` | Know the number of iterations |
| `while` | Check condition before each iteration |
| `do-while` | Run at least once, THEN check condition |

**Nested loop:** A loop inside a loop. Used in patterns, matrix traversal.
**Infinite loop:** A loop whose condition never becomes false. `while(true)`.

---

### Q7. Method Overloading vs Overriding ⭐

| Feature | Overloading | Overriding |
|---------|------------|-----------|
| Where | Same class | Subclass overrides parent method |
| When | Compile time (static binding) | Runtime (dynamic binding) |
| Signature | Different parameters | Same signature |
| `@Override` | Not needed | Required (best practice) |

```java
// Overloading — same name, different params
class Calc {
  int add(int a, int b) { return a + b; }
  double add(double a, double b) { return a + b; }
}

// Overriding — child redefines parent method
class Animal { void speak() { System.out.println("..."); } }
class Dog extends Animal {
  @Override
  void speak() { System.out.println("Woof!"); }
}
```

---

### Q8. Constructor ⭐

- Special method with the **same name as the class**
- No return type
- Called automatically when object is created with `new`
- If not defined, Java provides a **default no-arg constructor**

```java
class Person {
  String name;
  Person(String name) {   // constructor
    this.name = name;
  }
}
Person p = new Person("Alice"); // constructor called
```

---

## OOP — THE FOUR PILLARS ⭐ 🔥 MUST KNOW

---

### Q9. What is OOP? What are the 4 pillars? ⭐

**OOP (Object-Oriented Programming):** A paradigm that organizes code around **objects** (data + behavior).

**The 4 Pillars:**

| Pillar | One-line Definition |
|--------|-------------------|
| **Encapsulation** | Bundle data + methods; hide internals |
| **Inheritance** | Child class inherits parent's properties/methods |
| **Polymorphism** | Same method, different behavior depending on object |
| **Abstraction** | Hide complexity; show only necessary details |

**🧠 Remember:** **E-I-P-A** → "Every Individual Program Abstracts"

---

### Q10. Encapsulation ⭐

**Definition:** Bundling data (fields) and methods together in a class, and restricting direct access to internal data using **private** fields + **public getters/setters**.

```java
class BankAccount {
  private double balance;  // hidden

  public double getBalance() { return balance; }  // controlled access
  public void deposit(double amount) {
    if (amount > 0) balance += amount;  // validation logic
  }
}
```

**Benefits:** Data security, controlled access, maintainability.

**🧠 Remember:** Encapsulation = "capsule" — data wrapped and protected inside.

**Difference: Abstraction vs Encapsulation:**
| Abstraction | Encapsulation |
|-------------|--------------|
| Hides **complexity/implementation** | Hides **data** |
| Shows WHAT something does | Controls WHO can access it |
| Abstract class / Interface | private fields + getters/setters |

---

### Q11. Inheritance ⭐

**Definition:** A child class acquires properties and methods of a parent class using `extends`.

```java
class Animal {
  String name;
  void eat() { System.out.println(name + " eats"); }
}

class Dog extends Animal {
  void bark() { System.out.println("Woof!"); }
}

Dog d = new Dog();
d.eat();   // inherited from Animal ✅
d.bark();  // own method ✅
```

**`super` keyword:** Access parent class methods/constructor.
**`this` keyword:** Refers to the current object.

---

### Q12. Polymorphism ⭐

**Definition:** "Many forms" — one interface, multiple implementations.

**Two types:**
1. **Compile-time** (static): Method overloading — decided at compile time
2. **Runtime** (dynamic): Method overriding — decided at runtime based on actual object

```java
// Runtime polymorphism
Animal a = new Dog();  // Animal reference, Dog object
a.speak();  // calls Dog's speak() at RUNTIME
```

**Final Answer:**
> Polymorphism allows the same method/interface to behave differently based on the actual object type. Java achieves it via method overloading (compile-time) and method overriding (runtime).

---

### Q13. Abstraction ⭐

**Definition:** Hiding implementation details and showing only the interface/behavior.

**Two ways in Java:**
1. **Abstract class** — can have abstract AND concrete methods
2. **Interface** — all methods abstract by default (until Java 8 default methods)

```java
// Abstract class
abstract class Shape {
  abstract double area();  // abstract — must be implemented
  void display() { System.out.println("I am a shape"); }  // concrete
}

// Interface
interface Drawable {
  void draw();  // implicitly public abstract
  default void reset() { System.out.println("reset"); }  // Java 8+
}
```

---

### Q14. Interface vs Abstract Class ⭐

| Feature | Interface | Abstract Class |
|---------|-----------|----------------|
| Multiple inheritance | YES (implement many) | NO (extend one) |
| Fields | public static final only | Any fields |
| Methods | abstract + default (Java 8+) | abstract + concrete |
| Constructor | No | Yes |
| Use when | Define a contract/capability | Share common code |

**Can Java support multiple inheritance?**
- Multiple class inheritance: **NO** (diamond problem)
- Multiple interface implementation: **YES**

---

### Q15. `final` keyword ⭐

| Context | Effect |
|---------|--------|
| `final` variable | Cannot be reassigned |
| `final` method | Cannot be overridden |
| `final` class | Cannot be subclassed (e.g., `String`) |

---

### Q16. Java — Intermediate Concepts ⭐

**Exception handling:**
```java
try {
  int x = 10 / 0;  // ArithmeticException
} catch (ArithmeticException e) {
  System.out.println("Error: " + e.getMessage());
} finally {
  System.out.println("Always runs");  // even if exception, even if return
}
```

**Checked vs Unchecked exceptions:**
| Checked | Unchecked |
|---------|-----------|
| Compile-time (must handle) | Runtime (don't have to) |
| IOException, SQLException | NullPointerException, ArrayIndexOutOfBoundsException |

**`throw` vs `throws`:**
| `throw` | `throws` |
|---------|---------|
| Actually throw an exception | Declare that method may throw |
| `throw new Exception("msg")` | `void method() throws IOException` |

**`finally` without `catch`?** YES — `try-finally` is valid.

---

**String immutability:**
- `String` objects cannot be changed once created
- Any modification creates a **new String**
- Why? Security, thread safety, String pool optimization

**String Pool:** JVM reuses String literals to save memory
```java
String a = "hello";
String b = "hello";
a == b  // true — same pool object!

String c = new String("hello");
a == c  // false — different object
```

**StringBuilder vs StringBuffer:**
| Feature | StringBuilder | StringBuffer |
|---------|--------------|-------------|
| Thread-safe | NO | YES |
| Performance | Faster | Slower |
| Use | Single-threaded | Multi-threaded |

**Why StringBuilder for repeated modification?**
- String concatenation in loop: `"a" + "b" + "c"` creates many temporary strings
- StringBuilder uses a mutable internal buffer — much faster

---

**ArrayList vs LinkedList:**
| Feature | ArrayList | LinkedList |
|---------|-----------|-----------|
| Internal structure | Dynamic array | Doubly linked list |
| Access by index | O(1) | O(n) |
| Insert/delete middle | O(n) | O(1) |
| Best for | Random access | Frequent insert/delete |

---

**Comparable vs Comparator:**
| Feature | Comparable | Comparator |
|---------|-----------|-----------|
| Method | `compareTo()` | `compare()` |
| Where | Inside the class | Separate class/lambda |
| Use | Natural ordering | Custom ordering |

---

## 🔑 QUICK MEMORY TRICKS

- **JDK > JRE > JVM** (Russian dolls)
- **4 Pillars:** E-I-P-A (Encapsulation, Inheritance, Polymorphism, Abstraction)
- **Encapsulation** = capsule (data protected inside)
- **Polymorphism** = same method, different behavior
- **Interface = contract**, **Abstract class = partial blueprint**
- **throw** = do it, **throws** = declare it
- **StringBuilder** = fast, mutable String (no thread-safety)

---

## ⚠️ COMMON MISTAKES

1. Saying Java supports multiple inheritance — it doesn't for classes, only interfaces
2. Confusing `throw` and `throws`
3. Thinking `finally` only runs when there's no exception — it ALWAYS runs
4. Confusing overloading (compile-time) with overriding (runtime)
5. Using `==` to compare Strings — use `.equals()`
