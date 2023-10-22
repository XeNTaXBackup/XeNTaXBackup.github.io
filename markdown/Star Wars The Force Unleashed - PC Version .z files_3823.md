## Post #1
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-11-01T23:36:25+00:00
- Post Title: Star Wars The Force Unleashed - PC Version .z files

Hello,

I'm trying to uncompress some files found on PC version of Star Wars The Force Unleashed, I figured out the following until now:

```
0        4          Uncompressed size
4        4          ZSIZE -> Compressed size (file size minus 0xC bytes) 
8        4          Checksum?
C        ZSIZE   Contents

```


I have attached a sample, can some please take a look?

I already have tested quickbms using several uncompression type (ComType xxxxxx), none of them worked. Maybe contents are encrypted?

Thanks!
[RenderOptions.schema.xml.zip](https://xentaxbackup.github.io/file/2490_RenderOptions.schema.xml.zip)
## Post #2
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-02T23:25:31+00:00
- Post Title: Star Wars The Force Unleashed - PC Version .z files

The compressed data is XOR FF'd.
The compression looks like LZSS.
## Post #3
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-11-03T00:13:21+00:00
- Post Title: Star Wars The Force Unleashed - PC Version .z files

> Reply from GameZelda
>
> The compressed data is XOR FF'd.
The compression looks like LZSS.

Thanks!

But didn't work. I tried:

get SIZE LONG
get ZSIZE LONG

comtype lzss
filexor "\xff"
clog NAME.txt "\x0c" ZSIZE SIZE
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-05T03:33:40+00:00
- Post Title: Star Wars The Force Unleashed - PC Version .z files

the correct script would be:

```
get SIZE long
get ZSIZE long
get DUMMY long
savepos OFFSET
filexor 0xff
clog "dump.dat" OFFSET ZSIZE SIZE
```
but can't work because the algorithm is not lzss, it's something else
## Post #5
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-11-05T14:08:47+00:00
- Post Title: Star Wars The Force Unleashed - PC Version .z files

Thanks, aluigi.
## Post #6
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2009-11-05T20:51:15+00:00
- Post Title: Star Wars The Force Unleashed - PC Version .z files

Hi 
Can someone make an unpacker for the game .lp files?
Sample:[http://www.zshare.net/download/6802877050e22834/](http://www.zshare.net/download/6802877050e22834/)
## Post #7
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-08T17:33:06+00:00
- Post Title: Star Wars The Force Unleashed - PC Version .z files

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

# The container format seems pretty strange and I don't understand it much, but this script works...

# File Header
IDString "kaPA"
Get @version long
If @version != 5
	Print "@version = %@version%, expected 5."
	CleanExit
EndIf
Get @nFiles long

GoTo 0x1C
Get @fileNameTableSize long
Get @fileOffTableOff long
Get @dataOff long

# Calculate some useful stuff
Set @fileNameTableOff 0x50

Set @fileInfoTableOff @fileNameTableOff
Math @fileInfoTableOff += @fileNameTableSize

# Extract the files
For @i = 0 < @nFiles
	# Get the file name (there's an offset to it at 0x14 of the file info table)
	Set @fileNameOffOff @i
	Math @fileNameOffOff *= 0x40
	Math @fileNameOffOff += @fileInfoTableOff
	Math @fileNameOffOff += 0x14
	GoTo @fileNameOffOff

	Get @fileNameOff long
	Math @fileNameOff += @fileNameTableOff
	GoTo @fileNameOff

	Get @fileName string

	# Get the file size (it's at 0x28 of the file info table)
	Set @fileSizeOff @i
	Math @fileSizeOff *= 0x40
	Math @fileSizeOff += @fileInfoTableOff
	Math @fileSizeOff += 0x28
	Goto @fileSizeOff

	Get @fileSize long

	# Get the file offset (it's at 0x04 of the file offset table)
	Set @fileOffOff @i
	Math @fileOffOff *= 0x10
	Math @fileOffOff += @fileOffTableOff
	Math @fileOffOff += 0x04
	Goto @fileOffOff

	Get @fileOff long
	Math @fileOff += @dataOff
	
	# Extract the data, finally
	Log @fileName @fileOff @fileSize
Next @i

```
## Post #8
- Username: Magniel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 05, 2009 3:10 pm
- Post datetime: 2009-11-24T19:14:52+00:00
- Post Title: Star Wars The Force Unleashed - PC Version .z files

And can I use this script to extract and also pack that archive? In that case, can someone explain me how please?

//EDIT: Ok, I can extract that archive, thank you for script, but can I get it back to the archive?
## Post #9
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-11-30T11:20:08+00:00
- Post Title: Star Wars The Force Unleashed - PC Version .z files

The script don't work for larger files.

> QuickBMS generic files extractor 0.3.9a
>
> by Luigi Auriemma
>
> e-mail: aluigi@autistici.org
>
> web:    aluigi.org
>
> 
>
> - GUI mode activated, remember that the tool works also from command-line
>
>   where are available various options like folder scanning, filters and so on
>
> 
>
> - select the input archive/file to extract
>
> - select the output folder where extracting the files
>
> - open input file E:\Games\Star Wars The Force Unleashed\LevelPacks\tem_jeditemp
>
> le_b_pc.lp
>
> - open script D:\[SNP] Ripping Tools\quickbms2\starwars.txt
>
> - set output folder E:\[Archives] Extracted Files\[PC] Star Wars Force Unleashed
>
> 
>
> 
>
>   offset   filesize   filename
>
> ------------------------------
>
> 
>
> - 0 files found in 0 seconds
>
> 
>
> Press RETURN to quit
## Post #10
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-12-01T18:22:14+00:00
- Post Title: Star Wars The Force Unleashed - PC Version .z files

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: PantheraKing
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 04, 2009 3:44 pm
- Post datetime: 2009-12-04T20:50:04+00:00
- Post Title: Star Wars The Force Unleashed - PC Version .z files

Hi,

I did a more generic script to extract files from files .lp

It works with any .lp files (If not just tell me but i've tested it on almost all files)
If you can figure out some of the "UNKNOWN" fields please tell me, because i'm writing a SWTFU Tool like Kotor Tool

```
# Star Wars The Force Unleashed PC / .lp extractor
# script for QuickBMS http://aluigi.org/papers.htm#quickbms


# OFFSET TABLE LAYOUT - SIZE=0x10
#
#	0x00 - FILE INDEX - 4
# 	0x04 - FILE DATA OFFSET - 4
#	0x08 - ALWAYS 0 - 4
#	0x0C - ALWAYS 0 - 4

# INFO TABLE LAYOUT - SIZE=0x40
#
#	0x00 - UNKNOWN - 4
#	0x04 - UNKNOWN - 4
#	0x08 - ALWAYS 0 - 4
#	0x0C - UNKNOWN - 4
#	0x10 - UNKNOWN - 4
#	0x14 - NAME OFFSET - 4
#	0x18 - UNKNOWN - 4
#	0x1C - ALWAYS 0 - 4
#	0x20 - ALWAYS 0 - 4
#	0x24 - ALWAYS 0 - 4
#	0x28 - FILE SIZE - 4
#	0x2C - FILE SIZE CHECK? - 4
#	0x30 - ALWAYS 0 - 4
#	0x34 - UNKNOWN - 4
#	0x38 - ALWAYS 0 - 4
#	0x3C - ALWAYS 0 - 4

getdstring	IDSTRING		4
get		FILE_VERSION		long
get		NUM_FILES		long

get		UNKNOWN1		long # Seems to be always 0x00000000
get		UNKNOWN2		long # Seems to be always 0xFFFFFFFF
get		UNKNOWN3		long # Seems to be always 0x00000000


# The header seems to change depending of this value
# It seems to be the extra header size
# Default header size is 0x50, to get the correct offset for the name table, you have to do
# 0x50 + EXTRA_HEADER_SIZE

get		EXTRA_HEADER_SIZE	long
get		NAME_TABLE_SIZE		long
get		OFFSET_TABLE_OFF	long
get		DATA_OFF		long
get		UNKNOWN4		long
get		UNKNOWN5		long
get		DATA_OFF_2		long # Seems to be always the same value as DATA_OFF
get		WHOLE_FILE_SIZE		long # Seems to be the size of the whole file
get		UNKNOWN6		long # Seems to be always 0x00000000
get		UNKNOWN7		long # Seems to be always 0x00000000
get		UNKNOWN8		long # Seems to be always 0x00000000
get		DATA_OFF_3		long # Seems to be always the same value as DATA_OFF
get		WHOLE_FILE_SIZE_2	long # Seems to be always the same value as WHOLE_FILE_SIZE
get		UNKNOWN9		long # Seems to be always 0x00000000

set		NAME_TABLE_OFF		EXTRA_HEADER_SIZE
math		NAME_TABLE_OFF		+= 0x50

set		INFO_TABLE_OFF		NAME_TABLE_OFF
math		INFO_TABLE_OFF		+= NAME_TABLE_SIZE

########### FILE CHECKS ##############

if	IDSTRING != "kaPA"
		print "File type check error\nThis is not a SWTFU .lp file\n"
		cleanExit
endif

if	FILE_VERSION != 0x00000005
		print "File version is not supported!\nExpected version: 5\nThis version: %FILE_VERSION%\n"
		cleanExit
endif

if	WHOLE_FILE_SIZE != WHOLE_FILE_SIZE_2
		print "File size check error: %WHOLE_FILE_SIZE% - %WHOLE_FILE_SIZE_2%\n"
		cleanExit
endif

if	DATA_OFF != DATA_OFF_2
		print "Data offset check error: %DATA_OFF% - %DATA_OFF_2% - %DATA_OFF_3%\n"
		cleanExit
elseif	DATA_OFF != DATA_OFF_3
		print "Data offset check error: %DATA_OFF% - %DATA_OFF_2% - %DATA_OFF_3%\n"
		cleanExit
endif

########### EXTRACTION ###############

for	i = 0 < NUM_FILES
	
		set	FILE_INFO_POS		i
		math	FILE_INFO_POS		*= 0x40 # Size of INFO_TABLE struct for each file
		math	FILE_INFO_POS		+= INFO_TABLE_OFF

		set	FILE_OFFSET_POS		i
		math	FILE_OFFSET_POS		*= 0x10 # Size of FILE_OFFSET struct for each file
		math	FILE_OFFSET_POS		+= OFFSET_TABLE_OFF

		# GET FILE NAME

		set	TEMP_POS		FILE_INFO_POS
		math	TEMP_POS		+= 0x14
		
		goto	TEMP_POS
		get	FILE_NAME_OFFSET	long
		math	FILE_NAME_OFFSET	+= NAME_TABLE_OFF
		
		goto	FILE_NAME_OFFSET
		get	FILE_NAME		string

		# GET FILE SIZE
		
		set	TEMP_POS		FILE_INFO_POS
		math	TEMP_POS		+= 0x28
	
		goto	TEMP_POS
		get	FILE_SIZE		long
		
		# GET FILE DATA

		set	TEMP_POS		FILE_OFFSET_POS
		math	TEMP_POS		+= 0x04
		
		goto	TEMP_POS
		get	FILE_DATA_OFFSET	long
		math	FILE_DATA_OFFSET	+= DATA_OFF

		# WRITE FILE

		log	FILE_NAME FILE_DATA_OFFSET FILE_SIZE

next i


######################################

```
## Post #12
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-12-08T01:06:47+00:00
- Post Title: Star Wars The Force Unleashed - PC Version .z files

Have you been able to figure out anything for the pcp/pcd files?
## Post #13
- Username: Magniel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 05, 2009 3:10 pm
- Post datetime: 2009-12-08T07:33:59+00:00
- Post Title: Star Wars The Force Unleashed - PC Version .z files

> Reply from PantheraKing
>
> Hi,

I did a more generic script to extract files from files .lp

It works with any .lp files (If not just tell me but i've tested it on almost all files)
If you can figure out some of the "UNKNOWN" fields please tell me, because i'm writing a SWTFU Tool like Kotor Tool
Code: Select all.
.
.

That script don't work for me. QuickBMS shows "Error: invalid command "elseif" or arguments 3 at line 86" I'm noob, so I don't see any problem on that line...
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-08T09:52:58+00:00
- Post Title: Star Wars The Force Unleashed - PC Version .z files

in case of problems like this check EVER if exist a newer version of QuickBMS (0.3.10 at the moment):
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
## Post #15
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2009-12-15T20:28:46+00:00
- Post Title: Star Wars The Force Unleashed - PC Version .z files

Chrrox and I have been working on the Unleashed model format. Here is a picture of a StormTrooper that we ripped. The ripping is not yet automated, yet if you would like the script it will be posted on my blog when complete: [http://uberblack3d.blogspot.com/](http://uberblack3d.blogspot.com/)

WE NEED YOUR HELP!

What is left to do?

We would like to get some help finding the bone format and integrating this into our 3DSMAX script. Also animation is very possible and we also need help with this. If you are interested in helping in this project let Chrrox or me know or just edit our script and post it.

Also if anyone is good at figuring out the sound format that would be awesome too.

Note: All the mesh formats with UV's have been discovered and is able to be imported into max via Script.

Very special thanks to Luigi for a great BMS script to extract the assets.

The first link is for the Storm Trooper model, and Animations. I have also included the Alpha of the 3DSMax script that we are still working on for other's to critique or improve. The second is a PCP & PCD file which I think is sound.

Storm Trooper Mesh & Animations
[http://www.sendspace.com/file/gvvi7s](http://www.sendspace.com/file/gvvi7s)

Storm Trooper Sounds
[http://www.sendspace.com/file/ytdr37](http://www.sendspace.com/file/ytdr37)
## Post #16
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-12-16T17:09:04+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

i would be willing to help out with the mesh skinning and animation data.  i will take a look when i get the chance.
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2009-12-16T19:55:18+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from UberBlack
>
> Chrrox and I have been working on the Unleashed model format. Here is a picture of a StormTrooper that we ripped. The ripping is not yet automated, yet if you would like the script it will be posted on my blog when complete: http://uberblack3d.blogspot.com/


Note: All the mesh formats with UV's have been discovered and is able to be imported into max via Script.


The first link is for the Storm Trooper model, and Animations. I have also included the Alpha of the 3DSMax script that we are still working on for other's to critique or improve. 

Storm Trooper Mesh & Animations
http://www.sendspace.com/file/gvvi7s
Thank you for this info, I tried to run your maxscript with 3ds Max 2009 but it produces an error:
>> MAXScript FileIn Exception: -- Unable to convert: undefined to type: Integer << 

I have also been looking into the gto format since using PantheraKing's bms script to extract all the files from the lp containers, GameZelda's script didn't seem to work with the large lp files.
Although you can use 3d Ripper DX to extract the models and textures from SWTFU I prefer to have the characters already in their T-pose to make editing them much easier upon import.

My gto search led me to this site:
[http://www.tweaksoftware.com/products/o ... tware/gto/](http://www.tweaksoftware.com/products/open-source-software/gto/)
The source can be downloaded from here:
[http://sourceforge.net/projects/gto/](http://sourceforge.net/projects/gto/)
The example cube.gto and plane.gto included in the source looks very similar to the gto files extracted from the SWTFU lp containers. 

There is a gto2obj utility as well as others included in the source:
[http://gto.tweakadmin.com/3_4_docs/gto_60.html#SEC62](http://gto.tweakadmin.com/3_4_docs/gto_60.html#SEC62)

Apparently you need Cygwin environment and gcc 3.x to compile this for Windows but I have no experience with these things.
[http://gto.tweakadmin.com/3_4_docs/gto_5.html#SEC7](http://gto.tweakadmin.com/3_4_docs/gto_5.html#SEC7)
If someone here already has the required software set up on their machine and would be willing to compile and test the utilities that would be great since Wavefront obj is more common and can be imported into many different 3d programs and not just 3ds Max. 

[http://gto.tweakadmin.com/3_4_docs/gto_ ... C_Contents](http://gto.tweakadmin.com/3_4_docs/gto_toc.html#SEC_Contents)
## Post #18
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-12-17T02:40:24+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Good find on the format information.  The data does in deed appear to follow the format in the documentation.  But it appears to be a modified version of the file format as some things they list as being uint32 are uint16 values in this format.  i am still going through the documentation .  i had gotten the string table information and the data sizes of the first sections before i checked back here, but now with this i have easier access to determining what things should be, at least initially anyways.  will have to see how it goes.
## Post #19
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2009-12-18T00:39:22+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

I have only tested it with 3DSMax 2010. Make sure to change the path in the first line (of course). All meshes work but they have to be done by hand at this point. I will post the full 3DSMax script on this board for someone to improve the script if they wish. Animation and Bones with weighting would be most ideal.

>>>> SCRIPT

fname = "C:\\TEMP\\ma_trooperStormClassic.gto"  --file name
f = fopen fname "rb"   --open file in read only format
Vert_array = #()    --define arrays for verts, normals, UV and Faces
Normal_array = #()
UV_array = #()
Face_array = #()
--fseek f 0x12C38 #seek_cur
fseek f 0x54DBE #seek_cur

FCount = readlong f
Null1 = readlong f
VCount = readlong f
Null2 = readlong f

FaceDirection = -1
f1 = (readshort f) + 1   --read face indices, games are start form 0, but Max start from 1
f2 = (readshort f) + 1   --so we add 1 to each index
for i = 3 to (Fcount)  do (    --already readf 2 verts, so start from 3	
f3 = (readshort f) + 1
FaceDirection *= -1	
if (f3 != f1) AND (f3 != f2) then (   --if not idential verts, create face
if FaceDirection > 0 then append Face_array [f1,f2,f3]     --base on face direction to create face
else append Face_array [f1,f3,f2]
)
f1 = f2     --shift the verts
f2 = f3
)
--for i = 1 to (Fcount / 3) do (
--f1 = (readshort f) + 1   --read face indices, games are start form 0, but Max start from 1
--f2 = (readshort f) + 1   --so we add 1 to each index
--f3 = (readshort f) + 1
--append Face_array [f1,f2,f3] --save faces to Face_array
--)


for i = 1 to VCount do (   --* number of verts count
vx = readfloat f     --read xyz coordinates
vy = readfloat f
vz = readfloat f
append Vert_array [vx,vy,vz] --save verts to Vert_array
        --since UV in Max are in point3 format, so we add 0 for z value
nx = readlong f    --read Normal ??
ny = readlong f
nz = readlong f
append Normal_array [nx,ny,nz] --save normals to Normal_array

tu = readfloat f     --read UV float value
tv = (readfloat f) * -1 
append UV_array [tu,tv,0]  --save UVs to UV_array
boneweight1 = readlong f
boneweight2 = readlong f
boneweight3 = readlong f
boneweight4 = readlong f
boneweight5 = readlong f
)
for i = 1 to Bcount do (
	Bnum = readlong f
)


fclose f     --close file
msh = mesh vertices:Vert_array faces:Face_array   --build mesh
msh.numTVerts = UV_array.count
buildTVFaces msh
for j = 1 to UV_array.count     do setTVert  msh j UV_array[j]
for j = 1 to Face_array.count   do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
## Post #20
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2009-12-18T09:10:21+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Ok I fixed the script error that I previously posted about, I didn't realize the file paths were case sensitive so I had to change TEMP to temp to reflect the lower case letters of my folder's name.

The ma_trooperStormClassic.gto included in your download produced this error:

```
>> MAXScript FileIn Exception: -- Unable to convert: undefined to type: Integer <<
```


I ran the max script on mb_darkFelucianWarrior.gto and it looked liked it was finally going to work but another error crept up 3 seconds into it:

```
--  Frame:
--   i: 391646
--   f3: undefined
-- Error occurred during fileIn in <File:C:\Program Files\Autodesk\3ds Max 2009\Scripts\StarWarsUnleashed_StormTrooper.ms>
>> MAXScript FileIn Exception: -- No ""+"" function for undefined << 
```


dh_scrapDrone_LOD1.gto produced this error:

```
--  Frame:
--   vy: undefined
--   tv: undefined
--   nz: undefined
--   boneweight5: undefined
--   boneweight2: undefined
--   tu: undefined
--   vx: undefined
--   i: 11471
--   ny: undefined
--   boneweight4: undefined
--   boneweight1: undefined
--   vz: undefined
--   nx: undefined
--   boneweight3: undefined
-- Error occurred during fileIn in <File:C:\Program Files\Autodesk\3ds Max 2009\Scripts\StarWarsUnleashed_scrapDrone_LOD1.ms>
>> MAXScript FileIn Exception: -- Unable to convert: undefined to type: Float <<
```


dh_scrapDrone.gto produced this error:

```
>> MAXScript FileIn Exception: -- Unable to convert: undefined to type: Integer <<

```
 

Train_FloorA.gto produced this error:

```
-- Error occurred in i loop; filename: C:\Program Files\Autodesk\3ds Max 2009\Scripts\StarWarsUnleashed_Train_FloorA.ms; position: 635
--  Frame:
--   i: 44678
--   f3: undefined
-- Error occurred during fileIn in <File:C:\Program Files\Autodesk\3ds Max 2009\Scripts\StarWarsUnleashed_Train_FloorA.ms>
>> MAXScript FileIn Exception: -- No ""+"" function for undefined <<

```


Needless to say, none of my attempts to convert these gto files with your max script have been successful but i'll continue to try more gto files to see if anything changes.
Has anyone else here had any luck with this max script?
## Post #21
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-12-18T18:53:53+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

First, I want to say, guys, what you are doing is just great!!  
I tested the Max script for 2008 version, with any file gto he gives the same error:

```
-- No ""+"" function for undefined
```


Also I noticed mention of the bones in the xml-files.
## Post #22
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2009-12-19T20:53:27+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

The file only works with Storm Trooper (Classic). The script is not automatic, because we haven't yet discovered the offsets so it will only work with every file automatically. If you want other models, you will have to use a hex editor and extract the pieces by hand for example the Storm Trooper (Classic) model has 2 pieces. They are @:

0x12C38
0x54DBE

But that's for the Storm Trooper (Classic) model. This will change depending on the model, and there may be more or less pieces. Also we don't know the offset that says how many pieces there are in the file and where to start looking. This is important to create an automatic script in Max. Any help would be helpful. Like I said we can extract any model from this game by finding the offset by hand which is a pain
## Post #23
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2009-12-20T03:05:44+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Ok that makes sense, thanks for the heads-up I guess I misunderstood when you said "All meshes work but they have to be done by hand at this point".

I downloaded the 3ds Max 2010 trial(32 bit if it makes any difference) and tested the max script on the Storm Trooper (Classic) included in your download and it didn't work either, it produced the same error with 2009 as well.

Just to make sure we're on the same page; i'm trying to work with the PC version gto files extracted from SWTFU, whether or not that changes anything I have no idea.  

I think revelation was on to something as well so i'm patiently awaiting his return with more information, he said TFU gto files(although they are a modified version) follow the same format as the gto source that I linked to previously.
Hopefully a complete gto utility can come about from the information collected from all this.

PantheraKing said he was writing a SWTFU Tool similar to KotOR Tool so I look forward to this and I hope he succeeds as well.
## Post #24
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-12-20T05:04:47+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Unfortunately this gto format does not use file offsets to tell where data is stored.  It relies on keeping a running count from the various data sections present after the string table found at the beginning of the file.  After the table there are lists of objects, components, and properties.  Object data lists the number of components for each object, components list the number of properties for each component, and a running index needs to be kept in each case to tell where the component or property starts based on the number processed so far from prior data in the file.  Once the differences in the format are mapped out, should be easy to get the initial offsets from a file, as the objects, components, properties, etc. have indices into the string table that tell the purpose of the relevant data as well as the intended data type and format.  Haven't determined yet how much this format follows the spec yet.  Hopefully i should have this mapped out soon.
## Post #25
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-12-20T07:14:46+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Ok, well the little break away from the format helped.  i haven't determined everything yet, but the data does seem to match up with the max script after the data has been parsed.  i don't know enough about max script to make changes at the moment, but i will see what i can do if no one else is able to make sense of this script first.  i only had the one file from this thread to test with so far, so anyone with 010 Editor or that can otherwise verify the information would be helpful.  Once i am able to compare some more files i should be able to determine if the ordering of the data is always the same, otherwise it is actually more reliable (and correct) to use the type strings associated with the property info to determine the usage of the information.  Some of the data is assumed to follow the official spec; the parts i am using work for the information found so far, but some of the unused poortions may have another interpretation give some of the data types have been truncated.

The various indices in the structure are used to access data in the string table, which list the various data types and interpretation values.  i am currently unsure whether this information is accessible in some form other than strings at the moment, so currently string comparisons would be necessary to verify the type of data accessed by each property.  From that it would also be necessary to take the type, count, and width information into account to handle things properly for composite type for things like position vectors (i.e. a 3d vector would have a type of 1 (= float), variable count, and width of 3).  There are some other composite structure as well i believe.

i haven't checked how the official gto reader code works, but with the information below i would think it would be easy to modify it to work as needed.  i will continue to look into things.

Hope this helps.

```
 * gto.bt - Structure definitions for Star Wars The Force Unleashed - gto file related entities.
 *
 * File strucutre for gto files
 *
 *****************************************************************************
 * Revision History:
 *  2009/12/16 - GWC - Original
 *  2009/12/20 - GWC - Updates to format
 */

#include "common-types.bt"

SetReadOnly(true);

// #pragma displayname("gto structures")
// #pragma fileextensions(".gto")

// #pragma byteorder(little_endian)
LittleEndian();

// mark used bytes with a light green background
SetBackColor(cLtGreen);

// GTO File Structure
struct GTO_FILE
{
//	#pragma lockAt(0x00000000)

	// GTO File Header Structure - 0x14 (20) bytes
	struct GTO_HEADER
	{
		// 0x00
		uint32 fileTag; // GTO magic number 0x29F
		uint32 stringCount;
		uint32 objectCount;
		uint32 fileVersion;
		// 0x10
		uint32 fileFlags;
	} fileHeader; // file header
	
	struct
	{
		struct
		{
			string name;
		} stringTable[fileHeader.stringCount] <optimize = false>;
	} stringTable;
	
	struct
	{
		uint16 nameIndex <format = hex>;
		uint16 protocolIndex <format = hex>;
		uint16 protocolVersion <format = hex>;
		uint16 componentCount <format = hex>;
	} objectData[fileHeader.objectCount];
	
	local uint32 componentCount = 0;
	local uint32 objectNum = 0;
	for (objectNum = 0; objectNum < fileHeader.objectCount; ++objectNum)
	{
		componentCount += objectData[objectNum].componentCount;
	}
	
	Printf("Component Count = 0x%02X (%d)\n", componentCount, componentCount);
	
	struct
	{
		uint16 nameIndex <format = hex>;
		uint16 propertyCount <format = hex>;
	} componentData[componentCount];
	
	local uint32 propertyCount = 0;
	local uint32 componentNum = 0;
	for (componentNum = 0; componentNum < componentCount; ++componentNum)
	{
		propertyCount += componentData[componentNum].propertyCount;
	}
	
	Printf("Property Count = 0x%02X (%d)\n", propertyCount, propertyCount);
	
	struct
	{
		uint16 nameIndex <format = hex>;
		uint16 unknown0x02 <format = hex>;
		uint32 dataCount <format = hex>;
		uint8  dataType <format = hex>;
		uint8  dataWidth <format = hex>;
		uint16 unknown0x0A <format = hex>;
	} propertyInfo[propertyCount];
	
	local uint32 propertyNum = 0;
	struct
	{
		for (propertyNum = 0; propertyNum < propertyCount; ++propertyNum)
		{
			struct
			{
				switch (propertyInfo[propertyNum].dataType)
				{
				case 0: // int32
					int32  data[propertyInfo[propertyNum].dataCount * propertyInfo[propertyNum].dataWidth];
					break;
				case 1: // float
					float  data[propertyInfo[propertyNum].dataCount * propertyInfo[propertyNum].dataWidth];
					break;
				case 2: // double
					double data[propertyInfo[propertyNum].dataCount * propertyInfo[propertyNum].dataWidth];
					break;
				case 3: // float16
					uint16 data[propertyInfo[propertyNum].dataCount * propertyInfo[propertyNum].dataWidth];
					break;
				case 4: // string table index
					uint32 data[propertyInfo[propertyNum].dataCount * propertyInfo[propertyNum].dataWidth];
					break;
				case 6: // uint16
					uint16 data[propertyInfo[propertyNum].dataCount * propertyInfo[propertyNum].dataWidth];
					break;
				case 7: // uint8
					uint8  data[propertyInfo[propertyNum].dataCount * propertyInfo[propertyNum].dataWidth];
					break;
				case 8: // int64
					int64  data[propertyInfo[propertyNum].dataCount * propertyInfo[propertyNum].dataWidth];
					break;
				default:
					Printf("Unknown data format\n");
					break;
				}
			} propertyData;
		}
	} propertyData;
};

struct GTO_FILE fileInfo;

```
## Post #26
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-12-20T09:05:30+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Ok, after comparing against a few more files, and adding a printout of the property interpretation string values, i have abit more information on the format layout.  It appears to be a quite literal export of the original Maya model information directly into compatible structures for use with Direct3D rendering.  Given this i doubt this format would be the same for platforms that are not structured in this way, but i cannot be sure without comparing against the console version of the files.  Unfortunately with this structuring i believe it would be difficult to interpret the format during import without having to do comparisons against the values in the string table.  Modification of a gto importer, or a manual scan of the object, component, and property interpretation strings to find the start of the relevant structures would be necessary.  i am still looking to see of the component and property ordering is the same for the various sub-"structure" information.

Below is the output of the properties listed in the ma_trooperStormClassic.gto file.  For those of you familiar with the rendering methods of Direct3D you will probablt notice the data relevant to Vertex Declarations, Vertex and Index Buffers, etc.  There does appear to be a somewhat consistent ordering but i cannot say for sure it will hold for all cases.  With it appearing the data came from Maya i am guessing that is why certain files start with either ma_ or mb_, etc.  I have also noted the values that signal the start of the 2 offsets that were being used in the original max script for clarification (indices 48 and 135).  This may aid you in updating your script faster since you can verify what you are currently interpreting the data as against this list.  Note the ordering of the values, so it may be possible to come up with some suitable structures for this data if they always hold to this layout.  i will make some comparisons of the component names and see what the order of the associated properties is and how it could possibly relate give the objects the components are assigned to.

EDIT:
Modified output information below to be a little more structured in my script.  A lot more evident what is going on in the file now and the repeating structures are more visible.  After comparing again some models, a somewhat general method of loading parts of these files may be possible using the sub-structure layouts that don't change from file to file.

```
String Table Count = 0xAD (173)
Object Count = 0x09 (9)
Component Count = 0x20 (32)
Property Count = 0xCA (202)


--------------------------------------------------------
Object [0000] - Component Count:    1 - Identifier: ma_trooperStormClassic
	Component [0000] - Property Count:    3 - Identifier: Info
		Property [0000] - Identifier: Platform
		Property [0001] - Identifier: PlatformVersion
		Property [0002] - Identifier: MexVersion


--------------------------------------------------------
Object [0001] - Component Count:    1 - Identifier: ma_trooperStormClassic
	Component [0000] - Property Count:   17 - Identifier: Model
		Property [0003] - Identifier: Name
		Property [0004] - Identifier: CRC
		Property [0005] - Identifier: NumVertices
		Property [0006] - Identifier: NumPrimitives
		Property [0007] - Identifier: Breakable
		Property [0008] - Identifier: TetMaxNodeCount
		Property [0009] - Identifier: BBoxCenter
		Property [0010] - Identifier: BBoxExtents
		Property [0011] - Identifier: RawPolyVertCounts
		Property [0012] - Identifier: RawVertIndices
		Property [0013] - Identifier: NumMeshes
		Property [0014] - Identifier: NumMaterials
		Property [0015] - Identifier: locatorCount
		Property [0016] - Identifier: locators
		Property [0017] - Identifier: mayaAttrCount
		Property [0018] - Identifier: mayaAttrNameCrcs
		Property [0019] - Identifier: mayaAttrOwnerCrcs


--------------------------------------------------------
Object [0002] - Component Count:    1 - Identifier: ma_trooperStormClassic
	Component [0000] - Property Count:    3 - Identifier: Material
		Property [0020] - Identifier: CRC
		Property [0021] - Identifier: Name
		Property [0022] - Identifier: Data


--------------------------------------------------------
Object [0003] - Component Count:    1 - Identifier: ma_trooperStormClassic
	Component [0000] - Property Count:    5 - Identifier: Skeleton
		Property [0023] - Identifier: NumBones
		Property [0024] - Identifier: BasePoseMatrices
		Property [0025] - Identifier: BoneNames
		Property [0026] - Identifier: BoneCRCs
		Property [0027] - Identifier: BoneParents


--------------------------------------------------------
Object [0004] - Component Count:    1 - Identifier: PlaceholderMeshName_submesh
	Component [0000] - Property Count:   13 - Identifier: MeshInfo
		Property [0028] - Identifier: MaterialCrc
		Property [0029] - Identifier: MaterialName
		Property [0030] - Identifier: BBoxCenter
		Property [0031] - Identifier: BBoxExtents
		Property [0032] - Identifier: NumWeights
		Property [0033] - Identifier: LightmapUVIndex
		Property [0034] - Identifier: SubmeshNameCrc
		Property [0035] - Identifier: SubmeshName
		Property [0036] - Identifier: UniqueSubmeshNameCrc
		Property [0037] - Identifier: UniqueSubmeshName
		Property [0038] - Identifier: InteriorFaces
		Property [0039] - Identifier: NumBones
		Property [0040] - Identifier: BonePalette


--------------------------------------------------------
Object [0005] - Component Count:   13 - Identifier: PlaceholderMeshName_submesh
	Component [0000] - Property Count:    7 - Identifier: GeometryInfo
		Property [0041] - Identifier: NumVerts
		Property [0042] - Identifier: PrimitiveType
		Property [0043] - Identifier: NumPrimitives
		Property [0044] - Identifier: ives
		Property [0045] - Identifier: VertexFormat
		Property [0046] - Identifier: NumVertexElements
		Property [0047] - Identifier: NumVertexBuffers
	Component [0001] - Property Count:    5 - Identifier: Indices
		Property [0048] - Identifier: NumIndices                                       // // 0x12C38
		Property [0049] - Identifier: MinVertexIndex
		Property [0050] - Identifier: NumVertexIndices
		Property [0051] - Identifier: StartIndex
		Property [0052] - Identifier: IndexData
	Component [0002] - Property Count:    4 - Identifier: Stream0
		Property [0053] - Identifier: VertexData
		Property [0054] - Identifier: VertexStride
		Property [0055] - Identifier: NumBufferVerts
		Property [0056] - Identifier: VertexFlags
	Component [0003] - Property Count:    4 - Identifier: Stream1
		Property [0057] - Identifier: VertexData
		Property [0058] - Identifier: VertexStride
		Property [0059] - Identifier: NumBufferVerts
		Property [0060] - Identifier: VertexFlags
	Component [0004] - Property Count:    6 - Identifier: VertexDecl
		Property [0061] - Identifier: Stream
		Property [0062] - Identifier: Offset
		Property [0063] - Identifier: Type
		Property [0064] - Identifier: Method
		Property [0065] - Identifier: Usage
		Property [0066] - Identifier: UsageIndex
	Component [0005] - Property Count:    6 - Identifier: VertexDecl
		Property [0067] - Identifier: Stream
		Property [0068] - Identifier: Offset
		Property [0069] - Identifier: Type
		Property [0070] - Identifier: Method
		Property [0071] - Identifier: Usage
		Property [0072] - Identifier: UsageIndex
	Component [0006] - Property Count:    6 - Identifier: VertexDecl
		Property [0073] - Identifier: Stream
		Property [0074] - Identifier: Offset
		Property [0075] - Identifier: Type
		Property [0076] - Identifier: Method
		Property [0077] - Identifier: Usage
		Property [0078] - Identifier: UsageIndex
	Component [0007] - Property Count:    6 - Identifier: VertexDecl
		Property [0079] - Identifier: Stream
		Property [0080] - Identifier: Offset
		Property [0081] - Identifier: Type
		Property [0082] - Identifier: Method
		Property [0083] - Identifier: Usage
		Property [0084] - Identifier: UsageIndex
	Component [0008] - Property Count:    6 - Identifier: VertexDecl
		Property [0085] - Identifier: Stream
		Property [0086] - Identifier: Offset
		Property [0087] - Identifier: Type
		Property [0088] - Identifier: Method
		Property [0089] - Identifier: Usage
		Property [0090] - Identifier: UsageIndex
	Component [0009] - Property Count:    6 - Identifier: VertexDecl
		Property [0091] - Identifier: Stream
		Property [0092] - Identifier: Offset
		Property [0093] - Identifier: Type
		Property [0094] - Identifier: Method
		Property [0095] - Identifier: Usage
		Property [0096] - Identifier: UsageIndex
	Component [0010] - Property Count:    6 - Identifier: VertexDecl
		Property [0097] - Identifier: Stream
		Property [0098] - Identifier: Offset
		Property [0099] - Identifier: Type
		Property [0100] - Identifier: Method
		Property [0101] - Identifier: Usage
		Property [0102] - Identifier: UsageIndex
	Component [0011] - Property Count:    6 - Identifier: VertexDecl
		Property [0103] - Identifier: Stream
		Property [0104] - Identifier: Offset
		Property [0105] - Identifier: Type
		Property [0106] - Identifier: Method
		Property [0107] - Identifier: Usage
		Property [0108] - Identifier: UsageIndex
	Component [0012] - Property Count:    6 - Identifier: VertexDecl
		Property [0109] - Identifier: Stream
		Property [0110] - Identifier: Offset
		Property [0111] - Identifier: Type
		Property [0112] - Identifier: Method
		Property [0113] - Identifier: Usage
		Property [0114] - Identifier: UsageIndex


--------------------------------------------------------
Object [0006] - Component Count:    1 - Identifier: PlaceholderMeshName_submesh
	Component [0000] - Property Count:   13 - Identifier: MeshInfo
		Property [0115] - Identifier: MaterialCrc
		Property [0116] - Identifier: MaterialName
		Property [0117] - Identifier: BBoxCenter
		Property [0118] - Identifier: BBoxExtents
		Property [0119] - Identifier: NumWeights
		Property [0120] - Identifier: LightmapUVIndex
		Property [0121] - Identifier: SubmeshNameCrc
		Property [0122] - Identifier: SubmeshName
		Property [0123] - Identifier: UniqueSubmeshNameCrc
		Property [0124] - Identifier: UniqueSubmeshName
		Property [0125] - Identifier: InteriorFaces
		Property [0126] - Identifier: NumBones
		Property [0127] - Identifier: BonePalette


--------------------------------------------------------
Object [0007] - Component Count:   13 - Identifier: PlaceholderMeshName_submesh
	Component [0000] - Property Count:    7 - Identifier: GeometryInfo
		Property [0128] - Identifier: NumVerts
		Property [0129] - Identifier: PrimitiveType
		Property [0130] - Identifier: NumPrimitives
		Property [0131] - Identifier: ives
		Property [0132] - Identifier: VertexFormat
		Property [0133] - Identifier: NumVertexElements
		Property [0134] - Identifier: NumVertexBuffers
	Component [0001] - Property Count:    5 - Identifier: Indices
		Property [0135] - Identifier: NumIndices                                     // 0x54DBE
		Property [0136] - Identifier: MinVertexIndex
		Property [0137] - Identifier: NumVertexIndices
		Property [0138] - Identifier: StartIndex
		Property [0139] - Identifier: IndexData
	Component [0002] - Property Count:    4 - Identifier: Stream0
		Property [0140] - Identifier: VertexData
		Property [0141] - Identifier: VertexStride
		Property [0142] - Identifier: NumBufferVerts
		Property [0143] - Identifier: VertexFlags
	Component [0003] - Property Count:    4 - Identifier: Stream1
		Property [0144] - Identifier: VertexData
		Property [0145] - Identifier: VertexStride
		Property [0146] - Identifier: NumBufferVerts
		Property [0147] - Identifier: VertexFlags
	Component [0004] - Property Count:    6 - Identifier: VertexDecl
		Property [0148] - Identifier: Stream
		Property [0149] - Identifier: Offset
		Property [0150] - Identifier: Type
		Property [0151] - Identifier: Method
		Property [0152] - Identifier: Usage
		Property [0153] - Identifier: UsageIndex
	Component [0005] - Property Count:    6 - Identifier: VertexDecl
		Property [0154] - Identifier: Stream
		Property [0155] - Identifier: Offset
		Property [0156] - Identifier: Type
		Property [0157] - Identifier: Method
		Property [0158] - Identifier: Usage
		Property [0159] - Identifier: UsageIndex
	Component [0006] - Property Count:    6 - Identifier: VertexDecl
		Property [0160] - Identifier: Stream
		Property [0161] - Identifier: Offset
		Property [0162] - Identifier: Type
		Property [0163] - Identifier: Method
		Property [0164] - Identifier: Usage
		Property [0165] - Identifier: UsageIndex
	Component [0007] - Property Count:    6 - Identifier: VertexDecl
		Property [0166] - Identifier: Stream
		Property [0167] - Identifier: Offset
		Property [0168] - Identifier: Type
		Property [0169] - Identifier: Method
		Property [0170] - Identifier: Usage
		Property [0171] - Identifier: UsageIndex
	Component [0008] - Property Count:    6 - Identifier: VertexDecl
		Property [0172] - Identifier: Stream
		Property [0173] - Identifier: Offset
		Property [0174] - Identifier: Type
		Property [0175] - Identifier: Method
		Property [0176] - Identifier: Usage
		Property [0177] - Identifier: UsageIndex
	Component [0009] - Property Count:    6 - Identifier: VertexDecl
		Property [0178] - Identifier: Stream
		Property [0179] - Identifier: Offset
		Property [0180] - Identifier: Type
		Property [0181] - Identifier: Method
		Property [0182] - Identifier: Usage
		Property [0183] - Identifier: UsageIndex
	Component [0010] - Property Count:    6 - Identifier: VertexDecl
		Property [0184] - Identifier: Stream
		Property [0185] - Identifier: Offset
		Property [0186] - Identifier: Type
		Property [0187] - Identifier: Method
		Property [0188] - Identifier: Usage
		Property [0189] - Identifier: UsageIndex
	Component [0011] - Property Count:    6 - Identifier: VertexDecl
		Property [0190] - Identifier: Stream
		Property [0191] - Identifier: Offset
		Property [0192] - Identifier: Type
		Property [0193] - Identifier: Method
		Property [0194] - Identifier: Usage
		Property [0195] - Identifier: UsageIndex
	Component [0012] - Property Count:    6 - Identifier: VertexDecl
		Property [0196] - Identifier: Stream
		Property [0197] - Identifier: Offset
		Property [0198] - Identifier: Type
		Property [0199] - Identifier: Method
		Property [0200] - Identifier: Usage
		Property [0201] - Identifier: UsageIndex


--------------------------------------------------------
Object [0008] - Component Count:    0 - Identifier: ma_trooperStormClassic

```
## Post #27
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2009-12-21T21:49:38+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

I have posted a video that may help those who have had difficulty getting the script to work. You can find it on my blog: [http://uberblack3d.blogspot.com/search/ ... .UberBlack](http://uberblack3d.blogspot.com/search/label/Tutorials.UberBlack)

please post a message if this was helpful.

..|Ultra911|..
## Post #28
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2009-12-22T11:29:52+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

The contents of this post was deleted because of possible forum rules violation.
## Post #29
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2009-12-22T18:29:19+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

As I mentioned in the video, some models have more or less bones. this would effect the script. What I need is someone to step up and fix this script so it can be automated. for the Felucian Warrior to work, you must comment out:

--boneweight4 = readlong f
--boneweight5 = readlong f

Then it will import correctly. All meshes seem to work with this method. I don't know enough about Max to make these offsets automatic. Also the bones and Animation seem very straightforward to implement and I would like someone to help finish off support. 

..|Ultra911|..
## Post #30
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-12-22T19:22:41+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

i will attempt to look into some max script references when i get the chance and see if i can update the script accordingly.  i am a programmer, not an artist so i don't usually have a direct need for importers, but i will see what i can do if no one else beats me to it.  if there are any others more accustomed to max script than i currently am, the information i posted above should be enough to read the entire format correctly.  i am still looking into the unknown values, but so far i have not needed them to interpret the data, will have to see if that holds true.
## Post #31
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2009-12-22T21:32:35+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Any help would be great!

..|Ultra911|..
## Post #32
- Username: melechdude
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 24, 2009 4:58 am
- Post datetime: 2010-01-09T06:43:59+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

so is there any news with this?

or did it die...
## Post #33
- Username: reappper
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 11, 2010 8:03 am
- Post datetime: 2010-01-13T00:49:31+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

so whats the news about the project?

I mean can we now mod the force unleashed?

I really would love the models from tfu....

I hope its not dead any body?
## Post #34
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-01-13T01:52:14+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Things are not dead, i just haven't had time to look into the conversion to max script yet.  Reading the format is not an issue as like i said, i listed how everything works above.  just that i don't normally need art import support, so i don't currently have a code path in place that allows it to be done.  Once i get some time i will look into what i can do in that regard.
## Post #35
- Username: rogueclarkey
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 22, 2008 11:01 pm
- Post datetime: 2010-01-18T13:24:30+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Hi All,

Just thought I'd post my findings so far. I'm interested in the animation data format which seem to be held in the .animations files. No surprise there 

I wrote a some code over the weekend to try and extract the key data, but can't quite get there.

I got the data from [http://www.zshare.net/download/6802877050e22834/](http://www.zshare.net/download/6802877050e22834/) and once I decompressed the lp file with quickbms I found the animations in Scum\animation\characters\PCDX\MaleAverage\Player\navigation.

I think I've managed to get the overall structure right, but I've not managed to extract any keyframe data for translations or rotations.

I hope some finds this useful and can help me get the key data.

[Noob disclaimer - I've never tried this before and I'm guessing about the entire format so best not to assume I've got anything correct  ]

```

typedef unsigned char uint8;
typedef unsigned short uint16;
typedef unsigned long uint32;

typedef char int8;
typedef short int16;
typedef long int32;

struct R2D2PACK_HEADER
{
	uint8 id[8];
	uint32 unknown0x04;
	uint32 size;
};

struct PACK_HEADER
{
	uint8 id[4];
	uint8 unknown0x04[20];
	uint32 size;
	uint32 intNumber;
};

struct R2D2MULT_HEADER
{
	uint8 id[8];
	uint32 unknown0x04;
	uint32 size;
};

struct MINA_HEADER
{
	uint8 id[4];				// 0x0
	uint8 unknown0x04[16];		// 0x04
	uint32 numBones;			// 0x14
	float floatNumber;			// 0x18
	uint8 unknown0x1C[20];		// 0x1c
	uint32 boneDataSize;		// 0x30
	uint32 size1;				// 0x34
	uint32 unknown0x38;			// 0x38
	uint32 size2;				// 0x3C
};

struct BONE_INFO
{
	uint32 boneCRC;
	uint32 unknown0x04;
	uint32 offset;
	uint16 numKeys;
	uint16 unknown0x0E;
};


void main(int argc, char* argv[])
{
	char* pAnimName = "player_ma_nav_airdash_start";
	char fullPath[256];

	sprintf(fullPath, "%s.animations", pAnimName);

	FILE* pAnimFile = fopen(fullPath, "rb");
	FILE *pAnimExportFile = fopen("anim.txt", "w");

	if(pAnimFile && pAnimExportFile)
	{
		// file size
		fseek(pAnimFile, 0, SEEK_END);
		int fileSize = ftell(pAnimFile);
		fseek(pAnimFile, 0, SEEK_SET);
		fprintf(pAnimExportFile, "fileSize: %d\n", fileSize);

		// R2D2PACK header
		R2D2PACK_HEADER r2d2packHeader;
		fread(&r2d2packHeader, sizeof(R2D2PACK_HEADER), 1, pAnimFile);
		fprintf(pAnimExportFile, "%s\n", r2d2packHeader.id);
		fprintf(pAnimExportFile, "size: %d (fileSize - sizeof(R2D2PACK_HEADER)\n", r2d2packHeader.size);
		fprintf(pAnimExportFile, "\n");

		PACK_HEADER packHeader;
		fread(&packHeader, sizeof(PACK_HEADER), 1, pAnimFile);
		fprintf(pAnimExportFile, "%s\n", packHeader.id);
		fprintf(pAnimExportFile, "size: %d (fileSize)\n", packHeader.size);
		fprintf(pAnimExportFile, "int number: %d\n", packHeader.intNumber);
		fprintf(pAnimExportFile, "\n");


		// R2D2MULT header
		R2D2MULT_HEADER r2d2multHeader;
		fread(&r2d2multHeader, sizeof(R2D2MULT_HEADER), 1, pAnimFile);
		fprintf(pAnimExportFile, "%s\n", r2d2multHeader.id);
		fprintf(pAnimExportFile, "size: %d (fileSize - %d)\n", r2d2multHeader.size, fileSize - r2d2multHeader.size);
		fprintf(pAnimExportFile, "\n");
		
		// MINA header
		MINA_HEADER minaHeader;
		fread(&minaHeader, sizeof(MINA_HEADER), 1, pAnimFile);
		fprintf(pAnimExportFile, "%s\n", minaHeader.id);
		fprintf(pAnimExportFile, "numBones+1: %d\n", minaHeader.numBones);
		fprintf(pAnimExportFile, "float number (anim length?): %f\n", minaHeader.floatNumber);
		fprintf(pAnimExportFile, "\n");


		uint32 boneDataOffset = ftell(pAnimFile);
		fprintf(pAnimExportFile, "Bone Data - Offset: %d\n\n", boneDataOffset);

		uint32 boneInfoOffset = boneDataOffset+minaHeader.boneDataSize;
		fprintf(pAnimExportFile, "Bone Info - Offset: %d\n", boneInfoOffset);
		fseek(pAnimFile, boneInfoOffset, SEEK_SET);


		// BONE INFO

		uint32 lastOffset = 0;

		uint32 offsetTotal = 0;

		for(int boneIndex=0;boneIndex<minaHeader.numBones;boneIndex++)
		{
			BONE_INFO boneInfo;
			fread(&boneInfo, sizeof(BONE_INFO), 1, pAnimFile);

			fprintf(pAnimExportFile, "boneCRC: 0x%x\n", boneInfo.boneCRC);
			fprintf(pAnimExportFile, "offset: %d\n", boneInfo.offset);
			fprintf(pAnimExportFile, "numKeys?: %d\n", boneInfo.numKeys);

//			uint32 fileOffset = ftell(pAnimFile);
//			fseek(pAnimFile, boneDataOffset+boneInfo.offset, SEEK_SET);
			// hopefully the anim data for the bone is here...
//			fseek(pAnimFile, fileOffset, SEEK_SET);


			uint32 boneDataSize = boneInfo.offset - lastOffset;
			fprintf(pAnimExportFile, "previous bone data size: %d\n", boneDataSize);

			offsetTotal += boneInfo.offset - lastOffset;

			lastOffset = boneInfo.offset;


			fprintf(pAnimExportFile, "\n");
		}

		fprintf(pAnimExportFile, "offsetTotal: %d\n", offsetTotal);

		fclose(pAnimFile);
		fclose(pAnimExportFile);
	}
}

```
## Post #36
- Username: CeeX
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 22, 2010 9:45 am
- Post datetime: 2010-03-28T19:42:48+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Hello to all!

This is my first post on these forums and I actually joined the XeNTaX community to ask for help by making a request.

What I need help with is as this topic's title suggests, extracting a specific file from the game's archives. What I am looking for is the "Cybernetic Reconstruction" 3D model and it's textures.

I am not very knowledgeable about these reverse-engineering/HEX tweaking operations so it's nearly impossible for me to do this by myself...

So here I am, unsure that I'm even posting my request in the right place, asking someone to extract 2 files that I'll be able to open in a modeling program.

Thank you very much in advance!

Cheers
## Post #37
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-04-29T09:29:34+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Any chance for the sounds?
I found some sounds like tem_jeditemple_b.st.nv.pcp are RAW PCM (so maybe game can works with uncompressed audios), but normally the files are like "crypted" o compressed, looks the same header in a lot of files.
The compression ratio in Winrar it's 60-65% (not too bad) this indicates is not a dpcm (maybe i'm wrong in this) or mp3..(but who knows) can be a xma?

> C0 00 40 00 F0 00 00 00 02
[sounds.rar - 6.86MB](http://www.zshare.net/download/75506245a353ebd6/)
## Post #38
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-04-29T14:39:09+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

I tried to follow some hints from here [http://hcs64.com/mboard/forum.php?showt ... 8&lastpage](http://hcs64.com/mboard/forum.php?showthread=14818&lastpage)
But i failed..
## Post #39
- Username: reappper
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 11, 2010 8:03 am
- Post datetime: 2010-06-08T01:56:48+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

so hey has any one got some of the models out of the force unleashed or at least one a program that can?
## Post #40
- Username: Zerovisibilite
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 13, 2010 9:41 am
- Post datetime: 2010-06-13T11:12:44+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Ok, So I'm Brand spanking new here(as a registered user). I have taken some of the development that has been done here and moved forward with it. Using VB i was able to make an automated model extractor for this. It is still in the raw stage, but should be cleaned up enough to post a link in a short while.
## Post #41
- Username: Zerovisibilite
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 13, 2010 9:41 am
- Post datetime: 2010-06-14T16:03:26+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Ok, Her is the automated ripper. I used the BMS script above to get the GTO files then this program to ripp them into .obj. There are 2 radio buttons to select which bone weight to use 3 or 5. I have found that 3 works for most and for those that dont the 5 will work. It prompts for an export folder on first run, then never again unless you click change export folder.

Use the dds files that are ripped with the bms script above to skin the models when done.

Hope you enjoy

No credit necessary as all i did was take the maxscript(by the way is brilliant on how the face points are handled,Still having a wonder on why it works that way but, hey it works) and code it in vb and automate the front end. So if you thank anyone thank the above that paved the way
[TFU_GTO_Ripper.rar](https://xentaxbackup.github.io/file/3142_TFU_GTO_Ripper.rar)
## Post #42
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-15T17:27:29+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from Zerovisibilite
>
> Ok, Her is the automated ripper. I used the BMS script above to get the GTO files then this program to ripp them into .obj. There are 2 radio buttons to select which bone weight to use 3 or 5. I have found that 3 works for most and for those that dont the 5 will work. It prompts for an export folder on first run, then never again unless you click change export folder.

Use the dds files that are ripped with the bms script above to skin the models when done.

Hope you enjoy

No credit necessary as all i did was take the maxscript(by the way is brilliant on how the face points are handled,Still having a wonder on why it works that way but, hey it works) and code it in vb and automate the front end. So if you thank anyone thank the above that paved the way
You talking about weight data, but .obj format do not support bones. So how can i convert models with bones from .gto to my 3ds max?
## Post #43
- Username: Zerovisibilite
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 13, 2010 9:41 am
- Post datetime: 2010-06-15T19:14:22+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

The boneweight in the App is for placement of the typedata I used. It will not export bone weight or bones for that matter. Until I (or someone else) spends some time on the bone and animation stuff, t is what it is. Sorry
## Post #44
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-15T20:27:01+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from Zerovisibilite
>
> The boneweight in the App is for placement of the typedata I used. It will not export bone weight or bones for that matter. Until I (or someone else) spends some time on the bone and animation stuff, t is what it is. Sorry
 oh, it's to bad. But any way your tool it's great progress. I'll be waiting for support weight data and bones in your tool. Thank you
## Post #45
- Username: Zerovisibilite
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 13, 2010 9:41 am
- Post datetime: 2010-06-30T18:38:28+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Here is the latest Ripper. It auto finds the number of "Weights" for each verts segment. Exports as one obj, however I cant figure out the Material assignments so that is still manual. IE the .mtl file is bogus and just a place holder. I am looking at a different format to export to that will make the bones easier to attach but haven't had much time to play with it.
[TFU_GTO_Ripper.rar](https://xentaxbackup.github.io/file/3185_TFU_GTO_Ripper.rar)
## Post #46
- Username: Ryan7259
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 21, 2010 3:42 pm
- Post datetime: 2010-07-30T22:47:58+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

It's been a long time. Is there a new script? Whenever I use your gto converter and import the obj into max, the only part importable is the head. If I extract anything else it says something about bad vertex data.
## Post #47
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-08-07T00:18:22+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Why is it that the topic describes .z files, but the posts describe only .lp files?
## Post #48
- Username: Ryan7259
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 21, 2010 3:42 pm
- Post datetime: 2010-08-10T06:54:23+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

The contents of this post was deleted because of possible forum rules violation.
## Post #49
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2010-08-14T22:53:59+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from Ryan7259
>
> ...a certain model won't import. It only lets me import the head of the imperial officer...
You get a high poly head and eyes from ma_imperialOfficer.gto
The torso, arms and upper legs are in these lower poly files:
ma_imperialOfficer_LOD1.gto
ma_imperialOfficer_LOD2.gto
ma_imperialOfficer_LOD3.gto 
ma_imperialOfficer_LOD4.gto

Just combine the obj files produced from ma_imperialOfficer.gto and one of the LOD gto files in the same scene to get a near complete character.
The game probably pulls the hands and boots from another gto file elsewhere, maybe from an entirely different character.
## Post #50
- Username: darkmatter78
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jul 07, 2010 12:33 am
- Post datetime: 2010-08-15T03:10:32+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Please tell me why I am getting a syntax error when using this script.
## Post #51
- Username: deronar
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 04, 2010 10:27 pm
- Post datetime: 2010-09-08T07:42:52+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Hello
I have a problem with Star Wars - GTO files. I used TFU_GTO_Ripper but for some reason he does not work - the files that I received in obj corrupted.
Can somebody please write the process of extraction and tools that are used for models? Thanks
## Post #52
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2010-09-18T07:55:51+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

no update ???
the maxscript don't work, even the setting of the movie
the ripper give corrupted file ....

max detect bad vertex or size too small
## Post #53
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2010-10-03T04:01:19+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from CZW
>
> no update ???
the maxscript don't work, even the setting of the movie
the ripper give corrupted file ....

max detect bad vertex or size too small
There's really no need for an update unless someone finds a way to get bones and animations, everything else works great as-is. 
The maxscript although it was great when we had no other options is obsolete at this stage but I did test it out and it worked fine in 3ds Max 9, 3ds Max 2009 and 3ds Max 2010 but i don't know about other versions.
For the script you simply need to get the filepath correct, list all of the offsets and adjust the boneweights(if necessary) for each offset, the script must be run once for each offset. 

Zerovisibilite's latest [TFU_GTO_Ripper](http://forum.xentax.com/download/file.php?id=3185) works great and the resulting obj will import in 3ds Max without error if you use the default obj import:
## Post #54
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2010-10-03T21:07:31+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

test all yours infos ..
still don't work ..

try this file... and let me know if for you it's work ..

[http://www.filefactory.com/file/b3c8g10 ... nsport.rar](http://www.filefactory.com/file/b3c8g10/n/imperialTroopTransport.rar)
## Post #55
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2010-10-03T21:39:49+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

It works fine with the instruction i gave in my previous post, all objects and UVs are intact but like I said before if you are using a different version of 3ds Max then i can't confirm if your version imports properly or not, i am using 3ds Max 9 and the gto was converted to obj using Zerovisibilite's latest TFU_GTO_Ripper and was imported with the default obj import in 3ds Max. I don't know why it won't work for you.
## Post #56
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2010-10-03T22:09:21+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

i use 3Dmax 2010 32 bits under SEVEN ...
when i import it, i have a corrupted file on screen

i have PM you AceWell ..


edit :

a Big THX AceWell
## Post #57
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-10-03T23:58:10+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from CZW
>
> i use 3Dmax 2010 32 bits under SEVEN ...
when i import it, i have a corrupted file on screen

i have PM you AceWell ..


edit :

a Big THX AceWell
I think you need change "," to "." in your Regions and settings.
## Post #58
- Username: LunarYoshi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 05, 2010 6:47 am
- Post datetime: 2010-10-05T20:07:33+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Hello there,
First, thanks for all you've done so far.

Next, well, I must admit I followed AceWell instructions, and I still do have a problem.
What I've done :
- Download the last TFU_GTO_Ripper
- Use it to convert ImperialOfficer and Imperialtrooptransport gto files to obj files
- Import those .obj files into 3D Studio Max (9 and 2010, 32 bits under Win XP 32, using respectively default WaveFront .obj plugin, and Guruware .obj plugin)
- At this step, I obtain an ugly soup of vertices :
[http://img821.imageshack.us/img821/6636 ... alship.jpg](http://img821.imageshack.us/img821/6636/imperialship.jpg)
[http://img821.imageshack.us/img821/2820 ... fficer.jpg](http://img821.imageshack.us/img821/2820/imperialofficer.jpg)

So, I tried to export them back to .obj files from 3D Studio Max, and I compare the files. Of course, they're very different from the original ones...

Does anyone have a hint ?
Thank you guys.
## Post #59
- Username: Zerovisibilite
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 13, 2010 9:41 am
- Post datetime: 2010-10-05T22:46:01+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from LunarYoshi
>
> Hello there,
First, thanks for all you've done so far.

Next, well, I must admit I followed AceWell instructions, and I still do have a problem.
What I've done :
- Download the last TFU_GTO_Ripper
- Use it to convert ImperialOfficer and Imperialtrooptransport gto files to obj files
- Import those .obj files into 3D Studio Max (9 and 2010, 32 bits under Win XP 32, using respectively default WaveFront .obj plugin, and Guruware .obj plugin)
- At this step, I obtain an ugly soup of vertices :
http://img821.imageshack.us/img821/6636 ... alship.jpg
http://img821.imageshack.us/img821/2820 ... fficer.jpg

So, I tried to export them back to .obj files from 3D Studio Max, and I compare the files. Of course, they're very different from the original ones...

Does anyone have a hint ?
Thank you guys.

I Also tried the files you were requesting, Oddly enough I got different results than both of you. i am curious on why, However do not really have the time nor energy to investigate it, I have completely revamped the way it finds models and therefore this all is a moot point. Here is the "Latest" ripper, Again until I get the bones exporting, its really kind of a waste anyway
[TFU_GTO_Ripper.rar](https://xentaxbackup.github.io/file/3500_TFU_GTO_Ripper.rar)
## Post #60
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-10-05T23:54:40+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from LunarYoshi
>
> Hello there,
First, thanks for all you've done so far.

Next, well, I must admit I followed AceWell instructions, and I still do have a problem.
What I've done :
- Download the last TFU_GTO_Ripper
- Use it to convert ImperialOfficer and Imperialtrooptransport gto files to obj files
- Import those .obj files into 3D Studio Max (9 and 2010, 32 bits under Win XP 32, using respectively default WaveFront .obj plugin, and Guruware .obj plugin)
- At this step, I obtain an ugly soup of vertices :
http://img821.imageshack.us/img821/6636 ... alship.jpg
http://img821.imageshack.us/img821/2820 ... fficer.jpg

So, I tried to export them back to .obj files from 3D Studio Max, and I compare the files. Of course, they're very different from the original ones...

Does anyone have a hint ?
Thank you guys.I think you need change "," to "." in your Regions and settings to.
## Post #61
- Username: LunarYoshi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 05, 2010 6:47 am
- Post datetime: 2010-10-06T00:02:08+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Thank you Zerovisibilite for your new and latest GTO Ripper.
However, after a quick try with the above mentioned files, I still got the same results.

Maybe AceWell has a magic trick when importing into 3D Studio Max ?

Edit :
@Tosyk => I am not an advanced user of 3D Studio, so couldn't find this setting   
However, I replace each "," by a "." in the .obj files, and tried to import them afterwards. It worked for both models !   
But to my credit, I might add I'd already tried that trick the first time (with the old new GTO Ripper), and it failed then.

Thanks for pointing up that tip again
## Post #62
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-10-06T04:11:46+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from LunarYoshi
>
> @Tosyk => I am not an advanced user of 3D Studio, so couldn't find this setting
No, i'm talking about your windows!    Control Panel -> Regions and settings -> Additional Settings (bottom button).

p.s.: sorry my window is Russian, so i can make a little mistake
## Post #63
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2010-10-06T07:56:12+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

HI all

thx for screenshot, that's exactly what i have..
when i read your trick, i think the ripper use our regionnal setting and alterate the file ...
but i have try to change them after convert the model to obj, without chance...
same results ..

i will redo the rip with setting allready change and see if now the model is correct as soon as i'm back home

i will test your info 

> Reply from LunarYoshi
>
> 
However, I replace each "," by a "." in the .obj files, and tried to import them afterwards. It worked for both models !
## Post #64
- Username: LunarYoshi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 05, 2010 6:47 am
- Post datetime: 2010-10-06T12:05:02+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Ok Tosyk, I could finally understand what was happening.

In the Regional Settings of Windows, the Decimal separator must be set to "." instead of "," so that, when one use the GTO Ripper, data in OBJ files are written with "." (ie "1.32" instead of "1,32").
Thus, when importing into 3D Studio Max, the import plugin correctly recognize "1.32" as a float number, which is not the case for "1,32".

That explains why :
- Using the GTO ripper THEN changing the Regional Settings does not work
- Replacing all "," by "." in the OBJ files does work

Once again, thank you all for your help
## Post #65
- Username: lark125
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 10, 2010 6:08 pm
- Post datetime: 2010-10-10T18:09:31+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

hey i new to this forum but i have succesfully importet some models in 3ds max but has anybody figured out how to get the bones in 3ds max because i realy want to rig him???
## Post #66
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-10-10T18:23:04+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from lark125
>
> hey i new to this forum but i have succesfully importet some models in 3ds max but has anybody figured out how to get the bones in 3ds max because i realy want to rig him???
It's not possible for now, maybe in the future.
## Post #67
- Username: lark125
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 10, 2010 6:08 pm
- Post datetime: 2010-10-11T06:14:44+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

alright thanks for replying
## Post #68
- Username: reappper
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 11, 2010 8:03 am
- Post datetime: 2010-10-15T18:40:45+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

ok so is there way to get the models out or has that been done already?
## Post #69
- Username: lark125
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 10, 2010 6:08 pm
- Post datetime: 2010-10-17T10:13:15+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

yes that is already done now only the bonnes to rig
## Post #70
- Username: reappper
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 11, 2010 8:03 am
- Post datetime: 2010-10-19T15:44:26+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

coooool I'll just wait for it to be done this is soooooooooooooooo cooooool
## Post #71
- Username: lark125
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Oct 10, 2010 6:08 pm
- Post datetime: 2010-10-20T20:23:58+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

dus anybody know how to import in to 3ds max the .material files for the textures
## Post #72
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-10-25T16:06:23+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

I created a small tool based on quickbms by Luigi Auriemma for extracting all files from SWTFU *.lp containers into one folder.
You can download it on [my blog](http://cg.forexperts.ru/2010/10/star-wars-tfu-lp-bms-unpacker-exe/) by clicking on Скачать bms unpacker (exe)

how to use:
- copy bms_unpacker_swtfu.exe into the root directory of the game (where SWTFU.exe is)
- launch
- wait (there are many duplicate files in each *.lp container, so be patient)
- after the extracting process is finished, go to <game dir>\LevelPacks\output all the extracted files will be there

note: during the unpacking process quickbms.exe will ask you to rename several files, so just rename them and press Return.

p.s.: anyway, all thanks going to Luigi
## Post #73
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2010-10-26T12:36:01+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from Tosyk
>
> I created a small tool based on quickbms by Luigi Auriemma for extracting all files from SWTFU *.lp containers into one folder.
You can download it on my blog by clicking on Скачать bms unpacker (exe)

how to use:
- copy bms_unpacker_swtfu.exe into the root directory of the game (where SWTFU.exe is)
- launch
- wait (there are many duplicate files in each *.lp container, so be patient)
- after the extracting process is finished, go to <game dir>\LevelPacks\output all the extracted files will be there

note: during the unpacking process quickbms.exe will ask you to rename several files, so just rename them and press Return.

p.s.: anyway, all thanks going to Luigi

big thx man ...
i appreciated ..
## Post #74
- Username: darkmatter78
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jul 07, 2010 12:33 am
- Post datetime: 2010-11-13T23:54:28+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from Zerovisibilite
>
>  Again until I get the bones exporting, its really kind of a waste anyway

100% wrong. I learned how to rig, even with a lousy biped only, with your tool's help getting the models. So BIG thank you and fantastic work. I have spread your file and name around as you deserve many thanks.
## Post #75
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-11-21T20:04:49+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

I wanna translate the game, how can I do it?
## Post #76
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-27T02:24:09+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

I give this topic 2 thumbs up.

[thumbs up.png](https://xentaxbackup.github.io/file/3722_thumbs up.png)
## Post #77
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2010-12-27T05:36:06+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

It's been a long time on this.. Thanks so much Chrrox for this awesome Christmas present. Now the work begins
## Post #78
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2010-12-27T09:05:42+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

[](http://img193.imageshack.us/i/udkmaterialtest0001.png/)

Doing some quick material tests in UDK. I hope you guys like it..
## Post #79
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2010-12-27T09:05:58+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

[](http://img543.imageshack.us/i/mayameshtest001.png/)

Quick Render in Maya
## Post #80
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2010-12-27T18:42:07+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Awesome chroxx , thanks.
## Post #81
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-12-27T20:50:54+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

The contents of this post was deleted because of possible forum rules violation.
## Post #82
- Username: Zerovisibilite
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 13, 2010 9:41 am
- Post datetime: 2010-12-27T21:20:41+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Did you guys get the bones straightened out? If so are you using a max script?
## Post #83
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-27T21:47:33+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

I have everything about the format I just need to find a way to seek to the offsets other then manually setting them.
## Post #84
- Username: Zerovisibilite
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 13, 2010 9:41 am
- Post datetime: 2010-12-27T21:56:27+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

If you want I cam send you the code that I used for the ripper. it's in vb6. Worse case you can open it in a text editor and use it for  reference. or i can write an extractor that will dump the raw stuff you need without all the garbage that you dont.
## Post #85
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-27T22:20:42+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

that might help but using the search method you posted wont work to get meshes with bones and weights because the bone id's used in each mesh start before that data in each mesh section and vary in size.
## Post #86
- Username: Zerovisibilite
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 13, 2010 9:41 am
- Post datetime: 2010-12-27T23:01:09+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Shoot me a PM with some offsets and a specific file so i can see where they start and how they relate to the beginning of the mesh data. There has to be a relationship or something distinct as a header
## Post #87
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-28T00:45:22+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

use any file i just need to get to 00 00 00 FF FF FF FF at the start of each mesh section
in reality i could search for this offset its not idea but i could.
But i also need to get to the start of the matrix values that is more important.
## Post #88
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-01-04T21:31:42+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

The contents of this post was deleted because of possible forum rules violation.
[Blender249[StarWarsTheForceUnleashed][PC][gto][2011-01-17].zip](https://xentaxbackup.github.io/file/8319_Blender249[StarWarsTheForceUnleashed][PC][gto][2011-01-17].zip)
## Post #89
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2011-01-05T14:42:59+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Thank you very much, it's a great gift Szkaradek123! You are a true master, thank you very much for your  blender importers!
## Post #90
- Username: Ryan7259
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 21, 2010 3:42 pm
- Post datetime: 2011-01-16T04:56:16+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Doesn't work when I export to max 2011. It comes out as a mess of wires and bones sitting right into each other pointing upward. I already set my list separator(can't find anything else that says decimal separator) to . instead of ,
## Post #91
- Username: reappper
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 11, 2010 8:03 am
- Post datetime: 2011-01-28T23:14:52+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

so is the tool ready? can we now take models out of tfu????
## Post #92
- Username: reappper
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 11, 2010 8:03 am
- Post datetime: 2011-01-29T02:13:53+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

any body? so is the tool ready yet? and be so kind as to tell how to use it too
## Post #93
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-01-29T02:26:35+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from reappper
>
> any body? so is the tool ready yet? and be so kind as to tell how to use it too
Yes, in [this post](http://forum.xentax.com/viewtopic.php?p=46921#p46921).

And please, don't dubleposting here.

> Reply from Szkaradek123
>
> Blender importer for models from Star Wars The Force Unleashed .
(Blender 249 and Python 2.6.)
Hi, Szkaradek123. Please tell me more detail how to automatically apply textures, because when i jointing (ctrl+J, maybe?) all objects and then importing in 3ds max (trough the psk), i gets only one material.
## Post #94
- Username: reappper
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 11, 2010 8:03 am
- Post datetime: 2011-01-29T23:25:09+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

ok so I manage to get the models out of tfu now have we work on getting the rigs out? like the bones?
## Post #95
- Username: Ryan7259
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 21, 2010 3:42 pm
- Post datetime: 2011-01-30T07:39:20+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

You wait for the experts to make a script.
## Post #96
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2011-02-01T16:50:38+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

I am posting this link because I have had many requests for the tutorial I have made about extracting a Storm Trooper from Star Wars The Force Unleashed. Your suggestions and comments would be greatly appreciated.

[http://uberblack3d.com/articles/storm-t ... -tutorial/](http://uberblack3d.com/articles/storm-trooper-classic-tutorial/)
## Post #97
- Username: reappper
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 11, 2010 8:03 am
- Post datetime: 2011-06-15T00:15:36+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

so is this project dead or what? have we finally got bones no?? tired of waiting
## Post #98
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2012-03-20T22:49:11+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

The Force Unleashed plugin for Noesis has been updated: [http://oasis.xentax.com/index.php?content=plugins](http://oasis.xentax.com/index.php?content=plugins)

Fixes a bug with gto models and adds support for the .animations files.

If i get the chance i will try and put together documentation to supplement rogueclarkey's description earlier in the thread.

Have fun.
## Post #99
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-03-20T23:56:42+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from revelation
>
> The Force Unleashed plugin for Noesis has been updatedthank you revelation
## Post #100
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2012-03-21T00:16:31+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from revelation
>
> The Force Unleashed plugin for Noesis has been updated: http://oasis.xentax.com/index.php?content=plugins

Fixes a bug with gto models and adds support for the .animations files.

If i get the chance i will try and put together documentation to supplement rogueclarkey's description earlier in the thread.

Have fun.

It's been a long time coming.. thanks for letting me test it.
## Post #101
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2012-06-07T23:41:50+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Well i was asked about how to interpret the information within the .animations file, and i had not gotten around to coming back to this thread, so i guess i shal do a quick and dirty explaination of things.  Hopefully it will be enough to get those interested started in looking into the data (assuming i can express it clearly enough).

The animations files are structured into the following sections:

```
DATA
-JOINT_KEYFRAME_DATA
-JOINT_KEYFRAME_INFO
-JOINT_KEYFRAME_INDICES
-NAME_DATA

```


The HEADERS section can consist of up to 4 different headers:

```
{
	// 0x00
	char   fileTag[8]   <format = hex>; // 'R2D2pack'
	uint32 fileVersion;
	uint32 dataSize     <format = hex>;
	// 0x10
};

struct PACK_HEADER
{
	// 0x00
	uint32 dataTag           <format = hex>; // 'pack'
	uint32 unknown0x14[2]    <format = hex>; // [1] resource crc
	uint32 dataFlags         <format = hex>;
	// 0x10
	uint32 unknown0x20[4]    <format = hex>;
	// 0x20
};

struct R2D2mult_HEADER
{
	// 0x00
	char   fileTag[8]   <format = hex>; // 'R2D2mult'
	uint32 fileVersion;
	uint32 dataSize     <format = hex>;
	// 0x10
};

struct ANIM_HEADER
{
	// 0x00
	uint32 dataTag           <format = hex>; // 'mina'
	uint32 unknown0x04[3]    <format = hex>; // [1] resource crc
	// 0x10
	uint32 unknown0x10       <format = hex>;
	uint32 jointCount;
	float  duration;
	uint32 unknown0x1C       <format = hex>;
	// 0x20
	uint32 unknown0x20       <format = hex>;
	uint32 unknownSize0x24   <format = hex>; // sub-header/data alignment size?
	uint32 dataSize          <format = hex>; // animation name offset?
	uint32 unknown0x2C       <format = hex>;
	// 0x30
	uint32 jointInfoOffset   <format = hex>; // joint data?
	uint32 jointFramesOffset <format = hex>; // keyframe data?
	uint32 unknownSize0x38   <format = hex>; // base data offset?
	uint32 nameOffset        <format = hex>; // name offset?
	// 0x40
};

```


The PACK_HEADER follows the R2D2pack header if it is present.

The ANIM_HEADER follows the R2D2mult header.

The data sizes in the R2D2pack and R2D2mult headers is used to access the name strings in a slightly peculiar way in the code.  Using the the values starting from the begining of the data blocks that follow these headers actually takes you to the end of the string.  But if you read the byte prior to this point, add 2, and subtract it from this end offset you can obtain an offset to the beginning of the string that specifies the name of the animations file and the animation pack file (.r2a) respectively.

The ANIM_HEADER is treated as somewhat of a split data structure in the code, the second portion starting at the location of the unknownSize0x24 value.  This value contains an offset from this point to the beginning of the data section that follows.  In all of the files i have investigated so far this has always been 0x1C, but my assumption is that the data section may have alignment requirements (on a 32-byte boundary?) and this value would contain the offset to the aligned position of the data should it not follow directly after the ANIM_HEADER.  But for the most part i have not seen this needed, so i mention it solely to be complete.

The ANIM_HEADER jointInfoOffet and jointFramesOffset are relative to the beginning of the JOINT_KEYFRAME_DATA that follows the header.

The layout of the JOINT_KEYFRAME_DATA relies heavily on the flags specified in the JOINT_KEYFRAME_INFO structure that follows it, as does the JOINT_KEYFRAME_INDICEIS.  So i will describe that first:

```
{
	// 0x00
	uint32 jointHash    <format = hex>; // crc
	uint32 framesOffset <format = hex>; // keyframe indices?
	uint32 dataOffset   <format = hex>;
	uint16 framesCount  <format = hex>;
	uint16 formatFlags  <format = hex>; // flags?
	// 0x10
};

```


This section is a list of ANIM_HEADER.jointCount structure that define the data layout of each joints keyframe data and indices.  Joints do not have to be present for every one that is in the model file.  Since the animation it initialized with the base pose transforms, these joint will just not be modified.

The framesOffset and dataOffset values are relative to the JOINT_KEYFRAME_INDICES and JOINT_KEYFRAME_DATA sections respectively.  The jointHash is a simple crc value based on the actual joint name from the model file.

The real important piece of information in this structure are the formatFlags.  They specify whether or not the keyframe data is bit packed or not, whether it is 32-bit floats or 16-bit short values, whether position or rotation data is even present, which components of the position and rotation are valid, as well as what form the keyframe indices are in (8-bit byte, 16-bit short, 32-bit float).

The formatFlags can be assumed to have this format:

```
{
	// 0x00
	uint16 flags;
	struct
	{
		uint16 posLayout : 3;
		uint16 posFlag   : 1;
		uint16 rotLayout : 3;
		uint16 rotFlag   : 1;
		
		uint16 dataFlag  : 2;
		uint16 rotFormat : 2;
		uint16 posFormat : 2;
		uint16 idxFormat : 2;
	};
	// 0x02
};

```


The idxFormat determines the data size of the individual elements of the joints keyframe indices and can have the following values:

```
2 - 16-bit frame index
else - 32-bit float frame time (in seconds)

```


Animations are 30 frames per second, so for the non-float frame index values simply divide by 30 to get the float time in seconds, or the reverse by multiplying the float frame times by 30 to get the fram index.

The posFormat and rotFormat specify the data type of the position and roation values (if present):

```
2 - 32-bit float data
1 - 16-bit short data

```


16-bit data values are normalized by dividing by 32767.

The dataFlag specifies if position, rotation, or both of them are present:

```
2 - rotation data present
1 - position data present

```


The rotFlag and posFlag specify how to interpres the rotLayout and posLayout respectively;

```
1 - the Layout values are treated as a 3-bit mask for each of the x,y,z components to determine which of them are present in the data

```


When the rotFlag or posFlag bits are not set (0) then the respective Layout values can be:

```
2 - (3) 16-bit short values (x,y,z)
1 - (3) 32-bit float values (x,y,z) - NOTE: when the dataFlag specifies rotations are present and the rotLayout is also 32-bit float, an extra float for the w component is present for alignment purposes.

rotLayout:
3 - (3) 16-bit short values (x,y,z) -> w = 1 - sqrt(x^2 + y^2 + z^2)
2 - (4) 16-bit short values (x,y,z,w)
1 - (4) 32-bit float values (x,y,z,w)

```


The Layout values should match the Format values for their respective components.

When the rotFlag or posFlag are set the rotLayout and posLayout are 3 separate bit values each for the x, y, and/or z component that is present in the data.

```
210
xyz

```


With 0 being the least significant bit, etc.

When data is bit-packed the rot- and pos- Flag bits should be set if the dataFlag specifies they are present.

Reading the data from the JOINT_KEYFRAME_DATA section requires the information above.  When the data is not bit-packed the process if fairly straight forward.  Rotation and position components are packed ones after the other: pos0,rot0,pos1,rot1,...etc.  Assuming the dataFlag specifies they are present.

The skeleton for an animation is initialized using the base pose information from the model.  If data is not specified for a joint based on the flags information, then the values are not overwritten during processing.


- Bit Packed Data -

Bit-packed data complicates things slightly as the data is tightly packed into a big-ending ordered bit stream, where the components of the position and rotation components can be variable bit sizes which are specified in the data itself.

If position data is present the first 4 bytes are a 32-bit floating point scaling value for the position information.

Following this are up to (18) bytes of data used to specify the base values and bit-sizes for the position and rotation xyz components.  The presence of these values is controlled by the xyz bits in the posLayout and rotLayout respectively.

The values are used to specify the base values and bit sizes of each component of the position and rotation values.

The order is as follows:

```

```


These are specified for both the position and rotation data if specified as present.  The 'base' values are 16-bits each, the 'bitSize' values are 8-bits each (3 * 2-bytes + 3 * 1-byte == up to 9 bytes each for position and rotation == up to 18-bytes).

The individial components will not be present if the corresponding bit is not set in the respective Layout values from the joint data flags.

So if bit 0 is not set for posLayout, then the z-component of the positions are not present (basePosX, basePosY, bitSizeX, bitSizeY).  The rotation values are handled in the same manner using the respective flags and format information.

Following this information is framesCount number of bit packed values for the components specified as being present.  The bit stream is read a big-endian data in x,y,z order for position then rotation for the compoents that are valid.  The bitSize values specify the number of bits to read for each component from the stream.

The final value for each component is calculated using the following function:

```

packedValue == value read from bit-stream
bitSize == bit size for the component being read
baseValue == base value for the component being read
valueScale == scale for the component type being read (for positions this is the 32-bit float at the beginning of the data, for rotations this is 1/32767 to normalize into the range 0...1)

```


All the values are treated as signed 16-bit values.

Since only 3 components of the rotation are specified the w value is found through standard normalized quaternion methods.



Well that was simply a brain dump of how to interpret the animation data.  i am not entirely sure if it will make sense to anyone as i have written it, so feel free to ask for clarification on anything if needed.

Hope it helps.
## Post #102
- Username: Hamster Jovial
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 20, 2012 7:43 am
- Post datetime: 2012-06-08T09:13:04+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Thanks a lot revelation
## Post #103
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2014-02-01T12:37:04+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from UberBlack
>
> 

Quick Render in Maya
quick question if thats ok how did you get it in a T-pose? when i import they are A-pose
## Post #104
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2015-08-15T23:59:16+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Hi, i want to translate game. How can i do this?
## Post #105
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2017-05-08T05:50:39+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

so we ever figure out how to edit the xml.z files?
## Post #106
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2017-05-11T03:55:42+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

bump
## Post #107
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2017-06-26T17:12:21+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

bump
## Post #108
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-27T02:36:00+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from iambosh
>
> so we ever figure out how to edit the xml.z files?
no, because:

> Reply from aluigi
>
> the correct script would be:
Code: Select allcomtype lzss
get SIZE long
get ZSIZE long
get DUMMY long
savepos OFFSET
filexor 0xff
clog "dump.dat" OFFSET ZSIZE SIZEbut can't work because the algorithm is not lzss, it's something else
## Post #109
- Username: darthvader23
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 25, 2018 12:00 am
- Post datetime: 2018-01-24T16:14:24+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Hello everyone, 

 I have been wondering if anyone in here is still active and might be able to refresh some new links for the Noesis 3D plugin for Force Unleashed or the other extractor that was created. I would like to try improve one model, but I can't find any of the links working anymore
## Post #110
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-06-11T00:57:29+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

[https://github.com/RoadTrain/noesis-plugins-official](https://github.com/RoadTrain/noesis-plugins-official)
Look under "revelation"
## Post #111
- Username: StrangeUsernames
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 09, 2020 11:34 am
- Post datetime: 2022-11-28T03:10:10+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Can someone reupload the noesis script? The link is down.
## Post #112
- Username: kaasly
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 29, 2022 3:07 pm
- Post datetime: 2023-08-15T05:49:20+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

> Reply from StrangeUsernames ↑Mon Nov 28, 2022 11:10 am at Mon Nov 28, 2022 11:10 am
>
> 
Can someone reupload the noesis script? The link is down.

Hi did you got the link?
## Post #113
- Username: StrangeUsernames
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 09, 2020 11:34 am
- Post datetime: 2023-10-07T14:32:28+00:00
- Post Title: Re: Star Wars The Force Unleashed - PC Version .z files

Yes I have it. Can't remember what this was for anyway, but I have this
< shared assets - link removed by moderator>

Also this forum is going down by the end of the year. 

You can add me on Discord: StarLord#1620
