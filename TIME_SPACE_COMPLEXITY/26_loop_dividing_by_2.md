## 📝 Question

Find the Time Complexity:

```python
i = n

while i > 0:
    print(i)
    i = i // 2
```

## ✅ Answer

**O(log n)**

## Explanation

The important part is:

```python
i = i // 2
```

The value of `i` is divided by 2 after every iteration.

For example, if:

```text
n = 32
```

The values become:

```text
32 → 16 → 8 → 4 → 2 → 1
```

Only about **6 iterations** are needed.

For a larger `n`, the number of iterations grows very slowly.

The number of times we can divide `n` by 2 until reaching 1 is:

```text
log₂(n)
```

Therefore:

```text
Time Complexity = O(log n)
```

## 💡 Key Idea

Whenever you see a loop where the variable is repeatedly:

```python
i = i // 2
```

or

```python
i = i / 2
```

think:

**O(log n)**

### Quick Pattern

```python
while i > 0:
    i = i // 2
```

→ **O(log n)**
