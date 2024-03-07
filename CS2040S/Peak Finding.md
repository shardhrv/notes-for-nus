[[CS2040S Home Page]]

Relevant Links: [[Searching]], [[Algorithmic Analysis]]
## Motivation 

![[CS2040S - Peak Graph.png]]
An algorithm that is able to find global and local maxima
#### Global Maximum for Optimization problems:
- Finds a good solution for a problem
- Way to save costs, save time or make more money
Input: `A[0, 1, ..., n - 1]`
Output: max element in `A`.

#### Local Maximum for Optimization problems:
- Finds a "good enough" solution for a problem
- Not necessarily the best solution 
Input: `A[0, 1, ..., n - 1]`
Output: a local maximum in A
`A[i - 1] <= A[i]` **and** `A[i + 1] <= A[i]`
Assume that `A[-1] = A[n] = Integer.MIN_VALUE`

## 1-dimension

[[1-dimension Peak Finding]]

## 2-dimension

 [[2-dimension Peak Finding]]

## Summary
- Divide and Conquer (Binary Search) in $O(log(n))$ time
- Simple Divide and Conquer 2D with Binary Search in $O(nlog(m))$ time
- Careful Divide and Conquer in $O(n)$ time