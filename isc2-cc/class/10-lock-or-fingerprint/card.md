# Lesson 10. Lock or Fingerprint

**Listen:** lock-or-fingerprint.mp3 (2 min)

**The idea, in three lines**
- **Encryption** is a lock: reversible with a key, it protects confidentiality. Symmetric (one shared key, AES) is fast for bulk data; asymmetric (a public and private pair, RSA, ECC) solves key sharing and signing. TLS uses both.
- **Hashing** is a one-way fingerprint: any input, fixed length output, no key, no way back. It protects integrity. Change one character and the whole hash changes.
- MD5 and SHA-1 are broken. Passwords get a unique salt plus a slow password hash (bcrypt, Argon2), never reversible encryption.

**Impact:** you can pick the right tool from the job alone: need it back, encrypt; need proof it didn't change, hash.

**Who says it:** 3 of the 3 pages on cryptography teach encryption and hashing this way; none disagree. One page outside them (Heimdal) calls hashing a cipher; it isn't, because a hash has no key and can't be reversed.

**Try it** · Quick Win · 5 min
On paper, write these six jobs: hide a file, prove a download wasn't changed, store a password, send a secret message, keep a lost laptop's files private, check a backup copy matches the original. For each one:
> **1.** Write "lock" (encryption) or "fingerprint" (hash).
> **2.** One line on why: do you need the data back, or proof it didn't change?
> **3.** Next time a download page lists a SHA-256 checksum, notice it: that's the fingerprint at work.

**Rule to keep**
Encrypt to hide, hash to prove nothing changed.

**Skip** · no cost, no catch-up. Lesson 11 is just lesson 11.

**Go deeper (optional)**
- Hashing and encryption, with the hello123 avalanche example: https://www.20i.com/blog/how-encryption-works-from-hashing-to-modern-cryptography/
- Hashing vs encryption, and the mistake both ways (it lists DES as a common cipher; DES is obsolete): https://rippling.com/blog/hashing-vs-encryption
