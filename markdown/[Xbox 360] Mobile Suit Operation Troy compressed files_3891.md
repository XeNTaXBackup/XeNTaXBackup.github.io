## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-11-24T12:32:50+00:00
- Post Title: [Xbox 360] Mobile Suit Operation Troy compressed files

Can someone help me on this files? The header file is just xml file and the package file are data!
But the data are compressed with a unknow method which I can not figure it out! Please help on this.

Thanks
[MS_OP_Troy_Script.rar](https://xentaxbackup.github.io/file/2555_MS_OP_Troy_Script.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-26T17:58:34+00:00
- Post Title: [Xbox 360] Mobile Suit Operation Troy compressed files

the extraction of the files is trivial, the problem is their decompression because I don't know what algorithm is used.
I only know that it's the same/similar header used in Wolfenstein and other games.

in the meantime this is the quickbms script for the extraction of the files "as is" (so still compressed or encoded or what they are):

```
open FDDE package 1

for
    findloc NAME string "Name="
    math NAME += 6
    goto NAME
    getct NAME string 0x22

    findloc OFFSET string "Offset="
    math OFFSET += 8
    goto OFFSET
    getct OFFSET string 0x22

    findloc SIZE string "Size="
    math SIZE += 6
    goto SIZE
    getct SIZE string 0x22

    log NAME OFFSET SIZE 1
next
```
