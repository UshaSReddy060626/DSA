## 📝 Question

Find the **Best Case, Average Case, and Worst Case Time Complexity** of the following code:

```python
arr = [10, 20, 30, 40, 50]
target = 40

for i in range(len(arr)):
    if arr[i] == target:
        print("Found")
        break
```

---

## Explanation

This is an example of **Linear Search**.

The program checks each element one by one until it finds the target.

---

### 🟢 Best Case

Suppose the target is the **first element**:

```text
arr = [40, 20, 30, 50]
```

The program checks:

```text
40 → Found
```

Only **one comparison** is needed.

Therefore:

```text
Best Case = O(1)
```

---

### 🟡 Average Case

Suppose the target is somewhere around the middle.

The program may need to check approximately half of the elements.

That is roughly:

```text
n / 2
```

operations.

Ignoring the constant:

```text
Average Case = O(n)
```

---

### 🔴 Worst Case

The target could be the last element:

```text
[10, 20, 30, 40, 50]
```

The program must check almost every element.

It may perform approximately `n` comparisons.

Therefore:

```text
Worst Case = O(n)
```

---

## 📊 Summary

| Case         | Time Complexity |
| ------------ | --------------- |
| Best Case    | `O(1)`          |
| Average Case | `O(n)`          |
| Worst Case   | `O(n)`          |

## 🧠 Key Point

This is why **Best Case, Average Case, and Worst Case** are important when analyzing algorithms.

## ✅ Final Answer

**Best Case: `O(1)`**

**Average Case: `O(n)`**

**Worst Case: `O(n)`**
