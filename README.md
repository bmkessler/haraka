# haraka
[![GoDoc](https://godoc.org/github.com/bmkessler/haraka?status.svg)](https://godoc.org/github.com/bmkessler/haraka)

A golang implementation of the Haraka v2 family of hash functions
presented in:

Haraka v2 – Efficient Short-Input Hashing for
Post-Quantum Applications

by Stefan Kolbl, Martin M. Lauridsen, Florian Mendel,
and Christian Rechberger

[https://eprint.iacr.org/2016/098.pdf](https://eprint.iacr.org/2016/098.pdf)

These functions are designed to be fast for fixed-length (512/256-bit)
inputs on processors with AES instructions.  A primary use case is for
hash-based signatures in post-quantum cryptography.  Note, that if your
processor does not have AES instructions then the performance will be 
~10x slower due to software emulation of the AES round function.  Currently,
AES instruction optimization is only implemented for amd64 processors.

AES-NI and software AES (Ref) benchmarks
name            time/op
Haraka256-4     30.8ns ± 0%
Haraka512-4     81.1ns ± 1%
Haraka256Ref-4   469ns ± 0%
Haraka512Ref-4   953ns ± 2%
