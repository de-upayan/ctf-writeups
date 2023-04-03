## Flag
```
grepCTF{tw0_l3v3ls_0f_st3g}
```

## Problem Statement

Then Jesus turned, and seeing them following, said to them, 'what do you SEEK?

\- JOHN 1:38

## Files

*steg.jpg*

<img src="https://user-images.githubusercontent.com/96875426/229539134-acb9be22-e085-44cc-9d6b-043b1ccc0d62.jpg" width="300">

## My solution

From the statement, I gathered that we were meant to use two well-known Brute-forcing tools- `stegseek` and `John the Ripper`.

Brute-forcing *'steg.jpg'* using `stegseek` gave:

```console

upayan@CTF$ stegseek steg.jpg /home/upayan/Documents/CTF/tools/wordlists/rockyou.txt
StegSeek 0.6 - https://github.com/RickdeJager/StegSeek

[i] Found passphrase: "cuteessort37"     
[i] Original filename: "orig.zip".
[i] Extracting to "steg.jpg.out".

```

It revealed a hidden ZIP file *'orig.zip'* which was password-protected. Brute-forcing it using `John the Ripper` gave:

```console

upayan@CTF$ john-the-ripper.zip2john orig.zip > orig.hashes
ver 1.0 efh 5455 efh 7875 orig.zip/flag.txt PKZIP Encr: 2b chk, TS_chk, cmplen=39, decmplen=27, crc=0EA4D68A ts=6E5C cs=6e5c type=0
upayan@CTF$ john-the-ripper orig.hashes --wordlist=/home/upayan/Documents/CTF/tools/wordlists/rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (PKZIP [32/64])
Will run 12 OpenMP threads
Press 'q' or Ctrl-C to abort, 'h' for help, almost any other key for status
jesuslove        (orig.zip/flag.txt)     
1g 0:00:00:00 DONE (2023-04-03 20:11) 100.0g/s 2457Kp/s 2457Kc/s 2457KC/s 123456..280690
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 
upayan@CTF$ 

```

Unzipping the archive using the password `jesuslove` gave me a file *'flag.txt'* containing the flag.
