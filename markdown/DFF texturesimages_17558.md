## Post #1
- Username: Sorans
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Mar 26, 2010 3:53 am
- Post datetime: 2018-01-14T22:09:48+00:00
- Post Title: DFF textures/images

Hello o/

I've come to request some help in converting textures and images to a usable format (PNG for example).

Any help in figuring out how to properly read such files is appreciated.

Thanks in advance!
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-15T02:54:44+00:00
- Post Title: DFF textures/images

> Reply from Sorans
>
> .... I've tried using AceWell's Texture Finder v2.1 ....
i wish, but no it was made by Iceberg, though i probably use it more than he does. 
stl_chara_0069.g1t is 512x512 ABGR4444,
not sure of WorldMap.g1t format, the header says it it is 2048x2048 though.   
i guess being from a mobile game it could be a mobile compressed format,
you could run it through PVRTexTool to check.


 stl_chara_0069.zip
stl_chara_0069.png (79.9 KiB) Downloaded 73 times
## Post #3
- Username: Sorans
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Mar 26, 2010 3:53 am
- Post datetime: 2018-01-15T13:46:45+00:00
- Post Title: DFF textures/images

Thanks for the swift answer! Corrected the slight mistake.

The tool you mentioned has been getting me good results. Thanks 
Would you care to teach me how to figure out the size of the images from the header? I've been doing nothing but trial and error to find it, but I'm now wondering how it can be figured out from the header directly?

Thanks to your suggestion and after reading about Android supported format, I found out that the World Map uses ETC1 compression.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-15T19:43:15+00:00
- Post Title: DFF textures/images

> Reply from Sorans
>
> Would you care to teach me how to figure out the size of the images from the header? I've been doing nothing but trial and error to find it, but I'm now wondering how it can be figured out from the header directly?

the byte at 0x26 stores the width and height in the high and low bit, each of these are multiplied by power of 2 by that many.
for example if the byte is 0x99
the width = power of 2 multiplied 9 times
2x2x2x2x2x2x2x2x2 = 512
the height = power of 2 multiplied 9 times   
2x2x2x2x2x2x2x2x2 = 512

the width and height is 512x512
## Post #5
- Username: Sorans
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Mar 26, 2010 3:53 am
- Post datetime: 2018-01-16T12:13:07+00:00
- Post Title: DFF textures/images

That has been very useful, thanks   

Could I bother you with another question? How would you go about splitting a G1T file that contains multiple assets? It's not compressed and uses RGBA 4444.
I've looked at the raw data and it clearly has many different textures inside. Opening the whole file in PVRTexTool have been kinda okay but the limitations of its raw data wrapping are obvious when I open big files.
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-16T23:54:12+00:00
- Post Title: DFF textures/images

you have to post some samples but you could handle it a couple of ways,
split to individual files and read them or read them from the container in sequence.
## Post #7
- Username: Sorans
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Mar 26, 2010 3:53 am
- Post datetime: 2018-01-17T14:26:52+00:00
- Post Title: DFF textures/images

Hello AceWell,

Would it be simple enough to split them by looking at headers and figuring out their size?
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-18T02:23:25+00:00
- Post Title: DFF textures/images

okay since your sample only contained 2 easy formats i just made a Noesis python script  
*script updated Jan 17, 2019*


 tex_DissidiaFinalFantasyOperaOmnia_g1t.zip
(1.36 KiB) Downloaded 216 times


supports rgba4444, rgba8888, rgb565, a8 and etc1
and because i added ETC support you will also need these files:

```
https://www.mediafire.com/file/p2c8d3fmjnb6kvs/PVRTEXTool4Noesis.zip/file
```

extract them and place the bat and exe file in your Noesis\scenes folder.


and here is bms script to just split the files if you encounter a container with unsupported format  

```

idstring "GT1G0600"
get TOTAL_SZ long
get TABLE_OFFSET long
get FILES long
goto TABLE_OFFSET
savepos BASE_OFFSET
get NAME basename
for i = 1 to FILES
	string NAME p "%s\%d.g1t" NAME i
	get OFFSET long
	savepos TMP
	math OFFSET + BASE_OFFSET
	if i == FILES
		xmath SIZE "TOTAL_SZ - OFFSET"
	else
		get NEXT_OFFSET long
		math NEXT_OFFSET + BASE_OFFSET
		xmath SIZE "NEXT_OFFSET - OFFSET"
	endif
	log NAME OFFSET SIZE
	goto TMP
next i
```

this script will leave the original 8 byte header in each extracted file.
the format is the byte at 0x1
the width and height are stored in the high/low bits of the next byte at 0x2
then skip 5 bytes to go to start of image data
## Post #9
- Username: Sorans
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Mar 26, 2010 3:53 am
- Post datetime: 2018-01-18T11:04:18+00:00
- Post Title: DFF textures/images

You've been extremely helpful, thank you AceWell
## Post #10
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2019-02-18T12:27:09+00:00
- Post Title: DFF textures/images

Any chance for an update to support the alpha masks?
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-18T22:39:35+00:00
- Post Title: DFF textures/images

alpha masks for what? upload some samples please.
## Post #12
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2019-02-18T22:43:59+00:00
- Post Title: DFF textures/images

Ill upload some later. But basically when you export the textures the diffuse comes out fine, but has no alpha channel, which i assume is the extra texture that gets exported with the diffuse. Like when you open the g1t in noesis, it scrolls through textures that then get exported separately.
There has to be some alpha map somewhere since in the game you can see some characters have the alpha maps applied for hair, fur and some accessories

Samples of g1t files [https://mega.nz/#!YaYBCarA!u9EdT3Rf6LlN ... tOB3QKSeM0](https://mega.nz/#!YaYBCarA!u9EdT3Rf6LlNaAAVfNjwAQ1ek1v1SJqZHtOB3QKSeM0)
## Post #13
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-07-26T17:19:09+00:00
- Post Title: DFF textures/images

I know this falls on Necro-Post, but, its the right post to ask about:

Have any figure out the Alpha of the textures so far? Because, actually many have it (specially .dz ones)
## Post #14
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-11-13T07:05:21+00:00
- Post Title: DFF textures/images

Looking for this
