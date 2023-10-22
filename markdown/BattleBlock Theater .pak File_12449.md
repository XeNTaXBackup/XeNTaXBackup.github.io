## Post #1
- Username: SSSerek
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Aug 21, 2014 3:33 am
- Post datetime: 2014-12-31T10:58:15+00:00
- Post Title: BattleBlock Theater .pak File

Hi.

I want to unpack Txtfiles.pak file from that game to translate it, but I don't know how to do it. Can someone help me with that?
File in attachment.
[TxtFiles.rar](https://xentaxbackup.github.io/file/8404_TxtFiles.rar)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-12-31T15:25:07+00:00
- Post Title: BattleBlock Theater .pak File

```
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

endian BIG
get FILES long

for i = 0 < FILES
    get OFFSET long
    get SIZE long
    getdstring NAME 64
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-06T20:15:12+00:00
- Post Title: BattleBlock Theater .pak File

none of the files extracted from the sample contain localisation   
they look like audio parameters

reply here if you find something in the other gamedata files
