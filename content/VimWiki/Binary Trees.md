# Binary Trees
#data_structure

A **binary tree** is a finite set of nodes. It can be empty. But when it is empty:
	1.**Root** is the special node
	2.Each node can be have at most two associated nodes, **left** and **right** child
	3. Each node, except the root, has only one parent
	4. Tracing through a node's parent continuously will lead to root.

- A node with no children is called **leaf**.
- leaf with same parent is called **siblings**
- **Subtrees**: any node in a tree also be a root of a new smaller tree.
- **Depth of a tree**: the steps it take to reach its root, the depth of root is zero.
- **Full** binary tree: every leaf has same depth, and every non leaf has two children
- **complete** binary tree: every level except the deepest must be filled up, and at the deepest level, leaf are as far left as possible.