# Java

## Collection

- isEmpty()
- size()

## List
Implementations: ArrayList, LinkedList
- add(E e)
- add(int i, E e)
- get(int i)
- set(int i, E e)
    - *LinkedList is doubly linked*

## Set
Implementations: HashSet, TreeSet

- add(E e)
- contains(Object o)
- remove(Object o)
    - *TreeSet maintains order, has first() and last() operations*

```java
List<Integer> list = new ArrayList<>();
Set<Integer> set = new HashSet<Integer>();
ArrayList array_list = new ArrayList();
// allows insertion of any object; unprotected operations
```

## Map
Implementations: HashMap, TreeMap

- put(K key, V value)
- get(Object key)
- remove(Object key)
- containsKey(Object key)
- keySet()
- entrySet()
- values()

## Queue
Implementations: LinkedList, ArrayDeque

- add(E e)
- peek()
- poll()
    - *peek and poll return null if queue is empty*

## Deque
Implementations: LinkedList, ArrayDeque

- addFirst(E e)
- addLast(E e)
- peekFirst(E e)
- peekLast(E e)
- pollFirst(E e)
- pollLast(E e)

## Stack
Implementations: Stack *(Vector)*, ArrayDeque *declare as deque*

- peek()
- pop()
- push()

```java
Stack<Integer> stack = new Stack<>();
// vector based
Deque<Integer> stack = new ArrayDeque<>();
// deques can be used as stacks; support same operations
```

## PriorityQueue

- add(E e)
- peek()
- poll()
    - *min-heap by default*

```java
PriorityQueue<Integer> pq = new PriorityQueue<>();
// min-heap
PriorityQueue<Integer> max_pq = new PriorityQueue<>(20, Collections.reverseOrder());
// max-heap; must specify initial capacity and comparator
```

## Arrays

- Arrays.sort() *in-place*
- Arrays.copyOfRange(arr, start, end)
- Arrays.binarySearch(arr, key) *must be sorted ascending*
- Arrays.fill(arr, value)

```java
int[] arr = new int[5];
int[] arr = new int[]{1, 2, 3, 4, 5};
Item[] arr = new (Item []) new Object[5];
// must cast to create object array
```

## Collections

- Collections.sort(list) *in-place*
- Collections.reverse(list)
- Collections.binarySearch(list, key) *must be sorted ascending*

## String

- String.valueOf(x)
- s.concat(s2) *s + s2*
- s.charAt(index)
- s.toCharArray()
- s.length()
    - different from .length for arrays

## Math
- Math.max(x, y)
- Math.min(x, y)
- Math.sqrt(x)
- Math.abs(x)
- Math.random()
- Integer.MAX_VALUE
- Integer.MIN_VALUE
    - no factorial method

```java
int range = max - min + 1;
int rand = (int)(Math.random() * range) + min;
// random integer between min and max, inclusive
```

## Syntax

- Enhanced For Loop
```java
for(String str: str_set) {
    // do stuff
}
// works on iterables (arrays, Collections)
```

- Ternary Operator
```java
booleanExpression ? trueCase : falseCase
```