## Flag
```
grepCTF{r3j3ct_hum4n1ty_g0_b4ck_t0_m0nk3}
```

## Problem Statement

I was playing guitar and then this monkey came and broke all my strings 😢

## Files

*monke.jpg*

<img src="https://user-images.githubusercontent.com/96875426/229501365-fcf9b9ae-763c-4918-83b5-88503b3c4caa.jpg" width="300">

## My solution

Hinted by the problem statement, I used `strings` to list out sequences of printable strings in the binary hexdump of the file.

```console

upayan@CTF$ strings monke.jpg

```

```console

...
F#hI!U
;xJ*
wcbJ
/Q9xB
zbQ_
6mF*
Ri1BM#
1&Z5
a!{W
:CI%
e*>YI
-2My
_vxc
Z3JlcENURntyM2ozY3RfaHVtNG4xdHlfZzBfYjRja190MF9tMG5rM30K
upayan@CTF$ 

```

Decoding the last string using Base64 gives us the flag.

```console

upayan@CTF$ echo Z3JlcENURntyM2ozY3RfaHVtNG4xdHlfZzBfYjRja190MF9tMG5rM30K | base64 --decode
grepCTF{r3j3ct_hum4n1ty_g0_b4ck_t0_m0nk3}

```
