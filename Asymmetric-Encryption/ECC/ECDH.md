# Elliptic Curve Diffie-Hellman

[ECDH](https://en.wikipedia.org/wiki/Elliptic-curve_Diffie%E2%80%93Hellman) is a protocol for making shared secrets with a second party using public and private keys.
This shared secret can then be used as a symmetric key in a different algorithm.

Elliptic curve cryptography is more secure than RSA, as 160-bit ECC is as secure as 1024-bit RSA.
Here I have implemented it in GreyHack, although it is a 27-bit version and therefore shouldn't be secure (all 109-bit ECC and below are unsecure).

***However***, in order to break ECC, you need to solve the discrete log problem for given curve parameters, which requires the correct curve order. Calculating the order of an
elliptic curve is done by Schoof's algorithm or the Schoof–Elkies–Atkin algorithm. Unfortunately, even though these algorithms are faster than previous methods, they still are
pretty slow even for small curves (my computer took 15 seconds to calculate the order of y^2 = x^3 + 2a + 3 GF(97)), which is why I didn't put the true curve order in the source code.
This means that my 27-bit ECDH implementation might actually be secure (enough) since it would take a beefy computer and probably a few days to figure the true order of a curve with a 
27-bit p, and even then you could simply change curve parameters (just make sure your friends use the same parameters).

TL;DR: Just calculating the order of the elliptic curve in my implementation is harder than using the normal cracking algorithms (Baby-step giant step and Pollard Rho are instant on my 
computer) so my ECDH might be secure.

Still, I wouldn't use this ECDH for anything really important.

I haven't been able to get a [ECDSA](https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm) implementation working but you can look at ECDSAconcept.src for ideas.

To learn more about ECDH and ECDSA check out [this website](https://andrea.corbellini.name/2015/05/17/elliptic-curve-cryptography-a-gentle-introduction/).
