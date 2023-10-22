## Post #1
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-08-29T01:45:50+00:00
- Post Title: Help with Broken Sword Directors Cut  .dat file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-08-29T03:06:47+00:00
- Post Title: Help with Broken Sword Directors Cut  .dat file

quickbms script

```
get files long
for i = 0 < files
get name1 long
get offset long
get size long
string name1 + .ogg
log name1 offset size
next i

```
## Post #3
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-08-29T04:23:28+00:00
- Post Title: Help with Broken Sword Directors Cut  .dat file

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2010-08-29T06:17:04+00:00
- Post Title: Help with Broken Sword Directors Cut  .dat file

I had a look @ all of these dat files a while back and wrote a qbms script which works for all files from the revolution software games on apple handheld hardware:

```
getdstring DATT 4
get FILES long

for i = 0 < FILES
	get CRCFN long
	get OFFSET long
	get SIZE long

	if DATT == HSFS
		get ZSIZE long
		set DATA 1
	elif DATT == AUFS
		set DATA 2
	elif DATT == SPCH
		set DATA 2
	endif

	set FTYPE ""
	set NAME string CRCFN
	if DATA == 2
		log MEMORY_FILE OFFSET SIZE
		getdstring FTYPE 4 MEMORY_FILE
	endif
	if FTYPE == OggS
		string NAME += .ogg
	endif

	if DATA == 1
		clog NAME OFFSET ZSIZE SIZE
	elif DATA == 2
		log NAME OFFSET SIZE
	endif
next i

```

should work without probems, though lemme know if you do have any at all
## Post #5
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-08-30T13:47:39+00:00
- Post Title: Help with Broken Sword Directors Cut  .dat file

Very thanks. This is very useful for me!
## Post #6
- Username: sEri
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 26, 2009 8:02 pm
- Post datetime: 2010-08-31T01:36:23+00:00
- Post Title: Help with Broken Sword Directors Cut  .dat file

RENIKRILL, thank you very much for your script  
But I still got some problems  
For example, the bs1dc.dat which is zlib compressed, has thousands of files.
But we can't know the name or extension of each file.
That means, what we got are only some unknown binary files.
Some start with "BM" but is not .bmp file, some start with "SPRA" that I don't familiar with.

There're almost 3000 files, it's hard for me to analysis them one by one.
I think there may be another file which contains some important info like the name or type of each file.
Would you please take a look?  Very thanks

Regards.
## Post #7
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-09-06T17:28:10+00:00
- Post Title: Help with Broken Sword Directors Cut  .dat file

Here' my DAT extractor/replacer tool.
(Mainly for the "bs1dc.dat" file, but works with the other .dat files too)

During extraction it groups the files to subdirs:

DE=german language files
ES=spanish language files
FR=french
IT=italian (it's possible that I mixed some files with the spanish files)
UK=UK english
US=US english
EN=UK or US
XX=other, useless files

The language files are automatically converted to editable text files.
## Post #8
- Username: elitetum
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 03, 2011 4:28 pm
- Post datetime: 2011-11-03T08:41:43+00:00
- Post Title: Help with Broken Sword Directors Cut  .dat file

> Reply from bacter
>
> Here' my DAT extractor/replacer tool.
(Mainly for the "bs1dc.dat" file, but works with the other .dat files too)

During extraction it groups the files to subdirs:

DE=german language files
ES=spanish language files
FR=french
IT=italian (it's possible that I mixed some files with the spanish files)
UK=UK english
US=US english
EN=UK or US
XX=other, useless files

The language files are automatically converted to editable text files.

Sorry for digging out this old post, but I currently work on those files.

@bacter:  Can't see any link in your post!?? You still have that extractor tool?


I am having the same problem as sEri. Getting hunderds of binary files and don't know exactly how to use them. Many of them also start with FACE8. My maingoal was to extract sprites/gfx of the game. Any ideas how to proceed? Any help is appreciated a lot!!
