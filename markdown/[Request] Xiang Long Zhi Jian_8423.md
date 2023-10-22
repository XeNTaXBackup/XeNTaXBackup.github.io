## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-28T08:07:02+00:00
- Post Title: [Request] Xiang Long Zhi Jian

Ok I found a interesting game packed with .PK format, here I upload sample of files.





[Xiang Long Zhi Jian Archive Research](http://www.mediafire.com/download.php?z1u8s69u4416j1f)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-28T15:03:16+00:00
- Post Title: [Request] Xiang Long Zhi Jian

let me know if the following works correctly:

```
# script for QuickBMS http://quickbms.aluigi.org

math CHUNK_SIZE = 0x10000
comtype unzip_dynamic   # deflate but some files are not compressed
get DUMMY long
get FILES long
for i = 0 < FILES
    get DUMMY long
    get ZSIZE long
    get OFFSET long
    getdstring HASH 32
    savepos TMP
    goto OFFSET
    get DUMMY1 long
    get DUMMY2 long
    get DUMMY3 long
    get DUMMY4 long
    get DUMMY5 long # 0x309d4
    get DUMMY6 long # 0x2f74e
    get DUMMY7 long # 0x28
    get CHUNKS long # 0x27
    get DUMMY8 long # 0x1d4
    get DUMMY9 long # 0x30ba8 (total size)
    math OFFSET1 = OFFSET
    math OFFSET1 += DUMMY5
    math OFFSET2 = OFFSET
    math OFFSET2 += DUMMY6
    savepos OFFSET
    math SIZE = CHUNKS
    math SIZE *= CHUNK_SIZE
    putvarchr MEMORY_FILE SIZE 0
    log MEMORY_FILE 0 0
    append
    for j = 0 < CHUNKS
        goto OFFSET2
        get DUMMY1 long
        get DUMMY2 long     # 0x1a
        get DUMMY3 short    # 0x200
        get DUMMY4 short    # 0x200
        get DUMMY5 short    # 0x90
        get DUMMY6 short    # 0x70
        get DUMMY7 short    # 0x28
        get DUMMY8 short    # 0xa8
        get DUMMY9 long     # 0xa4
        get DUMMY10 long    # 0x28 (relative offset)
        get DUMMY11 long    # 0x12d9 (zsize)
        get DUMMY12 long    # 0x3f800000
        get DUMMY13 long    # 0x3f8000
        get DUMMY14 long    # 0x104
        math DUMMY7 *= 2
        getdstring DUMMY DUMMY7 # probably encoded name
        savepos OFFSET2
        clog MEMORY_FILE OFFSET DUMMY11 CHUNK_SIZE
        math OFFSET += DUMMY11
    next j
    append
    get SIZE asize MEMORY_FILE
    log "" 0 SIZE MEMORY_FILE
    goto TMP
next i
```
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-28T17:50:29+00:00
- Post Title: [Request] Xiang Long Zhi Jian

wow thats cool aluigi, the script begin fine, but after some seconds I get it.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-28T19:34:41+00:00
- Post Title: [Request] Xiang Long Zhi Jian

ok, run quickbms from command-line with the -V option and then paste or send me via pm the last 100 lines showed or similar
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-29T16:33:43+00:00
- Post Title: [Request] Xiang Long Zhi Jian

I have found no fields that state if the chunk is compressed or not so I have adopted the unzip_dynamic compression that does the job automatically, let me know if this work-around works and the files are ok
## Post #6
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-29T16:57:02+00:00
- Post Title: [Request] Xiang Long Zhi Jian

> Reply from aluigi
>
> I have found no fields that state if the chunk is compressed or not so I have adopted the unzip_dynamic compression that does the job automatically, let me know if this work-around works and the files are oksame here aluigi, after extract some files I get same error.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-29T17:09:51+00:00
- Post Title: [Request] Xiang Long Zhi Jian

in this case I don't know what to say because unzip_dynamic has been written just to avoid the zlib errors
## Post #8
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-29T17:44:46+00:00
- Post Title: [Request] Xiang Long Zhi Jian

ahh I forget paste new script, I use old one, sorry for mistakes, now it worked.
