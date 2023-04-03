## Flag
```
grepCTF{3sot3r1c_l4ngu4g3s_4r3_0k!}
```

## Problem Statement

2 levels of eso should make my message impossible to decipher.

## Files

*msg.txt*

```

+++++ +++[- >++++ ++++< ]>+++ +++++ +++++ ++.<+ ++++[ ->+++ ++<]> +++++
++.-- --.<+ +++++ +[->- ----- -<]>- ----- ----- -.<++ +[->- --<]> -----
.<+++ +++[- >++++ ++<]> +++++ +++++ +.<++ +++[- >++++ +<]>+ +++++ +.---
-.<++ +++++ [->-- ----- <]>-- ----- ----- .<+++ [->-- -<]>- ----. <++++
++[-> +++++ +<]>+ +++++ +++++ .<+++ ++[-> +++++ <]>++ +++++ .---- .<+++
++++[ ->--- ----< ]>--- ----- ----. <+++[ ->--- <]>-- ---.< +++++ +[->+
+++++ <]>++ +++++ ++++. <++++ +[->+ ++++< ]>+++ ++++. ----. <++++ +++[-
>---- ---<] >---- ----- ---.< +++[- >---< ]>--- --.<+ +++++ [->++ ++++<
]>+++ +++++ +++.< +++++ [->++ +++<] >++++ +++.- ---.< +++++ ++[-> -----
--<]> ----- ----- --.<+ ++[-> ---<] >---- -.<++ ++++[ ->+++ +++<] >++++
.
.
.

```

## My solution

I recognised the given file as [**BrainF\*ck**](https://en.wikipedia.org/wiki/Brainfuck) code. Running the code gave the following output:

```console

upayan@CTF$ bf msg.txt
Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook! Ook? Ook! Ook! Ook. Ook? Ook. Ook. Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook.
Ook. Ook? Ook. Ook? Ook! Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook.
Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook? Ook! Ook! Ook. Ook? Ook.
Ook. Ook. Ook. Ook. Ook. Ook? Ook. Ook? Ook! Ook. Ook? Ook. Ook. Ook. Ook.
Ook! Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook? Ook! Ook! Ook.
Ook? Ook! Ook! Ook! Ook! Ook! Ook! Ook? Ook. Ook? Ook! Ook. Ook? Ook! Ook!
Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook.
Ook. Ook! Ook? Ook! Ook! Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook? Ook.
.
.
.

```

Running the above output using the [**Ook!** Programming Language Interpreter](https://www.dcode.fr/ook-language) gave me the flag.

![image](https://user-images.githubusercontent.com/96875426/229524897-1e3946d7-506b-4d26-9749-751db3ac8dbd.png)
