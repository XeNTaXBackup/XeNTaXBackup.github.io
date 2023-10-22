## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:51:55+00:00
- Post Title: Basic BMS Scripting

Attention: This topic is subject to the Programming Section under the tutorial An Imitable Workflow for Reverse Engineering A Game Model.

Part I. Basic BMS Scripting

As you may or may not know, QuickBMS is an extremely powerful tool for archive unpacking. It's originally created by @aluigi and is now still under active development. 
[QuickBMS Homepage](http://quickbms.com)

This tutorial will not explain you the usage of the QuickBMS commands, because there's already been a highly detailed explanation in the QuickBMS document.

Instead, I'll list only the most frequently used commands here. And you have to read the usages of them in the doc.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:53:00+00:00
- Post Title: Basic BMS Scripting

The following division is not necessarily correct.

Controling Statements:

```
CleanExit
Append [Direction]

```

File Attributes Statements:

```
Endian Type [VAR]
ComType ALGO [Dict] [Dict_Size]

```

Searching and Jumping Statements:

```
GoTo Offset [FileNum] [Type]
Padding VAR [FileNum] [Base_OFF]

```

Reading Operations:

```
GetCT VAR Type Char [FileNum]
GetDString VAR length [FileNum]

```

Writing Operations:

```
Log Name Offset Size [FileNum] [Xsize]
Clog Name Offset Zsize Size [FileNum] [Xsize]

```

Mathematical/Assignment Operations:

```
XMath VAR INSTR
String VAR OP VAR
Set VAR [Type] VAR
SavePos VAR [FileNum]

```

File Accessing Statement:

```

```


Judgement Statement:

```
...
[Elif VAR COND VAR]
...
[Else]
...
EndIf

```

Circular Statements:

```
...
While VAR COND VAR

```

```
...
Next [VAR] [OP] [Value]

```
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:53:35+00:00
- Post Title: Basic BMS Scripting

If you've read all the usages of the above commands, we can start our demonstration now.

The game we're deaing with is still Marvel Avengers: Battle for Earth. But before we start writing our BMS script, we have to know the full structure of the
archive we're going to unpack. And this'is the overall format structure of the xpr archives from this game:

```

Long		0x534D5837/"SMX7"
Long		TexTableOffset
Long		TexTableSize
Long		kfDataSize
Long		RawTextureDataSize
Long		CompressionFlag(XMEMLZX Compressed)
Long		TexFileCount
Long		kfFileCount
Long		Magic("USER")
Long		xblockFileOffset
Long		xblockFileSize
Long		xblockFileNameOffset
Long		xblockFileUrnOffset
Long		Null
String		xblockFileName(Null-terminated)
String		xblockFileName(Padding to 0x10)

Bytes		xblockFile
{
	Long		CompressionFlag
	Long		UnzipSize
	Bytes		CompressedStream
}

Bytes		Padding(0x800)

for i = 0 < TexFileCount
{
	Long		Magic("TX2D")
	Long		TexInfoHeaderOffset(Relative)
	Long		TexInfoHeaderSize
	Long		TextureFilenameOffset(Relative)
	Long		TextureFilenameEndOffset(Relative)
}

Long		Null

for i = 0 < TexFileCount
{
	String		TextureFilename(Null-terminated)
	Byte		Null
}

for i = 0 < TexFileCount
{
	0x40-byte	TexInfoHeader
	{
		0x20-byte	Ignore
		Long		TextureDataOffset
		0x1C-byte	Ignore
	}
}

Bytes		Padding(0x800)

for i = 0 < kfFileCount
{
	Long		Magic("KFSQ", "KFMT", "SCNG")
	Long		kfDataOffset(Relative)
	Long		kfDataSize
	Long		kfFilenameOffset(Relative)
	Long		urnOffset(Relative)
}

Long		Null
 
for i = 0 < kfFileCount
{
	String		kfFilename(Null-terminated)
	String		urn(Null-terminated)
}

for i = 0 < kfFileCount
{
	Bytes		kfFile
	{
		Long		CompressionFlag
		Long		UnzipSize
		Bytes		CompressedStream
	}
}

Bytes		Padding(0x800)

for i = 0 < TexFileCount
{
	Bytes		RawTextureData
}

```
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:57:38+00:00
- Post Title: Basic BMS Scripting

The second step is to construct a simple algorithm for unpacking all the assets in the target archive:

1. read the variables from the file header;
2. locate to each chunk according to the above variables;
3. read the info table of each chunk;
4. extract all the assets in each chunk according to its coresponding info header.

Now let's translate this algorithm into a BMS script:

```
endian big  							# set global endianness to big-endian
comtype XMEMLZX						# specify used compression algorithm

### read the variables one by one ###
get TexTableOffset long				# offset to "TX2D" table
get TexTableSize long  				# size of "TX2D" table
get KfmDataSize long					# size of "KFSQ"/"KFMT"/"SCNG" assets
get RawTexDataSize long				# size of raw image data
get CompressionFlag long				# flag for compression
get TexFileCount long					# texture files count
get KfmFileCount long					# "KFSQ"/"KFMT"/"SCNG" files count
get Magic long							# "USER"
get xblockFileOffset long				# offset to xblock file
get xblockFileSize long				# size of xblock chunk
get xblockFilenameOffset long		# offset to filename of xblock

### handling xblock file ###
goto xblockFilenameOffset			# jump to the filename
getct xblockFilename string 0x2E	# read filename of xblock file, but skip the extension ".xblock"
string xblockFilename | \			# wipe the drive letter
string xblockFilename + ".xml"		# the xblock file is actually an XML document

goto xblockFileOffset				# jump to where xblock data starts
get CompressionFlag long			# xblock data is alway compressed
get UnzipSize long					# decompressed size of xblock file

savepos xblockFileOffset			# where compressed data begin
math xblockFileSize - 0x8			# CompressionFlag and UnzipSize took 8 bytes

## decompress the data and write it to file ##
clog xblockFilename xblockFileOffset xblockFileSize UnzipSize

### handling texture files ###
get TexDataOffset asize				# assign archive size to TexDataOffset
math TexDataOffset - RawTexDataSize	# calculate TexDataOffset
goto TexTableOffset					# jump to "TX2D" table

set i long 0						# initialize global cyclic variable
## read texture table ##
for i = 0 < TexFileCount
	get Magic long					# "TX2D"
	get InfoHeaderOffset[i] long	# create an array for these values
	get InfoHeaderSize long			# fixed size(0x34)
	get TexNameOffset[i] long		# offset to texture filename
	get TexNameEndOffset long		# offset to end of texture filename
next i
## read texture names ##
for i = 0 < TexFileCount
	math TexNameOffset[i] + TexTableOffset	# convert TexNameOffset to obsolute offset
	goto TexNameOffset[i]					# jump to offset to texture filename
	getct TexName[i] string 0x2E			# skip the file extension ".bmp"
	string TexName[i] | \					# wipe the drive letter
	string TexName[i] + ".bfe"				# we use custom extension to prevent confusion
next i
## write texture info header to file ##
for i = 0 < TexFileCount
	math InfoHeaderOffset[i] + TexTableOffset	# convert InfoHeaderOffset to obsolute offset
	goto InfoHeaderOffset[i]					# jump to offset to texture info header
	goto 0x20 0 SEEK_CUR						# skip 0x20 bytes
	get RawTexOffset[i] long					# read offset to raw image data
	math RawTexOffset[i] & 0xFFFFFF00			# the last byte is used as a format flag, so we need to set it to zero 
	log TexName[i] InfoHeaderOffset[i] 0x40		# the InfoHeaderSize = 0x34, but we use 0x40 for sake of alignment
next i
## initialize data size for each texture ##
set j long 0									# initialize global cyclic variable
for i = 1 < TexFileCount
	xmath j "i - 1"								# assign (i - 1) to j
	set TexSize[j] RawTexOffset[i]				# initialize TexSize[j] as RawTexOffset[i]
next i
xmath j "i - 1"									# assign (i - 1) to j, where current i = TexFileCount - 1
set TexSize[j] RawTexDataSize					# we have to initialize the last TexSize separately

## calculate data size for each texture and write data to file ##
append											# enable append mode as we've written the info header to these files
for i = 0 < TexFileCount
	math j = i									# synchronize j with i
	math TexSize[j] - RawTexOffset[i]			# calculate data size for texture
	math RawTexOffset[i] + TexDataOffset		# convert RawTexOffset to obsolute offset
	log TexName[i] RawTexOffset[i] TexSize[j]	# write raw texture data to file
next i
append											# disable append mode when we don't need it anymore

### handling KF files ###
set KfmTableOffset long TexTableOffset			# initialize KfmTableOffset as TexTableOffset
math KfmTableOffset + TexTableSize				# calculate KfmTableOffset
goto KfmTableOffset								# jump to KfmTableOffset
## read Kfm table ##
for i = 0 < KfmFileCount
	get Magic long								# "KFSQ" "KFMT" "SCNG"
	get KfmDataOffset[i] long
	get KfmDataSize[i] long						# size of Kfm asset
	get KfmNameOffset[i] long					# offset to Kfm filename
	get urnOffset long							# offset to urn string, which's useless though
next i
## read Kfm filenames ##
for i = 0 < KfmFileCount
	math KfmNameOffset[i] + KfmTableOffset		# convert KfmNameOffset to obsolute offset
	goto KfmNameOffset[i]						# jump to KfmNameOffset
	get KfmName[i] string						# read KfmName
	string KfmName[i] | \						# wipe the drive letter
next i
## extract Kfm assets ##
for i = 0 < KfmFileCount
	math KfmDataOffset[i] + KfmTableOffset		# convert KfmDataOffset to obsolute offset
	goto KfmDataOffset[i]						# jump to KfmDataOffset
	get CompressionFlag long					# read CompressionFlag
	get UnzipSize long							# decompressed size of Kfm asset
	savepos KfmDataOffset[i]					# save current address as offset to Kfm stream
	if CompressionFlag == 1						# data is compressed
		math KfmDataSize[i] - 8					# subtract 8 bytes from KfmDataSize
		clog KfmName[i] KfmDataOffset[i] KfmDataSize[i] UnzipSize	# write data to file
	else
		log KfmName[i] KfmDataOffset[i] UnzipSize					# write data to file
	endif
next i

```

You can copy and paste the above code into a text file and run it through QuickBMS with the xpr archive I provided.

Of course, there can still be some optimizations, like using shared variable names, etc. But to avoid reducing readability, I'll leave it just like that.

So this is the end of the BMS scripting lesson.

[Return to the main tutorial.](https://forum.xentax.com/viewtopic.php?p=138998#p138998)
