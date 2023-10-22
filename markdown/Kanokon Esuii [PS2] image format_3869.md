## Post #1
- Username: Okogawa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 15, 2009 7:16 am
- Post datetime: 2009-11-15T10:40:47+00:00
- Post Title: Kanokon Esuii [PS2] image format?

Hello, I have searched for over two weeks on the Internet for some sort of tool to extract the images from the Japanese PS2 game Kanokon Esuii without any progress. However, for what it is worth (thanks to all searches) I can now extract PSS (video) and AFS (mostly music) files.

Since I am stubborn as a mule, I have even mounted Kanokon Esuii in Pcsx2 0.9.6 (Playstation 2 emulator) and had 3D Ripper DX capture all textures in the background, but alas I could NOT beat the system. Well, 3D Ripper DX managed to capture textures / sprites, but without correct color tables - so I am back on square one

It's little "Obi-Wan you're my last hope" (in this case Xen-Tax) over this issue as I clearly cannot break this nut alone. But let's get down to the details, here is the files on the ISO which I suspect contains the images:

BG2.DAT
BG.DAT
CHARA2.DAT
CHARA.DAT

I know I am greedy now, but is there any way you can point me in a proper direction to a small tool that can extract all the images from the Kanokon Esuii PS2 dat-files and maybe even convert them to a usable file format (png). Oh, is there by chance any extractor that (like there was one for PS1 - don't remember its name now tho) can view graphics in PS2 games?

Here is the Kanokon Esuii files of relevance to this small matter (make sure to mount it with deamontools (or a similar software) - it's not that big to download, so don't be shy.

[http://www.megaupload.com/?d=PGSSKMNC](http://www.megaupload.com/?d=PGSSKMNC)
[http://www.megaupload.com/?d=C7VU1N08](http://www.megaupload.com/?d=C7VU1N08)
[http://www.megaupload.com/?d=V5C5LO92](http://www.megaupload.com/?d=V5C5LO92)
[http://www.megaupload.com/?d=FLDIHEYX](http://www.megaupload.com/?d=FLDIHEYX)
[http://www.megaupload.com/?d=JAL7XXF0](http://www.megaupload.com/?d=JAL7XXF0)

The very best regards

O.

P.S.

For those interested, this is how the images looks like that was "captured" by 3D Ripper DX
[15bdfa06.png](https://xentaxbackup.github.io/file/2531_15bdfa06.png)
## Post #2
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-16T17:50:55+00:00
- Post Title: Kanokon Esuii [PS2] image format?

A simple script that extracts the DAT files:

```

# Constants
Set DATA_START_OFFSET 0x8000
Set OFFSET_FACTOR 0x800
Set SIZE_FACTOR 0x400

# Extract files
For I = 0 < 0x1000
	# Read entry
	Get OFFSET long
	Get SIZE long

	If OFFSET == 0
		If SIZE == 0
			CleanExit
		EndIf
	EndIf

	Math OFFSET *= OFFSET_FACTOR
	Math OFFSET += DATA_START_OFFSET
	Math SIZE *= SIZE_FACTOR

	# Extract
	Log I OFFSET SIZE
Next I

```


However, the files seem to be compressed, and I have no idea about what compression do they use
## Post #3
- Username: Okogawa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 15, 2009 7:16 am
- Post datetime: 2009-11-17T18:37:43+00:00
- Post Title: Kanokon Esuii [PS2] image format?

I gave the suggested software and script a spin, and I am amazed! Finally one can *open* the files  - Personally I think the hardest step was just that part.

The rest should be easy (I hope)..., I am quite sure that the producer of Kanokon Esuii don't use any special homebrew compressor software for their images since that would be overkill, but what I think everything boils down to is two parts:

1. Identifying the compression (which partially leads to step 2)
2. Identifying the image format (which also might be the compression all-in-one)

So, what image formats are most widely used on the PS2 in low-protected games? And it's here I run out of ideas i.e. I hit my head on the wall.

Still, GameZelda..., megathanks for breaking down the biggest obstacle... hope it will be downhill from here as I badly need the raw images
## Post #4
- Username: asmodean
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 23, 2009 4:31 am
- Post datetime: 2009-11-22T20:42:26+00:00
- Post Title: Kanokon Esuii [PS2] image format?

This guy came around asking me about the same thing last week then disappeared or something, I never got any response.  Anyway, since he referenced this thread maybe some of you are interested in the resolution: [http://asmodean.reverse.net/pages/exkkesui.html](http://asmodean.reverse.net/pages/exkkesui.html)
## Post #5
- Username: Okogawa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 15, 2009 7:16 am
- Post datetime: 2009-11-23T13:24:10+00:00
- Post Title: Kanokon Esuii [PS2] image format?

> Reply from asmodean
>
> This guy came around asking me about the same thing last week then disappeared or something, I never got any response.  Anyway, since he referenced this thread maybe some of you are interested in the resolution: http://asmodean.reverse.net/pages/exkkesui.html

At work, but this is wonderful news... I'll look into this tool directly when I come home! 

The very best regards

O
## Post #6
- Username: Okogawa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 15, 2009 7:16 am
- Post datetime: 2009-11-23T18:56:10+00:00
- Post Title: Kanokon Esuii [PS2] image format?

You are a genius! The BIN-extractor works like a charm...   Thanks, thanks, so very very much!

O.
