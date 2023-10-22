## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-08-01T19:33:19+00:00
- Post Title: I.M.Meen (1995 PC/DOS) ANI format

[http://www.sendspace.com/file/xsl64g](http://www.sendspace.com/file/xsl64g)

This is the intro animation to the game. The format is very similar to that used in the CD-i Zelda games. The compression is RLE7 I believe. And the palette is ALSO RLE compressed, but some places in the decompression currently comes up distorted. As seen here:

[http://www.youtube.com/watch?v=b8hTgBD-Ad8](http://www.youtube.com/watch?v=b8hTgBD-Ad8)

Here is what we have so far.

Intro.ANI as in link above is this:

[http://www.youtube.com/watch?v=ekkk8sVajqE](http://www.youtube.com/watch?v=ekkk8sVajqE)

Minus the background which is a separate PCX image.

From KiiroBomber

> Want some info ?
>
> It's in RLE, same format as the Zelda CDi.
>
> It's even almost the same for the pallette, it's RRGGBB (but it gets a 00 between two colors, it's like : RR GG BB 00 RR GG BB 00).

Could somebody fill in the gaps that makes it distorted?
## Post #2
- Username: NotAnS
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 24, 2009 8:07 am
- Post datetime: 2009-10-06T21:23:30+00:00
- Post Title: I.M.Meen (1995 PC/DOS) ANI format

I would really like to work on this, but I'm not really experienced, so I might not be of much help.

From the other topic:

```
4 bytes unsigned long -> FileSize+6
4 bytes string -> Signature HDR.
```


I'm trying to find some more things about the header, but can't find anything for the dimensions of 320 or 200 (those are the dimensions that dosbox shows) which is anywhere near the beginning of the file
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-10-07T20:48:33+00:00
- Post Title: I.M.Meen (1995 PC/DOS) ANI format

320x200 is also the size of the PCX backgrounds.
## Post #4
- Username: NotAnS
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 24, 2009 8:07 am
- Post datetime: 2009-10-08T10:30:54+00:00
- Post Title: I.M.Meen (1995 PC/DOS) ANI format

> Reply from Darkfox
>
> 320x200 is also the size of the PCX backgrounds.
Maybe DosBox is only 320x200 because of the PCX file, because it seems like the PCX files are larger and better resolution. Unfortunately, I don't have a screenshot of one of the ani files, so I can't play around with it to find the actual resolution
EDIT: No, the actual animation is also 320x200
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-10-09T04:07:02+00:00
- Post Title: I.M.Meen (1995 PC/DOS) ANI format

Yeah, it'd have to be to fit the background.
## Post #6
- Username: NotAnS
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 24, 2009 8:07 am
- Post datetime: 2009-10-09T14:22:29+00:00
- Post Title: I.M.Meen (1995 PC/DOS) ANI format

> Reply from Darkfox
>
> Yeah, it'd have to be to fit the background.
No, it can't be because at 320x200, the pixels are exactly the same size, horizontally and vertically. Not to mention, the animation hits the top, bottom, and sides of the image, which means it can't just be a smaller image.
Here's a screenshot that shows most those things
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-10-09T18:29:34+00:00
- Post Title: I.M.Meen (1995 PC/DOS) ANI format

O_o You are saying it is 320x200, I'm saying it is 320x200 and yet you seem to be disagreeing? Or are you thinking I'm saying that the animation frames are being stretched? I'm not saying that.
## Post #8
- Username: NotAnS
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 24, 2009 8:07 am
- Post datetime: 2009-10-09T19:06:43+00:00
- Post Title: I.M.Meen (1995 PC/DOS) ANI format

> Reply from Darkfox
>
> O_o You are saying it is 320x200, I'm saying it is 320x200 and yet you seem to be disagreeing? Or are you thinking I'm saying that the animation frames are being stretched? I'm not saying that.
Oh sorry about that. I misunderstood what you said

There's something weird in the executable about the pallettes

```
ANIM_PAL.PCX..Cannot open animation palette ANIM_PAL.PCX..Cannot read animation palette from ANIM_PAL.PCX
```

I can't find anything about an anim_pal.pcx, but if that's where the palletes are, then what is this at the beginning of the file?
## Post #9
- Username: NotAnS
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 24, 2009 8:07 am
- Post datetime: 2009-10-11T22:36:48+00:00
- Post Title: I.M.Meen (1995 PC/DOS) ANI format

Here's something that might be the pallete
It's 640 (assuming it counts the first line as 0) lines, and I tried looking for 640(280 in hex) in the header, and it showed nothing until a while
[palette.zip](https://xentaxbackup.github.io/file/2435_palette.zip)
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-10-12T22:42:46+00:00
- Post Title: I.M.Meen (1995 PC/DOS) ANI format

The palette data is within the ANI file. However the palettes unaccounted for are for the image files. The palette mentioned may in fact be the palette for the animated sprites (just a thought) which would also be greatly useful.
## Post #11
- Username: NotAnS
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 24, 2009 8:07 am
- Post datetime: 2009-11-04T15:52:18+00:00
- Post Title: I.M.Meen (1995 PC/DOS) ANI format

I'm going to try to find the exact colors in the intro via recorded video, then see where they all are in that pallet data I posted before.
I'll also try looking for that number of colors in the header, and hopefully something will pop up.

If you didn't know, the game can be used as a player by replacing the logo animation with other animation.
Also, is there an in depth description of how RLE7 works? I can't find one anywhere, and that CD-i site doesn't give anything more than an already compiled RLE7 viewer
## Post #12
- Username: LuigiBlood
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jan 29, 2010 5:26 am
- Post datetime: 2010-01-29T18:09:58+00:00
- Post Title: I.M.Meen (1995 PC/DOS) ANI format

RLE7 format :

CD-i's RLE 7

The CD-i RLE7 is similar to CLUT8 but it's a compressed format. However its size is generally smaller, its palette may not contains more than 128 colors (against 256 for CLUT . RLE is one of the simplest compression methods. Here are the rules.

If the first bit of the byte is false, the next 7 bits are the color code (reffering to the palette) to be drawn 1 time.
Else, the next 7 bits are the color code (refering to the palette) to be drawn x times. x actually is the following byte.
In the second case, if the following byte is 0 then draw the color to the end of the image's width.



For example, we have an image 2x4 pixels with two colors. if the pixel part is the next 5 hexa bytes : 0x80 0x00 0x01 0x00 0x81 0x00, the output will be :

0	0	0	0
1	0	1	1

Source : [opt_fr_'s CD-i website](http://optfr.free-h.net/cdi/index.php?mod=formats)

About the pallette :
[http://i326.photobucket.com/albums/k425 ... EN-PAL.png](http://i326.photobucket.com/albums/k425/LuigiBlood/IMMEEN-PAL.png)

Pallette Data seems to be after PAL data and always beginning with FF FF FF 00.
Format :
RR GG BB 00 and it continues like that : RR GG BB 00 RR GG BB 00...

Now you can have ANI files working.
(By the way, i'm KiiroBomber)

EDIT :
Here's something to use with QuickBMS :

```
FindLoc PALoffset String "PAL data" 0
Math PALoffset += 16
log "Meen.pal" PALoffset Size
```
## Post #13
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-01-30T03:07:32+00:00
- Post Title: I.M.Meen (1995 PC/DOS) ANI format

Thanks a lot for clarifying, man!

Edit: And the QuickBMS script!
## Post #14
- Username: LuigiBlood
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jan 29, 2010 5:26 am
- Post datetime: 2010-01-30T16:08:35+00:00
- Post Title: I.M.Meen (1995 PC/DOS) ANI format

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-01-31T05:58:24+00:00
- Post Title: I.M.Meen (1995 PC/DOS) ANI format

Having some problems with the QuickBMS scripts. Is it because it is QuickBMS 0.2?

Fixed! Yup, just needed to update.

That one doesn't seem to extract palette data.
## Post #16
- Username: LuigiBlood
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jan 29, 2010 5:26 am
- Post datetime: 2010-01-31T11:11:33+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) ANI format

BMS Script RLE7 extractor only does extract frames.

However, about the pallette data extractor, there's two versions :
Pallette Extractor :

```
FindLoc PALoffset String "PAL data" 0
Math PALoffset += 16
log "Meen.pal" PALoffset Size
```


Pallette Extractor that does make a compatible pallette for CDiTool/MeenTool :

```
Math Size -= 6
Set Size2 0
FindLoc PALoffset String "PAL data" 0
Math PALoffset += 16
log "Meen-CDi.pal" PALoffset 3
Math Size += 3
append
Do
   Math PALoffset += 4
   log "Meen-CDi.pal" PALoffset 3
   Math Size2 += 3
While Size2 < Size
```


EDIT :

Optimized RLE7 Extractor :

```
Set FrameOffset 0 # Offset Used for detecting zeroes.
Set FrameOffset2 0 #Offset2
Set FrameNum 0
Set FrameSep 6
Get Size ASIZE 0
Set NAME String "MeenFrame"
Set Zeros 0 #Used for Zeros
Set Bytes 0
Set LONGBs LONG 0
# Set EndRLEBytes LONG 0x9d080000
Set EndRLEBytes LONG 0x0000089d

FindLoc FrameOffset String "PAL data" 0
Math FrameOffset += 536
Set FrameOffset2 FrameOffset
Math EndRLEBytes = 0
Do
	GoTo FrameOffset 0 #Go To Offset
	Get Bytes Byte 0 #Get Byte Data
	Get LONGBs LONG 0 #Get Long Data
	If LONGBs = 0x0000089d then
		Set NAME2 = NAME
		Math FrameNum += 1
		String NAME2 += FrameNum
		String NAME2 += ".rle7"
		Math FrameSize += 5
		log NAME2 FrameOffset2 FrameSize
		Math FrameOffset += 2207
		Math FrameOffset += 6
		Math FrameOffset += 5
		Set FrameOffset2 FrameOffset
		Set FrameSize 0
		Set Bytes 0
		Set LONGBs 0
	Else
		Math FrameOffset += 1
		Math FrameSize += 1
	EndIf
While FrameOffset < Size
```


RAW Audio Extractor :

```
Set FrameOffset 0 # Offset Used for detecting zeroes.
Set FrameOffset2 0 #Offset2
Set FrameNum 0
Set FrameSep 6
Set AudioSize 2205
Get Size ASIZE 0
Set NAME String "MeenFrame"
Set Zeros 0 #Used for Zeros
Set Bytes 0
Set LONGBs LONG 0
# Set EndRLEBytes LONG 0x9d080000
Set EndRLEBytes LONG 0x0000089d

FindLoc FrameOffset String "PAL data" 0
Math FrameOffset += 536
Set FrameOffset2 FrameOffset
append
Do
	GoTo FrameOffset 0 #Go To Offset
	Get Bytes Byte 0 #Get Byte Data
	Get LONGBs LONG 0 #Get Long Data
	If LONGBs = 0x0000089d then
		Math FrameOffset += 5
		Set FrameOffset2 FrameOffset
		log "MeenAudio.raw" FrameOffset2 AudioSize
		Math FrameOffset += 2205
		Math FrameOffset += 6
		Set FrameOffset2 FrameOffset
		Set FrameSize 0
		Set Bytes 0
		Set LONGBs 0
	Else
		Math FrameOffset += 1
		Math FrameSize += 1
	EndIf
While FrameOffset < Size
```


I.M. Meen RAW Audio to WAV (Based on RAW2WAV BMS script) :

```
set CHANNELS long 1
set BITS long 8

get SIZE asize
get NAME filename
string NAME += ".wav"

set MEMORY_FILE binary "\x52\x49\x46\x46\x00\x00\x00\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x64\x61\x74\x61\x00\x00\x00\x00"

set RIFFSIZE long SIZE
math RIFFSIZE += 36
set BLOCKALIGN long BITS
set AVGBYTES long FREQUENCY
math BLOCKALIGN /= 8
math BLOCKALIGN *= CHANNELS
math AVGBYTES *= BLOCKALIGN

putvarchr MEMORY_FILE 4 RIFFSIZE long
putvarchr MEMORY_FILE 20 1 short          # wFormatTag: Microsoft PCM Format (0x0001)
putvarchr MEMORY_FILE 22 CHANNELS short   # wChannels
putvarchr MEMORY_FILE 24 FREQUENCY long   # dwSamplesPerSec
putvarchr MEMORY_FILE 28 AVGBYTES long    # dwAvgBytesPerSec
putvarchr MEMORY_FILE 32 BLOCKALIGN short # wBlockAlign
putvarchr MEMORY_FILE 34 BITS short       # wBitsPerSample
putvarchr MEMORY_FILE 40 SIZE long

append
log NAME 0 44 MEMORY_FILE
log NAME 0 SIZE
```
## Post #17
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-01-31T21:40:03+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) ANI format

Well, the one that extracts a palette compatible with CDitool/Meentool seems to output 3byte files rather than extracting a palette.

Also, the audio one works great! Does the RAW extractor take out chunks of audio from an ANI file?
## Post #18
- Username: LuigiBlood
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jan 29, 2010 5:26 am
- Post datetime: 2010-02-01T06:13:01+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) ANI format

Actually, about extracting pallette compatible with CD-iTool/MeenTool's BMS, Append mode has been used, it doesn't output some files, but it adds to the file.

The RAW Audio Extractor BMS extracts audio from ANI files.
## Post #19
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-02-01T23:01:22+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) ANI format

Hey thanks, now I got it!
