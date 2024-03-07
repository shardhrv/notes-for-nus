[[CS2040S Home Page]] | [[Data Structures]] | [[Trees]] | [[Binary Trees]]

## BST Property

All nodes in left subtree < current Node < all nodes in right subtree

### Operations

**Search for maximum key:** Largest key in the BST. Take advantage of the fact that in BST, the larger element is always on the right. $O(height)$

```
public TreeNode getMax() {
	if (this.rightChild == null) {
		return this;
	} else {
		return getMax(this.rightChild.getMax());
	}
}
```

**Search for minimum key:** Smallest key in the BST. Similar to above, but on the left! $O(log(n))$
```
public TreeNode getMin() {
	if (this.leftChild == null) {
		return this;
	} else {
		return getMax(this.leftChild.getMin());
	}
}
```

**Search:** Find a key k! $O(height)$
```
public TreeNode search(Key k) {
	if (this.key == k) {
		return this;
	} 

	if (this.leftChild == null and this.rightChild == null) {
		return null; // not found!
	}

	if (k < this.key) {
		this.leftChild.search(k);
	} else {
		this.rightChild.search(k);
	}
}
```

**Insert:** Add a node! $O(height)$
```
public void insert(TreeNode node) {
	if (node.key < this.key) {
		if (this.leftChild == null) {
			this.leftChild == node;
		} else {
			this.leftChild.insert(node);
		}
	} else if (node.key > this.key) {
		if (this.rightChild == null) {
			this.rightChild == node;
		} else {
			this.rightChild.insert(node);
		}
	} else {
		return; // key is alr in the tree!
	}
}
```

**Successor:** Here is where it gets complicated. This can be broken down into several cases. $O(height)$.
- Case 1: Node has a right child $\Rightarrow$ Successor is the smallest element in the right subtree
- Case 2: Node has no right child $\Rightarrow$ Successor is the first parent that is bigger than node
```
public TreeNode successor() {
	if (this.rightChild != null) {
		return this.rightChild.getMin();
	}
	
	TreeNode parent = this.parentTree;
	TreeNode child = this;

	while ((parent != null) and (child == parent.rightTree)) {
		child = parent;
		parent = child.parentTree;
	}

	return parent;	
}
```

**Delete:** Remove a node! (not easy)
- Case 1: No children $\Rightarrow$ easy! just remove it!
- Case 2: 1 child $\Rightarrow$ Also easy! Reroute the parents edge to the child of the node!
- Case 3: 2 children $\Rightarrow$ Not so simple. 
	- Claim: Successor of a deleted node has at most 1 child!
	- Proof: Deleted node has two children. Hence, it has a rightChild. From **Successor** query, we can show that the successor of the deleted node will be the minimum of that subtree and will not have any children! We can replace the two nodes and safely delete!
## Tree Shapes

What determines the shape? Order of insertion of keys
How many possible shapes are there? Look up [Catalan Numbers](https://www.whitman.edu/mathematics/cgt_online/book/section03.05.html)
Performance depends on insertion. Insert keys in random order $\Rightarrow$ balanced!

## Problems

Imagine we add the following array into a BST in sequential order `[1, 2, 3, 4, 5]`
This will cause the BST to degenerate into a Linked List! Our $O(log(n))$ runtime would degenerate into $O(n)$. This is why it is important for our tree to be balanced.

[[Balanced Trees]]
