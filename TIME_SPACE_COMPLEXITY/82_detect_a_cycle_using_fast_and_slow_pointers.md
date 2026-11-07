## Question

Given a linked list containing \(n\) nodes, determine whether it has a cycle using the Fast and Slow Pointer technique.

Find the time and space complexity.

**Answer:**

- Time Complexity: \(O(n)\)
- Auxiliary Space Complexity: \(O(1)\)

## Explanation

The Fast and Slow Pointer technique uses two pointers:

- Slow pointer moves one step at a time.
- Fast pointer moves two steps at a time.

**Step 1: Initialize pointers**

Both pointers start at the head of the linked list.

**Step 2: Move the pointers**

In every iteration:

- Move slow by one node.
- Move fast by two nodes.

**Step 3: Check for a cycle**

If the linked list contains a cycle, the fast pointer will eventually meet the slow pointer.

If the fast pointer reaches `None`, the linked list has no cycle.

**Step 4: Calculate time complexity**

In a linked list with a cycle, the two pointers eventually meet. In a list without a cycle, the fast pointer reaches the end.

The number of pointer movements is bounded by a constant multiple of \(n\).

Therefore:

\[
T(n)=O(n)
\]

**Step 5: Calculate space complexity**

Only two pointers are used.

No additional array, stack, or data structure is required.

Therefore:

\[
S(n)=O(1)
\]

### Key Takeaway

Fast and Slow Pointers detect cycles efficiently.

- Time: \(O(n)\)
- Auxiliary space: \(O(1)\)

This technique is also called Floyd's Cycle Detection Algorithm.