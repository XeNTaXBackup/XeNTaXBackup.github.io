## Post #1
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-09T17:28:36+00:00
- Post Title: [PS3] Dead Space (*.viv)

Hello, friends, I am trying to extract the files or bigfile0.viv, bigfile1.viv bigfile2.viv and the PS3, but it does not work with the tool of Rick RickVisceral, nor with the script of Luigi.

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring BIGH
get VIV_SIZE long
endian big
get FILES long
get HEADER_SIZE long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get NAME_CRC long
    log NAME_CRC OFFSET SIZE
next i
```


I tested changing
idstring BIGH
changed
idstring BIGF

if someone can help.
[BIGFILE0-edit.rar](https://xentaxbackup.github.io/file/5973_BIGFILE0-edit.rar)
## Post #2
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-09T17:29:21+00:00
- Post Title: [PS3] Dead Space (*.viv)

Another file...
[BIGFILE1-edit.rar](https://xentaxbackup.github.io/file/5974_BIGFILE1-edit.rar)
## Post #3
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-13T18:15:24+00:00
- Post Title: [PS3] Dead Space (*.viv)

UP.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-11-14T07:37:39+00:00
- Post Title: [PS3] Dead Space (*.viv)

[http://aluigi.org/papers/bms/ea_big4.bms](http://aluigi.org/papers/bms/ea_big4.bms)
## Post #5
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-14T09:55:54+00:00
- Post Title: [PS3] Dead Space (*.viv)

Thank Luigi
