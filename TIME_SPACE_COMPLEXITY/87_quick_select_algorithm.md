## Question

Given an unsorted array of \(n\) elements, find the \(k\)-th smallest element using Quick Select.

Determine the average-case and worst-case time complexities.

**Answer:**

- Average Time Complexity: \(O(n)\)
- Worst Time Complexity: \(O(n^2)\)
- Auxiliary Space Complexity: \(O(1)\) for iterative in-place Quick Select.

### Explanation

Quick Select is used to find the \(k\)-th smallest element without completely sorting the array.

Example:

```python
arr = [7, 2, 9, 4, 1]
k = 3
```

The sorted array would be:

```python
[1, 2, 4, 7, 9]
```

The 3rd smallest element is `4`.

**Step 1: Choose a pivot**

Select one element as the pivot.

**Step 2: Partition the array**

Arrange elements so that:

- Smaller elements come before the pivot.
- Larger elements come after the pivot.

**Step 3: Check the pivot position**

- If the pivot is at position \(k-1\), we have found the answer.
- If it is after the required position, search only the left part.
- If it is before the required position, search only the right part.

**Step 4: Calculate average complexity**

On average, partitioning processes approximately \(n\) elements, then continues on a smaller portion of the array.

The total work forms a decreasing series:

\[
n+\frac{n}{2}+\frac{n}{4}+\cdots
\]

Therefore:

\[
T(n)=O(n)
\]

**Step 5: Calculate worst-case complexity**

If the pivot repeatedly becomes the smallest or largest element, almost the entire array is processed each time.

\[
n+(n-1)+(n-2)+\cdots+1
\]

Therefore:

\[
T(n)=O(n^2)
\]

### Key Takeaway

Quick Select finds the \(k\)-th smallest element without fully sorting the array.

- Average time: \(O(n)\)
- Worst time: \(O(n^2)\)
- Auxiliary space: \(O(1)\) for an iterative in-place implementation.