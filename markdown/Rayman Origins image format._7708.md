## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-11-19T00:43:55+00:00
- Post Title: Rayman Origins image format.

[viewtopic.php?f=21&t=7690](http://forum.xentax.com/viewtopic.php?f=21&t=7690)

Check the topic above for examples. Droolie started this expedition, and I fully support it. The sooner we have these unraveled the better. Anyway, they appear to be DDS files that are compressed. How do we decompress them? Any help is appreciated.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-11-19T02:44:51+00:00
- Post Title: Rayman Origins image format.

looks like standard xbox 360 swizzled dds.
## Post #3
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-11-19T03:58:08+00:00
- Post Title: Rayman Origins image format.

Any way to fix them to be viewed properly?

EDIT: Been messing around with them by 'importing raw' via photoshop. I can make out some things with another file...
Width: ? (Trial and Error thus far)
Height: ? (Trial and Error...)
Channel Count: 4
16 Bits, IBM PC.
Header: ? (No idea)
## Post #4
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-11-21T17:41:09+00:00
- Post Title: Rayman Origins image format.

I could use Unbundler from the Xbox 360 SDK to unswizzle them, but since it's failing we need to do something else first. Don't know what though... anyone help? 
EDIT -> I added the same textures but from the PS3 version here: [http://www.box.com/s/ryuuz3dzybuf0y5numn8](http://www.box.com/s/ryuuz3dzybuf0y5numn8)
They are probably higher quality so maybe we should switch to looking at those
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-11-21T23:47:44+00:00
- Post Title: Rayman Origins image format.

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-11-22T11:17:17+00:00
- Post Title: Rayman Origins image format.

That's great, thanks! I'm inexperienced with this though, so I'd like to know how exactly you changed the header - that way, I could maybe write a script to convert the files to readable dds. I already tried for an hour to adapt your header to other files, but I failed. It'd be great if you could help. Thanks again!
## Post #7
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-11-22T15:34:03+00:00
- Post Title: Rayman Origins image format.

Yeah, I, like the idiot I am, thought it would be as simple as copying and pasting that header in a hex editor and getting the same results with other files. Obviously that didn't work. Good luck on a script, Droolie!
## Post #8
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-11-23T21:55:48+00:00
- Post Title: Rayman Origins image format.

I recommend converting the PS3 textures this is because the xbox 360 format is 'swizzled' like Resident Evil 5. You'll need a good 'unswizzler' algorithm to fix the textures, you may aswell use PS3 ones since it's easier, and making up a new tool to 'unswizzle' would be a waste of time.

Edit: Anyone wanna help me out with PS3 dl links?
## Post #9
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-11-23T22:08:09+00:00
- Post Title: Rayman Origins image format.

Looks cool!
Again, I would like to know how you did that instead of just seeing results. :/
I can't help you with the download links but I could help by uploading all of the textures somewhere, if that's what you want.
## Post #10
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-11-23T22:17:12+00:00
- Post Title: Rayman Origins image format.

> Reply from Droolie
>
> Looks cool!
Again, I would like to know how you did that instead of just seeing results. :/
I can't help you with the download links but I could help by uploading all of the textures somewhere, if that's what you want.

I am an absolute beginner myself. I am downloading it now, I hope Chrrox can create a quick BMS script or I'll have a go once it's completely downloaded. Thanks again Chrrox for creating a sample, it really helped.

It just required modification of the DDS header, you need to know wether it is DXT1,2,3,4,5 and width, height bytes etc, I have only tested on these 2 so I don't know everything off the top of my head.
## Post #11
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-11-23T22:32:42+00:00
- Post Title: Rayman Origins image format.

I'd appreciate having the PS3 textures myself if possible. I only have the Wii version myself, and I'm not too keen on illegally downloading things I so wholeheartedly support, (I also would have no idea where to look). If you could give a link to just the textures, I'd be happy, as that's all I really need.
## Post #12
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-11-23T22:36:05+00:00
- Post Title: Rayman Origins image format.

> Reply from Doctor Loboto
>
> I'd appreciate having the PS3 textures myself if possible. I only have the Wii version myself, and I'm not too keen on illegally downloading things I so wholeheartedly support, (I also would have no idea where to look). If you could give a link to just the textures, I'd be happy, as that's all I really need.
Yes, I am downloading the game just to have a browse at the textures, sound tracks etc. It's not asif I can play it! ;]

I don't know if the Wii uses the same DDS format, i doubt it does anyway.
## Post #13
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-11-23T22:41:47+00:00
- Post Title: Rayman Origins image format.

> Reply from C00L12345
>
> Doctor Loboto wrote:I'd appreciate having the PS3 textures myself if possible. I only have the Wii version myself, and I'm not too keen on illegally downloading things I so wholeheartedly support, (I also would have no idea where to look). If you could give a link to just the textures, I'd be happy, as that's all I really need.
Yes, I am downloading the game just to have a browse at the textures, sound tracks etc. It's not asif I can play it! ;]

I don't know if the Wii uses the same DDS format, i doubt it does anyway.
Don't bother with the soundtrack of the PS3 version - it's divided into over 1000 segments and it's lower quality than the Xbox 360 version's soundtrack - which I (after lots and lots of work joining all of the segments correctly) made available... elsewhere (hint: my signature).
Here are the unconverted textures from the PS3 version:
[http://www.multiupload.com/DCOHJAYYV0](http://www.multiupload.com/DCOHJAYYV0)
[http://www.multiupload.com/GINFPSSHWY](http://www.multiupload.com/GINFPSSHWY)
## Post #14
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-11-23T22:48:12+00:00
- Post Title: Rayman Origins image format.

Is Xbox XMA audio format? I haven't found any sounds yet. I may aswell finish part 3/4 downloding pretty fast.
## Post #15
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-11-23T22:49:50+00:00
- Post Title: Rayman Origins image format.

> Reply from C00L12345
>
> Is Xbox XMA audio format? I haven't found any sounds yet. I may aswell finish part 3/4 downloding pretty fast.
Yep, it's XMA with custom headers. That's better than PS3's MSF (which is AT3) files.
## Post #16
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-11-24T13:11:13+00:00
- Post Title: Re: Rayman Origins image format.

Here's another sample. i'm not any good at quickbms scripts....



Ok im new to quickbms, I can insert the DDS header, but I can't make it overwrite the original header ;(
## Post #17
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-11-24T14:13:33+00:00
- Post Title: Re: Rayman Origins image format.

Great! If you'd give your script so far to me, I could adapt it so it overwrites the current one. 
EDIT -> You might also have gotten the height wrong for that texture (but I'm not sure at all about this), because the bottom image (which is the left and right side of the top image) should be just as long as the top one. It is in the Wii version...
## Post #18
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-11-24T16:53:15+00:00
- Post Title: Re: Rayman Origins image format.

> Reply from Droolie
>
> Great! If you'd give your script so far to me, I could adapt it so it overwrites the current one. 
EDIT -> You might also have gotten the height wrong for that texture (but I'm not sure at all about this), because the bottom image (which is the left and right side of the top image) should be just as long as the top one. It is in the Wii version...
Ok, I'm unable to fix the script and I've passed it on to Aluigi to see if he can correct the problem (he obviously can since he owns LoL)

I'll be able to post the script if it is fixed later on.



As you said before, the height and width values I used are correct. Some files are just like this, or I did something else wrong (unlikely since some do it some don't)
## Post #19
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-11-24T18:54:27+00:00
- Post Title: Re: Rayman Origins image format.

Okay, it seems that Aluigi is busy. Someone else can have a go at fixing the script P: 

Yeah it's a messy script, just rushed and it's my first one!

There is an issue where the DDS header is inserted before the original header, it doesn't overwrite the original header.
Open the image in hex editor and deleted the original header. If you don't the image will appear slightly out of place.

Script incomplete/buggy/inaccurate I'd appreciate it if someone would fix it 

```
# Only for Playstation 3, Xbox is not supported!
# UNFINISHED SCRIPT!

get NAME basename
goto 0x20
get UNK1 byte
get UNK2 byte
get UNK3 byte
get UNK4 byte
set MEMORY_FILE2 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr MEMORY_FILE2 0x11 UNK1 byte
putVarChr MEMORY_FILE2 0xA UNK1 byte
putVarChr MEMORY_FILE2 0xD UNK3 byte
putVarChr MEMORY_FILE2 0xC UNK4 byte
append
get SIZE asize MEMORY_FILE2         
log MEMORY_FILE 0 SIZE MEMORY_FILE2 
get SIZE asize                      
log MEMORY_FILE 0 SIZE             
append
get SIZE asize MEMORY_FILE
string NAME += ".dds"
log NAME 0 SIZE MEMORY_FILE
```
## Post #20
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-11-24T20:02:41+00:00
- Post Title: Re: Rayman Origins image format.

Fixed the issue you mentioned. I also rushed my fix but it works great now, thanks a lot for this!
How are you able to view the files' transparency though? I'm using the Photoshop DDS plugins from NVIDIA but they don't seem to show any transparency.

```
# Only for Playstation 3, Xbox is not supported!
# UNFINISHED SCRIPT!

get NAME basename
goto 0x20
get UNK1 byte
get UNK2 byte
get UNK3 byte
get UNK4 byte
set MEMORY_FILE2 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr MEMORY_FILE2 0x11 UNK1 byte
putVarChr MEMORY_FILE2 0xA UNK1 byte
putVarChr MEMORY_FILE2 0xD UNK3 byte
putVarChr MEMORY_FILE2 0xC UNK4 byte
append
get SIZE asize MEMORY_FILE2
log MEMORY_FILE 0 SIZE MEMORY_FILE2
get SIZE asize      
math SIZE -= 128               
log MEMORY_FILE 128 SIZE             
append
get SIZE asize MEMORY_FILE
string NAME += ".dds"
log NAME 0 SIZE MEMORY_FILE
```
## Post #21
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-11-24T20:04:59+00:00
- Post Title: Re: Rayman Origins image format.

Excellent. But I'm also running into the transparency issue. I use PAINT.NET though, so that may be a problem as well. The edges are extremely pixelated.
## Post #22
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-11-24T20:35:49+00:00
- Post Title: Re: Rayman Origins image format.

I am aware that there are some transparency issues with some textures. I've no idea why this is happening myself. Some are working perfect, some aren't. I'll take a look later since i'm abit busy right now.
## Post #23
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-11-24T22:13:57+00:00
- Post Title: Re: Rayman Origins image format.

Try changing from dxt 5 to dxt3 or vise versa
## Post #24
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-11-24T22:37:19+00:00
- Post Title: Re: Rayman Origins image format.

> Reply from chrrox
>
> Try changing from dxt 5 to dxt3 or vise versa
Alright, that works perfectly. Thanks a lot! 
So this is the most recent script:

```
# Only for Playstation 3, Xbox is not supported!
# UNFINISHED SCRIPT!

get NAME basename
goto 0x20
get UNK1 byte
get UNK2 byte
get UNK3 byte
get UNK4 byte
set MEMORY_FILE2 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x33\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr MEMORY_FILE2 0x11 UNK1 byte
putVarChr MEMORY_FILE2 0xA UNK1 byte
putVarChr MEMORY_FILE2 0xD UNK3 byte
putVarChr MEMORY_FILE2 0xC UNK4 byte
append
get SIZE asize MEMORY_FILE2
log MEMORY_FILE 0 SIZE MEMORY_FILE2
get SIZE asize      
math SIZE -= 128               
log MEMORY_FILE 128 SIZE             
append
get SIZE asize MEMORY_FILE
string NAME += ".dds"
log NAME 0 SIZE MEMORY_FILE
```
## Post #25
- Username: Athari
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Dec 16, 2011 1:32 pm
- Post datetime: 2011-12-17T09:45:39+00:00
- Post Title: Re: Rayman Origins image format.

Guys, thank you for writing scripts to extract and convert the textures and for sharing the textures of PS3! It really helped me with designing my own game to see how level backgrounds in Rayman Origins are structured (I mostly mean Warcraft II-like ground* textures). All the great things are simple. 

Information for people who try using the script above: it doesn't detect texture compression, it always assumes DXT3. If a texture isn't displayed correctly, try changing FOURCC code in its header from “DXT3” to either “DXT1” or “DXT5”. I've fixed manually all the textures I could fix and here is the result (I've probably missed some in the rush):

[RaymanOrigins_PS3_Textures_Unpacked.part1.rar](http://www.mediafire.com/file/a3y8mvqdu6o15pf/RaymanOrigins_PS3_Textures_Unpacked_.part1.rar)
[RaymanOrigins_PS3_Textures_Unpacked.part2.rar](http://www.mediafire.com/file/6giolgkypw769ff/RaymanOrigins_PS3_Textures_Unpacked_.part2.rar)

However, I'm still unable to view some of the textures. Some of them are 256-byte textures I couldn't care less about, some are light/ray maps or whatever, but some are likely real textures like “laser_heads_atlas01.png.dds” or “bosstail.tga.dds” or “jumping_mushrooms_*.png.dds”. Here is an example:

[laser_heads_atlas01.png.dds](http://www.mediafire.com/file/0806baodh1fadaj/laser_heads_atlas01.png.dds)

Any ideas?
## Post #26
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-12-19T01:59:26+00:00
- Post Title: Re: Rayman Origins image format.

You should have provided the unconverted textures......
## Post #27
- Username: Athari
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Dec 16, 2011 1:32 pm
- Post datetime: 2011-12-19T08:33:13+00:00
- Post Title: Re: Rayman Origins image format.

> Reply from C00L12345
>
> You should have provided the unconverted textures......
Original: [laser_heads_atlas01.png.ckd](http://www.mediafire.com/file/ka8cclasauso14i/laser_heads_atlas01.png.ckd)
