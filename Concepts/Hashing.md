# Hash Table
-------------

- A hash table is a data structure that lets you store and find data very quickly, usually in O(1) average time. 
- The key idea here is instead of searching through all elements one by one, compute and address (index) directly from the key. 

## Example

### Step 1: Imagine an array 
Suppose we have an array of size 10:
Index: 0  1  2  3  4  5  6  7  8  9 
Value: _  _  _  _  _  _  _  _  _  _

### Step 2: Define a hash function

A hash function converts a key into an index.

For example: 
`hash(key) = key % 10`

Suppose we insert: 15, 22, 27

Then:
`hash(15) = 15 % 10 = 5`
`hash(22) = 22 % 10 = 2`
`hash(37) = 37 % 10 = 7`

Store them:
Index: 0  1  2  3  4  5  6  7  8  9
Value: _  _ 22  _  _ 15  _ 37  _  _

### Step 3: Searching
Want to know if 22 exists ?

Compute:
`hash(22) = 22 % 10 = 2 `

Go directly to index 2. No need to scan entire array. 

This is why searching is O(1) on average. 