## Question

Given an array of \(n\) integers where every element lies between 0 and \(k\), sort the array using Counting Sort.

Determine the time and space complexity.

**Answer:**

- Time Complexity: \(O(n+k)\)
- Auxiliary Space Complexity: \(O(n+k)\) for the standard stable implementation.

### Explanation

Counting Sort sorts elements by counting how many times each value appears instead of directly comparing elements.

**Step 1: Create a count array**

Create an array of size \(k+1\), initialized with zeros.

Each position represents a possible input value.

**Step 2: Count occurrences**

Traverse the input array and increase the count for every encountered value.

Example:

```python
arr = [4, 2, 2, 8, 3, 3, 1]
```

The count array records:

- 1 appears once.
- 2 appears twice.
- 3 appears twice.
- 4 appears once.
- 8 appears once.

**Step 3: Calculate cumulative counts**

Convert the frequency array into cumulative counts.

These counts help determine the correct positions of elements in the sorted output.

**Step 4: Build the sorted array**

Place each element into its correct position using the cumulative counts.

**Step 5: Calculate complexity**

- Counting elements: \(O(n)\)
- Creating and processing count array: \(O(k)\)
- Building output: \(O(n)\)

Therefore:

\[
T(n)=O(n+k)
\]

The count array and output array require \(O(k+n)\) auxiliary space.

\[
S(n)=O(n+k)
\]

### Key Takeaway

Counting Sort is efficient when the range of input values is relatively small.

- Time: \(O(n+k)\)
- Auxiliary space: \(O(n+k)\)
- It is a non-comparison-based sorting algorithm.