# Greedy Algorithms

A greedy algorithm builds a solution by always choosing the next piece with the most immediate benefit.

A rigid proof of correctness for a greedy algorithm usually consists of an **exchange argument.** Assume for contradition the greedy output s is not optimal and there exists s* that is optimal.

Swap elements of s* and s to get a contradition:
  - Find a way s* and s differ.
  - Modify s* to be more like s.
  - Argue that s* didn't get worse.

Sometimes greedy algorithms do not yield an optimal solution, but instead an aproximation. An example of this would be the [set cover problem.](https://people.eecs.berkeley.edu/~vazirani/algorithms/chap5.pdf#page=20)