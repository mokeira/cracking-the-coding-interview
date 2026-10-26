## Hash Tables

<span style="color:#008000">Usage:</span> Maps keys to values for highly efficient lookup

Ways of implementing hash tables:

[ ] Linear Probing  
[ ] Quadratic Probing  
[ ] Double Hashing  
[ ] Cuckoo Hashing  
[ ] Hopscotch Hashing  
[ ] Robin Hood Hashing  
[ ] Chaining via Singly Linked Lists  
[ ] Chaining via Doubly Linked Lists  
[ ] Chaining via Self-Balancing Binary Search Trees  
[ ] Chaining via Dynamic Arrays  
[ ] Geometric / Bulk Resizing Table  
[ ] Incremental / Real-time Resizing Table  
[ ] Consistent Hashing Table  
[ ] Static / Fixed-size Array Table

We will start with a simple implementation: Using an array of linked lists and hash code function

### Inserting a key and value
##### Step 1: compute the key's hash code
- Since there may be an infinite number of keys and finite number of ints --> 2 different keys could have the same hash code
##### Step 2: Map hash code to index in the array.
- Simple function to use: 
> hash(key) % array_length
- 2 hash codes could make to the same index
##### Step 3: Store key and value in this index
- There's a linked list of keys, values at this index
- linked list is used to deal with collisions
> collisions:
>- 2 different keys with the same hash code
>- 2 hash codes that map to the same index
##### Retrieving the value pair by key
- Repeat the process: compute hash code from key, compute index from hash code, search through linked list for the value with the key

Worst case runtime: O(n) --> the number of collisions is very high  
Good implementation minimizes collisions --> lookup time O(1)

simple implemenation in simple_hash_table.py