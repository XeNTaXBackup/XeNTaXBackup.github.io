## Post #1
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-08-16T07:36:04+00:00
- Post Title: Star Wars - The Old Republic - Beta

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-16T09:24:00+00:00
- Post Title: Star Wars - The Old Republic - Beta

where can you download the entire client from?
Also the compression is zlib.

Quickbms script.

```
goto 0xC
get ftable long
goto 0x18
get files long
goto ftable
for i = 0 < files
get unk01 long
get unk02 long
get unk03 long
get offset long
get null01 long
get null02 long
get zsize long
get size long
get unk04 short
clog "" offset zsize size
next i



```
## Post #3
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-08-16T15:24:57+00:00
- Post Title: Star Wars - The Old Republic - Beta

look on your PM
## Post #4
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-08-17T07:00:58+00:00
- Post Title: Star Wars - The Old Republic - Beta

the script works.

but it seems we have different levels of data inside.
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-17T09:37:14+00:00
- Post Title: Star Wars - The Old Republic - Beta

Ill have to wait till the game comes out or is free to play i can not download the client.
## Post #6
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-12T23:10:40+00:00
- Post Title: Star Wars - The Old Republic - Beta

tor extractor
[http://code.google.com/p/easymyp/downloads/list](http://code.google.com/p/easymyp/downloads/list)
## Post #7
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-09-16T16:29:07+00:00
- Post Title: Star Wars - The Old Republic - Beta

good news ...

but your Quickbms script unpack into .DAT files
and your Hashcode list present all the tree of ressources with extension format


i hope test soon you TOR extractor but not present on your download list
## Post #8
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-18T14:58:57+00:00
- Post Title: Star Wars - The Old Republic - Beta

Hello everyone! I have done some research on the file types and thought I might as well share it with you. 
The wiki seems to be closed for creating pages or registering so I hope this is the right place for posting.

This file list could be used to improve the file recognition of easyMYP or to even build a complete SWTOR reader but is far from being finished.

To-do list (just to clarify: I do not plan to do all of this myself, so feel free to help out!):

 figuring out all file paths in the archives
 completing the list of all file extensions/file formats
 writing file specifications for the most important formats
 figuring out relationships between the files (eg. models/textures/animations belong together, so do dialogues/string tables/sound files) and possibly drawing a graph with the interdependencies
 writing a SWTOR tool that can handle all these files
EDIT: Note: This specification is outdated and only kept as a historical reference. The newest specification can be found on page 6 of this thread.

Archive files
These files are archives that contain other files.

File extension: .tor
File header: MYP
Description: Main archive for all files. In /Assets folder. Files start with either assets_, red_, or green_, depending on the type of beta version. Can be extracted with [easyMYP](http://code.google.com/p/easymyp/).

File extension: .bkt
File header: PBUK........DBLB
Description: Bucket files, contain compiled XML files with zlib encoding. See below for a specification.

File extension: .bnk
File header: BKHD
Description: Soundbank that contains multiple .ogg sound files. Sections are named DIDX, DATA, HIRC, STID. Search for "bnkextr" tool in [this topic](http://forum.xentax.com/viewtopic.php?f=17&t=3477&start=30).

File extension: .gom
File header: DBLB
Description: eg. client.gom. Contains files with zlib encoding.

File extension: .acb
File header: XX XX XX XX 00 00 00 00
Description: ACB soundbank that contains multiple .ogg sound files with the file extension .wem, similar to the BKHD archives. See page 4 of this thread for a specification.

Filelists
These files contain a list with references to other files.

File extension: .list
File header: SDEF or SIDS
Description: The first one references SCPT files, the other contains the files from assets_system_1.tor.

File extension: .info
File header: PINF or PBUK
Description: The first one references .node files, the other one .bkt files.

Compiled files
These files are binary files and can only be read in a HEX editor or designated reader.

File extension: .bik
File header: BIKi (42 49 4B 69)
Description: Regular Bink Video files, contained in the /Movies folder (ie. not part of the TOR archives). Can be opened with the [RAD Video Tools](http://www.radgametools.com/bnkdown.htm).

File extension: .bin
Description: Very small file without a header. Seems to contain version information.

File extension: .dds
File header: DDS
Description: Normal DDS texture (Direct Draw Surface), can be opened in any DDS reader.

File extension: .elf
File header: .ELF (7F 45 4C 46)
Description: Normal ELF script (Executable and Linkable Format), contained in the SCPT files. Can be opened in any ELF reader, including IDA Pro.

File extension: .fxa
File header: FACE (46 41 43 45)
Description: Facial animations, matched to the localised voices in the sound files.

File extension: .gfx
File header: CFX or GFX
Description: See swtor_fonts.gfx.

File extension: .gr2
File header: )ÞlÀ (29 DE 6C C0)
Description: Granny Format by RAD Game Tools, contains the models. See [this topic](http://forum.xentax.com/viewtopic.php?f=16&t=7403) and [that topic](http://forum.xentax.com/viewtopic.php?f=16&t=7705).

File extension: .jba
File header: 00 00 00 00
Description: Possibly contains animations. easyMYP automatically classifies them as zero.txt.

File extension: .mph
File header: 02 00 00 00
Description: Contains list of animations in a compiled format.

File extension: .node
File header: PROT.... (50 52 4F 54 02 00 04 00)
Description: Contains a compiled form of the XML dialogues and stringtables. See /resources/systemgenerated/prototypes/.

File extension: .ogg
File header: RIFF..6.WAVEfmt
Description: Ogg sound file with WWise encoding. Dialogue and sound effects are contained in .bnk/BKHD archives, music/soundtrack is stored in /resources/bnk/streamed/. See [here](http://hcs64.com/vgm_ripping.html) for the decoding tool ww2ogg.

File extension: .swf
File header: CWS. (43 57 53 0A)
Description: Normal Adobe Flash file, apparently used for fonts.

File extension: n/a
File header: AMX (41 4D 58 20)
Description: Contains animations.

File extension: n/a
File header: ¥+..BNRY....LTLE
Description: One file is called mount_neu_model_e_scheme_04. The first two bytes can vary but BNRY and LTLE are always in there. This seems to be part of the GR2 model files and may just as well be an error of the MYP extractor.

File extension: (none)
File header: SCPT
Description: Contains header with some strings and a ELF script file (Hydra script?). See the folder /resources/systemgenerated/compilednative/. See below for a specification.

Human-readable files (txt/xml)
These files can be opened and edited in normal text or XML editors, although I would recommend using a hex editor for editing. The files should be pretty self-explanatory.
Note: Many XML files use a encoding like ÿþ<.S.u.r.v.e.y.I.n.s.t.a.n.c.e.>, ie. a Byte Order Mark for Unicode encodings. Also, some have an <!xml> tag before the first tag.

File extension: .dat
Description: Text file. Contains definitions of the rooms/maps. Comments are marked with an exclamation mark at the beginning of a line, eg. "! Room Specification". Some files contain textures(?), to do that copy the hex bytes into a hex editor and decode them using gzip.

File extension: .dyc
Description: Text file. Sometimes begins with "Version=2". See /resources/art/dynamic/spec/.

File extension: .fxspec
File header: <nodeWClasses>
Description: XML file.

File extension: .lod
File header: <LODSchemaGroup>
Description: XML file.

File extension: .mag
Description: Text file. Comments are marked with an exclamation mark at the beginning of a line, eg. "! Character Specification for ...".

File extension: .mat
File header: <Material> (EF BB BF  ï»¿)
Description: XML file.

File extension: .mpn
File header: <mapNoteTemplate>
Description: XML file. See also /engine/mapnoteinstance.mpn.

File extension: .not
File header: <v><k>mapNotes</k><e>
Description: XML file.

File extension: .rul
File header: <Rules>
Description: XML file.

File extension: .svy
File header: <SurveyInstance> (FF FE  ÿþ)
Description: XML file. Survey/questionnaire for beta players about gameplay performance.

File extension: .tbl
File header: <DataTable>
Description: XML file. Contains a table with gameplay data, like amount of damage dealt.

File extension: .tex
File header: <TextureObject>
Description: XML file. Contains information on how to use the textures, eg. whether to stretch or clamp them.

File extension: .xml
File header: <aam> or <Assets> or <Palette>
Description: XML file.

There are a few more XML files, like <Ability>, <plcTemplate>, <spnTemplate>, <npcTemplate>, <Maps>, <Appearance>, <Item>, <HydraScriptMap>, <clientOnlySpawner>, <PlayerCustomizationSet>, <quest>, and <Sectors>, although I have not yet found out their file extensions.

Unknown engine files
I have seen these extensions mentioned in file paths but I have not yet found the respective files themselves.

File extension: .amk
Description: /engine/actionmark.amk.

File extension: .bil
Description: /engine/billboard.bil.

File extension: .bon
Description: /engine/bonetracker.bon.

File extension: .box
Description: /engine/genericbox.box.

File extension: .cam
Description: /engine/placeablecamera.cam.

File extension: .cdr
Description: /engine/cover/cover_dirty_region.cdr.

File extension: .cvr
Description: /engine/cover_point.cvr.

File extension: .ext
Description: /engine/projector.ext.

File extension: .fla
Description: /engine/flare.fla.

File extension: .fol
Description: /engine/follower.fol.

File extension: .fxp
Description: /engine/fxplaceable.fxp.

File extension: .hms
Description: /engine/heightmap.hms.

File extension: .lit
Description: /engine/light.lit.

File extension: .mir
Description: /engine/mirror.mir.

File extension: .osg
Description: In sectors XML: <CollisionFileName>data3D/sector_1011.osg</CollisionFileName>.

File extension: .p
Description: /engine/portal.p.

File extension: .phy
Description: /engine/physics.phy.

File extension: .phj
Description: /engine/physicsjoint.phj.

File extension: .rbd
Description: /engine/roombound.rbd.

File extension: .rgn
Description: /engine/region.rgn.

File extension: .sfq
Description: /engine/sf_gfx_quad.sfq.

File extension: .spn_activator
Description: /engine/spawnactivator.spn_activator.

File extension: .spn_c
Description: /engine/spawn_creature.spn_c.

File extension: .spn_crf
Description: /engine/spawn_crefac.spn_crf.

File extension: .spn_grp
Description: /engine/spawn_group.spn_grp.

File extension: .spn_lst
Description: /engine/spawn_list.spn_lst.

File extension: .spn_med
Description: /engine/spawn_medcenter.spn_med.

File extension: .spn_mov
Description: /engine/move_point.spn_mov.

File extension: .spn_p
Description: /engine/spawn_placeable.spn_p.

File extension: .spn_pt
Description: /engine/spawn_point.spn_pt.

File extension: .spn_rez
Description: /engine/spawn_rezpoint.spn_rez.

File extension: .spn_rly
Description: /engine/rally_point.spn_rly.

File extension: .spn_veh
Description: /engine/spawn_vehicle.spn_veh.

File extension: .stg
Description: /engine/stginstance.stg.

File extension: .trg
Description: /engine/trigger.trg.

File extension: .wtr
Description: /engine/basewater.wtr.

File extension: .wws
Description: /engine/wwiseaudio.wws.

File extension: .zzp
Description: /engine/zap.zzp.


Edit 1: Updated list with new information on some formats.
Edit 2: WEM archives added.
Edit 3: WEM archives updated (file extension: *.acb).
## Post #9
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2011-11-18T20:24:28+00:00
- Post Title: Star Wars - The Old Republic - Beta

Where can we download the béta from ?

T.
## Post #10
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-19T16:54:49+00:00
- Post Title: Star Wars - The Old Republic - Beta

Integer format specifications
In many compiled formats I have seen two types of integers being used, and I want to document them here so that I can refer to them in other file specifications.

I do not know much about compressed files, so these may be industry standards and have a special name. If you know more about them, please tell me so that I can correct the specification.

Fixed-sized integers
These integers are always four bytes long (or sometimes two or eight bytes).
They are stored in little-endian format and are often used to store the string length of the file name.

Example:
01 00 00 00 → Number 1
10 00 00 00 → Number 16
00 01 00 00 → Number 256

Variable-sized integers (C8/C9/CA/... format)
These integers take up different byte sizes depending on the size of the integer and use the big-endian format.
For sizes smaller than C0, the integer is written as one byte. Otherwise, a byte specifying the length is prepended before the integer:

Hex bytes and their meaning:
XX → Integers 00 to C0
C8 XX → Integer 00 to FF (1 byte/8 bit)
C9 XX XX → Integers up to 256^2 (2 bytes/16 bit)
CA XX XX XX → Integers up to 256^3 (3 bytes/24 bit)
CB XX XX XX XX → Integers up to 256^4 (4 bytes/32 bit)
CC XX XX XX XX XX → Integers up to 256^5 (5 bytes/40 bit)
CD XX XX XX XX XX XX → Integers up to 256^6 (6 bytes/48 bit)
CE XX XX XX XX XX XX XX → Integers up to 256^7 (7 bytes/56 bit)
CF XX XX XX XX XX XX XX XX → Integers up to 256^8 (8 bytes/64 bit)

Example:
C8 FF → Number 255
C9 01 00 → Number 256
C9 01 01 → Number 257
C9 01 02 → Number 258

So far, CF integers were the highest ones I have seen.
Sometimes, there is a C7 byte before an integer, and (like the CF byte) eight bytes follow, making it a total of nine bytes:
C7 XX XX XX XX XX XX XX XX → Integers up to 256^8 (8 bytes/64 bit)
I do not know what the difference between C7 and CF is.

Edit 1: Added description for C7 integers.
## Post #11
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2011-11-20T10:26:23+00:00
- Post Title: Star Wars - The Old Republic - Beta

Things to note:

1. A lot of files have been removed from the latest versions of the client so it will be increasingly difficult to discover proper filenames. Namely - most datatables and human readable xml files have been removed from the client and they held most information about proper filenames. For example - <Item> xml files contained the names of the item icons and these are not in the client anymore (as far as I know - please correct me if I am wrong - but I can't find them in red_ nor green_).

2. PROT files are a bit strange. I was able to extract (without fully understanding what all the bytes in it mean) some stringtable PROT files (I managed to extract lists of strings from them), but there are other prot files that have a different structure, so my method is not universal enough. I am not very experienced in game archive extraction - are PROT files zlibed (they do not look like they are to me - feels like their propriety binary archive/storage format)
## Post #12
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-20T13:32:42+00:00
- Post Title: Star Wars - The Old Republic - Beta

Just to let you know, I have already analysed most parts of the PROT files.
Those PROT files that are not stringtables are just a compiled version of the <Dialogue> xml files. They contain information on which dialogue options are possible and which answers follow after a sentence. Also, they contain the animations and camera movements during the dialogue.
Rest assured, I will probably write a specification for them as well, although the PROT files are currently not my highest priority.

It is worrysome that the newest archives no longer contain the xml files. I have not yet looked at the newest version so I can't confirm it.
However, that would explain why the dialogue and string files were included both in xml and compiled format (I had wondered what the difference between them is and which format is used by the program). Have you discovered any test files or are they also gone in the newest clients?
## Post #13
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-20T14:03:14+00:00
- Post Title: Star Wars - The Old Republic - Beta

SCPT file specification (version 4)

EDIT: The newest script files now use version 5. See page 7 for an updated specification.
Original text:

For starters, I want to post the specification of the SCPT format as it seems to be one of the easiest ones.
The SCPT files are can be found in assets_system_1.tor and are extracted into the folder /resources/systemgenerated/compilednative/. The files do not have an extension but are named after a number, like /resources/systemgenerated/compilednative/14988172135558299366. However, the file header begins with SCPT, or 53 43 50 54 in Hex.
Each SCPT file contains a script name, optionally a list of strings, and finally an uncompressed ELF file (Executable and Linkable Format) that can be opened in a normal ELF disassembler like [IDA Pro](http://www.hex-rays.com/products/ida/index.shtml).
Unfortunately, I fear that except for the strings, there is not much use with looking at assembler language, unless someone manages to extract the function names and format the assembler code nicely.
I do not yet know the quickBMS format so I can only give a general outline and no code, sry 

File header (16 bytes):
The file header is always the same.
0-3: 4 Bytes: SCPT (53 43 50 54)
4-5: file version as 16-bit integer (little-endian): 04 00
6-7: file version as 16-bit integer (little-endian): 04 00
8-11: Unknown 32-bit integer (little-endian): 01 00 00 00
12-15: Unknown 32-bit integer (little-endian): 00 00 00 00

CRC checksum:
16-21: 6-byte checksum (possibly CRC-32), always different for each file.
Examples:
6D B5 71 08 DF E9   (mµq.ßé)
5B 7C 43 5D 64 9D   ([|C]d.)
24 FD 2C CB 2A B2   ($ý,Ë*²)
C0 3A D3 4D A5 B8   (À:ÓM¥¸)

22-23: Two unknown bytes, always: .Ð (00 D0)

File name:
24-27: 32-bit integer specifying string length (little-endian), eg. 21 (15 00 00 00)
28-...: A string with the specified length. This string equals the name of the script file.
Examples: _AiDebuggerClassMethods, _BaseClientClassMethods, _CharacterSystemClassMethods, _ContextMenus, _DebugClassMethods, _ExternalFunctions, _FxSystemClassMethods, _GUIBaseWindowClassMethods, _GUIButtonClassMethods, ...

Unknown lengths:
8 zero bytes: 00 00 00 00 00 00 00 00
Unknown 32-bit integer (little-endian), eg. 94 43 00 00 or 79 0B 00 00 or 6E 05 00 00
→ This integer could stand for the file size, although I have not yet verified this.

List of strings:
Variable-length integer specifying number of strings, eg. 04
LOOP (for each string) {
→ Variable-length integer specifying length of string, eg. 0E
→ String with the specified length, eg. <font color='
}

ELF file:
Unknown variable-length integer, eg. C9 09 EC or C9 3B 2C
→ This integer could stand for the ELF file size, although I have not yet verified this.
From this point on to the rest of the file follows the ELF file. It has the header .ELF (7F 45 4C 46) and can be opened in any ELF disassembler.
## Post #14
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2011-11-20T14:17:35+00:00
- Post Title: Star Wars - The Old Republic - Beta

In the xml files they have left in there are still some files with the .test. identification. However, I think the only files left are those describing maps, rooms, 3d models and such. I am guessing they are streaming the rest.
## Post #15
- Username: DKK
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 20, 2011 11:45 am
- Post datetime: 2011-11-20T17:19:57+00:00
- Post Title: Star Wars - The Old Republic - Beta

The contents of this post was deleted because of possible forum rules violation.
## Post #16
- Username: badmp3
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 21, 2011 1:48 am
- Post datetime: 2011-11-20T17:52:46+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi - 

Just started using the EASYMPY to extract the files from TOR.

But my question is how did you get the filenames and correct directories to show? 

All I have are some folders for csv, txt, xml, dds and all the filenames are some weird numbers / letters.
## Post #17
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-20T18:32:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Wow, it's great to see how much response the topic got, thank you to everyone who wants to help out with the analyses! 

> Reply from badmp3
>
> But my question is how did you get the filenames and correct directories to show?
The problem with the TOR archives is that the filenames themselves are not stored in the archives, but only their hashes. That's why you get these weird numbers as filenames, like DEADBEEF_9C022D76484096A0.txt.
However, some xml files contain file paths and we can guess some filenames manually, but unfortunately not all.
On the easyMYP Google Code page there is a TOR-found.rar file that has about 17% of all filenames. But even better is [this file](http://www.megaupload.com/?d=YHWTMG4E) which has about 50% of all filenames.
Now to load these filenames into easyMYP, you have to first download and extract the archives. Then go to the folder where you have easyMYP saved and create a subfolder called "Hash". In this folder you can copy the file "hashes_download.txt" and then run easyMYP. It will automatically recognize the filenames if they are known, and extract the remaining ones as DEADBEEF_9C022D76484096A0.txt.
If you want to, you can of course try to find more filenames and publish them. I am confident we will soon have a list of all filenames, but with every new beta version new files are added or old ones removed so we always have to update the list.

> Reply from DKK
>
> There seems to be a good amount of data stuffed into the bucket files.
I'm relatively new to this so any help extracting would be appreciated.
@DKK: I already started analysing the bucket files as well and will post what I have got so far in a separate post.
## Post #18
- Username: badmp3
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 21, 2011 1:48 am
- Post datetime: 2011-11-20T18:45:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

When I place that Hash file the 50% one into the Hash folder and start up the program it crashes!

says 

EasyMYP has stopped working

im on Vista64 - not sure if thats the issue ... if i remove that file from the hash folder the program will start up again..


This is how the other generated ones show up as 

```
green_main_18?80420A6E?9946BCAE??A8111BD5
green_main_18?8047F092?E876C8B3??BEE2E22C
green_main_18?8052441B?BCBFC74F??3291FFA7
green_main_18?805BA3D9?BD4A1134??14ACD279
green_main_18?805D2840?46E1632C??B05DF64C
green_main_18?8066EF20?FD564B45??58DE0F47
```
## Post #19
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-20T19:47:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Bucket file specification (.bck file/PBUK DBLB file)
The bucket files are an archive that contains small files with zlib encoding.
They can be found in assets_system_1.tor and are extracted into the folder /resources/systemgenerated/buckets/. The file extension is .bck, the header starts with PBUK.
The file names are sequentially numbered from 0.bck onwards, a list of all bucket files can be found in /resources/systemgenerated/buckets.info.
There are quite a few integers that I am not sure about what they mean, so any help is appreciated. 

File header:
0-3: 4 byte identifier: PBUK (50 42 55 4B)
4-5: Unknown 16-bit little-endian integer (maybe number of DBLB sections?), always 02 00
6-7: Unknown 16-bit little-endian integer, always 04 00

DBLB block:
LOOP (for each DBLB block) {
--- 32-bit little-endian integer specifying the size of this block starting with DBLB, eg. 0C 00 00 00 or 64 A0 03 00
--- 4 byte identifier: DBLB (44 42 4C 42)
--- Unknown 32-bit little-endian integer, always 01 00 00 00
--- 32-bit little-endian integer specifying number of files in this block, eg. B6 00 00 00
--- LOOP (for each file in this block) {
--- --- Unknown 16-bit little-endian integer, always 0F 00
--- --- Unknown 16-bit little-endian integer, eg. 52 00 or 66 00 or 71 00
--- --- 6 unknown bytes (maybe CRC checksum?), eg. 01 FC 70 C1 12 01 or  20 32 63 27 01 or 80 0D 21 92 E2 0A
--- --- 4 bytes, always 00 E0 2E 00
--- --- Unknown 16-bit little-endian integer, always lower by one than the previous integer, eg. 51 00 or 65 00 or 70 00
--- --- Unknown 32-bit little-endian integer, eg. 17 00 00 00
--- --- 4 unknown bytes (maybe CRC checksum?), eg. 50 14 1E E2 or 0E CD 1A 01
--- --- 6 unknown bytes, always 00 00 00 40 00 00
--- --- Unknown 16-bit little-endian integer, eg. 58 00 or 68 00 or 78 00
--- --- Unknown 32-bit little-endian integer, eg. 61 00 00 00 or 63 02 00 00 or 74 01 00 00
--- --- Unknown 16-bit little-endian integer equal to the one two lines above, eg. 58 00 or 68 00 or 78 00
--- --- Unknown 16-bit little-endian integer, always 04 00
--- --- Two unknown bytes, always 01 03
--- --- String with a variable length until 00 00, specifying FQN of this file, eg. ipp.class.spy.a05.c02.s02.legs_v01
--- --- Separator/end of string, always 00 00
--- --- Beginning of a file, it is unknown where its length is stored. In most cases, the file starts with xœ (78 9C) and can be decoded with zlib.
--- --- 3 unknown bytes, identifying end of section, either 00 00 00 or 01 00 00
--- } END LOOP
} END LOOP
## Post #20
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-20T20:13:34+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from badmp3
>
> When I place that Hash file the 50% one into the Hash folder and start up the program it crashes!
The error may occur because those filename lists are based on earlier versions where the TOR files had the prefix assets_ and not green_. That's also why the filenames are not recognized in the 17% file.
I do not yet have the current version so unfortunately I cannot help you with it. You could try looking in the readme and playing with the "Test filename list" settings.
## Post #21
- Username: badmp3
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 21, 2011 1:48 am
- Post datetime: 2011-11-20T20:18:51+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

So your saying if I was to download EasyMYP and download that 50% hash file, insert it into the hash folder and start it up ... to which it crashes .. is caused due to different file names that I havent scanned yet ..

Isnt that a tad weird?
## Post #22
- Username: badmp3
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 21, 2011 1:48 am
- Post datetime: 2011-11-20T20:22:07+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Btw - Since you have the older verison did you happen to get any valueable data to which you may wanna share?

Alot of the big brand gaming db sites have tons of SWTOR information already and I can only assume its either from these client files or SWTOR gave them a database dump of sorts...

Did you find data about quests, skill tress, npcs, companions, icon files? Any data you can share?

Only things so far that I noted was as Ive been looking over the many .xml files I saw they had the full companion dialogs ..
## Post #23
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-20T20:23:30+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Sorry, my mistake. The 50% file is actually based on a newer of version of easyMYP, no wonder why it crashes.
You can download the new, special TOR build of easyMYP [here](http://holocron.so/files/tormyp.tar.bz2).
However, I cannot tell you if this tool will recognize the filenames from the newest beta version.

By the way, the 17% file can only be opened in the older version of easyMYP, but all of the files in there are also contained in the 50% file.

Edit:
As far as I know, the big gaming sites get these information from playing the beta versions. After all, the beta tests have been going one for a few months, and only a few days ago the NDA has been lifted so every one can talk about them. I doubt that someone has made any further progress in analysing the files than we currently have.
And yes, I have some exclusive story information but I want to follow Bioware's nonbinding request to not spoil any storylines until the game's release. And I don't want to convert this topic into "SWTOR spoiler information" since this would be off-topic. There are lots of gaming forums that have more than enough exclusive information. I recommend Wookieepedia or the SWTOR wiki as they are always on the frontline when it comes to spoilers, although I do not know if they will honor Bioware's request.
So sorry, I cannot help you with this, you have to look somewhere else. There is very much story in the game; I have only seen a small part of the files and even that took a long time to read.
## Post #24
- Username: badmp3
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 21, 2011 1:48 am
- Post datetime: 2011-11-20T20:33:11+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> Sorry, my error. The 50% file is actually based on a newer of version of easyMYP, no wonder why it crashes.
You can download a new, special TOR build of easyMYP here.
However, I cannot tell you if this tool will recognize the filenames from the newest beta version.

By the way, the 17% file can only be opened in the older version of easyMYP, but all of the files in there are also contained in the 50% file.

That verison worked, the HASH file was taken in no problems
## Post #25
- Username: badmp3
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 21, 2011 1:48 am
- Post datetime: 2011-11-20T20:57:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have a really old SWTOR Beta client that has 1 big file called smallassests.p2v  (7GB) 

Would ya know a way to take a peek at whats inside this?

I tried rename the file to TOR and use EASYMYP but it will crash out ... it starts estimating files gets to like 460k then the program dies..
## Post #26
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-20T21:11:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from badmp3
>
> I have a really old SWTOR Beta client that has 1 big file called smallassests.p2v  (7GB)
Very interesting, I have not yet heard of that file.  In which folder is this file stored? Is it the Assets/ folder?
If you are ever unsure how to open a file, you can use a hex editor to see its contents. I recommend [HxD](http://mh-nexus.de/en/hxd/) as it is a freeware standalone/portable hex editor.
You can open the file in there (fortunately, HxD is very fast and can easily open files this large). Just copy the first few lines (maybe 3 MB), save them as a new file and upload the small file.
This should be enough for us to analyse the basic format of the file but you may need to upload other parts later as well.
## Post #27
- Username: badmp3
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 21, 2011 1:48 am
- Post datetime: 2011-11-20T21:26:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

That file is from a veryyy early beta... its in the main folder.

heres the first lines 

```
 .Ø.............
 .Ø............
ÃžØ×............
```
## Post #28
- Username: DKK
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 20, 2011 11:45 am
- Post datetime: 2011-11-21T00:54:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> Bucket file specification (.bck file/PBUK DBLB file)
The bucket files are an archive that contains small files with zlib encoding.
They can be found in assets_system_1.tor and are extracted into the folder /resources/systemgenerated/buckets/. The file extension is .bck, the header starts with PBUK.
The file names are sequentially numbered from 0.bck onwards, a list of all bucket files can be found in /resources/systemgenerated/buckets.info.
There are quite a few integers that I am not sure about what they mean, so any help is appreciated. 

File header:
0-3: 4 byte identifier: PBUK (50 42 55 4B)
4-5: Unknown 16-bit little-endian integer (maybe number of DBLB sections?), always 02 00
6-7: Unknown 16-bit little-endian integer, always 04 00

DBLB block:
LOOP (for each DBLB block) {
--- 32-bit little-endian integer specifying the size of this block starting with DBLB, eg. 0C 00 00 00 or 64 A0 03 00
--- 4 byte identifier: DBLB (44 42 4C 42)
--- Unknown 32-bit little-endian integer, always 01 00 00 00
--- 32-bit little-endian integer specifying number of files in this block, eg. B6 00 00 00
--- LOOP (for each file in this block) {
--- --- Unknown 16-bit little-endian integer, always 0F 00
--- --- Unknown 16-bit little-endian integer, eg. 52 00 or 66 00 or 71 00
--- --- 6 unknown bytes (maybe CRC checksum?), eg. 01 FC 70 C1 12 01 or  20 32 63 27 01 or 80 0D 21 92 E2 0A
--- --- 4 bytes, always 00 E0 2E 00
--- --- Unknown 16-bit little-endian integer, always lower by one than the previous integer, eg. 51 00 or 65 00 or 70 00
--- --- Unknown 32-bit little-endian integer, eg. 17 00 00 00
--- --- 4 unknown bytes (maybe CRC checksum?), eg. 50 14 1E E2 or 0E CD 1A 01
--- --- 6 unknown bytes, always 00 00 00 40 00 00
--- --- Unknown 16-bit little-endian integer, eg. 58 00 or 68 00 or 78 00
--- --- Unknown 32-bit little-endian integer, eg. 61 00 00 00 or 63 02 00 00 or 74 01 00 00
--- --- Unknown 16-bit little-endian integer equal to the one two lines above, eg. 58 00 or 68 00 or 78 00
--- --- Unknown 16-bit little-endian integer, always 04 00
--- --- Two unknown bytes, always 01 03
--- --- String with a variable length until 00 00, specifying FQN of this file, eg. ipp.class.spy.a05.c02.s02.legs_v01
--- --- Separator/end of string, always 00 00
--- --- Beginning of a file, it is unknown where its length is stored. In most cases, the file starts with xœ (78 9C) and can be decoded with zlib.
--- --- 3 unknown bytes, identifying end of section, either 00 00 00 or 01 00 00
--- } END LOOP
} END LOOP

I'm wondering if  Bytes 4-5 and 6-7 are some kind of version tag as my bkt files (as linked in my previous post) are all 02 00 05 00 as opposed to your 02 00 04 00
The same applies to the 32-bit integer following the first DBLB where yours read 01 00 00 00 mine read 02 00 00 00
## Post #29
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2011-11-21T01:01:11+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

For whatever reason these feel like compressed XML files to me
## Post #30
- Username: DKK
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 20, 2011 11:45 am
- Post datetime: 2011-11-21T01:49:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I found additional changes between these versions of the BKT files.  Here's what I've come up with:

Bucket file specification (.bkt file/PBUK DBLB file)
The bucket files are an archive that contains small files with zlib encoding.
They can be found in assets_system_1.tor and are extracted into the folder /resources/systemgenerated/buckets/. The file extension is .bkt, the header starts with PBUK.
The file names are sequentially numbered from 0.bkt onwards, a list of all bucket files can be found in /resources/systemgenerated/buckets/

File header:
0-3: 4 Byte ID: PBUK (50 42 55 4B)
4-5: Unknown 16-bit little-endian integer (# of DBLB sections?), always 02 00
6-7: Unknown 16-bit little-endian integer (version?), always 05 00

DBLB block:
LOOP (for each DBLB block) {
--- 32-bit little-endian integer specifying the size of this block starting with DBLB, eg. 0C 00 00 00 or 64 A0 03 00
--- 4 byte identifier: DBLB (44 42 4C 42)
--- Unknown 32-bit little-endian integer, always 02 00 00 00
--- 32-bit little-endian integer specifying number of files in this block, eg. B6 00 00 00

--- LOOP (for each file in this block) {
--- --- 32-bit Null 00 00 00 00
--- --- 6 unknown bytes (maybe CRC checksum?), eg. 01 FC 70 C1 12 01 or 8D 20 32 63 27 01 or 80 0D 21 92 E2 0A
--- --- 4 bytes, always 00 E0 0F 00
--- --- Unknown 16-bit little-endian integer, always lower by one than the previous integer, eg. 51 00 or 65 00 or 70 00
--- --- Unknown 32-bit little-endian integer, eg. 17 00 00 00
--- --- 4 unknown bytes (maybe CRC checksum?), eg. 50 14 1E E2 or 0E CD 1A 01
--- --- 2 unknown bytes: typically 00 00 but values of 03 00, 04 00, and 05 00 have also been spotted
--- --- 8 unknown bytes, always 00 40 00 00 00 00 00 00
--- --- Unknown 16-bit little-endian integer, eg. 58 00 or 68 00 or 78 00
--- --- Unknown 32-bit little-endian integer, eg. 61 00 00 00 or 63 02 00 00 or 74 01 00 00
--- --- Unknown 16-bit little-endian integer equal to the one two lines above, eg. 58 00 or 68 00 or 78 00
--- --- Unknown 16-bit little-endian integer, always 05 00
--- --- Two unknown bytes, always 01 03
--- --- String with a variable length until 00 00   (I saw at least one file while scanning through one of the buckets, that seemed to end with 00 01 -- was very much a one-off thing and I couldn't find it replicated elsewhere), specifying FQN of this file, eg. ipp.class.spy.a05.c02.s02.legs_v01
--- --- Separator/end of string, always 00 00 
--- --- Beginning of a file, it is unknown where its length is stored. In most cases, the file starts with xœ (78 9C) and can be decoded with zlib.
--- --- 3 unknown bytes, identifying end of section, either 00 00 00 or 01 00 00
--- } END LOOP
} END LOOP
## Post #31
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2011-11-21T12:40:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

In the first file I tried (client green - file '0.bkt') I found that between the FQN of the file and the zlib-ed conten the separator might or might not be 00 00.

After FQN qst.test.location.dromund_kaas.bronze.jungle_raid there is only one 00 before zlib header.

The sad thing is that even ufter unpacking the zlib-ed content you are faced with more encoded/compressed stuff. There are some human readable things in there, but there is clearly a custom format of data at work here. I can see some byte sequences repeating for some of the uncompressed content as if they belong to the same group of data. 

Could it be that the data is split into chuncks and perhaps across all bucket files and the headers define chunks?
## Post #32
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2011-11-21T13:04:50+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I also wanted to know that uncompressed content of bucket file chunks usually starts with Ï@ (ascii). This "string" repeats throughout content which leads me to believe this is < from <xml>. 

I am also 99% sure that there are either compressed or encoded XML files in there. I found one quest xml whose fqn is qst.location.alderaan.class.bounty_hunter.kingmaker_for_a_day but it is all garbled due to compression. I am not sure if they are usin a propriety compression method or something already known about because I am not very experienced in these things. 

BTW - If you want me to share the file I used to uncompress content of bucket files I can, but be warned - it is a PHP script
## Post #33
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-21T17:00:08+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from stalja
>
> The sad thing is that even ufter unpacking the zlib-ed content you are faced with more encoded/compressed stuff.
I have only unpacked a few files, but those that I have unpacked were regular XML files. Either I was lucky with these files or you used a wrong zlib library. Anyway, I will extract some more files and look at them.
It would be great if you could share your PHP code, I have some experience with PHP and could use it as well. So far, I have been using VB.net for all of my scripts related to TOR but they are not yet worth sharing.

> Reply from DKK
>
> I'm wondering if  Bytes 4-5 and 6-7 are some kind of version tag as my bkt files (as linked in my previous post) are all 02 00 05 00 as opposed to your 02 00 04 00
The same applies to the 32-bit integer following the first DBLB where yours read 01 00 00 00 mine read 02 00 00 00
That seems very possible. It is probably best that we first find a way to identify the version of our assets files before we continue any analysis so that we don't also face the problem of having different versions of the file formats.


I looked into the main TOR folder that contains launcher.exe and found the following XML files (these files are dated approximately August 2011):
movies_en_us.version: <Version>3</Version><Name>3</Name><InProgress>FALSE</InProgress>
retailclient_he601.version: <Version>23</Version><Name>23</Name><InProgress>FALSE</InProgress>
swtor_assets_en_us.version: <Version>6</Version><Name>6</Name><InProgress>FALSE</InProgress>
swtor_assets_main.version: <Version>6</Version><Name>6</Name><InProgress>FALSE</InProgress>
patcher.version: <Version>93</Version><Name>93</Name><InProgress>FALSE</InProgress>
It would be great if everyone who is contributing to this topic could share his version numbers of these files so that we know which versions we have.


I also found the file /resources/localcacheversioninfo.bin which in my case is 33 88 71 64 4A 12 00 00 79 97 79 03 00 00 00 00 00 00 00 00.
## Post #34
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-21T17:00:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Finally, I looked into the metadata.bin file that can be found in the folder you extracted the assets to (this is the folder that contains the resources/ folder). According to its file title, it seems to contain metadata on some files. From my analysis, it is likely that this contains the metadata for the .bnk/BKHD files in the assets_locale_en_us_X.tor files.
If you open the file in a hex editor and set the line width to 32 bytes then you can see a special pattern for each of the 96,616 lines. There is no file header.
It seems like byte number 24 stands for the number of the archive, running from 1 to 17 (in my copy, there are 17 locale archives). Also, the number of lines for each archive seems to coincide with the number of .bnk files in this archive.

> Reply from metadata.bin specification
>
> 
LOOP (for each 32-byte line) {
--- 0-7: 8 bytes, different for each line, maybe CRC checksum
--- 8-11: 4 bytes, always the same: 78 97 79 03
--- 12-15: 4 bytes, either 10 00 00 00 (folders 01-0A), C0 BD F0 FF (archives 0B, 0E, 10-11) or A0 F1 12 00 (archives 0C-0D, 0F).
--- 16-23: 8 bytes, different for each line, maybe CRC checksum
--- 24: 1 byte, standing for the asset number, running from 01 to 11 (ie. from 1 to 17)
--- 25-26: 2 bytes, either 00 00 (for 01-0A), or EC 12 (for 0B-11)
--- 27: 1 byte, always 00
--- 28: 1 byte, usually ending with a 0, like 10, 40, 50, A0, C0, except for 7C.
--- 29: different for each older, except 5B (for 0C, 0D, 0F) or EB (for 0B, 0E, 10-11)
--- 30-31: 2 bytes, either B2 41 (for 01-0A), 49 78 (for 0C, 0D, 0F) or 12 00 (for 0B, 0E, 10-11)
} END OF LOOP
And here is the raw data I used for the analysis, with the CRC bytes replaced by XX:
00 01 02 03 04 05 06 07 08 09 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31
Assets 1 to 10:
XX XX XX XX XX XX XX XX 78 97 79 03 10 00 00 00 XX XX XX XX XX XX XX XX 01 00 00 00 40 3E B2 41
XX XX XX XX XX XX XX XX 78 97 79 03 10 00 00 00 XX XX XX XX XX XX XX XX 02 00 00 00 40 48 B2 41
XX XX XX XX XX XX XX XX 78 97 79 03 10 00 00 00 XX XX XX XX XX XX XX XX 03 00 00 00 10 56 B2 41
XX XX XX XX XX XX XX XX 78 97 79 03 10 00 00 00 XX XX XX XX XX XX XX XX 04 00 00 00 80 6D B2 41
XX XX XX XX XX XX XX XX 78 97 79 03 10 00 00 00 XX XX XX XX XX XX XX XX 05 00 00 00 C0 78 B2 41
XX XX XX XX XX XX XX XX 78 97 79 03 10 00 00 00 XX XX XX XX XX XX XX XX 06 00 00 00 B0 87 B2 41
XX XX XX XX XX XX XX XX 78 97 79 03 10 00 00 00 XX XX XX XX XX XX XX XX 07 00 00 00 60 92 B2 41
XX XX XX XX XX XX XX XX 78 97 79 03 10 00 00 00 XX XX XX XX XX XX XX XX 08 00 00 00 70 BD B2 41
XX XX XX XX XX XX XX XX 78 97 79 03 10 00 00 00 XX XX XX XX XX XX XX XX 09 00 00 00 A0 C8 B2 41
XX XX XX XX XX XX XX XX 78 97 79 03 10 00 00 00 XX XX XX XX XX XX XX XX 0A 00 00 00 50 D1 B2 41

Assets 12, 13 and 15:
XX XX XX XX XX XX XX XX 78 97 79 03 A0 F1 12 00 XX XX XX XX XX XX XX XX 0C EC 12 00 7C 5B 49 78
XX XX XX XX XX XX XX XX 78 97 79 03 A0 F1 12 00 XX XX XX XX XX XX XX XX 0D EC 12 00 7C 5B 49 78
XX XX XX XX XX XX XX XX 78 97 79 03 A0 F1 12 00 XX XX XX XX XX XX XX XX 0F EC 12 00 7C 5B 49 78

Assets 11, 14, 16 and 17:
XX XX XX XX XX XX XX XX 78 97 79 03 C0 BD F0 FF XX XX XX XX XX XX XX XX 0B EC 12 00 E0 EB 12 00
XX XX XX XX XX XX XX XX 78 97 79 03 C0 BD F0 FF XX XX XX XX XX XX XX XX 0E EC 12 00 E0 EB 12 00
XX XX XX XX XX XX XX XX 78 97 79 03 C0 BD F0 FF XX XX XX XX XX XX XX XX 10 EC 12 00 E0 EB 12 00
XX XX XX XX XX XX XX XX 78 97 79 03 C0 BD F0 FF XX XX XX XX XX XX XX XX 11 EC 12 00 E0 EB 12 00
## Post #35
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-21T17:25:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have not yet seen this format but it definitely is a binary file. Are you sure that it is from The Old Republic?
It seems that pow2h is a nickname of a pro gamer of Halo 2 Vista (H2V) but I do not know if this has any relation with this file (It is far-fetched, but maybe one of the Bioware developers plays H2V).

In order for us to analyse the file, we need a bigger part of it, at least 30 times as much, or more than 1 MB. [...]

It is better to have the original file than if you copy it into the forum, because many information is lost by copying.

EDIT: Restored post in an edited form to comply with forum rules.
## Post #36
- Username: badmp3
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 21, 2011 1:48 am
- Post datetime: 2011-11-21T20:59:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Some more lines 

[http://www.filefactory.com/file/cf26a93 ... s-part.p2v](http://www.filefactory.com/file/cf26a93/n/smallassests-part.p2v)
## Post #37
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-21T22:07:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I looked at the .p2v file and the format is completely different from the current MYP archives.
Most importantly, the filelist contains not hashes but actual filenames.

I am not sure what those bytes starting at 0x2040 mean, they seem to be 4-bit flags that can either be set to 0, 8 or 9.

Starting at position 0x012000, the filelist begins. Each file is described in a block of 512 bytes.
See below for the beginning of each block:

00 00 00 00 00 00 00 00 02 01 00 00 FF FF FF FF 01 00 01 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
95 9A 01 00 02 98 01 00 04 01 00 00 FE 36 04 00 02 46 1B 00 DF 05 0F 00 00 00 00 00 08 00 00 00 80 D8 2D 07
50 2B 00 00 8A 20 00 00 06 01 00 00 1E 02 04 00 02 46 57 00 13 86 04 00 00 00 00 00 0D 00 00 00 60 1F DE 07
E8 01 00 00 0A 01 00 00 08 01 00 00 5B 01 04 00 02 46 35 00 EC 20 19 00 00 00 00 00 06 00 00 00 45 5E E5 6F
58 01 00 00 A7 00 00 00 0A 01 00 00 37 01 04 00 02 46 69 00 88 63 17 00 00 00 00 00 07 00 00 00 45 5E E5 6F
F0 55 05 00 DB 17 02 00 0C 01 00 00 FE 75 04 00 02 46 49 00 FB 70 03 00 00 00 00 00 44 00 00 00 80 D8 2D 07
68 7A 00 00 90 49 00 00 0E 01 00 00 BE 06 04 00 02 46 25 00 0A 05 12 00 00 00 00 00 07 00 00 00 80 D8 2D 07
B9 02 00 00 64 01 00 00 10 01 00 00 0F 01 04 00 02 46 35 00 60 04 1A 00 00 00 00 00 05 00 00 00 45 5E E5 6F
__ __ 0_ 00|__ __ 0- 00|XX 01 00 00|-- --|04 00 02 46|-- 00|-- __ __ 00|00 00 00 00|-- 00 00 00|-- -- -- --|

Normally, typical bytes in a filelist include file offset, file size (both compressed and uncompressed) and possibly a checksum.
The file you uploaded is too small for us to be able to fully analyse the format. However, the red bytes do stand out because they are increasing. They could either be the file offset or just the ID of the file.
The filenames are similar to the ones in the current archives and all file formats are still in use, like /bnk/streamed/430210007.ogg or /art/static/area/all_all/arch/slum/texture/all_arch_slum_med_hut_int_r1_wall_s.tiny.dds.

@badmp3: I doubt there is any possibility for you to upload the whole 7GB file, right? Instead, what you can do is this: you can quickly scroll through the file and look for the position where the filename format ends and the contents of the files start. It should be pretty easy to recognize, at that point all those dots on the right side will be replaced by some strange letters and symbols.
If you have found this position, please upload a file with maybe 50 lines before and after this position. And please don't use FileFactory for uploading again, it took me at least five tried until I was able to download the file. A good list of uploading sites can be found in [this topic](http://forum.xentax.com/viewtopic.php?f=28&t=3792).
If I have time for it, I may write a program that goes through the file and outputs all filenames. This could be useful for figuring out the remaining filenames belonging to the hashes. Otherwise, there is not much we can do with an incomplete specification, sorry.
## Post #38
- Username: badmp3
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 21, 2011 1:48 am
- Post datetime: 2011-11-22T01:09:52+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

The contents of this post was deleted because of possible forum rules violation.
## Post #39
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-22T19:38:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have to correct myself, I have not yet found any plain xml files in the bucket files. (I confused it with the zlib files from the MYP archives)
Anyways, the files in the bucket archives really are compiled/binary versions of the raw xml files. They seem to be somewhat similar to the PROT/.node files I already analysed (they are just missing a header), so I should be able to post a specification soon.

Here are just some information already in advance:
I recommend looking at the integer format specification for variable-sized integers (see page 1 of this topic). The compiled files make frequent use of them.
Most files start with some zero bytes (00 00 00 00) but I found at least one compiled MPN file that starts with 86 BE BC 67 C1 DF 00 E0.

The general format of these files is like this:
0-...: varying number of zero bytes (0 to at least 7 bytes)
One variable-sized integer, eg. 15, 2F or C9 01 59 (15 = mapnote, 59 = item)
Another variable-sized integer, eg. 06, 05 or C9 00 14
LOOP (for all nodes) {
--- ID of the current node as variable-sized integer (most files, including PROT) or as 4-byte integer (compiled MPN files)
--- Node type, one byte.
--- More data, different for each node type
} END LOOP

Eg., one node type is the string type and is identified by the byte 06 (most files, including PROT) or 85 (compiled MPN files).
Example analysis for one string node:
CF 40 00 00 02 F5 E6 DC 5A (Ï@...õæÜZ) → node id, in this case: 4611686031142870000
06 (.) → node type #6 = string
25 (%) → length of string (37 bytes)
65 70 70 2E 73 74 61 74 65 2E 73 77 69 74 63 68 5F 77 65 61 70 6F 6E 5F 73 74 61 6E 63 65 2E 70 69 73 74 6F 6C
→ the actual string, in this case epp.state.switch_weapon_stance.pistol

There are very many node types and I have figured out the number of bytes for most of them, but unfortunately there are still many unknowns. However, we may be able to figure out more things by comparing these files to their respective XML equivalents.
## Post #40
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2011-11-24T08:01:29+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I guess I could build something that will connect the node names with the node names I have from uncompressed files from before. I don;t have much time at the moment though. I'll try and get some work done and share the results as soon as possible. So you think it is just a byte code = node type of compression here? There is probably a position byte in there somewhere (position of data).
## Post #41
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-24T13:16:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from stalja
>
> I guess I could build something that will connect the node names with the node names I have from uncompressed files from before. I don;t have much time at the moment though. I'll try and get some work done and share the results as soon as possible. So you think it is just a byte code = node type of compression here? There is probably a position byte in there somewhere (position of data).
I fear you understood me wrong, the compiled files are not 1:1 translations of the xml files. They seem to contain the same information, but in a completely different order, so unfortunately it is not that easy to write a translator. 

For those who do not yet have the newest beta version, here is an updated list of all TOR files. As XHD already wrote, the assets are now grouped by their contents, so this could help us with the file names.

And scratch what I said earlier about the version files; the newest version files are password-protected ZIP files and cannot be read so easily. However, there are two version files in the Assets folder that seem to contain the version number (Assets/assets_swtor_main_version.txt and Assets/assets_swtor_XX_XX_version.txt).

Main assets:

```
swtor_main_anim_creature_b_1.tor
swtor_main_anim_creature_npc_1.tor
swtor_main_anim_humanoid_bfab_1.tor
swtor_main_anim_humanoid_bfns_1.tor
swtor_main_anim_humanoid_bmaf_1.tor
swtor_main_anim_humanoid_bmns_1.tor
swtor_main_anim_misc_1.tor
swtor_main_areadat_1.tor
swtor_main_areadat_epsilon_1.tor
swtor_main_area_alderaan_1.tor
swtor_main_area_balmorra_1.tor
swtor_main_area_belsavis_1.tor
swtor_main_area_corellia_1.tor
swtor_main_area_coruscant_1.tor
swtor_main_area_dromund_kaas_1.tor
swtor_main_area_epsilon_1.tor
swtor_main_area_hoth_1.tor
swtor_main_area_hutta_1.tor
swtor_main_area_ilum_1.tor
swtor_main_area_korriban_1.tor
swtor_main_area_misc_1.tor
swtor_main_area_nar_shaddaa_1.tor
swtor_main_area_open_worlds_1.tor
swtor_main_area_ord_mantell_1.tor
swtor_main_area_quesh_1.tor
swtor_main_area_raid_1.tor
swtor_main_area_taris_1.tor
swtor_main_area_tatooine_1.tor
swtor_main_area_tython_1.tor
swtor_main_area_voss_1.tor
swtor_main_area_zed_1.tor
swtor_main_art_area_all_arch_a_1.tor
swtor_main_art_area_all_arch_b_1.tor
swtor_main_art_area_all_item_1.tor
swtor_main_art_creature_a_1.tor
swtor_main_art_creature_b_1.tor
swtor_main_art_creature_npc_1.tor
swtor_main_art_dynamic_cape_1.tor
swtor_main_art_dynamic_chest_1.tor
swtor_main_art_dynamic_chest_tight_1.tor
swtor_main_art_dynamic_hand_1.tor
swtor_main_art_dynamic_head_1.tor
swtor_main_art_dynamic_lower_1.tor
swtor_main_art_dynamic_mags_1.tor
swtor_main_art_fx_1.tor
swtor_main_art_harvesting_1.tor
swtor_main_art_misc_1.tor
swtor_main_art_space_combat_1.tor
swtor_main_art_vehicle_1.tor
swtor_main_art_weapon_1.tor
swtor_main_art_zed_1.tor
swtor_main_bnk_audiodata_1.tor
swtor_main_bnk_audio_1.tor
swtor_main_bnk_location_1.tor
swtor_main_bnk_streamed_a_1.tor
swtor_main_bnk_streamed_b_1.tor
swtor_main_bnk_streamed_c_1.tor
swtor_main_bnk_voc_1.tor
swtor_main_cnv_alien_1.tor
swtor_main_gamedata_1.tor
swtor_main_gfx_1.tor
swtor_main_global_1.tor
swtor_main_systemgenerated_gom_1.tor
swtor_main_zed_1.tor

```

Localised files:

```
swtor_XX-XX_area_balmorra_1.tor
swtor_XX-XX_area_belsavis_1.tor
swtor_XX-XX_area_corellia_1.tor
swtor_XX-XX_area_coruscant_1.tor
swtor_XX-XX_area_dromund_kaas_1.tor
swtor_XX-XX_area_hoth_1.tor
swtor_XX-XX_area_hutta_1.tor
swtor_XX-XX_area_ilum_1.tor
swtor_XX-XX_area_korriban_1.tor
swtor_XX-XX_area_misc_1.tor
swtor_XX-XX_area_nar_shaddaa_1.tor
swtor_XX-XX_area_open_worlds_1.tor
swtor_XX-XX_area_ord_mantell_1.tor
swtor_XX-XX_area_quesh_1.tor
swtor_XX-XX_area_raid_1.tor
swtor_XX-XX_area_taris_1.tor
swtor_XX-XX_area_tatooine_1.tor
swtor_XX-XX_area_tython_1.tor
swtor_XX-XX_area_voss_1.tor
swtor_XX-XX_cnv_comp_chars_imp_1.tor
swtor_XX-XX_cnv_comp_chars_rep_1.tor
swtor_XX-XX_cnv_misc_1.tor
swtor_XX-XX_cnv_transitions_1.tor
swtor_XX-XX_global_1.tor

```
## Post #42
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-25T16:02:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

@badmp3: I have now put together some tools for analysing p2v archives. You can download them at [http://www.sendspace.com/file/ykt0va](http://www.sendspace.com/file/ykt0va). In it, you will find five files.

P2V-Extractor.exe is a tool I wrote to extract the filenames from the p2v archives. Just run it, select the p2v file to open and a file to save the filelist to. Should be pretty easy to use. In case anyone is interested, I also included the source code in Form1.vb (written in VB.net).
p2v-filenames-sorted.txt contains the filenames from the p2v file you have uploaded and will hopefully help us with guessing more file names. Thank you again very much for providing the p2v file, it is always great to see exclusive beta files! 
It is also possible to extract the contents of the p2v files with the tool offzip.exe. Offzip is an extractor written by aluigi (not by me ) that extracts any zlib-encoded files in an archive. Just copy offzip.exe and extract.bat into the folder where you have the smallassets.p2v file stored and double-click on extract.bat. The program will then extract all files from the archive into a subfolder called "extracted". However, make sure that you have at least 20GB of disk space free before you run the program, because these files will be very large!

It is not a perferct solution (eg. the filenames are wrong), but for now you can extract filenames and files from p2v archives.
At the moment it is more important to analyse the newer files but I may come back to the p2v archives later.
## Post #43
- Username: hazballs
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 03, 2011 9:05 pm
- Post datetime: 2011-12-03T13:29:13+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi all! I've been watching this thread closely since finding it, as somebody who is very excited about SWTOR and would love to see some of the level 50 content unearthed, such as boss models, high end mission text, etc.

I am a total novice with reverse-engineering games, although I would like to learn and help out. I have a few questions about the TOR files which have been analysed so I can better understand the process that is going on.

Firstly, is the 50% complete hash list tied to a specific version of the beta client? i.e. does a new hash list need to be produced every time the game files are altered?

Secondly, as the game uses zlib compression, do the extracted files need to be "decompressed", or does easymyp do that in the process of extracting them?

Thirdly, are the DEADBEEF files useful in any way? For example, can a DEADBEEF text file simply be renamed to the correct extension provided the file header gives away what kind of file it is? i.e. is renaming "DEADBEEF_FE26FD386BBA06DA.txt" to "somename.gr2" the equivalent to easymyp extracting it with the name "somename.gr2" based on the hash list?

Sorry to ask n00bish questions as many of you are well versed in this stuff already!
## Post #44
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-03T14:15:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Glad of you to join in! 

> Reply from hazballs
>
> Firstly, is the 50% complete hash list tied to a specific version of the beta client?
Actually, until now I have only been working with older beta files so I could not test the 50% hash list yet.
It could be possible that the hash list no longer works because Bioware
a) changed all the file names, eg. by renaming the top directory /resources/ to a different name. In this case, no wonder that the file list no longer works.
b) changed the hash generation, so that the same filenames now have different paths.
Any case is bad news for us. Under a), we would need to find out the new filenames, under b), we would have the disassemble swtor.exe and would need to fix the Easymyp algorithm.
By the way, the hash list does not store any version information nor the filenames of the TOR archives, so there shouldn't be any problem with that.

> Reply from hazballs
>
> Secondly, as the game uses zlib compression, do the extracted files need to be "decompressed", or does easymyp do that in the process of extracting them?
Easymyp already decompresses all files during extraction, so you do not need to worry about that. However, there are some proprietary files, like the bucket or BKHD files, that are encoded twice, so we need to decompress/extract them once more before we can use them.

> Reply from hazballs
>
> Thirdly, are the DEADBEEF files useful in any way?
The DEADBEEF files are really just normal files, they just have a different filename. So you can open them in a hex editor, look for the file header, rename the file extension and open it in the correct program.
The only disadvantage with the DEADBEEF files is that for files like the textures they are not of much use: if you have a directory of multiple thousand DEADBEEF files and don't know what filename they have, good luck finding the right file .
But XML files work fine even if you do not know their filename as the FQN name is always specified in the first tag.

> Reply from hazballs
>
> Fourth, does a new hash list need to be made every time the game files change?
Similar to question one, the hash list should work with all versions so we do not need to update the format everytime, unless Bioware changes the algorithm again.
However, there will always be the case that old files are deleted, new ones added and other files renamed or modified. However, the majority of the files should stay the same so we only need to update a few file names everytime there is an update.

> Reply from hazballs
>
> Finally, how is everyone else's research coming along on the "close to release" version of the game files?
Well, right now I am still working on recognizing all file formats and hope that I will fix the filename issue soon.
In my opinion, we rather need a TOR viewer instead of an extractor like easyMYP, because the extracted files can be up to 60 GB in file size. It would be better to have a program similar to the Windows Explorer that can be used to look into the archives, preview the files and extract them on a "on demand" basis.
The only problem then is how we can keep track of file changes during patches.
## Post #45
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2011-12-03T14:28:54+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

The hash algorithm has not changed to the best of my knowledge. I just extracted all the item icons using the hash algorithm and it worked right. 

What you need to know and what is clearly stated in easymyp documentation. The files you get from extraction are named like this

CRC_Hash1Hash2.guessed_extension

so - DEADBEEF is in fact the CRC of the file that easymyp author wanted to use for versioning purposes. What is important for matching filenames to hashes is the second part of the filename and that is Hash1Hash2 thing.

So, I can confirm that, at least for the icons, the hashing algorithm still works. 

They have changed the filenames. They have added a lot more of them as well. They removed some. If I was to guess I would say that the old client and the new client intersect in about 60% of filenames, maybe more.
## Post #46
- Username: hazballs
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 03, 2011 9:05 pm
- Post datetime: 2011-12-03T14:48:30+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks for the replies!

I edited my original message after posting it, SWTOR fan, but it seems you were already in the process of replying - it seems the 50% hash list DOES work on the current beta files. Whether or not all the files in the hash list are still accurate I don't know, but I managed to get a good few .gr2 files (which is the main thing I'm currently looking for, as I'd like to see some of the end game boss models).

However, as you have probably noticed in your own findings, in the "release" version of the client (Bioware has stated that people in the big weekend beta won't have to re-download the client for the live game) the gr2 files now have the GAWB "magic number" instead of )ÞlÀ and cannot be converted to .ms/.smd files using the GrannyReader'98 tool posted in the other thread.

But yes, as you say, a general viewer would be ideal, similar to the general file/model viewers released for other games.
## Post #47
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-03T16:50:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

ACB file specification (WEM file archive)
I found a new file type in the newest version of the beta files that is only contained in the localized archives. It has the file extension "*.acb", like "/resources/en-us/bnk2/cnv_location_alderaan_bronze_imperial_adjusting_history_caliman_thul.acb".
These archives seem to be an updated version of the BKHD/.bnk archives and do not have a file header. According to the strings in these archives, the audio files contained in them have the file extension .wem, but they actually are just normal WAVE files (with Wwise encoding, of course).

Metadata in .tor archives:
The WEM file archives do not have a file header but contain a 36-byte long metadata in the TOR archives:
two bytes (always 02 00): maybe version number / ID
two bytes (always 20 00): length of following metadata → 32 bytes
unknown 32 bytes, different for each file, maybe some CRC checksum or version information

WEM archive file format:
64-bit integer (8 bytes): number of file entries (eg. 06 00 00 00 00 00 00 00 → 6 files)
LOOP (for each filename) {
--- variable-length string (= filename), terminated by 00
--- 64-bit integer (8 bytes): file length (eg. 9D D7 00 00 00 00 00 00)
--- 64-bit integer (8 bytes): file offset (eg. 78 3E 00 00 00 00 00 00)
} END LOOP
LOOP (for each file) {
--- data[]: Wwise encoded .ogg file, with length and offset as given above (header: RIFF....WAVEfmt)
} END LOOP

Example filenames: (from swtor_XX-XX_area_corellia_1.tor)
cnv_location_corellia_ambient_hub1_green1_imperial_1_m.wem
cnv_location_corellia_ambient_cc_poi_barks_226_m.wem
cnv_location_corellia_ambient_cc_poi_barks_1149_m.wem

Edit: Just to clarify, BKHD/.bnk archives are still used inside swtor_main_bnk_[...].tor, but the difference to the WEM archives is that WEM archives contain multiple files with different filenames for each of them, while BKHD archives only contain one filename with different audio files inside. And the BKHD also contain some additional sections on top of the audio files.

Edit 2: Here's a BMS script for extracting these kinds of archives:

```
for i = 0 < numberOfFiles
get fileName string
get fileSize longlong
get fileOffset longlong
log fileName fileOffset fileSize
next i
```

Edit 3: Thanks to Rick, I found out that these file archives have the extension "*.acb"!
## Post #48
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-03T19:24:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I looked into the release notes for Wwise and found out that Wwise has changed the file extension of the audio files, that's why they are now called .wem:

> 2.1 All Streamed and Converted Files Have a New File Extension (WEM)
>
> All streamed and converted files now have the .wem file extension (Wwise Encoded Media). Wwise does not generate anymore files with the ogg, xma or wav extensions. All streamed or converted files now have the .wem extension, whatever their encoding format is. The External Source files are also all converted to .wem files.
>
> You may have to modify your tools or installers to manipulate wem files instead of ogg, xma or wav files.
(source: [http://www.audiokinetic.com/download/do ... eNotes.pdf](http://www.audiokinetic.com/download/documents/Wwise_v2011.2_ReleaseNotes.pdf))

In any case, the audio files no longer work with the current version of the ww2ogg tool. For more information, see [this topic](http://forum.xentax.com/viewtopic.php?f=17&t=7792).

Edit: hcs has now updated ww2ogg and it is working again!
## Post #49
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-05T19:03:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Unknown string list file specification
There's another new file format contained in localized assets like swtor_de-de_global_1.tor, with the hashes 51378F9D_96EEED14D7CD0574.txt or CB7EAB01_96EEED14D7CD0574.txt, depending on the version of the beta files.
This file contains a list of strings for the abilities.
Thank you very much to Nomis who first discovered and analysed this file!

Each ability is described by four strings:
1. Name of the ability (eg. Bereich verlassen)
2. Repetition of the name (eg. Bereich verlassen)
3. Description of the ability (eg. Teleportiert dich aus dem aktuellen Flashpoint heraus.)
4. Repetition of the ability (eg. Teleportiert dich aus dem aktuellen Flashpoint heraus.)
Some strings have zero length and can therefore only be found in the metadata and not in the main body.

File format:
01 00 00 → header, maybe version number?
4 bytes: 32-bit integer, number of strings
LOOP (metadata foreach string) {
--- 4 bytes: 32-bit integer (0 = name of an ability, 1 = description of an ability)
--- unknown 4 bytes, maybe ID
--- unknown two bytes (41 01 if it is the first string, 46 01 if it is the repetition)
--- unknown 4 bytes, maybe ID
--- 4 bytes: string length
--- 4 bytes: string offset (absolute file position)
--- 4 bytes: string length
} END LOOP
LOOP (raw text foreach string) {
--- List of strings with the aforementioned offset and length
} END LOOP

As an example, here is the metadata for one ability, consisting of four strings:
00 00 00 00 C2 39 02 00 41 01 A3 01 40 40 11 00 00 00 53 99 0E 00 11 00 00 00 Bereich verlassen
00 00 00 00 C2 39 02 00 46 01 A3 01 40 40 11 00 00 00 64 99 0E 00 11 00 00 00 Bereich verlassen
01 00 00 00 C2 39 02 00 41 01 A3 01 00 40 36 00 00 00 75 99 0E 00 36 00 00 00 Teleportiert dich aus dem aktuellen Flashpoint heraus.
01 00 00 00 C2 39 02 00 46 01 A3 01 00 40 36 00 00 00 AB 99 0E 00 36 00 00 00 Teleportiert dich aus dem aktuellen Flashpoint heraus.
## Post #50
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2011-12-07T17:27:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

About the unknown string list file specification.

metadata for each string section
the first 4 bytes are the string id
next 4 bytes are the id of the xml they belong to (to put it plainly)

In your example of abilities - the first 4 bytes present id of first and second string in the XML that describes abilities. The second 4 bytes describe exactly that abilities xml that contains those strings.

the next 2 bytes are what you said - describing whether it is a repetition or not. 
last 4 unknown bytes are a mystery to me. They are not unique so I guess they are some sort of flag that describe how to build the unique id of the string.
## Post #51
- Username: Duhaccgzhn
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 08, 2011 1:17 pm
- Post datetime: 2011-12-08T05:43:10+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from stalja
>
> And scratch what I said earlier about the version files; the newest version files are password-protected ZIP files and cannot be read so easily.

I am new at this forum, but i have an idea on how to extract that zip files.
I have found that all .version, .bundle, .patchmanifest, .solidpkg and itself launcher.exe (except that this file is an exe) are actually same-type ecrypted zip-files with start as emty dll-file with certificate. 
Laucher starts as a webserver emulator, which binds on unique port at localhost each time is launched. Then exe creates instance of webkit browser. But it is not important at this time. After find opened port i`ve searched for, i`ll navitage to [http://127.0.0.1:8175/app/swtor.html](http://127.0.0.1:8175/app/swtor.html) (for example) in my browser.
.version files actually an hash-file on .tor files which launcher uses for patching and checking for errors.
I have started at disassemble laucher and see wheres password is located. But i am new at reverse-engineering, so i am dont have found it yet.
I am ask people who actualy good at reverse-engineering for finding info about password. So we can move forward.
## Post #52
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2011-12-08T10:19:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I don't see a reason why you would want to unpack those files. That was implemented to prevent people from downloading the client if they do not have access to beta. Now that the client is readily available for download for everyone I see no reason to get into those files at all. If you want to reverse engineer the executable rather do it to find the piece of code that unpacks bucket files...
## Post #53
- Username: Duhaccgzhn
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 08, 2011 1:17 pm
- Post datetime: 2011-12-09T03:48:11+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I know this. But i dont have broadband internet. I am doing my research to ensure that prevent laucher from downloading  those big over 5 gb files again.. Sometimes launcher did not success patching game files and after rechecking goes to redownload. Well i am do not agree with their approach for patching. I want to myself patch those files. Well human are more smart than any limited algorithm programs and can expect all incorrect actions.
## Post #54
- Username: Darjk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 08, 2011 3:02 pm
- Post datetime: 2011-12-10T15:31:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I've been keeping a close eye on this thread as its saving me a lot of the ground work which I'm extremely appreciative of.
I'm currently in the process of writing an app to open and view Tor files on the fly specifically for SWTOR to assist in figuring out all the file formats, etc (very similar to my Shadowbane Cache viewer that I wrote).  Then eventually down the track, I will be converting.. or adding the 'Model Viewer' part of the program to go along with my original WoW Model Viewer.

Once I have the base work done of opening, viewing, saving, and editing the files as well as a preview of each file, I'll release it for general use.  Hopefully won't take too long but hard to determine as I work a lot of hours.

Thanks to all of you who have contributed!
## Post #55
- Username: mvanderw
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 31, 2011 10:44 pm
- Post datetime: 2011-12-12T01:36:16+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Indeed. As part of my effort to grok the files contained in the buckets I've made a quick bucket explorer, available at [http://holocron.so/buckets](http://holocron.so/buckets).

It seems to me the buckets are fairly interesting as they seem to contain most (all?) of the game's items and abilities as well as lots of other curious bits (templates, area info, etc). Anyone gotten further in decoding those files?
## Post #56
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2011-12-12T08:02:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from mvanderw
>
> Indeed. As part of my effort to grok the files contained in the buckets I've made a quick bucket explorer, available at http://holocron.so/buckets.

It seems to me the buckets are fairly interesting as they seem to contain most (all?) of the game's items and abilities as well as lots of other curious bits (templates, area info, etc). Anyone gotten further in decoding those files?

Looking at the number of databases out there I'm fairly certain they have
## Post #57
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-12-12T19:08:22+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

If it has not been noted before, name hash algorithm is [jenkins lookup3](http://www.burtleburtle.net/bob/c/lookup3.c) (see hashlittle/hashlittle2).
## Post #58
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-13T18:12:51+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Bucket file format
As I wrote earlier, I already have analysed files which are similar to the files in the bucket files, so I will just post what I have. I hope the format did not change too much since I analysed them. 

Thank you very much for your bucket explorer, mvanderw! It is helping me a lot with the analysis. I hope you can improve the coloring with my information and we can improve the analysis of these files.

> Reply from SWTOR fan
>
> I recommend looking at the integer format specification for variable-sized integers (see page 1 of this topic). The compiled files make frequent use of them.

The general format of these files is like this:
0-...: varying number of header bytes (0 to at least 7 bytes)
One variable-sized integer, eg. 15, 2F or C9 01 59 (15 = mapnote, 59 = item) ??
Another variable-sized integer, eg. 06, 05 or C9 00 14
LOOP (for all nodes) {
--- ID of the current node as variable-sized integer (most files, including PROT) or as 4-byte integer (compiled MPN files)
--- Node type, one or two bytes.
--- More data, different for each node type
} END LOOP

Eg., one node type is the string type and is identified by the byte 06 (most files, including PROT) or 85 (compiled MPN files).
Example analysis for one string node:
CF 40 00 00 02 F5 E6 DC 5A (Ï@...õæÜZ) → node id, in this case: 4611686031142870000
06 (.) → node type #6 = string
25 (%) → length of string (37 bytes)
65 70 70 2E 73 74 61 74 65 2E 73 77 69 74 63 68 5F 77 65 61 70 6F 6E 5F 73 74 61 6E 63 65 2E 70 69 73 74 6F 6C
→ the actual string, in this case epp.state.switch_weapon_stance.pistol

In the following, you can find a list of the different node types. Some nodes reference other node ids, other nodes contain one string or a list of string, and even other nodes contain some kind of flags (e.g. 01=05, 02=DE, 03=AB, 04=01, ...). And of course there are many more node types where I do not know what they stand for.
But at least with this information one can write a better format analyser.
Once we have that done, we can try to make some sense of the data. It seems that the node id has something to do with what the node stands for. For example, in dialogue files, the node id classifies a node to say which audio should be spoken, what the parent node is, which animations/cameras to play etc.


01 (reference to a different node id)
Variable-length integer: Node id
One byte: 01
Variable-length integer: Another node id

02 (reference to a different node id)
Variable-length integer: Node id
One byte: 02
Variable-length integer: Another node id

In dialogue files, if the first node id is 0x2C, then the second id stands for the string id that is to be spoken.

03 (short node, end of section?)
Variable-length integer: Node id
One byte: 03
One byte: 01

04 02 (short node)
Variable-length integer: Node id
One byte: 04
One byte: 02

04 03 (short node)
Variable-length integer: Node id
One byte: 04
One byte: 03

04 02 02 (unknown)
Variable-length integer: Node id
Three bytes: 04 02 02
Four bytes: unknown
Three bytes: unknown

05 (short node)
Variable-length integer: Node id
One byte: 05
Two unknown bytes

06 (single string)
Variable-length integer: Node id
One byte: 06
Variable-length integer: Length of string
String with the aforementioned length

07 01 (multiple flags)
Variable-length integer: Node id
Two bytes: 07 01
Variable-length integer: Number of flags
Variable-length integer: Number of flags, same as above
LOOP {
--- Variable-length integer: Flag id
--- Variable-length integer: Flag value
} END LOOP

07 03 (short node)
Variable-length integer: Node id
Two bytes: 07 03

07 05 (multiple flags)
Variable-length integer: Node id
Two bytes: 07 05
Variable-length integer: Number of flags
Variable-length integer: Number of flags, same as above
LOOP {
--- Variable-length integer: Flag id
--- Variable-length integer: Flag value
} END LOOP

07 06 (multiple strings)
Variable-length integer: Node id
Two bytes: 07 06
Variable-length integer: Number of strings
Variable-length integer: Number of strings, same as above
LOOP {
--- Variable-length integer: String id
--- Variable-length integer: String length
--- String with aforementioned length
} END LOOP

07 09 (unknown)
Variable-length integer: Node id
Two bytes: 07 05
Two or five unknown bytes

08 01 09 (unknown length)
Variable-length integer: Node id
Three bytes: 08 01 09
Variable-length integer: Unknown length
Variable-length integer: Same as above

08 02 02 (multiple flags)
Variable-length integer: Node id
Three bytes: 08 02 02
Variable-length integer: Number of flags
Variable-length integer: Number of flags, same as above
LOOP {
--- Variable-length integer: Flag id
--- Variable-length integer: Flag value
} END LOOP

08 02 06 (multiple strings)
Variable-length integer: Node id
Three bytes: 08 02 06
Variable-length integer: Number of strings
Variable-length integer: Number of strings, same as above
LOOP {
--- Variable-length integer: String id
--- Variable-length integer: String length
--- String with aforementioned length
} END LOOP

08 02 07 (beginning of multiple string nodes)
Variable-length integer: Node id
Three bytes: 08 02 07
Variable-length integer: Number of string nodes following this node
Variable-length integer: Same as above

08 02 08 (beginning of multiple string nodes)
Variable-length integer: Node id
Three bytes: 08 02 08
Variable-length integer: Number of string nodes following this node
Variable-length integer: Same as above

08 02 09 (unknown length)
Variable-length integer: Node id
Three bytes: 08 02 09
Variable-length integer: Unknown length
Variable-length integer: Unknown length, same as above

08 05 08 (multiple string sections)
Variable-length integer: Node id
Three bytes: 08 05 08
Variable-length integer: Number of string sections
Variable-length integer: Number of string sections, same as above
LOOP (for each section) {
--- Variable-length integer: Section number
--- Two bytes: XX XX
--- Variable-length integer: Number of strings per section
--- Variable-length integer: Number of strings per section, same as above
--- LOOP (for each string in this section) {
--- --- Variable-length integer: String id
--- --- Variable-length integer: String length
--- --- String with aforementioned length, sometimes length = 0
--- } END LOOP
} END LOOP

08 05 (short node)
Variable-length integer: Node id
Two bytes: 08 05

08 06 03 (multiple strings)
Variable-length integer: Node id
Three bytes: 08 06 03
Variable-length integer: Number of strings
Variable-length integer: Number of strings, same as above
LOOP (for each string) {
--- Variable-length integer: String id
--- Variable-length integer: String length
--- String with aforementioned length, sometimes length = 0
--- Sometimes: one zero byte (00)
} END LOOP

08 06 08 (multiple strings)
Variable-length integer: Node id
Three bytes: 08 06 08
Variable-length integer: Number of strings
Variable-length integer: Number of strings, same as above
LOOP (for each string) {
--- Variable-length integer: String id
--- Variable-length integer: String length
--- String with aforementioned length, sometimes length = 0
} END LOOP
Four bytes: 06 03 01 01
Variable-length integer: String id
Variable-length integer: String length
String with aforementioned length, sometimes length = 0
One byte: 01

09, 39 or 3B (beginning of a section)
Variable-length integer: section number
One byte: 09, 39 or 3B (on dialogue files: 39=audio string, 09=metadata, 3B=unknown)
One unknown byte (on dialogue files: 05=metadata, 15=NPC speaking, 16=PC speaking, 16/17=unknown)

-----------------------------------------

Following 08 02 07 or 08 02 08 are not regular string sections; instead, they have the following format:

Following 08 02 07:
Variable-length integer: Node id
One byte: 06
Variable-length integer: Number of strings
Variable-length integer: Number of strings, same as above
LOOP (for each string) {
--- Variable-length integer: String id
--- Variable-length integer: String length
--- String with aforementioned length, sometimes length = 0
} END LOOP

Following 08 02 08:
Variable-length integer: Node id
One byte: 06
One byte: 07
Variable-length integer: Number of strings
Variable-length integer: Number of strings, same as above
LOOP (for each string) {
--- Variable-length integer: String id
--- Variable-length integer: String length
--- String with aforementioned length, sometimes length = 0
--- One unknown byte: 02 (maybe flag mode??)
--- Variable-length integer: Number of flags
--- Variable-length integer: Number of flags, same as above
--- LOOP (for each flag) {
--- --- Flag number
--- --- Flag value
--- } END LOOP
} END LOOP
## Post #59
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-12-13T20:50:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Is anyone building a file list for the retailclient besides myself? (sitting at 35% complete)
## Post #60
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-13T21:08:34+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Rick
>
> Is anyone building a file list for the retailclient besides myself? (sitting at 35% complete)
Yes, I am also currently working on a tool to do just that, but right now I am working with the final beta version. I hope to finish the tool soon so that I can compare the beta files with the retail files.
## Post #61
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-13T21:28:43+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

By the way, have you already tried to replace the file extension of the known audio files (".wav") with ".wem"? This may give you some new file names.

Also, you could try loading the file names from [http://www.sendspace.com/file/ykt0va](http://www.sendspace.com/file/ykt0va) into your program and see if there are new ones among them. I created this list based on a very old beta archive that still contained the file names (see page 2/3 for more information), so there may be some new file names if they are still valid.
## Post #62
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-12-14T19:13:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> By the way, have you already tried to replace the file extension of the known audio files (".wav") with ".wem"? This may give you some new file names.

Also, you could try loading the file names from http://www.sendspace.com/file/ykt0va into your program and see if there are new ones among them. I created this list based on a very old beta archive that still contained the file names (see page 2/3 for more information), so there may be some new file names if they are still valid.Pretty sure I imported that list at some point.

Now at 135041/364793 (37%).

edit: removed old file
## Post #63
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2011-12-14T19:47:29+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I can compile a list of item icon filenames if you are interested.
## Post #64
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-12-14T21:01:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Sure. How are you doing that? I haven't look at any of the data files yet myself so I've been operating purely off of what the game accesses.
## Post #65
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-12-16T04:45:04+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Looks like that p2v format mentioned earlier is still in active use, just not for the normal data archives. The game creates and uses a file called swtor\DiskCacheArena which has that format.
## Post #66
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-12-16T22:33:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Now at 176052/364793 (48%).

edit: removed old file
## Post #67
- Username: tolocago
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 17, 2011 7:10 am
- Post datetime: 2011-12-17T01:05:27+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi all!

Someone know how to edit .stb files?

Reading at them I can see that:
"gameoptions.stb"

```
01 00 00 05
```

05 for the five terms in it: Options Cancel Game_Exit Logout Preferences

```
00 00 00 01 
```

Introduce the first String "Options"

```
00 00 00 86 8a 03 00 41 01 00 00 80 3f 07 00 00 00 89 00 00 00 07
```

"00 00 00 86 8a 03 00 41 01 00 00 80 3f " its like a general text for all strings, repeat always. 
"07 00 00 00 89 00 00 00 07" and 07 its like the 7 letters of "Options" (Cancel and Logout have both a 06 for example).
The 89 of "07 00 00 00 89 00 00 00 07" I dont know what its talking about.

¿And maybe someone know hot to make the game reading a .stb modified file?

Thanks all.
## Post #68
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-17T12:21:08+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Finally I got my own MYP reader working and can start analysing the files.

Thank you very much for finding out the file names, Rick!  They're helping a lot with the analysis.
Because of them, I now know that the "WEM file archives" have the file extension "*.acb". I'll update my specification accordingly.

> Reply from tolocago
>
> Hi all!
Someone know how to edit .stb files?Those "*.stb" files seem to be the "Unknown string list files" I wrote about earlier, but the format has changed slightly. I will post an updated specification soon.

Also, here are some XML files from an earlier beta version. I hope they will help in analysing the bucket files. I have not yet found out which XML files were removed and which are still in there so I will post some more XML files when I know more.
Also, I put in the archive most of the FQNs (see [http://wiki.heroengine.com/wiki/FQN](http://wiki.heroengine.com/wiki/FQN) for more information). Since the FQNs relate to the file names in some way (like cnv.alien_vo.evocii.m_low → /resources/en-us/bnk2/cnv_alien_vo_evocii_m_low.acb), this hopefully will get us some more file names.
Download here: EDIT: Link removed.

EDIT: Post restored with download link removed to comply with new forum rules.
## Post #69
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-12-17T14:02:47+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> I hope they will help in analysing the bucket filesIt turns out there is actually a tool called NodeViewer which can view those files: [http://sithwarrior.com/forums/Thread-Ri ... 81#pid5081](http://sithwarrior.com/forums/Thread-Ripping-client-data?pid=5081#pid5081). I'm very curious where that tool came from.
## Post #70
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-17T17:35:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks for sharing that link, Rick! It seems like they have been working on the beta files since August, no wonder they are this far.
That NodeViewer will help us a lot in figuring out the format of the bucket files, and maybe we can use the Hero.dll for a TOR viewer.
## Post #71
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2011-12-17T18:21:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

has anyone else gotten that nodeviewer to work? just crashes for me
## Post #72
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-17T18:44:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from nicoli_s
>
> has anyone else gotten that nodeviewer to work? just crashes for me
Yes, you can fix the program by opening the file NodeViewer.exe.config in Notepad or a Hex editor.

In the file, you will find the line:

```
<add key="AssetsPath" value="C:\Program Files\Electronic Arts\Star Wars\Assets" />
```

Now you have to update the path to point to the folder where you installed SWTOR. If you used the default folder, you can use this line:

```
<add key="AssetsPath" value="C:\Program Files\Electronic Arts\BioWare\Star Wars-The Old Republic\Assets" />
```

Once you save the file you can start NodeViewer.exe and the program will search for the nodes and prototypes contained in the asset files.

Please tell us if you need any additional help.
## Post #73
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2011-12-17T20:59:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

edit:scratch that, was trying to load an old build, i have like 7 copies of swtor installed
## Post #74
- Username: ibbyes
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 18, 2011 5:07 am
- Post datetime: 2011-12-19T11:28:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

NodeViewer.exe and Hero.dll decompiled source code attached for those interested in how exactly it works but don't have the tools to do the decompilation themselves.
[Disassembler.rar](https://xentaxbackup.github.io/file/4915_Disassembler.rar)
## Post #75
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-19T16:58:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ibbyes
>
> NodeViewer.exe and Hero.dll decompiled source code attached for those interested in how exactly it works but don't have the tools to do the decompilation themselves.
Wow, that's great! Thank you very much for releasing it. 

However, I am wondering since I always thought that a compiled program cannot be reverted to its original source code. So is this actually possible, or did you have the original source code?
## Post #76
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-12-19T20:20:10+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

It's .NET code, which decompilers exist for.
## Post #77
- Username: SWTOR fan
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-20T05:42:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

use App call reflector
## Post #78
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-21T19:24:32+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

is there any tools to repack assets, i mean only texts or any way how to use translated texts in game ?
## Post #79
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-22T13:21:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Rick
>
> It's .NET code, which decompilers exist for.
Thank you for that information, I will keep it in mind! Too bad that not all programs are written in .NET. 

> Reply from michalss
>
> is there any tools to repack assets, i mean only texts or any way how to use translated texts in game ?
I have not yet heard of any tools for repacking the asset files.
Since SWTOR is an online game and the license agreement clearly states that it is not allowed to edit the asset files, I would not recommend doing that since you could risk being banned with your paid game time going to waste.
Apparently, they have a system in place to track any cheaters and I doubt that they will make a difference between a person who just wants to translate the game and someone who wants to cheat on purpose.

Anyway, in case you still want to edit the assets, this may help you:
The MYP archives themselves seem to be easy enough to edit. You can just append the new file to the archive and change the file offset in the file table and that should work. This can even be done in a hex editor, so you do not need a repacker tool.
However, I would recommend that you first analyse the ft.sig and metadata.bin files from the archives as they probably contain some kind of checksum to see if the assets were edited.
And of course, each time there is an update, you will have to edit the assets again.
## Post #80
- Username: delium
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 14, 2010 6:26 pm
- Post datetime: 2011-12-22T18:15:48+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

perhaps this helps:
[http://forum.ragezone.com/f111/fakewp-0-5-0-myp-801703/](http://forum.ragezone.com/f111/fakewp-0-5-0-myp-801703/)
-> [http://public.dadummy.net/war/](http://public.dadummy.net/war/)
## Post #81
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-22T23:35:59+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have looked at the source code of NodeViewer and it seems like most of the format of the prototype nodes and bucket files is not given in the NodeViewer source code itself, but actually in the assets files. What's even stranger is that the developers did not remove the comments from the file so it should be fairly easy to figure the format out.

Anyway, here's the code of Disassembler/Hero/HeroTypes.cs with an overview of all variable types. It is somewhat similar to my specification posted on page 4 but it looks like I missed quite a few of them.

```
{
    using System;

    public enum HeroTypes
    {
        Association = 10,
        Boolean = 3,
        Class = 9,
        Date = 0x15,
        Enum = 5,
        Float = 4,
        GuiControl = 0x10,
        Guid = 0x13,
        Id = 1,
        Integer = 2,
        List = 7,
        LookupList = 8,
        NodeRef = 15,
        None = 0,
        Rawdata = 0x16,
        ScriptRef = 14,
        String = 6,
        Timeinterval = 20,
        Timer = 0x11,
        Vector3 = 0x12
    }
}
```


The next file to look at is /resources/systemgenerated/client.gom from swtor_main_systemgenerated_gom_1.tor. This file (with the file header DBLB -- 44 42 4C 42) seems to contain the format of the bucket files and prototype nodes but it is in binary. I have yet to look at the Hero source code, I suppose that the format of this file is described in there.

To anyone wanting to help with the analysis I suggest reading these articles as they contain some information on the way the HeroEngine handles the game data:
[http://wiki.heroengine.com/wiki/DOM](http://wiki.heroengine.com/wiki/DOM)
[http://wiki.heroengine.com/wiki/GOM](http://wiki.heroengine.com/wiki/GOM)
## Post #82
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-24T00:08:28+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

List of file formats used in SWTOR
With the amount of new file formats discovered in the newest version of the client files and so many XML files dropped from the client, I decided to write a new list of file formats so that I could keep the old one as a historical reference and yet have an up-to-date version as well.
Of course, I may have missed some files, so please tell me if you have any more information to add to the list.

Archive files
These files are archives that contain other files.

File extension: .acb
File header: XX XX XX XX 00 00 00 00
Description: File containing bare audio files. The header is not completely correct (the first eigth bytes are actually a long integer) but should work.

File extension: .bkt
File header: PBUK........DBLB
Description: Bucket files, contain compiled XML files with zlib encoding. Found in /resources/systemgenerated/buckets.

File extension: .bnk
File header: BKHD
Description: Container for Wwise audio files with additional metadata. Sections are named DIDX, DATA, HIRC, STID. Search for "bnkextr" tool in [this topic](http://forum.xentax.com/viewtopic.php?f=17&t=3477&start=30).

File extension: .tor
File header: MYP
Description: Main archive for all files. In /Assets folder. Files start swtor_. Can be extracted with [easyMYP](http://code.google.com/p/easymyp/).

Filelists
These files contain a list with references to other files. All in /resources/systemgenerated.

File extension: .gom
File header: DBLB (44 42 4C 42)
Description: Specification of bucket files. Contains files with zlib encoding???

File extension: .info
File header: PBCK (50 42 43 4B)
Description: List of buckets.

File extension: .info
File header: PINF (50 49 4E 46)
Description: List of prototypes.

File extension: .list
File header: SDEF (53 44 45 46)
Description: List of scripts.

Compiled files
These files are binary files and can only be read in a HEX editor or designated reader.

File extension: .bik
File header: BIKi (42 49 4B 69)
Description: Regular Bink Video files, contained in the /Movies folder (i.e. not part of the TOR archives). Can be opened with the [RAD Video Tools](http://www.radgametools.com/bnkdown.htm).

File extension: .dds
File header: DDS
Description: Normal DDS texture (Direct Draw Surface), can be opened in any DDS reader.

File extension: .fxa
File header: FACE (46 41 43 45)
Description: FaceFX files, containing facial animations. Most have been renamed to .fxe, except the ones in /resources/server/facefx.

File extension: .fxe
File header: FACE (46 41 43 45)
Description: FaceFX files, containing facial animations, matched to the localised voices in the sound files.

File extension: .gfx
File header: CFX
Description: Possibly graphics effects, found in in /resources/gfx/gfx_production.

File extension: .gr2
File header: GAWB
Description: Granny Format by RAD Game Tools, containing the models. See [this topic](http://forum.xentax.com/viewtopic.php?f=16&t=7403) and [that topic](http://forum.xentax.com/viewtopic.php?f=16&t=7705) for more information. In the retail version, a custom model format seems to be used but the .gr2 file extension was retained.

File extension: .jba
File header: 00 00 00 00
Description: Possibly contains animations. easyMYP automatically classifies them as zero.txt. Found in /resources/anim.

File extension: .mph
File header: 02 00 00 00
Description: Contains list of animations in a compiled format.

File extension: .node
File header: PROT.... (50 52 4F 54 02 00 04 00)
Description: Prototype node, contains a compiled form of the XML dialogues and stringtables. See /resources/systemgenerated/prototypes.

File extension: .spt
File header: E8 03 00 00
Description: SpeedTree files, in /resources/art/static/area/.../speedtree. See [this article](http://nwn2.wikia.com/wiki/Speed_Tree_Format).

File extension: .stb
File header: 01 00 00
Description: String table, in /resources/en-us/str.

File extension: .swf
File header: CWS. (43 57 53 0A)
Description: Normal Adobe Flash file, used for fonts and some animations, e.g. /resources/gfx.

File extension: .wem
File header: RIFF..6.WAVEfmt
Description: WWise audio file. Dialogue and sound effects are contained in .bnk/BKHD or .acb archives, music/soundtrack is stored in /resources/bnk2/streamed. See [here](http://hcs64.com/vgm_ripping.html) for the decoding tool ww2ogg.

File extension: (none)
File header: SCPT
Description: Contains header with some strings and a custom script file (Hydra script?). See the folder /resources/systemgenerated/compilednative.

File extension: n/a
File header: AMX (41 4D 58 20)
Description: Contains animations.

Human-readable files (txt/xml)
These files can be opened and edited in normal text or XML editors, although I would recommend using a hex editor for editing. The format should be pretty self-explanatory.
Note: Many XML files are encoded in Unicode, so if you open them in a hex editor, don't be surprised if you see bytes like ÿþ<.S.u.r.v.e.y.I.n.s.t.a.n.c.e.>. (e.g. ÿþ = Byte Order Mark for UTF-16). Also, some files have an <!xml> tag before the first tag.

Text files

File extension: .dat
File starts with: ! Room Specification
File starts with: ! Area Specification for ...
File starts with: ! Character Specification for ...
Description: Text file in /resources/world and /resources/art/dynamic/spec. Contains definitions of the rooms/maps. Comments are marked with an exclamation mark at the beginning of a line, eg. "! Room Specification". Some files contain textures(?), to do that copy the hex bytes into a hex editor and decode them using gzip. See the [HeroEngine wiki](http://wiki.heroengine.com/wiki/Area_.DAT_file).

File extension: .dyc
File starts with: Version=2
Description: Text file (dynamic character specification). See /resources/art/dynamic/spec/ and the [HeroEngine wiki](http://wiki.heroengine.com/wiki/Technical:Dynamic_Char_Spec).

File extension: .mag
File starts with: ! Character Specification for ...
Description: Same as .dat files. See the [HeroEngine wiki](http://wiki.heroengine.com/wiki/Character_Spec).

File extension: .prt
File starts with: ! Particle Specification
Description: Found in /resources/art/fx/particles.

XML files

.clo → <ClothData> in /resources/art/dynamic/creature/model

.epp → <Appearance> in /resources/gamedata/epp

.fxspec → <nodeWClasses> in /resources/art/fx/fxspec

.lod → <LODSchemaGroup> in /resources/art

.manifest → <manifest> in /resources/gamedata/str/stb.manifest

.mat → <Material> in /resources/art/shaders/materials

.not → <v> in /resources/world/.../mapnotes.not

.rul → <Rules> file (whether the PC can wear certain item combinations at the same time)

.svy → <SurveyInstance> in /resources/gamedata/svy

.tbl → <DataTable> in /resources/server/tbl

.tex → <TextureObject> files for each .dds file

.xml → General xml file, e.g.
→ <aam> in /resources/anim
→ <Assets> in /resources/art/dynamic
→ <blocked> in /resources/engine/utility/stringfilter_profanity_en_us.xml
→ <createControlType> in /resources/guixml
→ <credits> in /resources/gfx/credits/credits.xml
→ <Palette> in /resources/art/dynamic/gamenthue

(unknown file extension) → <Root>

Unknown files
The following binary files occur only once and it is unclear what their content is. They do not have a file header to identify them and are yet to be analysed.

ft.sig
groupmanifest.bin
metadata.bin
resources/global.dep

Unknown engine files
As in the old file list, there are a few file extensions mentioned in paths but I have not yet found the respective files themselves. Instead of listing all of them, I will just point you to the old list on page 1.

Edit 1: .clo files added (<ClothData>)
Edit 2: .not files added, script files corrected
## Post #83
- Username: Seifer29
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 24, 2011 7:51 am
- Post datetime: 2011-12-24T00:08:54+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey guys, was just wondering about the old application Easymyp that was created mainly for Warhammer Online.  That tool was pretty nice and allowed for easy swapping of things like sounds, animations, models, etc.  My question was basically is the ultimate goal to have a similar tool for use with SWTOR?  Or maybe even an update to easymyp for use with SWTOR?  It seems like easymyp can open the .tor files, but everything comes up as .txt or zero txt files because I guess the hash files aren't done for SWTOR.  Was wondering how you guys go about figuring out the hash files and if there was anyway people could help out with such a thing (I am obviously clueless when it comes to this stuff, so these questions are probably absurd, but never hurts to ask).  Take care.
## Post #84
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-24T00:26:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Seifer29
>
> Hey guys, was just wondering about the old application Easymyp that was created mainly for Warhammer Online.  That tool was pretty nice and allowed for easy swapping of things like sounds, animations, models, etc.  My question was basically is the ultimate goal to have a similar tool for use with SWTOR?  Or maybe even an update to easymyp for use with SWTOR?  It seems like easymyp can open the .tor files, but everything comes up as .txt or zero txt files because I guess the hash files aren't done for SWTOR.  Was wondering how you guys go about figuring out the hash files and if there was anyway people could help out with such a thing (I am obviously clueless when it comes to this stuff, so these questions are probably absurd, but never hurts to ask).  Take care.
As far as I know, everyone working on the asset files is either writing his own MYP extractor or using easyMYP. I am not sure who is planning to release his tool but until then I would recommend using easyMYP (the newest version is 3.6, btw).
The new hash list Rick posted (with 48% analysed) is written in a custom format and cannot be used directly by easyMYP. However, you could try opening the .filelist files in Notepad and see if you can somehow import the filenames into easyMYP manually.
If you have some experience with computer programming, you can write yourself a tool that will rename the file extensions based on the file headers from my file format list. Other than that, I cannot help you at the moment. 

As I wrote above, I strongly discourage someone to try and edit the asset files as this could result in being banned. Before editing the assets, we have to analyse the metadata.bin and ft.sig files to make sure that they do not contain any file checksums, and even then it is better to just extract the files and not edit them since SWTOR is an online game.
## Post #85
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-24T23:06:33+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> If you have some experience with computer programming, you can write yourself a tool that will rename the file extensions based on the file headers from my file format list. Other than that, I cannot help you at the moment.
I posted a 010 script that could be used to maybe find all the different file types here.......
[viewtopic.php?p=64091#p64091](http://forum.xentax.com/viewtopic.php?p=64091#p64091)
I'll be following up with a renameing script for 010 also.
EDIT: Renameing script is posted.
I still have a lot to do on the stand alone program that will do a mass find and renameing of all known formats in one run.

Great Job here Guys!
## Post #86
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-12-30T07:56:56+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Now at 257587/364794 (70%).
[257587.zip](https://xentaxbackup.github.io/file/4937_257587.zip)
## Post #87
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2011-12-30T16:35:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Can't wait for 100%, keep up the good work
## Post #88
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-30T16:46:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Panzah
>
> Can't wait for 100%, keep up the good work
I can only second that; great work, Rick! 
I was just about to try to find out additional filenames myself when you posted the update. I have a few guesses on the remaining filenames so I will check if the filenames do exist and post them then.

By the way, how long does it take your program to start up and display all filenames in a tree node view?
For me it takes a few minutes because I have not presorted the nodes, but do it during the loading. Even if I do not sort all the nodes by name, it takes quite a long time to load.
Have you found a faster way to load them?
## Post #89
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-12-30T20:23:56+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> By the way, how long does it take your program to start up and display all filenames in a tree node view?
For me it takes a few minutes because I have not presorted the nodes, but do it during the loading. Even if I do not sort all the nodes by name, it takes quite a long time to load.
Have you found a faster way to load them?I don't have a visual archiving tool, my tools are command-line. It takes a few seconds to load the file lists and utilize them.
## Post #90
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-12-30T20:43:27+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Rick
>
> I don't have a visual archiving tool, my tools are command-line. It takes a few seconds to load the file lists and utilize them.
Alright, I guess it is not possible to speed up my program any further then.  But with thousands of files, it is not surprising that it is taking so long...

I was looking through the archives and noticed a few file names that seem to be missing (e.g. many .dds files have a .tiny.dds and a .tex file), and upon testing them, they worked. I doubt that these filenames will even increase the percentage to 71% but at least it is a start. If nothing else, they will at least complete the swtor_en-us_cnv_misc_1.tor filelist to 100%. 
Since the files come from different TOR files, I won't post them separated by TOR archive and just hope that your program can figure out their origin itself.

```
/resources/art/environmentmaps/ord_resize/ord_area.dds
/resources/art/environmentmaps/tar_main/area.dds
/resources/art/environmentmaps/tar_main/area.tex
/resources/art/environmentmaps/tar_main/area.tiny.dds

/resources/en-us/bnk2/cnv_misc_generic_lines_jedi_knight_m.acb
/resources/en-us/bnk2/cnv_misc_generic_lines_jedi_wizard_m.acb
/resources/en-us/bnk2/cnv_misc_generic_lines_jedi_wizard_f.acb
/resources/en-us/bnk2/cnv_misc_generic_lines_sith_sorcerer_m.acb
/resources/en-us/bnk2/cnv_misc_generic_lines_sith_warrior_f.acb
/resources/en-us/bnk2/cnv_misc_generic_lines_smuggler_f.acb
/resources/en-us/bnk2/cnv_misc_generic_lines_spy_f.acb
/resources/en-us/bnk2/cnv_misc_generic_lines_trooper_f.acb
/resources/en-us/bnk2/cnv_misc_generic_lines_trooper_m.acb

/resources/world/areas/4611686040187270001/mapnotes.not
/resources/world/areas/4611686033020472228/mapnotes.not
/resources/world/areas/4611686021579460422/mapnotes.not
/resources/world/areas/4611686039258170278/mapnotes.not
/resources/world/areas/4611686033507370314/mapnotes.not
/resources/world/areas/4611686035947170168/mapnotes.not
/resources/world/areas/4611686040994970456/mapnotes.not
/resources/world/areas/4611686041464170233/mapnotes.not
/resources/world/areas/4611686041700070232/mapnotes.not
/resources/world/areas/4611686041700070345/mapnotes.not
/resources/world/areas/4611686041748971553/mapnotes.not
/resources/world/areas/4611686041922470000/mapnotes.not
/resources/world/areas/4611686041944170162/mapnotes.not
/resources/world/areas/4611686044023070789/mapnotes.not
/resources/world/areas/4611686023014030644/mapnotes.not
/resources/world/areas/4611686025383332936/mapnotes.not
```
## Post #91
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-12-30T21:09:56+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have a tool called 'Rebuild File Lists' which takes all file lists and writes new ones out based on the archives. So yes, it can do that.
## Post #92
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-01-01T02:09:50+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Good to hear that, Rick!
I uploaded some more filenames to Pastebin: [http://pastebin.com/JqNyX3tA](http://pastebin.com/JqNyX3tA)
Now _bnk_audio_1.tor, _bnk_audiodata_1.tor and _bnk_location_1.tor are complete.
## Post #93
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-01-02T16:36:05+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

SCPT file specification (version 5)
I was looking at the script files (header: SCPT, path: /resources/systemgenerated/compilednative/) and what a surprise, the format has completely changed since I posted the specification on page 1 of this thread.  The current version is now 5, compared to the old version 4 I wrote about.

It seems like the ELF script files have been abandoned and a custom script format is now used. The new script files start with D1 03 but I have not looked into them very much. Anyway, here's the format of the new SCPT files, but without the last part that contains the script files:

File header:
0-3: 4 bytes, file header: SCPT (53 43 50 54)
4-7: file version as two 16-bit integers: 05 00 05 00 → version 5
8-11: Unknown 32-bit integer (little-endian), always 1: 01 00 00 00
12-15: four zero bytes: 00 00 00 00
16-21: six bytes, possibly a CRC checksum, different for each file
22-23: two bytes, end of header: 00 D0

Script Name:
24: Variable-length integer specifying length of script name (all version 5 files no longer contain a script name, i.e. this byte is always 00)
string with specified length, if it exists
25-32: eight zero bytes
33-36: 32-bit integer, length of file, offset starting after this length, excluding the final 00

Strings without id:
37: Variable-length integer specifying number of strings without an id
LOOP (for each string) {
→ Variable-length integer specifying string length
→ String with the specified length
} END LOOP

Strings with id:
Variable-length integer specifying number of strings with an id
LOOP (for each string) {
→ Variable-length integer specifying string id
→ Variable-length integer specifying string length
→ String with the specified length
} END LOOP

Script file:
Beginning of script file, starting with D1 03
Final byte: 00

Example
For example, the script file /resources/systemgenerated/compilednative/14988250124449474902 contains the following strings:

Strings without id: datecreated, datelastmodified, lastread, ticketstatus, summary, fulltickettext
Strings with id: MAX_UPDATE_LENGTH, SubmitNewTicket, UpdateTicketText, UpdateTicketRead, CloseTicket, OnRequestTicketsCB, _ParseTicketFields, OnRequestTicketCB, TrackLine, ConstructLookupListIterator, LookupListIteratorNext, PopUntilTemporaries, ConstructString, GetLookupListCurrentValueLookupList, PrepareLocalCall, UnprepareCall, RefLookupListElementROByStringString, ConvertFromStringInt, LookupListHasStringCopyValueString

It seems like the strings without id are just strings used by the script, while strings with id contain the function and variable names. However, I do not know enough about the script files to say this for sure.

Script file
As I said, I have not yet analysed the format of the script file; here are the starting bytes of one script files.
It seems like D1, D3 and bytes 00 to 06 are used very often.
Does anyone recognize this format by chance, or is it really a custom format?

D1 03 01 D1 00 02 D3 C9 09 C5 D3 05 D1 00 02 D3
D1 00 00 D3 D1 00 06 D3 D1 00 08 D1 00 02 D3 D1
00 08 D1 00 06 D3 D1 00 06 D3 D3 D3 D1 00 08 D1
00 06 D3 D1 00 06 D3 D3 06 02 00 01 04 02 03 00
01 04 00 04 02 02 00 01 04 00 02 00 01 04 03 08
00 01 04 04 03 00 03 00 03 00 03 02 03 02 03 02
03 00 01 04 00 04 04 01 06 04 01 00 00 00 00 00
00 C9 06 0F 01 00 03 01 10 C9 06 0F C3 00 00 00
00 00 00 00 00 00 00 00 00 00 00 00 83 EC 0C 8B
44 24 14 8B 00 89 44 24 04 8B 44 24 10 89 04 24
E8 FC FF FF FF 83 C4 0C C3 00 00 00 C3 00 00 00

Ñ..Ñ..ÓÉ.ÅÓ.Ñ..ÓÑ..ÓÑ..ÓÑ..Ñ..ÓÑ..Ñ..ÓÑ..ÓÓÓÑ..Ñ..ÓÑ..ÓÓ.........................................................É.......É..Ã...............ƒì.‹D$.‹.‰D$.‹D$.‰.$èüÿÿÿƒÄ.Ã...Ã...............ƒì.‹D$.‹.‹P.‹@.‰D$.‰T$.‰L$.‹D$.‰.$èüÿÿÿƒÄ.Ã.....Ã...............ƒì.‹D$.‹.‹@.‰D$.‰L$.‹D$.‰.$èüÿÿÿƒÄ.Ã............Ã...............ƒì.‹D$.‹.‹@.‰D$.‰L$.‹D$.‰.$èüÿÿÿƒÄ.Ã............USWVƒ
## Post #94
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-01-03T17:07:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Here's the biggest of my file name updates so far, with more than 30,000 new file names.  
Most of them are from swtor_main_gfx_1.tor (the item icons) but the archive is still not even near completion.

What percentage are we at now, Rick? Unfortunately, I have not built any statistics into my program yet.
[filenames-found2.zip](https://xentaxbackup.github.io/file/4948_filenames-found2.zip)
## Post #95
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-01-04T00:59:35+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> Here's the biggest of my file name updates so far, with more than 30,000 new file names.  
Most of them are from swtor_main_gfx_1.tor (the item icons) but the archive is still not even near completion.

What percentage are we at now, Rick? Unfortunately, I have not built any statistics into my program yet.Now at 299288/364794 (82%).

(Your list added 30876 new names to my lists.)
[299288.zip](https://xentaxbackup.github.io/file/4951_299288.zip)
## Post #96
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-01-04T16:24:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Rick
>
> (Your list added 30876 new names to my lists.)
That's strange, maybe you have a different version of the asset files than me. I am sure we will have that figured out when we got closer to 100%.

For now, here are nearly 15,000 new file names. 
[filenames-found3.zip](https://xentaxbackup.github.io/file/4954_filenames-found3.zip)
## Post #97
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-01-04T17:02:27+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> That's strange, maybe you have a different version of the asset files than me. I am sure we will have that figured out when we got closer to 100%.

For now, here are nearly 15,000 new file names.I'm adding new files all the time, it's possible that I added some that were in your lists since I posted the last update.
## Post #98
- Username: JasonBlack
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 19, 2011 8:55 pm
- Post datetime: 2012-01-22T06:02:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hate to make a request of my first post, but I'm sure others will be asking soon. Slap me if I'm out of line here, but I haven't been able to find the latest EasyMYP that isn't on megaupload (currently locked down in legal proceedings).

Can we get a new link?
## Post #99
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-01-22T06:50:44+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

There is a working link in [this](http://forum.xentax.com/viewtopic.php?p=62367#p62367) post, the archive contains a special TOR build of EasyMYP along with a hash dictionary which has 44.5% of file names.

EDIT
New working link to the SWTOR build of EasyMYP 3.6 in [this post](http://forum.xentax.com/viewtopic.php?p=85804#p85804).
You can get the latest compatible hash list in [this post](http://forum.xentax.com/viewtopic.php?p=83851#p83851).
The latest *.gr2 model import plugin for noesis can be found in [this post](http://forum.xentax.com/viewtopic.php?p=83383#p83383).
## Post #100
- Username: JasonBlack
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 19, 2011 8:55 pm
- Post datetime: 2012-01-22T06:55:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from AceWell
>
> There is a working link in this post, the archive contains a special TOR build of EasyMYP along with a hash dictionary which has 44.5% of file names.

I must've read past that couple of times and not seen it. Very sneaky. Many thanks.
## Post #101
- Username: revulva
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 19, 2012 10:18 am
- Post datetime: 2012-01-22T22:34:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I am new to this type of stuff, but have been really interested in all that is being said in this forum.

I see these lists of file names that are being posted fairly regularly. I saw a post saying that they are in a custom format that will not work with easyMYP. When I open the list of file names, it is just a list - how do I match those up to the actual files I have extracted? Specifically, I extracted all the .dds files in swtor_main_gfx_1.tor - now I would like to get those file names translated from just the numbers to something meaningful so I can start to match them up with items and abilities. 

If anyone would be willing to point me in the right direction, I'd appreciate it!
## Post #102
- Username: JasonBlack
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 19, 2011 8:55 pm
- Post datetime: 2012-01-22T23:36:34+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

This may not be how it was meant to go, but it works:

Download and unzip the 299288.zip posted by Rick (above), rename the .filelist file you would like to access to .txt  then open the .tor archive with the corresponding name in EasyMYP. Go to the dictionary tab and do test full filename list and open the file you just gave the extension txt. That doesn't make any immediate change, but when you close MYP the hash list is saved.

Reopen that .tor file and it will have good names in the archive file list view.
## Post #103
- Username: revulva
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 19, 2012 10:18 am
- Post datetime: 2012-01-23T16:53:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thank you! That worked.

It seems like many of you are veterans at doing this sort of stuff. Is there anyone here that would be willing to explain (or give me a beginner's understanding) HOW you figured out these file name hashes? I would love to be able to figure some of this stuff out on my own when updates to the game come out.
## Post #104
- Username: brutang
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 24, 2012 4:19 pm
- Post datetime: 2012-01-24T08:39:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I still can't seem to figure out how to get the ability data from these .tor files using EasyMYP. I believe it's swtor_main_global_1.tor in the bucket files but I'm not sure how to read them. Any advice?

The context of this is I'm doing a school project and would like to have the ability data to create a database for myself.

BTW Totally appreciate the work you guys have done!
## Post #105
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2012-01-26T15:05:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Any progress on completing the list? Mind you that Update 1.1 was released
## Post #106
- Username: fmauNeko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 16, 2012 6:26 am
- Post datetime: 2012-01-26T20:42:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello,
Did anyone found a specification for the String Tables (.stb) format ? That would be interesting to extract the item database.

Thanks
## Post #107
- Username: Nomis
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 05, 2011 6:54 pm
- Post datetime: 2012-01-27T15:04:53+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from fmauNeko
>
> Hello,
Did anyone found a specification for the String Tables (.stb) format ? That would be interesting to extract the item database.

Thanks

Here a simple 010 Template for the String Tables:

```
    byte header[3];
    int count;
} StlHead;

typedef struct StringEntry {
    int64 textId;
    short unknown1 <comment="321=First, 326=Second ?">;
    byte unknown2[8];
    int offset;
    int length;

    if (length > 0){
        local int pos;
        pos=FTell();
        FSeek(offset);
        char entryContent[length];
        FSeek(pos);
    }

} StringEntry;



LittleEndian();
local int i;

StlHead head;
for (i = 0; i<head.count; i++){
    StringEntry entry;
}
```


Each entry is doubled. The unknown1 field indicates if it's the first or the second occur.
## Post #108
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-02-06T20:38:05+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

It's been quite a while since my last response, I hope everyone's fine. 

I have found out nearly 4000 new filenames, mostly from the swtor_main_art_dynamic_*_1.tor archives. While these files are named after a certain pattern, there are so many files that it takes a long time to get all file names.
Rick, how have you been? Would you mind uploading a new .filelist archive? They are much more convenient than my list. Have you found out new file names yourself as well?

In other news, I have finally made some progress on the client.gom file. I'll give an update once I know more. By the way, @brutang and fmauNeko, the .stb files will unfortunately only give you the names of the items/abilities, the actual data, e.g. amount of damage, is saved in the buckets/prototype nodes, which are related to the .gom file.
[filenames-found4.zip](https://xentaxbackup.github.io/file/5040_filenames-found4.zip)
## Post #109
- Username: flipkick
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 09, 2012 8:40 pm
- Post datetime: 2012-02-09T12:45:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I've written a ruby script to extract the translations of the language (stb ?) files. Get it at [http://flip.netzbeben.de/2012/02/dfslf- ... nslations/](http://flip.netzbeben.de/2012/02/dfslf-swtor-translations/)

Example output:

```
 - 00220a00_de: [Zielgenauigkeit +2]
 - 00220a00_en: [ Aim +2 ]
 - 00890100_de: Haze wollte ihn erschießen. Aber Haze will jeden erschießen. Doch dann griffen die Sandleute an und haben sich für uns um Nerrik gekümmert.
 - 00890100_en: Haze wanted to shoot him. But Haze wants to shoot everyone. But then the Sand People attacked and took care of Nerrik for us.
 - 00930400_de: [Dieses Terminal enthält einen Teil der Bombenpläne.]
 - 00930400_en: [The terminal contains part of the bomb plans.]

```
## Post #110
- Username: flipkick
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 09, 2012 8:40 pm
- Post datetime: 2012-02-11T18:30:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Does anyone has access to the development tools of the Hero Engine? SWTOR is built with it, and i guess with these tools it would be easy to get more information about several file structures and their content. I'm very interested in the gom files: [http://wiki.heroengine.com/wiki/GOM](http://wiki.heroengine.com/wiki/GOM)

SWTOR also comes with the Granny 3D lib, dunno for what it is used actually there (maybe simply by the Hero Engine), i just wanted to let you know.
## Post #111
- Username: fmauNeko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 16, 2012 6:26 am
- Post datetime: 2012-02-11T18:34:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

For the GOM files, NodeViewer and Hero.dll are unobfuscated .NET assemblys, so you can decompile it with any .NET decompiler like JustDecompile, which works well.
## Post #112
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-02-11T18:38:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from flipkick
>
> Does anyone has access to the development tools of the Hero Engine? SWTOR is built with it, and i guess with these tools it would be easy to get more information about several file structures and their content. I'm very interested in the gom files: http://wiki.heroengine.com/wiki/GOM

SWTOR also comes with the Granny 3D lib, dunno for what it is used actually there (maybe simply by the Hero Engine), i just wanted to let you know.
Unfortunately, the developers of SW:TOR have adapted the Hero Engine source so much that it won't help too much to have the original source. However, the NodeViewer source code would be a good place to get you started.

The model files are a custom Bioware format; they are still called .gr2 files because they have been Granny models during the beta, but have since then been replaced by the new format. AFAIK nicoli_s is working on a model converter, though I do not know about his progress.
## Post #113
- Username: flipkick
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 09, 2012 8:40 pm
- Post datetime: 2012-02-13T16:18:05+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

fmauNeko, this was very helpful. I've written a small C# program which uses Hero.dll to extract information about the currently 41554 available items in SWTOR (which is what i have found at the moment)  And now i can confirm the 64bit int id of the translations in the stb files, they are referenced from the gom.

I'll try to improve the program to show more detailed information about the items and then i'll upload it here.
## Post #114
- Username: flipkick
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 09, 2012 8:40 pm
- Post datetime: 2012-02-14T21:45:38+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I found some first detailed information of the item prototypes. The C# source for my extract tool is attached, Hero.dll is required. The mysql stuff is for my personal translation db.

This is my very first C# program, so be gentle 

Example output:

```
 type: String: "armor.trooper"
 sub type: String: "ipp.class.bh.heroic.rdps1.t4x2.chest"
 bind on pickup
 durability: 120
 id: 16140952217605448722
 title: Xonolite Mesh Chestguard
 slot #0: Id: 16141113719776797593
  - title: Reflex Armoring 12
  - stats: STAT_att_agility: 15
  - stats: STAT_att_endurance: 10
 slot #1: Id: 16141146200986683659
  - title: Reflex Mod 12
  - stats: STAT_att_agility: 20
  - stats: STAT_att_endurance: 10
 slot #2: Id: 16141028933557874887
  - title: Rage Enhancement 12
  - stats: STAT_att_endurance: 10
  - stats: STAT_rtg_attack_power: 15
 slot #3: empty
 slot #4: empty

itm.eq.cc.pierce.legs.heavy.premium.cc_05i:
 type: String: "armor.trooper"
 sub type: String: "ipp.companion.pierce.default.legs"
 bind on pickup
 durability: 120
 stats: STAT_att_agility: 25
 stats: STAT_att_endurance: 42
 stats: STAT_rtg_accuracy: 3
 stats: STAT_rtg_defense: 13
 id: 16140958271266809222
 title: Pierce's Pants
 slot #0: empty
 slot #1: empty
 slot #2: empty
 slot #3: empty
 slot #4: empty

itm.gen.quest_wpn.theal1a.blaster.prototype.07x1:
 type: String: "weapon.ranged.blaster.holdout01"
 sub type: String: "blaster.high06.a03_v01"
 bind on pickup
 durability: 200
 id: 16140961445110358222
 title: D-203 Recon Interceptor
 slot #0: Id: 16140922506011855339
  - title: Blue Lethal Crystal
  - stats: STAT_rtg_critical_chance: 27
 slot #1: Id: 16141135957775441233
  - title: Commando Barrel 22
  - stats: STAT_att_agility: 34
  - stats: STAT_att_endurance: 36
 slot #2: Id: 16141046178047402709
  - title: Nimble Mod 22
  - stats: STAT_att_agility: 41
  - stats: STAT_att_endurance: 24
  - stats: STAT_rtg_critical_chance: 7
 slot #3: Id: 16141019615760744772
  - title: Assault Enhancement 22
  - stats: STAT_att_endurance: 22
  - stats: STAT_rtg_critical_chance: 10
  - stats: STAT_rtg_critical_damage: 28
 slot #4: empty

```


Nice, isn't it? I'll try to analyze even more item detail information.
[Program.rar](https://xentaxbackup.github.io/file/5065_Program.rar)
## Post #115
- Username: fmauNeko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 16, 2012 6:26 am
- Post datetime: 2012-02-14T22:27:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Good work here =)

I'm trying to understand how those gom files work from Hero.dll, and if I can, I'll make a program generating a real database from those files, and implement it in a real cross-platform language. My goal is to put it to run periodically on my server, and autogenerate the database whenever I upload the new files (to be reactive when new content is added.
## Post #116
- Username: OverWind
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 17, 2012 8:55 pm
- Post datetime: 2012-02-17T13:00:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Greetings good sirs and/or madams,

I would like to try datamining the swtor files (because I'm curious, and would like to learn new things).
I'm a programmer, but have mostly been using Java, PHP, Perl, etc. etc.

I have tried fetching EasyMYP and the Hash file and created the "Hash" folder, and the program starts up fine, but when I selected a tor file, it just crashes.
I guess my problem is that I don't really know what to do.

Could anyone post a simple tutorial to get from A to C? Where A is me knowing next to nothing (but I know what a C# and Ruby script is, and I know programming) and getting some info out from the files. I would really appreciate it.

Thanks in advance!
## Post #117
- Username: flipkick
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 09, 2012 8:40 pm
- Post datetime: 2012-02-17T16:11:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from OverWind
>
> 
I have tried fetching EasyMYP and the Hash file and created the "Hash" folder, and the program starts up fine, but when I selected a tor file, it just crashes.

use easymyp 3 instead of 2.
## Post #118
- Username: Lex Talionis
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 15, 2012 7:02 pm
- Post datetime: 2012-02-18T09:55:22+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Many thanks for all the hard work here, guys.

@flipkick & SWTOR fan - In the string tables entries the 2 bytes at position 08-09 seem to flag what type of string it is.  For example:

4100 - 4103 = Plain Text String (Can be used almost anywhere in the UI)
4104 - 4105 & 4115 = Voice Acted String (Galactic Basic - Will be spoken in whatever language the user's copy of the game allows.)
410d = Voice Acted String (Alien Language)
5004 - 5005 = Dialogue Wheel Option

I haven't figured out 4106 & 4107...  They seem to be a mess of test strings, Voice Acting Strings and everything else.

Anyway, hope that helps a little.  :3
## Post #119
- Username: bhaal85
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 19, 2012 1:52 am
- Post datetime: 2012-02-19T11:20:46+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello everyone, I need some information to extract items and spells from swtor.

I use easymyp v3.2.

I downloaded the file ricky (82%) but can not import it into EasyMYP.
If I understand it I should convert the files. Filelist one file and call it hashes_filename.txt and place it in the Hash EasyMYP.

How do I create this file?

Could you explain the steps to remove items?

Thanks and sorry for my english: D
## Post #120
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-02-20T17:29:07+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Bad news, unfortunately. 
It looks like all the names and descriptions were removed from the client.gom file (except for ~150 nodes) which will make it considerably harder to datamine the buckets/prototype nodes because one no longer knows what all these values stand for.
So anyone who was using the NodeViewer will now see many empty fields. It should be possible to identify the names of these fields based on their id and comparing them to old versions of the client.gom files.

Also, the script files (SCPT) seem to have changed as well but since I have not yet analysed their old format this is not too much of a setback. 

Here's the current header of the sections in the client.gom file. Anyone who has been working on the file before will know what it means, for everyone else I will post a full specification once I know more about the file.
The main thing that has changed is that the id field and the zero field have switched places, and that the name and description offsets, while still valid, now only produce a zero-length string.

```
Length     |Id                     |zero       |Type |StrO-|Name |Descr|
```

length = section length
id = section id
type = section type
StrO- = offset of strings
name = offset of name (zero-length string)
descr = offset of description (zero-length string)
## Post #121
- Username: flipkick
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 09, 2012 8:40 pm
- Post datetime: 2012-02-21T09:47:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> Bad news, unfortunately. 
It looks like all the names and descriptions were removed from the client.gom file (except for ~150 nodes) which will make it considerably harder to datamine the buckets/prototype nodes because one no longer knows what all these values stand for.

The gom still references to the STB files for game data. So you'll find the titles and descriptions there now.
## Post #122
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-02-21T11:14:38+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from flipkick
>
> The gom still references to the STB files for game data. So you'll find the titles and descriptions there now.
Well, names/descriptions of items or quests are of course still in the game, but the client.gom previously contained names such as "run speed", "quest trigger", "icon path", and all these are gone now; instead there are just a bunch of numbers without a name.
So if you know that the fifth value from the top, for example, is the item description, then you're good to go, but otherwise it will be very hard to read those values.

In any case, here are 5,000 new file names, mostly from the swtor_main_art_dynamic_*_1.tor archives again.
[filenames-found5.zip](https://xentaxbackup.github.io/file/5097_filenames-found5.zip)
## Post #123
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2012-02-24T17:08:47+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

the way i process the new gom is to load up the old and new version, and when i load up the old version i cache the field ids -> name, so i can have nice field names with the new gom
## Post #124
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-02-26T13:05:00+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from nicoli_s
>
> the way i process the new gom is to load up the old and new version, and when i load up the old version i cache the field ids -> name, so i can have nice field names with the new gom
That's a good idea! I have not yet tested if the old and new ids match up but if you say they do, then loading an old client.gom file should not be a problem. 
I just hope that they won't add too many new fields in the future and that we have as many fields named as possible.


Here's another 5,500 new file names; this time mostly *.jba animation files from swtor_main_anim_*_1.tor and maps from swtor_main_area_*_1.tor.


 filenames-found6.zip
5576 new file names for SW:TOR! (26.52 KiB) Downloaded 85 times



Also, due to the high demand, I decided to convert my file name lists into the format supported by easyMYP, so anyone who has been using easyMYP to open the .tor archives can just [download hashes_filename.txt here](http://www.sendspace.com/file/fzstmu) (9.37 MB), put the file in the "Hash" folder where easyMYP is stored and run easyMYP.
Please note that it may take a few minutes for easyMYP to load the big file. Also, I only tested the list with easyMYP 3.6 so you may run into problems if you are using a different version.
And please keep in mind that while you now have named files, these files may still be in a custom format, and that only a few of these files, like the .dds textures or audio files, can currently be opened with appropriate programs.
I included all the filenames I found out from both the main assets as well as the English, German and French localized assets. Right now, I left the CRC checksum field blank so you won't be able to check for file changes.

Edit: Download link fixed.
Edit 2: Just out of curiosity, I calculated the percentage of known file names and it currently stands at 89.55%. (40,270 unknown file names out of 385,484 total file names; not counting duplicate file names like metadata.bin)
## Post #125
- Username: DarkPhoenix
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 14, 2012 12:58 am
- Post datetime: 2012-03-13T17:09:22+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello, i wanted to ask if anyone can reupload EasyMYP 3.6, as megaupload was taken down. I have searched the thread but did not found any alternative links 

Edit: Found the link in other thread, [here](http://forum.xentax.com/viewtopic.php?f=16&t=7403&start=46)
## Post #126
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-03-18T14:19:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Since it seems to me that many do not know how to use easyMYP to extract files from the .tor archives, I decided to write a guide for it. 

Extracting .tor archives with easyMYP
1. Download EasyMYP 3.6 [here](http://holocron.so/files/tormyp.tar.bz2) and extract the archive.
2. Get the file name hashes:
--- 2a. If you have the beta files of SWTOR, extract the archive spitor-hash-44-5.rar and copy the hashes_filename.txt in there.
--- 2b. Otherwise, if you have the release version, download the newest version of hashes_filename.txt [here](http://www.sendspace.com/file/updvtx) (with about 91% of hashes complete). Extract the archive and copy the file hashes_filename.txt.
3. Now go to the folder "EasyMYP_v3.6-Spec SWTOR Batch Dict Parser", open the subfolder "Hash" and paste the hashes_filename.txt file in there.
4. Go back to the main EasyMYP folder and open EasyMYP.exe. Since the hash file is so large, it may take a few minutes for the program to start.
5. In the main menu (at the top), select "Archive → Open Archive".
6. In the open file dialogue, open the folder where you have Star Wars: The Old Republic installed. If you have kept the default path, you can find the game under "C:/Program Files/Electronic Arts/BioWare/Star Wars-The Old Republic/". Open the subfolder "Assets" and select a .tor archive to open. See below on which .tor archives contain which files.
7. Wait until the archive is opened. Then, under the "Archive Tree View" tab you will find a list of all the files. Please note that currently the file names are only known for about 90% of the files. Unknown files appear as a strange letter/digit-combination like "0EAAB4C2_C30F0F65F01C0A97". To see the named files, open the folder with no name, then open the folder called "resources" and pick the file you want.
8. Now you can either extract all files in the archive with "File → Extract All", or you can select a file to export and then either right-click this file and select "Extract", or choose "File → Extract Selected".
9. The first time you want to extract a file, you will be asked to choose a folder to extract to. You can later change the extraction folder under "Options → Preferences" and clicking on the "Set" button at the top.
10. Please note that many files are in a custom SWTOR game format and can only be opened with the right program. I suggest looking at the list I posted [here](http://forum.xentax.com/viewtopic.php?p=64104#p64104) for information on which files can be opened. For example, you can open .dds textures, .dat and .xml text files and audio files (.acb, .bnk, .wem) with the right program. If you want to convert audio files, see the tutorial I posted [here](http://forum.xentax.com/viewtopic.php?p=66311#p66311).

EasyMYP has many more options that I have not covered here. I suggest reading the "README.txt" file to learn more about those features.

[](http://imgur.com/wvfk6)

Description of .tor archives
The SWTOR files are grouped into different .tor archives.

The file names of the beta archives may start with red_main_*.tor/red_locale_*.tor or green_main_*.tor/green_locale_*.tor

If you have the release version, you will find file names starting with swtor_en-us_*.tor, and file names starting with swtor_main_*.tor. (Or swtor_de-de_*.tor and swtor_fr-fr_*.tor, if you are using the German or French language version.)

The German, English and French archives contain all the translated texts (like dialogues, item descriptions, conversations) and all of the spoken dialogue. Open the archive with the planet you want a file from, or open the "global" archive to get general files.
swtor_en-us_global_1.tor
swtor_de-de_area_hoth_1.tor

The main archives contain everything that does not need to be translated.
This includes .gr2 3D models and .dds textures (see swtor_main_art_*_1.tor) and animations (see swtor_main_anim_*_1.tor).
The swtor_main_area_*_1.tor archives contain .dds area maps and .gr2 3D models for specific planets.
The swtor_main_bnk_*_1.tor archives contain audio files without language (blaster fire, computer beeps, grunts, alien languages, ...) and the swtor_main_bnk_streamed_*_1.tor archives contain the music.
The swtor_main_gfx_1.tor archive contains the GUI icons, and all the other archives contain game mechanics like abilities, quests, items and so on.

Edit 1: Download link for hashes_filename.txt updated.
## Post #127
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-03-18T14:37:51+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

And here's another nearly 6,000 new file names!

It is getting increasingly difficult to get the remaining file names but slowly and steadily I am getting to 100%! 
Right now, the rate of named files is at 91.14%, with 34,186 file names missing.

Most of the missing file names (some 28k files) are animation files, and I plan to parse the .mph files to get the remaining file names.
[filenames-found7.zip](https://xentaxbackup.github.io/file/5210_filenames-found7.zip)
## Post #128
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2012-03-19T14:14:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

SWTOR Fan , i love your work ...
but could you upload a hashes_filename.txt instead a filesnames_found, i cannot merged the dictonnary with your file, it's crash
thx
## Post #129
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-03-19T17:03:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from CZW
>
> SWTOR Fan , i love your work ...
but could you upload a hashes_filename.txt instead a filesnames_found, i cannot merged the dictonnary with your file, it's crash
thxSure, here's a new hash list for EasyMYP: [http://www.sendspace.com/file/updvtx](http://www.sendspace.com/file/updvtx) (9.45 MB)
## Post #130
- Username: Marky
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 30, 2005 4:41 pm
- Post datetime: 2012-03-21T17:14:55+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> CZW wrote:SWTOR Fan , i love your work ...
but could you upload a hashes_filename.txt instead a filesnames_found, i cannot merged the dictonnary with your file, it's crash
thxSure, here's a new hash list for EasyMYP: http://www.sendspace.com/file/updvtx (9.45 MB)

Hey, thanks for the tutorial and help. I got started with easymvp and but I am having problems and wonder if you can help....

I followed the tutorial and downloaded mvp 3.6 and use the latest hash in the above post but when I try to extract the texture I am receiving the following error

Is there something I am doing wrong? (using Win 7 x64)

I have tried running it from within the program files (both x86 and x64 program folder) - and made sure I was running as administrator.
[Capture.JPG](https://xentaxbackup.github.io/file/5217_Capture.JPG)
## Post #131
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2012-03-22T07:28:18+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Marky
>
> SWTOR fan wrote:CZW wrote:SWTOR Fan , i love your work ...
but could you upload a hashes_filename.txt instead a filesnames_found, i cannot merged the dictonnary with your file, it's crash
thxSure, here's a new hash list for EasyMYP: http://www.sendspace.com/file/updvtx (9.45 MB) 

Hey, thanks for the tutorial and help. I got started with easymvp and but I am having problems and wonder if you can help....

I followed the tutorial and downloaded mvp 3.6 and use the latest hash in the above post but when I try to extract the texture I am receiving the following error

Is there something I am doing wrong? (using Win 7 x64)

I have tried running it from within the program files (both x86 and x64 program folder) - and made sure I was running as administrator.

Hi Marky

you have this failure, if you try to extract only one specific file, instead, extract the all folder, you will have no problem , as it was explain into the tutorial
## Post #132
- Username: Marky
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 30, 2005 4:41 pm
- Post datetime: 2012-03-22T10:17:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from CZW
>
> Marky wrote:

Hi Marky

you have this failure, if you try to extract only one specific file, instead, extract the all folder, you will have no problem , as it was explain into the tutorial

hi 

Yeah, that worked.... Apologies for not reading the tutorial right. Feel a bit stupid now. THanks for your help!
## Post #133
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2012-03-29T17:14:38+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from flipkick
>
> I found some first detailed information of the item prototypes. The C# source for my extract tool is attached, Hero.dll is required. The mysql stuff is for my personal translation db.

This is my very first C# program, so be gentle 

Example output:
Code: Select allitm.gen.quest_shared.rdps1.chest.heavy.prototype.04x2:
 type: String: "armor.trooper"
 sub type: String: "ipp.class.bh.heroic.rdps1.t4x2.chest"
 bind on pickup
 durability: 120
 id: 16140952217605448722
 title: Xonolite Mesh Chestguard
 slot #0: Id: 16141113719776797593
  - title: Reflex Armoring 12
  - stats: STAT_att_agility: 15
  - stats: STAT_att_endurance: 10
 slot #1: Id: 16141146200986683659
  - title: Reflex Mod 12
  - stats: STAT_att_agility: 20
  - stats: STAT_att_endurance: 10
 slot #2: Id: 16141028933557874887
  - title: Rage Enhancement 12
  - stats: STAT_att_endurance: 10
  - stats: STAT_rtg_attack_power: 15
 slot #3: empty
 slot #4: empty



Nice, isn't it? I'll try to analyze even more item detail information.

I wanted to thank you for your work. However I have a few corrections. I am working on finding and connecting all the right data still, but I am sure about these for now.

What you say is "type:" it is in fact "sound"
What you say is "sub type:" it is in fact "icon"
"bind on pickup" should not be just bind on pickup because it can be other things too
4611686030368870013 is item quality (out of enums of quality)
4611686030368870012 is item level
4611686052121471055 is disassemblecategory
4611686030368870030 is item value
4611686055050031219 is enhancementsubcategory


As I find more I will let you know
## Post #134
- Username: Carsten2011b
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 31, 2011 3:44 am
- Post datetime: 2012-04-05T13:12:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I made an EasyMYP/TOR audio guide using SWTOR fan's tutorials. 

[https://rapidshare.com/files/968436707/ ... _tools.rar](https://rapidshare.com/files/968436707/swtor_extract_tools.rar)
## Post #135
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-04-06T18:06:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

So I finally managed to get the client.gom file and the prototype nodes to load, but I am still working on the bucket files...
Hopefully, it should not take much longer, so people who (like me) want to reinvent the wheel and not use the prefabricated Hero.dll source code will soon find a correct specification for all those files here. 

According to my backups, the last patch that still contained the names and descriptions in the client.gom file is patch #29 (build 2012-01-10), which seems to be 1.0.2d, aka the last version before the 1.1.0 patch.
For those that do not have that patch, you can download that client.gom file here: EDIT: Link removed per new forum policy.

@flipkick, stalja: You are really making your lives hard. With the old client.gom file, you will be able to get the names and descriptions for all the fields whose meaning you are guessing.
In case you do not know how to read the client.gom file, I uploaded all the ids, names and descriptions into the wiki: [click](http://wiki.xentax.com/index.php/SWTOR:_Game_Object_Model).
## Post #136
- Username: strikehawk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 01, 2012 8:14 am
- Post datetime: 2012-04-06T20:43:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

For those interested, here's a C# class to read the .stb files. Many thanks to flipkick and SWTOR Fan for their research work   


 StbReader.zip
C# class to read .stb files (tested with version 1.1) (1.19 KiB) Downloaded 110 times



This class is a port from flipkick's Ruby script with a few corrections.
Major point is a fix in the way of getting the Id of the strings. There's no notion of type or anything, just read the first 8 bytes to get the Id.

I was able to correlate the Ids from the .stb with the ones found in field 4611686102842470023 of the items. I first add troubles to have NodeViewer parse the .tor files. Looks like there was a change in the Hasher. I reused the source code from the hasher of EasyMyp (can be found on Google Code) and fixed hero.dll.
And now NodeViewer works great. I'll upload my fixed version of the hero.dll source code in the next post, should any one need it.
## Post #137
- Username: strikehawk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 01, 2012 8:14 am
- Post datetime: 2012-04-06T20:48:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

And here's the new source code for Hero.dll (I only modified the Hasher).


 Hero.zip
Fixed version of Hero.dll source code (with Hasher from EasyMyp) (206.59 KiB) Downloaded 111 times



All credits go to the guys working on EasyMyp  

I discovered the Wiki tonight, with the list of fields. Amazing
## Post #138
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2012-04-07T19:36:27+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> 
@flipkick, stalja: You are really making your lives hard. With the old client.gom file, you will be able to get the names and descriptions for all the fields whose meaning you are guessing.
In case you do not know how to read the client.gom file, I uploaded all the ids, names and descriptions into the wiki: click.

In the meantime I reread the thread and started using the old version client.gom to get the names. I wonder why they chose to remove the names from the nodes and where do they keep them now? I thank you for the client.gom version you uploaded because I am not sure how old is the one I have.

The upside to all this. I have learning to and actually doing some programming in C# for the past 7 days.

The downside of all this - I have been programming in C# for the past 7 days.
## Post #139
- Username: Crixus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 10, 2012 3:52 am
- Post datetime: 2012-04-09T20:01:35+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Ive gotten EasyMYP working and can view the .tor files...I have also followed the instructions for getting the known file names to show...

I'm looking to do a very specific thing...I would like to replace the Consular project animation with just about any other instant animation, like a saber throw or Shock.  I understand this would be client only and would only show on my client, if at all.  I was hoping I could locate the project animation in the archive, and a replacement, like saber throw or shock, then copy, rename and replace project with saber throw or just about anything else...

Any ideas on how to do this or if this is even feasible?  I would be very appreciative for any help.

Thanks

EDIT:  I thought I found the archive where the project animation is kept... swtor_main_anim_humanoid_bmns_1.tor

In that archive there are the animation files: fp_force_project_01.jba and fp_force_project_02.jba

There are also a number of other fp entries (guessing fp = force powers).  So I tried extracting a single file,  fp_2h_elect_instant_right_1.jba, which I am guessing is the Shock animation.  I also tried extracting the  fp_force_push_1.jba file.  Both files extracted, in an uncompressed format.  Then I tried to simply replace the fp_force_project_01.jba with either one of them using the "Replace selected..." option.  Then new stats on the fp_force_project_01.jba file showed that it had indeed been changed, based on size, but was uncompressed.  

When I tried to run the game, several of the models were missing, but when I used the project skill, the animation was unchanged...So I must be in the wrong place...I will keep looking.
## Post #140
- Username: zoktar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 14, 2012 5:43 pm
- Post datetime: 2012-04-14T09:47:04+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Sorry if this is a noobish question, but is it currently possible to replace certain sound effects with empty ones?, im looking to mute all the user interface sound effects, they are driving me nuts.
## Post #141
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-04-21T07:31:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Crixus
>
> I'm looking to do a very specific thing...I would like to replace the Consular project animation with just about any other instant animation, like a saber throw or Shock.  I understand this would be client only and would only show on my client, if at all.  I was hoping I could locate the project animation in the archive, and a replacement, like saber throw or shock, then copy, rename and replace project with saber throw or just about anything else...

Any ideas on how to do this or if this is even feasible?  I would be very appreciative for any help.I stand by my opinion that I do not recommend changing the game files as this can get you banned if you play on the official servers. However, from what I heard it looks like the game does not check whether the game archives are changed, so it is rather safe to do it at the moment.
The safest way to replace a file is to edit the .tor archives directly with a hex reader. If you never used a hex reader or do not know about the format of game archives, this will be difficult, and I will not help with things like that which run contrary to the intentions of the developers.

> Reply from zoktar
>
> Sorry if this is a noobish question, but is it currently possible to replace certain sound effects with empty ones?, im looking to mute all the user interface sound effects, they are driving me nuts.I believe in your case it will be easier to just go to the game menu and deactivate the sound effects. Especially, since this is not against the game rules and much easier than trying to modify the game files.

----------------------------------------------------------------------------------------------------------------------------------------------------------

I am happy to announce that I have solved the biggest remaining mystery in file names! 
I have confirmed that the AMX files (beginning with 41 4D 58 20), which are something like an index of the .jba animations, actually do have the extension .amx. Most .amx files occur in pairs with .mph files, and the AMX files have the same path like the MPH files but have ".mph.amx" at the end of the path.
This means that I immediately was able to find out many more new file names!

In addition to that, I finally sat down to add the new file names from the 1.2 update.
In total, I have discovered nearly 15,000 new files! Unfortunately, the 1.2 update has added 10,000 new files so the discovery is not as big as I had hoped and there are still 30,000 files remaining.
Current progress is at: 92.26% (366,835 of 397,605 file names known)
[filenames-found8.zip](https://xentaxbackup.github.io/file/5343_filenames-found8.zip)
## Post #142
- Username: the1domo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Apr 13, 2012 4:15 pm
- Post datetime: 2012-05-01T00:23:08+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

[http://emulatornexus.com/swtor/Swtor_items.zip](http://emulatornexus.com/swtor/Swtor_items.zip)
[http://emulatornexus.com/swtor/Swtor_Quest.zip](http://emulatornexus.com/swtor/Swtor_Quest.zip)

tool v0.2


and new generated output

```
Quest Name: Quality Assurance
Quest NodeId: 16141134660316643495
Quest Id: 149412
------------------------------------------------------------
Item INFO
    +IsBonus: False
    +BonusShareable: False
    +Branches: System.Collections.Generic.List`1[GomLib.Models.QuestBranch]
    +CanAbandon: True
    +Category: NarShaddaa
    +CategoryId: 2466269005611273
    +Classes: System.Collections.Generic.List`1[GomLib.Models.ClassSpec]
    +Difficulty: Normal
    +Fqn: qst.location.nar_shaddaa.bronze.imperial.qualityassurance
    +Icon: cdx.locations.nar_shaddaa.network_access
    +IsClassQuest: False
    +IsHidden: False
    +IsRepeatable: False
    +Items: 
    +RequiredLevel: 17
    +XpLevel: 23
------------------------------------------------------------



------------------------------------------------------------
Quest Name: Crackdown at Club Ufora
Quest NodeId: 16141164521999183495
Quest Id: 168843
------------------------------------------------------------
Item INFO
    +IsBonus: True
    +BonusShareable: False
    +Branches: System.Collections.Generic.List`1[GomLib.Models.QuestBranch]
    +CanAbandon: False
    +Category: NarShaddaa
    +CategoryId: 2466269005611273
    +Classes: System.Collections.Generic.List`1[GomLib.Models.ClassSpec]
    +Difficulty: Normal
    +Fqn: qst.location.nar_shaddaa.bonus.single.crackdownatclubulfora
    +Icon: cdx.locations.nar_shaddaa.red_light_sector
    +IsClassQuest: False
    +IsHidden: False
    +IsRepeatable: False
    +Items: 
    +RequiredLevel: 0
    +XpLevel: 21
------------------------------------------------------------



------------------------------------------------------------
Quest Name: Honor and Offense
Quest NodeId: 16140965438769962996
Quest Id: 170133
------------------------------------------------------------
Item INFO
    +IsBonus: False
    +BonusShareable: False
    +Branches: System.Collections.Generic.List`1[GomLib.Models.QuestBranch]
    +CanAbandon: True
    +Category: Companion
    +CategoryId: 2466269005611288
    +Classes: System.Collections.Generic.List`1[GomLib.Models.ClassSpec]
    +Difficulty: NoExp
    +Fqn: qst.companion.republic.jedi_wizard.qyzen_fess.conversations.personalunhappy
    +Icon: cdx.persons.consular.qyzen_fess
    +IsClassQuest: False
    +IsHidden: False
    +IsRepeatable: False
    +Items: 
    +RequiredLevel: 0
    +XpLevel: 0
------------------------------------------------------------



------------------------------------------------------------
Quest Name: Grathan Assault
Quest NodeId: 16140975433343939496
Quest Id: 456955
------------------------------------------------------------
Item INFO
    +IsBonus: False
    +BonusShareable: False
    +Branches: System.Collections.Generic.List`1[GomLib.Models.QuestBranch]
    +CanAbandon: False
    +Category: DromundKaas
    +CategoryId: 2466269005611278
    +Classes: System.Collections.Generic.List`1[GomLib.Models.ClassSpec]
    +Difficulty: VeryHard
    +Fqn: qst.location.dromund_kaas.bonus.staged.grathan_assault_reward
    +Icon: cdx.location.dromund_kaas.grathan_estate
    +IsClassQuest: False
    +IsHidden: False
    +IsRepeatable: False
    +Items: 
    +RequiredLevel: 1
    +XpLevel: 13
------------------------------------------------------------

```
## Post #143
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-05-01T19:51:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I was getting desperate in trying to find a connection between various file names and took a look at the global.dep file. At a size of 3.70 MB, I was hoping that it may contain some information on the audio files or something, but no such luck. 
Anyway, now that I put in the effort to analyze the file, I will just go ahead and publish the file format specification in case anyone is interested in it.

global.dep file format specification
The global.dep file can be found in the archive swtor_main_global_1.tor and has the path /resources/global.dep.
It contains a list of all the .mph, .gr2, .mat and .tex files along with the files that are referenced by these files. The files are ordered alphabetically.
.mph files reference .jba files, .gr2 files reference .mat files, .mat files reference .dds files, and .tex files reference .tiny.dds files.
All of these references can be found in the individual .mph, .gr2 and .tex files as well. I am assuming that the global.dep file is used by the game to create a list of all files that need to be preloaded when entering the world. However, the global.dep file does not have to be read in order to parse the other files.

Note that the order of the primary and secondary hashes, as well as the order of the individual bytes in the hash fields may be reversed, depending on how you store the file hashes.
If you try to read a hash and it does not match up to a file name, try reverting the fields until you get a match.

> Reply from global.dep specification
>
> 
uint32: always 01 00 00 00 → possibly version number (1.0)
uint32: unknown, related to length
uint32: number of entries (as of patch 1.2.1, there are 79,730 entries)
uint32: unknown, related to length
uint32: number of entries, identical to first number of entries

LOOP (for each entry) {
--- 4 bytes: secondary hash of main file
--- 4 bytes: primary hash of main file
--- uint16: number of dependencies
--- LOOP (for each dependency) {
--- --- 4 bytes: secondary hash of dependent file
--- --- 4 bytes: primary hash of dependent file
--- } END LOOP
} END LOOP
And here's a screenshot of how the global.dep file will look like once parsed:
[](http://imgur.com/1YNEc)

Edit: Minor error corrected.
## Post #144
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-05-01T20:29:43+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I found out a few more file names; the current status is at:
96.058% (381,942 out of 397,616 file names found, with 15,674 file names missing) 

Unfortunately, I lost track of which new files were added, so I will just publish the whole hashes_filename.txt file for use with EasyMYP.
I have added some remaining files from the 1.2 patch, as well as many animations files and .wem audio files.

Download here: [filenames-found9.zip](http://www.sendspace.com/file/edb9jh) (10.50 MB)

@Mods: I believe that file names do not violate the new site rules; if you see this differently, feel free to delete my post and I will not publish file names again.
## Post #145
- Username: OroMatoko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 27, 2012 4:58 pm
- Post datetime: 2012-05-03T04:52:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> I found out a few more file names; the current status is at:
96.058% (381,942 out of 397,616 file names found, with 15,674 file names missing) 

Unfortunately, I lost track of which new files were added, so I will just publish the whole hashes_filename.txt file for use with EasyMYP.
I have added some remaining files from the 1.2 patch, as well as many animations files and .wem audio files.

Download here: filenames-found9.zip (10.50 MB)

@Mods: I believe that file names do not violate the new site rules; if you see this differently, feel free to delete my post and I will not publish file names again.

Didn't seem to add any new names to my MYP list when I did full test? =(
## Post #146
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2012-05-03T19:51:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

There is something new happening with the filename hashes. Maybe they changed the path of some of the icons or something, but I can;t figure out what is happening and I am hoping some of you guys can. The following icon

/resources/gfx/icons/ipp.class.inq.pvp.hdps1.t9x1.chest.dds

has hashes 48E4D523 and 222B5055 but there are no files with those hashes. I am certain that "ipp.class.inq.pvp.hdps1.t9x1.chest.dds" is correct because there is a file "ipp.class.inq.pvp.hdps1.t9x1.head.dds" . I am almost 100% certain that the file A0484D2A_089F94465C168011.dds is the one I am looking for.

Have they changed the path to icons perhaps? Has anyone else noticed this?
## Post #147
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-05-09T15:05:28+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from OroMatoko
>
> Didn't seem to add any new names to my MYP list when I did full test? =(
Not really sure what you did but the list I uploaded is correct.
You could test the archives swtor_main_bnk_streamed_*_1.tor since I added the remaining file names from these archives. If there are any unnamed files in there, you are doing something wrong.
However, since this is the full file name list, I recommend deleting your old EasyMYP folder and creating a new one with my hash list; there's no need to keep the old list.

> Reply from stalja
>
> The following icon

/resources/gfx/icons/ipp.class.inq.pvp.hdps1.t9x1.chest.dds

has hashes 48E4D523 and 222B5055 but there are no files with those hashes.
There must be something wrong with your hashes because I get the hashes 089F9446 and 5C168011 for that file name, which correctly translate to the icon you mentioned.
Anyway, thanks for the new file name, I added it to my list and will include it in my next hash list release, along with some other t9x1 icons.
## Post #148
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2012-05-10T14:50:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> 
stalja wrote:The following icon

/resources/gfx/icons/ipp.class.inq.pvp.hdps1.t9x1.chest.dds

has hashes 48E4D523 and 222B5055 but there are no files with those hashes.
There must be something wrong with your hashes because I get the hashes 089F9446 and 5C168011 for that file name, which correctly translate to the icon you mentioned.
Anyway, thanks for the new file name, I added it to my list and will include it in my next hash list release, along with some other t9x1 icons.

Thanks SWTOR Fan for your help. I was using the wrong hasher function. To contribute here's a list of all item icon names.
[item_icons.zip](https://xentaxbackup.github.io/file/5430_item_icons.zip)
## Post #149
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-05-10T15:12:07+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks for the icon file names, stalja!
Unfortunately, they added only 25 file names to my list (I had already included the t9x1 to t9x3 icons before), but given that I did a mass-download of all SW:TOR database sites and parsed all the prototype nodes, it's not surprising that it did not find much more. At least we now have all 1.2 icons complete. 

There are still more than one thousand icons missing and I am assuming that they are from the beta or something and are no longer used, so it will be extremely difficult to get the remaining icon file names, if we can get them at all.

My main concern right now is to get the animation file names (.jba, .mph, .amx) since there is room for some 8,000 new file names in those archives. Everything else will just be filling in the blanks.
## Post #150
- Username: Ferugre
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 20, 2012 10:56 pm
- Post datetime: 2012-05-20T15:05:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

SWTOR fan,

How do you go about finding the new filenames?

Thanks for all of the work!
## Post #151
- Username: Ferugre
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 20, 2012 10:56 pm
- Post datetime: 2012-05-20T16:27:25+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Also, the wiki seems to be down with a 500.
## Post #152
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2012-05-21T18:23:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks for your hard work SWTOR Fan, that newest batch allowed me to get all the music including tracks added in 1.1 and 1.2.
## Post #153
- Username: ategen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 13, 2012 9:40 pm
- Post datetime: 2012-06-27T03:43:11+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have easyMYP and I'm trying to extract item names to go with the items I've found in NodeViewer.  Can anyone point me in the right direction?

Do I need to extract stb files using easyMYP?  Something else?
## Post #154
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2012-07-30T17:58:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thank you for you hard work guys 

Is there any news about how the project goes (1.2 gr2 files, hash list)

*And a question: can some explain how to get filenames, i downloaded the old beta client, and i'd like to get the filenames, because i can convert those gr2 models (and the new ones i can't)

Thanks again

*edit: nevermind, i figured it out  and found a few thousand texture, mostly for the missing armors (the character creation armor, for eg)
## Post #155
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2012-10-09T03:34:34+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

no one has posted here in awhile, but i seen a plugin for noesis was released to open the models, but i have tried easymyp v3.6 on the retail version to extract the .tor files but it doesn't even open them, this is what happens, so has anyone update it yet for the retail version with all the updates since thin? or is there away for me to fix that error
## Post #156
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-10-10T14:46:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Once more, a rather long time went by without me posting anything, but rest assured that I still like the game and I will continue working on it whenever I have some free time.

Among other things, I added the new filenames from the 1.4 patch to the hashlist.
I got my program to a stage where most of the file names are added automatically. E.g., I open a model and the program automatically adds the file name for the material file and the textures to the list.
Or it reads a area.dat file and adds all assets from the map.
There still is some manual work involved but it gives me more time to work on file analysis instead of guessing a seemingly endless list of unknown file names.
There are a few remaining .gr2 files from Asation, once I have those added, I'll upload a current hashes_filename.txt (currently appr. 95% of file names known).

Other than that, I have done some analysis on the SpeedTree files (.spt), FaceFX files (only .fxe, NOT .fxa yet), the area.dat files and the Wwise soundbank files (.bnk). It's not really enough to post a specification yet. If you really are interested in a specification, feel free to ask me to publish it. Otherwise, I will just continue with my file analysis and will post the complete specifications sooner or later.
## Post #157
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2012-10-10T21:38:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> Once more, a rather long time went by without me posting anything, but rest assured that I still like the game and I will continue working on it whenever I have some free time.

Among other things, I added the new filenames from the 1.4 patch to the hashlist.
I got my program to a stage where most of the file names are added automatically. E.g., I open a model and the program automatically adds the file name for the material file and the textures to the list.
Or it reads a area.dat file and adds all assets from the map.
There still is some manual work involved but it gives me more time to work on file analysis instead of guessing a seemingly endless list of unknown file names.
There are a few remaining .gr2 files from Asation, once I have those added, I'll upload a current hashes_filename.txt (currently appr. 95% of file names known).

Other than that, I have done some analysis on the SpeedTree files (.spt), FaceFX files (only .fxe, NOT .fxa yet), the area.dat files and the Wwise soundbank files (.bnk). It's not really enough to post a specification yet. If you really are interested in a specification, feel free to ask me to publish it. Otherwise, I will just continue with my file analysis and will post the complete specifications sooner or later.
well awesome i can't wait i've been waiting forever to get models out of this game, i was able to at one point in the beta but harddrive crashed and i never could get that version back
## Post #158
- Username: Gregthegen
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 12, 2012 5:26 am
- Post datetime: 2012-10-11T21:59:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Looking forward to the hashlist!
## Post #159
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-12-15T19:04:00+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I know I took my time, but I finally want to release a new filename list!
Unfortunately, even though I have added many file names from 1.6, the list is still far from complete. Nevertheless, I decided to just release it instead of pushing it for another week.
Current status: 95.65% of file names known
Found: 392908 / 410758 (17850 file names missing)

Download here: [filenames-found10.zip](http://www.sendspace.com/file/j8d64p) (7.05 MB)

With the added knowledge of file format analysis and class hierarchies I gained this year, I am now rewriting major portions of my code.
In the process of this, I am discovering a few errors and new information in the file formats, so I will update my format specifications on the wiki concurrently.
## Post #160
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2012-12-16T02:59:27+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> I know I took my time, but I finally want to release a new filename list!
Unfortunately, even though I have added many file names from 1.6, the list is still far from complete. Nevertheless, I decided to just release it instead of pushing it for another week.
Current status: 95.65% of file names known
Found: 392908 / 410758 (17850 file names missing)

Download here: filenames-found10.zip (7.05 MB)

With the added knowledge of file format analysis and class hierarchies I gained this year, I am now rewriting major portions of my code.
In the process of this, I am discovering a few errors and new information in the file formats, so I will update my format specifications on the wiki concurrently.

do you happen to have a new link for easymyp 3.6 or higher cause when i try to load your file there with easymyp 3.6 it just says easymyp has stopped working, but anyways thanks for all your work on this it is much appreciated
## Post #161
- Username: levrivers
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Dec 15, 2012 3:01 am
- Post datetime: 2012-12-16T17:12:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from JakeGreen
>
> SWTOR fan wrote:I know I took my time, but I finally want to release a new filename list!
Unfortunately, even though I have added many file names from 1.6, the list is still far from complete. Nevertheless, I decided to just release it instead of pushing it for another week.
Current status: 95.65% of file names known
Found: 392908 / 410758 (17850 file names missing)

Download here: filenames-found10.zip (7.05 MB)

With the added knowledge of file format analysis and class hierarchies I gained this year, I am now rewriting major portions of my code.
In the process of this, I am discovering a few errors and new information in the file formats, so I will update my format specifications on the wiki concurrently.

do you happen to have a new link for easymyp 3.6 or higher cause when i try to load your file there with easymyp 3.6 it just says easymyp has stopped working, but anyways thanks for all your work on this it is much appreciated

Yeah the previous hashlist worked like a charm on the swtor tools download of EasyMYP, but this new one for some reason makes it crash. I'm confuzzled as to the cause.

But what you've done is really astounding swtorFan, it really is. Just make sure you realize there are some of us out there that really appreciate the amazing lengths you've gone to, in order for us to access the files
## Post #162
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2012-12-23T00:19:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Since apparently my post was deleted, I'll just repost the link to the correct release (I forgot to sort the hashes). EasyMYP v3.6 is included.

[filenames-found-10b.zip](http://www.sendspace.com/file/p5150c) (12.05 MB)
## Post #163
- Username: levrivers
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Dec 15, 2012 3:01 am
- Post datetime: 2012-12-25T19:07:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Works like a charm now, fan. Thanks!
## Post #164
- Username: Ferugre
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 20, 2012 10:56 pm
- Post datetime: 2013-01-10T15:06:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Has anyone had any luck finding the references to strings from a Node?  I'm looking at conversation nodes with Node Viewer and just don't see any string Definition ID's.
## Post #165
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2013-02-01T16:35:51+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Does anyone have a link to the TOR EasyMYP? Older versions crash when loading and the links dont work for the TOR version :/

EDIT: Ignore that, realised that a few posts above had the version I needed... but I get a error that someone a few posts up had D: (Unhandled Exception)
## Post #166
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2013-02-09T10:46:54+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Does anyone know a way around the Unhandled Exception error?
## Post #167
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-02-10T16:17:30+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

So Makeb hit the PTR last week and ain't it a thing of beauty? 


Here are the file names from swtor_test_main_area_makeb_1.tor to get you started: [http://pastebin.com/HMSbEngu](http://pastebin.com/HMSbEngu)

There have been guys like Eszi and Kamii who recently grabbed a little more attention than they liked:
[http://www.reddit.com/r/swtor/comments/ ... abilities/](http://www.reddit.com/r/swtor/comments/17xgb1/data_mined_17_and_lvl_55_abilities/)
[http://redeclipse.eu/viewtopic.php?f=24&t=871](http://redeclipse.eu/viewtopic.php?f=24&t=871) 
From what I can tell they just used EasyMYP and NodeViewer (without giving credit ) so I would not rate their achievement too high. I guess it's nice to see that there are still people datamining the files besides me.
But posting it on the official forums and getting permabanned for it is about as dumb as shooting oneself in the foot... 

Anyways, looking forward to the expansion!
## Post #168
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2013-02-19T23:52:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Is there a tool to get modified files back into the archives?
I'd really love to mod the interior of my ship!
## Post #169
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-02-20T07:53:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from surix
>
> Is there a tool to get modified files back into the archives?
I'd really love to mod the interior of my ship!There have been people who were able to edit the archives manually with varying degrees of success, but there is no finished tool to do that.
Since this is a MMO, editing the game files is against the TOS and I do not offer any help for that.
## Post #170
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2013-02-20T13:07:02+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from TRDaz
>
> Does anyone have a link to the TOR EasyMYP? Older versions crash when loading and the links dont work for the TOR version :/

EDIT: Ignore that, realised that a few posts above had the version I needed... but I get a error that someone a few posts up had D: (Unhandled Exception)
Any help? I cant get past the Unhandled Exception, seems to work for everyone else, but it doesnt for me.
## Post #171
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-02-20T15:46:44+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Well, I did not code EasyMYP and I have not been using it for over a year, so I am not interested in fixing anything related to EasyMYP. Either you could try reaching the original developer of the tool, or find someone else from the forum to take a look at it, or code your own extractor based on the specifications me and other users have posted.
Good luck!
## Post #172
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2013-02-20T17:48:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Where could I contact the original developer? 
Or is there another way to get the files from the .tor packages?
I dont know anything about coding so thats out of the picture xD
## Post #173
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2013-02-20T19:10:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> surix wrote:Is there a tool to get modified files back into the archives?
I'd really love to mod the interior of my ship!There have been people who were able to edit the archives manually with varying degrees of success, but there is no finished tool to do that.
Since this is a MMO, editing the game files is against the TOS and I do not offer any help for that.

Thanks swtor fan.
That is lame that they consider modifying graphic data as modifying the game client, its not like you could cheat without modifying the actual executables. 
I suppose there also might be the problem that as soon as you login with your new files the patcher will be like "these files don't hash, ill update them."  You'd probably have to inject them after the patcher finishes, then hope their anti hacking method doesnt thinking your trying to bot or something.

I'm really disappointed with my ship though, it doesn't even have a restroom, or a comfortable lounge, or a library, and has some random dude who I don't know carbon froze in the hold.
## Post #174
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2013-03-04T17:22:33+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

hi,

any of you guys have some information about the ".tor" files specification (especially how the names are stored)?

I'm interested to write a program, just to figure out filenames. EasyMyp is a fantastic tool, and everyone is great who works on guessing the filenames, but, but, but, there have to be an easy way than guessing the filenames...   1+1=2, logic dictates that, if you know the starting value and the result you can figure out the method? Or bioware refused the laws of nature?
## Post #175
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-03-04T17:52:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Vindis
>
> hi,

any of you guys have some information about the ".tor" files specification (especially how the names are stored)?

I'm interested to write a program, just to figure out filenames. EasyMyp is a fantastic tool, and everyone is great who works on guessing the filenames, but, but, but, there have to be an easy way than guessing the filenames...   1+1=2, logic dictates that, if you know the starting value and the result you can figure out the method? Or bioware refused the laws of nature?As written by Rick on page 4 on this thread, SWTOR uses the "Jenkins Lookup 3" algorithm to determine the hash for a file name. For each file, the .tor archives store the two hashes (primary + secondary) generated by that function.

It seems to me like you never heard of hash functions. Unless you know the exact file name, you have to test all possible combinations, which can quickly take multiple years, if not centuries.
If you still don't believe me, think of the Digit sum. It is the simplest example of a hash function that cannot be reversed, because e.g. 8 is the digit sum of 17, 35, 62, 80, 800, etc.

Fortunately, many files (e.g. the .mat and the .xml files) contain those file names, so with a little bit of work one can get the file names that way. Also, since Bioware had included the full file names in the early beta versions, we had a good starting point for a lot of file names. Everything that is left now is just filling in the blanks.
## Post #176
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2013-03-04T18:36:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> 
As written by Rick on page 4 on this thread, SWTOR uses the "Jenkins Lookup 3" algorithm to determine the hash for a file name. For each file, the .tor archives store the two hashes (primary + secondary) generated by that function.

It seems to me like you never heard of hash functions. Unless you know the exact file name, you have to test all possible combinations, which can quickly take multiple years, if not centuries.
If you still don't believe me, think of the Digit sum. It is the simplest example of a hash function that cannot be reversed, because e.g. 8 is the digit sum of 17, 35, 62, 80, 800, etc.

Fortunately, many files (e.g. the .mat and the .xml files) contain those file names, so with a little bit of work one can get the file names that way. Also, since Bioware had included the full file names in the early beta versions, we had a good starting point for a lot of file names. Everything that is left now is just filling in the blanks.

Well, i cannot say i have phD in Hashes  Now that i've read the wiki it's clear, that easymyp is the best tool to figure it out, yet. (I thought, you can just simply reverse the hash and you get the filename)

Isn't nodeviewer parse somehow, because that tiny part i read, seems look for exact name...
## Post #177
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-03-04T18:53:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

What you see in Node Viewer is a another type of file system contained inside the .bkt and .node files. For those files, the names are in fact given inside the files. This is why you can also find the new names from 2.0 in there, even though the programmer did not know about those names when he wrote the program.

However, all other files are only stored with their hashes.
## Post #178
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2013-03-11T01:06:43+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I found nearly 8000 new filename, i'll upload it if u guys don't mind.

Grab it here:[http://rapidshare.com/files/797895651/found.zip](http://rapidshare.com/files/797895651/found.zip)

I can't translate it to percentage, because it seems everybody have different file number  I have 414230
## Post #179
- Username: Tribalizer
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 04, 2012 11:26 pm
- Post datetime: 2013-03-11T11:03:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Vindis
>
> I found nearly 8000 new filename, i'll upload it if u guys don't mind.

Grab it here:http://rapidshare.com/files/797895651/found.zip

I can't translate it to percentage, because it seems everybody have different file number  I have 414230

Getting a "Download not available Download permission denied by uploader. (0b67c2f5)" when I go to download it.
## Post #180
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2013-03-11T12:01:37+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Tribalizer
>
> Vindis wrote:I found nearly 8000 new filename, i'll upload it if u guys don't mind.

Grab it here:http://rapidshare.com/files/797895651/found.zip

I can't translate it to percentage, because it seems everybody have different file number  I have 414230

Getting a "Download not available Download permission denied by uploader. (0b67c2f5)" when I go to download it.

Fix'd [http://rapidshare.com/files/797895651/found.zip](http://rapidshare.com/files/797895651/found.zip) (i hope)
## Post #181
- Username: Tribalizer
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 04, 2012 11:26 pm
- Post datetime: 2013-03-11T13:14:07+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Vindis
>
> Fix'd http://rapidshare.com/files/797895651/found.zip (i hope)

Yep, fixed it.
## Post #182
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-03-11T16:11:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thank you very much for posting that list, Vindis! Getting the file names is a very arduous task, and working together speeds it up a lot.
Your list added 5,329 file names for me, so I suppose I got some file names myself already, but nevertheless good job! 

There are many reasons why we have a different number of files. For example, if you have all three languages installed (English, German, French), you will of course have much more file names than if you just use the English files. Also, since the launcher patches the languages separately, make sure that you have all three languages patched.
Then, there are the "metadata.bin" and "ft.sig" files, which unlike other file names occur multiple times. My programs counts those as multiple file names, even though they theoretically should only be counted as two file names. This may result in a difference of something like 200 file names.
And of course, I only count the file names that are still used by the game. I have a few thousand file names still left over from the beta in case they should one day return, but I currently do not count them as file names.
Also, I did not include the main_gfx_1.tor file names, which contains mostly UI textures.

That being said, this is the current progress after I included your list. Both the live and the PTS client patched up to the latest version, with the German, English and French languages installed:
1.7.1: 98.002% = 406,184 / 414,465 (8,281 file names missing)
Beta 2.0: 96.346% = 429,444 / 445,732 (16,288 file names missing)

Most of the remaining file names originate from the animation and GFX archives. With better understanding of those files, it is easier to automatically get those file names. Nevertheless, getting the file names is mostly guesswork, and I would not set my hopes too high to get 100% progress, but 99.9%.

After I have merged Vindis' and my list, here you can download the most up-to-date list: [http://www.sendspace.com/file/cbmgvt](http://www.sendspace.com/file/cbmgvt)
This also includes the progress split up by the individual archives. I hope that this time you can use the hashes_filename.txt file with EasyMYP, since I am not entirely sure which format that file needs to be in.
## Post #183
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2013-03-12T09:00:05+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I didn't thought getting the filnames this exhausting, spending literally hours/days to compile a list that gives you just a few filenames... Now I appreciate what you guys did more   

I have only en-us client, so basically i have around 380k file, which means 97.5% completion, but i always merge your list, and that's add the additional 20k 

As I saw most of the missing files (from the gfx)tied to the cartel market, but i didn't find any useful info about them yet.

edit: with your list i have 98% 405997/414282 and have all the prototypes! (i wrote a simple program to list numbers from 16140000000000000000 to 1614999999999999999 and append directory/filename to it just to get those fricking prototypes  glad i don't have to use it)
## Post #184
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2013-03-13T16:41:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I've made a simple tool that might help discover new filenames (because there's a lots of file, what you can find in multiple directories).

The program use two file "c:\dirlist.txt" and "c:\filelist.txt", the output file is "output.txt", it's read both file and append filenames to the dirlist, so your dirlist have to look like

"/resources/anim/creature/acklay/
/resources/anim/creature/acklaydroid/"

and the filelist

"ad_body_yaw.jba
ad_cb_body_pitch.jba"

the output will be

/resources/anim/creature/acklay/ad_body_yaw.jba
/resources/anim/creature/acklay/ad_cb_body_pitch.jba
/resources/anim/creature/acklaydroid/ad_body_yaw.jba
/resources/anim/creature/acklaydroid/ad_cb_body_pitch.jba

then you can use the output in easymyp. This way i found nearly 3000 new animation file, but it works with any other dir/filenames.
I know it's not a big thing, but it saved me hours 

so here it is [http://rapidshare.com/files/2926264269/read.zip](http://rapidshare.com/files/2926264269/read.zip)

And here's a hashlist with nearly 4000 new filenames (mostly icons, and animations). I'm focusing for the PTS now, because it can go to live in any "minute", but i think you can merge it to live.

[http://rapidshare.com/files/2053843329/hashes_pts.zip](http://rapidshare.com/files/2053843329/hashes_pts.zip)
## Post #185
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2013-03-26T03:43:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

does anyone have a working link for easymyp 3.6? or tormyp?
## Post #186
- Username: sezerix
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 06, 2012 7:28 am
- Post datetime: 2013-05-30T01:00:27+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

HI new to the forums and this area. big fan im trying to find the npc's like the imperials, and moff uniforms for a project im doing if any one could point me in the right direction or something I would be greatly appreciated.I have everything set up even removing line 156. any help would be appreciated
## Post #187
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2013-05-30T03:27:46+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

You'll need to browse through the *.tor files pertaining to the various bodyparts like swtor_main_art_dynamic_chest_1.tor, swtor_main_art_dynamic_hand_1.tor etc to find all the pieces, then combine the models in your favorite 3d software to form a complete set of gear.


> Reply from luke9511
>
> does anyone have a working link for easymyp 3.6? or tormyp?
[EasyMYP_v3.6-Spec.rar](http://www.mediafire.com/download/d5qc92jwa2adad6/EasyMYP_v3.6-Spec.rar) (SWTOR build)
## Post #188
- Username: sezerix
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 06, 2012 7:28 am
- Post datetime: 2013-05-30T03:47:10+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Well that's gona take alot of what about npc's ? like mandalorian npc's? and imp or are they all part's? There must be a spot for the npc's or are they all made from the dynamic clothes?
## Post #189
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2013-05-31T16:08:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from AceWell
>
> You'll need to browse through the *.tor files pertaining to the various bodyparts like swtor_main_art_dynamic_chest_1.tor, swtor_main_art_dynamic_hand_1.tor etc to find all the pieces, then combine the models in your favorite 3d software to form a complete set of gear.

luke9511 wrote:does anyone have a working link for easymyp 3.6? or tormyp?
EasyMYP_v3.6-Spec.rar (SWTOR build)
thank you very much and i do apologize for not seeing this sooner and thanking you sooner!
## Post #190
- Username: levrivers
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Dec 15, 2012 3:01 am
- Post datetime: 2013-06-05T14:25:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from sezerix
>
> Well that's gona take alot of what about npc's ? like mandalorian npc's? and imp or are they all part's? There must be a spot for the npc's or are they all made from the dynamic clothes?

Yup they're all parts. The dev's design tool most likely includes a drop down list creator. They select the race of the character they're making, then select an armour set. The armour set itself isnt a model, its just a piece of code that itself selects all the individual pieces of 3d meshes as a group. The reason all the meshes are individual is so that it greatly increases their customization abilities to make things look different and new in NPCs.
## Post #191
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2013-06-17T20:51:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

is there a updated file list?
## Post #192
- Username: TheArk
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 03, 2013 12:12 am
- Post datetime: 2013-06-25T00:51:29+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Yes, I am curious if anyone has an updated list for this as well.
## Post #193
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2013-06-25T18:18:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Around five thousand new filename:

[http://rapidshare.com/files/211000940/h ... lename.zip](http://rapidshare.com/files/211000940/hashes_filename.zip)

not too much, but tbh, it's a windmill fight, without any point. Not too much interest around Swtor, and BW/EA doesn't help community either.
## Post #194
- Username: Alianin
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 28, 2012 12:07 am
- Post datetime: 2013-07-02T18:53:22+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I would love to help with this, but I'm new and have no idea where to start. Can anyone point me to some tutorials or guides? I have a basic programming understanding and realize this all might be a bit over my head, but I figured it is worth a shot since there's demand but few people working on it. (Thank you SWTOR fan and Vindis for your work thus-far!)
## Post #195
- Username: TheArk
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 03, 2013 12:12 am
- Post datetime: 2013-08-14T00:31:09+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey,

Just checking in to see if there are any more updates for the hash list since there have been several game updates. All the past ones have been very helpful and I want to thank everyone involved in this project.
## Post #196
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-08-31T13:22:05+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Sorry for the long wait. I am still analyzing the game, but I never bothered to check back on the forums. 

I did not dedicate too much time with finding new file names, but my program found some automatically. I'll just go ahead and share with you my most up-to-date hashes_filename.txt. It includes Vindis 6,000 new file names (thanks, Vindis!), so you can easily use it as the most current file name list.
Unfortunately, I have yet to find the folder name for the Cartel Market and Collections interface images. The folder name is sorted between "loadingscreen" and "placeables", so I am fairly confident that it is something like "mtx", but so far I have not been able to get a match. 

Anyway, download the file names here:
Total progress: 95.85%
Found: 436,044 / 454,897 (18,853 file names missing)
[http://www.sendspace.com/file/4ma0rh](http://www.sendspace.com/file/4ma0rh) (12.22 MB)


So all this time, I have been working on the GOM, and I finally have a database of items, NPCs, quests etc. to work with. This makes it much easier to lookup information from the game, since I longer have to lookup three different files, but my program does that for me.

Also, I did major progress on the SCPT files. The most interesting revelation certainly was a small developer comment regarding raid difficulties from the early red beta assets: 8-man normal, 8-man heroic, 24-man normal and 24-man heroic.
It looks like they originally planned to have 8-man and 24-man raids, instead of the 8-man and 16-man raids we have now. I assume they reduced that due to the engine's limitation. In any case, that explains why the maximum group size is 24 and not 16. I always wondered about that. 

Currently, I am once more working on the areas. Specifically, I am trying to figure out how the game maps the player position to a map page.
One of my biggest dreams right now is to create a 3D viewer for not just individual .gr2 files, but whole areas to walk inside and take screenshots. Unfortunately, I have yet to find the heightmap file. Without it, there's not much point trying to display a planet.

Apart from that, there's still work to be done regarding the ability/effect nodes, the hydra scripts, the animation system and the GUIXML files. I'm getting there. 


By the way, on Reddit a user named [swtor_miner](http://www.reddit.com/user/swtor_miner) has recently started posting about his datamining progress. I am not too impressed, since I have not yet seen him figure out anything I could not figure out, but it's always great to see that I am not the only one working on the files. Maybe I am just jealous that he receives so many responses.
## Post #197
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-08-31T13:40:00+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Alianin
>
> I would love to help with this, but I'm new and have no idea where to start. Can anyone point me to some tutorials or guides? I have a basic programming understanding and realize this all might be a bit over my head, but I figured it is worth a shot since there's demand but few people working on it. (Thank you SWTOR fan and Vindis for your work thus-far!)
Are you still interested?

The best way to start with reverse engineering is learn all the major datatypes (uint32, uint64, uint16, single float, ...), and how to recognize them. Knowledge of hexadecimal numbers (0123456789ABCDEF) is a must. See [The Definitive Guide To Exploring File Formats](http://forum.xentax.com/viewtopic.php?t=968).
If you can recognize the meaning of the following bytes, you should be good to go:
01 00 00 00 -> 1 in uint32
2C 01 00 00 -> 300 in uint32
FF FF FF FF -> -1 in int32
10 00 -> 16 in uint16
00 00 80 3F -> +1 in single float
04 74 65 73 74 -> String "test", prefixed by length=4

Then, google "file streams" + your favorite programming language, and read up on how you can read a binary file when you know what datatypes it consists of.

Also, you need to get a Hex Editor (like HxD or 010 Editor) so that you can open binary files.
Open a few .tor files in it, and compare then to the [file format specification](https://code.google.com/p/easymyp/source/browse/trunk/EasyMYP/MYPInfo.txt).
Now you just need to be good at Maths and logical thinking. If you have those skills, you should be able to work your way from there.
## Post #198
- Username: cire992
- Rank: beginner
- Number of posts: 31
- Joined date: Sun May 02, 2010 11:39 am
- Post datetime: 2013-08-31T17:47:05+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks for the hard work SWTOR Fan. Just want to let you know that I really appreciate what you're doing, and your work isn't going unnoticed.

I'm having some trouble with your latest hashlist, when I place it in the hash folder and load up EasyMYP, it crashes. Going to double-check a few things.
## Post #199
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-09-01T03:18:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Yeah my bad, I forgot to remove duplicate file names (metadata.bin and ft.sig). This file will work: [http://www.sendspace.com/file/u57pbu](http://www.sendspace.com/file/u57pbu)
## Post #200
- Username: jpreston84
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Sep 01, 2013 2:05 pm
- Post datetime: 2013-09-01T15:59:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Greetings all!

Great work so far -- especially in terms of the file lists. That's a lot of work, and it's much appreciated.

I've been working on deciphering SWTOR's mapping data myself, but admittedly have had minimal success. Have you had any success regarding mapping information?

Who am I? I'm a web dev (mostly just a reasonably high-end LAMP guy) with about 12 years experience. I'm no-one special, and have no formal programming education. I don't presume to know much/anything about this stuff, but I can take some guesses, and I'm decent with data analysis, file parsing, and data manipulation.

Here's what I have so far:
 - Composited map images (.dds) files.
 - A very-slightly-better understanding of some parts of the .stb spec than posted previously (which I'll post eventually, of course -- I'm still working on a few pieces).
 - A rough guess at the positional coordinates from the .dat files.
 - Some very rough understanding of how the GUIDs work.

Here's what I'm looking for help with right now:
 - Confirmation of how the coordinate system works for plotting elements from the .dat onto the map.
 - Information on how to correlate .dat entries (presumably via GUIDs) with information about entity type, string titles, etc.
 - Information on correlating string titles to each map.
 - Information on where the size/coordinates of each of the map sections is stored. (i.e. How do I know that map X goes from -234,1000 to 101,1500, and what range of Z coordinates is covered by it?)

I have a lot more that I'm planning to work on as well, but I'd like to start with this.

Can anyone offer assistance? What information is known about how elements are placed on the map?
## Post #201
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-09-02T18:25:27+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi there!

The .stb specification I posted earlier is no longer up to date, but I never bothered to update it.
Here is the current format:

String buckets specification (.stb file format)
01 00 00: header bytes
uint32: number of strings
FOR EACH (string) {
--- uint64: string id
--- byte: type1
--- byte: type2
--- float: unknown, always 00 00 80 3F = 1.0, possibly related to how quickly the text is read
--- uint32: string length
--- uint32: string offset
--- uint32: repetition of string length
} END FOR

To get a specific string, go to the given offset and read the given number of bytes. Then convert these bytes into a string.

Type1 can be:
- 65: main string
- 70: alternate female string (e.g. huntress instead of hunter). Only used by German and French strings, where it is more common that male and female professions are named differently.
- 80: for conversations, the main summary when you can choose one of the three responses
- 81: for conversations, the alternate female summary

Type2 seems to be related to localization. If type2==0, then the string should not be translated, e.g. because it is just a placeholder and may be changed later when the content goes live.

locTextRetrieverMap
All of the main nodes (abilities, items, NPCs, ...) have the locTextRetrieverMap field (4611686102842470023), which is a LookupList IndexedBy(Integer) Of(Class strLocalizedTextRetriever).

The index is a integer that describes the type of string. I have not found a complete list that tells which index stands for which string, so I am assuming that we need to figure out the meanings ourselves.
For example, here are two indices:
15685385242400905286 = item name
2806211896052149513 = item description
Note that I am working with unsigned integers. Depending on how you read the GOM, the first index may show up as -2761358831308646330 for you.

The class strLocalizedTextRetriever (4611686093000569991) contains the following fields:
strLocalizedTextRetrieverStringID (4611686093000569992): This is set to the string id in the .stb file
strLocalizedTextRetrieverBucket (4611686093000569993): This is the file name of the .stb file, where the dot is used as a directory separator. For example, "str.itm" -> "/resources/en-us/str/itm.stb"
I am ignoring the other fields.

Areas

In SWTOR, each planet, each flashpoint, each operation, each player starship etc. is its own area. Basically, everytime you see the loading screen, you are travelling to a new area.
Each area can have one or multiple instances. New instances are automatically opened, and empty instances are closed, depending on the number of players in the instances.
Each Player Character is positioned inside exactly one instance of one area.

A list of all areas can be found inside the "mapAreasDataProto" node (1614095165023949372).
The areaID can be found inside the "mapAreasDataAreaId" field (4611686052789731191).
Also, the "mapAreasDataDisplayNameId" field (4611686052789731199) contains the string id for the "str.sys.worldmap" bucket, which can be used to lookup the area display name. The area display name is only shown in the /who finder, and not on the minimap or world map.

If you have the area id, you can lookup the Area Specification (area.dat file).
The area.dat files can be found under /resources/world/areas/[area id]/area.dat. The area.dat contains a list of assets (e.g. 3D models, spawners), paths (for NPC patrols and taxis) and room names.

Rooms
If you have an area id and a room name, you can lookup the Room Specification, which can be found under /resources/world/areas/[area id]/[room name].dat.
It is important to remember that the rooms have nothing to do with the world map or minimap. The rooms are only used by the game to group certain asset instances together, so that the engine only has to render the current surroundings and not the whole area.
Each asset instance has multiple properties, including the position and rotation, given as Vector3.

Map Pages
In the game, when you open the World Map, you always see a certain map page.
The list of map pages can be found inside the "world.areas.[area id].mapdata" node.
The most important fields are:
mapName: name of the map page, which can be used to lookup the map page texture under /resources/world/areas/[area id]/[mapName]_r.dds
mapPageMinCoord: The coordinates of the top left corner of the texture as Vector3
mapPageMaxCoord: The coordinates of the top bottom right of the texture as Vector3
locTextRetrieverMap: Can be used to lookup the Display Name of the Map Page, which is shown above the minimap and as the window title for the World Map
mapUseParentMinimaps: If true, the minimap will show the minimap texture of the parent map page. Otherwise, this Map Page has its own minimap, which can be found under multiple textures of the format /resources/world/areas/[area id]/minimaps/[mapName]_00_00_r.dds, where 00_00 is the top left corner, and continues like 01_00, ... 0n_00, 00_01, 01_01, ...

When you have not yet discovered a map, it will be full of honeycombs (hexagons). Each hexagon stands for one Fow field (Fow = fog of war). Multiple Fow fields are group into a Fow group. 
The "world.areas.[area id].mapdata" node also contains a list of those Fow groups. Each Fow group has its own display name, which is displayed along with the display name of the Map Page

For example, you can stay inside the same map page, but may move to a different Fow group.
The Map Page "Tatooine: Dune Sea" has multiple Fow groups, e.g. the Sarlacc pit or the Republic outpost. When you are standing at those places, you still see the full map of the Dune Sea, but the map will say something like "Tatooine - Dune Sea - Sarlacc Pit" or "Tatooine - Dune Sea - Thorazan Outpost"

With the area id, you can lookup the map notes, which can be found under /resources/world/areas/[area id]/mapnotes.not.
The mapnotes.not file only contains the position of a map note, and in which map pages it is visible. Use the FQN reference to lookup the mpn node that contains information about the display name of the map note and the type.

Coordinate system
For the coordinates that are shown in game, one unit represents one meter, for example the point (1000, 0, 0) would be 1,000 meters away from the origin.
However, the game itself always uses decameters for coordinates, so the above position is stored as a (100, 0, 0) Vector3 in the files. In other words, always multiply a coordinate by 10 if you want to display a coordinate to a user.

It is important to realize that the Y and Z coordinates are swapped. In the files, a position is given as (X, Y, Z), while the game shows the coordinates as (X, Z, Y) to the players.
There are two ways to show your current position in game:
When you hover with your mouse over the minimap in the game, the tooltip shows: "Current player position: X: "+round(player.x*10)+", Y: "+round(player.z*10)+", Z: "+round(player.y*10)
When you open the World Map, it will display your position in the top left corner. There is a small bug when you open the World Map. As soon as you open it, the position will in fact show the X and Y coordinates. Only when you move your character, the position will be updated and correctly show the X and Z coordinates. This has led to major confusion on Torhead, where users would report the X, Y position from the World Map in comments.

I hope you understood the coordinate system now. Here are some more examples:
The origin (0, 0, 0) is usually somewhere in the center of the map.
The top left corner of the world map of Tatooine is (-414, 0, -433), the bottom right corner is (403, 0, 385). The size of Tatooine is 8,177 x 8,177 meters.

What I have yet to figure out is how the game determines which Map Page and Fow Group the player is currently in. Also, I am not sure how the game knows which Map Page is the root Map Page for a planet.
## Post #202
- Username: ulukai
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 23, 2009 2:59 am
- Post datetime: 2013-09-02T19:31:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I can't get easymyp working !

Got the 3.6 and the last filenames that i put on hash folder.

But when I click on open archive and select the tor file, i get a error message !

Any idea ?

[http://img5.imageshack.us/img5/1137/10mm.jpg](http://img5.imageshack.us/img5/1137/10mm.jpg)
## Post #203
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-09-02T19:54:55+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ulukai
>
> I can't get easymyp working !

Got the 3.6 and the last filenames that i put on hash folder.

But when I click on open archive and select the tor file, i get a error message !

Any idea ?

http://img5.imageshack.us/img5/1137/10mm.jpg
It looks like EasyMYP tried to convert a string into an int32 but failed because the string was in an unknown format.
Does EasyMYP work on the other archives, or do they show the same error message? And could you please copy & paste the first few lines of the details? They are cut off in the screenshot, but they show the line number in the source code, which will help with debugging.

By the way, I recommend that you close the game before running EasyMYP. While I am not sure whether the game is reading the list of processes, it is safer to not do that.
## Post #204
- Username: ulukai
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 23, 2009 2:59 am
- Post datetime: 2013-09-02T19:59:50+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Got the error for every files and I tried when the game was off too.

Here : 

System.FormatException: Le format de la chaîne d'entrée est incorrect.
   à System.Number.StringToNumber(String str, NumberStyles options, NumberBuffer& number, NumberFormatInfo info, Boolean parseDecimal)
   à System.Number.ParseInt32(String s, NumberStyles style, NumberFormatInfo info)
   à System.Int32.Parse(String s, IFormatProvider provider)
   à System.Diagnostics.PerformanceCounterLib.GetStringTable(Boolean isHelp)
   à System.Diagnostics.PerformanceCounterLib.get_NameTable()
   à System.Diagnostics.PerformanceCounterLib.get_CategoryTable()
   à System.Diagnostics.PerformanceCounterLib.CounterExists(String category, String counter, Boolean& categoryExists)
   à System.Diagnostics.PerformanceCounterLib.CounterExists(String machine, String category, String counter)
   à System.Diagnostics.PerformanceCounter.Initialize()
   à System.Diagnostics.PerformanceCounter..ctor(String categoryName, String counterName, String instanceName, Boolean readOnly)
   à System.Diagnostics.PerformanceCounter..ctor(String categoryName, String counterName, String instanceName)
   à MYPHandler.MYPHandler..ctor(String filename, del_FileTableEventHandler eventHandler_FileTable, del_FileEventHandler eventHandler_Extraction, HashDictionary hashDic) dans C:\Code\Personal\SWTOR ripper\EasyMYP\MYPHandler\MYPHandler_extraction.cs:ligne 154
   à EasyMYP.MainWindow.OpenArchive(String filename, Boolean block) dans C:\Code\Personal\SWTOR ripper\EasyMYP\EasyMYP\MainWindow.cs:ligne 182
   à EasyMYP.MainWindow.openArchiveToolStripMenuItem_Click(Object sender, EventArgs e) dans C:\Code\Personal\SWTOR ripper\EasyMYP\EasyMYP\MainWindow.cs:ligne 160
   à System.Windows.Forms.ToolStripItem.RaiseEvent(Object key, EventArgs e)
   à System.Windows.Forms.ToolStripMenuItem.OnClick(EventArgs e)
   à System.Windows.Forms.ToolStripItem.HandleClick(EventArgs e)
   à System.Windows.Forms.ToolStripItem.HandleMouseUp(MouseEventArgs e)
   à System.Windows.Forms.ToolStripItem.FireEventInteractive(EventArgs e, ToolStripItemEventType met)
   à System.Windows.Forms.ToolStripItem.FireEvent(EventArgs e, ToolStripItemEventType met)
   à System.Windows.Forms.ToolStrip.OnMouseUp(MouseEventArgs mea)
   à System.Windows.Forms.ToolStripDropDown.OnMouseUp(MouseEventArgs mea)
   à System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
   à System.Windows.Forms.Control.WndProc(Message& m)
   à System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   à System.Windows.Forms.ToolStrip.WndProc(Message& m)
   à System.Windows.Forms.ToolStripDropDown.WndProc(Message& m)
   à System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   à System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   à System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)
## Post #205
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-09-02T20:45:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hm, it seems like this line in the code is producing the error:

```
ramCounter = New PerformanceCounter("Process", "Private Bytes", Process.GetCurrentProcess().ProcessName)
```

The same error is discussed here: [http://stackoverflow.com/questions/3121 ... at-c-sharp](http://stackoverflow.com/questions/3121688/performance-counter-input-string-was-not-in-a-correct-format-c-sharp) and [http://social.msdn.microsoft.com/Forums ... ncecounter](http://social.msdn.microsoft.com/Forums/vstudio/en-US/9d687de5-a791-473b-8f82-ef64c723f572/problem-creating-performancecounter)
It seems like EasyMYP is working fine, but there is an error with your computer / Windows.
Do you have another computer? If so, try running EasyMYP on there. Other than that, I cannot help you, sorry.
## Post #206
- Username: jpreston84
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Sep 01, 2013 2:05 pm
- Post datetime: 2013-09-02T22:45:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

SWTOR fan,

First, let me say thank you for posting all that additional data. It's very helpful. Please keep up the great work!

I had already figured out the coordinate system, and the X, Z, Y representation by looking through the .dat files and comparing them with in-game representations. However, it's very helpful to have confirmation, and the additional data you provided on this is extremely useful.

I have a few comments, and questions. I'll present them below, and allow you to update format definitions, specs, and provide answers as you see fit. This way, there is a single source putting out information, rather than two competing sources.


My questions/comments are as follows...

1) In the STB format, there are a few differences I've noted from your documentation...
 - Type1 (byte position 08) can also be 0x41 or 0x50. In many files (for instance, /resources/en-us/str/cnv/location/balmorra/bronze/colicoid_expulsion/captain_augatta.stb), even-numbered entries always receive 0x50, while odd-numbered entries always receive 0x41. This would seem to be irrespective of whether an entry is zero-length, etc. Other files have only 0x41 in this location.
 - For Type2 (byte position 09), I've observed values 0x00, 0x01, 0x04, 0x05, 0x0D in the en-us files. Any idea on what the differences are here? I somehow suspect this is a bitfield, though I don't know what its purpose is.
 - It might be worth noting for newcomers that all values appear to be stored in Little Endian format.
2) Regarding the map/location data, I'll apologize in advance for asking what is probably a very stupid question. I glanced back through this thread for answers, and apparently have missed seeing them, so I'll just ask -- where/what are the "nodes" you speak of? Specifically, you say "The list of map pages can be found inside the 'world.areas.[area id].mapdata' node." What file would I find this inside, and what program would I use to read it (or what format data do we have about its composition)?
3) I've found reference to a number of .spn_c files (inside area.dat files, etc). How might I go about adding these to the hash list, or doing whatever else needs to be done so I can find and intelligently start to look at these files? (I'm a bit new to using EasyMYP.)

Again, thanks for your efforts thus far!
## Post #207
- Username: ulukai
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 23, 2009 2:59 am
- Post datetime: 2013-09-02T22:45:48+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Ok thx you anyway !
## Post #208
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-09-03T00:09:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

@jpreston84:
I definitely recommend you to develop your own application for reading the .tor files, instead of using EasyMYP. EasyMYP is a little buggy, and extracting all files is wasting disk space.
I have written a program that has a TreeView control on the left side, where the program displays all of the files, and when I select a file, the program reads the file directly from the .tor archive, analyses it and displays it in the center panel.

In Type1, 0x41=65 is the main string and 0x50=80 is the summary for conversations where you can choose one of multiple options. I already wrote that above, you may have missed it. 

You are 100% spot on about Type2 being a bitflag field. I never realized that before, thanks for the tip!
But to be honest, I have been working with the files for nearly two years, and ignored this field all the time. I am pretty confident that it has to do with localization, since te strings for the upcoming Rakghoul event have type2=0. The 1 bit probably stands for "do translate this string", but I have no idea what the other bits could stand for.

And yeah, SWTOR uses little-endian format for pretty much every file. One of the vendor-specific files (Bink/Speedtree/FaceFX) uses big-endian, but I don't remember which one it was and you probably won't need to read that file anyway.

So far, you have been working with just the files. That will give you the text files, the 3D models, the areas and much more, but you are still missing the GOM. The GOM is characteristic to HeroEngine, and you can find it in the folder /resources/systemgenerated/.
The GOM connects all of the other files together. It contains information like:
- a list of all items, along with names, icons, descriptions
- a list of all NPCs, along with names, level, their appearance
- a list of all conversations, that show in which order the .stb files are read
In order to read the game files, it is best to start with the GOM, because the GOM references all other files.
The GOM is quite complicated, but fortunately there is a tool that can read it, the NodeViewer. It looks like the original site where it was uploaded no longer exists, so I reuploaded it for you: [http://www.sendspace.com/file/1gq4ls](http://www.sendspace.com/file/1gq4ls)
You may need to edit the NodeViewer.exe.config file so that it points to the folder where you have installed the game.

Once you open the NodeViewer, all your question should be answered.
Here is a screenshot of the world.areas.4611686018437650020.mapdata node, which contains the Map Pages for Tatooine:


The HeroEngine wiki is a great resource when analyzing SWTOR, but it is also not easy to understand. Maybe it helps you: [http://hewiki.heroengine.com/wiki/GOM](http://hewiki.heroengine.com/wiki/GOM)
Also, I posted a list of all the fields of the GOM to the Xentax wiki: [http://wiki.xentax.com/index.php/SWTOR: ... ject_Model](http://wiki.xentax.com/index.php/SWTOR:_Game_Object_Model)
## Post #209
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-09-03T00:20:59+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

After further consideration, I now believe that type1 is also a bitflag. So type1 and type2 can be read together as uint16, and then be processed as a bitflag field.

```
0x46 = 0100 0110
0x50 = 0101 0000
0x51 = 0101 0001

```

The 0x40 bit is always set, and the 0x10 bit controls whether the string is a summary or not.
But for the moment, I'll leave my program to read Type1 as byte and go with 65, 70, 80 and 81, since that is easier than reading the bitflags.
## Post #210
- Username: jpreston84
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Sep 01, 2013 2:05 pm
- Post datetime: 2013-09-03T01:53:27+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

SWTOR fan,

Sorry I missed that you were giving decimal values rather than hex values for those fields. I should have checked that first.

After further looking, I am still not sure what to make of the many files that have Type1 as an alternating 0x41/0x50...I'll have to look more into it in the future.

For now, I want to concentrate more on the map data, particularly regarding determining the coordinates of the maps and points on the maps.

I've opened NodeViewer, and found the map data as noted in your previous post. However, now I'm left with another problem -- how to get the data out. I don't want to manually copy out all the data for each map, as there are hundreds of different maps, and I'd like to be able to update my data set when a patch is released. Thus, I have another question -- has anyone written a tool which can parse the client.gom file, and output all its data into a set of text files (or something else I can parse)?

I could write a tool myself, if a decent GOM file spec is available somewhere, though I'll be limited to PHP, since I don't know any other languages. In absence of a tool that can bulk-export all the data in client.gom, this might be the approach I have to take.

Thoughts?
## Post #211
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-09-03T03:40:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

The NodeViewer.exe was written in .NET, therefore you can easily get the original source code in a disassembler. Download here: [viewtopic.php?p=63821#p63821](http://forum.xentax.com/viewtopic.php?p=63821#p63821)
The main code is in the Hero.dll; the NodeViewer.exe is just doing the UI and handing over file contents to the Hero.dll.

But I don't know about any other public tool to read the GOM. Good luck trying to port that to PHP! It took me a while to understand the serialization. Maybe you can even include the original Hero.dll into PHP, that would save you a lot of work.

Unfortunately, I don't have enough time to document the DOM serialization, so I hope you can understand it just from the source code.
The NodeViewer was developed sometime during the late beta. I believe it originated from a user at BetaCake.net, but I do not know who really is behind it. Whoever did it receives a lot of credit for figuring the DOM out!
## Post #212
- Username: jpreston84
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Sep 01, 2013 2:05 pm
- Post datetime: 2013-09-03T04:28:22+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Ugh. Not only do I not know anything .NET (so its syntax, file setup, etc is foreign enough to me that I don't much know where to begin), but there are also apparently no comments in that source either, which means I'm probably out of luck.

Anyone out there willing to lend a hand dumping out the contents of client.gom to something that's actually usable? I don't really care whether the solution is PHP, C++/C#, .NET or anything else. A PHP class, or a CLI tool that just takes a client.gom input and outputs a bunch of text and other files with appropriate data, would be ideal to me!

(I'll keep working at it, but I must stress that it's highly unlikely I'll succeed at this.)
## Post #213
- Username: jpreston84
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Sep 01, 2013 2:05 pm
- Post datetime: 2013-09-03T21:37:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Well, I've gotten further than I'd thought. I've gotten through much of the client.gom, and into the ZLib sections in the bucket files, and decoded the ZLib compression. While I'm sure these are the key/value pairs, the actual format of these sections still escapes me.
## Post #214
- Username: TheArk
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 03, 2013 12:12 am
- Post datetime: 2013-09-04T05:56:47+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks for posting all this stuff SWTOR and Vindis and whoever else has been involvt.


Was just wondering TORFAN if with the last filename list you posted there was any knowledge of where the Texture files were, we found all the new Czerka Stuff model wise but no luck on textures?
## Post #215
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2013-09-04T13:01:09+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from TheArk
>
>  ..we found all the new Czerka Stuff model wise but no luck on textures
The models and their textures are in swtor_main_art_zed_1.tor, but most of the textures still don't have names yet.
## Post #216
- Username: TheArk
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 03, 2013 12:12 am
- Post datetime: 2013-09-04T19:55:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Alright, so then what's the process for giving them names, if there's any way I can help speed up the process I will.
## Post #217
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2013-09-04T20:37:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I don't know, the only ones finding file names are SWTOR fan, Rick and Vindis. 

Vindis released a tool that helps find names but i can't get it to work.
[viewtopic.php?p=83851#p83851](http://forum.xentax.com/viewtopic.php?p=83851#p83851)

This is what Rick says about the filenames:
[viewtopic.php?p=63422#p63422](http://forum.xentax.com/viewtopic.php?p=63422#p63422)
[http://www.burtleburtle.net/bob/c/lookup3.c](http://www.burtleburtle.net/bob/c/lookup3.c)

I'm sure a lot of people would contribute to finding names if those guys released their tools.
## Post #218
- Username: jpreston84
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Sep 01, 2013 2:05 pm
- Post datetime: 2013-09-06T18:47:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

FYI -- Despite not being able to use the .NET source code that was made available (except for the list of data types, half of which I'd already identified), by using a hex editor and looking at data in NodeViewer, I've deciphered 95% or so of the Bucket file spec. I'll try to post that as soon as I can solve a little detail about the ZLib-compressed sections. (This is all somewhat changed from the data that's been posted here previously.)

SWTOR Fan,

Can you possibly enlighten me on where the labels are pulling from in the ZLib-compressed sections? In cases where the label for an entry is something like CC XX XX XX XX XX or CF XX XX XX XX XX XX XX XX, I am assuming these bytes represent an address, perhaps an offset, but I can't figure out the specifics of what it's an offset to. Can you help with that? Just a pointer in the right direction is all I think I need.

My one other issue at present is that the ZLib-compressed sections have a varying number of header bits in some cases, and I haven't been able to decipher the purpose of these bits. Any help would be appreciated.
## Post #219
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2013-09-11T06:23:38+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Here's my latest hashlist: [http://www.sendspace.com/file/nedoar](http://www.sendspace.com/file/nedoar)
It has several thousand new files, including most of the files in the main_gfx_1.tor that's not in the Assets directory.

You guys might want to load up the *.gfx files extracted from the main_gfx_1.tor in a hex editor.
1. Change the header from CFX to CWS
2. Change the extension to .swf
3. Run them through a flash decompiler like trillix.

For those that don't know, the .gfx files are in Scaleform GFX format. Which is an embedded version of Flash, and you can decompile them with this method. Some very interesting stuff in the SCFF tagged files.

Expect updated versions of EasyMYP and Nodeviewer in the near future. Once I'm sure they don't have any major bugs.

edit: I guess this is the wrong thread for the Noesis plugin now that I think about it. I'll leave it here. But, I posted the information to: [viewtopic.php?f=16&t=9703&p=88035](http://forum.xentax.com/viewtopic.php?f=16&t=9703&p=88035)

> And, I know you guys will like this. Here's an updated version of Vindis's Noesis Plugin that now loads multiple meshes into one model: http://www.sendspace.com/file/1mchxl
>
> 1. Put it in the Noesis/plugins/python directory, and it will allow you to view .gr2 files.
>
> 2. Now put all the .gr2 files you want to view, and their associated textures (just the files ending in _d.dds) into a folder.
>
> 3. Create a file in that directory called model_list.txt, and put all but one of the names of those .gr2 files in that file. (Just the file name, one per line, no /'s)
>
> 4. Load up the one .gr2 you left off the list, and it will reassemble it for you.
>
> 
>
> I've left in/fixed support for the Specular Maps(_s.dds) and Normal Maps(_n.dds), and you can set Noesis to load these by  enabling the loading non-diffuse textures in the Data Viewer. Unfortunately the Normal Maps seem to require tweaked lighting data to function properly, and loading of that data is not implemented yet.
## Post #220
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-09-11T20:26:44+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi swtor_miner, it's nice to finally see you on XeNTaX!
Thank you very much for posting your hashes_filename.txt file! I found a few thousand new file names myself since I last published the hashes_filename.txt file, and will post an update on the current file name progress later.

I spent a lot of time with the BWA Material format recently. It was not too much fun working with the HLSL shader code, but I am happy that I am mostly done with it.

I can now confirm that the 8 unknown bytes for vertices with vertexSize>12 stand for the normals and tangents.
Basically, the values from -1 to +1 are encoded into a byte, so that 0x00 is -1, 0x7F is 0, and 0xFF is +1. You can convert a byte to the float value the following way:
float byteToFloat(byte byteValue) {
return byteValue / 127.5 + 1.0;
}
The eight bytes in the vertices are stored this way:
byte: normal.x
byte: normal.y
byte: normal.z
byte: always -1 or +1
byte: tangent.x
byte: tangent.y
byte: tangent.z
byte: always -1 or +1
Unfortunately, I always get an error when I try to edit the wiki, so I cannot update the .gr2 specification there. 

For the standard materials that just have a DiffuseMap, RotationMap1 and GlossMap, the output color is calculated the following way:
- Use the RGB channels of the DiffuseMap as diffuse color
- Ambient color and emissive color are the same as the diffuse color.
- Use the red channel of the RotationMap1 as opacity
- Use the blue channel of the RotationMap1 as emissive luminance
- Use the green and alpha channel of the RotationMap1 as red and green channel of the bump map.
- Use the RGB channels of the GlossMap as the specular color, and the alpha channel as the shininess.

Also, my program can preview models with AnimatedUV and PaletteMap materials, but it is still looking different from the 3d models in-game.
Here is a preview of the /resources/art/static/area/all_all/item/tech/all_item_tech_city_computer_01.gr2 file with an AnimatedUV material (and yes, the texture is animated, but I cannot take an animated screenshot ):
## Post #221
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-09-12T00:44:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Alright, I calculated the current progress of how many file names we have discovered, based on the current versions of the client.

Retailclient, 2.3.2b:
444,135 / 455,078 files named (97.60%), 10,943 file names missing

PTS, 2013-09-11:
452,313 / 468,471 files named (96.55%), 16,158 file names missing


This looks very promising. We are mostly missing some animation files (.jba/.mph/.amx) and the Cartel Market files (.dds).
I am still looking for the names of the Cartel Market icons, which are stored in the swtor_main_gfx_assets_1.tor archive.
Like I said, all the files are ordered alphabetically, and the Cartel Market icons are placed in between
/resources/gfx/loadingscreen/warzone_voidstar_overlay_text.dds and
/resources/gfx/placeables/galaxy_map/noise_1.swf.
Because of that, I am confident that the folder name starts with "mtx".

Also, I am quite certain that the Cartel Market icon file names can be found in field 0x40000040A41F2780 of the mtxStorefrontInfoPrototype. Some of those file names are:
generic_unlock, lifeday_fireworks_pack_x12, legacy_upsell, interface_upsell_color_match, interface_upsell_legacy_display, class.war.bis.mdps2.t2x2, heavy_chest_bh_rheal_6x1.

In the game, there are five different-sized images shown:
120x120: displayed on the front page as a small size
260x260: displayed in the Collections Interface as a small icon
260x400: displayed on the front page as a 1x3 sized icon
328x160: displayed when browsing through the different categories in the Cartel Market
400x400: displayed on the right side in the Cartel Market, as well as the large icon in the Collections interface

So it seems like there is a certain suffix to the file name to reference the current size of the image, like _a.dds, _b.dds, etc.
I have looked through the SCPT files because they contain the folder names for many other files, but unfortunately I haven't found the folder name for the Cartel Market there, and I do not have much motivation to look through them again.
I guess I will once more try out different variations of /resources/gfx/mtx/generic_unlock_1.dds... 

If anyone encounters an error message that accidentally exposes the file name, or has any idea how a folder name might be called, feel free to tell me.
## Post #222
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2013-09-12T08:35:54+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SWTOR fan
>
> Hi swtor_miner, it's nice to finally see you on XeNTaX!
Thank you very much for posting your hashes_filename.txt file! I found a few thousand new file names myself since I last published the hashes_filename.txt file, and will post an update on the current file name progress later.
Hi SWTOR fan! I've been lurking for a while now, and I very much appreciate your posts.

As, someone not very well versed in the art of 3d modelling the Noesis plugin helped me a lot. Long term, a standalone modelviewer that reads directly from the game files seems like a better option than the Noesis plugin. But, it's functional for now, and I think I'll implement your fixes when I get some time.

I have a few standalone programs for searching extracted output for filenames. Which I'm in the process of updating for animations. I made some progress tonight, but was mainly looking at the latest PTS build. Scanned through it for more file names. Here's my latest hash: [http://www.sendspace.com/file/muqtt2](http://www.sendspace.com/file/muqtt2)

A lot, and I mean a lot of the file names are in xml files, which makes it a breeze to write programs to find them.. I really need to write a program like yours to see how many are left, but that's not high on my priority list.

edit: On a hunch I checked "\resources\gfx\gfx_production\ui_hud.gfx", and it contained the format for the Cartel Market assets: 
```
"/resources/gfx/mtxstore/" + file + "_" + imgWidth +  "x" + imgHeight + ".dds"
```


Which I checked with: "/resources/gfx/mtxstore/lifeday_fireworks_pack_x12_120x120.dds" and it was found! Enjoy!
## Post #223
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-09-14T00:27:18+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Wow, good job on finding the folder name for the MTX icons! Also, thank you very much for your lead about the .gfx files. I never imagined that they would contain so many helpful information. Just from looking through the ActionScript code, I found a lot of answers to things I had wondered about previously.

And finally, I figured out the PaletteMap materials. I can now display NPCs and items from the game with the correct garment hues. 

For example, this is npp.location.flashpoint.shared.mandalorian_raiders.trash.mandalorian_tech_commando. The green and red colors do not come from the diffuse texture, but from the garment hues:


And here is an example of an NPC with visible skin (npp.location.flashpoint.shared.cademimu.flavor.dancer). The red color of the skirt and the yellow headdress and buttons once again come from the garment hues, not the diffuse texture. Note that the white pixels should in fact be transparent; that's just a bug with my 3D viewer.
There are a lot of threads on the official forums regarding revealing clothes items where the companions have gray skin, so it's nice to see that the developers were also having problems working with the skin. 


Now I am only missing hair and eye colors, as well as adding the age/complexion/facepaint textures to the head slot.


The AMI system is so complicated that I do not want to spend too much time explaining it, but here are the most important parts:
The "derived" field in the .mat files explicitly describes the type of texture. The game uses this field to determine which shader should be used for the material.
Most of the normal models (walls, terminals, tables, ...) have "derived" set to "Uber", where the materials are parsed like I wrote in my previous post.
All of the body parts (boot/chest/leg/etc., but not eye/hair/head) have "derived" set to "Garment". The pixel shader for Garment materials then hues the pixel according to the palettes.
If the PaletteMaskMap is black, then the diffuse texture is displayed.
If the PaletteMaskMap is red, then the palette1 color mixed with the PaletteMap texture is displayed.
If the PaletteMaskMap is green, then the palette2 color mixed with the PaletteMap texture is displayed.
If the PaletteMaskMap is blue, then this pixel has a metallic specular color.
The alpha value of the PaletteMaskMap is not used.
Any other colors (cyan, purple etc.) are just combinations of these cases.

palette1 and palette2 are of the format "hue, specular, lightness, contrast" and they default to (0, 0.5, 0, 1).
The ipp and npp nodes usually reference two garment hues (appApperanceSlotHuePrimary, appApperanceSlotHueSecondary). Read the respective garment hue .xml file in /resources/art/dynamic/garmenthue/ and override the palette1/palette2 fields from the .mat file with the new hue/specular/lightness/contrast values from the .xml.
If you are interested in how the palette1/palette2 colors are mixed with the PaletteMap, I'll just upload the original HLSL shader code from the game: [http://pastebin.com/sDRVvBYy](http://pastebin.com/sDRVvBYy) You best start reading the code at the HuePixel() function, which is called by the Garment shader.
See also [http://msdn.microsoft.com/en-us/library ... s.85).aspx](http://msdn.microsoft.com/en-us/library/windows/desktop/bb509638%28v=vs.85%29.aspx) if you are new to shaders.
## Post #224
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2013-09-14T07:57:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Yeah, I've never even attempted anything remotely like 3d modeling/programming. But, I taught myself python. Which is kind of an odd language, and that you have to target a very small subset of the language for Noesis. I've mainly dabbled with c++/c#/java and was a major slacker on learning them. Now that I've got the basics I think I'm going to write a native C# version of it.

Mainly thanks to your posts, and others here. I taught myself to reconstruct some of the progress you've made. I still have to implement the vertexsize>12 normals and tangents, but I don't see that being too hard. I probably could've put together which channels were which by myself, but you really saved me some time. I even assumed, at first, that some of the color channels might be normalized or flipped, but it was really nice that they weren't. So, far I've got emissives and bump maps to work. 



A laundry list of things I need to work on include making the glossmap work properly, loading bones/skeletons, animations, mutliUVExtractions, palatte map materials, scrolling UVs, mat/asset xml parsing for gear/npcs.

I've made a little bit of headway on the file names, but most of my free time has been spent playing or working on the modelviewer. It works on a surprising large number of models now, considering it's 12KB of code. [http://www.sendspace.com/file/mjqh3u](http://www.sendspace.com/file/mjqh3u)

If you have a decent hashlist most static models should load from the EasyMYP extracted output. You can put several .gr2 filenames in a "model_list.txt" file. Then open a .gr2 in that folder and it will load the models from "model_list.txt" as well. There are a lot of models that don't work with it right now. But, I think it's a huge improvement over the other one.

I'm downloading the fr/de localizations now to run my filename finder against. With just the English assets, I'm sitting at:

434,458/447,694 files	13,236 missing files	97% filenames found
## Post #225
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-09-18T16:51:59+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Why oh why did they have to put all the space pvp stuff into 2.3.3... 
I was hoping I had at least until 2.4 before I had to deal with that, but no such luck. I also wonder who at Bioware had the stupid idea of not placing those nodes under a nice folder name, but placing them in the main GOM directory instead.

Anyway, I now adjusted my program to automatically rename nodes from the spvp base classes so that they are placed into a separate folder and do not pollute the main directory.

For anyone who wants to do the same, here is a list of all the new spvp base classes that do not have a folder name:
4611686299377594007 - BlasterVisual
4611686299377594016 - BlasterConfig
4611686299409904000 - SCFF Damage FX Package Prototype
4611686299409904002 - Hull Damage FX Tier Prototype
4611686299446374010 - Shield Damage FX Prototype
4611686299499134001 - Damage FX Names Prototype
4611686299618324017 - Barrel Roll Camera Behavior
4611686348326037001 - A free flight component
## Post #226
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2013-09-19T09:24:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Latest Hashlist: [http://www.sendspace.com/file/11zzgt](http://www.sendspace.com/file/11zzgt)

Current Stats for the latest 2.4PTS Build(Including FR/DE Locals, and main_gfx_1.tor):
456,811 of 468,479 Filenames known. 97.5% Completion
11,668 Missing Filenames.

Here's the breakdown of .tor files with incomplete file names:

```
localizations\swtor_de-de_global_1.tor	3847	3890	43	98.90%
localizations\swtor_de-de_zed_1.tor	454	617	163	73.60%
localizations\swtor_fr-fr_global_1.tor	3879	3922	43	98.90%
localizations\swtor_fr-fr_zed_1.tor	470	619	149	75.90%
publictest\retailclient\main_gfx_1.tor	254	282	28	90.10%
swtor_en-us_global_1.tor	4131	4139	8	99.80%
swtor_main_anim_creature_a_1.tor	9490	9888	398	96.00%
swtor_main_anim_creature_b_1.tor	9529	9930	401	96.00%
swtor_main_anim_creature_npc_1.tor	20588	21271	683	96.80%
swtor_main_anim_humanoid_bfab_1.tor	15058	15680	622	96.00%
swtor_main_anim_humanoid_bfns_1.tor	15054	15678	624	96.00%
swtor_main_anim_humanoid_bmaf_1.tor	15061	15782	721	95.40%
swtor_main_anim_humanoid_bmns_1.tor	15361	15890	529	96.70%
swtor_main_anim_misc_1.tor	4089	4222	133	96.80%
swtor_main_area_balmorra_1.tor	1563	1579	16	99.00%
swtor_main_area_belsavis_1.tor	2778	2793	15	99.50%
swtor_main_area_coruscant_1.tor	2159	2161	2	99.90%
swtor_main_area_dromund_kaas_1.tor	1624	1625	1	99.90%
swtor_main_area_epsilon_1.tor	154	161	7	95.70%
swtor_main_area_ilum_1.tor	691	713	22	96.90%
swtor_main_area_makeb_1.tor	3923	3970	47	98.80%
swtor_main_area_misc_1.tor	6461	6662	201	97.00%
swtor_main_area_nar_shaddaa_1.tor	2067	2117	50	97.60%
swtor_main_area_raid_1.tor	444	459	15	96.70%
swtor_main_area_tatooine_1.tor	2646	2648	2	99.90%
swtor_main_area_tython_1.tor	1656	1657	1	99.90%
swtor_main_areadat_epsilon_1.tor	644	786	142	81.90%
swtor_main_art_area_all_item_1.tor	9737	9759	22	99.80%
swtor_main_art_creature_a_1.tor	2471	2485	14	99.40%
swtor_main_art_creature_b_1.tor	1245	1255	10	99.20%
swtor_main_art_creature_npc_1.tor	1938	2006	68	96.60%
swtor_main_art_dynamic_cape_1.tor	6591	6931	340	95.10%
swtor_main_art_dynamic_chest_1.tor	5591	5888	297	95.00%
swtor_main_art_dynamic_chest_tight_1.tor	6311	6897	586	91.50%
swtor_main_art_dynamic_hand_1.tor	18920	19208	288	98.50%
swtor_main_art_dynamic_head_1.tor	24006	24534	528	97.80%
swtor_main_art_dynamic_lower_1.tor	33814	34490	676	98.00%
swtor_main_art_dynamic_mags_1.tor	973	978	5	99.50%
swtor_main_art_fx_1.tor	31376	32820	1444	95.60%
swtor_main_art_misc_1.tor	2484	2593	109	95.80%
swtor_main_art_vehicle_1.tor	2942	2949	7	99.80%
swtor_main_art_weapon_1.tor	5267	5277	10	99.80%
swtor_main_art_zed_1.tor	7313	7611	298	96.10%
swtor_main_bnk_audiodata_1.tor	77	78	1	98.70%
swtor_main_bnk_location_1.tor	60	61	1	98.40%
swtor_main_bnk_streamed_a_1.tor	416	427	11	97.40%
swtor_main_bnk_streamed_b_1.tor	453	474	21	95.60%
swtor_main_bnk_streamed_c_1.tor	292	297	5	98.30%
swtor_main_bnk_voc_1.tor	415	428	13	97.00%
swtor_main_gfx_assets_1.tor	60202	61966	1764	97.20%
swtor_main_systemgenerated_gom_1.tor	889	936	47	95.00%
swtor_main_zed_1.tor	1038	1067	29	97.30%

```


I agree, the space stuff being in the root of the GOM kind of blows.
## Post #227
- Username: jpreston84
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Sep 01, 2013 2:05 pm
- Post datetime: 2013-09-23T22:21:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Okay, so, question to those of you who have been finding a bunch of file names....

1) Can someone give me a basic walkthrough on finding file names, including...
   i) A pointer to the .tor/.myp file spec. I'm assuming one exists, but can't seem to find it (I could just be blind, in which case, you're perfectly entitled to hit me over the head with a blunt object).
   ii) A how-to on the hashing algorithm used to match the filenames.
   iii) If you have it, a program that's better than EasyMYP for working with these files. It doesn't have to be perfect. I'd just really love to not have to write my own program for this right now.

2) Can someone please tell me if you've actually scanned the /resources/word/areas/*/area.dat files for filenames yet? I've been working with area.dat (and related files) a bit, and if you look inside there, in the [ASSETS] section, you'll notice that many of the entries are clearly file names. For instance...

  4611686041729870061=\art\static\area\all_all\arch\imperial\all_arch_imp_space_door_med_closed.gr2

...is a filename which has already been discovered and placed in the file lists (technically stored under the /resources/art path, not just /art) . On the other hand, consider these...

  4611686045449371975=\spn\location\coruscant\taxi\taxi_hub3_poi01_blacksun.spn_c
  4611686045449371977=\spn\location\coruscant\taxi\taxi_hub1_poi02_senate.spn_c
  4611686045449371983=\spn\location\coruscant\taxi\taxi_hub2_poi01_market.spn_c
  4611686045449371985=\spn\location\coruscant\taxi\taxi_hub4_poi01_justicar.spn_c
  4611686045449371987=\spn\location\coruscant\taxi\taxi_hub5_poi01_works.spn_c

...which to my knowledge, are NOT in the file lists so far. These particular files would seem, I guess, to be related to the spawning of taxi droids on the map (and are referenced in the individual room .dat files, with coordinates, etc).

There are over 115K entries in the area.dat files [ASSETS] sections, and so I'm wondering if some of these aren't the ones missing from the file lists. If it seems like this would be relevant, and someone wants to give me next steps for how to identify these files in the archives, or wants to just do the work themselves and provide us with an updated file list, that'd be swell.
## Post #228
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-09-24T02:06:18+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi jpreston84!

You can find the MYP file format on [https://code.google.com/p/easymyp/sourc ... YPInfo.txt](https://code.google.com/p/easymyp/source/browse/trunk/EasyMYP/MYPInfo.txt).

For hashing filenames, I just included the HashCreator.dll and HashDictionary.dll libraries from EasyMYP since that saves you a lot of trouble of dealing with the hash function itself.
If you use .NET, you can copy & paste the following code:

```
myCreator = New nsHashCreator.HashCreator(myDict, nsHasherFunctions.Hasher.HasherType.TOR);

```

to initialize the hasher. Then call the following function to save the primary/secondary hashes for the file name in ph and sh.

```
uint sh;
myCreator.hashFilename("/resources/your_path_here", ph, sh);
```


Sorry, I do not have plans to share any of my tools.


Regarding the area.dat files, those are in fact one of the best sources to get file names. My program is automatically reading and testing them, so rest assured that the hash lists I publish contains those files. (although I may be behind one or two patches)

Back in the beta, the .spn_c files were in fact contained as .xml files under those paths, but they have since been removed. Instead, the game is now reading the spawners by their GOM node.
For example, if a file is given by
\spn\location\coruscant\taxi\taxi_hub3_poi01_blacksun.spn_c
, the game does in fact load the GOM node
spn.location.coruscant.taxi.taxi_hub3_poi01_blacksun

Hope I could answer your questions.
## Post #229
- Username: jpreston84
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Sep 01, 2013 2:05 pm
- Post datetime: 2013-09-24T16:14:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks for the information! Clearly, you folks are way more on top of this stuff than I am. 

As the tools that are available (including your hash lists) are sufficient, I think I'll avoid writing my own for the moment, particularly since, as mentioned, I'm a PHP junkie, which unfortunately means loading Hero.dll would be a problem for me (PHP has no good way to do this).

I have no doubt I'll have more questions later.

Again, thanks for the help so far.
## Post #230
- Username: jpreston84
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Sep 01, 2013 2:05 pm
- Post datetime: 2013-09-26T22:05:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Okay, I've got another question for whoever will still put up with me! 

In the process of parsing the buckets (and client.gom), I'm able to parse only some of the labels, and am missing a few ancillary pieces of data that would be helpful to have. This is a bit long-winded, so please bear with me.

For example, if you consider node "world.areas.4611686018427650020.mapdata". The first node/section inside here has a label of 4611686042955270002, which can be looked up in an old version of client.gom to reveal the proper label of "mapDataContainerMapDataList". The label of the first sub-node in this list is simply the integer 1, which shows identically in NodeViewer. This is a class which contains data about a map page. The first entry in this class is clearly labeled with a value that, once looked up in client.gom, translates to "mapName". However, the following two values (of the Vector3 type) are labeled with 0x04 and 0x01, respectively, where they should be (according to NodeViewer) labeled with entries for "mapPageMinCoord" and "mapPageMaxCoord".

I've double and triple-checked the data in this section by hand, and there are definitely no bytes which I am not accounting for. I believe I'm understanding the format correctly. My current guess is that because we're inside a class structure, the labels of 0x04 and 0x01 are actually referencing something else, which ultimately references to the client.gom entries. However, thus far, I've been unable to determine exactly how this correlation is made. I really could use some help here.

Also, I'm interested to find out how NodeViewer is making the association for what type of class a node is. For example, the definition for the first list (mapDataContainerMapDataList) is as follows:

CF 40 00 00 05 B5 F9 C7 72 07 09 90 90

To my understanding this breaks down as follows:

CF 40 00 00 05 B5 F9 C7 72 - Reference to client.gom entry "mapDataContainerMapDataList"
07 - Data type 0x07 is "List".
09 - The list is a list of classes (because type 0x09 is Class)
90 90 - Number of entries (144) in the list, repeated once.

Note that I have no idea how NodeViewer figures out this is "list of Class mapData". Is it just looking inside the list and seeing what types of classes are there, and using that to generate the type column?

Then the definition for the first contained class follows:

01 1B 14

I understand that as:
01 - Label for this class, apparently just the integer 1.
09 - Not specified, but implicit because the list specifies the data type.
1B - Unknown
14 - Number of entries (20) in this class.

I'm assuming that 1B is how NodeViewer identifies this class as "Class mapData", but I'm not sure HOW that happens.


So, to recap:
 1) When a class member has a label which is not directly a reference a client.gom entry, how do I look up the proper label?
 2) How do I determine what type of class, a given class instance is?
## Post #231
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-09-28T03:52:11+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from jpreston84
>
> For example, if you consider node "world.areas.4611686018427650020.mapdata". The first node/section inside here has a label of 4611686042955270002, which can be looked up in an old version of client.gom to reveal the proper label of "mapDataContainerMapDataList". The label of the first sub-node in this list is simply the integer 1, which shows identically in NodeViewer. This is a class which contains data about a map page. The first entry in this class is clearly labeled with a value that, once looked up in client.gom, translates to "mapName". However, the following two values (of the Vector3 type) are labeled with 0x04 and 0x01, respectively, where they should be (according to NodeViewer) labeled with entries for "mapPageMinCoord" and "mapPageMaxCoord".
It's much easier than you think. To save memory, the game only stores the full id of the first field. For all other fields, it just stores the difference to the previous field. So just create a variable that stores the id of the previous field, and add the number of the current field to get the full id.

In your example:
4611686020073980011 -> 4611686020073980011 = mapName
0x04 -> 4611686020073980011 + 4 = 4611686020073980015 = mapPageMinCoord
0x01 -> 4611686020073980015 + 1 = 4611686020073980016 = mapPageMaxCoord


From my understanding, the nodes from the bucket files just contain information of the form "List of Class". The "List of Class mapData" you're talking about is contained in the client.gom file I believe, but I have never looked too much into that.
There's not much of a point reading the client.gom since the names and descriptions have been removed.
## Post #232
- Username: jpreston84
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Sep 01, 2013 2:05 pm
- Post datetime: 2013-09-28T04:24:28+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Ah yes, I actually figured this out a bit earlier today. Sorry I didn't reply to alert you to that.

I'm still struggling a bit through the top of each section in the bucket files (the data before the label of the first entry in the section), but I am hopeful that I'll figure it out.
## Post #233
- Username: jpreston84
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Sep 01, 2013 2:05 pm
- Post datetime: 2013-10-16T16:59:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Greetings all!

So, I've been working on figuring out a lot of the GOM structure, but have been trying in vain to find certain nodes for several hours.

Consider, for example, a node like npc.location.tatooine.vendor.vendor_army_heavy_h1_g1_emp_poi00_mos_ila . In it, it contains a list of strings, for what I presume are sets of items which it has available for sale. These are as follows:

pkg.vendor.armor.heavy.level_24_25
pkg.vendor.armor.heavy.level_26_27
pkg.vendor.armor.heavy.level_28_29

Unfortunately, these nodes do not exist either within the prototypes or the buckets (as far as I can tell). Now, certain "packages" do exist. For example, pkg.profession_trainer.armstech_base contains a list of what appears to be all of the armstech schematics the vendors usually sell.

I've tried scanning through the GOM for many different things, with no success. Does anyone have an idea where the pkg.vendor.* nodes might have moved to?
## Post #234
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-10-16T17:12:07+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Certain nodes are only contained in the server GOM, not in the client files, and they are requested by the client on a need-to-know basis. The vendor packages are an example of this; you won't find them in the client files.
## Post #235
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2013-11-03T05:50:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

im working on updated my outdated files for swtor model extraction and conversion and when i go to open easymyp it just crashes is there a new version or is the latest hash list just to big for it to handle? im on win 7 x64
## Post #236
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2013-11-05T01:57:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

[My latest Hashlist.](http://www.sendspace.com/file/jrzzba)

I'm showing the following stats including the main_gfx_1.tor, but not the french/german localizations.
451,706 named
458,471 total
6,765 unnamed
98.5% complete

A while back I disassembled the latest EasyMYP and made additions and recompiled it. [You can find a version with my updates here.](http://www.sendspace.com/file/vip4si)

It's got a few nagging bugs, like the about window and potentially a few others in functions I didn't often use. So, I didn't feel a pressing need to fix them. [Here's my disassembled source. If you want to play with it.](http://www.sendspace.com/file/m505q7)

When you do fix it, you can merge the code with the [the original project.](https://code.google.com/p/easymyp/) Or start a new repo for it somewhere. I've included a default .gitignore file if you want to get a git repo going with it.

Right now I'm working on the new GS Expansion data. With it, I'm helping to create a ship calculator for a relatively well known community site. If successful it might just be the first of many projects I'm working on to see the light of day.
## Post #237
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2013-11-17T10:51:18+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks for that update swtor miner! I can finally extract some files 
One problem though, some of the models/textures dont extract, the main example i tried was Darth Malgus, i press extract, no files appear. But Satele's model works fine.. any idea why his model/textures wont extract? I havent tried anymore models yet.

EDIT: After extracting the whole .tor file it seems that Malgus' model is the only one that doesnt extract :/
## Post #238
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2013-11-18T03:34:47+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from TRDaz
>
> Thanks for that update swtor miner! I can finally extract some files 
One problem though, some of the models/textures dont extract, the main example i tried was Darth Malgus, i press extract, no files appear. But Satele's model works fine.. any idea why his model/textures wont extract? I havent tried anymore models yet.

EDIT: After extracting the whole .tor file it seems that Malgus' model is the only one that doesnt extract :/

I'll have to look into that when I get some time.

[Here's an updated version of Nodeviewer for you guys to play with in the mean time.](http://www.sendspace.com/file/qr1dmi)

[And a link to my latest post where I discuss how to datamine some of the Galactic Starfighter information](http://www.reddit.com/r/swtor/comments/1qvc7q/swtormined_deconstructing_galactic_starfighter/)
## Post #239
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2013-11-18T16:13:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thank you, take your time
## Post #240
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2013-11-19T04:06:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I didn't have any trouble extracting the textures for malgus's model.

They were in swtor_main_art_creature_a_1.tor - "\resources\art\dynamic\npc\unique_characters\texture\___psd\"
## Post #241
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2013-11-19T07:42:55+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Well, that's weird... I extracted that whole tor file and got nothing, even extracting the textures/gr2 alone and I still got nothing... maybe I did something wrong? :/

EDIT: Nevermind, re-tested, randomly works now lol. Thanks for checking though
## Post #242
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2013-12-31T15:47:35+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

just thought i would post and say so far everything is working great but like someone else said alot of textures dont get extracted so alot of models are missing sometimes one or two textures or all of them and some models wont load in the noesis viewer it pops up with an error but thats for a different thread
## Post #243
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2014-01-01T09:01:34+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from luke9511
>
> just thought i would post and say so far everything is working great but like someone else said alot of textures dont get extracted so alot of models are missing sometimes one or two textures or all of them and some models wont load in the noesis viewer it pops up with an error but thats for a different thread
[This is something that I'm working on.](http://imgur.com/a/5ta9P) Unfortunately none of my code is quite ready for you guys just yet.

I also discovered (at least haven't seen it posted anywhere) how the game stores the heightmap for areas. In the Room Specification .dat files the heightmap is stored in the .VertexData property as a zlib compressed hex string in one of two encodings.

If it starts with "78 9C" it's a regular zlib stream. If it starts with "1F 8B" it's compressed with gzip encoding. Here's a small piece of the uncompressed data to look at:

```
00000010h: 40 CD CC E2 42 00 D0 44 90 3F 1C C9 84 3F D0 44 ; @ÍÌâB.ÐD?.É„?ÐD
00000020h: 90 3F E3 83 85 3F D0 44 90 3F B2 EA 82 3F D0 44 ; ?ãƒ…?ÐD?²ê‚?ÐD

```


I've been meaning to analyze them, but just haven't had the opportunity.
## Post #244
- Username: swtor enthusiast
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 31, 2013 5:23 am
- Post datetime: 2014-01-07T06:20:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi all,

I apologize in advance for the rather novice questions, I tried to do a bit of searching through this thread and several others but may have missed the answers to these rather basic questions.

First, when I load up Noesis with the SWTOR plugin that swtor miner posted, I can view extracted .gr2 models, but they are without textures (all white). I've tried placing the texture files in the same folder as the .dds model I'm trying to view, but cannot seem to get it to display with the texture. Is there something I need to be doing to assign a texture to the .gr2 model before viewing/exporting?

Lastly, I'm not having much luck locating the icon images used for vehicles, weapons, and so on in the game. Do you know offhand which directory I might find those located in?

Thank you very much for your time and sorry for the beginner-level questions.
## Post #245
- Username: Alianin
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 28, 2012 12:07 am
- Post datetime: 2014-01-07T17:22:43+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor enthusiast
>
> Lastly, I'm not having much luck locating the icon images used for vehicles, weapons, and so on in the game. Do you know offhand which directory I might find those located in?

Look at the 6th post down by SWTOR Fan on page 9 on this thread and there's a list and description of the tor archive files. You're looking for swtor_main_gfx_1.tor which has all the GUI icons.
## Post #246
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2014-01-08T04:28:25+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor enthusiast
>
> First, when I load up Noesis with the SWTOR plugin that swtor miner posted, I can view extracted .gr2 models, but they are without textures (all white). I've tried placing the texture files in the same folder as the .dds model I'm trying to view, but cannot seem to get it to display with the texture. Is there something I need to be doing to assign a texture to the .gr2 model before viewing/exporting?

First off, here's [an updated test version of the Noesis .gr2 Plugin.](http://www.sendspace.com/file/cm5gtn) You'll want to rename/delete the other plugin if you decide to try this one. This is one contains A LOT of test code, and some ugly hacks till features are fully implemented. This version also has the debug log enabled, so that might be annoying. I might port it to a native plugin, but that's pretty far down the to do list.

If a model's textures aren't loading look for the "MaterialName:" lines in the debug log. These are what the model textures should be named. So, that can be a way to fix some models. The proper way to load materials/textures would be to look up the dependencies of the specified .gr2 model in the global.dep file, or one of the many index.xml files. Then you can then read in the textures and other settings for that material, and apply that to the model.

Given their fragmented nature in the game files, loading a .gr2 file properly without context is very difficult. So, I'll probably have to create a fork of my personal SWTOR tool to package the dependencies for each one to ensure they view properly.

That might be a while, as I've decided to play more SWTOR. (GSF is addictive) Well until they release a new PTS build, and that should be sometime this week or next.
## Post #247
- Username: jpreston84
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Sep 01, 2013 2:05 pm
- Post datetime: 2014-01-29T20:10:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey all! I know I've been silent for a while -- I've been pretty busy, playing SWTOR (finally leveled a char to 55, heh), dealing with life, and working on SWTOR dev stuff as well.

In any case, I've been deciphering the conversation nodes, and inside each actual conversation, one or more of the nodes can have the list of affection recipients (your companions) and the list of how much affection they can receive from your choices. These numbers correlate to the tables found in qstrewardsaffectionData, but I'm having a problem converting the labels to match what NodeViewer does (which is how I found the correlation -- poking around until I saw the same numbers somewhere).

So, for example, in NodeViewer, when I view the node qstrewardsaffectionData, there are several data tables (listed under qstRewardsPerLevelData), labeled as follows in NodeViewer:

-530180456931428419
-4783781478483316801
-4591313547948601546
-4560859075783160276
-1761015921176014301
-1279836118038687359

These correlate to (based on the numbers in each of their data tables)...

high loss
high gain
medium loss
medium gain
small gain
small loss

However, when I extract the data using my own software, the labels come out as...

13144940616778123197
13662962595226234815
13855430525760950070
13885884997926391340
16685728152533537315
17166907955670864257

I have checked and verified these manually. For instance, the hex for the first label is 0xCFB66C35D898AA07BD. As best I can understand, the CF indicates a positively signed integer with a representation 8 bytes in length, with the next 8-bytes representing (as big endian) the value, which is 13144940616778123197. This means of converting numbers works throughout the nodes in many places, including the label for qstRewardsPerLevelData, which is stored only a few bytes before the labels I'm having trouble with.

All that said, I do believe NodeViewer's interpretation is correct, because its labels match the values of conversation affection gains found in the conversation nodes themselves (and, I'm able to translate the values in the conversation nodes exactly the same way NodeViewer does -- the hex values are different than the labels for this table). What I can't figure out is how they start with 0xCFB66C35D898AA07BD, and end up with -530180456931428419 rather than 13144940616778123197.

Can anyone familiar with the node structures give me a hand?
## Post #248
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2014-01-29T21:32:55+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from jpreston84
>
> I have checked and verified these manually. For instance, the hex for the first label is 0xCFB66C35D898AA07BD. As best I can understand, the CF indicates a positively signed integer with a representation 8 bytes in length, with the next 8-bytes representing (as big endian) the value, which is 13144940616778123197. This means of converting numbers works throughout the nodes in many places, including the label for qstRewardsPerLevelData, which is stored only a few bytes before the labels I'm having trouble with.
...

What I can't figure out is how they start with 0xCFB66C35D898AA07BD, and end up with -530180456931428419 rather than 13144940616778123197.The 0xCF byte tells you the length of integer, 8 bytes in this case, not the sign. Byte-wise the values are identical, and it's about how you're choosing to type the value.

0xB66C35D898AA07BD = -530180456931428419
0xB66C35D898AA07BD = 13144940616778123197

Pages 4 and 5 of this thread have information on determining the type of the value. The relevant information is that the byte right before the 0xCF byte tells you the type. If it's 0x01, it's an unsigned integer (likely a node id). If it's 0x02, then you got a signed integer (likely a value or id looked up in a prototype node).
## Post #249
- Username: jpreston84
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Sep 01, 2013 2:05 pm
- Post datetime: 2014-01-29T23:24:59+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor miner
>
> jpreston84 wrote:I have checked and verified these manually. For instance, the hex for the first label is 0xCFB66C35D898AA07BD. As best I can understand, the CF indicates a positively signed integer with a representation 8 bytes in length, with the next 8-bytes representing (as big endian) the value, which is 13144940616778123197. This means of converting numbers works throughout the nodes in many places, including the label for qstRewardsPerLevelData, which is stored only a few bytes before the labels I'm having trouble with.
...

What I can't figure out is how they start with 0xCFB66C35D898AA07BD, and end up with -530180456931428419 rather than 13144940616778123197.The 0xCF byte tells you the length of integer, 8 bytes in this case, not the sign. Byte-wise the values are identical, and it's about how you're choosing to type the value.

0xB66C35D898AA07BD = -530180456931428419
0xB66C35D898AA07BD = 13144940616778123197

Pages 4 and 5 of this thread have information on determining the type of the value. The relevant information is that the byte right before the 0xCF byte tells you the type. If it's 0x01, it's an unsigned integer (likely a node id). If it's 0x02, then you got a signed integer (likely a value or id looked up in a prototype node).

Okay, so I'm slightly confused then. Until now, I've been operating on the assumption that the 0xC prefixes for integers worked like this...

Bits 0 - 4 are always 1100 (0xC)
Bit 5 is a sign bit (0 negative, 1 positive)
Bits 6 - 8 are the length-1 (in bytes) of the integer value (000 is 1 byte, 101 is 6 bytes, etc)

In fact, in the cnv.* nodes, for the cnvRewardAffectionRewards, the negative values are definitely stored with the 0xC7 prefix (I just double-checked this fact). Here's an example...

In the cnv nodes, we will see 0xC7187062A66980EDDD, so we convert 0x187062A66980EDDD to a positive value of 1761015921176014301. Then, per the negative sign bit in 0xC7, this becomes -1761015921176014301.
On the other hand, in the qstrewardsaffectionData node, we see the value 0xCFE78F9D59967F1223. We convert 0xE78F9D59967F1223 as a signed integer of -1761015921176014301.

So, are we effectively saying that there are two different ways of signing the integers depending on context?

Yay for "quality" software.
## Post #250
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2014-01-30T00:00:32+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from jpreston84
>
> swtor miner wrote:jpreston84 wrote:I have checked and verified these manually. For instance, the hex for the first label is 0xCFB66C35D898AA07BD. As best I can understand, the CF indicates a positively signed integer with a representation 8 bytes in length, with the next 8-bytes representing (as big endian) the value, which is 13144940616778123197. This means of converting numbers works throughout the nodes in many places, including the label for qstRewardsPerLevelData, which is stored only a few bytes before the labels I'm having trouble with.
...

What I can't figure out is how they start with 0xCFB66C35D898AA07BD, and end up with -530180456931428419 rather than 13144940616778123197.The 0xCF byte tells you the length of integer, 8 bytes in this case, not the sign. Byte-wise the values are identical, and it's about how you're choosing to type the value.

0xB66C35D898AA07BD = -530180456931428419
0xB66C35D898AA07BD = 13144940616778123197

Pages 4 and 5 of this thread have information on determining the type of the value. The relevant information is that the byte right before the 0xCF byte tells you the type. If it's 0x01, it's an unsigned integer (likely a node id). If it's 0x02, then you got a signed integer (likely a value or id looked up in a prototype node).

Okay, so I'm slightly confused then. Until now, I've been operating on the assumption that the 0xC prefixes for integers worked like this...

Bits 0 - 4 are always 1100 (0xC)
Bit 5 is a sign bit (0 negative, 1 positive)
Bits 6 - 8 are the length-1 (in bytes) of the integer value (000 is 1 byte, 101 is 6 bytes, etc)

In fact, in the cnv.* nodes, for the cnvRewardAffectionRewards, the negative values are definitely stored with the 0xC7 prefix (I just double-checked this fact). Here's an example...

In the cnv nodes, we will see 0xC7187062A66980EDDD, so we convert 0x187062A66980EDDD to a positive value of 1761015921176014301. Then, per the negative sign bit in 0xC7, this becomes -1761015921176014301.
On the other hand, in the qstrewardsaffectionData node, we see the value 0xCFE78F9D59967F1223. We convert 0xE78F9D59967F1223 as a signed integer of -1761015921176014301.

So, are we effectively saying that there are two different ways of signing the integers depending on context?

Yay for "quality" software.

You got in a nutshell.

There's also two other cases I've run into:

Bits 0 - 4 are 1101 (0xD)
Bits 5 - 8 are 0000 (0x0) or 0010 (0x2)

I haven't fully investigated these cases, and treating them as single byte values appears to work. How else they should be handled I'm not certain.
## Post #251
- Username: jpreston84
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Sep 01, 2013 2:05 pm
- Post datetime: 2014-01-30T04:01:34+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor miner
>
> You got in a nutshell.

There's also two other cases I've run into:

Bits 0 - 4 are 1101 (0xD)
Bits 5 - 8 are 0000 (0x0) or 0010 (0x2)

I haven't fully investigated these cases, and treating them as single byte values appears to work. How else they should be handled I'm not certain.
Yeah, there are actually many cases I've noticed where a label or value is a single-byte value. It seems that 0xC8 (which I've seen in a few cases) is basically unnecessary.

Thanks for the insight.
## Post #252
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-02-15T18:27:16+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi swtor miner! Have you managed to figure out bones in SWTOR? I stuck with them a bit, so if you have some info on them I'll be very greatful if you share this info with me. Thanks in advance

P.S. Problem solved - I've got the bones import:)
[bms.jpg](https://xentaxbackup.github.io/file/7021_bms.jpg)
## Post #253
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-02-21T23:09:18+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Bones and weights? If so, any possibility of sharing that?
## Post #254
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2014-03-04T15:17:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Credit to SWTOR fan for this:

If you come across a 0xD2 byte when reading a number, skip the 0xD2 byte and try to read the number again. I haven't confirmed it as the only case, but it only seems to show up on look up lists. It's probably a flag of some kind.

[Here's my latest hashlist.](http://www.sendspace.com/file/04db7j)
[And my latest gom type names](http://www.sendspace.com/file/x0bhe2) for [my updated Nodeviewer](http://www.sendspace.com/file/qr1dmi)
## Post #255
- Username: vertalius
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Mar 05, 2014 3:08 am
- Post datetime: 2014-03-04T19:48:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I would like to know about bones export too...How did you do that? All the bones are weigted? Mesh is skinned?
## Post #256
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2014-03-05T23:09:04+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from vertalius
>
> I would like to know about bones export too...How did you do that? All the bones are weigted? Mesh is skinned?
I've mentioned everything about the bones in my .gr2 specification; if you know a little bit about programming, you should be able to get the bones. 

[http://wiki.xentax.com/index.php?title= ... model_file](http://wiki.xentax.com/index.php?title=SWTOR:_.gr2_3D_model_file)

Each NPC and each placeable with movable parts belongs to a certain body type. If you know which body type it is, you can look up the skeleton file.
For example,
/resources/art/dynamic/spec/bfnnew_skeleton.gr2
is the skeleton file for female NPCs with body type 2 (in the files, this body type is called "bfn", which probably stands for "body female normal").
Skeleton files have the same structure as other .gr2 files, but the field I call "type of .gr2 file" is set to 0x02, and you can find a list of the bone joints at offsetBoneStructure = 0x70.
Each joint is defined with:
- uint32: offsetBoneName
- int32: parentBoneIndex
- 16 floats: 4x4 joint-to-parent rotation matrix
- 16 floats: 4x4 joint-to-root rotation matrix
With this information, you will be able to draw a skeleton yourself.

The regular .gr2 files then contain a list of joints that are used by the current model. Also, each dynamic model has a vertexSize of 32, so each vertex will contain information on up to four bones that influence it's position, as well as the weights for each bone. See the "Vertices" section of my specification for more information.


So with the information from the specification, you should be able to get a model with a skeleton structure. However, I have not yet figured out the format of the .jba, .mph and .amx files which contain the animations. If anyone has made any progress with those, please do share! Unfortunately, I lack the knowledge to parse the animations myself since that matrix Math is way above my head...
## Post #257
- Username: vertalius
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Mar 05, 2014 3:08 am
- Post datetime: 2014-03-06T20:36:07+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Unfortunately I know nothing about programming, so... I've asked about simple way to get skeletons/bones than those you've mentioned in post above =)
## Post #258
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-15T09:07:48+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi guys! Here's maxscript to import SWTOR models with bones (3ds max 2009-2011)

Instruction:
1. Load SWTOR_BONES.ms
2. Point it to a file like ***_skeleton.gr2
3. Bones will be loaded

4. Load SWTOR.ms
5. Point it to a file like ***.gr2 without word "skeleton"
6. Model will be loaded above bones

Done

[](http://piccy.info/view3/6067969/47cf3fd9c0bb20f5463538c3c179e2af/orig/)[](http://i.piccy.info/a3c/2014-03-15-09-07/i9-6067969/744x574-r)
[SWTOR_SCRIPTS.7z](https://xentaxbackup.github.io/file/7092_SWTOR_SCRIPTS.7z)
## Post #259
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-03-15T12:54:34+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Any of you guys know where to find the lightsabers or other items such as that? Like Satele's Lightsaber?
## Post #260
- Username: vertalius
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Mar 05, 2014 3:08 am
- Post datetime: 2014-03-15T22:27:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

2 zaramot
Thanks a lot man! That was exactly what I've looked for!

Is there any chance to get bone weights from models to get them rigged & ready to animate?
## Post #261
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-16T10:38:35+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Weights are supported, there are problems with finding right skeleton for models. But if you will find right one, weights will work fine. Here's some player models for you to test, that weights works normal.

P.S. Should be skeletons with extra bones - for capes, cloth, skirts, loin etc. Base skeletons don't have them - that's the problem.
[Models_to_Test.7z](https://xentaxbackup.github.io/file/7095_Models_to_Test.7z)
## Post #262
- Username: vertalius
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Mar 05, 2014 3:08 am
- Post datetime: 2014-03-16T22:11:44+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

No, skeletons is ok, but some body parts is not "fully" skinned/rigged.
For example, when I import mesh "chest_xxxx_xx_01.gr2" to 3dmax, skin modificator doesn't have all the bones, only 2-3 of them so I need to add needed bones & weight them manually 
But when I load to that skeleton another body part it have all the needed bones in skin modificator & fully rigged.
## Post #263
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-03-17T16:25:05+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

That's probably the problem with capes/cloth etc. It was like that with Malgus, he didn't have cape bones which caused problems with the weights.
## Post #264
- Username: vertalius
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Mar 05, 2014 3:08 am
- Post datetime: 2014-03-18T13:36:16+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

2 swtor miner

Do you have any update/news your viewer or noesis plugin for swtor?

BTW in Noesis i get an error, when trying to import some of .gr2 models - I've described the problem here [viewtopic.php?f=16&t=9703&p=93195#p93195](http://forum.xentax.com/viewtopic.php?f=16&t=9703&p=93195#p93195)

2 Zaramot

Can you edit your "SWTOR bones/models import" script to load them with Z axis up?
## Post #265
- Username: vertalius
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Mar 05, 2014 3:08 am
- Post datetime: 2014-05-21T13:44:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Any updates for exporting animations?
## Post #266
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2014-05-21T23:19:54+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey guys it's been a while!

Here's my latest Hashlist: [hashes_filename.zip](http://www.sendspace.com/file/xyfego)

Not including French/German localized filenames, it's status is 477,503/489,639 files named, only missing 12,136 filenames. Of which ~5700 are map image prototype files that will likely never have their names discovered. So that's ~6400 filenames left to discover, the vast majority of which are animation/fx related.

You'll be needing this new hashlist to play with my [updated GR2 Noesis Plugin](http://forum.xentax.com/viewtopic.php?f=16&t=9703&p=94778#p94778).

It'll now attempt to load textures from the material files directly, rather than searching for them in nearby folders. This means you'll likely have to extract all the swtor_main_art*.tor archives to a folder to ensure that the materials/textures are available for loading. And change the swtor-config.xml file to point to where the "resources" folder is.
## Post #267
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2014-06-10T18:09:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor miner
>
> Hey guys it's been a while!

Here's my latest Hashlist: hashes_filename.zip

Not including French/German localized filenames, it's status is 477,503/489,639 files named, only missing 12,136 filenames. Of which ~5700 are map image prototype files that will likely never have their names discovered. So that's ~6400 filenames left to discover, the vast majority of which are animation/fx related.

You'll be needing this new hashlist to play with my updated GR2 Noesis Plugin.

It'll now attempt to load textures from the material files directly, rather than searching for them in nearby folders. This means you'll likely have to extract all the swtor_main_art*.tor archives to a folder to ensure that the materials/textures are available for loading. And change the swtor-config.xml file to point to where the "resources" folder is.
i downloaded the latest noesis aswell as re-extracted all the models and textures but when i load a model into noesis i can see the model but no textures are loaded, i also set up the path correctly but still no textures, do you know what the issue might be?
## Post #268
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2014-06-10T22:28:28+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from luke9511
>
> swtor miner wrote:Hey guys it's been a while!

Here's my latest Hashlist: hashes_filename.zip

Not including French/German localized filenames, it's status is 477,503/489,639 files named, only missing 12,136 filenames. Of which ~5700 are map image prototype files that will likely never have their names discovered. So that's ~6400 filenames left to discover, the vast majority of which are animation/fx related.

You'll be needing this new hashlist to play with my updated GR2 Noesis Plugin.

It'll now attempt to load textures from the material files directly, rather than searching for them in nearby folders. This means you'll likely have to extract all the swtor_main_art*.tor archives to a folder to ensure that the materials/textures are available for loading. And change the swtor-config.xml file to point to where the "resources" folder is.
i downloaded the latest noesis aswell as re-extracted all the models and textures but when i load a model into noesis i can see the model but no textures are loaded, i also set up the path correctly but still no textures, do you know what the issue might be?

Open up the Swtor.py plug-in file and remove the "#" in front of "#noesis.logPopup()" and save it. Reopen Noesis and paste the debug output here.
## Post #269
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2014-06-11T13:48:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor miner
>
> luke9511 wrote:swtor miner wrote:Hey guys it's been a while!

Here's my latest Hashlist: hashes_filename.zip

Not including French/German localized filenames, it's status is 477,503/489,639 files named, only missing 12,136 filenames. Of which ~5700 are map image prototype files that will likely never have their names discovered. So that's ~6400 filenames left to discover, the vast majority of which are animation/fx related.

You'll be needing this new hashlist to play with my updated GR2 Noesis Plugin.

It'll now attempt to load textures from the material files directly, rather than searching for them in nearby folders. This means you'll likely have to extract all the swtor_main_art*.tor archives to a folder to ensure that the materials/textures are available for loading. And change the swtor-config.xml file to point to where the "resources" folder is.
i downloaded the latest noesis aswell as re-extracted all the models and textures but when i load a model into noesis i can see the model but no textures are loaded, i also set up the path correctly but still no textures, do you know what the issue might be?

Open up the Swtor.py plug-in file and remove the "#" in front of "#noesis.logPopup()" and save it. Reopen Noesis and paste the debug output here.
looks like from me reading the log it is my fault cause of the way i extracted it, i will start over and edit my post wether it was a success or not, also all of the mat files are missing the .mat on them and they are showing up as microsoft access files which is strange

ok it was a success and it was my fault due to how i had the folders setup but thanks for the help!
## Post #270
- Username: swtor enthusiast
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 31, 2013 5:23 am
- Post datetime: 2014-07-22T20:49:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey all,

I was wondering if someone could direct me to where skill tree ability names and the hover tooltip text descriptions are stored? I have NodeViewer and Noesis but wasn't seeing the descriptions on my first look-through.
## Post #271
- Username: vertalius
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Mar 05, 2014 3:08 am
- Post datetime: 2014-08-21T19:22:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Any updates?
## Post #272
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-10-18T11:41:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

After re-downloading swtor miner's easymyp update, I get a unhandled exception error when I try and load a .tor file, like I did before. I don't know why this is happening again :/
## Post #273
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2014-10-19T13:23:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from TRDaz
>
> After re-downloading swtor miner's easymyp update, I get a unhandled exception error when I try and load a .tor file, like I did before. I don't know why this is happening again :/

Mind posting the exception stacktrace?
## Post #274
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-10-21T22:05:43+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

You mean this?

```
just-in-time (JIT) debugging instead of this dialog box.

************** Exception Text **************
System.FormatException: Input string was not in a correct format.
   at System.Number.StringToNumber(String str, NumberStyles options, NumberBuffer& number, NumberFormatInfo info, Boolean parseDecimal)
   at System.Number.ParseInt32(String s, NumberStyles style, NumberFormatInfo info)
   at System.Int32.Parse(String s, IFormatProvider provider)
   at System.Diagnostics.PerformanceCounterLib.GetStringTable(Boolean isHelp)
   at System.Diagnostics.PerformanceCounterLib.get_NameTable()
   at System.Diagnostics.PerformanceCounterLib.get_CategoryTable()
   at System.Diagnostics.PerformanceCounterLib.CounterExists(String category, String counter, Boolean& categoryExists)
   at System.Diagnostics.PerformanceCounterLib.CounterExists(String machine, String category, String counter)
   at System.Diagnostics.PerformanceCounter.Initialize()
   at System.Diagnostics.PerformanceCounter..ctor(String categoryName, String counterName, String instanceName, Boolean readOnly)
   at System.Diagnostics.PerformanceCounter..ctor(String categoryName, String counterName, String instanceName)
   at MYPHandler.MYPHandler..ctor(String filename, del_FileTableEventHandler eventHandler_FileTable, del_FileEventHandler eventHandler_Extraction, HashDictionary hashDic) in C:\Code\Personal\SWTOR ripper\EasyMYP\MYPHandler\MYPHandler_extraction.cs:line 154
   at EasyMYP.MainWindow.OpenArchive(String filename, Boolean block) in C:\Code\Personal\SWTOR ripper\EasyMYP\EasyMYP\MainWindow.cs:line 182
   at EasyMYP.MainWindow.openArchiveToolStripMenuItem_Click(Object sender, EventArgs e) in C:\Code\Personal\SWTOR ripper\EasyMYP\EasyMYP\MainWindow.cs:line 160
   at System.Windows.Forms.ToolStripItem.RaiseEvent(Object key, EventArgs e)
   at System.Windows.Forms.ToolStripMenuItem.OnClick(EventArgs e)
   at System.Windows.Forms.ToolStripItem.HandleClick(EventArgs e)
   at System.Windows.Forms.ToolStripItem.HandleMouseUp(MouseEventArgs e)
   at System.Windows.Forms.ToolStripItem.FireEventInteractive(EventArgs e, ToolStripItemEventType met)
   at System.Windows.Forms.ToolStripItem.FireEvent(EventArgs e, ToolStripItemEventType met)
   at System.Windows.Forms.ToolStrip.OnMouseUp(MouseEventArgs mea)
   at System.Windows.Forms.ToolStripDropDown.OnMouseUp(MouseEventArgs mea)
   at System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
   at System.Windows.Forms.Control.WndProc(Message& m)
   at System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   at System.Windows.Forms.ToolStrip.WndProc(Message& m)
   at System.Windows.Forms.ToolStripDropDown.WndProc(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)


************** Loaded Assemblies **************
mscorlib
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.6421 (Win8RTMGDR.050727-6400)
    CodeBase: file:///C:/Windows/Microsoft.NET/Framework/v2.0.50727/mscorlib.dll
----------------------------------------
EasyMYP
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///D:/Models/EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/EasyMYP.exe
----------------------------------------
System.Windows.Forms
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.6419 (Win8RTMGDR.050727-6400)
    CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System.Windows.Forms/2.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.6421 (Win8RTMGDR.050727-6400)
    CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System/2.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Drawing
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.6419 (Win8RTMGDR.050727-6400)
    CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System.Drawing/2.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
MYPHandler
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///D:/Models/EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/MYPHandler.DLL
----------------------------------------
HashDictionary
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///D:/Models/EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/HashDictionary.DLL
----------------------------------------
HashCreator
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///D:/Models/EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/HashCreator.DLL
----------------------------------------
System.Core
    Assembly Version: 3.5.0.0
    Win32 Version: 3.5.30729.6387 built by: Win8RTM
    CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System.Core/3.5.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
WarhammerOnlineHash
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///D:/Models/EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/WarhammerOnlineHash.DLL
----------------------------------------
System.Configuration
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.6419 (Win8RTMGDR.050727-6400)
    CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System.Configuration/2.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Management
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.6419 (Win8RTMGDR.050727-6400)
    CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System.Management/2.0.0.0__b03f5f7f11d50a3a/System.Management.dll
----------------------------------------

************** JIT Debugging **************
To enable just-in-time (JIT) debugging, the .config file for this
application or computer (machine.config) must have the
jitDebugging value set in the system.windows.forms section.
The application must also be compiled with debugging
enabled.

For example:

<configuration>
    <system.windows.forms jitDebugging="true" />
</configuration>

When JIT debugging is enabled, any unhandled exception
will be sent to the JIT debugger registered on the computer
rather than be handled by this dialog box.



```
## Post #275
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2014-10-21T23:51:34+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from TRDaz
>
> You mean this?

Yeah, that's what I was looking for. Though I've altered EasyMyp even more since that release, and I don't have the code handy to debug that version. Try this one. 
[https://www.sendspace.com/file/dpw2hg](https://www.sendspace.com/file/dpw2hg)
## Post #276
- Username: rogue9607
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 22, 2014 4:05 pm
- Post datetime: 2014-10-22T17:15:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I just found all of this and wanted to say THANK YOU! for all of the hard work.  I managed to find the armor/weapon models I was looking for.

One question if anyone could point me in the right direction... Is there a way to combine the models and textures?  I'm very new to 3D modeling and spend more of my hobby time on the crafting side.
## Post #277
- Username: shygeekguy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 23, 2014 9:11 am
- Post datetime: 2014-10-23T01:13:00+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

anyone have an updated gom_type_names.xml ?
## Post #278
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-10-23T12:42:43+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Nope, that version doesn't work either :/
## Post #279
- Username: NepsterCZ
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 30, 2014 4:53 am
- Post datetime: 2014-11-02T06:34:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello i have a two questions, is there any way to find out what body parts does companions use? I sped alot of time trying to build companions from scratch, and had initial success with Ashara Zavros, mainly because there are only 6 Torgue heads and dozens of face paints. Later i tried do build Nadia Grell with semi-success but it was obvious that this is not a valid approach. So my question is this.

Is there any way to determinate what exact specification does given companion has? Like "Jaesa Willsaam - Type 3 head, Type 1 Customization, Type 4 Eyes, Type 21 haircolor".

And my second question is about republic/imperial army. Was anyone able to find imperial/republic assault droid? I mean the humanoid like, not the "big-robot-ish like one". I thought it will be pretty easy to find because HK-51 does have them as customization, but for my surprise, they are pretty hard to find.

Thanks for your time.
## Post #280
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2014-11-03T00:07:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from NepsterCZ
>
> Was anyone able to find imperial/republic assault droid? I mean the humanoid like, not the "big-robot-ish like one". I thought it will be pretty easy to find because HK-51 does have them as customization

swtor_main_art_creature_a_1.tor

Republic model
resources\art\dynamic\creature\model\assassin_magnatrooper_a01.gr2
texture
resources\art\dynamic\creature\texture\assassin_magnatrooper_a01_v01_d.dds

Imperial model
resources\art\dynamic\creature\model\assassin_autotrooper_a01.gr2
texture
resources\art\dynamic\droid\assassin_droid\texture\___psd\assassin_autotrooper_a01_v01_d.dds
## Post #281
- Username: NepsterCZ
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 30, 2014 4:53 am
- Post datetime: 2014-11-03T11:18:47+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Wow, this is awkward. Now i feel like a moron. Thank you, i spend over 10 hours looking for them
## Post #282
- Username: TheArk
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 03, 2013 12:12 am
- Post datetime: 2014-11-07T01:14:16+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Any hashlist updates, I've not been doing a whole lot of work on TOR in the past few months was just wondering if anything news come up!
## Post #283
- Username: swtor enthusiast
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 31, 2013 5:23 am
- Post datetime: 2015-02-08T06:40:50+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

It's been a few months, can you show us how to help update the hash list for this?
## Post #284
- Username: Talgalar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 17, 2015 2:06 am
- Post datetime: 2015-08-16T18:26:22+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi !
Some news about hashlist updates ? Or a new way to extract swtor models ?
## Post #285
- Username: geerzo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 23, 2015 1:19 am
- Post datetime: 2015-08-22T17:21:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Does anyone know where to download the NodeViewer program (or better yet where the source lives)? All the links in this thread seem to be bad and so is every other link found through Google.
## Post #286
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-08-22T19:37:09+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

This is all i could find in my files


 NodeViewer.zip
(177.32 KiB) Downloaded 129 times
## Post #287
- Username: Kualan
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 27, 2015 4:23 am
- Post datetime: 2015-09-05T12:40:28+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi folks. Does anyone have a hash update from some time in the past six or so months?
## Post #288
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-09-06T07:04:02+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

You can use the NodeViewer to see some file names and you can find others in index.xml and other various extracted xml formatted files.
*.gr2 files have *.mat file names and those have texture file names. SWTOR fan says area.dat files are a great source of file names.

I'm not a programmer and don't have any specialized tools to work with like Rick and SWTOR fan, so everything i do is manual. 
This is what i tried based on the replies throughout this thread
-if you see a file name that you know is part of a recent game update, copy it into a txt file with the path starting with /resources
-launch EasyMYP
-go to Dictionary>Test Full Filename List and browse to your txt file
-you will get a message if a new name was found
-close EasyMYP
-if a new name was found it will be added to the hashes_filename.txt


Example
launch NodeViewer and expand "ami" then click on "head" and scroll through the rightside window
eventually you will find head_selkath_bmn_non_a02.gr2 which hasn't been found by current hash lists
copy this into your anyname.txt file:

```
/resources/art/dynamic/head/model/head_selkath_bmn_non_a02.gr2
```

launch EasyMYP, i like to call it TORexplore   
go to Dictionary>Test Full Filename List and browse to and select your anyname.txt file and wait
you have just found 1 new name if using the last updated hash list  
close EasyMYP and it will add the new name to the hashes_filename.txt and also formatted correctly with hashes.
now you can launch EasyMYP again and open the tor archive and extract the file with name
## Post #289
- Username: Alianin
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 28, 2012 12:07 am
- Post datetime: 2015-09-06T21:51:04+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

AceWell, thank you for that info! I've managed to identify all the decoration icon names (yay, 84 new names for the list). I know what folder most images I'm concerned with are located in but is there a way to be sure that's the correct folder?
## Post #290
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-09-06T22:45:04+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thats awesome thanks!    I'm new to finding names, i realized the guys that were doing it before may not come back for lack of interest so we'll need to figure it out ourselves. Like Vindis was saying earlier, much of it is guessing. The folder structures have already been discovered and are consistent with tor archives of similar content. I think its okay to say at this point any new game files will fall into these known locations, but there is always a possibility of things being changed by the devs.



Edit
It looks like the devs are making file changes for the KotFE expansion according to swtor_miner on Twitter.
[https://twitter.com/swtor_miner/status/ ... 96?lang=en](https://twitter.com/swtor_miner/status/639586953340522496?lang=en)

> The patch size for #SWTOR #KotFE is likely to be 15GB+ due to them altering a ton of the data formats.
> They switched area files from a text format to a binary format.
> It broke part of my filename finder. @Swtor_Potato and I are wondering if they integrated code from a newer heroengine version.

Keep a copy of the old game files before updating to KotFE just in case.
## Post #291
- Username: Kualan
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 27, 2015 4:23 am
- Post datetime: 2015-09-07T04:26:38+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Excellent response Ace, that's very helpful thanks.
## Post #292
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2015-09-22T19:59:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi,
first post here.
I have some new hashes for you. Round about 10000 since last update from SWTOR Miner
[hashes_filename.rar](http://www.file-upload.net/download-10927316/hashes_filename.rar.html)
## Post #293
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-09-22T20:53:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Awesome first post Ferouc!   


> Reply from geerzo
>
> Does anyone know where to download the NodeViewer program (or better yet where the source lives)? All the links in this thread seem to be bad and so is every other link found through Google.
I found this newer version on another of my external harddrives


 Nodeviewer.7z
(198.49 KiB) Downloaded 100 times
## Post #294
- Username: Kualan
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 27, 2015 4:23 am
- Post datetime: 2015-09-23T00:16:10+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> Hi,
first post here.
I have some new hashes for you. Round about 10000 since last update from SWTOR Miner
hashes_filename.rar

Awesome!!! Thanks man, appreciate it.
## Post #295
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-09-25T13:43:21+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have found 35 new texture names while putting together the Havoc trooper armor, these are all for the havoc armor


 35_names.zip
(422 Bytes) Downloaded 46 times



these are the gr2 files that make up the havoc armor male body type 2
boot_tall_bmn_archetype.gr2
boot_tall_bmn_heavy_tr_mtx03_cover.gr2
chest_tight_bmn_heavy_tr_mtx03_backpack.gr2
chest_tight_bmn_heavy_tr_mtx03_chest.gr2
chest_tight_bmn_heavy_tr_mtx03_shoulder.gr2
chest_tightskin11_bmn_archetype.gr2
face_trhelmet21_bmn_archetype.gr2
face_trhelmet21_bmn_attachment.gr2
hand_glove_bmn_archetype.gr2
hand_glove_bmn_heavy_tr_mtx03_forearm.gr2
leg_armor03_bmn_archetype.gr2
waist_belt_bmn_heavy_tr_mtx03_back.gr2
waist_belt_bmn_heavy_tr_mtx03_front.gr2



bma = male body type 1
bmn = male body type 2
bms = male body type 3
bmf = male body type 4

bfa = female body type 1 
bfn = female body type 2
bfs = female body type 3
bfb = female body type 4



also i'm trying to learn what all these file name designations mean, anyone know these? I gave it a guess
_tr_ = trooper gear
_ge_ = agent gear?
_bh_ = bounty hunter gear
_sw_ = sith warrior gear?
_ss_ = sith inquisitor gear?
_jw_ = jedi consular gear?
_jk_ = jedi knight gear?
_sm_ = smuggler gear?
## Post #296
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2015-09-25T16:34:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Yeah, for the names that looks right. JW for Consular/Sage is because originally they were called Jedi Wizard. Not sure about the Agent, but I assume it is also some legacy name.

For the body sizes, 

Male:
1 - BMA
2 - BMN (N=normal presumably)
3 - BMS (S=super?)
4 - BMF (F=fat)

Female:
1 - BFA
2 - BFN
3 - BFS
4 - BFB (B=booty or buxom?)
## Post #297
- Username: Wefi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 15, 2012 11:41 am
- Post datetime: 2015-10-01T17:09:37+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from AceWell
>
> I have found 35 new texture names while putting together the Havoc trooper armor, these are all for the havoc armor
35_names.zip

these are the gr2 files that make up the havoc armor male body type 2
boot_tall_bmn_archetype.gr2
boot_tall_bmn_heavy_tr_mtx03_cover.gr2
chest_tight_bmn_heavy_tr_mtx03_backpack.gr2
chest_tight_bmn_heavy_tr_mtx03_chest.gr2
chest_tight_bmn_heavy_tr_mtx03_shoulder.gr2
chest_tightskin11_bmn_archetype.gr2
face_trhelmet21_bmn_archetype.gr2
face_trhelmet21_bmn_attachment.gr2
hand_glove_bmn_archetype.gr2
hand_glove_bmn_heavy_tr_mtx03_forearm.gr2
leg_armor03_bmn_archetype.gr2
waist_belt_bmn_heavy_tr_mtx03_back.gr2
waist_belt_bmn_heavy_tr_mtx03_front.gr2



bma = male body type 1
bmn = male body type 2
bms = male body type 3
bmf = male body type 4

bfa = female body type 1 
bfn = female body type 2
bfs = female body type 3
bfb = female body type 4



also i'm trying to learn what all these file name designations mean, anyone know these? I gave it a guess
_tr_ = trooper gear
_ge_ = agent gear?
_bh_ = bounty hunter gear
_sw_ = sith warrior gear?
_ss_ = sith inquisitor gear?
_jw_ = jedi consular gear?
_jk_ = jedi knight gear?
_sm_ = smuggler gear?

Agent is a tricky one, there a SP one which should stand for Spy, A Pre-Alpha name for Agent, and JW is Jedi Wizard, antoher pre-Alpha name.
## Post #298
- Username: Kualan
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 27, 2015 4:23 am
- Post datetime: 2015-10-01T19:50:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from AceWell
>
> I have found 35 new texture names while putting together the Havoc trooper armor, these are all for the havoc armor
35_names.zip

these are the gr2 files that make up the havoc armor male body type 2
boot_tall_bmn_archetype.gr2
boot_tall_bmn_heavy_tr_mtx03_cover.gr2
chest_tight_bmn_heavy_tr_mtx03_backpack.gr2
chest_tight_bmn_heavy_tr_mtx03_chest.gr2
chest_tight_bmn_heavy_tr_mtx03_shoulder.gr2
chest_tightskin11_bmn_archetype.gr2
face_trhelmet21_bmn_archetype.gr2
face_trhelmet21_bmn_attachment.gr2
hand_glove_bmn_archetype.gr2
hand_glove_bmn_heavy_tr_mtx03_forearm.gr2
leg_armor03_bmn_archetype.gr2
waist_belt_bmn_heavy_tr_mtx03_back.gr2
waist_belt_bmn_heavy_tr_mtx03_front.gr2



bma = male body type 1
bmn = male body type 2
bms = male body type 3
bmf = male body type 4

bfa = female body type 1 
bfn = female body type 2
bfs = female body type 3
bfb = female body type 4



also i'm trying to learn what all these file name designations mean, anyone know these? I gave it a guess
_tr_ = trooper gear
_ge_ = agent gear?
_bh_ = bounty hunter gear
_sw_ = sith warrior gear?
_ss_ = sith inquisitor gear?
_jw_ = jedi consular gear?
_jk_ = jedi knight gear?
_sm_ = smuggler gear?

You're pretty close with those code translations, but as Wefi said 'sp' is the Imperial Agent designation. 'Ge' seems to stand for 'generic' as it covers a wide range of mostly faction-neutral models - everything from Mantellian Separatists to Dathomiri Shamans.
## Post #299
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-10-01T21:09:59+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks! Okay so this is what we got
tr = trooper
bh = bounty hunter
sp = agent (spy)
sw = sith warrior
ss = sith inquisitor (sith shaman)
jw = jedi consular (jedi wizard)
jk = jedi knight
sm = smuggler
ge = generic
## Post #300
- Username: vertalius
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Mar 05, 2014 3:08 am
- Post datetime: 2015-10-03T14:08:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

For the body sizes, 

Male:
1 - BMA = Base Male Anorexic
2 - BMN = Base Male Normal
3 - BMS = Base Male Strong
4 - BMF = Base Male Fat

Female:
1 - BFA = Base Female Anorexic
2 - BFN = Base Female Normal
3 - BFS = Base Female Strong
4 - BFB = Base Female Big/Fat (I assume "Big" is used to be polite with woman - they allways get it wrong   )
## Post #301
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-10-05T20:50:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I've been extracting models from this recently, and have found pieces of armor I need, however the textures are nowhere to be found. The pieces are chest_cyborg05, boot_cyborg05, leg_cyborg05 etc, and there is no folder with any textures for "cyborg05". I tried using nodeviewer to add the textures to the hash list, but I am unsure where the textures are located within nodeviewer to find the correct names needed. Any help with this would be really appreciated.
## Post #302
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-10-06T01:49:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

here ya go, 90 new cyborg05 texture names


 90_names.zip
(669 Bytes) Downloaded 59 times



you can get these from the .mat files
## Post #303
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-10-06T05:42:16+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Oh, thank you! I'll keep that in mind for if I need anything in the future
## Post #304
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-10-06T15:43:32+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Apologies for the double post, but I am still looking at the cyborg05 items, and am unable to find textures for "chest_cyborg05_bfn_heavy_ge_cy03" pieces. I tried finding the .mat file for this, but I cannot seem to find that either.

EDIT: Figured it out, I extracted one of the .mat files that was missing a name in the tor archive, and checked in there. Made a new name list, and added the .mat files to it also, here is 24 new names:
[24_names.zip](https://xentaxbackup.github.io/file/9839_24_names.zip)
## Post #305
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2015-10-10T16:14:10+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

take a look into the index.xml
Search for the Armor your looking for. There you can find all the Meshes for the Armor and the mat file too.
## Post #306
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-10-10T18:52:50+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Didn't realise the xml held that information. Thank you for telling me
## Post #307
- Username: KaosXIV
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 07, 2014 6:28 am
- Post datetime: 2015-10-23T01:26:59+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor miner
>
> luke9511 wrote:just thought i would post and say so far everything is working great but like someone else said alot of textures dont get extracted so alot of models are missing sometimes one or two textures or all of them and some models wont load in the noesis viewer it pops up with an error but thats for a different thread
This is something that I'm working on. Unfortunately none of my code is quite ready for you guys just yet.

I also discovered (at least haven't seen it posted anywhere) how the game stores the heightmap for areas. In the Room Specification .dat files the heightmap is stored in the .VertexData property as a zlib compressed hex string in one of two encodings.

If it starts with "78 9C" it's a regular zlib stream. If it starts with "1F 8B" it's compressed with gzip encoding. Here's a small piece of the uncompressed data to look at:
Code: Select all00000000h: 09 40 00 00 00 40 00 00 00 33 33 33 41 9E EF A9 ; .@...@...333Ažï©
00000010h: 40 CD CC E2 42 00 D0 44 90 3F 1C C9 84 3F D0 44 ; @ÍÌâB.ÐD?.É„?ÐD
00000020h: 90 3F E3 83 85 3F D0 44 90 3F B2 EA 82 3F D0 44 ; ?ãƒ…?ÐD?²ê‚?ÐD


I've been meaning to analyze them, but just haven't had the opportunity.
I've been wondering, has this been analyzed any further?
I'd love to get my hands on those heightmaps
## Post #308
- Username: Kualan
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 27, 2015 4:23 am
- Post datetime: 2015-10-23T09:15:16+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I still can't quite get my head around how to compile a new, updated hash list to include files from the recent expansion. Anybody had any luck with that?
## Post #309
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2015-10-23T20:58:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey all, I've been perusing this thread regularly, searching for some help for my project. I want to extract the models and textures of the various 'forms' of Emperor Vitiate, starting with his most 'human' appearance. Can someone point me in the right direction, or let me know what files I should be looking for?
## Post #310
- Username: Nengalore
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 26, 2015 2:34 am
- Post datetime: 2015-10-25T18:40:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I can't seem to load .TOR files into EasyMYP, if I try it gives me this error:

Unhandled exception has occurred in your application. If you click Continue, the application will ignore this error and attempt to continue. If you click Quit, the application will close immediately.

Input string was not in a correct format.

See the end of this message for details on invoking 
just-in-time (JIT) debugging instead of this dialog box.

************** Exception Text **************
System.FormatException: Input string was not in a correct format.
   at System.Number.StringToNumber(String str, NumberStyles options, NumberBuffer& number, NumberFormatInfo info, Boolean parseDecimal)
   at System.Number.ParseInt32(String s, NumberStyles style, NumberFormatInfo info)
   at System.Int32.Parse(String s, IFormatProvider provider)
   at System.Diagnostics.PerformanceCounterLib.GetStringTable(Boolean isHelp)
   at System.Diagnostics.PerformanceCounterLib.get_NameTable()
   at System.Diagnostics.PerformanceCounterLib.get_CategoryTable()
   at System.Diagnostics.PerformanceCounterLib.CounterExists(String category, String counter, Boolean& categoryExists)
   at System.Diagnostics.PerformanceCounterLib.CounterExists(String machine, String category, String counter)
   at System.Diagnostics.PerformanceCounter.Initialize()
   at System.Diagnostics.PerformanceCounter..ctor(String categoryName, String counterName, String instanceName, Boolean readOnly)
   at System.Diagnostics.PerformanceCounter..ctor(String categoryName, String counterName, String instanceName)
   at MYPHandler.MYPHandler..ctor(String filename, del_FileTableEventHandler eventHandler_FileTable, del_FileEventHandler eventHandler_Extraction, HashDictionary hashDic)
   at EasyMYP.MainWindow.OpenArchive(String filename, Boolean block)
   at EasyMYP.MainWindow.openArchiveToolStripMenuItem_Click(Object sender, EventArgs e)
   at System.Windows.Forms.ToolStripItem.RaiseEvent(Object key, EventArgs e)
   at System.Windows.Forms.ToolStripMenuItem.OnClick(EventArgs e)
   at System.Windows.Forms.ToolStripItem.HandleClick(EventArgs e)
   at System.Windows.Forms.ToolStripItem.FireEventInteractive(EventArgs e, ToolStripItemEventType met)
   at System.Windows.Forms.ToolStripItem.FireEvent(EventArgs e, ToolStripItemEventType met)
   at System.Windows.Forms.ToolStripItem.PerformClick()
   at EasyMYP.MainWindow.ProcessCmdKey(Message& msg, Keys keyData)
   at System.Windows.Forms.Control.ProcessCmdKey(Message& msg, Keys keyData)
   at System.Windows.Forms.Control.ProcessCmdKey(Message& msg, Keys keyData)
   at System.Windows.Forms.Control.PreProcessMessage(Message& msg)
   at System.Windows.Forms.Control.PreProcessControlMessageInternal(Control target, Message& msg)
   at System.Windows.Forms.Application.ThreadContext.PreTranslateMessage(MSG& msg)


************** Loaded Assemblies **************
mscorlib
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.5485 (Win7SP1GDR.050727-5400)
    CodeBase: file:///C:/Windows/Microsoft.NET/Framework/v2.0.50727/mscorlib.dll
----------------------------------------
EasyMYP
    Assembly Version: 0.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///C:/Users/edangus/Documents/EasyMYP/EasyMYP.exe
----------------------------------------
System.Windows.Forms
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.5491 (Win7SP1GDR.050727-5400)
    CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System.Windows.Forms/2.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.5485 (Win7SP1GDR.050727-5400)
    CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System/2.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Drawing
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.5491 (Win7SP1GDR.050727-5400)
    CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System.Drawing/2.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
HashDictionary
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///C:/Users/edangus/Documents/EasyMYP/HashDictionary.DLL
----------------------------------------
MYPHandler
    Assembly Version: 0.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///C:/Users/edangus/Documents/EasyMYP/MYPHandler.DLL
----------------------------------------
HashCreator
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///C:/Users/edangus/Documents/EasyMYP/HashCreator.DLL
----------------------------------------
System.Core
    Assembly Version: 3.5.0.0
    Win32 Version: 3.5.30729.5420 built by: Win7SP1
    CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System.Core/3.5.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
WarhammerOnlineHash
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///C:/Users/edangus/Documents/EasyMYP/WarhammerOnlineHash.DLL
----------------------------------------
System.Configuration
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.5483 (Win7SP1GDR.050727-5400)
    CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System.Configuration/2.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Management
    Assembly Version: 2.0.0.0
    Win32 Version: 2.0.50727.5483 (Win7SP1GDR.050727-5400)
    CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System.Management/2.0.0.0__b03f5f7f11d50a3a/System.Management.dll
----------------------------------------

************** JIT Debugging **************
To enable just-in-time (JIT) debugging, the .config file for this
application or computer (machine.config) must have the
jitDebugging value set in the system.windows.forms section.
The application must also be compiled with debugging
enabled.

For example:

<configuration>
    <system.windows.forms jitDebugging="true" />
</configuration>

When JIT debugging is enabled, any unhandled exception
will be sent to the JIT debugger registered on the computer
rather than be handled by this dialog box.


Does anyone know what to do?
## Post #311
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-10-26T10:55:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Here is an update of names for main_art_creature_a_1, these include some new KOTFE characters too.
[main_art_creature_a_1_names.zip](https://xentaxbackup.github.io/file/9924_main_art_creature_a_1_names.zip)
## Post #312
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-10-26T16:55:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Okay i'm trying to document this layman process for finding new names, at least for characters and here's what i got. 
It works and although it seems lengthy it is still quicker than doing this by hand with thousands of lines.   


Getting gr2 and mat file names

After a game update extract the index.xml files from the tor archives and run them through the steps below in Notepad++ 

these are some example index.xml files 
/art/dynamic/boot/index.xml
/art/dynamic/bracer/index.xml
/art/dynamic/chest/index.xml
/art/dynamic/creature/index.xml
/art/dynamic/face/index.xml
/art/dynamic/facehair/index.xml
/art/dynamic/hair/index.xml
/art/dynamic/hand/index.xml
/art/dynamic/head/index.xml
/art/dynamic/leg/index.xml
/art/dynamic/waist/index.xml


Open an index.xml in Notepad++
Press ctrl+h

1. Keep lines containing /art/
Find and replace all in "Regular expression" search mode:

Find what:
(?!^.*/art/.*$)^.+
Replace with:


give it some time to perform the task
then go to Edit > Line Operations > Remove Empty Lines (Containing Blank characters)


2. Remove anything before /art/
Find and replace all in "Regular expression" search mode:

Find what:
.+(\/art/)
Replace with:
\1


3. Remove anything after gr2
Find and replace all in "Regular expression" search mode:

Find what:
^(.*?gr2).*$
Replace with:
\1


Remove anything after .mat
Find and replace all in "Normal" search mode:

Find what:
">
Replace with:


The general rule here is to at least have each line formatted correctly regardless of what file type is listed or you might not get those names. If there is a .fx file for example then you'll need to do a search and replace for anything after that.


4. Add /resources to the beginning of each line
Find and replace all in "Normal" search mode:

Find what:
/art/
Replace with:
/resources/art/


The paths in the file are now correct but the file is still not ready.


5. You will see some names with [bt] and [gen] in them
[bt] is body type, i just search and replace all of these with bmn (male body type 2) because i think the others look cartooney 
[gen] is gender, i just search and replace all of these with m for male because i don't care for the other version of armor. 
This may affect some female only armors not being named but it won't harm anything. 

You will need to adjust these based on what body type and gender you want or you can make a copy and change the gender and body type in multiple copies to check against in EasyMYP. There might be an easier way but i have not researched that far yet.


6. Rename the index.xml to index.txt
Now launch EasyMYP and go to Dictionary > Test Full Filename List and find your index.txt file to check for new names in it.
After the new names are found just close EasyMYP and it will automatically add the new names to hashes_filename.txt with proper formatting.
Only found names will be added to hashes_filename.txt
Now you can launch EasyMYP and extract files from the tor archive with names. 






Getting texture names from named or unnamed mat files

1. Download and install this Combine plugin for Notepad++
[http://www.scout-soft.com/combine/](http://www.scout-soft.com/combine/)

Go into a mat folder and ctrl+a then right click and Edit with Notepad++ to open all files at once
Go to Plugins > Combine > Start and press OK
The contents of all opened mat files are now copied into the same file for processing


2. Press ctrl+f and click on the Mark tab
make sure "Bookmark line" is ticked and you are in "Normal" search mode:

Find what:
art\dynamic

press "Mark All"

Go to Search > Bookmark > Remove Unmarked Lines
at this point you can Clear all marks in the Mark tab to make the document easier to look at

Go to Edit > Blank Operations > Trim Leading Space


3. Switch to the Replace tab and replace all in "Normal" search mode 
Find what:
<value>
Replace with:
\resources\

Find what:
</value>
Replace with:
.dds

save the file then check it for new names with EasyMYP like you did for the index.txt files.






Also, because i don't care for anything in this game other than models and textures, i'll remove anything that isn't .gr2, .mat, .dds, .xml and anything with .lod. or .tiny (because i want only the highest res mesh and textures) from the hashes_filename.txt file so i have less to sort through after extraction or while browsing the tor in EasyMYP. 
I hope this helps someone.
## Post #313
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-10-26T17:30:18+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

That method works really great! Obviously it misses out the textures, but those can be found from the mat files anyway, thank you for explaining that!
However, the macro didn't work for me (it would only place /resources/ at the first line) so I just used the replace function to replace /art/ with /resources/art/
## Post #314
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-10-26T17:38:11+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from TRDaz
>
> ... I just used the replace function to replace /art/ with /resources/art/

Thanks for the feedback!  I think search and replace is probably better anyway, i'll change the macro part to that.
## Post #315
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2015-10-26T19:53:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Doctor Loboto
>
> Hey all, I've been perusing this thread regularly, searching for some help for my project. I want to extract the models and textures of the various 'forms' of Emperor Vitiate, starting with his most 'human' appearance. Can someone point me in the right direction, or let me know what files I should be looking for?

This again, I still can't figure out where to even start searching for him...
## Post #316
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-10-27T19:42:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

If you're looking for an easy way to find outfit sets, you will be disappointed. 
Sometimes you get lucky and the set might have the character name in the filename like shae or thexen, but most of them have an alpha numeric outfit ID like a09 for example. 
I usually start with an image of the outfit then i browse through the models, usually the helmet or chest piece first until i find something that looks the same and take note of the outfit ID. If the gr2 file has no name you can open it with a hex editor and look near the bottom for the outfit ID and follow the breadcrumbs to get the rest of the outfit.
## Post #317
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2015-10-27T21:59:25+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

So in your opinion which should I start with, like, folder wise?

Moreover...can you uh...give a tutorial of sorts for extraction, like what program to use for the .tor archives, an updated hashlist, and how to extract models properly? Apparently I've been doing it wrong.
## Post #318
- Username: KaosXIV
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 07, 2014 6:28 am
- Post datetime: 2015-10-28T00:42:10+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Doctor Loboto
>
> Hey all, I've been perusing this thread regularly, searching for some help for my project. I want to extract the models and textures of the various 'forms' of Emperor Vitiate, starting with his most 'human' appearance. Can someone point me in the right direction, or let me know what files I should be looking for?
[http://swtor.jedipedia.net/en/npc/the-emperor](http://swtor.jedipedia.net/en/npc/the-emperor)
[http://swtor.jedipedia.net/en/npc/the-emperor-7](http://swtor.jedipedia.net/en/npc/the-emperor-7)
[http://swtor.jedipedia.net/en/npc/vitiate-2](http://swtor.jedipedia.net/en/npc/vitiate-2)
[http://swtor.jedipedia.net/en/npc/vitiate](http://swtor.jedipedia.net/en/npc/vitiate)

There's probably more there, but that should be what you want.
## Post #319
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2015-10-28T12:17:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Awesome, that really helps!

Now sorry if this is an annoying question, but which is the most updated hash list?

Also, a download for EasyMYP 3.6? The past ones aren't working. I keep getting an exception error.
## Post #320
- Username: vertalius
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Mar 05, 2014 3:08 am
- Post datetime: 2015-10-29T05:28:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I'm certainly not an expert but you might get an error because Bioware changed the structure of the files since the patch 4.x as the new addon was released. Someone warned about this few post (or pages?)  ago, so you have to find somewhere old client (version <4.x) while waiting for the new extractor, if someone will recompile it.
## Post #321
- Username: KaosXIV
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 07, 2014 6:28 am
- Post datetime: 2015-10-29T10:19:11+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from vertalius
>
> I'm certainly not an expert but you might get an error because Bioware changed the structure of the files since the patch 4.x as the new addon was released. Someone warned about this few post (or pages?)  ago, so you have to find somewhere old client (version <4.x) while waiting for the new extractor, if someone will recompile it.
This is half true, the format of the Area files was changed, the models etc. remain the same.
I'm still able to extract everything like normal, but the area.dat files are now in a binary format.
## Post #322
- Username: Amzadi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 09, 2013 1:26 am
- Post datetime: 2015-10-31T23:46:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi, long time lurker.

I have been wondering if anyone has found an easier way to find the likes of static and non character dynamic model names, other than looking through Noesis, one model at a time trying to guess what the name and directory might be from the node data?

So far I have not found anything like the index.xml files and it is driving me crazy at the moment.

Regards,
## Post #323
- Username: LordJypx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 15, 2015 3:49 am
- Post datetime: 2015-11-14T21:12:28+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

where to Download : EasyMYP?
## Post #324
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-11-15T09:15:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Amzadi
>
> I have been wondering if anyone has found an easier way to find the likes of static and non character dynamic model names...
Nope, i wish there was. maybe one of the other guys posting in this thread will eventually share their name-finding tools but i won't get my hopes up.   




just for kicks and practice with Hex2obj   
veh_imp_walker_prototype_a01.gr2
## Post #325
- Username: SithAssassin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 15, 2015 3:23 am
- Post datetime: 2015-11-15T13:01:32+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey, I have been looking for ways to extract models from this game for a long time, could anyone give me a tutorial on how to find the gr2 files? I have extracted multiple .tor files, but none of them seem to contain any .gr2 files. Sorry for my ignorance concerning this topic.
## Post #326
- Username: Kualan
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 27, 2015 4:23 am
- Post datetime: 2015-11-25T20:27:16+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I bought a new PC recently, and only just got around to trying to tinker around with SWTOR again. I redownloaded the EasyMYP files from this thread (the latest version) and the up-to-date hash file, but now every time I try to open a .tor file EasyMYP runs into an unhandled exception error? I can see from this thread that others have run into this issue in the past but the solution was never actually posted - anyone able to enlighten me? Hope you can help!
## Post #327
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2015-12-02T18:04:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi,
Iam searching the following model/ship/vehicle in the .tor files  of swtor:

X-70B Phantom (Imperial Agent Ship)

I found this only as mini-model in swtor_main_art_vehicle_1.tor, but its a very low poly model.
Does someone find a high-poly version of this model or anybody knows, if there are many models not included in the standard download of the game??

Regards,
olli
## Post #328
- Username: barabelmaster
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 02, 2015 8:47 am
- Post datetime: 2015-12-02T20:09:43+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey I have easy myp and can open .tor files but there are no models in my files, is there anyway to get them, I am trying to export alien heads as well as the hair models for humans in the game, how can I get models out?? Thank you
## Post #329
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-12-03T00:09:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from olli9000
>
> Iam searching the following model/ship/vehicle in the .tor files  of swtor:
X-70B Phantom (Imperial Agent Ship)
Does someone find a high-poly version of this model ....
The higher poly player ships are in this folder after extraction
\resources\art\static\area\spc_space\playership

i don't remember which tor file they are stored in though   


@barabelmaster
EasyMyp extracts everything from the tor file whether it is named or not, maybe check the unnamed files for gr2 extension?
## Post #330
- Username: barabelmaster
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 02, 2015 8:47 am
- Post datetime: 2015-12-03T04:45:54+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from AceWell
>
> olli9000 wrote:Iam searching the following model/ship/vehicle in the .tor files  of swtor:
X-70B Phantom (Imperial Agent Ship)
Does someone find a high-poly version of this model ....
The higher poly player ships are in this folder after extraction
\resources\art\static\area\spc_space\playership

i don't remember which tor file they are stored in though   


@barabelmaster
EasyMyp extracts everything from the tor file whether it is named or not, maybe check the unnamed files for gr2 extension?

Yeah I have extracted all the files and the only folders there are; are dds xml and text all with files of that format
## Post #331
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-12-03T05:36:37+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Sorry i don't know then, try running it with Dependency Walker and see if your system is missing libraries or something.

[http://www.dependencywalker.com/](http://www.dependencywalker.com/)
## Post #332
- Username: barabelmaster
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 02, 2015 8:47 am
- Post datetime: 2015-12-03T17:00:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from AceWell
>
> Sorry i don't know then, try running it with Dependency Walker and see if your system is missing libraries or something.

http://www.dependencywalker.com/
 I will try that! Thank you! I should export an archive to test correct?
## Post #333
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2015-12-03T19:08:55+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Many thanks! You are welcome! I dont know, if there are all ships in that folder, but that what iam looking for is there. =)
## Post #334
- Username: Talgalar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 17, 2015 2:06 am
- Post datetime: 2015-12-23T15:01:25+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello !

I try to understand what you said Acewell about : Getting gr2 and mat file names
So I opened one of this index to find a Zakel knight helmet so : face_gehelmet69_bmn_archetype
I find it in the index but I didn't have to change anything, but the model doesn't appear in noesis. So what can I do ?
Because I would like to have a Zakel knight 

[](http://www.hostingpics.net/viewer.php?id=514695SWTOR1.png)
## Post #335
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-12-23T17:46:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I'm sorry but i don't know what you are asking, everything i do is typed up in that post in the simplest way i could think of.
## Post #336
- Username: Alianin
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 28, 2012 12:07 am
- Post datetime: 2015-12-27T18:51:44+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Still have a ways to go, but I thought I'd throw out an updated hashlist. This includes all the new files from earlier in the thread as well as 92 icon filenames I found. If I'm calculating it correctly, that still leaves 17% of unknown filenames (106,453).

[https://www.dropbox.com/s/q9yf4ugffudi7 ... e.zip?dl=0](https://www.dropbox.com/s/q9yf4ugffudi7k1/hashes_filename.zip?dl=0)
## Post #337
- Username: TheNoblePeanut
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 29, 2015 4:25 am
- Post datetime: 2015-12-28T21:00:00+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Not sure if this is the correct place to post this, but I've been fighting for hours to extract AUDIO/SFX files from SWTOR, but it seems everything is working against me. Has anybody successfully done this? And if so, is there any way I could persuade you to upload the sounds to some file server and PM me a link?
## Post #338
- Username: SquigglyV
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 06, 2016 11:14 am
- Post datetime: 2016-01-08T18:44:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello, i'm having a problem where there are no models in my .tor files. I extract them with EasyMYP but the only things inside are folders with .dds, .txt, .xml, or a few other file types. I can't find a single .gr2 file in any of the archives. I installed Dependency Walker because of an earlier post here but I couldn't figure out how to check for missing libraries or anything like that. If it helps, i'm specifically looking for all the starship models (transports from warzones, class ships, space mission enemies, landed ships on planets, etc).
## Post #339
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-09T03:15:55+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I don't know why some of you can't extract the gr2 files with easyMYP anymore but i suppose you could try the bms script posted on the first page of this thread to extract them. If it doesn't work i'm sure someone could fix it right up. 


It is also disheartening to see there is a nice looking model viewer for this game that isn't being shared. 
[http://i.imgur.com/mZRSu9K.png](http://i.imgur.com/mZRSu9K.png)
I'm pretty sure that program wouldn't be possible without some of the knowledge posted here and an efficient model viewer is exactly what is needed given how many files this game has.
## Post #340
- Username: SquigglyV
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 06, 2016 11:14 am
- Post datetime: 2016-01-09T05:14:05+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I got this error with that script in QuickBMS: [http://imgur.com/CytnGqz](http://imgur.com/CytnGqz)

I found another script when trying to fix that, and ended up with a different error when using it: [http://imgur.com/6GNXxY2](http://imgur.com/6GNXxY2)

I can post the new script if it might help, I have almost no experience in coding so I can't see if something is wrong in it.
## Post #341
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-09T05:19:21+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I posted a thread on Zenhax to see if aluigi can update [chrrox's script from the first page](http://forum.xentax.com/viewtopic.php?p=57937#p57937), i will post it here if/when it gets fixed.

edit
No luck yet with an update to the script but since chrrox says tor files are zlib compressed i figured offzip will work and i was able to test extract 229 files from swtor_main_zed_1.tor like this
offzip.exe -a swtor_main_zed_1.tor C:\offzip\extracted_files 0

Your gr2 files will extract with a gaw extension but you can just rename them and import into Noesis.
## Post #342
- Username: SquigglyV
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 06, 2016 11:14 am
- Post datetime: 2016-01-13T03:30:22+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Using offzip seems to work quite well for me, I got the .gaw/.gr2 files from it and I can view them in Noesis. Well there's no textures but I was able to get those with EasyMYP. Thanks for the help!

And I have a semi-related question, are there any complete npc models (generic ones like sith, dancers, jedi, etc.) in the files or are they all assembled in-game from the different head/body/armor pieces?

EDIT
Ok I was wrong. Stuff extracted with offzip doesn't play well with the .gr2 plugin i'm using in noesis, the extracted files are strangely named, and I cannot for the life of me get any textures matched to their models.
## Post #343
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2016-01-13T18:25:11+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I believe they are all assembled through the armor/head/body files. I haven't seen any compiled npcs other than the main npcs from Knights of the Fallen Empire.
## Post #344
- Username: SquigglyV
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 06, 2016 11:14 am
- Post datetime: 2016-01-19T01:26:27+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from TRDaz
>
> I haven't seen any compiled npcs other than the main npcs from Knights of the Fallen Empire.

Including Lana, HK-55, and the other new companions? If so, do you know what archive they're in?
## Post #345
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-19T02:48:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SquigglyV
>
> Ok I was wrong. Stuff extracted with offzip doesn't play well with the .gr2 plugin i'm using in noesis, the extracted files are strangely named, and I cannot for the life of me get any textures matched to their models.
You shouldn't be having problems opening gr2 files, i tested those files myself with swtor miner and vindis plugin. 
The textures aren't going to show up in Noesis 100% of the time even if the path is set right in the config file and the textures won't show up if using vindis plugin if they are not in the same folder as the gr2 file, and even still some may not show up because of how the devs named them. 
The files extracted with offzip bypass the hash name algorithm and are named by the position it was stored in the tor file. That is just how it is when using this method of extraction. 
I still don't understand how you can extract everything from tor files with EasyMYP except for gr2 files. Are you using an old version of it or something?

try the one linked here
[viewtopic.php?p=99890#p99890](http://forum.xentax.com/viewtopic.php?p=99890#p99890)


vindis gr2 plugin
[viewtopic.php?p=83383#p83383](http://forum.xentax.com/viewtopic.php?p=83383#p83383)

swtor miner gr2 plugin
[viewtopic.php?p=94880#p94880](http://forum.xentax.com/viewtopic.php?p=94880#p94880)
## Post #346
- Username: SquigglyV
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 06, 2016 11:14 am
- Post datetime: 2016-01-19T04:20:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Oh yay i'm an idiot, EasyMYP was outdated. That version of it seems to be working fine, and I haven't had another error in Noesis yet. Thanks for the help again.
## Post #347
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2016-01-19T14:18:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SquigglyV
>
> TRDaz wrote:I haven't seen any compiled npcs other than the main npcs from Knights of the Fallen Empire.

Including Lana, HK-55, and the other new companions? If so, do you know what archive they're in?
I believe all are in swtor_main_art_creature_a_1. HK-55 uses HK-51's mesh, but with a different texture. Lana, Arcann, Vaylin, Valkorion, Koth, Senya and new Satele are all in that and don't need to be compiled with player items.
## Post #348
- Username: Nengalore
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 26, 2015 2:34 am
- Post datetime: 2016-03-02T16:15:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Well, I can't figure out garment hues, is it possible to modify the diffuse texture using the garment hue and palette mask files?
## Post #349
- Username: swtor2316
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Feb 11, 2016 9:55 pm
- Post datetime: 2016-03-07T18:27:08+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi,

Do you know why I have an error ( unable to convert undefined to type: float ) when I load the model of a spaceship with the plugin SWTOR.ms on 3DS Max? I have no this error with a character but only with a vehicle or a static object.

Thanks in advance
## Post #350
- Username: Nengalore
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 26, 2015 2:34 am
- Post datetime: 2016-03-08T00:08:37+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor2316
>
> Hi,

Do you know why I have an error ( unable to convert undefined to type: float ) when I load the model of a spaceship with the plugin SWTOR.ms on 3DS Max? I have no this error with a character but only with a vehicle or a static object.

Thanks in advance

What version of 3ds Max are you using?
If it's a static object, you can load it into Noesis, and export it to a different format, then load that into Max.
## Post #351
- Username: swtor2316
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Feb 11, 2016 9:55 pm
- Post datetime: 2016-03-09T12:52:18+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Nengalore
>
> swtor2316 wrote:Hi,

Do you know why I have an error ( unable to convert undefined to type: float ) when I load the model of a spaceship with the plugin SWTOR.ms on 3DS Max? I have no this error with a character but only with a vehicle or a static object.

Thanks in advance

What version of 3ds Max are you using?
If it's a static object, you can load it into Noesis, and export it to a different format, then load that into Max.

Thanks for your answer. I use 3DS Max 9.
## Post #352
- Username: Nengalore
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 26, 2015 2:34 am
- Post datetime: 2016-03-09T14:21:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor2316
>
> I use 3DS Max 9.

As far as I know, the script only works for Max 2009-2011.
Then again, I haven't tried the script with any vehicles.
## Post #353
- Username: swtor2316
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Feb 11, 2016 9:55 pm
- Post datetime: 2016-03-09T15:06:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Nengalore
>
> swtor2316 wrote:I use 3DS Max 9.

As far as I know, the script only works for Max 2009-2011.
Then again, I haven't tried the script with any vehicles.

Okay thus that should work on my version but it does not work for vehicles. Would you have a link to download Noesis ?
## Post #354
- Username: Nengalore
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 26, 2015 2:34 am
- Post datetime: 2016-03-09T18:14:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor2316
>
> Would you have a link to download Noesis?

Download Noesis [here](http://richwhitehouse.com/index.php?content=inc_projects.php&filemirror=noesisv4177.zip)
And the SWTOR plugin for Noesis [here](http://forum.xentax.com/download/file.php?id=7380)

For the plugin:
After installing Noesis, extract the files to your Noesis plugin folder, (in my case, C:\Program Files (x86)\NoEsiS 3d models tool\plugins\python).
Then run Noesis and find your SWTOR files, you can preview and export them.

Hope this helps.
## Post #355
- Username: swtor2316
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Feb 11, 2016 9:55 pm
- Post datetime: 2016-03-09T19:20:47+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Nengalore
>
> swtor2316 wrote:Would you have a link to download Noesis?

Download Noesis here
And the SWTOR plugin for Noesis here

For the plugin:
After installing Noesis, extract the files to your Noesis plugin folder, (in my case, C:\Program Files (x86)\NoEsiS 3d models tool\plugins\python).
Then run Noesis and find your SWTOR files, you can preview and export them.

Hope this helps.

Thanks so much !
It is a reliable program ?
## Post #356
- Username: Nengalore
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 26, 2015 2:34 am
- Post datetime: 2016-03-09T21:17:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor2316
>
> It is a reliable program ?

Yes, the only problem is that the models from Noesis are at a different scale than the ones that are imported into Max.
## Post #357
- Username: swtor2316
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Feb 11, 2016 9:55 pm
- Post datetime: 2016-03-10T14:13:47+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Nengalore
>
> swtor2316 wrote:It is a reliable program ?

Yes, the only problem is that the models from Noesis are at a different scale than the ones that are imported into Max.

I tested this software, it is practical but many elements are not exported. I have the model but not the textures... There is a tutoriel to use well this software?
## Post #358
- Username: Nengalore
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 26, 2015 2:34 am
- Post datetime: 2016-03-10T14:16:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor2316
>
> I tested this software, it is practical but many elements are not exported. I have the model but not the textures... There is a tutorial to use well this software?

The textures will not be exported in 3DS Max, either, you have to find them yourself in the texture folders.
## Post #359
- Username: swtor2316
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Feb 11, 2016 9:55 pm
- Post datetime: 2016-03-10T14:38:27+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Nengalore
>
> swtor2316 wrote:I tested this software, it is practical but many elements are not exported. I have the model but not the textures... There is a tutorial to use well this software?

The textures will not be exported in 3DS Max, either, you have to find them yourself in the texture folders.

Ah okay, thanks for this information. And animations, can they be exported ?
## Post #360
- Username: Nengalore
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 26, 2015 2:34 am
- Post datetime: 2016-03-10T14:42:08+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor2316
>
> And animations, can they be exported ?

The .jba animation files currently cannot be used, as far as I know, there is no way to use the animations, sorry.
## Post #361
- Username: swtor2316
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Feb 11, 2016 9:55 pm
- Post datetime: 2016-03-10T14:48:32+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Nengalore
>
> swtor2316 wrote:And animations, can they be exported ?

The .jba animation files currently cannot be used, as far as I know, there is no way to use the animations, sorry.

Thanks, I did not know. What a pity !
## Post #362
- Username: swtor2316
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Feb 11, 2016 9:55 pm
- Post datetime: 2016-03-10T15:06:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Nengalore
>
> swtor2316 wrote:And animations, can they be exported ?

The .jba animation files currently cannot be used, as far as I know, there is no way to use the animations, sorry.

By chance, do you know where is the model 3d of the cruiser of the eternal empire in .tor archive ?
## Post #363
- Username: Nengalore
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 26, 2015 2:34 am
- Post datetime: 2016-03-10T15:10:05+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor2316
>
> By chance, do you know where is the model 3d of the cruiser of the eternal empire in .tor archive ?
I do not, sorry.
## Post #364
- Username: probe
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 05, 2012 4:59 am
- Post datetime: 2016-04-17T19:50:51+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Can I use that tool to replace malgus textures? (Original armor to item)
## Post #365
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2016-04-30T10:00:18+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello there!!! People, does anyone have textures for Shae Vizla or hash_ names for this model and its resources?
## Post #366
- Username: Max Orchibay
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 21, 2016 8:13 am
- Post datetime: 2016-06-21T00:27:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

hello, trying to extract the files from Havoc said armor I get this error:
See the end of this message for details on how to invoke debugging
Just-In-Time (JIT) debugging instead of this dialog box.

************** ************** Exception text
System.NullReferenceException: Object reference not set to an instance of an object.
   in EasyMYP.MainWindow.contextMenuStripFileSystemTreeView_ItemClicked (Object sender, ToolStripItemClickedEventArgs e) in C: \ Code \ Personal \ SWTOR ripper \ EasyMYP \ EasyMYP \ MainWindow_Delegates_Events.cs: line 622
   in System.Windows.Forms.ToolStrip.OnItemClicked (ToolStripItemClickedEventArgs e)
   in System.Windows.Forms.ToolStripDropDown.OnItemClicked (ToolStripItemClickedEventArgs e)
   in System.Windows.Forms.ToolStrip.HandleItemClick (ToolStripItem dismissingItem)
   in System.Windows.Forms.ToolStripItem.HandleClick (EventArgs e)
   in System.Windows.Forms.ToolStripItem.HandleMouseUp (MouseEventArgs e)
   in System.Windows.Forms.ToolStripItem.FireEventInteractive (EventArgs e, ToolStripItemEventType meth)
   in System.Windows.Forms.ToolStripItem.FireEvent (EventArgs e, ToolStripItemEventType meth)
   in System.Windows.Forms.ToolStrip.OnMouseUp (MouseEventArgs mea)
   in System.Windows.Forms.ToolStripDropDown.OnMouseUp (MouseEventArgs mea)
   in System.Windows.Forms.Control.WmMouseUp (Message & m, MouseButtons button, Int32 clicks)
   in System.Windows.Forms.Control.WndProc (Message & m)
   in System.Windows.Forms.ScrollableControl.WndProc (Message & m)
   in System.Windows.Forms.ToolStrip.WndProc (Message & m)
   in System.Windows.Forms.ToolStripDropDown.WndProc (Message & m)
   in System.Windows.Forms.Control.ControlNativeWindow.OnMessage (Message & m)
   in System.Windows.Forms.Control.ControlNativeWindow.WndProc (Message & m)
   in System.Windows.Forms.NativeWindow.Callback (IntPtr hWnd, Int32 msg, IntPtr wParam, IntPtr lParam)


************** ************** Loaded Assembled
mscorlib
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5485 (Win7SP1GDR.050727-5400)
    codebase: file: /// C: /Windows/Microsoft.NET/Framework/v2.0.50727/mscorlib.dll
----------------------------------------
EasyMYP
    Assembly version: 1.0.0.0
    1.0.0.0: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/EasyMYP.exe
----------------------------------------
System.Windows.Forms
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5491 (Win7SP1GDR.050727-5400)
    codebase: file:///C:/Windows/assembly/GAC_MSIL/System.Windows.Forms/2.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5485 (Win7SP1GDR.050727-5400)
    codebase: file: /// C: /Windows/assembly/GAC_MSIL/System/2.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Drawing
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5495 (Win7SP1GDR.050727-5400)
    codebase: file: /// C: /Windows/assembly/GAC_MSIL/System.Drawing/2.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
MYPHandler
    Assembly version: 1.0.0.0
    1.0.0.0: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/MYPHandler.DLL
----------------------------------------
HashDictionary
    Assembly version: 1.0.0.0
    1.0.0.0: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/HashDictionary.DLL
----------------------------------------
HashCreator
    Assembly version: 1.0.0.0
    1.0.0.0: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/HashCreator.DLL
----------------------------------------
System.Core
    Assembly version: 3.5.0.0
    Win32 version: 3.5.30729.5420 built by: Win7SP1
    codebase: file: /// C: /Windows/assembly/GAC_MSIL/System.Core/3.5.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
WarhammerOnlineHash
    Assembly version: 1.0.0.0
    1.0.0.0: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/WarhammerOnlineHash.DLL
----------------------------------------
System.Windows.Forms.resources
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5420 (Win7SP1.050727-5400)
    codebase: file:///C:/Windows/assembly/GAC_MSIL/System.Windows.Forms.resources/2.0.0.0_es_b77a5c561934e089/System.Windows.Forms.resources.dll
----------------------------------------
mscorlib.resources
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5485 (Win7SP1GDR.050727-5400)
    codebase: file: /// C: /Windows/Microsoft.NET/Framework/v2.0.50727/mscorlib.dll
----------------------------------------
System.Configuration
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5483 (Win7SP1GDR.050727-5400)
    codebase: file:///C:/Windows/assembly/GAC_MSIL/System.Configuration/2.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Management
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5483 (Win7SP1GDR.050727-5400)
    codebase: file:///C:/Windows/assembly/GAC_MSIL/System.Management/2.0.0.0__b03f5f7f11d50a3a/System.Management.dll
----------------------------------------
System.Xml
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5494 (Win7SP1GDR.050727-5400)
    codebase: file: /// C: /Windows/assembly/GAC_MSIL/System.Xml/2.0.0.0__b77a5c561934e089/System.Xml.dll
----------------------------------------
ICSharpCode.SharpZipLib
    Assembly version: 0.85.4.369
    0.85.4.369: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/ICSharpCode.SharpZipLib.DLL
----------------------------------------

************** ************** JIT Debugging
To enable debugging Just In Time (JIT), the configuration file of this
application or computer (machine.config) must have the
jitDebugging value established in the system.windows.forms section.
The application must also be compiled with debugging
enabled

For example:

<Configuration>
    <System.windows.forms jitDebugging = "true" />
</ Configuration>

When JIT debugging is enabled, any unhandled exception
JIT debugger registered will be sent on the computer
rather than be handled by this dialog box.


Can somebody help me? or at least spend the .gr2 files?
Thanks  
Google translate
## Post #367
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2016-06-26T18:37:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

It's summer and not Chrismas but here is your present.

[hashes_filename.rar](http://www.file-upload.net/download-11714188/hashes_filename.rar.html)
## Post #368
- Username: Kualan
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 27, 2015 4:23 am
- Post datetime: 2016-07-01T13:04:16+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> It's summer and not Chrismas but here is your present.

hashes_filename.rar

Nice! Thanks man.
## Post #369
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2016-07-05T18:08:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> It's summer and not Chrismas but here is your present.

hashes_filename.rar

You are my savior!! thank you very much!!
## Post #370
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2016-08-13T13:28:48+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey gues,
I was boring and had some time.

All Body Parts are encoded. (Dynamic stuff without mags)
Only some txt files are missing, but nobody need them.

This time you can't copy the list into the Hash folder. You have to check it against the assets.
I do it this way, because you can't overwrite your work. (diffrent languages or something I don't have in my list)

If somebody know a way how to export only the latest hashes, please let me know.

Have fun and best regards from germany,

Ferouc


[hashes_filename-Kopie.rar](http://www.file-upload.net/download-11846100/hashes_filename-Kopie.rar.html)


edit:
I did some extra work and figured out a way to export my new hashes. (very ugly process)
The rar contains 3 files. The first one contains the new hashes from above, the other two are 20k new hashes since yesterday.
[hashes.rar](http://www.file-upload.net/download-11850336/hashes.rar.html)
## Post #371
- Username: vonnika
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 25, 2014 5:30 am
- Post datetime: 2016-08-14T21:30:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> Hey gues,
I was boring and had some time.

All Body Parts are encoded. (Dynamic stuff without mags)
Only some txt files are missing, but nobody need them.

This time you can't copy the list into the Hash folder. You have to check it against the assets.
I do it this way, because you can't overwrite your work. (diffrent languages or something I don't have in my list)

If somebody know a way how to export only the latest hashes, please let me know.

Have fun and best regards from germany,

Ferouc


hashes_filename-Kopie.rar

Thank you! Vielen Dank!
## Post #372
- Username: Kualan
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 27, 2015 4:23 am
- Post datetime: 2016-08-26T17:01:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> Hey gues,
I was boring and had some time.

All Body Parts are encoded. (Dynamic stuff without mags)
Only some txt files are missing, but nobody need them.

This time you can't copy the list into the Hash folder. You have to check it against the assets.
I do it this way, because you can't overwrite your work. (diffrent languages or something I don't have in my list)

If somebody know a way how to export only the latest hashes, please let me know.

Have fun and best regards from germany,

Ferouc


hashes_filename-Kopie.rar


edit:
I did some extra work and figured out a way to export my new hashes. (very ugly process)
The rar contains 3 files. The first one contains the new hashes from above, the other two are 20k new hashes since yesterday.
hashes.rar

Excellent work, really appreciate it.
## Post #373
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2016-09-04T09:39:00+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

A short post, not much time in the next future so you get my new Hashes.

I looked after the bodyparts and I'm nearly finished.

Only in the swtor_main_art_dynamic_face_1 archive are 6 texture files unnamed.

The weapon archive is tricky. I checked all combinations for known filenames, extensions und paths that have shown up in this archive, but I got no new name.
[new Hashes 4.rar](https://xentaxbackup.github.io/file/11658_new Hashes 4.rar)
## Post #374
- Username: IronE
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 24, 2016 6:42 am
- Post datetime: 2016-10-23T22:49:35+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey guys, I'm looking for all the sounds files (SFX, Music, Dialogue, etc) from SWTOR, but having issues with the whole extracting and conversion. So I was just wondering if anyone had them on hand? Thanks!
## Post #375
- Username: cmdrzoom
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 02, 2016 4:06 am
- Post datetime: 2016-12-01T20:37:48+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello, board.  I have a somewhat odd request/question, about replacing a model/texture ... no, not a "nude mod".  Something less smutty and more OCD than that.
The latest update (5.0) changed, among other things that didn't really need changing, Lana Beniko's face.  Again.  I'm really not a fan of her new look, and I'd like to swap in the old model/texture, if only for finishing up the KotFE content on those characters who haven't (which is my fault for putting it off, I know), but I've run into the limits of my own file-modding expertise.

From a friend who hadn't yet updated, I got a copy of the old main_art_creature_a_1 file (which, among other characters and critters, contains Lana and most of the other KotFE npcs - my thanks to the earlier poster on this thread who mentioned that was where they were located).  Unfortunately, while the game loads with no complaints with this file in place of the new one, something in the way animations are now handled causes all characters to flip face-down when they're the one speaking during cut-scenes.  So that's not gonna work.  (I tried swapping all the anim_humanoid files too, but that didn't seem to help.  )
I also tried opening a copy of the new art file (with EasyMYP) and replacing all the .tex and .dds files for the "new" Lana with those I'd extracted from the older archive.  That didn't work either, possibly because it changed the filesize of the archive; the client refused to load, giving me a C5 error.

So, as I said, I'm at my limit.  But before I just give up (maybe on SWTOR entirely ... it's one of those "just one more little thing" situations for me right now) and/or try to force myself to accept it, I thought I'd turn to the more experienced archive divers here to find out what I'm doing wrong and, ideally, do it right.
Apologies in advance if I'm posting in the wrong place, or something that shouldn't be asked at all.
## Post #376
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-01-17T09:52:02+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I've been looking to extract different sets of armor lately, and also some characters like Shae Vizla and Revan, however I encountered a problem. In both cases, the hash list apparently has the files I need listed, however when I check in EasyMYP those files are nowhere to be found. For example Shae's helmet textures (face_gehelmet50_heavy_ge_a59shae01_u) seem to be in the hash list but I can't see the folder. Nor can I find Revan's outfit textures or Ajunta Pall textures like chest_longsleeve_light_ge_mtx58ajunta01_u. The mat files are there, but the textures aren't, I added the Ajunta Pall ones to a new hash list but it doesn't find them. Any idea why this is happening or are they stored in some weird .tor file?
## Post #377
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2017-03-13T14:47:56+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi!  I have a question. Where, in the game I can find prop model names for the hash_file? (Furniture, weapons, stronghold structures)
## Post #378
- Username: Farrarie
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Mar 19, 2017 6:00 pm
- Post datetime: 2017-03-25T22:23:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

hello guys im a total newbie
where I can find the imperial command bridge .gr2 parts?
and is there a hash that have it ?
## Post #379
- Username: SultanaVerena
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 02, 2017 1:35 am
- Post datetime: 2017-04-01T17:49:46+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Disregard. I have figured it all out.
## Post #380
- Username: Kualan
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 27, 2015 4:23 am
- Post datetime: 2017-04-30T08:39:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Coming back to this game after a long while - anybody have a more up to date hashlist they'd be happy to share?
## Post #381
- Username: twilight
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 06, 2017 10:03 am
- Post datetime: 2017-05-06T06:10:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Max Orchibay
>
> hello, trying to extract the files from Havoc said armor I get this error:
See the end of this message for details on how to invoke debugging
Just-In-Time (JIT) debugging instead of this dialog box.

************** ************** Exception text
System.NullReferenceException: Object reference not set to an instance of an object.
   in EasyMYP.MainWindow.contextMenuStripFileSystemTreeView_ItemClicked (Object sender, ToolStripItemClickedEventArgs e) in C: \ Code \ Personal \ SWTOR ripper \ EasyMYP \ EasyMYP \ MainWindow_Delegates_Events.cs: line 622
   in System.Windows.Forms.ToolStrip.OnItemClicked (ToolStripItemClickedEventArgs e)
   in System.Windows.Forms.ToolStripDropDown.OnItemClicked (ToolStripItemClickedEventArgs e)
   in System.Windows.Forms.ToolStrip.HandleItemClick (ToolStripItem dismissingItem)
   in System.Windows.Forms.ToolStripItem.HandleClick (EventArgs e)
   in System.Windows.Forms.ToolStripItem.HandleMouseUp (MouseEventArgs e)
   in System.Windows.Forms.ToolStripItem.FireEventInteractive (EventArgs e, ToolStripItemEventType meth)
   in System.Windows.Forms.ToolStripItem.FireEvent (EventArgs e, ToolStripItemEventType meth)
   in System.Windows.Forms.ToolStrip.OnMouseUp (MouseEventArgs mea)
   in System.Windows.Forms.ToolStripDropDown.OnMouseUp (MouseEventArgs mea)
   in System.Windows.Forms.Control.WmMouseUp (Message & m, MouseButtons button, Int32 clicks)
   in System.Windows.Forms.Control.WndProc (Message & m)
   in System.Windows.Forms.ScrollableControl.WndProc (Message & m)
   in System.Windows.Forms.ToolStrip.WndProc (Message & m)
   in System.Windows.Forms.ToolStripDropDown.WndProc (Message & m)
   in System.Windows.Forms.Control.ControlNativeWindow.OnMessage (Message & m)
   in System.Windows.Forms.Control.ControlNativeWindow.WndProc (Message & m)
   in System.Windows.Forms.NativeWindow.Callback (IntPtr hWnd, Int32 msg, IntPtr wParam, IntPtr lParam)


************** ************** Loaded Assembled
mscorlib
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5485 (Win7SP1GDR.050727-5400)
    codebase: file: /// C: /Windows/Microsoft.NET/Framework/v2.0.50727/mscorlib.dll
----------------------------------------
EasyMYP
    Assembly version: 1.0.0.0
    1.0.0.0: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/EasyMYP.exe
----------------------------------------
System.Windows.Forms
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5491 (Win7SP1GDR.050727-5400)
    codebase: file:///C:/Windows/assembly/GAC_MSIL/System.Windows.Forms/2.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5485 (Win7SP1GDR.050727-5400)
    codebase: file: /// C: /Windows/assembly/GAC_MSIL/System/2.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Drawing
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5495 (Win7SP1GDR.050727-5400)
    codebase: file: /// C: /Windows/assembly/GAC_MSIL/System.Drawing/2.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
MYPHandler
    Assembly version: 1.0.0.0
    1.0.0.0: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/MYPHandler.DLL
----------------------------------------
HashDictionary
    Assembly version: 1.0.0.0
    1.0.0.0: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/HashDictionary.DLL
----------------------------------------
HashCreator
    Assembly version: 1.0.0.0
    1.0.0.0: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/HashCreator.DLL
----------------------------------------
System.Core
    Assembly version: 3.5.0.0
    Win32 version: 3.5.30729.5420 built by: Win7SP1
    codebase: file: /// C: /Windows/assembly/GAC_MSIL/System.Core/3.5.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
WarhammerOnlineHash
    Assembly version: 1.0.0.0
    1.0.0.0: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/WarhammerOnlineHash.DLL
----------------------------------------
System.Windows.Forms.resources
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5420 (Win7SP1.050727-5400)
    codebase: file:///C:/Windows/assembly/GAC_MSIL/System.Windows.Forms.resources/2.0.0.0_es_b77a5c561934e089/System.Windows.Forms.resources.dll
----------------------------------------
mscorlib.resources
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5485 (Win7SP1GDR.050727-5400)
    codebase: file: /// C: /Windows/Microsoft.NET/Framework/v2.0.50727/mscorlib.dll
----------------------------------------
System.Configuration
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5483 (Win7SP1GDR.050727-5400)
    codebase: file:///C:/Windows/assembly/GAC_MSIL/System.Configuration/2.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Management
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5483 (Win7SP1GDR.050727-5400)
    codebase: file:///C:/Windows/assembly/GAC_MSIL/System.Management/2.0.0.0__b03f5f7f11d50a3a/System.Management.dll
----------------------------------------
System.Xml
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5494 (Win7SP1GDR.050727-5400)
    codebase: file: /// C: /Windows/assembly/GAC_MSIL/System.Xml/2.0.0.0__b77a5c561934e089/System.Xml.dll
----------------------------------------
ICSharpCode.SharpZipLib
    Assembly version: 0.85.4.369
    0.85.4.369: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/ICSharpCode.SharpZipLib.DLL
----------------------------------------

************** ************** JIT Debugging
To enable debugging Just In Time (JIT), the configuration file of this
application or computer (machine.config) must have the
jitDebugging value established in the system.windows.forms section.
The application must also be compiled with debugging
enabled

For example:

<Configuration>
    <System.windows.forms jitDebugging = "true" />
</ Configuration>

When JIT debugging is enabled, any unhandled exception
JIT debugger registered will be sent on the computer
rather than be handled by this dialog box.


Can somebody help me? or at least spend the .gr2 files?
Thanks  
Google translate

Hi,

I'm getting this error.  I've searched this thread and noticed similar errors but no solutions.  I've googled but the only solution I found was to check Framework (which is updated).

I was very excited to find this thread and discover there were actual tools to extract models from SWTOR.  Any help would be appreciated.
Thanks!
## Post #382
- Username: twilight
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 06, 2017 10:03 am
- Post datetime: 2017-05-06T14:06:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Yea...so I just put it on an old laptop I have - and it worked!  

So no need to respond
## Post #383
- Username: Cutsie33
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 01, 2017 5:46 am
- Post datetime: 2017-06-30T22:21:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Complete newbie here.  I came across this thread and others and have been trying to extract the model files but I must be going crazy.  Everytime I try and add the hashes_filename.txt file EasyMYP it crashes.  If I don't add it then I can open the .tor files but only see 3 folders, txt, xml and dds, I don't see anywhere that th.gr2 files are.  Am I just being stupid?  Also the hashes_filename.txt file I have is from 2012 so an updated one would probably be useful.  I also couldn't fine version 3.6 of EasyMYP and am using version 3.2.  Any help would be appreciated.  Thanks.
## Post #384
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2017-08-08T10:46:51+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Cutsie33
>
> Complete newbie here.  I came across this thread and others and have been trying to extract the model files but I must be going crazy.  Everytime I try and add the hashes_filename.txt file EasyMYP it crashes.  If I don't add it then I can open the .tor files but only see 3 folders, txt, xml and dds, I don't see anywhere that th.gr2 files are.  Am I just being stupid?  Also the hashes_filename.txt file I have is from 2012 so an updated one would probably be useful.  I also couldn't fine version 3.6 of EasyMYP and am using version 3.2.  Any help would be appreciated.  Thanks.

I had the same issue with EasyMYP, 'till I found out TorMYP is the way to go. I'll try to upload it for you, when I get access to my computer.
## Post #385
- Username: rithkhmer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 08, 2017 6:20 am
- Post datetime: 2017-08-08T21:20:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

thank for good post and sharing......

[ดูหนังออนไลน์](https://movie-review-2017.blogspot.com)
## Post #386
- Username: Graesholt
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Oct 16, 2017 9:02 pm
- Post datetime: 2017-10-17T05:48:52+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from twilight
>
> Max Orchibay wrote:hello, trying to extract the files from Havoc said armor I get this error:
See the end of this message for details on how to invoke debugging
Just-In-Time (JIT) debugging instead of this dialog box.

************** ************** Exception text
System.NullReferenceException: Object reference not set to an instance of an object.
   in EasyMYP.MainWindow.contextMenuStripFileSystemTreeView_ItemClicked (Object sender, ToolStripItemClickedEventArgs e) in C: \ Code \ Personal \ SWTOR ripper \ EasyMYP \ EasyMYP \ MainWindow_Delegates_Events.cs: line 622
   in System.Windows.Forms.ToolStrip.OnItemClicked (ToolStripItemClickedEventArgs e)
   in System.Windows.Forms.ToolStripDropDown.OnItemClicked (ToolStripItemClickedEventArgs e)
   in System.Windows.Forms.ToolStrip.HandleItemClick (ToolStripItem dismissingItem)
   in System.Windows.Forms.ToolStripItem.HandleClick (EventArgs e)
   in System.Windows.Forms.ToolStripItem.HandleMouseUp (MouseEventArgs e)
   in System.Windows.Forms.ToolStripItem.FireEventInteractive (EventArgs e, ToolStripItemEventType meth)
   in System.Windows.Forms.ToolStripItem.FireEvent (EventArgs e, ToolStripItemEventType meth)
   in System.Windows.Forms.ToolStrip.OnMouseUp (MouseEventArgs mea)
   in System.Windows.Forms.ToolStripDropDown.OnMouseUp (MouseEventArgs mea)
   in System.Windows.Forms.Control.WmMouseUp (Message & m, MouseButtons button, Int32 clicks)
   in System.Windows.Forms.Control.WndProc (Message & m)
   in System.Windows.Forms.ScrollableControl.WndProc (Message & m)
   in System.Windows.Forms.ToolStrip.WndProc (Message & m)
   in System.Windows.Forms.ToolStripDropDown.WndProc (Message & m)
   in System.Windows.Forms.Control.ControlNativeWindow.OnMessage (Message & m)
   in System.Windows.Forms.Control.ControlNativeWindow.WndProc (Message & m)
   in System.Windows.Forms.NativeWindow.Callback (IntPtr hWnd, Int32 msg, IntPtr wParam, IntPtr lParam)


************** ************** Loaded Assembled
mscorlib
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5485 (Win7SP1GDR.050727-5400)
    codebase: file: /// C: /Windows/Microsoft.NET/Framework/v2.0.50727/mscorlib.dll
----------------------------------------
EasyMYP
    Assembly version: 1.0.0.0
    1.0.0.0: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/EasyMYP.exe
----------------------------------------
System.Windows.Forms
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5491 (Win7SP1GDR.050727-5400)
    codebase: file:///C:/Windows/assembly/GAC_MSIL/System.Windows.Forms/2.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5485 (Win7SP1GDR.050727-5400)
    codebase: file: /// C: /Windows/assembly/GAC_MSIL/System/2.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Drawing
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5495 (Win7SP1GDR.050727-5400)
    codebase: file: /// C: /Windows/assembly/GAC_MSIL/System.Drawing/2.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
MYPHandler
    Assembly version: 1.0.0.0
    1.0.0.0: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/MYPHandler.DLL
----------------------------------------
HashDictionary
    Assembly version: 1.0.0.0
    1.0.0.0: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/HashDictionary.DLL
----------------------------------------
HashCreator
    Assembly version: 1.0.0.0
    1.0.0.0: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/HashCreator.DLL
----------------------------------------
System.Core
    Assembly version: 3.5.0.0
    Win32 version: 3.5.30729.5420 built by: Win7SP1
    codebase: file: /// C: /Windows/assembly/GAC_MSIL/System.Core/3.5.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
WarhammerOnlineHash
    Assembly version: 1.0.0.0
    1.0.0.0: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/WarhammerOnlineHash.DLL
----------------------------------------
System.Windows.Forms.resources
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5420 (Win7SP1.050727-5400)
    codebase: file:///C:/Windows/assembly/GAC_MSIL/System.Windows.Forms.resources/2.0.0.0_es_b77a5c561934e089/System.Windows.Forms.resources.dll
----------------------------------------
mscorlib.resources
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5485 (Win7SP1GDR.050727-5400)
    codebase: file: /// C: /Windows/Microsoft.NET/Framework/v2.0.50727/mscorlib.dll
----------------------------------------
System.Configuration
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5483 (Win7SP1GDR.050727-5400)
    codebase: file:///C:/Windows/assembly/GAC_MSIL/System.Configuration/2.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Management
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5483 (Win7SP1GDR.050727-5400)
    codebase: file:///C:/Windows/assembly/GAC_MSIL/System.Management/2.0.0.0__b03f5f7f11d50a3a/System.Management.dll
----------------------------------------
System.Xml
    Assembly version: 2.0.0.0
    Win32 version: 2.0.50727.5494 (Win7SP1GDR.050727-5400)
    codebase: file: /// C: /Windows/assembly/GAC_MSIL/System.Xml/2.0.0.0__b77a5c561934e089/System.Xml.dll
----------------------------------------
ICSharpCode.SharpZipLib
    Assembly version: 0.85.4.369
    0.85.4.369: Win32 version
    file: /// D codebase: /EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/ICSharpCode.SharpZipLib.DLL
----------------------------------------

************** ************** JIT Debugging
To enable debugging Just In Time (JIT), the configuration file of this
application or computer (machine.config) must have the
jitDebugging value established in the system.windows.forms section.
The application must also be compiled with debugging
enabled

For example:

<Configuration>
    <System.windows.forms jitDebugging = "true" />
</ Configuration>

When JIT debugging is enabled, any unhandled exception
JIT debugger registered will be sent on the computer
rather than be handled by this dialog box.


Can somebody help me? or at least spend the .gr2 files?
Thanks  
Google translate 

Hi,

I'm getting this error.  I've searched this thread and noticed similar errors but no solutions.  I've googled but the only solution I found was to check Framework (which is updated).

I was very excited to find this thread and discover there were actual tools to extract models from SWTOR.  Any help would be appreciated.
Thanks!

I have this same error every time I try to extract anything, and unfortunately on all three machines I have access to. Does anyone have any ideas on what to do about this?

> Reply from Vindis
>
> Cutsie33 wrote:Complete newbie here.  I came across this thread and others and have been trying to extract the model files but I must be going crazy.  Everytime I try and add the hashes_filename.txt file EasyMYP it crashes.  If I don't add it then I can open the .tor files but only see 3 folders, txt, xml and dds, I don't see anywhere that th.gr2 files are.  Am I just being stupid?  Also the hashes_filename.txt file I have is from 2012 so an updated one would probably be useful.  I also couldn't fine version 3.6 of EasyMYP and am using version 3.2.  Any help would be appreciated.  Thanks.

I had the same issue with EasyMYP, 'till I found out TorMYP is the way to go. I'll try to upload it for you, when I get access to my computer.

This TorMYP, is this something you would be willing to share with me as well?
My hope would be that it fixes the error described above, so I'd be able to extract models.

Thank you.
## Post #387
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2017-10-21T20:18:44+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Here you go 

[https://drive.google.com/open?id=0B_EjQ ... DVHb1J3RDg](https://drive.google.com/open?id=0B_EjQD5_He_IN2NZaDVHb1J3RDg)
## Post #388
- Username: Kualan
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 27, 2015 4:23 am
- Post datetime: 2017-10-25T07:56:35+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Does anyone have a more up-to-date hashes_filename.txt file to share? There's a lot of stuff from the last year or so that I can't seem to dig out.
## Post #389
- Username: daddyrus1994
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Aug 24, 2017 4:36 am
- Post datetime: 2017-10-27T21:44:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello guys, I managed to extract game files, but among all I can not find the right clothes. Exactly Vandal Jacket Casual and Relaxed Uniform Suit . How to find them?
## Post #390
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2017-11-04T17:03:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Kualan
>
> Does anyone have a more up-to-date hashes_filename.txt file to share? There's a lot of stuff from the last year or so that I can't seem to dig out.
Wait a moment I searching in my pocket.....
[A here is it](https://www.file-upload.net/download-12798122/hashes_filename2.rar.html)

I focused on the weapons and got most of them named.
The normal clothing updade is performed, so all clothes are named. (haven't checked this. I trust the method)
I work on the newer planets and I get more and more file names, but it's a lot of work. to open every single file and write down mesh- and matnames need some time.

> Reply from daddyrus1994
>
> Hello guys, I managed to extract game files, but among all I can not find the right clothes. Exactly Vandal Jacket Casual and Relaxed Uniform Suit . How to find them?

This is a little bit complecated. Clothings are typical combined from more than one file. You have the archetyp for each bodytype and clothingslot. And then you put extras on top.
The extras are hard to identifie but its possible. Most clothing folders contains an index.xml file.
This file contains the info which models are combined for which item. (don't think you get clear names)
The easiest way to find the right set is to look for an ikonic detail und search for it in the .gr2 files.
Eventualy you find the right model. Open the xml file and search for the model name, then you get your item. All other items from this set have a simelar filename. (older sets have lower numbers and are clearer. newer set containes often some older parts)

Is there anybody else who is working on this? If yes, please share your hashes with me/us. It isn't nessesary to do the work twice.


update 2017-11-05: 600 hashes for function "test full filename list"
[update2017-11-05.rar](https://xentaxbackup.github.io/file/13527_update2017-11-05.rar)
## Post #391
- Username: Zuzupel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 06, 2017 7:21 am
- Post datetime: 2017-11-06T01:17:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi all, 
anyone can help me with easyMYP 3.6? When im using of the uploaded hash files from the previous page, it crashes on startup and it only works when im not using a hash file at all? 
All i need is to get my characters models for a uni project of mine and their weapons later, can someone help me out?
## Post #392
- Username: Zuzupel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 06, 2017 7:21 am
- Post datetime: 2017-11-06T01:38:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Vindis
>
> Here you go 

https://drive.google.com/open?id=0B_EjQ ... DVHb1J3RDg
 This one is still crashing for me when using a hash file
## Post #393
- Username: daddyrus1994
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Aug 24, 2017 4:36 am
- Post datetime: 2017-11-06T15:58:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Nice! Thanks man.
## Post #394
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2017-11-06T17:07:07+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Zuzupel
>
> Vindis wrote:Here you go 

https://drive.google.com/open?id=0B_EjQ ... DVHb1J3RDg
 This one is still crashing for me when using a hash file

Do you have an own hashfile which works?
## Post #395
- Username: Zuzupel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 06, 2017 7:21 am
- Post datetime: 2017-11-06T17:15:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> Zuzupel wrote:Vindis wrote:Here you go 

https://drive.google.com/open?id=0B_EjQ ... DVHb1J3RDg
 This one is still crashing for me when using a hash file 

Do you have an own hashfile which works?

No. none of the hash files ive ever tried to add worked with the easyMYP
## Post #396
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2017-11-06T17:19:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have no special knowledge of the easymyp so I'm only guessing.

Have you edited the EasyMyp.exe.Config file?
I've tried to use the version from above and all worked fine.
## Post #397
- Username: Zuzupel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 06, 2017 7:21 am
- Post datetime: 2017-11-08T16:55:55+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Im all good now, got my hands on all game meshes, but weapons category is not good for me, anyone got a really recent hash file for weapons like unstable peacemaker and latest armors? Basically the unstable sabers are my real priority, if anyone got it please let me know!
## Post #398
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2017-11-08T20:22:53+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

my lates hash_file from above should contain all what you want.
in combination with the update (you have to read in) you have all!! clothing pieces
and most of the weapons. Only some NPC weapons, the zakuul-shields, one old rifle and one old sniperrifle are unnamed. The remaining unnamed files are unable to open or multiUvExtraction, which nobody realy needs.

In the moment I work on the vehicle asset, 300files to go.
So update is near.
[update 2017-11-08.rar](https://xentaxbackup.github.io/file/13533_update 2017-11-08.rar)
## Post #399
- Username: Zuzupel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 06, 2017 7:21 am
- Post datetime: 2017-11-09T02:23:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> my lates hash_file from above should contain all what you want.
in combination with the update (you have to read in) you have all!! clothing pieces
and most of the weapons. Only some NPC weapons, the zakuul-shields, one old rifle and one old sniperrifle are unnamed. The remaining unnamed files are unable to open or multiUvExtraction, which nobody realy needs.

In the moment I work on the vehicle asset, 300files to go.
So update is near.

Hey thanks again, but easyMYP crashes with this  file and ive noticed that its not written like a hash file at all, so do i have to copy these names to my original hash file? But still it should be written like this :
8000506F#48EE5BD3#/resources/world/areas/4611686348220847000/minimaps/world_map_28_09_r.dds#ECC43BF0
800061E0#73D64612##13CF34EB
## Post #400
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-09T04:35:16+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

launch EasyMYP and go "Dictionary > Test Full Filename List ..." then browse to and select "update 2017-11-08.txt", 
any new found names will merge with your existing hash file and format on exit.
## Post #401
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2017-11-09T18:12:25+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from AceWell
>
> launch EasyMYP and go "Dictionary > Test Full Filename List ..." then browse to and select "update 2017-11-08.txt", 
any new found names will merge with your existing hash file and format on exit.
This are only round about 400 files and nothing Zuzupel has ask for.

I've downloaded the file and checked it. all is fine.
Something went wrong after your download.
You can try to download the file again an check it. The other very very very ugly way is to open the file with notepad and perform following steps:
hit ctrl+h
check the second box in the searchmode pane
replace /resources/ with \n/resources/
save this file and read this in like Ace discribed.
You have to notice that Notepad could crash during this process, also easymyp. To read this file in you also need a complete hashlist. To create the hashlist you have to open all assets one time. Or perform a complete extraction, but this could take several hours and needs a lot of space on your hdd.

Hopefully the redownload works, the rest works but it's a pain in the ass and very time consuming.


For general understanding.
My update files contains only new files since my last update.
For full function you need a complete hashlist.
All update files must be read in.
They are much smaller and easier to handle. (direct upload on this site)
## Post #402
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-18T03:58:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> This are only round about 400 files and nothing Zuzupel has ask for.
 
well i'm pretty sure he was asking how to add those 400 new names to his hash file, so i told him how.
## Post #403
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2017-11-18T19:10:00+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

All problems solved, so what ever.

3000 new files attached. (a lot of language specific files, so don't blame me, if you don't get 3k)

I have trouble to find references for the new maps. I can see the map files (dds), but I can't name them.
Any hints where I can find the area number and the minimap names?
[update 2017-11-18.rar](https://xentaxbackup.github.io/file/13561_update 2017-11-18.rar)
## Post #404
- Username: AkenStyle
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 19, 2017 3:38 am
- Post datetime: 2017-11-23T16:54:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> All problems solved, so what ever.

3000 new files attached. (a lot of language specific files, so don't blame me, if you don't get 3k)

I have trouble to find references for the new maps. I can see the map files (dds), but I can't name them.
Any hints where I can find the area number and the minimap names?

Hi Ferouc in the FILE (update 2017-11-08.rar)

i have found this line
Line 99: /resources/art/shaders/materials/str_planet_ord_mantell_atmosphere.mat

I want to know, what i can find inside the files .mat? Textures, 3D models?
## Post #405
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2017-11-24T16:40:09+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

In short, information.
In long:
The mat files contain all information for the textures.
The texture files are stored an other folder, the filepath is in the mat file.
Normaly you use the latest noesis plugin and noesis add all related texturefiles.
If all files are extracted, all works fine.
## Post #406
- Username: AkenStyle
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 19, 2017 3:38 am
- Post datetime: 2017-11-25T12:25:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> In short, information.
In long:
The mat files contain all information for the textures.
The texture files are stored an other folder, the filepath is in the mat file.
Normaly you use the latest noesis plugin and noesis add all related texturefiles.
If all files are extracted, all works fine.

ok thanks. I want to extract the structures of the planet ord mantell, houses, fort garnik spaceport etc.. etc.., where are these 3D models and textures?
## Post #407
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2017-11-27T17:01:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from AkenStyle
>
> 
ok thanks. I want to extract the structures of the planet ord mantell, houses, fort garnik spaceport etc.. etc.., where are these 3D models and textures?

I don't know. Try to locate the area.dat for ord mantell (there up to 160 possible files) and open it with an editor. Then you have all used files.
## Post #408
- Username: AkenStyle
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 19, 2017 3:38 am
- Post datetime: 2017-11-28T09:12:02+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> AkenStyle wrote:
ok thanks. I want to extract the structures of the planet ord mantell, houses, fort garnik spaceport etc.. etc.., where are these 3D models and textures?

I don't know. Try to locate the area.dat for ord mantell (there up to 160 possible files) and open it with an editor. Then you have all used files.

ok, i have another question, in the file .dat how many meshes and textures i can find?

And you can write a format glossary? With this method we can know what a file contains, and then exclude the files they do not interest us


for example

.gr2 = 3d model
.dds = texture
.dat =
.mat = texture filepath
.jba =
.prt =
.stb =
.tex =
.acb =
.epp =
.gfx =
.fxe =
.spt =
.mph.amx =

I have found these, if there are others add them XD
## Post #409
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2017-11-29T11:59:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from AkenStyle
>
> Ferouc wrote:AkenStyle wrote:
ok thanks. I want to extract the structures of the planet ord mantell, houses, fort garnik spaceport etc.. etc.., where are these 3D models and textures?

I don't know. Try to locate the area.dat for ord mantell (there up to 160 possible files) and open it with an editor. Then you have all used files.

ok, i have another question, in the file .dat how many meshes and textures i can find?

And you can write a format glossary? With this method we can know what a file contains, and then exclude the files they do not interest us


for example

.gr2 = 3d model
.dds = texture
.dat =
.mat = texture filepath
.jba = animation data
.prt = particle
.stb = this is the dialog text maybe (it was very long ago, when I last spent time with swtor)
.tex = texture (if i remember correctly)
.acb =
.epp =
.gfx = geometry FX
.fxe = FX emitter
.spt =
.mph.amx =

I have found these, if there are others add them XD
## Post #410
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-29T12:57:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

[viewtopic.php?p=62258#p62258](http://forum.xentax.com/viewtopic.php?p=62258#p62258) 
[viewtopic.php?p=64104#p64104](http://forum.xentax.com/viewtopic.php?p=64104#p64104)
## Post #411
- Username: AkenStyle
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 19, 2017 3:38 am
- Post datetime: 2017-11-30T11:52:38+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from AceWell
>
> viewtopic.php?p=62258#p62258 
viewtopic.php?p=64104#p64104

ok thanks!
## Post #412
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2017-12-01T21:46:32+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

New stuff.
Round about 3400 names. Clothing, weapons and vehicles.
[Updates 2017-12-01.rar](https://xentaxbackup.github.io/file/13625_Updates 2017-12-01.rar)
## Post #413
- Username: AkenStyle
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 19, 2017 3:38 am
- Post datetime: 2017-12-02T19:06:43+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> New stuff.
Round about 3400 names. Clothing, weapons and vehicles.

Great Update 

PS: do you know what is the name of  the cannons that you can see in the image? And where i can find them?
[IMAGE.jpg](https://xentaxbackup.github.io/file/13631_IMAGE.jpg)
## Post #414
- Username: Zuzupel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 06, 2017 7:21 am
- Post datetime: 2017-12-04T18:23:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> New stuff.
Round about 3400 names. Clothing, weapons and vehicles.
 Ok so ive downloaded all your hash files and tried to do what the other person suggested : Dictionary-> Test full filename list.. and easyMYP finds like 100-400 new names on each but theyre not added to my hashes filename, instead there are being created 2 new files, a found one and a not found one. I tried copy-paste the new found names on my hashes filename file and now easyMYP crashes again. If i remove them it works again. I really need help to extract from this game, can someone help me and tell me why this programm crashes to new names?? Its not my downloads that are faulty because ive tried it many times! If my easy MYP is wrong then please someone send me their own software ? Thanks again.
## Post #415
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-04T20:57:34+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

new "found" names are added to your hash file automatically by EasyMYP on exit.
## Post #416
- Username: Zuzupel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 06, 2017 7:21 am
- Post datetime: 2017-12-04T22:50:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from AceWell
>
> new "found" names are added to your hash file automatically by EasyMYP on exit.

Thats weird because when i hit ctrl+H on my existing hashes file and pasted a random entry of the found file it didnt exist at all so i guessed that it doesnt automatically copy them, i mean it wasnt there..?? 
Also i did re-scan the weapons.tor and sill it extracts for me the same basic weapons, no new stuff at all? :/
## Post #417
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-05T02:39:08+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

must be something wrong with your setup, it works here, there should be a new hash file 
saved when new names are found and the old hash file is renamed to "oldHashList_blabla"
## Post #418
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2017-12-05T17:08:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi,

first. ctrl+h is for replacing, don't use the hotkey only to find something. ctrl+f is for search.

Then, if you only have 400 new files out off 4000, then you have found 3600 files on your own or you don't have the latest filelist. When you pick randomly one line you have a high chance to pick one that wasn't found.

Please perform the following steps.
open easymyp
then click Dictionary->Scan all Tors...
select the asset folder.
The process take some time. Close easymyp after the programm has finished.

Reopen easymyp and read in this file [hashes_filename-Kopie.rar](https://www.file-upload.net/download-12851721/hashes_filename-Kopie.rar.html)

close easymyp again.

now you shoul have a working hashfile.

[hashes_filename.rar](https://www.file-upload.net/download-12851726/hashes_filename.rar.html)
This is my latest hashes_filename.txt. It should work too.

[easymyp.rar](https://www.file-upload.net/download-12851740/easymyp.rar.html)
And this is my whole easymyp program.
## Post #419
- Username: Zuzupel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 06, 2017 7:21 am
- Post datetime: 2017-12-06T00:56:16+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> Hi,

first. ctrl+h is for replacing, don't use the hotkey only to find something. ctrl+f is for search.

Then, if you only have 400 new files out off 4000, then you have found 3600 files on your own or you don't have the latest filelist. When you pick randomly one line you have a high chance to pick one that wasn't found.

Please perform the following steps.
open easymyp
then click Dictionary->Scan all Tors...
select the asset folder.
The process take some time. Close easymyp after the programm has finished.

Reopen easymyp and read in this file hashes_filename-Kopie.rar

close easymyp again.

now you shoul have a working hashfile.

hashes_filename.rar
This is my latest hashes_filename.txt. It should work too.

easymyp.rar
And this is my whole easymyp program.

Thanks for your help, unfortunately i cant download the 2 hash files , it seems that the page youve uploaded them on converts them to some virus exe and my antivirus blocks it. It would be easier if you send them to my email address or upload them on rapidshare, or somewhere else? Thanks again ^_^
## Post #420
- Username: AkenStyle
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 19, 2017 3:38 am
- Post datetime: 2017-12-06T18:12:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> Hi,

first. ctrl+h is for replacing, don't use the hotkey only to find something. ctrl+f is for search.

Then, if you only have 400 new files out off 4000, then you have found 3600 files on your own or you don't have the latest filelist. When you pick randomly one line you have a high chance to pick one that wasn't found.

Please perform the following steps.
open easymyp
then click Dictionary->Scan all Tors...
select the asset folder.
The process take some time. Close easymyp after the programm has finished.

Reopen easymyp and read in this file hashes_filename-Kopie.rar

close easymyp again.

now you shoul have a working hashfile.

hashes_filename.rar
This is my latest hashes_filename.txt. It should work too.

easymyp.rar
And this is my whole easymyp program.

hi you can help me to find the cannons that you can see in the previous comment?
## Post #421
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2017-12-06T21:30:21+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Yes I could say where the files are located, but I have no desire to do this.
I used the method I posted a few days ago and found the models within two minutes.
(I did this to test myself and my method)

The models are number 59 and 60 in the ord mantel area.dat.
This is all you get from me.

Your behavior is very disappointing.
You found this topic and instead of reading all the previous posts you ask directly for solutions.
I always try to help, but I don't do the work for you.
## Post #422
- Username: AkenStyle
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 19, 2017 3:38 am
- Post datetime: 2017-12-07T08:19:46+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> Yes I could say where the files are located, but I have no desire to do this.
I used the method I posted a few days ago and found the models within two minutes.
(I did this to test myself and my method)

The models are number 59 and 60 in the ord mantel area.dat.
This is all you get from me.

Your behavior is very disappointing.
You found this topic and instead of reading all the previous posts you ask directly for solutions.
I always try to help, but I don't do the work for you.

Sorry but i'am not an expert like you, and the forum is to help people.
## Post #423
- Username: thealgerianprince
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 11, 2017 8:38 pm
- Post datetime: 2017-12-11T19:03:52+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey i was wondering, has Senya's lightsaber pike been found yet. That is one weapon i'd really like. I looked through all the weapon files but couldn't find it. There is a possibility it's not dehashed yet since 8512/8629 are done and if so can someone please work on dehashing the last 117.
Also i'm having trouble finding armor sets, i'm looking for Thexan's Set, Satele's Set and Lana's Set. Could you locate these files or instruct me on how to find them.
## Post #424
- Username: AkenStyle
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 19, 2017 3:38 am
- Post datetime: 2017-12-12T10:39:38+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

hi, in the folder (ASSETS) of the game i have found the file     swtor_en-us_area_ord_mantell_1.tor
Inside this file there are 2 format type

1) = .acb
2) = .fxe

I read on another post that the .acb files are audio files, and the .fxe file are facial animations
are true these informations?

And what type of sound there are in the .acb files? fx effect? music? voices? ambiental sound? what?
## Post #425
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2017-12-12T16:18:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from AkenStyle
>
> hi, in the folder (ASSETS) of the game i have found the file     swtor_en-us_area_ord_mantell_1.tor
Inside this file there are 2 format type

1) = .acb
2) = .fxe

I read on another post that the .acb files are audio files, and the .fxe file are facial animations
are true these informations?

And what type of sound there are in the .acb files? fx effect? music? voices? ambiental sound? what?

I don't know anything about the audio files.

> Reply from thealgerianprince
>
> Hey i was wondering, has Senya's lightsaber pike been found yet. That is one weapon i'd really like. I looked through all the weapon files but couldn't find it. There is a possibility it's not dehashed yet since 8512/8629 are done and if so can someone please work on dehashing the last 117.
Also i'm having trouble finding armor sets, i'm looking for Thexan's Set, Satele's Set and Lana's Set. Could you locate these files or instruct me on how to find them.

Are you serious? I've worked for hours on the weapon asset and this 117 files are the remaining trash. Most of the files are effects, only a hand full are weapons. There are two Zakul shields, one in white the other in the normal color, one very old rifle wich is also stored in two other locations, one very old sniper rifle, one npc rifle, one npc electro staff and one part of an assault cannon. There is no unnamed saber!
You can find a description how to find clothing pieces a few pages above. Please read this first and ask when there are open questions. And don't ask me to search for files.
## Post #426
- Username: AkenStyle
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 19, 2017 3:38 am
- Post datetime: 2017-12-13T16:59:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> AkenStyle wrote:hi, in the folder (ASSETS) of the game i have found the file     swtor_en-us_area_ord_mantell_1.tor
Inside this file there are 2 format type

1) = .acb
2) = .fxe

I read on another post that the .acb files are audio files, and the .fxe file are facial animations
are true these informations?

And what type of sound there are in the .acb files? fx effect? music? voices? ambiental sound? what?

I don't know anything about the audio files.
thealgerianprince wrote:Hey i was wondering, has Senya's lightsaber pike been found yet. That is one weapon i'd really like. I looked through all the weapon files but couldn't find it. There is a possibility it's not dehashed yet since 8512/8629 are done and if so can someone please work on dehashing the last 117.
Also i'm having trouble finding armor sets, i'm looking for Thexan's Set, Satele's Set and Lana's Set. Could you locate these files or instruct me on how to find them.

Are you serious? I've worked for hours on the weapon asset and this 117 files are the remaining trash. Most of the files are effects, only a hand full are weapons. There are two Zakul shields, one in white the other in the normal color, one very old rifle wich is also stored in two other locations, one very old sniper rifle, one npc rifle, one npc electro staff and one part of an assault cannon. There is no unnamed saber!
You can find a description how to find clothing pieces a few pages above. Please read this first and ask when there are open questions. And don't ask me to search for files.

I'm interested only one thing: where are all the 3d models and the textures of the planet ord mantell (houses, bases, structures, trees, cannons etc...) ? In the file     swtor_main_area_ord_mantell_1.tor   ?
## Post #427
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2017-12-13T17:29:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I don't know in which assets the files are and I don't need this information.
I've extract all assets so I have access to all files.

I took a short look into the ord_mantel asset. There are some models but not much.

/resources/world/areas/XXX
this is the path where all area information are stored. Each area has it's own id/folder.
In each folder there should be a subfolder containing the images for the maps, so you can identify the area.
In the area-id-folder is a file named area.dat. This file contain every model name and location used in this area.

When you have the model you can open it with noesis. Use the data viewer to get the name of the used mat file.
All mat files are located in /resources/art/shader/material/.
In this file you find all information for the textures. (Noesis import them automatical if they are extracted)

I hope this helps.
## Post #428
- Username: AkenStyle
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 19, 2017 3:38 am
- Post datetime: 2017-12-14T09:56:50+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> I don't know in which assets the files are and I don't need this information.
I've extract all assets so I have access to all files.

I took a short look into the ord_mantel asset. There are some models but not much.

/resources/world/areas/XXX
this is the path where all area information are stored. Each area has it's own id/folder.
In each folder there should be a subfolder containing the images for the maps, so you can identify the area.
In the area-id-folder is a file named area.dat. This file contain every model name and location used in this area.

When you have the model you can open it with noesis. Use the data viewer to get the name of the used mat file.
All mat files are located in /resources/art/shader/material/.
In this file you find all information for the textures. (Noesis import them automatical if they are extracted)

I hope this helps.

ah, ok thanks
## Post #429
- Username: Phrisou
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 11, 2018 3:35 am
- Post datetime: 2018-01-11T22:23:07+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello i'm new , may you explain me how to export the skeleton of a model ? Because I have exported HK-55 model and he has not his skeleton , I know how to add it manually in blender but it's long , if I had the skeleton file it would be faster. 

Sorry for my english
## Post #430
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2018-01-12T16:02:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi,

the easiest way to export the model and the skeleton is to open both together and export then.
To open all models together, copy them into a seperate folder, then you create a txt file and name it like one of the files.
Open the txt and type in all files you want to open. One name per line.
I'm not sure if you need the filepath of the files. If it doesn't work without, try with the path.

To open them, open the file you have used for the name for the txt. Noesis should open all files.
When you export the new model, you get one file with multible meshes.

The skeleton model is another gr2 file. I don't knwo where they are, but i've seen this a long time ago. Use the windows search function and search for skeleton.
## Post #431
- Username: KaosXIV
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 07, 2014 6:28 am
- Post datetime: 2018-01-15T03:27:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

It's been a while.
Anybody found anything new about the heigtmaps?

Really hoping to get a map viewer working at somepoint, I can get all the art assets loaded minus the terrain.
## Post #432
- Username: Talgalar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 17, 2015 2:06 am
- Post datetime: 2018-01-31T16:22:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi,

Is there a solution about the problem with diffuse texture ? (page 15)
Maybe it's writte on this page but I'm not english so maybe I made a bad translation and didn't find what I was looking for
## Post #433
- Username: CaptnKoda
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 07, 2018 1:36 am
- Post datetime: 2018-04-11T00:12:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello! I just wanna start by saying thank you to everyone that added their own advice into this forum.. You've helped me a ton in creating some images, and I appreciate it a lot!  I just have a few questions/problems.

1. Is there any quicker way to finding a chest piece than looking through all the chest .gr2 files and hoping to find it? It's a really long winded way to do and it seems inefficient.
2. Has anyone gotten the normal maps to function yet? The colour is all off for them, and they're completely unusable. I think the topic was already brought up before, but all of the technical stuff went over my head. Same goes for all the other texture maps. I'm not quite sure how to utilise them, so any renders look really flat and dull
3. How would I go ahead getting the exact colours in game? Like, when you dye a chest-piece in-game and it dyes certain parts either the primary or secondary colour. Is there anyway to do that? I've been manually retexturing in photoshop so far which isn't always accurate.

Again, I appreciate y'all helping with this program. Cheers
## Post #434
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2018-04-11T14:54:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi,

I can't say anything about 2 and 3.
Regarding topic 1: At first, I would copy out only one bodytype, so you have a lot smaler amount of files.
Open the index.xml files in the chest folder. This files contains all chest combinations in the game. From here its trail and error.
There are a few hints in the names. Names with BH or TR will never be a robe.
BH is Bountyhunter
TR is trooper
...

The lates armor set won't be the one with the lowest counter.

There is no list like. Imp trooper armor has item id xyz in the index.xml.
But I would be happy, when you create one.

Best regards,
Ferouc
## Post #435
- Username: CaptnKoda
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 07, 2018 1:36 am
- Post datetime: 2018-04-12T02:39:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Yo,

I found out how to fix the normal maps so they can be used. I'm really bad at explaining things with typing, so I went ahead and made a YouTube video to show what to do.
[https://www.youtube.com/watch?v=91X4zldVzVc](https://www.youtube.com/watch?v=91X4zldVzVc)
Glad I can give a lil' back to the forum that helped me this far
## Post #436
- Username: CaptnKoda
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 07, 2018 1:36 am
- Post datetime: 2018-04-18T19:43:21+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Yo, Ferouc. You still working on naming files? Worried that the number of people who still are will drop to zero, so none of the new content gets named. If you are, any chance you could let us in on your secrets?  I'd like to lend a hand towards it
## Post #437
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2018-04-19T18:36:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi,

if I have the time, I work on the files.
All clothing and most weapons are named.

Best regards, Ferouc
[update 2018-04-13.rar](https://xentaxbackup.github.io/file/14243_update 2018-04-13.rar)
## Post #438
- Username: Noto
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 10, 2018 11:48 pm
- Post datetime: 2018-05-10T16:17:32+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Im trying to get the ardent oracle armor set but honestly I have no idea what im doing.
## Post #439
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2018-05-11T14:18:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi,

maybe I can help you, but I need more information.
Have you followed my latest instruction?
If yes, then please discripe your problem more detailed if not, please use the instruction.
## Post #440
- Username: Noto
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 10, 2018 11:48 pm
- Post datetime: 2018-05-11T20:57:54+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I just recently started this and this is brand new to me trying to do this lol
## Post #441
- Username: Noto
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 10, 2018 11:48 pm
- Post datetime: 2018-05-11T20:58:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I just got the necessary things downloaded.
## Post #442
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2018-05-12T14:51:55+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Okay this is a lot. I give you a gideline to work with.

You need easymyp and noesis. For noesis you also need the latest swtor plugin from this topic.
Download the attached file and import it to easymyp.
Extract the files with easymyp.
Open noesis and open the extracted files. GR2 files are models. Noesis loads the texture if extracted.
Search for your armor. They are all located in "resource/art/dynamic/xxx".
XXX are folders for the seperat bodyparts (chest, leg...)
If you want to open all your armorparts at once, copy them all in a other folder. Create a txt file and name it after one of them. After this you type in all the models with extension. When you open the model with the similar name as the txt file, noesis load all other parts as well.

I hope this helps. Please ask if you get stuck.

regards, Ferouc

[hashes_filename.rar](https://www.file-upload.net/download-13125663/hashes_filename.rar.html)
## Post #443
- Username: CaptnKoda
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 07, 2018 1:36 am
- Post datetime: 2018-05-19T10:18:28+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Yo, real quick.

I've extracted every .tor archive related to the meshes (armor, environment, etc..) including textures and what not. However, noesis can't find matching textures at all. I've gone back through the pages and downloaded the most recent plugin, changed the line in the notepad thing.. but it still doesn't work for anything. Anything I'm doing wrong? I'd also appreciate you could throw in the plugin you're using (if it's a working version) just to make sure I got the right version
## Post #444
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2018-05-20T13:12:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi,

are the texture only missing on armor?
The armor textur is loaded diffrent and I don't know how to combine them.
When you open a gr2 file with noesis, click on "tools/data viewer" in the upper left corner.
Extend the model tree.
In meshes you can see the model name
In material you can see the name of the material.
If the name of the material is default noesis doesn't conect the correct mat file.

The next problem could be, tha the mat file or the textures are in a diffrent asset.
The mtx02 weaponset for example is located in the weapon asset. The coresponding mat file is part of the kotfe asset.

You can use the function "extract all files by extension" and extract all mat, dds and tex files.

I've attached the swtor plugin I'm using.
[python.rar](https://xentaxbackup.github.io/file/14378_python.rar)
## Post #445
- Username: CaptnKoda
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 07, 2018 1:36 am
- Post datetime: 2018-05-20T14:08:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I swapped out the plugin for yours, and now it works! Thanks so much, I had a lot of trouble hunting down the textures for the Dealer's Den cantina floor. Thank youuu! \o/
## Post #446
- Username: AkenStyle
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 19, 2017 3:38 am
- Post datetime: 2018-06-15T16:21:54+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> Okay this is a lot. I give you a gideline to work with.

You need easymyp and noesis. For noesis you also need the latest swtor plugin from this topic.
Download the attached file and import it to easymyp.
Extract the files with easymyp.
Open noesis and open the extracted files. GR2 files are models. Noesis loads the texture if extracted.
Search for your armor. They are all located in "resource/art/dynamic/xxx".
XXX are folders for the seperat bodyparts (chest, leg...)
If you want to open all your armorparts at once, copy them all in a other folder. Create a txt file and name it after one of them. After this you type in all the models with extension. When you open the model with the similar name as the txt file, noesis load all other parts as well.

I hope this helps. Please ask if you get stuck.

regards, Ferouc

hashes_filename.rar

Hi this is the last hashes file with all the games items?
## Post #447
- Username: AkenStyle
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 19, 2017 3:38 am
- Post datetime: 2018-06-15T16:30:21+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Danteurius
>
> I swapped out the plugin for yours, and now it works! Thanks so much, I had a lot of trouble hunting down the textures for the Dealer's Den cantina floor. Thank youuu! \o/

Hi i saw that you have a youtube channel, can you make a video tutorial please?
## Post #448
- Username: Ferouc
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 24, 2013 9:12 pm
- Post datetime: 2018-06-18T15:20:33+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from AkenStyle
>
> Ferouc wrote:Okay this is a lot. I give you a gideline to work with.

You need easymyp and noesis. For noesis you also need the latest swtor plugin from this topic.
Download the attached file and import it to easymyp.
Extract the files with easymyp.
Open noesis and open the extracted files. GR2 files are models. Noesis loads the texture if extracted.
Search for your armor. They are all located in "resource/art/dynamic/xxx".
XXX are folders for the seperat bodyparts (chest, leg...)
If you want to open all your armorparts at once, copy them all in a other folder. Create a txt file and name it after one of them. After this you type in all the models with extension. When you open the model with the similar name as the txt file, noesis load all other parts as well.

I hope this helps. Please ask if you get stuck.

regards, Ferouc

hashes_filename.rar

Hi this is the last hashes file with all the games items?

Hi,

its my latest hash_file, but it doesn't include the updates since may and I only use the german language pack, so the newer languagefiles are missing too.
It isn't 100% decoded.
In the last months I didn't had the time to work on this stuff and it doesn't get better this summer.

I think I've posted all my methods in this topic, so you should be able to find some stuff.
I have the topic notification on, so feel free to ask if you need help.

Regards, Ferouc
## Post #449
- Username: AkenStyle
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 19, 2017 3:38 am
- Post datetime: 2018-07-07T10:07:32+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ferouc
>
> AkenStyle wrote:Ferouc wrote:Okay this is a lot. I give you a gideline to work with.

You need easymyp and noesis. For noesis you also need the latest swtor plugin from this topic.
Download the attached file and import it to easymyp.
Extract the files with easymyp.
Open noesis and open the extracted files. GR2 files are models. Noesis loads the texture if extracted.
Search for your armor. They are all located in "resource/art/dynamic/xxx".
XXX are folders for the seperat bodyparts (chest, leg...)
If you want to open all your armorparts at once, copy them all in a other folder. Create a txt file and name it after one of them. After this you type in all the models with extension. When you open the model with the similar name as the txt file, noesis load all other parts as well.

I hope this helps. Please ask if you get stuck.

regards, Ferouc

hashes_filename.rar

Hi this is the last hashes file with all the games items?

Hi,

its my latest hash_file, but it doesn't include the updates since may and I only use the german language pack, so the newer languagefiles are missing too.
It isn't 100% decoded.
In the last months I didn't had the time to work on this stuff and it doesn't get better this summer.

I think I've posted all my methods in this topic, so you should be able to find some stuff.
I have the topic notification on, so feel free to ask if you need help.

Regards, Ferouc

it's possible to extract the base of the landscape without rocks, structures trees etc? I want edit some landscapes in Zbrush
## Post #450
- Username: daddyrus1994
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Aug 24, 2017 4:36 am
- Post datetime: 2018-08-10T10:45:37+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello guys. Need help, i I can not find these resources manually, so please help me how to find them from this data

[https://swtor.jedipedia.net/en/itm/rela ... uit-jacket](https://swtor.jedipedia.net/en/itm/relaxed-jumpsuit-jacket)
[https://swtor.jedipedia.net/en/itm/rela ... form-shirt](https://swtor.jedipedia.net/en/itm/relaxed-uniform-shirt)

Thank you in advance.
## Post #451
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2018-08-10T11:04:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

The ModelId value tells you what you need to know. It's a reference you will find in the appropriate index.xml for the specific body part it relates to (in both these cases, resources\art\dynamic\chest\index.xml). 

The best approach when looking up values from Jedipedia is to use Notepad++ and its Find In Files function. Set the base search directory to resources\art\dynamic and the file type filter to *.xml, then search for the IDs Jedipedia produces.
## Post #452
- Username: daddyrus1994
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Aug 24, 2017 4:36 am
- Post datetime: 2018-08-12T12:30:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks for the help, your advice helped me to do what I wanted for a long time. I redesigned my favorite character sets in garrys mod. Thanks, for a long time I was looking for a great answer to the question. Here are screenshots of what I did with your help:

[https://cdn.pbrd.co/images/HyPiqhT.jpg](https://cdn.pbrd.co/images/HyPiqhT.jpg)
[https://cdn.pbrd.co/images/HyPiylu.jpg](https://cdn.pbrd.co/images/HyPiylu.jpg)
[https://cdn.pbrd.co/images/HyPiDPr.jpg](https://cdn.pbrd.co/images/HyPiDPr.jpg)
[https://cdn.pbrd.co/images/HyPiIsO.jpg](https://cdn.pbrd.co/images/HyPiIsO.jpg)
## Post #453
- Username: Ausar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 03, 2018 6:59 am
- Post datetime: 2018-09-04T23:33:25+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I know i'm really new/late to this, but could someone tell me what the resources folder is specifically, in terms of what file was extracted to make it, or is it just an amalgam of all the specific files extracted? thanks!

(im new to this so don't murder me for being a noob)
## Post #454
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2018-10-08T08:32:09+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Sorry, if this has already been asked or answered, but is it also possible to view complete areas / planets and if so, how?
## Post #455
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2018-10-23T16:09:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have a new hash list that includes a lot of Ossus (PTS)!    

Download:
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #456
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2018-10-26T18:34:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ausar
>
> I know i'm really new/late to this, but could someone tell me what the resources folder is specifically, in terms of what file was extracted to make it, or is it just an amalgam of all the specific files extracted? thanks!An ultra-n00b here . I think it's the amalgam of all the named files in the hashes_filename, as every other folder outside it contains the unnamed ones.


Hi, everyone. I discovered this thread half a year ago but only recently managed to locate the versions of the tools that seemed to work correctly. I have most basic things figured out and have been able to assemble and texture the models of my player characters, and try things (Zabrak full body tattoos!), but I'd ask for some help on the texturing from the perspective of a typical commercial 3D rendering app user instead of a programmer:

• What's the best way to tint objects (characters' skin hue and dyed armor) from a Photoshop's layers' transfer modes or image adjustment tools point of view, using the hue values found in the XML data? I read [SWTOR fan's post](http://forum.xentax.com/viewtopic.php?p=88127&sid=dda135c11ab468de25e0cafa38f72274#p88127) about the matter, but I got utterly lost in the hueing shader code. I'm looking for a general procedure that works for everything without further per case manual adjustments, as the 3D app I own (EIAS3D. Learning Blender at the moment, too) supports texture layering with transfer modes.

I'm hoping for either setting a model's diffuse color to the one specified in the XML data or some formula-calculated version and put the diffuse map on top with some specific transfer mode. Or viceversa. That, or some Photoshop image adjustment I could automate to process whole folders of texture files.

• Also, what are the correct or most approximate layer transfer modes to use on the head customization maps? Specifically the Complexion, Makeup, Pattern and Tattoo maps. They seem to work well with Darken and Multiply, but if someone has the right answer it would be very welcome.
## Post #457
- Username: honos5677
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 28, 2017 11:55 pm
- Post datetime: 2018-10-29T07:11:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Can anyone link me to the version of EasyMYP that works for this? The one that was posted originally doesn't seem to work anymore.
## Post #458
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2018-10-30T00:19:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from honos5677
>
> Can anyone link me to the version of EasyMYP that works for this? The one that was posted originally doesn't seem to work anymore.I found this one at the bottom of [this post](http://forum.xentax.com/viewtopic.php?p=135991#p135991) by Ferouc: [easymyp.rar](https://www.file-upload.net/download-12851740/easymyp.rar.html).
## Post #459
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2018-10-31T14:44:53+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from honos5677
>
> Can anyone link me to the version of EasyMYP that works for this? The one that was posted originally doesn't seem to work anymore.

I have a collection of TorMYP, Noesis and NodeViewer here: [https://drive.google.com/file/d/1b_lvKA ... Nikzt/view](https://drive.google.com/file/d/1b_lvKA2VRmVzf9gqoJ0ClOu2cCiNikzt/view)
## Post #460
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2018-11-01T12:55:18+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks. I think mine could be outdated, so I'll check it against yours.
## Post #461
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2018-11-03T18:51:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have a new Hash-List for EasyMYP / TorMYP with over 3000 neu file names (included most Ossus 3D-Models and textures) but without Ossus dialogs!
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #462
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2018-11-10T19:27:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

That's great. Thanks again
## Post #463
- Username: Rekya
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 02, 2018 8:44 pm
- Post datetime: 2018-11-16T21:18:33+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

did somebody know how to get the texture of the armor without the brown texture that we know ?
## Post #464
- Username: Bella Asuna
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 18, 2018 7:17 am
- Post datetime: 2018-11-17T23:43:16+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Soooo...
basically i worked out the usage of all tools and finally got anything i got.
But while exporting "_skeleton.gr2" files with the Tool "Neosis" the following error:
*External Link with leads to Imgur

[https://i.imgur.com/GkoPZNc.png](https://i.imgur.com/GkoPZNc.png)

occurs, i really need help on that one..... Like please
## Post #465
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-11-17T23:51:48+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

"_skeleton.gr2" are just bones, there's no geometry inside, you need a maxscript or other Noesis plugin for bones.
## Post #466
- Username: Tanile
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Mar 23, 2017 12:55 am
- Post datetime: 2018-11-18T21:14:11+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello, when I open EasyMYP and I decide to press "Open Archive", the file loads and puts me as an error, can you help me? Thank you








Consultez la fin de ce message pour plus de détails sur l'appel du débogage
juste-à-temps (JIT) à la place de cette boîte de dialogue.

************** Texte de l'exception **************
System.InvalidOperationException: La catégorie n'existe pas.
   à System.Diagnostics.PerformanceCounterLib.CounterExists(String machine, String category, String counter)
   à System.Diagnostics.PerformanceCounter.Initialize()
   à System.Diagnostics.PerformanceCounter..ctor(String categoryName, String counterName, String instanceName, Boolean readOnly)
   à System.Diagnostics.PerformanceCounter..ctor(String categoryName, String counterName, String instanceName)
   à MYPHandler.MYPHandler..ctor(String filename, del_FileTableEventHandler eventHandler_FileTable, del_FileEventHandler eventHandler_Extraction, HashDictionary hashDic) dans C:\Code\Personal\SWTOR ripper\EasyMYP\MYPHandler\MYPHandler_extraction.cs:ligne 154
   à EasyMYP.MainWindow.OpenArchive(String filename, Boolean block) dans C:\Code\Personal\SWTOR ripper\EasyMYP\EasyMYP\MainWindow.cs:ligne 182
   à EasyMYP.MainWindow.openArchiveToolStripMenuItem_Click(Object sender, EventArgs e) dans C:\Code\Personal\SWTOR ripper\EasyMYP\EasyMYP\MainWindow.cs:ligne 160
   à System.Windows.Forms.ToolStripItem.RaiseEvent(Object key, EventArgs e)
   à System.Windows.Forms.ToolStripMenuItem.OnClick(EventArgs e)
   à System.Windows.Forms.ToolStripItem.HandleClick(EventArgs e)
   à System.Windows.Forms.ToolStripItem.HandleMouseUp(MouseEventArgs e)
   à System.Windows.Forms.ToolStripItem.FireEventInteractive(EventArgs e, ToolStripItemEventType met)
   à System.Windows.Forms.ToolStripItem.FireEvent(EventArgs e, ToolStripItemEventType met)
   à System.Windows.Forms.ToolStrip.OnMouseUp(MouseEventArgs mea)
   à System.Windows.Forms.ToolStripDropDown.OnMouseUp(MouseEventArgs mea)
   à System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
   à System.Windows.Forms.Control.WndProc(Message& m)
   à System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   à System.Windows.Forms.ToolStrip.WndProc(Message& m)
   à System.Windows.Forms.ToolStripDropDown.WndProc(Message& m)
   à System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   à System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   à System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)


************** Assemblys chargés **************
mscorlib
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.8800 (QFE.050727-8800)
    CodeBase : file:///C:/Windows/Microsoft.NET/Framework/v2.0.50727/mscorlib.dll
----------------------------------------
EasyMYP
    Version de l'assembly : 1.0.0.0
    Version Win32 : 1.0.0.0
    CodeBase : file:///C:/Users/Mael/Desktop/EasyMYP_v3.6-Spec/EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/EasyMYP.exe
----------------------------------------
System.Windows.Forms
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.8015 (FX35W81RTMGDR.050727-8000)
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System.Windows.Forms/2.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.8791 (QFE.050727-8700)
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System/2.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Drawing
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.8019 (FX35W81RTMGDR.050727-8000)
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System.Drawing/2.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
MYPHandler
    Version de l'assembly : 1.0.0.0
    Version Win32 : 1.0.0.0
    CodeBase : file:///C:/Users/Mael/Desktop/EasyMYP_v3.6-Spec/EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/MYPHandler.DLL
----------------------------------------
HashDictionary
    Version de l'assembly : 1.0.0.0
    Version Win32 : 1.0.0.0
    CodeBase : file:///C:/Users/Mael/Desktop/EasyMYP_v3.6-Spec/EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/HashDictionary.DLL
----------------------------------------
HashCreator
    Version de l'assembly : 1.0.0.0
    Version Win32 : 1.0.0.0
    CodeBase : file:///C:/Users/Mael/Desktop/EasyMYP_v3.6-Spec/EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/HashCreator.DLL
----------------------------------------
System.Core
    Version de l'assembly : 3.5.0.0
    Version Win32 : 3.5.30729.7903 built by: Win9Rel
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System.Core/3.5.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
WarhammerOnlineHash
    Version de l'assembly : 1.0.0.0
    Version Win32 : 1.0.0.0
    CodeBase : file:///C:/Users/Mael/Desktop/EasyMYP_v3.6-Spec/EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/WarhammerOnlineHash.DLL
----------------------------------------
System.Windows.Forms.resources
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.7905 (win9rel.050727-7900)
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System.Windows.Forms.resources/2.0.0.0_fr_b77a5c561934e089/System.Windows.Forms.resources.dll
----------------------------------------
mscorlib.resources
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.8800 (QFE.050727-8800)
    CodeBase : file:///C:/Windows/Microsoft.NET/Framework/v2.0.50727/mscorlib.dll
----------------------------------------
System.Configuration
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.8007 (FX35W81RTMGDR.050727-8000)
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System.Configuration/2.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Management
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.8766 (QFE.050727-8700)
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System.Management/2.0.0.0__b03f5f7f11d50a3a/System.Management.dll
----------------------------------------
System.resources
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.7905 (win9rel.050727-7900)
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System.resources/2.0.0.0_fr_b77a5c561934e089/System.resources.dll
----------------------------------------

************** Débogage JIT **************
Pour activer le débogage juste-à-temps (JIT), le fichier de configuration pour cette
application ou cet ordinateur (machine.config) doit avoir la valeur
jitDebugging définie dans la section system.windows.forms.
L'application doit également être compilée avec le débogage
activé.

Par exemple :

<configuration>
    <system.windows.forms jitDebugging="true" />
</configuration>

Lorsque le débogage juste-à-temps est activé, les exceptions non gérées
seront envoyées au débogueur JIT inscrit sur l'ordinateur
plutôt que d'être gérées par cette boîte de dialogue.
## Post #467
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2018-11-21T21:16:44+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Tanile
>
> Hello, when I open EasyMYP and I decide to press "Open Archive", the file loads and puts me as an error, can you help me? Thank you








Consultez la fin de ce message pour plus de détails sur l'appel du débogage
juste-à-temps (JIT) à la place de cette boîte de dialogue.

************** Texte de l'exception **************
System.InvalidOperationException: La catégorie n'existe pas.
   à System.Diagnostics.PerformanceCounterLib.CounterExists(String machine, String category, String counter)
   à System.Diagnostics.PerformanceCounter.Initialize()
   à System.Diagnostics.PerformanceCounter..ctor(String categoryName, String counterName, String instanceName, Boolean readOnly)
   à System.Diagnostics.PerformanceCounter..ctor(String categoryName, String counterName, String instanceName)
   à MYPHandler.MYPHandler..ctor(String filename, del_FileTableEventHandler eventHandler_FileTable, del_FileEventHandler eventHandler_Extraction, HashDictionary hashDic) dans C:\Code\Personal\SWTOR ripper\EasyMYP\MYPHandler\MYPHandler_extraction.cs:ligne 154
   à EasyMYP.MainWindow.OpenArchive(String filename, Boolean block) dans C:\Code\Personal\SWTOR ripper\EasyMYP\EasyMYP\MainWindow.cs:ligne 182
   à EasyMYP.MainWindow.openArchiveToolStripMenuItem_Click(Object sender, EventArgs e) dans C:\Code\Personal\SWTOR ripper\EasyMYP\EasyMYP\MainWindow.cs:ligne 160
   à System.Windows.Forms.ToolStripItem.RaiseEvent(Object key, EventArgs e)
   à System.Windows.Forms.ToolStripMenuItem.OnClick(EventArgs e)
   à System.Windows.Forms.ToolStripItem.HandleClick(EventArgs e)
   à System.Windows.Forms.ToolStripItem.HandleMouseUp(MouseEventArgs e)
   à System.Windows.Forms.ToolStripItem.FireEventInteractive(EventArgs e, ToolStripItemEventType met)
   à System.Windows.Forms.ToolStripItem.FireEvent(EventArgs e, ToolStripItemEventType met)
   à System.Windows.Forms.ToolStrip.OnMouseUp(MouseEventArgs mea)
   à System.Windows.Forms.ToolStripDropDown.OnMouseUp(MouseEventArgs mea)
   à System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
   à System.Windows.Forms.Control.WndProc(Message& m)
   à System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   à System.Windows.Forms.ToolStrip.WndProc(Message& m)
   à System.Windows.Forms.ToolStripDropDown.WndProc(Message& m)
   à System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   à System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   à System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)


************** Assemblys chargés **************
mscorlib
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.8800 (QFE.050727-8800)
    CodeBase : file:///C:/Windows/Microsoft.NET/Framework/v2.0.50727/mscorlib.dll
----------------------------------------
EasyMYP
    Version de l'assembly : 1.0.0.0
    Version Win32 : 1.0.0.0
    CodeBase : file:///C:/Users/Mael/Desktop/EasyMYP_v3.6-Spec/EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/EasyMYP.exe
----------------------------------------
System.Windows.Forms
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.8015 (FX35W81RTMGDR.050727-8000)
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System.Windows.Forms/2.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.8791 (QFE.050727-8700)
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System/2.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Drawing
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.8019 (FX35W81RTMGDR.050727-8000)
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System.Drawing/2.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
MYPHandler
    Version de l'assembly : 1.0.0.0
    Version Win32 : 1.0.0.0
    CodeBase : file:///C:/Users/Mael/Desktop/EasyMYP_v3.6-Spec/EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/MYPHandler.DLL
----------------------------------------
HashDictionary
    Version de l'assembly : 1.0.0.0
    Version Win32 : 1.0.0.0
    CodeBase : file:///C:/Users/Mael/Desktop/EasyMYP_v3.6-Spec/EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/HashDictionary.DLL
----------------------------------------
HashCreator
    Version de l'assembly : 1.0.0.0
    Version Win32 : 1.0.0.0
    CodeBase : file:///C:/Users/Mael/Desktop/EasyMYP_v3.6-Spec/EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/HashCreator.DLL
----------------------------------------
System.Core
    Version de l'assembly : 3.5.0.0
    Version Win32 : 3.5.30729.7903 built by: Win9Rel
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System.Core/3.5.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
WarhammerOnlineHash
    Version de l'assembly : 1.0.0.0
    Version Win32 : 1.0.0.0
    CodeBase : file:///C:/Users/Mael/Desktop/EasyMYP_v3.6-Spec/EasyMYP_v3.6-Spec%20SWTOR%20Batch%20Dict%20Parser/WarhammerOnlineHash.DLL
----------------------------------------
System.Windows.Forms.resources
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.7905 (win9rel.050727-7900)
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System.Windows.Forms.resources/2.0.0.0_fr_b77a5c561934e089/System.Windows.Forms.resources.dll
----------------------------------------
mscorlib.resources
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.8800 (QFE.050727-8800)
    CodeBase : file:///C:/Windows/Microsoft.NET/Framework/v2.0.50727/mscorlib.dll
----------------------------------------
System.Configuration
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.8007 (FX35W81RTMGDR.050727-8000)
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System.Configuration/2.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Management
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.8766 (QFE.050727-8700)
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System.Management/2.0.0.0__b03f5f7f11d50a3a/System.Management.dll
----------------------------------------
System.resources
    Version de l'assembly : 2.0.0.0
    Version Win32 : 2.0.50727.7905 (win9rel.050727-7900)
    CodeBase : file:///C:/Windows/assembly/GAC_MSIL/System.resources/2.0.0.0_fr_b77a5c561934e089/System.resources.dll
----------------------------------------

************** Débogage JIT **************
Pour activer le débogage juste-à-temps (JIT), le fichier de configuration pour cette
application ou cet ordinateur (machine.config) doit avoir la valeur
jitDebugging définie dans la section system.windows.forms.
L'application doit également être compilée avec le débogage
activé.

Par exemple :

<configuration>
    <system.windows.forms jitDebugging="true" />
</configuration>

Lorsque le débogage juste-à-temps est activé, les exceptions non gérées
seront envoyées au débogueur JIT inscrit sur l'ordinateur
plutôt que d'être gérées par cette boîte de dialogue.

Have you already tried this version?
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #468
- Username: Tanile
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Mar 23, 2017 12:55 am
- Post datetime: 2018-11-22T11:41:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Yes it still doesn't work
## Post #469
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2018-11-22T20:03:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Tanile
>
> Yes it still doesn't work

Oh sorry, I posted the wrong link. Here is the right link: [https://drive.google.com/file/d/1MptD-t ... sp=sharing](https://drive.google.com/file/d/1MptD-tdB75nb2JorU4XQTR4d--UO6Wqo/view?usp=sharing)
## Post #470
- Username: Tanile
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Mar 23, 2017 12:55 am
- Post datetime: 2018-11-23T13:13:38+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I tried this version but it still doesn't work to, same error
## Post #471
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2018-11-23T19:40:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Tanile
>
> I tried this version but it still doesn't work to, same error

Have you also tried to rename the .tor file to .myp and import it with drag and drop?
## Post #472
- Username: Tanile
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Mar 23, 2017 12:55 am
- Post datetime: 2018-11-23T19:57:08+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

"EasyMYP as stopped working"
## Post #473
- Username: Rekya
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 02, 2018 8:44 pm
- Post datetime: 2018-11-24T13:34:08+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

hey realmanlp do you have a discord ?
## Post #474
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2018-11-24T21:53:10+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Rekya
>
> hey realmanlp do you have a discord ?

No, why?
## Post #475
- Username: Gezmondo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 21, 2016 10:53 am
- Post datetime: 2018-11-25T10:57:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I've noticed that every planet in the 1-50 story has it's own musical theme, except for Quesh, and Ilum, which reuse music from elsewhere in the game, and I was wondering if there is a way to find out which planet plays which piece of music and where, so I can attempt to make a fan made theme for Quesh and Ilum to match the officially released tracks?
## Post #476
- Username: Rekya
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 02, 2018 8:44 pm
- Post datetime: 2018-11-26T20:51:27+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from RealymanLP
>
> Rekya wrote:hey realmanlp do you have a discord ?

No, why?

because i want talk to you in private ^^
## Post #477
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2018-11-26T21:05:21+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Rekya
>
> RealymanLP wrote:Rekya wrote:hey realmanlp do you have a discord ?

No, why?

because i want talk to you in private ^^

I'm sorry, but unfortunately that's not possible and I'm not very good at English.
## Post #478
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2018-12-08T18:12:44+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey all!

Does anyone know if there is something like a World Viewer for SWTOR?

Edit: New Hash-List: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #479
- Username: Rekya
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 02, 2018 8:44 pm
- Post datetime: 2018-12-23T19:56:07+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from RealymanLP
>
> Hey all!

Does anyone know if there is something like a World Viewer for SWTOR?

Edit: New Hash-List: https://drive.google.com/drive/folders/ ... sp=sharing

this new file also includes the old hash files?
or is it a new hashfile with only new things?
## Post #480
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2018-12-24T22:41:54+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Rekya
>
> RealymanLP wrote:Hey all!

Does anyone know if there is something like a World Viewer for SWTOR?

Edit: New Hash-List: https://drive.google.com/drive/folders/ ... sp=sharing 

this new file also includes the old hash files?
or is it a new hashfile with only new things?

Of course, the old hashes are still in there.
## Post #481
- Username: Rekya
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 02, 2018 8:44 pm
- Post datetime: 2018-12-25T18:58:11+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from RealymanLP
>
> Rekya wrote:RealymanLP wrote:Hey all!

Does anyone know if there is something like a World Viewer for SWTOR?

Edit: New Hash-List: https://drive.google.com/drive/folders/ ... sp=sharing 

this new file also includes the old hash files?
or is it a new hashfile with only new things?

Of course, the old hashes are still in there.

ok thx your awsome
## Post #482
- Username: AkenStyle
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 19, 2017 3:38 am
- Post datetime: 2018-12-29T19:18:34+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from RealymanLP
>
> Hey all!

Does anyone know if there is something like a World Viewer for SWTOR?

Edit: New Hash-List: https://drive.google.com/drive/folders/ ... sp=sharing

Great! There are 3D models of the new planet Ossus?
## Post #483
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2018-12-30T10:40:04+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from AkenStyle
>
> RealymanLP wrote:Hey all!

Does anyone know if there is something like a World Viewer for SWTOR?

Edit: New Hash-List: https://drive.google.com/drive/folders/ ... sp=sharing 

Great! There are 3D models of the new planet Ossus?

Yes, in the hash list are 3D models of Ossus, but unfortunately not all.
## Post #484
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2018-12-30T11:01:28+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have a question about Noesis' GR2-to-OBJ conversion. I see it sometimes failing to perform it (while batch-processing I'm using an MMO mouse macro to just OK it and let it continue). Is there any rhyme or reason for that, say, the object being some special case?

(It isn't terribly important, as I seem to get everything I need converted)
## Post #485
- Username: Rekya
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 02, 2018 8:44 pm
- Post datetime: 2019-01-02T22:04:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

hi guys did somebody know how to get the real textures of all the armors without the brown texture ?
## Post #486
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-01-03T00:41:11+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Regarding that, which subforum would be best to start a thread specifically about the correct usage of SWTOR's different types of texture maps, XML info, and possibly bones and such to assemble the models in 3D apps such as Blender, 3DSMax and the like? This thread explains most of the texture stuff, but it is too disperse and at times uncomprehensible to mere mortals (say, dyed gear or characters' skin hueing), so it would be nice to get all that simplified somewhere.
## Post #487
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-01-22T16:53:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

New hash-list is there!
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #488
- Username: Rekya
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 02, 2018 8:44 pm
- Post datetime: 2019-01-24T14:54:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from RealymanLP
>
> New hash-list is there!
https://drive.google.com/drive/folders/ ... sp=sharing

thx again for your share
## Post #489
- Username: distiny
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 20, 2019 9:07 am
- Post datetime: 2019-02-20T22:28:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Latest Hash anyone ?
## Post #490
- Username: Wedge
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 11, 2019 3:32 am
- Post datetime: 2019-02-21T21:12:13+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello, everyone 

Thank You all for this amazing job, I am completely new not only to this. But I am reading through this for a few days already and thanks to You I already managed to do a few things. I just got two questions:

1)I tried to extract "swtor_main_art_creature_a_1.tor" and a few others with TorMYP You have provided here. In "resources\art\dynamic\creature\model" I managed to find some .gr2 files. But when I open them with Noesis, I got two results:

First one is error and the model cannot be opened (I have the same error when I try to extract some model that can be opened). I tried changing the plugins You guys provided here but nothing helps. Malgus as an example:


The second case is that the model opens, but is without texture. Now, if I understand it correctly, someone wrote here that Noesis should load the extracted textures, but it does not seem to work. Could someone help me with how to get the correct textures to the model? T7 as an example:


2) Apart from other things, I am trying to find a Battle-Scarred Boltblaster’s MK-2 (Pub) armor and mostly helmet (or any of the similar style sets [https://torf.mmo-fashion.com/xonolite-asylum-pub/](https://torf.mmo-fashion.com/xonolite-asylum-pub/)). Again, I am not entirely sure if I understand it correctly, but all armors are made from more parts (like some basic for body type, the armor itself and some extensions for it etc.?) and I would need to find all of it to put it together? I am also not entirely sure that I understand how exactly You do that 
But it´s not that important, right now I just need to get to the helmet (but I guess it would be also divided into more parts, right?). I see that there are .tor archives for hands, legs, multiple for chests... But damn, I cannot find the helmets anywhere  Tried few archives but found only things like faces and hairs. Could someone point me in the right direction, please?

I sincerely apologize if the answer I am looking for is already here. I was reading it all, but as it´s a really old topic with so much information, it´s quite possible I overlooked something. Sorry :/
## Post #491
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-02-21T21:41:02+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

What I do in such cases — and there could be more efficient ways to go at it, sorry, I'm a novice    — is:

• First I search for the item at [https://swtor.jedipedia.net/](https://swtor.jedipedia.net/) (say, [https://swtor.jedipedia.net/en/search?q ... er&patch=0](https://swtor.jedipedia.net/en/search?q=Battle-Scarred+Boltblaster&patch=0) ) and get some results.

• In the actual item's page: [https://swtor.jedipedia.net/en/itm/batt ... elmet-mk-2](https://swtor.jedipedia.net/en/itm/battle-scarred-boltblasters-helmet-mk-2) I can see in the Appearance box a reference to [ModelId] => 1000176. What I do then is use my PC (a Mac, actually) desktop's indexed search to look for any of the game's XML files that contains that 1000176 number.

• In this case, I'm finding this file at extracted_swtor/resources/art/dynamic/face/index.xml. I open it with a text editor and search inside for that number, finding it in a section of the file that goes like this:

```
    <ID>1000176</ID>
    <ArtName>face_trhelmet02_heavy_tr_a02</ArtName>
    <DesignerName>face trhelmet02 heavy tr a02</DesignerName>
    <BaseFile>/art/dynamic/face/model/face_trhelmet02_[bt]_archetype.gr2</BaseFile>
    <Attachments>
      <Attachment id="1001554" name="face_trhelmet02_bt_heavy_tr_a02_back" filename="/art/dynamic/face/model/face_trhelmet02_[bt]_heavy_tr_a02_back.gr2" />
    </Attachments>
    <Materials>
      <Material id="1001542" name="face_trhelmet02_heavy_tr_a02c02_u" filename="/art/shaders/materials/face_trhelmet02_heavy_tr_a02c02_u.mat">
        <ColorSchemes>
          <ColorScheme guid="1002489" />
          <ColorScheme guid="1002487" />
          <ColorScheme guid="1002488" />
          <ColorScheme guid="1375793" />
          <ColorScheme guid="1375794" />
          <ColorScheme guid="1375795" />
          <ColorScheme guid="1375796" />
          <ColorScheme guid="1402653" />
          <ColorScheme guid="1402654" />
          <ColorScheme guid="1402655" />
          <ColorScheme guid="1402656" />
          <ColorScheme guid="1402657" />
          <ColorScheme guid="1402659" />
          <ColorScheme guid="1375788" />
        </ColorSchemes>
        <MaterialOverrides />
      </Material>
    </Materials>
    <Bodytypes>
      <Bodytype>bfa</Bodytype>
      <Bodytype>bfb</Bodytype>
      <Bodytype>bfn</Bodytype>
      <Bodytype>bfs</Bodytype>
      <Bodytype>bma</Bodytype>
      <Bodytype>bmf</Bodytype>
      <Bodytype>bmn</Bodytype>
      <Bodytype>bms</Bodytype>
    </Bodytypes>
    <SkinMaterialIndex>-1</SkinMaterialIndex>
    <SkinHueIndex>-1</SkinHueIndex>
    <Filters>
      <Filter name="Style" value="heavy" />
      <Filter name="Class" value="tr" />
    </Filters>
    <Identities />
    <Tags />
    <CustomData />
  </Asset>

```


You can see that the base file of the item is /art/dynamic/face/model/face_trhelmet02_[bt]_archetype.gr2
That [bt] part ought to be substituted by the body type the item you want is meant for (bma, bmn, bfn, etc.).

It says too that there is an attachment object that completes it, and its filename:
<Attachment id="1001554" name="face_trhelmet02_bt_heavy_tr_a02_back" filename="/art/dynamic/face/model/face_trhelmet02_[bt]_heavy_tr_a02_back.gr2" />

• With those filenames in hand you can do another indexed search to get to them quickly (Windows and macOS' desktop search is a godsend for these things). And you can see how there are references to material description and texture files that point at the textures meant to be used for the item.


By the way, If there are smarter ways to do this, I'd like to know   I would also like to know how to get Noesis to autoload all those elements by itself: I never managed to make that work.
## Post #492
- Username: Wedge
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 11, 2019 3:32 am
- Post datetime: 2019-02-22T18:17:48+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Fri Feb 22, 2019 5:41 am at Fri Feb 22, 2019 5:41 am
>
> 
What I do in such cases — and there could be more efficient ways to go at it, sorry, I'm a novice    — is:

• First I search for the item at https://swtor.jedipedia.net/ (say, https://swtor.jedipedia.net/en/search?q ... er&patch=0 ) and get some results.

• In the actual item's page: https://swtor.jedipedia.net/en/itm/batt ... elmet-mk-2 I can see in the Appearance box a reference to [ModelId] => 1000176. What I do then is use my PC (a Mac, actually) desktop's indexed search to look for any of the game's XML files that contains that 1000176 number.

• In this case, I'm finding this file at extracted_swtor/resources/art/dynamic/face/index.xml. I open it with a text editor and search inside for that number, finding it in a section of the file that goes like this:
Code: Select all  <Asset>
    <ID>1000176</ID>
    <ArtName>face_trhelmet02_heavy_tr_a02</ArtName>
    <DesignerName>face trhelmet02 heavy tr a02</DesignerName>
    <BaseFile>/art/dynamic/face/model/face_trhelmet02_[bt]_archetype.gr2</BaseFile>
    <Attachments>
      <Attachment id="1001554" name="face_trhelmet02_bt_heavy_tr_a02_back" filename="/art/dynamic/face/model/face_trhelmet02_[bt]_heavy_tr_a02_back.gr2" />
    </Attachments>
    <Materials>
      <Material id="1001542" name="face_trhelmet02_heavy_tr_a02c02_u" filename="/art/shaders/materials/face_trhelmet02_heavy_tr_a02c02_u.mat">
        <ColorSchemes>
          <ColorScheme guid="1002489" />
          <ColorScheme guid="1002487" />
          <ColorScheme guid="1002488" />
          <ColorScheme guid="1375793" />
          <ColorScheme guid="1375794" />
          <ColorScheme guid="1375795" />
          <ColorScheme guid="1375796" />
          <ColorScheme guid="1402653" />
          <ColorScheme guid="1402654" />
          <ColorScheme guid="1402655" />
          <ColorScheme guid="1402656" />
          <ColorScheme guid="1402657" />
          <ColorScheme guid="1402659" />
          <ColorScheme guid="1375788" />
        </ColorSchemes>
        <MaterialOverrides />
      </Material>
    </Materials>
    <Bodytypes>
      <Bodytype>bfa</Bodytype>
      <Bodytype>bfb</Bodytype>
      <Bodytype>bfn</Bodytype>
      <Bodytype>bfs</Bodytype>
      <Bodytype>bma</Bodytype>
      <Bodytype>bmf</Bodytype>
      <Bodytype>bmn</Bodytype>
      <Bodytype>bms</Bodytype>
    </Bodytypes>
    <SkinMaterialIndex>-1</SkinMaterialIndex>
    <SkinHueIndex>-1</SkinHueIndex>
    <Filters>
      <Filter name="Style" value="heavy" />
      <Filter name="Class" value="tr" />
    </Filters>
    <Identities />
    <Tags />
    <CustomData />
  </Asset>


You can see that the base file of the item is /art/dynamic/face/model/face_trhelmet02_[bt]_archetype.gr2
That [bt] part ought to be substituted by the body type the item you want is meant for (bma, bmn, bfn, etc.).

It says too that there is an attachment object that completes it, and its filename:
<Attachment id="1001554" name="face_trhelmet02_bt_heavy_tr_a02_back" filename="/art/dynamic/face/model/face_trhelmet02_[bt]_heavy_tr_a02_back.gr2" />

• With those filenames in hand you can do another indexed search to get to them quickly (Windows and macOS' desktop search is a godsend for these things). And you can see how there are references to material description and texture files that point at the textures meant to be used for the item.


By the way, If there are smarter ways to do this, I'd like to know   I would also like to know how to get Noesis to autoload all those elements by itself: I never managed to make that work.

Thanks a lot for help, I´ll look into it
## Post #493
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-03-22T18:54:07+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

New hast list!!! [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #494
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-03-23T14:23:07+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from RealymanLP ↑Sat Mar 23, 2019 2:54 am at Sat Mar 23, 2019 2:54 am
>
> 
New hast list!!! https://drive.google.com/drive/folders/ ... sp=sharing
Yay! Thanks
## Post #495
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-04-02T19:22:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey everyone!

i have a new Hashlist for you with lots of new sounds in swtor_test_main_bnk_location_1.tor and swtor_main_bnk_audiodata_1.tor
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #496
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-04-06T18:21:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

New hash list with over 600 (new) SWTOR dialoges: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #497
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-04-19T10:43:53+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

New hashlist with lots of Dantooine 3D-Models is there!
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)

You can find the files in the swtor_test_main_art_zed_1.tor file.
## Post #498
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-04-20T10:31:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey!
I added some gom-type names to the NodeViewer. Here is the new version: [https://drive.google.com/file/d/1d184OO ... sp=sharing](https://drive.google.com/file/d/1d184OOz_1mC5Lw4Tmnge8gc3JPfyDMiX/view?usp=sharing)
It is also sufficient to only exchange the gom_type_names.xml.
## Post #499
- Username: esreveR
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Sep 28, 2016 11:52 pm
- Post datetime: 2019-05-06T09:21:32+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Newbish question but where would I find side npcs, like the imperial/republic troopers. Not even named ones either unless I need to be looking at armor pieces instead.
## Post #500
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-05-08T23:32:44+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from esreveR ↑Mon May 06, 2019 5:21 pm at Mon May 06, 2019 5:21 pm
>
> 
Newbish question but where would I find side npcs, like the imperial/republic troopers. Not even named ones either unless I need to be looking at armor pieces instead.
If what you mean is simple background troopers or trooper mob models, I suppose they ought to be among the ones listed at [https://swtor.jedipedia.net/en/npc](https://swtor.jedipedia.net/en/npc) but I'm not quite sure because it's taking me too much time to find any there. Each link leads to a page with game asset IDs and a small 3D viewer to check that they are what you are looking for.

Could anyone corroborate that?
## Post #501
- Username: esreveR
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Sep 28, 2016 11:52 pm
- Post datetime: 2019-05-09T05:05:29+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Thu May 09, 2019 7:32 am at Thu May 09, 2019 7:32 am
>
> 
esreveR wrote: ↑Mon May 06, 2019 5:21 pm
Newbish question but where would I find side npcs, like the imperial/republic troopers. Not even named ones either unless I need to be looking at armor pieces instead.

If what you mean is simple background troopers or trooper mob models, I suppose they ought to be among the ones listed at https://swtor.jedipedia.net/en/npc but I'm not quite sure because it's taking me too much time to find any there. Each link leads to a page with game asset IDs and a small 3D viewer to check that they are what you are looking for.

Could anyone corroborate that?

Yeah it was that essentially, and just been digging finding some. Takes a lot of time though.
## Post #502
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-05-11T16:02:43+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Perhaps it would be more efficient to check for some full set of trooper armor and assemble the pieces as if it was a NPC.
## Post #503
- Username: DominusInvictus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 03, 2019 3:17 am
- Post datetime: 2019-06-05T03:34:50+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Does anyone know where I can find head/ face models?
## Post #504
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-05T12:47:29+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from DominusInvictus ↑Wed Jun 05, 2019 11:34 am at Wed Jun 05, 2019 11:34 am
>
> 
Does anyone know where I can find head/ face models?Do you mean where they are inside the extracted assets' folders? That would be:

extracted_swtor > resources > art > dynamic > head > model

(all characters' body parts are inside the 'dynamic' subfolder)
## Post #505
- Username: DominusInvictus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 03, 2019 3:17 am
- Post datetime: 2019-06-06T02:47:21+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Wed Jun 05, 2019 8:47 pm at Wed Jun 05, 2019 8:47 pm
>
> 
DominusInvictus wrote: ↑Wed Jun 05, 2019 11:34 am
Does anyone know where I can find head/ face models?
Do you mean where they are inside the extracted assets' folders? That would be:

extracted_swtor > resources > art > dynamic > head > model

(all characters' body parts are inside the 'dynamic' subfolder)

I mean in what archive?
## Post #506
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-07T23:14:32+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I think the models are at:
C:\Program Files (x86) > Electronic Arts > BioWare > Star Wars - The Old Republic > Assets > swtor_main_art_dynamic_head_1.tor
and some other elements (textures and more models) at:
C:\Program Files (x86) > Electronic Arts > BioWare > Star Wars - The Old Republic > Assets > swtor_main_art_dynamic_face_1.tor
## Post #507
- Username: DominusInvictus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 03, 2019 3:17 am
- Post datetime: 2019-06-08T03:17:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Does anyone know where to find the bfs togruta head? I have found bfn in resources\art\dynamic\head\model but there seems to be not bfs.
## Post #508
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-08T09:47:00+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from DominusInvictus ↑Sat Jun 08, 2019 11:17 am at Sat Jun 08, 2019 11:17 am
>
> 
Does anyone know where to find the bfs togruta head? I have found bfn in resources\art\dynamic\head\model but there seems to be not bfs.It's weird. There seems to be just three Togruta head models: two identical female ones and one male.
head_togruta_bfn_cc_a01.gr2
head_togruta_bfn_non_a01.gr2
head_togruta_bmn_non_a01.gr2

And, in the head folder's index.xml file, those are mentioned only once. When the time comes to describe Togruta player characters it actually points at human head models. Say:

    <ArtName>head_pctogruta_bfs_african_a04</ArtName>
    <DesignerName>head pctogruta bfs african a04</DesignerName>
    <BaseFile>/art/dynamic/head/model/head_human_bfs_african_a04.gr2</BaseFile>

I'm not sure how that works  Possibly those full heads are for the Togruta NPCs, and PCs are somehow made by merging them with the human heads in some manner, or there's a Togruta faceless headpiece model somewhere else (perhaps classified as 'hair').
## Post #509
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-08T10:17:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Bingo! There are faceless Togruta heads for all body types, classified as 'hair', at:

extracted_swtor > resources > art > dynamic > hair > model

hair_pctogruta_bfa_non_a01
hair_pctogruta_bfb_non_a01
hair_pctogruta_bfn_non_a01
hair_pctogruta_bfs_non_a01
hair_pctogruta_bma_non_a01
hair_pctogruta_bmf_non_a01
hair_pctogruta_bmn_non_a01
hair_pctogruta_bms_non_a01

One could fit them to the usual human heads.
## Post #510
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-06-14T17:32:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

New hash list for the 6.0 PTS files with lots of Onderon and Meksha files: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)

You can find the Onderon files in the swtor_test_main_area_onslaught_1.tor and the meksha files in the swtor_test_main_art_zed_1.tor
## Post #511
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T13:11:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Can i swap malgus armor model+texture to use it as player in game?
## Post #512
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T13:27:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from probe88 ↑Mon Jun 24, 2019 9:11 pm at Mon Jun 24, 2019 9:11 pm
>
> 
Can i swap malgus armor model+texture to use it as player in game?I think there might be a way through the modding utility included in SWTOR Fan's Nude Mod. I don't know if there's a thread in Xentax about it, but there's this one [here](https://www.undertow.club/threads/swtor-file-changer-nude-mod.3047/) that could help.

I played with the tool before discovering this thread. Despite producing error messages when run (possibly out of differences between the contents of the game files at the time it was made and current ones?) it works well: Just press enter when they appear until it finishes the task. One can play with the text file describing the meshes and texture files changes and test the results quite easily: It's quite straightforward.
## Post #513
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T13:35:28+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Big thanks, will try
## Post #514
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T13:46:33+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

When using the tool, remember to apply the mod after you launch the game launcher and it finishes verifying the files before activating the button to start the game. If you apply it before that, the launcher will see the modded files as corrupted and will simply redownload them.

After playing with the modded game, you apply the tool to revert the changes so that the launcher doesn't do that redownloading the next time you play.
## Post #515
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T14:15:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Mon Jun 24, 2019 9:46 pm at Mon Jun 24, 2019 9:46 pm
>
> 
When using the tool, remember to apply the mod after you launch the game launcher and it finishes verifying the files before activating the button to start the game. If you apply it before that, the launcher will see the modded files as corrupted and will simply redownload them.

After playing with the modded game, you apply the tool to revert the changes so that the launcher doesn't do that redownloading the next time you play.

And maybe you know do i need to extract gr2 and dds files and only after that make a replacement

or i can replace it inside the game. 

e.g

replace /resources/art/dynamic/player_character/outfit/all_naked_body/texture/___psd/chest_naked_caucasian_young_a01c01_bfa_h.dds /resources/art/dynamic/player_character/textureineed.dds
## Post #516
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T14:35:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I believe you need to extract them first and place them in the tool's "files" folder, so that it can have them at hand to do the swapping  EasyMyp could help there.

Without EasyMyp, a way to extract them might be by using the modding tool to substitute the Malgus stuff with, say, the nude model assets that come with it. My guess is that the Malgus items would be stored in a temporary folder (for the tool to be able to put them back in place when finished playing), so one could make a copy while they are there.

(I'm just thinking aloud. It's been a long while since the last time I used it, so I'm not sure about this)
## Post #517
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T14:38:05+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor miner ↑Tue Nov 19, 2013 12:06 pm at Tue Nov 19, 2013 12:06 pm
>
> 
I didn't have any trouble extracting the textures for malgus's model.

They were in swtor_main_art_creature_a_1.tor - "\resources\art\dynamic\npc\unique_characters\texture\___psd\"

It is strange but no such folder in swtor_main_art_creature_a_1.tor or any other tor arhives
## Post #518
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T14:48:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

[https://i.ibb.co/nsBkXjC/image.png](https://i.ibb.co/nsBkXjC/image.png)
## Post #519
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T14:59:53+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have the whole game assets extracted via the hash files RealymanLP kindly linked to a few posts ago, and by searching for "Malgus" I find there are some single mesh Malgus characters (classified as 'creature') indeed. I'm sorry I can't try checking the TOR files right now, but certainly Malgus must be somewhere in there, for sure.

Now that I realise, that those Malgus models are single mesh ones including the armor, pre-geared, as it were, might be a problem for what you wanted to achieve (replace your player character with Malgus, If I got that right?). I don't know what the game will do when adding your character's gear to it.
## Post #520
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T15:01:50+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from probe88 ↑Mon Jun 24, 2019 10:48 pm at Mon Jun 24, 2019 10:48 pm
>
> 
https://i.ibb.co/nsBkXjC/image.pngTry directly inside the creature/model folder instead of the NPC one.

(you can open the hash file inside some text editor and do searches there, too. EasyMyp's file tree depends on that file's data, after all)
## Post #521
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T15:10:37+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Mon Jun 24, 2019 11:01 pm at Mon Jun 24, 2019 11:01 pm
>
> 
Try directly inside the creature/model folder instead of the NPC one.

Nope, not there.

> Reply from ZeroGravitas ↑Mon Jun 24, 2019 11:01 pm at Mon Jun 24, 2019 11:01 pm
>
> 
(you can open the hash file inside some text editor and do searches there, too. EasyMyp's file tree depends on that file's data, after all)

Already tried. hash told

8C0DF5D5#4356B2C8#/resources/art/dynamic/npc/unique_characters/texture/___psd/bms_malgus_a01_v01_d.dds#84D9DA47

But it doesnt tell how to find it..
## Post #522
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T15:18:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Aw, you are right about the directory route. The thing is, I actually have that file there: I'm looking at it right now. But I can't look at what TOR file it is inside of, at the moment. Sorry
## Post #523
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T15:19:25+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Mon Jun 24, 2019 10:59 pm at Mon Jun 24, 2019 10:59 pm
>
> 
I have the whole game assets extracted via the hash files RealymanLP kindly linked to a few posts ago

Can you give me a link?
## Post #524
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T15:23:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Yeah, it's this post in the previous page of this thread  
[https://forum.xentax.com/viewtopic.php? ... 95#p153724](https://forum.xentax.com/viewtopic.php?f=10&t=7186&start=495#p153724)
## Post #525
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T15:31:46+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Mon Jun 24, 2019 11:23 pm at Mon Jun 24, 2019 11:23 pm
>
> 
Yeah, it's this post in the previous page of this thread  
https://forum.xentax.com/viewtopic.php? ... 95#p153724

Oh i misunderstand you, i thought someone already upload whole exctracted files somewhere   

Latest hashfile i already have, but thanks you anyway
## Post #526
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T15:41:56+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Fri Feb 22, 2019 5:41 am at Fri Feb 22, 2019 5:41 am
>
> 
What I do in such cases — and there could be more efficient ways to go at it, sorry, I'm a novice    — is:

• First I search for the item at https://swtor.jedipedia.net/ (say, https://swtor.jedipedia.net/en/search?q ... er&patch=0 ) and get some results.

• In the actual item's page: https://swtor.jedipedia.net/en/itm/batt ... elmet-mk-2 I can see in the Appearance box a reference to [ModelId] => 1000176. What I do then is use my PC (a Mac, actually) desktop's indexed search to look for any of the game's XML files that contains that 1000176 number.

• In this case, I'm finding this file at extracted_swtor/resources/art/dynamic/face/index.xml. I open it with a text editor and search inside for that number, finding it in a section of the file that goes like this:
Code: Select all  <Asset>
    <ID>1000176</ID>
    <ArtName>face_trhelmet02_heavy_tr_a02</ArtName>
    <DesignerName>face trhelmet02 heavy tr a02</DesignerName>
    <BaseFile>/art/dynamic/face/model/face_trhelmet02_[bt]_archetype.gr2</BaseFile>
    <Attachments>
      <Attachment id="1001554" name="face_trhelmet02_bt_heavy_tr_a02_back" filename="/art/dynamic/face/model/face_trhelmet02_[bt]_heavy_tr_a02_back.gr2" />
    </Attachments>
    <Materials>
      <Material id="1001542" name="face_trhelmet02_heavy_tr_a02c02_u" filename="/art/shaders/materials/face_trhelmet02_heavy_tr_a02c02_u.mat">
        <ColorSchemes>
          <ColorScheme guid="1002489" />
          <ColorScheme guid="1002487" />
          <ColorScheme guid="1002488" />
          <ColorScheme guid="1375793" />
          <ColorScheme guid="1375794" />
          <ColorScheme guid="1375795" />
          <ColorScheme guid="1375796" />
          <ColorScheme guid="1402653" />
          <ColorScheme guid="1402654" />
          <ColorScheme guid="1402655" />
          <ColorScheme guid="1402656" />
          <ColorScheme guid="1402657" />
          <ColorScheme guid="1402659" />
          <ColorScheme guid="1375788" />
        </ColorSchemes>
        <MaterialOverrides />
      </Material>
    </Materials>
    <Bodytypes>
      <Bodytype>bfa</Bodytype>
      <Bodytype>bfb</Bodytype>
      <Bodytype>bfn</Bodytype>
      <Bodytype>bfs</Bodytype>
      <Bodytype>bma</Bodytype>
      <Bodytype>bmf</Bodytype>
      <Bodytype>bmn</Bodytype>
      <Bodytype>bms</Bodytype>
    </Bodytypes>
    <SkinMaterialIndex>-1</SkinMaterialIndex>
    <SkinHueIndex>-1</SkinHueIndex>
    <Filters>
      <Filter name="Style" value="heavy" />
      <Filter name="Class" value="tr" />
    </Filters>
    <Identities />
    <Tags />
    <CustomData />
  </Asset>


You can see that the base file of the item is /art/dynamic/face/model/face_trhelmet02_[bt]_archetype.gr2
That [bt] part ought to be substituted by the body type the item you want is meant for (bma, bmn, bfn, etc.).

It says too that there is an attachment object that completes it, and its filename:
<Attachment id="1001554" name="face_trhelmet02_bt_heavy_tr_a02_back" filename="/art/dynamic/face/model/face_trhelmet02_[bt]_heavy_tr_a02_back.gr2" />

• With those filenames in hand you can do another indexed search to get to them quickly (Windows and macOS' desktop search is a godsend for these things). And you can see how there are references to material description and texture files that point at the textures meant to be used for the item.


By the way, If there are smarter ways to do this, I'd like to know   I would also like to know how to get Noesis to autoload all those elements by itself: I never managed to make that work.

Just interesting, maybe it will be easiers to swap xmls not gr2 files. I mean if i change model/texture location to gear i need to swap
## Post #527
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T15:47:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Oh, you are right!  That would solve everything.

The difficult part is getting the modified XMLs back inside the TOR files. That completely eludes me.
## Post #528
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T16:04:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

If anyone (i dunno for what reason lol) searhing malgus textures like me

their new location here

swtor_main_art_creature_body_type_1.tor

ZeroGravitas and how you extract all tor arhives, just one by one?
## Post #529
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T16:15:55+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hmm

Dunno why

but i can extract all from arhive - and its doing well

but when i want extract current dds/gr2 it returns error
## Post #530
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T16:31:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from probe88 ↑Mon Jun 24, 2019 9:11 pm at Mon Jun 24, 2019 9:11 pm
>
> 
Can i swap malgus armor model+texture to use it as player in game?

will answer to myself, i am afraid it is impossible   

I just open textures in Photoshop, and malgus hasnt his armour separate. Armor+head+mask = all in one file.
## Post #531
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T17:13:27+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from probe88 ↑Tue Jun 25, 2019 12:15 am at Tue Jun 25, 2019 12:15 am
>
> 
Hmm
Dunno why
but i can extract all from arhive - and its doing well
but when i want extract current dds/gr2 it returns error
Not sure about what could be happening there.

Regarding Malgus, perhaps you could try using the separate armor pieces instead. You wouldn't have the guy's lovely face  but at least you would wear the suit.

[https://swtor.jedipedia.net/en/search?q=malgus%27s](https://swtor.jedipedia.net/en/search?q=malgus%27s)
## Post #532
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T17:20:48+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Tue Jun 25, 2019 1:13 am at Tue Jun 25, 2019 1:13 am
>
> 

Regarding Malgus, perhaps you could try using the separate armor pieces instead. You wouldn't have the guy's lovely face  but at least you would wear the suit.

https://swtor.jedipedia.net/en/search?q=malgus%27s

The problem is Cartel Market player's malgus set is awfull comparing to original one   

ZeroGravitas can you help me with bodytypes. All that bms/bmn - what does these means?
## Post #533
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T17:30:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from probe88 ↑Tue Jun 25, 2019 1:20 am at Tue Jun 25, 2019 1:20 am
>
> ZeroGravitas can you help me with bodytypes. All that bms/bmn - what does these means?Oh, those have to do with the character creator's body type selector, and are as follows:

Male Body Type 1: bma = base male anorexic (seriously  )
Male Body Type 2: bmn = base male normal
Male Body Type 3: bms = base male strong
Male Body Type 4: bmf = base male fat

Female Body Type 1: bfa = base female anorexic
Female Body Type 2: bfn = base female normal
Female Body Type 3: bfs = base female strong
Female Body Type 4: bfb = base female big (phew!  )
## Post #534
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T17:54:11+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Ty very much
## Post #535
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T18:40:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have a question about current item xml

E.g

[https://swtor.jedipedia.net/en/itm/dart ... reastplate](https://swtor.jedipedia.net/en/itm/darth-skotias-breastplate)

Under modl id we can see - 1002645

in xml in attachments we can ses

```
      <Attachment id="1002646" name="chest armor01 heavy sw a07" filename="/art/dynamic/chest/model/chest_armor01_[bt]_heavy_sw_a07_hooddown.gr2" />
      <Attachment id="1002647" name="chest armor01 heavy sw a07" filename="/art/dynamic/chest/model/chest_armor01_[bt]_heavy_sw_a07_hoodup.gr2" />
      <Attachment id="1002654" name="chest armor01 heavy sw a07" filename="/art/dynamic/chest/model/chest_armor01_[bt]_heavy_sw_a07_shld.gr2" />
```


However shoulders model and hoodup - are missing on darth skotia armor.

So what ID i need to find to edit exactly set of armor i need?
## Post #536
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T18:49:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Are you replacing the "[bt]" part in the filenames with the body type you want to use? Say, "bmn" for a Body Type 2 male:

chest_armor01_bmn_heavy_sw_a07_hoodup.gr2

I ask because I've done a search in my drive for that file and I found it at resources/art/dynamic/chest/model
## Post #537
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T18:58:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

UPD: nvm
## Post #538
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T18:59:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Tue Jun 25, 2019 2:49 am at Tue Jun 25, 2019 2:49 am
>
> 
Are you replacing the "[bt]" part in the filenames with the body type you want to use? Say, "bmn" for a Body Type 2 male:

chest_armor01_bmn_heavy_sw_a07_hoodup.gr2

I ask because I've done a search in my drive for that file and I found it at resources/art/dynamic/chest/model

i am not repalcing gr2 atm, just lurking in xml

e.g [ModelId] => 1002645 - that ID answering for ALL armors with such piece, not Darth Skotia exactly

I will try to play with gr2 later
## Post #539
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T19:04:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from probe88 ↑Tue Jun 25, 2019 2:59 am at Tue Jun 25, 2019 2:59 am
>
> i am not repalcing gr2 atm, just lurking in xmlSorry, I meant searching for the file pointed at by that XML file, by doing such substitution. OK
## Post #540
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T19:13:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

My english is awful but i will try to explain what i want

e.g

we have Darth Skotia chest
[https://swtor.jedipedia.net/en/itm/dart ... reastplate](https://swtor.jedipedia.net/en/itm/darth-skotias-breastplate)

i want to add hood to that piece of armor 
[https://swtor.jedipedia.net/en/npc/darth-skotia](https://swtor.jedipedia.net/en/npc/darth-skotia) (heres same armor with hood)

from last link i understand that i need 3 armor pieces
chest_armor01_[bt]_archetype
+ chest_armor01_[bt]_heavy_sw_a07_chest
+ chest_armor01_[bt]_heavy_sw_a07_hooddown

When i lurking for Darth Skotia chest [https://swtor.jedipedia.net/en/itm/dart ... reastplate](https://swtor.jedipedia.net/en/itm/darth-skotias-breastplate) 
i can see strings

 [Id] => 16140952691667918224
    [Id62] => a5r0OzK
    [Fqn] => ipp.mtx.season8.darth_skotia.chest
    [Type] => 4
    [ModelId] => 1002645
    [MaterialIndex] => 1002659
    [Attachments] => Array

I search for  [ModelId] => 1002645, and in /resources/art/dynamic/chest/index.xml i have strings


```
      <Attachment id="1002646" name="chest armor01 heavy sw a07" filename="/art/dynamic/chest/model/chest_armor01_[bt]_heavy_sw_a07_hooddown.gr2" />
      <Attachment id="1002647" name="chest armor01 heavy sw a07" filename="/art/dynamic/chest/model/chest_armor01_[bt]_heavy_sw_a07_hoodup.gr2" />
      <Attachment id="1002654" name="chest armor01 heavy sw a07" filename="/art/dynamic/chest/model/chest_armor01_[bt]_heavy_sw_a07_shld.gr2" />
```


as we can see that Attachments realates to all types of such gear not exactly Darth Skotia chest. I just tried delete string

```
  <Attachment id="1002647" name="chest armor01 heavy sw a07" filename="/art/dynamic/chest/model/chest_armor01_[bt]_heavy_sw_a07_hoodup.gr2" />
```


sucesfully swaped files - but hood doesnt appear in game   


Now i will try just replace 
chest_armor01_bmn_heavy_sw_a07_hooddown.gr2 with chest_armor01_bmn_heavy_sw_a07_hoodup.gr2
## Post #541
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T19:19:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from probe88 ↑Tue Jun 25, 2019 3:13 am at Tue Jun 25, 2019 3:13 am
>
> Now i will try just replace 
chest_armor01_bmn_heavy_sw_a07_hooddown.gr2 with chest_armor01_bmn_heavy_sw_a07_hoodup.gr2My guess is that it should work. Good luck!
## Post #542
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T19:26:32+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Tue Jun 25, 2019 3:19 am at Tue Jun 25, 2019 3:19 am
>
> 
probe88 wrote: ↑Tue Jun 25, 2019 3:13 amNow i will try just replace 
chest_armor01_bmn_heavy_sw_a07_hooddown.gr2 with chest_armor01_bmn_heavy_sw_a07_hoodup.gr2
My guess is that it should work. Good luck!

Damn..

It asks me to make file smaller because original file is smaller than new
## Post #543
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T19:35:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Argh: That's something that was mentioned in the thread about the nude mod. For some reason the game checks that the files aren't bigger than the originals. The author, when redoing the textures to show nipples and genitalia, had to be careful to keep them under their original filesize  .

For the mesh files a possible solution could be to use the reduced polygon count versions that the game uses when the objects are too distant to the camera, instead. Those have a ".lod" in their filenames (I think it means "level of detail"). Say:

chest_armor01_bmn_heavy_sw_a07_hoodup.lod.gr2

(it might be necessary to rename it, deleting the ".lod" part)

I don't know how worse-looking they are
## Post #544
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T19:49:51+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Tue Jun 25, 2019 3:35 am at Tue Jun 25, 2019 3:35 am
>
> 
chest_armor01_bmn_heavy_sw_a07_hoodup.lod.gr2

(it might be necessary to rename it, deleting the ".lod" part)

I don't know how worse-looking they are

Yeah it worked..

But still no changes in game (i checked gr2 file was really changed)

seems i am missing smth
## Post #545
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T20:18:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

ZeroGravitas if you can, can you search for "16140952691667918224" through all files extracted.. Does it mentioned somewhere?
## Post #546
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T20:23:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Sorry, I'm finding nothing out of that reference
## Post #547
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T20:31:53+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Tue Jun 25, 2019 4:23 am at Tue Jun 25, 2019 4:23 am
>
> 
Sorry, I'm finding nothing out of that reference

Ty very very much for helping and answering my noob questions.

I dont give up. Finally it should be somewhere in the game.
## Post #548
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T20:38:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I'm as much of a noob myself, so no worries 

I see from your posts that this reference number comes from the XML block for Darth Scotia's chest. Sadly, those long Ids at the head of those blocks never seem to be useful for anything when searching for parts: At least I've never found matches for them. Only the other Ids (ModelId, MaterialIndex and such) seem to be useful.
## Post #549
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T20:49:35+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

ZeroGravitas have you ever "played" with dds?

i downloaded plugin for photoshop - edit dds, but dunno what option i need to choose when save.
## Post #550
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-24T20:56:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from probe88 ↑Tue Jun 25, 2019 4:49 am at Tue Jun 25, 2019 4:49 am
>
> 
ZeroGravitas have you ever "played" with dds?

i downloaded plugin for photoshop - edit dds, but dunno what option i need to choose when save.I'm afraid not  I've found a couple of free apps that read and convert .dds, too. Perhaps, when previewing the original .dds, they might show information about what options to choose:

[https://www.xnview.com/en/xnview/](https://www.xnview.com/en/xnview/)
[https://www.xnview.com/en/xnconvert/](https://www.xnview.com/en/xnconvert/)

There are a lot of other utilities around. I believe GIMP has native support for the format

[https://www.gimp.org/](https://www.gimp.org/)

I'm going to have to leave my computer now. I'll keep an eye on the thread to see if I can be of more help. Good luck!
## Post #551
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-24T21:13:32+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

ZeroGravitas I just swap first texture!

Huge big enormous thanks for your help!!!

It looks awful shiny seems i f***d up with n dds, but at least in working))
## Post #552
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-25T12:28:29+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Fantastic!

The shininess problem could be because of other texture files associated to every model. The ones ending with a "_d.dds" hold the colors of the model, but there are others:

• The ones ending in "_s.dds" hold the way the parts of the models shine.
• The ones ending in "_n.dds" hold the model's surface relief, so to speak (the Normals).
• There are others, ending in "_m.dds" and "_h.dds", that hold things like what areas are affected by a dye, what parts of the model have light, etc.

So perhaps you could try repeating what you did before to the .dds files ending in "_s.dds" and see what happens. It's a bit of boring work, but…
## Post #553
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-06-27T09:02:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

By some reason texture i swaped - changed in game, but remain old one in cutscene and character creation window
## Post #554
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-27T18:47:33+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Yeah  . Some version of this tool and the scripts posted in that original thread work with the character selector and cutscenes, but only for the female characters. I don't know what the trick is to make it work with male ones yet.
## Post #555
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-30T00:06:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

A question of my own: Has anybody constructed an [Outbreak Response Lightsaber](https://swtor.jedipedia.net/en/itm/outbreak-response-lightsaber) (the one sold by the Rakghoul Event vendor)? Sadly, Jedipedia has no Model IDs for this one. I'm trying to see if this lightsaber is just like some other one with just some glowy textures added.
## Post #556
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-30T00:43:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I found it by looking at the models: It's the saber_high16_a02_v02 one. Finding the textures will be more difficult. They could be the saber_high04_a01_v01 ones: The normals map seems to have extra channel information that looks like corresponding to the glowy bits.

Edit: nope, they don't match. I'll have to go through a few folders by eye. It is strange that this model hasn't been catalogued yet (unless I'm missing something)
## Post #557
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-30T14:05:11+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

The Outbreak Response Lightsaber exists at [TORCommunity's 3D model viewer](https://torcommunity.com/tools/model-viewer) as Lightsaber Style 40. You can check it [here](https://p3d.in/nbXo8), too.

It's fully textured in the viewer, so I assume the saber has to be listed somewhere in the game's XML files including model and texture references.

Interesting: Searching their database and locating the item [here](https://torcommunity.com/database/item/80i21B2/outbreak+response+lightsaber/?#tab-details), there's the DETAILED DATA tab listing a boatload of XML information about the item. Going down I've managed to find the Model ID, file name and directory:

[Model] => \art\dynamic\weapon\model\saber_high16_a02_v02.gr2

Sadly, I'm finding no hits for the filename in any of the game assets' text files, so I wonder how the TORCommunity people managed to do it
## Post #558
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-06-30T14:46:09+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Noesis to the rescue (but how?)!

Using Noesis' SWTOR plugin's texture loading functionality (which I discovered a couple of weeks ago by watching RealymanLP's YouTube tutorial… in German, a language I don't understand. Luckily, the involved steps were quite clear in the video anyway) I tried previewing the saber and it loaded with its textures, so I exported them without any trouble.

But where did Noesis get the necessary information from? I've been doing all kind of indexed searches through the game's XML files from the desktop, to no avail, and that used to be the fastest route, once one has exported all the game's assets.

Oh, well…


HOW TO MAKE NOESIS SHOW SWTOR's 3D MODELS WITH THEIR TEXTURES ON:

Inside the folder at noesis\plugins\python there is a file named swtor-config.xml. Opening it with any text editor, it shows a <ResourcePath>with a sample directory path. One must rewrite it with the path to the folder where one has been extracting all the assets coming from the game's .TOR files whose name starts with "swtor_main_art" (or, if one has extracted just everything, the folder where one did so).

Once saved, Noesis will load the textures of the objects it previews whenever possible, and will be able to export them too.

(sorry if most of you knew that already or if it was mentioned in the thread. I'm just a bit slow for such things   )

By the way, I've managed to run Noesis on my Mac through Wine, which means it ought to work on Linux too, just in case that is of interest to anybody (although I game on PC, I'm Mac-based for most everything, including toying with Blender)
## Post #559
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-07-01T08:00:25+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

After a week of "pain in the ****" with modelling and textueing - i finally did what i wanted! MAjor redesign of MAlgus Armor + remodelling to make it hood down 

Big thanks for your help!
## Post #560
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-07-01T13:07:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Congrats on your results
## Post #561
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-07-15T10:54:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey all!
I have a new hashlist for you! [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)

Edit (17.07.2019): Updated!
## Post #562
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-07-19T21:11:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hashes file updated to PTS 6.0.0 #4 [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #563
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-07-20T23:58:33+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from RealymanLP ↑Sat Jul 20, 2019 5:11 am at Sat Jul 20, 2019 5:11 am
>
> Hashes file updated to PTS 6.0.0 #4 https://drive.google.com/drive/folders/ ... sp=sharing

Thank you! A question if it isn't a bother: Could you point me to some guide about how to have EasyMyp extract only the difference between a new hash file and a previous one? I usually keep a full game asset extraction set around, and when a new hash file arrives I do a new full one out of ignorance on such matters. I guess it's explained somewhere in these forums but for the life of me I can't find it.
## Post #564
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-07-21T11:17:05+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Sun Jul 21, 2019 7:58 am at Sun Jul 21, 2019 7:58 am
>
> 
RealymanLP wrote: ↑Sat Jul 20, 2019 5:11 amHashes file updated to PTS 6.0.0 #4 https://drive.google.com/drive/folders/ ... sp=sharing

Thank you! A question if it isn't a bother: Could you point me to some guide about how to have EasyMyp extract only the difference between a new hash file and a previous one? I usually keep a full game asset extraction set around, and when a new hash file arrives I do a new full one out of ignorance on such matters. I guess it's explained somewhere in these forums but for the life of me I can't find it.

Do you mean what the hash file does?
In the hash file are the filenames of the whole individual files inside. With a more recent file, you can unpack more files with the correct name.
## Post #565
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-07-21T11:28:05+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Sorry, I meant some way to extract only the new items in your latest file instead of just everything all over again. I'm guessing I could try finding some utility that shows the differences between your latest hash file and the one before it, and feed the result to EasyMyp.

(It wouldn't be a problem to just let EasyMyp do the whole hash list again if not for sometimes the program getting stuck while at it, which means I have to keep an eye on it)
## Post #566
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-07-21T12:02:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey!

You can use the file names.zip in the download folder. There you can find all filenames from the hashlist and import it to your currently list.
## Post #567
- Username: Gezmondo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 21, 2016 10:53 am
- Post datetime: 2019-07-22T07:49:56+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello all, so I've been working on making a soundtrack with all the original music (AKA Non-John Williams) from the base game and expansions, using files that were already extracted from a post over on FFShrine, along with the stuff that BioWare has officially released and some fan soundtracks for KotFE/ET. Granted, I'm not sure how much of an audio quality difference there is from what is out there to what I am doing, but It's given me a reason to learn more about Adobe Audition.   However, since BioWare has yet to release the music that was made for Ossus, I decided to just try and put one together myself. But, I could use some help/pointers, as I really don't want to just sit on Ossus or Dantooine and record only the music (I did that on Quesh and Ilum, and it was not fun).

So, I am wondering if there is a file in the main_area files, or somewhere else that would tell me which music file plays on the planet, or even if I can find which patch the music file was added. Or would I just need to listen to them and hope for the best?

Thanks!
## Post #568
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-07-27T17:47:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Filenames updated to PTS 6.0.0 #8 [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #569
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-07-27T23:17:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Gezmondo ↑Mon Jul 22, 2019 3:49 pm at Mon Jul 22, 2019 3:49 pm
>
> 
…since BioWare has yet to release the music that was made for Ossus, I decided to just try and put one together myself. But, I could use some help/pointers, as I really don't want to just sit on Ossus or Dantooine and record only the music (I did that on Quesh and Ilum, and it was not fun).

So, I am wondering if there is a file in the main_area files, or somewhere else that would tell me which music file plays on the planet, or even if I can find which patch the music file was added. Or would I just need to listen to them and hope for the best?

Thanks!I've found no such music list file, but doing some desktop searching in my extracted assets folder I've seen a "location_5_10_ossus_data.bnk" file at the resources > bnk2 directory. It weights about 15.4 MB. so perhaps that could be the one.
## Post #570
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-08-01T09:34:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Does anybody know of any forum/thread outside Xentax where actual usage of SWTOR's texture files in packages such as Blender is discussed? Out of this thread I've figured out most of what each type of texture (_d, _n, _m, etc.) and its channels do, but I still have holes in my knowledge (say, how to apply skin tones and dyes' XML values to simulate SWTOR's hueing system, how to apply complexion textures in a way that doesn't create a noticeable difference between the skin of the head and the rest of the body, or how to translate the _s textures' values to what a Principled BSDF shader would accept). I made notes out of what was discussed in this forum, even took a look at the game's hueing shader code ("we all float down here"  ), but certain things, like how some of the eye textures work, weren't talked about at all.

I've been building in Blender a shader node group that accepts all the usual texture files associated to a SWTOR object without need for modifying them at all, for efficiency's sake, exposing fields for entering dyes' colour data, etc. Things like masking the areas that each of the colours of a dye affect are easy but, sillily enough, using the shininess maps correctly and a few others aren't.

At most, I've seen what some artists on DeviantArt have published and shared, including some Blender add-ons that import XNALara models, and SWTOR models ported to XNALara (some heroic person did [the whole interior of the Fury Class Interceptor ship](https://www.deviantart.com/torol/art/Fury-Class-Interceptor-V2-SWTOR-for-XNAlara-744563176)!). Studying the shader node system that comes out of importing such models is enlightening, but only to an extent, as those XNALara models had their SWTOR textures altered (or omitted in some cases).
## Post #571
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-08-08T12:41:54+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hashlist and filenames updated to PTS 6.0 #11 [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #572
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-08-27T08:31:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hashlist and filenames updated to PTS 6.0 #15 [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #573
- Username: CaptnKoda
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 07, 2018 1:36 am
- Post datetime: 2019-09-07T12:57:08+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

@ZeroGravitas I've gotten pretty comfortable using the textures in Blender myself, the image below being my typical Blender setup



As much as it seems really simple, this seems to work well enough for most materials. I use the _m map outside of Blender in photoshop, using the Green and Red channel as masks. If you know of a way to do it within Blender itself, I would really like to know if you've no problem sharing the knowledge. I've found through old posts on this forum that the alpha of the _s or _gloss map is strictly responsible for an objects roughness/shininess. I would usually use a colour ramp to alter it, as out-of-the-box it can produce some ugly results. It can also be used for the metalness of an object, though some fine tuning with the colour ramp would be needed to isolate the parts that actually should be metal. A good example of this is the Huttsbane's jacket, with the circular metal discs on the scarf and jacket.

For objects that have some transparency to them, I use a slightly different node setup that uses the emission and opacity textures. Not all textures come with these though, I know a few character customisation items don't like the headset for the cyborgs. They're a part of the unaltered normal map and need to be removed manually. 

If you want to see how these materials look, I have an imgur album here ([https://imgur.com/a/ZKhxacX](https://imgur.com/a/ZKhxacX)) of the stuff I've been creating with it. I've added my own take on the Fury at the bottom just for you
## Post #574
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-09-07T15:21:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Those renders of yours are most impressive and inspiring! Myself, I've been so obsessed with the matter of understanding SWTOR's materials system that I haven't tried building a proper scene yet and am just fighting the whole thing to get my player characters to look right. It doesn't help that I'm learning Blender on the fly, but I'm getting to like it a whole lot.

(I'm afraid that, for some reason, your image attachment shows as a broken icon in your message)
EDIT: I can see the attachment now   

Separating the maps' channels to be able to use them as masks inside Blender is fairly easy thanks to the 'Separate RGB' converter node. This is the way I'm simulating the use of Dyes on a piece of gear or the color changes that Bioware applies to some items to create new varieties.




How-to-simulate-dyeing.png (112.81 KiB) Viewed 243 times



(It's a bit simplified, but I'm using the same principle for other properties such as, say, shininess, which means repeating the mixing process for each material's feature. I'm trying to use the Node Groups feature to create a few reusable ones: environment items, gear, skin+face and some others so that, for each model's piece, I just add the relevant node group, plug the texture files, tweak a few values, and get almost there before any node tweaking (I too can use node groups to store, say, common skin tone values for all visible body parts. It's the closest thing to having global variables for nodes).

Thank you for the advice on using a color ramp on the roughness/shininess channel, as I was getting poor results there and that was one of the things I was most frustrated about.

Something I'd like to do in a following post is to summarise what I know and what I don't about all the texture files and their channels (I was going through all the posts these last days to make sure I hadn't missed anything). For example, I haven't the faintest idea about how to use the _h ones, and I have several questions about the face and eye-related textures. It would be great to compare notes.
## Post #575
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-09-08T00:53:46+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

This is what I've got out of interpreting [this post](https://forum.xentax.com/viewtopic.php?f=10&t=7186&start=210#p88047) and [this one](https://forum.xentax.com/viewtopic.php?f=10&t=7186&start=210#p88127). I should note that, rather than using Noesis to locate specific items and produce their meshes and texture files, I gather everything "manually" out of using jedipedia.net's references: It's just that Noesis, when exporting single models, converts RotationMaps to traditional "blue" normal maps automatically, so what I'm posting here wouldn't quite apply.

-------------------

_d DiffuseMap:
RGB: diffuse, ambient, emissive colors.
Alpha: Unused most of times. On ocassion seems to do as… some kind of Reflectivity map?

-------------------

_n RotationMap:
R: visibility mask, if in use.
G: normal map's G channel.
B: emissivity, if in use.
Alpha: normal map's inverted R channel.

I'm using [this recipe](https://forum.xentax.com/viewtopic.php?f=10&t=7186&start=420#p139665) from the thread to turn this "green" normal map into the classic "blue" type: Alpha to R, G to G, fill B with white. This is the kind of thing I'd package as a Node Group in Blender for reuse.
(SWTOR Fan spoke of "bump map" channels instead of "normal map" ones, but I assume they are normals, as they are multichannel and as far as I understand bump maps are greyscale.)

-------------------

_s GlossMap:
RGB: specular color.
Alpha: shininess

After googling suggestions on how to use specular workflow-type maps in metalness workflow shaders, the gross rule of thumb seems to be to square and invert the shininess values. [johnzero7 at DeviantArt](https://www.deviantart.com/johnzero7) has a [XNALara-to-Blender](https://www.deviantart.com/johnzero7/journal/XPS-tools-2-0-0-for-Blender-2-80-final-release-808426599) importer Addition, and the node arrangements it produces apply that to the RGB specular color (previously converting it to greyscale) instead.



specular-to-roughness.png (9.87 KiB) Viewed 233 times



Reading [this article](https://marmoset.co/posts/pbr-texture-conversion/#spectometal) I think I kinda get the reason why. In the end, I guess your method is the most practical one.
The thing is, though, that Blender has a Specular node that might deal with SWTOR's Gloss maps correctly (I just noticed its existence today. Got to test it).

-------------------

_m PaletteMaskMap:

If material is of the Uber type (such as furniture, tech items, etc.)
R: Opacity.
G: bump map's R channel.
B: emissivity.
Alpha: bump map's G channel.

(Again, G and Alpha are described in the SWTOR thread as "bump map" channels, but I always understood bump maps to be single channel, greyscale images. Could they be Normal maps instead, or some kind of normal map modifiers? I don't know how I should go about applying them)

If material is of the Garment type (such as armor gear, etc.): 
R: Palette1 mask for hue/spec/lightness/contrast override.
G: Palette2 mask for hue/spec/lightness/contrast override.
B: Metalness mask?
Alpha: unused, or a mask for letting skin show in sexy gear  like, say, Casual Vandal Jacket.

For now, when applying Dyes to the pieces of armoring through those masks, I'm applying HSV nodes and the like through the masked regions, as it is quicker to judge the results by eye.

-------------------

_h PaletteMap: I haven't the faintest idea about its usage.

(When it is associated to a head material, the R channel seems to mask the tongue, eyelashes and upper eyelid. To preserve them from hueing, perhaps?)


I'll write tomorrow another post referring to my troubles with body skin, face and eye materials.
## Post #576
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-09-08T22:41:52+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

(follow up to [this post](https://forum.xentax.com/posting.php?mode=reply&f=10&t=7186#pr156018))

------------------------------------------------------

Regarding characters' skin (I think the Material type is called SkinB): everything looks mostly like in the previous post, keeping consistency while making use of less channels given the simpler demands of the skin material (except the head one, where things get very interesting).

-------------------

_d DiffuseMap:
RGB: diffuse, ambient colors.
Alpha: Unused.

-------------------

_n RotationMap:
R: visibility mask (fully black, usually).
G: normal map's G channel.
B: emissivity again? (fully black, usually).
Alpha: normal map's inverted R channel.

-------------------

_s GlossMap:
RGB: specular color.
Alpha: shininess

-------------------

_m PaletteMaskMap:
R: (fully white, usually).
G: (fully black, usually).
B: (fully black, usually).
Alpha: (fully black, usually).

Seems to be there for consistency, mostly. As changing the skin color of a character affects the full bodyparts, I don't see any use for it as a mask (I guess Bioware could take advantage of it in the future).

About the Character Creator's Skin Color selector: the "simplest" way I've found to re-hue the DiffuseMap with the RGB values for each color in the slider that show up in the .XML files is to feed those values to a Mix RGB node set to Color transfer mode (kind of as one could do in Photoshop by painting with the pencil or overlaying a solid color using that transfer mode). I tried two of my characters' settings (pale white and pale red/pinkish) with that method and the result is very close, if not identical to their in-game's looks.




Re-hue.jpg (42.4 KiB) Viewed 220 times



-------------------

_h PaletteMap: no idea about its usage.
(its channels seem to contain copies of the diffuse channel at different intensities)

-------------------

Something to point out: in the .mat files there are lots of parameters there to modulate everything. Their names are fairly self-explanatory and I can try to approximate the results, although some of them suggest being a bit subtler in their use. I'm most interested in FleshBrightness, as it seems to apply to the Rattataki species' bright white skin, and FlushTone, which I wonder how it works. See:

RimWidth (float)
RimStrength (float)
FlushTone (RGBA)
FleshBrightness (Float)
DirectionMap (associated texture)
ReflectionSpecInfluence (float)
etc.


------------------------------------------------------

Regarding characters' heads: there are a series of additional texture files types:

Age:
looks like a _n style of RotationMap containing normal data to combine with the base normal map in some manner. I have somewhere a Blender nodes recipe to mix normal maps. Got to try and see what happens.

-------------------

Complexion: 
RGB: Diffuse color.
Alpha: ignored.
Looks like overlaying the RGB by applying some Photoshop-like transfer mode (Multiply seems to work well).

-------------------

FaceHair: The folder contains only a single pair of DiffuseMap and RotationMap with flat values in their channels.
Actually useful in any way?

-------------------

FacePaint: (seems specific to certain NPCs such as companion Nadia Grell)
RGB: Diffuse color.
Alpha: Alpha.
Looks like simply overlaying the diffuse color through the alpha.

-------------------

Make_Up: 
RGB: Diffuse color.
Alpha: Alpha.
Looks like simply overlaying the diffuse color through the alpha.

-------------------

Pattern: feline hair color patterns for Cathar only.
RGB: Diffuse color.
Alpha: Alpha.
Looks like simply overlaying the diffuse color through the alpha.

-------------------

Scars:
RGBA: unclear.
Looks like a _n style of RotationMap containing normal data to combine with the base normal map in some manner. The R channel is filled with black. I'm noticing that scars have a certain amount of coloration, so I'm wondering if instead of a normal map it is a bump map and perhaps some coloration mask. One can make a bump map out of the most prominent-looking channel to make things simpler, anyway.

(In the old posts people seemed to use the terms "bump map" kind of interchangeable with "normal map", so I don't know if the game uses traditional bump maps at all or actually everywhere)

-------------------

Tattoos:
RGB: Diffuse color.
Alpha: Alpha.
Looks like simply overlaying the diffuse color through the alpha (the alpha isn't fully opaque, letting some of the DiffuseMap show through and give the tattoo some of the underlying skin texture).

-------------------

Wrinkles: 
_wm: unclear: weight maps for face bones?
_w: unclear.


------------------------------------------------------

Regarding characters' eyes (I think the Material type is called Eye):

-------------------

_d DiffuseMap:
RGB: diffuse.
Alpha: empty.

-------------------

_n RotationMap:
R: visibility mask (fully black, usually).
G: normal map's G channel.
B: emissivity (actually of use at times: Chiss eyes, plague infectees, etc.).
Alpha: normal map's inverted R channel.

-------------------

_s GlossMap:
RGB: specular color.
Alpha: at times empty, others simply there's no alpha at all, but I've seen it used in a couple of cases.

-------------------

_m PaletteMaskMap: 
R: Eye color mask.
G: Filled with black mask. It seems to have to do with the reflectivity, which would affect the whole eye, then.
B: Unknown: looks like a copy of the R channel but some species have it and others have it blank. I can't see what's the criteria.
Alpha: Unused in most species. Rattataki even lack the channel.

-------------------

_h PaletteMap: as usual, no idea what it does. Some of those channels could have to do with Dark Side glowy eyes' emissivity and Dark Side corruption effects.

-------------------

Eyecubemap.dds seems to be the cubic environment map Bioware is currently using for the eyes' main catchlights, mixed in some manner and to some degree with the environment maps corresponding to each locale in the game. As Blender doesn't seem to understand the way .dds-formatted cubic sky maps work, I'll have to Photoshop it into shape or make my own (cubic sky maps are a general issue for Blender, I believe: it uses its own arrangement of the six views instead of the usual horizontal cross type).
Anyway, the eye's reflections will come naturally from the scene, so… But it would be nice to create some kind of directable eye highlights.


------------------------------------------------------

And that's all, I think. Of course, probably most of all that texture data can be omitted or approximated manually, but I'd still like to know all about those flippin' _h maps and the other subtleties.

Sorry for the (incomplete) info dump. I hope it comes useful somehow.
## Post #577
- Username: Pomelo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 21, 2015 5:56 am
- Post datetime: 2019-09-09T19:37:18+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

This is the node setup i use for normal maps ( .dds textures ending with _n). As stated on a post previously, the Red channel is completely black, the green is for vertical height information, and the alpha channel is where the red or horizontal height is.
## Post #578
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-09-09T20:06:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks. I'll try that instead of that recipe I was following.

(I've just discovered that the alpha in the _m texture files for gear pieces seems to hold the areas that let skin show in sexy chest armor pieces like, say, the [Casual Vandal Jacket](https://swtor.jedipedia.net/en/itm/casual-vandal-jacket))
## Post #579
- Username: DarthAtroxa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 16, 2019 8:26 pm
- Post datetime: 2019-09-10T17:17:16+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Bit of a n00b question but are you guys able to import the SWTOR GR2 files directly into blender or are you using an intermediary like say converting to .obj using Noesis?

FWIW I've found that alpha in the _m texture only works for displaying skin when the area of the model the alpha corresponds to uses the "defaultMirror" material within the GR2 file. In other words you can't control where skin is visible or not visible purely using the alpha in the _m texture.
## Post #580
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-09-10T19:05:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

n00b here myself    . Yes, I'm using Noesis to previously convert the meshes to .obj.

My guess is that when SWTOR characters use armor that shows skin, that skin is the relevant body part's skin texture applied to those "defaultMirror" areas of the armor's mesh, isn't it? The thing is, I'm kinda trying to "dress" my characters instead of replacing body parts, for dubious convenience, and I got some partial success. Not as automatic a process as I'd wish, though. We'll see.

(I need to check all the material types the game uses, to try to better generalize my nodes setups)

By the way, any ideas on what the _h texture files' channels might do  ?
## Post #581
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-09-13T21:05:18+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Regarding SWTOR's Character Creator: is there any XML file describing the correspondence between the sliders' numbers and what they refer to? For now I'm having to find my characters' heads by eye. Things like eye, hair or skin colors seem to keep the same order in their XMLs as to what the Creator shows, but the heads are a nutty affair:

24 human head meshes shown in Caucasian - Caucasian NPC - African - African NPC - Asian order.
15 Chiss head references (to human ones) in a Caucasian - Asian - African order.
15 Zabrak Sith head references in a Asian - African - Caucasian order.
etc.

Given that, I've been writing a table of heads slider numbers-to-mesh files, but it isn't ideal as I'm having to compare what I see in the game to the meshes by eye. Surely there must be a file where all that is referenced in a rational manner.
## Post #582
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-09-15T13:36:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hashlist and filenames updated to PTS 6.0 #21 [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #583
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-09-15T13:42:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Trying using the _m texture file's alpha mask that skin showing gear seems to use in some manner.

This is the Casual Vandal Jacket. The model comes with a visible shirt part that usually is textured as such for the plain variant, but it can use the character's skin textures too (the UVs match). I was trying to work it differently: I disabled the shirt mesh, and I applied the mask to the character's body to have it visible in that area only (too much artifacting, otherwise).

Sadly, the mask doesn't work too well, as it leaves those visible holes at those angles. I'll have to play by their rules, then, but I'm not sure how to make textures such as those full body tattoos of mine work, as they aren't using the original UVs currently.



Casual Vandal Jacket.jpg (28.27 KiB) Viewed 144 times
## Post #584
- Username: DarthAtroxa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 16, 2019 8:26 pm
- Post datetime: 2019-09-15T19:08:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Sat Sep 14, 2019 5:05 am at Sat Sep 14, 2019 5:05 am
>
> 
Regarding SWTOR's Character Creator: is there any XML file describing the correspondence between the sliders' numbers and what they refer to? For now I'm having to find my characters' heads by eye. Things like eye, hair or skin colors seem to keep the same order in their XMLs as to what the Creator shows, but the heads are a nutty affair:

24 human head meshes shown in Caucasian - Caucasian NPC - African - African NPC - Asian order.
15 Chiss head references (to human ones) in a Caucasian - Asian - African order.
15 Zabrak Sith head references in a Asian - African - Caucasian order.
etc.

Given that, I've been writing a table of heads slider numbers-to-mesh files, but it isn't ideal as I'm having to compare what I see in the game to the meshes by eye. Surely there must be a file where all that is referenced in a rational manner.I'm not aware of any XML file but if you use the NodeViewer and look at the entries under pcs > class > gender > species it should be possible to map the different head models to the different sliders for that combo of class/species/gener.

Sorry I couldn't be more helpful!
## Post #585
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-09-15T19:50:32+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks   . I've never used that tool (I mean, I tried it but didn't see what to take advantage of it for). Let's see what I dig.

EDIT: looks promising. I've got some doubts about how it organises the entries (I suspect it piles up all the heads for the four body types) but I'll give it a try an afternoon and see what I get.

EDIT 2: is there any way to export its texts? One can't copypaste them, and it's a lot of typing getting to check each reference.
## Post #586
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-10-13T09:33:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

A quick question about SWTOR's native objects' absolute scale and Noesis:

I notice that, when converting from .gr2 to .obj, the resulting objects appear to be scaled down to a tenth of their "real world" size (assuming 1 unit is 1 metre). I can add a scaling command during batch conversions to compensate instead of correcting that in Blender, so that's not too much of a problem, but I was wondering if this was because of the way the game assets are stored or out of Noesis' or the SWTOR plugin's behaviour.

Edit: Could a variant of Noesis' SWTOR plugin be made that limits itself to converting meshes and prescinds of checking associated texture files and the like, to speed up simple batch-conversion of the whole game's 3D assets from .gr2 to .obj? If it could also omit warnings of conversion failures and just continue working it would be a godsend (I'm having to use AutoHotKey to autoclick the warning dialogs away, which makes the PC unusable while it's working on that).
## Post #587
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-10-13T12:43:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hashlist and filenames updated to PTS 6.0 #28 [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #588
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-10-20T20:47:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey SWTOR-Friends,

since yesterday 6.0 is available to download. You can use the [predownloader](https://torcommunity.com/tools/swtor-pre-downloader), if you have a non-bitraider launcher, to download it now.

I already mined this update, but didn't found much new.
But I created a new hash and filename list anyway for you: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)

I also created a [playlist on youtube](https://www.youtube.com/playlist?list=PL0H7wSPQruMTeMCGvteT_APxgOpfm4lRS) with all of my Datamining Videos of 6.0. Also feel free to take a look at [this reddit post](https://www.reddit.com/r/swtor/comments/dk7dof/spoiler_swtor_60_datamining_story_excerpts/) by me.

Greetings
-RealymanLP
## Post #589
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-10-20T21:16:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thank you for all the effort  I'll give it all a look
## Post #590
- Username: wawawawawawa
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 30, 2019 4:05 am
- Post datetime: 2019-10-29T20:07:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

is there an off-line mode or emulator for swtor? even if it's WIP
## Post #591
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-10-30T15:32:13+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey wawawawawawa
Currently I know nothing about that. Sorry.
## Post #592
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-11-11T00:04:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I just found this by sheer chance. It might be of some use.

[CINEMATIC CHARACTER LIGHTING IN STAR WARS: THE OLD REPUBLIC](http://twvideo01.ubm-us.net/o1/vault/gdc2011/slides/Ben_Cloward_Art_Cinematic_Character_lighting.pdf)

It's a PDF of a presentation on the subject, 156 slides long. It explains several of the tricks they use at the shader level and the like to personalize each planet's environment lighting, simulate bounce light, rim light, certain specularity nuances, depth of field, etc.
## Post #593
- Username: Xorras
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 08, 2016 12:39 am
- Post datetime: 2019-11-13T23:23:02+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Does anyone know if there is a texture somewhere for high poly station (imp/rep fleet station i mean) model?
## Post #594
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-11-13T23:48:54+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Xorras ↑Thu Nov 14, 2019 7:23 am at Thu Nov 14, 2019 7:23 am
>
> Does anyone know if there is a texture somewhere for high poly station (imp/rep fleet station i mean) model?

At resources > art > static > vehicle > neutral > texture there are several textures whose names start with "veh_neu_space_station" that could be what you are looking for.

The model they seem to be related to, called veh_neu_space_station.gr2, is at a lower directory level, at:
art > static > vehicle > neutral
## Post #595
- Username: toomanyluigis
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 30, 2014 12:36 pm
- Post datetime: 2019-11-17T15:28:25+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Im trying to edit the jetpack nodes on some armors but even swapping models in game seems to have no affect. Does anyone know where the jetpack nodes are stored for armors?
## Post #596
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-11-24T15:05:47+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

No idea, I'm afraid
## Post #597
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-11-24T15:11:56+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I'm kind of making sense of NodeViewer's info on Players Characters' appearance and how it relates to the Character Creator's sliders. It's a chore because one can't dump the app's listings into a text file where to tidy things up, so one has to go back and forth a lot.

Unless there is some way to dump it?
## Post #598
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-11-25T18:24:07+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

New hashlist for 6.0.1a: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #599
- Username: DarthAtroxa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 16, 2019 8:26 pm
- Post datetime: 2019-11-27T21:06:09+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Sun Nov 24, 2019 11:11 pm at Sun Nov 24, 2019 11:11 pm
>
> 
I'm kind of making sense of NodeViewer's info on Players Characters' appearance and how it relates to the Character Creator's sliders. It's a chore because one can't dump the app's listings into a text file where to tidy things up, so one has to go back and forth a lot.

Unless there is some way to dump it?Have you tried right clicking on a node in the left hand pane and selecting extract? This will usually output the contents of that node(s) to CSV file(s) in the "extracted" folder in the NodeViewer folder.
## Post #600
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-11-27T21:20:56+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from DarthAtroxa ↑Thu Nov 28, 2019 5:06 am at Thu Nov 28, 2019 5:06 am
>
> 
ZeroGravitas wrote: ↑Sun Nov 24, 2019 11:11 pm
I'm kind of making sense of NodeViewer's info on Players Characters' appearance and how it relates to the Character Creator's sliders. It's a chore because one can't dump the app's listings into a text file where to tidy things up, so one has to go back and forth a lot.

Unless there is some way to dump it?
Have you tried right clicking on a node in the left hand pane and selecting extract? This will usually output the contents of that node(s) to CSV file(s) in the "extracted" folder in the NodeViewer folder.
Can I marry you  ? You just saved me from a slow, torturous death-by-copy-pasting (seriously, I was just starting to try to make a spreadsheet out of that, and dreading the whole thing).

Are there more tricks I should know? I tried to learn more about how NodeViewer works, but I didn't find anything.
## Post #601
- Username: DarthAtroxa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 16, 2019 8:26 pm
- Post datetime: 2019-11-30T12:03:37+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Thu Nov 28, 2019 5:20 am at Thu Nov 28, 2019 5:20 am
>
> 
DarthAtroxa wrote: ↑Thu Nov 28, 2019 5:06 am
ZeroGravitas wrote: ↑Sun Nov 24, 2019 11:11 pm
I'm kind of making sense of NodeViewer's info on Players Characters' appearance and how it relates to the Character Creator's sliders. It's a chore because one can't dump the app's listings into a text file where to tidy things up, so one has to go back and forth a lot.

Unless there is some way to dump it?
Have you tried right clicking on a node in the left hand pane and selecting extract? This will usually output the contents of that node(s) to CSV file(s) in the "extracted" folder in the NodeViewer folder. 

Can I marry you  ? You just saved me from a slow, torturous death-by-copy-pasting (seriously, I was just starting to try to make a spreadsheet out of that, and dreading the whole thing).

Are there more tricks I should know? I tried to learn more about how NodeViewer works, but I didn't find anything.Not that I know of.
## Post #602
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-11-30T18:45:38+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

nvm
## Post #603
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-11-30T18:56:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

And i have question about nodes

i extracted it - edit - how to convert edited one back to .node format to use in game?
## Post #604
- Username: twitkiss
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Apr 02, 2018 10:33 pm
- Post datetime: 2019-12-07T05:13:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks for these hash file updates.

I am having the hardest time finding this hairstyle - 
[https://www.reddit.com/r/swtor/comments ... hairstyle/](https://www.reddit.com/r/swtor/comments/8h3h16/new_free_hairstyle/)

Wondering if someone could help me out.
## Post #605
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-12-07T13:17:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I did a first try at finding it and it's proving to be difficult. I'll try again later on.
## Post #606
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-12-07T16:28:37+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from probe88 ↑Sun Dec 01, 2019 2:56 am at Sun Dec 01, 2019 2:56 am
>
> 
And i have question about nodes

i extracted it - edit - how to convert edited one back to .node format to use in game?

Anyone?
## Post #607
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2019-12-07T16:29:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from twitkiss ↑Sat Dec 07, 2019 1:13 pm at Sat Dec 07, 2019 1:13 pm
>
> 
Thanks for these hash file updates.

I am having the hardest time finding this hairstyle - 
https://www.reddit.com/r/swtor/comments ... hairstyle/

Wondering if someone could help me out.

/resources/art/dynamic/hair/model/hair_human_non_a30_bmn.gr2
## Post #608
- Username: twitkiss
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Apr 02, 2018 10:33 pm
- Post datetime: 2019-12-07T22:28:28+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from probe88 ↑Sun Dec 08, 2019 12:29 am at Sun Dec 08, 2019 12:29 am
>
> 
twitkiss wrote: ↑Sat Dec 07, 2019 1:13 pm
Thanks for these hash file updates.

I am having the hardest time finding this hairstyle - 
https://www.reddit.com/r/swtor/comments ... hairstyle/

Wondering if someone could help me out.


/resources/art/dynamic/hair/model/hair_human_non_a30_bmn.gr2

Well shoot.  Still can't get the mesh for some reason.  I'm just gonna try and ninjarip it
## Post #609
- Username: SilentxValkyrie
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 31, 2018 9:29 pm
- Post datetime: 2019-12-09T11:45:29+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Does anyone know how to fix the unhandled exception has occured. Error.

Input string was not in a correct format. 

Really weird because it never happened to me before. But now it does it whenever I try to open a archive. And it pretty muchs stops easy myp

Tried both tor myp and easy myp and dosnt seem to make a difference regardless of version
## Post #610
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-12-10T00:42:55+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I think something similar happened to me some time ago, and I had to use fresh copies of both TorMyp and a hash file to make it work again.
## Post #611
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-12-12T17:05:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hashes and Filenames updated to 6.0.2: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #612
- Username: SilentxValkyrie
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 31, 2018 9:29 pm
- Post datetime: 2019-12-14T01:14:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I am going to try and reinstall the game and do some stuff to get it to work
Does anyone know what the names.txt file does in regards to to the hashfiles_etc...
Where do you put names? 
i know you put hashfiles in the hash folder
Anyone got a updated tor myp extractor tool or fresh/clean download
## Post #613
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-12-14T01:30:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

RealymanLP kindly posted the tools here a while ago: [viewtopic.php?p=151229#p151229](https://forum.xentax.com/viewtopic.php?p=151229#p151229)
That download includes TorMYP, Noesis and NodeViewer. I believe that's the latest release.

I think the names.txt file isn't needed to operate TorMYP. At least I've never used it with the app.
## Post #614
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2019-12-14T14:59:35+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey all!
The names.txt is a file with only the filenames without hash-values. When you use TorMYP it's not important for you.
In my SWTOR-Tools package the hashlist is not up-to-date.
When you download TorMYP from the link, ZeroGravitas posted, replace the current hashes_filename.txt in the hash folder with the newest file I linked some posts above this.
Don't forget to extract the hashes_filename.txt from the zip first-  

<Where do you put names? >
I am finding the names with a program.
## Post #615
- Username: twitkiss
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Apr 02, 2018 10:33 pm
- Post datetime: 2019-12-14T18:12:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Is anyone running TorMYP on Win10?   I haven't been able to get it to run, it usually closes out when I get to the Extract All From Folder step.  I've tried running as admin, going Win 7 compatibility, but nothing seems to work.  

Just wondering if there were any other tricks I should try.  Currently, I get what I need using an old laptop but if I could figure this Win10 compatibility issue out it would make things a lot easier.
## Post #616
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-12-15T00:12:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I run it on Windows 10 (64bit, but that's typical nowadays) and I'm not doing anything special at all to have it work
## Post #617
- Username: twitkiss
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Apr 02, 2018 10:33 pm
- Post datetime: 2019-12-15T14:25:46+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Sun Dec 15, 2019 8:12 am at Sun Dec 15, 2019 8:12 am
>
> 
I run it on Windows 10 (64bit, but that's typical nowadays) and I'm not doing anything special at all to have it work

Thanks for the response.  It's just so weird.  I'm not doing anything different than I do on my old laptop.  Oh well.
## Post #618
- Username: Marillocke
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 22, 2019 12:33 pm
- Post datetime: 2019-12-22T05:27:02+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Eh is there a way to convert an .obj/.dae./whatever to SWTOR-usable .gr2?
## Post #619
- Username: SilentxValkyrie
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 31, 2018 9:29 pm
- Post datetime: 2019-12-30T23:32:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I believe the reason the open archive isn't working is some new change to net framework and windows ten, thus any future assets may be difficult to extract on up to date systems. If anyone has the current extracted assets they could upload somewhere, it would be greatly appreciated as the only other solutions I can think of to get into the archives to even open them is an adjustment to the program, a different program or different way (any ideas?) or going on an older computer, I only do want the Gr2s and DDs/tex/mat files. My node viewer still reads the .tor files so at least I know my tor files and node viewer work, I wish I could extract the gr2's through node viewer.
## Post #620
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-12-31T13:36:59+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

My static and dynamic assets folders add up to some 50 GB. I have the bandwidth to get that uploaded anywhere in an evening (unless the zillion small files slow down the process), but I don't know where I could put them.

I think I don't have any Windows 10 autoupdate blocker in my PC, and the last time I did a full extraction was after SWTOR 6.0 Onslaught's release, so it still feels weird that you aren't able to. I'll do some testing later in the day to check that the same isn't happening to me, just to make sure.

I don't know if it would help but, just in case… Can you create a new, temporary user account in your Windows machine and try the apps there, to test that your troubles aren't due to some strange interaction with stuff in your normal user account?

Edit: I didn't delete the .gr2 files yet, and have .obj copies too, so surely that could be trimmed down quite a lot.

Edit 2: the .obj are about 14,5 GB, so the .gr2 and .dds ought to total about 35 GB.
## Post #621
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2019-12-31T16:32:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

By the way: I've managed to have Noesis work on my Mac wrapped in [WINE](https://www.winehq.org/) (accessing a copy of the game's .tor files that I moved to my Mac's HDD), exporting game objects without trouble so perhaps that might be a route if the problem proves itself unsolvable.
## Post #622
- Username: SilentxValkyrie
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 31, 2018 9:29 pm
- Post datetime: 2020-01-02T23:24:44+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Well I am pretty sure in order to use WINE I got to use a virtual machine with linux/mac OS and then run Wine to get windows in order to open it correct?
Also you can upload the 50 gig sized files to google drive with ease, google drive is good for that type of stuff, I did try the temporary account on windows and it didn't work unfortunetly, it seems to be the way the new netframework with latest windows handles new net expressions as before it let the error run and the error wasn't really an error and worked, however now it closes it unfortunetly D: also the newest windows update for main versions was 3 days ago and 4 days before that was the net framework update. Unfortunetly my laptop is the same but other machines would probably make it work until they update their files to that OS (If they need to that is). But yeah google drive should work if your willing, it would be extremely appreciated especially if you have all the OBJs with all their textures already compiled on them
## Post #623
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-01-03T14:31:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

About WINE: yes, I guess you would have to get, say, Oracle's VirtualBox, install some Linux plus Wine, and tell the thing to access the Windows folder where the game assets are. A bit eeergh  

Alright: I'll see about uploading the thing to my Gdrive. When it's ready I'll send you a linkie. About the .obj files, they are simply converted from the original .gr2 through Noesis, placed alongside. There are no texture conversions and assignments, I'm afraid. Given that, would you rather I omit them? That would save you a lot of space.
## Post #624
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-01-03T15:19:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

My Gdrive limits me to about 17 GB. I'll have to slim down things.
## Post #625
- Username: SilentxValkyrie
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 31, 2018 9:29 pm
- Post datetime: 2020-01-05T20:16:18+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Big shout out to zero for giving me ALL the assets up to date, and ontop of that the patience he had dealing with me!

Also big tip guys. If your textures arent showing on your noesis viewers, download Noesis 434 from a clean download place (the site or something, empty) I found out if u download it from someone else, and its a newer version, rarely does the config work in setting the right paths (probably because the paths auto generate in python) But also that way u can view with the textures and export easier! I found one on the youtube video of how to clean N mat files 

Make sure to download a fresh swtor python addon for noesis as well, found one by swtor miner in the noesis plugin thread that had some fixes and was empty (not plugged into someone elses noesis, previously)
## Post #626
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-01-18T11:39:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hashes and Filenames updated to Alderaan SH PTS Phase 2: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #627
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-01-18T17:49:15+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I've been given notice of a recent guide to extract SWTOR models for 3D-printing by means of Ninja Ripper, Noesis and Blender (or any other 3d app able to open .obj files and export .stl ones). I'm posting it here just in case it's useful:
[https://www.reddit.com/r/swtor/comments ... _3d_print/](https://www.reddit.com/r/swtor/comments/eptxfv/ripping_your_character_from_swtor_to_3d_print/)

The author has posted samples of the results, including downloadable models.
## Post #628
- Username: toomanyluigis
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 30, 2014 12:36 pm
- Post datetime: 2020-01-23T05:02:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Seems the mining tools (Pugtools) I have been using are now broken, they cant mine new abilities or items without the program crashing.

I cant contact the author to fix the problem, does anyone else have this experience?
## Post #629
- Username: fobk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 06, 2017 6:03 pm
- Post datetime: 2020-01-26T02:15:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Is there a way to extract from the .jba animation files?
## Post #630
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-01-26T11:20:09+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from fobk ↑Sun Jan 26, 2020 10:15 am at Sun Jan 26, 2020 10:15 am
>
> Is there a way to extract from the .jba animation files?
The people at Jedipedia.net said they had managed to decipher it. I don't know if they posted the information anywhere.
[https://swtor.jedipedia.net/en/news/skeletal-animation](https://swtor.jedipedia.net/en/news/skeletal-animation)
## Post #631
- Username: fobk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 06, 2017 6:03 pm
- Post datetime: 2020-01-26T11:32:13+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Sun Jan 26, 2020 7:20 pm at Sun Jan 26, 2020 7:20 pm
>
> 
fobk wrote: ↑Sun Jan 26, 2020 10:15 amIs there a way to extract from the .jba animation files?
The people at Jedipedia.net said they had managed to decipher it. I don't know if they posted the information anywhere.
https://swtor.jedipedia.net/en/news/skeletal-animation

I saw that but I wasn't able to find any information on how they managed it, was hoping someone on here might know.
## Post #632
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-01-27T15:57:35+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from fobk ↑Sun Jan 26, 2020 7:32 pm at Sun Jan 26, 2020 7:32 pm
>
> 
ZeroGravitas wrote: ↑Sun Jan 26, 2020 7:20 pm
The people at Jedipedia.net said they had managed to decipher it. I don't know if they posted the information anywhere.
https://swtor.jedipedia.net/en/news/skeletal-animation


I saw that but I wasn't able to find any information on how they managed it, was hoping someone on here might know.

As far as I know, they didn't published their methods of deciphing the jba-animations. But on their tools (not public) it's possible to see the animations. Here are some of it: [https://youtu.be/Kr49-CnTu0U](https://youtu.be/Kr49-CnTu0U)

They used reverse engineering to find out, how it's written and then they programmed the player for it by himselfes.
## Post #633
- Username: fobk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 06, 2017 6:03 pm
- Post datetime: 2020-01-28T04:58:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from RealymanLP ↑Mon Jan 27, 2020 11:57 pm at Mon Jan 27, 2020 11:57 pm
>
> 
fobk wrote: ↑Sun Jan 26, 2020 7:32 pm
ZeroGravitas wrote: ↑Sun Jan 26, 2020 7:20 pm
The people at Jedipedia.net said they had managed to decipher it. I don't know if they posted the information anywhere.
https://swtor.jedipedia.net/en/news/skeletal-animation


I saw that but I wasn't able to find any information on how they managed it, was hoping someone on here might know.


As far as I know, they didn't published their methods of deciphing the jba-animations. But on their tools (not public) it's possible to see the animations. Here are some of it: https://youtu.be/Kr49-CnTu0U

They used reverse engineering to find out, how it's written and then they programmed the player for it by himselfes.

Shame there doesn't seem to be a public way to use the jba's. Thank you for the reply.
## Post #634
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-02-06T13:55:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hashes and Filenames updated to Alderaan SH PTS 4: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)

Btw: If anyone interessts, which files are in the launcher, [here is a german video by me](https://youtu.be/zNyilGQOeH8).
## Post #635
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-02-07T18:43:22+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey SWTOR-Friends!

I made a newer version of the NodeViewer with lots of new gom type names for a better overview.
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1rpZMAM-J5etFH-jdcXlCU5fQHAWtU85g?usp=sharing)
## Post #636
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-02-07T18:50:09+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks!
## Post #637
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-02-10T12:38:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hashes and Filenames updated to 6.1: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)

-RealymanLP
## Post #638
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-03-07T20:00:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hashes and Filenames updated to 6.1.1 PTS #4: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)

-RealymanLP
## Post #639
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-03-08T11:19:55+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Nice! Thanks   


A couple of questions for anybody who could answer them:

Years ago, at [an old post](https://forum.xentax.com/viewtopic.php?f=10&t=7186&start=210#p88127) in this very thread, [SWTOR fan](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=38417) posted a link to the game's [HLSL code for the rehueing shader](http://pastebin.com/sDRVvBYy). Although it's almost gibberish to me (not so much for it being programming code but for the myriad math operations being done on the data), it kinda gave me some ideas for imitating its behaviour in Blender. As I'd like to give other shaders (the head skin one, eyes, hair, etc.) a look, I was wondering if that kind of shader code resides somewhere in the game resources in a human readable format, or if one has to convert it to such and how.

Also, are any of the people involved in those old efforts to understand SWTOR's texture mapping system ([SWTOR fan](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=38417), [swtor miner](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=44679), etc.) reachable somehow? I still have this itch with the _h PaletteMap files and what their RGBA channels mean. For now I've settled on using their alphas as a greyscale version of the _d Diffuse maps, so I can colour them in Blender by multiplying the colours specified in the XML files by them, which seems to work fairly OK, but I'd still wish for a general, short explanation of what the R, G, and B ones are meant to be for.
## Post #640
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-04-01T15:30:10+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have a Nodeviewer question. Are the game items' common names (say, "R-55 Searing Disruptor") stored somewhere visible in the Nodeviewer's tree structure? I'm trying to learn how to find them and derive stuff like Model IDs and FQNs from that, so that I'm able to work that out in the absence of jedipedia.net's database.

(as I'm no programmer, I'm thinking of using the Nodeviewer app directly or Explorer's indexed searches through exported .csv files, kind of what I already do through the game's exported .xml to locate gear meshes and textures, or through those very .csv files to identify player character creator settings and the corresponding head and body's meshes and textures)
## Post #641
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-04-02T11:52:37+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Wed Apr 01, 2020 11:30 pm at Wed Apr 01, 2020 11:30 pm
>
> 
I have a Nodeviewer question. Are the game items' common names (say, "R-55 Searing Disruptor") stored somewhere visible in the Nodeviewer's tree structure? I'm trying to learn how to find them and derive stuff like Model IDs and FQNs from that, so that I'm able to work that out in the absence of jedipedia.net's database.

(as I'm no programmer, I'm thinking of using the Nodeviewer app directly or Explorer's indexed searches through exported .csv files, kind of what I already do through the game's exported .xml to locate gear meshes and textures, or through those very .csv files to identify player character creator settings and the corresponding head and body's meshes and textures)

Not directly. The GOM only have the ID of the texts and names. The names itself are saved in the swtor_en-us_global_1.tor. The item names with the ID are in /resources/en-us/str/itm.stb but in a not directly readable format.

That makes it not easy to find it out.
## Post #642
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-04-03T17:03:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I see. Thanks.
## Post #643
- Username: Scyrner
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 09, 2020 10:27 am
- Post datetime: 2020-04-09T02:30:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hello!

I have a question about datafiles and such with regards to Star Wars the Old Republic. 

All y'all have super cool ideas for complex tools and such, but what I'm hoping to get is just the actual image that the game shows as the area map when you open your map. I'd want to be able to use a typical image viewer program so that I can just look at the map, without the FoW, without the icons or names or anything, literally just the blue map.....

Where should I start? 

Thanks.
## Post #644
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-04-09T11:05:05+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

From a full extraction of the game assets that I did through EasyMyp, I'm seeing all the blue maps stored as plain .dds image files at:

resources > world > areas > (a numeric ID) > (human-readable map name).dds

It seems that the game's .tor files where they are stored are those named "swtor_main_area_xxxx.tor", xxxx being the name of a locale (say, "tython", "open_worlds", etc.).

Probably the easiest thing to do would be to temporarily put all those .tor files in a subfolder and batch-extract them in one go instead of going through them one by one, unless you only care for a few specific ones  .
## Post #645
- Username: Scyrner
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 09, 2020 10:27 am
- Post datetime: 2020-04-10T00:13:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Okay cool, thank you very much!
## Post #646
- Username: estrella
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 11, 2019 7:13 am
- Post datetime: 2020-04-13T23:04:46+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I'm having an issue where I look through the hash file in EasyMYP and I cannot find Shae Vizla's helmet texture, its called "face_gehelmet50_heavy_ge_a59shae01_u" on Jedipedia, however, I cannot find it. I can only find the mesh for Shae Vizla's helmet, can anyone help me here?
## Post #647
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-04-13T23:14:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Right now I can't launch EasyMYP, but I've located the textures in my collection of extracted assets. In case it helps, they end up stored at:

resources > art > dynamic > player_character > outfit > gehelmet > texture > ___psd > (the usual five textures starting with that name)

((tomorrow I'll check through EasyMYP)
## Post #648
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-04-14T09:49:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey both!
As I already answered on Discord the mat file you are serching is in swtor_main_area_flashpoint_b_1.tor in path /ressorces/art/shaders/materials/face_gehelmet50_heavy_ge_a59shae01_u.mat

-RealymanLP
## Post #649
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-04-14T09:52:51+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks
## Post #650
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-04-15T10:32:14+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hashes and Filenames updated to newest PTS: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)

-RealymanLP
## Post #651
- Username: Searchy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 21, 2018 10:41 am
- Post datetime: 2020-04-27T18:06:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey everyone,
I've been trying to rip the new Tau Idair Armor set using EasyMYP and the 3DSMax script so I can have a fully working skeleton.

I've imported the bfnnew_skeleton.gr2 and then every piece of armor into 3DSMax.
Now I see certain weight/skinning issues with the chest piece being weighted to the leg bones rather than the arm bones rendering it (kind of) useless.

Should I not use the MaxScript and rather use some Noesis script? I've tried to export using Noesis but wasn't quite able to get weighted models out of it. Or is it just this way and I have to fix it myself? I was just wondering if there is a easy fix before I put so much work into it.
## Post #652
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-04-27T21:36:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have no experience with 3DS Max and that script, so I can't be of any help in this matter. If no one else here could, I'd suggest trying some of the people publishing or doing art with SWTOR models at deviantart.com and the like, such as [Sticklove](https://www.deviantart.com/sticklove) or [Torol](https://www.deviantart.com/torol). They seem to be using such Max script despite offering XNALara conversions.
## Post #653
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-05-09T12:31:52+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hashes and Filenames updated to newest PTS with SwoopRacing: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)

-RealymanLP
## Post #654
- Username: Timberley
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 01, 2016 3:17 am
- Post datetime: 2020-05-19T14:18:02+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey all, does anyone have or know of a Noesis plugin for the skeletons?  I don't have 3DSMax so can't use that plugin.  I'm trying to get bfnnew_skeleton.gr2 and bmnnew_skeleton.gr2 into something readable by Blender.  I've extracted a lot of meshes and done UVs and texturing, so I'd prefer not to have to re-export everything.

Many thanks!
## Post #655
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-05-19T16:31:12+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Same case here. As a circuitous route, I have been checking a few (swtor-to-3DS Max-to-)XNALara models posted at DeviantArt.com and tried importing them into Blender with a XPS-to-Blender addon. The addon imports them with a functional armature which I assume is the original imported SWTOR model's one instead of something built in Max or XNALara afterwards, but the measurements are a bit off (when applied to a character scaled to x10). I haven't tried a transplant yet.

If you want to experiment:

- XNALara importer addon for Blender. It imports the meshes including any bound skeleton and creates appropriate materials:
[https://www.deviantart.com/johnzero7](https://www.deviantart.com/johnzero7)
[https://github.com/johnzero7/XNALaraMesh](https://github.com/johnzero7/XNALaraMesh)

- Downloadable SWTOR models in XNALara format (including most of the companions):
[https://www.deviantart.com/sticklove/ga ... /star-wars](https://www.deviantart.com/sticklove/gallery/45419187/star-wars)
[https://www.deviantart.com/torol/galler ... /star-wars](https://www.deviantart.com/torol/gallery/64766214/star-wars)
## Post #656
- Username: Timberley
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 01, 2016 3:17 am
- Post datetime: 2020-05-19T23:10:37+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Wed May 20, 2020 12:31 am at Wed May 20, 2020 12:31 am
>
> 
Same case here. As a circuitous route, I have been checking a few (swtor-to-3DS Max-to-)XNALara models posted at DeviantArt.com and tried importing them into Blender with a XPS-to-Blender addon. The addon imports them with a functional armature which I assume is the original imported SWTOR model's one instead of something built in Max or XNALara afterwards, but the measurements are a bit off (when applied to a character scaled to x10). I haven't tried a transplant yet.

If you want to experiment:

- XNALara importer addon for Blender. It imports the meshes including any bound skeleton and creates appropriate materials:
https://www.deviantart.com/johnzero7
https://github.com/johnzero7/XNALaraMesh

- Downloadable SWTOR models in XNALara format (including most of the companions):
https://www.deviantart.com/sticklove/ga ... /star-wars
https://www.deviantart.com/torol/galler ... /star-wars

Thanks for that!  I'll give it a look.
## Post #657
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2020-05-21T13:34:29+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Does anyone have any idea where "manta_thrantamount_a01.gr2" is? I checked in all of the archives where it should be and I really can't find it... it's in the hash list so it exists but I don't know where, it makes no sense.
## Post #658
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-05-21T14:12:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I've tried and I can't find it either. Its associated info and texture files are there, though. Weird.

(I've been trying the folders where the unidentified stuff is, too, to no avail)
## Post #659
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2020-05-21T14:21:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Yeah I have the textures, I think it's the thranta's "saddle" on the back, but I don't know why the model file just doesn't exist...
## Post #660
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-05-21T14:22:09+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey! I also looked and can't see it. Looks like it got removed or changed.
## Post #661
- Username: Pomelo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 21, 2015 5:56 am
- Post datetime: 2020-05-22T01:00:33+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from TRDaz ↑Thu May 21, 2020 9:34 pm at Thu May 21, 2020 9:34 pm
>
> 
Does anyone have any idea where "manta_thrantamount_a01.gr2" is? I checked in all of the archives where it should be and I really can't find it... it's in the hash list so it exists but I don't know where, it makes no sense.

 I think i found it. It's called mag_taxithranta_a01.gr2



2020-05-22 03_55_12-.jpg (163.69 KiB) Viewed 300 times
## Post #662
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2020-05-22T17:08:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Pomelo ↑Fri May 22, 2020 9:00 am at Fri May 22, 2020 9:00 am
>
> 
 I think i found it. It's called mag_taxithranta_a01.gr2
Awesome! Exactly what I wanted, thank you very much!
## Post #663
- Username: Pomelo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 21, 2015 5:56 am
- Post datetime: 2020-05-24T14:42:00+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

This guide from Steam that shows how to extract SWTOR models just got updated with a blender import add-on for gr2 files. It's on the Tools section with a link to dropbox .
[https://steamcommunity.com/sharedfiles/ ... 1918317239](https://steamcommunity.com/sharedfiles/filedetails/?id=1918317239)



2020-05-24 17_40_56-Window.jpg (35.24 KiB) Viewed 276 times
## Post #664
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-05-24T16:06:45+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

OH CROM!!! Rushing to test it right now. Thanks!
## Post #665
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-05-24T17:46:22+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Okay, a first impression:
It understands a mesh' mutiple materials correctly, which solves a few cases where Noesis messes up, such as some Zabrak hairpieces containing both hair and horns where Noesis failed to separate them by material, ending up with a combined hair+horn object with a single material. It isn't able to split the mesh into several objects, though, so, for example, the eyes in a head mesh can't be separated on import. It can be done afterwards through a Edit > Mesh > Separate > By Material operation, anyway.
It imports the meshes' vertex groups data.
It doesn't understand armature files.
It has no importing settings at all. Ideally one would have a "split by Object" and "by group", and a scale setting. 

All in all, a great tool. The thing is, it's written in Python and seems fairly tidy code (I'm a complete novice there, but…), so it could be improved upon
## Post #666
- Username: SultanaVerena
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 02, 2017 1:35 am
- Post datetime: 2020-05-27T16:23:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I now see why the guide suddenly blew up in view numbers and comments.. Hello there!

LeeThorogood, who made the Blender plug-in, is super thrilled that the lot of you are putting it to use and are enjoying it. If any of you have some sample code he can take a gander at for extra import options, he would appreciate it.
## Post #667
- Username: DarthAtroxa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 16, 2019 8:26 pm
- Post datetime: 2020-05-27T16:30:02+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Mon May 25, 2020 1:46 am at Mon May 25, 2020 1:46 am
>
> 
Okay, a first impression:
It understands a mesh' mutiple materials correctly, which solves a few cases where Noesis messes up, such as some Zabrak hairpieces containing both hair and horns where Noesis failed to separate them by material, ending up with a combined hair+horn object with a single material. It isn't able to split the mesh into several objects, though, so, for example, the eyes in a head mesh can't be separated on import. It can be done afterwards through a Edit > Mesh > Separate > By Material operation, anyway.
It imports the meshes' vertex groups data.
It doesn't understand armature files.
It has no importing settings at all. Ideally one would have a "split by Object" and "by group", and a scale setting.Hi, I'm the author of the plugin, I just wanted to say thank you for the feedback.   I don't have any plans to develop it further at present but if that ever changes I will see what I can do to overcome the limitations you've highlighted here. 

> Reply from ZeroGravitas ↑Mon May 25, 2020 1:46 am at Mon May 25, 2020 1:46 am
>
> 
All in all, a great tool. The thing is, it's written in Python and seems fairly tidy code (I'm a complete novice there, but…), so it could be improved uponThank you   , I did my best to make sure the code would be tidy and easily readable for anyone who understands Python & Blender's API.
## Post #668
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-05-27T17:05:00+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

First of all, my deepest gratitude to Lee for his plugin: I've tried it in a few more cases and I think It might let me discard Noesis' batch-conversions to .obj completely. I know of another person doing 3D art of his player characters that literally said "it's Christmas already!" as soon as I told him about it  .

I hope I didn't give the impression that I was being too picky or demanding when suggesting more features. Luckily, as far as I've tested, splitting objects by material and scaling them can be done in Blender itself (I was afraid of the body parts not keeping their relative positions upon being scaled x10, but that's not the case), so there's no real need to implement them in the import phase. The only real chore, inherent to Blender's lack of basic multiple mesh file import capabilities, is having to import one .gr2 at a time (some people created an addon for importing multiple .obj and .fbx at once that I was taking advantage of), but solving that seems a bit too major an effort.

Actually, I'm dipping my toes in Python and Blender scripting (it's kinda painful!   ), hoping to be able to automate some of the assembling of my characters and their gear. This plugin could become a fundamental piece of the puzzle.

So, again, my thanks. To you all, because that guide and its tools will help a few friends of mine, too.
## Post #669
- Username: DarthAtroxa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 16, 2019 8:26 pm
- Post datetime: 2020-05-27T20:28:47+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Thu May 28, 2020 1:05 am at Thu May 28, 2020 1:05 am
>
> 
First of all, my deepest gratitude to Lee for his plugin: I've tried it in a few more cases and I think It might let me discard Noesis' batch-conversions to .obj completely. I know of another person doing 3D art of his player characters that literally said "it's Christmas already!" as soon as I told him about it  .

I hope I didn't give the impression that I was being too picky or demanding when suggesting more features.Not to worry, I didn't get the impression you were being too picky or demanding!  In fact you were very complimentary!  I'm pleased the plugin is proving to be useful and reliable.

> Reply from ZeroGravitas ↑Thu May 28, 2020 1:05 am at Thu May 28, 2020 1:05 am
>
> 
Actually, I'm dipping my toes in Python and Blender scripting (it's kinda painful!   ), hoping to be able to automate some of the assembling of my characters and their gear. This plugin could become a fundamental piece of the puzzle.

So, again, my thanks. To you all, because that guide and its tools will help a few friends of mine, too.Good luck with the scripting, Python is quite a nice language to work with as it's been designed to be easy to follow / read, unfortunately Blender's Python API while well documented isn't very clearly explained / demonstrated.
## Post #670
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-06-03T16:00:03+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

New Hashlist of newest PTS is there: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #671
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-06-13T21:10:06+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I've got a question for anyone who knows how these things work:

As Blender has some colorspace management features for texture files (treating them individually as non-color data, sRGB, linear, linear ACES, etc.), until now I've been using all textures related to actual appearance's colors and values (diffuse maps, make-up maps, tattoos, complexions, etc.) as sRGB and everything else (normals, glossiness, masks, etc.) as non-color.

What I wonder is if I actually ought to treat just everything as non-sRGB, "non-color" data (that is, non-color corrected whatsoever) and leave matters of contrast and the like to the final output's color correction settings (or perhaps adding some to my generic SWTOR material node trees).

Given that SWTOR was built on top of Hero Engine, which provided plugins for 3DS Max and Maya in its base package, does anybody know how textures were supposed to work, colorspace-wise?
## Post #672
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-06-28T13:38:20+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

New Hashlist of 6.1.2: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #673
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-06-28T13:42:56+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from RealymanLP ↑Sun Jun 28, 2020 9:38 pm at Sun Jun 28, 2020 9:38 pm
>
> 
New Hashlist of 6.1.2: https://drive.google.com/drive/folders/ ... sp=sharing
Thanks! I had my eye on some of the new gear
## Post #674
- Username: Boda
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 15, 2019 10:41 am
- Post datetime: 2020-07-02T00:35:04+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I have the newest hash list, but for some reason cannot extract the .dds textures for the helmet of the Mandalorian Stormbringer armor set. Everything else extracts from the armor, even the gr2 files for the helmet extract but the .dds files won't. I've checked the hash list, and it has the textures files in it, but whenever I open the .tor they are the only ones missing. Not sure what to do, can anyone help?
## Post #675
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-07-02T00:47:24+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I did a full batch-export yesterday and I'm able to locate those textures in my results. Their names are:

face_bhhelmet37_heavy_bh_mtx17c01_u_d.dds
face_bhhelmet37_heavy_bh_mtx17c01_u_h.dds
face_bhhelmet37_heavy_bh_mtx17c01_u_m.dds
face_bhhelmet37_heavy_bh_mtx17c01_u_n.dds
face_bhhelmet37_heavy_bh_mtx17c01_u_s.dds

They are supposed to be in a subdirectory named:
\art\dynamic\player_character\outfit\bh_baggy_heavy_mtx17\textures\

Right now I don't have my PC at hand (almost 3:00 AM here). Tomorrow I'll try exporting them as specific items and see if it works in my setup.
## Post #676
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-07-02T22:23:19+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

It's taking me a lot to locate them through EasyMYP. I wonder if it wouldn't be easier to just extract all the contents of the head and face-related .tor files and then do a Windows search for those filenames.
## Post #677
- Username: Boda
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 15, 2019 10:41 am
- Post datetime: 2020-07-04T10:14:51+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I did exactly that, and still have nothing on the textures. I know the names, I know where they are supposed to be, but they simply are not there. Unless I'm totally missing something. The weird thing is by exporting the entire face and head I was able to get the .gr2 files for the helmet, but not the textures.
## Post #678
- Username: DarthAtroxa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 16, 2019 8:26 pm
- Post datetime: 2020-07-05T13:00:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Take a look in swtor_main_art_zed_1.tor
## Post #679
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-07-05T13:05:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from DarthAtroxa ↑Sun Jul 05, 2020 9:00 pm at Sun Jul 05, 2020 9:00 pm
>
> 
Take a look in swtor_main_art_zed_1.tor
Bioware is EVIL!!!
## Post #680
- Username: Boda
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 15, 2019 10:41 am
- Post datetime: 2020-07-07T18:34:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

YOU'RE FANTASTIC!
## Post #681
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-07-14T18:18:31+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Heyho! I created a new hashlist for you with more than 7.000 new names! We currently have 97,3% of all names.
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #682
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-07-14T18:22:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from RealymanLP ↑Wed Jul 15, 2020 2:18 am at Wed Jul 15, 2020 2:18 am
>
> 
Heyho! I created a new hashlist for you with more than 7.000 new names! We currently have 97,3% of all names. https://drive.google.com/drive/folders/ ... sp=sharing
THANK YOU!!!  TorMYP, there I go!
## Post #683
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-08-09T00:23:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I've got a question regarding Jedipedia's database's tree view. I'm searching for this no-name bearded Body Type 3 Sith NPC standing at the far end of Dantooine's Imperial base, next to a tent and some weaponry racks. So far, I'm having no problem finding the NPCs there that have a name and maybe a role, but I don't know how to locate those others that are mostly unclickable "living" props.

Filtering the tree by NPCs, the Dantooine stuff seems to be at event > pirate_onslaught > imperial > base, but I've checked all the Sith characters through their pages' 3D viewer, and no one matches this guy, so, I was wondering if those "prop people" fall under a different classification from NPC.



Screenshot - 07_06_2019 , 19_51_43.jpg (18.77 KiB) Viewed 200 times



(I'm interested in recreating his facial features, and I wanted to avoid having to search for the relevant assets by eyeballing head models and the rest)
## Post #684
- Username: SultanaVerena
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 02, 2017 1:35 am
- Post datetime: 2020-08-13T16:13:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Updated the GitHub repository [https://github.com/SultanaVerena/SWTOR-Extraction-Tools](https://github.com/SultanaVerena/SWTOR-Extraction-Tools) with "NodeViewer" (provided by RealyManLP).

I am very busy but I promise I will get to a guide re-write when I have the chance. I am also going to see if I can put the guide on the repo.
## Post #685
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-08-16T17:32:50+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks! If we can help in any way, give us a hey
## Post #686
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-08-18T21:32:43+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I'm writing a Python script that, upon being fed the ModelID and MaterialIndex for a game item, reads the relevant XML and MAT files to locate and copy the meshes and textures from inside an EasyMYP extraction folder to an user-specified one. It's kinda half-working now (it's my very first Python script and the Python Police would terminate me on the spot if it gave the code a read). In its actual state, it collects the files to cover for all the body types and genders.

You might hear firetruck sirens   

Working…
## Post #687
- Username: DarthAtroxa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 16, 2019 8:26 pm
- Post datetime: 2020-08-22T13:29:55+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

It's too late, the Python police are on their way, you will be taken to a re-education centre where you will  be detained until all your Python code fully conforms to PEP8, even the rule about lines not exceeding 80 characters!
## Post #688
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-08-26T06:16:38+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Noooo, not the 80 characters Iron Maiden!!!   

I have the script functioning correctly already, dealing with material overrides and everything. Now it needs to be presentable inside and outside.

Next in line would be a player character assets collector that works out of Character Creator settings data. The problem there is going to be analyzing the .csv exports from NodeViewer, as they aren't as structured as .xml is.
## Post #689
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2020-09-02T19:31:49+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Everything might not work, and I provide no documentation. But have fun with these.

[https://github.com/swtor-miner/pug_tools/](https://github.com/swtor-miner/pug_tools/)
[https://github.com/swtor-miner/launcher_replacement/](https://github.com/swtor-miner/launcher_replacement/)  <- not really the most accurate name anymore.

They are public but are collaborator edit only right now. If i get an invite to the swtor datamining discord server, you can message me there as "Aikion" to be added.

edit: Well it seems not everyone is on that discord server. So you can message me as /u/aikiwoce on reddit.
## Post #690
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-09-02T21:07:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Wow!!! Thank you so much!    It's great to see you revisiting the thread, and bearing gifts to boot.
## Post #691
- Username: SultanaVerena
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 02, 2017 1:35 am
- Post datetime: 2020-09-04T20:55:57+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I am in the process of remaking the GitHub with the tools and setting up a Discord server for extractors/modders/miners. Right now the server is only open to people who I would consider "significant names" in these communities. If you are interested in joining this server before it is made public, please send me a DM on here. Thank you.
## Post #692
- Username: Ausar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 03, 2018 6:59 am
- Post datetime: 2020-09-05T13:14:48+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from SultanaVerena ↑Sat Sep 05, 2020 4:55 am at Sat Sep 05, 2020 4:55 am
>
> 
I am in the process of remaking the GitHub with the tools and setting up a Discord server for extractors/modders/miners. Right now the server is only open to people who I would consider "significant names" in these communities. If you are interested in joining this server before it is made public, please send me a DM on here. Thank you.

We have had a dataminer discord server for a while now, albeit it's not been open to the public yet, but if you want to take over the server and eventually make it public I would be happy to give you all the permissions, DM me if you want to.
## Post #693
- Username: SultanaVerena
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 02, 2017 1:35 am
- Post datetime: 2020-09-07T20:41:17+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Ausar ↑Sat Sep 05, 2020 9:14 pm at Sat Sep 05, 2020 9:14 pm
>
> 
SultanaVerena wrote: ↑Sat Sep 05, 2020 4:55 am
I am in the process of remaking the GitHub with the tools and setting up a Discord server for extractors/modders/miners. Right now the server is only open to people who I would consider "significant names" in these communities. If you are interested in joining this server before it is made public, please send me a DM on here. Thank you.


We have had a dataminer discord server for a while now, albeit it's not been open to the public yet, but if you want to take over the server and eventually make it public I would be happy to give you all the permissions, DM me if you want to.

I only just now got back to this thread and I've already made everything and have custom bots in the server, etc., but thank you for the offer! 

The tools are all being moved to a GitHub organization and each tool has its own separate repository. There is an invitation URL to the Discord if you review the GitHub page. [https://github.com/SWTOR-Extractors-Modders-Dataminers](https://github.com/SWTOR-Extractors-Modders-Dataminers)
## Post #694
- Username: swtor miner
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Sep 10, 2013 7:05 am
- Post datetime: 2020-09-08T20:49:39+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from swtor miner ↑Thu Sep 03, 2020 3:31 am at Thu Sep 03, 2020 3:31 am
>
> 
Everything might not work, and I provide no documentation. But have fun with these.

https://github.com/swtor-miner/pug_tools/
https://github.com/swtor-miner/launcher_replacement/  <- not really the most accurate name anymore.

They are public but are collaborator edit only right now. If i get an invite to the swtor datamining discord server, you can message me there as "Aikion" to be added.

edit: Well it seems not everyone is on that discord server. So you can message me as /u/aikiwoce on reddit.

I was asked about the dependencies to build the second one. They are available at:
[https://github.com/seanoflynn/research-bittorrent](https://github.com/seanoflynn/research-bittorrent)
and
[https://jonskeet.uk/csharp/miscutil/](https://jonskeet.uk/csharp/miscutil/)
## Post #695
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-09-11T17:55:27+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Heyho! New hashlist is there for you! Also added some beta-filenames (also when they are not used anymore). Currently we have a 97,3% completion.
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #696
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-09-11T19:06:01+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Thanks! A certain PC is going to be EasyMYPing tonight
## Post #697
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-09-19T18:54:53+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

New hashlist for 6.1.4 PTS patch: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #698
- Username: probe88
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Jun 24, 2019 9:10 pm
- Post datetime: 2020-10-02T14:25:30+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

With new blender plugin (export import) - is it possible to edit .gr2 and import it back in the game?
## Post #699
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-10-02T21:09:22+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I believe the possibility exists, if under limitations. Could you try the Discord server where several of the people in this forum is being more active as of late? There's a "Modding" set of threads there, and the people posting on them surely would be better able to help.

[https://discord.gg/XfHFjSN](https://discord.gg/XfHFjSN)
## Post #700
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-10-16T17:27:00+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

New hashlist for 6.1.4: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #701
- Username: Vitani
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 21, 2010 6:44 am
- Post datetime: 2020-10-28T22:17:58+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Anyone have any luck getting SWTOR Miner's World Browser to work? I've enabled the button but it just launches the Model Browser when I click it.
I've been looking through the code, specifically tools_ui.cs and worldbrowser.cs and havent been able to determine if something isnt pointing to the right place, granted my programming ability is limited.

Also, could I get an invite to the dataming server please? Thank you.
## Post #702
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-10-29T09:15:40+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Yes. It's [https://discord.gg/XfHFjSN](https://discord.gg/XfHFjSN)
## Post #703
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-11-03T17:05:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

This is the day!
Have fun with my [SWTOR Patch Downloader](https://torcommunity.com/realymanlp/tools/patchdownloader.zip). With it you can download every patch of SWTOR. 

After downloading patch files, you can use miners [launcher_replacement (Unzipper)](https://github.com/swtor-miner/launcher_replacement/) to install the patches.

Best regards
-RealymanLP
## Post #704
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-11-06T18:19:54+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

New Hashlist is there for you: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #705
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2020-11-11T18:51:41+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

New hashlist for first 6.2 PTS: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #706
- Username: swtorastic88
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 18, 2020 10:36 pm
- Post datetime: 2020-12-18T14:43:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I'm just starting on this, and have no experience, so it's been interesting, lol. It was a struggle, but I have managed to get the meshes and textures from the assets. Now I just have to figure out how to get and apply those textures (i am guessing GIMP since i refuse to pay for photoshop sub and looks like dds doesn't work with photoshop 5.5). 

Oh! one question I do have... if we don't use dds file format for textures, what is a "common" format to use? 

After that, I guess it's time to learn how to rig in blender.

Anyway, I wanted to post a thanks to those who create the programs that help extract things, and to the explanations people provide. Thanks.
## Post #707
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2020-12-18T15:12:28+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I'd encourage you to join the Discord server where most of the people active in this forum chat and exchange information. We can lend you a hand there   .

[https://discord.gg/Rap3KjXm](https://discord.gg/Rap3KjXm)

Regarding the texture files: Blender directly accepts those .dds files, and all the image channels' shenanigans (like turning "green" normal maps into "blue" conventional ones, or isolating the opacity channel) can be solved directly there, without needing to go through a paint app. If you want to go further and, say, repaint them, you could convert them to .png which is a fairly typical format for these things (most formats would do, really: tga, jpg… It mostly depends on whether you need to preserve the alpha channel or not). There are free batch-converters around, such as Noesis, XnConvert, etc.

DarthAtroxa's .gr2 importer addon for Blender provides with a replica of SWTOR's materials system, so that you just plug the texture files and some values into them and they give you results faithful to the game. Those aside, I built a kind of approximation to them that might be a bit more artist-friendly. There's people creating better tools that one day might automate most of this stuff.

And regarding rigging, you might be able to skip its rigors, actually   . DarthAtroxa's addon is able to import the game's armatures and the objects' matching vertex groups, so it's just a matter of parenting the objects to the armatures with the deformations option and you can immediately start posing them! It's not as fully featured and user-friendly a system as Blender's own tools can provide (no drivers or IK… although one could add them to it), but it is what the game uses, including weight map-driven limb deformations and everything.
## Post #708
- Username: seedhartha
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 31, 2021 2:14 pm
- Post datetime: 2021-02-03T01:59:26+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hi!

I've decided to share with you the progress I'm making on reverse-engineering JBA animations:

[https://github.com/seedhartha/reone/wiki/SWTOR-Research](https://github.com/seedhartha/reone/wiki/SWTOR-Research)

I think the file layout is pretty accurate, but we still have to figure out the exact format and ordering of keyframes. If someone here could give direction, I would be very grateful.
## Post #709
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2021-02-03T11:16:23+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from seedhartha ↑Wed Feb 03, 2021 9:59 am at Wed Feb 03, 2021 9:59 am
>
> 
Hi!

I've decided to share with you the progress I'm making on reverse-engineering JBA animations:

https://github.com/seedhartha/reone/wiki/SWTOR-Research

I think the file layout is pretty accurate, but we still have to figure out the exact format and ordering of keyframes. If someone here could give direction, I would be very grateful.

Thank you! Would you be interested in joining the SWTOR Extraction/Modding/Datamining Discord server? It's where most of the activity of this thread is being carried on, nowadays, and there are several fellow coders there that for sure would like to study your analysis and maybe lend a hand.

The link is: [https://discord.gg/Rap3KjXm](https://discord.gg/Rap3KjXm)
## Post #710
- Username: seedhartha
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 31, 2021 2:14 pm
- Post datetime: 2021-02-03T16:52:22+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from ZeroGravitas ↑Wed Feb 03, 2021 7:16 pm at Wed Feb 03, 2021 7:16 pm
>
> 
Thank you! Would you be interested in joining the SWTOR Extraction/Modding/Datamining Discord server? It's where most of the activity of this thread is being carried on, nowadays, and there are several fellow coders there that for sure would like to study your analysis and maybe lend a hand.

The link is: https://discord.gg/Rap3KjXm

Gladly! Your link has expired, though.
## Post #711
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2021-02-03T18:05:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Aw, sorry. Try this one: [https://discord.gg/XfHFjSN](https://discord.gg/XfHFjSN)
## Post #712
- Username: RealymanLP
- Rank: advanced
- Number of posts: 54
- Joined date: Sat Oct 06, 2018 9:11 pm
- Post datetime: 2021-03-21T09:55:36+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

New hashlist for PTS 3.6 #2: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1VmoAOY9EM12BV5qeWkiAHaef6nDR0XBT?usp=sharing)
## Post #713
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2021-03-21T13:19:28+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

UPDATED Jul 2022:
For any visitor finding this thread and being interested in extracting and assembling their SWTOR player characters, this is the state of play regarding SWTOR's assets extraction and assembling   :

The needed tools have been reduced to mostly four:
TORCommunity.com's online Character Designer, for recreating our Player Characters and exporting a description of the required game assets and an empty folder structure where to place them.

(Alternatively, TORCommunity.com's database of NPCs, which can export the same information for NPCs (companions, other characters, and creatures).
Slicers GUI: an unified tool for extracting game assets, examining the game's data, modding and, as it concerns this post, processing those Player Character and NPC exports to locate their assets and fill their folder structures with them. This tool replaces the old EasyMYP and Noesis ones, which are no longer necessary (they are still available at the same Github repository, as they can be useful as file inspectors).
Blender, the popular free, open source 3D app.
The SWTOR Granny2 import/export add-on for Blender. This add-on reads the folder processed by Slicers GUI and auto-assembles and textures the character with materials that replicate the game's looks IN ONE CLICK. It's also capable of importing the character's rigging information, character skeleton objects, plain import multiple game objects in one go, and import and apply game animations!
[The whole process is explained in this wiki](https://github.com/SWTOR-Slicers/WikiPedia/wiki/locating-swtor-characters-assets-automatically). There are also guides on how to rig characters (in literally three clicks or so), find weapons (not so automated yet but fairly easy) and hook them to the characters, and how to improve upon the game models through Blender's features (SDS for smoothing their skins, using full bodies underneath their armor, etc.).

Even if these guides and tools are Blender-centric, there are ways to export the PCs and NPCs to other platforms such as Unreal, VRChat, etc. The guides are rather lacking on those at the moment.

As this thread is in a bit of a state of hibernation, most of the activity regarding all this and other sides of SWTOR datamining is happening at the SWTOR Slicers Discord Server. There, you can find people, including some Xentax old-timers , producing additional tools, guides, art, etc. to ask questions to.
## Post #714
- Username: Boda
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 15, 2019 10:41 am
- Post datetime: 2021-08-06T03:18:21+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Hey, I'm looking for an active invite link into the discord. Is there any way someone can provide one? I have several questions and it seems like it'd be easier to communicate that way.
## Post #715
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2021-08-06T11:33:42+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

> Reply from Boda ↑Fri Aug 06, 2021 11:18 am at Fri Aug 06, 2021 11:18 am
>
> 
Hey, I'm looking for an active invite link into the discord. Is there any way someone can provide one? I have several questions and it seems like it'd be easier to communicate that way.

Sure   . Here you are:
[https://discord.gg/XfHFjSN](https://discord.gg/XfHFjSN)
## Post #716
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2021-08-06T11:45:30+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Update for any visitor finding this thread:

Things have become far easier since the last time we posted about the progress in extracting, modding, and datamining SWTOR. Basically, everything is being put under the umbrella of a single multipurpose app.

Now it is possible to autoassemble fully textured player characters and NPCs in almost one click through the latest versions of the importer add-on for Blender. The models preserve their rigging information so that, when paired with a skeleton object, they become posable and animatable. An experimental animation importer allows for some of the game animations to be applied.

Also, there's an effort to turn modding into an easy, colaborative endeavor, allowing for the sharing of recipes.

To learn more, please visit the related Github's wiki, at [https://github.com/SWTOR-Slicers/WikiPedia/wiki](https://github.com/SWTOR-Slicers/WikiPedia/wiki)
## Post #717
- Username: DaarthYceyy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 07, 2018 2:17 am
- Post datetime: 2021-09-15T04:57:27+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I've seen a lot of information in this forum about extracting and assembling character models, but has anyone figured out yet how to reproduce an area map?  The player ships have skeletons that assemble all the room objects correctly, but I've yet to find anything similar that would piece together an area -- like Nar Shaddaa or Coruscant -- for example.  The terrain maps are probably not able to be reproduced, but I'm hoping there's a way to at least assemble the architecture of an area, similar to how a skeleton does for the player ships.  Importing individual meshes and trying to assemble the pieces by hand isn't worth the effort.
## Post #718
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2021-09-15T11:56:25+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

There's a private tool in use by some dataminers that is able to load and navigate whole SWTOR locales, and there's the intention to develop a public one, although right now other projects are taking precedence.

(You can see the private tool in action here: [https://youtu.be/Wa8q6gAj6hM?list=PL0H7 ... msR&t=1986](https://youtu.be/Wa8q6gAj6hM?list=PL0H7wSPQruMRtfVuqkf50yNj2KnICgmsR&t=1986) )
## Post #719
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2022-07-16T09:59:02+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

I've updated [the post describing the current state of play](https://forum.xentax.com/viewtopic.php?f=10&t=7186&p=172514#p172514) regarding game characters extraction and assembling to reflect the latest advances .
## Post #720
- Username: ZeroGravitas
- Rank: veteran
- Number of posts: 103
- Joined date: Thu Sep 27, 2018 7:59 am
- Post datetime: 2023-04-23T21:02:10+00:00
- Post Title: Re: Star Wars - The Old Republic - Beta

Minor update: the team is still active at the [SWTOR Slicers Discord](https://discord.gg/XfHFjSN). Tools are being updated for SWTOR 64 bit compatibility (assets extraction and object import are working already), and we have a fairly functional game locations assembler addon for Blender (working on having it import heightmap-based terrain, too).

Also, guides: at [https://github.com/SWTOR-Slicers/WikiPedia/wiki](https://github.com/SWTOR-Slicers/WikiPedia/wiki)
