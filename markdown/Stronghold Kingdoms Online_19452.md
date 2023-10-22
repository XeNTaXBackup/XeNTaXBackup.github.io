## Post #1
- Username: SoldierTODD
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Oct 25, 2014 5:15 am
- Post datetime: 2019-02-04T22:35:19+00:00
- Post Title: Stronghold Kingdoms Online

How to unzip Stronghold Kingdoms Online graphic files?

[https://www.mediafire.com/file/af2482r2 ... e.rar/file](https://www.mediafire.com/file/af2482r2z1fx3na/Stronghold_Kingdoms_Online.rar/file)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-05T02:24:36+00:00
- Post Title: Stronghold Kingdoms Online

script for QuickBMS to extract dds from zlib compressed ddsx sample files.  

```

comtype zlib_noerror
get ZSIZE asize
get NAME basename
string NAME + .dds
clog NAME 0x0 ZSIZE ZSIZE

```
