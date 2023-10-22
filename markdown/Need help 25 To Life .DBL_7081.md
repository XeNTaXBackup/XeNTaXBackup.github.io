## Post #1
- Username: tuckdragon
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 27, 2011 5:28 am
- Post datetime: 2011-07-30T02:59:00+00:00
- Post Title: Need help: 25 To Life .DBL

Need help to convert, extract or open this file type.

Download:
[http://dl.dropbox.com/u/10322904/25%20t ... models.zip](http://dl.dropbox.com/u/10322904/25%20to%20life%20.hog/models.zip)

Thanx in advance
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-03T01:14:03+00:00
- Post Title: Need help: 25 To Life .DBL

if you bump again i am going to delete your topic
## Post #3
- Username: tuckdragon
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 27, 2011 5:28 am
- Post datetime: 2011-08-04T01:38:56+00:00
- Post Title: Need help: 25 To Life .DBL

sry, just want help with this.
would be pretty dope since im pretty sure this game counts as abondonware x)
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-04T14:11:25+00:00
- Post Title: Need help: 25 To Life .DBL

Names come first, followed by some unknown section, followed by faces, then vertices.

You will need to provide more samples.
I am not interested in the character models, only relatively small files like items or scene props (1-200 KB). If someone else is interested afterwards, maybe they will pick it up from there and write a formal import script.

This is why: no clue what that section is supposed to be, and it's 32 KB long. A tga file maybe? But there's nothing that indicates it as such.
[25toLife.JPG](https://xentaxbackup.github.io/file/4576_25toLife.JPG)
## Post #5
- Username: tuckdragon
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 27, 2011 5:28 am
- Post datetime: 2011-08-04T19:37:21+00:00
- Post Title: Need help: 25 To Life .DBL

i think almost all the scene props from 1 map and the map are in the same file.   

but here are some weapons and items:
[http://dl.dropbox.com/u/10322904/TTL%20 ... models.zip](http://dl.dropbox.com/u/10322904/TTL%20models/More%20models.zip)
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-04T22:06:34+00:00
- Post Title: Need help: 25 To Life .DBL

Hmm, so it is an image file.

The dimensions are given there, followed by the image name (null-terminated), and then the image data.
For some reason the actual data is width*height*2 number of bytes...don't know why I still haven't looked at any graphic files yet.

Didn't notice that earlier 
Looks like extra bytes will have to be added to make it a proper tga file.

At least that part of the mystery is dealt with.

A single file could have multiple images depending on how many textures are assigned.
Faces are straightforward, vertices have 24 bytes each, but there's still a lot of unknown stuff leading up to it.
[25tl_image.jpg](https://xentaxbackup.github.io/file/4577_25tl_image.jpg)
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-05T13:44:22+00:00
- Post Title: Need help: 25 To Life .DBL

Appears to be a chunk-based format.

very simple outline that covers the entire file:

```
dword numChunks
dword unk

numChunks Chunk {
   dword unk #chunk type?
   dword chunkSize
   word unk #maybe this is chunk type?
   char_4 "1000"
   byte_50 null padding

   #replace this with cases for each type of chunk
   <seek chunkSize bytes>
}

```


I don't know which one indicates the chunk type.
I don't know how to calculate the image data size though. It seems like height * width doesn't work, and height * width * 2 works SOMETIMES.

```
	byte_236 ? #does not hold for all cases
	dword numIndices
	dword unk
	
	numIndices ? {
	   short index
	}
	
	dword unk
	dword numVerts
	dword vertSize
	dword vertChunkSize
	
	numVerts Vertex
	
	#more stuff. Temporarily calculate chunkSize - total read

}

```


There are several different vertex types. I have seen three:

```
	float_3 coords
	float_3 normals
	float-2 uv
}

vertSize 40 {
	float_3 coords
	...
}

vertSize 72 {
	...
}
```


The indices don't make much sense to me. A lot of them repeat several times in a row.
A confusing format.

This is supposedly a "deagle". It does resemble a gun of some sort.
[deagle.JPG](https://xentaxbackup.github.io/file/4582_deagle.JPG)
## Post #8
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2018-06-30T20:11:15+00:00
- Post Title: Need help: 25 To Life .DBL

Hey. I added DBL files of different classifications, perhaps this will help to unpack them.

[https://drive.google.com/open?id=1T0k7i ... zxvurNfnVy](https://drive.google.com/open?id=1T0k7iPMQjlfMRqXHm55sZNzxvurNfnVy)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-30T20:46:59+00:00
- Post Title: Need help: 25 To Life .DBL

well, I'm asking myself what could be the motivation to revive a nearly seven years old thread?  
Anyways, welcome to the rider-of-dead-horses club!

Here's a simple mesh, created by hex2obj (view link in my sig):



health_pkup-dlb.jpg (180.66 KiB) Viewed 281 times
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-30T21:00:25+00:00
- Post Title: Need help: 25 To Life .DBL

and an NPC; sorry that I didn't finish the mesh -- too "average" to arise my motivation:



averageguy1-dbl.jpg (207.31 KiB) Viewed 278 times
## Post #11
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2018-07-01T09:16:59+00:00
- Post Title: Need help: 25 To Life .DBL

Nice. Many players still play this game online. The ability to unpack DBL would allow creating custom maps. It would be cool. So what about the unpacker, is this possible?
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-01T09:46:09+00:00
- Post Title: Need help: 25 To Life .DBL

> Reply from Elephantkilla
>
> Nice. Many players still play this game online. The ability to unpack DBL would allow creating custom maps.It would require a repacker, too, wouldn't it?

> So what about the unpacker, is this possible?Not sure whether we're talking about the same thing. I just converted the 3D data in the dbls into wavefront obj files. If you mean that then yes, it's possible.

With some basic knowledge in 'C' you could add dbl2obj conversion to the Make_obj project:
[viewtopic.php?f=29&p=141547#p141547](http://forum.xentax.com/viewtopic.php?f=29&p=141547#p141547)
## Post #13
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2018-07-01T10:18:12+00:00
- Post Title: Need help: 25 To Life .DBL

Repackaging may not be necessary. The game, for example, works with unpacked files from the archive .HOG. Thanks to the users of this resource for the complete unpacking of this file. Just need to fully get all the files. This archive has not only the 3d model, it contains textures, some information (a kind of script), some contain sounds.

In general, I noticed that the .HOG archive, and then contained in it .DBL is not a novelty for the archives of consoles. In many games xBox meet these archives. 
And 25 To Life was ported from the console version, saving many files that were only on the console.

I understand, you just extracted the model? But this can be done in a more reasonable way, for example 3D Ripper DX
"sorry my bad translator"
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-01T10:29:20+00:00
- Post Title: Need help: 25 To Life .DBL

> Reply from Elephantkilla
>
> In general, I noticed that the .HOG archive, and then contained in it .DBL is not a novelty for the archives of consoles. [...]

I understand, you just extracted the model? But this can be done in a more reasonable way, for example 3D Ripper DX
"sorry my bad translator"Seems your confusing things, at least for me. Now your talking about .HOG archives BUT in your starting post you wrote about unpacking DBL files:

> Reply from Elephantkilla
>
> Hey. I added DBL files of different classifications, perhaps this will help to unpack them.(If you need to unpack dbl files from .HOG archives you'll need to upload one of those; not dbl files.)
## Post #15
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2018-07-01T10:42:29+00:00
- Post Title: Need help: 25 To Life .DBL

I just wanted to say that this game can work with an unpacked archive .HOG
Therefore, most likely I suggested that the game can work with an unpacked dbl file.
But you are right. In most cases, you need to be able to repackage the file DBL, for example, part of the character's clothing and texture for this clothing, the game uses as one file, so to add for example a new item of clothing you need to create a similar dbl file. I need an unpacker and a packer for the DBL archive.

UPD
Here is an example 3d model of a long T-shirt. And one of the variants of its texture is Red Blue Stripes
[https://drive.google.com/open?id=1vy96c ... uTS9HLz_AG](https://drive.google.com/open?id=1vy96cVnQ_HLwp9-Bk4hkRluTS9HLz_AG)
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-01T11:09:12+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from Elephantkilla
>
> I need an unpacker and a packer for the DBL archive.What exactly does that mean?

[Texture].dbl -> .tga -> [Texture].dbl ?
[mesh].dbl -> wavefront-obj -> [mesh].dbl ?

If so then the obj to dbl conversion (== packing?) will be the hard part since you need a full format analysing for such.

edit: an ugly attempt to get textures; guess there is already a tool for such?



DBL-texture.jpg (139.29 KiB) Viewed 204 times
## Post #17
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2018-07-01T11:45:23+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from shakotay2
>
> 
[Texture].dbl -> .tga -> [Texture].dbl ?
[mesh].dbl -> wavefront-obj -> [mesh].dbl ?

Yes, although, In principle, it would be enough to be able to create a 3d model and texture readable by the game.  ( .tga -> [Texture].dbl),  mesh.FORMAT?? -> [mesh].dbl ?[/quote]
Did you look at the details of the clothes? They are most important.

> Reply from Elephantkilla
>
> UPD
Here is an example 3d model of a long T-shirt. And one of the variants of its texture is Red Blue Stripes
https://drive.google.com/open?id=1vy96c ... uTS9HLz_AG
I sent you this here is a shirt 


I'm sure that in dbl there is still information about the position of the model in space.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-01T11:58:04+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from Elephantkilla
>
> Yes, although, In principle, it would be enough to be able to create a 3d model and texture readable by the game.  ( .tga -> [Texture].dbl),  mesh.FORMAT?? -> [mesh].dbl ?mesh.FORMAT?? -> [mesh].dbl, ok, the hard part. What you need is an obj to dbl converter. 

Be informed that it's not as easy as the reverse way. Search this forum and you'll see that there's very rare solutions for "obj to someBinaryGameFormat" conversions. 

> Did you look at the details of the clothes? They are most important.nope, I'm looking for models in general.
## Post #19
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2018-07-01T12:18:32+00:00
- Post Title: Re: Need help: 25 To Life .DBL

But the DBL file is not just a model. It can contain anything. It's a container. I think the game gets information from it, whether it has textures, sounds and other information. Some DBL files contain a full range of files inside themselves. I think you need to be able to unpack it, because, I think, even a simple 3d model of the DBL model contains the default texture. Tobish in this file is at least an unknown format 3d model, texture, script information, for example config.

Most likely without knowing the full contents of this file, you can not create a new readable file. hmmm....
## Post #20
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2018-07-03T11:32:30+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from Elephantkilla
>
> 

If you pull out this texture with a ripper, it looks like this.
[2b75d004.jpg](https://xentaxbackup.github.io/file/14546_2b75d004.jpg)
## Post #21
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2018-07-10T14:41:13+00:00
- Post Title: Re: Need help: 25 To Life .DBL

This Wave.DBL  is the archive of one of the maps. This map is a car park.
[https://drive.google.com/file/d/1xc-0jS ... sp=sharing](https://drive.google.com/file/d/1xc-0jSovyPdqMDHEQC1cjqfzko2pD9wr/view?usp=sharing)

The game looks like this:
[https://www.youtube.com/watch?v=S-xNpE6MVs4](https://www.youtube.com/watch?v=S-xNpE6MVs4)
## Post #22
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2018-08-23T15:56:31+00:00
- Post Title: Re: Need help: 25 To Life .DBL

Unpacked the XBox version. There .DBL file is subdivided into 2, 3 parts. As I understand the model has the extension .DXD
A secondary .XVH file that has content of this type:

```

#define Health_Pkup_IB00_OFFSET 0UL
#define Health_Pkup_VB01_OFFSET 12UL
```


And the .dbl file itself, which apparently contains basic information and links to the main model .DXD

Help create a converter, it will allow you to create your own maps, clothes and stuff for a network game.


XBOX VERSION FILES: [https://drive.google.com/open?id=1VKJsP ... JQIwIPJXdc](https://drive.google.com/open?id=1VKJsPQMP0piDiUaIa6AE9uJQIwIPJXdc)
## Post #23
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2018-09-16T11:57:19+00:00
- Post Title: Re: Need help: 25 To Life .DBL

I found a regularity, that these lines are almost always the same for clothing. There are exceptions in some bytes, but most likely they determine the occurrence in the category for each file. There is suspicion on the end of the file, but there mostly all files differ from each other. Tried to insert the DDS texture to this identified under the heading container the game crashes when selecting a modified clothes. Only once the game has not taken off, but there were no clothes, she was transparent. The type file is empty.
These textures are more like some kind of number system, hex texture. The fact that the file header specified TGA texture is clearly a hoax. Maybe they keep a record of what was converted.

I put two textures of the same t-shirt, differing only in color.
[https://drive.google.com/open?id=1IS0IA ... Yzglut2t_h](https://drive.google.com/open?id=1IS0IAUEOaoDl0pXI4evUrQYzglut2t_h)
one orange the other purple

Please help!
[Untitled-3.jpg](https://xentaxbackup.github.io/file/14857_Untitled-3.jpg)
## Post #24
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2018-09-16T12:03:34+00:00
- Post Title: Re: Need help: 25 To Life .DBL

This is how the orange texture pulled out by the Ripper looks like
[a9849c8c.jpg](https://xentaxbackup.github.io/file/14858_a9849c8c.jpg)
## Post #25
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2018-09-16T12:04:28+00:00
- Post Title: Re: Need help: 25 To Life .DBL

This is how the purple texture pulled out by the Ripper looks like


Help, at least change the color of these textures
[9e388f89.jpg](https://xentaxbackup.github.io/file/14859_9e388f89.jpg)
## Post #26
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2019-01-21T12:29:55+00:00
- Post Title: Re: Need help: 25 To Life .DBL

as I understand it the game uses the format YUY2 \ UYVY and supports DXT1 DXT2 DXT3 DXT4 DXT5 (DDS)
Someone familiar with the images  YUY2?

I studied the game a little and I'll say this
The game was created using Microsoft DirectX SDK, and the extension of the models are probably .X or .Mesh 
But now it's all in the shell .DBL

Here is the text from TTL.EXE 

> libpng version 1.0.5 - October 15, 1999
>
>    Copyright (c) 1995, 1996 Guy Eric Schalnat, Group 42, Inc.
>
>    Copyright (c) 1996, 1997 Andreas Dilger
>
>    Copyright (c) 1998, 1999 Glenn Randers-Pehrson
## Post #27
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-22T01:32:17+00:00
- Post Title: Re: Need help: 25 To Life .DBL

looks like the texture data is palettized with 32bit color palette 0x400 length followed by the index.   
you can decode them by hand easily with "Console Texture Explorer".
## Post #28
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2019-01-23T21:58:31+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from Acewell
>
> looks like the texture data is palettized with 32bit color palette 0x400 length followed by the index.   
you can decode them by hand easily with "Console Texture Explorer".
Can you help me with this? I can't even find where to download it. Discord #8484



Безымянный.jpg (69.62 KiB) Viewed 101 times


I downloaded another program. I can see it partially defines the texture, but it's pixelated..
## Post #29
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-24T07:32:31+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from Elephantkilla
>
> I can't even find where to download it.
its easy, you just type "Console Texture Explorer" in search and sort through results.  
download link is second one in this post
[viewtopic.php?f=33&t=15540&p=131457&hil ... r+#p131457](http://forum.xentax.com/viewtopic.php?f=33&t=15540&p=131457&hilit=+Console+Texture+Explorer+#p131457)



T349.png (54.64 KiB) Viewed 96 times
## Post #30
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2019-01-24T09:08:43+00:00
- Post Title: Re: Need help: 25 To Life .DBL

Abruptly. And how to convert the changed texture back?

I'm trying to import a modified texture. and an error pops up when importing. But the texture seems to be replaced. But UV Mapping is not correct ...



Untitled-3.jpg (32.69 KiB) Viewed 92 times
## Post #31
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2019-01-24T10:13:53+00:00
- Post Title: Re: Need help: 25 To Life .DBL

Untitled-5.jpg (39.69 KiB) Viewed 188 times


I have pixels on top, probably a problem with that.
but pressing any buttons does not move the positioning.
## Post #32
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2019-01-24T16:15:39+00:00
- Post Title: Re: Need help: 25 To Life .DBL

Even if the resulting texture is converted back (without changes), it turns out to be erroneous (even if it is expanded and inverted position)....this program does not provide reverse decoding?
## Post #33
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2019-02-06T15:19:01+00:00
- Post Title: Re: Need help: 25 To Life .DBL

In DBL archives responsible for PARTICLES contains such information:



pig.jpg (165.17 KiB) Viewed 175 times


sp_downtown.pig ?????
This format is used by some other games. Anyone familiar with this?
## Post #34
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2019-02-11T15:10:06+00:00
- Post Title: Re: Need help: 25 To Life .DBL

DBL.jpg (104.92 KiB) Viewed 166 times



> created by DBLMerge
I found this line in one of the DBL archive headers

I found the same line in an existing BMS script for Dragon ball Z Sagas DBU (created by DBLMerge) . 1000 [Dblmerge Dbu]
But he doesn't unpack. Perhaps it can be corrected?

dblmerge_dbu.bms

```
# script for QuickBMS http://quickbms.aluigi.org

get SIZE line
getdstring DBLMerge_STRING SIZE

getdstring DB_STRING 8
get DUMMY long  # 0x100
get ZERO long
get DUMMY long  # 0x28
get DUMMY long  # some size?
get ARCHIVE_SIZE asize
do
    savepos OFFSET
    get DUMMY long
    get SIZE long
    get FLAGS short
    getdstring DUMMY 0x36
    if DUMMY != "1000"  # lame work-around, some files have problems
        math OFFSET - 1
        goto OFFSET
    else
        savepos OFFSET
        if FLAGS == 1 && SIZE == 0x100  # another work-around
            getdstring NAME SIZE
            log NAME 0 0
        else
            append
            log NAME OFFSET SIZE
            append
            math OFFSET + SIZE
            goto OFFSET
        endif
    endif
while OFFSET != ARCHIVE_SIZE

```


This is an archive of textures and files to build the game menu.
[UBER_ALLSCREENS.DBL](https://drive.google.com/open?id=1_GL2OHeYOV9NNOxZ4cN1GzhPsWp2-qI_)
## Post #35
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-11T23:13:40+00:00
- Post Title: Re: Need help: 25 To Life .DBL

For me it looks as if you're trying a random script on a file, do you?  

Would make more sense to identify some data then create a script, imho.

For example bytes from 0x1300 to 0x1F3f can be displayed as raw file in irfan view like such:
8 BPP Grayscale, 64x512 pixels



UBER_ALLSCREENS-DBL_0x1300.jpg (4.02 KiB) Viewed 160 times
## Post #36
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2019-02-12T10:58:39+00:00
- Post Title: Re: Need help: 25 To Life .DBL

This is a similar script. And he tried to unpack, even after reading and creating the name of the first file.
Thank you for your interest in the topic. We know for sure that textures have .bmp format
But each texture is always packed in .dbl and can be located inside the common .dbl archive

I know for sure, all 3D models, textures, and sounds in archives are cropped in the header area. 
The header for each file is substituted in the .exe itself.
## Post #37
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-12T11:55:03+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from Elephantkilla
>
> Untitled-5.jpg
I have pixels on top, probably a problem with that.
but pressing any buttons does not move the positioning.What?  
What about changing the graphics offset?

I'd suggest to learn more about graphics formats and file structures; it would spare you tons of life time.
Just my two cents.

(btw: I don't know too much about graphics but I know that you're lost without basics.)
## Post #38
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2019-02-12T13:03:04+00:00
- Post Title: Re: Need help: 25 To Life .DBL

I do not understand this, probably why I am here. Try changing this shirt and exporting it back to confirm your words. Because I, in any case, cannot understand this. There are pixels on top ..
## Post #39
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2019-02-12T13:05:42+00:00
- Post Title: Re: Need help: 25 To Life .DBL

I understand that I should get a hex value where the image begins?
## Post #40
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-12T13:22:57+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from Elephantkilla
>
> Try changing this shirt and exporting it back to confirm your words.This will be the very last step. First of all you need to get the picture displayed correctly to understand WHERE (start address) it starts and where it ends (ENDADDRESS).

(Not "get"; you should set or enter a value.)
Looks to me like decimal values; but doesn't really matter in this case - try out 1200 for example. (And don't be surprised when the picture gets distorted, try other values until the picture moves, then change address in steps of 4 bytes for example.)

basic question for the size of pure picture data:
assumed you have a 64 pixel x 64 pixel image with a 256 colors scheme (8 bit).
What is the size of its data (in bytes)? (If you don't know when I'd suggest to read some tutorials.)
## Post #41
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2019-02-12T13:45:44+00:00
- Post Title: Re: Need help: 25 To Life .DBL

All single-texture archives open with this value. And displayed correctly.

> 
And the texture was obtained correctly, exactly the same as if it was pulled out by a 3DRipper.

However, if I try to export this texture to the archive without any editing. It will not be correctly positioned.
The difference whether I changed the texture or not it will in any case not be displayed correctly.
## Post #42
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-12T15:30:17+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from Elephantkilla
>
> All single-texture archives open with this value. And displayed correctly.Good.  

> However, if I try to export this texture to the archive without any editing.Correct, this the first thing to check.

> It will not be correctly positioned.You need to compare original and "modified" files. (Even if you didn't change the texture your export tool seems to change something.)

(Use HxD for example for file compare. It's in menu Analysis/File-compare.)
## Post #43
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2019-02-12T17:01:23+00:00
- Post Title: Re: Need help: 25 To Life .DBL

A screenshot of the comparison I gave above. You don't seem to hear what I'm saying..

I tried to manually enter the modified texture without changing the number of bytes, but no success. The game reads the texture in some coded form, going backwards in front.
There is clearly need some kind of encoder that will add additional bytes to the code
## Post #44
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-12T17:05:06+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from Elephantkilla
>
> You don't seem to hear what I'm saying..nope  

You can't seriously do the comparison in ASCII format!
It's required to do it in hex here.
## Post #45
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2019-03-20T10:20:03+00:00
- Post Title: Re: Need help: 25 To Life .DBL

TAGFRAME.7z
(20.03 KiB) Downloaded 31 times


This file contains three textures: TagFrameOutline, Blue_Tag, Red_Tag

Maybe someone will try to unpack it. It is a pity that the game is not so popular. Although this is the only game in which it would be possible to create their own locations for multiplayer, such as port maps from the CS and other games.
## Post #46
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-02-22T22:26:36+00:00
- Post Title: Re: Need help: 25 To Life .DBL

Is there anyway that DBL can be formated for Noesis. I need Chicken Little Models extracted.
## Post #47
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-01T18:36:49+00:00
- Post Title: Re: Need help: 25 To Life .DBL

here is my draft for this format.  




11.png (34.02 KiB) Viewed 87 times
## Post #48
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-03-01T19:16:19+00:00
- Post Title: Re: Need help: 25 To Life .DBL

I cant get .DBL to register   
[](https://ibb.co/h2P7M9m)

I was going to try them on Disney Bolt
## Post #49
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-01T19:41:50+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from Sharppy ↑Wed Mar 02, 2022 3:16 am at Wed Mar 02, 2022 3:16 am
>
> 
I cant get .DBL to register   
I was going to try them on Disney Bolt
I don't know what's the problem  
i see screenshot and think most likely your DBL does not contain mesh
## Post #50
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-03-01T19:47:36+00:00
- Post Title: Re: Need help: 25 To Life .DBL

Copy. Yeah these are different. But i couldn't even get the loader to seek .DBL files. Hm aliens   all good. Thanks anyway.
## Post #51
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-07-06T20:52:35+00:00
- Post Title: Re: Need help: 25 To Life .DBL

When i Tried .DBL Files for Noesis by using fmt_DBL, This Error pops up.
[nothing with DBL.png](https://xentaxbackup.github.io/file/22459_nothing with DBL.png)
## Post #52
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-07-08T20:46:46+00:00
- Post Title: Re: Need help: 25 To Life .DBL

can you please help me?
The Current One needs updating for Chicken Little Characters.
## Post #53
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-08-11T00:34:56+00:00
- Post Title: Re: Need help: 25 To Life .DBL

Can Anyone just Listen to me for One Day?
## Post #54
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-08-11T20:49:39+00:00
- Post Title: Re: Need help: 25 To Life .DBL

i mean where's the link?
## Post #55
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2022-08-27T17:27:16+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from tritterman ↑Thu Aug 11, 2022 8:34 am at Thu Aug 11, 2022 8:34 am
>
> 
Can Anyone just Listen to me for One Day?

I have finished my 25 to Life *.dbl loader module and I have released the following programs:

- 3D Object Converter v9.005 (Windows)
- i3DConverter v4.304	         (macOS)
- i3DConverter v2.304	         (Linux)

How to get the 3D Object Converter v9.005:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version (if you don’t have it yet).
(Or just use the Help/Check for updates... function to get the v9.005.)

How to get the i3DConverter macOS v4.304:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it (if you don’t have it yet).
(Or just use the Help/Check for updates... function to get the v4.304.)

How to get the i3DConverter Linux v2.304:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it (if you don’t have it yet).
(Or just use the Help/Check for updates... function to get the v2.304.)


Use the Draw/Show back-facing geometry function.
## Post #56
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-08-31T00:19:08+00:00
- Post Title: Re: Need help: 25 To Life .DBL

I don't think the 3D Object Converter can give me Chicken Little Models. I just need Blender or Noesis.
I Wish someone will Care for me.
## Post #57
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2022-08-31T03:46:17+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from tritterman ↑Wed Aug 31, 2022 8:19 am at Wed Aug 31, 2022 8:19 am
>
> 
I don't think the 3D Object Converter can give me Chicken Little Models.

Did you try to open your models using the Object Converter?
## Post #58
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-31T05:34:01+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from tritterman ↑Fri Aug 12, 2022 4:49 am at Fri Aug 12, 2022 4:49 am
>
> 
i mean where's the link?Maybe it's gone for good? And from your post as of 6th of July it seems you have a fmt_DBL.py already. So what?  

I found a 4 years old solution of mine, first submesh only, so the right leg is missing:
.



25tolife.jpg (98.24 KiB) Viewed 107 times



If you uploaded the barriere.DBL which seemed to break the .py script I could try hex2obj on it.

If you insist on having a blender or Noesis script, well, then take your time.
## Post #59
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-31T15:48:09+00:00
- Post Title: Re: Need help: 25 To Life .DBL

Here's what I get from chickenlittle.DBL (first sub mesh only, as mostly):
.



CHICKENLITTLE-DBL.jpg (171.04 KiB) Viewed 93 times


(UVs may require some correction - I have no idea.)

note for myself: maybe introduce a 2nd strips algo?
## Post #60
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-08-31T15:50:13+00:00
- Post Title: Re: Need help: 25 To Life .DBL

Thanks for helping.
Even if I don't contact as much.
## Post #61
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-08-31T16:37:06+00:00
- Post Title: Re: Need help: 25 To Life .DBL

I think the guy is gonna show it to noesis with Chicken Little Characters.
## Post #62
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-08-31T22:21:14+00:00
- Post Title: Re: Need help: 25 To Life .DBL

is Someone gonna Still send the Noesis Link of the Models for Chicken Little?
## Post #63
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-09-03T15:21:18+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from Karpati ↑Sun Aug 28, 2022 1:27 am at Sun Aug 28, 2022 1:27 am
>
> 
I have finished my 25 to Life *.dbl loader module and I have released the following programs:
that's not all



DBL.png (90.99 KiB) Viewed 191 times
## Post #64
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-09-03T16:53:48+00:00
- Post Title: Re: Need help: 25 To Life .DBL

Anyone voting for the zip for the .DBL Format for Noesis / Blender?
## Post #65
- Username: Clash
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 04, 2021 3:06 am
- Post datetime: 2023-02-06T02:03:52+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from Durik256 ↑Wed Mar 02, 2022 2:36 am at Wed Mar 02, 2022 2:36 am
>
> 
here is my draft for this format.  

11.png
Does you still have this to work? Im having some problems with dbl from Hannah Spotlight World Tour from Wii, kinda hard to get the mesh

[https://www.dropbox.com/sh/hj0fg3fxcmd9 ... cmrQa?dl=0](https://www.dropbox.com/sh/hj0fg3fxcmd90yh/AAAJR8vSsWup_cM2U3PlcmrQa?dl=0)
## Post #66
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2023-03-08T01:01:59+00:00
- Post Title: Re: Need help: 25 To Life .DBL

i really need to have Chicken Little Models be seen on Noesis.
Is there anyone who can help without me giving Money?
Because it's Cyber Bulling.
## Post #67
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-03-08T20:26:29+00:00
- Post Title: Re: Need help: 25 To Life .DBL

> Reply from Clash ↑Mon Feb 06, 2023 10:03 am at Mon Feb 06, 2023 10:03 am
>
> 
kinda hard to get the mesh

your files are different from the game files from this thread. my plugin does not open them, most likely you need to make a new one plugin..
## Post #68
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2023-06-25T14:34:03+00:00
- Post Title: Re: Need help: 25 To Life .DBL

how can i rip the Textures from the Chicken Little Game Now? Any Ideas?
