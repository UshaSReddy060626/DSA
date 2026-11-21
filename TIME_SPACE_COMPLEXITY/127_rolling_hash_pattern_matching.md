## Question

Find the time and auxiliary space complexity of the following algorithm.

```python
def search(text, pattern):
    n = len(text)
    m = len(pattern)

    if m > n:
        return []

    base = 31
    mod = 10**9 + 7

    pattern_hash = 0
    window_hash = 0
    power = pow(base, m - 1, mod)

    for i in range(m):
        pattern_hash = (pattern_hash * base + ord(pattern[i])) % mod
        window_hash = (window_hash * base + ord(text[i])) % mod

    result = []

    for i in range(n - m + 1):
        if pattern_hash == window_hash:
            if text[i:i + m] == pattern:
                result.append(i)

        if i < n - m:
            window_hash = (
                (window_hash - ord(text[i]) * power) * base
                + ord(text[i + m])
            ) % mod

    return result
```

Let:
- \(n\) = length of the text
- \(m\) = length of the pattern
- \(k\) = number of actual matches

## Answer

- **Expected Time Complexity:** \(O(n+m+km)\), assuming hash collisions are uncommon.
- **Worst-case Time Complexity:** \(O(nm)\)
- **Auxiliary Space Complexity:** \(O(k)\), excluding the input strings.

## Explanation

### Step 1: Calculate the initial hashes

```python
for i in range(m):
```

This loop runs \(m\) times.

Each iteration calculates part of the pattern hash and initial window hash.

Time:

\[
O(m)
\]

### Step 2: Calculate the rolling hash power

```python
power = pow(base, m - 1, mod)
```

This uses modular exponentiation.

Time:

\[
O(\log m)
\]

This is smaller than the overall \(O(n+m)\) preprocessing bound.

### Step 3: Slide the window

```python
for i in range(n - m + 1):
```

The loop runs approximately \(n\) times.

Updating the rolling hash requires a constant number of arithmetic operations.

Time:

\[
O(n)
\]

### Step 4: Verify matching hashes

```python
if pattern_hash == window_hash:
    if text[i:i + m] == pattern:
```

If hashes match, the algorithm compares the actual substring with the pattern.

One comparison can take \(O(m)\) time.

If there are \(k\) hash matches, verification takes:

\[
O(km)
\]

With uncommon collisions, \(k\) is usually small. In the worst case, every window can have a matching hash, giving \(O(nm)\) verification time.

### Step 5: Calculate total time

Expected:

\[
O(m+n+km)
\]

Worst case:

\[
\boxed{O(nm)}
\]

### Step 6: Calculate space

The algorithm stores:
- Hash variables: \(O(1)\)
- Result positions: \(O(k)\)

Therefore:

\[
\boxed{O(k)}
\]

The substring comparison may create a temporary substring of length \(m\) in Python. If counting that temporary allocation, peak auxiliary space can be \(O(m+k)\).

## Key Takeaway

- Rolling hash updates: \(O(1)\) per window.
- Initial hash calculation: \(O(m)\).
- Expected matching time: close to \(O(n+m)\) when few hashes match.
- Worst-case time: \(O(nm)\) because of repeated substring verification.
- Always distinguish expected and worst-case complexity.