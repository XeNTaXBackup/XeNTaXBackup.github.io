## Post #1
- Username: saurav
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-03-08T17:33:29+00:00
- Post Title: Chaos Rings 3 mvgl

Here is a script to extract these .mvgl archives.


```
#quickbms script by chrrox
#http://www.chaosrings.com/3/
comtype doboz
IDSTRING "MDB1"
get COUNT1 short
get COUNT2 short
get FILES long
get BASE long
get ARCHIVE_SIZE long

for i = 0 < COUNT1
	get UNK01 short
	get UNK02 short
	get UNK03 short
	get UNK04 short
	putarray 0 i UNK01
	putarray 1 i UNK02
	putarray 2 i UNK03
	putarray 3 i UNK04
next i

for i = 0 < COUNT2
	getdstring EXT 4
	getdstring NAME 0x3C
	putarray 4 i NAME
	putarray 5 i EXT
next i

for i = 0 < FILES
	get OFFSET long
	math OFFSET += BASE
	get SIZE long
	get ZSIZE long
	putarray 6 i OFFSET
	putarray 7 i SIZE
	putarray 8 i ZSIZE
next i

for i = 0 < COUNT1
	getarray VAR1 1 i
	if VAR1 != 0xFFFF
		getarray NAME 4 i
		getarray EXT 5 i
		if EXT == "img "
		    set EXT string "pvr"
		endif
		string NAME += "."
		string NAME += EXT
		getarray OFFSET 6 VAR1
		getarray SIZE   7 VAR1
		getarray ZSIZE  8 VAR1 
		if ZSIZE == SIZE
			log NAME OFFSET ZSIZE
		else
			clog NAME OFFSET ZSIZE SIZE
		endif
	endif
next i

```
## Post #2
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2015-03-08T18:38:27+00:00
- Post Title: Chaos Rings 3 mvgl

I hope that's sweat...
## Post #3
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2015-03-09T03:00:35+00:00
- Post Title: Chaos Rings 3 mvgl

DAMN!!! you are god !!! thank you soo muchXD
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2015-03-09T04:05:51+00:00
- Post Title: Chaos Rings 3 mvgl

that's what i call false advertising LMAO!
## Post #5
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-03-11T11:17:44+00:00
- Post Title: Chaos Rings 3 mvgl

Hi 
Here is importer for rigged and textured characters (files like c101,c127....) from this game.
It requires Blender version 249b and Python 2.6.6.
How to use:
1.run Blender249.blend
2.in Blender Text Window press alt+p and select:
- geom file for textured meshes
- skel file - for skeleton
Make sure there is "images" folder in geom files folder.
The script use PVRTexToolCLI.exe for convert images.

Update 2015-03-12
[http://www.mediafire.com/download/oc7uu ... -12%5D.zip](http://www.mediafire.com/download/oc7uub6xq7uab7w/Blender249%5BChaosRing%5D%5BAndroid%5D%5Bgeom%5D%5B2015-03-12%5D.zip)
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-03-11T22:22:16+00:00
- Post Title: Chaos Rings 3 mvgl

instead of the if statement on uv's you could use

```
                        f.seek(mshInfo[17] + fvfList[c][5] + (b * mshInfo[2]), 0)
                        uArray.append( abs(struct.unpack("h",f.read(2))[0]) / 1024.0)
                        vArray.append( (struct.unpack("h",f.read(2))[0] / 1024.0) + 1 )
```


and i noticed.

```
                        f.seek(mshInfo[17] + fvfList[c][5] + (b * mshInfo[2]), 0)
                        normal = struct.unpack("3H",f.read(6))
                        normalArray.append(om.MFloatVector(normal[0] / 0xFFFF, normal[1] / 0xFFFF, normal[2]/ 0xFFFF))
```
## Post #7
- Username: Deary5
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 21, 2014 4:39 pm
- Post datetime: 2015-08-16T11:10:23+00:00
- Post Title: Chaos Rings 3 mvgl

Can you teach me how to rig models from Chaos rings? And how to use this script and what app to use this script?
## Post #8
- Username: Farrent0
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 30, 2014 10:52 pm
- Post datetime: 2015-08-16T16:02:59+00:00
- Post Title: Chaos Rings 3 mvgl

for the archive you need quickbms to run chrrox's script.
Blender, Python, PVRTexToolCLI it's needed for import characters, and already rigged.
## Post #9
- Username: Deary5
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 21, 2014 4:39 pm
- Post datetime: 2015-08-16T23:18:20+00:00
- Post Title: Chaos Rings 3 mvgl

Btw,what file i use to get the model? I have download apk and obb file,which file should I export?
## Post #10
- Username: Deary5
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 21, 2014 4:39 pm
- Post datetime: 2015-08-16T23:21:37+00:00
- Post Title: Chaos Rings 3 mvgl

@Farrent0: If you don't mind,can you teach me from the beginning until I managed to export it? I really want to learn rig Chaos Rings models
## Post #11
- Username: Farrent0
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 30, 2014 10:52 pm
- Post datetime: 2015-08-17T15:09:47+00:00
- Post Title: Chaos Rings 3 mvgl

run chrrox's script to extract obb file, then you can follow Szkaradek123's guide.
## Post #12
- Username: Deary5
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 21, 2014 4:39 pm
- Post datetime: 2016-05-12T22:42:21+00:00
- Post Title: Chaos Rings 3 mvgl

> Reply from Farrent0
>
> run chrrox's script to extract obb file, then you can follow Szkaradek123's guide.

Well it's been a long time since i last log in. But i still trying to ripping this models. But do you know where is Szkaradek123's guide? It seem i can't found it and how do i run chrrox's script to extract obb file?
## Post #13
- Username: MrYoso
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 01, 2016 12:52 am
- Post datetime: 2016-09-30T17:49:21+00:00
- Post Title: Chaos Rings 3 mvgl

How can I repack the modified files back to mvgl?
## Post #14
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-28T21:09:34+00:00
- Post Title: Chaos Rings 3 mvgl

trying to load c101 char: skeleton works fine but geom gives me this:

```
======================================================================
Traceback (most recent call last):
  File "chaosring3.py", line 167, in openFile
    parser=Parser()
  File "chaosring3.py", line 151, in Parser
    geomParser(filename,g)
  File "chaosring3.py", line 75, in geomParser
    boneMap=g.i(mesh.A[0])
  File "C:\Program Files (x86)\Blender Foundation\Blender249b\newGameLib\myLibra
ries\binaresLib.py", line 100, in i
    data=struct.unpack(self.endian+n*'i',self.inputFile.read(n*4))
struct.error: unpack requires a string argument of length 4608
```
any suggestions?
## Post #15
- Username: ofthriceandmen
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Dec 01, 2018 1:08 am
- Post datetime: 2018-11-30T17:15:34+00:00
- Post Title: Chaos Rings 3 mvgl

I've been trying to use this for Digimon Story Cyber Sleuth Hacker's Memory (specifically, the Japanese Anime Sound Edition, there is a hidden english mode that isn't accessible that I'm working on)
This game uses the same file formats as Chaos Rings 3.
This quickbms script did unpack the mvgl after I decrypted it with psvpfsparer. 
After that, I deleted 4 folders and modified nothing else.
I tried to repack the files using the same quickbms script but it gave me the same error for every files: signature of offset ___________ is doesn't match the one expected by the script (it wasn't the same offset for them all).

Why did this happen? I didn't modify any of the files so why are they all incorrect? 

Before this I tried replacing some jp image files with en ones but the eng ones were bigger than the jp ones, which is why i wanted to repack the whole thing any of the 4 non-English folders, so I didn't have to worry about replacing them with files that were too big. I believe either approach would work to my purposes but I get either to repack, albeit for different reasons.


If I can't solve this problem I can't do this project.

Thanks.
## Post #16
- Username: zgmfx14a
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Oct 19, 2019 8:11 am
- Post datetime: 2019-12-16T15:50:23+00:00
- Post Title: Re: Chaos Rings 3 mvgl

See the code in your forum can extract mvgl format file, how can I use it to extract Digimon Story: Cyber Sleuth Hacker's Memory（PC）.Can you tell me? I'm very interested in the model of the game and hope to get your help.I made the code in. BMS format, but the prompt failed to extract.Can you tell me how to use this code?
## Post #17
- Username: zgmfx14a
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Oct 19, 2019 8:11 am
- Post datetime: 2019-12-17T08:51:58+00:00
- Post Title: Re: Chaos Rings 3 mvgl

- open input file D:\game\Extract\file\Original file\DSDB.steam.mvgl
- open script D:\game\Extract\quickbms\SMBBForceUnpacker.bms
- set output folder D:\game\Extract\file\Unpack file

  offset           filesize   filename
--------------------------------------

- signature of 4 bytes at offset 0x0000000000000000 doesn't match the one
  expected by the script:

  this one: "`"
  0c 92 8d 60                                       ...`

  expected: "MDB1"
  4d 44 42 31                                       MDB1

- 0 files found in 0 seconds
  coverage file 0     0%   4          2682654775 . offset 0000000000000004

Press ENTER or close the window to quit

I used this code to extract the model but failed. Above is the error message. Can you tell me how to extract the  Digimon Story Cyber Sleuth Hacker's Memory（PC） model? 
The file format is. mvgl.
## Post #18
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-01-26T06:39:11+00:00
- Post Title: Re: Chaos Rings 3 mvgl

I found this:

[https://zenhax.com/viewtopic.php?t=12967](https://zenhax.com/viewtopic.php?t=12967)

About the Steam/PC version of Digimon Cyber Sleuth, but to really know how it works.
Or if someone can update the BMS too, because as

> Reply from zgmfx14a ↑Tue Dec 17, 2019 4:51 pm at Tue Dec 17, 2019 4:51 pm
>
> 
- open input file D:\game\Extract\file\Original file\DSDB.steam.mvgl
- open script D:\game\Extract\quickbms\SMBBForceUnpacker.bms
- set output folder D:\game\Extract\file\Unpack file

  offset           filesize   filename
--------------------------------------

- signature of 4 bytes at offset 0x0000000000000000 doesn't match the one
  expected by the script:

  this one: "`"
  0c 92 8d 60                                       ...`

  expected: "MDB1"
  4d 44 42 31                                       MDB1

- 0 files found in 0 seconds
  coverage file 0     0%   4          2682654775 . offset 0000000000000004

Press ENTER or close the window to quit

I used this code to extract the model but failed. Above is the error message. Can you tell me how to extract the  Digimon Story Cyber Sleuth Hacker's Memory（PC） model? 
The file format is. mvgl.

Says, it gives that error.
