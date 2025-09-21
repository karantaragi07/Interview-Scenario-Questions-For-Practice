# ![Java](https://img.shields.io/badge/Java-Programming-red?style=for-the-badge) ![Interview](https://img.shields.io/badge/Interview-Questions-blue?style=for-the-badge) ![Production Ready](https://img.shields.io/badge/Production-Ready-green?style=for-the-badge)

## Table of Contents
- [Java Basics](#java-basics)
- [OOP Concepts](#oop-concepts)
- [Collections](#collections)
- [Exception Handling](#exception-handling)
- [Multithreading & Concurrency](#multithreading--concurrency)
- [Streams & Lambda Expressions](#streams--lambda-expressions)
- [Java 8/11 Features](#java-811-features)
- [JVM & Memory Management](#jvm--memory-management)
- [Garbage Collection](#garbage-collection)
- [JDBC](#jdbc)
- [Production-Level Questions](#production-level-questions)
- [Best Practices](#best-practices)
- [Java Commands / Tools Cheat Sheet](#java-commands--tools-cheat-sheet)

---

<details>
<summary><strong>Java Basics</strong></summary>

### ⚡ Difference between JDK, JRE, and JVM
- JVM runs bytecode, JRE provides JVM + libraries, JDK provides JRE + dev tools.

### ⚡ Difference between `==` and `.equals()`
- `==` compares references, `.equals()` compares object content.

### Primitive data types
- byte, short, int, long, float, double, char, boolean.

### ⚡ Difference between `final`, `finally`, and `finalize()`
- `final`: constants or prevent inheritance/overriding.  
- `finally`: block executed after try-catch.  
- `finalize()`: called before GC destroys an object.

### ⚡ String vs StringBuilder vs StringBuffer
- String: immutable.  
- StringBuilder: mutable, fast, not thread-safe.  
- StringBuffer: mutable, thread-safe, slower.

### ⚡ String immutability reason
- Security, thread-safety, caching in String pool.

### How concatenation works with Strings
- Compiler uses `StringBuilder` internally for `+` operations.

</details>

---

<details>
<summary><strong>OOP Concepts</strong></summary>

### ⚡ Polymorphism
- One object can take many forms; includes overloading (compile-time) and overriding (runtime).

### Abstract class vs Interface
- Abstract class: methods with/without implementation, constructors, fields.  
- Interface: method declarations (Java 8+ allows default/static methods), supports multiple inheritance.

### Encapsulation
- Wrapping data and methods in a class; control access with getters/setters.

### Inheritance
- Mechanism to derive a class from another to reuse code.

### ⚡ Method Overloading vs Overriding
- Overloading: same name, different params, compile-time.  
- Overriding: subclass changes parent method behavior, runtime.

</details>

---

<details>
<summary><strong>Collections</strong></summary>

### List vs Set vs Map
- List: ordered, allows duplicates.  
- Set: unordered, no duplicates.  
- Map: key-value, unique keys.

### ⚡ HashMap vs Hashtable vs ConcurrentHashMap
- HashMap: not synchronized, allows null keys/values.  
- Hashtable: synchronized, no null keys/values.  
- ConcurrentHashMap: thread-safe, efficient concurrency.

### ArrayList vs LinkedList
- ArrayList: index-based, fast random access.  
- LinkedList: node-based, fast insert/remove.

### Fail-fast vs Fail-safe iterators
- Fail-fast: throws ConcurrentModificationException (ArrayList).  
- Fail-safe: works on clone, no exception (ConcurrentHashMap).

</details>

---

<details>
<summary><strong>Exception Handling</strong></summary>

### Checked vs Unchecked Exceptions
- Checked: compiler-enforced (IOException).  
- Unchecked: runtime errors (NullPointerException).

### Custom exceptions
- Extend Exception for checked, RuntimeException for unchecked.

### try-with-resources
- Auto-closes resources like files or streams.

### throw vs throws
- throw: explicitly throw exception.  
- throws: declare exceptions a method may throw.

</details>

---

<details>
<summary><strong>Multithreading & Concurrency</strong></summary>

### ⚡ synchronized vs volatile
- synchronized: mutual exclusion + visibility.  
- volatile: visibility only, no locking.

### ExecutorService
- Manages thread pool and task submission efficiently.

### Runnable vs Callable
- Runnable: no return, cannot throw checked exceptions.  
- Callable: returns result, can throw checked exceptions.

### Avoid deadlocks
- Acquire locks in consistent order, minimize scope, use tryLock.

### ThreadLocal
- Thread-local variable; each thread has its own copy.

</details>

---

<details>
<summary><strong>Streams & Lambda Expressions</strong></summary>

### ⚡ Stream
- Functional processing of collections; supports map, filter, reduce.

### map vs flatMap
- map: one-to-one mapping.  
- flatMap: flattens nested collections.

### Optional
- Container that may/may not hold a value; avoids NullPointerException.

### Lambda syntax
```java
(int a, int b) -> a + b
```
</details>

---

<details> <summary><strong>Java 8/11 Features</strong></summary>
Default vs static methods

- Default: method with implementation in interface.

- Static: belongs to interface, not instance.

Functional interface

- Interface with single abstract method (Runnable, Callable, Comparator).

LocalDate vs Date

- LocalDate: immutable, thread-safe.

- Date: mutable, older API.

parallelStream

- Allows multi-core processing automatically.

</details>

---

<details> <summary><strong>JVM & Memory Management</strong></summary>
JVM memory areas

- Heap, Stack, Metaspace, Code Cache, PC Registers.

Stack vs Heap

- Stack: method calls, primitives, short-lived.

- Heap: objects, garbage collected.

ClassLoader

- Loads classes into JVM at runtime (Bootstrap, Extension, Application).

</details>

---

<details> <summary><strong>Garbage Collection</strong></summary>
How GC works

- Frees memory of unreachable objects automatically.

GC algorithms

- Serial, Parallel, CMS, G1.

Forcing GC

- System.gc() requests GC (not guaranteed immediately).

⚡ Memory leaks

- Objects unintentionally referenced prevent GC.

</details>

---

<details> <summary><strong>JDBC</strong></summary>
Connecting to DB

- DriverManager.getConnection(url, user, pass) or DataSource.

Statement vs PreparedStatement vs CallableStatement

- Statement: simple SQL, prone to injection.

- PreparedStatement: precompiled, safer.

- CallableStatement: calls stored procedures.

Transaction management

- Use commit() and rollback() for atomicity.

</details>

---

<details> <summary><strong>Production-Level Questions</strong></summary>
⚡ Detect memory leaks

- Use heap dump analysis with VisualVM/Eclipse MAT.

Performance improvement with collections

- Choose proper data structures, avoid unnecessary synchronization.

Concurrency issues

- Use Concurrent collections, locks, atomic operations.

GC tuning

- Pick GC type based on workload (G1: low-latency, Parallel: throughput).

⚡ Debug slow apps

- Profile, analyze thread dumps, GC logs, monitor performance.

</details>

---

<details> <summary><strong>Best Practices</strong></summary>

- Prefer immutability (final) for thread safety.

- Use StringBuilder for heavy string ops.

- Always close resources (try-with-resources).

- Avoid unnecessary object creation in loops.

- Use Concurrent collections for multi-threaded apps.

- Handle exceptions gracefully.

- Write unit tests.

- Follow proper naming conventions and document code.

</details>

---

<details> <summary><strong>Java Commands / Tools Cheat Sheet</strong></summary>

- javac FileName.java → Compile Java file.

- java ClassName → Run compiled class.

- jar cf app.jar *.class → Create JAR file.

- jar xf app.jar → Extract JAR.

- javadoc FileName.java → Generate documentation.

- jdb ClassName → Debug Java app.

- java -Xmx512m ClassName → Set max heap size.

- java -version → Check Java version.

</details>

