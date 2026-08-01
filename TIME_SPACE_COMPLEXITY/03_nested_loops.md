## Question

What is the time complexity of the following code?

```python
for i in range(n):
    for j in range(n):
        print(i, j)
```

---

## Solution

**Time Complexity:** `O(n²)`

### Explanation

* The outer loop runs `n` times.
* For each iteration of the outer loop, the inner loop also runs `n` times.

Total operations:

```text
n × n = n²
```

Therefore, the overall time complexity is:

```text
O(n²)
```
