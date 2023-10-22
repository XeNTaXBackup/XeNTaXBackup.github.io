## Post #1
- Username: Xep76
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 14, 2010 5:57 pm
- Post datetime: 2010-07-03T04:18:55+00:00
- Post Title: Lego Harry Potter *.DAT

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-07-03T10:21:22+00:00
- Post Title: Lego Harry Potter *.DAT

the script works perfectly, the problem is ever that CRC stuff I talked about in the old main thread about this file format
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-07-03T10:32:12+00:00
- Post Title: Lego Harry Potter *.DAT

update: I'm reworking on the script, maybe I can do something so stay tuned
## Post #4
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-07-03T10:34:53+00:00
- Post Title: Lego Harry Potter *.DAT

> Reply from aluigi
>
> update: I'm reworking on the script, maybe I can do something so stay tuned

does the game work with unpacked? or ther dat must be still rebulid?
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-07-03T10:44:59+00:00
- Post Title: Lego Harry Potter *.DAT

I have updated the script adding a work-around that should work almost ever.
in case of problem set the NAMELESS var to 1 and it will not consider the names
[http://aluigi.org/papers/bms/ttgames.bms](http://aluigi.org/papers/bms/ttgames.bms)

I know nothing about the game for the loading of the free files or the archives
## Post #6
- Username: Xep76
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 14, 2010 5:57 pm
- Post datetime: 2010-07-03T12:15:50+00:00
- Post Title: Lego Harry Potter *.DAT

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-07-03T19:05:01+00:00
- Post Title: Lego Harry Potter *.DAT

I have fixed it anyway with NAMELESS disabled it will ever give problems because in some games (like LEGO Batman) the current file doesn't match the current filename so if the crc check fails then the file will be wrong.

in Lego Harry Potter the problem seems minor anyway for 100% good files it's necessary to set NAMELESS to 1 otherwise there will be dupicated files with different names and other that don't get extracted
## Post #8
- Username: Xep76
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 14, 2010 5:57 pm
- Post datetime: 2010-07-04T05:39:00+00:00
- Post Title: Lego Harry Potter *.DAT

aluigi Thank
Game Extractor - opened the archives!
.ogg - not work ((
## Post #9
- Username: lark125
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 10, 2010 6:08 pm
- Post datetime: 2010-12-03T21:08:41+00:00
- Post Title: Lego Harry Potter *.DAT

heey guess, 
doess anybody knows were i can get the biped of lego harry potter minifigs or (star wars)
## Post #10
- Username: RickyOs
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Nov 30, 2010 12:54 am
- Post datetime: 2010-12-07T12:15:39+00:00
- Post Title: Lego Harry Potter *.DAT

Hey,

I'am new to this topic (extract games), but I have a theory why some of
the files do not match the crc's:

1. Inside the archives there are folders that names starts with a number. 
2. The ttgames.bms script contains a "string shift" (>>=).
3. The QuickBMS-application looks only at the first char of a value
   to look up if it is a number or not.

Two examples: 
In LEGO Indiana Jones ([viewtopic.php?p=32603#p32603](http://forum.xentax.com/viewtopic.php?p=32603#p32603)):

> - SCRIPT's MESSAGE:
>
> Alert: the crc of the file "audio\_soundfx\1_ra2_td\water_fall_wheel_lp.wav" h
>
> as not been found, it can't be extracted!

Inside the archive there is a folder audio\_soundfx\1_ra\.
The script shifts back with 1_ra.
QuickBMS thinks it is a number (starts with 1) and only shifts 1 char away.
The temporary result path is audio\_soundfx\1_ra.
Now there comes the next subfolder 2_td.
The result becomes audio\_soundfx\1_ra2_td\ instead of audio\_soundfx\2_td\.
And this does not match the crc.

LEGO Star Wars The Complete Saga:

```
  CHARS\2_1B\2_1B.TXT
  CHARS\2_1B\2_1B_LR_PC.GHG
  CHARS\2_1B\2_1B_PC.GHG
- SCRIPT's MESSAGE:
  Alert: the crc of the file CHARS\2_14LOM\4LOM.TXT has not been found, it can't be extracted!
```


Inside the archive there is a folder CHARS\2_1B\.
The script shifts back with 2_1B.
QuickBMS thinks it is a number (starts with 2) and only shifts 2 chars away.
The temporary result path is CHARS\2_1.
Now there comes the next subfolder 4LOM.
The result becomes CHARS\2_14LOM\ instead of CHARS\4LOM\.
And this again does not match the crc.


I did not found an easy way to surround this, yet. But remember I am new to this and maybe one of yours knowes a workaround.
Thanks for the possibilities...
## Post #11
- Username: RickyOs
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Nov 30, 2010 12:54 am
- Post datetime: 2010-12-13T12:59:51+00:00
- Post Title: Lego Harry Potter *.DAT

Hey again,

I had a closer look to the game.dat from LEGO STAR WARS The Complete Saga and
the game.dat from LEGO Indiana Jones. 

After replacing

```
if NEXT > 0 # folder
    getarray OLDNAME 1 PREV
    string FULLPATH >>= OLDNAME
    if NAME != ""
        string FULLPATH += NAME
        string FULLPATH += \
    endif
endif
```


by

```
if NEXT > 0 # folder
    if PREV != 0
        getarray FULLPATH 1 PREV
    endif
    putarray 1 NAMEZ FULLPATH

    if NAME != ""
        string FULLPATH += NAME
        string FULLPATH += \
    endif
endif
```


in aluigi's ttgames.bms script the script runs for both games without crc-Error.
## Post #12
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-12-13T21:09:39+00:00
- Post Title: Lego Harry Potter *.DAT

> Reply from RickyOs
>
> Hey again,

I had a closer look to the game.dat from LEGO STAR WARS The Complete Saga and
the game.dat from LEGO Indiana Jones. 

After replacing
Code: Select allputarray 1 NAMEZ NAME
if NEXT > 0 # folder
    getarray OLDNAME 1 PREV
    string FULLPATH >>= OLDNAME
    if NAME != ""
        string FULLPATH += NAME
        string FULLPATH += \
    endif
endif

by
Code: Select allputarray 1 NAMEZ FULLPATH
if NEXT > 0 # folder
    if PREV != 0
        getarray FULLPATH 1 PREV
    endif
    putarray 1 NAMEZ FULLPATH

    if NAME != ""
        string FULLPATH += NAME
        string FULLPATH += \
    endif
endif

in aluigi's ttgames.bms script the script runs for both games without crc-Error.

Thank you!

EDIT: I'm still getting the CRC error. Could you post the script with your changes?
## Post #13
- Username: RickyOs
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Nov 30, 2010 12:54 am
- Post datetime: 2010-12-14T07:22:29+00:00
- Post Title: Lego Harry Potter *.DAT

I did not change version numbers or any comments.

```
#  LEGO Batman
#  LEGO Star Wars
#  LEGO Indiana Jones
#  LEGO Harry Potter
#  Transformers
#  others, check them on http://www.ttgames.com
#
# this script is a complete chaos... it's only a work-around since I didn't finish the research
# if you want all the files in PERFECT state you must set NAMELESS to 1
#
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

print "NOTE that this script is a work-around so will not work with all the files\nif you want to extract ALL the files without names (but they will be 100% corrects) edit this script setting NAMELESS to 1"

set NAMELESS long 0 # set to 1 to extract the files without names
comtype lz2k

get INFO_OFF long
if INFO_OFF & 0x80000000
    math INFO_OFF ^= 0xffffffff
    math INFO_OFF <<= 8
    math INFO_OFF += 0x100
endif
get INFO_SIZE long
log MEMORY_FILE INFO_OFF INFO_SIZE

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

math TMP = NAMES
math TMP *= 8
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
        #print "Error: not implemented yet"
        #cleanexit
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
    # do NOT try to understand this part because I have not understood it too :)
    do
        goto NAME_INFO MEMORY_FILE
        get NEXT short MEMORY_FILE
        get PREV short MEMORY_FILE
        get OFF long MEMORY_FILE
        savepos NAME_INFO MEMORY_FILE

        math OFF += NAME_OFF
        goto OFF MEMORY_FILE
        get NAME string MEMORY_FILE

        if NEXT & 0x8000    # 16bit sign conversion
            math NEXT |= 0xffff0000
        endif

        putarray 1 NAMEZ FULLPATH
        if NEXT > 0 # folder
            if PREV != 0
                getarray FULLPATH 1 PREV
            endif
            putarray 1 NAMEZ FULLPATH

            if NAME != ""
                string FULLPATH += NAME
                string FULLPATH += \
            endif
        endif

        math NAMEZ += 1
    while NEXT > 0
    set FULLNAME string FULLPATH
    string FULLNAME += NAME

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
            math CRC ^= CHR
            math CRC *= 0x199933
        next j
        for j = 0 < FILES
            getarray TMP 0 j
            if CRC == TMP
                break
            endif
        next j
        if j >= FILES
            print "Alert: the crc of the file %FULLNAME% has not been found, it can't be extracted!"
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
    endif

        math TMP *= 16
        math TMP += INFO_OFF
        goto TMP MEMORY_FILE
        get OFFSET long MEMORY_FILE
        math OFFSET <<= 8
        get ZSIZE long MEMORY_FILE
        get SIZE long MEMORY_FILE
        get PACKED long MEMORY_FILE

        goto OFFSET
        getdstring SIGN 4
        if SIGN == "LZ2K"
            set PACKED long 2
        else
            set PACKED long 0
        endif

        if PACKED & 2
            callfunction UNLZ2K
            log FULLNAME 0 SIZE MEMORY_FILE2
        else
            if SIZE != 0
            if ZSIZE != 0
            if SIZE != ZSIZE
                print "SIZE (%SIZE%) and ZSIZE (%ZSIZE%) differ, contact me"
                cleanexit
            endif
            endif
            endif
            log FULLNAME OFFSET SIZE
        endif
next i


startfunction UNLZ2K
    putvarchr MEMORY_FILE2 SIZE 0
    log MEMORY_FILE2 0 0
    append
    for TMPSZ = 0 < ZSIZE
        goto OFFSET
        getdstring SIGN 4
        if SIGN != "LZ2K"
            print "Error: the signature at offset %OFFSET% (%SIGN%) is not LZ2K, contact me"
            cleanexit
        endif
        get LZ2K_SIZE long
        get LZ2K_ZSIZE long
        savepos OFFSET
        if LZ2K_ZSIZE == LZ2K_SIZE
            log MEMORY_FILE2 OFFSET LZ2K_SIZE
        else
            clog MEMORY_FILE2 OFFSET LZ2K_ZSIZE LZ2K_SIZE
        endif
        math OFFSET += LZ2K_ZSIZE
        savepos TMP MEMORY_FILE2
        math TMPSZ += 12
        math TMPSZ += LZ2K_ZSIZE
    next
    append
endfunction

```
## Post #14
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-12-14T21:39:06+00:00
- Post Title: Lego Harry Potter *.DAT

> Reply from RickyOs
>
> I did not change version numbers or any comments.
Code: Select all# Traveller's Tales games DAT files extractor (script 0.3)
#  LEGO Batman
#  LEGO Star Wars
#  LEGO Indiana Jones
#  LEGO Harry Potter
#  Transformers
#  others, check them on http://www.ttgames.com
#
# this script is a complete chaos... it's only a work-around since I didn't finish the research
# if you want all the files in PERFECT state you must set NAMELESS to 1
#
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

print "NOTE that this script is a work-around so will not work with all the files\nif you want to extract ALL the files without names (but they will be 100% corrects) edit this script setting NAMELESS to 1"

set NAMELESS long 0 # set to 1 to extract the files without names
comtype lz2k

get INFO_OFF long
if INFO_OFF & 0x80000000
    math INFO_OFF ^= 0xffffffff
    math INFO_OFF <<= 8
    math INFO_OFF += 0x100
endif
get INFO_SIZE long
log MEMORY_FILE INFO_OFF INFO_SIZE

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

math TMP = NAMES
math TMP *= 8
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
        #print "Error: not implemented yet"
        #cleanexit
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
    # do NOT try to understand this part because I have not understood it too :)
    do
        goto NAME_INFO MEMORY_FILE
        get NEXT short MEMORY_FILE
        get PREV short MEMORY_FILE
        get OFF long MEMORY_FILE
        savepos NAME_INFO MEMORY_FILE

        math OFF += NAME_OFF
        goto OFF MEMORY_FILE
        get NAME string MEMORY_FILE

        if NEXT & 0x8000    # 16bit sign conversion
            math NEXT |= 0xffff0000
        endif

        putarray 1 NAMEZ FULLPATH
        if NEXT > 0 # folder
            if PREV != 0
                getarray FULLPATH 1 PREV
            endif
            putarray 1 NAMEZ FULLPATH

            if NAME != ""
                string FULLPATH += NAME
                string FULLPATH += \
            endif
        endif

        math NAMEZ += 1
    while NEXT > 0
    set FULLNAME string FULLPATH
    string FULLNAME += NAME

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
            math CRC ^= CHR
            math CRC *= 0x199933
        next j
        for j = 0 < FILES
            getarray TMP 0 j
            if CRC == TMP
                break
            endif
        next j
        if j >= FILES
            print "Alert: the crc of the file %FULLNAME% has not been found, it can't be extracted!"
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
    endif

        math TMP *= 16
        math TMP += INFO_OFF
        goto TMP MEMORY_FILE
        get OFFSET long MEMORY_FILE
        math OFFSET <<= 8
        get ZSIZE long MEMORY_FILE
        get SIZE long MEMORY_FILE
        get PACKED long MEMORY_FILE

        goto OFFSET
        getdstring SIGN 4
        if SIGN == "LZ2K"
            set PACKED long 2
        else
            set PACKED long 0
        endif

        if PACKED & 2
            callfunction UNLZ2K
            log FULLNAME 0 SIZE MEMORY_FILE2
        else
            if SIZE != 0
            if ZSIZE != 0
            if SIZE != ZSIZE
                print "SIZE (%SIZE%) and ZSIZE (%ZSIZE%) differ, contact me"
                cleanexit
            endif
            endif
            endif
            log FULLNAME OFFSET SIZE
        endif
next i


startfunction UNLZ2K
    putvarchr MEMORY_FILE2 SIZE 0
    log MEMORY_FILE2 0 0
    append
    for TMPSZ = 0 < ZSIZE
        goto OFFSET
        getdstring SIGN 4
        if SIGN != "LZ2K"
            print "Error: the signature at offset %OFFSET% (%SIGN%) is not LZ2K, contact me"
            cleanexit
        endif
        get LZ2K_SIZE long
        get LZ2K_ZSIZE long
        savepos OFFSET
        if LZ2K_ZSIZE == LZ2K_SIZE
            log MEMORY_FILE2 OFFSET LZ2K_SIZE
        else
            clog MEMORY_FILE2 OFFSET LZ2K_ZSIZE LZ2K_SIZE
        endif
        math OFFSET += LZ2K_ZSIZE
        savepos TMP MEMORY_FILE2
        math TMPSZ += 12
        math TMPSZ += LZ2K_ZSIZE
    next
    append
endfunction

Works great!
## Post #15
- Username: lark125
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 10, 2010 6:08 pm
- Post datetime: 2011-01-18T12:32:44+00:00
- Post Title: Lego Harry Potter *.DAT

heey guyss i wanted to know how if this tread is dead, and if it isn't is it already possible to rip the 3d models of the lego characters and if its possible the bones 


many thanks.
## Post #16
- Username: RickyOs
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Nov 30, 2010 12:54 am
- Post datetime: 2011-01-22T10:58:09+00:00
- Post Title: Re: Lego Harry Potter *.DAT

TTGames has developed several LEGO games. Almost each one of them uses a
different file format for the character data. Inside the game.dat file
there is a folder named CHARS. Insiede this folder you can find the requested
data files.

In chronological order:

LEGO Star Wars: The Video Game
  *.hgp Version 1
LEGO Star Wars: The Original Triology
  *.hgp Version 2
LEGO Star Wars: The Complete Saga
  *.ghg Version 1
LEGO Indiana Jones: The Original Adventures
  *.ghg Version 2
LEGO Batman: The Videogame
  In the demo they use *.ghg Version 2
LEGO Indiana Jones 2: The Adventure Continues
  I do not own this game
LEGO Harry Potter: Years 1-4
  In the demo they use *.ghg Version 3

I have managed to extract mesh and image data from hgp Version 2, ghg Version 1,
and ghg Version 2. Since I am new to this topic, I have no idea how to share 
the INCOMPLETE structures (besides I have to write them down first) so that 
you may use it. I use Hex Workshop, so I could try to write hsl-files?
## Post #17
- Username: lark125
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 10, 2010 6:08 pm
- Post datetime: 2011-02-04T14:14:13+00:00
- Post Title: Re: Lego Harry Potter *.DAT

he it is great that you can extract the meshes can you teach me how to do that?
## Post #18
- Username: StarWarsFan786
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 09, 2010 6:03 pm
- Post datetime: 2011-04-01T18:39:53+00:00
- Post Title: Re: Lego Harry Potter *.DAT

Thanks, this works for Lego Star Wars III: The Clone Wars!
## Post #19
- Username: Kane
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 28, 2010 5:50 pm
- Post datetime: 2011-04-02T10:47:56+00:00
- Post Title: Re: Lego Harry Potter *.DAT

I get crc error with Lego SW3.
Also how can I do to work with extracted files?
## Post #20
- Username: lark125
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 10, 2010 6:08 pm
- Post datetime: 2011-04-05T10:51:16+00:00
- Post Title: Re: Lego Harry Potter *.DAT

heey, is it already possible to open the .ghg models?

somthing with hex there is said but i don't know how please help me
