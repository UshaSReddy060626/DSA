## Question

What is the time complexity of the following code?

```python id="cw7f3k"
arr = [10, 20, 30, 40, 50]

print(arr[3])
```

---

## Solution

**Time Complexity:** `O(1)`

### Explanation

* Accessing an element using its index is a **direct operation**.
* The computer can immediately locate the element without checking other elements.
* It takes the same amount of time whether the array has **5 elements** or **5 million elements**.

Therefore, the overall time complexity is:

```text id="8ik6cz"
O(1)
```
