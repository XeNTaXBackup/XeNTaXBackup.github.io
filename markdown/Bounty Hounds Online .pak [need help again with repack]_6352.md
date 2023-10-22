## Post #1
- Username: msgdim
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Apr 04, 2011 6:12 pm
- Post datetime: 2011-04-04T12:52:25+00:00
- Post Title: Bounty Hounds Online .pak [need help again with repack]

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-04T13:11:09+00:00
- Post Title: Bounty Hounds Online .pak [need help again with repack]

script for quickbms:

```

get DUMMY long
get DUMMY long
get FILES long
for i = 0 < FILES
    getdstring NAME 0x30
    get DUMMY long
    get OFFSET long
    get SIZE long
    get ZSIZE long
    clog NAME OFFSET ZSIZE SIZE
next i
```
## Post #3
- Username: msgdim
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Apr 04, 2011 6:12 pm
- Post datetime: 2011-04-04T14:47:38+00:00
- Post Title: Bounty Hounds Online .pak [need help again with repack]

Oh, it works very well.
Thanks for advance.
## Post #4
- Username: msgdim
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Apr 04, 2011 6:12 pm
- Post datetime: 2011-04-07T04:06:46+00:00
- Post Title: Bounty Hounds Online .pak [need help again with repack]

> Reply from aluigi
>
> script for quickbms:
Code: Select all# Bounty Hounds Online

get DUMMY long
get DUMMY long
get FILES long
for i = 0 < FILES
    getdstring NAME 0x30
    get DUMMY long
    get OFFSET long
    get SIZE long
    get ZSIZE long
    clog NAME OFFSET ZSIZE SIZE
next i

can you create a nice repack script one? thanks in advanced.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-07T11:53:40+00:00
- Post Title: Bounty Hounds Online .pak [need help again with repack]

that script works also as reinjector.
you must only create a link to quickbms.exe and adding -r -w in the "Target:" field in the properties of the link.
make a backup of the original archive
click on the link and select the same script, archive and folder you used for the extraction

remember to delete the files that you didn't modify in the folder where you extracted them, so if you modified only the file blahblah.xxx you must delete all the others and you MUST be sure that the size of such file is not bigger than the original one
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-13T00:40:02+00:00
- Post Title: Bounty Hounds Online .pak [need help again with repack]

It seems the archives have changed since then (probably since they've completed the game, or at least, from what I've read on MMO news sites)

Here's a small sample that contains shader information (everything else is 10+ MB)
[Shaders.7z](https://xentaxbackup.github.io/file/4620_Shaders.7z)
