## Question

Given a string of length \(n\), construct a suffix array by generating all suffixes, sorting them lexicographically, and storing their starting positions.

Determine the time and space complexity of this straightforward approach.

**Answer:**

- Time Complexity: \(O(n^2\log n)\)
- Auxiliary Space Complexity: \(O(n^2)\)

### Explanation

A suffix is a substring that starts at a particular position and continues until the end of the string.

Consider:

```python id="k2p9va"
s = "banana"
```

Its suffixes are:

```python id="x7w4mb"
banana
anana
nana
ana
na
a
```

**Step 1: Generate all suffixes**

There are \(n\) possible starting positions.

Generating and storing all suffixes requires a total of:

\[
n+(n-1)+(n-2)+\cdots+1
\]

Therefore, generating and storing them takes:

\[
O(n^2)
\]

**Step 2: Sort the suffixes**

There are \(n\) suffixes.

A comparison-based sorting algorithm performs \(O(n\log n)\) comparisons.

However, comparing two suffixes can take up to \(O(n)\) character comparisons.

Therefore:

\[
O(n\log n)\times O(n)
\]

\[
=O(n^2\log n)
\]

**Step 3: Store starting positions**

After sorting, store the starting index of each suffix.

This requires \(O(n)\) additional space.

**Step 4: Calculate total complexity**

The sorting operation dominates the total time.

\[
\boxed{O(n^2\log n)}
\]

The stored suffixes require \(O(n^2)\) space.

\[
\boxed{O(n^2)}
\]

### Key Takeaway

A straightforward suffix array construction generates and sorts every suffix.

- Time: \(O(n^2\log n)\)
- Auxiliary space: \(O(n^2)\)

*Note:* More advanced suffix-array construction algorithms can achieve \(O(n\log n)\) or even \(O(n)\) time.