## Question

Given an AVL Tree containing \(n\) nodes, determine the time complexity of insertion, deletion, and searching.

**Answer:**

- Search: \(O(\log n)\)
- Insertion: \(O(\log n)\)
- Deletion: \(O(\log n)\)
- Space Complexity: \(O(n)\) for storing the tree.

### Explanation

An AVL Tree is a self-balancing Binary Search Tree (BST).

It maintains balance so that one side of the tree does not become significantly taller than the other.

**Step 1: Understand the balance factor**

The balance factor is calculated as:

\[
BF=Height(Left)-Height(Right)
\]

For an AVL Tree, the balance factor of every node must be -1, 0, or 1.

**Step 2: Searching**

Searching follows the Binary Search Tree property.

At every step, we move either left or right.

Because the tree remains balanced, its height is \(O(\log n)\).

Therefore:

\[
T(n)=O(\log n)
\]

**Step 3: Insertion and deletion**

After inserting or deleting a node:

- Update the heights.
- Check the balance factors.
- Perform rotations if the tree becomes unbalanced.

Since the tree height is logarithmic, insertion and deletion take \(O(\log n)\).

**Step 4: Calculate space complexity**

The tree stores \(n\) nodes.

Therefore:

\[
S(n)=O(n)
\]

### Key Takeaway

AVL Trees maintain balance to keep operations efficient.

- Search: \(O(\log n)\)
- Insertion: \(O(\log n)\)
- Deletion: \(O(\log n)\)
- Space: \(O(n)\)