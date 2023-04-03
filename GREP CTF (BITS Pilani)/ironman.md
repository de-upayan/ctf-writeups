## Flag
```
grepCTF{i_d0n't_f3el_s0_g00d}
```

## Problem Statement

I'm ironm-an.

HINT - LSB steganography

## Files

*ironman.png*

<img src="https://user-images.githubusercontent.com/96875426/229525694-81e22f87-f3a3-44a2-aea0-b223b86b33c3.png" width="300">

## My solution

Brute-forcing `zsteg` using the `-a` (all known) switch gave me the flag.

```console

upayan@CTF$ zsteg -a ironman.png

```

```console

.
.
.
b8,rgb,lsb,xy,prime .. text: " $(.+/729D3?I1BJ6DQ8CO4@L9DP;GS5AO3AL0>I2>I6?J;>F79?<10:0(>1,C61A5,@0#F6)J5*F4(G5)D2#J8)F4$C4%@0!G7(E5&E5&F6'C3'E5(I9,K8,E5(A1$>-%;&"
b8,bgr,lsb,xy,prime .. text: ".($7/+D92I?3JB1QD6OC8L@4PD9SG;OA5LA3I>0I>2J?6F>;?9701<(0:,1>16C,5A#0@)6F*5J(4F)5G#2D)8J$4F%4C!0@(7G&5E&5E'6F'3C(5E,9I,8K(5E$1A%->"
b1,rgb,lsb,yx       .. text: "grepCTF{i_d0n't_f3el_s0_g00d}\n"
b1,bgr,lsb,yx       .. <wbStego size=915921, data="\x19QP\xFBl]\xB4\x18\xD8\xAD"..., even=false, enc="wbStego 2.x/3.x", mix=true, controlbyte="\xC4">
b2,g,msb,yx         .. text: "UBUUUDUlA"
b3,g,lsb,yx         .. text: "rO&I/PI\"\""
b3,g,msb,yx         .. text: "$Im+I*MR"
.
.
.

```
