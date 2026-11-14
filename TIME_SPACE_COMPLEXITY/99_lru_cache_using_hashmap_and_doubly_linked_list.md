## Question

Design an LRU (Least Recently Used) Cache with a fixed capacity using a Hash Map and Doubly Linked List.

Determine the time and space complexity of the `get()` and `put()` operations.

**Answer:**

- `get()`: \(O(1)\) average.
- `put()`: \(O(1)\) average.
- Space Complexity: \(O(C)\), where \(C\) is the cache capacity.

### Explanation

An LRU Cache stores recently used data and removes the least recently used item when the cache becomes full.

**Step 1: Use a Hash Map**

The Hash Map stores keys and references to their corresponding nodes.

It allows us to find an item in \(O(1)\) average time.

**Step 2: Use a Doubly Linked List**

The Doubly Linked List maintains the order of usage.

- Most recently used items are placed at the front.
- Least recently used items remain at the back.

**Step 3: Perform the GET operation**

When a key is requested:

- Search for it in the Hash Map.
- If found, move its node to the front.
- Return its value.

Hash Map lookup and list movement both take \(O(1)\).

Therefore:

\[
GET=O(1)
\]

**Step 4: Perform the PUT operation**

When inserting an item:

- If the key already exists, update its value and move it to the front.
- Otherwise, insert a new node at the front.
- If the cache is full, remove the last node and its key from the Hash Map.

All these operations take \(O(1)\) average time.

Therefore:

\[
PUT=O(1)
\]

**Step 5: Calculate space complexity**

The cache stores at most \(C\) entries.

The Hash Map and Doubly Linked List together require:

\[
S(C)=O(C)
\]

### Key Takeaway

An LRU Cache combines two data structures to achieve efficient access and updates.

- GET: \(O(1)\) average.
- PUT: \(O(1)\) average.
- Space: \(O(C)\).