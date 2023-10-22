## Post #1
- Username: hdwong
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 19, 2014 11:02 pm
- Post datetime: 2014-09-20T05:57:20+00:00
- Post Title: Aura Kingdom *.pkg  unpack Fail

hello everyone .. My English is not very good,Please do not take offense..

I recently playing [Fantasy Frontier Online(Chinese Version)].. [http://filesty.changyou.com/hxsy/gw/HXS ... 140708.zip](http://filesty.changyou.com/hxsy/gw/HXSY-4.0.1.6-20140708.zip)
I use QuickBMS Unpack This GameRes..

```
#   Eden Eternal
#   Kitsu Saga
#   Dragon Slayer
# script for QuickBMS http://quickbms.aluigi.org

comtype unzip_dynamic
getdstring DUMMY 260
getdstring SIGN 32
math PKG_OLD = -1
get FULLSIZE asize
do
    get DUMMY long
    get OFFSET long
    get DUMMY long
    get ZSIZE long
    getdstring DUMMY 0x28
    get SIZE long
    getdstring NAME2 260
    getdstring NAME 260
    get DUMMY long
    get PKG long
    get DUMMY long
    if PKG != PKG_OLD
        string PKG_NAME p= "pkg%03d.pkg" PKG
        open FDSE PKG_NAME 1
        math PKG_OLD = PKG
    endif
    string NAME += NAME2

    goto OFFSET 1
    get TMP1 byte 1
    get TMP2 byte 1
    if TMP1 == 0x88 && TMP2 == 0x1c
        savepos OFFSET 1
        math ZSIZE -= 2
    endif
    clog NAME OFFSET ZSIZE SIZE 1
    savepos CURR
while CURR < FULLSIZE

```


This script success unpack head is 0x7801 and Most 0x881c..However, some 0x881c head file unpack is fail..I look Zdata Like Zlib.but is deform..

some unpack fail File:
\data\db\t_textindex.ini
\data\db\t_item.ini
\data\db\t_itemmall.ini
\data\db\t_biology.ini
\biology\texture\m74001.dds
\biology\texture\m74051.dds
\biology\texture\m74052.dds

GameRes is too big..I picked the two can't unpack files to upload..

So I would like in this forum looking for your help..Thank you 
[pkg.rar](https://xentaxbackup.github.io/file/7841_pkg.rar)
