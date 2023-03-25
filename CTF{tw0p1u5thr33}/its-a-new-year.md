**Flag:**
```
JUCTF{h4h4_1h4t_wa5_3a$y_p34sy}
```

The word **rotten** in the problem statement is a faint allusion to the fact that the cipher is a **ROT** cipher. The second clue hidden in the statement was the fact that the year **2023** was explicitly mentioned, which is of quite some significance. Hit-and-trial decryption with the few different variants of the ROT-cipher is then sufficient to crack the code in reasonable time.


To obtain the flag, we first apply a **ROT-20 Cipher** decryption on the ciphertext using the **94-character printable ASCII** alphabet. This gives us:
`JXCWF~h7h7_4h7tbwd5b3d$|_s37s|}`

Applying a **ROT-23 Cipher** decryption using the same alphabet, gives:
`GU@TC{e4e4\1e4q_ta2_0a!y\p04pyz`

By inspection, it is clear that concatenating alternate characters from the two strings gives us our flag.


![image](https://s3.amazonaws.com/hr-assets/0/1677491058-d7617f103e-tmp.png)

![image](https://s3.amazonaws.com/hr-assets/0/1677491137-96917480fa-tmp.png)


*Alternate approach:*

![image](https://s3.amazonaws.com/hr-assets/0/1677491466-9a1625834d-tmp.png)
