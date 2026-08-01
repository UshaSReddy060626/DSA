## Question

What is the time complexity of the following code?

```python
for i in range(n):
    print(i)
```

---

## Solution

**Time Complexity:** `O(n)`

### Explanation

* The loop runs from `0` to `n-1`.
* Therefore, it executes **`n` times**.
* Each iteration performs one constant-time operation (`print()`).

Total operations = `n`

Hence, the time complexity is:

```text
O(n)
```
