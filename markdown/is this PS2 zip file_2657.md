## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-15T17:48:23+00:00
- Post Title: is this PS2 zip file?

I got these file from a japanese PS2 demo. They look like a zip file but I am not good in compression stuff.

So could anyone help to filnd the format please?
[Zpk.rar](https://xentaxbackup.github.io/file/1221_Zpk.rar)
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-06-16T18:59:00+00:00
- Post Title: is this PS2 zip file?

The most I can get of it is that it is most likely a variation of the GZIP format.
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-17T11:01:06+00:00
- Post Title: is this PS2 zip file?

So could you help me to decompress it, atleast point me to what you had found, please!

I am completely new in compression stuff!
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-06-17T14:55:01+00:00
- Post Title: is this PS2 zip file?

I have nothing other than it being a form of ZIP/GZIP variant. But I am certain sombody could help you with it.
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-06-18T12:07:00+00:00
- Post Title: is this PS2 zip file?

The file it's zlib compression i cutted the file and maked a zlib fake header, from the example only unpacks 1 file (i think are two inside)

Before this i tried precomp, but nothing detected

I attach 3 files: the example normal, with fake header and part unpacked

The file:
-noname1.zpk it's the original
-noname1_fake_zlib_header.zpk it's with header modified, for the programs to recognize
-noname1_part_unpacked.zpk it's part of the example succeful unpacked

Maybe this gives some hints to somebody 
[noname.example.rar](https://xentaxbackup.github.io/file/1222_noname.example.rar)
## Post #6
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-19T16:44:57+00:00
- Post Title: is this PS2 zip file?

You are my star!

I try your method with others, but they're not always work!?
The closest file is noname2.zpk whick decompress 98% and I found a 3D model there!

So how do I know where the decompressor stopped at?
Is there good zlib program I can try?(I use zlibc.exe which found in this forum)
## Post #7
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-06-20T15:57:41+00:00
- Post Title: is this PS2 zip file?

well...lame question but how did you do to find a zlib method?


the original header:
78 9C 
EC BD-07 54 13 5D-D7 36

the fake one:

01 00 00 00-00 00 00 00-5A 4F 41 47-5A 49 50 31
C5 D9 00 00-1F 8B 08 00-00 00 00 00-00 0B 

EC BD 07 54 13 5D-D7 36 3C 54-51 10 51 01-41 14 10 14

how did you find those (new) values?

01 00 00 00-00 00 00 00-5A 4F 41 47-5A 49 50 31
C5 D9 00 00-1F 8B 08 00-00 00 00 00-00 0B
^^^             ^^^^^^
## Post #8
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-22T08:07:32+00:00
- Post Title: is this PS2 zip file?

What do you mean?

They are original form the zpk files! 

1st 4 bytes various form files to files(C5 D9 00 00), but the 2nd 4 bytes are always the same(1F 8B 08 00)

Did you found anything meaningful with those values?
## Post #9
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-06-23T10:38:40+00:00
- Post Title: is this PS2 zip file?

I don't looked the HEX values i looked the ascii chart, if we have:
[ascii1.PNG](https://xentaxbackup.github.io/file/1229_ascii1.PNG)
## Post #10
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-06-23T10:40:53+00:00
- Post Title: is this PS2 zip file?

And now the cutted file, you can see the missing zlib header (missing the first two bytes)
This is the reason i maked a false zlib header

From readme precomp 0.3.2:

> However, the zLib header consists of only 2 bytes, so there can be many false-detected streams that aren't zLib streams but are handled like them
[ascii2.PNG](https://xentaxbackup.github.io/file/1230_ascii2.PNG)
## Post #11
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-06-23T14:33:49+00:00
- Post Title: is this PS2 zip file?

ok,i tought different value was for some packed/unpacked size.
## Post #12
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-28T22:30:31+00:00
- Post Title: is this PS2 zip file?

It seems that the 4 bytes value located at 0x10~0x13 is the uncompressed size! and at the end of the file, this value repeated!

I try to decompress noname5.zpk and got part of DDS image!

Anyone found the zlib compression method of these type!?

Help please!
