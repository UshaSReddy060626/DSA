## Question

What is the time complexity of the following code?

```python id="v8y1nk"
i = n

while i > 1:
    print(i)
    i = i // 2
```

---

## Solution

**Time Complexity:** `O(log n)`

### Explanation

* Initially, `i = n`.
* In every iteration, the value of `i` is divided by `2`.

The values of `i` will look like this:

```text id="ewopmk"
n
n/2
n/4
n/8
n/16
...
1
```

Since the value is reduced by half every iteration, the number of iterations grows logarithmically with the input size.

Therefore, the overall time complexity is:

```text id="a7y3mk"
O(log n)
```
