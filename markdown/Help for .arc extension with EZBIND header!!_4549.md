## Post #1
- Username: kenn
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Mar 23, 2010 12:59 am
- Post datetime: 2010-06-03T06:14:57+00:00
- Post Title: Help for .arc extension with EZBIND header!!

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-03T12:53:29+00:00
- Post Title: Help for .arc extension with EZBIND header!!

script for QuickBMS:

```
idstring "EZBIND\0\0"
get FILES long
get DUMMY long
for i = 0 < FILES
    get NAME_OFF long
    get SIZE long
    get OFFSET long
    get CRC long

    savepos TMP
    goto NAME_OFF
    get FNAME string
    goto TMP

    get NAME basename
    string NAME += /
    string NAME += FNAME

    clog NAME OFFSET SIZE SIZE
next i
```
I have programmed it to create a folder with the same name of the archive so that you will have no troubles with duplicated names
## Post #3
- Username: kenn
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Mar 23, 2010 12:59 am
- Post datetime: 2010-07-09T13:37:22+00:00
- Post Title: Help for .arc extension with EZBIND header!!

thanks it works perfectly
now i can see those text that i need

but i have another one request..

is this possible to repack it again using quickbms? i cant find a repacker of this EZBIND header
can you please help to deal with this.. i really really need to pack it again after editing some of the dialogues please..
## Post #4
- Username: damimavpl
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jul 16, 2011 4:03 pm
- Post datetime: 2011-07-19T21:36:20+00:00
- Post Title: Help for .arc extension with EZBIND header!!

> Reply from aluigi
>
> script for QuickBMS:
Code: Select allcomtype gzip
idstring "EZBIND\0\0"
get FILES long
get DUMMY long
for i = 0 < FILES
    get NAME_OFF long
    get SIZE long
    get OFFSET long
    get CRC long

    savepos TMP
    goto NAME_OFF
    get FNAME string
    goto TMP

    get NAME basename
    string NAME += /
    string NAME += FNAME

    clog NAME OFFSET SIZE SIZE
next iI have programmed it to create a folder with the same name of the archive so that you will have no troubles with duplicated names

This is work also for "Tales of The Worlds Radiant Mythology 2"  but how to pack again (finish translating) files to *.arc ??
## Post #5
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2011-08-15T13:59:11+00:00
- Post Title: Help for .arc extension with EZBIND header!!

If you wait until tomorrow I can code a C++ program to unpack/pack the files.
## Post #6
- Username: damimavpl
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jul 16, 2011 4:03 pm
- Post datetime: 2011-08-15T20:04:20+00:00
- Post Title: Help for .arc extension with EZBIND header!!

> Reply from Truthkey
>
> If you wait until tomorrow I can code a C++ program to unpack/pack the files.

Yes, please
## Post #7
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2011-08-17T22:13:41+00:00
- Post Title: Help for .arc extension with EZBIND header!!

> Reply from damimavpl
>
> Truthkey wrote:If you wait until tomorrow I can code a C++ program to unpack/pack the files.

Yes, please

That package in the first post doesn't seem to have any text file (the facechats thingy). Can any of you provide me with an actual text file (compressed) so I can make the program? Send it to me through PM, don't post here.
## Post #8
- Username: damimavpl
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jul 16, 2011 4:03 pm
- Post datetime: 2011-08-18T06:23:11+00:00
- Post Title: Help for .arc extension with EZBIND header!!

> Reply from Truthkey
>
> damimavpl wrote:Truthkey wrote:If you wait until tomorrow I can code a C++ program to unpack/pack the files.

Yes, please 

That package in the first post doesn't seem to have any text file (the facechats thingy). Can any of you provide me with an actual text file (compressed) so I can make the program? Send it to me through PM, don't post here.

here: [viewtopic.php?f=21&t=6996](http://forum.xentax.com/viewtopic.php?f=21&t=6996)
## Post #9
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2011-08-19T20:56:39+00:00
- Post Title: Help for .arc extension with EZBIND header!!

Does anyone know what kind of checksum do the arc files have? I'm trying with crc32 but the result number is not the same as the ones in the package.

EDIT: I already finished the program, but until I can add the CRC data it probably won't work ingame.
