## Question

Given an array of \(n\) elements, construct a Segment Tree to answer range sum queries and update individual elements.

Determine the time and space complexity.

**Answer:**

- Construction: \(O(n)\)
- Range Sum Query: \(O(\log n)\)
- Point Update: \(O(\log n)\)
- Space Complexity: \(O(n)\)

### Explanation

A Segment Tree is a tree-based data structure used to answer queries on a range of array elements efficiently.

Example:

```python
arr = [2, 4, 6, 8, 10]
```

Suppose we want the sum of elements from index 1 to index 3.

\[
4+6+8=18
\]

**Step 1: Build the Segment Tree**

The tree stores sums of different portions of the array.

- Leaf nodes store individual elements.
- Parent nodes store the sum of their child nodes.

Building the complete tree takes:

\[
O(n)
\]

**Step 2: Perform a range sum query**

To calculate the sum between two indices, the tree checks only the required segments.

It avoids visiting every element individually.

The tree height is approximately \(\log n\).

Therefore:

\[
O(\log n)
\]

**Step 3: Update an element**

Suppose the value at index 2 changes from 6 to 12.

The tree updates the corresponding leaf node and recalculates the sums of its ancestors.

Only one path from the leaf to the root is updated.

Therefore:

\[
O(\log n)
\]

**Step 4: Calculate space complexity**

A Segment Tree requires approximately \(4n\) array positions in a common implementation.

Ignoring constant factors:

\[
S(n)=O(n)
\]

### Key Takeaway

Segment Trees are useful when we need frequent range queries and updates.

- Construction: \(O(n)\)
- Range query: \(O(\log n)\)
- Point update: \(O(\log n)\)
- Space: \(O(n)\)