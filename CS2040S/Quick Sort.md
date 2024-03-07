[[CS2040S Home Page]] | [[Sorting]]
## Java Pseudocode

```
QuickSort(A, begin, end) {
	if (n == 1) {
		return;
	} else {
		total = end - begin
		p = partition(A, begin, end);
		x = QuickSort(A, begin, p - 1);
		y = QuickSort(A, p + 1, end);
	}
}

// assuming no duplicates
partition(A, begin, end) {
	// pivot = random(begin to end); probabilitstic approach, good expected val
	pivot = begin // deterministic approach, adversary can impede
	left = begin + 1;
	right = end;

	while (left < right) {
		while (A[left] < pivot and left < right) { left++; }
		while (A[right] > pivot and left < right) { right--; }
		if (A[left] < A[right]) swap(A[left], A[right]);
	}
	// final swap to put pivot in correct spot
	swap(A[0], A[left - 1]); // assuming pivot is the first element
	// return pivot index
	return low - 1;
}
```


## Invariants
Single partition:
- `A[right] > pivot` at the end of every **loop** -- true by assumption `A[n + 1] = Interger.MAX_VALUE` 
- `A[right] > pivot` at the end of every **iteration** 
	- During loop: 
		- When exiting `while (A[left] < pivot and left < right)`: `A[left] > pivot`
			- if `(left > right)`, then by `while` condition
			- if `(left == right)`, then by inductive assumption
		- When exiting `while (A[right] > pivot and left < right)`:  `A[right] < pivot` OR `right == left`
			- if `(right == left)`, then `A[high] > pivot`
			- else `swap(A[high], A[low])` > `pivot`
- At the end of every loop iteration:
	- for all `i >= right`, `A[i] > pivot` 
	- for all `j > 1 and j < left`, `A[j] < pivot` 

![[CS2040S - Pivot Invariant.png]]
