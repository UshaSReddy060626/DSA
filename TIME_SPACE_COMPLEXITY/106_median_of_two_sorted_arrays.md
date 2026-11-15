## Question

Given two sorted arrays of lengths \(m\) and \(n\), find their median without completely merging the arrays.

Determine the time and space complexity using Binary Search.

Example:

```python
arr1 = [1, 3]
arr2 = [2]
```

Output:

```python
2
```

**Answer:**

- Time Complexity: \(O(\log(\min(m,n)))\)
- Auxiliary Space Complexity: \(O(1)\)

### Explanation

The median is the middle value of a sorted collection.

Instead of merging both arrays, we use Binary Search to find a correct partition.

**Step 1: Select the smaller array**

Always perform Binary Search on the smaller array to reduce the number of search operations.

**Step 2: Divide both arrays**

Choose a partition in the first array.

Calculate the corresponding partition in the second array so that the left half contains half of the total elements.

**Step 3: Check the partition**

A correct partition satisfies:

\[
LeftA\leq RightB
\]

and

\[
LeftB\leq RightA
\]

These conditions ensure that every element on the left is less than or equal to every element on the right.

**Step 4: Adjust Binary Search**

- If the first condition is violated, move the partition left.
- If the second condition is violated, move the partition right.
- Otherwise, the correct partition is found.

**Step 5: Calculate the median**

If the total number of elements is odd, take the maximum value on the left side.

If it is even, calculate:

\[
Median=\frac{\max(Left)+\min(Right)}{2}
\]

**Step 6: Calculate complexity**

Binary Search is performed on the smaller array.

Therefore:

\[
\boxed{O(\log(\min(m,n)))}
\]

Only a fixed number of variables are used.

\[
\boxed{O(1)}
\]

### Key Takeaway

Median of Two Sorted Arrays uses Binary Search on partitions instead of merging the arrays.

- Time: \(O(\log(\min(m,n)))\)
- Auxiliary space: \(O(1)\)