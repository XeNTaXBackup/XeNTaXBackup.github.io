## Post #1
- Username: tomitza
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 04, 2010 5:41 am
- Post datetime: 2010-05-08T16:08:21+00:00
- Post Title: Wizard101 - game archive extract

Hi,

The game data of the free online game Wizard101 (Brio engine) are structured in some WAD packs.

Do can someone figure how to extract those packages ?

Thanks,
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-05-08T16:48:17+00:00
- Post Title: Wizard101 - game archive extract

if you want help post sample files.
## Post #3
- Username: tomitza
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 04, 2010 5:41 am
- Post datetime: 2010-05-09T09:31:14+00:00
- Post Title: Wizard101 - game archive extract

Ok, here are some example files:

[http://www.megafileupload.com/en/file/2 ... 1-wad.html](http://www.megafileupload.com/en/file/227635/file1-wad.html)
[http://www.megafileupload.com/en/file/2 ... 2-wad.html](http://www.megafileupload.com/en/file/227636/file2-wad.html)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-09T09:46:35+00:00
- Post Title: Wizard101 - game archive extract

script for QuickBMS:

```
get DUMMY long
get FILES long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get ZSIZE long
    get DUMMY byte
    get ZIP long
    get NAMESZ long
    getdstring NAME NAMESZ
    if ZIP == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #5
- Username: tomitza
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 04, 2010 5:41 am
- Post datetime: 2010-05-09T18:46:05+00:00
- Post Title: Wizard101 - game archive extract

Thanks alot for the superfast help - it worked !!

Some of the file extracted are some textures in "nif" format (Game Brio engine); i'll post also the help request for acces/convert those files - in the adequate forum branch.
