## Question

Find the worst-case time and auxiliary space complexity.

```python
def generate(n, path):
    if len(path) == n:
        print(path)
        return

    for i in range(n):
        if i not in path:
            path.append(i)
            generate(n, path)
            path.pop()

generate(n, [])
```

Assume checking membership in `path` takes \(O(n)\) time and printing a complete path takes \(O(n)\) time.

## Answer

- **Time Complexity:** \(O(n \cdot n!)\)
- **Auxiliary Space Complexity:** \(O(n)\), excluding printed output.

## Detailed Explanation

**Step 1: Understand the choices**

The function generates every possible arrangement of the numbers from \(0\) to \(n-1\).

Each number can be selected only once.

**Step 2: Count the recursive calls**

The number of complete arrangements is:

\[
n!
\]

The recursion explores permutations of different lengths as well, but the total number of recursion-tree nodes is also \(O(n!)\).

**Step 3: Analyze membership checking**

```python
if i not in path:
```

Checking whether an element exists in the list takes \(O(n)\) in the worst case.

Each recursive node can perform up to \(n\) membership checks.

A simple safe upper bound for the total search work is:

\[
O(n\cdot n!)
\]

**Step 4: Analyze printing**

There are \(n!\) complete permutations.

Each printed permutation contains \(n\) elements.

Therefore:

\[
O(n\cdot n!)
\]

Printing has the same order as the search upper bound.

**Step 5: Calculate auxiliary space**

The maximum recursion depth is \(n\).

The `path` list stores at most \(n\) elements.

Therefore:

\[
\boxed{O(n)}
\]

This excludes the output storage. If every permutation is stored, output space is \(O(n\cdot n!)\).

## Key Takeaway

Backtracking can generate factorially many possibilities. Always distinguish the recursion's working memory from the memory used to store all generated results.