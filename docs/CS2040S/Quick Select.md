[[CS2040S Home Page]] | [[Sorting]] | [[Quick Sort 3-way partition]]

```
QuickSelect(A, k, begin, end) {
	if (end - begin == 0) {
	 return A[beign];
	} else {
		int [] p = threeWayPart(A, begin, end);
		if (k > p[0] and k < p[1]) {
			return A[k];
		} else if (k <= p[0]) {
			return QuickSelect(A, k, begin, p[0]);
		} else {
			return Quickselect(A, k, p[1], end);
		}
	}
}
```

Note for the above implementation, this would be single pass Quick Select which is slightly different from the slides. 