## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-17T16:39:28+00:00
- Post Title: The Agency of Anomalies: Mystic Hospital Collector's Edition

script for QuickBMS:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get DUMMY short
get ZSIZE short
comtype unzip_dynamic
savepos OFFSET
clog MEMORY_FILE OFFSET ZSIZE ZSIZE
math OFFSET += ZSIZE
comtype zlib
get DUMMY byte MEMORY_FILE
get FILES short MEMORY_FILE
for i = 0 < FILES
    get NAMESZ byte MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get ZSIZE long MEMORY_FILE
    get SIZE long MEMORY_FILE
    clog NAME OFFSET ZSIZE SIZE
    math OFFSET += ZSIZE
next i
```
