## Post #1
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-04-28T16:31:19+00:00
- Post Title: Gameloft Custompak (obb unpacker)

obb files from Android games are supposedly plain zip archives, but I've come across one from GT Racing 2 that doesn't look like a zip. I started analyzing it and below is a quickbms script that should extract it.

```
# script for QuickBMS http://quickbms.aluigi.org
# tested with GT Racing 2 and The Dark Knight Rises .obb archives

endian big

get DUMMY long
get DATA_OFF long
get NAMES_OFF long
get FILES long
get BNAME basename

savepos LASTFILE
for i = 0 < FILES
	goto LASTFILE
	get OFFSET long	#relative to file start
	get SIZE long
	get NAME_OFF long	#relative to NAMES_OFF
	get DUMMY long
	savepos LASTFILE

	math NAME_OFF += NAMES_OFF
	goto NAME_OFF
	get NAME string
	set FNAME string BNAME
	string FNAME += /
	string FNAME += NAME

	log FNAME OFFSET SIZE
next i
```
## Post #2
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-07-23T13:23:52+00:00
- Post Title: Gameloft Custompak (obb unpacker)

It's actually a [Gameloft CustomPak](http://forum.xentax.com/viewtopic.php?f=32&t=10794). You might meet some encryption on the filenames and/or file contents.
## Post #3
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-23T14:54:13+00:00
- Post Title: Gameloft Custompak (obb unpacker)

Thanks for the info. I renamed the script and made a few changes to get rid of that quickbms warning.

I tested it with The Dark Knight Rises for Android and it seems to extract both .obb and .gla archives.
## Post #4
- Username: weisuolong0
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 20, 2014 12:41 pm
- Post datetime: 2014-08-21T16:31:10+00:00
- Post Title: Gameloft Custompak (obb unpacker)

tankyou lz

how can you do this script step by step?
where shall i to study  meathod of to extract obb bat and any other data files?
sorry ,my english is poor ..
## Post #5
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-09-14T16:24:30+00:00
- Post Title: Gameloft Custompak (obb unpacker)

If you want to extract CustomPaks, use the CustomPak extractor. It's the most straightforward way of getting the files out. Otherwise, get comfy with a hex editor and study the format.
