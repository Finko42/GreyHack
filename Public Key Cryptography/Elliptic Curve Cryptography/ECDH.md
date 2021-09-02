# Elliptic Curve Diffie-Hellman

[ECDH](https://en.wikipedia.org/wiki/Elliptic-curve_Diffie%E2%80%93Hellman) is a protocol for making shared secrets with a second party using public and private keys.
Elliptic curve cryptography is more secure than RSA, as 160-bit ECC is as secure as 1024-bit RSA.
Here I have implemented it in GreyHack, although it is a 27-bit version and therefore not secure.
I haven't been able to get a [ECDSA](https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm) implementation working but you can look at ECDSAconcept.src for ideas.

To learn more about ECDH and ECDSA check out [this website](https://andrea.corbellini.name/2015/05/17/elliptic-curve-cryptography-a-gentle-introduction/).
