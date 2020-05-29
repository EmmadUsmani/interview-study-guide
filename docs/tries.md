# Tries
A trie is a special type of tree for storing strings. Tries support prefix operations, for instance, checking if a there is a string starting with a certain prefix in the database of strings.


Applications of tries include autocomplete, searches, spell checking, and more.

## Implementation

Each node in a trie represents a character. Children represent characters that immediately follow in a stored word. The end of word can be denoted by a boolean on the last character's node, or by a delimeter node.


Child links can be stored in array, which allows for fast lookup by simply going to the index of a character. However, this is not space efficient, as each node needs to store an array the size of the alphabet, mostly filled with empty values. A hash table can be used instead to achieve a good balance of speed and space efficiency.

## Runtime Complexity
Operation | Worst Case
--- | ---
lookup(word) | O(k)
lookup(prefix) | O(k)
insert | O(k)

k is the length of the word/prefix.

A hash table may be faster if only looking up words is needed (prefix operations would be slow), however its runtime may detoriate with collisions. A BST would have O(log n) lookup time, with n being the number of keys.

## Top Questions

Blind Top 75
 **TODO**