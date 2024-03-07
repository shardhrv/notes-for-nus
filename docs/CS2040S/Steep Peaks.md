[[CS2040S Home Page]] | [[Peak Finding]] | [[1-dimension Peak Finding]]

Input: `A[0, 1, ..., n - 1]`
Output: a local maximum in A
`A[i - 1] < A[i]` **and** `A[i + 1] < A[i]` <-- Note that the **equality** has changed from FindPeak!
Assume that `A[-1] = A[n] = Integer.MIN_VALUE`

**HOWEVER!** The [[Find Peak]] approach cannot be used here!

![[CS2040S - Find Peak Fails.png]]
We can't say! Is there a missing else condition to our FindPeak implementation?
What if we recurse on both sides?

FindPeak: 
```
FindPeak(A, n):
	if A[n / 2 + 1] > A[n / 2] then
		FindPeak(A[n / 2 + 1, ..., n], n / 2)
	if A[n / 2 - 1] > A[n / 2] then
		FindPeak(A[1, ..., n / 2 - 1], n / 2)
	if A[n / 2 - 1] == A[n / 2] == A[n / 2 + 1] then
		FindPeak(A[1, ..., n / 2 - 1]) and FindPeak(A[n / 2 + 1, ..., n])
	else A[n / 2] is a steep peak, return n / 2
```

What is the recurrence?
$T(n) = 2T(n/2) + O(1)$
	$= O(n)$
