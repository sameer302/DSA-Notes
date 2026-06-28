# Hash Table
-------------

- A hash table is a data structure that lets you store and find data very quickly, usually in O(1) average time. 
- The key idea here is instead of searching through all elements one by one, compute and address index directly from the key.
- Think of a hash table as a set of buckets (an array), where each bucket can store one or more key-value pairs.
- We apply hash function on key (which can be of any data type) which returns us a index. Then at that index we can store the value corresponding to our key. 
- When more than one key maps to the same value/index it is called as collision. The most common method to handle collision (which is also used in unordered_map in c++) is separate chaining. In this each array element stores a linked list (or similar container).
- So with an efficient hash function we can expect average Time complexity to be O(1) but in worst case, if all the keys map to the same index, then we need to traverse the whole list which leads to an Time complexity of O(n).  
- Load factor tells us how full the hash table is or on average how many elements are present in each bucket, Load Factor ($\lambda$) = Number of elements / Number of buckets.
- The average search time in a hash table using chaining is O(1 + $\lambda$), so we want $\lambda$ to remain small.
- If the load factor exceeds some threshold (for example 1.0 in many implementations), the hash table creates a larger bucket array and all elements are inserted again into the new table.
- Implementations ensure that Number of buckets ~ constant x Number of elements, hence space complexity always stays O(n).
- Also the hash functions work in a way such that, `index = hash(key) % number of buckets`, so the index obtained from hash function does not increase the size of our array. 

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

# Hash Map 
---------------

- Hash Map is nothing but a ready-made hash table implementation in C++ that stores (key, value) pairs and handles hashing, collisions, resizing, and memory management for us.
- In C++, `unordered_map` is the STL implementation of a hash map.
```cpp
unordered_map<KeyType, ValueType> mp;
```
