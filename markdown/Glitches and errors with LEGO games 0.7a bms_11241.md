## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2014-02-22T16:29:39+00:00
- Post Title: Glitches and errors with LEGO games 0.7a bms

All in one thread it's better   

But 1rst..

PS:
@Kaoskrew I KNOW you found this bms after my first post (2 days ago) and used, give credits to ALUIGI, you LAMERS, give RESPECT to the REAL authors.
What a bounch of idiots....(This "team" usually "rips" or recode games stealing tools from other people, what a pathetic.. I KNOW you are making money with your rips with the info from this site)
--
Hi!

I used this bms

```
#  Lego Movie: The Video Game
#  LEGO Batman 1
#  LEGO Batman 2
#  LEGO Star Wars
#  LEGO Star Wars III
#  LEGO Indiana Jones
#  LEGO Harry Potter
#  LEGO Pirates of the Caribbean
#  LEGO Lord of the Rings
#  Transformers
#  others, check them on http://www.ttgames.com
#
# in case of problems with the extraction try setting NAMELESS to 1
# thanx to who fixed the handling of the names!
#
# script for QuickBMS http://quickbms.aluigi.org

quickbmsver "0.5.16c"
set NAMELESS long 0 # set to 1 to extract the files without names

getdstring SIGN 4
goto 0
math ONE_FILE = 0
if SIGN == "LZ2K"
    math ONE_FILE = 1
elif SIGN == "DFLT"
    math ONE_FILE = 1
endif
if ONE_FILE != 0
    math OFFSET = 0
    get ZSIZE asize
    math SIZE = ZSIZE
    callfunction UNPACK
    log "" 0 SIZE MEMORY_FILE2
    cleanexit
endif

get HDR_NAME basename
string HDR_NAME += ".hdr"
open FDSE HDR_NAME 1 EXISTS

if EXISTS != 0
    get NAME filename
    if NAME == HDR_NAME
        get NAME basename
        string NAME += ".dat"
        open FDSE NAME
    endif
    get HDR_SIZE asize 1
    log MEMORY_FILE 0 HDR_SIZE 1
    get DUMMY long MEMORY_FILE
else
    get INFO_OFF long
    if INFO_OFF & 0x80000000
        math INFO_OFF ^= 0xffffffff
        math INFO_OFF <<= 8
        math INFO_OFF += 0x100
    endif
    get INFO_SIZE long
    log MEMORY_FILE INFO_OFF INFO_SIZE
endif

get TYPE_BOH long MEMORY_FILE
get FILES long MEMORY_FILE
savepos INFO_OFF MEMORY_FILE

math TMP = FILES
math TMP *= 16
math NAME_INFO = INFO_OFF
math NAME_INFO += TMP

goto NAME_INFO MEMORY_FILE
get NAMES long MEMORY_FILE
savepos NAME_INFO MEMORY_FILE

math NAME_FIELD_SIZE = 8
if TYPE_BOH <= 0xfffffffb
    math NAME_FIELD_SIZE = 12
endif

math TMP = NAMES
math TMP *= NAME_FIELD_SIZE
math NAME_OFF = NAME_INFO
math NAME_OFF += TMP

goto NAME_OFF MEMORY_FILE
get NAMECRC_OFF long MEMORY_FILE
savepos NAME_OFF MEMORY_FILE

math NAMECRC_OFF += NAME_OFF
goto NAMECRC_OFF MEMORY_FILE
for i = 0 < FILES
    get CRC long MEMORY_FILE
    putarray 0 i CRC
next i

if TYPE_BOH <= -2
    get DUMMY1 long MEMORY_FILE
    get DUMMY2 long MEMORY_FILE
    if DUMMY1 > 0
        print "Error: positive DUMMY1 not implemented yet, contact me"
        cleanexit
    endif
endif

# print "files:       %FILES%"
# print "names:       %NAMES%"
# print "info_off:    %INFO_OFF%"
# print "info_size:   %INFO_SIZE%"
# print "name_info:   %NAME_INFO%"
# print "name_off:    %NAME_OFF%"
# print "namecrc_off: %NAMECRC_OFF%"

set NAMEZ long 0
set FULLNAME string ""
set FULLPATH string ""

for i = 0 < FILES
    do
        goto NAME_INFO MEMORY_FILE
        get NEXT short MEMORY_FILE
        get PREV short MEMORY_FILE
        get OFF long MEMORY_FILE
        if TYPE_BOH <= 0xfffffffb   # if NAME_FIELD_SIZE >= 12
            get DUMMY long MEMORY_FILE
        endif
        savepos NAME_INFO MEMORY_FILE

        math OFF += NAME_OFF
        goto OFF MEMORY_FILE
        get NAME string MEMORY_FILE

		# used only for LEGO the game if you don't use the hdr file
		getvarchr TMP0 NAME 0
		if TMP0 >= 0xf0
			set NAME string ""
		endif
        #string NAME u= NAME # needed for the crc check, but doesn't improve performances so much

        if NEXT & 0x8000    # 16bit sign conversion
            math NEXT |= -0x10000
        endif

        if PREV != 0
            getarray FULLPATH 1 PREV
        endif
        putarray 1 NAMEZ FULLPATH   # putarray 1 NAMEZ NAME
        if NEXT > 0 # folder
            getarray TMP 1 PREV
            if TMP != ""    # long story to avoid things like 2foldername that gives problems to QuickBMS
                set OLDNAME string \    # do not use /
                string OLDNAME += TMP
                string OLDNAME += \     # do not use /
                string FULLPATH >>= OLDNAME
            endif
            if NAME != ""
            #    string FULLPATH += \    # do not use /
                string FULLPATH += NAME
                string FULLPATH += \    # do not use /
            endif
        endif
        math NAMEZ += 1
    while NEXT > 0
    set FULLNAME string FULLPATH
    string FULLNAME += NAME

	getvarchr TMP0 FULLNAME 0
	if TMP0 == '\\'
		string FULLNAME <<= 1
	endif
	
    if NAMELESS == 0
        math CRC = 0x811c9dc5
        strlen NAMESZ FULLNAME
        for j = 0 < NAMESZ
            getvarchr CHR FULLNAME j
            if CHR >= 0x61
                if CHR <= 0x7a
                    math CHR -= 0x20
                endif
            endif
            #if CHR == 0x2f      # /
            #    math CHR = 0x5c # \
            #endif
            math CRC ^= CHR
            math CRC *= 0x199933
        next j
        math CRC &= 0xffffffff
        for j = 0 < FILES
            getarray TMP 0 j
            if CRC == TMP
                break
            endif
        next j
        if j >= FILES
            print "Alert: the crc of the file %FULLNAME% has not been found, I extract the current file"
            #cleanexit
            # all wrongs!
            math j = i
            #math TMP = NEXT
            #math j = 0
            #math j -= NEXT
            #math j -= 1
        endif
        math TMP = j
    else
        math TMP = i
        set FULLNAME string ""
    endif

    math TMP *= 16
    math TMP += INFO_OFF
    goto TMP MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get ZSIZE long MEMORY_FILE
    get SIZE long MEMORY_FILE
    get PACKED threebyte MEMORY_FILE
    get OFFSET2 byte MEMORY_FILE
    math OFFSET <<= 8
    math OFFSET += OFFSET2

    goto OFFSET
    getdstring SIGN 4
    if SIGN == "LZ2K"
        set PACKED long 2
    elif SIGN == "DFLT"
        set PACKED long 3
    else
        set PACKED long 0
    endif

    if PACKED & 2   # includes both 2 and 3
        callfunction UNPACK
        log FULLNAME 0 SIZE MEMORY_FILE2
    else
        if SIZE  != 0
        if ZSIZE != 0
        if SIZE  != ZSIZE
            print "SIZE (%SIZE%) and ZSIZE (%ZSIZE%) differ at offset %OFFSET|x%, contact me"
            cleanexit
        endif
        endif
        endif
        log FULLNAME OFFSET SIZE
    endif
next i


startfunction UNPACK
    putvarchr MEMORY_FILE2 SIZE 0
    log MEMORY_FILE2 0 0
    append
    for TMPSZ = 0 < ZSIZE
        goto OFFSET
        getdstring SIGN 4
        if SIGN == "LZ2K"
            comtype lz2k
            get CHUNK_SIZE long
            get CHUNK_ZSIZE long
        elif SIGN == "DFLT"
            comtype dflt
            get CHUNK_ZSIZE long
            get CHUNK_SIZE long
        else
            print "Error: the signature at offset %OFFSET% (%SIGN%) is not LZ2K, contact me"
            cleanexit
        endif
        savepos OFFSET
        if CHUNK_ZSIZE == CHUNK_SIZE
            log MEMORY_FILE2 OFFSET CHUNK_SIZE
        else
            clog MEMORY_FILE2 OFFSET CHUNK_ZSIZE CHUNK_SIZE
        endif
        math OFFSET += CHUNK_ZSIZE
        savepos TMP MEMORY_FILE2
        math TMPSZ += 12
        math TMPSZ += CHUNK_ZSIZE
    next
    append
endfunction

```


This is the games are not working or working bad:

Lego Batman 2: Wont' start, crashes to desktop
Lord of The rings: Wont' start, crashes to desktop
Harry Potter years 1-4: 1st you need to check if your Audio Card is configured, if the game crashes with the original files you need to do this:
[http://forums.steampowered.com/forums/s ... p=34238373](http://forums.steampowered.com/forums/showthread.php?p=34238373)

> Hello.
>
> 
>
> Here's how to fix the issue for immediate crashes to the Desktop when starting Lego Harry Potter: Years 1-4:
>
> 
>
> Windows XP:
>
> 1. Open your sound cards control panel, and set the sampling frequency to 48 KHz or 44.1 KHz.
>
> 2. It's fixed
>
> 
>
> Windows Vista / Windows 7:
>
> 1. Open your sound cards control panel, and set the sampling frequency to 48 KHz or 44.1 KHz.
>
> 2. Rightclick the speaker icon in the notification area of your start bar (also known as the systray area). Select playback devices.
>
> 3. Doubleclick your playback device.
>
> 4. Go to advanced.
>
> 5. Set the sampling frequency to either:
>
> 24 bit, 48000 Hz
>
> 16 bit, 48000 Hz
>
> 24 bit, 44100 Hz
>
> 16 bit, 44100 Hz
>
> 6. It's fixed.
>
> 
>
> Obviously you should revert both settings back to the highest possible value when you are done playing, otherwise your sound quality will be decreased.
>
> 
>
> This game is a terrible port from the XBox 360, and can't deal with any sampling frequency setting above 48 KHz. :
If you can play then unpack the data.
Now the "glitch": Harry's legs are not moving  looks is missing some data.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-02-24T11:52:22+00:00
- Post Title: Glitches and errors with LEGO games 0.7a bms

Do you mean that the games don't work after you extract the files and remove (or leave there) the original archives?

If that's the case I suggest this simple test, comment the 2 commands executed "if PACKED & 2" so that you will extract only the non-compressed files and check if the games continue to crash:

```
        #log FULLNAME 0 SIZE MEMORY_FILE2
```


In LEGO The Movie (PS3 tested) unfortunately the last chunk of the files compressed with the DFLT algorithm causes a crash of quickbms due to some invalid datas, I still don't know if it's a slightly modified algorithm or some sort of obfuscation added to these last chunk to avoid the decompression of the files.

In my opinion the DFLT algorithm I use is correct but this is strange.
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2014-02-24T13:54:03+00:00
- Post Title: Glitches and errors with LEGO games 0.7a bms

Thanks for the answer Aluigi, this is what i did with LEGO BATMAN 2

-Modified the bms as you said
-Extracted the data
-Moved the files .dat to another folder
-Run the game
-Still crashing  

LEGO The Movie in PC works great with the files unpacked
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-02-24T15:44:58+00:00
- Post Title: Glitches and errors with LEGO games 0.7a bms

in this case we can exclude problems with the decompression, additionally the filenames are checksummed so we are sure that the extracted names are correct.
