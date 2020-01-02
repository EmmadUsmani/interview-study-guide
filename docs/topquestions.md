# Top Questions

## [Two Sum](https://leetcode.com/problems/two-sum/)

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


### Other Top Questions
 - [LRU Cache](https://leetcode.com/problems/lru-cache/) *TODO*
 - [Number of Islands](https://leetcode.com/problems/number-of-islands/) *TODO*
 - [Median of Two Sorted Arrays](https://leetcode.com/problems/median-of-two-sorted-arrays/) *TODO*


