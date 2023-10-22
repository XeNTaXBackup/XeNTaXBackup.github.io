## Post #1
- Username: datahaven
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 09, 2013 6:23 am
- Post datetime: 2013-10-09T09:40:56+00:00
- Post Title: Rogue Legacy (PC) - Graphics Mod

Hi Everyone,

Here's a guide I wrote on how to view/change the graphics in Rogue Legacy:

[http://www.adriandale.co.uk/index.php/2 ... gue-legacy](http://www.adriandale.co.uk/index.php/2013/10/04/how-to-mod-rogue-legacy)

Below are the QuickBMS scripts referred to in the article.

Enjoy,

Adrian

RL_uncmp_xnb.bms

```
# Adrian Dale October 2013
# http://www.adriandale.co.uk
#
# X  N  B  tt       lllllllllll ccccccccccc
# 58 4e 42 77 05 80 5e 24 01 00 b1 00 40 00 
# tt = target platform = Windows
# 05 format version = XNA Game Studio 4.0
# 80 flag - asset data is compressed
# lll = full file size
# ccc = uncompressed data size
# Followed by compressed data

#XMemDecompress, Xbox 360 LZX algorithm of xcompress.lib
ComType XMemDecompress 0x10000

get NAME basename
get EXT extension
string NAME += "_unpacked."
string NAME += EXT

# Extract the info we need from the header of the xnb file
idstring "XNB"
get PLATFORM byte
get FORMAT_VERSION byte

get FORMAT_FLAGS byte
math FORMAT_CHECK = FORMAT_FLAGS
math FORMAT_CHECK & 0x80
If FORMAT_CHECK == 0x00
  print "WARNING: File is not compressed\n"
  cleanexit
Endif

get FILESIZE_COMPRESSED long
get FILESIZE_UNCOMPRESSED long
math FILESIZE_COMPRESSED - 0x0e

# Create a new version of the xnb file in memory that will be
# the uncompressed file
log MEMORY_FILE 0 0
putvarchr MEMORY_FILE TMP 0   # improves the speed with pre-allocation
log MEMORY_FILE 0 0           # reset the position and size of the file
append
PutCT "XNB" string -1 MEMORY_FILE
Put PLATFORM byte MEMORY_FILE
Put FORMAT_VERSION byte MEMORY_FILE

math FORMAT_FLAGS ^ 0x80    # Clear the compression flag
Put FORMAT_FLAGS byte MEMORY_FILE

math FINAL_FILESIZE_UNCOMPRESSED = FILESIZE_UNCOMPRESSED
math FINAL_FILESIZE_UNCOMPRESSED += 0x0a
Put FINAL_FILESIZE_UNCOMPRESSED long MEMORY_FILE

Clog MEMORY_FILE 0x0e FILESIZE_COMPRESSED FILESIZE_UNCOMPRESSED 
math FILESIZE_UNCOMPRESSED += 0x0a
append

log NAME 0 FINAL_FILESIZE_UNCOMPRESSED MEMORY_FILE

```

RL_extract_bmp.bms

```
# Adrian Dale October 2013
# http://www.adriandale.co.uk
#
# This is a QuickBMS script that creates a .bmp bitmap file from
# an uncompressed Rogue Legacy .xnb texture file
# (NB RL_uncmp_xnb.bms must be used on the compressed files to decompress them)

get NAME basename
string NAME += ".bmp"

idstring "XNB"

get PLATFORM byte
get FORMAT_VERSION byte

get FORMAT_FLAGS byte
math FORMAT_CHECK = FORMAT_FLAGS
math FORMAT_CHECK & 0x80
If FORMAT_CHECK != 0x00
  print "WARNING: File is compressed\n"
  cleanexit
Endif

get FILESIZE_UNCOMPRESSED long

# Next part of the .xnb file is the Type Manifest, which says
# which readers are needed.
# Rather than parse this properly, I'm assuming that this code
# will only be run on Rogue Legacy texture resource files
# and hardcoding a few offsets and values.
goto 0xab # Skips the reader name
get BMP_WIDTH long
get BMP_HEIGHT long
get MIP_COUNT long
get BMP_DATA_SIZE long

log MEMORY_FILE 0 0
putvarchr MEMORY_FILE TMP 0   # improves the speed with pre-allocation
log MEMORY_FILE 0 0           # reset the position and size of the file
append

# Bitmap file header
PutCT "BM" string -1 MEMORY_FILE
math BMP_OFFSET = 0x7a
math TOTAL_BMP_SIZE = BMP_DATA_SIZE
math TOTAL_BMP_SIZE + BMP_OFFSET
Put TOTAL_BMP_SIZE long MEMORY_FILE 
Put 0x0 long MEMORY_FILE      # reserved bytes
Put BMP_OFFSET long MEMORY_FILE     # offset of bmp data

# DIB header (bitmap information header)
Put 0x6c long MEMORY_FILE
Put BMP_WIDTH long MEMORY_FILE   # bitmap width in pixels
Put BMP_HEIGHT long MEMORY_FILE   # bitmap height
Put 0x01 short MEMORY_FILE # no. of colour planes being used. Must be set to 1
Put 0x20 short MEMORY_FILE # no. of bits per pixel
Put 0x03 long MEMORY_FILE # compression method (Allows us to specify RGBA order)
Put BMP_DATA_SIZE long MEMORY_FILE # image size
Put 0x0b13 long MEMORY_FILE # horizontal resolution (pixels per meter)
Put 0x0b13 long MEMORY_FILE # vertical resolution
Put 0x00 long MEMORY_FILE # no. of colours in palette, or 0 to default to 2^n
Put 0x00 long MEMORY_FILE # no. of important colours

Put 0x000000ff long MEMORY_FILE # Red bit mask    # Needed for compression method 3
Put 0x0000ff00 long MEMORY_FILE # Green bit mask
Put 0x00ff0000 long MEMORY_FILE # Blue bit mask
Put 0xff000000 long MEMORY_FILE # Alpha bit mask
Put 0x57696e20 long MEMORY_FILE # LCS_WINDOWS_COLORSPACE
Put 0x00 long MEMORY_FILE # unused
Put 0x00 long MEMORY_FILE # unused
Put 0x00 long MEMORY_FILE # unused
Put 0x00 long MEMORY_FILE # unused
Put 0x00 long MEMORY_FILE # unused
Put 0x00 long MEMORY_FILE # unused
Put 0x00 long MEMORY_FILE # unused
Put 0x00 long MEMORY_FILE # unused
Put 0x00 long MEMORY_FILE # unused

Put 0x00 long MEMORY_FILE # unused
Put 0x00 long MEMORY_FILE # unused
Put 0x00 long MEMORY_FILE # unused

log MEMORY_FILE 0xbb BMP_DATA_SIZE

append
log NAME 0x00 TOTAL_BMP_SIZE MEMORY_FILE


```


RL_repack.bms

```
# Adrian Dale October 2013
# http://www.adriandale.co.uk
#
# Re-packs a bmp file back into the uncompressed .xnb
# file that it was taken from.
# Note that script expects to find an xnb file with the same
# name as the bmp file being modified.
# ie
# converting filename_unpacked.bmp will require filename_unpacked.xnb
# in the same directory
# and will produce filename_unpacked_repacked.xnb
get NAME basename
string NAME += "_repacked.xnb"

open FDDE xnb 1

get FILE_SIZE asize

math DATA_SIZE = FILE_SIZE
math DATA_SIZE - 0x8a
math WORD_COUNT = DATA_SIZE
math WORD_COUNT / 4
math FINAL_SIZE = DATA_SIZE
math FINAL_SIZE + 0xbb
idstring "BM"
goto 0x8a

log MEMORY_FILE 0 0
putvarchr MEMORY_FILE TMP 0   # improves the speed with pre-allocation
log MEMORY_FILE 0 0           # reset the position and size of the file

# Add the header from our uncompressed xnb file to the memory file
log MEMORY_FILE 0x00 0xbb 1

append
goto 0xbb MEMORY_FILE
For i = 0 < WORD_COUNT
  Get LONGVAL long
  ReverseLong LONGVAL
  Put LONGVAL long MEMORY_FILE
Next i

append
log NAME 0x00 FINAL_SIZE MEMORY_FILE


```
## Post #2
- Username: kamuline
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Sep 02, 2009 2:11 am
- Post datetime: 2013-11-02T15:19:14+00:00
- Post Title: Rogue Legacy (PC) - Graphics Mod

Hello

I made a script to unpack/repack only the dds image in the Font files, based on datahaven's and merlinsvk's script.

Firt decompress the xnb file with datahaven's RL_uncmp_xnb.bms script.

Then use this on decompressed file to unpack:

```

get NAME basename
string NAME += ".dds"

idstring "XNB"

get PLATFORM byte
get FORMAT_VERSION byte

get FORMAT_FLAGS byte
math FORMAT_CHECK = FORMAT_FLAGS
math FORMAT_CHECK & 0x80
If FORMAT_CHECK != 0x00
  print "WARNING: File is compressed\n"
  cleanexit
Endif

get FILESIZE_UNCOMPRESSED long

goto 0x3ce
get WIDTH long
get HEIGHT long
get MIP_COUNT long
get DATASIZE long
savepos START

putVarChr MEMORY_FILE 0XC HEIGHT long
putVarChr MEMORY_FILE 0x10 WIDTH long

append
log MEMORY_FILE START DATASIZE
append

get DDSSIZE asize MEMORY_FILE
log NAME 0 DDSSIZE MEMORY_FILE
```


And this to repack:

```
string NAME += "_repacked.xnb"

open FDDE xnb 1
open FDDE dds 0

get FILE_SIZE asize
get XNB_SIZE asize 1

math DATA_SIZE = FILE_SIZE
math DATA_SIZE - 0x80

idstring "DDS"

goto 0x3DA 1
get IMGSIZE long 1
math IMGSIZE += 0x3DE
math XNB_SIZE -= IMGSIZE
log MEMORY_FILE 0x00 0x3DE 1

append
log MEMORY_FILE 0x80 DATA_SIZE
log MEMORY_FILE IMGSIZE XNB_SIZE 1
append

putVarChr MEMORY_FILE 0x3DA DATA_SIZE long
get ASIZE asize MEMORY_FILE
putVarChr MEMORY_FILE 0X6 ASIZE long


log NAME 0x00 ASIZE MEMORY_FILE
```
