# Rivest–Shamir–Adleman

RSA is public key cryptography system used for generating public and private keys that can be used to encrypt and decrypt symmetric keys.

RSA is unfortunately not secure below 1024 bits so my implementation should not be considered secure (in fact it can be broken with just an online integer factorization calculator).

As for how to encrypt and decrypt using RSA:
1. Generate a private and public key (d is the private key and both n and e are part of the public key).
2. Take the number you want to encrypt.
3. Encrypt the number by calculating ``m^e mod n`` where m is the number you wish to encrypt.
4. Decrypt the number by calculating ``c^d mod n`` where c is the encrypted number.
