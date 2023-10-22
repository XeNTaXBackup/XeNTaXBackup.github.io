## Post #1
- Username: qscrgn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 26, 2015 11:19 pm
- Post datetime: 2017-09-27T11:21:24+00:00
- Post Title: [HELP] Lineage 2 Revolution

Hello everybody,
I'm trying to open this data pak of Lineage 2 Revolution but a key is required.
I have understood that libUE4 is directly implicated in the opening of the file.

Here you can find both the download.
Full Data: [https://mega.nz/#!nN9gFZRZ!60-vJhhZvwxw ... jLxP1b3L-8](https://mega.nz/#!nN9gFZRZ!60-vJhhZvwxwm3Iv6unrTLff5EjkaFna8jLxP1b3L-8)
LibUE4: [https://mega.nz/#!jUtQTJDB!oW-bVF3eEsb1 ... nyiObHuitM](https://mega.nz/#!jUtQTJDB!oW-bVF3eEsb1f66ft9wUlzd6rjFb_sZEsnyiObHuitM)

Thank you everybody for the help you'll provide.
## Post #2
- Username: qscrgn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 26, 2015 11:19 pm
- Post datetime: 2017-09-27T11:28:19+00:00
- Post Title: [HELP] Lineage 2 Revolution

Solved with this modified version of Unreal Tournament script by Ekey and Aluigi

```
# script for QuickBMS http://quickbms.aluigi.org

# set your AES_KEY here as text or C string ("\x11\x22...")
set AES_KEY binary ""
putarray 10 -1 "KIWIKIWIKIWIKIWIKIWIKIWIKIWIKIWI"   # first beta of Street Fighter V
putarray 10 -1 "_aS4mfZK8M5s5KWC2Lz2VsFnGKI7azgl"   # current version of Street Fighter V
putarray 10 -1 "bR!@nbR0wnc@rychR!$d@nd@v3d3R3kj!mj0$hk3v!nm!ch@3lm!k3s3@nst3v3t!m" # Victory: The Culling
putarray 10 -1 "casd#55@#$%323!$^#b%05sa5W|hhaf4365s52ss51|55m!|{55s^@@36f233|-|0w@%3g8hssDk35/!Nm|_|%ds23%a32d5&23as3%12p|-|y$t3ds562d23fav3c@dyw38#49" # Victory: The Culling
putarray 10 -1 "C8C4847F3B4FA52D4AAD57A52358CDBC"   # Injustice 2 (iOS)
putarray 10 -1 "k14z0ZLR8a7jNm49uyBzxXYY9LpTHcehLSNiC3jAkzBsffPuy8YsTa72RLD9KWIn"   # Gal*Gun VR
putarray 10 -1 ""
math AES_KEY_IS_SET = 0

math ALTERNATIVE_MODE = 0

# 1 = HIT
math WORKAROUND = 0

goto -0x2c
get MAGIC long  #idstring "\xe1\x12\x6f\x5a" # 0x5a6f12e1
if MAGIC == 0x5a6f12e1
    # ok
elif MAGIC == 0xe1126f5a
    endian big
else
    # HIT game 0x1233a
    math WORKAROUND = 1
endif
get VERSION long
get OFFSET longlong
get SIZE longlong
getdstring HASH 20
if WORKAROUND == 1
    math VERSION = 3
endif

goto OFFSET
callfunction GET_NAME 1

if ALTERNATIVE_MODE == 0
    get FILES long
else
    math FILES = 0x7fffffff
    math MAX_OFF = OFFSET
    goto 0
    set NAME string ""
endif

math CHUNK_SIZE = 0x10000   # just in case...
for i = 0 < FILES
    if ALTERNATIVE_MODE == 0
        callfunction GET_NAME 1
    endif
    savepos TMP_OFF

    get OFFSET longlong
    get ZSIZE longlong
    get SIZE longlong
    get ZIP long
    if WORKAROUND == 1
        getdstring HASH 20
    elif VERSION <= 1
        get TSTAMP longlong
    endif
    getdstring HASH 20
    math CHUNKS = 0
    math ENCRYPTED = 0
    if VERSION >= 3
        if ZIP != 0
            get CHUNKS long
            for x = 0 < CHUNKS
                get CHUNK_OFFSET longlong
                get CHUNK_END_OFFSET longlong
                putarray 0 x CHUNK_OFFSET
                putarray 1 x CHUNK_END_OFFSET
            next x
        endif
        get ENCRYPTED_ byte
        get CHUNK_SIZE long
    endif
    if WORKAROUND == 1
        math ENCRYPTED = 0
    endif
    if ALTERNATIVE_MODE != 0
        savepos TMP_OFF
        math OFFSET + TMP_OFF
    endif

    comtype copy    # for AES
      if ZIP & 1
        comtype zlib
    elif ZIP & 2
        comtype gzip
    elif ZIP & 4
        comtype snappy
    elif ZIP & 0x10
        comtype oodle
    endif

    if CHUNKS > 0
        putvarchr MEMORY_FILE SIZE 0
        log MEMORY_FILE 0 0
        append
        math TMP_SIZE = SIZE
        for x = 0 < CHUNKS
            getarray CHUNK_OFFSET 0 x
            getarray CHUNK_END_OFFSET 1 x
            math CHUNK_ZSIZE = CHUNK_END_OFFSET
            math CHUNK_ZSIZE - CHUNK_OFFSET
            if ENCRYPTED != 0
                callfunction SET_AES_KEY 1
                math CHUNK_ZSIZE x 16
            endif
            if TMP_SIZE u< CHUNK_SIZE
                math CHUNK_SIZE = TMP_SIZE
            endif
            clog MEMORY_FILE CHUNK_OFFSET CHUNK_ZSIZE CHUNK_SIZE
            math TMP_SIZE - CHUNK_SIZE
        next x
        append
        encryption "" ""
        log NAME 0 SIZE MEMORY_FILE
    else
        # the file offset points to an entry containing
        # the "same" OFFSET ZSIZE SIZE ZIP HASH ZERO fields,
        # just an additional backup... so let's skip them
        savepos BASE_OFF
        math BASE_OFF - TMP_OFF
        math OFFSET + BASE_OFF
        if ENCRYPTED != 0
            callfunction SET_AES_KEY 1
            math ZSIZE x 16
        endif
        clog NAME OFFSET ZSIZE SIZE
        encryption "" ""
    endif

    if ALTERNATIVE_MODE != 0
        math OFFSET + ZSIZE
        goto OFFSET
        if OFFSET == MAX_OFF
            break
        endif
        if VERSION >= 4
            padding 0x800   # necessary for WitchIt
        endif
    endif
next i

startfunction SET_AES_KEY_ASK
    math AES_KEY_IS_SET = 1
    print "The archive is encrypted, select the number of the key to use or type yours:"
    for z = 0
        getarray KEY 10 z
        if KEY == ""
            break
        endif
        print "%z%: %KEY%"
    next z
        print "%z%: press RETURN for no encryption (Lineage 2 Revolution)"
    set KEY unknown "???"
    strlen TMP KEY
    if KEY == ""
        math AES_KEY_IS_SET = -1
        set AES_KEY string "no key, encryption disabled"
    elif TMP <= 2
        getarray AES_KEY 10 KEY
    else
        set AES_KEY binary KEY
    endif
    print "KEY: %AES_KEY%"
endfunction

startfunction SET_AES_KEY
    if AES_KEY_IS_SET == 0
        callfunction SET_AES_KEY_ASK 1
    endif
    if AES_KEY_IS_SET > 0
        encryption aes AES_KEY "" 0 32
    endif
endfunction

startfunction GET_NAME
    get NAMESZ signed_long
    if NAMESZ >= 0
        if NAMESZ > 0x200
            math ALTERNATIVE_MODE = 1
        else
            getdstring NAME NAMESZ
        endif
    else
        math NAMESZ n NAMESZ
        if NAMESZ > 0x200
            math ALTERNATIVE_MODE = 1
        else
            math NAMESZ * 2
            getdstring NAME NAMESZ
            set NAME unicode NAME
        endif
    endif
endfunction

```
## Post #3
- Username: abedy
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Aug 29, 2015 3:03 am
- Post datetime: 2017-09-29T19:33:37+00:00
- Post Title: [HELP] Lineage 2 Revolution

Unpack script works fine however csv data are still encrypted when extracted. Could any of you guys have a look and see if you can help with decrypt.

Script example
[http://www46.zippyshare.com/v/Knnuse0X/file.html](http://www46.zippyshare.com/v/Knnuse0X/file.html)


many thanks
