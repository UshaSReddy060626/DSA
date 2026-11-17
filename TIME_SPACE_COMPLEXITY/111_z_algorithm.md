## Question

Find the time and space complexity of the Z Algorithm used for pattern matching.

```python
def z_algorithm(s):
    n = len(s)
    z = [0] * n
    left = right = 0

    for i in range(1, n):
        if i <= right:
            z[i] = min(right - i + 1, z[i - left])

        while i + z[i] < n and s[z[i]] == s[i + z[i]]:
            z[i] += 1

        if i + z[i] - 1 > right:
            left = i
            right = i + z[i] - 1

    return z
```

## Answer

- **Time Complexity:** \(O(n)\)
- **Space Complexity:** \(O(n)\)

Here, \(n\) is the length of the input string.

## Explanation

1. The Z Algorithm calculates how many characters match between the beginning of a string and the substring starting at each position.
2. It creates a Z-array to store these matching lengths.
3. Two variables, `left` and `right`, maintain the current matching window.
4. Instead of comparing characters repeatedly from the beginning, the algorithm reuses previously calculated matches.
5. The right boundary moves forward through the string and never moves backward.
6. Therefore, the total number of character comparisons is linear in the string length.

## Key Takeaway

The Z Algorithm performs pattern matching in \(O(n+m)\) time when the pattern and text are combined with a separator, where \(n\) is the text length and \(m\) is the pattern length.