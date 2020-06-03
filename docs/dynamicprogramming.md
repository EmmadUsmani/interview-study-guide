# Dyanmic Programming

DP is a technique to optimize recursive algorithms.

Consider a simple fibonnaci algorithm.

```python
def fib(n):
    if n == 0 or n == 1:
        return n 
    return fib(n-1) + fib(n-2)
```

While correct and elegant, this solution has a runtime of O(2^n), due to the large amount of nodes in its recursive call tree.

**Top down** DP, or **memoization**, significantly improves runtime by simply storing return values to previously seen inputs.

```python
def fib(n):
    return fibMemo(i, [None]*n+1)

def fibMemo(i, memo):
    if i == 0 or i == 1: return i

    if memo[i] is None:
        memo[i] = fibMemo(i - 1, memo) + fibMemo(i - 2, memo)
    return memo[i]
```

The memoized fib algorithm has a runtime of Θ(n).

Notice that to compute memo[i], we only need memo[i - 1] and memo[i - 2]. Thus,we can save space by iteravely working up from the base cases of i = 1 and i = 0, storing only the previous two values. This is **Bottom up** DP.

```python
def fib(n):
    if n == 0 or n == 1: return n

    a, b = 0, 1
    for i in range(2, n):
        a, b = b, a + b
    return a + b
```

We maintain the Θ(n) runtime, but now only using constant space.