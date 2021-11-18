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

- Why? Suppose that the `Pb(0)= x` and `Pb(1)=y` such that `x != y`, then the `Pb(01) == Pb(10)== x*y`. The ` Pb(00) == x^2 || Pb(11) == y^2` are discarded.

