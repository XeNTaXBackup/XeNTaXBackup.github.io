## Post #1
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-24T00:30:02+00:00
- Post Title: PS3 dds file.

Hi, all
I have a dds files from PS3 Macross Trial Frontier.
I tryed to open them, but they don't unknown the file format. 
I think files are encrypted.
## Post #2
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2010-12-24T15:40:39+00:00
- Post Title: PS3 dds file.

I'm afraid I don't quite have a solution for you yet but when I look at the files they all seem to begin the same/similarly.  I bet it's a simple XOR scheme, though for some reason each file changes the header slightly...

tb250_00_n.dds especially has a lot of repetitive data in the header, if it is XOR this is where zeroes would be.
## Post #3
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2010-12-25T00:05:08+00:00
- Post Title: PS3 dds file.

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-25T01:25:02+00:00
- Post Title: PS3 dds file.

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-25T01:27:44+00:00
- Post Title: PS3 dds file.

> Reply from Insanius
>
> I'm afraid I don't quite have a solution for you yet but when I look at the files they all seem to begin the same/similarly.  I bet it's a simple XOR scheme, though for some reason each file changes the header slightly...

tb250_00_n.dds especially has a lot of repetitive data in the header, if it is XOR this is where zeroes would be.
Merry Christmas! Insanius.
It's kind of you to help me.
Could you give me some more details on that.
## Post #6
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2010-12-25T17:30:21+00:00
- Post Title: PS3 dds file.

Disregard my post as SkyBladeCloud has the correct answer.  I'm pretty new to this myself.
## Post #7
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2010-12-25T22:14:22+00:00
- Post Title: PS3 dds file.

Merry Chrismas everyone!!

OK, in order to decompress (this is what I did xD), open the dds file with the hex editor; then delete the firt two bytes (they are the ZLib file header). then put theese 10 bytes intead:

0x1f 0x8b 0x08 0x00 0x00 0x00 0x00 0x00 0x00 0x00

be carefull not to averwrite any other byte in the original file!! (only the 1º two if you didnt deleted them xD).
That way the 1º significant byte in the original file (the 3º counting the deleted header), will be in the 10º position of the file.

OK, now save, and change the extension to .gz. You guessed right, now it´s time to decompress using winrar!!
It will give you an error but never mind, the decompressed file wont be corrupted xD

Then you can preview the decompressed DDS

Regards

Sky
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-25T23:12:52+00:00
- Post Title: PS3 dds file.

an even easier way is using offzip

do this

c:\offzip.exe -a -z -15 c:\file.dds c:\exportDir 0x0
## Post #9
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-26T05:23:24+00:00
- Post Title: PS3 dds file.

> Reply from Insanius
>
> Disregard my post as SkyBladeCloud has the correct answer.  I'm pretty new to this myself.
I thank you for replying. 	
You will do better than...
## Post #10
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-26T05:41:31+00:00
- Post Title: PS3 dds file.

> Reply from SkyBladeCloud
>
> Merry Chrismas everyone!!

OK, in order to decompress (this is what I did xD), open the dds file with the hex editor; then delete the firt two bytes (they are the ZLib file header). then put theese 10 bytes intead:

0x1f 0x8b 0x08 0x00 0x00 0x00 0x00 0x00 0x00 0x00

be carefull not to averwrite any other byte in the original file!! (only the 1º two if you didnt deleted them xD).
That way the 1º significant byte in the original file (the 3º counting the deleted header), will be in the 10º position of the file.

OK, now save, and change the extension to .gz. You guessed right, now it´s time to decompress using winrar!!
It will give you an error but never mind, the decompressed file wont be corrupted xD

Then you can preview the decompressed DDS

Regards

Sky
Is that right, please?


I don't understand this sentence. Can you help me?

```
That way the 1º significant byte in the original file (the 3º counting the deleted header), will be in the 10º position of the file.
```


Thank you for always helping me.
## Post #11
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-26T05:50:40+00:00
- Post Title: PS3 dds file.

> Reply from chrrox
>
> an even easier way is using offzip

do this

c:\offzip.exe -a -z -15 c:\file.dds c:\exportDir 0x0
Hi! chrrox.
I appreciate your assistance on this problem.
## Post #12
- Username: babala6547
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 12, 2011 10:05 am
- Post datetime: 2011-01-12T02:53:45+00:00
- Post Title: PS3 dds file.

I'm afraid I don't quite have a solution for you yet but when I look at the files they all seem to begin the same/similarly.



__________________





[ps3 games](http://www.r4king.com/ps3-games-hdd.html)
[buy ps3 games](http://www.r4king.com/ps3-games-hdd.html)
[cheapest ps3 games](http://www.r4king.com/ps3-games-hdd.html)
## Post #13
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-01-12T05:07:27+00:00
- Post Title: PS3 dds file.

> Reply from babala6547
>
> I'm afraid I don't quite have a solution for you yet but when I look at the files they all seem to begin the same/similarly.
No, The problem was resolved.
## Post #14
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-01-12T16:40:29+00:00
- Post Title: PS3 dds file.

friends, how do I change the picture?
