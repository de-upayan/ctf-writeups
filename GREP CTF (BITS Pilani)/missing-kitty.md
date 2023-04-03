## Flag
```
GREP{steghide,Sw33t_l1ttle_k1tt3n}
```

## Problem Statement

My kitty is missing. Can you find her ? Last seen saying meow meow under the blanket !! Where is she HIDEing

FLAG FORMAT: ``GREP{tool used,flag found}`` Remove brackets

## Files

*Missing.jpg*

<img src="https://user-images.githubusercontent.com/96875426/229532620-21a046c3-5580-40a0-b106-84a6e0fe0557.jpg" width="500">

## My solution

Brute-forcing using `stegseek` yielded the following:

```console

upayan@CTF$ stegseek Missing.jpg /home/upayan/Documents/CTF/tools/wordlists/rockyou.txt
StegSeek 0.6 - https://github.com/RickdeJager/StegSeek

[i] Found passphrase: "kitty123"
[i] Original filename: "secret.txt".
[i] Extracting to "Missing.jpg.out".

```

<br>

*secret.txt*

```

Dk what's this, some kitten language

memmemmmmeemmememeemeemmmeemeemmmeemeeeemmemmmmmmeemeememeeeemmemmemmmmmmeememeemeememmemeeememmmeeememmmeeeemmemmemeemmmmmmememmmmmememmemmmeemmeememmemeemeeemmeemmmmemeemeemmmeemeemmmeeeemmemmemmmmmmeeeemmemeemeeeemeeemememmemmmmmmeemmeemmeemeeeemeeemememeemeeemmeemmemmmmemmmmmmeememmmmeemmememeeemmemmmemeeemmmemmmmmmemmemmemmemmmmmmeemmmmemeemeememmemmmmmmeemmemmmeemmememeemeemmmeememmemeemmeeemeememmmmeeememmmeemmememeemmemmmmemeeemmmmmememmmmmememmemememmmeemmmmemeememeemeemmememmemmmmmmeememmemeeememmmmemeemmmmemmmmmmeememmmmeemmememeeemmemmeemmememmemmeeemeeemmeemmemmmmmmeeeemmemeemeeeemeeemememeeemmemmmemmmmmmeemmeeemeememmemeemmeemmeeememmmmmmememmeemmeemmeemeemmmeemmmmemeemmeeemmemmmmmmmeeememmmemmmmmmeeeemeemememmeemeeemeeemmeemmeemmeemmeemeeememmmemeeeeemeemeemmmmeemmmemeeememmmeeememmmeemeemmmeemmemememeeeeemeememeemmeemmmemeeememmmeeememmmmeemmeemeemeeemmeeeeeme

```

After trying many unsuccessful approaches from this point (including looking into [wixette/meowlang](https://github.com/wixette/meowlang) and [kittenlang](https://kittenlang.org/)), I noticed that the given string had exactly **888** characters, which is a *multiple of 8*. Furthermore, the string consists of only **two** characters 'm' and 'e'. So, I guessed it might be a **Binary encoded string** with letter substitutions for 0 and 1. Trying out the two possible configurations of mapping bits to the letters gave me the flag.

```python

## author: twoplusthree

C = "memmemmmmeemmememeemeemmmeemeemmmeemeeeemmemmmmmmeemeememeeeemmemmemmmmmmeememeemeememmemeeememmmeeememmmeeeemmemmemeemmmmmmememmmmmememmemmmeemmeememmemeemeeemmeemmmmemeemeemmmeemeemmmeeeemmemmemmmmmmeeeemmemeemeeeemeeemememmemmmmmmeemmeemmeemeeeemeeemememeemeeemmeemmemmmmemmmmmmeememmmmeemmememeeemmemmmemeeemmmemmmmmmemmemmemmemmmmmmeemmmmemeemeememmemmmmmmeemmemmmeemmememeemeemmmeememmemeemmeeemeememmmmeeememmmeemmememeemmemmmmemeeemmmmmememmmmmememmemememmmeemmmmemeememeemeemmememmemmmmmmeememmemeeememmmmemeemmmmemmmmmmeememmmmeemmememeeemmemmeemmememmemmeeemeeemmeemmemmmmmmeeeemmemeemeeeemeeemememeeemmemmmemmmmmmeemmeeemeememmemeemmeemmeeememmmmmmememmeemmeemmeemeemmmeemmmmemeemmeeemmemmmmmmmeeememmmemmmmmmeeeemeemememmeemeeemeeemmeemmeemmeemmeemeeememmmemeeeeemeemeemmmmeemmmemeeememmmeeememmmeemeemmmeemmemememeeeeemeememeemmeemmmemeeememmmeeememmmmeemmeemeemeeemmeeeeeme"

def byte_string_to_ascii(S):
    n = len(S)
    ascii_str = ""

    assert n % 8 == 0

    for i in range(0, n, 8):
        ascii_str += chr(int(S[i : i + 8], 2))

    return ascii_str


X = C.replace("m", "0").replace("e", "1")

print(byte_string_to_ascii(X))

```

```console

upayan@CTF$ python3.8 main.py
Hello my kitty,

Finally you found her. I am delighted.

Take it, here's your gift
flag : {Sw33t_l1ttle_k1tt3n}
upayan@CTF$ 


```
