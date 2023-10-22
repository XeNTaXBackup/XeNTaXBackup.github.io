## Post #1
- Username: techtechi
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 26, 2022 10:08 am
- Post datetime: 2022-06-08T21:49:24+00:00
- Post Title: Michigan: Report from Hell (PS2) .dat .gmd

Samples: [https://www.mediafire.com/file/g739s8zf ... A.zip/file](https://www.mediafire.com/file/g739s8zfanczgma/HAYA.zip/file)
## Post #2
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-06-09T02:35:08+00:00
- Post Title: Michigan: Report from Hell (PS2) .dat .gmd

Hello.

Maybe this?

```
# Michigan: Report from Hell (.???/GMDF)
# Version 0.1b

findloc MAGIC STRING "GMDF"
GOTO MAGIC
get file asize
idstring "GMDF"
get ID long
get entries long
SAVEPOS TEMP
XMATH TEMP "(TEMP + 0X34)"
GOTO TEMP
for rip = 1 to entries

get offset long
savepos temp
get size long
if SIZE == 0X00
xmath size "(file - offset)"
log "" offset SIZE
break
endif
xmath size "(size - offset)"


log "" offset size
goto temp
next rip
```
