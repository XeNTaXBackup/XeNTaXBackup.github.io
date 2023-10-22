## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-07T23:17:35+00:00
- Post Title: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

The IMG files are the containers for the textures.



Which I have been able to extract and apply to a map remake in progress for Doom of Level 1 of this very game. The palette had to be gained by doing a DOSBox memory dump. It is provided in this thread:

[viewtopic.php?f=18&t=3470&start=45](http://forum.xentax.com/viewtopic.php?f=18&t=3470&start=45)

"MeenMapPalette.rar"



The sprites and animated doors as you can see are broken up and data regarding them is stored above them. The palette displays the correct colors for each but the sprites themselves are incorrect.

Here are a number of tiles that do not display correctly. (Some have flames like the flame behind the furnace, the enemies, and the fires)

Here is a wall with a peep hole:


Here's an animated flaming pot:


A transpared stove texture with an animated flame behind it:


An animated door that goes up having spikes at the bottom:


Pedestal thingy:


Animated troll enemy:


Skull gargoyle statue thingy:


An animated fire wand pickup:

[IMAGES.rar](https://xentaxbackup.github.io/file/2600_IMAGES.rar)
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-09T01:08:13+00:00
- Post Title: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Coming to a conclusion:

Compression

The black portions (00) of each sprite and transparent texture are missing absolutely. And in the palette, 00 IS the black portion. Thus the headers of each sprite contains the compressed data.
[CompressedGraphics.png](https://xentaxbackup.github.io/file/2606_CompressedGraphics.png)
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-10T23:35:44+00:00
- Post Title: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Well, I've been relatively fruitless in my attempts to replenish the black (transparent) portions of each graphic. I still don't know why they did this. Anyone able to figure this one out? I can't quite understand how the engine replaces all the transparent sections.
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-20T23:02:04+00:00
- Post Title: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Anyone have an idea on what kind of encryption this is or a means to decode it? This is all I really need to start up on my zMeen project.
## Post #5
- Username: optfr
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 30, 2009 7:44 pm
- Post datetime: 2009-12-21T11:16:46+00:00
- Post Title: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Hi !

Are you sure the pictures are compressed ? It seems that there is a gap or bad additional pixels like in this [http://i326.photobucket.com/albums/k425 ... roblem.png](http://i326.photobucket.com/albums/k425/LuigiBlood/Problem.png) (pic taken from antoher game)

PS : do you knowhow to extract images.img in the lab files ?
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-21T19:42:47+00:00
- Post Title: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

[LINK](http://forum.xentax.com/viewtopic.php?f=10&t=3469&p=29256)

Here is a link to a BMS script that will extract all content of a LAB file.

Also, I'm not seeing the transparent sections (00 00 00 in RGB) of each sprite/transparent texture.
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-26T08:17:55+00:00
- Post Title: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

optfr sent me a PM and says that he has dropped out. So anybody who can figure out how it puts in the transparent segments please help.
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-01-19T21:29:48+00:00
- Post Title: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Still haven't been successful in extracting the sprites/transparent walls properly.
## Post #9
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-01-27T07:25:29+00:00
- Post Title: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Sorry to bump once again but I've come to a realization. The sprites and transparent textures are not compressed per say, but encoded in a way that the engine upon scanning the lump of data before the graphical portion tells it where to fill in the gaps and construct it. It seemed odd to me at first because it seemed like a form of file compression that takes out the 00 00 00 portions storing it in a table of some sort. Not the case, or at least, in that it is not really a compression otherwise everything would be that way.

Now the question is, how to decode the sprites?
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-02-03T20:24:07+00:00
- Post Title: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Still no luck in decoding the sprites. Could it be some RLE7 like the ANI files?



[http://optfr.free-h.net/cdi/index.php?mod=formats](http://optfr.free-h.net/cdi/index.php?mod=formats)
## Post #11
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-05-28T19:32:35+00:00
- Post Title: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Bumping this to give some speculation:

The sprites are likely coded in this way:

The odd data at the beginning points out the position of the transparent portions and how many bytes/pixels it does so, then as the game reads it, it uses these to fill it in ingame. Basically that chunk of data tells where the transparency goes as a form of compression. Though they could have just used the Doom method and had a transparent color which would have been more effective and less pointless. Then again, this is the makers of Link and the Faces of Evil. XD

Basically I believe the stuff is pointers telling where and how much to fill in each portion.
## Post #12
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-31T01:14:59+00:00
- Post Title: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Can you post a screen grab of what the image at 0x1C000 is suppose to look like? It seems to have a small amount of compression data needed for it and might be easier to figure out something about what is going on.  The viewable pixels so far look like a pillar with a gargoyle in the center--I'm guessing this will end up having transparent sides and actually be 64x64 like all the rest of the images.
## Post #13
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-10-28T00:46:33+00:00
- Post Title: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

I will try to get what you requested soon, sorry for little updates, things came up and stuff.

I DO have some extra info though to share:

The game's sequel Chill Manor uses the same setup and the same compression on transparent portions. So I'm adding it to the title to indicate that the format is shared.

Edit:

Is it the attached, or this?


[Torch.png](https://xentaxbackup.github.io/file/3558_Torch.png)
## Post #14
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-10-30T19:52:53+00:00
- Post Title: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Oh sorry, I think I've found the right one now. This it?
## Post #15
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-11-03T00:29:09+00:00
- Post Title: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Good news! Thanks to MortoQueiba [http://www.youtube.com/user/MortoQueiba](http://www.youtube.com/user/MortoQueiba) the way the game decompiles the compressed sprites has been cracked effectively. I will quote him here, and it has been tested and verified extracting and decompressing all sprites for I.M.Meen's first level.

Here's his documentation, credit him for finding this out.

> The format of each image is as follows: Header, Pixel data, Footer.
>
> 
>
> =====[Header]=====
>
> The first four bytes are the "true" ends of each sprite. Every sprite (I've tested) is 64x64 pixels big, but these bytes determine the true dimensions, using vertical and horizontal lines. The values in these are as follows:
>
> 
>
> Left, ???, Right, ??? (more experimentation needed, probably Up and Down).
>
> 
>
> These values are the exact lines that the first pixels of the sprite appears on. Left and Right share scales, and so do Up and Down (probably). That means that to make a 32x32 image on the 64x64 canvas, Left would be 11 (hex), and Right would be 30 (hex). This puts 16 (10 hex) transparent pixels to the left, and 16 (10 hex) transparent pixels to the right of the "true" sprite.
>
> 
>
> Then after those four bytes, the rest of the Header is composed of several pairs of bytes. These are actually offsets pointing to the footer for further direction in spacing out the pixels in the image. Take these and reverse them, then add "1C000" to them to get these addresses. THESE ARE RELATIVE TO THE IMAGES.IMG FILE, not the RES### file. 
>
> 
>
> 
>
> 
>
> =====[Pixel Data]=====
>
> Just the pixel data. Nothing special here.
>
> 
>
> 
>
> 
>
> =====[Footer]=====
>
> The footer is composed of the pixel lines. By which, I mean it tells the game where to put each pixel. Each section is formatted as such.
>
> 
>
> "AA 00 BB 00 CC 00 XX 00"
>
> 
>
> AA - The end of the pixel set on that vertical line. The exact spot the transparency starts again.
>
> BB - The start of the pixel line. The exact spot of the first pixel in line.
>
> CC - The offset of the pixels themselves. Read from Pixel Data. Add "1C000" to this byte.
>
> XX - trigger/command. If it is 00, then there are no more pixels on that vertical line, move onto the next one. If it is not 	00, treat it as the next command's AA and continue on the same line.
## Post #16
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-11-03T10:34:03+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

This looks a lot like Heroes of Might and Magic 1 sprites and is probably a common technique, one that I also came up with during my DOS days  The "footer" data look a lot like a "mask" datafield. A spritemask. So where to *not* render pixels.
## Post #17
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-12-09T21:06:03+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

> Reply from Darkfox
>
> Good news! Thanks to MortoQueiba http://www.youtube.com/user/MortoQueiba the way the game decompiles the compressed sprites has been cracked effectively. I will quote him here, and it has been tested and verified extracting and decompressing all sprites for I.M.Meen's first level.

Here's his documentation, credit him for finding this out.
The format of each image is as follows: Header, Pixel data, Footer.

=====[Header]=====
The first four bytes are the "true" ends of each sprite. Every sprite (I've tested) is 64x64 pixels big, but these bytes determine the true dimensions, using vertical and horizontal lines. The values in these are as follows:

Left, ???, Right, ??? (more experimentation needed, probably Up and Down).

These values are the exact lines that the first pixels of the sprite appears on. Left and Right share scales, and so do Up and Down (probably). That means that to make a 32x32 image on the 64x64 canvas, Left would be 11 (hex), and Right would be 30 (hex). This puts 16 (10 hex) transparent pixels to the left, and 16 (10 hex) transparent pixels to the right of the "true" sprite.

Then after those four bytes, the rest of the Header is composed of several pairs of bytes. These are actually offsets pointing to the footer for further direction in spacing out the pixels in the image. Take these and reverse them, then add "1C000" to them to get these addresses. THESE ARE RELATIVE TO THE IMAGES.IMG FILE, not the RES### file. 



=====[Pixel Data]=====
Just the pixel data. Nothing special here.



=====[Footer]=====
The footer is composed of the pixel lines. By which, I mean it tells the game where to put each pixel. Each section is formatted as such.

"AA 00 BB 00 CC 00 XX 00"

AA - The end of the pixel set on that vertical line. The exact spot the transparency starts again.
BB - The start of the pixel line. The exact spot of the first pixel in line.
CC - The offset of the pixels themselves. Read from Pixel Data. Add "1C000" to this byte.
XX - trigger/command. If it is 00, then there are no more pixels on that vertical line, move onto the next one. If it is not 	00, treat it as the next command's AA and continue on the same line.

So with this is there any possibility we can get a script to do the work for us rather than having to open up a hex editor each time and doing it manually?
## Post #18
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-12-30T21:47:35+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Yeah, the program I have he made with Game Maker to do it that way. It is buggy but it works, I would love if somebody used that knowledge to make a program that does this automatically. Added CMPs seem to use this as well.

I could provide it and maybe somebody can use information in it to make a command-line tool that uses a palette and IMG, and splits up the IMG into colored 64x64 images in a manageable format.
## Post #19
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-01T00:47:38+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

*removed most of this post, but i said:*

i cant see where the footers are in the files
how i understand the IMG format from the sample:

```
ushort Headers[HeaderCount]  --> in FLOOR/SKY Headers[0] is the exact number of imagedatapointers. with IMAGES.IMG this is NOT the case
uint ImageDataPointers[ see notes above ]

The just seek to each pointer and deal with each image (4096 bytes, unless pixel alignment, which i dont think i have an example of)

```


i also uploaded a quickbms script which contains the palette and can dump square (no padding) images as BMPs. now attached
[IMG quickbms.zip](https://xentaxbackup.github.io/file/3763_IMG quickbms.zip)
## Post #20
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-01-02T10:44:32+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

The contents of this post was deleted because of possible forum rules violation.
## Post #21
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-02T17:35:46+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

*edit*


[sprite_1C000.PNG](https://xentaxbackup.github.io/file/3764_sprite_1C000.PNG)
## Post #22
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-03T04:27:40+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

(another post so i could attach another file)

some graphics do have odd glitches. i have no discovered why they occur yet.

[img_dumps.zip](https://xentaxbackup.github.io/file/3766_img_dumps.zip)
## Post #23
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-01-03T09:41:47+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Ah, very good! Yeah, that is the glitch we get with some sprites. In sprites it tends to add bars of stuff as well as clone some things.
## Post #24
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-04T14:54:58+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

at the sprite data, the header pointers are sometimes only 2 bytes apart. this means that the footer section is actually read like:

```
{
  ushort AA;
  if(AA == 0) break;
  ushort BB;
  ushort CC;

  // where AA is the right and BB is the left (so when AA == 0 there isn't any left (BB) data to read)
  // and CC is the offset to the palette index (from start of the sprite data)
}

```


which should fix reading your sprites.

i haven't yet written that up into bms because i dont completely understand the IMG header - my best guess is this:

```

if(HeaderFlag == 1)
{
  ushort FileCount
}
else
{
  ushort FileCount1
  ushort FileCount2
  ushort PaddedFileCount

  // where FileCount1+FileCount2+PaddedFileCount == number of headers
  // FileCount1+FileCount2 == number of unpadded files
  // and PaddedFileCount is the number of files which are padded

  FSeek(2 + (HeaderFlag * 2));
}

```


do you have any more info on that?
[117616.PNG](https://xentaxbackup.github.io/file/3772_117616.PNG)
## Post #25
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-01-07T08:14:23+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Really good find there... as to information on that... er, sorry, I never figured that out, all I know is what you two have found. Regarding the IMAGES.IMG, somehow something tells the game how to number the sprites for the actors script but I dunno there either, never figured it out.
## Post #26
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-14T19:53:56+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

After a gentle reminder, I've now finished that IMG -> BMP converter  
[IMG2BMP.zip](https://xentaxbackup.github.io/file/3800_IMG2BMP.zip)
## Post #27
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-01-15T01:28:32+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Wow, I just tested this on level 1's IMAGES.IMG and it captured everything, even the multiple blank tiles, this is beyond dandy, it makes this a whole lot more accurate and easy! Thanks a lot for this.   Now I can fix a few errors in the sprites I currently have of levels 1-5 (there are 36 so this will make it a whole lot better than the current method) thanks a lot again. So far I get no errors to speak of.
## Post #28
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-05-14T09:29:03+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

The contents of this post was deleted because of possible forum rules violation.
[ChillPal.rar](https://xentaxbackup.github.io/file/4238_ChillPal.rar)
## Post #29
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-05-14T20:44:11+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

There is extra data in the newer IMG format, which are height and width due to now variable ones used in Chill Manor. I have programmed in the new palette but not sure how to compensate for the change in format.

I'm attaching the slightly modified source code (palette change) along with the 2 other IMG files, FLOOR and SKY, these are 64x64. Extra data seems to say dimensions as opposed to just beginning and end.

Edit: Also, I used Lazarus for editing, thats why it is a little different looking than WRS's.

Edit 2: Oh wow... turns out the palette for I.M.Meen was stored in GAME_SCR.PCX of RESINT.LAB. Weird method I must say. I know I've already extracted both formats but found that interesting to say the least.
[IMG2BMP.rar](https://xentaxbackup.github.io/file/4239_IMG2BMP.rar)
## Post #30
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-06-13T08:00:45+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Bumping this to update, it seems that the extra bytes deal with the variable width (which translates to height once flipped properly) and perhaps the mipmaps for the larger wall textures as little else seems changed besides that. So version 2 Animation Magic IMGs aren't a vast difference. It seems they were picking up some newer gimmicks of the time though.
## Post #31
- Username: YoshiOG1
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 16, 2011 2:30 am
- Post datetime: 2011-10-15T19:08:39+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Hey, guys!
I'm new here, and I was wondering of someone could figure out how to extract the sprite of I.M. Meen himself from Level 36.  I'd greatly appreciate if you guys could get the first frame of the sprite (the one where he's standing still).

Thanks in advance.  

**EDIT: Thanks to Darkfox (and two image editing websites), I was able to create an animated avatar of I.M. Meen.  I'm attaching the image to this message, so feel free to use it as your avatar!  
[animated sprite.gif](https://xentaxbackup.github.io/file/4791_animated sprite.gif)
## Post #32
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-10-18T14:21:02+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

The contents of this post was deleted because of possible forum rules violation.
## Post #33
- Username: YoshiOG1
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 16, 2011 2:30 am
- Post datetime: 2011-10-19T19:32:59+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

The contents of this post was deleted because of possible forum rules violation.
## Post #34
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-10-20T04:36:40+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Yeah, there's a tool on here called IMG2BMP and there is a BMS script for extracting files from the LAByrinth files.
## Post #35
- Username: YoshiOG1
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 16, 2011 2:30 am
- Post datetime: 2011-10-26T19:30:54+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

> Reply from Darkfox
>
> Yeah, there's a tool on here called IMG2BMP and there is a BMS script for extracting files from the LAByrinth files.

Ah, yes.  That makes sense now.  Because at the time I asked for the Ignatius sprites, I didn't really know/think about that script.
Now, I used the IMG2BMP script on the Level 32 LAB file so that I could get Frankenmeen's sprites, as seen in [this YouTube Poop of mine](http://www.youtube.com/watch?v=NI08e9uXzv8).

I will upload a ZIP folder with all of Frankenmeen's sprites later.  In the meantime, enjoy [this YouTube video of mine](http://www.youtube.com/watch?v=NI08e9uXzv8)!
## Post #36
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2012-09-04T05:04:17+00:00
- Post Title: Re: I.M.Meen/Chill Manor (1995 PC/DOS) Sprites [Compressed]

Sorry to bump but there's new data.

[http://www.shikadi.net/moddingwiki/IMG_Format_(Meen)](http://www.shikadi.net/moddingwiki/IMG_Format_%28Meen%29)

Here's some documentation explaining why IMG2BMP can't handle Chill Manor IMG files. Not just multiple sizes but another index. Wonder how one would calculate WxH?

pseudocode:

```
Width = totalImagebytes/Height;

```


That only gets height (width in pre-processed raw form as raw images are on their side) though...

Update: Figured it out. The formula is "totalImageBytes=height*width" as long as one of these is known, the other can be found. But I found my formula in pseudocode doesn't account for all the mipmaps.
