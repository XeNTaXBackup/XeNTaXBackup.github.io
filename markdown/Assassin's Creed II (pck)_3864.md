## Post #1
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-11-13T23:21:57+00:00
- Post Title: Assassin's Creed II (pck)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-11-14T20:13:08+00:00
- Post Title: Assassin's Creed II (pck)

the file it's from xbox360 ?
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-11-14T21:23:03+00:00
- Post Title: Assassin's Creed II (pck)

its a 360 file, but i cant figure this out either.
## Post #4
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-15T12:58:03+00:00
- Post Title: Assassin's Creed II (pck)

```

Endian big

# Main header
IDString "AKPK"
Get HEADER_TOTAL_SIZE long
Get HEADER_UNK1 long
If HEADER_UNK1 != 1
	Print "Strange HEADER_UNK1 = %HEADER_UNK1%, may crash..."
EndIf
Get HEADER_EXTRA_DATA_SIZE long
Get SIZE_OF_BLOCK1 long
Get SIZE_OF_BLOCK2 long

SavePos TEMP_POS
Math TEMP_POS += HEADER_EXTRA_DATA_SIZE
GoTo TEMP_POS

# Block 1
Set EXTRACT_BLOCK_BASE_PATH string "1"
CallFunction EXTRACT_BLOCK

# Block 2
Set EXTRACT_BLOCK_BASE_PATH string "2"
CallFunction EXTRACT_BLOCK

# Function to extract a block
# Set EXTRACT_BLOCK_BASE_PATH to the path where the files should be extracted before calling
StartFunction EXTRACT_BLOCK
	Get BLOCK_NUM_ENTRIES long

	For I = 0 < BLOCK_NUM_ENTRIES
		# Read the file entry
		Get ENTRY_ID long
		Get ENTRY_BLOCK_SIZE long
		Get ENTRY_UNK1 long
		If ENTRY_UNK1 != 0
			Print "Strange ENTRY_UNK1 = %ENTRY_UNK1%, may crash..."
		EndIf
		Get ENTRY_SIZE long
		Get ENTRY_OFFSET_IN_BLOCKS long
		Get ENTRY_UNK2 long
		If ENTRY_UNK2 != 0
			If ENTRY_UNK2 != 1
				Print "Strange ENTRY_UNK2 = %ENTRY_UNK2%, may crash..."
			EndIf
		EndIf

		# Extract
		Set PATH EXTRACT_BLOCK_BASE_PATH
		String PATH += "/"
		String PATH += ENTRY_ID

		Set OFFSET ENTRY_OFFSET_IN_BLOCKS
		Math OFFSET *= ENTRY_BLOCK_SIZE

		Log PATH OFFSET ENTRY_SIZE
	Next I
EndFunction

```


It will create 2 folders, the first one contains BKHD files (I found some info about them, it did almost match the data, but the format seems to be updated) and some RIFX files that seem to contain a headerless Ogg.
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-11-15T23:03:50+00:00
- Post Title: Assassin's Creed II (pck)

So its not possible to do anything with these RIFX files?
## Post #6
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-16T16:56:47+00:00
- Post Title: Assassin's Creed II (pck)

No, unless someone figures out how it's packed, probably they're just vorbis packets.
## Post #7
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-12-05T13:36:27+00:00
- Post Title: Assassin's Creed II (pck)

I finished a Audiokinetic Wwise RIFF/RIFX Vorbis to Ogg Vorbis converter yesterday, ww2ogg here [http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)

(All interested parties already know, but I thought it'd be best to give this thread closure)
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-12-05T19:56:35+00:00
- Post Title: Assassin's Creed II (pck)

And you have worked your magic hcs
## Post #9
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-12-05T22:05:15+00:00
- Post Title: Assassin's Creed II (pck)

Indeed.
