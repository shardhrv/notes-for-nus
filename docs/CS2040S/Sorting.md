[[CS2040S Home Page]]

### Key Questions
- How to analyse a sorting algorithm?
- What are the invariants?
- What are the trade-offs? When to use which implementation?

## Properties of Sorting Algorithms
- Runtime
	- How many operations to sort the space?
- Space Usage
	- How much additional memory required?
- Stability
	- Does sorting preserve the initial order of the elements in the space?


## Sorting Algorithms 

### BogoSort (Joke Sort)

Step 1: Choose a random permutation of the Array A
Step 2: If the permutation is sorted, DONE, else repeat

Runtime: $O(n*n!)$
Space Complexity: $O(1)$

### Bubble Sort (Stable)

[[Bubble Sort]]

### Selection Sort (Unstable)

[[Selection Sort]]

### Insertion Sort (Stable)

[[Insertion Sort]]

### Merge Sort (Stable)

[[Merge Sort]]

### Quick Sort (Unstable)

[[Quick Sort]]
[[Quick Sort 3-way partition]] 
[[Choosing a pivot]]
[[Optimisations for Quick Sort]]

### Order Statistics

Problem: Finding the k-th smallest element in an array `A`. 

Option 1: Sort the array and return `A[k - 1]`.
- Expected Time: $O(nlog(n))$
Option 2: [[Quick Select]]

## Runtimes

[[Time and Space Complexity Mega Table]]