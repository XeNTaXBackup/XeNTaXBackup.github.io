## Post #1
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-05-15T10:28:40+00:00
- Post Title: LEGO Pirates of the Caribbean

Hello!
Is there anyone who knows where the game stores the texts, and how can i extract it? I think the .dat files store it, but i don't know which, (game0 game1...game4) i can't upload them (1gb+ each) if you want part of a file, i do it with winrar or total commander? Thank you!
## Post #2
- Username: Giggity
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 18, 2011 12:14 am
- Post datetime: 2011-05-17T16:24:39+00:00
- Post Title: LEGO Pirates of the Caribbean

I've tried QuickBMS with the "ttgames.bms" script, but that only extracted some of the files. Realy wanted the hidden Armada of the Damned music from that game and maybe some other unreleased cues
## Post #3
- Username: RickyOs
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Nov 30, 2010 12:54 am
- Post datetime: 2011-05-17T20:18:18+00:00
- Post Title: LEGO Pirates of the Caribbean

Try this one:

```
#  LEGO Harry Potter
#  LEGO Star Wars III
#  LEGO Pirates of the Caribbean
#
# this script is expansion to the original script from aluigi
# original script for QuickBMS http://aluigi.org/papers.htm#quickbms

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
        print "Error: not implemented yet"
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
        savepos NAME_INFO MEMORY_FILE

        math OFF += NAME_OFF
        goto OFF MEMORY_FILE
        get NAME string MEMORY_FILE

        if NEXT & 0x8000    # 16bit sign conversion
            math NEXT |= 0xffff0000
        endif

        if PREV != 0
            getarray FULLPATH 1 PREV
        endif
        putarray 1 NAMEZ FULLPATH

        if NEXT > 0 # folder
            if NAME != ""
                string FULLPATH += NAME
                string FULLPATH += \
            endif
        else #file
        endif

        math NAMEZ += 1

    while NEXT > 0
    set FULLNAME string FULLPATH
    string FULLNAME += NAME

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
## Post #4
- Username: Giggity
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 18, 2011 12:14 am
- Post datetime: 2011-05-17T21:46:34+00:00
- Post Title: LEGO Pirates of the Caribbean

Thanks man   this script did the job very well.

As from what i can tell here's a small list of what the .DAT files contains:

GAME : 
Contains various folders, Audio, Movies, common objects/vehicles/creature/character/GUI textures, scripts and some TXT files 

GAME0 :
Titles, main quest hub textures and some textures for loading screens/credits and parts of the Curse of the Black Pearl level

GAME1 : Curse of the Black Pearl level data/textures
GAME2 : Dead Men's Chest level data/textures
GAME3 : At World's End level data/textures
GAME4 : On Stranger Tides level data/textures
## Post #5
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-05-18T09:23:55+00:00
- Post Title: LEGO Pirates of the Caribbean

Nice script thank you
## Post #6
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-05-23T18:52:16+00:00
- Post Title: LEGO Pirates of the Caribbean

Is there anyone who know where are the save games?
## Post #7
- Username: beyondsight
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 26, 2011 8:19 am
- Post datetime: 2011-05-26T00:30:21+00:00
- Post Title: LEGO Pirates of the Caribbean

> Reply from Giggity
>
> this script did the job very well.
Did you manage to extract the music? I've been looking for Armada of the Damned's tracks, too. Though I suppose they might be hard to distinguish from the movie's score...
## Post #8
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-07-05T17:01:45+00:00
- Post Title: LEGO Pirates of the Caribbean

I have some issues:
1. Where are the save game file(s)?
    I found it: C:\Documents and Settings\Your_Name\Application Data\DisneyInteractiveStudios\LEGOPirates\SavedGames
    Or: C:\Users\Your_Name\AppData\Roaming\DisneyInteractiveStudios\LEGOPirates
2. Is there anyway to import bigger files than the original?
3. Is there anyway to run the game with extracted files?

Thank you, if someone can help me!
## Post #9
- Username: nickx
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 25, 2011 7:08 am
- Post datetime: 2011-11-11T20:37:25+00:00
- Post Title: LEGO Pirates of the Caribbean

> Reply from RickyOs
>
> Try this one:

the script isnt reinjecting the files back into the dat file correctly (on the new lego harry potter), could you have a closer look
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-12T16:42:04+00:00
- Post Title: LEGO Pirates of the Caribbean

some files can't be reinjected because they use MEMORY_FILEs operations due to the usage of chunks (the file is splitted in various compressed pieces)
## Post #11
- Username: patcher999
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 21, 2012 3:20 am
- Post datetime: 2012-02-20T19:24:15+00:00
- Post Title: LEGO Pirates of the Caribbean

Can you sort of reverse the script and put files into GAME.DAT? If so, how?
## Post #12
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-08T16:09:39+00:00
- Post Title: LEGO Pirates of the Caribbean

> Reply from RickyOs
>
> Try this one:
Code: Select all# Traveller's Tales games DAT files extractor (script 0.5)
#  LEGO Harry Potter
#  LEGO Star Wars III
#  LEGO Pirates of the Caribbean
#
# this script is expansion to the original script from aluigi
# original script for QuickBMS http://aluigi.org/papers.htm#quickbms

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
        print "Error: not implemented yet"
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
        savepos NAME_INFO MEMORY_FILE

        math OFF += NAME_OFF
        goto OFF MEMORY_FILE
        get NAME string MEMORY_FILE

        if NEXT & 0x8000    # 16bit sign conversion
            math NEXT |= 0xffff0000
        endif

        if PREV != 0
            getarray FULLPATH 1 PREV
        endif
        putarray 1 NAMEZ FULLPATH

        if NEXT > 0 # folder
            if NAME != ""
                string FULLPATH += NAME
                string FULLPATH += \
            endif
        else #file
        endif

        math NAMEZ += 1

    while NEXT > 0
    set FULLNAME string FULLPATH
    string FULLNAME += NAME

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
hey i just wanted to know will this extract all the files? in the dat file?

Update:
thanks you soo much it extracted all the files with out any problems
## Post #13
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-08T16:16:53+00:00
- Post Title: LEGO Pirates of the Caribbean

> Reply from nickx
>
> RickyOs wrote:Try this one:


the script isnt reinjecting the files back into the dat file correctly (on the new lego harry potter), could you have a closer lookhey nickx how do you reinject  back into the .dat file? i want to try modding the credits for a test 
and if anyone knows how to do this can you tell me?
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-01-29T17:00:05+00:00
- Post Title: LEGO Pirates of the Caribbean

Finally I have updated my ttgames.bms script for working correctly with all the games of the LEGO series included Lord of the Rings:

[http://aluigi.org/papers/bms/ttgames.bms](http://aluigi.org/papers/bms/ttgames.bms)
## Post #15
- Username: rip88
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 28, 2012 10:10 pm
- Post datetime: 2013-01-30T20:26:26+00:00
- Post Title: LEGO Pirates of the Caribbean

TY Aluigi,
Export and ReImport LEGO Lord of the Rings works Perfectly.
## Post #16
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2013-01-31T06:52:58+00:00
- Post Title: Re: LEGO Pirates of the Caribbean

> Reply from aluigi
>
> Finally I have updated my ttgames.bms script for working correctly with all the games of the LEGO series included Lord of the Rings:

http://aluigi.org/papers/bms/ttgames.bms
Thanks, aluigi, the script works great.
I very want to translate the lego game(batman1,Indiana Jones1&2,etc.) to my language, although I am still working on the *.fnt(charmap).
But I couldn't test because I don't know how to reimport them.
Could you take a look when you have time, please?
## Post #17
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-01-31T09:17:44+00:00
- Post Title: Re: LEGO Pirates of the Caribbean

the script can't be used for reimporting the files because the file format uses chunks.
have you tried if the game can use the extracted files without the original archive?
## Post #18
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2013-01-31T14:36:40+00:00
- Post Title: Re: LEGO Pirates of the Caribbean

> Reply from aluigi
>
> the script can't be used for reimporting the files because the file format uses chunks.
have you tried if the game can use the extracted files without the original archive?
I have tried, but it didn't work.
## Post #19
- Username: rip88
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 28, 2012 10:10 pm
- Post datetime: 2013-01-31T19:18:44+00:00
- Post Title: Re: LEGO Pirates of the Caribbean

Aluigi,
i make reimport to original file and the game work with CZECH fain. Text and font are on the GAME.DAT.
// 4 Edit the csv try Notepad+.

TY for very good work. BTW TTGame 0.6 script and new QuickBMS work. If you want i up the file on my dropbox.

Sorry for my very bad English.
## Post #20
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-03-31T05:42:00+00:00
- Post Title: Re: LEGO Pirates of the Caribbean

> Reply from RickyOs
>
> Try this one:
Code: Select all# Traveller's Tales games DAT files extractor (script 0.5)
#  LEGO Harry Potter
#  LEGO Star Wars III
#  LEGO Pirates of the Caribbean
#
# this script is expansion to the original script from aluigi
# original script for QuickBMS http://aluigi.org/papers.htm#quickbms

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
        print "Error: not implemented yet"
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
        savepos NAME_INFO MEMORY_FILE

        math OFF += NAME_OFF
        goto OFF MEMORY_FILE
        get NAME string MEMORY_FILE

        if NEXT & 0x8000    # 16bit sign conversion
            math NEXT |= 0xffff0000
        endif

        if PREV != 0
            getarray FULLPATH 1 PREV
        endif
        putarray 1 NAMEZ FULLPATH

        if NEXT > 0 # folder
            if NAME != ""
                string FULLPATH += NAME
                string FULLPATH += \
            endif
        else #file
        endif

        math NAMEZ += 1

    while NEXT > 0
    set FULLNAME string FULLPATH
    string FULLNAME += NAME

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

I used  Traveller's Tales games DAT files extractor (script 0.5), Export and ReImport works Perfectly with .DAT on PC, but with PS3 version, i have some problem:


Thanks for any help!
## Post #21
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-03-31T10:16:25+00:00
- Post Title: Re: LEGO Pirates of the Caribbean

Those of the PS3 don't work because they use something on the last chunk of each file.
But you can modify the script to skip the compressed files and so extracting all the others (mainly audio, video and music)

If you check the latest version of ttgames.bms I wrote this information in the notes at the beginning:

```
# Lego Movie for PS3, in case of crashes or other issues you can
# extract only the non compressed files by setting
# EXTRACT_COMPRESSED to 0.
```
## Post #22
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-03-31T13:44:03+00:00
- Post Title: Re: LEGO Pirates of the Caribbean

> Reply from aluigi
>
> Those of the PS3 don't work because they use something on the last chunk of each file.
But you can modify the script to skip the compressed files and so extracting all the others (mainly audio, video and music)

If you check the latest version of ttgames.bms I wrote this information in the notes at the beginning:
Code: Select all# Note that the script may not work with the compressed files of
# Lego Movie for PS3, in case of crashes or other issues you can
# extract only the non compressed files by setting
# EXTRACT_COMPRESSED to 0.
Thanks! But I'm not coder. Thank you very much again,
> if EXTRACT_COMPRESSED != 0 I will changed: if
> EXTRACT_COMPRESSED = 0?
Thanks!
## Post #23
- Username: anahuj
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 21, 2011 11:48 pm
- Post datetime: 2014-04-05T16:12:37+00:00
- Post Title: Re: LEGO Pirates of the Caribbean

> Reply from aluigi
>
> the script can't be used for reimporting the files because the file format uses chunks.
have you tried if the game can use the extracted files without the original archive?
Can you explain this?
Is this something that we need better quickbms?
