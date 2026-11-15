## Question

Given two strings of lengths \(m\) and \(n\), find the length of their Longest Common Substring using Dynamic Programming.

Determine the time and space complexity.

Example:

```python
s1 = "ABABC"
s2 = "BABCA"
```

Output:

```python
4
```

The longest common substring is `"BABC"`.

**Answer:**

- Time Complexity: \(O(mn)\)
- Space Complexity: \(O(mn)\) for the standard 2D DP approach.

### Explanation

A substring is a continuous sequence of characters.

The Longest Common Substring problem finds the longest continuous sequence shared by two strings.

**Step 1: Create a DP table**

Create a table of size:

\[
(m+1)\times(n+1)
\]

Initialize all values to zero.

**Step 2: Compare characters**

For every character in the first string, compare it with every character in the second string.

If the characters match:

\[
dp[i][j]=dp[i-1][j-1]+1
\]

If they do not match:

\[
dp[i][j]=0
\]

We reset to zero because a substring must contain consecutive matching characters.

**Step 3: Track the maximum**

Whenever a matching substring becomes longer, update the maximum length.

For the example, the maximum length is 4.

**Step 4: Calculate time complexity**

There are \(m\times n\) table entries.

Each entry requires constant-time work.

Therefore:

\[
T(m,n)=O(mn)
\]

**Step 5: Calculate space complexity**

The 2D table contains approximately \(m\times n\) entries.

Therefore:

\[
S(m,n)=O(mn)
\]

A space-optimized implementation can use \(O(\min(m,n))\) auxiliary space.

### Key Takeaway

Longest Common Substring uses Dynamic Programming to find the longest continuous matching sequence.

- Time: \(O(mn)\)
- Standard auxiliary space: \(O(mn)\)
- Optimized auxiliary space: \(O(\min(m,n))\)

**Remember:** Longest Common Substring is different from Longest Common Subsequence because a substring must be continuous.