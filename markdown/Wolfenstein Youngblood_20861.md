## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-07-26T17:52:58+00:00
- Post Title: Wolfenstein Youngblood

I tried wolfenstein2 script but it doesn't work. Anyone can take a look and improve it somehow? it uses oodle as well.

Error: the variable index is invalid, there is an error in this tool

```
# script for QuickBMS http://quickbms.aluigi.org

comtype oodle

get EXT extension
if EXT == "texdb"

    print "Error: %EXT% is no longer supported: sorting arrays takes forever and the data seems obfuscated or useless"
    cleanexit

    callfunction NEED_64 1

    getdstring DUMMY 0x18
    get FILES longlong
    for i = 0 < FILES
        get SOME_CRC longlong
        get OFFSET longlong
        putarray 0 i OFFSET
    next i

        get OFFSET asize
        putarray 0 i OFFSET

    print "sorting array, wait some minutes..."
    sortarray 0

    for i = 0 < FILES
        getarray OFFSET 0 i
        math i + 1
        getarray SIZE   0 i
        math SIZE - OFFSET
        log "" OFFSET SIZE
    next

else
    # .resources, .pack and so on

    idstring "IDCL"
    get VER long  # 12
    get DUMMY longlong
    get ZERO long
    get DUMMY long  # 1
    get DUMMY long  # -1
    get DUMMY long
    get DUMMY longlong
    get FILES long
    get DUMMY_NUM long
    get DUMMY2_NUM long
    get FILES_2 long
    get ZERO longlong
    get DUMMY2 longlong
    get NAMES_OFF longlong
    get DUMMY4_OFF longlong
    get INFO_OFF longlong
    get DUMMY6_OFF longlong
    get DUMMY7_OFF longlong
    get DATA_OFF longlong

    goto NAMES_OFF
    get NAMES longlong
    for i = 0 < NAMES
        get NAME_OFF longlong
        putarray 0 i NAME_OFF
    next i
    savepos NAMES_OFF
    for i = 0 < NAMES
        getarray NAME_OFF 0 i
        math NAME_OFF + NAMES_OFF
        goto NAME_OFF
        get NAME string
        string NAME % "$"
        string NAME | "#"
        putarray 0 i NAME
    next i

    # thanks toxic72 https://zenhax.com/viewtopic.php?p=27774#p27774
    goto DUMMY7_OFF
    for i = 0 < DUMMY2_NUM
        get DUMMY long
    next i
    savepos DUMMY7_OFF

    goto INFO_OFF
    for i = 0 < FILES
        get ZERO longlong
        get DUMMY longlong      # 1
        get DUMMY longlong      # -1
        get TYPE_ID longlong
        get NAME_ID longlong
        get ZERO longlong
        get ZERO longlong
        get OFFSET longlong
        get ZSIZE longlong
        get SIZE longlong
        get DUMMY longlong  
        get DUMMY long
        get DUMMY long
        get DUMMY longlong

        get DUMMY long          # ZIP related?
        get DUMMY long          # ZIP related?
        get ZIP_FLAGS longlong  # 0, 2, 4, 0x210002, 0x410002 and so on
        get ZERO longlong
        get FLAGS long          # 2
        get FLAGS2 long
        get ZERO longlong

        math TYPE_ID * 8
        math TYPE_ID + DUMMY7_OFF
        math NAME_ID + 1
        math NAME_ID * 8
        math NAME_ID + DUMMY7_OFF
        savepos TMP
        goto TYPE_ID
        get TYPE_ID longlong
        goto NAME_ID
        get NAME_ID longlong
        goto TMP
        getarray STR1 0 TYPE_ID
        getarray STR2 0 NAME_ID
        string NAME p "%s/%s" STR1 STR2

        if SIZE == ZSIZE
            log NAME OFFSET SIZE
        else
            if ZIP_FLAGS & 4
                math OFFSET + 12
                math ZSIZE  - 12
            endif
            clog NAME OFFSET ZSIZE SIZE
        endif
    next i

endif

startfunction NEED_64
    math TMP = 0x10000000
    math TMP * 16
    if TMP == 0
        print "you must use quickbms_4gb_files.exe with big archives"
        cleanexit
    endif
endfunction

```
## Post #2
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-07-27T01:06:32+00:00
- Post Title: Wolfenstein Youngblood

> Reply from OrangeC ↑Sat Jul 27, 2019 1:52 am at Sat Jul 27, 2019 1:52 am
>
> Anyone can take a look and improve it somehow?
If Luigi is the creator of the script then maybe posting the error about it on ZENHAX might help.
