## Flag
```
GREP{W3lc0me_t0_GR3P_CTF}
```

## Problem Statement

Finally, the clock ticks 3:48 am and I got approved. **TIME** flies when you are playing **CTF**. I welcome you all to GREP CTF, enjoy !! Oops, approved of what and where 🤔, I leave that to you, gn....

HINT : Follow the bold path and you will directly get your flag !

## Files

None

## My solution

I checked out the website [ctftime.org](https://ctftime.org/), and on the page for [GREP CTF](https://ctftime.org/ctf/918), I found the following string: 

`475245507b57336c63306d655f74305f475233505f4354467d`

![image](https://user-images.githubusercontent.com/96875426/229511166-190755fc-ec8f-4a53-bf99-67e2352cc188.png)

Converting this string from **HEX** encoding to ASCII gave me the flag.

```console

upayan@CTF$ echo 475245507b57336c63306d655f74305f475233505f4354467d | xxd -r -p
GREP{W3lc0me_t0_GR3P_CTF}

```
