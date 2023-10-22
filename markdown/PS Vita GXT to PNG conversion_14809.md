## Post #1
- Username: WinkelHime
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 06, 2016 5:01 am
- Post datetime: 2016-08-06T18:03:35+00:00
- Post Title: PS Vita GXT to PNG conversion

I extracted CG files from "Eyuu Senki" PS Vita version, but they are in ".gxt" format.
Need help to convert them in png ( tried GXT Converter and Neptunia/Senran kagura gxt sripts for Noesis, no use).
[CGsamples.7z](https://xentaxbackup.github.io/file/11495_CGsamples.7z)
## Post #2
- Username: WinkelHime
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-08-07T00:47:40+00:00
- Post Title: PS Vita GXT to PNG conversion

elif texInfo[8] == 0x85:
			#texFmt = noesis.NOESISTEX_DXT1
			texFmt = noesis.NOESISTEX_RGBA32
			texData = rapi.imageFromMortonOrder(texData, texInfo[9]>>1, texInfo[10]>>2, 4)
			texData = rapi.imageDecodeDXT(texData, texInfo[9], texInfo[10], noesis.FOURCC_DXT1)
			texData = rapi.imageDecodeRaw(texData, texInfo[9], texInfo[10], "r8g8b8a8")
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-07T01:45:44+00:00
- Post Title: PS Vita GXT to PNG conversion

> Reply from chrrox
>
> Code: Select allelif texInfo[8] == 0x85:
	#texFmt = noesis.NOESISTEX_DXT1
	texFmt = noesis.NOESISTEX_RGBA32
	texData = rapi.imageFromMortonOrder(texData, texInfo[9]>>1, texInfo[10]>>2, 4)
	texData = rapi.imageDecodeDXT(texData, texInfo[9], texInfo[10], noesis.FOURCC_DXT1)
	texData = rapi.imageDecodeRaw(texData, texInfo[9], texInfo[10], "r8g8b8a8")

where is the elusive Noesis script that this goes into?    
it doesn't look like it belongs in this one 
[viewtopic.php?p=119216#p119216](http://forum.xentax.com/viewtopic.php?p=119216#p119216)


edit
okay since no one is linking their sources i made a new Noesis script with chrrox's info to open these samples   
*updated Nov 18, 2016*


 tex_EyuuSenki_PSVita_gxt.zip
(936 Bytes) Downloaded 106 times



don't think those dimensions are correct for that image in chrrox's post,
1024x1024 seems to support the image data better
## Post #4
- Username: WinkelHime
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 06, 2016 5:01 am
- Post datetime: 2016-08-08T07:59:33+00:00
- Post Title: PS Vita GXT to PNG conversion

Good progress.
For reference, thats how it should look like.
## Post #5
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-08-08T08:38:10+00:00
- Post Title: PS Vita GXT to PNG conversion

okay since no one is linking their sources i made a new Noesis script with chrrox's info to open these samples   


[viewtopic.php?f=16&t=14626](http://forum.xentax.com/viewtopic.php?f=16&t=14626)
## Post #6
- Username: WinkelHime
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 06, 2016 5:01 am
- Post datetime: 2016-08-08T12:27:39+00:00
- Post Title: PS Vita GXT to PNG conversion

Tnx for your work, got all CG's that I need.
## Post #7
- Username: pashok6798
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Sep 06, 2014 2:45 am
- Post datetime: 2016-08-10T16:40:39+00:00
- Post Title: PS Vita GXT to PNG conversion

How did you extract resource from PS Vita? I know about henkaku, but I can't decrypt resources on game which I wanted.
## Post #8
- Username: WinkelHime
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 06, 2016 5:01 am
- Post datetime: 2016-08-13T01:16:56+00:00
- Post Title: PS Vita GXT to PNG conversion

> Reply from pashok6798
>
> How did you extract resource from PS Vita? I know about henkaku, but I can't decrypt resources on game which I wanted.
I don't own Vita personally so have little knowledge about actual process. Got ready to extraction game files by my source.
## Post #9
- Username: Acewell
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-09-23T12:46:06+00:00
- Post Title: PS Vita GXT to PNG conversion

I wrote a GXT importer for Noesis about 2 years ago, for my own personal use, because Vita content wasn't really public at that point. Since people are leaking things all over the place, I figured I might as well enable it in the latest release, so it's in Noesis 4.2. It will handle these GXT's, as well as probably any other GXT on the planet, including correct PVRTC 1 & 2 decoding. Its PVRTC2 decoder is actually the only hardware-accurate one in existence that I'm aware of - the PvrTexTool and SCE libs both handle the palettized block mode incorrectly, which produces some subtle flaws that you won't see on hardware. So that's something to keep in mind if you've been using a makeshift solution by changing the block ordering in order to shovel these things into PvrTexTool or something.

So, enjoy. By the way, the issue with your script here was that tiled data on this hardware will always be padded to a power of 2, so it's correct to pad to the next power of 2 when not dealing with LINEAR/LINEAR_STRIDED data.
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-15T02:01:23+00:00
- Post Title: PS Vita GXT to PNG conversion

> Reply from MrAdults
>
> ... tiled data on this hardware will always be padded to a power of 2, so it's correct to pad to the next power of 2 when not dealing with LINEAR/LINEAR_STRIDED data.
okay i know Noesis has native support for gxt now but i wanted to fix the python script for 
completion's sake. i updated my previous post with the updated script so it read the width and height
and will round them up to the next power of 2 so they look correct.
## Post #11
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2016-10-17T14:08:03+00:00
- Post Title: PS Vita GXT to PNG conversion

Hey uhm, I'm having some trouble with a specific gxt file, and it seems to be recurring in a few. It throws the error 'an integer is required'?

[https://www.dropbox.com/s/chvcm8200nzp0dm/GEAR.gxt?dl=0](https://www.dropbox.com/s/chvcm8200nzp0dm/GEAR.gxt?dl=0)
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-17T20:08:04+00:00
- Post Title: PS Vita GXT to PNG conversion

it works fine with Noesis native plugin, don't use my script because it 
was made to work only on the samples in the first post (type 0x85)
