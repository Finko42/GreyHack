# Advanced Encryption Standard

AES is a cipher used to encrypt and decrypt messages using a symmetric key. I have implemented the 128-bit version and it uses
[CBC](https://en.wikipedia.org/wiki/Block_cipher_mode_of_operation).

My implementation works the same as real life and is as secure as real life implementations of AES. The only unsecure part of my implementation is that it uses ``rnd()``, which is
(probably) not cryptographically secure. However, the algorithm should still be sufficiently secure for users of GreyHack.

If you want to know more about AES, you can look at the [official docs](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.197.pdf).
