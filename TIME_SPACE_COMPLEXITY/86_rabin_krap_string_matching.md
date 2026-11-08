## Question

Given a text of length \(n\) and a pattern of length \(m\), find the pattern in the text using the Rabin-Karp algorithm.

Determine the average-case and worst-case time complexities.

**Answer:**

- Average Time Complexity: \(O(n+m)\)
- Worst Time Complexity: \(O(nm)\)
- Auxiliary Space Complexity: \(O(1)\)

### Explanation

Rabin-Karp uses hashing to find a pattern inside a larger text.

**Step 1: Calculate the pattern hash**

Calculate a hash value for the given pattern.

For example:

```python
text = "ABCCDDAEFG"
pattern = "CDD"
```

**Step 2: Calculate the text window hash**

Calculate the hash of the first text window having the same length as the pattern.

Here, the window size is 3.

**Step 3: Compare hash values**

- If the hash values are different, move to the next window.
- If the hash values match, compare the actual characters to confirm the match.

**Step 4: Use rolling hash**

Instead of calculating the hash from scratch for every window, update the previous hash when moving to the next window.

This makes average searching efficient.

**Step 5: Calculate complexity**

- Pattern hash calculation: \(O(m)\)
- Text scanning with rolling hash: \(O(n)\) average.
- In the worst case, many hash collisions require character-by-character comparisons, taking \(O(nm)\).

Therefore:

\[
\text{Average}=O(n+m)
\]

\[
\text{Worst}=O(nm)
\]

### Key Takeaway

Rabin-Karp uses hashing to search for patterns efficiently.

- Average time: \(O(n+m)\)
- Worst time: \(O(nm)\)
- Auxiliary space: \(O(1)\), assuming fixed-size rolling-hash variables.