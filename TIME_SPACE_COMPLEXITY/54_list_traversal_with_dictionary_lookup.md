## Question

Find the time complexity of the following code.

```python
def count_matches(arr, lookup):
    count = 0

    for x in arr:
        if x in lookup:
            count += 1

    return count
```

Assume `lookup` is a Python set or dictionary.

## Answer

**Time Complexity: \(O(n)\) average case**, where \(n\) is the length of `arr`.

## Explanation

**Step 1: Analyze the loop**

```python
for x in arr:
```

The loop visits every element in `arr`, so it runs \(n\) times.

Its complexity is \(O(n)\).

**Step 2: Analyze the lookup**

```python
if x in lookup:
```

Checking whether an element exists in a Python set or dictionary takes \(O(1)\) time on average.

**Step 3: Combine the operations**

Each of the \(n\) iterations performs an average \(O(1)\) lookup.

\[
T(n)=n\times O(1)
\]

\[
\boxed{O(n)}
\]

## Key Takeaway

A loop containing a dictionary or set lookup is generally \(O(n)\), because each lookup takes \(O(1)\) on average.

Remember: list membership (`x in a_list`) is different. It takes \(O(n)\) in the worst case, so using it inside a loop can produce \(O(n^2)\) time.