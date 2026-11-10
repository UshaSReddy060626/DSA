## Question

Given an array of \(n\) integers, find the length of the Longest Increasing Subsequence using the Dynamic Programming approach.

Determine the time and space complexity.

Example:

```python
arr = [10, 9, 2, 5, 3, 7, 101, 18]
```

Output:

```python
4
```

One longest increasing subsequence is `[2, 3, 7, 101]`.

**Answer:**

- Time Complexity: \(O(n^2)\)
- Auxiliary Space Complexity: \(O(n)\)

### Explanation

A subsequence is formed by selecting elements in their original order, without requiring them to be next to each other.

**Step 1: Create a DP array**

Create a DP array of size \(n\).

Initially, every element has a subsequence length of 1 because an individual element is itself an increasing subsequence.

**Step 2: Compare previous elements**

For every element at index \(i\), check all previous elements at indices \(j\).

If:

\[
arr[j]<arr[i]
\]

Update:

\[
dp[i]=\max(dp[i],dp[j]+1)
\]

This means we can extend the increasing subsequence ending at \(j\).

**Step 3: Find the maximum**

After processing all elements, the answer is the maximum value in the DP array.

**Step 4: Calculate time complexity**

There are two nested loops:

- Outer loop runs \(n\) times.
- Inner loop checks up to \(n\) previous elements.

Therefore:

\[
T(n)=O(n^2)
\]

**Step 5: Calculate space complexity**

The DP array stores \(n\) values.

Therefore:

\[
S(n)=O(n)
\]

### Key Takeaway

The Dynamic Programming solution to LIS compares each element with its previous elements.

- Time: \(O(n^2)\)
- Auxiliary space: \(O(n)\)

*Note:* An optimized LIS algorithm using binary search takes \(O(n\log n)\) time.