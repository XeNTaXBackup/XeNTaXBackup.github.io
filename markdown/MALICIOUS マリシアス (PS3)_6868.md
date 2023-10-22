## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-29T02:31:09+00:00
- Post Title: MALICIOUS マリシアス (PS3)

Here is a script to extract the archives from this Japanese game.
use this script after you use psarc to extract the psarc files.
[http://malicious.alvion.jp/](http://malicious.alvion.jp/)


```
goto 0x10
get files long
goto 0x40
get baseoff long
get tablenums long
goto baseoff
for i = 0 < tablenums
get byte1 byte
get byte2 byte
get byte3 byte
get byte4 byte
get secsize long
get BASE long
get null long
putarray 0 byte1 BASE
next i
goto 0x50
savepos ntbl
for i = 0 < files
goto ntbl
get tbloff long
savepos ntbl
goto tbloff
getdstring name 0x20
get type long
get null long
get size long
get offset long
getdstring null 6
get offpos byte
getdstring null 9
getarray BASE 0 offpos
math offset + BASE
log name offset size
next i

```


here is the psn link to the game.
[http://zeus.dl.playstation.net/cdn/JP00 ... lg0VUV.pkg](http://zeus.dl.playstation.net/cdn/JP0015/NPJB00070_00/sSOyuEm7Kq0LM3xICPQm83tQADOPiUbL9Vqv32qKc3HWfLQQCCco46RiK1Xu6dmOajaNK3W4vFSIQn1df8qom6KuMIIkNUulg0VUV.pkg)
