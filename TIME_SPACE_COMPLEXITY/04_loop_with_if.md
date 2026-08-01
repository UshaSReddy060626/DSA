## Question

What is the time complexity of the following code?

```python
for i in range(n):
    if i % 2 == 0:
        print(i)
```

---

## Solution

**Time Complexity:** `O(n)`

### Explanation

* The loop runs `n` times.
* The `if` condition is checked during every iteration.
* Checking the condition `i % 2 == 0` takes constant time, i.e., `O(1)`.

Total operations:

```text
n × O(1) = O(n)
```

Even though `print()` is executed only for even numbers, the loop still checks all `n` elements.

Therefore, the overall time complexity is:

```text
O(n)
```
