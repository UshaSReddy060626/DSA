## Question

Find the total time complexity and auxiliary space complexity of appending \(n\) elements to a dynamic array that doubles its capacity whenever it becomes full.

```python
def append_all(items):
    arr = []
    capacity = 1

    for x in items:
        if len(arr) == capacity:
            capacity *= 2

            new_arr = [None] * capacity

            for i in range(len(arr)):
                new_arr[i] = arr[i]

            arr = new_arr

        arr.append(x)

    return arr
```

Assume each append takes \(O(1)\), excluding resizing, and copying one element takes \(O(1)\).

## Answer

- **Total Time Complexity:** \(O(n)\) amortized
- **Auxiliary Space Complexity:** \(O(n)\)

## Detailed Explanation

**Step 1: Analyze the outer loop**

The loop processes \(n\) elements.

Normal append operations take \(O(1)\).

Total normal append cost:

\[
O(n)
\]

**Step 2: Analyze resizing**

The capacity doubles:

\[
1,2,4,8,16,\ldots
\]

When resizing occurs, existing elements are copied.

The total number of copied elements is approximately:

\[
1+2+4+8+\cdots
\]

Up to the largest power of 2 smaller than \(n\).

Using the geometric series:

\[
1+2+4+\cdots < 2n
\]

Therefore, total copying work is \(O(n)\).

**Step 3: Calculate total time**

\[
O(n)+O(n)=\boxed{O(n)}
\]

This is the amortized cost across all append operations. A single append that triggers resizing can still take \(O(n)\).

**Step 4: Calculate auxiliary space**

The new array can hold up to approximately \(2n\) elements in the worst case.

Therefore, auxiliary space is:

\[
\boxed{O(n)}
\]

## Key Takeaway

An individual resizing operation can take \(O(n)\), but appending \(n\) elements to a doubling dynamic array takes \(O(n)\) total time, or \(O(1)\) amortized time per append.