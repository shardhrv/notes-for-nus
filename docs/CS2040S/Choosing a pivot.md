[[CS2040S Home Page]] | [[Sorting]]

## "Good Pivot"

A deterministic pivot can always have an adversarial input engineered. The Deterministic QuickSort Recurrence will look like $T(n) = T(n - 1) + T(1) + n$ --> $O(n^2)$. We want to find a pivot that roughly splits the array into two equivalent (or good enough parts). As such, we must turn to probability. 

## "Probably Good"

Lets arbitrarily say that a pivot is good if it can split an array into $9 : 1$. If we pick a pivot at random, the probability that the pivot is bad is $\frac{2}{10}$. Likewise a good pivot's probability is $\frac{8}{10}$.

Assuming that we use the paranoid implementation of Quick Sort, we can calculate the expected value of the recurrence. The expected value can be calculated. Note: $X$ is the number of iterations of choosing the pivot by being paranoid. 
$$
E[X] = \frac{8}{10} * 1 + (1 -\frac{8}{10}) * (E[X] + 1) 
$$$$
E[X] = \frac{8}{10} +  E[X] - \frac{8}{10}*E[X] + 1 - \frac{8}{10}
$$
$$
\frac{8}{10} * E[X] = 1 
$$
$$
 E[X] = \frac{10}{8}
$$

Hence, the expected number of iterations needed is $\frac{10}{8}$, or about $2$. From this, we can construct a recurrence relation $T(n) \leq T(\frac{n}{10}) + T(\frac{9n}{10}) + E[\#pivot](n) \equiv T(\frac{n}{10}) + T(\frac{9n}{10}) + 2n = O(nlog(n))$. Hallelujah. Hence, Paranoid Quick Sort has an *expected* runtime of $O(nlog(n))$.  