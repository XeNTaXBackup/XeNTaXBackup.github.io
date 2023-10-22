## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-02-02T17:55:29+00:00
- Post Title: The Last of Us Model/Animation Tools (PS4)

A set of tools for loading and exporting models/animations from The Last of Us Remastered. It has great model support now, including automatic texture mapping and map tool. Animation support is not perfect but improved a lot.

Animation Tool



Models
I am releasing a new version of the model tool. It has material support like the map tool, and also lot of bug fixes.



How to use

Load

PAK: Loads models (skinned) in selected PAK file.
Textures will be applied automatically if they are in the same folder. For exporting textures use TLOU Texture Editor
If the skeleton is found inside the pak file it will be loaded. If not, another file selection will appear for choosing the skeleton PAK file. (optional)
You can load multiple models. Everything will stay until you clear the scene.

Export

NUX: Exports the model in custom binary format (.nux), intended to be loaded by Noesis. Noesis script for this format : NUX Script
Models will the grouped by their original PAK file. So separate NUX for every PAK.
Like with the tool, the textures need to be in the same folder as NUX, for Noesis to load them.
Note  : Models will be exported into the folder Export.
Download : [https://www.mediafire.com/file/znv85uml ... 3.rar/file](https://www.mediafire.com/file/znv85umlezjx8mi/TLOUViewer_V2_U3.rar/file)

Map Tool
[viewtopic.php?p=161587#p161587](https://forum.xentax.com/viewtopic.php?p=161587#p161587)

Animations
Animation support works much better than before, but it still has problems that I am aware of. Don't bother reporting broken animations.



How to use

Load

NUX: Loads models in selected NUX file. This is the exported model that you get from TLOUViewer.
Textures will be applied automatically if they are in the same folder. Only diffuse texture as this is just for preview purposes. (optional)
You can't load multiple models.
Animation (PAK/STM):Loads animations inside the selected PAK or STM files.
You can cycle through animations using left/right arrow keys.
Note  : If you are not seeing any animations being played after selecting the PAK file, there may be two reasons. You have selected a wrong animation file, meaning the animations doesn't match with the model loaded (most likely reason). Or none of the animations in that file are supported (less likely).

Export

NUX: Exports the animation in custom binary format (.nux), intended to be loaded by Noesis. Noesis script for this format : NUX Script
Note  : Animations will be exported into the folder Export.
Download : [https://www.mediafire.com/file/n0eoa7qr ... 1.rar/file](https://www.mediafire.com/file/n0eoa7qrf9jmq8l/TLOUAnimViewer_V2_U1.rar/file)

Textures
If you are also interested in getting the textures, check out my texture tool : [TLOU Texture Editor](https://forum.xentax.com/viewtopic.php?p=161585#p161585)

Credits
daemon1 - for figuring out all of the model data and explaining it really well with videos
luxox18 - for finding out data manually, so that I can use them as a reference
## Post #2
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2017-02-13T14:18:50+00:00
- Post Title: The Last of Us Model/Animation Tools (PS4)

wow ,this is realy awsome!!
## Post #3
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2017-02-16T01:05:44+00:00
- Post Title: The Last of Us Model/Animation Tools (PS4)

Will this work on uncharted 4?
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-02-16T01:19:08+00:00
- Post Title: The Last of Us Model/Animation Tools (PS4)

> Reply from Jaydenthetank
>
> Will this work on uncharted 4?
I don't know, it might work if the file structure is identical with the last of us. I don't have the uncharted files, so didn't have the chance to test them.
## Post #5
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2017-02-16T05:53:02+00:00
- Post Title: The Last of Us Model/Animation Tools (PS4)

Just curious because I don't think anyone has ripped ps4 models before
## Post #6
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2017-02-16T10:21:26+00:00
- Post Title: The Last of Us Model/Animation Tools (PS4)

> Reply from Jaydenthetank
>
> Just curious because I don't think anyone has ripped ps4 models before
[https://www.youtube.com/watch?v=-Y1bigdq-6o&t](https://www.youtube.com/watch?v=-Y1bigdq-6o&t)
## Post #7
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-18T23:10:29+00:00
- Post Title: The Last of Us Model/Animation Tools (PS4)

> Reply from akderebur
>
> Jaydenthetank wrote:Will this work on uncharted 4?
I don't know, it might work if the file structure is identical with the last of us. I don't have the uncharted files, so didn't have the chance to test them.

Uncharted 4 is something I started looking into. But the whole game is just one single pak file, so I suspect it's not similar at all. EDIT: I found out it's because PS4 games are encrypted, and still nobody knows how to unencrypt them (which begs the question how you unencrypted this game?)

I am curious if you can release the source code or futher explain the findings, as I'm sure it would help with my own investigations, the more we can pool information, the farther we can go.
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-02-19T01:43:41+00:00
- Post Title: The Last of Us Model/Animation Tools (PS4)

> Reply from volfin
>
> Uncharted 4 is something I started looking into. But the whole game is just one single pak file, so I suspect it's not similar at all. EDIT: I found out it's because PS4 games are encrypted, and still nobody knows how to unencrypt them (which begs the question how you unencrypted this game?)
I did not, luxox is the guy you are looking for  

He released some character files in this thread : [viewtopic.php?f=10&t=15801](http://forum.xentax.com/viewtopic.php?f=10&t=15801)
## Post #9
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-19T05:55:43+00:00
- Post Title: The Last of Us Model/Animation Tools (PS4)

[out]
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-02-19T07:01:01+00:00
- Post Title: The Last of Us Model/Animation Tools (PS4)

[well, I've been told, my guess is wrong for PS4, does apply for PS3 models only]

Guess, it's also a matter of Sony's edge compression:
[viewtopic.php?f=16&t=12070&p=99284#p99284](http://forum.xentax.com/viewtopic.php?f=16&t=12070&p=99284#p99284)

Only tool I know (so far) that can handle it is Noesis:
rapi.rpgCommitTriangles(edgeDecomp, noesis.RPGEODATA_USHORT, indexCount, noesis.RPGEO_TRIANGLE, 1)

But detailed informations are kept secret.
That's sad because more infos could help with Gran Turismo 6 Models, too.

I tend to ignore edge decompression, because it's so boring. I remember fiddling around with Sony's edge SDK (or something like that, not sure). 
Just a waste of time and life...
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-19T11:32:39+00:00
- Post Title: The Last of Us Model/Animation Tools (PS4)

> Reply from akderebur
>
> I did not, luxox is the guy you are looking for

luxox will not be able to help you. Hes just the guy who delivers decrypted files from the scene. He can't decrypt them.
## Post #12
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-02-19T12:49:22+00:00
- Post Title: The Last of Us Model/Animation Tools (PS4)

> Reply from Wobble
>
> Viewers and characters are nice, but as a coder, we would like to see some discussion on formats, algorithms, or code.
There is no real algorithm that can bring you further, it is just like pattern matching program designed specifically for The Last of Us pak files. Let me explain how the program works and you will see what I mean.

The way I did it was I basically opened bunch of character files in the hex editor and tried to find out recurring patterns in each file. Here is an example for getting vertex/index count and index offset.

There are 4 patterns for this (in hex) :

03 00 00 00 00 00 00 00 00 00 00 00
04 00 00 00 00 00 00 00 00 00 00 00
05 00 00 00 00 00 00 00 00 00 00 00
06 00 00 00 00 00 00 00 00 00 00 00

Also after 44 bytes from the start of the above patterns, there should be this pattern : FFFFFFFF.

So lets say the file contains 10 meshes. The program starts and searches for these patterns in the file and when there is a match it adds the offset to a list. When it is done there are like 3000 (I am making up numbers for this example) records in the list. It then goes through the list, for each offset it advances 44 bytes and checks if there is FFFFFFFF. If it finds out that pattern, it adds that offset (end of FFFFFFFF) – 56 bytes to a new list. The reason for offset - 56 bytes is because the data we are looking for actually starts there, again something that I found out looking at the hex editor. In the end that list has 10 records with correct offsets.

Now we can read the actual data. The program goes through each offset in the new list : 

binary reader’s position is set to the current offset
first integer read = vertex count
second integer read = index count
advance 28 bytes
integer read  = index offset

I think at this point you can see that the program is a product of binary search and pattern matching and that it doesn’t use a proper way to find data. It is like a bruteforcer for finding data in tlou files only. I find it hard to believe that anyone can develop it further to let’s say work with uncharted 4 files. If the file structure is identical, it will work. If not you would need new patterns and it would be a whole new program in that case.

The program as it is contains more code for graphics and ui programming than the actual code for reading the pak file and it is a bit messy . If you want I can strip the Unity stuff and share the part related to pak files.

> Reply from shakotay2
>
> Guess, it's also a matter of Sony's edge compression
Mesh data (index, vertex, uv) is not compressed in the ps4 files. Only the ps3 version has edge compression.
## Post #13
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-19T23:37:24+00:00
- Post Title: The Last of Us Model/Animation Tools (PS4)

[out]
## Post #14
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-02-20T01:22:37+00:00
- Post Title: The Last of Us Model/Animation Tools (PS4)

ps4 developers are not using the edge compression anymore. Instead are using swizzled textures  and models with same structure as PC with little endian data. (nothing compressed)

in this game specifically the vertex data and the uv data are separated and all faces start with 00 00 01 00 02. 

not all games can be decrypted, for the moment is possible in games with firmware 1.76 (2013 - 2014 games)

oh, and about how to obtain decrypted games.. I just have a contact in the ps4 scene
## Post #15
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-20T10:14:09+00:00
- Post Title: The Last of Us Model/Animation Tools (PS4)

[out]
## Post #16
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-02-20T13:36:26+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

The format for the pkg files in tlou is nearly identical to the format on ps3 structure wise.
## Post #17
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-20T18:47:58+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

it's probably a flag for something, but specifically it's a programmer's inside joke:
[https://en.wikipedia.org/wiki/Hexspeak](https://en.wikipedia.org/wiki/Hexspeak)
## Post #18
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-20T23:07:05+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #19
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-21T03:57:55+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

the PS3 pkg format is described here:
[http://www.psdevwiki.com/ps3/PKG_files](http://www.psdevwiki.com/ps3/PKG_files)

The source code to a PS4 Pkg unpacker is here:

[https://github.com/Keyaku/ps4tools](https://github.com/Keyaku/ps4tools)

The problem is, the encryption. The PS4 tool above can only decrypt a few basic files using RSA keys. but the rest uses a different encryption. It's made up of PFS blocks. [http://www.psdevwiki.com/ps4/PFS](http://www.psdevwiki.com/ps4/PFS)
## Post #20
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-21T04:50:55+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #21
- Username: Wobble
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-02-21T10:39:57+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[viewtopic.php?f=16&t=10502](http://forum.xentax.com/viewtopic.php?f=16&t=10502)
## Post #22
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-21T12:09:53+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #23
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-21T17:35:41+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

pretty sure that's what the model viewer/extractor of this thread does.
## Post #24
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-21T22:53:36+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #25
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-22T00:13:52+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

Well if it's anything like the PS3 games I've worked on, they do not include vertex/face counts anywhere in the model file. Which is why he has to scan for the beginning. To call it a 'format' is a bit misleading, it's closer to a memory image. I know the buffer sizes have to be stored somewhere, but it might be in the main executable code of the game itself, or in the shaders, or only the devs know where. It will be quite  a challenge to accomplish a clean extract.
## Post #26
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-22T04:00:33+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #27
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-22T07:34:51+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #28
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-02-22T08:12:28+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from Wobble
>
>  how you are calculating these offsets to the vertex and index data?
.

Those offsets are not from the beginning of the file, they are from the starting offset of their respective blocks.

In pak files not all of the mesh data is in one place, it is divided into seperate blocks. For example let's say a file has 6 meshes and 3 blocks. It is possible that 3 meshes are in block 1, 2 meshes in block 2 and 1 mesh in block 3. It differs for each file.

So how do you find these blocks? I assume you already checked chrrox's noesis script. Headers and info1 arrays are what you need. Headers [4] tells you how many blocks there are in the file and info1 array has the offset of these blocks. Info1's elements (blocks) are integer arrays with 2 elements, so there are 2 values for each block. Value at index 0 is the starting offset of the block and value at index 1 is the offset you need to advance to reach the next block. I couldn't find any use for index 1 so I will say that you only need the values at index 0.

The program can find the index offset of each mesh and it can also find the different blocks in the file. Only problem is that it doesn't know which mesh belongs to which block. It just tries each offset with every block, trying to find a reasonable data. Maybe you can find a way to get this info.
## Post #29
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-22T12:51:26+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #30
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-24T17:09:55+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #31
- Username: roodythepoo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 28, 2017 6:52 pm
- Post datetime: 2017-03-01T03:52:42+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

This is an excellent tool, thanks!

I am new at this, but how do I view models from Luxox's thread ( [viewtopic.php?f=10&t=15801](http://forum.xentax.com/viewtopic.php?f=10&t=15801) )?  The smaller < 10mb files work fine on the tool, but the 300mb file does not work.

Just not sure how to work the pak files
## Post #32
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-03-03T17:29:08+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from roodythepoo
>
> This is an excellent tool, thanks!

I am new at this, but how do I view models from Luxox's thread ( viewtopic.php?f=10&t=15801 )?  The smaller < 10mb files work fine on the tool, but the 300mb file does not work.

Just not sure how to work the pak files

The viewer works for separate actor50 files  (characters, props etc). That common file is a collection of bunch of stuff from the game and it won't open with this tool. I am even not sure if there are models in it, it contains mostly textures for different models. Even if there is mesh data in it, this tool won't be able to load it.
## Post #33
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-04T08:04:57+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

I wanted to take a look at this.
## Post #34
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-04T21:38:22+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

Finally got the bones working. It took long: almost whole day.
## Post #35
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-03-04T22:17:06+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

nice   , so you're pulling this from original data?
## Post #36
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-03-04T22:21:51+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from daemon1
>
> Finally got the bones working. It took long: almost whole day.

Nice to see that you managed to read the skeleton data. Did you take a look at the animation files?
## Post #37
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-05T05:19:42+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from volfin
>
> nice   , so you're pulling this from original data?
Yes.

> Reply from akderebur
>
> Did you take a look at the animation files?
Not yet.
## Post #38
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-05T05:39:51+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #39
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-05T06:42:49+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from Wobble
>
> You can identity a lot of data in these files, but with all the offsets being screwed up, I find it to be a complete time waster.
That's why I'm here  I can do things nobody else can do. I've seen this many times: first it looks like madness, but then, when you find the answer, it seems so obvious.

p.s. I already found how to fix the offsets.
## Post #40
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-05T21:28:24+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #41
- Username: Wobble
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-05T23:52:32+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

just print this info and it becomes easy to read the file.

```
	bs.seek(info2[1], NOESEEK_ABS)
	for a in range(0, info2[2]):
		info3.append(bs.read(endian + "2HI"))
	#for a in range(0, info2[2]):
	#	print(("0x%0.10X" % info3[a][2]))
	texList = []
	matList = []
	for a in range(0, header[3]):
		bs.seek(info1[a][0], NOESEEK_ABS)
		print(bs.tell())
		info4 = bs.read(endian +  "4I2H")
		info5 = []
		print("Group" + str(a))
		for b in range(0, info4[5]):
			info5.append(bs.read(endian + "4I"))
			#for c in range(0, 4):
			#	print(("0x%0.10X" % info5[b][c]))
		for b in range(0, info4[5]):
			bs.seek(info1[a][0] + info5[b][0], NOESEEK_ABS)
			mainStr = bs.readString()
			#print(mainStr)
			bs.seek(info1[a][0] + info5[b][2], NOESEEK_ABS)
			info6 = bs.read(endian + "8I")
			bs.seek(info1[a][0] + info6[0], NOESEEK_ABS)
			mainStr = bs.readString()
			bs.seek(info1[a][0] + info6[2], NOESEEK_ABS)
			typeStr = bs.readString()
			print(str(b), mainStr, " - ", typeStr, str(info1[a][0] + info5[b][2]))

```
## Post #42
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-06T04:23:36+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from chrrox
>
> just print this info and it becomes easy to read the file.

Oh, it was all in the script? Then I completely can't understand why so many people here was unable to correct the offsets, having all this information.
## Post #43
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-03-06T05:34:05+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

no, that code is new, wasn't in the script.
## Post #44
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-06T12:22:47+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #45
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-06T16:41:48+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

I'm gonna make a free tool to extract models with bones and a new video tutorial explaining how to research such a format. This I think will be interesting, because it will show how one thing leads to another, and how step by step you can explore the whole file.
## Post #46
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-03-06T17:09:59+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

A video tutorial would be great, looking forward to it.
## Post #47
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-06T17:15:58+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

you can watch my other tutorials meanwhile
## Post #48
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-08T18:59:07+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #49
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-09T04:26:40+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[https://www.youtube.com/watch?v=Q-BSLGHZZSs](https://www.youtube.com/watch?v=Q-BSLGHZZSs)

Here's the first part of a tutorial. Its not a complete guide how to convert it, its a short version of a process how 
actually I was researching it. What kind of steps it usually includes and so on.
## Post #50
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-09T08:54:42+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #51
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-09T14:48:33+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #52
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-09T15:46:35+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from Wobble
>
> you should probably using something like, 010 Editor

No. All modern editors lack most essential features, including 010. They are not very usable and uncomfortable.

> Reply from Wobble
>
> two tables.  GEOMETRY_1 is in the 2nd table.  some offsets work, some don't.
All offsets work. You're probably using the data incorrectly. Can you give the exact example of "not working" offset?

What do you mean by "tables"? There are lots of tables, which one do you mean?
## Post #53
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-09T18:53:43+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #54
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-09T20:33:35+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from Wobble
>
> Ok, you asked for it.

No, I only asked for one offset, not the wall of data you typed.

Anyway, I see that you're doing it wrong. You are not using the table from the beginning of the file.
## Post #55
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-09T21:18:54+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #56
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-10T19:39:22+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #57
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-03-10T20:32:35+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from Wobble
>
> No one has access to them, so what's the point?

I guess that question is directed towards me, right?

Actually I made this tool for luxox and myself. He contacted me saying that he managed to get the last of us ps4 files and that he was able to rip some meshes manually. So I thought of making a viewer/exporter to extract the meshes faster from the pak files, because finding each mesh data manually via hex editor is not practical. I decided that I might as well release the program on the off chance that some people also have these files and want to get the models.

Also "no one" is a bit of an overstatement. Clearly some people have access to the files, maybe even more people than you think  I don't think that every script/tool in this forum are used by thousands of people but there is surely a group of people who can use them and find them useful.
## Post #58
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-10T20:39:42+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #59
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-10T20:54:09+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from akderebur
>
> So I thought of making a viewer/exporter to extract the meshes faster from the pak files, because finding each mesh data manually via hex editor is not practical.
Was my tutorial any helpful to you? Do I have to proceed with next parts showing how to extract bones/weights?
## Post #60
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-03-10T21:01:56+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from daemon1
>
> Was my tutorial any helpful to you? Do I have to proceed with next parts showing how to extract bones/weights?

Yes, I found it really helpful. I am not that experienced with finding data in hex, so it gave me a general idea on how to proceed and find the offset tables.

Another video showing how to get the bone positions and weights would be much appreciated. If you have the time of course.
## Post #61
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-10T21:11:41+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from akderebur
>
> it gave me a general idea on how to proceed and find the offset tables
Good, that's what I was hoping to.
## Post #62
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-03-11T02:12:12+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from Wobble
>
> What I mean is, the typical end user can't decrypt or access them.  So, any time spent on this side project, will only benefit a select few.  At this point in time, I see no need for another mesh pak importer, so I'm done with it.  Thanks for all the help.

Well the fact is the importers I make are primarily for my own use, and the fact anyone else has use for them is just a bonus. I'm always glad when others find them useful. But even just one user (me) benefitting is enough for me.    Of course I don't have a profit motive.... that's probably the big difference.
## Post #63
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-11T04:31:40+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #64
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-11T04:33:26+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #65
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-11T04:58:50+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

Asking for donations and charging for commissions are two completely different things. Luxox18 puts out models regardless of whether people donate or not. I managed to extract the files with some guidance from a friend who also has them -- each character has a unique skeleton. I'm sure akderebur and Luxox18 and a number of others have those files, too, it's just whether or not they choose to look into them. Some people don't care about rigs, I do, and I know Daemon1 is a wizard when it comes to these things, so I asked him to look into it because I'm sure plenty of people would love to be able to make use of the files if they have them. Whether you choose to charge is your own thing and I'll be honest, I'll offer to pay someone if they're helping me out and it's eating into their time, but unless you're referring to someone else, then I don't think asking for donations is necessarily wrong, especially if it's to maintain an outdated computer system, or software to continue releasing models for free, which Luxox18 does at least.
## Post #66
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-11T06:49:06+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #67
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-11T07:10:24+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from Wobble
>
> I having nothing against artists from getting paid for their work.  Neither should anyone else criticize me for getting paid for my work either.  End of story.
I should add that the fact you're charging money for your tool greatly decreases the will to help you in your researches. Just a suggestion.
## Post #68
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-11T08:02:14+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from Wobble
>
> I having nothing against artists from getting paid for their work.  Neither should anyone else criticize me for getting paid for my work either.  End of story.

It's not like Volfin or Daemon1 are making tools for massive numbers of people either, "so, any time spent on this side project, will only benefit a select few" anyway. At least for now. IF the tools exist, more people will eventually find them. I've come across tools that a number of people here have made that I've found useful literally YEARS after they were made for maybe one or two people, so what's the difference? 

As I said, you choosing to charge is totally fine, but when you give the impression that you only help when it solely benefits you (monetarily here), and you're involved in a discussion where people are basically doing similar things to yourself, sometimes less, sometimes more, for the benefit of just figuring it out (because of course, others can take that tool or knowledge and apply it to other games if it's there), then I think you kinda do open yourself up to criticism. At least in this instance, because it's basically reading like you opt out of helping here, even though you're really clearly smart enough TO help, because you can't see the benefit, which is obvious, because it's the same as it is in literally every single one of these boards -- some people have access to models/data + some are working on tools. It's not like everyone on this forum has an interest in Last of Us, or really any other game you could choose from here.

Just to be clear, I don't think anyone's genuinely having a go at you, Wobble, but this is how it comes across.
## Post #69
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-11T09:43:17+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #70
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-11T16:13:26+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

Meanwhile here's tutorial part 2. Includes TLoU vs Uncharted 2 part, EDGE decompression and weights. After all, EDGE proved to be different in different games, though, nothing impossible.

[https://youtu.be/VBqYEaqCzxY](https://youtu.be/VBqYEaqCzxY)
## Post #71
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-03-11T16:58:33+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from daemon1
>
> Meanwhile here's tutorial part 2.
Thank you, you made it really easy to understand. I will try to adapt it to code and read the weights programmatically.
## Post #72
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-03-11T18:22:36+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from Wobble
>
> I have nothing against you.  I'm replying to volfin.  He is the instigator.  There has been more than one occasion where he directs remarks like that towards me, and I'm not going to sit here and take it anymore.

Sorry you're upset, but you asked why would people work on this when it 'didn't benefit a large amount of people' and I answered. If you felt it was an attack, that may be your conscience. 

I've never asked for a single dime for what I do, you do. And you have every right to. However, I don't think a paid solution should be the only solution, which is why I said so in the Watchdogs thread, and why I made a free importer. Honestly, whether you had been there or not, I would have made that. It was a game I wanted to support. So don't take it personally.
## Post #73
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-11T23:37:02+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[out]
## Post #74
- Username: Wobble
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-03-14T15:17:03+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

Hey everyone!

On behalf of Xentax's Moderator Team. I regret to inform you that, some posts in this thread are clearly unacceptable and not of nature we want from our Xentax community. 

It seems that, most of these later posts are directed towards Wobble's choice of paid Software distribution. Though I do understand this may frustrate some of you as your work is released for free. Please understand this is not anyone's business and making assumptions as to why someone chose to charge for their Software and making sly digs towards them is unfair. You are free to not use the said Software in question if you feel being charged is unacceptable. Bringing this up in a thread the way it was is appalling behavior. The better way to have done this would be sending a kind PM to Wobble stating your views. To go further, argue, gang up on Wobble with no clear information or respect on his motives incurring public humiliation isn't what you should have done.

If this discussion does not cease, warnings and/or bans may be handed out.
Cheers, Gh0stBlade.
## Post #75
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-14T21:42:26+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

[moved to pm]
## Post #76
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-18T16:04:42+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

The last tutorial part: skeleton [https://www.youtube.com/watch?v=Cwji54Qmpos](https://www.youtube.com/watch?v=Cwji54Qmpos)
## Post #77
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-20T04:25:55+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

Thanks so much for your hard work on these daemon1! Hopefully someone can put together some kind of tool for us plebs to use!
## Post #78
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-03-23T15:35:00+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

I released a new version of the viewer that supports skeleton. You can see the changes in the first post.

Huge thanks to daemon1 for his awesome work with tutorials and for answering my questions.
## Post #79
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-25T09:06:43+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

Thank you SO much for this akderebur!! One thing I've noticed though -- I tried loading the Tommy model, but when I go to add the skeleton, the model doesn't appear at all. However, when I DON'T add the skeleton, I can see the parts of the model. Any suggestions as to what I might need to do here?
## Post #80
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-03-25T10:24:40+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from trexjones
>
> I tried loading the Tommy model, but when I go to add the skeleton, the model doesn't appear at all.

It looks like I made a slight offset mistake which affected some of the models. I fixed it and updated the download link. You should be able to load Tommy fine now.
## Post #81
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-26T04:28:41+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

Worked perfectly! Thanks dude!
## Post #82
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-30T09:37:33+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

Hey guys! I've been going through the models bit by bit and every now and then coming across ones that still present errors -- parts not appearing, models not loading in spite of following the correct skel paths, etc. 

I'm not sure if you've moved on from this, but I can go through and give you a list of files presenting errors if that helps out at all.
## Post #83
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-03-30T10:01:06+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from trexjones
>
> I'm not sure if you've moved on from this, but I can go through and give you a list of files presenting errors if that helps out at all.

Yes, it would be good if you can tell me what files cause the problem.

Also do they load fine without the skeleton or are there still missing meshes?
## Post #84
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-30T10:45:06+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

I'll double check -- but some of them definitely load fine if I don't try to open the corresponding skeletons.
## Post #85
- Username: smasher248
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 14, 2015 9:52 am
- Post datetime: 2017-06-24T21:11:27+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

So has anyone got Ellie with her skeleton, or can someone tell me wher i get the .pak files from?
## Post #86
- Username: mdtarmimi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 15, 2014 3:42 pm
- Post datetime: 2017-10-06T14:34:35+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

Sorry for to interrupt, I just want to ask is there possible to rip model from ps4 game? I know couple guy's from you here were made brilliant tools such ripping pak. file or bin. file from ps3 or PC to get complete file 3d mesh with texture easily for us. But those people outside use the tools with out consider having give a credit to author it self and look shameless to see them around. My point is if there a tools or method to rip ps4 or Xbox One in future please remain the name title reference which group or people to start the project for easy us from who the source came from...
## Post #87
- Username: Skryle
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 09, 2018 5:06 pm
- Post datetime: 2018-04-06T09:17:45+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

you can give a link for download to PS4 TLOU ?
## Post #88
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-06T10:57:48+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from Skryle
>
> you can give a link for download to PS4 TLOU ?
It is against the forum rules. Check psxhax, there are lots of game backups there.
## Post #89
- Username: Skryle
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 09, 2018 5:06 pm
- Post datetime: 2018-04-19T17:01:35+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

s there a new version of the software?
## Post #90
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-21T11:21:59+00:00
- Post Title: Re: Last of Us Model Viewer/Extractor (PS4)

> Reply from Skryle
>
> s there a new version of the software?
Yea, I finally had time to finish it .

I updated the first post, you can find the new download link there. Read "How to use?" section again, as the usage changed slightly for loading the skeleton.

The main focus of the update was map support, but I also fixed the problem, where some of the meshes load distorted. Also when you load the maps, all of the map objects will be placed at the center (just like Uncharted).
## Post #91
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2018-04-21T11:45:57+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

A tool for Gran Turismo 6 would be useful
## Post #92
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-04-24T09:15:34+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Does anybody know where the weapon skel. files are loacted or even named for that matter?

This is the name for the skel. files for charaters the one's i know

For Civilians
civilian-fem-skel-tstrm (Female)
civilian-skel-tstrm (Male)

For Infected
infected-fem-skel-tstrm (Female)
infected-skel-tstrm (Male)

For NPC's
npc-normal-fem-skel-tstrm (Female)
npc-normal-skel-tstrm (Male)

For the kid that appears on second mission
kid-skel-tstrm
## Post #93
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-24T12:23:02+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from Faithfullfaun
>
> Does anybody know where the weapon skel. files are loacted or even named for that matter?
It is also possible that a model doesn't have a seperate skel file and has both meshes and the skeleton in a single pak file. So if you can't find the skel file, try selecting the same pak file again in the skeleton selection dialog.
## Post #94
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-04-24T19:05:42+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

As far as i have seen that mostly only happens with Vehicles and animals

But not weapons 
if i do that then the weapon won't appear
## Post #95
- Username: CreaseInTime
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 13, 2016 11:59 am
- Post datetime: 2018-04-30T21:46:30+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

I can't seem to open hom-house-interior-tstrm.pak, if anyone can could they send me the extracted files?
## Post #96
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-30T22:40:37+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from CreaseInTime
>
> I can't seem to open hom-house-interior-tstrm.pak, if anyone can could they send me the extracted files?
Updated the tool, it loads fine now.


This should also fix some other maps that don't load. Download it from the link in the first post.
## Post #97
- Username: CreaseInTime
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 13, 2016 11:59 am
- Post datetime: 2018-04-30T23:52:34+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Thank you so much!
## Post #98
- Username: imarceldoe
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jan 28, 2016 9:55 pm
- Post datetime: 2018-05-01T04:35:41+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Sorry to ask,

But does anyone know where I can get the pak files/extract them myself?

Thanks.
## Post #99
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-05-04T09:24:08+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Anyone have or know the files from the Left Behind DLC? Been looking into getting at least some of the props from the mall e.g. the American Princess stuff and a few others.
## Post #100
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-04T09:42:21+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from huckleberrypie
>
> Been looking into getting at least some of the props from the mall e.g. the American Princess stuff and a few others.
They are probably inside one of the files from "world-mall.psarc".
## Post #101
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2018-05-12T06:31:26+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

'tess-hair-cloth-tstrm' has broken UVs, mainly the hair mesh.
## Post #102
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-12T06:45:45+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from meganmi
>
> 'tess-hair-cloth-tstrm' has broken UVs, mainly the hair mesh.
Have you tried using "Remake UV"?
## Post #103
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2018-05-12T20:11:36+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from akderebur
>
> meganmi wrote:'tess-hair-cloth-tstrm' has broken UVs, mainly the hair mesh.
Have you tried using "Remake UV"?
Yes, but it comes out even more broken than it was.
## Post #104
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-12T20:23:15+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from meganmi
>
> 
Yes, but it comes out even more broken than it was.
I will take a look when I have the time.

Edit : 

I improved the "Remake UVs" function, it should be able to find the correct UVs now. You can download the updated version from the first post.
## Post #105
- Username: ebross67
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 04, 2016 1:42 am
- Post datetime: 2018-08-03T22:30:00+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Will this tool work on the PS3 .pak files of The Last of Us?
## Post #106
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-03T23:04:44+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from ebross67
>
> Will this tool work on the PS3 .pak files of The Last of Us?
Nope. Use daemon's tool for the ps3 version : [viewtopic.php?f=16&t=16499](http://forum.xentax.com/viewtopic.php?f=16&t=16499)
## Post #107
- Username: cursore
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Mar 06, 2019 9:26 pm
- Post datetime: 2020-03-25T15:30:53+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Is it possible to load maps with all the meshes in the right place and not scattered around like that?
## Post #108
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-25T15:46:30+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from cursore ↑Wed Mar 25, 2020 11:30 pm at Wed Mar 25, 2020 11:30 pm
>
> 
Is it possible to load maps with all the meshes in the right place and not scattered around like that?

Yes, it is possible actually. I was working on a map tool, but never had the chance to release it. Maybe I can post it in the upcoming days.
## Post #109
- Username: cursore
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Mar 06, 2019 9:26 pm
- Post datetime: 2020-03-25T16:01:57+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from akderebur ↑Wed Mar 25, 2020 11:46 pm at Wed Mar 25, 2020 11:46 pm
>
> 
cursore wrote: ↑Wed Mar 25, 2020 11:30 pm
Is it possible to load maps with all the meshes in the right place and not scattered around like that?


Yes, it is possible actually. I was working on a map tool, but never had the chance to release it. Maybe I can post it in the upcoming days.

That's awesome news! I know a lot of people who'd be glad to extract some levels from this game.
## Post #110
- Username: no00ob
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 28, 2020 5:58 am
- Post datetime: 2020-03-25T16:21:58+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from akderebur ↑Wed Mar 25, 2020 11:46 pm at Wed Mar 25, 2020 11:46 pm
>
> 
cursore wrote: ↑Wed Mar 25, 2020 11:30 pm
Is it possible to load maps with all the meshes in the right place and not scattered around like that?


Yes, it is possible actually. I was working on a map tool, but never had the chance to release it. Maybe I can post it in the upcoming days.

Please do! I'd absolutely love that as I've been in need to extract these maps for few weeks now but its a pain with the meshes scattered around like this.
## Post #111
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-28T13:43:19+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

I will release the map tool soon after writing the exporter. There will be automatic material mapping, but won't be shown in the preview because of high memory usage. I will also update the texture exporter for bulk exporting. Again thanks to daemon1 for his help with this format.

Single interior



Whole map folder loaded
## Post #112
- Username: no00ob
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 28, 2020 5:58 am
- Post datetime: 2020-03-28T14:15:13+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from akderebur ↑Sat Mar 28, 2020 9:43 pm at Sat Mar 28, 2020 9:43 pm
>
> 
I will release the map tool soon after writing the exporter. There will be automatic material mapping, but won't be shown in the preview because of high memory usage. I will also update the texture exporter for bulk exporting. Again thanks to daemon1 for his help with this format.

Single interior



Whole map folder loaded

Whaat! Auto material mapping as well this is amazing!
## Post #113
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2020-03-28T16:12:07+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from akderebur ↑Sat Mar 28, 2020 9:43 pm at Sat Mar 28, 2020 9:43 pm
>
> 
I will release the map tool soon after writing the exporter. There will be automatic material mapping, but won't be shown in the preview because of high memory usage. I will also update the texture exporter for bulk exporting. Again thanks to daemon1 for his help with this format.

Single interior

]

Whole map folder loaded

wow! thank you very much!
## Post #114
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-29T22:29:34+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Did some fixes and coded the exporter. I will probably release the tool tomorrow after making a basic UI. Also it seems like Blender is the best option for loading the exported OBJ files. It gets all the texture references, unlike other software I have tried.

Preview video of Joel's house loaded in Blender. It lags a bit because whole map is loaded and I suck at Blender 

[https://www.youtube.com/watch?v=s8o3KxHizbY](https://www.youtube.com/watch?v=s8o3KxHizbY)
## Post #115
- Username: cursore
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Mar 06, 2019 9:26 pm
- Post datetime: 2020-03-30T13:35:02+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Awesome    Can't wait
## Post #116
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-30T22:29:44+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

RELEASE : Map Tool

Overview



Part of map loaded in Blender



Usage
- Load PAK : Loads a single pak file
- Load Folder : Loads all the pak files inside the selected folder
Note :  Materials won't be shown in preview

- Export OBJs : Exports all the meshes in OBJ format with their respective mtl files for material mapping. Each pak will have a separate obj export.

Upon trying various importers I find Blender the best for importing OBJ. Still you are free to use whatever you want, most softwares should support OBJ.

Material mapping / Textures

Textures need to be in the same folder as OBJ files. By default models reference PNG files. You can edit mtl files to change them to DDS if you really need that. In any case make sure to use the updated tool for extracting textures : [viewtopic.php?p=161585#p161585](https://forum.xentax.com/viewtopic.php?p=161585#p161585)

Download :  [https://www.mediafire.com/file/4brogfya ... r.rar/file](https://www.mediafire.com/file/4brogfyaoqfe12m/TLOUMapViewer.rar/file)
## Post #117
- Username: cursore
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Mar 06, 2019 9:26 pm
- Post datetime: 2020-03-30T23:48:15+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Exceptionally fast too. Clear and user friendly.

Thank you so much for this.
## Post #118
- Username: no00ob
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 28, 2020 5:58 am
- Post datetime: 2020-03-31T21:21:00+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Thank you so much for this tool!
## Post #119
- Username: cursore
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Mar 06, 2019 9:26 pm
- Post datetime: 2020-04-03T18:24:56+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from akderebur ↑Mon Mar 30, 2020 6:29 am at Mon Mar 30, 2020 6:29 am
>
> 
Did some fixes and coded the exporter. I will probably release the tool tomorrow after making a basic UI. Also it seems like Blender is the best option for loading the exported OBJ files. It gets all the texture references, unlike other software I have tried.

Preview video of Joel's house loaded in Blender. It lags a bit because whole map is loaded and I suck at Blender 

https://www.youtube.com/watch?v=s8o3KxHizbY

Hi akderebur, is there a way to view what textures the single mesh parts are using when visualizing character models?

Some of the npcs models are all-in-one and there's dozens of mesh parts and the model name doesn't always have a correlation with texture names.

Thanks in advance.
## Post #120
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-03T18:28:02+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from cursore ↑Sat Apr 04, 2020 2:24 am at Sat Apr 04, 2020 2:24 am
>
> 
is there a way to view what textures the single mesh parts are using when visualizing character models?
You mean the TLOUExporter tool, right? I have plans to make auto texturing for it too, but I will also rewrite most of the code in the process. Will probably do it some time in upcoming days.
## Post #121
- Username: cursore
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Mar 06, 2019 9:26 pm
- Post datetime: 2020-04-03T18:40:46+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Awesome!
## Post #122
- Username: cursore
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Mar 06, 2019 9:26 pm
- Post datetime: 2020-04-12T12:01:12+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Hi, any news?
## Post #123
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-14T13:23:27+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from cursore ↑Sun Apr 12, 2020 8:01 pm at Sun Apr 12, 2020 8:01 pm
>
> 
Hi, any news?
I was busy with other stuff. I will update the tool, but don't know when. Probably soon though.
## Post #124
- Username: cursore
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Mar 06, 2019 9:26 pm
- Post datetime: 2020-04-15T13:00:50+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from akderebur ↑Tue Apr 14, 2020 9:23 pm at Tue Apr 14, 2020 9:23 pm
>
> 
cursore wrote: ↑Sun Apr 12, 2020 8:01 pm
Hi, any news?

I was busy with other stuff. I will update the tool, but don't know when. Probably soon though.

Don't worry, take your time. Thanks again for all the splendid work.
## Post #125
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-01T10:39:51+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

I was looking at TLOU animations lately. Still have work to do, but I got some basic stuff loaded.

Take hit



Horse aim



Also almost finished with the new character tool which will have automatic texture mapping. I am planning to release it soon.
## Post #126
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2020-06-01T11:09:09+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from akderebur ↑Mon Jun 01, 2020 6:39 pm at Mon Jun 01, 2020 6:39 pm
>
> 
I was looking at TLOU animations lately. Still have work to do, but I got some basic stuff loaded.

Also almost finished with the new character tool which will have automatic texture mapping. I am planning to release it soon.
Awesome work as always
## Post #127
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2020-06-01T14:23:18+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Impressive work on the Animations!

I was wondering if you have any plans to release a template or format documentation regarding motions?

The reason i ask i assume the other naughty dog games such as Uncharted are probably almost identical so those could be loaded then too.
## Post #128
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-01T16:20:57+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from Highflex ↑Mon Jun 01, 2020 10:23 pm at Mon Jun 01, 2020 10:23 pm
>
> 
I was wondering if you have any plans to release a template or format documentation regarding motions?
I can do some kind of documentation I guess. Still I want to polish some stuff a bit more before releasing anything. It is still in a very early stage and have unknown stuff.
## Post #129
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-05T15:26:23+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

UPDATE

- Animation tool (limited test version)
- New model tool

Texture mapping
Overall improvements

Read first post for details and downloads.
## Post #130
- Username: cursore
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Mar 06, 2019 9:26 pm
- Post datetime: 2020-06-07T03:10:01+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

I'm testing the new viewer and it's working like a charme. Thank you 

Edit: I noticed that opening this large .pak file causes a crash: "npc-ffly-kit-all-tstrm.pak" inside the "world-lab" archive, and it's 16 MB in size.
## Post #131
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-07T09:20:57+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from cursore ↑Sun Jun 07, 2020 11:10 am at Sun Jun 07, 2020 11:10 am
>
> 
I noticed that opening this large .pak file causes a crash
Thanks for reporting, it was a memory management issue. It should be fixed now. I have updated the link in the first post.
## Post #132
- Username: khovasapian
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 30, 2017 8:23 pm
- Post datetime: 2020-06-12T11:40:21+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Great work on the animation tool. Any chance on extracting correct root positions - at the moment the characters just slide all over the place, and the root bone is instead being placed where the hips are. Maybe some extra bone node is missing which will correct root transforms? Thanks.
## Post #133
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-12T13:12:07+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from khovasapian ↑Fri Jun 12, 2020 7:40 pm at Fri Jun 12, 2020 7:40 pm
>
> 
at the moment the characters just slide all over the place, and the root bone is instead being placed where the hips are.
I haven't looked at the root motion at all. Translation keys might even be entirely wrong for some cases. Anyway I will get to root motion soon enough. Just finished all rotation types, will check translations and root motion next.

Just to remind, the animation tool is still very fresh. I even realized that I am skipping some bones completely after working on GoW  I will update the tool frequently as I have some significant progress, but don't expect anything proper until 2-3 iterations.
## Post #134
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2020-06-21T17:59:41+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from akderebur ↑Tue Mar 31, 2020 6:29 am at Tue Mar 31, 2020 6:29 am
>
> 
RELEASE : Map Tool

Overview



Part of map loaded in Blender



Usage
- Load PAK : Loads a single pak file
- Load Folder : Loads all the pak files inside the selected folder
Note :  Materials won't be shown in preview

- Export OBJs : Exports all the meshes in OBJ format with their respective mtl files for material mapping. Each pak will have a separate obj export.

Upon trying various importers I find Blender the best for importing OBJ. Still you are free to use whatever you want, most softwares should support OBJ.

Material mapping / Textures

Textures need to be in the same folder as OBJ files. By default models reference PNG files. You can edit mtl files to change them to DDS if you really need that. In any case make sure to use the updated tool for extracting textures : viewtopic.php?p=161585#p161585

Download :  https://www.mediafire.com/file/4brogfya ... r.rar/file

Is this possible to do with you're Uncharted 1,2,3 tool?
## Post #135
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-21T18:41:47+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from Faithfullfaun ↑Mon Jun 22, 2020 1:59 am at Mon Jun 22, 2020 1:59 am
>
> 
Is this possible to do with you're Uncharted 1,2,3 tool?
No, but it shouldn't be too hard to add map support. My uncharted tools need a rewrite anyway, so I might as well add map support while doing that. I can't say when I will do it though. Too many things to do, but too little time
## Post #136
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2020-06-21T19:44:58+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from akderebur ↑Mon Jun 22, 2020 2:41 am at Mon Jun 22, 2020 2:41 am
>
> 
Faithfullfaun wrote: ↑Mon Jun 22, 2020 1:59 am
Is this possible to do with you're Uncharted 1,2,3 tool?

No, but it shouldn't be too hard to add map support. My uncharted tools need a rewrite anyway, so I might as well add map support while doing that. I can't say when I will do it though. Too many things to do, but too little time

No hurry   
It's nice to see you updating the tools for easier use
## Post #137
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-06-23T00:18:27+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Hi there,

Thanks for creating these tools, it's great to be able to get levels/characters from the game.  

I'm currently trying to extract Marlene's hair from the file marlene-hair-cloth-tstrm.pak using the model viewer. But for some reason, only her hair tie is loaded. The actual hair itself just isn't there.

If anyone could shed some light on this problem, it would be much appreciated.
## Post #138
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-23T00:38:10+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from gep55 ↑Tue Jun 23, 2020 8:18 am at Tue Jun 23, 2020 8:18 am
>
> 
If anyone could shed some light on this problem, it would be much appreciated.

A small bug probably. I will take a look tomorrow. Will let you know when its fixed.
## Post #139
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-06-23T00:41:33+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Thanks. That's great
## Post #140
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2020-06-23T05:10:55+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from gep55 ↑Tue Jun 23, 2020 8:18 am at Tue Jun 23, 2020 8:18 am
>
> 
Hi there,

Thanks for creating these tools, it's great to be able to get levels/characters from the game.  

I'm currently trying to extract Marlene's hair from the file marlene-hair-cloth-tstrm.pak using the model viewer. But for some reason, only her hair tie is loaded. The actual hair itself just isn't there.

If anyone could shed some light on this problem, it would be much appreciated.

I don't have problems loading marlene hair
[](https://ibb.co/yBqyz2x)
## Post #141
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-23T10:09:07+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from fil1969 ↑Tue Jun 23, 2020 1:10 pm at Tue Jun 23, 2020 1:10 pm
>
> 
I don't have problems loading marlene hair

He meant using the new TLOUViewer. The old one loads it.

> Reply from gep55 ↑Tue Jun 23, 2020 8:41 am at Tue Jun 23, 2020 8:41 am
>
> 
Thanks. That's great
I have fixed it and updated the download link in the first post.

The problem is that the hair has no primary uv set. The uv is defined as secondary (compared to other models), and the tool was skipping the mesh entirely since it was seen as having no uvs. Now it will be loaded fine. Still I didn't want to change the logic entirely for couple of exceptional meshes. So the first uv channel of the hair mesh will be empty. Correct uvs will be in UV2 channel.
## Post #142
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2020-06-23T10:56:21+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

I found something weird when browsing the map files using the TLOUMapViewer and found this when looking at the suburbs map 
Looks like the vertices is broken in some parts?
I don't know if it's just me or does anyone have the same issue?
## Post #143
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-23T11:07:45+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from Faithfullfaun ↑Tue Jun 23, 2020 6:56 pm at Tue Jun 23, 2020 6:56 pm
>
> 
Looks like the vertices is broken in some parts?
With maps it might be hard to guess just by looking at the geometry. Might be something that has transparency textures, so the geometry looks weird or it might be a out of map (considering ingame bounds) part.

Better view it with the material and check the mesh name as a hint to what it should look like.
## Post #144
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2020-06-23T14:21:25+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Ok i will take a look when i get home
## Post #145
- Username: ImEnFuego
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 24, 2020 12:14 pm
- Post datetime: 2020-06-23T18:05:52+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

Is there any chance of a tool update for TLOU 2?
## Post #146
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-23T18:47:15+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from ImEnFuego ↑Wed Jun 24, 2020 2:05 am at Wed Jun 24, 2020 2:05 am
>
> 
Is there any chance of a tool update for TLOU 2?

Nope. I don't have the game files.
## Post #147
- Username: connorukboy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 29, 2018 9:53 pm
- Post datetime: 2020-06-23T19:31:43+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

itll be great to see a tool for tlou2, i know these things can take a few months after the games release. i think tlou2 uses same engine as uncharted 4. wonder if anyone will upload a tool soon
## Post #148
- Username: wthisme
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 23, 2020 11:04 pm
- Post datetime: 2020-06-25T08:03:21+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from akderebur ↑Wed Jun 24, 2020 2:47 am at Wed Jun 24, 2020 2:47 am
>
> 
ImEnFuego wrote: ↑Wed Jun 24, 2020 2:05 am
Is there any chance of a tool update for TLOU 2?


Nope. I don't have the game files.

Bro I can send you the PKG file of Last Of Us 2, but I only have the official PKG file, which requires a passcode to extract it, I don’t know what the passcode is. Maybe it’s the same as Uncharted 4? because they use the same engine.
## Post #149
- Username: connorukboy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 29, 2018 9:53 pm
- Post datetime: 2020-06-25T16:29:15+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from wthisme ↑Thu Jun 25, 2020 4:03 pm at Thu Jun 25, 2020 4:03 pm
>
> 
akderebur wrote: ↑Wed Jun 24, 2020 2:47 am
ImEnFuego wrote: ↑Wed Jun 24, 2020 2:05 am
Is there any chance of a tool update for TLOU 2?


Nope. I don't have the game files.


Bro I can send you the PKG file of Last Of Us 2, but I only have the official PKG file, which requires a passcode to extract it, I don’t know what the passcode is. Maybe it’s the same as Uncharted 4? because they use the same engine.

do you get the file from opening tlou2 ps4 disc in pc?
## Post #150
- Username: wthisme
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 23, 2020 11:04 pm
- Post datetime: 2020-06-26T08:51:09+00:00
- Post Title: Re: The Last of Us Model Viewer/Extractor (PS4)

> Reply from connorukboy ↑Fri Jun 26, 2020 12:29 am at Fri Jun 26, 2020 12:29 am
>
> 
wthisme wrote: ↑Thu Jun 25, 2020 4:03 pm
akderebur wrote: ↑Wed Jun 24, 2020 2:47 am


Nope. I don't have the game files.


Bro I can send you the PKG file of Last Of Us 2, but I only have the official PKG file, which requires a passcode to extract it, I don’t know what the passcode is. Maybe it’s the same as Uncharted 4? because they use the same engine.


do you get the file from opening tlou2 ps4 disc in pc?
I have the pkg file of last of us 2, but cannot open and extract the file to get animation, sounds etc, because it is encrypted.
## Post #151
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2020-06-26T11:44:44+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

what size are we talking about? i'd not mind to take a look (and trnya get some models out of it). if it's encrypted, this sux tho.

if it's organized well and can be taken apart i'd also want the weed lab map.
## Post #152
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-26T14:34:57+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

UPDATE

Animation Tool Updates
- In-game cutscene support (.stm)
- Secondary bone set (face animations)
- New rotation type
- Scale keys
- Translations fixed (mostly)

Not supported (yet)
- Additive animations
- Root motion? (might be controlled by game script)

Important Note
The exported animations will not look exactly as ingame in most cases. TLoU/Uncharted use physics animations frequently. Meaning for some clips there are physics simulations on top of keyframe animation. These are done using couple of constraints/limits defined in Havok, and some simulation values set in game scripting. Trying to reverse them is obviously not very reasonable 

Model Tool Updates
- Lower quality LODs will be discarded
- Texture references fix

Riley is happy with the updates
## Post #153
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2020-06-27T08:07:56+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from akderebur ↑Fri Jun 26, 2020 10:34 pm at Fri Jun 26, 2020 10:34 pm
>
> 
UPDATE

Animation Tool Updates
- In-game cutscene support (.stm)
- Secondary bone set (face animations)
- New rotation type
- Scale keys
- Translations fixed (mostly)

Not supported (yet)
- Additive animations
- Root motion? (might be controlled by game script)

Great job! If it`s not a secret were you able to find animation code in the game or reversing it all by guessing?
## Post #154
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-27T12:11:24+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from Skykila ↑Sat Jun 27, 2020 4:07 pm at Sat Jun 27, 2020 4:07 pm
>
> 
were you able to find animation code in the game or reversing it all by guessing?

I didn't get it from the game. Don't know how to do that for ps4 stuff tbh. I would call it educated guessing , based on research and experience. Also got some hints from ps documentation.
## Post #155
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2020-06-29T13:12:02+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

is there progress on the file front anywhere? not talking 80+ gigs. but atleast samples of some form in some kind of format? i read about the file system encryption. that level should be done. dunno what container wrap is next in line.

or are those tools working for #2? i dunno.
## Post #156
- Username: connorukboy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 29, 2018 9:53 pm
- Post datetime: 2020-06-29T18:15:58+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from episoder ↑Mon Jun 29, 2020 9:12 pm at Mon Jun 29, 2020 9:12 pm
>
> 
is there progress on the file front anywhere? not talking 80+ gigs. but atleast samples of some form in some kind of format? i read about the file system encryption. that level should be done. dunno what container wrap is next in line.

or are those tools working for #2? i dunno.

if you can bro, would you be able to rip joel whe  he plays the guitar in the first cutscene to ellie
## Post #157
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2020-06-29T23:32:24+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from connorukboy ↑Tue Jun 30, 2020 2:15 am at Tue Jun 30, 2020 2:15 am
>
> if you can bro, would you be able to rip joel whe  he plays the guitar in the first cutscene to ellie

what? you gotta "bro" with the sony tech group and be a naughty dog, dude. i don't fux with that shit. gotta wait for it to open up.

(i just wanna extend a lewd scene and snag ellie's on the boat costume too, but... it is what it is)
## Post #158
- Username: connorukboy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 29, 2018 9:53 pm
- Post datetime: 2020-06-30T02:21:41+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from episoder ↑Tue Jun 30, 2020 7:32 am at Tue Jun 30, 2020 7:32 am
>
> 
connorukboy wrote: ↑Tue Jun 30, 2020 2:15 amif you can bro, would you be able to rip joel whe  he plays the guitar in the first cutscene to ellie


what? you gotta "bro" with the sony tech group and be a naughty dog, dude. i don't fux with that shit. gotta wait for it to open up.

(i just wanna extend a lewd scene and snag ellie's on the boat costume too, but... it is what it is)

when a tools out im sure ill get what i want  bro
## Post #159
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2020-07-25T19:05:09+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

Hello, can you continue the work on the animation tool to get all animation, please
## Post #160
- Username: adminahmed321
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 25, 2020 3:08 pm
- Post datetime: 2020-07-27T11:36:06+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

Problem exporting animation.
There is any way to export animation of complete model?
Because the tool load only one .nux file, the character is not complete(miss hair,eye....)
## Post #161
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2020-07-27T21:25:47+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

you can complete the model in a 3d Modeling Programm like Blender. Bind the Parts to one skel. In an engine like Unity you just need the skel of the animation to use it on the player.
## Post #162
- Username: adminahmed321
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 25, 2020 3:08 pm
- Post datetime: 2020-07-28T08:02:26+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

How can i export only the animation with noesis?
I need to apply the animation to the complete 3d model in blender.
## Post #163
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2020-07-28T21:37:30+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

you export it in noesis also at additional animation output as bvh file or dae or fbx.
i cant see in blender the bones of the skel just points (seems like motion capture points), when i import it in maya the bones have confused postions, is their a way to see the skel (Bones, Joints)  like in noesis in blender or in maya?
## Post #164
- Username: adminahmed321
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 25, 2020 3:08 pm
- Post datetime: 2020-08-01T13:53:06+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

There is any way to create only 1 .nux file that include all the .pak file loaded in the TLOUViewer?
## Post #165
- Username: adminahmed321
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 25, 2020 3:08 pm
- Post datetime: 2020-08-13T12:27:34+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from Jan666 ↑Tue Jul 28, 2020 5:25 am at Tue Jul 28, 2020 5:25 am
>
> 
you can complete the model in a 3d Modeling Programm like Blender. Bind the Parts to one skel. In an engine like Unity you just need the skel of the animation to use it on the player.

How can i bind the parts to one skel corectly in blender?
## Post #166
- Username: vadik
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 23, 2020 4:15 am
- Post datetime: 2020-08-29T11:56:41+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

akderebur, could you please provide source code for your tools?
## Post #167
- Username: junminlee2004
- Rank: n00b
- Number of posts: 13
- Joined date: Fri May 08, 2020 3:08 am
- Post datetime: 2021-03-05T04:13:09+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

So how do you make the textures transparent, the texture editor tools only allows me to download non-transparent textures.
## Post #168
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2021-03-06T06:00:44+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from junminlee2004 ↑Fri Mar 05, 2021 12:13 pm at Fri Mar 05, 2021 12:13 pm
>
> 
So how do you make the textures transparent, the texture editor tools only allows me to download non-transparent textures.

when you extract the textures, there are also black and white ones, that are the alpha channel, in photoshop (ore any other similar software) open the color texture, in the channels tab, add a new channel, that will be called "alpha1", on that channel paste the related black and white texture then save the texture in any format that supports transparency, like PNG, DDS or TGA
## Post #169
- Username: junminlee2004
- Rank: n00b
- Number of posts: 13
- Joined date: Fri May 08, 2020 3:08 am
- Post datetime: 2021-03-08T01:09:02+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

can you be a little more specific, I'm not sure I understand how to do it in photoshop.
## Post #170
- Username: junminlee2004
- Rank: n00b
- Number of posts: 13
- Joined date: Fri May 08, 2020 3:08 am
- Post datetime: 2021-03-09T03:47:22+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from fil1969 ↑Sat Mar 06, 2021 2:00 pm at Sat Mar 06, 2021 2:00 pm
>
> 
junminlee2004 wrote: ↑Fri Mar 05, 2021 12:13 pm
So how do you make the textures transparent, the texture editor tools only allows me to download non-transparent textures.


when you extract the textures, there are also black and white ones, that are the alpha channel, in photoshop (ore any other similar software) open the color texture, in the channels tab, add a new channel, that will be called "alpha1", on that channel paste the related black and white texture then save the texture in any format that supports transparency, like PNG, DDS or TGA

I've done everything that you've said but I'm still stuck as to how to remove the background from the textures.
[Capture.PNG](https://xentaxbackup.github.io/file/19683_Capture.PNG)
## Post #171
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2021-03-09T05:19:46+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from junminlee2004 ↑Tue Mar 09, 2021 11:47 am at Tue Mar 09, 2021 11:47 am
>
> 
fil1969 wrote: ↑Sat Mar 06, 2021 2:00 pm
junminlee2004 wrote: ↑Fri Mar 05, 2021 12:13 pm
So how do you make the textures transparent, the texture editor tools only allows me to download non-transparent textures.


when you extract the textures, there are also black and white ones, that are the alpha channel, in photoshop (ore any other similar software) open the color texture, in the channels tab, add a new channel, that will be called "alpha1", on that channel paste the related black and white texture then save the texture in any format that supports transparency, like PNG, DDS or TGA


I've done everything that you've said but I'm still stuck as to how to remove the background from the textures.

in the picture I see the alpha is not selected, select all channels, the image background will turn pink, that is the alpha mask, export it with all selected, in TGA format
[](https://ibb.co/BsWf0cm)
## Post #172
- Username: junminlee2004
- Rank: n00b
- Number of posts: 13
- Joined date: Fri May 08, 2020 3:08 am
- Post datetime: 2021-03-09T18:01:43+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from fil1969 ↑Tue Mar 09, 2021 1:19 pm at Tue Mar 09, 2021 1:19 pm
>
> 
junminlee2004 wrote: ↑Tue Mar 09, 2021 11:47 am
fil1969 wrote: ↑Sat Mar 06, 2021 2:00 pm


when you extract the textures, there are also black and white ones, that are the alpha channel, in photoshop (ore any other similar software) open the color texture, in the channels tab, add a new channel, that will be called "alpha1", on that channel paste the related black and white texture then save the texture in any format that supports transparency, like PNG, DDS or TGA


I've done everything that you've said but I'm still stuck as to how to remove the background from the textures.


in the picture I see the alpha is not selected, select all channels, the image background will turn pink, that is the alpha mask, export it with all selected, in TGA format

so initially you added a channel to the color image and copy pasted the black and white image into Alpha 1 right? For me it's still not working, and the image selected with the channel just turns slightly dimmer.
## Post #173
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2021-03-10T09:35:17+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from junminlee2004 ↑Wed Mar 10, 2021 2:01 am at Wed Mar 10, 2021 2:01 am
>
> 
fil1969 wrote: ↑Tue Mar 09, 2021 1:19 pm
junminlee2004 wrote: ↑Tue Mar 09, 2021 11:47 am


I've done everything that you've said but I'm still stuck as to how to remove the background from the textures.


in the picture I see the alpha is not selected, select all channels, the image background will turn pink, that is the alpha mask, export it with all selected, in TGA format



so initially you added a channel to the color image and copy pasted the black and white image into Alpha 1 right? For me it's still not working, and the image selected with the channel just turns slightly dimmer.

Yes, did you scaled the black and white to fit the color one? I converted the same right now, and i don't have any problems
[](https://ibb.co/b6zCWr6)
## Post #174
- Username: junminlee2004
- Rank: n00b
- Number of posts: 13
- Joined date: Fri May 08, 2020 3:08 am
- Post datetime: 2021-03-10T17:40:08+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from fil1969 ↑Wed Mar 10, 2021 5:35 pm at Wed Mar 10, 2021 5:35 pm
>
> 
junminlee2004 wrote: ↑Wed Mar 10, 2021 2:01 am
fil1969 wrote: ↑Tue Mar 09, 2021 1:19 pm


in the picture I see the alpha is not selected, select all channels, the image background will turn pink, that is the alpha mask, export it with all selected, in TGA format



so initially you added a channel to the color image and copy pasted the black and white image into Alpha 1 right? For me it's still not working, and the image selected with the channel just turns slightly dimmer.


Yes, did you scaled the black and white to fit the color one? I converted the same right now, and i don't have any problems
Yes, I scaled it to 1024x1024 I really don't know what I'm doing wrong. I made this 30 second clip of what I did on this youtube link
[https://www.youtube.com/watch?v=KW-P8TuMqxw](https://www.youtube.com/watch?v=KW-P8TuMqxw)
## Post #175
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-03-27T17:09:38+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

UPDATE

Animation Tool Updates
- Root motion
- Better rotation support
- Overall fixes

Updated download link in the first post.

The tool should be able to handle the animations MUCH better. There is still some non-working stuff though. This is probably close to the final release. I don't see myself digging deeper into this. I might continue doing some quality of life updates.

Root motion previews
## Post #176
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2021-03-28T06:02:58+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from akderebur ↑Tue Mar 31, 2020 6:29 am at Tue Mar 31, 2020 6:29 am
>
> 
RELEASE : Map Tool

Overview



Part of map loaded in Blender



Usage
- Load PAK : Loads a single pak file
- Load Folder : Loads all the pak files inside the selected folder
Note :  Materials won't be shown in preview

- Export OBJs : Exports all the meshes in OBJ format with their respective mtl files for material mapping. Each pak will have a separate obj export.

Upon trying various importers I find Blender the best for importing OBJ. Still you are free to use whatever you want, most softwares should support OBJ.

Material mapping / Textures

Textures need to be in the same folder as OBJ files. By default models reference PNG files. You can edit mtl files to change them to DDS if you really need that. In any case make sure to use the updated tool for extracting textures : viewtopic.php?p=161585#p161585

Download :  https://www.mediafire.com/file/4brogfya ... r.rar/file

Maybe you can make the same Tool for tlou part 2?
## Post #177
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-03-28T16:55:13+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from Jan666 ↑Sun Mar 28, 2021 2:02 pm at Sun Mar 28, 2021 2:02 pm
>
> 
Maybe you can make the same Tool for tlou part 2?

I don't have any plans for releasing TLOU 2 tools atm. I think daemon will make a map tool at some point.
## Post #178
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2021-03-28T17:31:17+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from akderebur ↑Mon Mar 29, 2021 12:55 am at Mon Mar 29, 2021 12:55 am
>
> 
Jan666 wrote: ↑Sun Mar 28, 2021 2:02 pm
Maybe you can make the same Tool for tlou part 2?


I don't have any plans for releasing TLOU 2 tools atm. I think daemon will make a map tool at some point.

Yes, He said that, but He has no time atm, hmm maybe you know how i can get the xyz coordinate/ position of an object (to reconstruct a level) ((is it possible to See it in Hexeditor when i put the pak file in it?))

Btw thanks for your Animation Tool its Amazing
## Post #179
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-03-29T08:05:58+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from akderebur ↑Sun Mar 28, 2021 1:09 am at Sun Mar 28, 2021 1:09 am
>
> 
The tool should be able to handle the animations
For their animations, Naughty dogs did things i've never seen before in any other engine. Real crazy things.
I couldn't solve it whatever i tried. The only way was to reverse and debug the original SPU code.
But now, after i did that, i think it was indeed possible to guess.
## Post #180
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-03-29T09:17:03+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from daemon1 ↑Mon Mar 29, 2021 4:05 pm at Mon Mar 29, 2021 4:05 pm
>
> 
For their animations, Naughty dogs did things i've never seen before in any other engine. Real crazy things.

Indeed. They are using many different techniques depending on the situation. Need to handle them all to get the correct output. I had to really broaden my animation knowledge to make sense of some stuff. Still not sure if I am doing everything correctly 

If anyone is interested in animation data, I suggest checking out this blog: [https://nfrechette.github.io/](https://nfrechette.github.io/) It has some great posts about animation compression.
## Post #181
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-03-29T10:25:22+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from akderebur ↑Mon Mar 29, 2021 5:17 pm at Mon Mar 29, 2021 5:17 pm
>
> 
They are using many different techniques depending on the situation.
I'm not talking about techniques here. This is common, and not much different from others.
The way they encode the very basic thing: data tracks. And also quaternion compression.
## Post #182
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-03-29T12:07:52+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from daemon1 ↑Mon Mar 29, 2021 6:25 pm at Mon Mar 29, 2021 6:25 pm
>
> 
I'm not talking about techniques here. This is common, and not much different from others.
The way they encode the very basic thing: data tracks. And also quaternion compression.
I haven't worked on many AAA engine animations, so most stuff was new to me in terms of compression  Especially variable bit length streams, but I know it is used by some other games too.
## Post #183
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-03-29T12:12:47+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from akderebur ↑Mon Mar 29, 2021 8:07 pm at Mon Mar 29, 2021 8:07 pm
>
> 
I haven't worked on many AAA engine animations, so most stuff was new to me in terms of compression  Especially variable bit length streams, but I know it is used by some other games too.
ok forget about this 
i was talking about different thing
## Post #184
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-03-29T12:16:05+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from daemon1 ↑Mon Mar 29, 2021 8:12 pm at Mon Mar 29, 2021 8:12 pm
>
> 
i was talking about different thing
Yea, I guess I didn't quite get it
## Post #185
- Username: junminlee2004
- Rank: n00b
- Number of posts: 13
- Joined date: Fri May 08, 2020 3:08 am
- Post datetime: 2021-04-02T03:27:35+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

So how do you combine multiple .nux files into one? I can't really find a way to do it in noesis and the TLOU viewer only exports .nux files separately.
## Post #186
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2021-04-02T22:54:14+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from akderebur ↑Mon Mar 29, 2021 12:55 am at Mon Mar 29, 2021 12:55 am
>
> 
Jan666 wrote: ↑Sun Mar 28, 2021 2:02 pm
Maybe you can make the same Tool for tlou part 2?


I don't have any plans for releasing TLOU 2 tools atm. I think daemon will make a map tool at some point.
 Can i ask you how, did you find the xyz coordinates of the objects when you load the pak files in your maptool? What should i put attention on, when i search this values in hex editor?
## Post #187
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-03T08:25:34+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from junminlee2004 ↑Fri Apr 02, 2021 11:27 am at Fri Apr 02, 2021 11:27 am
>
> 
So how do you combine multiple .nux files into one?

I think by combining you want to have single model with multiple animation clips, right? It can probably be done in Maya/Blender. You can try googling how to do that.

> Reply from Jan666 ↑Sat Apr 03, 2021 6:54 am at Sat Apr 03, 2021 6:54 am
>
> 
Can i ask you how, did you find the xyz coordinates of the objects when you load the pak files in your maptool?

There was like a map objects table. Containing references to meshes and their transforms. No idea if that is also the case for tlou2.
## Post #188
- Username: junminlee2004
- Rank: n00b
- Number of posts: 13
- Joined date: Fri May 08, 2020 3:08 am
- Post datetime: 2021-04-03T22:05:04+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

How do you export the animation with root motion? I exported the animation from noesis and it didn't include root motion
## Post #189
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-04T08:35:00+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from junminlee2004 ↑Sun Apr 04, 2021 6:05 am at Sun Apr 04, 2021 6:05 am
>
> 
How do you export the animation with root motion? I exported the animation from noesis and it didn't include root motion

Aw shit, my bad. I have applied the root motion on the viewer's root but forgot that it isn't exported to NUX. I will fix this and release an update. Thanks for pointing it out.

Edit

The root motion should work now. I have updated the link in the first post.
## Post #190
- Username: junminlee2004
- Rank: n00b
- Number of posts: 13
- Joined date: Fri May 08, 2020 3:08 am
- Post datetime: 2021-04-13T14:17:57+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

Is there any option to export textures from the texture editor at higher resolution (2048X2048) ? Resizing the textures, specifically the normal maps to that size makes the model look like low quality
## Post #191
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-13T15:14:54+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from junminlee2004 ↑Tue Apr 13, 2021 10:17 pm at Tue Apr 13, 2021 10:17 pm
>
> 
Is there any option to export textures from the texture editor at higher resolution (2048X2048) ?
High quality textures are in common-tstrm.pak. If you can't find the 2048x2048 resolution of the texture you want, it means it doesn't exist.
## Post #192
- Username: RemyDemy
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Apr 08, 2021 5:17 am
- Post datetime: 2021-04-13T20:07:57+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

Can you release a Maptool for tlou2 aswell???
## Post #193
- Username: junminlee2004
- Rank: n00b
- Number of posts: 13
- Joined date: Fri May 08, 2020 3:08 am
- Post datetime: 2021-04-15T03:29:16+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from akderebur ↑Tue Apr 13, 2021 11:14 pm at Tue Apr 13, 2021 11:14 pm
>
> 
junminlee2004 wrote: ↑Tue Apr 13, 2021 10:17 pm
Is there any option to export textures from the texture editor at higher resolution (2048X2048) ?

High quality textures are in common-tstrm.pak. If you can't find the 2048x2048 resolution of the texture you want, it means it doesn't exist.

about that, is it possible to make a setting so that only the high quality versions of the textures are downloaded? when I export all the textures it only saves the low quality versions of the same texture because they override the high quality textures. Perhaps you could make it so that the textures are exported with the last portion of the texture name (DXT1, BC4, NA) so that textures are not overridden due to having the same name.
## Post #194
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-15T09:19:53+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from junminlee2004 ↑Thu Apr 15, 2021 11:29 am at Thu Apr 15, 2021 11:29 am
>
> 
they override the high quality textures. Perhaps you could make it so that the textures are exported with the last portion of the texture name

It was like that before, but I changed it to make it easier to use with the map tool. You can use the previous versions of the texture tool if it fits your needs.

Otherwise, give me an example of an overridden texture and which pak file it is in. I can try fixing it when I have the time. Also can you write issues regarding the textures under my texture thread?
## Post #195
- Username: ExactExtract
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 05, 2020 2:39 am
- Post datetime: 2021-04-26T18:57:25+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

YO! We need a working tool for TLOU2!     
STM files ready to be unlocked!
## Post #196
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2021-04-27T04:45:01+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

I wanna ask you again to make a maptool for tlou2, daemon1 will never do it, please
## Post #197
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-04-27T06:19:41+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from Jan666 ↑Tue Apr 27, 2021 12:45 pm at Tue Apr 27, 2021 12:45 pm
>
> 
I wanna ask you again to make a maptool for tlou2, daemon1 will never do it, please
i did not say i will never do it
i said i dont know
## Post #198
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2021-04-27T06:29:30+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from daemon1 ↑Tue Apr 27, 2021 2:19 pm at Tue Apr 27, 2021 2:19 pm
>
> 
Jan666 wrote: ↑Tue Apr 27, 2021 12:45 pm
I wanna ask you again to make a maptool for tlou2, daemon1 will never do it, please

i did not say i will never do it
i said i dont know
You said you not gonna do data reversing for a long time, so let me ask other people, bevor my Lifetime is over
## Post #199
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-04-27T07:32:23+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from Jan666 ↑Tue Apr 27, 2021 2:29 pm at Tue Apr 27, 2021 2:29 pm
>
> 
You said you not gonna do data reversing for a long time, so let me ask other people, bevor my Lifetime is over
I did NOT say that! You need to read again what i said.
## Post #200
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2021-04-27T08:20:27+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from daemon1 ↑Tue Apr 27, 2021 3:32 pm at Tue Apr 27, 2021 3:32 pm
>
> 
Jan666 wrote: ↑Tue Apr 27, 2021 2:29 pm
You said you not gonna do data reversing for a long time, so let me ask other people, bevor my Lifetime is over  

I did NOT say that! You need to read again what i said.
Whats wrong with you still write that "i'm not doing any reversing work for a long time now." But its not important, i search someone who create a maptool for tlou2, and when you dont wanna make a decision if your do it or not, dont waist my time
## Post #201
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-04-27T08:32:05+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from Jan666 ↑Tue Apr 27, 2021 4:20 pm at Tue Apr 27, 2021 4:20 pm
>
> 
Whats wrong with you still write that "i'm not doing any reversing work for a long time now." But its not important, i search someone who create a maptool for tlou2, and when you dont wanna make a decision if your do it or not, dont waist my time
I'm just telling you that you misread my words. Or wrong translation.
You are saying lies about me, and this is important.
## Post #202
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2021-04-27T09:09:10+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from daemon1 ↑Tue Apr 27, 2021 4:32 pm at Tue Apr 27, 2021 4:32 pm
>
> 
Jan666 wrote: ↑Tue Apr 27, 2021 4:20 pm
Whats wrong with you still write that "i'm not doing any reversing work for a long time now." But its not important, i search someone who create a maptool for tlou2, and when you dont wanna make a decision if your do it or not, dont waist my time

I'm just telling you that you misread my words. Or wrong translation.
You are saying lies about me, and this is important.
i just quote a fact, so dont say iam liar, i am just here for search a Tool, why are you interfering  here since i am not asking you anymore?
## Post #203
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-04-27T10:39:58+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from Jan666 ↑Tue Apr 27, 2021 5:09 pm at Tue Apr 27, 2021 5:09 pm
>
> 
i just quote a fact, so dont say iam liar, i am just here for search a Tool, why are you interfering  here since i am not asking you anymore?
Because you post a lie here. And people may think that this is real.
If you will delete your words where you say "daemon1 will never do it", i will stop interfering.
## Post #204
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2021-04-27T10:55:13+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from daemon1 ↑Tue Apr 27, 2021 6:39 pm at Tue Apr 27, 2021 6:39 pm
>
> 
Jan666 wrote: ↑Tue Apr 27, 2021 5:09 pm
i just quote a fact, so dont say iam liar, i am just here for search a Tool, why are you interfering  here since i am not asking you anymore?

Because you post a lie here. And people may think that this is real.
If you will delete your words where you say "daemon1 will never do it", i will stop interfering.
I delete it when you do it, how else should i know if it is a lie or the truth
## Post #205
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-27T17:46:10+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from Jan666 ↑Tue Apr 27, 2021 12:45 pm at Tue Apr 27, 2021 12:45 pm
>
> 
I wanna ask you again to make a maptool for tlou2
As I said before, I don't have any plans for TLoU2 atm.
## Post #206
- Username: ExactExtract
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 05, 2020 2:39 am
- Post datetime: 2021-04-27T17:56:49+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from akderebur ↑Wed Apr 28, 2021 1:46 am at Wed Apr 28, 2021 1:46 am
>
> 
Jan666 wrote: ↑Tue Apr 27, 2021 12:45 pm
I wanna ask you again to make a maptool for tlou2

As I said before, I don't have any plans for TLoU2 atm.

Excuse me while I go and be le sad   

What would one have to do to get stm animations into fbx? I assume it's a complicated nightmare, but if no one else has time or interest, I wouldn't mind learning and sharing.
## Post #207
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-27T18:19:56+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from ExactExtract ↑Wed Apr 28, 2021 1:56 am at Wed Apr 28, 2021 1:56 am
>
> 
I assume it's a complicated nightmare
Kind of. Loading animations from stm isn't too hard and it works same as loading pak animations. You can read it in the first post. The problematic part is that the cutscene sequence is split into chunks and the tool will load each chunk as a new animation. So you need to manually extract every chunk and merge in a 3D software atm. I am thinking of adding some updates like auto merge stm animations and bulk exporting. However, I don't know when I will have time/interest to do it.
## Post #208
- Username: ExactExtract
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 05, 2020 2:39 am
- Post datetime: 2021-04-27T18:31:06+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from akderebur ↑Wed Apr 28, 2021 2:19 am at Wed Apr 28, 2021 2:19 am
>
> 
ExactExtract wrote: ↑Wed Apr 28, 2021 1:56 am
I assume it's a complicated nightmare

Kind of. Loading animations from stm isn't too hard and it works same as loading pak animations. You can read it in the first post. The problematic part is that the cutscene sequence is split into chunks and the tool will load each chunk as a new animation. So you need to manually extract every chunk and merge in a 3D software atm. I am thinking of adding some updates like auto merge stm animations and bulk exporting. However, I don't know when I will have time/interest to do it.

Damn, that sounds a bit strange to me, I wonder why the game works like that. Thanks for the info. I really hope you get the itch and urge to make an STM TLOU2 tool. I know I'll be keeping my eyes open for it cause that tool you mentioned sounds excellent
## Post #209
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-27T18:44:31+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from ExactExtract ↑Wed Apr 28, 2021 2:31 am at Wed Apr 28, 2021 2:31 am
>
> 
Damn, that sounds a bit strange to me, I wonder why the game works like that.
You should consider the target console of the game. It was designed to run on a PS3 with only 256MB RAM . So, everything is divided into small chunks that are loaded into the memory when they are required. It is basically a design choice for efficient memory usage.
## Post #210
- Username: junminlee2004
- Rank: n00b
- Number of posts: 13
- Joined date: Fri May 08, 2020 3:08 am
- Post datetime: 2021-05-01T18:09:14+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

akderebur, can you adjust the TLOU viewer so that the export model function exports models with the "NUXroot" instead of the "root" for the bones so that it can be compatible with the root motion animations? Thanks for your help by the way.
## Post #211
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-07-11T17:40:48+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

WIP: Additive animations and blending

I am testing some animation blending and support for additive animations. Using both will produce results closer to in-game animations. The game itself seems to use them heavily depending on player input or other variables.

Below is an example for blending "walk" animation with "look around" animation. For some stuff, it can get even more layered. I will probably release the update with a short tutorial.
## Post #212
- Username: 578465367
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 03, 2021 12:38 am
- Post datetime: 2021-10-03T15:48:41+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

The model cannot be opened with TLOUMapViewer, what should I do?
## Post #213
- Username: JamesBone
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jan 08, 2022 4:43 pm
- Post datetime: 2022-01-15T07:08:23+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from akderebur ↑Mon Mar 30, 2020 6:29 am at Mon Mar 30, 2020 6:29 am
>
> 
Did some fixes and coded the exporter. I will probably release the tool tomorrow after making a basic UI. Also it seems like Blender is the best option for loading the exported OBJ files. It gets all the texture references, unlike other software I have tried.

Preview video of Joel's house loaded in Blender. It lags a bit because whole map is loaded and I suck at Blender 

https://www.youtube.com/watch?v=s8o3KxHizbY

Thank you! I have successfully
## Post #214
- Username: Jaimito
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 22, 2020 7:01 am
- Post datetime: 2022-02-22T20:05:04+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)


## Post #215
- Username: Jaimito
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 22, 2020 7:01 am
- Post datetime: 2022-02-22T20:08:15+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from akderebur ↑Mon Jul 12, 2021 1:40 am at Mon Jul 12, 2021 1:40 am
>
> 
WIP: Additive animations and blending

I am testing some animation blending and support for additive animations. Using both will produce results closer to in-game animations. The game itself seems to use them heavily depending on player input or other variables.

Below is an example for blending "walk" animation with "look around" animation. For some stuff, it can get even more layered. I will probably release the update with a short tutorial.

very good work friends, could you share the update of the tool ??
## Post #216
- Username: junminlee2004
- Rank: n00b
- Number of posts: 13
- Joined date: Fri May 08, 2020 3:08 am
- Post datetime: 2022-06-06T09:03:20+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

By the way, I wanted to say that transparent textures do not work for every character. For example, the "sarah-hair-cloth-tstrm.pak" model does not show up on the TLOUViewer when imported with corresponding textures. However, when "ellie-hair-cloth-skel-tstrm.pak" is imported with corresponding textures, the model shows up in its transparent form.
## Post #217
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2023-04-01T15:44:53+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

Seems like TLOU Part 1's format is close enough to the PS4 version. I might update my tools if I find the time.
## Post #218
- Username: kkhaial
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 28, 2015 4:20 pm
- Post datetime: 2023-04-07T11:19:22+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

Sweet!, extracted the game and waiting when you update.
## Post #219
- Username: zeroy
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 03, 2010 6:08 pm
- Post datetime: 2023-04-12T16:05:22+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

> Reply from akderebur ↑Sat Apr 01, 2023 11:44 pm at Sat Apr 01, 2023 11:44 pm
>
> 
Seems like TLOU Part 1's format is close enough to the PS4 version. I might update my tools if I find the time.

This would be greatly appreciated!
## Post #220
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2023-05-02T09:10:17+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

Can you make a new maptool too?
## Post #221
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2023-06-07T16:45:34+00:00
- Post Title: Re: The Last of Us Model/Animation Tools (PS4)

When will this tool for tlou part 1 for pc come?
