[[CS2040S Home Page]]

TODO: Watch Lecture 12

Topics
Direct Access Tables:
- Problem: 
	- Huge number of possible keys, not necessary that all the keys will go inside universe U

Solution: Hashing
- function that limits universe U size
Problems: Collision 
two distinct keys may collide if they are hashed to the same address

Solution to Collision: Chaining 


[[Hash Table]]

Assumption: SUHA
- Assume 
	- n items
	- m buckets
- Define load(hash table) = n/m

Searching 
- expected O(1) + n/m = O(1) with SUHA

expected maximum chain length with SUHA is O(log(n))

See:
Power of Two Choices
[Java Map](https://docs.oracle.com/javase/8/docs/api/java/util/Map.html) 
