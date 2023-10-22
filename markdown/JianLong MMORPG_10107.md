## Post #1
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2013-02-02T22:02:32+00:00
- Post Title: JianLong MMORPG

Can someone help me to unpack .bag files please? the extension is not the same as emperor.

Here the site:
[http://lj.163.com/index.html](http://lj.163.com/index.html)
Sample
[http://www48.zippyshare.com/v/43770202/file.html](http://www48.zippyshare.com/v/43770202/file.html)

IF YOU NEED DLL OR OTHER FILES TELL ME.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-03T10:23:23+00:00
- Post Title: JianLong MMORPG

Old thread [here](http://forum.xentax.com/viewtopic.php?f=10&t=9777)
## Post #3
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2013-02-04T11:05:05+00:00
- Post Title: JianLong MMORPG

I've tryed this script but i don't know why it doesn't work, infact at the end result 0 files extracted.

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

#Debug [MODE]

get PAKSIZE asize
get ID long

if ID == 0x62616731
    set TotalFiles_Key "0xe7356461"
    set TableOffset_Key "0xcb449442"
    set UNK1_Key "0x698346bd"
    set UNK2_Key "0x867389fe"
    set UNK3_Key "0xabedc59d"
else ID == 0x62616732
    set TotalFiles_Key "0x27252421"
    set TableOffset_Key "0x3b343432"
    set UNK1_Key "0x5953565d"
    set UNK2_Key "0x6663696e"
    set UNK3_Key "0x7b7d757d"
endif

filexor TotalFiles_Key
get FILES long
filexor TableOffset_Key
get TABLEOFFSET long
filexor ""

set TABLESIZE = PAKSIZE
math TABLESIZE -= TABLEOFFSET
math TABLESIZE -= 4

string TF p= "%08X" FILES
string TO p= "%08X" TABLEOFFSET
string TS p= "%08X" TABLESIZE
print "Total Files: %FILES% (%TF%)"
print "Table Offset: %TABLEOFFSET% (%TO%)"
print "Table Size: %TABLESIZE% (%TS%)"

goto TABLEOFFSET

for i = 0 < FILES
    filexor UNK1_Key
    get UNKNOWN1 long
    filexor UNK2_Key
    get UNKNOWN2 long
    filexor UNK3_Key
    get UNKNOWN3 long
    print "----------------------------"
    string UNK1 p= "%08X" UNKNOWN1
    string UNK2 p= "%08X" UNKNOWN2
    string UNK3 p= "%08X" UNKNOWN3
    print "Unknown1: %UNKNOWN1% (%UNK1%)"
    print "Unknown2: %UNKNOWN2% (%UNK2%)"
    print "Unknown3: %UNKNOWN3% (%UNK3%)"
    print "----------------------------"
next i
```
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-04T12:43:30+00:00
- Post Title: JianLong MMORPG

This script for get only info about archive and files inside. See old thread again chrrox seems finish script for unpack.
## Post #5
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2013-02-04T14:43:35+00:00
- Post Title: JianLong MMORPG

Ok it works  thanks a lot.

But isn't this a unreal engine game? I read that it was made with unreal engine 3
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-04T15:05:12+00:00
- Post Title: JianLong MMORPG

> Reply from Drawing
>
> Ok it works  thanks a lot.

But isn't this a unreal engine game? I read that it was made with unreal engine 3
Nope it's not UE3 it's [BigWorld Engine](http://www.bigworldtech.com/)

[http://www.bigworldtech.com/tian-xia-ii](http://www.bigworldtech.com/tian-xia-ii)
[http://www.bigworldtech.com/tian-xia-iii](http://www.bigworldtech.com/tian-xia-iii)
