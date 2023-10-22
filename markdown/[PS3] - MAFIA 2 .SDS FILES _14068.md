## Post #1
- Username: Scofield
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Jul 13, 2014 5:27 am
- Post datetime: 2016-03-09T12:46:28+00:00
- Post Title: [PS3] - MAFIA 2 .SDS FILES ?

Hi friends and @michalss , @Mr.Mouse , @Gh0stBlade , @WRS

How are you ? 

I need your help with something. Mafia 2 .sds extractor programs have made.
I can not get the PS3 file. 

[viewtopic.php?p=99507#p99507](http://forum.xentax.com/viewtopic.php?p=99507#p99507)

Please type the program will extract this file and will re-import.

Sorry, my little english.

Example File: [http://rghost.net/7wyBS6WCY](http://rghost.net/7wyBS6WCY)

I'm waiting for your answer.

Thanks.
## Post #2
- Username: ferex
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 04, 2015 6:06 am
- Post datetime: 2016-03-15T11:57:18+00:00
- Post Title: [PS3] - MAFIA 2 .SDS FILES ?

> Reply from Scofield
>
> Hi friends and @michalss , @Mr.Mouse , @Gh0stBlade , @WRS

How are you ? 

I need your help with something. Mafia 2 .sds extractor programs have made.
I can not get the PS3 file. 

viewtopic.php?p=99507#p99507

Please type the program will extract this file and will re-import.

Sorry, my little english.

Example File: http://rghost.net/7wyBS6WCY

I'm waiting for your answer.

Thanks.
Quick bms ile bu kodla açarsın

> # Mafia SDS PS3
>
> # script for QuickBMS http://quickbms.aluigi.org
>
> 
>
> endian big
>
> idstring "SDS\0"
>
> get DUMMY long  # 0x13
>
> endian guess DUMMY  # maybe other games can be supported
>
> idstring "PS3\0"
>
> get DUMMY long
>
> get OFFSET1 long
>
> get OFFSET2 long
>
> get XML_OFFSET long
>
> get DUMMY long
>
> get DUMMY long
>
> goto OFFSET2
>
> getdstring DUMMY 4  # "lzEU"?
>
> get CHUNK_SIZE long
>
> get DUMMY byte  # 4
>
> savepos OFFSET
>
> log MEMORY_FILE 0 0
>
> for OFFSET = OFFSET != XML_OFFSET
>
>     get DUMMY1 long
>
>     get DUMMY2 byte
>
>     if DUMMY1 == 0 && DUMMY2 == 0
>
>         break
>
>     endif
>
>     get SIZE long
>
>     get DUMMY long
>
>     get CHUNK_SIZE short
>
>     get CHUNKS short
>
>     get DUMMY long
>
>     math TMP = CHUNKS
>
>     math TMP * 2
>
>     math TMP x 16
>
>     savepos OFFSET
>
>     math OFFSET + TMP    
>
>     append
>
>     for x = 0 < CHUNKS
>
>         get CHUNK_ZSIZE short
>
>         if CHUNK_ZSIZE == 0 || CHUNK_ZSIZE >= CHUNK_SIZE    # ??? not in my samples
>
>             log MEMORY_FILE OFFSET CHUNK_SIZE
>
>         else
>
>             clog MEMORY_FILE OFFSET CHUNK_ZSIZE CHUNK_SIZE
>
>         endif
>
>         math OFFSET + CHUNK_ZSIZE
>
>     next x
>
>     append
>
>     goto OFFSET
>
> next
>
> 
>
> get SIZE asize
>
> math SIZE - XML_OFFSET
>
> log MEMORY_FILE2 XML_OFFSET SIZE
>
> 
>
> get MEM_SIZE asize MEMORY_FILE
>
> goto 0 MEMORY_FILE
>
> for ENTRY_OFF = 0 != MEM_SIZE
>
>     savepos ENTRY_OFF MEMORY_FILE
>
>     get TYPE long MEMORY_FILE
>
>     get ENTRY_SIZE long MEMORY_FILE
>
>     get DUMMY short MEMORY_FILE
>
>     getdstring DUMMY 0x10 MEMORY_FILE
>
>     get CRC long MEMORY_FILE    # ???
>
> 
>
>     savepos OFFSET MEMORY_FILE
>
>     math ENTRY_OFF + ENTRY_SIZE
>
>     goto ENTRY_OFF MEMORY_FILE
>
> 
>
>     math SIZE = ENTRY_OFF
>
>     math SIZE - OFFSET
>
> 
>
>     findloc TMP string "<SourceDataDescription>" MEMORY_FILE2 ""
>
>     if TMP == ""
>
>         set NAME string ""
>
>     else
>
>         goto TMP MEMORY_FILE2
>
>         get NAME line MEMORY_FILE2
>
>         string NAME | ">"
>
>         string NAME >> "<"
>
>     endif
>
> 
>
>     set EXT extension NAME
>
>     if EXT == "dds"
>
>         math OFFSET + 10
>
>         math SIZE   - 10
>
>     endif
>
> 
>
>     log NAME OFFSET SIZE MEMORY_FILE
>
> next

açtıgında tables içindeki .dat dosyasının içindeki textler. dds dosyaları fotoshop dosyaları.Klasör şeklinde atsanda oyun açılır
