## Flag
```
grepCTF{n3v3r_tru1y_r4nd0m}
```

## Problem Statement

Now that my program is truly random, you'll never be able to guess the flag.

## Files

*encrypt.py*

```python

import random
flag = open('flag.txt').read()

rand_seed = random.randint(0, 999)
random.seed(rand_seed)
encrypted = ''

for chr in flag:
    encrypted += f'{(ord(chr) ^ random.randint(0, 255)):02x}'

with open('out.txt', 'w') as f:
    f.write(encrypted)

```

*out.txt*

```

a282b415279f5aa08cd4649515268910b8968a1eabda7c1bb2898c

```

## My solution

Reverse-engineering the encryption algorithm, and brute-forcing all possible values of `rand_seed` gave me the flag.

```python

## author: twoplusthree

import random

C = open("out.txt").read()

D = []
for i in range(0, len(C), 2):
    D.append(int(C[i : i + 2], 16))

for rand_seed in range(0, 1000):
    random.seed(rand_seed)
    decrypted = ""

    for x in D:
        decrypted += chr(x ^ random.randint(0, 255))

    if decrypted.find("CTF") != -1:
        print(decrypted)
        break

```

```console

upayan@CTF$ python3.8 main.py
grepCTF{n3v3r_tru1y_r4nd0m}

```
