# Bit Manipulation

## Binary Numbers

|        | 4s | 2s | 1s |
| ------ | -- | -- | -- |
| digits | 1  | 0  | 1  |

The places in binary numbers are sequential powers of 2. The first digit (from right) indicates 1s; the second digit indicates 2s; then the 3rd digit indicates 4s, and so on...

### Negative numbers and two's complement
Negative numbers are typically represented in binary using two's complement encoding. In two's complement, the leftmost digit is negative, and the rest of the digits are positive.
Example: 101 = 1 * (-4) + 0 * 2 + 1 * 1 = 3


## Bitwise AND
The AND operation takes two bits and returns 1 if both bits are 1. Otherwise, it returns 0.
```
1 & 1 -> 1
1 & 0 -> 0
0 & 1 -> 0
0 & 0 -> 0
```

When performing AND on two integers, the AND operation is calculated on each pair of bits
```
5 & 6  # gives 4

# At the bit level:
#     0101  (5)
#   & 0110  (6)
#   = 0100  (4)
```

## Bitwise OR
The OR operation takes two bits and returns 1 if either of the bits are 1. Otherwise, it returns 0.
```
1 | 1  →  1
1 | 0  →  1
0 | 1  →  1
0 | 0  →  0
```

Performing OR on two integers:
```
5 | 6  # gives 7

# At the bit level:
#     0101  (5)
#   | 0110  (6)
#   = 0111  (7)
```

## Bitwise XOR
The XOR operation (exlusive or) takes two bits and return 1 if exactly one of the bits is 1. Otherwise, it returns 0.
```
1 ^ 1  →  0
1 ^ 0  →  1
0 ^ 1  →  1
0 ^ 0  →  0
```

Performing XOR on two integers:
```
5 ^ 6  # gives 3

# At the bit level:
#     0101  (5)
#   ^ 0110  (6)
#   = 0011  (3)
```

## Bitwise NOT
The NOT bitwise operation inverts bits. A 0 becomes a 1. A 1 becomes a 0.

The NOT operator is often written as a tilde character **~**
```
~ 0000 0101
= 1111 1010
```

Performing NOT on an integer:
```
~ 5  # gives -6

# At the bit level:
#   ~ 0000 0101  (5)
#   = 1111 1010  (-6)
```


## Bit shifting
A bit shift moves each digit in a number's binary representation left or right. 

### Left shifts
When shifting left, the most-significant bit is lost, and a 0 bit is inserted on the other end.
The left shift operator is usually written as **<<**

```
0010 << 1  →  0100
0010 << 2  →  1000
```
A single left shift multiplies a binary number by 2

### Logical Right Shifts
When shifting right with a logical right shift, the least-significant bit is lost and a 0 is inserted on the other end.
```
1011 >> 1  →  0101
1011 >> 3  →  0001
```
For positive numbers, a single logical right shift divides a number by 2, throwing out any remainders.

### Arithmetic Right Shifts
Whenn shifting right with an arithmetric right shift, the least-significant bit is lost and the most-significant bit is copied.
```
# Arithmetic Right Shifts: 
# the most significant number for these two numbers are 1, so 1's were inserted during the shift.
1011 >> 1  →  1101
1011 >> 3  →  1111

# the most significant nubmer for these two numbers are 0, so 0's were inserted during the shift.
0011 >> 1  →  0001
0011 >> 2  →  0000
```

If a number is encoded using two's complement, then an arithmetic right shift preserves the number's sign, while a logical right shift makes the number positive.

## Integer overflow
Check out the swift playground called bitManipulation