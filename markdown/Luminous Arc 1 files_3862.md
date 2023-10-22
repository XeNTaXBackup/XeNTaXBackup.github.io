## Post #1
- Username: floral
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 03, 2009 7:50 pm
- Post datetime: 2009-11-13T04:13:08+00:00
- Post Title: Luminous Arc 1 files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-13T12:19:24+00:00
- Post Title: Luminous Arc 1 files

i looked at the bin file for a little bit it contains a name table in the beggining with a matching offset table.
Some of the files might be unicode or sometype of compression like lzss.
its a very wierd offset table but the firstfile starts at 0x1f80
I think the table goes something like file start offset file end offset
a lot of the files begin with 10 00 06 00


the .iear looks like a model format.
## Post #3
- Username: floral
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 03, 2009 7:50 pm
- Post datetime: 2009-11-14T18:27:24+00:00
- Post Title: Luminous Arc 1 files

It is a japanese game, sorry i should have mentioned that.  shift jis encode will allow you to see the japanese characters.  Can you get at the files?  extract them?  it sounds like you figured out some of what they are.
## Post #4
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-15T00:17:23+00:00
- Post Title: Luminous Arc 1 files

A small script for .BIN files.

```

# Main Block
Get OFF_FILENAMES_BLOCK long
Get SIZE_FILENAMES_BLOCK long
Get OFF_OFFSETS_BLOCK long
Get SIZE_OFFSETS_BLOCK long

Set NUM_FILES SIZE_OFFSETS_BLOCK
Math NUM_FILES /= 8

# Filenames block
Math OFF_FILENAMES_BLOCK += 0x08
GoTo OFF_FILENAMES_BLOCK
Math OFF_FILENAMES_BLOCK -= 0x08

Get OFF_FILENAMES_BLOCK_DATA long
Math OFF_FILENAMES_BLOCK_DATA += OFF_FILENAMES_BLOCK

# Offsets block & extract files
Set OFF_NEXT_FILENAME OFF_FILENAMES_BLOCK_DATA
Set OFF_NEXT_OFFSET OFF_OFFSETS_BLOCK

For I = 0 < NUM_FILES
	# Get the file offset
	GoTo OFF_NEXT_OFFSET
	Get START_OFFSET long
	Get END_OFFSET long
	SavePos OFF_NEXT_OFFSET

	# Calculate the size
	Set SIZE END_OFFSET
	Math SIZE -= START_OFFSET

	# Get the file name
	GoTo OFF_NEXT_FILENAME
	Do
		Get FILENAME_LENGTH byte
	While FILENAME_LENGTH == 0 # Zero = End of a folder. Not handled, ATM.
	
	GetDString FILENAME FILENAME_LENGTH
	SavePos OFF_NEXT_FILENAME

	# Extract the file
	Log FILENAME START_OFFSET SIZE
Next I

```


All files have 5 bytes + LZSS compressed data block.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-15T10:53:23+00:00
- Post Title: Luminous Arc 1 files

if you refer to the files extracted from the BIN archive, no they don't use lzss and they look even not compressed at all
## Post #6
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-15T13:35:46+00:00
- Post Title: Luminous Arc 1 files

> Reply from aluigi
>
> if you refer to the files extracted from the BIN archive, no they don't use lzss and they look even not compressed at all

They are compressed with LZ77 (Wii). I always confuse LZSS and LZ77   
[http://wiibrew.org/wiki/LZ77](http://wiibrew.org/wiki/LZ77)

BTW, there are just 4 bytes before the LZ77 block, the 5th byte is the first LZ77 flags.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-15T15:51:14+00:00
- Post Title: Luminous Arc 1 files

are you aware of other compression algorithms widely used in consoles like this one?
## Post #8
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-15T16:09:02+00:00
- Post Title: Luminous Arc 1 files

NDS games also use the same LZ77 implementation frequently. Other than that, no.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-15T16:18:17+00:00
- Post Title: Luminous Arc 1 files

good, it will be added in the next version of quickbms
