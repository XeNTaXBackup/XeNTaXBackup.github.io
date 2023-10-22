## Post #1
- Username: Tyce2
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-28T09:36:22+00:00
- Post Title: Castlevania: Lords of Shadow

This is a bms script to extract the assets of Castlevania: Lords of Shadow
I tested this on the ps3 files.

```
idstring BFPK
get version long
get files long
savepos TMP
for i = 0 < files
goto TMP
get NSIZE long
getdstring name NSIZE
get size long
get offset long
savepos TMP
goto offset
get zsize long
savepos OFFSET
if zsize == size
log name offset zsize
else
clog name offset zsize size
endif
goto TMP
next i


```
## Post #2
- Username: dogkarl
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Sep 10, 2010 2:56 pm
- Post datetime: 2010-09-30T06:49:33+00:00
- Post Title: Castlevania: Lords of Shadow

Great job! I wonder if it'll works on XBOX360 files.
## Post #3
- Username: tommy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 05, 2010 5:11 am
- Post datetime: 2010-10-04T21:27:45+00:00
- Post Title: Castlevania: Lords of Shadow

It doesn't work for X360 version, or maybe it only works for demo files?

I get error: incomplete input file number 0, can't read xxxxxxxx bytes.

However when used with -l parameters, it lists file list correctly, so it seem it doesn't extract data...
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-10-04T21:49:38+00:00
- Post Title: Castlevania: Lords of Shadow

there's a typo in the script. 

change

> log name ofset size

to 
```
log name offset size
```


?
## Post #5
- Username: tommy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 05, 2010 5:11 am
- Post datetime: 2010-10-04T21:57:53+00:00
- Post Title: Castlevania: Lords of Shadow

Well it actually works, but I get error when trying to extract Music.packed, first file has space in its file name. Could that be an issue? Data00 for example worked fine.

And change ofset to offset didn't work 

EDIT: So English.packed didn't work either, and there was no space in filename....Hmm what could it be? quickbms -l parameter does however work for all files, including English.packed and Music.packed. But extracting works with Data00.packed, and I imagine with Data01.packed as well...

Here's verbose log:

```
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open input file English.packed
- open script los.bms
READLINE 1   idstring BFPK
READLINE 2   get version long
             >set version (0) to version
READLINE 3   get files long
             >set files (1) to files
READLINE 4   savepos TMP
             >set TMP (2) to TMP
READLINE 5   for i = 0 < files
             >set i (3) to i
             >set 0 (4) to 0x00000000
             >set i (3) to i
             >set files (1) to files
READLINE 6   goto TMP
             >set TMP (2) to TMP
READLINE 7   get NSIZE long
             >set NSIZE (5) to NSIZE
READLINE 8   getdstring name NSIZE
             >set name (6) to name
             >set NSIZE (5) to NSIZE
READLINE 9   get size long
             >set size (7) to size
READLINE 10  get offset long
             >set offset (8) to offset
READLINE 11  savepos TMP
             >set TMP (2) to TMP
READLINE 12  goto offset
             >set offset (8) to offset
READLINE 13  get zsize long
             >set zsize (9) to zsize
READLINE 14  savepos OFFSET
             >set offset (8) to offset
READLINE 15  if zsize == size
             >set zsize (9) to zsize
             >set size (7) to size
READLINE 16  log name offset size
             >set name (6) to name
             >set offset (8) to offset
             >set size (7) to size
READLINE 17  else
READLINE 18  clog name offset zsize size
             >set name (6) to name
             >set offset (8) to offset
             >set zsize (9) to zsize
             >set size (7) to size
READLINE 19  endif
READLINE 20  goto TMP
             >set TMP (2) to TMP
READLINE 21  next i
             >set i (3) to i
- set output folder ./Test/

  offset   filesize   filename
------------------------------
             .start_bms start: -1 0 0

00000000 1   idstring BFPK

00000004 2   get version long
             >set version (0) to 0x00000000

00000008 3   get files long
             >set files (1) to 0x00000246

0000000c 4   savepos TMP
             >set TMP (2) to 0x0000000c
- variable i seems uninitialized, I use its name
             >get i (3) i
             >get 0 (4) 0x00000000
             >set i (3) to 0x00000000
             .start_bms start: 6 0 0

0000000c 5   for i = 0 < files
             >get i (3) 0x00000000
             >get files (1) 0x00000246
             condition < is met

0000000c 6   goto TMP
             >get TMP (2) 0x0000000c
             >get TMP (2) 0x0000000c

0000000c 7   get NSIZE long
             >set NSIZE (5) to 0x00000029

00000010 8   getdstring name NSIZE
             >get NSIZE (5) 0x00000029
             >set name (6) to sounds/voices/english/babba_off_msg_1.ogg

00000039 9   get size long
             >set size (7) to 0x000076f7

0000003d 10  get offset long
             >set offset (8) to 0x00008e17

00000041 11  savepos TMP
             >set TMP (2) to 0x00000041

00000041 12  goto offset
             >get offset (8) 0x00008e17
             >get offset (8) 0x00008e17

00008e17 13  get zsize long
             >set zsize (9) to 0x5367674f

00008e1b 14  savepos OFFSET
             >set offset (8) to 0x00008e1b

00008e1b 15  if zsize == size
             >get zsize (9) 0x5367674f
             >get size (7) 0x000076f7
             condition == is not met
             .start_bms start: 17 1 0
             .start_bms end: 17 1 0 (ret 18)
             .start_bms start: 19 0 0

00008e1b 18  clog name offset zsize size
             >get name (6) sounds/voices/english/babba_off_msg_1.ogg
             >get offset (8) 0x00008e1b
             >get zsize (9) 0x5367674f
             >get size (7) 0x000076f7
  00008e1b 30455      sounds/voices/english/babba_off_msg_1.ogg

Error: incomplete input file number 0, can't read 1362753026 bytes.
       anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted


Note that if both the scripts and your files are correct then it's possible
that the script needs a newer version of QuickBMS, in which case download it:

  http://aluigi.org/quickbms
```
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-10-05T02:16:25+00:00
- Post Title: Castlevania: Lords of Shadow

it was a type just correct the one word offset it was a copy paste error.
i edited my first post try it now.
## Post #7
- Username: tommy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 05, 2010 5:11 am
- Post datetime: 2010-10-05T02:24:29+00:00
- Post Title: Castlevania: Lords of Shadow

It still didn't work.

However this script did (took from Clive Barker's Jericho)

```
Goto 8 0 ;
Get FNum Long 0 ;
For n = 1 to FNum ;
Get FNLen Long 0 ;
GetDString FN FNLen 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Log FN FS FO FSO FOO ;
Next n ;
```
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-10-05T02:40:44+00:00
- Post Title: Castlevania: Lords of Shadow

I don't have the full game only the one pac file they gave me glad to hear the other script worked tho.
## Post #9
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2010-10-05T20:51:22+00:00
- Post Title: Castlevania: Lords of Shadow

¿and to create a  new *.packed file? i want to join dvd1 and dvd 2 packages.

thanks for the scripts.
## Post #10
- Username: viperxp
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 01, 2011 7:15 pm
- Post datetime: 2011-01-01T12:47:05+00:00
- Post Title: Castlevania: Lords of Shadow

hello script helped me managed to unpack everything but I need to wrap it back again I tried to translate the lyrics, and now try whether it works
## Post #11
- Username: 3pacalypse
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Jul 08, 2010 10:17 am
- Post datetime: 2011-06-22T05:50:53+00:00
- Post Title: Castlevania: Lords of Shadow

Please tell us how to pack it back again!
## Post #12
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-23T18:40:34+00:00
- Post Title: Castlevania: Lords of Shadow

That scrip it could be use also for repack, but there is 1 problem with filesize of some files. Bu they are exact the same size like it was just after extract:
Please help ?

```
       the reimport option acts as a reimporter and so you cannot reinsert a
       file if it's bigger than the original otherwise it will overwrite the
       rest of the archive:
         new size: 104229
         old size: 102588

```


EDIT : This is strange i have my file modded and it has 30KB less than the oringal and still telling me new file is bigger. Anyone seen this before ?
## Post #13
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-24T06:23:33+00:00
- Post Title: Castlevania: Lords of Shadow

please anyone ???
## Post #14
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2012-07-06T20:11:25+00:00
- Post Title: Castlevania: Lords of Shadow

Guys I am having the same problem that michalss friend, when you import the file contents Data00.packed some files show the error message stating that the size is different from the original, but in my case these files are not edited, or are unique how can they be bigger?
Would fix this?

```
       the reimport option acts as a reimporter and so you cannot reinsert a
       file if it's bigger than the original otherwise it will overwrite the
       rest of the archive:
         new size: 141 (189)
         old size: 126 (189)

- do you want to skip this file? (y/N)

```


PS
File size English.txt was around 60 ~ 63KB larger than the original and was able to import successfully.
## Post #15
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-01-31T10:11:00+00:00
- Post Title: Castlevania: Lords of Shadow

I have written a script that should match the format at 100% (music.packed included):
[http://aluigi.altervista.org/papers/bms ... evania.bms](http://aluigi.altervista.org/papers/bms/others/castlevania.bms)
## Post #16
- Username: mrvan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 26, 2011 1:01 am
- Post datetime: 2013-02-23T22:52:58+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from aluigi
>
> I have written a script that should match the format at 100% (music.packed included):
http://aluigi.altervista.org/papers/bms ... evania.bms

Tried your link, and it didn't work for me.
## Post #17
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-06T13:26:42+00:00
- Post Title: Re: Castlevania: Lords of Shadow

it has been tested with an archive of over 600 megabyte of which I don't remember the name.

anyway what exact error message you receive?
## Post #18
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2013-07-31T17:34:17+00:00
- Post Title: Re: Castlevania: Lords of Shadow

The PC demo available from Steam.
Unfortunately the dat files (.packed on console) still have BFPK header, but the version is 3 (not 0 or 1), and I cannot see the filenames inside the file.
Maybe encrypted or compressed.
## Post #19
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-07-31T20:28:23+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Well i see names like (7C66E2C3D83B12F2.bik, 07E3A945F071A231.bik) in BIK folder. Maybe file names in archives just hashed?

Edited: Hashed video file names (FNV64-1a)
## Post #20
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-07-31T20:28:49+00:00
- Post Title: Re: Castlevania: Lords of Shadow

evin
OffZip - worked
zlib
English Text - [http://pastebin.com/KQ0bSxTE](http://pastebin.com/KQ0bSxTE)
But filetable encrypted =(

Ekey, там же еще должны быть смещения и размеры. Тоже пошифрованы. Так-то можно было бы начать перевод, ибо текст полный в демке. Около 400 новых строк по сравнения с PS3-версией.
## Post #21
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-01T10:27:41+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Well table really encrypted > it's AES / 256 / CBC mode 

see below
## Post #22
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-01T14:24:49+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Done.

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "BFPK"
get VERSION long
get TABLESIZE long
math TABLESIZE += 16
savepos TABLEOFFSET

callfunction TableDecrypt 1

getdstring TRASH 0x10 MEMORY_FILE
get FILES long MEMORY_FILE

for i = 0 < FILES
    get NSIZE long MEMORY_FILE
    getdstring NAME NSIZE MEMORY_FILE
    get SIZE long MEMORY_FILE
    get OFFSET long MEMORY_FILE
	
    if VERSION = 2
        log NAME OFFSET SIZE
    elseif VERSION = 3
        goto OFFSET
        get ZSIZE long
        savepos OFFSET
        clog NAME OFFSET ZSIZE SIZE
    endif
next i

startfunction TableDecrypt
    encryption aes_256_cbc "\x50\x43\x56\x80\x72\x73\xEE\x6F\xF1\x44\xF3\x6E\xEA\xDF\x79\x43\x6C\x69\x6D\x61\x78\x53\x74\x75\x64\x69\x6F\x73\x32\x30\x31\x33"
    log MEMORY_FILE TABLEOFFSET TABLESIZE
    encryption "" ""
endfunction
```
## Post #23
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2013-08-01T18:31:59+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Ekey, Haoose :
## Post #24
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-08-02T05:26:12+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Ekey, not work pack =(
P.S. Что-то не до конца разобрано видимо, запаковать не вышло по этому алгоритму. Пробовал поместить измененный файл в конец dat-файла. Игра не стартует. Хотя измененный файл корректно распаковывется твоим скриптом. Где-то еще проверка есть. Или CRC, или может быть последовательность файлов имеет значение.
## Post #25
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-02T06:26:47+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Edited: Reimport work great. Checked.
## Post #26
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2013-08-28T11:28:05+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Ekey
>
> Edited: Reimport work great. Checked.

How you did it? i can't i get errors
example:

unpacked the file Data00.dat with your script, this worked great and i want to add again the file scripts\preload_lua.lbt, i did:

> quickbms.exe -w -r castlevania.bms unpacked\scripts\preload_lua.lbt Data00.dat

and i get the error:

> - REIMPORT mode enabled!
>
> - open input file d:\Program Files (x86)\casteldata\unpacked\scripts\preload_lua
>
> .lbt
>
> - open script castlevania.bms
>
> - set output folder Data00.dat
>
> - the folder doesn't exist, do you want to create it (y/N)?:

Any idea? 

Thanks
## Post #27
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-08-28T13:56:37+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Savage
Try:

```
quickbms.exe -w -r castlevania.bms Data00.dat unpacked\
```
## Post #28
- Username: benzinjiq snake
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jul 18, 2011 10:07 pm
- Post datetime: 2013-08-28T19:59:32+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Hello, can anyone give me cyrillic fonts for the game? I've made Bulgarian translation for PS3 and 360, but I cannot adapt the fonts from console versions to PC version. I see here some of you guys speak Russian and if you share your fonts from russian localizations I'll apreceate your help. Thank you in advance. 

Edit: Fonts are stored in Data00.dat
## Post #29
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2013-08-29T08:22:51+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Haoose
>
> Savage
Try:
Code: Select allquickbms.exe -w -r castlevania.bms Data00.dat unpacked\

Thanks!! works great
## Post #30
- Username: benzinjiq snake
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-08-29T18:44:21+00:00
- Post Title: Re: Castlevania: Lords of Shadow

benzinjiq snake
Rus Fonts
[http://yadi.sk/d/BXSj5eG48TzwJ](http://yadi.sk/d/BXSj5eG48TzwJ)
## Post #31
- Username: benzinjiq snake
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jul 18, 2011 10:07 pm
- Post datetime: 2013-08-30T11:36:39+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Haoose
>
> benzinjiq snake
Rus Fonts
http://yadi.sk/d/BXSj5eG48TzwJ

Thank you, good sir.
## Post #32
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2013-08-31T18:03:55+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Just released an Unpakke module for the game. As much as i get from the thread the xbox version doesn't use structure encryption?
I was reversing the Ultimate Edition, and there was XOR encryption... does anyone know if that's only on the UE or something?
## Post #33
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2013-09-01T15:29:26+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Would it be possible to decode (decrypt?) the config file as well in addition to the game archives, would be nice to know what's stored in that and possibly also the profile file.
(The game has two config files, one for settings and one for the user profile from what I can tell, also a .profile file type which might be checkpoint progress or something.)

Should be safe to upload since it's generated by the game and not part of the default files plus it's just a config and probably contains plain text once decoded but it would be fun to know what those contain even if it can't be repacked for making modifications or such. 

[http://www41.zippyshare.com/v/54172177/file.html](http://www41.zippyshare.com/v/54172177/file.html)
(The .localconfig file from the User\Appdata\MercurySteam folder and the .cfg from the Steam profile\user folder.)

Just asking, have been thinking for a few days whether to post about it or not and now I decided to do it, it might not be anything significant in those files at all but it would be fun to know what those actually do contain if they can be decoded without breaking the entire game or game engine down to get the data needed for such a task. 

Unsure if those files contains any profile specific or Steam specific info either but it's probably nothing important, heh.
(Probably just stuff for the game or the profile used for the game.)
## Post #34
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-01T15:43:43+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Here script for decrypt only castlevania.cfg.

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

get SIZE asize
encryption aes_256_cbc "\x50\x43\x56\x80\x72\x73\xEE\x6F\xF1\x44\xF3\x6E\xEA\xDF\x79\x43\x6C\x69\x6D\x61\x78\x53\x74\x75\x64\x69\x6F\x73\x32\x30\x31\x33"
log "castlevania.cfg.dec" 0 SIZE
```
## Post #35
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2013-09-01T18:55:19+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Thank you, that will do nicely. 

EDIT: That's a lot of useful settings and info, this is quite interesting.
## Post #36
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-01T20:45:49+00:00
- Post Title: Re: Castlevania: Lords of Shadow

I dunno what the algo used for .localconfig. Maybe aes with other key. I can't check because pirated (ALI213, FLT / Skidrow) versions dont work for me, but demo work perfect.
## Post #37
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2013-09-02T05:43:41+00:00
- Post Title: Re: Castlevania: Lords of Shadow

anyone know how to make the .dds and .mst font files? I wanna localize this game but stuck with .mst files
## Post #38
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2013-09-02T06:44:57+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Ekey
>
> I dunno what the algo used for .localconfig. Maybe aes with other key. I can't check because pirated (ALI213, FLT / Skidrow) versions dont work for me, but demo work perfect.

From what I could tell by the decrypted config file it contains nearly all settings minus the screen resolution so the .localconfig probably only contains that and maybe one or two other things.

The CFG contained everything from the game settings (Including FOV even.) to the key bindings (Both gamepad and keyboard.) and even a few things related to some multiplayer modes and other odd info (Localization and references to the KONAMI code the console version had, but I don't think it can be activated with a keyboard from what I've tried.) so that's been very useful to have available.
## Post #39
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2013-09-02T09:17:26+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Here's what Castlevania.localcfg contains:

```

gvWindowMaximized              = 0                                   ### Whether the window is maximized
WindowPosY                     = 90                                  ### Window y position
WindowPosX                     = 80                                  ### Window x position
WindowHeight                   = 720                                 ### Window width
WindowWidth                    = 1280                                ### Window height
FullScreen                     = 1                                   ### 0 = Windowed mode, 1 = Fullscreen mode
VideoWidth                     = 1024                                ### Fullscreen width
VideoHeight                    = 768                                 ### Fullscreen height

## End
```
## Post #40
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-02T11:35:14+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Well nothing interesting...
## Post #41
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2013-09-03T10:31:54+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Ekey
>
> Well table really encrypted > it's AES / 256 / CBC mode 

see below

Nicely done, buddy
## Post #42
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-09-11T07:03:35+00:00
- Post Title: Re: Castlevania: Lords of Shadow

The Ultimate Edition uses a variant of the format, that isn't (yet) supported by the script (no names or TOC in header).
Can somebody please take a quick look? 
[http://www.putlocker.com/file/68387889704A090D](http://www.putlocker.com/file/68387889704A090D)
Thanks
## Post #43
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-09-11T07:06:30+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Whoops, didn't see the other pages of this topic  Disregard previous post.
## Post #44
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2013-11-02T04:55:31+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Seeing as Lords of Shadow 2 Demo is out, I wanted to extract the music from it, but none of the scripts from here seem to work, the Jericho script posted on first page however only extracts 1 track before returning an error. Based on my inspection of the file in hex, there's 12 tracks inside.

Can anyone take a look at it and see if you could make a script to extract it?
[http://www.mediafire.com/download/rw0cj ... sic.packed](http://www.mediafire.com/download/rw0cjm8u927x0vr/Music.packed)

And another, main data file this time, none of the scripts (not even the Jericho one) were able to extract anything from it. Taking a glance at it in hex editor reveals it's not encrypted.
[http://www.mediafire.com/download/62155 ... a00.packed](http://www.mediafire.com/download/621555wpo8ajrkp/Data00.packed)
## Post #45
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-02T07:43:14+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Panzah
>
> Seeing as Lords of Shadow 2 Demo is out, I wanted to extract the music from it, but none of the scripts from here seem to work, the Jericho script posted on first page however only extracts 1 track before returning an error. Based on my inspection of the file in hex, there's 12 tracks inside.

Can anyone take a look at it and see if you could make a script to extract it?
http://www.mediafire.com/download/rw0cj ... sic.packed

And another, main data file this time, none of the scripts (not even the Jericho one) were able to extract anything from it. Taking a glance at it in hex editor reveals it's not encrypted.
http://www.mediafire.com/download/62155 ... a00.packed
Done.

Edited: [here](http://forum.xentax.com/viewtopic.php?p=89767#p89767)
## Post #46
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2013-11-02T08:59:24+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Thank you very much, will test it now.
And actually it's the PS3 version demo, but PC is supposed to be released soon along with pre-order page for LoS2.
Also Lords of Shadow - Mirror of Fate HD is coming to PC later this year too.
## Post #47
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-11-02T09:26:40+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Hm, for what version this script? Xbox version use chunk compression, zlibbed blocks - 64kb
## Post #48
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2013-11-02T09:42:40+00:00
- Post Title: Re: Castlevania: Lords of Shadow

It's for PS3 version, as that's the one I requested it for and uploaded example files of.

Also, it doesn't seem to work quite right. All files that are extracted that are EXACTLY 64 KB are broken. Music files simply cut off at points they shouldn't, textures are inopenable and such.
Script needs revision.
## Post #49
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-03T08:51:55+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Well here updated script.

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype unzip_dynamic

idstring "BFPK"
get VERSION long

if VERSION = 256
    get FILES long
elseif VERSION = 258
    get TABLESIZE long
    get FILES long
endif

for i = 0 < FILES
    get NSIZE long
    getdstring NAME NSIZE
    get SIZE long
    get OFFSET long
    get NULL long
    savepos TEMP

    if VERSION = 256
        log NAME OFFSET SIZE
    elseif VERSION = 258
	
        goto OFFSET
        get FULLZSIZE long
        savepos CHUNKOFFSET
		
        log MEMORY_FILE 0 0
        append
        set TEMPZSIZE long 0

        #Ugly part for decompress chunks :)

        do
            goto CHUNKOFFSET
            get CHUNKZSIZE long
            math TEMPZSIZE += CHUNKZSIZE
            math TEMPZSIZE += 4
            savepos OFFSET
            clog MEMORY_FILE OFFSET CHUNKZSIZE CHUNKZSIZE
            math CHUNKOFFSET += CHUNKZSIZE
            math CHUNKOFFSET += 4
        while TEMPZSIZE < FULLZSIZE
		
        append
        log NAME 0 SIZE MEMORY_FILE
        goto TEMP
    endif
next i
```
## Post #50
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2013-11-03T11:13:46+00:00
- Post Title: Re: Castlevania: Lords of Shadow

This one seems to work perfectly, much appreciated. Hopefully it will work on the final build of the game too.
## Post #51
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-03T18:44:37+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Panzah
>
> This one seems to work perfectly, much appreciated. Hopefully it will work on the final build of the game too.
I do not think that anything will change in final release.
## Post #52
- Username: cienislaw
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 30, 2013 5:22 am
- Post datetime: 2013-11-07T06:41:24+00:00
- Post Title: Re: Castlevania: Lords of Shadow

PC version probably wont use compressed chunks, most likely it will be the same format as for CLoS1. anyway, kudos Ekey, you make life of many ppl much easier;-)

scripts also works with X360 demo of CLos2.
## Post #53
- Username: McGregor II
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jun 29, 2010 8:21 am
- Post datetime: 2014-01-11T16:46:05+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Hey, I tried to reimport the Castlevania 1 files but it gives me error: wrong cammand-line argument (castlevania.txt) - that's how I named the script file. Here's my input in command-line: quickbms.exe -w -r Castlevania.txt (or bms I tried it too) Data00.dat folder_path\Data00\
## Post #54
- Username: cienislaw
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 30, 2013 5:22 am
- Post datetime: 2014-02-01T21:52:11+00:00
- Post Title: Re: Castlevania: Lords of Shadow

I take back what I said about PC version;-) C2 will have open world with no loading screens, so 64kb chunks makes now more sense. can't wait to see what they did!
## Post #55
- Username: cienislaw
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 30, 2013 5:22 am
- Post datetime: 2014-02-11T19:58:27+00:00
- Post Title: Re: Castlevania: Lords of Shadow

PC demo of C2 is out. data is in .packed archives which has one difference from a aluigi script - extra 4 nulls after each file entry in table. sadly texts are not final retail and DLC lang file in english is missing too. format didn't change, so get ready for translation.
## Post #56
- Username: namquang93
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-02-16T16:18:18+00:00
- Post Title: Re: Castlevania: Lords of Shadow

For PC:

```
get version long
get files long
savepos TMP
for i = 0 < files
#goto TMP
get NSIZE long
getdstring name NSIZE
get size long
get offset long
savepos TMP
goto offset
get zsize long
savepos OFFSET
if zsize == size
log name offset zsize
else
clog name offset zsize size
endif
goto TMP
get dummy long
next i
```
## Post #57
- Username: Isilfor
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Jul 20, 2010 12:01 am
- Post datetime: 2014-02-26T15:06:55+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Ekey
>
> Well here updated script.
Code: Select all# Seeing as Lords of Shadow 2 (PS3-DEMO) (PACKED format) 0.2
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype unzip_dynamic

idstring "BFPK"
get VERSION long

if VERSION = 256
    get FILES long
elseif VERSION = 258
    get TABLESIZE long
    get FILES long
endif

for i = 0 < FILES
    get NSIZE long
    getdstring NAME NSIZE
    get SIZE long
    get OFFSET long
    get NULL long
    savepos TEMP

    if VERSION = 256
        log NAME OFFSET SIZE
    elseif VERSION = 258
	
        goto OFFSET
        get FULLZSIZE long
        savepos CHUNKOFFSET
		
        log MEMORY_FILE 0 0
        append
        set TEMPZSIZE long 0

        #Ugly part for decompress chunks :)

        do
            goto CHUNKOFFSET
            get CHUNKZSIZE long
            math TEMPZSIZE += CHUNKZSIZE
            math TEMPZSIZE += 4
            savepos OFFSET
            clog MEMORY_FILE OFFSET CHUNKZSIZE CHUNKZSIZE
            math CHUNKOFFSET += CHUNKZSIZE
            math CHUNKOFFSET += 4
        while TEMPZSIZE < FULLZSIZE
		
        append
        log NAME 0 SIZE MEMORY_FILE
        goto TEMP
    endif
next i
This script works for full PC version of Castlevania - Lords of Shadow 2. 
Except 4,1 Gb file Data00.packed. 
Error: "memory allocation problem Not enough storage is available to process this command/"
- error is src\xalloc.h line 600^ xdbg_malloc()
## Post #58
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-02-26T23:44:46+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Isilfor
>
> 
This script works for full PC version of Castlevania - Lords of Shadow 2. 
Except 4,1 Gb file Data00.packed.

> Reply from Haoose
>
> For PC:
Code: Select allidstring BFPK
get version long
get files long
savepos TMP
for i = 0 < files
#goto TMP
get NSIZE long
getdstring name NSIZE
get size long
get offset long
savepos TMP
goto offset
get zsize long
savepos OFFSET
if zsize == size
log name offset zsize
else
clog name offset zsize size
endif
goto TMP
get dummy long
next i
## Post #59
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2014-02-27T00:29:24+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Tried the last bms for Pc with the big file Data00.packed (4,120Gb's) using quickbms_4gb_files last version i get:

> 0000000000019ba8 524416     2d/loading/book/i_menu_sw_relics_01-b.dds
>
> Error: the compressed zlib/deflate input is wrong or incomplete (-3)
>
> 
>
> Error: there is an error with the decompression
>
>        the returned output size is negative (-1)
## Post #60
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2014-02-27T01:16:28+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Thanks Ekey, Haoose for the updated scripts, I was able to get them working for Data00.packed by using quickbms_4gb_files.exe.

I see the high res detail textures in the 1 GB content\0\Data00.packed archive, but I haven't been able to locate the high res normal maps... can anyone confirm if they exist?
## Post #61
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2014-02-27T05:39:13+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Well that would explain why some surfaces are so pixelated up close, how unfortunate if that's so.
(Normal map texture being compressed and of a lower resolution than the diffuse/base texture if that's all that's in the high-res archive.)
## Post #62
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-02-27T10:54:29+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Savage
>
> Tried the last bms for Pc with the big file Data00.packed (4,120Gb's) using quickbms_4gb_files last version i get:

0000000000019ba8 524416     2d/loading/book/i_menu_sw_relics_01-b.dds
Error: the compressed zlib/deflate input is wrong or incomplete (-3)

Error: there is an error with the decompression
       the returned output size is negative (-1)

I've got extractly the same error when using Haoose's updated script.
## Post #63
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-27T12:21:27+00:00
- Post Title: Re: Castlevania: Lords of Shadow

I check it later.
## Post #64
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-27T15:10:41+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Done.

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype unzip_dynamic

idstring "BFPK"
get VERSION short
get FLAG short
get FILES long

for i = 0 < FILES
    get NSIZE long
    getdstring NAME NSIZE
    get SIZE long
    get OFFSET longlong
    savepos TEMP
	
	if FLAG = 0
        log NAME OFFSET SIZE
	elseif FLAG = 1
        goto OFFSET
        get ZSIZE long
        savepos OFFSET
        clog NAME OFFSET ZSIZE SIZE
    endif
    goto TEMP
next i
```
## Post #65
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-02-27T17:19:27+00:00
- Post Title: Re: Castlevania: Lords of Shadow

it's weird, I got this message and can not get the last txt files.



And also, at first I tried using Haoose's bms script, the game seems be able to load the extracted files, but when I use your script the game did not. I checked the extracted files and they seems broken or compressed. You can see the left wav files are not read/indentityable and the right one (extracted from Haoose's script) is fine.
## Post #66
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-27T18:04:39+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Hm strange. You can see for example : on my screen offset for file language/portoguese.txt is 0x10674a85c but on your screen 0x10674a858 - difference 4. Seems not all files with FLAG 1 is compressed or bug with OFFSET. I check it later. Try this one

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype unzip_dynamic

idstring "BFPK"
get VERSION short
get FLAG short
get FILES long

for i = 0 < FILES
    get NSIZE long
    getdstring NAME NSIZE
    get SIZE long
    get OFFSET longlong
    savepos TEMP
    
    goto OFFSET
    get ZSIZE long
    savepos OFFSET
	
    if ZSIZE == SIZE
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
    goto TEMP
next i
```
## Post #67
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-02-27T19:49:29+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Packer for localisation coming in March =)
## Post #68
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-02-28T02:25:58+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Ekey
>
> Hm strange. You can see for example : on my screen offset for file language/portoguese.txt is 0x10674a85c but on your screen 0x10674a858 - difference 4. Seems not all files with FLAG 1 is compressed or bug with OFFSET. I check it later. Try this one
Code: Select all# Castlevania: Lords of Shadow 2 (PC) (PACKED format) 0.1a
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype unzip_dynamic

idstring "BFPK"
get VERSION short
get FLAG short
get FILES long

for i = 0 < FILES
    get NSIZE long
    getdstring NAME NSIZE
    get SIZE long
    get OFFSET longlong
    savepos TEMP
    
    goto OFFSET
    get ZSIZE long
    savepos OFFSET
	
    if ZSIZE == SIZE
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
    goto TEMP
next i

extracted perfectly with this bms script   

game seems load extracted files but unfortunately as soon as enters the first screen, it crashed.
## Post #69
- Username: Isilfor
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Jul 20, 2010 12:01 am
- Post datetime: 2014-03-01T11:03:40+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from namquang93
>
> 
game seems load extracted files but unfortunately as soon as enters the first screen, it crashed.
Same problem. Also tried to replace some textures in the archive - game crashed after intro video.
## Post #70
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-03-01T20:19:16+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Need create new packed-file
## Post #71
- Username: Isilfor
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Jul 20, 2010 12:01 am
- Post datetime: 2014-03-02T05:51:09+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Any idea, how to change player model?
I tried:
1. Change parameter "_Dracula_Skin" in my save game. But it can be only "Alucard" or "Dracula". Affects armor color.
2. Replacing mesh files in the packed file. dracula.msh to draculaold.msh for ex. This method crashes game after intro video.
I think the player model is defined in the script of each level (\levels\levelname\scripts). But scripts are compiled lua and "unluac" does not work for them .
## Post #72
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2014-03-04T18:45:44+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Hi! I was able to extract all the files from the 4gb archieve but i have problem to open the dds textures..   what format is really?
Thank you in advance!
Sorry for my English
## Post #73
- Username: namquang93
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-03-05T09:30:21+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Packer for localisation
[http://games-gen.com/soft/CastlevaniaLo ... Packer.rar](http://games-gen.com/soft/CastlevaniaLoS2-PC-Localisation-Packer.rar)
Edit files in folder files
Press button
Copy new packed-file to folder mods/
Run game =)
## Post #74
- Username: Isilfor
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Jul 20, 2010 12:01 am
- Post datetime: 2014-03-09T18:12:17+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Haoose
>
> Packer for localisation
Is it possible to make packer for other game files? Textures, models etc.
## Post #75
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-03-10T16:09:50+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Yes. Of course. Easy file-format
## Post #76
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2014-03-10T22:32:31+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Ekey
>
> Hm strange. You can see for example : on my screen offset for file language/portoguese.txt is 0x10674a85c but on your screen 0x10674a858 - difference 4. Seems not all files with FLAG 1 is compressed or bug with OFFSET. I check it later. Try this one
Code: Select all# Castlevania: Lords of Shadow 2 (PC) (PACKED format) 0.1a
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype unzip_dynamic

idstring "BFPK"
get VERSION short
get FLAG short
get FILES long

for i = 0 < FILES
    get NSIZE long
    getdstring NAME NSIZE
    get SIZE long
    get OFFSET longlong
    savepos TEMP
    
    goto OFFSET
    get ZSIZE long
    savepos OFFSET
	
    if ZSIZE == SIZE
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
    goto TEMP
next i

A silly request..what i need to change to extract the data?, NOT decompress, i want the files compressed.
Thanks.
## Post #77
- Username: benzinjiq snake
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jul 18, 2011 10:07 pm
- Post datetime: 2014-03-11T12:21:04+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Haoose
>
> Packer for localisation
http://games-gen.com/soft/CastlevaniaLo ... Packer.rar
Edit files in folder files
Press button
Copy new packed-file to folder mods/
Run game =)

Can you make it to support Xbox360 font files? They are the same, just the names are:

x360arial20.alpha.dds 
x360arial20.alpha.mst
x360bradley47.alpha.dds
x360bradley47.alpha.mst

Otherwise your tool works with 360, too. No problem there. Just doesn't support the font files.
## Post #78
- Username: benzinjiq snake
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-03-11T21:33:27+00:00
- Post Title: Re: Castlevania: Lords of Shadow

benzinjiq snake
Check: [http://games-gen.com/soft/CastlevaniaLo ... Packer.rar](http://games-gen.com/soft/CastlevaniaLoS2-PC-X360-Localisation-Packer.rar)
## Post #79
- Username: cienislaw
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 30, 2013 5:22 am
- Post datetime: 2014-03-25T21:37:01+00:00
- Post Title: Re: Castlevania: Lords of Shadow

DLC content 4 Revelations is complete 'resource pack' to which games switch's when DLC is activated. to make your mod working for DLC just put it in DLC folder for example /content/4/ and name Data01.packed - works like a charm. there is also DataEnglish.packed (in console 64kb chunk format) which contains one localized texture ('no wolves allowed'). didn't tried yet to override, but even if had to be replaced its just 326KB.
## Post #80
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2014-03-28T21:47:52+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Hello 
I wanted to open the file Castlevania Lords of Shadow 2 \ content \ 0 \ Data00.packed (1036 343 kb)


[quote]incomplete input file number 0, can't read 4 bytes.
anyway don't worry, it's possible that the BMS script has been written
to exit in this way if it's reached the end of the archive so check it
or contact its author or verify that all the files have been extracted
[/quote]


An idea?
## Post #81
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-04-08T02:59:51+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Ekey
>
> Done.
Code: Select all# Castlevania: Lords of Shadow - Ultimate Edition (PC-DEMO) (DAT format) 0.3
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "BFPK"
get VERSION long
get TABLESIZE long
math TABLESIZE += 16
savepos TABLEOFFSET

callfunction TableDecrypt 1

getdstring TRASH 0x10 MEMORY_FILE
get FILES long MEMORY_FILE

for i = 0 < FILES
    get NSIZE long MEMORY_FILE
    getdstring NAME NSIZE MEMORY_FILE
    get SIZE long MEMORY_FILE
    get OFFSET long MEMORY_FILE
	
    if VERSION = 2
        log NAME OFFSET SIZE
    elseif VERSION = 3
        goto OFFSET
        get ZSIZE long
        savepos OFFSET
        clog NAME OFFSET ZSIZE SIZE
    endif
next i

startfunction TableDecrypt
    encryption aes_256_cbc "\x50\x43\x56\x80\x72\x73\xEE\x6F\xF1\x44\xF3\x6E\xEA\xDF\x79\x43\x6C\x69\x6D\x61\x78\x53\x74\x75\x64\x69\x6F\x73\x32\x30\x31\x33"
    log MEMORY_FILE TABLEOFFSET TABLESIZE
    encryption "" ""
endfunction

I want to translate (localization) Castlevania: Lords of Shadow, and use of the BMS script's Ekey and uppack sucessfully  but when used reimporter 3 file: " english.txt "," arial20.alpha.dds "," bradley47.alpha.dds " the capacity increased file size and game not working. if only import "english.txt" the file size "Data00.dat" no change but could not get into the game. Thanks for any help!
## Post #82
- Username: Scofield
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Jul 13, 2014 5:27 am
- Post datetime: 2014-07-14T09:05:21+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Hi, 

Friends I ps3 user. 
I'm having trouble Data00.Packed reimport. 
I would like your help in this regard.
## Post #83
- Username: Sungam
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 31, 2009 2:35 pm
- Post datetime: 2014-08-09T21:13:17+00:00
- Post Title: Re: Castlevania: Lords of Shadow

What exactly is this xdbg_malloc() error in quickbms? I mean technically.
## Post #84
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-05-11T02:37:58+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Haoose
>
> Packer for localisation
http://games-gen.com/soft/CastlevaniaLo ... Packer.rar
Edit files in folder files
Press button
Copy new packed-file to folder mods/
Run game =)

Link is death  
Can you refresh please ?
## Post #85
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2015-05-11T23:23:04+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Taner038
>
> Haoose wrote:Packer for localisation
http://games-gen.com/soft/CastlevaniaLo ... Packer.rar
Edit files in folder files
Press button
Copy new packed-file to folder mods/
Run game =)

Link is death  
Can you refresh please ?
[http://games-gen.com/soft/CastlevaniaLo ... Packer.rar](http://games-gen.com/soft/CastlevaniaLoS2-PC-X360-Localisation-Packer.rar)
Edit files in folder files
Press button
Copy new packed-file to folder mods/
Run game =)
## Post #86
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-10-18T05:18:09+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Haoose
>
> 
http://games-gen.com/soft/CastlevaniaLo ... Packer.rar
Edit files in folder files
Press button
Copy new packed-file to folder mods/
Run game =)

Can you make it to support PS3 font files? They are the same, just the names are:

ps3arial20.alpha.dds 
ps3arial20.alpha.mst
ps3bradley47.alpha.dds
ps3bradley47.alpha.mst

Your tool works with ps3, too. No problem there. Just doesn't support the font files. Thanks for anyhelp!
## Post #87
- Username: shadowlonely1989
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2015-10-18T22:27:01+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from shadowlonely1989
>
> Can you make it to support PS3 font files?
Packer for localisation (PC/XBOX360/PS3)
[http://games-gen.com/soft/CastlevaniaLo ... Packer.rar](http://games-gen.com/soft/CastlevaniaLoS2-PC-X360-PS3-Localisation-Packer.rar)
Edit files in folder files
Press button
Copy new packed-file to folder mods/
Run game =)
## Post #88
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-10-20T00:14:44+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Haoose
>
> shadowlonely1989 wrote:Can you make it to support PS3 font files?
Packer for localisation (PC/XBOX360/PS3)
http://games-gen.com/soft/CastlevaniaLo ... Packer.rar
Edit files in folder files
Press button
Copy new packed-file to folder mods/
Run game =)

I tried to test on PC and Xbos360 patch, working with text and try to extract file with quickbms, working normal. But with ps3 patch, it show an error. Please help!
## Post #89
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2015-10-20T05:10:28+00:00
- Post Title: Re: Castlevania: Lords of Shadow

shadowlonely1989
Fixed. Check now.
## Post #90
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-10-20T05:50:46+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Haoose
>
> shadowlonely1989
Fixed. Check now.

Thank you very much!
## Post #91
- Username: humannos
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 07, 2015 2:54 pm
- Post datetime: 2015-11-07T06:57:50+00:00
- Post Title: Re: Castlevania: Lords of Shadow

How to encrypt castlevania.cfg back?
## Post #92
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-03-10T21:53:42+00:00
- Post Title: Re: Castlevania: Lords of Shadow

can anybody help me with this old script for castlevania los2
[http://www.mediafire.com/download/uuh4m ... OS_2_PC.7z](http://www.mediafire.com/download/uuh4m1fz8l38c3w/LOS_2_PC.7z)

the issue is that the imported models turns axis X mirrored wich is not correct.
## Post #93
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2016-08-13T19:26:16+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Localisation packer not work for me, ps3 show Unhandled error (466B0067)
english.txt :
[https://drive.google.com/file/d/0Bx23XH ... sp=sharing](https://drive.google.com/file/d/0Bx23XH_6oxY3ZHhoQ01TeGJFSWs/view?usp=sharing)
data.packed
[https://drive.google.com/file/d/0Bx23XH ... sp=sharing](https://drive.google.com/file/d/0Bx23XH_6oxY3SkNHUFVHdkdlakU/view?usp=sharing)
please help why not work ?!
## Post #94
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2016-08-14T19:49:58+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from dvoika
>
> Localisation packer not work for me, ps3 show Unhandled error (466B0067)
english.txt :
https://drive.google.com/file/d/0Bx23XH ... sp=sharing
data.packed
https://drive.google.com/file/d/0Bx23XH ... sp=sharing
please help why not work ?!

Fixed ps3 file: [https://dl.dropboxusercontent.com/u/495 ... Ps3.packed](https://dl.dropboxusercontent.com/u/4953836/Xentax/ShablonPs3.packed)
## Post #95
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2016-08-27T17:46:02+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Unhalder error. (4d650089)  

> Reply from evin
>
> dvoika wrote:Localisation packer not work for me, ps3 show Unhandled error (466B0067)
english.txt :
https://drive.google.com/file/d/0Bx23XH ... sp=sharing
data.packed
https://drive.google.com/file/d/0Bx23XH ... sp=sharing
please help why not work ?!

Fixed ps3 file: https://dl.dropboxusercontent.com/u/495 ... Ps3.packed
## Post #96
- Username: TERMINATOR2452
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 16, 2017 2:43 am
- Post datetime: 2017-03-15T20:03:29+00:00
- Post Title: Re: Castlevania: Lords of Shadow

hI, NEW HERE.
I been trying to get the debugmenu working in these xbox 360 games. I can only get it to work in Clive Barker's Jericho. By running it in preview mode. In the castlevania ones is it locked or something in the data file.
## Post #97
- Username: Dante00001
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 26, 2017 5:36 am
- Post datetime: 2017-03-25T21:39:48+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Hi guys! Help me, plz. I want to replace Castlevania's default XBOX button icon with PS3 icons. I've replaced them in file folder, packed file and put into created mod folder but nothing got changed. I would really appreciate some help!

Thank you! You're awesome!
## Post #98
- Username: Dante00001
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 26, 2017 5:36 am
- Post datetime: 2017-03-26T11:08:15+00:00
- Post Title: Re: Castlevania: Lords of Shadow

ok, I've managed to replace those icons and they show up correctly in game BUT text went crazy! It's unreadable! Can someone explain me why this happened? Does the  game uses some hash-sums to protect itself from altering any of the files?

Thank you!
## Post #99
- Username: Lorian Elder Prince
- Rank: n00b
- Number of posts: 12
- Joined date: Fri May 13, 2016 12:11 am
- Post datetime: 2018-08-01T10:16:55+00:00
- Post Title: Re: Castlevania: Lords of Shadow

My apologies for bumping such an old thread, but I can't seem to find anything related to my issue aside from another user asking help about what seems to be the same problem, and that's decades ago.
So to put it simply I've extracted the main data pack but all the .dds contained inside won't open normally, usually noesis does the trick but here even noesis doesn't recognize them.

So here are some samples, if someone could tell me what I'm supposed to do to fix them. Thanks in advance.

[http://www.mediafire.com/file/vs9bk0av2 ... in+dds.zip](http://www.mediafire.com/file/vs9bk0av2i615ko/godpaladin+dds.zip)
## Post #100
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-08-01T13:06:10+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Lorian Elder Prince
>
> So here are some samples, if someone could tell me what I'm supposed to do to fix them. Thanks in advance.
http://www.mediafire.com/file/vs9bk0av2 ... in+dds.zip
run this bms script on your samples to decompress them.  

```

comtype zlib_dynamic
get NAME basename
string NAME + _decmp.dds
get ZSIZE asize
math ZSIZE - 4
clog NAME 0x4 ZSIZE ZSIZE
```
## Post #101
- Username: Lorian Elder Prince
- Rank: n00b
- Number of posts: 12
- Joined date: Fri May 13, 2016 12:11 am
- Post datetime: 2018-08-02T08:24:21+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from AceWell
>
> 
run this bms script on your samples to decompress them.

Holy! You're amazing, thank you a lot!
## Post #102
- Username: ReginA
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 12, 2019 3:14 am
- Post datetime: 2019-08-07T21:13:15+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Does each DataXX.dat/.packed has fixed bite lenghs? Cuz I hardly lost myself with trying to change game scripts. Game crashes everytime with new archives. I even tried extract all archives and delete them like was with Jericho, but this doesn't work too. I can't inject debug script into data without crashes everytime on start. Checked PS3 and PC. Help.
## Post #103
- Username: ReginA
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 12, 2019 3:14 am
- Post datetime: 2019-08-07T21:24:05+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from TERMINATOR2452 ↑Thu Mar 16, 2017 4:03 am at Thu Mar 16, 2017 4:03 am
>
> 
hI, NEW HERE.
I been trying to get the debugmenu working in these xbox 360 games. I can only get it to work in Clive Barker's Jericho. By running it in preview mode. In the castlevania ones is it locked or something in the data file.

Like that? 
[https://youtu.be/gN79dWpX73E](https://youtu.be/gN79dWpX73E)

LoS has much, much more options from my researchers.
## Post #104
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2019-12-14T02:24:17+00:00
- Post Title: Re: Castlevania: Lords of Shadow

I've extracted all the files form Lords of Shadows 1 with no issues using quickbms, but I can't find Carmilla's files..

Am I missing something?

Cheers.
## Post #105
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2019-12-14T11:22:21+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from gep55 ↑Sat Dec 14, 2019 10:24 am at Sat Dec 14, 2019 10:24 am
>
> 
I've extracted all the files form Lords of Shadows 1 with no issues using quickbms, but I can't find Carmilla's files..

Am I missing something?

Cheers.

Don't worry, found the files
## Post #106
- Username: Big Boss
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jan 31, 2020 9:10 am
- Post datetime: 2020-01-31T01:22:35+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Hello guys, I'm Big Boss, new here, I work translating games from the Castlevania franchise, and I would like to know if any of you have a script to unpack and compress the Castlevania: Lords of Shadow 2 DLC Revelations, by Xbox 360, because this Script: [https://aluigi.altervista.org/bms/castlevania.bms](https://aluigi.altervista.org/bms/castlevania.bms) did not work for me, it presents an error in the half of the unpacking, and it does not recompact, I tried all that are in this Topic, and I couldn't, I need it, to fix some Localization errors of my language in the game , please help me, thank you ...
## Post #107
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2021-05-23T16:27:20+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Hello, impossible decompression of "Castlevania Lords of Shadow 2\content\0\Data00.packed", it must be the hd textures.

Any solutions/idea?
## Post #108
- Username: MaLDo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 28, 2012 12:27 pm
- Post datetime: 2021-05-26T07:47:42+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Hi, 

I've put some work in the BINK cinematics of this game. Those are 1280x720 at 25 fps without antialising. I've created versions at 4K@60 fps with antialiasing using a few AI tools.

Those new videos work because are separated files in the game folder. The only problem is with subtitles timing. They are syncronized using number of frames, so they appear in the wrong moment.

I've found the files where I can edit those timmings extracting files from Data00.pak using the BMS script in this thread. 

But can't find a way to import the modified files again without crashing the game. Normally, QuickBMS rises an error about new/old different size. But even maintaining the file size, the game crash in every loading screen.

Someone found the same problem in this thread. Is there an updated script to avoid this problem?

Thank you very much
## Post #109
- Username: MaLDo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 28, 2012 12:27 pm
- Post datetime: 2021-05-26T08:36:54+00:00
- Post Title: Re: Castlevania: Lords of Shadow

I want to add a gif to show the improvement in the cutscenes

[https://i.ibb.co/R4ykjmB/LOS-BINK.gif](https://i.ibb.co/R4ykjmB/LOS-BINK.gif)
## Post #110
- Username: MaLDo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 28, 2012 12:27 pm
- Post datetime: 2021-05-27T16:13:14+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Another comparisson

[https://i.ibb.co/FwpDrFf/LOS-BINK2.gif](https://i.ibb.co/FwpDrFf/LOS-BINK2.gif)

Someone knows who can I contact to find help?
## Post #111
- Username: someoneelse2
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 25, 2016 10:44 am
- Post datetime: 2022-11-09T23:08:15+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from Haoose ↑Wed Mar 05, 2014 5:30 pm at Wed Mar 05, 2014 5:30 pm
>
> 
Packer for localisation
http://games-gen.com/soft/CastlevaniaLo ... Packer.rar
Edit files in folder files
Press button
Copy new packed-file to folder mods/
Run game =)

Hello!
Does someone has this packer and willing to give new link?
games-gen seems to be down for some time , file unavailable.
Thanks!
## Post #112
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-10T18:12:03+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from someoneelse2 ↑Thu Nov 10, 2022 7:08 am at Thu Nov 10, 2022 7:08 am
>
> 
Does someone has this packer and willing to give new link?
games-gen seems to be down for some time , file unavailable.

Try this mirror [https://drive.google.com/file/d/1kQxWFN ... share_link](https://drive.google.com/file/d/1kQxWFNuapppoi5nxqNa8PW9doIqSG1CY/view?usp=share_link)
## Post #113
- Username: someoneelse2
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 25, 2016 10:44 am
- Post datetime: 2022-11-10T18:14:17+00:00
- Post Title: Re: Castlevania: Lords of Shadow

> Reply from ikskoks ↑Fri Nov 11, 2022 2:12 am at Fri Nov 11, 2022 2:12 am
>
> 
someoneelse2 wrote: ↑Thu Nov 10, 2022 7:08 am
Does someone has this packer and willing to give new link?
games-gen seems to be down for some time , file unavailable.


Try this mirror https://drive.google.com/file/d/1kQxWFN ... share_link

Google is blocking file download. it says its virus. Can you please upload to another host? I cant bypass google block

```

Only the owner is allowed to download infected files.

```
## Post #114
- Username: someoneelse2
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-10T18:24:38+00:00
- Post Title: Re: Castlevania: Lords of Shadow

Sure, here it is as an attachment:
[CastlevaniaLoS2-PC-Localisation-Packer.zip](https://xentaxbackup.github.io/file/23018_CastlevaniaLoS2-PC-Localisation-Packer.zip)
