**Justin Ciocoi**

**Nov. 27, 2023**

# CSCI 360 Textbook Notes

## Chapter 9: Elliptic Curve Cryptosystems

#### 9.1: How to Compute with Elliptic Curves

- Elliptic curve cryptosystems, like other public-key cryptosystems, is based on the generalized discrete logarithm problem

- Thus, we must first find a cyclic group on which we can build our cryptosystem

- The mere existence of such a cyclic group is not enough though, as the group must be computationally hard to prevent against brute-force attacks

- **9.1.1: Definition of Elliptic Curves**
  
  - The *elliptic curve* over $\Z_p,\ p>3$, is the set of all pairs $(x, y)\in\Z_p$ which fulfill
    
    $$
    y^2\equiv x^3+a\cdot x+b\ \text{mod}\ p
    $$
    
    together with an imaginary point of infinity, $\infty $, where 
    
    $$
    a,b\in\Z_p
    $$
    
    and the condition $4\cdot a^3+27\cdot b^2 \ne0\ \text{mod}\ p$ 
    
    <img title="" src="file:///C:/Users/Justin/Pictures/marktextImages/94ee22d03485c0aa791dc9b0351c7906752a3ea0.png" alt="" data-align="center" width="429">

- **9.2.2: Group Operations on Elliptic Curves**
  
  - Point addition, $P+Q$ and point doubling, $P+P$ can be achieved using the following methods respectively
    
    <img title="" src="file:///C:/Users/Justin/Pictures/marktextImages/3f88c8c714f3780715e1b99e5935042c30141ea2.png" alt="" data-align="center" width="318">
    
    <img title="" src="file:///C:/Users/Justin/Pictures/marktextImages/43f3360cddac414b3eb2b95939611c4968750060.png" alt="" data-align="center" width="332">
  
  - In addition, we can find the inverse of a point on an elliptic curve by finding its reflection over the x-axis

#### 9.2: Building a Discrete Logarithm Problem with Elliptic Curves

- **Theorem 9.2.1**
  
  The points on an elliptic curve together with $\infty$ have cyclic subgroups, and under certain conditions all points on an elliptic curve form a cyclic group

#### 9.3: Diffie-Hellman Key Exchange with Elliptic Curves

- **Elliptic Curve Diffie-Hellman Domain Parameters**
  
  1. Choose a prime $p$ and the elliptic curve
     
     $$
     E:y^2\equiv x^3+a\cdot x+b\ \text{mod}\ p
     $$
  
  2. Choose a primitive element $P=(x_p, y_p)$
  
  The prime $p$, the curve given by its coefficients $a, b$, and the primitive element $P$ are the domain parameters

- Key exchange here is done in essentially the same way as conventional Diffie-Hellman key exchange
  
  <img src="file:///C:/Users/Justin/Pictures/marktextImages/a537df64d4387cc46da98468f63e06bc4e5dc08e.png" title="" alt="" data-align="center">

#### **9.4: Security**

- The reason why elliptic curves are used in modern cryptography is the fact that they have very good one way properties

- As opposed to the simpler discrete logarithm problems based in $\Z_p^*$, discrete logarithm problems in elliptic curve groups are not vulnerable to index calculus attacks

- Thus, the best remaining algorithms when attacking an elliptic curve discrete logarithm problem are Shanks' baby-step giant-step methos and Pollard's rho method

- With these attacks, the number of computations needed is the square root of the cardinality of the group
  
  - Therefore, a prime $p$ should be chosen to be 256 bits in order to provide 128 bits of security, since $\sqrt{2^{256}}=2^{128}$

#### 9.5: Implementation in Software and Hardware

- In practice, a core requirement for using ECC in cryptography is that the cyclic group formed by the curve points has prime order

- When implementing elliptic curve cryptography, it is useful to view an ECC scheme as a structure with four layers
  
  - On the bottom layer, modular arithmetic is performed
  
  - On the next layer, the two group operations, point addition and point doubling, are realized
  
  - On the third layer, scalar multiplication is realized, which uses the group operations of the previous layer 
  
  - The top layer implements the protocol, such as ECDH (Elliptic Curve Diffie-Hellman) or ECDSA (Elliptic Curve Digital Signature Algorithm)
