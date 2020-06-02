# Python

## List
implemented with Array

- lst.append(elem)
- lst.insert(pos, elem)
- lst.extend(lst2) *lst += lst2*
- lst.remove(elem)
- lst.sort() *ascending; TimSort*
- lst.reverse()
- del lst[index]
    - *all functions above modify lst, return None*
- lst.pop([index]) *default last elem, O(1) for last, O(n) for arbitrary*
- lst.index(elem, [beg], [end])
- lst.count(elem)
- sum(lst), min(lst), max(lst), len(lst) *len is O(1)*
- lst + lst2
- lst * x
- lst[start: stop: step] *includes start, not stop*
- list(iterable)

```python
lst = [1, 2, 'cat' (100, 200)]
alphabet = [None] * 26 # array with 26 Nones, slot for each char
```

## Tuple
implemented with Array

```python
t = (1, 2, 3)
t[1] # allowed
t[1] = 5 # not allowed
# tuples are essentially immuatable lists
```

## Dictionary
implemented with HashTable

- d.get(key)
- d[key] *raises KeyError if key not in d*
- key in d
- d[key] = value
- d.pop(key)
- d.items() *list of tuples of key val pairs*
- d.keys()
- d.values()

```python
d = {}
d = {1: 'Emmad', 2: 'Kitten', 'Alpha': [300, 44, 7]}
d = dict([(1, 'Emmad'), (2, 'Kitten')])
1 in d
#True
```

## Counter
implemented with HashTable, inhereits from Dictionary
must be imported from collections

- Counter([iterable-or-mapping]) *linear time to pass thru iter*
- c.most_common([n])
- c.elements() *iterator over elements with each as many times as its count*
- c.substract([iter-or-mapping]) *subtract counts*

```python
from collections import Counter
cnt = Counter()
for word in words:
    cnt[word] += 1

cnt = Counter(words) #simpler
```

## Set
implemented with HashTable

- s.add(elem)
- s.remove(elem)
- s.difference(s2)
- s.intersection(s2)
- s.union(s2)
- set(iterable)

```python
s = {"cow", 1, (99, -20, 0), "apple"}
s = set() # creates empty set
s = {} # does not work, will make dict

```


## Deque
implemented with *(doubly)* LinkedList

- deque([iter[, maxlen]])
- d.append(elem)
- d.appendleft(elem)
- d.pop()
- d.popleft()
    - *O(1) appends and pops from front and back*
    - *item from oppposite end will be removed if maxlen exceeded*

```python
from collections import deque
queue = deque()
queue = deque(["Cat", "Dog", "Hamster"], 5)
```

## Heapq
methods allow for min-heap operations on an array

- heapq.heappush(heap, item)
- heapq.heappop(heap)
- heapq.heapify(x) *in-place, linear time*
- heapq.heappushpop(heap, item)

Push 'item' onto the heap, then pop and return the smallest element (which may be item). Faster than heappush() then heappop()
- heapq.heapreplace(heap, item)

Pop and return the smallest item, while pushing the new item. Faster than heappop() then heappush()

```python
import heapq
heap = []
heapq.heappush(heap, 2)
heapq.heappush(heap, 1)
heapq.heappush(heap, 3)
heapq.heappop(heap)
>>> 1
heapq[0] # peek min item
>>> 2
```

## String
Strings in python are immutable, so all methods return new strings.

 - string[start: stop: step]
 - string.split(seprator) *returns list, no seperator*
 - string.index(substr)
 - string.count(substr)
 - str() *invokes \_\_str\_\_(), if not \_\_repr\_\_()*


 - ord() *returns unicode number of char*
 - chr(i) *returns char with unicode number i*
```python
ord('a')
>>> 97
ord('b') - ord('a')
>>> 1
```

## Math

- math.sqrt(x) *x**0.5*
- math.pow(x, y) *x**y*
- math.ceil(x)
- math.floor(x)
- math.factorial(x)
- abs(x)
- int(x)
- float(x)
- sum(...), min(...), max(...)
- // *floor division, returns int*

## Synatax
- Equality
```python
lst1 = []
lst2 = []
lst1 == lst2 # value equality
>>> True
lst1 is lst2 # reference equality
>>> False
```

- Sorting
```python
lst = [4, 5, 2, 1, 3]
sorted(lst) # lst is not modified
>>> [1, 2, 3, 4, 5]
lst.sort() # lst is modified, returns None
```