## Post #1
- Username: bird
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 08, 2010 5:01 pm
- Post datetime: 2010-08-10T11:16:31+00:00
- Post Title: Mafia II SDS files?

Hi!

Anyone succeeded extracting text or other localization related text or data from *.sds files?
I downloaded the demo and I think this sds file could hold some valuable text

Thanks for helping me.
-Bird
## Post #2
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-08-10T11:40:30+00:00
- Post Title: Mafia II SDS files?

Yeah, i just came in to open thread about...

So i need to translate the game too, so I need the font file too - texture i guess.


My respects to anyone trying to help, i love you for that
## Post #3
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-08-10T11:43:40+00:00
- Post Title: Mafia II SDS files?

Zlbi compressed. So not a big deal.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2010-08-10T13:10:38+00:00
- Post Title: Mafia II SDS files?

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: bird
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 08, 2010 5:01 pm
- Post datetime: 2010-08-10T13:53:51+00:00
- Post Title: Mafia II SDS files?

Thanks, but how can I re-compress it again?
## Post #6
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-08-11T06:03:55+00:00
- Post Title: Mafia II SDS files?

okey, compressed file got decompressed - we need a tool for decompressing all of sds files or algorithm or like one how to decompress other ones too.

Second, we need to make it editable, with only decompressed format we can't edit text or other file.
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-08-11T15:20:11+00:00
- Post Title: Mafia II SDS files?

I think there's more to that. In one file I found a plain xml file at the end and other plain text in between.
So I guess the format supports compression on a per-file basis.
## Post #8
- Username: bird
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 08, 2010 5:01 pm
- Post datetime: 2010-08-11T19:13:20+00:00
- Post Title: Mafia II SDS files?

Thanks for putting effort into the matter, with Evin's help I found out that there are 117 pieces of compressed zlib files in text_default.sds Since I'm not a programmer I can't figure out the whole mechanism how the file structure handles those separately compressed files.
## Post #9
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-08-11T20:17:14+00:00
- Post Title: Mafia II SDS files?

Well strangely there's some 36(?) byte info between some file data but between others there seems to be no such data.
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2010-08-11T22:27:58+00:00
- Post Title: Mafia II SDS files?

> Reply from Rheini
>
> I think there's more to that. In one file I found a plain xml file at the end and other plain text in between.
So I guess the format supports compression on a per-file basis.
Indeed. Everyone SDS contains some files which compressed with zlib

Examples : 
m05main.sds contained LuaQ files (compiled lua scripts - 5.x ?)

```
/scripts/missions/M05Main/M05MainScript.lua
/scripts/missions/M05Main/M05Saves.lua
/missions/M05Main/scriptname.txt

```


1 file offset start - 000031D6
2 file offset start - 00008C49
3 file offset start - 0000EEF9

m05waytoelgreco.sds

```
/scripts/missions/M05WayToElGreco/SpawnPoliceCars2.lua
/scripts/missions/M05WayToElGreco/SpawnPoliceCars3.lua
/scripts/missions/M05WayToElGreco/WayToElGrecoPolice.lua
/scripts/missions/M05WayToElGreco/Script/M05PoliceChase.lua
/scripts/missions/M05WayToElGreco/Script/WayTimer.lua

```


1 file offset start - 00007E8E
2 file offset start - 0000BDC4
3 file offset start - 0000BE4A
4 file offset start - 0000F3B4
5 file offset start - 0000FCBC
6 file offset start - 00010014

See attached file, mb who can can extract from there files  
[m05main.rar](https://xentaxbackup.github.io/file/3312_m05main.rar)
## Post #11
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-12T17:04:19+00:00
- Post Title: Mafia II SDS files?

spent a little bit of time reversing some of the headers. the plaintext xml is for the engine to allocate memory (see the first header).

zlib data looks chunked. haven't yet bothered splitting up the files.

edit: haven't read the latest post - will download these new attachments now!

```
#    xentax.com
#    .sds BMS script (wip)

print "WARNING: THIS SCRIPT WILL NOT DUMP ANYTHING YET (WIP)"

idstring "SDS\x00"

goto 16

### Part of the header

get P_RES long
get P_DATA long
get P_XML long
get TOT_RAM long # sum of all ram usage (see xml)
get TOT_VRAM long # sum of all vram usage (see xml)

###

get xmlsize asize
math xmlsize -= P_XML

log "sds_desc.xml" P_XML xmlsize


goto 64

### Res info

get RES_COUNT long
get UNKNOWN long
get RES_TYPES long

for i = 1 to RES_TYPES

  get RES_INDEX long
  get RES_NAME_sIZE long

  math RES_NAME_sIZE += 4 # padded byte
  getdstring RES_NAME RES_NAME_SIZE

  print "%RES_NAME%"

next i

### zlib data

goto P_DATA # will already be here


getdstring UNKNOWN 30 # some sort of header

set chunkcnt long 0

for

  get CHUNK_SIZE long

  if CHUNK_SIZE == 0

    print "Chunks found: %chunkcnt%"
    cleanexit

  endif

  get FLAG byte

  if FLAG == 0

    getdstring UNKNOWN 11

    ## zlib data is here

    savepos DATASTART

    ## todo: clog to memory_file, append result to result
    math DATASTART += CHUNK_SIZE

    goto DATASTART

  else

    get UNKNOWN long
    get SKIP long

    savepos SKIPVAL

    math SKIPVAL += SKIP
    math SKIPVAL -= 8

    goto SKIPVAL

    savepos DATASTART

    ## todo: clog to memor_file, append result to result
    math CHUNK_SIZE -= SKIP
    math DATASTART += CHUNK_SIZE

    goto DATASTART

  endif

  math chunkcnt += 1

next

```
## Post #12
- Username: stgn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 13, 2010 12:14 am
- Post datetime: 2010-08-12T17:53:41+00:00
- Post Title: Mafia II SDS files?

the lua files are, more specifically, compiled lua 5.1 scripts. their magic is actually "[0x1b]Lua", not "LuaQ". the "Q" is actually the version (0x51 -> 5.1).
## Post #13
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-12T18:56:19+00:00
- Post Title: Mafia II SDS files?

well i'm almost done.

i've attached DEMO_end4.dds from demo_end4.sds (had to scale down so i could upload it).
[output.jpg](https://xentaxbackup.github.io/file/3313_output.jpg)
## Post #14
- Username: stgn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 13, 2010 12:14 am
- Post datetime: 2010-08-12T19:16:26+00:00
- Post Title: Mafia II SDS files?

mafia ii appears to use a modified lua vm. first obvious sign i could find is that it uses single-precision floats for numbers instead of double according to compiled lua headers. i compiled a custom version of luadec to handle this but i'm still getting errors like "unexpected end in precompiled chunk" or "memory allocation error: block too big", which suggest that there might be more going on.
## Post #15
- Username: sng
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 13, 2010 12:39 am
- Post datetime: 2010-08-12T19:18:24+00:00
- Post Title: Mafia II SDS files?

I'm trying to decompile the file [M05ListOfParts.luac](http://narod.ru/disk/23677733000/M05ListOfParts.luac.html) taken from the file "pc\sds\missionscript\m05main.sds".

I use [LuaDec51](http://luadec51.luaforge.net/), but get an error "bad header in precompiled chunk".
Having sorted out, I realized that the error here: (luaconf.h)
```
"#define LUA_NUMBER double"
```

I changed it to 8, but a new error "bad constant in precompiled chunk".
I understand, they use a modified Lua script. Am I right?

Mafia Lua Header:

```

```


Lua Header v5.1:

```

```
## Post #16
- Username: stgn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 13, 2010 12:14 am
- Post datetime: 2010-08-12T19:25:45+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from sng
>
> I'm trying to decompile the file M05ListOfParts.luac taken from the file "pc\sds\missionscript\m05main.sds".

I use LuaDec51, but get an error "bad header in precompiled chunk".
Having sorted out, I realized that the error here: (luaconf.h)Code: Select all"#define LUA_NUMBER double"
I changed it to 8, but a new error "bad constant in precompiled chunk".
I understand, they use a modified Lua script. Am I right?

Mafia Lua Header:
Code: Select all1B 4C 75 61 51 00 01 04 04 04 [04] 00


Lua Header v5.1:
Code: Select all1B 4C 75 61 51 00 01 04 04 04 [08] 00
i compiled a modified luadec51 that uses single-precision lua_number. the file you posted began to decompile but it crashed luadec. i guess i was extracting the files wrong.
## Post #17
- Username: stgn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 13, 2010 12:14 am
- Post datetime: 2010-08-12T19:28:04+00:00
- Post Title: Re: Mafia II SDS files?

```
  if game.datastore:IsVariableExist("CON_DEMO") == false then
    player = game.game:GetActivePlayer()
    player:InventoryAddItem(55)
    game.speech:LoadStage(60)
    idMessages = common.messages.Id
    questComM05 = Lokace.Create(idMessages.Distillery, idMessages.QuestDirector)
    game.datastore:SetBool("tempDemoStart", true)
    kteryPartik = game.datastore:GetNumber("missionPart")
    kteraJeMise = game.datastore:GetNumber("missionNumber")
    player:SetFightAbility(false, enums.FightAbility.COUNTER)
    player:SetFightAbility(false, enums.FightAbility.COMBO)
    if kteryPartik == 1 then
      M05Part1(l_1_0)
    elseif kteryPartik == 2 then
      M05Part2(l_1_0)
    elseif kteryPartik == 3 then
      M05Part3(l_1_0)
    elseif kteryPartik == 4 then
      M05Part4(l_1_0)
    elseif kteryPartik == 5 then
      M05Part5(l_1_0)
    elseif kteryPartik == 6 then
      M05Part6(l_1_0)
    elseif kteryPartik == 7 then
      M05Part7(l_1_0)
    elseif kteryPartik == 8 then
      M05Part8(l_1_0)
    elseif kteryPartik == 9 then
      M05Demo(l_1_0)
    elseif kteryPartik == 10 then
      M05DemoDistFlat(l_1_0)
    end
  end
end)
```

here's a portion though.
## Post #18
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2010-08-12T20:23:58+00:00
- Post Title: Re: Mafia II SDS files?

Great job WRS
## Post #19
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-12T21:43:51+00:00
- Post Title: Re: Mafia II SDS files?

thanks!

here's my final version. the filenames are in the xml - so this needs to be written up in another programming language - but it can decompress the chunks and split all the listed files 

leave a message or pm me if you have any problems.
[sds_bmsbywrs.zip](https://xentaxbackup.github.io/file/3314_sds_bmsbywrs.zip)
## Post #20
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2010-08-13T01:09:05+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from WRS
>
> thanks!

here's my final version. the filenames are in the xml - so this needs to be written up in another programming language - but it can decompress the chunks and split all the listed files 

leave a message or pm me if you have any problems.

trying on m05waytoelgreco.sds

```
------------------------------
- SCRIPT's MESSAGE:
  Dumping XML description..

  000093c5 3149       m05waytoelgreco_desc.xml
- SCRIPT's MESSAGE:
  total chunks: 6
  decompressed size: 93408 bytes

- SCRIPT's MESSAGE:
  Parsing uncompressed data..

- SCRIPT's MESSAGE:
  warning: next output will keep header information

  0000002a 7001       1__FrameResource
- SCRIPT's MESSAGE:
  warning: next output will keep header information

  00001bbc 6          2__FrameNameTable
- SCRIPT's MESSAGE:
  warning: next output will keep header information

  00001bfb 7476       3__Actors
- SCRIPT's MESSAGE:
  warning: next output will keep header information

- error in src\quickbms.c line 2480: CMD_GetDString_func()
Error: tentative of allocating -1 bytes
```


demo05.sds

```
------------------------------
- SCRIPT's MESSAGE:
  Dumping XML description..

  00009de0 2794       demo05_desc.xml
- SCRIPT's MESSAGE:
  total chunks: 9
  decompressed size: 131859 bytes

- SCRIPT's MESSAGE:
  Parsing uncompressed data..

- SCRIPT's MESSAGE:
  warning: next output will keep header information

  0000002a 5518       1__FrameResource
- SCRIPT's MESSAGE:
  warning: next output will keep header information

  000015f1 6          2__FrameNameTable
- SCRIPT's MESSAGE:
  warning: next output will keep header information

  00001630 6824       3__Actors
  00003127 12         4__MemFile
  00003193 18919      5__MemFile
  00007bbf 61848      6__MemFile

- error in src\quickbms.c line 8504: myalloc()
Error: Not enough space
```


Error: Not enough space - wtf 795gb free
## Post #21
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-08-13T01:37:09+00:00
- Post Title: Re: Mafia II SDS files?

i just get an error with all SDS i've trying 

```
------------------------------
- SCRIPT's MESSAGE:
  Dumping XML description..

  00a05599 55351      tunel_desc.xml

Error: the compressed zlib/deflate input is wrong or incomplete (-3)

Error: there is an error with the decompression
       the returned output size is negative (-1)

Press RETURN to quit
```
anyway great job:)

upd:
or maybe it's not a bms script??
## Post #22
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-13T01:40:08+00:00
- Post Title: Re: Mafia II SDS files?

i only had 2 files to write my script from. cut me some slack.


> Reply from Ekey
>
> Error: Not enough space - wtf 795gb free
memory doesn't refer to hard disk space


can you upload the ones you tried it with?
## Post #23
- Username: bird
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 08, 2010 5:01 pm
- Post datetime: 2010-08-13T01:53:58+00:00
- Post Title: Re: Mafia II SDS files?

Tried your script with text_default.sds and it worked like a charm, thanks (I used quickbms)!
It produced 5 files: 1__Texture 2__MemFile 3__MemFile 4__MemFile 5__XML
I hope you'll find a way to recompress those files (especially Memfiles which contain translatable text) easily, without crashing the game.

Great job so far!
## Post #24
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-08-13T02:09:43+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from WRS
>
> can you upload the ones you tried it with?I think
[player - vito](http://www.sendspace.com/file/frrk1d) and [houston car](http://www.sendspace.com/file/otf4nz)
## Post #25
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2010-08-13T10:51:05+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from WRS
>
> i only had 2 files to write my script from. cut me some slack.

Ekey wrote:Error: Not enough space - wtf 795gb free  
memory doesn't refer to hard disk space


can you upload the ones you tried it with?
yup , attached
[demo05.rar](https://xentaxbackup.github.io/file/3317_demo05.rar)
## Post #26
- Username: s0beit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 13, 2010 2:07 pm
- Post datetime: 2010-08-13T11:51:48+00:00
- Post Title: Re: Mafia II SDS files?

The contents of this post was deleted because of possible forum rules violation.
## Post #27
- Username: bird
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 08, 2010 5:01 pm
- Post datetime: 2010-08-13T12:20:37+00:00
- Post Title: Re: Mafia II SDS files?

Thanks for the link from Facepunch's megathread. I knew that board already.
It's awesome!
## Post #28
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2010-08-13T20:59:06+00:00
- Post Title: Re: Mafia II SDS files?

in folder "Steam\SteamApps\common\mafia ii - public demo\pc\shaders\buildLogs\" i found interesting log file 

Autobuilder.log


Edit by Rheini: removed the log to keep this thread clean
## Post #29
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-08-13T22:16:53+00:00
- Post Title: Re: Mafia II SDS files?

that is useless dude. please delete that its was to big for the forum posts use an attached text file next time.
## Post #30
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-13T23:32:59+00:00
- Post Title: Re: Mafia II SDS files?

updated my script. adding some comments before i upload
[new_extracted.jpg](https://xentaxbackup.github.io/file/3320_new_extracted.jpg)
## Post #31
- Username: s0beit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 13, 2010 2:07 pm
- Post datetime: 2010-08-13T23:50:40+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from WRS
>
> updated my script. adding some comments before i upload
Good job.

I don't know which luac script my friend used to make this:
[http://pastie.org/1088974](http://pastie.org/1088974)


but he claims there is corrupted (or something) bytes in my dumped Luas.

If we could really dump the true luac files, it would help us alot
## Post #32
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-14T00:04:26+00:00
- Post Title: Re: Mafia II SDS files?

final version #2 !

note:
dumped files will have 30 bytes or so of random data at the start. i cant find the size of this to remove it, so work with it   

removed the naming-by-resource-type. you can name them yourself from the xml.


this should be all.
[sds_bmsbywrs_v2.zip](https://xentaxbackup.github.io/file/3322_sds_bmsbywrs_v2.zip)
## Post #33
- Username: s0beit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 13, 2010 2:07 pm
- Post datetime: 2010-08-14T00:39:54+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from WRS
>
> final version #2 !

note:
dumped files will have 30 bytes or so of random data at the start. i cant find the size of this to remove it, so work with it   

removed the naming-by-resource-type. you can name them yourself from the xml.


this should be all.

Hi, and thank you very much!

I noticed the beginning of the file chunk for compiled Lua files has those extra bytes you mentioned, looks like a header.

i will explain:

```
03 00 00 00 60 22 A9 B3 3A BA 5C C9 11 19 61 FE 3D 37 41 (SIZE OF FILENAME PATH) 00 (FILENAME) E0 59 00 00 (FILE START)
```


which is, like this in the hex editor for me:
[http://img685.imageshack.us/img685/2259/dadat.png](http://img685.imageshack.us/img685/2259/dadat.png)

The highlighted byte is the start of the actual compiled Lua file, hope this helps!

EDIT:

Then again some .dat files with no directories in it do this:

```
01 00 00 00 (SIZE OF FILE CHUNK) 00 00 00  (FILE START)

```


It is complex, i'll give you that much.

Edit 2: I also noted that the number of entries in the XML match exactly the order and number of the actual files generated.

Maybe it should be more like:

FrameResource.sds.pak
FrameNameTable.sds.pak
Actors.sds.pak
MemFile.sds.pak
Script.sds.pak

Although i might work on a version in C++, i'm unsure of QuickBMS's full capabilities but i think i can handle the final dumping of the files from the combined file.
## Post #34
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-14T01:02:24+00:00
- Post Title: Re: Mafia II SDS files?

yeah, the xml description holds information for the engine to allocate memory as well as the filenames.

the headers have 16 bytes+, but some dds headers have 30 bytes, some 29 - and neither have filenames.

edit: the files may be handled by resource type - i left the headers commented out, but they might be needed to read these headers
## Post #35
- Username: s0beit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 13, 2010 2:07 pm
- Post datetime: 2010-08-14T01:13:37+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from WRS
>
> yeah, the xml description holds information for the engine to allocate memory as well as the filenames.

the headers have 16 bytes+, but some dds headers have 30 bytes, some 29 - and neither have filenames.

edit: the files may be handled by resource type - i left the headers commented out, but they might be needed to read these headers

I concur, they seem to be different for some files but not others.

At the moment I'm just going to write one for the mission files 

EDIT: So far i'm here

```
	{
		guidtech::Buffer::DynamicReadable BufferRead( buff );

		unsigned long TotalFileSize = BufferRead.Read< unsigned long >();

		printf( "TotalFileSize [%i]\n", TotalFileSize );

		BufferRead.Read( 12 ); // Unknown chunk

		unsigned long UnknownDword = BufferRead.Read< unsigned long >();

		printf( "UnknownDword [%i]\n", TotalFileSize );

		unsigned char LengthOfDirectory = BufferRead.Read< unsigned char >();

		printf( "LengthOfDirectory [%i]\n", LengthOfDirectory );

		BufferRead.Read< unsigned char >(); // 00

		char *pszDirectoryName = new char[ LengthOfDirectory ];

		for( unsigned long i = 0; i < LengthOfDirectory; i++ )
		{
			pszDirectoryName[ i ] = BufferRead.Read< char >();
		}

		pszDirectoryName[ LengthOfDirectory ] = '\0';

		printf( "DirectoryName [%s]\n", pszDirectoryName );

//		delete[] pszDirectoryName; // Crashy??.....

		unsigned char NumberOfFilesInArchive = BufferRead.Read< unsigned char >();

		printf( "NumberOfFilesInArchive [%i]\n", NumberOfFilesInArchive );

		BufferRead.Read( 2 ); // End of header for Script

		/*for( unsigned char f = 1; f < NumberOfFilesInArchive; f++ )
		{
			//
		}*/

		BufferRead.Read( 17 ); // Unknown chunk

		unsigned char LengthOfFileName = BufferRead.Read< unsigned char >();

		BufferRead.Read( 1 ); // 00

		printf( "LengthOfFileName [%i]\n", LengthOfFileName );

		char *pszFileName = new char[ LengthOfFileName ];

		for( unsigned long i = 0; i < LengthOfFileName; i++ )
		{
			pszFileName[ i ] = BufferRead.Read< char >();
		}

		pszFileName[ LengthOfFileName ] = '\0';

		printf( "FileName [%s]\n", pszFileName );

		// 

		return false;
	}
```


```
TotalFileSize [56594]
UnknownDword [56594]
LengthOfDirectory [34]
DirectoryName [/scripts/missions/M05WayToElGreco/]
NumberOfFilesInArchive [3]
LengthOfFileName [56]
FileName [/scripts/missions/M05WayToElGreco/WayToElGrecoPolice.lua]

```


```
TotalFileSize [65644]
UnknownDword [65644]
LengthOfDirectory [26]
DirectoryName [/scripts/missions/M05Main/]
NumberOfFilesInArchive [3]
LengthOfFileName [44]
FileName [/scripts/missions/M05Main/M05ListOfParts.lua]

```
## Post #36
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-08-14T02:29:34+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from WRS
>
> final version #2 !

note:
dumped files will have 30 bytes or so of random data at the start. i cant find the size of this to remove it, so work with it   

removed the naming-by-resource-type. you can name them yourself from the xml.


this should be all.Thank you. Script work great   But how can i rename files using xml file?
## Post #37
- Username: s0beit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 13, 2010 2:07 pm
- Post datetime: 2010-08-14T03:01:02+00:00
- Post Title: Re: Mafia II SDS files?

Hizzah!

I've dumped /missionscripts/

Here is the pastebin for the code i used (DynamicBuffer i won't be giving out, but it is possible to rewrite this easily with structs, full source will be available later)

[http://pastebin.com/PPKLG3Ne](http://pastebin.com/PPKLG3Ne)

EDIT: Removed link, the dumps were buggy but I'm almost there!
## Post #38
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-08-14T05:58:23+00:00
- Post Title: Re: Mafia II SDS files?

So guys is there a way to extract text and font files for editing and to repack back? I mean trasnlation
## Post #39
- Username: bird
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 08, 2010 5:01 pm
- Post datetime: 2010-08-14T06:18:06+00:00
- Post Title: Re: Mafia II SDS files?

You can actually unpack the fontfile and the strings with WRS's Final Version #2 [BMS-script](http://forum.xentax.com/download/file.php?id=3322) using [QuickBMS](http://aluigi.altervista.org/papers/quickbms.zip).

Fire up your command prompt and type:

```
quickbms.exe sds_bmsbywrs_v2.txt text_default.sds C:\path_for_stuff_youd_like_to_extract_things_blah\
```

You'll get 4 files (00000000.NEO 00000001.dat 00000002.dat 00000003.dat 00000004.NEO):
Datfiles contain strings encoded in UTF-8. 00000001.dat and 00000002.dat is what you need.

Oh, and you have to cut 00000000.NEO's first 30 bytes to get a proper DDS file (as WRS mentioned it before), so load up your favourite hexeditor and wipe out those bytes and start editing! 
As for now, I don't know how to repack these files. In order to get an intact .sds file, guess we have to wait until someone does the magic.
## Post #40
- Username: s0beit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 13, 2010 2:07 pm
- Post datetime: 2010-08-14T23:54:14+00:00
- Post Title: Re: Mafia II SDS files?

The script .dat format is as follows

```
[filesize (int)][12 bytes][filesize2 (int)][directory length (byte)][00 (byte)][directory name (str)][number_of_files (byte)][3 bytes (end header?)]

(HEADER FOR EACH ENTRY)
[hash (16 bytes, md5)][file name length (byte)][00 (byte)][file name (str)][size of file (int)][file data raw (bytes, size of file)]
```
## Post #41
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-15T19:25:51+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from s0beit
>
> 
Code: Select all(FILE HEADER)
[filesize (int)][12 bytes][filesize2 (int)]....

the first 12 bytes of all the extracted files is another ram header:

```
uint32 VRAM;
uint32 OtherRAM;
uint32 OtherVRAM;

```


so dont rely on this value - use filesize2 instead!
## Post #42
- Username: s0beit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 13, 2010 2:07 pm
- Post datetime: 2010-08-15T20:52:31+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from WRS
>
> s0beit wrote:
Code: Select all(FILE HEADER)
[filesize (int)][12 bytes][filesize2 (int)]....

the first 12 bytes of all the extracted files is another ram header:
Code: Select alluint32 RAM;
uint32 VRAM;
uint32 OtherRAM;
uint32 OtherVRAM;


so dont rely on this value - use filesize2 instead!

Nice find, will do, probably will fix an error i had previously
## Post #43
- Username: sng
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 13, 2010 12:39 am
- Post datetime: 2010-08-16T06:08:05+00:00
- Post Title: Re: Mafia II SDS files?

SDS file structure:

```
SDS header (SDS - Source Data Streams (?)) (0x0A + 4) (0x1A)
------------------------------------------
int32 sdsSign ("SDS/0")
int32 version (0x13)
int32 platformSign ("PC/0/0")
int32 sdsHeaderHash 0x5FFB74F3
------------------------------
fileInfo (0x34 + 4)
------------------------------
void* typeHeader 
void* zlibHeader
void* xmlFile
int32 totalSlotRam
int32 totalSlotVram
int32 totalOtherRam
int32 totalOtherVram
int32 ? const 0x01
char[16] const "73979+"
int32 resrcCount
int32 fileInfoHash
-----------------------
typeHeader
-----------------------
int32 typeCount
-----------------------
typeDesc[typeCount]
-----------------------
int32 typeId
int32 typeStrSize
char[typeStrSize] typeName
int32 ? typeFlags
------------------------
zlibHeader
------------------------
int32 zlibSign ("UEzl")
int32 uncompressedStreamSize (default 16384 bytes or 16 KBytes)
byte version
-----------------------
streamHeader
-----------------------
int32 ? compressedStreamSizeWithHeader
bool ? 
int32 ? uncompressedStreamSize (default 16384 bytes or 16 KBytes)
int32 ?
int32 ?
int32 ?
int32 compressedStreamSize
int32 ?
int32 ?
int32 ?
-----------------------
streamData
-----------------------
```

Unpacked data header:

```
data block header
------------------------
int32 id
int32 nextBlockOffset
int16 ?
int32 fileSize
int32 ?
...
------------------------
```

Hash-function:

```
{
    unsigned int r = initHash;
    for(unsigned int i = 0; i < size; i++) r = data[i] ^ (r*0x01000193);
}
```
## Post #44
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-16T13:16:56+00:00
- Post Title: Re: Mafia II SDS files?

my version already has all that and more. hash function is useful though.
## Post #45
- Username: westernsys
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 13, 2010 11:19 pm
- Post datetime: 2010-08-16T13:29:57+00:00
- Post Title: Re: Mafia II SDS files?

Impressive stuff!
I tried to change luadec's lua_number to 4 byte (float), because looking the .luac file with hex editor i saw it said 04 on 11th byte.
So I changed luaconf.h line 505 to "#define LUA_NUMBER	float" and compiled it.
But luadec still complains "bad header in precompiled chunk" when i run it on luac files...
## Post #46
- Username: sng
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 13, 2010 12:39 am
- Post datetime: 2010-08-16T13:43:37+00:00
- Post Title: Re: Mafia II SDS files?

westernsys where you took luadec?there may be requests for the Unicode version of the lua files?
## Post #47
- Username: westernsys
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 13, 2010 11:19 pm
- Post datetime: 2010-08-16T13:54:49+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from sng
>
> westernsys where you took luadec?there may be requests for the Unicode version of the lua files?
[http://winmo.sztupy.hu/luadec/luadec_2.0_src_win32.zip](http://winmo.sztupy.hu/luadec/luadec_2.0_src_win32.zip)
[http://winmo.sztupy.hu/luadec.html](http://winmo.sztupy.hu/luadec.html)
## Post #48
- Username: sng
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 13, 2010 12:39 am
- Post datetime: 2010-08-16T14:01:08+00:00
- Post Title: Re: Mafia II SDS files?

See in changelog:

> The provided lua package (lua, luac and luadec) is now unicode compilant, it will read and write the unicode variants of the scripts instead of the ascii variants.
## Post #49
- Username: westernsys
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 13, 2010 11:19 pm
- Post datetime: 2010-08-16T15:10:40+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from sng
>
> See in changelog:
The provided lua package (lua, luac and luadec) is now unicode compilant, it will read and write the unicode variants of the scripts instead of the ascii variants.
Hmm, ok I got the older version, compiled it with modified luaconf.h, now i get "bad constant in precompiled chunk"
## Post #50
- Username: sng
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 13, 2010 12:39 am
- Post datetime: 2010-08-16T16:50:51+00:00
- Post Title: Re: Mafia II SDS files?

westernsys Do you have a bad lua file that is extracted is not correct.
## Post #51
- Username: westernsys
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 13, 2010 11:19 pm
- Post datetime: 2010-08-16T16:52:44+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from sng
>
> westernsys Do you have a bad lua file that is extracted is not correct.
I used your luac example here
[http://narod.ru/disk/23677733000/M05Lis ... .luac.html](http://narod.ru/disk/23677733000/M05ListOfParts.luac.html)
## Post #52
- Username: sng
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 13, 2010 12:39 am
- Post datetime: 2010-08-16T17:04:58+00:00
- Post Title: Re: Mafia II SDS files?

Hmm, try using this [http://narod.ru/disk/23779654000/luadec.rar.html](http://narod.ru/disk/23779654000/luadec.rar.html). this is my ascii version of luadec 2.0 [http://winmo.sztupy.hu](http://winmo.sztupy.hu).
There are decompiled so far only a few functions. Run with "-f x", where x - number of function.
## Post #53
- Username: westernsys
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 13, 2010 11:19 pm
- Post datetime: 2010-08-16T17:14:28+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from sng
>
> Hmm, try using this http://narod.ru/disk/23779654000/luadec.rar.html. this is my ascii version of luadec 2.0 http://winmo.sztupy.hu.
There are decompiled so far only a few functions. Run with "-f x", where x - number of function.
Thanks, I will check it out
## Post #54
- Username: stgn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 13, 2010 12:14 am
- Post datetime: 2010-08-16T17:18:30+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from sng
>
> Hmm, try using this http://narod.ru/disk/23779654000/luadec.rar.html. this is my ascii version of luadec 2.0 http://winmo.sztupy.hu.
There are decompiled so far only a few functions. Run with "-f x", where x - number of function.
in luadec51, print.c, line 837, add this line after:

```
   if(!tbl) return;
```
## Post #55
- Username: sng
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 13, 2010 12:39 am
- Post datetime: 2010-08-16T17:40:31+00:00
- Post Title: Re: Mafia II SDS files?

stgn Big thanks
## Post #56
- Username: stgn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 13, 2010 12:14 am
- Post datetime: 2010-08-16T17:50:50+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from sng
>
> stgn Big thanks
no problem, but i'm curious. how did you extract m05listofparts.luac? i tried to extract it myself in numerous ways but it doesn't decompile, only the file you posted worked for me.
## Post #57
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-08-16T18:41:59+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from sng
>
> Hash-function:
Code: Select allint getHash(unsigned char* data, unsigned int size, unsigned int initHash = 0x811C9DC5)
{
    unsigned int r = initHash;
    for(unsigned int i = 0; i < size; i++) r = data[i] ^ (r*0x01000193);
}This is FNV32.
## Post #58
- Username: sng
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 13, 2010 12:39 am
- Post datetime: 2010-08-16T19:30:17+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from stgn
>
> sng wrote:stgn Big thanks
no problem, but i'm curious. how did you extract m05listofparts.luac? i tried to extract it myself in numerous ways but it doesn't decompile, only the file you posted worked for me.

How do you extract the files?
## Post #59
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2010-08-17T02:00:45+00:00
- Post Title: Re: Mafia II SDS files?

EDIT: Please disregard, I think I've figured it out - thanks!

I have extracted .xml and .dat file from texture sds - apologies, I am not very familiar with hex editing. I am using HxD - is it possible someone could walk me through an example of how I know what to delete from the .dat file in order to get the desired .dds file? I have read through this thread, but I don't fully understand everything.

For example, demo_end4, I saw the filesize in XML is given as 1843200, and I deleted all the opening data in the .dat file until the resulting filesize was 1843200. However, Photoshop DDS import could not parse it (and I've had no trouble opening other DDS files, including the DDS wallpaper files in the Mafia II demo that are just sitting in one of the directories).
## Post #60
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-08-17T02:07:45+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from relight
>
> I have extracted .xml and .dat file from texture sds - apologies, I am not very familiar with hex editing. I am using HxD - is it possible someone could walk me through an example of how I know what to delete from the .dat file in order to get the desired .dds file? I have read through this thread, but I don't fully understand everything.Open .dat/.neo file in HEX-editor and delete all symbols before "DDS" and save. If you not see DDS in first page in HEX, than it's not a dds-image.
## Post #61
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2010-08-17T02:08:42+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from Tosyk
>
> Open .dat/.neo file in HEX-editor and delete all symbols before "DDS" and save. If you not see DDS in first page in HEX, than it's not a dds-image.
Ahhh... that makes it much clearer. Thanks for the explanation!
## Post #62
- Username: Hyperz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Aug 14, 2010 12:45 am
- Post datetime: 2010-08-17T12:59:10+00:00
- Post Title: Re: Mafia II SDS files?

This is probably a stupid question but I'm not familiar with all this stuff  .
Do these luac files have an EoF header or does some part of the header tell you the length of the file?
I'm asking this because I dumped the memory of mafia2.exe and I wanna see if I could extract some luac files from there .
## Post #63
- Username: s0beit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 13, 2010 2:07 pm
- Post datetime: 2010-08-17T19:33:19+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from s0beit
>
> The script .dat format is as follows
Code: Select all(FILE HEADER)
[filesize (int)][12 bytes][filesize2 (int)][directory length (byte)][00 (byte)][directory name (str)][number_of_files (byte)][3 bytes (end header?)]

(HEADER FOR EACH ENTRY)
[hash (16 bytes, md5)][file name length (byte)][00 (byte)][file name (str)][size of file (int)][file data raw (bytes, size of file)]

Wrote this a couple pages back, for poster above me :\

Also, "LuaQ"
## Post #64
- Username: Hyperz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Aug 14, 2010 12:45 am
- Post datetime: 2010-08-19T15:31:11+00:00
- Post Title: Re: Mafia II SDS files?

A lot of the SDS archives contain XML files. But they aren't plain text. Looks like some form of binary XML.
They seem to have a similar header as the script files and have some strange data at the end.
Does anyone have more info on these XML files or know a way to read or convert them?
I attached 3 examples from different SDS archives.

And also, I was wondering if anyone made any improvements/fixes to luadec?
Some scripts still crash the program (some kind of assert error, I debugged it but I don't know C ).

Thanks.
[xml_files.zip](https://xentaxbackup.github.io/file/3352_xml_files.zip)
## Post #65
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2010-08-19T16:23:48+00:00
- Post Title: Re: Mafia II SDS files?

I have used WRS's BMS v2 to unpack sounds from .sds archives, but most of extracted FSBs are cutted from their end. But FSBs from m05_sounds_6.sds (czech version) are all good - uncutted.
Does anybody know how to fix it? 

Thx

Example of .sds from which are sounds cutted (spjoe.sds)

[http://www.mediafire.com/?mrs9v3bgxsk6wvn](http://www.mediafire.com/?mrs9v3bgxsk6wvn)
## Post #66
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2010-08-20T03:14:55+00:00
- Post Title: Re: Mafia II SDS files?

Any chance for the quickbms script to name the .sds extracted .dat content using the SourceDataDescription field from the .xml file?  When there's hundreds of .dat files in the .sds file, it's tedious to figure them all out or find the one you want from the .xml file.

If so, it would be very useful and very much appreciated!

Thanks!
## Post #67
- Username: Hyperz
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-08-20T12:44:22+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from Hyperz
>
> A lot of the SDS archives contain XML files. But they aren't plain text. Looks like some form of binary XML
Really strange format, only have a rough overview (the data types of the unknown variables aren't correct, they are just placeholders for space):

```
{
    uint len;
    //char data[len];
    string data;
};

uint null1;
uint null2;
uint null3;
uint null4;

uint uk1;
String s1;
String s2;
byte uk_2;
uint uk_3;
uint uk_4;
byte uk_7;
uint uk_5;
uint uk_6;

struct Entry
{
    byte flag;

if (flag == 1)
{
    uint uk1;
    uint uk2;
}
else if (flag == 2)
{
    byte uk;
    uint uk1;
    uint uk2;
}
else if (flag == 3)
{
    short uk;
    uint uk1;
    uint uk2;
}
else if (flag == 4)
{
    byte uk;
    short uk1;
    uint uk2;
}
    string s;
if (flag == 0)
    byte nulls[2];
};
do
    Entry entries;
while(entries.flag != 0);

uint uks[500];

```
## Post #68
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2010-08-21T21:13:00+00:00
- Post Title: Re: Mafia II SDS files?

Unpacker 

ExSDS v0.3 Writed by CJay



Download
[http://dl.dropbox.com/u/202588/mafia/ExSDS03.zip](http://dl.dropbox.com/u/202588/mafia/ExSDS03.zip)
## Post #69
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2010-08-21T23:56:35+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from Ekey
>
> Unpacker 

ExSDS v0.3 Writed by CJay
Nice, thanks! This is REALLY useful! You rock
## Post #70
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2010-08-22T09:38:04+00:00
- Post Title: Re: Mafia II SDS files?

We have need a SDS Repacker
## Post #71
- Username: Energy
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 19, 2010 9:05 am
- Post datetime: 2010-08-25T15:36:24+00:00
- Post Title: Re: Mafia II SDS files?

All people wait for repacker  
Please make us happy
## Post #72
- Username: Psychoka
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 22, 2010 6:13 am
- Post datetime: 2010-08-25T22:06:09+00:00
- Post Title: Re: Mafia II SDS files?

.SDS Repack please dude! Unpacker is nice job!! Thanks!!!!
## Post #73
- Username: michu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 26, 2010 1:14 am
- Post datetime: 2010-08-26T07:45:41+00:00
- Post Title: Re: Mafia II SDS files?

The contents of this post was deleted because of possible forum rules violation.
## Post #74
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-08-28T10:43:23+00:00
- Post Title: Re: Mafia II SDS files?

The contents of this post was deleted because of possible forum rules violation.
## Post #75
- Username: Engineer
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2010-08-28T10:56:58+00:00
- Post Title: Re: Mafia II SDS files?

SDS tool has already been made to unpack and repack
## Post #76
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-08-28T11:22:41+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from Engineer
>
> SDS tool has already been made to unpack and repack
where?
## Post #77
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-08-28T11:33:54+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from Tosyk
>
> Engineer wrote:SDS tool has already been made to unpack and repack 
where?
+1
## Post #78
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-08-28T11:49:18+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from qabRieL
>
> Tosyk wrote:Engineer wrote:SDS tool has already been made to unpack and repack 
where? 
+1
+2  
I only see this:
 -Added support to open files via Commandline (So you can set up a file association for *.sds files)
If you do ExSDS.exe file.sds that's all, im missing something?
## Post #79
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-08-28T12:51:00+00:00
- Post Title: Re: Mafia II SDS files?

Well, does anyone know what is that at the adress 0x44 of the pc sds files?

Is it a hash of some sort?
## Post #80
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-08-28T14:20:47+00:00
- Post Title: Re: Mafia II SDS files?

Yes, it's a FNV32 hash of 52 bytes starting at 0x10 (just before 0x44).
## Post #81
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2010-08-28T15:55:14+00:00
- Post Title: Re: Mafia II SDS files?

any luck extrating model data?
## Post #82
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-08-28T15:58:19+00:00
- Post Title: Re: Mafia II SDS files?

Please xbox360 support?
## Post #83
- Username: Energy
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 19, 2010 9:05 am
- Post datetime: 2010-08-28T16:22:09+00:00
- Post Title: Re: Mafia II SDS files?

please text editor support. For all who need translate game please.
## Post #84
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-08-28T16:41:13+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from Rick
>
> Yes, it's a FNV32 hash of 52 bytes starting at 0x10 (just before 0x44).

Good, thanks man.

And what about the decompressed files, before the filename path there is the size of the filename path, and before that, is that other hash?

EDit:No need, its th same FNV32 but now with 26 bytes...

Thanks, i'm creating my tool with you guys informations.



Im almost finishing my tool...
## Post #85
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-08-28T18:34:55+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from caws
>
> Rick wrote:Yes, it's a FNV32 hash of 52 bytes starting at 0x10 (just before 0x44).

Good, thanks man.

And what about the decompressed files, before the filename path there is the size of the filename path, and before that, is that other hash?

EDit:No need, its th same FNV32 but now with 26 bytes...

Thanks, i'm creating my tool with you guys informations.



Im almost finishing my tool...

Can you share it with us when you complete the tool?
## Post #86
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2010-08-28T21:12:59+00:00
- Post Title: Re: Mafia II SDS files?

Good work  Share the tool, plz
## Post #87
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-08-28T22:27:44+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from zeeh
>
> Good work  Share the tool, plz

Its not finished yet.

Now that it repacks the files correctly. I will make it more user-friendly.
## Post #88
- Username: westernsys
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 13, 2010 11:19 pm
- Post datetime: 2010-08-29T08:05:38+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from caws
>
> zeeh wrote:Good work  Share the tool, plz 

Its not finished yet.

Now that it repacks the files correctly. I will make it more user-friendly.
This is very good news. I wouldn't mind a console app though, just wanna get my hands on it real quick
## Post #89
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2010-08-29T09:51:45+00:00
- Post Title: Re: Mafia II SDS files?

And modified lua bytecode decompiler working with M2 is still in progress?
## Post #90
- Username: Just
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 22, 2009 3:38 pm
- Post datetime: 2010-08-29T13:29:37+00:00
- Post Title: Re: Mafia II SDS files?

The Lua decompiler that was linked is incomplete, many language features aren't handled by it. If you want to check whether the opcodes have been changed you can use the disassembly option for the decompiler (that part is complete), if that doesn't crash then there are no new/changed opcodes and to decompile you "only" have to finish the decompiler.
## Post #91
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-08-29T18:08:26+00:00
- Post Title: Re: Mafia II SDS files?

So when will x360 support come?
## Post #92
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-08-30T10:40:27+00:00
- Post Title: Re: Mafia II SDS files?

xbox 360 version of my bms script with the endian swapped. few incorrect short/integer definitions updated on the way.

@tool makers - if your using my research, please link back to xentax
[sds_bmsbywrs_v3.zip](https://xentaxbackup.github.io/file/3387_sds_bmsbywrs_v3.zip)
## Post #93
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-08-30T15:25:31+00:00
- Post Title: Re: Mafia II SDS files?

Any news about tool?
## Post #94
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2010-08-30T19:49:47+00:00
- Post Title: Re: Mafia II SDS files?

Mod con una herramienta ?
## Post #95
- Username: bhrun
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Mar 20, 2010 8:20 pm
- Post datetime: 2010-08-31T13:45:03+00:00
- Post Title: Re: Mafia II SDS files?

[http://forum.gamevicio.com.br/i/topicos ... index.html](http://forum.gamevicio.com.br/i/topicos/92/92787-mafia-ii/index.html)

Brazilian guy made tool!
## Post #96
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-08-31T14:32:55+00:00
- Post Title: Re: Mafia II SDS files?

I cant find a tool link in the post.
## Post #97
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-09-01T00:25:42+00:00
- Post Title: Re: Mafia II SDS files?

The contents of this post was deleted because of possible forum rules violation.
## Post #98
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2010-09-01T02:19:42+00:00
- Post Title: Re: Mafia II SDS files?

Can made this in xbox360 ISO?
[http://www.imagebam.com/gallery/84p7e71 ... wrcrefn2dv](http://www.imagebam.com/gallery/84p7e71bt18z9q26l44t0qwrcrefn2dv)
## Post #99
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-09-01T11:40:03+00:00
- Post Title: Re: Mafia II SDS files?

Sorry guys, i'm having problems with energy supply at my house, hopefullly it will be fixed today.

Gotta go, im in a cyber cafe..

PS:My tool already repacks everything sucessfully. 

PS2:I will put the link on it to the forum of course, since all the work was from here.
## Post #100
- Username: bird
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 08, 2010 5:01 pm
- Post datetime: 2010-09-01T12:23:16+00:00
- Post Title: Re: Mafia II SDS files?

Thanks Caws, I really appreciate your work!
## Post #101
- Username: nightvison
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 20, 2009 2:35 pm
- Post datetime: 2010-09-01T16:49:49+00:00
- Post Title: Re: Mafia II SDS files?

Sds un/repacker

[http://www.ccgm.de/Mafia/II/SDSTool_v1.0.1.7z](http://www.ccgm.de/Mafia/II/SDSTool_v1.0.1.7z)
## Post #102
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2010-09-01T17:00:58+00:00
- Post Title: Re: Mafia II SDS files?

thats a unpacker, u can view some files (posters etc ) but u cant open/modify lua files, and you cant repack it, this tool that those gentlemens talking about, sounds far supperior  cant wait to look trough lua files and change them and try them out
## Post #103
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2010-09-01T18:03:58+00:00
- Post Title: Re: Mafia II SDS files?

does anyone know a good program to open and modify lua files ?:)
## Post #104
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2010-09-01T20:07:53+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from kalleoskar
>
> does anyone know a good program to open and modify lua files ?:)
[http://mafiascene.com/downloads?did=890](http://mafiascene.com/downloads?did=890)
## Post #105
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2010-09-01T20:14:45+00:00
- Post Title: Re: Mafia II SDS files?

thats the lua console, i meant to open the lua files that are in the sds files, but thanks anyway
## Post #106
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2010-09-01T20:32:14+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from kalleoskar
>
> thats the lua console, i meant to open the lua files that are in the sds files, but thanks anyway
Oh Sorry. I´m use translator,...
## Post #107
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2010-09-02T03:24:16+00:00
- Post Title: Re: Mafia II SDS files?

sweet the extractor gets me everything i need 

but wtf are these file types, i know the dss are textures but wheres the meshs... ps:srry fr noob question i see a few posts back that theres a tool or something, just want to get stuff into 3dmax
## Post #108
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2010-09-02T10:25:20+00:00
- Post Title: Re: Mafia II SDS files?

dont think there been released an model importer so u just have to be patient ^^ im waiting for a program to open and modify the lua files, there are a lot of things u can change then
## Post #109
- Username: SAS
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 08, 2008 6:38 pm
- Post datetime: 2010-09-02T13:44:06+00:00
- Post Title: Re: Mafia II SDS files?

here is packer\unpacker for sds files with very comfortable GUI [http://www.mafia2portal.ru/files/Soft/S ... v1.0.1.zip](http://www.mafia2portal.ru/files/Soft/SDSTool_GUI_v1.0.1.zip)
## Post #110
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2010-09-02T14:19:31+00:00
- Post Title: Re: Mafia II SDS files?

yes i know^^ its pretty good, but i need something to open and modify the lua files, there is all kind of nice stuff in there which u can unlock to use in freeride etc, but u cant use wordpad or other programs to open lua, just a lot of zeros and wierd letters. so please  help
## Post #111
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2010-09-02T20:44:27+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from kalleoskar
>
> yes i know^^ its pretty good, but i need something to open and modify the lua files, there is all kind of nice stuff in there which u can unlock to use in freeride etc, but u cant use wordpad or other programs to open lua, just a lot of zeros and wierd letters. so please  help

well modding halflife has some lua messing?.

maby a look on garrysmod for lua tuts or something might throw something up, ill have a look & see what i find 

lua linkie: [http://www.facepunch.com/forumdisplay.php?f=65](http://www.facepunch.com/forumdisplay.php?f=65)
## Post #112
- Username: Mbi2010
- Rank: Banned
- Number of posts: 15
- Joined date: Fri Sep 03, 2010 2:12 pm
- Post datetime: 2010-09-03T06:15:09+00:00
- Post Title: Re: Mafia II SDS files?

How to Increase the size of subtitles? Which file contains the settings size of subtitles?
Any idea?
## Post #113
- Username: cml
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 10, 2009 10:49 pm
- Post datetime: 2010-09-03T07:52:34+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from Mbi2010
>
> How to Increase the size of subtitles? Which file contains the settings size of subtitles?
Any idea?

Have the same question , maybe possible replace and use other one (more readable) ?
## Post #114
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2010-09-03T10:38:58+00:00
- Post Title: Re: Mafia II SDS files?

[http://www.dfordsoft.com/cs/LuaCodingSetup.zip](http://www.dfordsoft.com/cs/LuaCodingSetup.zip) found an awesome program for lua files! and the crosshair i think is in the gui map folder somewhere ^^
## Post #115
- Username: Mbi2010
- Rank: Banned
- Number of posts: 15
- Joined date: Fri Sep 03, 2010 2:12 pm
- Post datetime: 2010-09-03T10:40:21+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from cml
>
> Mbi2010 wrote:How to Increase the size of subtitles? Which file contains the settings size of subtitles?
Any idea?  

Have the same question , maybe possible replace and use other one (more readable) ?
Fix for Increasing size of subtitles in Mafia II.
Made by DronCho[CentR].

Install Notes:

1. Install to your Mafia II dir (...\Mafia II\);
2. Enjoy!

P.S. Installer provides backup of original files (see BACKUP_filename.sds_BACKUP) 

Download:

Russian installer - [mafia2_subfix.exe (1.27 MB)](http://www.multiupload.com/GJ7HOWVKZR)
English installer - [mafia2_subfix_en.exe (1.27 MB)](http://www.multiupload.com/623DZGWVIB)

[](http://fastpic.ru/view/9/2010/0903/a1e684879278327ea351f8c9635c7c8d.png.html) [](http://fastpic.ru/view/9/2010/0903/f9007ed5e71a1915ad714c9031bf0dcd.png.html) [](http://fastpic.ru/view/9/2010/0903/762aa81330ca0069ff0609ffe5a94501.png.html) [](http://fastpic.ru/view/9/2010/0903/23d5fd5a9f06e8a45f3b4709634b4960.png.html) [](http://fastpic.ru/view/9/2010/0903/939910df1db10a8d73503472859c5b0d.png.html) [](http://fastpic.ru/view/9/2010/0903/4f40c191d89daf742f3fcf4d534cd5f1.png.html) [](http://fastpic.ru/view/9/2010/0903/9b65f3e114f81e5c0f38b227e5fdfdac.png.html)
## Post #116
- Username: speedycars
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 04, 2010 3:34 am
- Post datetime: 2010-09-03T19:39:18+00:00
- Post Title: Re: Mafia II SDS files?

Hello,

I've already translated the main text file of the game, and imported it successfully into the game structure. But I have trouble with packing the bin subtitle files from missionscript folder. It seems they are not extracted correctly, or they're not packed correctly, or both.

Does anyone have more knowledge about SDS files in missionscript folder?!

The game shows error message that the load of the mission has failed. If you unpack and repack the untouched original files in these SDS's, it shows the same error. If you put the original SDS file, there is no problem at all...
## Post #117
- Username: venomtrk
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 28, 2009 5:36 am
- Post datetime: 2010-09-04T12:07:05+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from speedycars
>
> Hello,

I've already translated the main text file of the game, and imported it successfully into the game structure. But I have trouble with packing the bin subtitle files from missionscript folder. It seems they are not extracted correctly, or they're not packed correctly, or both.

Does anyone have more knowledge about SDS files in missionscript folder?!

The game shows error message that the load of the mission has failed. If you unpack and repack the untouched original files in these SDS's, it shows the same error. If you put the original SDS file, there is no problem at all...

I have the same problem as well. I'm translating the Turkish version of this great game but when you continue a mission sometimes it crashes to desktop. 

As you said, problem is missionscript sds files. If you unpack and repack just original files you will receive Load Failed message.
## Post #118
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-09-04T14:01:55+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from venomtrk
>
> speedycars wrote:Hello,

I've already translated the main text file of the game, and imported it successfully into the game structure. But I have trouble with packing the bin subtitle files from missionscript folder. It seems they are not extracted correctly, or they're not packed correctly, or both.

Does anyone have more knowledge about SDS files in missionscript folder?!

The game shows error message that the load of the mission has failed. If you unpack and repack the untouched original files in these SDS's, it shows the same error. If you put the original SDS file, there is no problem at all...

I have the same problem as well. I'm translating the Turkish version of this great game but when you continue a mission sometimes it crashes to desktop.
Damn!
## Post #119
- Username: speedycars
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 04, 2010 3:34 am
- Post datetime: 2010-09-05T10:08:38+00:00
- Post Title: Re: Mafia II SDS files?

The author of the SDSTool released a new version of his program, which fixes my problem.
## Post #120
- Username: Mbi2010
- Rank: Banned
- Number of posts: 15
- Joined date: Fri Sep 03, 2010 2:12 pm
- Post datetime: 2010-09-05T16:33:07+00:00
- Post Title: Re: Mafia II SDS files?

When support .sds from x360 will be possible? 

I can give some files from x360 version
## Post #121
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-09-05T18:23:55+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from Mbi2010
>
> When support .sds from x360 will be possible? 

I can give some files from x360 version

Remember you can already extract them using this BMS: [download/file.php?id=3387](http://forum.xentax.com/download/file.php?id=3387)
## Post #122
- Username: Mbi2010
- Rank: Banned
- Number of posts: 15
- Joined date: Fri Sep 03, 2010 2:12 pm
- Post datetime: 2010-09-05T19:02:49+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from WRS
>
> Mbi2010 wrote:When support .sds from x360 will be possible? 

I can give some files from x360 version 

Remember you can already extract them using this BMS: download/file.php?id=3387
I tried to unpack.sds from dlc
I have received many *.dat files is unpacked, what with them to do, how to open/unpack? 
[](http://fastpic.ru/view/9/2010/0905/488188f1644d886a17003af041543a44.png.html)

P.S. sds from dlc is encrypted, right?   I saw [DecryptTool for PC](http://mafia-empire.com/wiki/Gibbed_Tools), but it doesn't work with files x360... maybe somebody can fix it?
## Post #123
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2010-09-05T21:01:38+00:00
- Post Title: Re: Mafia II SDS files?

still all very good but we need something that will get the mesh's into 3dmax or blender.

i been working for the last few nights without sucsess.
## Post #124
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-09-07T23:00:40+00:00
- Post Title: Re: Mafia II SDS files?

DLC and other SDS files are encrypted. My DecryptSDS can work yes, but it's not made to work with 360 files, I'll look at making an update for it but it's not a primary concern of mine. The code is there if you want to fix it yourself.
## Post #125
- Username: forensic
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 08, 2010 9:13 am
- Post datetime: 2010-09-08T02:32:20+00:00
- Post Title: Re: Mafia II SDS files?

delete pls mispost ^^
## Post #126
- Username: Mbi2010
- Rank: Banned
- Number of posts: 15
- Joined date: Fri Sep 03, 2010 2:12 pm
- Post datetime: 2010-09-08T08:08:24+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from Rick
>
> DLC and other SDS files are encrypted. My DecryptSDS can work yes, but it's not made to work with 360 files, I'll look at making an update for it but it's not a primary concern of mine. The code is there if you want to fix it yourself.
Let's hope that you will make these tools for x360
## Post #127
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2010-09-09T04:40:19+00:00
- Post Title: Re: Mafia II SDS files?

3d ripper sucks balls :p haha

decided to jump in & give it a shot, plays pretty well but theres a whole lot of reorginizeing shit about once you capture a frame & even at that allmost half the textures are missing & uv-mapping gets messed up.

put my atention to other models at the mo but hopefully aint giveing up on this
## Post #128
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-09-10T07:44:38+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from Energy
>
> please text editor support. For all who need translate game please.
Yea please, i need too, and please much more i need a way to edit font, i mean characret table for font in normal way
## Post #129
- Username: Mbi2010
- Rank: Banned
- Number of posts: 15
- Joined date: Fri Sep 03, 2010 2:12 pm
- Post datetime: 2010-09-13T05:35:03+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from Rick
>
> DLC and other SDS files are encrypted. My DecryptSDS can work yes, but it's not made to work with 360 files, I'll look at making an update for it but it's not a primary concern of mine. The code is there if you want to fix it yourself.
any news?
## Post #130
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-09-13T14:15:12+00:00
- Post Title: Re: Mafia II SDS files?

No, it's not a priority for me, sorry.
## Post #131
- Username: jackpack
- Rank: advanced
- Number of posts: 47
- Joined date: Wed Sep 09, 2009 2:28 am
- Post datetime: 2010-09-13T18:20:43+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from Rick
>
> No, it's not a priority for me, sorry.

hey rick i bookmarked your blog  thats was a nice find 

you intrested in takeing on an aprentice :p

ps: come come i way behind & need mafia2 models, my game makeing is on hold aaaaaaa
## Post #132
- Username: Mbi2010
- Rank: Banned
- Number of posts: 15
- Joined date: Fri Sep 03, 2010 2:12 pm
- Post datetime: 2010-09-14T16:52:56+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from Rick
>
> No, it's not a priority for me, sorry.
 

Can you tell me what it is necessary to make to adapt these tools for 360 versions?
## Post #133
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-09-14T17:34:36+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from Mbi2010
>
> Rick wrote:No, it's not a priority for me, sorry.
 

Can you tell me what it is necessary to make to adapt these tools for 360 versions?

the 360 version uses big endian.
## Post #134
- Username: Mbi2010
- Rank: Banned
- Number of posts: 15
- Joined date: Fri Sep 03, 2010 2:12 pm
- Post datetime: 2010-09-14T21:29:57+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from WRS
>
> Mbi2010 wrote:Rick wrote:No, it's not a priority for me, sorry.
 

Can you tell me what it is necessary to make to adapt these tools for 360 versions?  

the 360 version uses big endian.
We can't convert to little-endian?
## Post #135
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2010-09-19T07:44:17+00:00
- Post Title: Re: Mafia II SDS files?

Anyone know the files that make the cars parked?

I found this for what it is to someone:
[http://svn.gib.me/public/illusion/trunk/](http://svn.gib.me/public/illusion/trunk/)
## Post #136
- Username: AmirATM
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 20, 2010 7:11 pm
- Post datetime: 2010-09-20T11:25:30+00:00
- Post Title: Re: Mafia II SDS files?

hello my friends

I want to translate mafia II and I read the hole topic, but can't find a straight guidance.   
I'm ultra-no0b in this case   So Is there anybody who can complain me?? I highly need details. (step by step in everything)

best regards
AmirATM
## Post #137
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2010-09-21T14:06:32+00:00
- Post Title: Re: Mafia II SDS files?

Guys, I really need the compiled version of the tool: Gibbed.Illusion.DecryptSDS that can be found here: [http://mafia-empire.com/wiki/Gibbed_Tools](http://mafia-empire.com/wiki/Gibbed_Tools)

I don't know how to compile it by myself. Please, I need this to decrypt the Jimmy's Vendeta DLC files, pc version. 

Thanx.
## Post #138
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2010-09-30T13:43:19+00:00
- Post Title: Re: Mafia II SDS files?

The contents of this post was deleted because of possible forum rules violation.
## Post #139
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2010-10-17T07:26:23+00:00
- Post Title: Re: Mafia II SDS files?

is it possible to extract and repack SDS from x360 version?
i wanna convert Freeplay Mod to xbox 360
## Post #140
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2010-10-18T14:05:45+00:00
- Post Title: Re: Mafia II SDS files?

abnyone? i really need to repack xbox 360 SDS
i wanna convert Freeplay Mod to xbox 360
## Post #141
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2010-11-04T13:37:02+00:00
- Post Title: Re: Mafia II SDS files?

He is a friend I'm wanting to convert the PS3, plus I'm not getting too ..

can anyone help?
## Post #142
- Username: hajradac
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 30, 2011 11:24 pm
- Post datetime: 2011-04-30T15:53:55+00:00
- Post Title: Re: Mafia II SDS files?

Hi fellas

where can i find  english subtitles in the game? I already found some subtitle files in the "missionscript" folder. I want to translate the game to hungarian language.
## Post #143
- Username: speedycars
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 04, 2010 3:34 am
- Post datetime: 2011-07-31T15:28:31+00:00
- Post Title: Re: Mafia II SDS files?

The contents of this post was deleted because of possible forum rules violation.
## Post #144
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-31T15:30:47+00:00
- Post Title: Re: Mafia II SDS files?

its not gonna happen its the ps3's npdrm encryption which no one has released the keys for.
## Post #145
- Username: speedycars
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 04, 2010 3:34 am
- Post datetime: 2011-07-31T16:01:16+00:00
- Post Title: Re: Mafia II SDS files?

So there is no way modding ps3 version of Mafia 2.
I've found encrypter/decrypter for sdata, but says it's not with the right key to decrypt it, like you said. 
Pity...  

[http://www.elitepvpers.com/forum/shaiya ... ource.html](http://www.elitepvpers.com/forum/shaiya-pserver-development/711369-release-sdata-encryptor-decryptor-w-source.html)
## Post #146
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2011-08-01T12:30:24+00:00
- Post Title: Re: Mafia II SDS files?

Any progress with the 3D formats? It's been a while but still no one bothered to make a workable import/export tool for M2 meshes.
## Post #147
- Username: speedycars
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 04, 2010 3:34 am
- Post datetime: 2011-09-07T12:09:41+00:00
- Post Title: Re: Mafia II SDS files?

Hi, does anyone have a contact with the author of Gibbed Illusion Tools?
I think he could help with decrypting/reading of XBOX sds files.
They could not be opened with the standard tools.
## Post #148
- Username: error
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Feb 15, 2011 7:42 am
- Post datetime: 2011-10-22T18:36:23+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from hajradac
>
> Hi fellas

where can i find  english subtitles in the game? I already found some subtitle files in the "missionscript" folder. I want to translate the game to hungarian language.

Well I've found the cutscenes subtitles here -> (D:\2K Games\Mafia II\pc\sds_en\fmv)
Extract the SDS files using ExSDS here [http://hotfile.com/dl/79794320/2dbe7a7/ExSDS.rar.html](http://hotfile.com/dl/79794320/2dbe7a7/ExSDS.rar.html)
Each SDS file contains 1 subtitle file inside which can be edited using notepad I guess

now the thing I need is to know how to put the edited file back in the SDS file, I mean I can extract it..but can't put replace it with the new one

Hope someone got a tool
## Post #149
- Username: Tabo8226
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 10, 2012 6:42 pm
- Post datetime: 2012-04-16T19:08:30+00:00
- Post Title: Re: Mafia II SDS files?

who can help me with fonts? i am interesting where are the main fonts? and if someone can help me to edit this?
## Post #150
- Username: mmm273
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Apr 14, 2012 9:30 pm
- Post datetime: 2012-04-17T12:40:23+00:00
- Post Title: Re: Mafia II SDS files?

any pprogress with X360 moding ? i love FreeRun mod in PC... how convert to x360 ?
## Post #151
- Username: leoaires
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Aug 06, 2012 9:06 am
- Post datetime: 2012-09-26T14:33:29+00:00
- Post Title: Re: Mafia II SDS files?

> Reply from WRS
>
> spent a little bit of time reversing some of the headers. the plaintext xml is for the engine to allocate memory (see the first header).

zlib data looks chunked. haven't yet bothered splitting up the files.

edit: haven't read the latest post - will download these new attachments now!
Code: Select all# -- WRS
#    xentax.com
#    .sds BMS script (wip)

print "WARNING: THIS SCRIPT WILL NOT DUMP ANYTHING YET (WIP)"

idstring "SDS\x00"

goto 16

### Part of the header

get P_RES long
get P_DATA long
get P_XML long
get TOT_RAM long # sum of all ram usage (see xml)
get TOT_VRAM long # sum of all vram usage (see xml)

###

get xmlsize asize
math xmlsize -= P_XML

log "sds_desc.xml" P_XML xmlsize


goto 64

### Res info

get RES_COUNT long
get UNKNOWN long
get RES_TYPES long

for i = 1 to RES_TYPES

  get RES_INDEX long
  get RES_NAME_sIZE long

  math RES_NAME_sIZE += 4 # padded byte
  getdstring RES_NAME RES_NAME_SIZE

  print "%RES_NAME%"

next i

### zlib data

goto P_DATA # will already be here


getdstring UNKNOWN 30 # some sort of header

set chunkcnt long 0

for

  get CHUNK_SIZE long

  if CHUNK_SIZE == 0

    print "Chunks found: %chunkcnt%"
    cleanexit

  endif

  get FLAG byte

  if FLAG == 0

    getdstring UNKNOWN 11

    ## zlib data is here

    savepos DATASTART

    ## todo: clog to memory_file, append result to result
    math DATASTART += CHUNK_SIZE

    goto DATASTART

  else

    get UNKNOWN long
    get SKIP long

    savepos SKIPVAL

    math SKIPVAL += SKIP
    math SKIPVAL -= 8

    goto SKIPVAL

    savepos DATASTART

    ## todo: clog to memor_file, append result to result
    math CHUNK_SIZE -= SKIP
    math DATASTART += CHUNK_SIZE

    goto DATASTART

  endif

  math chunkcnt += 1

next
With this .bms i can extract the files, but i can't reimport the same..
I really need this tool.. plz
## Post #152
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-05T10:27:51+00:00
- Post Title: Re: Mafia II SDS files?

When someone can see the files on ps3, ja could decrypt .sdat. is now .sds simple ps3.

[http://www.mediafire.com/?au2rtaww8fagdp7](http://www.mediafire.com/?au2rtaww8fagdp7)

Hugs.
## Post #153
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-13T18:15:47+00:00
- Post Title: Re: Mafia II SDS files?

UP.
## Post #154
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2014-10-11T16:29:33+00:00
- Post Title: Re: Mafia II SDS files?

Mafia 2 *.SDS Resource Unpacker: [http://www.extractor.ru/ipb/index.php?showtopic=5185](http://www.extractor.ru/ipb/index.php?showtopic=5185)

[](http://www.radikal.ru)
[Mafia II .SDS Resource Unpacker by ViolentPain.rar](https://xentaxbackup.github.io/file/7919_Mafia II .SDS Resource Unpacker by ViolentPain.rar)
## Post #155
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-12T22:37:45+00:00
- Post Title: Re: Mafia II SDS files?

Не актуальный инструмент. > [http://svn.gib.me/public/illusion/trunk/](http://svn.gib.me/public/illusion/trunk/)
## Post #156
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2014-10-13T08:44:51+00:00
- Post Title: Re: Mafia II SDS files?

Ekey там нет самой тулзы лишь src. Ты можешь собрать и кинуть на паблик?
## Post #157
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-13T13:28:33+00:00
- Post Title: Re: Mafia II SDS files?

Here
[Gibbed.Illusion_r42.rar](https://xentaxbackup.github.io/file/7928_Gibbed.Illusion_r42.rar)
## Post #158
- Username: jaqub
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 14, 2017 11:15 pm
- Post datetime: 2018-07-04T12:30:30+00:00
- Post Title: Re: Mafia II SDS files?

Hello again, There has been a big research into the models in the sds files around this year. most likely tools made for 3ds max to edit and create new in-game models. So, m2 map modding is nearly now possible thanks to @Greavesy!
Post (Mafiascene forum): [http://mafiascene.com/forum/viewtopic.php?t=10315](http://mafiascene.com/forum/viewtopic.php?t=10315) GitHub: [https://github.com/Greavesy1899/Mafia2Toolkit](https://github.com/Greavesy1899/Mafia2Toolkit)
my msg here was just to spread this around to find ppl with interrests, thought still ppl wanted to create new tools for Mafia 2.

Map import on 3ds max


collision model


Thanks for seeking this! I hope interrests woke for Mafia 2 modding!
## Post #159
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-07-04T17:21:39+00:00
- Post Title: Re: Mafia II SDS files?

Has anyone got SFX and voice files?
