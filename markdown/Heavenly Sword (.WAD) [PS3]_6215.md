## Post #1
- Username: maggot666x
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Dec 13, 2010 3:51 am
- Post datetime: 2011-03-13T21:53:14+00:00
- Post Title: Heavenly Sword (.WAD) [PS3]

Please help me unpack/pack archive files of Heavenly Sword (.WAD) [PS3]





1) sample files (1.86 MB) [http://www.multiupload.com/JLU3L15SXE](http://www.multiupload.com/JLU3L15SXE)
3) global.wad (142.23 MB) [http://www.multiupload.com/V4ZO6YLHVI](http://www.multiupload.com/V4ZO6YLHVI)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-14T05:35:03+00:00
- Post Title: Heavenly Sword (.WAD) [PS3]

script for QuickBMS:

```
get DUMMY long
get FILES long
get BASE_OFFSET long
getdstring DUMMY 0x20
for i = 0 < FILES
    get OFFSET long
    get ZSIZE long
    get SIZE long
    get CRC long
    math OFFSET += BASE_OFFSET
    if ZSIZE == SIZE
        log "" OFFSET SIZE
    else
        clog "" OFFSET ZSIZE SIZE
    endif
next i
```


*edit* updated
