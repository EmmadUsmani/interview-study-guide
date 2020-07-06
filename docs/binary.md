# Binary

## Two's Complement

Computers usually store integers in two's complement representation. In this representation, the ith bit from the right (starting at 0) represents 2^i, with the exception of the leftmost bit, which represents -2^i

N bits can represent the range [-2^(n-1), 2^(n-1)-1]

The negation of a number is found by flipping the bits and adding one

The smallest number is 10..00, the largest is 01..11

-1 is 11..11

## Arithmetic vs. Logical Right Shift

A logical right shift visibly shifts bits to the right, adding 0s to the most significant bits. An arithmetic right shift is division by 2, shifting bits to the right and adding the sign bit the most significant bits.

## Techniques

**XOR**

XOR of a number and 0 is the number
- x ^ 0 = x

XOR of a number and its negation is all 1s
- x ^ ~x = 1s

XOR of a number and 1s is its negation
- x ^ 1s = ~x

XOR of a number and itself is 0
- x ^ x = 0

**XOR is associative and communtative**
- a ^ b ^ a = (a ^ a) ^ b = 0 ^ b = b


**AND**

- x & 0s = 0
- x & 1s = x
- x & x = x

x & x-1 sets the least significant 1-bit to 0


**OR**

- x | 0s = x
- x | 1s = 1s
- x | x = x
