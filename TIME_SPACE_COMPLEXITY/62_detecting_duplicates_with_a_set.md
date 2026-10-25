## Question

Find the time complexity of this function.

```python
def contains_duplicate(arr):
    seen = set()

    for x in arr:
        if x in seen:
            return True

        seen.add(x)

    return False
```

Assume the input contains `n` elements and set operations take \(O(1)\) time on average.

## Answer

- **Best case:** \(O(1)\)
- **Worst-case time:** \(O(n)\) average-case operation model
- **Auxiliary space:** \(O(n)\)

## Detailed Explanation

### Step 1: Understand the set

The set `seen` stores elements already encountered.

For every element, the function checks whether it is already present.

```python
if x in seen:
    return True
```

Set membership takes \(O(1)\) time on average.

### Step 2: Analyze the loop

If no duplicates exist, the loop visits all `n` elements.

Each iteration performs an average constant-time membership check and insertion.

Therefore:

\[
T(n)=n\times O(1)=O(n)
\]

If a duplicate appears immediately, the function returns after constant work:

\[
T(n)=O(1)
\]

### Step 3: Calculate space complexity

In the worst case, every element is unique, so the set stores all `n` elements.

\[
\boxed{O(n)\text{ auxiliary space}}
\]

## Key Takeaway

A set can reduce duplicate detection from \(O(n^2)\) with pairwise comparisons to \(O(n)\) expected time, using \(O(n)\) extra space.

**Important:** The \(O(n)\) time claim assumes average-case set operations. Pathological hash collisions can make performance worse.