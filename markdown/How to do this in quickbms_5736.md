## Post #1
- Username: Ghostt
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 19, 2009 11:19 pm
- Post datetime: 2011-01-09T08:52:41+00:00
- Post Title: How to do this in quickbms?

My structure goes like this:


```
	tableoffset (file/foldertable offset)
	numfiles (number of files)
filedata	
	data (size = sizecomp)
	name (file/folder name, not full path)
table
	id
	type (folder / file)
	abovefolder (points to a folderid or 0 if it's in the root)
	start (dataoffset)
	sizecomp (size compressed)
	sizedecomp (size decompressed)

```


The name of the file / folder would be on the offset (start+sizecomp)

A worked out example would be:

```
FILEDATA:
-------------

offset 	data	(offset+sizecomp)	name
50		0xdata		50				system
100		0xdata		100				sound
170		0xdata		400				magic.mp3
524		0xdata		1284				config.cfg



TABLE:
--------

ID	TYPE	 ABOVE	OFFSET	SIZECOMP	SIZEDECOMP
					
1	folder	 0		 50		0			0
2	folder	 1		100		0			0
3	file		 2		170		230		340
4	file	 	1		524		760		1520
					

archive extracted:
---------------------				
system					
system/sound					
system/sound/magic.mp3					
system/config.cfg					


```


I have no idea how to create a loop like this in quickbms..
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-09T18:14:18+00:00
- Post Title: How to do this in quickbms?

upload a sample! and checkout quickbms.txt - which does a great job explaining all the commands!

savepos VAR # save current position - like FTell()
math VAR += VAR # calculate offsets
also LOG
and FOR .. NEXT:

```
  # ...
next i

```
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-01-12T22:42:02+00:00
- Post Title: How to do this in quickbms?

you need to use a function recursively.
this type of archives is ever a pain.
