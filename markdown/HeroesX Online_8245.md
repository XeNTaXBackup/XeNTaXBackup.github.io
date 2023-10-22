## Post #1
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-02-10T11:04:39+00:00
- Post Title: HeroesX Online

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-10T11:58:03+00:00
- Post Title: HeroesX Online

the fomrat looks fairly easy do you have one more sample just so i can confirm th estarting header.
## Post #3
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-02-10T12:31:20+00:00
- Post Title: HeroesX Online

> Reply from chrrox
>
> the fomrat looks fairly easy do you have one more sample just so i can confirm th estarting header.

sample:

[http://www.mediafire.com/?z9dqzprwws6sg ... 3e23vje1qf](http://www.mediafire.com/?z9dqzprwws6sg5z,iry7m87q4s8sjnq,zq0t3na8taxm3ao,if2dd3e23vje1qf)
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-10T12:38:55+00:00
- Post Title: HeroesX Online

```
# script for QuickBMS http://quickbms.aluigi.org

comtype deflate
idstring "LTAR"
get VERSION long

# it's possible to make the check on the version or using this solution
savepos TMP
get FULL_SIZE asize
get DUMMY1 long
get DUMMY2 long
math AUTOGUESS = 0
if DUMMY1 u> FULL_SIZE
    math AUTOGUESS = 1
endif
if DUMMY2 u> FULL_SIZE
    math AUTOGUESS = 1
endif
goto TMP
if AUTOGUESS == 0
    get NAMESSZ long
    get FOLDERS long
    get FILES long
    get DUMMY long      # 1
    get DUMMY long      # 0
    get DUMMY long      # 0
    getdstring HASH 16
else
    getdstring HASH 16
    get DUMMY long      # 1
    get DUMMY long      # 0
    get DUMMY long      # 0
    get FILES long
    get FOLDERS long
    get NAMESSZ long
endif

savepos OFFSET
log MEMORY_FILE OFFSET NAMESSZ

math OFFSET += NAMESSZ
set FILESSZ long FILES
math FILESSZ *= 32
log MEMORY_FILE2 OFFSET FILESSZ

math OFFSET += FILESSZ
set FOLDERSSZ long FOLDERS
math FOLDERSSZ *= 16
log MEMORY_FILE3 OFFSET FOLDERSSZ

set FOLDER string ""
callfunction EXTRACT

startfunction EXTRACT
    savepos CURR_OFF MEMORY_FILE3
    if CURR_OFF >= FOLDERSSZ
        cleanexit
    endif
    get NAME_OFF long MEMORY_FILE3
    get SUB_FOLDERS long MEMORY_FILE3
    get NEXT_FOLDERS long MEMORY_FILE3
    get NUM_FILES long MEMORY_FILE3

    goto NAME_OFF MEMORY_FILE
    get NAME string MEMORY_FILE

    # don't have the minimal idea if it's correct, it's an update of the old script
    if AUTOGUESS == 0
        string FOLDER = NAME
    else
        string FOLDER += NAME
    endif
    string FOLDER += /

    for i = 0 < NUM_FILES
        savepos CURR_OFF MEMORY_FILE2
        if CURR_OFF >= FILESSZ
            cleanexit
        endif
        get NAME_OFF long MEMORY_FILE2
        get OFFSET  longlong MEMORY_FILE2
        get ZSIZE   longlong MEMORY_FILE2
        get SIZE    longlong MEMORY_FILE2
        get ZIP     long MEMORY_FILE2

        goto NAME_OFF MEMORY_FILE
        get NAME string MEMORY_FILE

        if FOLDER != "CRC/" # they are not files
            set FNAME string FOLDER
            string FNAME += NAME
            if ZIP == 0
                log FNAME OFFSET SIZE
            else
                # compression 9
                callfunction ZIP_DUMP 1 # 1 only for being faster
            endif
        endif
    next i

    for i = 0 < SUB_FOLDERS
        callfunction EXTRACT
    next i

    set FOLDER string ""
    for i = 0 < NEXT_FOLDERS
        callfunction EXTRACT
    next i
endfunction

startfunction ZIP_DUMP
    log MEMORY_FILE4 0 0
    append
    for j = 0 < SIZE
        math TMP = OFFSET
        math TMP += j
        goto TMP
        get CHUNK_ZSIZE long
        get CHUNK_SIZE long
        savepos TMP
        if CHUNK_ZSIZE == CHUNK_SIZE
            log MEMORY_FILE4 TMP CHUNK_SIZE
        else
            clog MEMORY_FILE4 TMP CHUNK_ZSIZE CHUNK_SIZE
        endif
        math j += 8
        math j += CHUNK_ZSIZE
        math j x= 4
    next
    append
    get SIZE asize MEMORY_FILE4
    log FNAME 0 SIZE MEMORY_FILE4
endfunction
```


Work fine
