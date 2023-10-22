## Post #1
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2013-04-15T21:53:21+00:00
- Post Title: Xbox Minecraft MCR (region) Files

Hi, I made a hacky Batch + Swiss File Knife world extractor for the Xbox version of minecraft, I can get all the files out of the savegame.dat but the region files are compressed differently from the PC version.

PC version uses zlib compression, the xbox not sure, (gzip? or lzx?) the structure is identical to Minecraft 1.3 (PC) so the wiki has been helpful but I'm stuck at getting the files loaded in MCEdit (stable33 MCR version)

[XBLA Minecraft World Extractor v1.0.zip](https://dl.dropboxusercontent.com/u/17063965/XBLA%20Minecraft%20World%20Extractor%20v1.0.zip)

I have included the extractor + savegame.dat & also a Xbox region file as well as a PC Region file, for comparison.

any help would be very much appreciated as I have got so far & hit a roadblock.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-04-16T03:26:35+00:00
- Post Title: Xbox Minecraft MCR (region) Files

The xbox version uses xmemcompress (MS LZX) with compressed size plus 0x80000000 followed by the uncompressed size.
## Post #3
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2013-04-16T13:23:19+00:00
- Post Title: Xbox Minecraft MCR (region) Files

Thank you, but sorry to ask how would I go about decompressing said files, I know where the everything is inside the region files, & where the compressed length value is located (I didn't know about the decompressed length value & the use for the 0x80000000)

I'm no programmer I dabble in batch files for doing simple tasks & no one has attempted what I have done, which I find strange, there more for the inventory editing :-/
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-04-16T13:48:38+00:00
- Post Title: Xbox Minecraft MCR (region) Files

You need to use the xbox sdk to use that decompression library.

Regarding the format I have not found information about it, I simply wrote a lame script to do the job:
[http://aluigi.org/papers/bms/others/minecraft_mcr.bms](http://aluigi.org/papers/bms/others/minecraft_mcr.bms)
## Post #5
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-04-16T15:51:46+00:00
- Post Title: Xbox Minecraft MCR (region) Files

thanks aluigi ^_^
## Post #6
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2013-04-16T18:11:55+00:00
- Post Title: Xbox Minecraft MCR (region) Files

Bellow.
## Post #7
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2013-05-20T21:45:06+00:00
- Post Title: Xbox Minecraft MCR (region) Files

bellow
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-05-21T18:18:35+00:00
- Post Title: Xbox Minecraft MCR (region) Files

```
set NAME unicode NAME
```
## Post #9
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2013-05-21T20:01:55+00:00
- Post Title: Xbox Minecraft MCR (region) Files

> Reply from aluigi
>
> ....

Thank you very much  I tried everything, bar put NAME at the end of that set string :-/

My first scripts  - they have batches that does some work to  not included bellow.

The bellow Scripts will Decompress your Savegame.dat & extract the files from the decompressed save.

Save Decryption.

```
# MCXB_Save_Decrypt.bms
# (c) 25/05/2013 by Rocky5
#=================================================================================================

endian big
get NAME FILENAME				# Gets the file name

	comtype xmemdecompress
	get CSIZE long				# Compressed file size.
	math CSIZE -= 0x08
	goto 0x08					# Used to skip the NULLED bytes.
	get DSIZE long				# Uncompressed Size.

clog "tmp\0.tmp" 0xC CSIZE DSIZE

```

Save Encryption.

```
# MCXB_Save_Encrypt.bms
# (c) 25/05/2013 by Rocky5
#=================================================================================================

endian big
open "tmp" 0.tmp                        # Open uncompressed file.
get DSIZE ASIZE                        # Get uncompressed size.

   comtype xmemlzx_compress

clog "tmp\1.tmp" 0x0 DSIZE DSIZE         # Compress file.

open "tmp" 1.tmp
get CSIZE ASIZE                        # Get compressed size.
math CSIZE += 0x08                     # Needed for the Xbox to read the save

log MEMORY_FILE1 0x0 0x0               # Create a memory file.
put CSIZE long MEMORY_FILE1               # Puts file compressed size.
put 0     long MEMORY_FILE1               # Puts Nuls for 4 bytes.
put DSIZE long MEMORY_FILE1               # Puts file uncompressed size.

math CSIZE -= 0x08                     # Reset the compressed size

append
log MEMORY_FILE1 0x0 CSIZE               # Puts it all together.
append

get SIZE asize MEMORY_FILE1

log "tmp\savegame.dat" 0 SIZE MEMORY_FILE1

```

Save extractor.

```
# MCXB_Save_Extractor.bms
# (c) 25/05/2013 by Rocky5
#=================================================================================================
# First 4 Bytes are the index offset.
# The next 4 bytes are the file count.
# Each files Index is 144 in decimal & 0x90 hex.
# At Offset 0x80 4 bytes long on each file index is the Region size. (in hex)
# The next 4 bytes are the Region file starting offset.

# There are bytes after the above, but I don't know what there for. (Hash maybe?)

# The Region files are a similar format to Minecraft Beta 1.3 for the PC. There compressed using
# XmemCompress (LZX), it appears the Xbox format doesn't have padding in the chunks, instead it
# creates more files. A PC 1024x1024x127 map (Xbox map size) has 64, 81kbs files. the Xbox has
# 729 files ranging from 5kbs to 4kbs, with no padding, this is true on a flatland created world.
#
# PC Chunk files are 16x16x127 hence 64 files. 64 * 16 = 1024
# Xbox has a max of 729 chunk files but if going by the above that would mean there 1.**** chunks
# per file. 1024 / 729 = 1.404663923182442 - cant be this though.
#
# So Region files can be extracted, decompressed. But thats it for me.
#=================================================================================================

endian big
get FILESIZE asize
get INDEXOFFSET long
get FILEINDEXCOUNT long

for A = 0 < FILEINDEXCOUNT
	goto INDEXOFFSET           	# Jumps to the Index.
	getdstring NAME 0x80		# Gets bytes with the files names
	set NAME unicode NAME		# Translates them to unicode so 00 works.
	get SIZE long				# Size of the region file.
	get OFFSET long				# Offset for the start of the region file.
	get UNKNOWN1 long			# Just put that here to catch the next 4 bytes.
	get UNKNOWN2 long			# Just put that here to catch the next 4 bytes.
	math INDEXOFFSET += 0x90    # Starts on the next index entry.
	log NAME OFFSET SIZE		# Outputs the files.
next A

```
