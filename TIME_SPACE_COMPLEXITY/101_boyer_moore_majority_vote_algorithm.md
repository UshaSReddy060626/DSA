## Question

Given an array of \(n\) elements, find the element that appears more than \(n/2\) times using the Boyer-Moore Majority Vote Algorithm.

Determine the time and space complexity.

Example:

```python
arr = [2, 2, 1, 1, 2, 2, 2]
```

Output:

```python
2
```

**Answer:**

- Time Complexity: \(O(n)\)
- Auxiliary Space Complexity: \(O(1)\)

### Explanation

The Boyer-Moore algorithm finds a majority element without using a Hash Map or sorting the array.

A majority element appears more than half the total number of times.

**Step 1: Initialize two variables**

- `candidate` stores the possible majority element.
- `count` stores its current vote count.

Initially, the count is zero.

**Step 2: Traverse the array**

For every element:

- If count is zero, select the current element as the candidate.
- If the current element equals the candidate, increase the count.
- Otherwise, decrease the count.

**Step 3: Understand the cancellation idea**

Different elements cancel each other's votes.

Because a true majority element appears more than all other elements combined, it remains the candidate after cancellation.

**Step 4: Calculate time complexity**

The algorithm traverses the array once.

\[
T(n)=O(n)
\]

**Step 5: Calculate space complexity**

Only two variables are maintained.

\[
S(n)=O(1)
\]

**Important:** If the problem does not guarantee that a majority element exists, perform a second traversal to verify the candidate.

### Key Takeaway

Boyer-Moore Majority Vote efficiently finds an element occurring more than \(n/2\) times.

- Time: \(O(n)\)
- Auxiliary space: \(O(1)\)
- One pass finds a candidate; a second pass verifies it when necessary.