## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-02T12:58:40+00:00
- Post Title: Tasogare no Sinsemilla Portable (PSP)

Here is a quickbms extractor for this game.
黄昏のシンセミア portable
[http://www.cyberfront.co.jp/title/sinsemilla/](http://www.cyberfront.co.jp/title/sinsemilla/)


```
# Decrypt the pgd files first then rename them to match the .hed files.
# script for QuickBMS http://quickbms.aluigi.org by chrrox

open FDDE "decrypted" 0
open FDDE "hed" 1

goto 8 1
get files long 1
goto 32 1
savepos tbl 1
for i = 0 < files
goto tbl 1
get offset long 1
get zsize long 1
get null long 1
get noff long 1
savepos tbl 1
goto noff 1
get name string 1
if zsize != 0
log MEMORY_FILE offset zsize
get Zpac long MEMORY_FILE
get size long MEMORY_FILE
math zsize - 8
clog name 8 zsize size MEMORY_FILE
endif
next i

```

you can open the images with
[viewtopic.php?f=18&t=10489](http://forum.xentax.com/viewtopic.php?f=18&t=10489)
