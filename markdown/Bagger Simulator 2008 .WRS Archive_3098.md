## Post #1
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2008-07-19T10:10:57+00:00
- Post Title: Bagger Simulator 2008 .WRS Archive

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2008-07-22T22:34:25+00:00
- Post Title: Bagger Simulator 2008 .WRS Archive

This game is made by using a game-library called "3dgamestudio" ([http://www.3dgamestudio.com](http://www.3dgamestudio.com)) which may be used by other game developers.
I've never heard of this company and for me it is a rather boring theme but I think it is worth to regard.
I would appreciate if someone has a clue how to decompress the RLE-compressed data without using the interface of "acknex.dll".

This is what I found out about the WRS-file-format:
All files are compressed with a proprietary RLE-compression.
The WRS-file doesn't seem to have a directory structure.
The filenames are encrypted with a XORVALUE.
GOBREAD can only recover the compressed files, but not the uncompressed data.
Have a look at:
[viewtopic.php?f=10&t=3081](http://forum.xentax.com/viewtopic.php?f=10&t=3081)


WRS structure definitions:
--
mark	dword ?	;= "WRS2" or "WRS3"

if mark eq "WRS2"
	xorvalue=0A5h
elseif mark eq "WRS3"
	xorvalue=0B5h
endif
--
file_descr_struct struct
	file_name		byte 32 dup (?)
	file_compressed_size	dword ?
	file_uncompressed_size	dword ?
ends

--------
The WRS-file contains:
mark
(for_each_file):{file_descr_struct + file_data}
## Post #3
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2008-09-13T21:31:23+00:00
- Post Title: Bagger Simulator 2008 .WRS Archive

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2008-12-07T11:22:00+00:00
- Post Title: Bagger Simulator 2008 .WRS Archive

Here you can find an unpacker for WRS-files:
[viewtopic.php?p=27492#p27492](http://forum.xentax.com/viewtopic.php?p=27492#p27492)
## Post #5
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2008-12-12T20:00:03+00:00
- Post Title: Bagger Simulator 2008 .WRS Archive

Great thx!!!
Works like a charm

bye asmxtx
