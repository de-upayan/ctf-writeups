## Flag
```
grepCTF{m0th3r_of_dr4g0n5}
```

## Problem Statement

I got this file of 10000 lines and someone said it's format was Quick Reload.

## Files

*stormborn.txt*

```

0
0
0
0
0
0
0
0
0
0
0
0
0
0
0
0
0
0
0
0
0
0
0
0
0
0
0
0
1
1
1
1
.
.
.

```

## My solution

The problem statement hints at the term **QR** by means of an acronym. Additionally I observed that the file contains exactly **10000** lines containing either **0** or **1**. Hence, I guessed that we might need to rearrange the 10000 values into a **100 X 100 square matrix** and plot it obtain a QR code.

```python

## author: twoplusthree

import numpy as np
from matplotlib import pyplot as plt

data = np.zeros((100, 100))

with open("stormborn.txt", "r") as f:
    idx = 0

    for bit in f:
        bit = int(bit)
        data[idx // 100][idx % 100] = bit

        idx = idx + 1

plt.imshow(data, interpolation = "nearest")
plt.show()

```

![image](https://user-images.githubusercontent.com/96875426/229530417-a30cfcf7-a29b-49b5-a5bc-492ed4eb2a40.png)

Scanning the QR reveals the flag.
