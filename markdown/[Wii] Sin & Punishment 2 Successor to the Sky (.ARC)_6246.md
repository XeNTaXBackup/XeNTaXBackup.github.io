## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-19T18:13:06+00:00
- Post Title: [Wii] Sin & Punishment 2: Successor to the Sky (*.ARC)

The files are ARC, but are not u8 archives, the headers say NARC but do not work with NARC tools. Possibly proprietary variation?
[comdat.rar](https://xentaxbackup.github.io/file/4084_comdat.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-20T09:51:54+00:00
- Post Title: [Wii] Sin & Punishment 2: Successor to the Sky (*.ARC)

script for quickbms:

```
idstring "NARC"
get FILES long
get NAME_SIZE long
get BASE_OFF long
math NAME_BASE = BASE_OFF
math NAME_BASE -= NAME_SIZE
for i = 0 < FILES
    get DUMMY long
    get NAME_OFF long
    get OFFSET long
    get SIZE long
    savepos TMP
    math NAME_OFF += NAME_BASE
    goto NAME_OFF
    get NAME string
    goto TMP
    math OFFSET += BASE_OFF
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-21T10:02:27+00:00
- Post Title: [Wii] Sin & Punishment 2: Successor to the Sky (*.ARC)

Thanks a lot! Was using the hex editor extract method which made the process rather tedious so again thanks.
