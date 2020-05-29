# Arrays

## Runtime Complexity

Operation | Worst Case
--- | ---
space  | O(n)
lookup | O(1)
append | O(1)
insert | O(n)
delete | O(n)

- For resizing arrays (List in Python, ArrayList in Java), amoritzed append is O(1), worst case individual is O(n) *(CTCI pg 89)*
- Upon resizing, the original array is not extended; instead elements are copied to a new array
- Array slicing takes O(n) time and space

## Techniques

General types of algorithms, Dynamic Programming, Sorting & Searching, Divide & Conquer, Greedy, work well on array problems. Sliding Window (aka Multiple Pointers) is especially suited to arrays, and is good for interval problems.
