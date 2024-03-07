[[CS2040S Home Page]] | [[Peak Finding]] | [[1-dimension Peak Finding]]

##### Linear sort implementation
FindPeak:
	Start from `A[1]`
	 Examine every element
	 Stop when you find a peak

Runs in O(n)

##### Binary Search Implementation: 

FindPeak: 
```
FindPeak(A, n):
	if A[n / 2 + 1] > A[n / 2] then
		FindPeak(A[n / 2 + 1, ..., n], n / 2)
	if A[n / 2 - 1] > A[n / 2] then
		FindPeak(A[1, ..., n / 2 - 1], n / 2)
	else A[n / 2] is a peak, return n / 2
```

###### Why does this work?
Key Property: Invariant
	If we recurse on the right, there is a peak on the right.

Explanation:
```
– Assume there is “no peak” in the right half.
– Given: A[middle] < A[middle + 1]
– Since no peaks, A[middle+1] < A[middle+2]
– Since no peaks, A[middle+2] < A[middle+3]
– . . .
– Since no peaks, A[n-1] < A[n] //PEAK!! 
```

### Convince yourself this works!

Invariant: Correctness
1. $\exists peak[begin, end]$ (This is not enough to prove that the peak is in this range!)
2. Every peak in $[begin, end]$ is a peak in $[1, n]$

The recursion relation for the binary implementation would be 
$T(n) = T(n/2) + O(1)$
which would evaluate to 
$O(log(n))$

Note: [[Common Recurrence Relations]]