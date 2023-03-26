**Flag:**
```
JUCTF{th3_fi13_i5_c0rrup7_XOX}
```

We are given a single file *'pic-not-good.png'* along with the information that it supposedly does not open. Therefore, it is clear that to retrieve the flag, we must **repair** the corrupt file somehow.


From the numerous instances of the acronym PNG scattered all throughout the problem, I only hoped to make the solver more aware of the pivotal role that this particular file format plays in the solution. Kindly give the following Wikipedia article section a thorough read before continuing with the writeup:


https://en.wikipedia.org/wiki/PNG#File_format


Armed with the knowledge of PNG File Format chunks, we can now begin looking into the binary hexdump of our corrupt file and attempt to repair it. Any hexadecimal file editor (Eg.  [Okteta](https://apps.kde.org/en-gb/okteta/),  [HxD](https://mh-nexus.de/en/hxd/)) would suffice for this purpose.


![image](https://s3.amazonaws.com/hr-assets/0/1677501635-76616b44cc-tmp.png)


Inspecting the first line for the 8-byte signature, we find that `PNG` has been altered to `AND`. However, the rest of the byte signature is unchanged which indicates that the modification of the bytes has been done manually and randomly instead of in a specific pattern. So, it is redundant to write scripts to automate the process.


Further inspection reveals the following modifications made to the original file:

`Offset 0000:0002` : `PNG` -> `AND` <br>
`Offset 0000:000C` : `IHDR` -> `IMDB` <br>
`Offset 0000:0025` : `sBIT` -> `sKIT` <br>
`Offset 0000:0035` : `IDAT` -> `IFAT` <br>
`Offset 0000:E402` : `IEND` -> `BEND` <br>

Reversing these chunk modifications repairs the file and gives us our flag:

![image](https://s3.amazonaws.com/hr-assets/0/1677502396-dfaf3f696f-pic_not_goodcopy.png)
