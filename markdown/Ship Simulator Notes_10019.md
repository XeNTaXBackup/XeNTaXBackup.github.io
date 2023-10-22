## Post #1
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2013-01-06T23:52:44+00:00
- Post Title: Ship Simulator Notes

Ship Simulator (by VStep, distributed by Paradox) uses the open source compression method Gzip (or GNU zip) to pack many of its files. In a hex editor, they are easy to recognize by the x789C at displacement x08 in the header of all records compressed this way.

Ship Simulator of course adds its own extra header information (x00 - x07), confusing the matter some. The first 3 bytes of each record is identified by the ASCII characters "ENC". The extra information ahead of the x789C is unnecessary and easily stripped out by software. Then by adding adding 4 trailing bytes to the end of the record, which is a fullword compressed data length count, the resultant file can then be unzipped using the freeware command line utility zlibc.exe (written by the same people who wrote Gzip).

Ship Simulator does not pack masses of files into one compressed ".PAK" file like so many games do, but chooses to compress each file individually, leaving its original file extension intact. You will even find some graphic files (like .dds, .jpg, etc.) compressed in this method in case you wonder why they won't open up normally in an image editor.

NOTE: .CGR files, of which there are many in this game, cannot be extracted. They are exported (let me call that "compiled") Quest3D channel graphics files (many include sounds too) and by nature are not extractable. About 50% of the game files ARE extractable though, of many different file extensions, using the above method.

Once extracted, they are simply a text file (.xml, .ini, etc.), easily modified in any text editor. The technique is to keep the original compressed file in the same folder by just renaming it with a ".bak" extension. Ship Simulator won't see it, but instead will use the plain text modified file in its place. Recompression of your modified file is not necessary. Many modding abilities will now be possible, something sorely lacking in Ship Simulator.

-timetraveller
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2013-01-07T05:25:03+00:00
- Post Title: Ship Simulator Notes

you could easily write a script for this - is the uncompressed size part of the header?

```

get name basename
get zsize asize
math zsize -= 8

clog basename 8 zsize size

```
## Post #3
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2013-01-07T08:09:01+00:00
- Post Title: Ship Simulator Notes

Yes, I suppose a script would do it too. The size of the compressed data is 10 bytes less than the size of the file (8 + the x789C). Size is not kept in the ENC header. It must be computed.
## Post #4
- Username: Joe295398
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 21, 2021 5:06 am
- Post datetime: 2021-02-20T21:08:31+00:00
- Post Title: Ship Simulator Notes

Hello. I know its been a really long time since this post was made, but I'm still actively trying to mod the game. Is there anyway I could get a laymen's definition of what you're describing?
