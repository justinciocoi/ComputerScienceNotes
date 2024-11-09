**Justin Ciocoi**

**Nov. 15, 2023**

# CSCI 360

## Project 2 Report

#### Part 1

Below is the screenshot demonstrating my password free login using RSA

<img title="" src="file:///C:/Users/Justin/Pictures/marktextImages/199d8cb41692952bbd111aeec40ed3175cfa077f.png" alt="" data-align="center" width="426">

I generated the keys for this project using SSH rather than openSSL, and the format in which they were was unable to be decoded by the openSSL command provided in the project description. To account for this, I generated a sample key on the server under a sample_key directory and used the command to view the various fields of the key. Upon taking the screenshot below, I used the rm command to remove the sample_key directory from your machine.

<img title="" src="file:///C:/Users/Justin/Pictures/marktextImages/b6c4325591c383def95d2803d35db80347882d18.png" alt="" data-align="center" width="288">

****

#### Part 2

Here I will describe the meaning of the various fields shown in the above key:

- *Modulus:* This refers to the modulus, $n$ with which public key cryptography will be done

- *Public Exponent:* will be used in the public portion of the key and a small value is used to speed up encryption of RSA

- *Private Exponent:* will similarly be used in the private portion of the key. a small value cannot be used without compromising the security of RSA

- *Primes 1 and 2:* are prime numbers of roughly equal bit lengths that multiply together to produce the value of modulus $n$

- The rest of the fields: *Exponents 1 and 2,* and *coefficient* are used in the Chinese Remainder Theorem used to speed up the decryption and signature generation portions of RSA

****

#### Part 3

Below is a picture of both the RSA and ECDSA keys I used for this project

<img title="" src="file:///C:/Users/Justin/Pictures/marktextImages/b287dae602f04d170c9bdb074b3e8348a099d52f.png" alt="" data-align="center" width="439">

Here is my login using the ECDSA key

<img title="" src="file:///C:/Users/Justin/Pictures/marktextImages/1f7d3930f0dbe68fe16f446a4445ee1209833e5c.png" alt="" data-align="center" width="363">

    The advantages of ECDSA over RSA can be seen when looking at the keys. Since ECDSA has a shorter key length, computations done in ECDSA are less computationally intensive and can thus be done more efficiently. This is because of the lack of index calculus attack that exists for ECDSA algorithms, since these are the attacks that require RSA to have such long key lengths. The main disadvantage of ECDSA is that it does not have as as much of a track record as RSA does, so while RSA remains feasible, many people will prefer to use what they know works.
