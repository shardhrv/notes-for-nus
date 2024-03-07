[[CS2040S Home Page]] | [[Data Structures]]

## Motivation

I want to implement a dictionary (collection of key-value pairs) that supports the following operations:

```
void insert(Key k, Value v) {} // add key-value pair
Value search(Key k) {} // find k
Key successor(Key k) {} // find next key > k
Key predeccessor(Key k) {} // find next key < k
void delete(Key k) {} // remove k and its value
boolean contains(Key k) {} // is there a value for k?
int size() //number of key-value pairs
```

There are many ways to approach this...

#### Approach 1: Unsorted Array
- insert: $O(1)$
- search: $O(n)$
#### Approach 2: Sorted Array
- insert: $O(n)$
- search: $O(log(n))$
#### Approach 3: Linked List
- insert: $O(1)$
- search: $O(n)$

Which implementation is best? What are the trade-offs? What are the benefits? There is no strict best answer, but we can add another tool (Trees!) to your toolbox!
## Terminology

**Nodes:** Key-value pair in a list. Contains the data
**Edges:** Path from one node to another
**Root:** Special node, does not have any parents
**Leaves:** Special node, does not have any children
**Siblings:** Special nodes, shares the same parents


There are no cycles in a tree!

## Variations

- [[Binary Trees]]
- [[Binary Search Trees (BST)]]

