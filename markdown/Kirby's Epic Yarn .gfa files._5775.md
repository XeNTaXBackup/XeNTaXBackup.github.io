## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-01-13T23:06:55+00:00
- Post Title: Kirby's Epic Yarn .gfa files.

Well here we go again. I know we've covered GFA files before with Wario Land: Shake It! but it seems there's a slight difference in these. Take a look at [THIS TOPIC LINK](http://forum.xentax.com/viewtopic.php?p=35866) to see how we managed to work that out.

Now have a look at some of these files, mainly the ones I'm concerned with are the Boss files, but the enemy files are cool too. It seems the enemy files extract fine but into another format we know nothing about.
[CHECK THESE OUT](http://www.sendspace.com/file/qquyyb)

So...I need the images or a way of viewing them, hopefully a modification to the quickbms script will work.
## Post #2
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2011-01-19T13:25:46+00:00
- Post Title: Kirby's Epic Yarn .gfa files.

I must admit GFA files always confused me. I tried extracting some of the enemy files but they all dump out even more obscure files, which I assume are frames of animation. Thus far I've been unable to extract any Boss files, which is a shame since I wanted Yin-Yarn's animations. I assume the only reason the boss files can't be properly extracted is that they contain small 3-D models as well (Yin-Yarn for example has the two knitting needles.) So we need a way to properly extract both.
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-19T20:59:52+00:00
- Post Title: Kirby's Epic Yarn .gfa files.

well, it hasn't' changed much from hcs's version!

note: not really tested, so that other comtypes may still be checked

```
# Wario Land: The Shake Dimension GFA

Endian little

# Main header
IDString "GFAC"
Get HEADER_1_1 long
Get HEADER_1_2 long
# ---
# Change of version here
If HEADER_1_1 != 0x300
   Print "Strange HEADER_1_1 = %HEADER_1_1%, may crash..."
EndIf
# ---
If HEADER_1_2 != 1
   Print "Strange HEADER_1_2 = %HEADER_1_2%, may crash..."
EndIf
Get FILE_TABLE_OFFSET long
Get FILE_TABLE_SIZE long
Get DATA_OFFSET long
Get DATA_SIZE long

# Read compressed data header
GoTo DATA_OFFSET

IDString "GFCP"
Get HEADER_1_1 long
Get CTYPE long
If HEADER_1_1 != 1
   Print "Strange GFCP HEADER_1_1 = %HEADER_1_1%, may crash..."
EndIf

## ---
# If CTYPE == 1

ComType lz77wii_raw30
## ---

Get RAW_DATA_SIZE long
Get COMPRESSED_DATA_SIZE long

Set CDATA_OFFSET DATA_OFFSET
Math CDATA_OFFSET + 0x14

# Decompress
Clog MEMORY_FILE CDATA_OFFSET COMPRESSED_DATA_SIZE RAW_DATA_SIZE

# Extract files
GoTo FILE_TABLE_OFFSET
Get FILE_COUNT long
SavePos READ_OFFSET

For I = 0 < FILE_COUNT
   GoTo READ_OFFSET

   # Read the file entry
   Get CRC32 long # guess
   Get NAME_OFFSET long

   ## ---
   # Note: last NAME_OFFSET has it's size flagged
   #       pointless because we know FILE_COUNT

   Math NAME_OFFSET %= 0x80000000
   ## ---

   Get FILE_SIZE long
   Get FILE_OFFSET long

   SavePos READ_OFFSET

   Math FILE_OFFSET - DATA_OFFSET

   GoTo NAME_OFFSET
   Get FILE_NAME string

   Log FILE_NAME FILE_OFFSET FILE_SIZE MEMORY_FILE
Next I

```
## Post #4
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-01-19T21:30:16+00:00
- Post Title: Kirby's Epic Yarn .gfa files.

Oho! Thank you! Now all I need is something to convert the output to pngs.
## Post #5
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2011-01-21T19:12:41+00:00
- Post Title: Kirby's Epic Yarn .gfa files.

Excellent! Now what about the mneb and brres files they output? The brres files are different than normal wii compression, and I've just plain never heard of MNEB files. We need a converter, quick.
