[[CS2040S Home Page]] | [[Sorting]]
### Divide and Conquer Sort

Step 1: Divide - Split the array into two halves
Step 2: Recurse - Sort the two halves
Step 3: Combine - Merge the sorted halves

## Java Pseudocode

Lecture implementation: (Not in place!)

```
Merge(A1, A2) {
	l = A1.length;
	m = A2.length;

	res = new Array[l + m]
	i, j, k = 0;

	while (i < l and j < m) {
		if (A1[i] <= A2[j]) {
			res[k++] = A1[i++];
		} else {
			res[k++] = A2[j++];
		}
	}

	while (i < l) {
		res[k++] = A1[i++];
	}

	while (j < m) {
		res[k++] = A1[j++];
	}

	return res;
}

MergeSort(A, n) {
	if (n == 1) {
		return; // an array of 1 is always sorted
	}
	
	A = MergeSort(A[1, ..., n / 2], n / 2);
	B = MergeSort(A[n / 2 + 1, ..., n], n / 2);
	
	return Merge(A, B);
}
```

In-place implementation:
```
Merge(A, B, begin, mid, end) {
	i, k = 0;
	j = mid;

	while (i < mid and j < end) {
		if (B[i] <= B[j]) {
			A[k++] = B[i++];
		} else {
			A[k++] = B[j++];
		}
	}

	while (i < mid) {
		A[k++] = B[i++];
	}
	while (j < end) {
		A[k++] = B[i++];
	}
	return A;
}

MergeSort(A, B, begin, end) {
	if (begin == end) {
		return;
	}

	n = end - begin;
	MergeSort(B, A, 0, n / 2);
	MergeSort(B, A, n / 2 + 1, end);
	Merge(A, 0, n / 2, end);
	return A;	
}
```

## Invariants
With every recursive call, the problem size is split into halves until it converges to n = 1, where by virtue of it being the only value will always be sorted. 