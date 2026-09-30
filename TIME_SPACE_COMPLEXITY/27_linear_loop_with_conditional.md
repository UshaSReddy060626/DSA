## 📝 Question

Find the Time Complexity:

```python
for i in range(n):
    if i % 2 == 0:
        print(i)
```

## ✅ Answer

**O(n)**

## Explanation

The outer loop runs from `0` to `n-1`.

So it runs approximately:

```text
n times
```

Inside the loop, we have:

```python
i % 2 == 0
```

The modulo operation takes constant time:

```text
O(1)
```

The `if` condition is checked during every iteration.

Even though `print()` happens only for even numbers, the loop still checks **every value**.

Therefore:

```text
n × O(1) = O(n)
```

### 💡 Key Idea

Don't count only the number of times the `if` body executes.

Count how many times the **loop and condition are evaluated**.

**Final Answer: O(n)**
