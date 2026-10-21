## Question

Find the time complexity of this Python code.

```python
def build_string(n):
    result = ""

    for i in range(n):
        result += "a"

    return result
```

## Answer

**Typical time complexity: \(O(n^2)\)** for this repeated immutable-string concatenation pattern.

## Explanation

### Step 1: Understand strings

Python strings are immutable, meaning their contents cannot be changed in place.

When concatenation creates a new string, existing characters may need to be copied.

### Step 2: Count the work

During successive iterations, the string grows:

- First iteration: approximately 1 character copied.
- Second iteration: approximately 2 characters copied.
- Third iteration: approximately 3 characters copied.
- Final iteration: approximately `n` characters copied.

### Step 3: Add the work

\[
T(n)=1+2+3+\cdots+n
\]

Using the sum formula:

\[
T(n)=\frac{n(n+1)}{2}
\]

Therefore, under the usual copying-cost model:

\[
\boxed{O(n^2)}
\]

**Python implementation note:** Exact performance can depend on the interpreter and whether concatenation optimizations apply. For predictable efficient construction, prefer collecting pieces and joining them.

```python
def build_string(n):
    parts = []

    for i in range(n):
        parts.append("a")

    return "".join(parts)
```

This approach takes \(O(n)\) time overall.

## Key Takeaway

Repeatedly rebuilding an immutable object inside a loop can increase complexity. For strings, consider using a list of pieces followed by `"".join(parts)` when constructing a large result.