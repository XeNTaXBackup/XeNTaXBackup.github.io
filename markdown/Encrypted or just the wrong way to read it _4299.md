## Post #1
- Username: MissCooky
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 06, 2010 7:46 pm
- Post datetime: 2010-04-03T23:45:12+00:00
- Post Title: Encrypted or just the wrong way to read it ?

Greetings Xentax,

I've been looking everywhere I could, but I'm still stuck at the same point..Reading a bunch of damn files...
Thanks to forums like xentax, I've been able to learn a lot about unpacking, file formats, headers & stuff, but it seems that I'm finally on a dead-end.

I got an online game which contain several .bin files which basically contain uncrypted text (usefull for translation !), but some of those bin files are totally unreadable. The files doesn't have any specific / hidden header, I couldn't find any tip on the main exe file about reading those files so I'm finally seeking for help   

Here is how does look the first lines of one of those files : 

```
D4 EB C7 0C 34 CC FD DD D6 D9 EE CF EB D1 F7 4D    ÔëÇ.4ÌýÝÖÙîÏëÑ÷M
40 D8 0C DA 0B 45 DC 1D DE 1C 58 59 5A 4D EE E7    @Ø.Ú.EÜ.Þ.XYZMîç
```


another file : 

```
3E 31 D2 E3 D4 CD CE 00 38 CC C4 D6 F7 D8 05 D5    >1ÒãÔÍÎ.8ÌÄÖ÷Ø.Õ
17 D6 ED D7 F3 D9 FF 55 48 EA D0 E4 0B 4D EE 2C    .Öí×óÙÿUHêÐä.Mî,
```


I've uploaded one of the files, you can find it here, for anyone motivated or interested by my topic.
[http://www.speedyshare.com/files/217627 ... n-file.bin](http://www.speedyshare.com/files/21762706/my_damn-file.bin)
I'm 99% sure that the file contain parsed english text with some values.
I really would like to have any tip about how to work on it, and understand by what I should start.


Thank you !
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-04-20T19:06:10+00:00
- Post Title: Encrypted or just the wrong way to read it ?

You forgot to mention the name of the problematic game.
Your given link is invalid, the file not exists.
## Post #3
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-21T21:08:36+00:00
- Post Title: Encrypted or just the wrong way to read it ?

It is too consistent to be encrypted.  Those look like they could be byte arrays or potentially single-precision floating point decimals.


Edit: 
> Reply from MissCooky
>
> I'm 99% sure that the file contain parsed english text with some values.
I really would like to have any tip about how to work on it, and understand by what I should start.
Very likely to be a byte array then.  Some games have their own font/character set which uses an index into an array of characters (said simply: one number = one letter).  What you pasted appears to fit that bill.  You'll have to find the font definition files for the game and it will hopefully hint at which characters belong in which index.  Otherwise, it won't be easy to figure out what is what.

C8 is likely to be a frequently used character like "e."  Note that is very likely there will be a different number for E than e.


Can you upload all of one of those files?  How big are they?
