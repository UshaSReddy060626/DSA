## Question

What is the time complexity of the following code?

```python id="bq1zkw"
i = 1

while i < n:
    print(i)
    i = i * 2
```

---

## Solution

**Time Complexity:** `O(log n)`

### Explanation

* Initially, `i = 1`.
* In every iteration, the value of `i` is multiplied by `2`.

The values of `i` will look like this:

```text id="mrvvht"
1
2
4
8
16
32
...
n
```

Since the value doubles every iteration, the number of iterations grows logarithmically with the input size.

Therefore, the overall time complexity is:

```text id="vj9h4k"
O(log n)
```
