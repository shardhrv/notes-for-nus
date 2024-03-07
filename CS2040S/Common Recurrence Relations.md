#ComputerScience #DSA 
[[CS2040S Home Page]]
## Recurrence Relations
**Note:** a, b, d and k are all constant values
1. $T(n) = T(n-1)+b, T(1) = a$ 
    $T(n) = O(n)$
2. $T(n) = T(n-1) + bn, T(1) = a$
    $T(n) = O(n²)$
3. $T(n) = T(n/2) + b, T(1) = a$  
    $T(n) = O( log n)$
4. $T(n) = T(n/2) + bn, T(1) = a$  
    $T(n) = O(n)$
5. $T(n) = kT(n/k) + b, T(1) = a$  
    $T(n) = O(n)$
6. $T(n) = kT(n/k) + bn, T(1) = a$
    $T(n) = O(n log n)$
7. $T(n) = T(n-1) + T(n-2) + d, T(1) = a, T(2) = b$
    $T(n) = O(2^n)$
8. $T(n) = 2T(n - 1) + d, T(1) = a$
	$T(n) = O(2^n)$
9. $T(n) = T(n-1) + b n^k, T(1) = a$ 
    $T(n) = O(n^{(k+1)})$
