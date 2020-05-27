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

## Top Questions

Blind Top 75
- [Two Sum](https://leetcode.com/problems/two-sum/) *HashTables*
- [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/) *Greedy* 
- [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
- [Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/) 
- [Maximum Subarray](https://leetcode.com/problems/maximum-subarray/) *Divide & Conquer, Greedy, Dynamic Programming* 
- [Maximum Product Subarray](https://leetcode.com/problems/maximum-product-subarray/) *Dynamic Programming*
- [Find Minimum in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/) *Search* 
- [Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/) *Search*
- [3Sum](https://leetcode.com/problems/3sum/)
- [Container With Most Water](https://leetcode.com/problems/container-with-most-water/) *Multiple Pointers* 

Other
- [Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/) 
- [First Missing Positive](https://leetcode.com/problems/first-missing-positive/) 
- [Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water)
- [Majority Element](https://leetcode.com/problems/majority-element) *Prefix Counting*