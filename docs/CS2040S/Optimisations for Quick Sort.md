[[CS2040S Home Page]] | [[Sorting]]
## Many Optimisations are available!

### Base case?
#### Option 1:
- Recurse all the way down
#### Option 2:
- Switch to Insertion Sort for small arrays!
![[CS2040S - Small Array Insert.png]]
#### Option 3:
- Halt recursion early so that there are many small subarrays that are unsorted and switch to Insertion Sort (Since it works great for almost sorted arrays!)
![[CS2040S - Whole array insertion sort.png]]

