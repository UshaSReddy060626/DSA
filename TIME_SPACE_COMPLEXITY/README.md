# 📅 Day 1 – Time Complexity & Big O

## 📌 Overview

Today, I learned the fundamentals of **Time Complexity** and **Big O Notation**, which are essential concepts in Data Structures and Algorithms (DSA). Understanding these concepts helps in analyzing how efficiently an algorithm performs as the input size increases.

---

# 📚 Topics Covered

## 1. What is an Algorithm?

* Definition of an algorithm
* Characteristics of a good algorithm
* Input → Process → Output
* Real-life examples of algorithms

---

## 2. Why Analyze Algorithms?

* Importance of algorithm efficiency
* Time vs Space Trade-off
* Scalability of algorithms

---

## 3. Time Complexity

Learned the following time complexities:

* **O(1)** – Constant Time
* **O(log n)** – Logarithmic Time
* **O(n)** – Linear Time
* **O(n log n)** – Linearithmic Time
* **O(n²)** – Quadratic Time
* **O(n³)** – Cubic Time
* **O(2ⁿ)** – Exponential Time
* **O(n!)** – Factorial Time

---

## 4. Big O Notation

* Definition of Big O
* Growth rate of algorithms
* Ignoring constants and lower-order terms

Examples:

```text
5n + 10 → O(n)

3n² + 5n + 2 → O(n²)
```

---

## 5. Best, Average, and Worst Case

* Best Case
* Average Case
* Worst Case

Example:

* Linear Search

---

## 6. Rules for Calculating Time Complexity

Learned how to analyze:

* Single loops
* Consecutive loops
* Nested loops
* Loops with `if` statements
* Loops that divide or multiply by 2
* Basic recursive functions

---

## 7. Space Complexity

* Definition
* Auxiliary Space vs Input Space
* Examples of:

  * **O(1)**
  * **O(n)**
  * **O(n²)**

---

## 8. Complexity of Common Python Operations

Studied the average time complexity of:

| Operation              | Complexity       |
| ---------------------- | ---------------- |
| List Indexing          | O(1)             |
| append()               | O(1) *(Average)* |
| pop() *(last element)* | O(1)             |
| insert() *(beginning)* | O(n)             |
| Dictionary Lookup      | O(1)             |
| Set Lookup             | O(1)             |
| List Slicing           | O(k)             |

---

## 9. Complexity Order

```text
O(1)
   ↓
O(log n)
   ↓
O(n)
   ↓
O(n log n)
   ↓
O(n²)
   ↓
O(n³)
   ↓
O(2ⁿ)
   ↓
O(n!)
```

---

# 💻 Practice Completed

Solved time complexity problems involving:

* ✅ Single Loop
* ✅ Consecutive Loops
* ✅ Nested Loops
* ✅ Three Nested Loops
* ✅ Loop with an `if` Statement
* ✅ Loop that Divides by 2
* ✅ Loop that Doubles by 2
* ✅ Constant Inner Loop
* ✅ Array Indexing
* ✅ List `append()`

---

# 🎯 Key Takeaways

* Learned how to estimate the time complexity of simple programs.
* Understood how different algorithms scale as input size increases.
* Learned to distinguish between efficient and inefficient algorithms.
* Practiced identifying common Big O patterns.
* Gained a foundational understanding of Space Complexity.

---

