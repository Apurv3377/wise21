#### Sheet 2 
##### Dated 16.11.2021
##### Compiled Deo Pranav


#### Exercise 2


**TRNG 1**

```
00100000000011111100000000100100
01111111111111100000100011010101
10000001110111111111111111100100
00000011111111001011101111111111
11111011111011110111010111101111
```

**TRNG 2**

```
00110110100110110010000111000010
00111110001101111101111000100001
01001000110100111110000111001100
00111000000001100010110001101000
11010110101010010010101010111001
```

**2.1 Compare quality of given TRNGs, list observations.**


**2.2 Apply the Von-Neumann correction to the random sequences**

*Method*

- Take two random bits and compare, if they are same discard the bits, and if not then use the first bit.

- Why? Suppose that the `Pb(0)==x && Pb(1)==y` such that `x!=y`, then the ` Pb(01)==Pb(10)==x*y `. The ` Pb(00)==x^2 || Pb(11)==y^2 ` are discarded.


**2.3 Apply parity based method on the sequence given in the task using a chunk size of 16**

*Method*

- Divide stream in n bits.

- Calculate XOR calculation of the bits, and discard the chunk.

`n=16`

```
XOR TABLE REF

A   B  A_XOR_B

0   0     0
0   1     1
1   0     1
1   1     0

```

*Dividing the Sequence of TRNG 1 into chunk size of 16 ::*

```
0010000000001111      1100000000100100   ---->    1     0
   (Chunk 1)              (Chunk 2)

0111111111111110      0000100011010101   ---->    0     0


1000000111011111      1111111111100100   ---->


0000001111111100      1011101111111111   ---->


1111101111101111      0111010111101111   ---->

```

*Dividing the Sequence of TRNG 2 into chunk size of 16 ::*

```
0011011010011011      0010000111000010   ---->


0011111000110111      1101111000100001   ---->


0100100011010011      1110000111001100   ---->


0011100000000110      0010110001101000   ---->


1101011010101001      0010101010111001   ---->



```

#### Task 3:  Cellular Automata Shift Register

(175)base_10 = (10101111)base_2

(242)base_10 = (11110010)base_2

*Rule Tables for (175)base_10*

|  Number |  Neighborhood  |  Rule Set |
|---------|----------------|-----------|
|    7     |    1 11           |    1       |
|    6     |    1 10           |    0       |
|    5     |    1 01           |    1       |
|    4     |    1 00           |    0       |
|    3     |    0 11           |    1       |
|    2     |    0 10           |    1       |
|    1     |    0 01           |    1       |
|    0     |    0 00           |    1       |


*Rule Tables for (242)base_10*

|  Number |  Neighborhood  |  Rule Set |
|---------|----------------|-----------|
|    7     |    1 11           |    1       |
|    6     |    1 10           |    1       |
|    5     |    1 01           |    1       |
|    4     |    1 00           |    1       |
|    3     |    0 11           |    0       |
|    2     |    0 10           |    0       |
|    1     |    0 01           |    1       |
|    0     |    0 00           |    0       |


|  Rule List |  175  | 242  |  175 |  175  |  242 |  175 |  242  |  242 |
|---------|----------------|-----------|---------|----------------|-----------|---------|----------------|-----------|     
 | State 0 | 0  | 1  | 1 | 1  | 0  | 1  | 1 | 0 |
 | State 1 | 1  | 0  | 1 | 1  | 1  | 1  | 1 | 1 |


    

#### Task 4 : PUFs : Physically Unclonable Functions


**4.1 Three PUF application and how PUFs are used for it?

PUFs can be used for 
- Identification and Authentication

- Storing keys and hashes

-  Random Number Generators



