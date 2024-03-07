[[CS2040S Home Page]] | [[Sorting]]

## Java Pseudocode

```
QuickSort(A, begin, end) {
	if (begin >= end) {
		return;
	} else {
		int[] p = threeWayPart(A, begin, end);
		x = QuickSort(A, begin, p[0]);
		y = QuickSort(A, p[1], end);
	}
}

// with duplicates
threeWayPart(A, begin, end) {
	if (A.length > 1) {
		pivotIdx = random(begin, end); //probabilistic pivot choice
		int pivot = A[pivotIdx];
		swap(A[begin], A[pivotIdx]);
		
		eqBegin = begin;
		eqEnd = begin;
		ipBegin = start + 1;
		ipEnd = end;
		
		while (ipBegin <= ipEnd) {
			int curr = arr[ipStart];
			// less than pivot
			if (curr < pivot) {
				swap(A[ipStart], A[eqStart]);
				// increment pointers
				eqStart++;
				eqEnd++;
				ipStart++;
			// equal to pivot
			} else if (curr == pivot) {
				swap(A[ipStart], A[eqEnd]);
				// increment pointers
				eqEnd++;
				ipStart++;		
			// more than pivot	
			} else {
				swap(A[ipStart], A[ipEnd]);
				ipEnd--;
			}
		}
		// return the boundaries
		int[] result = {eqStart - 1, eqEnd + 1};
        return result;
	} else {
		return null;
	}
}
```

## Three-Pass Partition

### Option 1: 2 pass partition
Step 1: Regular partition
Step 2: Pack duplicates
### Option 2: 1 pass partition
Maintain 4 regions of the array 
![[CS2040S - ThreeWayPartitioning.jpeg]]

## Invariant:

The pivot and any element numerically equal to the pivot will be in the correct positions in the array. Elements to their left are < them and elements to their right are > than them.

