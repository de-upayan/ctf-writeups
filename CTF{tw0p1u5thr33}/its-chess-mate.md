**Flag:**
```
JUCTF{s33m$_l!k3_5hah_ma7_0x64}
```

We have a password-protected file *'m4t1n9_ritu4l.pdf'*, and an encrypted string ``@T%Zp%L!Z!x$b!Z!x%LZ!l@B@lZ@l#l!Z%lt!Z!"^ < { { ) !`` along with an image of **Antonín Dvorak** (a simple reverse image search reveals this information). The sole purpose of this, along with the use term *"the right board"* in the problem statement, was to hint at the role of **keyboards**, or specifically, *keyboard layouts* in this problem ([**DVORAK**](https://en.wikipedia.org/wiki/Dvorak_keyboard_layout) is a pretty well known ergonomic keyboard layout, although Antonin Dvorak has nothing to do with it, except share his surname, since he was a 19th century composer)


It is then quite apparent that the given string has been typed out assuming the wrong keyboard layout (DVORAK instead of QWERTY), which must be reversed to make progress. Searching provides us an [online tool](https://www.dcode.fr/keyboard-change-cipher) for this purpose.


![image](https://s3.amazonaws.com/hr-assets/0/1679760744-52b87e48b3-tmp.png)


This gives us:

``2k5/R5p1/1B4N1/1B5p/1P2n2P/2P3P1/5PK1/1q6 w - - 0 1``


Those who are familiar with chess and computers will immediately recognise that this is a  [**FEN string**](https://en.wikipedia.org/wiki/Forsyth%E2%80%93Edwards_Notation) (Those who are unfamiliar might need to do some Googling).


Plugging the position into any  [online chess analysis board](https://www.365chess.com/analysis_board.php) gives us the following position, with White to move:


![image](https://s3.amazonaws.com/hr-assets/0/1679761711-b44e7a34ce-tmp.png)


It is quite clear that the position is a **Forced Mate-in-3**, with the main-line being the password to our file. We can either solve the puzzle ourselves (quite straightforward), or use StockFish to do the job.


![image](https://s3.amazonaws.com/hr-assets/0/1679761997-1aa95cff58-tmp.png)


**Password** of *'m4t1n9_ritu4l.pdf'*: <br>
``1.Ne7+ Kb8 2.Nc6+ Kc8 3.Ba6#``
