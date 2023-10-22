## Post #1
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2015-01-20T12:48:39+00:00
- Post Title: [REQ] Kritika APL Unpack Script

Hello there again! I'm wondering if anyone has a working QBMS script for Kritika.

Client:
[http://kt.hangame.com/index.nhn](http://kt.hangame.com/index.nhn)

The following script by chrrox doesn't seem to be working and searching for awhile turned up nothing:

```
#Quickbms script by chrrox
comtype MSF
get TSIZE asize
idstring "GKPA"
get VERSION short
get FTABLE long
goto FTABLE
Do
filexor ""
savepos TMP
get TBLSIZE long
savepos TMP
filexor "\xDF\x97\x6F\x03" TMP
getdstring MAGIC 4
#print "%MAGIC%"
if MAGIC == "DGKP"
getdstring NULL 0xA
get NSIZE short
math NSIZE * 2
getdstring UNAME NSIZE
set DIRNAME unicode UNAME
else
getdstring NULL 0x7
get OFFSET long
get SIZE long
get ZSIZE long
getdstring NULL 0xC
get NSIZE short
math NSIZE * 2
getdstring UNAME NSIZE
set NAME2 unicode UNAME
set NAME DIRNAME
string NAME + \
string NAME + NAME2
filexor "\xDF\x97\x6F\x03" OFFSET
clog NAME OFFSET ZSIZE SIZE
endif
While TMP < TSIZE 

```


I've uploaded a sample APL here:
[https://mega.co.nz/#!Z8sDTQTC!BB1zAoXRj ... ilCQfPN9Xg](https://mega.co.nz/#!Z8sDTQTC!BB1zAoXRjL1gTP1NrZIRrObJuOupctQ2SilCQfPN9Xg)


Thanks for reading!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-20T14:20:04+00:00
- Post Title: [REQ] Kritika APL Unpack Script

firstly: wrong subforum
2ndly: read this thread:
[viewtopic.php?f=21&t=12048](http://forum.xentax.com/viewtopic.php?f=21&t=12048)

try the updated script; you'll need npc.alph, too
## Post #3
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2015-01-20T16:52:59+00:00
- Post Title: [REQ] Kritika APL Unpack Script

> Reply from shakotay2
>
> firstly: wrong subforum
2ndly: read this thread:
viewtopic.php?f=21&t=12048

try the updated script; you'll need npc.alph, too

Thanks for the reply, I got it working with blender, but unfortunately there is no animation support :<
