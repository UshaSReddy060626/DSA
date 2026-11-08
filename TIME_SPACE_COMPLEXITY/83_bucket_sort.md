## Question

Given an array of \(n\) numbers distributed uniformly between 0 and 1, sort the elements using Bucket Sort.

Find the average-case and worst-case time complexities.

**Answer:**

- Average Time Complexity: \(O(n)\)
- Worst Time Complexity: \(O(n^2)\)
- Auxiliary Space Complexity: \(O(n)\)

## Explanation

Bucket Sort divides elements into smaller groups called buckets.

**Step 1: Create buckets**

Create \(n\) empty buckets to store the elements.

**Step 2: Distribute elements**

Place each element into its appropriate bucket based on its value.

For example:

```python
arr = [0.42, 0.32, 0.23, 0.52, 0.25]
```

The elements are distributed into different buckets according to their values.

**Step 3: Sort individual buckets**

Sort the elements inside each bucket.

When elements are distributed uniformly, each bucket contains only a few elements.

**Step 4: Combine buckets**

Collect the sorted elements from all buckets to get the final sorted array.

**Step 5: Calculate complexity**

- Creating buckets: \(O(n)\)
- Distributing elements: \(O(n)\)
- Sorting buckets: \(O(n)\) on average under uniform distribution.
- Combining buckets: \(O(n)\)

Therefore, average time complexity is:

\[
\boxed{O(n)}
\]

If all elements fall into one bucket, sorting that bucket can take \(O(n^2)\) using insertion sort.

Therefore, worst-case complexity is:

\[
\boxed{O(n^2)}
\]

### Key Takeaway

Bucket Sort performs efficiently when elements are uniformly distributed.

- Average time: \(O(n)\)
- Worst time: \(O(n^2)\)
- Auxiliary space: \(O(n)\)