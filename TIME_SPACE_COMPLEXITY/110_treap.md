## Question

What is the time complexity of searching, inserting, and deleting an element in a Treap?

```python
class Node:
    def __init__(self, key, priority):
        self.key = key
        self.priority = priority
        self.left = None
        self.right = None

def search(root, key):
    if root is None or root.key == key:
        return root

    if key < root.key:
        return search(root.left, key)

    return search(root.right, key)
```

## Answer

- **Average / Expected Time Complexity:** \(O(\log n)\)
- **Worst-Case Time Complexity:** \(O(n)\)
- **Space Complexity:** \(O(n)\) for storing the tree.

## Explanation

1. A Treap combines a Binary Search Tree (BST) and a Heap.
2. Each node has a key and a randomly assigned priority.
3. The BST property keeps smaller keys on the left and larger keys on the right.
4. Random priorities help maintain a balanced tree on average.
5. Searching follows one path from the root to a leaf.
6. In a balanced tree, the height is approximately \(\log n\), so searching takes \(O(\log n)\).
7. If the tree becomes completely skewed, its height can become \(n\), resulting in \(O(n)\).

## Key Takeaway

Treaps provide expected \(O(\log n)\) search, insertion, and deletion by using randomized priorities, but their worst-case complexity is \(O(n)\).