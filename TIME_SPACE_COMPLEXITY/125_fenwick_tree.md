## Question

Find the time and auxiliary space complexity of the following operations.

```python
def process(arr, operations):
    n = len(arr)
    bit = [0] * (n + 1)

    def update(i, value):
        while i <= n:
            bit[i] += value
            i += i & -i

    def query(i):
        total = 0
        while i > 0:
            total += bit[i]
            i -= i & -i
        return total

    for i in range(1, n + 1):
        update(i, arr[i - 1])

    for op in operations:
        if op[0] == "update":
            update(op[1], op[2])
        else:
            query(op[1])

```

Assume there are \(n\) array elements and \(q\) operations.

## Answer

- **Time Complexity:** \(O((n+q)\log n)\)
- **Auxiliary Space Complexity:** \(O(n)\)

## Explanation

### Step 1: Creating the Fenwick Tree

```python
bit = [0] * (n + 1)
```

This creates an array of size \(n+1\).

Time: \(O(n)\)  
Space: \(O(n)\)

### Step 2: Understanding update()

```python
while i <= n:
    bit[i] += value
    i += i & -i
```

The index moves forward by its lowest set bit.

This skips through selected positions rather than visiting every element.

The number of iterations is at most proportional to \(\log n\).

Time per update: \(O(\log n)\)

### Step 3: Understanding query()

```python
while i > 0:
    total += bit[i]
    i -= i & -i
```

The index moves backward by its lowest set bit.

It also takes at most \(O(\log n)\) operations.

Time per query: \(O(\log n)\)

### Step 4: Building the tree

```python
for i in range(1, n + 1):
    update(i, arr[i - 1])
```

This loop runs \(n\) times.

Each update costs \(O(\log n)\).

Therefore:

\[
O(n\log n)
\]

### Step 5: Processing operations

There are \(q\) operations.

Each operation performs either one update or one query, both taking \(O(\log n)\).

Therefore:

\[
O(q\log n)
\]

### Step 6: Total complexity

\[
O(n\log n+q\log n)
\]

Taking the common factor:

\[
\boxed{O((n+q)\log n)}
\]

The Fenwick Tree uses an array of size \(n+1\), so auxiliary space is:

\[
\boxed{O(n)}
\]

## Key Takeaway

- One Fenwick Tree update: \(O(\log n)\)
- One Fenwick Tree prefix query: \(O(\log n)\)
- Building using repeated updates: \(O(n\log n)\)
- Multiple operations: count how many operations occur and multiply by their individual cost.