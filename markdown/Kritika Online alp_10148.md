## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-02-18T17:11:17+00:00
- Post Title: Kritika Online alp

Here is an alp extractor for Kritika Online. [http://kt.hangame.com](http://kt.hangame.com)
Client download [http://krdown.hangame.com/pub/PUBKRITIK ... angame.zip](http://krdown.hangame.com/pub/PUBKRITIKA/Install/Kritika_OBT_Hangame.zip)


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
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-18T17:21:24+00:00
- Post Title: Kritika Online alp

You outstripped me
## Post #3
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2013-02-19T10:24:03+00:00
- Post Title: Kritika Online alp

Directory and file name in Korean, an error
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-02-19T11:17:05+00:00
- Post Title: Kritika Online alp

just rename them or click rename automatically.
its only a few files.
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-03-28T06:16:43+00:00
- Post Title: Kritika Online alp

> Reply from chrrox
>
> just rename them or click rename automatically.
its only a few files.any chance to update it? when tyr upack files of JP version I get that.

Dropmodel.alp



Dropmodel.alph



Samples:

[https://www.dropbox.com/s/6pla9rb6f2dpo ... e%20ALP.7z](https://www.dropbox.com/s/6pla9rb6f2dpoei/Kritika%20Online%20ALP.7z)
