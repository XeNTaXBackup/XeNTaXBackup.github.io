## Post #1
- Username: MadMartin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 07, 2008 2:16 am
- Post datetime: 2008-07-06T19:19:51+00:00
- Post Title: Request for Raptor - Call of the Shadows GLB-file

Hi everyone,

I've just stumbled upon my old copy of Raptor - Call of the Shadows. A great yet simple vertical scroller where you control a jet and shoot masses of enemies. Although this game's over a decade old, I'd like to try out if it's modable. Starting with the archive files, significant by their file size...

After making some unsuccessful google researches about those archive files ( FILE0000.GLB e.g. ) I decided to decipher the file format by myself. At this time I've not been able to gather much information, but while I'm keeping on with it, I wanted to ask if s.o. here has attempted to decipher the format or knows s.th. about it.

At [http://www.3drealms.com/raptor/index.html](http://www.3drealms.com/raptor/index.html) you can download the demo version, if interested.

By the time of this post, I've gathered the following infos:
- files start with 4-bytes header identifier: 64 9B D1 09
- there seems not be an index of files in clear text, neither at the beginning nor the end, perhaps encrypted?
- file data seems not to be encrypted, or at least not every file (??)

- files found in FILE0000.GLB at this time:
	DMXGUS, start offset: 0x598B, size: 0x18A7 (identified not by filename given in archive, but by google research; often named GUSMIDI.INI or s.th. like that if not in archive)
	OPL_II lump (not sure, is this a file?; seems to hold some info about some instrument patches), start offset: 0x7232, size: 0x2E84 (identified not by filename given in archive, but by google research)

	music files similar to the doom-music format (specs at: [http://edge.sourceforge.net/edit_guide/doom_specs.htm](http://edge.sourceforge.net/edit_guide/doom_specs.htm)) 
		start offset	size
		0x11273		0xAA
		0x1131D		0x317
		0x11634		0xCE1
		0x12315		0x87A
		0x12B8F		0x108F
		0x13C1E		0x3453
		0x17071		0x12FB
		0x1836C		0x1632
		0x1999E		0x1F31
		0x1B8CF		0x2439
		0x1DD08		0x17DC
		0x1F4E4		0x18FB
		0x20DDF		0xA73
		0x21852		0x2184
		0x239D6		0x4F3

This first file, FILE0000.GLB, seems to hold sound and music data. The ASCII-text forming some weird patterns after those MUS files seems to be familiar, but I'm not exactly sure where it comes from. Perhaps s.o.'s got an idea? The other files also show patterns, some similar to bitmaps. By now I've not been successful in finding some files in there.

I know that this info is not that much, but as I mentioned already, this post is a attempt somewhat parallel to my own investigations. Perhaps it will reveal some info, hm? Would be nice if s.o. with more experience and some free time    would give it a try...

If you have trouble playing it, try the Dosbox. It runs good within...

greetings
Martin
## Post #2
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2013-10-11T09:09:24+00:00
- Post Title: Request for Raptor - Call of the Shadows GLB-file

Sorry about digging up such an old topic, but I was just going to post the same question anyway.

Does anyone know if any progress has been made in the last five years with this file format?
## Post #3
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2013-10-11T10:20:07+00:00
- Post Title: Request for Raptor - Call of the Shadows GLB-file

I've just had a closer look at this format, and this is what I have discovered so far:

Only the FAT (the list of filenames and offsets) is encrypted.  This is the first 43008 bytes of the file, which is 768 file entries of 56 bytes each.

I have only managed to partially decrypt so far.  By taking each byte, then subtracting the previous byte, you end up with a file that seems to have a phrase repeated with bits missing.  This is a classic XOR cipher, with the key "32768GLB".  This key appears in the .exe file, along with "32768SH".

If I XOR with this key the data clears up considerably, but there is still another layer of encryption as no filenames appear yet, but the 56-byte structure is clearly visible.

EDIT: The first file in FILE0001.GLB is at offset 0xA800 (immediately after the FAT) and is an unencrypted 768-byte VGA palette.  The FAT might actually be in entries of 28 bytes, but every second entry is XOR crypted with the hex key 75 7B 74 0B.  At least running this over every second lot of 28 bytes makes them look the same as the other lot of 28 bytes!
## Post #4
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2013-10-12T09:15:45+00:00
- Post Title: Request for Raptor - Call of the Shadows GLB-file

Last post - I've successfully reverse engineered this file format.  I am in the process of writing up an explanation for the full encryption algorithm and the file structures, which will appear shortly on the [ModdingWiki page for the GLB format](http://www.shikadi.net/moddingwiki/GLB_Format).
