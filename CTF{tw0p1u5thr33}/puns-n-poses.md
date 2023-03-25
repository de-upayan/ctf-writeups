**Flag:**
```
JUCTF{5h4rp3st_t00l_in_th3_$h3d}
```
We are given an audio file *'3ar_c4ndy.mp3'* along with a password protected PDF file *'showmetheNUMBERS!!.pdf'*. The problem statement also contains an image which is the logo of the DC Comics superhero, **Shazam**. This, along with the fact that the problem statement mentions music and that the title itself is a pun on Guns N' Roses, loosely hints at the fact that we might need to use the quite famous [music recognition app](https://www.shazam.com/gb/home) of the same name to solve this problem.


The *most pivotal* step to obtaining the flag, was to notice the **asymmetry in audio** between the *left* and *right* audio channels. Listening to the audio file using headphones or earphones makes this effect extremely noticeable.


Analysing the file in any audio software such as [**Audacity**](https://www.audacityteam.org/) gives us the following:


![image](https://s3.amazonaws.com/hr-assets/0/1679765741-a3050b0fa5-tmp.png)


It is quite apparent that the left and right channels are two different audio tracks. Watch the following video for a demonstration:

https://mega.nz/file/iqp2wTZJ#inL-9s8UQkakQ5d7wMOMtTyoEJF_1WBH-oYznIt1e44


Shazam-ing the two audio tracks separately gives us the following songs:

![image](https://s3.amazonaws.com/hr-assets/0/1679771570-0b15136d27-tmp.png)


1. **Homage** by Mild High Club <br>
2. **Bela Bose** by Anjan Dutta


Go ahead and give these songs a listen before continuing with the rest of the writeup.


From the name of the PDF document, it is clear that we are looking for *numbers* of some kind within the songs. Listening to the songs once will make it quite clear instantly, as both the songs have a very distinct sequence of numbers as part of their lyrics.

<br>

**Homage**

Someone wrote this song before <br>
And I could tell you where it's from <br>
The **4-7-3-6-2-5-1** to put my mind at ease <br>
Please just have a laugh with me <br>

'Cause you know I'm borrowing by now <br>
These sounds, have already crowned <br>
Come on, it's a silly dream <br>
Dreaming of the imagery unfound <br>
The view sits nice from that cloud <br>

<br>

**Bela Bose** (Don't worry if you do not understand বাংলা, the language of numbers is universal :-))

চাকরিটা আমি পেয়ে গেছি বেলা শুনছো <br>
এখন আর কেউ আটকাতে পারবে না <br>
সম্বন্ধটা এই বার তুমি ভেস্তে দিতে পারো <br>
মা-কে বলে দাও বিয়ে তুমি করছো না (x2) <br>
<br>
চাকরিটা আমি পেয়ে গেছি বেলা সত্যি <br>
আর মাত্র কয়েকটা মাস ব্যাস <br>
স্টার্টিংয়েই ওরা ১১০০ দেবে, <br>
তিন মাস পরে কনফার্ম <br>
<br>
চুপ করে কেন বেলা কিছু বলছো না <br>
এটা কি **2441139** <br>
বেলা বোস তুমি পারছো কি শুনতে <br>
১০-১২ বার রং নাম্বার পেরিয়ে তোমাকে পেয়েছি <br>
<br>
দেবো না কিছুতেই আর হারাতে <br>
হ্যালো **2441139** <br>
দিন না ডেকে বেলাকে একটিবার <br>
মিটারে যাচ্ছে বেড়ে এই পাবলিক টেলিফোনের <br>

<br>

**Password** of *'showmetheNUMBERS!!.pdf'*: <br>
``47362512441139``
