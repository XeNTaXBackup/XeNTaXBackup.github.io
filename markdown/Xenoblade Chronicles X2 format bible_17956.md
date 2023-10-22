## Post #1
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2018-04-10T18:59:12+00:00
- Post Title: Xenoblade Chronicles X/2 format bible

Topology of list: 

File ExtensionFormat/usage Can be opened with
Here is list of formats used in XenobladeX

.adx            ADX ADPCM Audio format VLC
.usm            CRI Movie 2 VGMToolbox/Stream Tools/Video Demultiplexer
.cpk            CRI Archive VGMToolbox/Extraction Tools/Common Archives
.mca            Script
.eva            Script
.bdat           Binary Data
.csvb           CSV Binary
.sha            Shader Container
.efb            Effect Bundle
.epac           EFB Container
.evpa           Container
.mdlstm         Skeleton path table
.motstm         Animation Table
.motstm_data    Animation data container
.hkt            Havok 2013 binary file 
.sar            SAR Container viewtopic.php?p=139633#p139633
.camdo          MXMD Model container viewtopic.php?f=16&t=18006
.casmt          Texture Container viewtopic.php?f=16&t=18006
.camtp          CSV Binary
.cea            CES Container
.ces            Hash table
.efp            CSV Binary
.cadsys         CSV Binary
.catex          MTXT Texture viewtopic.php?f=18&t=14645
.chr            CSV Binary
.crv            CSV Binary
.canvda         NVTP Container
.canvhe         NVMS map related file
.casmda         Map data container
.casmhd         DMSM map related file
.bmn            UI Script/MTXT Container
.fnt            Font file/MTXT Container
.gsh            GFX2 Datafile
.casfb          CSV Binary
.caavp          MTXT Texture viewtopic.php?f=18&t=14645
.bmv            UI Script
.caevd          Unknown/MTXT Container
.caevh          Unknown/MTXT Container
.calgs          SHTM shader container
.cashd          SHTM shader/ container
.acb            CRI Sound Bank VGMToolbox/Extraction Tools/Common Archives
And here is list of formats used in Xenoblade 2.

.nop            Sound Container (opus, adpcm)
.webm           Video Format VLC
.bdat           Binary Data
.mi             Minimap
.bnvib          Unknownn (Force Feedback curve?)
.gcp            Camera Paramaters
.rimb           RimBloom  Paramaters
.pdb            SAR Container (.pad files) viewtopic.php?p=139633#p139633
.prm            SAR Container (.param files) viewtopic.php?p=139633#p139633
.sb             Binary Script
.seg            Minimap Segment
.vpr            Particle Parameter
.wisty          Font
.wiefb          Effect Bundle
.wieab          Unknownn (.wiefb related)
.eva            Camera Effect
.evpa           EVPA Container
.mot            SAR Container (.anm/.asm files) viewtopic.php?p=139633#p139633
.motstm         PACK Container (Cutscene animations?)
.motdata        Data for .motstm
.lvl            LVLB Script (Gimmick)
.wiidcm         IDCM Texture
.wismt          DRSM Container viewtopic.php?f=16&t=18006
.winvhe         NVMS map related file
.wismda         Map data container
.wismhd         DMSM map related file
.winvda         NVDA map Container
.wifnt          Font
.wilay          LAHD Texture
.uin            UI Motion
.uio            UI Object
.wimdo          MXMD Model container/header viewtopic.php?f=16&t=18006
.wiefp          CSV Binary
.wiswt          Basic Container
.arc            SAR Container viewtopic.php?p=139633#p139633
.witex          Texture
.wishp          Shader
.witx           Texture
.csvb           CSV Binary
.xsp            SAR Container (.nop sounds) viewtopic.php?p=139633#p139633
.stp            SAR Container (.stb files) viewtopic.php?p=139633#p139633
.pad            Binary Collection
.param          Binary Collection
.anm            Binary Collection
.asm            Binary Collection
.stb            Binary Collection
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-04-10T23:48:18+00:00
- Post Title: Xenoblade Chronicles X/2 format bible

is there a decrypted release out there?
## Post #3
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2018-04-11T08:24:33+00:00
- Post Title: Xenoblade Chronicles X/2 format bible

> Reply from chrrox
>
> is there a decrypted release out there?
There is hactool decryptor already released. It can extract/decrypt most NSW cartriges.


Here is another script, that will extract SAR Containers from both games.

```
# Author Lukas Cone in 2016-2018
# script for QuickBMS http://quickbms.aluigi.org

get FOURCC long

if FOURCC == 0x31524153   
	endian big
elif FOURCC == 0x53415231
	endian little
else
	cleanexit
endif


get filesize long
get Version long
get FILES long
get OFFSET long
get DataOffset long
get dummy long
get dummy long
getdstring PATH 128

goto OFFSET

for i = 0 < FILES
    get iOffset long
    get iLen long
    get dummy long
    putarray 0 i iOffset
    putarray 1 i iLen
    set _fname PATH
	string _fname + "/"
	if Version > 500 
		getdstring iFname 36
		string _fname + iFname
		goto 48 0 SEEK_CUR
	else
		getdstring iFname 52
		string _fname + iFname
	endif
	putarray 2 i _fname	
next i

for i = 0 < FILES
  getarray iOffset 0 i
  getarray iLen 1 i
  getarray iFname 2 i
  log iFname iOffset iLen
next i   
```
## Post #4
- Username: 4g3n75m17h
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 08, 2017 9:49 am
- Post datetime: 2018-04-16T13:56:01+00:00
- Post Title: Xenoblade Chronicles X/2 format bible

I am probably just being a bit stupid, but I am having the following problem when I try to extract the bf2.ard/arh archives:

```
- open script D:\NS\QBMS\xenoblade2.txt
- set output folder D:\NS\QBMS\out

  offset           filesize   filename
--------------------------------------
- enter in folder D:\NS\QBMS
- open input file D:\NS\QBMS\bf2.ard

- signature of 1 bytes at offset 0x0000000000000000 doesn't match the one
  expected by the script:

  this one: "a"
  61                                                a

  expected: "0"
  30                                                0

- 0 files found in 0 seconds
  coverage file 0     0%   1          1915120    . offset 0000000000000001
  coverage file 1     0%   0          10957229330 . offset 0000000000000000

Press ENTER or close the window to quit
```


Any idea what's wrong and how to fix it? The .ard/.arh files are ones that I extracted myself from a Xenoblade 2 .nca using hactool. All other files from that .nca, such as the .webm files, all seem fine. Also, I have used QuickBMS to extract other files before (quite a while ago, I admit) and haven't seen this issue before.

I am using QuickBMS 0.8.4 on Windows 10 Pro 64 Bit, if that makes any difference. Also, already tried running as admin and using compatibility options, but that seemed to make no difference.

I am but a humble 3D modeller with very limited programming knowledge, so any help would be much appreciated!
## Post #5
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2018-04-18T14:17:10+00:00
- Post Title: Xenoblade Chronicles X/2 format bible

> Reply from 4g3n75m17h
>
> I am probably just being a bit stupid, but I am having the following problem when I try to extract the bf2.ard/arh archives:

I am using QuickBMS 0.8.4 on Windows 10 Pro 64 Bit, if that makes any difference. Also, already tried running as admin and using compatibility options, but that seemed to make no difference.

ARH file must have arh1 as signature (fist 4 bytes), when opened with hex editor. Otherwise it's a corrupted file.
## Post #6
- Username: 4g3n75m17h
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 08, 2017 9:49 am
- Post datetime: 2018-04-19T01:50:57+00:00
- Post Title: Xenoblade Chronicles X/2 format bible

> Reply from PredatorCZ
>
> ARH file must have arh1 as signature (fist 4 bytes), when opened with hex editor. Otherwise it's a corrupted file.

That is what makes me curious though. When I open the .arh file with a hex editor, arh1 are the first 4 bytes. 

Also, the .ard and .arh files extract perfectly when I use the ‘xenoblade2-research’ tool from ‘Thealexbarney’ on GitHub. I compiled their tool using Visual Studio 2017 Community, ran the extraction command for the .ard and .arh files through CMD using the tool, and all the files were extracted successfully, so I can assume based on that; my .ard and .arh files are not corrupted.

I had these files extracted before I used your script, and was mainly interested in using your script to extract the files again so I could compare the newly extracted files from your script to the already extracted files from the ‘xenoblade2-research’ tool to see if there are any differences before I start trying to figure out how to access the models and textures.

So, that said, assuming my files are not corrupted, I am at a loss as to why your script isn’t working.   Any ideas about what might be happening?
## Post #7
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2018-04-20T15:35:23+00:00
- Post Title: Xenoblade Chronicles X/2 format bible

> Reply from 4g3n75m17h
>
> 

So, that said, assuming my files are not corrupted, I am at a loss as to why your script isn’t working.   Any ideas about what might be happening?

The problem is QuickBMS, I'm using version 0.7.7. I tried version 0.8.4 and it showns exact same error. I will try to fix script. I might also figure out those broken filenames.

EDIT:
For some reason they removed IDString "hello" FILEID syntax, looks like they don't give a shit about backwards compatibility, whinch is sad.

EDIT2:
Filenames are using some kinda of Patricia or Radix Tree, my knowlege of this technique is very limited and take some time, so in that case I fixed script, it's edited version is on first post. I also deleted attachemt.
## Post #8
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2018-04-21T15:29:41+00:00
- Post Title: Xenoblade Chronicles X/2 format bible

Here is a QuickBMS script version 2, that will extract contents of bf2.ard/arh archives. From Xenoblade 2.
Some extracted files will have [%file id%] %filename% names, cause is that script cannot find them in a tree. Cause is unknown.

Make sure that both ard/arh files are in same folder and in quickbms dialog, always select bf2.arh.

```
# Author Lukas Cone in 2018, Version 2
# script for QuickBMS http://quickbms.aluigi.org
# 1st iteration 1:15 hours
# 2nd iteration 40 minutes
endian little
comtype zlib
open FDSE "bf2.ard" 1

idstring 0 "arh1" 

get unk long
get numnodes long
get offset1 long
get size1 long
get offset2 long
get size2 long
get tocoffset long
get numfiles long

filexor "0x33 0xB5 0xE2 0x5D"
GoTo offset1 0 SEEK_SET
get chunksize long
for i = 0 < numfiles
	savepos OFFSET
	get fname string
	putarray 0 i fname
	math OFFSET n OFFSET
	math OFFSET + offset1
	putarray 3 i OFFSET
	get fid long;
next i

GoTo offset2 0 SEEK_SET
set numusednodes long 0
for i = 0 < numnodes
	get id1 SIGNED_LONG
	get id2 SIGNED_LONG
	putarray 1 i id1
	putarray 2 i id2
	if id2 > -1
		putarray 4 numusednodes i
		math numusednodes + 1
	endif
next i
filexor ""



GoTo tocoffset 0 SEEK_SET
for i = 0 < numfiles
	get coffset longlong
	get csize long
	get ucsize long
	get compressed long
	get id long
	getarray Filename01 0 i
	getarray fileoffset 3 i
	strlen filenamelen Filename01
	math Fileend = fileoffset
	math Fileend - filenamelen
	string cstr = ""
	callfunction FindFilename 1
	strlen NAME_LENGTH cstr
	math filenameoffset - fileoffset
	math filenameoffset n filenameoffset
#	print "%filenameoffset%"
	if filenameoffset > 0
		string Filename01 < filenameoffset
	endif
	string cstr + Filename01
	
	if compressed > 0
		GoTo coffset 1 SEEK_SET
		idstring 1 "xbc1" 
		get _numfiles long 1
		get _ucsize long 1
		get _csize long 1
		get _hash long 1
		getdstring _fname 28 1
		savepos OFFSET 1
		if NAME_LENGTH < 1
			string cstr P "[%id%] %_fname%"
		endif
		clog cstr OFFSET csize ucsize 1
	else
		if NAME_LENGTH < 1
			string cstr P "[%id%] %Filename01%"
		endif
		log cstr coffset csize 1
	endif	
next i


startfunction FindFilename
	for g = 0 < numusednodes
		getarray f 4 g
		getarray id1 1 f
		getarray id2 2 f
		if id1 <= fileoffset && id1 > Fileend 
			set filenameoffset SIGNED_LONG id1
#			print "%filenameoffset% %id2%"
			set currentChar SIGNED_LONG f
			callfunction LOOPNODES 1
			string cstr r cstr
#			print "%cstr%"
			break	
		endif
	next g
endfunction

startfunction LOOPNODES
	set cci SIGNED_LONG id2
	getarray id1 1 id2
	getarray id2 2 id2
	math currentChar ^ id1
#	print "%currentChar% %id1% %id2%"
	string _cstr = currentChar
	string cstr + _cstr
	set currentChar SIGNED_LONG cci
#	print "%cstr%"
	if id2 > 0 
		callfunction LOOPNODES 1
	endif
endfunction



```
## Post #9
- Username: DragonScion
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 24, 2018 11:16 am
- Post datetime: 2018-04-24T03:21:58+00:00
- Post Title: Xenoblade Chronicles X/2 format bible

Can't wait until we can extract 3d models
## Post #10
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-05-21T09:06:41+00:00
- Post Title: Xenoblade Chronicles X/2 format bible

is there a way to extract data from xci (switch cartridge image)?
## Post #11
- Username: LOGCETERA
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon May 28, 2018 4:51 pm
- Post datetime: 2018-07-24T07:59:29+00:00
- Post Title: Xenoblade Chronicles X/2 format bible

I've been browsing around in the Xenoblade 2 game files and found a file called tora.bin in the minigames folder. It's got to be the game file to Tiger! Tiger!, right? If so, what could be done with it? Messing around in a text editor didn't get me anywhere... Answers would be kindly appreciated!
## Post #12
- Username: ignika98
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 08, 2012 11:09 pm
- Post datetime: 2018-11-19T10:26:36+00:00
- Post Title: Xenoblade Chronicles X/2 format bible

Any way to extract the data from the .casmda files? I'm trying to extract the map model, if that's even possible.
## Post #13
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2018-11-19T23:14:07+00:00
- Post Title: Xenoblade Chronicles X/2 format bible

Hey, is it possible to convert .anm files into FBX files or no?
## Post #14
- Username: sfc123
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 10, 2014 2:25 am
- Post datetime: 2019-01-07T13:31:37+00:00
- Post Title: Xenoblade Chronicles X/2 format bible

welldone~~ how to export nca from xci?
## Post #15
- Username: sfc123
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 10, 2014 2:25 am
- Post datetime: 2019-01-07T13:34:08+00:00
- Post Title: Xenoblade Chronicles X/2 format bible

how to export Xenoblade Chronicles 2 from xci?
## Post #16
- Username: sfc123
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 10, 2014 2:25 am
- Post datetime: 2019-01-07T14:07:59+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

well done;~~
## Post #17
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-01-13T14:06:14+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

Just got my hands on XC2 Torna, arh/ard unpacker extacts files without problems.
All you need to do is rename bf2.ard to ira.ard at line 8 or so.
## Post #18
- Username: masagrator
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 17, 2018 7:45 am
- Post datetime: 2019-01-20T12:36:58+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

I tried your script for arh file (Xenoblade 2 + update 2.0.2) and i got

```

Error: invalid command "if" or arguments -1 at line 41
```


I tried on 0.9.2, 0.9.0 and 0.7.7
Always the same

Edit: OK, problem solved, it just copied wrong.
## Post #19
- Username: MBychowski
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 18, 2019 7:02 am
- Post datetime: 2019-10-17T23:06:33+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

Is it possible to open and extract data from .wismda files?
It'd be pretty great to have access to the map models
## Post #20
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2020-03-13T01:04:28+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

```
  expected by the script:

  this one: "~%"
  7e 98 25 f8                                       ~.%.

  expected: "xbc1"
  78 62 63 31                                       xbc1

- 24 files found in 6 seconds
  coverage file 0    53%   1036794    1929104    . offset 00000000000fd208
  coverage file 1     0%   1627499    11007429922 . offset 000000000018d5e4
```

So I tried extracting the updated .ard and .arh file with the quickbms script with quickbms version 0.9.2 and it didn't extract all files, is it the updated .ard and .arh files or it is the script itself I need to edit?
## Post #21
- Username: kees
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 11, 2019 5:52 am
- Post datetime: 2020-05-19T20:40:22+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

> Reply from PredatorCZ ↑Wed Apr 11, 2018 4:24 pm at Wed Apr 11, 2018 4:24 pm
>
> 
chrrox wrote:is there a decrypted release out there?
There is hactool decryptor already released. It can extract/decrypt most NSW cartriges.


Here is another script, that will extract SAR Containers from both games.
Code: Select all# Xenoblade Chronicles sar unpacker
# Author Lukas Cone in 2016-2018
# script for QuickBMS http://quickbms.aluigi.org

get FOURCC long

if FOURCC == 0x31524153   
	endian big
elif FOURCC == 0x53415231
	endian little
else
	cleanexit
endif


get filesize long
get Version long
get FILES long
get OFFSET long
get DataOffset long
get dummy long
get dummy long
getdstring PATH 128

goto OFFSET

for i = 0 < FILES
    get iOffset long
    get iLen long
    get dummy long
    putarray 0 i iOffset
    putarray 1 i iLen
    set _fname PATH
	string _fname + "/"
	if Version > 500 
		getdstring iFname 36
		string _fname + iFname
		goto 48 0 SEEK_CUR
	else
		getdstring iFname 52
		string _fname + iFname
	endif
	putarray 2 i _fname	
next i

for i = 0 < FILES
  getarray iOffset 0 i
  getarray iLen 1 i
  getarray iFname 2 i
  log iFname iOffset iLen
next i

ive tried it and tried feeding it into foobar with the .nop plugin but each time seem to get the file is corrupted. am i trying to read it out wrong or? even on quick bms 0.7.7.
## Post #22
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-05-20T19:25:27+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

> Reply from andree ↑Fri Mar 13, 2020 9:04 am at Fri Mar 13, 2020 9:04 am
>
> 
So I tried extracting the updated .ard and .arh file with the quickbms script with quickbms version 0.9.2 and it didn't extract all files, is it the updated .ard and .arh files or it is the script itself I need to edit?

This thing is still being updated? Damn. From this error message, it seems, that file is marked as compressed, but actually isn't. Or they added something new to the archives.

> Reply from kees ↑Wed May 20, 2020 4:40 am at Wed May 20, 2020 4:40 am
>
> 
ive tried it and tried feeding it into foobar with the .nop plugin but each time seem to get the file is corrupted. am i trying to read it out wrong or? even on quick bms 0.7.7.

If the file begins with sadf dpcm/opus and head, it's a valid nop file. Make sure, your filename extension is .nop, if you're using vgmstream plugin, it will detect formats by extension first. Also vgmstream only supports opus formats, so if you have the one with dpcm, it won't work.
## Post #23
- Username: MasterFoodsBBQSauce
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 10, 2020 9:02 am
- Post datetime: 2020-06-10T01:17:28+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

I've dumped my RomFS, then extracted the files from bf2.arh and bf2.ard. I've also located [this list of data tables](https://xenoblade.github.io/xb2/) online, which...seems to pull data from common.bdat ...?
I don't know how to edit anything here, how to compile those tables myself; the online collection doesn't seem to have an author listed, so I can't exactly ask them for help.

Specifically, I want to locate three tables: this [AchievementSet table](https://xenoblade.github.io/xb2/bdat/common/FLD_AchievementSet.html), so I can reset my Affinity Charts for a NG-like NG+ playthrough, this [Blade data table](https://xenoblade.github.io/xb2/bdat/common/CHR_Bl.html) so I can give Blades with only two Aux Core slots three of them, and optionally this [Driver data table](https://xenoblade.github.io/xb2/bdat/common/CHR_Dr.html), so I can edit max HP and other stats for Rex, Tora, and Zeke.

Could someone please assist me? I know this game's old, and unfortunately almost no-one's working on this brilliant game anymore, and Xenoblade: Definitive just released, but I still much prefer this one.
## Post #24
- Username: KUTSHKY
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 15, 2020 9:58 am
- Post datetime: 2021-03-10T11:31:28+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

how to extract .wifnt
Font?
## Post #25
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-07-23T15:24:28+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

> Reply from PredatorCZ ↑Sat Apr 21, 2018 11:29 pm at Sat Apr 21, 2018 11:29 pm
>
> 
Here is a QuickBMS script version 2, that will extract contents of bf2.ard/arh archives. From Xenoblade 2.
Some extracted files will have [%file id%] %filename% names, cause is that script cannot find them in a tree. Cause is unknown.

Make sure that both ard/arh files are in same folder and in quickbms dialog, always select bf2.arh.
Code: Select all# Xenoblade Chronicles arh/ard unpacker
# Author Lukas Cone in 2018, Version 2
# script for QuickBMS http://quickbms.aluigi.org
# 1st iteration 1:15 hours
# 2nd iteration 40 minutes
endian little
comtype zlib
open FDSE "bf2.ard" 1

idstring 0 "arh1" 

get unk long
get numnodes long
get offset1 long
get size1 long
get offset2 long
get size2 long
get tocoffset long
get numfiles long

filexor "0x33 0xB5 0xE2 0x5D"
GoTo offset1 0 SEEK_SET
get chunksize long
for i = 0 < numfiles
	savepos OFFSET
	get fname string
	putarray 0 i fname
	math OFFSET n OFFSET
	math OFFSET + offset1
	putarray 3 i OFFSET
	get fid long;
next i

GoTo offset2 0 SEEK_SET
set numusednodes long 0
for i = 0 < numnodes
	get id1 SIGNED_LONG
	get id2 SIGNED_LONG
	putarray 1 i id1
	putarray 2 i id2
	if id2 > -1
		putarray 4 numusednodes i
		math numusednodes + 1
	endif
next i
filexor ""



GoTo tocoffset 0 SEEK_SET
for i = 0 < numfiles
	get coffset longlong
	get csize long
	get ucsize long
	get compressed long
	get id long
	getarray Filename01 0 i
	getarray fileoffset 3 i
	strlen filenamelen Filename01
	math Fileend = fileoffset
	math Fileend - filenamelen
	string cstr = ""
	callfunction FindFilename 1
	strlen NAME_LENGTH cstr
	math filenameoffset - fileoffset
	math filenameoffset n filenameoffset
#	print "%filenameoffset%"
	if filenameoffset > 0
		string Filename01 < filenameoffset
	endif
	string cstr + Filename01
	
	if compressed > 0
		GoTo coffset 1 SEEK_SET
		idstring 1 "xbc1" 
		get _numfiles long 1
		get _ucsize long 1
		get _csize long 1
		get _hash long 1
		getdstring _fname 28 1
		savepos OFFSET 1
		if NAME_LENGTH < 1
			string cstr P "[%id%] %_fname%"
		endif
		clog cstr OFFSET csize ucsize 1
	else
		if NAME_LENGTH < 1
			string cstr P "[%id%] %Filename01%"
		endif
		log cstr coffset csize 1
	endif	
next i


startfunction FindFilename
	for g = 0 < numusednodes
		getarray f 4 g
		getarray id1 1 f
		getarray id2 2 f
		if id1 <= fileoffset && id1 > Fileend 
			set filenameoffset SIGNED_LONG id1
#			print "%filenameoffset% %id2%"
			set currentChar SIGNED_LONG f
			callfunction LOOPNODES 1
			string cstr r cstr
#			print "%cstr%"
			break	
		endif
	next g
endfunction

startfunction LOOPNODES
	set cci SIGNED_LONG id2
	getarray id1 1 id2
	getarray id2 2 id2
	math currentChar ^ id1
#	print "%currentChar% %id1% %id2%"
	string _cstr = currentChar
	string cstr + _cstr
	set currentChar SIGNED_LONG cci
#	print "%cstr%"
	if id2 > 0 
		callfunction LOOPNODES 1
	endif
endfunction
It works with Xenoblade 3's archive files, all you need to do is to replace bf2.ard with bf3.ard and zlib with zstd.
## Post #26
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2022-07-25T13:17:00+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

> Reply from andree ↑Sat Jul 23, 2022 11:24 pm at Sat Jul 23, 2022 11:24 pm
>
> 
It works with Xenoblade 3's archive files, all you need to do is to replace bf2.ard with bf3.ard and zlib with zstd.

It took me 4 hours to extract around 76k files and around 7k had incomplete filenames. That's kinda unacceptable. The script is clearly flawed.

EDIT: Made a native tool in [https://github.com/PredatorCZ/XenoLib/releases/](https://github.com/PredatorCZ/XenoLib/releases/)
## Post #27
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2022-07-30T17:21:41+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

> Reply from PredatorCZ ↑Mon Jul 25, 2022 9:17 pm at Mon Jul 25, 2022 9:17 pm
>
> 
andree wrote: ↑Sat Jul 23, 2022 11:24 pm
It works with Xenoblade 3's archive files, all you need to do is to replace bf2.ard with bf3.ard and zlib with zstd.  


It took me 4 hours to extract around 76k files and around 7k had incomplete filenames. That's kinda unacceptable. The script is clearly flawed.

Please update your max tool for Xenoblade 3
## Post #28
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-07-31T04:30:29+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

> Reply from ice ↑Sun Jul 31, 2022 1:21 am at Sun Jul 31, 2022 1:21 am
>
> 
PredatorCZ wrote: ↑Mon Jul 25, 2022 9:17 pm
andree wrote: ↑Sat Jul 23, 2022 11:24 pm
It works with Xenoblade 3's archive files, all you need to do is to replace bf2.ard with bf3.ard and zlib with zstd.  


It took me 4 hours to extract around 76k files and around 7k had incomplete filenames. That's kinda unacceptable. The script is clearly flawed.


Please update your max tool for Xenoblade 3

He's already working on a new tool that replaces it.
## Post #29
- Username: yham
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 30, 2019 1:22 pm
- Post datetime: 2022-08-01T11:58:57+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

Is anyone working on the new Bdat format for XB3?
I had trouble finding labels and value types.
## Post #30
- Username: Nohmdd
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 24, 2022 6:48 am
- Post datetime: 2022-08-03T17:37:56+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

> Reply from yham ↑Mon Aug 01, 2022 7:58 pm at Mon Aug 01, 2022 7:58 pm
>
> 
Is anyone working on the new Bdat format for XB3?
I had trouble finding labels and value types.

Someone on gbatemp seems to have
## Post #31
- Username: yham
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 30, 2019 1:22 pm
- Post datetime: 2022-08-03T19:39:41+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

> Reply from Nohmdd ↑Thu Aug 04, 2022 1:37 am at Thu Aug 04, 2022 1:37 am
>
> 
yham wrote: ↑Mon Aug 01, 2022 7:58 pm
Is anyone working on the new Bdat format for XB3?
I had trouble finding labels and value types.


Someone on gbatemp seems to have

Can you give me the post title or link?
## Post #32
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2022-08-12T09:03:35+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

> Reply from yham ↑Mon Aug 01, 2022 7:58 pm at Mon Aug 01, 2022 7:58 pm
>
> 
Is anyone working on the new Bdat format for XB3?
I had trouble finding labels and value types.

Made simple dumper [https://github.com/PredatorCZ/XenoLib/releases](https://github.com/PredatorCZ/XenoLib/releases)
I'm trying to figure out encryption for key names.
## Post #33
- Username: yham
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 30, 2019 1:22 pm
- Post datetime: 2022-08-13T05:24:33+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

> Reply from PredatorCZ ↑Fri Aug 12, 2022 5:03 pm at Fri Aug 12, 2022 5:03 pm
>
> 
yham wrote: ↑Mon Aug 01, 2022 7:58 pm
Is anyone working on the new Bdat format for XB3?
I had trouble finding labels and value types.


Made simple dumper https://github.com/PredatorCZ/XenoLib/releases
I'm trying to figure out encryption for key names.

Thanks for your efforts. I am about to give up on key names and am hoping you can help us.
## Post #34
- Username: Alexj9626
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 18, 2022 1:08 pm
- Post datetime: 2022-08-18T05:10:06+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

Any way to extract XC3 .arh/ard files?

Looking for the game pictures/icons and all that.

Edit: for anyone looking for the pics/icons files:

[https://drive.google.com/drive/folders/ ... TvqC0ZFDwk](https://drive.google.com/drive/folders/1L2QeQGjoyXc5S7qahM8Ep3TvqC0ZFDwk)
## Post #35
- Username: wulfy12
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 04, 2020 12:33 pm
- Post datetime: 2022-08-23T21:33:00+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

> Reply from Alexj9626 ↑Thu Aug 18, 2022 1:10 pm at Thu Aug 18, 2022 1:10 pm
>
> 
Any way to extract XC3 .arh/ard files?

Looking for the game pictures/icons and all that.

Edit: for anyone looking for the pics/icons files:

https://drive.google.com/drive/folders/ ... TvqC0ZFDwk
[https://github.com/PredatorCZ/XenoLib/releases](https://github.com/PredatorCZ/XenoLib/releases) should have the extract arh tool in it
## Post #36
- Username: CleanHUDplease
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 11, 2023 11:35 pm
- Post datetime: 2023-07-11T15:39:52+00:00
- Post Title: Re: Xenoblade Chronicles X/2 format bible

Hello, would it be possible to re-convert a .WILAY files back? I am using the XenobladeToolset-0.4.64-win64, tex_to_dds.cmd. It will load the texture under visual studio. I can edit it, however I can not resave it as a .WILAY file. So I can't load the custom texture on my Nintendo Switch. I am trying to create a clean HUD mod for the Xenoblade games on Nintendo Switch, starting with Xenoblade 2. If anyone could help me I would be eternally greatful.
