## Post #1
- Username: damimavpl
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jul 16, 2011 4:03 pm
- Post datetime: 2011-07-17T20:26:47+00:00
- Post Title: Tales Of The World Radiant Mythology 2 : ARC/BIN & TOTWRM3

I need tools to unpack & pack again when finish translating files from game on PSP "Tales Of The World Radiant Mythology 2"

archives: *.arc & *.bin


 files.rar
some files from (40.52 KiB) Downloaded 66 times



EDIT: I find text from game using HEXEditor in file "eboot.bin" Is any chance to unpack this file (this is normal eboot file from PSP on every game)
         Also I need method to unpack BIG file from "Tales Of The World Radiant Mythology 3": name file "namco.bdi" 970MB

         Me and my friends wanna translate this games completely (15 people waiting)

 Please help with translating games and finding method to unpack & pack again this files
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-17T20:35:41+00:00
- Post Title: Tales Of The World Radiant Mythology 2 : ARC/BIN & TOTWRM3

no one can help without samples
## Post #3
- Username: damimavpl
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jul 16, 2011 4:03 pm
- Post datetime: 2011-07-18T07:55:20+00:00
- Post Title: Tales Of The World Radiant Mythology 2 : ARC/BIN & TOTWRM3

> Reply from chrrox
>
> no one can help without samples

I added the files from game
## Post #4
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2011-08-18T20:52:35+00:00
- Post Title: Tales Of The World Radiant Mythology 2 : ARC/BIN & TOTWRM3

I'm making a program for you guys, to unpack/pack those arc files. I'm already done with the unpacking, working on the packing part now.

Also, if you can provide me through a PM that bigfile I may be able to help you.
## Post #5
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-10-28T22:06:57+00:00
- Post Title: Tales Of The World Radiant Mythology 2 : ARC/BIN & TOTWRM3

For better understanding: file with EZBIND header = .arc file

Partial success 
After making an arc extractor and understanding .ppt (the textures) somewhat I present:

sucessful recompression into an arc file (that doesn't crash the game)

Steps (assuming that the new data is equal or less Bytes than the old one):
extract file, alter file, recompress using standard gzip util (gzip.exe), hex edit the file back into the .arc, change filesize in metadata for the file 

it seems that what was assumed to be a CRC is either irrelevant for the game or something completly different (like flags for the file)
(see [http://www.mechanical.co.at/0xFAIL/file ... ormat.html](http://www.mechanical.co.at/0xFAIL/files/HTML/ARC_fileformat.html))


the things above their heads should be a yellow '?',
after editing it looks like a white square(on purpose)

Next step is to write a compressor for .arc
(of course I have to try how the game reacts when I blindly compress all files instead of compressing specific filetypes, hopefully it works)

Don't worry, even though this screenshot is from TotW:RM1 the file formats are the same for RM2 und RM3
(.bin in the RM1 are just simple GZip files that contain an .arc file, didn't look for RM2 and RM3)
## Post #6
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-11-01T20:11:11+00:00
- Post Title: Tales Of The World Radiant Mythology 2 : ARC/BIN & TOTWRM3

I started messing with the files a bit more with the result of constant crashing of the game, I tried
to make sense of the CRC field but failed (see the link in the last post), tried flags, time_t, CRC of data,
CRC of metadata, sequential file number nothing of that seems to be right, yet I think it's a custom CRC
with the metadata as an input. 

BTW the .bin have to be decompressed with GZip before being valid .arc files
(the extension from the resulting file has to be changed manually from .bin to .arc)
## Post #7
- Username: Feit
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 27, 2011 10:14 am
- Post datetime: 2011-12-28T02:08:04+00:00
- Post Title: Tales Of The World Radiant Mythology 2 : ARC/BIN & TOTWRM3

Excuse me kind sir's, may i ask if there a compressor for the files stated in this topic??
