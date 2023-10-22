## Post #1
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-23T05:34:10+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

This thread is about converting x2t texture files of various size from the cancelled Free Radical game where they have no header and only some have a footer with info about the texture.



here is the Noesis python plugin for the x2t textures i originally released on page 3 of this thread


 fmt_SWBF3_x2t.zip
(730 Bytes) Downloaded 119 times


Thanks to chrrox for the base code from fmt_star_wars_kinect_tga.py.
The script goes in the Noesis\plugins\python folder
it is titled for SWBF3 but is mostly universal for swizzled 360 textures. 

edit
After a bit of testing i have determined there was no noticable consequence to
removing the byte read length setting from the script, at first i was concerned 
the footer bytes would shift the image data but i don't see any ill effects. 
Now you only have to open the script and set the format type, width and height.  



........................................................................................
Wobble created a compiled dll for this format too here
[viewtopic.php?f=18&t=13868&start=60#p166977](https://forum.xentax.com/viewtopic.php?f=18&t=13868&start=60#p166977)

Read the thread from then forward for details on usage
## Post #2
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-25T04:07:41+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-31T01:49:15+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

The mysterious texture format here is the main thing holding us back and i'm curious what results could come from running these x2t samples through a couple of the unreleased tools in the thread here
[viewtopic.php?f=18&t=12224](http://forum.xentax.com/viewtopic.php?f=18&t=12224)

mainly EcheloCross's Game Format Scanner or michalss's Texture Convertor (PC,X360)
[viewtopic.php?p=100537#p100537](http://forum.xentax.com/viewtopic.php?p=100537#p100537)
[viewtopic.php?p=103260#p103260](http://forum.xentax.com/viewtopic.php?p=103260#p103260)
## Post #4
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-31T07:01:51+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #5
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-31T07:23:01+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #6
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-31T08:23:34+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #7
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-31T10:11:03+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #8
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-31T13:13:16+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-01T03:40:29+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

I sent michalss a message to see if he could get any decent results from the x2t samples with his Texture Convertor (PC,X360) but Noesis looks like it should be capable of untiling these textures too according to some things in __NPReadMe.txt

{"imageUntile360Raw", Noesis_ImageUntile360Raw, METH_VARARGS, "returns untiled raw pixel data. (Oiii)"}, //args=source image array, width, height, bytes per pixel
{"imageUntile360DXT", Noesis_ImageUntile360DXT, METH_VARARGS, "returns untiled dxt pixel data. (Oiii)"}, //args=source image array, width, height, block size (e.g. 8 for dxt1, 16 for dxt5)

I have no clue how to set up a python script to read raw image data and have it displayed untiled in the program though.  
i'll look for this unbundler and see if i can get anything out of it.
## Post #10
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-01T05:04:54+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #11
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-01T10:19:14+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #12
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-02T06:31:38+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #13
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-02T06:49:42+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from Wobble
>
> I don't know Python well, but I know C.  It looks like you can create C plugins too with Noesis.
So, I create a simple one from the PCX image source.

Functions:
Code: Select all	//untiles raw pixel data
	void				(*Noesis_UntileImageRAW)(BYTE *dst, BYTE *src, int dstSize, int imgW, int imgH, int bytesPerPix);
	//untiles dxt-encoded pixel data
	void				(*Noesis_UntileImageDXT)(BYTE *dst, BYTE *src, int dstSize, int imgW, int imgH, int blockSize);


I think calling RAW on scroller_right.x2t actually works.  That is a 32-bit uncompressed image, swizzled.
neosis.PNG

But, it fails for others.  They might be DXT.  I haven't had enough time to test more.  Lots of files have zero headers.
Might have to guess width,height based on file size of other files with good headers.

Um i would most likely guess most if not all characters would be like 1024x1024,weapons around 512x512 (maybe some 1024x1024 for first person view models) and vehicles around those 2 some could be higher, but with it being a quick and dirty pc to xbox 360 port some of them could be higher just not scaled right for the xbox 360 yet.
## Post #14
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-02T15:41:00+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #15
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-02T18:33:45+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #16
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-02T18:35:24+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-02T21:37:41+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

That was a valiant effort Wobble, thanks!   
maybe MrAdults could step in and offer some advice on this or a quick solution.

edit
should there be anything in the code about Endianess?
The fmt_star_wars_kinect_tga.py plugin for Kinect Star Wars textures might hold the key

[viewtopic.php?f=16&t=8714](http://forum.xentax.com/viewtopic.php?f=16&t=8714)

```
	#DXT1
	if imgFmt == 0x28:
		data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 8)
		texFmt = noesis.NOESISTEX_DXT1
	#DXT5
	elif imgFmt == 0x33:
		data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
		texFmt = noesis.NOESISTEX_DXT5
	#DXT5 packed normal map
	elif imgFmt == 0x1C:
		data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
		data = rapi.imageDecodeDXT(data, imgWidth, imgHeight, noesis.FOURCC_ATI2)
		texFmt = noesis.NOESISTEX_RGBA32
	#DXT5 packed normal map2
	elif imgFmt == 0x36:
		data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
		data = rapi.imageDecodeDXT(data, imgWidth, imgHeight, noesis.FOURCC_ATI1)
		texFmt = noesis.NOESISTEX_RGBA32
	#DXT1 packed normal map
	elif imgFmt == 0x16:
		data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 8)
		data = rapi.imageDecodeDXT(data, imgWidth, imgHeight, noesis.FOURCC_DXT1NORMAL)
		texFmt = noesis.NOESISTEX_RGBA32
	#raw
	elif imgFmt == 0x1B:
		data = rapi.imageUntile360Raw(rapi.swapEndianArray(data, 4), imgWidth, imgHeight, 4)
		texFmt = noesis.NOESISTEX_RGBA32
	#unknown, not handled
...
```
## Post #18
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-03T02:31:15+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #19
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-03T03:08:00+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from Wobble
>
> Woohoo, you got it!
62e82b02_solo_face_1024.JPG

The data needs to be endian swapped before passing it to unswizzle functions.

But, it's not perfect.  The pixels are still very jagged.  I  don't know if this is how the original texture is supposed to look like on the XBox 360,
or if the unswizzle function is not unswizzling the entire image.

It seems like maybe it's pixelated like that cause the head is maybe 512x512 and not 1024x1024.

But great job this is really amazing now we just need a proper importer for noesis for the models.
## Post #20
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-03T08:19:11+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #21
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-03T15:48:00+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #22
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-03T18:29:32+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #23
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-03T21:02:09+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from Wobble
>
> Last one:
- Added filename argument scanning for zero headers.  Arguments must be separated by spaces.
x2t_image.zip
Code: Select all<filename> <width> <height> <bpp> <format>.x2t

This is really amazing it's just sad they didn't extract with the proper file names cause going down through noesis to find textures you want is pretty hard since there are so many.
## Post #24
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-03T21:37:33+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

The textures were extracted with the names that were stored in the str file, and these same names are referenced in the rax files, the names are correct for this build.
## Post #25
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-03T22:08:28+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from AceWell
>
> The textures were extracted with the names that were stored in the str file, and these same names are referenced in the rax files, the names are correct for this build.

Ah okay,

Well i found something that isn't right compared to one of the textures i already had to one i just exported.

The one i have here is 2048x2048 and the one i converted is 1024x1024.

Now i know the plugin isn't fully finished but i thought i'd point this out to help you fix it.

Pre-alpha 1024x1024


Final 2048x2048
## Post #26
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-04T02:20:58+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #27
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-05T06:17:52+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

I was just comparing the Kinect Star Wars tga python script with your x2t_image.cpp and was wondering if image_bpp/8 should be image_bpp/4 instead for untile raw

```

 if(image_format == 3) {

    //                                   BYTE *dst,    BYTE *src, int dstSize,   int imgW,     int imgH, int bytesPerPix
    rapi->Noesis_UntileImageRAW( unswizzled_buffer, image_buffer, image_size, image_width, image_height, (image_bpp/8) );
 }

```


fmt_star_wars_kinect_tga.py

```
	elif imgFmt == 0x1B:
		data = rapi.imageUntile360Raw(rapi.swapEndianArray(data, 4), imgWidth, imgHeight, 4)
		texFmt = noesis.NOESISTEX_RGBA32
```
## Post #28
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-06T03:22:39+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #29
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-06T03:43:33+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #30
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-07T00:18:31+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

this is what MrAdults says here [viewtopic.php?p=115576#p115576](http://forum.xentax.com/viewtopic.php?p=115576#p115576)

> There are lots of image processing scripts of this nature to use as examples over on the old Google Code depot.
>
> The Gamebryo NIF script shows how to do all kinds of untiling including 360-style and straight up Morton order. Use rapi.swapEndianArray to quickly endian-swap DXT blocks as commonly needed on the 360, this is demonstrated in the BulletWitch script in cprLoadTexture.

> Reply from Wobble
>
> The problem is with the imageUntile360Raw() function.  It doesn't seem work for these textures.
Can't do nothing about it, because we don't know how it works.  It is based on Morton order or something else?
maybe it does have something to do with Morton order.  

this is a snip from the fmt_gamebryo_nif.py script that i think MrAdults was talking about, morton untile is near the end

```
		pixObject = nif.objects[texObject.pixLinkID]
		noeFmt = noesis.NOESISTEX_UNKNOWN
		pixelFormatObj = noeSafeGet(pixObject, "pixelFormat")
		if pixelFormatObj is None:
			print("WARNING: Object", texObject.pixLinkID, "type", pixObject.typeName, "should have contained a pixel format, but didn't.")
			continue
		pixelFormat = pixelFormatObj.format
		imageData = pixObject.imageData
		
		pixelImageInfo = [pixObject.numFaces, pixObject.mipLevels, pixObject.mipsTotalSize, pixObject.mipInfo]
		
		if pixelFormat == NIFTEX_RGB:
			noeFmt = noesis.NOESISTEX_RGBA32
			imageData = noeProcessImage(imageData, pixelImageInfo, rapi.imageDecodeRaw, "r8g8b8")
		elif pixelFormat == NIFTEX_RGBA:
			noeFmt = noesis.NOESISTEX_RGBA32
			if pixObject.platform == NIF_PLATFORM_PS3: #alpha first on ps3 (or so we not always correctly assume)
				imageData = noeProcessImage(imageData, pixelImageInfo, rapi.imageDecodeRaw, "a8r8g8b8")
			elif pixObject.platform == NIF_PLATFORM_XBOX360: #another potentially-faulty assumption - bgra for 360
				imageData = noeProcessImage(imageData, pixelImageInfo, rapi.imageDecodeRaw, "b8g8r8a8")
		elif pixelFormat == NIFTEX_DXT1:
			noeFmt = noesis.NOESISTEX_DXT1
		elif pixelFormat == NIFTEX_DXT3:
			noeFmt = noesis.NOESISTEX_DXT3
		elif pixelFormat == NIFTEX_DXT5:
			noeFmt = noesis.NOESISTEX_DXT5
		elif pixelFormat == NIFTEX_MONO:
			#expand out to rgba32
			noeFmt = noesis.NOESISTEX_RGBA32
			imageData = noeProcessImage(imageData, pixelImageInfo, rapi.imageDecodeRaw, "r8")
			imageData = noeProcessImage(imageData, pixelImageInfo, rapi.imageKernelProcess, 4, nifImageExpandMonoColorKernel)
		else:
			print("WARNING: Unsupported texture format", pixelFormat)

		if noeFmt != noesis.NOESISTEX_UNKNOWN:
			if pixelFormatObj.tiling != 0:
				#lots of games seem to have bad mip offsets when using tiling/swizzling modes,
				#which don't take into account necessary platform-specific padding. so, sadly,
				#we'll have to skip the mips.
				pixelImageInfo[1] = 1
			
			if pixelFormatObj.tiling == 1:
				#360 untile
				if noeFmt == noesis.NOESISTEX_RGBA32:
					imageData = noeProcessImage(imageData, pixelImageInfo, rapi.imageUntile360Raw, 4)
				else: #dxt
					imageData = noeProcessImage(imageData, pixelImageInfo, rapi.imageUntile360DXT, 8 if noeFmt == noesis.NOESISTEX_DXT1 else 16)
			elif pixelFormatObj.tiling == 3:
				#morton untile
				if noeFmt == noesis.NOESISTEX_RGBA32:
					imageData = noeProcessImage(imageData, pixelImageInfo, rapi.imageFromMortonOrder, 4, 2 if pixObject.platform == NIF_PLATFORM_VITA else 0)
				else: #dxt
					dxtBlockBytes = 4 if noeFmt == noesis.NOESISTEX_DXT1 else 8
					imageData = rapi.imageFromMortonOrder(imageData, pixObject.width>>1, pixObject.height>>2, dxtBlockBytes)
					#possible todo - support untiling dxt blocks with multiple mips/faces
					pixelImageInfo[0] = 1
					pixelImageInfo[1] = 1
					
```
## Post #31
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-07T01:06:11+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #32
- Username: gistech
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 07, 2016 5:12 am
- Post datetime: 2016-02-07T12:29:52+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

Some interesting progress is going on here.
## Post #33
- Username: Wobble
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-02-08T05:23:51+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

I don't have this game/data, and looking at the samples provided on page 1 the rip is clearly fucked. Thoughts:

- No runtime is going to be intuiting image format/size from file size, find the proper place to get reliable header data (possibly another archive/binary entirely) before running around in circles.
- Don't use the raw untile function on DXT data. The routines for each are very different. (the Noesis implementation isn't based on any existing code in the wild)
- Some of the "garbled pixels" shots provided in this thread are telltale signs of trying to interpret tiled DXT1 as tiled DXT5.
- You aren't limited to DXT1-5, a number block compression formats are also possible which don't even fall under moden BC*, including a DXT1 normal map compression. (Noesis supports these as well)
- Tiling/twiddling/etc. is of course lossless. If you think about the reason to use any form of micro/macro tiling mode, and what Morton coordinates give you, you can see that it's all about maximizing efficiency of the texture cache. It's just the same data, but sampling patterns are usually going to dictate that caching that texture block that lays out linearly in memory is going to be of much greater benefit than caching the rest of a linear-ordered row of pixels occupying the same memory.
- You need to be obeying expectations for implicit alignment between rows (or rows of blocks in the case of DXT), mipmaps, and cube faces as applicable. For example, a 30x30 DXT1 texture will contain block data for a 32x32 texture, as a single DXT block represents 4x4 texels. There are also different alignment/padding requirements depending on the format/tiling for mipmaps and cubemaps. Tiling may also dictate row alignment/padding beyond DXT block-alignment. If variable modes are employed then the correct header data for each texture no doubt specifies this.

Ok, have fun.
## Post #34
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-08T08:42:39+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from gistech
>
> Some interesting progress is going on here.
Indeed!   




*i removed the attached file and turned off logPopup, see the first post for this Noesis python plugin*


Thanks to chrrox for the base code from fmt_star_wars_kinect_tga.py.
This script is titled for SWBF3 but it is mostly universal for swizzled 360 textures. 
You have to open the script and set the format type, width and height. 
i have not tested on a lot of textures, its pretty much trial and error but it should get the job done.
## Post #35
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-08T08:48:59+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from AceWell
>
> gistech wrote:Some interesting progress is going on here.
Indeed!   


fmt_SWBF3_x2t.zip

Thanks to chrrox for the base code from fmt_star_wars_kinect_tga.py.
This script is titled for SWBF3 but it is mostly universal for swizzled 360 textures. 
You have to open the script and set the length of data in bytes, format type, width and height. 
i have not tested on a lot of textures, its pretty much trial and error but it should get the job done.

Alright so most of the characters are what 1024x1024? but what are the faces 512x512?
## Post #36
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-08T09:15:19+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

I don't know you'll have to play around with the settings.

I forgot to turn off the logPopup in the script, you comment line 7 out with this # so it won't appear.   

maybe someday we can hook the script into a tool window.
## Post #37
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-08T10:12:55+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #38
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-08T10:14:58+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #39
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-08T16:08:15+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from Wobble
>
> Here is the fixed Noesis plugin.
x2t_image_noesis_final.zip

Thanks all!

So i'm finding a lot of textures that aren't working mainly if you go by name in Noesis and go down to 7efb9702.x2t that's where i started cause i was looking for the DC15 carbine first person texture and i found that.

From what i'm seeing all the texture that are after 6fd20406m.x2t to the end of 7ffad30at.x2t are broken and that's just what i've viewed so far, but some of them are so small it doesn't even matter but the ones that aren't are broken.

There are way more i'm seeing now.
## Post #40
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-08T23:27:53+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #41
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-08T23:35:24+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from Wobble
>
> JakeGreen wrote:
So i'm finding a lot of textures that aren't working mainly if you go by name in Noesis and go down to 7efb9702.x2t that's where i started cause i was looking for the DC15 carbine first person texture and i found that.

From what i'm seeing all the texture that are after 6fd20406m.x2t to the end of 7ffad30at.x2t are broken and that's just what i've viewed so far, but some of them are so small it doesn't even matter but the ones that aren't are broken.

There are way more i'm seeing now.

There are still textures with zero headers.  Nothing is going to fix that.
If you need to see a particular texture, then you need to guess its header.

For example, if you want to see the storm trooper texture posted above, add this to the filename:
Code: Select all7f40ed02.x2t  ->   7f40ed02 1024 1024 32 5.x2t


Always use spaces to separate parameters.

Alright, well i've noticed some of the vehicle textures you can view them but they look like this.

They mostly look like they are complete just wrong format.
## Post #42
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-08T23:37:44+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #43
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-09T00:09:24+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from Wobble
>
> JakeGreen wrote:
They mostly look like they are complete just wrong format.


You got it right, just the wrong size.  When you see a texture with "bands" like that, it means you need to increase the texture size by a power of 2.  If you picked 512x512, go up to 1024x1024.

Try:
Code: Select all0350b882 2048 2048 32 5.x2t

Ah that works great i kept having problems with it even after i seen your updated post and i realized i had Acewell's plugin in there and once i removed it that did the trick.
## Post #44
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-09T00:34:12+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #45
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-09T00:37:01+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from Wobble
>
> If you want a texture loader that uses a "fixed" size, all the time, then using his Python script is a good idea.
You can scan for all 1024x1024 textures, and nothing else.

Well so far i've found textures that have been so messed up with pixels and used your method and it worked perfectly.
## Post #46
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-09T01:08:05+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from JakeGreen
>
> Ah that works great i kept having problems with it even after i seen your updated post and i realized i had Acewell's plugin in there and once i removed it that did the trick.
Yeah you cant have both plugins loading at the same time because they will clash.  

> Reply from JakeGreen
>
> Well so far i've found textures that have been so messed up with pixels and used your method and it worked perfectly. 
which textures? are you sure you had the right settings in the script?
## Post #47
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-09T01:12:43+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from AceWell
>
> JakeGreen wrote:Ah that works great i kept having problems with it even after i seen your updated post and i realized i had Acewell's plugin in there and once i removed it that did the trick.
Yeah you cant have both plugins loading at the same time because they will clash.  
JakeGreen wrote:Well so far i've found textures that have been so messed up with pixels and used your method and it worked perfectly. 
which textures? are you sure you had the right settings in the script?

Textures from the Spoiled_Clone_Stormtrooper in his plugin by default they were super pixelated and really small but once i applied his method to the filename it came out perfect, texture name was 1f2e2f82.x2t
## Post #48
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-09T01:23:32+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from JakeGreen
>
> Textures from the Spoiled_Clone_Stormtrooper in his plugin by default they were super pixelated and really small but once i applied his method to the filename it came out perfect, texture name was 1f2e2f82.x2t
Your settings were wrong, it came out perfect with this

```
	imgWidth = 1024                    #set image width
	imgHeight = 1024                   #set image height
```
## Post #49
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-09T01:36:55+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from AceWell
>
> JakeGreen wrote:Textures from the Spoiled_Clone_Stormtrooper in his plugin by default they were super pixelated and really small but once i applied his method to the filename it came out perfect, texture name was 1f2e2f82.x2t
Your settings were wrong, it came out perfect with this
Code: Select all   datasize = 720896                 #set the length of data in bytes
	bs = NoeBitStream(data)
	imgFmt = 1                        #set image format 1 2 3 4 5 6
	imgWidth = 1024                    #set image width
	imgHeight = 1024                   #set image height

Well this is what it looked like before i did anything with just wobble's dll



and after i added 1f2e2f82 1024 1024 32 5.x2t
## Post #50
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-09T01:45:23+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

Oh so you meant you weren't using proper file naming with his plugin and were expecting the textures to come out perfect automagically... thought you were talking about the python script at first. 

edit
heres a list of all the texture sizes i see
5 kb = 
9 kb = 
17 kb = 
25 kb =
33 kb =
49 kb =
65 kb =
81 kb =
97 kb =
105 kb =
113 kb =
121 kb =
129 kb =
193 kb =
209 kb =
225 kb =
241 kb =
257 kb =
345 kb =
361 kb =
385 kb =
513 kb =
705 kb = 1024x1024
721 kb =
769 kb =
1025 kb =
1385 kb =
1409 kb =
2049 kb =
2753 kb =
2769 kb =
4097 kb =
5465 kb =
5481 kb =
5505 kb =
8193 kb =
10945 kb =
10961 kb =
21889 kb =

guess i'll try to find image dimensions for these sizes
## Post #51
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-09T02:19:26+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #52
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-09T08:58:31+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

Well i did get this so far don't know if it's helpful or not but yeah.....

Textures with 128kb (if you look at this via windows search it will say 129kb)
256 256 32 4

Textures with 192kb (if you look at this via windows search it will say 193kb)
512 512 32 5

Textures with 384kb (if you look at this via windows search it will say 385kb)
512 512 32 4

Textures with 704kb (if you look at this via windows search it will say 705kb)
1024 1024 32 5

Textures with 720kb (if you look at this via windows search it will say 721kb)
1024 1024 32 4

Textures for 1.37mb
2048 2048 32 5

Textures with 2.68mb (if you look at this via windows search it will say 2,753kb)
2048 2048 32 5
## Post #53
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-10T14:18:08+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #54
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-11T09:44:37+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

Alright so i tried finishing the list i did most of the textures that matter cause the smaller ones like 64x64 aren't that important as they seem liked resized main textures.

I will update it if i find anymore but i don't think there will be anymore

```
256 256 32 5

Textures with 128kb (129kb)
256 256 32 4

Textures with 192kb (193kb)
512 512 32 5

Texture with 208kb(209kb)
Unknown (32 4 or 32 5 didn't work didn't know what other numbers to try, but texture is probably 512x256)

Textures with 384.kb (385kb)
512 512 32 4

Textures with 256.kb (257kb)
1024 512 32 5

Textures with 704kb (705kb)
1024 1024 32 5

Textures with 720kb (721kb)
1024 1024 32 4

Textures for 1.35mb
2048 2048 32 5

Textures for 1.37mb
2048 2048 32 5

Textures with 2.68mb (2,753kb)
2048 2048 32 5

Textures with 2.70mb
unknown(couldn't figure it out, but it's most likely 2048x2048)

Textures (4mb) (4,097kb)
4096 2048 32 5

Textures with 5.33mb (5,465kb)
2048 2048 32 5

Textures with 5.37mb (5,505kb)
2048 2048 32 4 

Textures with 8mb (8193kb)
4096 2048 32 5

Textures with 10.6mb (10,954)
4096 2048 32 5

Textures with 21.3mb (21,889kb)
4096 4096 32 4

```
## Post #55
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-11T10:48:34+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from JakeGreen
>
> Code: Select allTextures with 2.70mb
unknown(couldn't figure it out, but it's most likely 2048x2048)
these seem to work with the width and height at 1024x2048 or 2048x1024 in dxt5
## Post #56
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-13T15:41:27+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #57
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-13T15:42:17+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

[out]
## Post #58
- Username: cocco1960
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 10, 2016 4:01 pm
- Post datetime: 2017-10-06T14:26:43+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

Hi, I just tried to use the script and it gives me bad array error  on every texture and it says "the item cannot be previewed but may be exportable. Would you like to export?" And when I export it  says bad array again. Do you know any fix?
## Post #59
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-06T15:53:21+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

not sure what you mean, most of the textures are headerless and the script is not automated,
you have to set the values in it like i explained in the first post.
## Post #60
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2020-09-17T01:52:32+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

Sorry to necropost, but does anyone still have the DLL? I've been converting Elite Squadron maps, and most share textures with Battlefront III. Acewell's python plugin has been amazing, but if the DLL can scan for the correct size, etc that'd be great. I'm not sure if it does, but thus far it's a long (but doable) process.
## Post #61
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-09-19T03:31:50+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

i actually have a better version of the python script now that reads
that footer data when available i just have not uploaded yet.   

> Reply from Teancum ↑Thu Sep 17, 2020 9:52 am at Thu Sep 17, 2020 9:52 am
>
> does anyone still have the DLL?
looks like that attachment was nuked, here it is again:


 x2t_image_noesis_final.zip
(5.83 KiB) Downloaded 58 times
## Post #62
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2020-09-24T20:52:09+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

Thanks Acewell. I went through and extracted a ton of textures last week with your script. Had a few I couldn't figure out, but I pulled several hundred out.
## Post #63
- Username: Stoppingriver52
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 09, 2020 9:41 am
- Post datetime: 2021-12-14T02:53:49+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from Acewell ↑Sat Sep 19, 2020 11:31 am at Sat Sep 19, 2020 11:31 am
>
> 
i actually have a better version of the python script now that reads
that footer data when available i just have not uploaded yet.   
Teancum wrote: ↑Thu Sep 17, 2020 9:52 amdoes anyone still have the DLL?
looks like that attachment was nuked, here it is again:
x2t_image_noesis_final.zip

Do you still plan to upload the new python script at some point?
## Post #64
- Username: ggctuk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 07, 2016 5:08 am
- Post datetime: 2022-05-29T07:40:19+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.x2t)

> Reply from Acewell ↑Sat Sep 19, 2020 11:31 am at Sat Sep 19, 2020 11:31 am
>
> 
i actually have a better version of the python script now that reads
that footer data when available i just have not uploaded yet.   
Teancum wrote: ↑Thu Sep 17, 2020 9:52 amdoes anyone still have the DLL?
looks like that attachment was nuked, here it is again:
x2t_image_noesis_final.zip

May I ask how you use this? It looks like the instructions were also nuked.
