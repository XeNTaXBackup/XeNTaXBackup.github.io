## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-07-21T15:21:39+00:00
- Post Title: Sacred Legend Online (幻想神域 Online) bms script

This game uses nif files fully supported in nifskope.
Gamebryo File Format, Version 20.3.0.9


```
#幻想神域 Online
#http://ff.x-legend.com.tw/#
open FDSE pkg.idx
get files asize
math files - 0x124
math files / 0x250
goto 0x124
for i = 0 < files
get FILENUM long
get OFFSET long
get unk02 long
get ZSIZE long
get unk04 long
get unk05 long
get unk06 long
get unk07 long
get unk08 long
get unk09 long
get unk10 long
get unk11 long
get unk12 long
get unk13 long
get SIZE long
getdstring file 0x104
getdstring NAME 0x108
string NAME + file
get packfile long
get unk15 long
if packfile < 10
set pname 0x3030
string pname = pname
string pname + packfile
set var string "pkg"
string var + pname
string var + ".pkg"
open FDSE var 1
elif packfile < 100
set pname 0x30
string pname = pname
string pname + packfile
set var string "pkg"
string var + pname
string var + ".pkg"
open FDSE var 1
elif packfile < 1000
set pname ""
string pname + packfile
set var string "pkg"
string var + pname
string var + ".pkg"
open FDSE var 1
endif
if ZSIZE != SIZE
clog NAME OFFSET ZSIZE SIZE 1
else
log NAME OFFSET ZSIZE 1
endif
next i
```
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-22T00:05:03+00:00
- Post Title: Sacred Legend Online (幻想神域 Online) bms script

is this one 20 GB too ?
