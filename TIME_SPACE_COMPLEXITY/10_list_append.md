## Question

What is the time complexity of the following code?

```python
arr = [10, 20, 30]

arr.append(40)
```

---

## Solution

**Time Complexity:** `O(1)` (Average Case)

### Explanation

* `append()` adds an element to the **end** of the list.
* Most of the time, Python places the new element directly at the end.
* Therefore, it takes constant time.

Hence, the overall time complexity is:

```text
O(1)
```

