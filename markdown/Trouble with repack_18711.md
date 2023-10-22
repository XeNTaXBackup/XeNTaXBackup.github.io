## Post #1
- Username: haiwood
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 20, 2018 4:20 pm
- Post datetime: 2018-08-20T08:40:23+00:00
- Post Title: Trouble with repack

Hi,

I've already been succeeding in using Quickbms to extract from a data file using provided script, but cannot reimport or repack it with the same script. It keeps displaying the following error:


After running some tests, i succeeded in importing only *.fev extension file but not the others, is there any working method that I can use for reimporting or repacking? Thank you.

Quickbms script code:

> # New Sword of Legends Online - 古剑奇谭网络版 (script 0.2.1)
>
> # script for QuickBMS http://quickbms.aluigi.org
>
> 
>
> math NAMES = 0
>
> get EXT extension
>
> if EXT == "idx"
>
>     callfunction PARSE_IDX 1
>
>     for DATA_NUM = 0
>
>         string TMP p "%s%03d" "data" DATA_NUM
>
>         print "try open data file %TMP%"
>
>         open FDSE TMP 0 EXISTS
>
>         if EXISTS != 0
>
>             callfunction EXTRACT 1
>
>         else
>
>             if DATA_NUM > 0
>
>                 break
>
>             endif
>
>         endif
>
>     next DATA_NUM
>
> else
>
>     callfunction EXTRACT 1
>
> endif
>
> 
>
> startfunction PARSE_IDX
>
>     comtype lzma
>
>     get SIZE longlong
>
>     get DUMMY longlong
>
>     get ZSIZE longlong
>
>     get CHUNK_SIZE long
>
>     get DUMMY long
>
>     xmath CHUNKS "SIZE / CHUNK_SIZE"
>
>     if SIZE % CHUNK_SIZE
>
>         math CHUNKS + 1
>
>     endif
>
>     savepos TMP
>
>     xmath OFFSET "TMP + (CHUNKS * 4)"
>
>     putvarchr MEMORY_FILE SIZE 0
>
>     log MEMORY_FILE 0 0
>
>     append
>
>     for x = 0 < CHUNKS
>
>         get CHUNK_ZSIZE long
>
>         clog MEMORY_FILE OFFSET CHUNK_ZSIZE CHUNK_SIZE
>
>         math OFFSET + CHUNK_ZSIZE
>
>     next x
>
>     append
>
>     goto 0 MEMORY_FILE
>
>     math IDX_SIZE = SIZE
>
>     for TMP = 0 < IDX_SIZE
>
>         get TMP line MEMORY_FILE
>
>         string ELEMENTS S TMP HASH NAME SIZE
>
>         putarray 10 -1 HASH
>
>         putarray 11 -1 NAME
>
>         putarray 12 -1 SIZE
>
>         savepos TMP MEMORY_FILE
>
>     next NAMES
>
> endfunction
>
> 
>
> startfunction EXTRACT
>
> comtype oodle
>
> idstring "ZFS\0"
>
> do
>
>     idstring "[IX]"
>
>     get NEXT_OFF long
>
>     for i = 0 < 0x1000
>
>         getdstring HASH 20
>
>         get OFFSET long
>
>         get ZSIZE long
>
>         get DUMMY long  # no, it's not the decompressed size
>
> 
>
>         set NAME string ""
>
>         if NAMES != 0
>
>             string HASH b HASH
>
>             putvarchr HASH 40 0
>
>             for x = 0 < NAMES
>
>                 getarray TMP 10 x
>
>                 if HASH == TMP
>
>                     getarray NAME 11 x
>
>                     break
>
>                 endif
>
>             next x
>
>         endif
>
> 
>
>         if OFFSET != 0
>
>             savepos TMP
>
>             goto OFFSET
>
>             get SIZE longlong
>
>             get DUMMY longlong
>
>             get ZSIZE longlong
>
>             get CHUNK_SIZE long
>
>             get ALGO short  # 0:no_chunks, 4:oodle
>
>             get DUMMY short # ???
>
> 
>
>             if ALGO == 0
>
>                 savepos OFFSET
>
>                 log NAME OFFSET SIZE
>
> 
>
>             elif ALGO == 4
>
>                 putvarchr MEMORY_FILE SIZE 0
>
>                 log MEMORY_FILE 0 0
>
>                 xmath CHUNKS "SIZE / CHUNK_SIZE"
>
>                 if SIZE % CHUNK_SIZE
>
>                     math CHUNKS + 1
>
>                 endif
>
>                 for x = 0 < CHUNKS
>
>                     get CHUNK_ZSIZE long
>
>                     putarray 0 x CHUNK_ZSIZE
>
>                 next x
>
>                 append
>
>                 for x = 0 < CHUNKS
>
>                     getarray CHUNK_ZSIZE 0 x
>
>                     savepos OFFSET
>
>                     get CHUNK_SIZE long
>
>                     math OFFSET      + 4
>
>                     math CHUNK_ZSIZE - 4
>
>                     clog MEMORY_FILE OFFSET CHUNK_ZSIZE CHUNK_SIZE
>
>                     goto CHUNK_ZSIZE 0 SEEK_CUR
>
>                 next x
>
>                 append
>
>                 log NAME 0 SIZE MEMORY_FILE
>
> 
>
>             else
>
>                 print "Error: unknown ALGO %ALGO% at offset %OFFSET|x%, contact me"
>
>                 cleanexit
>
>             endif
>
>             goto TMP
>
>         endif
>
>     next i
>
> 
>
>     goto NEXT_OFF
>
> while NEXT_OFF != 0
>
> endfunction
