## Question

What is the time complexity of the following code?

```python id="m6b4tw"
for i in range(n):
    for j in range(n):
        for k in range(n):
            print(i, j, k)
```

---

## Solution

**Time Complexity:** `O(n³)`

### Explanation

* The outer loop runs `n` times.
* The middle loop runs `n` times for each iteration of the outer loop.
* The inner loop also runs `n` times for each iteration of the middle loop.

Total operations:

```text id="u0y3l9"
n × n × n = n³
```

Therefore, the overall time complexity is:

```text id="w7f9ce"
O(n³)
```
