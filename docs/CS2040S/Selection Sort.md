[[CS2040S Home Page]] | [[Sorting]]

## Java Pseudocode
```
SelectionSort(A, n) {
	for (int i = 0; i < n; i++) {
		minIndex = i
		for (int j = i; j < n; j++) { //finding the min element
			minIndex = (A[minIndex] <= A[j]) ? minIndex : j;
		}
		swap(A[i], A[minIndex]);
	}
}
```

## Invariant 

After i-iterations, the first i-elements will be sorted and the smallest i elements in `A`.