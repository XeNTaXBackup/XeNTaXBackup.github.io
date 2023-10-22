## Post #1
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-22T07:59:12+00:00
- Post Title: Ys seven *.itv

Hi. There are .sp4 files in Ys seven and here is a bms script to unpack .sp4 files. However, .sp4 contains lots of .itv files. I think it is graphic files but had no idea what is MMV3.   

```

get files long

for i = 0 < files
   getdstring name 0x10
   get offset long
   get size long
   get null long
   get null long
   
   get packname filename
   string packname += _unpacked/
   string packname += name
   log packname offset size
next i

```
