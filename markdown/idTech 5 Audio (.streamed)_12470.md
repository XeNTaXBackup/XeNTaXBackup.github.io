## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-01-05T20:37:59+00:00
- Post Title: idTech 5 Audio (.streamed)

Currently solved with: RAGE, Wolfenstein: The New Order, The Evil Within.

=======================================
Format, which can be a container or archive with compression.

Currently used in three games - Rage, Wolfenstein: New Order, The Evil Within(aka Psychobreak).
All information down is about PC versions.

Rage:
Single files for audio and voices. Uses different format that .resource files.
Nova Extractor dont find anything.
Possibly uses chunk structure and byte ordering, no header.

> streamed.resources
>
> First bytes:
>
> Code: Select all...¤.]..пьaвфю. ...г..:р.б..Ъ.."р‘ `..ят°О/СG+.е.с..'....ва....G..@буа.B.3.t.;"рРа.у~ .яЖб.,и.1.
>
> Last bytes:
>
> Code: Select all.......ыяюя............р.....................................................чяшя...............................................................

> english.streamed
>
> First bytes:
>
> Code: Select all...ќяДя.>Ф....ь0г.р.С0.я...вMт.р. РPР..<ф.я..п0Т
>
> Last bytes:
>
> Code: Select all...а....рр.....р..р..........цячя......................р.р........................р.............
Wolfenstein: New Order:
Single files for audio and voices. Uses different format that .resource files.
Nova Extractor find oggs, but only small audio files is extractable. Also detects 987MB(18474 oggs, 48000 Hz, stereo, 128kbps) from 1.07GB streamed.resource file.
Uses chunk sctructure(several empty big blocks), no header.

> streamed.resources
>
> First bytes:
>
> Code: Select allOggS..........)........ Ёя...vorbis.....Ђ»..яяяя.ф..яяяяё.OggS..
>
> Last bytes:
>
> Code: Select allќj.wћФЏmL¦.8a·ЖМґ...бтћ\зп?/П5–—u±Клї.Ч..ыс |Юk.

> english.streamed:
>
> First bytes:
>
> Code: Select allOggS..........)........…l1...vorbis.....Ђ»..яяяя.w..яяяяё.OggS..
>
> Last bytes:
>
> Code: Select all8и БLВ5..,р.t.ђCѓ..®-ъЯYx©.Ё_Ё).................
Evil Within(aka Psychobreak):
Separate files for every level. Example: a_planted_seed_will_grow.streamed, a_planted_seed_will_grow.tangoresource, a_planted_seed_will_grow_en.streamed. Has the same format as .resource files, but can use another compression method.
Nova Extractor dont find anything.
Extractable with bms script(can be find in aluigi's quickbms page), but dont sure about correcting extraction.
Uses byte ordering(table in the end of file), have header(4 bytes, #”«Н as 23 94 AB CD).

> a_planted_seed_will_grow.streamed
>
> First bytes:
>
> Code: Select all#”«Н.P®Т..Јk.M.·юияпЊЪЫрV*О..E!QП.ъбQ..Ю..®а....
>
> Last bytes:
>
> Code: Select allR.OTФ..|”..|”...S.OСh..rў..rў...T.PD...jИ..jИ

> a_planted_seed_will_grow_en.streamed
>
> First bytes:
>
> Code: Select all#”«Н.ВW(..Rэ.....!..а.[!б/у-4с1N.Гщ.юЮ.р.~3 -аЬ.
>
> Last bytes:
>
> Code: Select allш.Gћш...Я.Ў:њ...„...„...а.¬D ...„...„...б.·M¤...„...„

> a_planted_seed_will_grow.tangoresource:
>
> First bytes:
>
> Code: Select all#”«Н..3л<...textures/uitng/img/chapter_select_pic/chapter_load_1
>
> Last bytes:
>
> Code: Select all€A....9¤..€B....9Є..€C....9°..€D....9¶..€E....9ј

Files for researching can be transfered throught PM or request for public download link in thread.
[idt5aud_pack.7z](https://xentaxbackup.github.io/file/8999_idt5aud_pack.7z)
## Post #2
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-01-05T21:41:41+00:00
- Post Title: idTech 5 Audio (.streamed)

Few extractable examples(Wolfenstein: New Order, The Evil Within):
[http://dropmefiles.com/GPLmA](http://dropmefiles.com/GPLmA)
[https://mega.co.nz/#!lFkFWaoB!k1PdxtSU8 ... LIX24tbuEY](https://mega.co.nz/#!lFkFWaoB!k1PdxtSU8NM4gwGtBKJQKtv6wqXLb65BRLIX24tbuEY)
## Post #3
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-01-06T12:01:24+00:00
- Post Title: idTech 5 Audio (.streamed)

Information about console versions(Xbox360 and PS3 can be researched currently):
Rage:
Uses the same formats as in PC version.

Wolfenstein: New Order:
Uses the same formats as in PC version.

Evil Within:
.tpr+.str files. Same format as in PC version.
.tpr contains .tangoresource data, .str contains .streamed data
PS3 version uses .MSF format for audio(MP3). Just rename .MSF to .MP3. (tested in Media Player Classic)
Xbox360 version uses .XMA format for audio.
Extractable with bms script(can be find in aluigi's quickbms page).


Additional info about audio in PC versions - uses WAV with MS ADPCM.
Currently see two problems:
- container unpacking(streamed.resource) in Rage and Wolfenstein: New Order. (all versions)
- MS ADPCM decoding. Currently can be researched in Evil Within. (PC version)
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2015-02-02T00:20:52+00:00
- Post Title: idTech 5 Audio (.streamed)

> Reply from Researchman
>
> Information about console versions(Xbox360 and PS3 can be researched currently):
Rage:
Uses the same formats as in PC version.

Wolfenstein: New Order:
Uses the same formats as in PC version.

Evil Within:
.tpr+.str files. Same format as in PC version.
.tpr contains .tangoresource data, .str contains .streamed data
PS3 version uses .MSF format for audio(MP3). Just rename .MSF to .MP3. (tested in Media Player Classic)
Xbox360 version uses .XMA format for audio.
Extractable with bms script(can be find in aluigi's quickbms page).


Additional info about audio in PC versions - uses WAV with MS ADPCM.
Currently see two problems:
- container unpacking(streamed.resource) in Rage and Wolfenstein: New Order. (all versions)
- MS ADPCM decoding. Currently can be researched in Evil Within. (PC version)

if you have RAGE on steam, the container unpacking is not an issue. install the "RAGE Tool Kit" found under "Tools" category of library. (and now steam downloads 20gb or so) all sounds are now available in the folder structure as ms adpcm. The bigger issue with RAGE was that the .streamed and .resources used some kind of link for the header in one and the raw data in the other. I know the ps3 version of wolfenstein the new order uses mp3 files, if you scan it for them you'll get then all. albeit nameless.
## Post #5
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-02-04T16:05:11+00:00
- Post Title: idTech 5 Audio (.streamed)

Sorry, but I dont understand your point.

I think, possible to unpack .streamed data without a header in another file, because .streamed files of Evil Within can be unpacked in any version(PC, PS3, Xbox360).

Also:

- .streamed files of PS3 version of Wolfenstein: New Order contains .msf files variant, which is mp3. If cut it as samples throught Nova Extractor, so begin and end of files will be cuted(has place with Killzone 3 as minimum).

- I dont find MS ADPCM decoder for idTech5 PC versions of games on him. They dont supported in Media Player Classic, VLC, XMPlay.
## Post #6
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2015-02-12T19:20:04+00:00
- Post Title: idTech 5 Audio (.streamed)

> Reply from Researchman
>
> Sorry, but I dont understand your point.

I think, possible to unpack .streamed data without a header in another file, because .streamed files of Evil Within can be unpacked in any version(PC, PS3, Xbox360).

Also:

- .streamed files of PS3 version of Wolfenstein: New Order contains .msf files variant, which is mp3. If cut it as samples throught Nova Extractor, so begin and end of files will be cuted(has place with Killzone 3 as minimum).

- I dont find MS ADPCM decoder for idTech5 PC versions of games on him. They dont supported in Media Player Classic, VLC, XMPlay.

I was just informing you that the files in the rage toolkit are all the sounds in ms adpcm. decoding worked for me via the xbox adpcm codec (only way to decode it on windows 8 with goldwave, default ms adpcm codecs have been gimped for a long time as they are .acm which is no longer supported) also the exact frequency of each file is semi-random. all 48khz files are a random number +- 2000 within the range of 48000, which messes up alot of decoding, or makes playback impossible without first doing a re encode on certain audio systems. (realtek HD handles adpcm at 47329khz with a noticable 2 seconds of lag before even being able to start playback, other drivers fail altogether.) the xbox adpcm codec installer that is stored in ekszbox abx's sourceforge repository handles a wide array of ms/xbox adpcm very well, better than vlc or mpc does by default. the strange somewhat random khz ranges is an issue for not just latency but also decoding depending on your system.
## Post #7
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-02-28T16:54:52+00:00
- Post Title: idTech 5 Audio (.streamed)

It will restore headers to get playable adpcm .wav's

```
# Put .bsnd (extracted from .tangoresource) and .msadpcm (extracted from .streamed) files in the same dir and use .bsnd as input
# Written by spider91
# script for QuickBMS http://quickbms.aluigi.org
idstring "bsnf"
get BSND_NAME FILENAME
get WAV_NAME BASENAME
string WAV_NAME -= "_msadpcm"
string WAV_NAME += ".msadpcm"
open FDSE BSND_NAME 0
open FDSE WAV_NAME 1
get RIFFSIZE ASIZE 1
math RIFFSIZE += 70
set FMTSIZE long 50
get DATA_SIZE ASIZE 1
Goto -50 0
get CODEC_ID short
get CHANNELS short
get FREQUENCY long
get BPS long
get ALIGN short
get UNKNOWN1 long
get UNKNOWN2 long
get UNKNOWN3 long
get UNKNOWN4 long
get UNKNOWN5 long
get UNKNOWN6 long
get UNKNOWN7 long
get UNKNOWN8 long
get UNKNOWN9 long
putVarChr MEMORY_FILE 78 0
log MEMORY_FILE 0 0
set MEMORY_FILE binary "\x52\x49\x46\x46\x00\x00\x00\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x64\x61\x74\x61\x00\x00\x00\x00"
putVarChr MEMORY_FILE 4 RIFFSIZE long
putVarChr MEMORY_FILE 16 FMTSIZE long
putVarChr MEMORY_FILE 20 CODEC_ID short
putVarChr MEMORY_FILE 22 CHANNELS short
putVarChr MEMORY_FILE 24 FREQUENCY long
putVarChr MEMORY_FILE 28 BPS long
putVarChr MEMORY_FILE 32 ALIGN short
putVarChr MEMORY_FILE 34 UNKNOWN1 long
putVarChr MEMORY_FILE 38 UNKNOWN2 long
putVarChr MEMORY_FILE 42 UNKNOWN3 long
putVarChr MEMORY_FILE 46 UNKNOWN4 long
putVarChr MEMORY_FILE 50 UNKNOWN5 long
putVarChr MEMORY_FILE 54 UNKNOWN6 long
putVarChr MEMORY_FILE 58 UNKNOWN7 long
putVarChr MEMORY_FILE 62 UNKNOWN8 long
putVarChr MEMORY_FILE 66 UNKNOWN9 long
putVarChr MEMORY_FILE 74 DATA_SIZE long
append
log MEMORY_FILE 0 DATA_SIZE 1
get NAME BASENAME
string NAME -= "_msadpcm"
string NAME += ".wav"
set FULLSIZE long RIFFSIZE
math FULLSIZE += 8
log NAME 0 FULLSIZE MEMORY_FILE
```
## Post #8
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-03-01T06:29:12+00:00
- Post Title: idTech 5 Audio (.streamed)

> It will restore headers to get playable adpcm .wav's
Works. Thanks.
## Post #9
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-03-04T05:06:02+00:00
- Post Title: idTech 5 Audio (.streamed)

Some .bsnd files have bad "data" size. Updated script to avoid that problem.
## Post #10
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-04-04T17:24:51+00:00
- Post Title: idTech 5 Audio (.streamed)

Additional information:
- Wolfenstein: The New Order dont use .index file for streamed.resources, english.streamed and other separate audio archives.
- File headers stores separated in gameresources.resources(Rage), chunk0-13(Wolfenstein: The New Order).
- Rage probably uses WAV ADPCM without headers(they stores separated)(.idmsa).
- Wolfenstein: The New Order uses vorbis or wwise ogg (PC version), MSF MP3(PS3 version) for audio in .resources/.streamed files.

Headers for music files in attach. (Rage and Wolfenstein: The New Order PC versions)
[idt5_aheaders.7z](https://xentaxbackup.github.io/file/8942_idt5_aheaders.7z)
## Post #11
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-04-04T20:28:14+00:00
- Post Title: idTech 5 Audio (.streamed)

Thanks!!

This is what i needed. So will test.

EDIT: Is there any automated way to match the headers witht he audio files themselves.
## Post #12
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-04-05T04:17:48+00:00
- Post Title: idTech 5 Audio (.streamed)

No, because no one made .streamed files unpacker and find a way to get filenames.
## Post #13
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-04-05T14:04:57+00:00
- Post Title: idTech 5 Audio (.streamed)

> -File headers stores separated in gameresources.resources(Rage), chunk0-13(Wolfenstein: The New Order).
>
> - Wolfenstein: The New Order uses vorbis or wwise ogg (PC version), MSF MP3(PS3 version) for audio in .resources/.streamed files.

I'm not good with ogg format (and in WTNO files are simple ogg vorbis), but i'll try to find some way to get filenames for WTNO sounds.

> - Rage probably uses WAV ADPCM without headers(they stores separated)(.idmsa).

As i remember there is wav adpcm with headers, but i can be wrong. If they are really without headers i can take a look, it should be similiar to Evil Within.
## Post #14
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-04-06T14:44:10+00:00
- Post Title: idTech 5 Audio (.streamed)

I've fidured out how to locate WTNO filenames for sounds. They are stored in .index files. I'm pretty busy now, so i don't know when i will write a script, but i'll try to make it as soon as i can.

Upd.
Rage seems to be the same (names stored in gameresources.resources), exept files are headerless adpcm.
## Post #15
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-04-07T00:15:00+00:00
- Post Title: idTech 5 Audio (.streamed)

GREAT!!

Can't wait.
## Post #16
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-04-07T02:20:12+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

I've modified .resources script for WTNO, so now it unpacks game sounds with names. Filenames are splitted into *.index files, so if you want to extract all of them place quickbms, wtno_snd.txt (the script below) and the batch files with this line

```
for %%i in (*.index) do quickbms -Y wtno_snd.txt %%i unpackedsounds
```


into Wolfenstein.The.New.Order\base directory. If you want to extract main sounds or specific language voices just remove # before open commad with respective sound archieve and add it to other lines at the beginning of the script.

```
open FDSE english.streamed 2 ENG_SOUND
#open FDSE french.streamed 3 FRA_SOUND
#open FDSE italian.streamed 4 ITA_SOUND
#open FDSE spanish.streamed 5 SPA_SOUND

endian big
goto 0x24
get files long
get unk long
math TMP = files
math TMP - 1
for i = 0 < files
endian little
get FNsize1 long
getdstring FN1 FNsize1
get FNsize2 long
getdstring FN2 FNsize2
get namesize long
getdstring name namesize
endian big
get offset long
get size long
get zsize long
get unksize long
string FN2 -= ".wav"
string FN2 += ".ogg"

if unksize = 1
   savepos pos
   math pos += 0x10
   goto pos
   get offset long
   get size long
   if MAIN_SOUND = 1
      log FN2 offset size 1
   endif
elif unksize = 4
   savepos pos
   math pos += 0x10
   goto pos
   get offset long
   get size long
   if ENG_SOUND = 1
      log FN2 offset size 2
   endif

   savepos pos
   math pos += 0x10
   goto pos
   get offset long
   get size long
   if FRA_SOUND = 1
      log FN2 offset size 3
   endif

   savepos pos
   math pos += 0x10
   goto pos
   get offset long
   get size long
   if ITA_SOUND = 1
      log FN2 offset size 4
   endif

   savepos pos
   math pos += 0x10
   goto pos
   get offset long
   get size long
   if SPA_SOUND = 1
      log FN2 offset size 5
   endif
   

else
   math unksize *= 0x18
   getdstring unkdata unksize
endif

savepos pos
math pos += 0x5
goto pos

if i != TMP
get filenumber long
endif
next i
```
## Post #17
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-04-07T12:25:59+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

Great work. (duplicate file paths in .index files is strange)

Try to use with RAGE, but it fails. As I understand, the reason in another archive method, which probably works directly with streamed.resources.
## Post #18
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-04-07T13:03:56+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

> Reply from Researchman
>
> Great work. (duplicate file paths in .index files is strange)

Try to use with RAGE, but it fails. As I understand, the reason in another archive method, which probably works directly with streamed.resources.

Nothing strange. It uses a lot of same files in each level, so duplicates are normal.

As about Rage the resources archieve is different from WTNO, so it won't work. I'll take a look when get some more free time.
## Post #19
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-04-08T22:52:36+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

Rage - uses headerless wav adpcm. Filenames are stored into gameresources.resources. To unpack headerless .msadpcm files use sript below. You can choose betwen main sounds and specific language voices at the beginning of the script (just like in Wolfenstein TNO). 

```
open FDSE english.streamed 2 ENG_SOUND
#open FDSE french.streamed 3 FRA_SOUND
#open FDSE italian.streamed 4 ITA_SOUND
#open FDSE german.streamed 5 GER_SOUND
#open FDSE spanish.streamed 6 SPA_SOUND
#open FDSE russian.streamed 7 RUS_SOUND
#open FDSE japanese.streamed 8 JAP_SOUND

endian big

get DUMMY long
get FOFFSET long
goto FOFFSET
get FILES long

for i = 0 < FILES

  endian little

  get FILENUM long
  get STRLEN long
  getdstring BLOCKNAME STRLEN
  get STRLEN long
  getdstring VALUE1 STRLEN
  get STRLEN long
  getdstring VALUE2 STRLEN

  endian big

  get OFFSET long
  get SIZE long 
  get ZSIZE long
  get EXTRA long

  string VALUE1 -= ".wav"
  string VALUE1 += ".msadpcm"

  if EXTRA = 1

     savePOS POS
     math POS += 0x10
     goto POS
     get OFFSET long
     get SIZE long
     if MAIN_SOUND = 1
        log VALUE1 OFFSET SIZE 1
     endif

  elif EXTRA = 7

     savePOS POS
     math POS += 0x10
     goto POS
     get offset long
     get SIZE long
     if ENG_SOUND = 1
        log VALUE1 OFFSET SIZE 2
     endif

     savePOS POS
     math POS += 0x10
     goto POS
     get offset long
     get SIZE long
     if FRA_SOUND = 1
        log VALUE1 OFFSET SIZE 3
     endif

     savePOS POS
     math POS += 0x10
     goto POS
     get offset long
     get SIZE long
     if ITA_SOUND = 1
        log VALUE1 OFFSET SIZE 4
     endif

     savePOS POS
     math POS += 0x10
     goto POS
     get offset long
     get SIZE long
     if GER_SOUND = 1
        log VALUE1 OFFSET SIZE 5
     endif

     savePOS POS
     math POS += 0x10
     goto POS
     get offset long
     get SIZE long
     if SPA_SOUND = 1
        log VALUE1 OFFSET SIZE 6
     endif

     savePOS POS
     math POS += 0x10
     goto POS
     get offset long
     get SIZE long
     if RUS_SOUND = 1
        log VALUE1 OFFSET SIZE 7
     endif

     savePOS POS
     math POS += 0x10
     goto POS
     get offset long
     get SIZE long
     if JAP_SOUND = 1
        log VALUE1 OFFSET SIZE 8
     endif

  else
     math EXTRA *= 0x18
     getdstring EXTRADATA EXTRA
  endif

  savePOS POS
  math POS += 0x14
  goto POS

next i

get SIZE asize
savePOS POS

if POS != SIZE
  print "!! other footer data here !!"
endif

print "Completed!!"
```


To get playable wav adpcm (restore headers) put .idmsa (you can unpack them from gameresources.resources with this [script](http://forum.xentax.com/viewtopic.php?p=60625#p60625)) and .msadpcm files with the same name in same directory and use this script (same thing with main sounds and language voices at the beginning of the script).

```
set SHIFT 0xE2 # english sounds
#set SHIFT 0x145 # french sounds
#set SHIFT 0x1A8 # italian sounds
#set SHIFT 0x20B # german sounds
#set SHIFT 0x26E # spanish sounds
#set SHIFT 0x2D1 # russian sounds
#set SHIFT 0x334 # japanese sounds
open FDDE idmsa 0
open FDDE msadpcm 1
idstring "mzrt"
get RIFFSIZE ASIZE 1
math RIFFSIZE += 70
set FMTSIZE long 50
get DATA_SIZE ASIZE 1
Goto SHIFT 0
get CODEC_ID short
get CHANNELS short
get FREQUENCY long
get BPS long
get ALIGN short
get UNKNOWN1 long
get UNKNOWN2 long
get UNKNOWN3 long
get UNKNOWN4 long
get UNKNOWN5 long
get UNKNOWN6 long
get UNKNOWN7 long
get UNKNOWN8 long
get UNKNOWN9 long
putVarChr MEMORY_FILE 78 0
log MEMORY_FILE 0 0
set MEMORY_FILE binary "\x52\x49\x46\x46\x00\x00\x00\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x64\x61\x74\x61\x00\x00\x00\x00"
putVarChr MEMORY_FILE 4 RIFFSIZE long
putVarChr MEMORY_FILE 16 FMTSIZE long
putVarChr MEMORY_FILE 20 CODEC_ID short
putVarChr MEMORY_FILE 22 CHANNELS short
putVarChr MEMORY_FILE 24 FREQUENCY long
putVarChr MEMORY_FILE 28 BPS long
putVarChr MEMORY_FILE 32 ALIGN short
putVarChr MEMORY_FILE 34 UNKNOWN1 long
putVarChr MEMORY_FILE 38 UNKNOWN2 long
putVarChr MEMORY_FILE 42 UNKNOWN3 long
putVarChr MEMORY_FILE 46 UNKNOWN4 long
putVarChr MEMORY_FILE 50 UNKNOWN5 long
putVarChr MEMORY_FILE 54 UNKNOWN6 long
putVarChr MEMORY_FILE 58 UNKNOWN7 long
putVarChr MEMORY_FILE 62 UNKNOWN8 long
putVarChr MEMORY_FILE 66 UNKNOWN9 long
putVarChr MEMORY_FILE 74 DATA_SIZE long
append
log MEMORY_FILE 0 DATA_SIZE 1
append
get NAME BASENAME
string NAME += ".wav"
set FULLSIZE long RIFFSIZE
math FULLSIZE += 8
log NAME 0 FULLSIZE MEMORY_FILE
```
## Post #20
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-04-09T15:06:43+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

Thanks for huge help!

Collect and pack basic extractors for all three games in one archive.

See attach in the first post. Readme with thanks included.
## Post #21
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-04-09T15:22:33+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

I've tried to unpack gameresources.resources from RAGE dlc and scirpt stops working at one moment. Same thing with script for audio, cause its based on rage script v2. Extracted files seems to be good, but that's not all the files, i think. I don't have time now, but maybe next week i'll take a look and try to fix script for dlc.
## Post #22
- Username: Shepard62700FR
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 14, 2015 1:49 am
- Post datetime: 2016-02-17T00:53:34+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

Sorry for bringing this back from the dead but any chance to get the scripts for RAGE working again ? It stops after the extraction at line 23 "getdstring BLOCKNAME STRLEN" with "the requested amount of bytes to allocate is negative". If I use the 4Gb version of QuickBMS, it say "not enough memory".
## Post #23
- Username: Raik
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 17, 2015 7:51 am
- Post datetime: 2016-02-24T19:30:03+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

Hello  spider91

Could you take a look into Doom BFG Edition? This game use .idwav. Its also msadpcm but with header stored in the file instead outside like Rage. However this header cannot be played without modification. I have add a working header for one file but maybe you can write a working BMS script: [http://s000.tinyupload.com/index.php?fi ... 8459561560](http://s000.tinyupload.com/index.php?file_id=16152129288459561560)

thx
## Post #24
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2016-02-25T10:27:57+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

Shepard62700FR
I don't have much time now, don't even know when i'll be able to take a look.

Raik
I've already done it a month ago, but forgot to post script)

```
log MEMORY_FILE 0 0
set MEMORY_FILE binary "\x52\x49\x46\x46\x00\x00\x00\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x32\x00\x00\x00"
append
log MEMORY_FILE 0x15 0x32
putVarChr MEMORY_FILE 0x46 0x64617461 long
goto 0x47
get OFFSET long
math OFFSET += 0x57
goto OFFSET
get SIZE long
savepos OFFSET
reverselong SIZE
putVarChr MEMORY_FILE 0x4A SIZE long
reverselong SIZE
log MEMORY_FILE OFFSET SIZE
math SIZE += 0x46
reverselong SIZE
putVarChr MEMORY_FILE 0x4 SIZE long
get SIZE asize MEMORY_FILE
get NAME basename
string NAME += ".wav"
log NAME 0 SIZE MEMORY_FILE
```
## Post #25
- Username: Raik
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 17, 2015 7:51 am
- Post datetime: 2016-02-25T21:06:09+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

great, works perfect
## Post #26
- Username: kangmin
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 17, 2012 4:38 pm
- Post datetime: 2016-04-13T15:40:05+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

this is kinda old .. sorry .. im a total newb with this.. i wanted to extract the audio in " the evil within" game, every sfx /bgm used .. i tried extracting the .streamed files..but get stuck at .msadpcm.. anyone willing to guide me .. step by step? or teach me  what file should i extract?
## Post #27
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2017-02-14T06:15:06+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

Hi Spider91, I'd really appreciate your help in changing script or even making a new one for Rage on PS3! [Qartar's rendition](http://forum.xentax.com/viewtopic.php?p=60625#p60625) of original bms file by WRS works on gameresources.resources from both base & mp folders but your BMS doesn't unpack a single file out of streamed.resources from both aforementioned folders. The error QuickBMS reports is "incomplete input file: can't reach 0xN bytes".
[Here](https://mega.nz/#!YFN3AaAR!-1q3AJMTizQUx7rnbJHjTXNiiBxWxVUr8AZL_8TRGMs)'re beginning and end cuts from both streamed.resources archives, forgive me they're so different in size. I hope you can help, I can surely wait for you to try & deal with the problem so there's no rush.
Goodbye, take care!
## Post #28
- Username: amiraria
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 06, 2017 2:15 am
- Post datetime: 2017-07-10T17:41:00+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

> Reply from spider91
>
> It will restore headers to get playable adpcm .wav's
Code: Select all# The Evil Within adpcm script (PC)
# Put .bsnd (extracted from .tangoresource) and .msadpcm (extracted from .streamed) files in the same dir and use .bsnd as input
# Written by spider91
# script for QuickBMS http://quickbms.aluigi.org
idstring "bsnf"
get BSND_NAME FILENAME
get WAV_NAME BASENAME
string WAV_NAME -= "_msadpcm"
string WAV_NAME += ".msadpcm"
open FDSE BSND_NAME 0
open FDSE WAV_NAME 1
get RIFFSIZE ASIZE 1
math RIFFSIZE += 70
set FMTSIZE long 50
get DATA_SIZE ASIZE 1
Goto -50 0
get CODEC_ID short
get CHANNELS short
get FREQUENCY long
get BPS long
get ALIGN short
get UNKNOWN1 long
get UNKNOWN2 long
get UNKNOWN3 long
get UNKNOWN4 long
get UNKNOWN5 long
get UNKNOWN6 long
get UNKNOWN7 long
get UNKNOWN8 long
get UNKNOWN9 long
putVarChr MEMORY_FILE 78 0
log MEMORY_FILE 0 0
set MEMORY_FILE binary "\x52\x49\x46\x46\x00\x00\x00\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x64\x61\x74\x61\x00\x00\x00\x00"
putVarChr MEMORY_FILE 4 RIFFSIZE long
putVarChr MEMORY_FILE 16 FMTSIZE long
putVarChr MEMORY_FILE 20 CODEC_ID short
putVarChr MEMORY_FILE 22 CHANNELS short
putVarChr MEMORY_FILE 24 FREQUENCY long
putVarChr MEMORY_FILE 28 BPS long
putVarChr MEMORY_FILE 32 ALIGN short
putVarChr MEMORY_FILE 34 UNKNOWN1 long
putVarChr MEMORY_FILE 38 UNKNOWN2 long
putVarChr MEMORY_FILE 42 UNKNOWN3 long
putVarChr MEMORY_FILE 46 UNKNOWN4 long
putVarChr MEMORY_FILE 50 UNKNOWN5 long
putVarChr MEMORY_FILE 54 UNKNOWN6 long
putVarChr MEMORY_FILE 58 UNKNOWN7 long
putVarChr MEMORY_FILE 62 UNKNOWN8 long
putVarChr MEMORY_FILE 66 UNKNOWN9 long
putVarChr MEMORY_FILE 74 DATA_SIZE long
append
log MEMORY_FILE 0 DATA_SIZE 1
get NAME BASENAME
string NAME -= "_msadpcm"
string NAME += ".wav"
set FULLSIZE long RIFFSIZE
math FULLSIZE += 8
log NAME 0 FULLSIZE MEMORY_FILE
hi
it is not working

The Evil Within *.streamed files extracted with quickBMS. But *..msadpcm files have been obtained.
help
## Post #29
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2017-07-11T20:51:24+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

Read second line from script, you need *.bsnd extracted from *.tangoresource too, not only *.msadpcm
## Post #30
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2017-10-27T22:51:57+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

Anyone know how to properly extract the new colusses? it uses the WWise music system this time so not sure if the proper file names can be added this time.
## Post #31
- Username: atrina
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 02, 2017 7:25 am
- Post datetime: 2019-02-20T20:14:04+00:00
- Post Title: Re: idTech 5 Audio (.streamed)

> Reply from spider91 ↑Sun Mar 01, 2015 12:54 am at Sun Mar 01, 2015 12:54 am
>
> 
It will restore headers to get playable adpcm .wav's
Code: Select all# The Evil Within adpcm script (PC)
# Put .bsnd (extracted from .tangoresource) and .msadpcm (extracted from .streamed) files in the same dir and use .bsnd as input
# Written by spider91
# script for QuickBMS http://quickbms.aluigi.org
idstring "bsnf"
get BSND_NAME FILENAME
get WAV_NAME BASENAME
string WAV_NAME -= "_msadpcm"
string WAV_NAME += ".msadpcm"
open FDSE BSND_NAME 0
open FDSE WAV_NAME 1
get RIFFSIZE ASIZE 1
math RIFFSIZE += 70
set FMTSIZE long 50
get DATA_SIZE ASIZE 1
Goto -50 0
get CODEC_ID short
get CHANNELS short
get FREQUENCY long
get BPS long
get ALIGN short
get UNKNOWN1 long
get UNKNOWN2 long
get UNKNOWN3 long
get UNKNOWN4 long
get UNKNOWN5 long
get UNKNOWN6 long
get UNKNOWN7 long
get UNKNOWN8 long
get UNKNOWN9 long
putVarChr MEMORY_FILE 78 0
log MEMORY_FILE 0 0
set MEMORY_FILE binary "\x52\x49\x46\x46\x00\x00\x00\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x64\x61\x74\x61\x00\x00\x00\x00"
putVarChr MEMORY_FILE 4 RIFFSIZE long
putVarChr MEMORY_FILE 16 FMTSIZE long
putVarChr MEMORY_FILE 20 CODEC_ID short
putVarChr MEMORY_FILE 22 CHANNELS short
putVarChr MEMORY_FILE 24 FREQUENCY long
putVarChr MEMORY_FILE 28 BPS long
putVarChr MEMORY_FILE 32 ALIGN short
putVarChr MEMORY_FILE 34 UNKNOWN1 long
putVarChr MEMORY_FILE 38 UNKNOWN2 long
putVarChr MEMORY_FILE 42 UNKNOWN3 long
putVarChr MEMORY_FILE 46 UNKNOWN4 long
putVarChr MEMORY_FILE 50 UNKNOWN5 long
putVarChr MEMORY_FILE 54 UNKNOWN6 long
putVarChr MEMORY_FILE 58 UNKNOWN7 long
putVarChr MEMORY_FILE 62 UNKNOWN8 long
putVarChr MEMORY_FILE 66 UNKNOWN9 long
putVarChr MEMORY_FILE 74 DATA_SIZE long
append
log MEMORY_FILE 0 DATA_SIZE 1
get NAME BASENAME
string NAME -= "_msadpcm"
string NAME += ".wav"
set FULLSIZE long RIFFSIZE
math FULLSIZE += 8
log NAME 0 FULLSIZE MEMORY_FILE

hi

How do I return the header?
