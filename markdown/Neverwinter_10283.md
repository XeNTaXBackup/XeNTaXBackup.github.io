## Post #1
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2013-03-29T06:56:20+00:00
- Post Title: Neverwinter

im looking at the files from the neverwinter beta. it uses the same engine as star trek online so I extracted the pigg archives without a problem.  the images are .wtex like sto but don't seem to be dds in there.  the header of the wtex is also larger in these (160 bytes) to the dds wtex's 36 bytes header.


does anyone have any ideas?

I attached a dds one and one of the mystery ones.
[images.zip](https://xentaxbackup.github.io/file/6299_images.zip)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-29T10:01:58+00:00
- Post Title: Neverwinter

> Reply from surix
>
> im looking at the files from the neverwinter beta. it uses the same engine as star trek online so I extracted the pigg archives without a problem.  the images are .wtex like sto but don't seem to be dds in there.  the header of the wtex is also larger in these (160 bytes) to the dds wtex's 36 bytes header.


does anyone have any ideas?

I attached a dds one and one of the mystery ones.

This looks compressed....
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-03-29T11:20:49+00:00
- Post Title: Neverwinter

Dyn_Playercostume_Species_Drow_F_01.Wtex is  a plain dds file after you delete the first 0x24 bytes
## Post #4
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2013-03-29T17:52:55+00:00
- Post Title: Neverwinter

Yeah i included one of the dds ones, and one of the other ones.


I am mildly familiar with quickbms but how would i go about testing compression on it?  would i choose a few offsets i think might be the start of the compressed part and try the algos there? compression is not my strong area so i dont know what clues to look for in picking the offsets
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-03-29T18:02:33+00:00
- Post Title: Neverwinter

having a few compressed files would help in testing.
you need the compscan2.bms and compscan2.bat file to test for compression.
## Post #6
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2013-03-29T18:08:51+00:00
- Post Title: Neverwinter

thanks chrrox. i have those but i'm not sure where to start to test for compression,  the header is not compressed being it has the size of the header, size of file, width and height of image and some other 32 bit integers in it.

im not home right now but tonight ill upload some more images
## Post #7
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2013-03-30T03:19:56+00:00
- Post Title: Neverwinter

I added some more examples


here's what I do know about the files


[images2.zip](https://xentaxbackup.github.io/file/6301_images2.zip)
## Post #8
- Username: GlassZeppelin
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Feb 07, 2010 9:20 am
- Post datetime: 2013-04-05T22:11:23+00:00
- Post Title: Neverwinter

It seems like these files may be compressed with crunch -- [http://code.google.com/p/crunch/](http://code.google.com/p/crunch/) and [http://code.google.com/p/crunch/wiki/TechnicalDetails](http://code.google.com/p/crunch/wiki/TechnicalDetails)

The GameClient.exe even makes mention of this header file: [http://code.google.com/p/crunch/source/ ... n_decomp.h](http://code.google.com/p/crunch/source/browse/trunk/inc/crn_decomp.h)

I tested it out and compressing images to the .crn format results in a header of 48 78 00 and other data that looks similar to the Neverwinter textures, but I couldn't quite get the Neverwinter files to decompress. Perhaps someone else will have better luck?
## Post #9
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-05-05T19:52:16+00:00
- Post Title: Neverwinter

First of all, I love this game, and, ofcourse was interested in the models 

I used this to unpack the hogg file: [Download here](http://mod.gib.me/champions/bin-rev5.zip)

To use it: 
Gibbed.Champions.Bacon.exe <input hogg file> <output directory>

The exe and files are .net code, and can be decompiled with Telerik's Decompiler

In the textures.hogg, there are a lot of htex and wtex files, don't know how to decompile them yep, hopefully we find something shortly 

Keep up the good works guys!

T.
## Post #10
- Username: GlassZeppelin
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Feb 07, 2010 9:20 am
- Post datetime: 2013-05-15T21:21:52+00:00
- Post Title: Neverwinter

Here's some more info on what happened to the textures -- this post is for STO but details the same new .wtex stuff as in Neverwinter:

[http://sto-forum.perfectworld.com/showp ... ostcount=1](http://sto-forum.perfectworld.com/showpost.php?p=9825131&postcount=1)

I am still not able to decompress the .wtex files into an editable format, though...
## Post #11
- Username: clairegrube
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-09-02T06:55:35+00:00
- Post Title: Neverwinter

Upgrade to Noesis v4.085 before using this script or it won't work. (I had to modify the crunch decoder to handle their changes, and on top of that their DDS files are badly-formatted and don't have the correct flags)

```

def registerNoesisTypes():
	handle = noesis.register("Perfect World Texture", ".wtex")
	noesis.setHandlerTypeCheck(handle, wtexCheckType)
	noesis.setHandlerLoadRGBA(handle, wtexLoadRGBA)

	return 1

def wtexCheckType(data):
	if len(data) < 40 or (noeUnpackFrom("i", data, 32)[0]>>8) != 0x355854:
		return 0
	return 1

def wtexLoadRGBA(data, texList):
	dataOfs = noeUnpack("i", data[:4])[0]
	if noeUnpackFrom("i", data, dataOfs)[0] == 0x20534444: #dds
		print("Loading as DDS.")
		texture = rapi.loadTexByHandler(data[dataOfs:], ".dds")
	else:
		print("Loading as CRN.")
		texture = rapi.loadTexByHandler(data[dataOfs:], ".crn")

	if texture is None:
		return 0

	texList.append(texture)
	return 1

```
## Post #12
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2014-02-09T22:38:03+00:00
- Post Title: Neverwinter

Is there a way to get the .htex textures as well? Or are they even textures, at least the sizes are comparable?
## Post #13
- Username: Maximvs
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 02, 2016 6:47 am
- Post datetime: 2016-08-01T22:51:31+00:00
- Post Title: Neverwinter

How exactly do you use this ?

To use it: 
Gibbed.Champions.Bacon.exe <input hogg file> <output directory>

Can you please give details info of the procedure? Do I double click it ? ( doesnt work ). Do I drag a .hogg file on it and then it works? ( doesn't work for me ). Or do I drag the Bacon.exe on a file and then it works ? ( doesn't work for me ) or do I have to open my CMD and type stuff in there? If so, can you give an example of that, please?
## Post #14
- Username: Melecon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 12, 2016 5:53 am
- Post datetime: 2017-03-08T03:07:07+00:00
- Post Title: Neverwinter

Run it from the command line.
## Post #15
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-04-18T16:23:30+00:00
- Post Title: Neverwinter

Any progress with Neverwinter?
I need some models, but noob in command line or scripting
## Post #16
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-11-15T18:42:01+00:00
- Post Title: Re: Neverwinter

I get models in MSET files and textures in WTEX. But I an open only normal maps, colormaps give me error in all software (I use Irfran view and Nvidia tools).
When I use wtex to dds tool it have same result
Do someone know how to get textures normally?
I use google, but have only dead links or not-working-tools (have error when open dds too)

But what tools can convert MSET to fbx?
I found Mset to obj tools only. It's working so.
[Снимок3.PNG](https://xentaxbackup.github.io/file/23038_Снимок3.PNG)
