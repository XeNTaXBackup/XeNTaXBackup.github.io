## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-04T13:13:56+00:00
- Post Title: ps3 pkg files

Here is a quickbms script to extract ps3 pkg files after they are decrypted.

```
get files long
math files / 0x20
set path /
goto 0
savepos tbl
for i = 0 < files
goto tbl
get nameoff long
get NSIZE long
get offset longlong
get size longlong
get unk03 long
get unk04 long
savepos tbl
goto nameoff
getdstring name NSIZE
if size != 0
log name offset size
endif
next i

```
## Post #2
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-09-05T12:37:22+00:00
- Post Title: ps3 pkg files

can't work with the PKG files of monster's hunter P3 HD verson
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-05T12:38:13+00:00
- Post Title: ps3 pkg files

you have to decrypt it first.

also that game is not using pkg files its using edat files which are encrypted with an unkown key.
## Post #4
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-09-05T14:05:00+00:00
- Post Title: ps3 pkg files

the game file
[1.jpg](https://xentaxbackup.github.io/file/4688_1.jpg)
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-05T15:46:48+00:00
- Post Title: ps3 pkg files

Inside that pkg file are edat files.
Edat files are encrypted DLC files with no way of extracting them.
## Post #6
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-09-06T00:53:29+00:00
- Post Title: ps3 pkg files

ok i see
