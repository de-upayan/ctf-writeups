**Flag:**
```
JUCTF{con9r4t5_y0u_t00k_th3_r3d_pi11}
```

We are given a folder consisting of 9 image files, numbered serially according to the format *'pi3c3_x.png'*. Simple inspection tells us that they are part of a **QR Code**, which must be **assembled** and **scanned** to retrieve the flag.


The image provided in the problem statement hints at the fact that the pieces need to be arranged in the fashion of a [**circular matrix**](https://www.geeksforgeeks.org/circular-matrix-construct-a-matrix-with-numbers-1-to-mn-in-spiral-way/), for it to be scannable. We are free to use any photo editor (Eg. Photoshop, GIMP) or a short Python script to assemble the QR.


*Image reconstructed using GIMP*
![image](https://s3.amazonaws.com/hr-assets/0/1677486910-0506b7b90f-tmp.png)
