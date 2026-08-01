## Question

What is the time complexity of the following code?

```python id="9vmb8a"
for i in range(n):
    for j in range(10):
        print(i, j)
```

---

## Solution

**Time Complexity:** `O(n)`

### Explanation

* The outer loop runs `n` times.
* The inner loop always runs **10** times, regardless of the value of `n`.

Total operations:

```text id="5zd6e6"
n × 10 = 10n
```

In Big O notation, constant factors are ignored.

```text id="q4z5hj"
10n → O(n)
```

Therefore, the overall time complexity is:

```text id="vxgb8d"
O(n)
```
