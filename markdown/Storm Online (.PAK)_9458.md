## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-12T18:19:52+00:00
- Post Title: Storm Online (*.PAK)

Site: [here](http://storm.cherrycredits.com)
Download: [here](http://storm.cherrycredits.com/download/fullclient.html)
Screenshots: [here](http://storm.cherrycredits.com/wiki/feature--screenshots)

and script for unpack PAK files 

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype lzo1x

get PAKSIZE long
get BASEOFF long
get FILES long

for i = 0 < FILES
   filexor "\xff"
   getdstring NAME 0x100
   get OFFSET long
   get ZSIZE long
   get SIZE long
   get DUMMY longlong
   get DUMMY long
   filexor ""
if ZSIZE == SIZE
   log NAME OFFSET SIZE
else
   clog NAME OFFSET ZSIZE SIZE
 endif
next i
```
