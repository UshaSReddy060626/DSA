## Question

Given an array of \(n\) elements and a window size \(k\), find the number of distinct elements in every window using a sliding window and a frequency dictionary.

Determine the time and space complexity.

Example:

```python
arr = [1, 2, 1, 3, 4, 2, 3]
k = 4
```

Output:

```python
[3, 4, 4, 3]
```

**Answer:**

- Time Complexity: \(O(n)\) expected.
- Auxiliary Space Complexity: \(O(k)\), excluding the output.

### Explanation

A sliding window processes a fixed-size portion of an array and moves it forward one position at a time.

**Step 1: Create the first window**

Take the first \(k\) elements:

```python
[1, 2, 1, 3]
```

The distinct elements are `1, 2, 3`.

Count = 3.

**Step 2: Store frequencies**

Use a dictionary to store how many times each element appears.

For the first window:

```python
{1: 2, 2: 1, 3: 1}
```

**Step 3: Move the window**

When moving to the next window:

- Remove the outgoing element from the frequency dictionary.
- Add the incoming element.
- Update the distinct count.

For example, the next window is:

```python
[2, 1, 3, 4]
```

Distinct count = 4.

**Step 4: Calculate time complexity**

- Initial window processing: \(O(k)\).
- Each of the remaining \(n-k\) positions requires constant expected-time dictionary updates.

Therefore:

\[
T(n)=O(k)+O(n-k)
\]

\[
\boxed{O(n)}
\]

**Step 5: Calculate space complexity**

The frequency dictionary stores at most \(k\) different elements.

Therefore:

\[
\boxed{O(k)}
\]

### Key Takeaway

Sliding Window avoids calculating every window from scratch.

- Time: \(O(n)\) expected.
- Auxiliary space: \(O(k)\).
- Dictionary operations are expected \(O(1)\).