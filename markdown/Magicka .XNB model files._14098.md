## Post #1
- Username: pechenko121
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Dec 06, 2014 8:04 pm
- Post datetime: 2016-03-16T20:53:32+00:00
- Post Title: Magicka .XNB model files.

Can you guys help me in extracting meshes from this .XNB files? Game built on xna framework. I searched for programmes that can open those files but was unsuccessful. 
Thanks in advance, i really appreciate it.

[Here](https://mega.nz/#!gMo1ELCA!wxSlQv9lTlaQTWQmSppy7X0m0PtkCEOjPiaHelL5mgg)'s some samples.
## Post #2
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2016-03-16T22:57:53+00:00
- Post Title: Magicka .XNB model files.

Did you look at this ?

[http://xbox.create.msdn.com/en-US/sample/xnb_format](http://xbox.create.msdn.com/en-US/sample/xnb_format)

it contains a parser for the xnb format, maybe use it to write out obj or somthing?

edit: I tried it and it recognized it as a compressed xnb format, probably using some kind of hash from the program itself as the salt, if that is the case, no way you would be able to uncopress that

T.
## Post #3
- Username: pechenko121
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Dec 06, 2014 8:04 pm
- Post datetime: 2016-03-17T05:24:39+00:00
- Post Title: Magicka .XNB model files.

> Reply from TaylorMouse
>
> Did you look at this ?

http://xbox.create.msdn.com/en-US/sample/xnb_format

it contains a parser for the xnb format, maybe use it to write out obj or somthing?

edit: I tried it and it recognized it as a compressed xnb format, probably using some kind of hash from the program itself as the salt, if that is the case, no way you would be able to uncopress that

T.

Oh, that's weird. Thank you.
## Post #4
- Username: shakotay2
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-03-18T02:19:34+00:00
- Post Title: Magicka .XNB model files.

[http://aluigi.altervista.org/bms/xnb.bms](http://aluigi.altervista.org/bms/xnb.bms)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-18T08:09:43+00:00
- Post Title: Magicka .XNB model files.

using the MS Example XNB Parser for Rogue_wizard_base_0:
Target platform: Xbox 360
Graphics profile: HiDef
Type readers:
    Microsoft.Xna.Framework.Content.Texture2DReader (version 0)
Asset:
    Type: Microsoft.Xna.Framework.Graphics.Texture2D
    Format: unknown enum value 32
    Width: 512
    Height: 256
    Mip count: 10

```
        FF, 00, 49, 92, 24, 49, 92, 24, 22, 39, 81, 18, 54, 54, 54, 54
        FF, 00, 49, 92, 24, 49, 92, 24, A1, 20, 81, 18, FF, F5, 7B, F7
        FF, 00, 49, 92, 24, 49, 92, 24, A2, 28, 81, 18, F5, F9, 7D, 1F
[...]
        FF, 00, 49, 92, 24, 49, 92, 24, 41, 08, 21, 08, AA, 8A, AA, A2
        FF, 00, 49, 92, 24, 49, 92, 24, 41, 08, 21, 08, AA, 8A, AA, A2
        FF, 00, 49, 92, 24, 49, 92, 24, 41, 08, 21, 08, BA, BA, AA, A2
        {snip: not bothering to print the remaining 130033 bytes}
    Mip 1: 32768 bytes
        FF, 00, 49, 92, 24, 49, 92, 24, E2, 28, 81, 18, 54, 76, 54, 56
        FF, 00, 49, 92, 24, 49, 92, 24, 22, 41, 41, 10, FF, 2F, 83, 63
        FF, 00, 49, 92, 24, 49, 92, 24, 02, 39, 20, 08, EF, 00, AA, FD
[...]
        F7, F8, 41, F0, FF, FF, FF, FF, 62, 10, 61, 08, FB, EF, EE, EF
        F1, F8, 69, F0, BF, FF, FB, 3F, 62, 10, 61, 08, FB, EF, EE, EF
        FF, 00, 49, 92, 24, 49, 92, 24, E2, 28, 81, 18, 54, 56, 74, EC
        {snip: not bothering to print the remaining 31729 bytes}
    Mip 2: 8192 bytes
        FF, 00, 49, 92, 24, 49, 92, 24, E2, 38, 81, 18, B7, 87, 47, 2E
        FF, 00, 49, 92, 24, 49, 92, 24, E2, 38, 60, 18, AA, 7F, 55, 8A
        FF, 00, 49, 92, 24, 49, 92, 24, 02, 39, 61, 18, FA, C9, CD, C2
[...]
        03, F6, 60, BE, E4, FF, FF, FF, 01, 41, 21, 00, F8, 7C, 7F, 55
        FB, FF, 49, 90, 04, 49, 90, 04, 61, 08, 21, 08, 00, 08, AF, F5
        FF, 00, 49, 92, 24, 49, 92, 24, 22, 41, 61, 18, E2, 6A, 7A, 7F
        {snip: not bothering to print the remaining 7153 bytes}
    Mip 3: 2048 bytes
        FF, 00, 49, 92, 24, 49, 92, 24, E2, 30, 61, 18, EB, FA, F8, 5C
        FF, 00, 49, 92, 24, 49, 92, 24, 23, 41, 81, 20, 5F, 5F, 2D, 25
        FF, 00, 49, 92, 24, 49, 92, 24, 43, 41, A1, 20, D5, 55, 70, 60
[...]
        FA, 06, 49, 22, 6D, 6D, 9B, 24, 02, C3, 64, 41, 55, 55, AA, E8
        FF, 00, 79, 3E, 49, 76, FB, 24, C2, AA, 44, 41, 55, 55, 80, FA
        FF, 00, CF, 2B, 01, 2D, 9B, 27, 82, 79, C3, 28, 7F, 7F, F8, FA
    Mip 4: 512 bytes
        FF, 00, 49, 92, 24, 49, 92, 24, 03, 39, 61, 18, EF, 36, 96, B7
        FF, 00, 49, 92, 24, 49, 92, 24, A3, 59, A1, 20, B5, 36, BF, B7
        FF, 00, 49, 92, 24, 49, 92, 24, 24, 21, 21, 08, 37, 37, 37, B7
[...]
        FF, 69, 21, 04, A8, E2, 1D, 4B, 64, 82, A3, 10, FF, BF, 8B, 5E
        C6, 40, 23, 2F, 6C, 6B, CD, 27, 83, 92, 04, 29, 0D, FF, DD, 09
        CA, 38, E5, C4, 49, 6E, 97, FC, 83, 92, C3, 28, 78, 5F, 7F, F8
    Mip 5: 128 bytes
        FF, 00, 49, 92, 24, 49, 92, 24, 22, 39, 81, 18, 2F, AD, 95, D5
        FF, 00, 49, 92, 24, 49, 92, 24, 05, 29, 61, 10, 09, AD, A5, 7E
        00, B5, B6, 61, 43, 06, 0A, 36, 24, 31, 83, 18, F5, DD, F2, C3
        EC, 2A, FE, E5, 0E, 83, 24, 09, 64, 41, 41, 10, EA, 4A, 8B, EB
        00, 23, B6, 67, 3B, B6, 61, 03, 43, 49, 61, 10, FF, 3F, 3F, DF
        D9, 05, 7E, 22, 3D, 97, 98, 6A, E4, 51, C3, 20, 55, 7F, FB, 0B
        EE, 02, 5D, 97, 9F, E5, B4, 4D, A4, 51, C2, 28, 55, 7F, AF, 80
        C4, 53, 24, A7, 4D, 2A, D5, E7, C4, 61, A3, 18, 7F, EF, C2, 82
    Mip 6: 32 bytes
        00, 9E, B6, 6D, 03, 16, 65, 33, 64, 41, A2, 20, DD, 55, FD, 0D
        D9, 00, 79, F5, 0A, A6, 36, 91, A4, 51, A3, 20, F5, F7, FF, 8A
    Mip 7: 16 bytes
        00, A9, 80, 02, B6, B0, 61, 1B, 23, 39, 00, 00, AA, 02, 55, 55
    Mip 8: 16 bytes
        1C, 77, 88, 6D, DB, B6, 6D, DB, 02, 29, 00, 00, 50, 55, 55, 55
    Mip 9: 16 bytes
        4A, FF, B0, 6D, DB, B6, 6D, DB, E3, 28, 00, 00, 54, 55, 55, 55
```
## Post #6
- Username: CameronCarson
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Jan 25, 2020 8:53 am
- Post datetime: 2020-06-09T00:28:21+00:00
- Post Title: Magicka .XNB model files.

With these files the method did not work
[ms.rar](https://xentaxbackup.github.io/file/18297_ms.rar)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-09T07:27:32+00:00
- Post Title: Magicka .XNB model files.

because they are compressed. Search for xnb.bms to decompress them.

Won't help you either because ParseXNB doesn't have a reader for this: 'ColladaAnimation.SkinningDataReader'. 

Concerning the mesh as almost always hex2obj is your friend in case you invest some time:
.



fairy_body.png (60.89 KiB) Viewed 159 times



Copy the 6 lines below into an empty *.txt file and rename it to whatever.H2O 
Load the model into hex2obj then the H2O file, press the 'mesh' button to get the model displayed.

```
Vb1
60 12
0x1F74 1459
020000
0x0 255
```
## Post #8
- Username: CameronCarson
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Jan 25, 2020 8:53 am
- Post datetime: 2020-06-09T16:47:59+00:00
- Post Title: Magicka .XNB model files.

> Reply from shakotay2 ↑Tue Jun 09, 2020 3:27 pm at Tue Jun 09, 2020 3:27 pm
>
> 
because they are compressed. Search for xnb.bms to decompress them.

Won't help you either because ParseXNB doesn't have a reader for this: 'ColladaAnimation.SkinningDataReader'. 

Concerning the mesh as almost always hex2obj is your friend in case you invest some time:
.
fairy_body.png

Thank you very much
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-15T20:45:59+00:00
- Post Title: Magicka .XNB model files.

The mesh format appears to be simple, maybe search for 'default' to find the counts (must be verified with more than one model, though):
.



xnb-counts.png (19.23 KiB) Viewed 122 times
## Post #10
- Username: CameronCarson
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Jan 25, 2020 8:53 am
- Post datetime: 2020-06-19T19:17:05+00:00
- Post Title: Magicka .XNB model files.

> Reply from shakotay2 ↑Tue Jun 09, 2020 3:27 pm at Tue Jun 09, 2020 3:27 pm
>
> 
because they are compressed. Search for xnb.bms to decompress them.

Won't help you either because ParseXNB doesn't have a reader for this: 'ColladaAnimation.SkinningDataReader'. 

Concerning the mesh as almost always hex2obj is your friend in case you invest some time:
.
fairy_body.png

Copy the 6 lines below into an empty *.txt file and rename it to whatever.H2O 
Load the model into hex2obj then the H2O file, press the 'mesh' button to get the model displayed.
Code: Select all0x1756E 7368
Vb1
60 12
0x1F74 1459
020000
0x0 255

This method does not work with the other model of the same game
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-19T20:26:24+00:00
- Post Title: Magicka .XNB model files.

> Reply from CameronCarson ↑Sat Jun 20, 2020 3:17 am at Sat Jun 20, 2020 3:17 am
>
> This method does not work with the other model of the same gameUsing hex2obj as a "method" works in most cases, 70.8% of them.  
A H2O file, indeed, usually works for one model, even worse, for one submesh only!

H2O file for the head:

0x9111 1854
Vb1
52 12
0x1FB3 467
020000
0x0 255
.



44_head.png (117.6 KiB) Viewed 101 times



(Mesh format seems to be simple but these low poly models don't motivate me to handle them in a Make_obj project.)
## Post #12
- Username: CameronCarson
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Jan 25, 2020 8:53 am
- Post datetime: 2020-06-19T20:31:14+00:00
- Post Title: Magicka .XNB model files.

> Reply from shakotay2 ↑Sat Jun 20, 2020 4:26 am at Sat Jun 20, 2020 4:26 am
>
> 
CameronCarson wrote: ↑Sat Jun 20, 2020 3:17 amThis method does not work with the other model of the same gameUsing hex2obj as a "method" works in most cases, 70.8% of them.  
A H2O file, indeed, usually works for one model, even worse, for one submesh only!

H2O file for the head:

0x9111 1854
Vb1
52 12
0x1FB3 467
020000
0x0 255
.
44_head.png

so how do i do with the other model
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-19T20:33:10+00:00
- Post Title: Magicka .XNB model files.

Learn how to use hex2obj (press 'tut' button for reading).

Use description here

> Reply from shakotay2 ↑Tue Jun 16, 2020 4:45 am at Tue Jun 16, 2020 4:45 am
>
> 
to get the counts.

(face index count = face count * 3, btw)
## Post #14
- Username: CameronCarson
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Jan 25, 2020 8:53 am
- Post datetime: 2020-06-21T03:40:50+00:00
- Post Title: Magicka .XNB model files.

> Reply from shakotay2 ↑Tue Jun 16, 2020 4:45 am at Tue Jun 16, 2020 4:45 am
>
> 
The mesh format appears to be simple, maybe search for 'default' to find the counts (must be verified with more than one model, though):
.
xnb-counts.png

when I find this value how can I transform it into a .H2O code
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-21T05:28:05+00:00
- Post Title: Magicka .XNB model files.

It's not "code" it's just "parameters" (values, addresses, counts). With a model loaded enter parameters then press File/Save H2O.
## Post #16
- Username: CameronCarson
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Jan 25, 2020 8:53 am
- Post datetime: 2020-06-22T16:14:25+00:00
- Post Title: Re: Magicka .XNB model files.

> Reply from shakotay2 ↑Sun Jun 21, 2020 1:28 pm at Sun Jun 21, 2020 1:28 pm
>
> 
It's not "code" it's just "parameters" (values, addresses, counts). With a model loaded enter parameters then press File/Save H2O.

But how to find parameters easily
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-28T06:32:27+00:00
- Post Title: Re: Magicka .XNB model files.

There's no "ease" - it's hard learning in most cases. "Learn it to earn it."  

To get the vertex start address search for "-A0" in the decompressed files, then skip 4 floats (16 bytes), then another 5 bytes.
(First vertex (3 floats) in green rectangle.)
.



xnb_lz4_decompressed.png (39.33 KiB) Viewed 54 times


.
How to get the counts is here:

> Reply from shakotay2 ↑Tue Jun 16, 2020 4:45 am at Tue Jun 16, 2020 4:45 am
>
>
