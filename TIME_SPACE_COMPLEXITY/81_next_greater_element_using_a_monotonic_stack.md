## Question

Given an array of \(n\) elements, find the next greater element for every element using a stack.

Determine the time and space complexity.

Example:

```python
arr = [4, 5, 2, 10]
```

Output:

```python
[5, 10, 10, -1]
```

**Answer:**

- Time Complexity: \(O(n)\)
- Auxiliary Space Complexity: \(O(n)\)

## Explanation

The next greater element is the first element on the right that is greater than the current element.

**Step 1: Traverse the array**

Visit each element from right to left.

**Step 2: Use a stack**

For every element:

- Remove smaller or equal elements from the stack.
- If the stack is empty, the answer is -1.
- Otherwise, the top of the stack is the next greater element.
- Push the current element onto the stack.

**Step 3: Understand why the time is O(n)**

At first, it may look like nested loops because we traverse the array and sometimes pop elements.

However, every element:

- Is pushed onto the stack exactly once.
- Can be popped from the stack at most once.

Therefore, the total number of stack operations is proportional to \(n\).

\[
T(n)=O(n)
\]

**Step 4: Calculate space**

In the worst case, all \(n\) elements may be stored in the stack.

Therefore:

\[
S(n)=O(n)
\]

### Key Takeaway

Even though a stack is used inside a loop, the algorithm takes \(O(n)\), not \(O(n^2)\), because each element is pushed and popped at most once.