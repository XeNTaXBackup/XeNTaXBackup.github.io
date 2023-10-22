## Post #1
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2009-10-31T23:54:56+00:00
- Post Title: [REQ] PC Eradicator (c) 1996 Accolade

I'm looking for a ripper for the DOS FPS game [Eradicator](http://www.mobygames.com/game/eradicator). 

You can download the game [here](http://eradicatordemo.bravehost.com/), I expect the [MAIN.RID file](http://www.sendspace.com/file/hyhvl2) to contain the desired resources.

Basically the (now abandoned) tool [XWE, source available](http://www.doomworld.com/xwe/index.shtml) states it has  [Eradicator support](http://www.doomworld.com/xwe/xwe-erad.shtml), but it doesn't seem to work. Still, the source code might contain a clue.

I've tried several other general rippers, none of which seem to get the job done.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-01T01:36:27+00:00
- Post Title: [REQ] PC Eradicator (c) 1996 Accolade

*edit* use the script provided by GameZelda
## Post #3
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2009-11-01T12:47:01+00:00
- Post Title: [REQ] PC Eradicator (c) 1996 Accolade

Wow, I never imagined getting a response to this, let alone so quickly!   Thank you so much! 

While I now managed to decompose the MAIN.RID file, the resulting files don't make much sense; they lack a file extension and the headers aren't too helpful either as they differ for each file.

I think I'll have to see how much I can do with the ripped files, but at least I'm one step closer to my goal!
## Post #4
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-01T13:17:28+00:00
- Post Title: [REQ] PC Eradicator (c) 1996 Accolade

aluigi:  Your script is broken   It doesn't extract the files in the root dir and it doesn't handle subdirectories.

Fixed (& modified syntax...):

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms
# modified by GameZelda

Set @outputPath string ""
CallFunction !unpackRidb

StartFunction !unpackRidb
	SavePos @ridbOff

	# Header
	IDString "RIDB"
	Get @numEntries long
	Get @entriesOff long
	Math @entriesOff += @ridbOff

	# Entry table
	GoTo @entriesOff

	For @i = 0 < @numEntries
		# Entry
		GetDString @entryName 12

		Set @entryOutputPath string @outputPath
		If @entryOutputPath != ""
			String @entryOutputPath += /
		EndIf
		String @entryOutputPath += @entryName

		Get @entryOff long
		Math @entryOff += @ridbOff
		Get @entrySize long

		# Entry contents
		SavePos @entriesOff
		GoTo @entryOff

		GetDString @magic 4

		If @magic == "RIDB"                                   # RIDB magic = folder
			Set @outputPathBak string @outputPath
			Set @outputPath string @entryOutputPath
			GoTo @entryOff
			CallFunction !unpackRidb
			Set @outputPath string @outputPathBak
		Else                                                 # no RIDB magic = file
			log @entryOutputPath @entryOff @entrySize
		EndIf

		GoTo @entriesOff
	Next @i
EndFunction

```


EDIT: About the files...

The files seem to have this format:

```
{
	uint32_t width;
	uint32_t height;
	uint8_t image[width * height]; // 8 BPP
}

struct TEXTURES_SKIES
{
	uint32_t width;
	uint32_t height;
	uint32_t unk; // Always 0?
	uint8_t image[width * height]; // 8 BPP
}

(most likely using some of the included palettes)

struct SOUNDS
{
	uint8_t sound[fileSize]; // 8 BPS
}

struct PALETTE_PALETTE
{
	uint24_t color[0x100]; // 8R8G8B
}

```


Haven't tried any of this but seems very simple...

EDIT: Found a small optimization for the script...
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-01T14:03:56+00:00
- Post Title: [REQ] PC Eradicator (c) 1996 Accolade

excellent job GameZelda
perfect script :)
## Post #6
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2009-11-01T16:14:54+00:00
- Post Title: [REQ] PC Eradicator (c) 1996 Accolade

Ah, I was wondering whether there would be more in the main file, or if I had its purpose wrong. Thanks for the quick fix GameZelda! 

So, this means they used their own (non-standard) file format with the graphic/sound resources? No wonder generic rippers can't produce meaningful files. 

I was somewhat expecting some BMP/GIF files to appear, along with some VOC/WAV files. Basically the only programming I'm relatively skilled at is PHP, and I haven't got a clue how to define the Structs you mentioned, nor how to 'read' those files into them. And the addition of having custom palettes only makes matters worse, right?

I guess I'll try some fopen/fread code to see if I can make sense of it. First time I've been looking into binaries though, it'll be a challenge.
## Post #7
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-04T22:40:40+00:00
- Post Title: [REQ] PC Eradicator (c) 1996 Accolade

The sounds can be loaded with Audacity in RAW data mode, with a frequency of 11025Hz (It worked for the files that I have tested), and "Unsigned 8-bit PCM" format.

The images & textures are also effectively 8-bit palettized images.

Does someone know / have any idea about what are the other files in the PALETTE folder (DEPTH, NIGHTVISION, RED, TRANSLUC)?
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-11-05T06:20:44+00:00
- Post Title: [REQ] PC Eradicator (c) 1996 Accolade

It is an interesting coincidence that somebody requested this, as I just today got my hands on it as part of my retro collection. I was going to look into it myself but it seems you got most of it already. I suppose all that is needed is a simple tool for the images. Or perhaps GGD can handle it?

EDIT: TiledGGD works for palette and graphics. Still can't beat a batch program that reads from an assigned palette and spits them out in BMP/TGA. But this works for me since I'm fine with the slow but surely way.

EDIT2: Example below. Works fine but is a slow process. I believe the palette is correct.
[Example1.png](https://xentaxbackup.github.io/file/2500_Example1.png)
## Post #9
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2009-11-05T21:42:32+00:00
- Post Title: [REQ] PC Eradicator (c) 1996 Accolade

Woohoo! More progress then! 

Thanks SO much for the info GameZelda and Darkfox, I'll be checking it out! 

*edit*
Sounds ripped already, now for the graphics. I can't seem to be able to reproduce the results with TiledGGD, not even when using the settings 1:1 to those in the screengrab... 

As for the palettes, it could be that different palettes were used for different levels. XWE (allegedly supporting the Eradicator palette) offered [this](http://urahost.com/download.php?file=95338) palette.
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-11-05T23:13:11+00:00
- Post Title: [REQ] PC Eradicator (c) 1996 Accolade

Was that palette correct? The monster seemed correctly shown, it was zoomed in though. And I adjusted height/width. And I think I used the core RED palette in 3-byte format.
## Post #11
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2009-11-06T09:32:19+00:00
- Post Title: [REQ] PC Eradicator (c) 1996 Accolade

> Reply from Darkfox
>
> Was that palette correct? The monster seemed correctly shown, it was zoomed in though. And I adjusted height/width. And I think I used the core RED palette in 3-byte format.I can see the settings in that screenshot. 

And actually I don't recall the graphics being THAT good in the game, I assumed it would've been a still from a prerendered/movie file or something. I don't even remember that monster from the gameplay this way hehe...   

If these indeed are the sprites, the quality is much better than I remember from the game. The palette seems to match the atmosphere from the game, rather dark and blue like the screenshot you posted. I'll try to see if I can grab some screenshots from the monster in-game.

Slightly offtopic: you buy retro games to see if you can make sense of their resource-files? Or are you a (retro) games collector? 

*edit*
Palette is correct, here's an ingame shot: 
Perhaps the engine is kinda sucky as I find your rendering much more detailed! 

Perhaps your sprite should be flipped though, like a negative width.
## Post #12
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-11-07T07:38:54+00:00
- Post Title: [REQ] PC Eradicator (c) 1996 Accolade

Great! Palette correct! This makes the job much easier. And yes, it is the ingame rendering that does it.

The sprite I shown was 2x it's normal size. But yes, it is very detailed. In many games like this you do not often see the full detail because of the in-game scaling.
## Post #13
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2009-11-07T21:59:31+00:00
- Post Title: [REQ] PC Eradicator (c) 1996 Accolade

Well Darkfox, I've been toying with TiledGGD some more and I still can't reproduce the results you presented.

However, in my case it seems like the MENUPAL does the trick, whereas the RED palette doesn't:
RED palette:

MENUPAL palette:


Note that my MENUPAL palette as presented in TiledGGD does NOT match your screenshot, even though I used the same settings. I'm using TiledGGD 2.1.0, although the About-box states it's 2.0.3.0.

Anyway, I also specified my own offset so that the monster fits in the frame (the top of his head was on the bottom in the previous setting). I'm not sure however if the vertical offset is right, as the weapon comes awfully close to the edge of the frame.
