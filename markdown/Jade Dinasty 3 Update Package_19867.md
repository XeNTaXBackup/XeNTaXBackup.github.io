## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2019-03-27T11:48:36+00:00
- Post Title: Jade Dinasty 3 Update Package

Hello guys, well today I try collect some information about angelica package and got file was change because can't use script updated by aluigi, maybe somebody can take a look this new samples and update script? would be grateful if can help, thanks a lot for all.



```
# script for QuickBMS http://quickbms.aluigi.org

comtype zlib_noerror
goto -16
math INFO_ZSIZE = 0
get TEST1 long
get TEST2 long  # no, the "\x42\xc1\x5d\xa7" magic is not constant, it can be anything or just zero
get FILES long
get FLAG1 short
get FLAG2 short

# FLAG 3.2 is used for both compressed and non compressed info! so let's guess it
if TEST1 != 0 && TEST2 != 0
    math INFO_ZSIZE = TEST2
elif TEST2 u< 0x1000000  # ???
    math INFO_ZSIZE = TEST2
endif

findloc TAIL_OFFSET string "Angelica File Package" 0 "" 0
if TAIL_OFFSET == ""
    print "Error: no magic 2 string found"
    cleanexit
endif

if FLAG2 <= 1
    math TAIL_OFFSET - 4
    goto TAIL_OFFSET
    get INFO_OFF long
else
    math TAIL_OFFSET - 12
    goto TAIL_OFFSET
    if FLAG1 <= 2 || INFO_ZSIZE != 0
        get FLAG long
        get INFO_OFF long
        math INFO_OFF ^ 0x62A4F9E1
    else
        get INFO_OFF long
        math INFO_OFF ^ 0x33C3EDDB

        get INFO_OFF64 long
        math INFO_OFF64 ^ 0x49ab7f1d
        if INFO_OFF64 != 0
            math INFO_OFF64 u<< 32
            math INFO_OFF + INFO_OFF64
        endif
    endif
    get ZERO long
endif

idstring "Angelica File Package"

if INFO_ZSIZE == 0
    xmath TMP "TAIL_OFFSET - INFO_OFF"
    log MEMORY_FILE10 INFO_OFF TMP
else
    clog MEMORY_FILE INFO_OFF INFO_ZSIZE INFO_ZSIZE
endif
for i = 0 < FILES
    if FLAG2 <= 1
        get NAMESZ long MEMORY_FILE10
        getdstring NAME NAMESZ MEMORY_FILE10
        get OFFSET long MEMORY_FILE10
        get SIZE long MEMORY_FILE10
        get ZSIZE long MEMORY_FILE10
    else
        if INFO_ZSIZE == 0
            get HEAD long MEMORY_FILE10
            math HEAD ^ 0x62A4F9E1
            get FOOT long MEMORY_FILE10
            math FOOT ^ 0x3520C3D5

            savepos TMP MEMORY_FILE10
            get ZERO long MEMORY_FILE10
            if ZERO != 0
                goto TMP MEMORY_FILE10
            else
                math HEAD - 4
            endif

            savepos INFO_OFF MEMORY_FILE10
            clog MEMORY_FILE INFO_OFF HEAD 0x118 MEMORY_FILE10
            math INFO_OFF + HEAD
            goto INFO_OFF MEMORY_FILE10
        endif

        getdstring NAME 260 MEMORY_FILE
        get OFFSET long  MEMORY_FILE
        get XSIZE long MEMORY_FILE
        get SIZE long MEMORY_FILE
        get ZSIZE long MEMORY_FILE
        if ZSIZE == 0   # some archives are different?!
            math ZSIZE = SIZE
            math SIZE = XSIZE
        endif
    endif

    if ZSIZE == SIZE
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i

```


Samples

[https://www.mediafire.com/file/g67fhyr8 ... te.7z/file](https://www.mediafire.com/file/g67fhyr8k7k2bxm/Jade_Dinasty_3_pck_update.7z/file)

Full File

[https://www.mediafire.com/file/z57o69fn ... ck.7z/file](https://www.mediafire.com/file/z57o69fnpifr3vb/Jade_Dinasty_3_models.pck.7z/file)
