## Question

Consider a Trie data structure used to store words. Each word contains \(k\) characters.

Find the time complexity of:
1. Inserting one word.
2. Searching for one word.
3. Storing \(N\) words with a total of \(L\) characters.

**Answer:**

- Insertion: \(O(k)\)
- Search: \(O(k)\)
- Storing all words: \(O(L)\) time and \(O(L)\) space.

## Explanation

A Trie stores words character by character.

**Step 1: Insertion**

Suppose we insert the word `"CAT"`.

- Check the character `C` and create a node.
- Check `A` and create a node.
- Check `T` and create a node.
- Mark the final node as the end of the word.

If the word has 3 characters, we perform 3 character operations.

Therefore, for a word of length \(k\):

\[
T(k)=O(k)
\]

**Step 2: Searching**

To search for `"CAT"`:

- Start from the root.
- Follow the `C` node.
- Follow the `A` node.
- Follow the `T` node.
- Check whether it marks the end of a word.

We visit at most \(k\) characters.

Therefore:

\[
T(k)=O(k)
\]

**Step 3: Storing N words**

If all words together contain \(L\) characters, inserting them takes \(O(L)\) time.

The Trie also requires \(O(L)\) space in the worst case.

### Key Takeaway

Trie operations depend on the **length of the word**, not directly on the number of words stored.

- Insert: \(O(k)\)
- Search: \(O(k)\)
- Total storage: \(O(L)\)