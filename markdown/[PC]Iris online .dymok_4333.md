## Post #1
- Username: dongdong
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 28, 2009 11:50 am
- Post datetime: 2010-04-14T08:48:22+00:00
- Post Title: [PC]Iris online *.dymok

Hi,guys,I've played game of iris online.
I want to extract the game resource files, but the following error(use zip.bms):
Error:unknown ZIP signature 10585 at offset 0

Please help me, thanks.

bin file:[http://www.sendspace.com/file/nkafcu](http://www.sendspace.com/file/nkafcu)
sample file:[http://www.sendspace.com/file/rh85cu](http://www.sendspace.com/file/rh85cu)

game:[http://iris.enpang.com/event/2010/0401/](http://iris.enpang.com/event/2010/0401/)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-14T09:51:01+00:00
- Post Title: [PC]Iris online *.dymok

zip.bms must be used only with zip or zip-like files.
dymok is obfuscated in some way and it's used by mkonline.exe
## Post #3
- Username: dongdong
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 28, 2009 11:50 am
- Post datetime: 2010-04-14T10:12:07+00:00
- Post Title: [PC]Iris online *.dymok

> Reply from aluigi
>
> zip.bms must be used only with zip or zip-like files.
dymok is obfuscated in some way and it's used by mkonline.exe

Which bms files available for this game？

download: [http://iris.enpang.com/pds/download.asp](http://iris.enpang.com/pds/download.asp)

Thanks.
## Post #4
- Username: dongdong
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 28, 2009 11:50 am
- Post datetime: 2010-04-16T02:09:57+00:00
- Post Title: [PC]Iris online *.dymok

Who can help me to write script to extract the file of *.dymok？
Thanks a lot.
## Post #5
- Username: dongdong
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 28, 2009 11:50 am
- Post datetime: 2010-04-17T05:50:11+00:00
- Post Title: [PC]Iris online *.dymok

I had update the file.
[http://www.sendspace.com/file/aqhwxh](http://www.sendspace.com/file/aqhwxh)

The file contain *.nif.

Please help me to extract *.nif. 
Thank in advance.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-17T13:32:21+00:00
- Post Title: [PC]Iris online *.dymok

you are really lucky because I had an intuition and it revelead to be the correct one:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get SIZE asize
get NAME basename
string NAME += ".zip"
filexor 0x69
log MEMORY_FILE 0 SIZE
filexor ""
for i = 0 < SIZE
    getvarchr TMP MEMORY_FILE i
    math TMP2 = TMP
    math TMP  >>= 4
    math TMP2 <<= 4
    math TMP |= TMP2
    putvarchr MEMORY_FILE i TMP
next i
log NAME 0 SIZE MEMORY_FILE

print "the zip password is jZKCZ/aDV/ORScsYCEAK=n4BH"
```

note that I would have never download the whole game client so bumping and PMing was totally useless, I repeat: you were lucky this time
## Post #7
- Username: dongdong
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Sep 28, 2009 11:50 am
- Post datetime: 2010-04-18T00:51:12+00:00
- Post Title: [PC]Iris online *.dymok

> Reply from aluigi
>
> you are really lucky because I had an intuition and it revelead to be the correct one:
Code: Select all# Iris Online
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get SIZE asize
get NAME basename
string NAME += ".zip"
filexor 0x69
log MEMORY_FILE 0 SIZE
filexor ""
for i = 0 < SIZE
    getvarchr TMP MEMORY_FILE i
    math TMP2 = TMP
    math TMP  >>= 4
    math TMP2 <<= 4
    math TMP |= TMP2
    putvarchr MEMORY_FILE i TMP
next i
log NAME 0 SIZE MEMORY_FILE

print "the zip password is jZKCZ/aDV/ORScsYCEAK=n4BH"
note that I would have never download the whole game client so bumping and PMing was totally useless, I repeat: you were lucky this time

Thanks very much! aluigi
