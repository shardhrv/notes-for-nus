[[CS2040S Home Page]] | [[Peak Finding]]

Given: 2D Array `A[1...n, 1...m]`

![[CS2040S - 2D Array.png]]

Output: a peak that is not smaller than (at most) 4 of its neighbours

## Linear Search - Amended to 2D

Step 1: Find a global peak in each column --> $O(n)$
Step 2: Find a global peak amongst the peak in each column --> $O(m)$

Runs in $O(nm)$!

## Divide and Conquer Implementation (Binary Search)

Step 1: Use Linear Search to find max in one column --> $O(n)$
Step 2: Compare the element left and right of the found max --> $O(1)$
Step 3: Recurse left / right using the same conditions as the 1D Find peak --> $O(log(m))$

Runtime: $O(nlog(m))$

## Reduce and Conquer Implementation

Follow these [MIT slides](https://courses.csail.mit.edu/6.006/spring11/lectures/lec02.pdf) for a swift overview

Broken down into these steps:
Step 1: Find MAX element (g) in the border and cross (purple). If it is a peak, DONE.

![[CS2040S - O(n) Peak finding 2D.png]]

Step 2: If it is not, recurse on quadrant with the element bigger than g (h).

### Proof
#### Correctness:
1. The quadrant contains a peak. If there is no peak, then you can find an increasing path that keeps going until you either find a maximum element (a peak) or it exits the quadrant.
2. Every peak in the quadrant is NOT a peak in the matrix. (pictured below)
3. Key property: Find a peak at least as large as every element on the boundary.

![[CS2040S - O(n) Peak finding 2D 2.png]]

## Resources

[Find Peak in 2D Array](https://www.youtube.com/watch?v=nGGp5XBzC4g) 

