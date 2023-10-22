## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-01T16:03:18+00:00
- Post Title: PS3 .msf files

have MSF or MSFC\MSF0 header.

example:

```
Gв л%¬  яооЮЭопј$  РуН1с"№"рD 
јd юБ;у>БмнbЎ# 3П>сЯ1унЮBр4 "аЮННпј нfЭC сс а.ясь3Р$ 

```


files - [http://ifolder.ru/19565908](http://ifolder.ru/19565908)

Need decoder.
## Post #2
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-01T20:20:02+00:00
- Post Title: PS3 .msf files

Ok.

MF Audio normal play Sonic .msf file(but i don`t think true value(hz`s)).

Battle Fantasia normal convert to aa3, but i can`t find aa3 to wav converter(little and simple).
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-10-01T20:53:19+00:00
- Post Title: PS3 .msf files

Sony Soundforge can decode aa3 files.
## Post #4
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-01T20:59:04+00:00
- Post Title: PS3 .msf files

sorry it is able to only one program
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-10-01T21:11:19+00:00
- Post Title: PS3 .msf files

what? i didn't understand that
## Post #6
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-01T21:16:19+00:00
- Post Title: PS3 .msf files

I meen SoundForge only can work with aa3 files.
## Post #7
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-01T21:57:55+00:00
- Post Title: PS3 .msf files

aa3 files is empty(what alpha`s scripts, what at3 converter). I think this is not standart at3\aa3 or, maybe, not standart MF Audio.
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-10-01T22:11:19+00:00
- Post Title: PS3 .msf files

try the standard at3 header script not aa3. then load with soundforge. drag and drop. worked for me
## Post #9
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-02T06:51:40+00:00
- Post Title: PS3 .msf files

Results - [http://ifolder.ru/19571546](http://ifolder.ru/19571546)

SoundForge still defines as empty.

MediaInfo say it:
General
Complete name                    : C:\Users\i(^_^)i\Desktop\bfm_01.at3
Format                           : Wave
File size                        : 1.23 MiB
Duration                         : 1mn 18s
Overall bit rate                 : 132 Kbps

Audio
Format                           : Atrac3
Codec ID                         : 270
Codec ID/Hint                    : Sony
Duration                         : 1mn 18s
Bit rate                         : 132 Kbps
Channel(s)                       : 2 channels
Sampling rate                    : 48.0 KHz
Stream size                      : 1.23 MiB (100%)
## Post #10
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-02T11:33:35+00:00
- Post Title: PS3 .msf files

I tried use alpha`s scripts and at3 converter, but SoundForge still believes .aa3 and RIFF .at3 files as empty:


I think on my system .aa3 decoding trite does not work.
## Post #11
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-02T16:26:03+00:00
- Post Title: PS3 .msf files

msf2at3.bms
Converts the *.msf files with MSF0 identifier to playable AT3 files with standard RIFF header. You won't need SoundForge for these, they have the old Atrac3 codec, which can be downloaded here: [http://www.free-codecs.com/download/son ... _codec.htm](http://www.free-codecs.com/download/sony_atrac3_audio_codec.htm)

```
get CODE short

set INTERL 0x2b8
set SKIP 0x8
set LAYERS 1
set JUMP INTERL
math JUMP *= LAYERS
math INTERL -= SKIP
get FSIZE asize
for i = 1 <= LAYERS
    log MEMORY_FILE 0 0
    set OFFSET i
    math OFFSET -= 1
    math OFFSET *= INTERL
    math OFFSET += SKIP
    append
    DO
        log MEMORY_FILE OFFSET INTERL
        math OFFSET += JUMP
        math OFFET += SKIP
        set TEST OFFSET
        math TEST += INTERL
    WHILE TEST <= FSIZE
    if OFFSET < FSIZE # write last block
        get LB asize
        math LB -= OFFSET
        log MEMORY_FILE OFFSET LB
    endif
    append
next i

set MEMORY_FILE2 binary "\x65\x61\x33\x3\x0\x0\x0\x0\x7\x76\x47\x45\x4f\x42\x00\x00\x01\xc6\x00\x00\x02\x62\x69\x6e\x61\x72\x79\x00\x00\x00\x00\x4f\x00\x4d\x00\x47\x00\x5f\x00\x4c\x00\x53\x00\x49\x00\x00\x00\x01\x00\x40\x00\xdc\x00\x70\x00\x08\x00\x00\x00\x00\x00\x00\x4b\x45\x59\x52\x49\x4e\x47"
putVarChr MEMORY_FILE2 0x400 0x1334145 long
putVarChr MEMORY_FILE2 0x404 0xffff6000 long
putVarChr MEMORY_FILE2 0x420 0x1 byte
putVarChr MEMORY_FILE2 0x422 CODE short
goto 0 MEMORY_FILE
get FIRST long MEMORY_FILE
putVarChr MEMORY_FILE2 0x460 FIRST long
savepos DATA MEMORY_FILE
get SIZE asize MEMORY_FILE
math SIZE -= 4
print "here"
append
log MEMORY_FILE2 4 SIZE MEMORY_FILE1
append
get NAME basename
string NAME += ".aa3"
math SIZE += 0x460

log NAME 0 SIZE MEMORY_FILE2
```

Hope that helps...
## Post #12
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-02T17:01:59+00:00
- Post Title: PS3 .msf files

You're cool AlphaTwentyThree. Thanks! Resulted .at3 file simple can rename to .wav and with installed ATRAC3 Codec his play in Media Player Classics.
## Post #13
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-02T17:37:11+00:00
- Post Title: PS3 .msf files

> Reply from Researchman
>
> You're cool AlphaTwentyThree. Thanks! Resulted .at3 file simple rename to .wav and with installed ATRAC3 Codec his play in Media Player Classics.
You don't have to rename the files, it works as it is. You can also open them with any audio editor.
## Post #14
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-02T18:09:27+00:00
- Post Title: PS3 .msf files

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-03T07:28:31+00:00
- Post Title: PS3 .msf files

Maybe this is a ps adpcm data.
## Post #16
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-08T21:44:40+00:00
- Post Title: Re: PS3 .msf files

Ok, found out how those MSF files work. Needed the other two headers for 66 kbps and 105 kbps. The distinguishing byte seems to be the long value directly after the "MSF0" or "MSFC" (4 = 66kbps, 5 = 105kbps, 6 = 132kbps). Here's a script that should work for all .msf files now:

```
# written in 2011 by AlphaTwentyThree
# transform PS3 *.msf files into playable Atrac *.at3 files

IDstring MSF
set MEMORY_FILE binary "\x52\x49\x46\x46\x88\xb3\x6d\x0\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x0\x0\x0\x70\x2\x2\x0\x80\xbb\x0\x0\x9a\x40\x0\x0\x80\x1\x0\x0\xe\x0\x1\x0\x0\x10\x0\x0\x0\x0\x0\x0\x1\x0\x0\x0\x66\x61\x63\x74\x8\x0\x0\x0\x91\x81\x24\x1\x1b\x4\x0\x0\x64\x61\x74\x61\x88\xb3\x6d\x0"
endian big
get SIGN byte
get BITSIGN long
get CH long
get SIZE long
get FREQ long
set SKIP 0x40
get SIZE asize
math SIZE -= SKIP
set RIFFSIZE SIZE
math RIFFSIZE += 0x44

endian little
putVarChr MEMORY_FILE 0x04 RIFFSIZE long
putVarChr MEMORY_FILE 0x16 CH byte
putVarChr MEMORY_FILE 0x18 FREQ long
putVarChr MEMORY_FILE 0x48 SIZE long
if BITSIGN == 4 # 66 kbps
        putVarChr MEMORY_FILE 0x1c 0x204d long
        putVarChr MEMORY_FILE 0x20 0xc0 long
    elif BITSIGN == 5 # 105 kbps
        putVarChr MEMORY_FILE 0x1c 0x3324 long
        putVarChr MEMORY_FILE 0x20 0x130 long
    elif BITRSIGN == 6 # 132 kbps
        putVarChr MEMORY_FILE 0x1c 0x409a long
        putVarChr MEMORY_FILE 0x20 0x180 long
endif

append
log MEMORY_FILE SKIP SIZE
append
math SIZE += 0x4c
goto 0x28
getDstring NAME 0x17
string NAME += ".at3"
log NAME 0 SIZE MEMORY_FILE
```


And additionally, here's the script for those *.xws containers: 

```
# written in 2010 by AlphaTwentyThree
# extracts PS3 *.xws archives, automatically adjusts all AT3 headers
# extracted *.at3 files are playable with the Atrac coded installed

endian big
getdstring IDENT 8
get UNKNOWN long
get UNKNOWN long
get FILESIZE long
get UNKNOWN long
get UNKNOWN long
get UNKNOWN long
get INFO1OFF long
get INFO2OFF long # unknown informatin

goto INFO1OFF
get UOFF long # unknown information
get CODEOFF long
get MSF long # MSFBANK

goto INFO2OFF
get UNKNOWNOFF long
get UNKNOWNOFF long
get DATASIZE long # size from MSFBANK till end

set OFF MSF
math OFF += 0x14
goto OFF

get FILES long
math OFF += 0x1c
set OFFPOS OFF
set SIZEPOS FILES
math SIZEPOS *= 4
math SIZEPOS += OFFPOS
math SIZEPOS += 0xc
get BNAME basename
string BNAME += "_"

for i = 1 <= FILES
    endian big
    goto OFFPOS
    get OFFSET long
    math OFFSET += MSF
    
    savepos OFFPOS
    goto SIZEPOS
    get SIZE long
    savepos SIZEPOS
    set NAME BNAME
    string NAME += i
    goto OFFSET
    callfunction writeAT3 1
next i

startfunction writeAT3
    
    # read info from header and adjust size
    goto OFFSET
    getDstring MSIG 4 # "MSF0" or "MSFC"
    get BITSIGN long
    get UNK long
    get SIZE long
    get FREQ long
    math OFFSET += 0x40
    
    endian little
    set MEMORY_FILE binary "\x52\x49\x46\x46\x88\xb3\x6d\x0\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x0\x0\x0\x70\x2\x2\x0\x80\xbb\x0\x0\x9a\x40\x0\x0\x80\x1\x0\x0\xe\x0\x1\x0\x0\x10\x0\x0\x0\x0\x0\x0\x1\x0\x0\x0\x66\x61\x63\x74\x8\x0\x0\x0\x91\x81\x24\x1\x1b\x4\x0\x0\x64\x61\x74\x61\x88\xb3\x6d\x0"
    string NAME += ".at3"
    set RIFFSIZE SIZE
    math RIFFSIZE += 0x44
    if BITSIGN == 4 # 66kbps
        putVarChr MEMORY_FILE 0x1c 0x204d long
        putVarChr MEMORY_FILE 0x20 0xc0 long
    elif BITSIGN == 5 # 105 kbps
        putVarChr MEMORY_FILE 0x1c 0x3324 long
        putVarChr MEMORY_FILE 0x20 0x130 long
    elif BITSIGN == 6 # 132 kbps
        putVarChr MEMORY_FILE 0x1c 0x409a long
        putVarChr MEMORY_FILE 0x20 0x180 long
    endif
    putVarChr MEMORY_FILE 0x04 RIFFSIZE long
    putVarChr MEMORY_FILE 0x16 0x2 byte
    putVarChr MEMORY_FILE 0x18 FREQ long
    putVarChr MEMORY_FILE 0x48 SIZE long
    append
    log MEMORY_FILE OFFSET SIZE
    append
    math SIZE += 0x4c
    log NAME 0 SIZE MEMORY_FILE
    endian big
endfunction

```
## Post #17
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2010-10-09T02:45:13+00:00
- Post Title: Re: PS3 .msf files

Pretty sure the latest vgmstream release supports MSF with PS ADPCM since this is the file we used (not the exact one you posted though) to add support for it.
## Post #18
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-09T12:42:16+00:00
- Post Title: Re: PS3 .msf files

> Reply from bxaimc
>
> Pretty sure the latest vgmstream release supports MSF with PS ADPCM since this is the file we used (not the exact one you posted though) to add support for it.This script isn't for PS ADPCM as you can clearly see. It's for Atrac. Also supported by vgmstream? Guess not...
## Post #19
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2010-10-09T13:59:21+00:00
- Post Title: Re: PS3 .msf files

I know, I can read. I'm not talking about your post. I'm talking about Researchmans's MSF from Sonic Genesis Collection.
## Post #20
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-09T15:04:24+00:00
- Post Title: Re: PS3 .msf files

> Reply from bxaimc
>
> I know, I can read. I'm not talking about your post. I'm talking about Researchmans's MSF from Sonic Genesis Collection.
Lol, sorry.
