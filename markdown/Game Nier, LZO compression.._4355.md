## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-04-19T23:58:36+00:00
- Post Title: Game: Nier, LZO compression..

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Rikto
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 02, 2010 4:37 am
- Post datetime: 2010-05-03T22:01:05+00:00
- Post Title: Game: Nier, LZO compression..

I would also be very interested in these files if anyone can figure out how to decompress them.
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-05-04T18:27:55+00:00
- Post Title: Game: Nier, LZO compression..

looked at it with offzip and signsrch and the only thing I found was on the file KAINE010.MDV

000867ad 309  padding used in hashing algorithms (0x80 0 ... 0) [..64]

The other didnt show me anything, the lzo in the beginning doesnt actually always mean lzo but of course it's a big chance
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-23T16:47:02+00:00
- Post Title: Game: Nier, LZO compression..

I got this its lzo1x

Here is the Script

```
#quickbms script
#By chrrox
endian big
get name FILENAME
string name + ".dec"
get lzo long
get version long
get subversion long
get files long
get TotalUncompSize long
get unk long
goto 0x20
comtype LZO1X
for i = 1 to files
get memoffset long
get size long
get zsize long
savepos offset
append
clog MEMORY_FILE offset zsize size
append
math offset + zsize
goto offset
Padding 0x10000
next i
log NAME 0 TotalUncompSize MEMORY_FILE

```
