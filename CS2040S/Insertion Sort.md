[[CS2040S Home Page]] | [[Sorting]]

## Java Pseudocode

```
InsertionSort(A, n) {
	for (int i = 0; i < n - 1; i++) {
		key = A[i];
		j = i - 1;
		
		while (j >= 0 and A[j] > key) {
			A[j + 1] = A[j];
			j = j - 1;
		}
			
		A[j + 1] = key;
	}
}
```

## Invariants

At the end of i-iterations, the first i-items are in sorted order