# Sorting & Searching

The most common sorting algorithms in interviews are Merge Sort, Quick Sort, and Radix (Bucket) Sort.

All sorts listed below (except Quick Sort) are stable, meaning they preserve the order of duplicate elements. Usually, implementations of Quick Sort are not stable.

## Merge Sort

Merge Sort the left and right halves, then merge the two.

```python
def mergeSort(arr):
    if len(arr) <= 1: return arr

    mid = len(arr) // 2
    left_arr = mergeSort(arr[:mid])
    right_arr = mergeSort(arr[mid:])

    return merge(left_arr, right_arr)

def merge(left_arr, right_arr):
    arr = []
    i, j = 0, 0

    while i < len(left_arr) and j < len(right_arr):
        if left_arr[i] < right_arr[j]:
            arr.append(left_arr[i])
            i += 1
        else:
            arr.append(right_arr[j])
            j += 1

    if i < len(left_arr):
        arr += left_arr[i:]
    if j < len(right_arr):
        arr += right_arr[j:]

    return arr
```

This implementation is not space efficient. See CTCI pg. 147 or [geeksforgeeks](https://www.geeksforgeeks.org/in-place-merge-sort/) for an in-place implementation.

The runtime of Merge Sort is Θ(N log N). The space is Θ(log N), due to the recursive call stack. A bottom-up implementation ([video](https://www.youtube.com/watch?v=lOUe8Q9jQow), [textbook](https://algs4.cs.princeton.edu/22mergesort/)) can use constant space.

## Quick Sort

Randomly or arbitrarily select a pivot, then partition the array so items < the pivot are left of it, > to the right of it. Quick Sort the left and right partitions.

```python
def quickSort(arr):
    if len(arr) <= 1: return arr

    pivot = arr[-1]
    left, middle, right = [], [], []
    for elem in arr:
        if elem < pivot:
            left.append(elem)
        elif elem == pivot:
            middle.append(elem)
        else:
            right.append(elem)

    return quickSort(left) + middle + quickSort(right)
```

This implementation is not space efficient. See CTCI pg. 148 or [geeksforgeeks](https://www.geeksforgeeks.org/quick-sort/) for an in-place implementation.

The expected runtime of Quick Sort is Θ(N log N), but its worst case is O(N^2) (bad pivots). With the naive implementation where both partitions are recursively sorted, the worst case space is O(N). However, we can optimize by sorting the larger partition with a tail recursive call or iteravely, reducing worst case space to O(log N). See [geeksforgeeks](https://www.geeksforgeeks.org/quicksort-tail-call-optimization-reducing-worst-case-space-log-n/), [wikipedia](https://en.wikipedia.org/wiki/Quicksort#Optimizations).

## Insertion Sort

For each item in the array, swap it backwards until it is in the right place among all previously examined items. [Demo](https://docs.google.com/presentation/d/10b9aRqpGJu8pUk8OpfqUIEEm8ou-zmmC7b_BE5wgNg0/edit#slide=id.g463de7561_042)

```python
def insertionSort(arr):
    for i in range(len(arr)):
        key = arr[i]

        j = i - 1
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
```

The runtime for Insertion Sort is Θ(N+K), where K is the number of inversions (pairs of out of order elements). Thus worst case is O(N^2), best is Ω(N). Space is constant, since the algorithm is in-place.

Insertion Sort is useful due to its speed with low inversions. Many implementations of sorting, such as Python's [Timsort](https://en.wikipedia.org/wiki/Timsort), switch to Insertion Sort once the number of elements in a subarray is small.

## Counting Sort

When the items we'd like to sort belong to a finite alphabet, we can count the occurances of each key, then iterate through the array, using the counts to decide where to put everything. [Demo](https://docs.google.com/presentation/d/1vmVKHRSwb5WN1rHvktplbPGecHChxOwWa7ovRuiLzbA/edit#slide=id.g582f6c5a07_0_0)

Runtime and space are Θ(N+R), where R is the size of the alphabet.

## Radix (Bucket) Sort

When the items we'd like to sort are strings over a finite alphabet, we can simply sort each digit independently with counting. In LSD (least significant digit) Radix Sort, we sort from right to left. In MSD (most significant digit) Radix Sort, where we sort from left to right, we must make sure to [sort each subproblem seperately](https://docs.google.com/presentation/d/1YBYV2ymAFiHHbSNcC1DRRi2C56blMxEsTZ7G_QE3q_8/edit#slide=id.g20841d522d_0_15).

The runtime of LSD Radix Sort is Θ(W(N+R)), where W is the width of the widest key. Space is Θ(N+R).

[Implementation](https://brilliant.org/wiki/radix-sort/#implementation-of-radix-sort) of Counting and Radix Sort.

## Binary Search

In binary search, we look for an element x in a sorted array by first comparing x to the midpoint of the array. If it is less than the midpoint, we search the left half, if it is greater we search the right half (if it is equal we are done).

Runtime is Θ(log N), space can be constant with an iterative implementation.

Binary search is analgous to a binary search tree.

```python
def binarySearch(arr, x):
    if len(arr) == 0:
        raise ValueError(f'{x} not found.')

    mid = len(arr) // 2
    if arr[mid] == x:
        return mid
    elif arr[mid] < x:
        return mid + 1 + binarySearch(arr[mid+1:], x)
    else:
        return binarySearch(arr[:mid], x)

def binarySearchIter(arr, x):
    low, high = 0, len(arr) - 1
    while low <= high:
        mid = (low + high) // 2 + low
        if arr[mid] == x:
            return mid
        elif arr[mid] < x:
            low = mid + 1
        else:
            high = mid - 1
    raise ValueError(f'{x} not found.')
```

## Quick Select

Quick Select finds the kth smallest element in an unsorted array. Like in Quick Sort, we first partition the array. If there are >= k elements in the left partition, we recurse on it. If there are k-1 elements in the left parition, return the pivot. Otherwise, recurse on the right parition.

Expected runtime is Θ(N), but worst case is O(N^2). An iterative implementation can use constant space.
