## Post #1
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-06-19T04:33:56+00:00
- Post Title: KOFXIII: unpacking cps

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-19T07:40:44+00:00
- Post Title: KOFXIII: unpacking cps

script for QuickBMS:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "TEXLIST\0"
get MAX_OFFSET long
get DUMMY long

for i = 0
    savepos OFFSET
    if OFFSET >= MAX_OFFSET
        cleanexit
    endif

    getdstring TYPE 8
    get FULLZSIZE long
    get DUMMY long
    get DUMMY long
    get ZIP long
    get FULLZSIZE long
    get DUMMY long
    get CHUNKS long
    get DUMMY long
    math SIZE = 0x10000
    savepos NEXT_OFF

    math TMP = CHUNKS
    math TMP *= SIZE
    putvarchr MEMORY_FILE TMP 0
    log MEMORY_FILE 0 0
    append
    for j = 0 < CHUNKS
        get ZSIZE long
        savepos OFFSET
        clog MEMORY_FILE OFFSET ZSIZE SIZE
        math OFFSET += ZSIZE
        goto OFFSET
    next j
    append

    get NAME basename
    string NAME += "_"
    string NAME += TYPE
    string NAME += i
    get SIZE asize MEMORY_FILE
    log NAME 0 SIZE MEMORY_FILE

    math NEXT_OFF += FULLZSIZE
    goto NEXT_OFF
next i
```
P.S.: it's useless and lame to delete and recreate a thread only to bump it, was enough to add a bump-post to attire our attention instead of using this lame way
## Post #3
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2011-06-19T14:15:54+00:00
- Post Title: KOFXIII: unpacking cps

CPS? Isn't it meant to be PCS?
## Post #4
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2011-06-19T14:37:57+00:00
- Post Title: KOFXIII: unpacking cps

After extracting using QuickBMS, I see files without extensions such as: "00_TEXTURE0"
I've attached an example of it, is there a way to open these files?

Edit:

After using "trid", it scanned these formats being "maybe" the types of file it actually is, thought I'd share this info too:

24.6% (.TGA) Targa bitmap <Original TGA Format - No Image ID> <1007/3>
24.5% (.) MacBinary 2 header <1002/3>
24.5% (.ABR) Adobe Photoshop Brush <1002/3>
24.5% (.BONK) BONK lossless/lossy audio compressor <1001/2>
  1.5% (.CEL) Lumena CEL bitmap <63/63>
[00_TEXTURE0.zip](https://xentaxbackup.github.io/file/4354_00_TEXTURE0.zip)
