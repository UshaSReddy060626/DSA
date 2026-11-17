## Question

Given a stream of \(n\) elements, select one element uniformly at random without storing the entire stream.

Determine the time and space complexity using Reservoir Sampling.

**Answer:**

- Time Complexity: \(O(n)\)
- Auxiliary Space Complexity: \(O(1)\)

### Explanation

Reservoir Sampling is an algorithm used to randomly select elements from a data stream when the total number of elements may not be known in advance.

**Step 1: Select the first element**

Initially, store the first element as the selected element.

**Step 2: Process the remaining elements**

For the element at position \(i\), starting from 2:

- Generate a random integer between 1 and \(i\).
- If the generated number is 1, replace the currently selected element.
- Otherwise, keep the existing selection.

**Step 3: Understand uniform probability**

The first element initially has a selection probability of 1.

When the second element arrives:

- The first element remains selected with probability \(1/2\).
- The second element is selected with probability \(1/2\).

For every new element, the replacement probability ensures that all processed elements have equal chances of remaining selected.

Thus, every element has a final selection probability of:

\[
P=\frac{1}{n}
\]

**Step 4: Calculate time complexity**

Every element is processed once.

Therefore:

\[
T(n)=O(n)
\]

**Step 5: Calculate space complexity**

Only the selected element, current index, and a few variables are stored.

Therefore:

\[
S(n)=O(1)
\]

### Key Takeaway

Reservoir Sampling selects a uniformly random element from a stream.

- Time: \(O(n)\)
- Auxiliary space: \(O(1)\)
- Useful when the stream is too large to store entirely.