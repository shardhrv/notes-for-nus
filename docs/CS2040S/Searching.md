[[CS2040S Home Page]]
#ComputerScience #DSA #Algorithms

# Linear Search

#### Goal
Find an element in an array

Just look through every element in the array. Slow and inefficient :(. But sometimes still necessary, and computationally more suited than binary search! (esp if your search space is not sorted~).


# Binary Search 

#### Goal
Find an element in a sorted array

#### Precondition 
Sorted array in ascending order (Do not do input validation as that would slow down the algorithm!)
Array is of size n

#### Postcondition 
If element is in the array, `A[begin] == key`

#### Invariant
The key is always within the range of the array

Correctness:
`A[begin] <= key <= A[end]`

Performance:
`(end - begin) <= n/(2^k)` in iteration k

#### Implementation 
```
int search(int[] A, int key, int n) {
	int begin = 0;
	int end = n - 1;
	while (begin < end) { 
		mid = begin + (end - begin) / 2;
		if (key <= A[mid]) {
			end = mid;
		} else {
			begin = mid + 1;
		}
	}
	return (A[begin] == key) ? begin : -1;
}
```

#### Binary Search to find max students
```
int search(int[] A, int key, int n) {
	int begin = 0;
	int end = n - 1;
	while (begin < end) { 
		mid = begin + (end - begin) / 2;
		if (MaxStudents(mid) <= 18) { // This is the only line that changed!
			end = mid;
		} else {
			begin = mid + 1;
		}
	}
	return (A[begin] == key) ? begin : -1;
}
```

#### Time and Space Complexity:
[[Time and Space Complexity Mega Table]]

### Peak-Finding
How search algorithms can be used: [[Peak Finding]]