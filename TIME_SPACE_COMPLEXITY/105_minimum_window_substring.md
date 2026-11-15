## Question

Given two strings, `s` and `t`, find the smallest substring of `s` that contains every character of `t`, including duplicate characters.

Determine the time and space complexity using Sliding Window and a Frequency Dictionary.

Example:

```python
s = "ADOBECODEBANC"
t = "ABC"
```

Output:

```python
"BANC"
```

**Answer:**

- Time Complexity: \(O(n+m)\) expected.
- Auxiliary Space Complexity: \(O(|\Sigma|)\), where \(\Sigma\) is the character set.

### Explanation

The Minimum Window Substring problem finds the shortest continuous portion of a string containing all required characters.

**Step 1: Count required characters**

Create a frequency dictionary for the characters in `t`.

For `"ABC"`:

```python
{'A': 1, 'B': 1, 'C': 1}
```

**Step 2: Expand the sliding window**

Use two pointers:

- `left` marks the beginning of the window.
- `right` expands the window.

Move the right pointer and update character frequencies until the window contains all required characters.

**Step 3: Shrink the window**

Once a valid window is found:

- Record its length.
- Move the left pointer forward.
- Continue shrinking while the window remains valid.

This helps find the smallest possible window.

**Step 4: Calculate time complexity**

Both pointers move forward through the string.

- Right pointer visits at most \(n\) positions.
- Left pointer visits at most \(n\) positions.
- Building the frequency dictionary takes \(O(m)\).

Therefore:

\[
T(n,m)=O(n+m)
\]

**Step 5: Calculate space complexity**

The frequency dictionaries store character counts.

Their size is bounded by the number of distinct characters.

Therefore:

\[
S=O(|\Sigma|)
\]

### Key Takeaway

Minimum Window Substring combines Sliding Window and Hash Maps.

- Time: \(O(n+m)\) expected.
- Auxiliary space: \(O(|\Sigma|)\).
- Each pointer moves forward, avoiding repeated scanning.