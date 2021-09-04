# Elliptic Curve Diffie-Hellman

[ECDH](https://en.wikipedia.org/wiki/Elliptic-curve_Diffie%E2%80%93Hellman) is a protocol for making shared secrets with a second party using public and private keys.
This shared secret can then be used as a symmetric key in a different algorithm.

Elliptic curve cryptography is more secure than RSA, as 160-bit ECC is as secure as 1024-bit RSA.
Here I have implemented it in GreyHack, although it is a 27-bit version and therefore shouldn't be secure (all 109-bit ECC and below are unsecure).

You may have noticed that the curve order is incorrect. This is because Schoof's algorithm is surprisingly slow even for small curves. I ran a python version of the algorithm
(I couldn't get the more offical C++ implementation to work) for 24 hours and it still couldn't calculate the curve order. I recorded the time it took the algorithm to calculate
a bunch of different p values for curves with the same a and b, graphed them on Desmos, and found the best case scenario being 109 days to calculate the correct curve order.

This also means that using the regular cracking algorithms to break ECC (Baby-steps giant-steps and Pollard Rho) don't actually work because they require the correct curve order.
Still, a person could still bruteforce a private key since it is only 27-bits.

I haven't been able to get a [ECDSA](https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm) implementation working but you can look at ECDSAconcept.src for ideas.
Most likely it won't work until the correct curve order is found, but if that happens the protocol can be cracked instantly anyways with one of the aforementioned cracking algorithms 
(as long as a low bit curve order is used).

To learn more about ECDH and ECDSA check out [this website](https://andrea.corbellini.name/2015/05/17/elliptic-curve-cryptography-a-gentle-introduction/).
