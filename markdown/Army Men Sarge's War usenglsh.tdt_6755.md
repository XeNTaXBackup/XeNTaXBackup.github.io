## Post #1
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2011-06-09T03:07:33+00:00
- Post Title: Army Men Sarge's War usenglsh.tdt

Hi, is there a way to open the file usenglsh.tdt from army men sarge's war? thank you.
[usenglsh.rar](https://xentaxbackup.github.io/file/4312_usenglsh.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-11T10:56:50+00:00
- Post Title: Army Men Sarge's War usenglsh.tdt

it's just a sequence of offsets but the content has no sense probably because it's obfuscated text, anyway the following script for quickbms extracts these parts as files but I guess it's not what you needed:

```
get FILES long
    get OFFSET long
for i = 1 <= FILES
    if i < FILES
        get NEXT_OFFSET long
    else
        get NEXT_OFFSET asize
    endif
    math SIZE = NEXT_OFFSET
    math SIZE -= OFFSET
    log "" OFFSET SIZE
    math OFFSET = NEXT_OFFSET
next i
```
## Post #3
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2011-06-11T17:36:24+00:00
- Post Title: Army Men Sarge's War usenglsh.tdt

I thought this file had the texts from the game. well, thanks for the help anyway.

EDIT: Can you help me with this game?
[viewtopic.php?f=10&t=5625](http://forum.xentax.com/viewtopic.php?f=10&t=5625)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-11T18:11:46+00:00
- Post Title: Army Men Sarge's War usenglsh.tdt

no because I work only with archives (big file containing many files) and not single translation files
## Post #5
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2011-06-13T15:45:06+00:00
- Post Title: Army Men Sarge's War usenglsh.tdt

OK, thanks
