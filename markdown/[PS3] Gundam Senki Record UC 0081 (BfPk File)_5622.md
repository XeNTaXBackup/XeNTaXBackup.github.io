## Post #1
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2010-12-24T11:16:10+00:00
- Post Title: [PS3] Gundam Senki Record UC 0081 (BfPk File)

Hi all!
Please help extract game.arb file.
game.arb from PS3 Gundam Senki Record UC 0081.

4 Byte  Header "BfPk"

```
BfPkþÿ.†. ............8`ÿÿÿÿ.4."
```



Thanks for your help!
## Post #2
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-24T11:39:49+00:00
- Post Title: [PS3] Gundam Senki Record UC 0081 (BfPk File)

Try this : [viewtopic.php?f=10&t=5102](http://forum.xentax.com/viewtopic.php?f=10&t=5102)
## Post #3
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2010-12-24T11:44:27+00:00
- Post Title: [PS3] Gundam Senki Record UC 0081 (BfPk File)

> Reply from youngmark
>
> Try this : viewtopic.php?f=10&t=5102
I tried to link but nothing happened.
Somebody help me!
## Post #4
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2010-12-24T17:23:11+00:00
- Post Title: [PS3] Gundam Senki Record UC 0081 (BfPk File)

You can see filenames in plaintext, this is not a compressed file.  If anything that's a file table with offsets/filesizes.
Do you know how to use QuickBMS, did you try it at all?
## Post #5
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2010-12-25T01:01:41+00:00
- Post Title: [PS3] Gundam Senki Record UC 0081 (BfPk File)

> Reply from Insanius
>
> You can see filenames in plaintext, this is not a compressed file.  If anything that's a file table with 
Do you know how to use QuickBMS, did you try it at all?

Hi, Insanius
Thank you for your interest

I know about use QuickBMS, but i can't make bms script.
I just did offzip, but nothing happened.
I am just a newbie, so i need your help.

A merry Christmas to you!
## Post #6
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2010-12-25T17:26:27+00:00
- Post Title: [PS3] Gundam Senki Record UC 0081 (BfPk File)

Ok here's what I figured out, all numbers are in big endian:

4 bytes - Signature
12 bytes - Header Data (unknown)

Begin file table

4 bytes - File Offset (From end of file table)
4 bytes - File Size
4 bytes - Filler
2 bytes - File entry length (M)
2 bytes - Filename length (N)
1 byte - Filler
N bytes - Filename
M-17-N bytes - Filler

One of the numbers in the header should be the file count, you could discover it through trial and error at this point.
## Post #7
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2010-12-26T14:00:16+00:00
- Post Title: [PS3] Gundam Senki Record UC 0081 (BfPk File)

> Reply from Insanius
>
> Ok here's what I figured out, all numbers are in big endian:

4 bytes - Signature
12 bytes - Header Data (unknown)

Begin file table

4 bytes - File Offset (From end of file table)
4 bytes - File Size
4 bytes - Filler
2 bytes - File entry length (M)
2 bytes - Filename length (N)
1 byte - Filler
N bytes - Filename
M-17-N bytes - Filler

One of the numbers in the header should be the file count, you could discover it through trial and error at this point.

I certainly appreciate your helping me out.
I'm very sorry! 
I am new at this, and i can't understand what you're reply.
## Post #8
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-01-09T15:40:03+00:00
- Post Title: [PS3] Gundam Senki Record UC 0081 (BfPk File)

I need some help solving these.
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-01-09T16:47:16+00:00
- Post Title: [PS3] Gundam Senki Record UC 0081 (BfPk File)

I am not sure where they are getting the start offset from but if there is only one big archive it does not matter.
this will extract that file for you.

```
#By chrrox
endian big
goto 0x8
get files short
get unk short
get start short
get null short
savepos tbl
for i = 0 < files
goto tbl
get offset long
math offset + 0x43000
get size long
get FFFF long
get short1 short
get nsize short
get null byte
getdstring name nsize
math tbl + short1
log name offset size
next i

```
## Post #10
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-05-12T15:39:06+00:00
- Post Title: [PS3] Gundam Senki Record UC 0081 (BfPk File)

Original script can handle only main game archive (game.arb) due to hardcoded offset. Here is fixed script which should work with all game archives properly.



 gundam_senki_bfpk_extract.zip
(485 Bytes) Downloaded 20 times
## Post #11
- Username: ssenrober
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat May 07, 2022 9:51 pm
- Post datetime: 2022-05-16T00:32:41+00:00
- Post Title: [PS3] Gundam Senki Record UC 0081 (BfPk File)

Thank you very much!
