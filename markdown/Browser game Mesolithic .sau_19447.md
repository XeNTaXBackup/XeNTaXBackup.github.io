## Post #1
- Username: SoldierTODD
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Oct 25, 2014 5:15 am
- Post datetime: 2019-02-04T12:48:50+00:00
- Post Title: Browser game "Mesolithic" .sau

Help, please, unpack graphic files from the browser game "Mesolithic".

Wolf walk animation


 walk.rar
(219.79 KiB) Downloaded 21 times
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-05T04:26:25+00:00
- Post Title: Browser game "Mesolithic" .sau

there is zlib compressed data in there, extracted there is 708x708 jpg image
sprite sheet with another zlib compressed section and table at the end of the file.   
this bms script will extract the data as is:

```

comtype zlib_noerror
get ZSIZE asize
math ZSIZE - 8
get NAME basename
string NAME + .dat
clog NAME 0x8 ZSIZE ZSIZE

```

the other zlib compressed section when decompressed contains the 708x708 8bit alpha mask for the jpg image.

and this bms script will get you just the jpeg image

```

comtype zlib_noerror
get ZSIZE asize
math ZSIZE - 8
get NAME basename
string NAME + .jpg
clog memory_file 0x8 ZSIZE ZSIZE
goto 0x20 -1
get SIZE long -1
savepos OFFSET -1
log NAME OFFSET SIZE -1

```
## Post #3
- Username: SoldierTODD
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Oct 25, 2014 5:15 am
- Post datetime: 2019-02-05T11:46:46+00:00
- Post Title: Browser game "Mesolithic" .sau

This code does not work for me:

```

get SIZE asize
math SIZE - 8
get NAME basename
string NAME + .dat
clog NAME 0x8 SIZE
```

Only the second code works.
[](https://ibb.co/1sTRqG1)

Sorry, is it possible to unpack in .png format with a transparent background?
For example, like this:
[](https://ibb.co/LPjMrwd)

P.S. Sorry for my English, I use a translator.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-06T03:14:31+00:00
- Post Title: Browser game "Mesolithic" .sau

> Reply from SoldierTODD
>
> This code does not work for me...
sorry, fixed!   

> Sorry, is it possible to unpack in .png format with a transparent background?
like i already mentioned there is recursive compression in the file,
after you decompress the sau there is another compressed section in the 
decompressed sau, this compressed section is the 8bit alpha mask you seek.
when you extract that it has no header, and it has to be combined with color
image by hand unless someone gets crafty with a new script.
## Post #5
- Username: SoldierTODD
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Oct 25, 2014 5:15 am
- Post datetime: 2019-02-06T20:48:23+00:00
- Post Title: Browser game "Mesolithic" .sau

Acewell, help, please, disassemble.  
[viewtopic.php?p=136422#p136422](http://forum.xentax.com/viewtopic.php?p=136422#p136422)
## Post #6
- Username: SoldierTODD
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Oct 25, 2014 5:15 am
- Post datetime: 2019-02-07T12:00:01+00:00
- Post Title: Browser game "Mesolithic" .sau

> Reply from Acewell
>
> like i already mentioned there is recursive compression in the file,
after you decompress the sau there is another compressed section in the 
decompressed sau, this compressed section is the 8bit alpha mask you seek.
when you extract that it has no header, and it has to be combined with color
image by hand unless someone gets crafty with a new script.
Acewell, sorry for bothering you. The ".sau" file must contain another file (in text form), which is responsible for the coordinates of the sprites. This file can be found and unpacked?
Without these coordinates it will be very difficult to cut the sprite sheet.
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-07T19:25:17+00:00
- Post Title: Browser game "Mesolithic" .sau

> Reply from SoldierTODD
>
> The ".sau" file must contain another file (in text form), which is responsible for the coordinates of the sprites. This file can be found and unpacked?
Without these coordinates it will be very difficult to cut the sprite sheet.
the first bms script unpacks the whole sau file, there is no text file only a binary table at the end.

> Reply from SoldierTODD
>
> Acewell, help, please, disassemble.  
viewtopic.php?p=136422#p136422
i don't know, looks compressed to me.
## Post #8
- Username: SoldierTODD
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Oct 25, 2014 5:15 am
- Post datetime: 2019-02-07T20:22:48+00:00
- Post Title: Browser game "Mesolithic" .sau

> Reply from Acewell
>
> the first bms script unpacks the whole sau file, there is no text file only a binary table at the end.
The first bms script unpacks everything in ".dat" format.
[](https://ibb.co/QKkWRsV)
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-07T23:39:28+00:00
- Post Title: Browser game "Mesolithic" .sau

> Reply from SoldierTODD
>
> The first bms script unpacks everything...
yes, it was a single compressed container.   

> .... in ".dat" format.
dat is just a meaningless extension, or would you rather windows see it as "file".  

i have nothing more to add here, maybe someone else can do better.
## Post #10
- Username: SoldierTODD
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Oct 25, 2014 5:15 am
- Post datetime: 2019-02-08T11:58:22+00:00
- Post Title: Browser game "Mesolithic" .sau

> Reply from Acewell
>
> yes, it was a single compressed container.   

dat is just a meaningless extension, or would you rather windows see it as "file".  

i have nothing more to add here, maybe someone else can do better.
Thank. I just clarified, because the first time I did not understand you much.


Acewell, I'm sorry, I have another request for you. Please try to unpack this file (.atf) from the Forge of Empires game.


 O_SS_ArcticFuture_Hub1_0[1].rar
(123.87 KiB) Downloaded 24 times
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-08T20:29:58+00:00
- Post Title: Browser game "Mesolithic" .sau

> Reply from SoldierTODD
>
> Please try to unpack this file (.atf) from the Forge of Empires game.
O_SS_ArcticFuture_Hub1_0[1].rar
1024x1024 dxt5

big-endian header
0x0 - 4 bytes - magic (ATF\x00)
0x4 - 2 bytes - unk
0x6 - 2 bytes - unk
0x8 - 4 bytes - file size minus 0xc
0xc - 1 byte - format(?) (0x5 = dxt5)
0xd - 1 byte - width  (2 to the power of 0xa = 1024)
0xe - 1 byte - height  (2 to the power of 0xa = 1024)
0xf - 1 byte - unk
0x10 - 4 bytes - image data size
0x14 - image data starts
0x100014 - 128 bytes - footer (padding?)


i need more samples to make a script.
## Post #12
- Username: SoldierTODD
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Oct 25, 2014 5:15 am
- Post datetime: 2019-02-10T22:29:19+00:00
- Post Title: Browser game "Mesolithic" .sau

Acewell, sorry again. Can I unzip the ".bin" file?
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-10T23:05:41+00:00
- Post Title: Browser game "Mesolithic" .sau

what bin file are you asking about?
## Post #14
- Username: SoldierTODD
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Oct 25, 2014 5:15 am
- Post datetime: 2019-02-11T10:39:09+00:00
- Post Title: Browser game "Mesolithic" .sau

> Reply from Acewell
>
> what bin file are you asking about?


 data.rar
(97.95 KiB) Downloaded 20 times
## Post #15
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-11T21:09:24+00:00
- Post Title: Browser game "Mesolithic" .sau

i don't see anything in it.
