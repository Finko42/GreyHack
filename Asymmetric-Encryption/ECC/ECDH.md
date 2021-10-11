# Elliptic Curve Diffie-Hellman

[ECDH](https://en.wikipedia.org/wiki/Elliptic-curve_Diffie%E2%80%93Hellman) is a protocol for making shared secrets with a second party using public and private keys.
This shared secret can then be used as a symmetric key in a different algorithm.

Elliptic curve cryptography is more secure than RSA, as 160-bit ECC is as secure as 1024-bit RSA.
Here I have implemented it in GreyHack, although all 109-bit ECC and below are considered unsecure.

You may have noticed that the correct curve order is missing from both implementations. This is because the order of an elliptic curve actually takes a long time to compute
therefore I have omitted it (ECDH works fine without it). However, this means that another ECC protocol, 
[ECDSA](https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm), will not work unless standardised curve parameters with pre-computed curve orders like Curve25519
are used (but those require high-bit ECC to be used).

To learn more about ECC check out [this website](https://andrea.corbellini.name/2015/05/17/elliptic-curve-cryptography-a-gentle-introduction/).
