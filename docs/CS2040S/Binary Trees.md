[[CS2040S Home Page]] | [[Data Structures]] | [[Trees]]

## Definition:

**A Binary Tree is:** 
**(a) empty, or** 
**(b) a node pointing to two binary trees.**

## Java Pseudocode
```
public class TreeNode {
	private TreeNode leftNode;
	private TreeNode rightNode;

	private Key key;
	private Value value;

	// Constructor and methods omitted for brevity
}
```

## Terminology and Operations

**Height**: Number of edges on the longest path from root to leaf
```
h(v) == 0; // v is a leaf!
h(v) = max(h(v.leftChild), h(v.rightChild)) + 1;
h(null) = -1; // convention and simplicity
```

Calculate Height:
```
public int height(TreeNode node) {
	if (node == null) {
		return -1;
	}

	int leftHeight = height(node.leftChild);
	int rightHeight = height(node.rightChild);

	return max(h(v.leftChild), h(v.rightChild)) + 1;
}
```

**Level:** Number of edges from root node

## Tree Traversal $O(n)$

### In-order Traversal

```
public String inOrderTraversal() {
	if (this == null) {
		return;
	}

	String traversal = this.leftChild.inOrderTraversal() + ((String) this.value) + " " + this.rightChild.inOrderTraversal();

	return traversal;	
}
```
### Pre-order Traversal

```
public String preOrderTraversal() {
	if (this == null) {
		return;
	}

	String traversal = ((String) this.value) + " " + this.leftChild.preOrderTraversal() + this.rightChild.preOrderTraversal();

	return traversal;	
}
```

### Post-order Traversal

```
public String postOrderTraversal() {
	if (this == null) {
		return;
	}

	String traversal = this.leftChild.postOrderTraversal() + this.rightChild.postOrderTraversal() + ((String) this.value) + " ";

	return traversal;	
}
```

### Level-order Traversal
[TODO]

## Variation
- [[Binary Search Trees (BST)]]
