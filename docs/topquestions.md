# Top Questions

## Arrays

Top 75
- [Two Sum](https://leetcode.com/problems/two-sum/) *HashTables*
- [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/) *Greedy* **TODO** 
- [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
- [Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/) **REDO**
- [Maximum Subarray](https://leetcode.com/problems/maximum-subarray/) *Divide & Conquer, Greedy, Dynamic Programming* **REDO**
- [Maximum Product Subarray](https://leetcode.com/problems/maximum-product-subarray/) *Dynamic Programming*
- [Find Minimum in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/) *Search* **REDO**
- [Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/) *Search* **TODO**
- [3Sum](https://leetcode.com/problems/3sum/) **TODO**
- [Container With Most Water](https://leetcode.com/problems/container-with-most-water/) *Multiple Pointers* **REDO**

Other
- [Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/) **REDO**
- [First Missing Positive](https://leetcode.com/problems/first-missing-positive/) **REDO**
- [Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water) **REDO**

## Binary
- [Sum of Two Integers](https://leetcode.com/problems/sum-of-two-integers/)
- [Number of 1 Bits](https://leetcode.com/problems/number-of-1-bits/)
- [Counting Bits](https://leetcode.com/problems/counting-bits/)
- [Missing Number](https://leetcode.com/problems/missing-number/)
- [Reverse Bits](https://leetcode.com/problems/reverse-bits/)

## Dynamic Programming
- [Climbing Stairs](https://leetcode.com/problems/climbing-stairs/) **REDO**
- [Coin Change](https://leetcode.com/problems/coin-change) **REDO**


## Misc
- [LRU Cache](https://leetcode.com/problems/lru-cache/) **TODO**



## Solutions

### [Two Sum](https://leetcode.com/problems/two-sum/)

*Arrays, HashTables*

Given an array of integers, return indices of the two numbers such that they add up to a specific target. You may assume that each input would have exactly one solution, and you may not use the same element twice.

**Example:**
```
Input: nums = [2, 7, 11, 15], target = 9,
Outpu: [0, 1].
```

### Solution:
Use a HashMap to map values to their indicies in the array. Iterate over the array. If the current value's complement (target - current value) is in the HashMap, return the current index and the complement's index. Otherwise, add the current value and index to the HashMap.

```java
public int[] twoSum(int[] nums, int target) {
    Map<Integer, Integer> index_map = new HashMap<>();
    for(int i = 0; i < nums.length; i++) {
        int complement = target - nums[i];
        if(index_map.containsKey(complement)) {
            return new int[]{index_map.get(complement), i};
        }
        index_map.put(nums[i], i);
    }
    return null;
}
```

Time: O(n) Space: O(n)

## [Best Time to Buy and Sell Stock] *TODO*
*Arrays, Greedy*

## [Container with Most Water](https://leetcode.com/problems/container-with-most-water/) *REDO*
*Arrays*

## [Coin Change](https://leetcode.com/problems/coin-change) *REDO, attempt bottom up*
*Dynamic Programming*

## [Climbing Stairs](https://leetcode.com/problems/climbing-stairs/) *REDO, attempt bottom up*
*Dynamic Programming*

## [Binary Tree Level Order Traversal]() *REDO*
*Trees*

## [Number of Islands](https://leetcode.com/problems/number-of-islands/) *TODO*
*Graph*




### Other Top Questions (blind)
Arrays
- [Median of Two Sorted Arrays](https://leetcode.com/problems/median-of-two-sorted-arrays/) *TODO*
- [Longest Increasing Subsquence]() *REDO, or look at solution*
- [Maximum Subarray]*REDO, after learning Divide and Conquer, Greedy, also DP solution*
Dynamic Programming
- [Unique Paths]() *REDO*
- [Jump Game]() *TODO*

Linked List
- [Linked List Cycle]() *REDO*

Trees
- [Maximum Depth of Binary Tree]() *REDO*
- [Kth Smallest Element in BST]() *REDO*


### Misc (not on blind)

- [Perfect Squares]() *REDO, use bottom up dp*
- [Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water) *REDO, potential solution list*
- [First Missing Positive](https://leetcode.com/problems/first-missing-positive) *REDO*
- Find the duplicate number *medium*

### Solutions to read
- Convert Sorted Array to Binary Search Tree *after reviewing traversals*
