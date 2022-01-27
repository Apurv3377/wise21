#### Security of Embedded Systems - Assignment
###### Dated:  28.01.2022
###### Compiled -  Deo, Pranav


**1. (2 points) Many banks issue hardware tokens for authenticating their e-banking customers. These hardware tokens**  
**- require the user to enter a code into the hardware token and** 
**- generate  a  one-time  password  that  the  user  enters  as  password  into  the  e-banking application (website).** 
**Explain why this is considered a two-factor authentication and explain if this is a good or bad two factor authentication system.**



**2. (3 points) Recall the “STRIDE” mnemonic used in threat modelling. In the below table, you are given certain threat/problem examples. Fill the “Threat” and “Property Violated” columns in the table with corresponding elements where “Threat”: STRIDE threats (each letter stands for a threat) and “Property Violated”: Confidentiality, Integrity, Authentication, Authorization, Availability, Non-repudiation.**

|  Threat 	| Property Violated   	|  Example  	| 
|---	|---	|---	|
|   Information Disclosure	| Confidentiality 	|  Allowing someone to read the Windows source code; publishing a list of customers to a website 	|
|  Tampering of Data	|   Integrity	|  Modifying a DLL on disk or DVD, or a packet as it traverses the network 	|
|   Elevation of Privileges	|   Authorization	|   Allowing a remote internet user to run commands, going from a limited user to admin	|
|  Spoofing of Identity 	|   Authentication	|  Pretending to be any of Bill Gates, Paypal.com, or ntdll.dll 	|
|   Repudiation	|   Non Repudiation	| “I didn’t send that email”, “I didn’t modify that file”, “I certainly didn’t visit that website!”   	|
|   Denial of Service	|   Availability	|  Crashing Windows or a web site, sending a packet and absorbing seconds of CPU time, or routing packets into a black hole 	|





**3. (6 points) What is the output of the first round of the DES algorithm [2] when the plaintext and the key are both**
**- all zeros?**
**- all ones?**
**Calculate and give details step by step using paper, pen, and a simple calculator. You may want to write a small program to check the correctness of your answers (or find online tools for verification).**

**5. (2  points)  Assume  a  (small)  company  with  120  employees.  A  new  security  policy  demands  encrypted message exchange with a symmetric cipher. How many keys are required, if you are to ensure a secret communication for every possible pair of communicating parties?**


Suppose that there are 120 employees in a company, and we assume that there is not one single common symmetric key that every employee uses to encrypt and decrypt communication ( as such this is very unsafe), then :

- Each party/ pair of employees would require a single key to facilitate communication between them.
- For `n` number of employees, the number of pairs that can be formed are `n*(n-1)`. (Since the possibility of choosing first member of pair is `n` and then we have `n-1` options to choose second member.)   
- Now since the order of members in the pair does not matter, we need to divide this number further by two.

The number of total symmetric keys required can be given by the following formula:
$$ \begin{bmatrix}n \\2 \end{bmatrix}  =  \frac{n * (n-1)}{2} $$


So for n = 120,

the total symmetric keys required are   = $$ \begin{bmatrix} 120 \\2 \end{bmatrix}  =  \frac{120 * (120-1)}{2} $$
                                        = $$ \begin{bmatrix} 120 \\2 \end{bmatrix}  =  \frac{120 * (119)}{2} $$
                                        = 7140

Thus a total of `7140` symmetric keys are required for secure communications.

**6. (6 points) Alice wants to compute an RSA key-pair. She chooses the “large” prime numbers p = 13 and q = 7. Complete the RSA key generation for Alice, i.e., compute an RSA key pair for her. Describe briefly the intermediate steps of your calculation.(Hint: You might want to make use of the following fact: 7-1 mod 72 = 31.)**

*Let us first look at how RSA key pairs are calculated:*

```
- Choose p = 3 and q = 11
- Compute n = p * q = 3 * 11 = 33
- Compute φ(n) = (p - 1) * (q - 1) = 2 * 10 = 20
- Choose e such that 1 < e < φ(n) and e and φ(n) are co prime. Let e = 7
- Compute a value for d such that (d * e) % φ(n) = 1. One solution is d = 3 [(3 * 7) % 20 = 1]
- Public key is (e, n) => (7, 33)
- Private key is (d, n) => (3, 33)
- The encryption of m = 2 is c = 27 % 33 = 29 
- The decryption of c = 29 is m = 293 % 33 = 2
```

For our example:

```
Alice's prime number => 

p = 13
q = 7

Thus n = p * q = 13 * 7 = 91

Thus   φ(n) = (p - 1) * (q - 1) 
            = (13 -1 )*(7 -1 ) 
            = 72

Now we select a value 'e', such that 1 < e < φ(n) and e and φ(n) are co prime.

So, let e = 5

Thus the public key for Alice = PBk = (e, n) = (5, 91) 

Now we shall calculate 'd', such that (d * e) % φ(n) = 1.

    d = ( 29 * 5) % 72 = 1 is possible.
    d = ( 31 * 5) % 72 = 11 also is possible.


    Thus d = 29

Thus the private key for Alice = PRk = (d, n) = (29, 91) 

```

If Bob wants to send a message to Alice, He will use the public key of Alice to encode the Message:

```
Thus the ciphertext = [(message)^e] mod n
                    = [(TOPSECRET)^5] mod 91
```

**- Bob wants to send Alice the message “topsecret” as encrypted. Encode the letters by their position in the alphabet (e.g., the letter "a" is represented by the number 1) and compute the ciphertext for each character of the message.**



```

```
**- Alice wants to send Bob the signed message “signature”. Encode the letters by their position in the alphabet (e.g. the letter "a" is represented by the number 1) and compute the signature for each character of the message (i.e., to simplify the problem, we do not hash the message).**


**7. (3 points) As you have seen in the lectures, public-key cryptography can be used for encryption  and key exchange. Furthermore, it has some properties (such as non-repudiation) which are not  offered  by  secret  key  cryptography.  So  why  do  we  still  use  symmetric  cryptography  in  current   applications?**


- Embedded systems or sub-systems often deploy devices that have very low or `sub-par computation capabilities.`
- Such devices are `heavily constrained with the amount of computation power, RAM, sand storage space`.`
- Thus, it is not possible for such device to perform certain asymmetric cryptographic functions.
    (For example, it would be very difficult for a class A device to perform a heavy `2048 bit RSA encryption/ decryption`.)

- Thus we make use of lightweight symmetric keys, such as the `Present Cipher, Simon Cipher, Speck cipher`etc. ALl these implementations are symmetric block ciphers, which can be deployed with key lengths of `128 bits` or `80 bits` respectively.

- However, one problem that is persistent with symmetric keys, and to some extent with asymmetric keys is the issue of `key management and distribution.`

- For a symmetric key based environment, for each device to use separate keys to interact with other devices, we would need `{n(n-1)}/2`. IS is possible for such contradicted devices to store these keys. And as embedded systems are often scalable in in an IoT infrastructure, how would a new added device share, receive and store these keys while having constrained resources.
 
**8. (4 points) One of the most attractive applications of public-key algorithms is the establishment of  a secure session key for a private-key algorithm such as AES over an insecure channel.**
**Assume Bob has a pair of public/private keys for the RSA cryptosystem. Develop a simple protocol  using  RSA  which  allows  the  two  parties  Alice  and  Bob  to  agree  on  a  shared  secret  key.  Who  determines the key in this protocol, Alice, Bob, or both?** 

We are to assume that:

1. Bob has a pair of public and private keys.
2. Alice has no keys.
3. Alice does not know the public key of Bob.

We need to establish a symmetric session key between Alice and Bob such that they can communicate with each other.

The following rules can be followed to establish a basic protocol for simple secure communication:

1. Bob sends to Alice: His `public key`, along with his `identity B` a nonce `Nb` which is  encrypted with his `private key`.
2. Alice receives the message, and now has possession of Bob's public key. She then uses the `public key` to decipher the message and understands that it is `Bob`.
3. Alice then decides on a symmetric key that can be used as a `session key` for subsequent communication.
4. Alice uses the `public key` of Bob to encrypt the following: Her `identity A`, her `nonce Na`, Bob's `nonce Nb` and the `session key`. This message can be sent over to Bob now.
5. Bob will then use his `private key` to decrypt the message and gets the `session key`.
6. Bob can the confirm the message receipt of the message by responding with  Alice's `nonce Na` encrypted in the session key.

- Here, it is Alice that decides which session key to use, as Bob cannot  be completely sure that the message he sends to Alice will not be intercepted, neither does he have any way of encrypting them such that Alice can decipher them safely.

**9. (4 points) Consider the C program for which we assume that in the block starting at line 24, code  with administrative privileges is executed. The program has two different vulnerabilities. Name the vulnerabilities and explain them briefly.**

Code:

```
#include <stdio.h>
#include <string.h>

int main(void)
{
    
    
    char buff[15];
    int pass = 0;
    static const char secret[] = "deopranav";
    
    printf("Please input password \n");
    gets(buff);
    
    if(strcmp(buff, secret))
    {
        printf("WrongPassword");
    }
    else
    {
        printf("CorrectPass");
        pass = 1;
    }
    
    if(pass)
    {
        printf("root access given");
    
    }

    return 0;
}
```

1. The following code suffers from a `Buffer Overflow` vulnerability. 

    - `buffers` are essentially temporary storage areas used to hold information.
    - `buffers` are used to store user data along with control flow information, on a stack.
    -  When the user data may exceed the `buffer` memory size, it may overflow the `buffer` and also corrupt the control flow information.


The code `gets()` will keep reading until `EOF` is reached or a newline char is input. As such using `gets()` may lead to the buffer to overflow. 
This can be fixed by using `fgets()`.

Output of code when Buffer Overflows:

```
main.c:(.text+0x36): warning: the `gets' function is dangerous and should not be used.
Please input password 
deopranav1234567
*** stack smashing detected ***: terminated
```

- Note that the compiler already warns that `gets()` is a deprecated function and should not be used.

2. The code also suffers from a `Side Channel Attacks`. The password of the code has been stored in a `static constant` variables, thus exposing it to various side channel attacks such as `Timing Attacks`, wherein the attacker can measure the time taken to compare the correct character as opposed to an incorrect password character. This makes it simpler to break the password, even simpler than brute forcing.


**10. (2 points) You have two security testing tools with the following false positive and negative rates:**
**Assume you want to minimize the risk of delivering insecure software to customers. Would you use Tool A or Tool B? Why?**

**Tool A**
False Positive Rate 20%
False Negative Rate 70%

**Tool B**
False Positive Rate 40%
False Negative Rate 40%


- There are two ways at analyzing the situation, one from a developer perspective, and one from the perspective of a security expert.
- SInce we are concerned with minimizing the risk of delivering insecure software, we shall analyse the situation as a security expert.

**as security experts, we want a tool that has the least amount of `false negative rates`, since `false negative rates` simply increase the risk associated with system.**

`false negative rates`  are the number of instances where an existing weakness/ vulnerability is not reported by the tool. 
`false positive rates`  are the number of instances where a non-existing weakness/ vulnerability is reported falsely by the tool. 

We are not bothered with the non-existing weakness that is reported falsely, we are more concerned if an existing problem/ weakness is not reported successfully.

Thus we will choose `Tool B`, which has the least `false negative rates` among the two tools to compare.


