# Sliding Window

Sliding Window is a technique for array/sequence problems in which you consider a fixed subarray at each step, gradually moving it to the end.

The runtime of a sliding window algorithm is usually linear, as you do a single linear scan of the array. This is useful for optimizing nested loops.

Problems involving minimium, maximum, longest, or shortest values, especially when dealing with a fixed size constraint, are suitable for this technique.

## Example

Find the maximum sum of a contigious sequence of k elements in an array.

```python
def maxSumK(arr, k):
    maxSum = sum(arr[:k])
    windowSum = maxSum
    for i in range(len(arr)-k):
        windowSum = windowSum - arr[i] + arr[i+k]
        maxSum = max(windowSum, maxSum)
    return maxSum
```

At each step we slide the window over, adding the new element's value to windowSum and subtracting the first element of the old window.