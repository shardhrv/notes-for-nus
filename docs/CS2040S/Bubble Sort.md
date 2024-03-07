[[CS2040S Home Page]] | [[Sorting]]

## Java Pseudocode

```
BubbleSort(A, n) {
	for (int i = 0; i < n; i++) {
		for (int j = 0; i < n - 1; i++) {
			if (A[j] > A[j + 1]) {
				swap(A[j], A[j + 1]); // Assume swap exists
			}
		}
	}
}
```

### Invariant
- After i-iterations, the last i items will be sorted and the largest i elements in `A`.