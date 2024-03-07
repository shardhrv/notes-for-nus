#ComputerScience #DSA #Algorithms
[[CS2040S Home Page]]

## Algorithms

For every algorithm, the following must be understood:
- What problem does this algorithm solve?
- When can this algorithm be applied? 
	- ie What are the preconditions and when does this algorithm fail?
- Why is the algorithm correct?
- What is the key invariant behind the algorithm?
- What is the running time of the algorithm?
- What optimisations are possible?

#### Preconditions and Postconditions
Precondition:
- Something that is true when the function begins
- Something important for it to work correctly
Postcondition:
- Fact that is true when the function ends
- Something useful to show that the computation was done correctly
## Big-O Notation 

> **Always** think big

Precise definition: $T(n) = O(f(n))$ if T grows no faster than f
	$T(n) = O(f(n))$ if:
	- there exists a constant $c > 0$
	- there exists a constant $n_{0} > 0$
such that for all $n > n_{0}$:
	$T(n) \leq cf(n)$

![[CS2040S - Big O Graph.png]]

In English: Worst-Case performance of the algorithm can be tightly bounded by $O(f(n))$
### Big-Omega Notation

Precise definition: $T(n) = \Omega(f(n))$ if T grows no slower than f
	$T(n) = \Omega(f(n))$ if:
	- there exists a constant $c > 0$
	- there exists a constant $n_{0} > 0$
such that for all $n > n_{0}$:
	$T(n) \geq cf(n)$

In English: Best-Case performance of the algorithm can be tightly bounded by $\Omega(f(n))$

### Big-Theta Notation

Precise definition: $T(n) = \Theta(f(n))$ if T grows at the same rate as f
	$T(n) = \Theta(f(n))$ if:
	- $T(n) = O(f(n))$ and 
	- $T(n) = \Omega(f(n))$

In English: Expected performance of the algorithm can be tightly bounded by $\Theta(f(n))$

> **Always** think tight

- Choose the tightest bound that you can find

### Order or size

Quick look-up table:

![[CS2040S - Big-O Size Table.png]]

### Big-O Rules

If $T(n) = O(f(n))$ and $S(n) = O(g(n))$ then $T(n) + S(n) = O(f(n) + g(n))$
If $T(n) = O(f(n))$ and $S(n) = O(g(n))$ then $T(n) * S(n) = O(f(n) * g(n))$

*Note:* $O(n!) = O(nlogn)$

## Algorithmic Analysis Rules

Suppose we have the code
```
void sum(int k, int[] intArray) {
	int total = 0;
	for (int 1 = 0; i <= k; i++) {
		total += intArray[i];
	}
	return total;
}
```

#### What is the cost of running this excerpt?

There are many ways of doing it, but it all depends on what we are trying to analyse. If we wanted, we could look at each assignment as adding to the cost, or each increment as another operation. But just because something is more specific, does not mean it is more useful. Always thing about what the target of your analysis is!

#### How can we calculate cost?

Loops
$cost = (n-iterations) * (max(one-iteration))$
Nested-Loops
$cost = (n-iterations) * (max(one-iteration))$
Sequential Statements 
$cost = a_{cost} + b_{cost}$
Conditional statements
$cost = max(a_{cost}, b_{cost}) \leq (a_{cost} + b_{cost})$
Recursive calls (spooky)
Recursion relations need to be analysed. See [[Common Recurrence Relations]]
