# Linked List

The primary advantage of a linked list is that appending and prepending (that is, appending to the front) take constant time. Lookup, as well as insertion and deletion, take O(n) since you have to follow a chain of node pointers. The actual acts of insertion and deletion take constant time, because only next (and prev if doubly linked) pointers need to changed.

While asympotics may be similar, in pratice linked lists are slower than arrays due to poor cache performance, since nodes are not contiguous in memory.


## Runtime Complexity

Operation | Worst Case
--- | ---
space  | O(n)
lookup | O(n)
append | O(1)
prepend | O(1)
insert | O(n)
delete | O(n)


## Techniques
Multiple Pointers are very useful with Linked Lists. Fast and slow pointers are common.

- **Kth last element**: Have the fast pointer be k nodes ahead of the other, when it reaches the end, the slow pointer is at the kth last element.

- **Detecting cylces**: Have the fast pointer increment twice as much as the slow one. If they meet, there is a cycle.

- **Middle Node**: Have the fast pointer increment twice as fast. When it reaches the end, the slow pointer will be at the middle.

It can be helpful to utilize sentinel nodes ("dummy" heads), remember to return sentinel.next.

## Top Questions

**TODO**