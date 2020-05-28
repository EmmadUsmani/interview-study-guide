# Trees

A tree is an undirected, connected, acyclic graph. In graph theory a tree does not need a root, however in programming contexts we often consider trees as having roots.

A tree is a recursive data structure. A node has 0 or more child nodes. Each child node has 0 or more child notes, etc.

"Balanced" trees have a similar amount of children on each side.

## Types

- Binary: At most 2 children.
- Binary Search Tree: Binary and BST property holds; left child contains values <, right child contains values >=.
- Complete: every level is filled completely, except the last, which is filled left to right.
- Full: 0 or max children at each node.
- Perfect: complete & full; all leaves are at the same depth.

A binary tree of height h has n = 2^h - 1 nodes.

An m-ary tree has height O(log_m(n)), where n is the number of nodes. *Assuming tree is fairly balanced.*

## Representation

Typically a tree is represented with nodes storing pointers to its children.

A complete binary tree can be represented by an array, with the leftmost (0th) element being the root.

For a node with index k
- parent(k) = (k - 1) // 2 *floor div*
- left child(k) = 2k + 1
- right child(k) = 2k + 2 

[m-ary tree array representation](https://en.wikipedia.org/wiki/M-ary_tree#Arrays)


## Traversals

- Level-order: top to bottom, left to right.
- In-order: traverse left child, visit node, traverse right child.
- Pre-order: visit node, traverse left, traverse right.
- Post-order: traverse left, traverse right, visit node.

Level-order is BFS (breadth first search), while the latter are all DFS (depth first search).

In-order visits nodes in a BST in ascending order.

## Runtime Complexity
Operation | Worst Case
--- | ---
space  | O(n)
lookup | O(h)
insert | O(h)
delete | O(h)

n is the number of nodes while h is the tree height. This is assuming a linked tree representation.

## Techniques
Recursion (dynamic programming) is common for tree problems, as trees are recursive data structues. Often a problem can be solved by solving the same problem on the subtrees, then doing some comparison/computation with the answers and current node.

## Top Questions

Blind Top 75

**TODO**

Other

