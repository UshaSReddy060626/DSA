## Question

What is the time complexity of the following code?

```python
for i in range(n):
    print(i)

for j in range(n):
    print(j)
```

---

## Solution

**Time Complexity:** `O(n)`

### Explanation

* The first loop runs `n` times.
* The second loop also runs `n` times.

Total operations:

```text
n + n = 2n
```

In Big O notation, constant factors are ignored.

```text
2n → O(n)
```

Therefore, the overall time complexity is:

```text
O(n)
```
