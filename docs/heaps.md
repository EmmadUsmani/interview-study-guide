# Heaps

A min-heap priority queue supports lookup of the minimum element in constant time. *(Without loss of generality, you can also have a max-heap.)*

The data structure is a complete binary tree where each node is smaller than its children.

- insert: insert at the rightmost position in the bottom row, then swap up with parent repeatedly until the parent is smaller (or it is the root).
- deleteMin: replace the root with the last element, then sink the new root with its smaller child until both children are larger (or it is a leaf).


## Runtime Complexity
Operation | Worst Case
--- | ---
space  | O(n)
lookup(min) | O(1)
insert | O(log n)
delete(min) | O(log n)

Heapifying an array (that is, turning it into a heap), takes O(n) time if done by moving from the back of the array and sinking elements. *[Explanation & Proof](https://stackoverflow.com/a/18742428)*

Heap sort sorts an array by max-heapifying it, then repeatedly deleting the root element, moving it to the back of the array. It has an O(n log n) runtime, due to the repeated deletion.


## Techniques

Heaps are useful for questions involving "top k" or "lowest k" elements.

To store the k largest elements, use a min-heap of size k. When the heap exceeds k elements, remove the minimum.