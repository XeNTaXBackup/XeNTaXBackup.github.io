## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-24T06:33:32+00:00
- Post Title: Albion graphics (PC/DOS)

A little PC RPG from the past. I've been tinkering with it a little, some tools support the archiving (Game Extractor and XLD Extractor) I found that some graphics are ILBM and were easily viewable and editable until I figured out that most other graphics are of a format that seems to be raw uncompressed though I can't find out much else than view it in Texturefinder.

Here are a couple extracted from the monster graphic archive. My issue however is that I fear there is no palettes which are stored in a separate archive. Still, could extract them but it might give trial and error unless I can figure out where it tells which palettes they use. :/
[SomeMonsters.rar](https://xentaxbackup.github.io/file/1281_SomeMonsters.rar)
## Post #2
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-24T08:41:37+00:00
- Post Title: Albion graphics (PC/DOS)

You feared correctly, there do not seem to be any palettes in these files, but only raw image data. The format:

uint16 {2} - Width
uint16 {2} - Height
uint16 {2} - Unknown
char {X} - Width * Height bytes of image data

This structure is repeated until the file ends, i.e. there are multiple graphics in each file.

I don't know what the "Unknown" value is supposed to be. It seems to be constant throughout each file (though I haven't checked each instance). If you're lucky, it is some sort of palette ID ...
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-24T09:19:59+00:00
- Post Title: Albion graphics (PC/DOS)

I had thoughts of that. As each resource is not named but instead numbered dependent on their position inside the XLD library. Give or take 2 files there are between 56 and 54 palettes.

Edit: Giving the height and width of each graphic is very good news as it'll save needing those. If the unknown one is indeed the palette ID then it will be a walk in the park it would seem if that is the case. I have attached the palette library and the extracted content of it or at least what seems to be as I've had no means to test it's accuracy other than with the pictures file and with xmidi music.
[PALETTE0.rar](https://xentaxbackup.github.io/file/1283_PALETTE0.rar)
## Post #4
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-24T09:32:01+00:00
- Post Title: Albion graphics (PC/DOS)

The values I see here are 66 and 120, respectively. Any indication where these might fit? Maybe values inside the palette files?
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-24T09:42:23+00:00
- Post Title: Albion graphics (PC/DOS)

I am not sure but I have given the palette files just in case. I'm not 100% sure to be honest.
## Post #6
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-24T10:17:59+00:00
- Post Title: Albion graphics (PC/DOS)

I'm afraid the value stands for something else. Let me revise the specification:

uint16 {2} - Width
uint16 {2} - Height
byte {1} - Unknown (usually zero, maybe three-byte height value?)
byte {1} - Number of frames/sprites
char {X} - Width * Height bytes of image data

So this additional header value seems to indicate the number of graphics (or frames) within a single file, which is a bit odd, but fits nonetheless.

The palette files do not seem to carry any other information than colour data, though I'm not entirely sure which format is used.
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-24T19:08:02+00:00
- Post Title: Albion graphics (PC/DOS)

Probably because the game has to recognize how many frames are for a monster. Hmmmm...

Well shoot, I wonder if I can find anything within the script.

Edit: By the way, when you say your not entirely sure what format is used you mean with the palette or what? The left problem would be to figure out how the image is associated with the palette?
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-25T04:28:52+00:00
- Post Title: Albion graphics (PC/DOS)

It is possible that in these two libraries, the monster graphics and the monster data that other than giving monster stats and their attacks may at the beginning of each entry tell each monster's image AND palette.

[http://download.yousendit.com/4A0371DF6FCAC111](http://download.yousendit.com/4A0371DF6FCAC111)

It's the best lead I could think of.

Edit: Also I think the palettes are in IFF format. The game tends to use IFF in both the music and those graphics that are ILBMs. Does this carry over into the palettes as well?

Edit 2: Eh if it is all too hard I'm fine with trial and error. If it helps any I could extract an image then compare it to a screenshot. I managed to match an image while playing the game to one extracted from a library. A character profile picture.
## Post #9
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-25T22:47:01+00:00
- Post Title: Albion graphics (PC/DOS)

> Reply from Darkfox
>
> It is possible that in these two libraries, the monster graphics and the monster data that other than giving monster stats and their attacks may at the beginning of each entry tell each monster's image AND palette.
Quite possible, but hard to say. There are many values within the character files looking quite alike. You would have to compare all of those files manually to find the position of the releavant information. At the same time, you would have to take a look at the graphics to match the graphics and the character sheets. I hope you know the game well. 

Regarding the palettes: I was just confused by the fact that the palette files are only 576 bytes in size and not 768 bytes, as standard RGB palettes with 256 colours would be. Most probably, though, there are simply 64 reserved colours (for menus or backgrounds), such that there are only 192 colours for the other graphics left. Thus, as 192 * 3 = 576, it seems reasonable to me that the palettes are indeed uncompressed RGB  (or BGR or whatever) values. You still would need to find out which are the reserved values, though.
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-25T22:50:31+00:00
- Post Title: Albion graphics (PC/DOS)

I know the game well enough to convert the sounds to standard wav and the music is xmidis. But you do mean making comparisons to the ingame graphics to the extracted ones yes?

I think the easiest right now would be comparing the full body profile images. Maybe that would help figure things out better?
## Post #11
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-25T23:14:53+00:00
- Post Title: Albion graphics (PC/DOS)

> Reply from Darkfox
>
> But you do mean making comparisons to the ingame graphics to the extracted ones yes?
Yes. If you could find out which graphics belong to which character sheet files (at least some examples), you might find the system used to match these files.

(That's why I wrote that you need to know the game -- as far as I can see, there are names in the character files; this information would pose a possible way to get some matches.)

> Reply from Darkfox
>
> I think the easiest right now would be comparing the full body profile images. Maybe that would help figure things out better?
Sounds good.
## Post #12
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-25T23:38:21+00:00
- Post Title: Albion graphics (PC/DOS)

Alright, these are the comparisons I have made thus far. With the exception of equipment boxes which are separate images everything matches up perfectly (I could not get rid of them without hacking the game). I can do the same with monsters though it's difficult because the game likes to zoom since it uses a 3D system similar to games like Doom.

Edit: I'm also going to see if I can figure out monster graphics. It'll be easier in the game's built-in debug mode.
[FBODPIX001-002.rar](https://xentaxbackup.github.io/file/1287_FBODPIX001-002.rar)
## Post #13
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-26T20:58:10+00:00
- Post Title: Albion graphics (PC/DOS)

OK, as I said I'd do I did, I had to hack monster group 2 (the one automatically loaded by Producer Mode when pressing Alt+F8) and got all information I could get on the monster Fear 1. What I got was:

Monster 1 is "Fear 1" and it uses graphic graphic 1 and seemingly palette 24 or palette 6 however I could not find this present in the monster data sadly. it also uses transparency table 24 and tactical icon 13.

I have managed to make a modifier for each monster group and can go through each monster one by one.

Monster 2 is "Brogg 1", it uses monster graphic 4, tactical icon 16 and there is still mention of palette 24 which could be a shared palette for monsters.

I'll attach all my findings with screenshots below, how is this? 
[Monsters.rar](https://xentaxbackup.github.io/file/1291_Monsters.rar)
## Post #14
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-29T11:32:27+00:00
- Post Title: Albion graphics (PC/DOS)

> Reply from Darkfox
>
> I'll attach all my findings with screenshots below, how is this?
Good work! 
You are right, however, that there does not seem to be an indicator of the palette in the data files. These values might even be hard-coded ...

By the way: These are the palette files (6 and 24, respectively), when read as RGB data. Looks somehow sensible to me, though I'm not yet sure.
[Palettes006_024.jpg](https://xentaxbackup.github.io/file/1295_Palettes006_024.jpg)
## Post #15
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-29T19:37:59+00:00
- Post Title: Albion graphics (PC/DOS)

Wow, thats great!  It does look sensible to me as well. Actually, I can see the monster colors in #24 if I'm not mistaken.

Well what is the alternative if the images don't ID their palettes? Trial and error matching (which can be greatly eased using Albion's Producer Mode) Or what?
## Post #16
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-30T10:16:23+00:00
- Post Title: 

> Reply from Darkfox
>
> Well what is the alternative if the images don't ID their palettes? Trial and error matching (which can be greatly eased using Albion's Producer Mode) Or what?
As long as we cannot find that information elsewhere -- yes, probably.
## Post #17
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-30T17:27:59+00:00
- Post Title: 

I say this because I'm afraid it might be hard coded somewhere or who knows what. It is not present in the libraries I've looked at so far. The game handles palettes somehow but I cannot tell how for certainty. They are not mentioned in the scripts as if it assumes that a matching palette is told by some other manner. Though is it possible that there is an assigned palette for each image library?
## Post #18
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-31T22:06:48+00:00
- Post Title: 

> Reply from Darkfox
>
> Though is it possible that there is an assigned palette for each image library?
Why, it's certainly possible, either by hard-coded values or some other (not yet discovered) means.
## Post #19
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-31T23:10:16+00:00
- Post Title: 

I don't know if it is accurate or not but looking within the MONGFX library I found several references to 18 which is the hex of 24 and stops short of the biggest portion of the library. Perhaps they are coded into the libraries. I dunno, could just be a part of an image but it would have at least once popped up again within the library if that were the case.
## Post #20
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-01T18:40:29+00:00
- Post Title: 

This is an XLD library as well, right? As far as I can see, the XLD format is almost completely understood. Beside a two-byte header value at offset 4, all values and their purpose are clear.

So, if you have found certain bytes within an XLD library, they will either be part of a file contained within the library or part of the length table. (The file data starts at offset 8 + 4 * (uint16 at offset 6).)

Interesting fact: Some length values in the header of PALETTE0.XLD are actually 0. I suspect that palettes were removed, but their entries were kept (albeit with size zero) to keep the numbering intact.
## Post #21
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-01T20:41:22+00:00
- Post Title: 

That is correct. The same for many other libraries. I think they might have later been removed and serve as null points. Btw, I can't seem to find anything about how the game assigns palettes to images yet. Unless there is another library that does it (for who knows why they would do this) I don't know what.
## Post #22
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-03T19:00:36+00:00
- Post Title: 

Well here's the transparency table that "Fear 1" uses (#24) for possible information of any sort, otherwise I've found nothing else of possible use. There is no other libraries that tell which palettes to use and there is no mention in the scripts. *sigh* I'm totally out of ideas here.
[TransparencyTable024.rar](https://xentaxbackup.github.io/file/1302_TransparencyTable024.rar)
## Post #23
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-07T23:57:29+00:00
- Post Title: 

Hm, no, sorry. I can't seem to identify any relevant structure in that data.
## Post #24
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-08T00:04:25+00:00
- Post Title: 

Didn't really think so. Though I have no clue why they are among the biggest if they just assign transparency. It was the only other thing used, sorry.

*sigh* Not sure what else to try, there seems to be no relevant information, though perhaps each image library uses a specific palette. I'll look through a couple more monsters and see if it continues to use palette 6/24. Then see if full body pictures follows this as well.

Edit: It is a working theory so far. Full body pictures seem to use palette #19
Monster and battle graphics seem to use palette #24, RPG style top view character graphics seem to use palette #6. First two assumptions seem to hold water, palette #6 I'm not 100% sure on.

Edit 2: If I was to give a wild guess the palette data is hard coded in the main executable (funny enough named Main.exe) however it may be a reach on my part.
## Post #25
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-08T15:04:31+00:00
- Post Title: 

> Reply from Darkfox
>
> If I was to give a wild guess the palette data is hard coded in the main executable (funny enough named Main.exe) however it may be a reach on my part.
You might be right there. There are a lot of (especially older) games which have some kind of hard-coded data. You could also try grabbing a disassembler and find out, but I'm not sure if the result is worth the hassle.
## Post #26
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-08T15:51:24+00:00
- Post Title: 

> You might be right there. There are a lot of (especially older) games which have some kind of hard-coded data. You could also try grabbing a disassembler and find out, but I'm not sure if the result is worth the hassle.

Thats what I'm thinking. I've managed to find out more about what image goes to what palette using the debug mode. Plus assembly is a bit difficult to read for me.
## Post #27
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-10T22:42:15+00:00
- Post Title: 

Sorry for the bump but has the palettes been confirmed as RGB? Or is that something still to be figured out? Graphics are the main, if not only, falling part. Music was XMI and sounds were raw PCM I believe, I used an existing VOC to get the correct rate.
## Post #28
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-11T08:19:07+00:00
- Post Title: 

If the attached picture looks sensible to you, then it's RGB.

This is the first frame of "File 000361" with palette 024 for the first 192 colours and palette000.dat (which is probably the shared palette) for the upper 64 entries.
[00036_024_000.jpg](https://xentaxbackup.github.io/file/1312_00036_024_000.jpg)
## Post #29
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-11T17:04:46+00:00
- Post Title: 

This is a monster graphic yes?

Edit: Otherwise the skin looks right, if it was other than RGB the skin would have a blue or green tint to it. The other qualities such as the beard and etc also look well and in order.
## Post #30
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-11T18:41:03+00:00
- Post Title: 

> Reply from Darkfox
>
> This is a monster graphic yes?
I assume so. 
I just copied the data from the "File 000361", which was in the very first data sample you have uploaded.
## Post #31
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-11T19:17:03+00:00
- Post Title: 

Ok I found it, now to check how it looks ingame compared to the palletized image you submitted, it is monster graphic #36, I was using Game Extractor at the time. I will check.
## Post #32
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-11T21:59:53+00:00
- Post Title: 

Great news! 

Dare to compare! 
[AlbionBandit3.PNG](https://xentaxbackup.github.io/file/1313_AlbionBandit3.PNG)
## Post #33
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-14T00:34:03+00:00
- Post Title: 

Looks fine to me.
## Post #34
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-14T00:46:41+00:00
- Post Title: 

Thats an ingame screenshot of the graphic. A bit zoomed but you can tell that you were on the money with the palette.
## Post #35
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-15T18:13:21+00:00
- Post Title: 

You'd like to have a converter now, wouldn't you? 

(Until now, I have constructed the images by hand. Will see if I can whip something up.)

Edit: Try [this here](http://www.xentax.com/uploads/author/denizoezmen/_ALB2BMP.zip), example syntax:

```
ALB2BMP *.img special.pal shared.pal
```
## Post #36
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-15T23:23:55+00:00
- Post Title: 

Works great so far, looks like you even included converting animation frames in separate BMPs from the # part, I'll have to try out an animated monster and see how that goes. 

Edit: Another success! 

Edit 2: Also I found the shared palette is I believe the one that isn't in a library but is an external one called "Palette.000" and it seems to be working just fine.
## Post #37
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-15T23:54:17+00:00
- Post Title: 

Nice to hear that it works. 

> Reply from Darkfox
>
> Also I found the shared palette is I believe the one that isn't in a library but is an external one called "Palette.000" and it seems to be working just fine.
Yes, I think that's the one I used for constructing the "manual" sample earlier.
## Post #38
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-16T00:03:05+00:00
- Post Title: 

Without any hitch it has successfully converted a monster graphic and all party full body graphics. Next is to try out 3D textures and objects which are done much like early FPS.

Excellent work!  Still I am confused why a tool to handle XLDs was made but nothing to handle sound or graphics. Well at least now there is something  for graphics thanks to you and sound is no big problem.
## Post #39
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-16T04:22:40+00:00
- Post Title: 

Strangely they changed something for the 3D Objects. They are 2D images as well but for some odd reason will not convert them. Do they work for you or did they change something for these?

Edit: Backgrounds work but a similar problem is with tactical icons. I think these images lack certain... data O_o

Edit 2: So far what doesn't work is textures, "3D" objects, "3D" overlays, tactical icons. Still testing more. They seem to be raw images without any width data or anything in that manner. Floor graphics seem to be 64*64 block textures while wall textures are oddly variable. Perhaps the width of these would have been told by the 3D maps, which would be a bummer.

Edit 3: Overview character graphics like for walking around party members and NPC are handled differently but DO contain data at the beginning thankfully. Some examples can be seen here: [http://download.yousendit.com/77BA5F2019E56B9C](http://download.yousendit.com/77BA5F2019E56B9C)

I'd like to apologize for this, I had figured that it would keep this pattern... apparently there were exceptions. I don't exactly see how changing the method would help them any but ah well... converter still worked flawlessly on the things that use method 1. 
[3DObjects.rar](https://xentaxbackup.github.io/file/1320_3DObjects.rar)
## Post #40
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-16T08:29:54+00:00
- Post Title: 

You're right. There are those files without any header and those where the header exists, but is not repeated with each frame.

Strange unstructured formats are no fun. 

Anyway, I've updated the converter to try and compensate for this. For the files which only contain one header, call

```
ALB2BMP *.img special.pal shared.pal /noheadrepeat
```

For those without any header at all, try

```
ALB2BMP *.img special.pal shared.pal /nohead:width,height
```

Obviously, you have to specify the dimensions yourself, unless we can be sure that only one frame is contained in every file. In that case just the width or height might be enough.
## Post #41
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-16T09:36:03+00:00
- Post Title: 

I'll try it out now, though one question...

For those like data099.dat (the animated torch, a 3D Object) how would it be handled? One image very long or is there a way the file tells where to cut the frames? Neither way bothers me but just curious.

> Strange unstructured formats are no fun.

No argument here.  Hit me off guard. Didn't notice it until it crashed.
## Post #42
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-16T09:53:40+00:00
- Post Title: 

> Reply from Darkfox
>
> For those like data099.dat (the animated torch, a 3D Object) how would it be handled?
It would produce seperate images for each frame, if I hadn't programmed a buggy piece of software. 
Updated version available.

(That's why the program asks for the image height as well; if it didn't, it could just generate one large strip containing all frames.)

In that particular case, the image dimensions are 24x78.
## Post #43
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-16T10:01:12+00:00
- Post Title: 

I see, I believe that makes sense. And determining the width is no problem and I suppose a height wouldn't be difficult either using Texture Finder to figure out a fitting one. Again much appreciation.
## Post #44
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-16T10:19:33+00:00
- Post Title: 

You're welcome. See if you can find any other bugs.
## Post #45
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-09-02T04:20:02+00:00
- Post Title: 

No bugs so far but I did put together a small frontend for the program, it's not much but it handles each image and then when all information is filled out one just has to push a button and call up the program. I did it to pick up on things for my programming class but at the same time it streamlines the usage of ALB2BMP and I threw in some tooltips. It would have been done earlier today but I took effort to pretty it up with a custom cursor and icons and such which wasn't covered in class. All in all it was a learning experience to get my feet wet with.

Again thanks for the program. 
[AlbionConvert.PNG](https://xentaxbackup.github.io/file/1329_AlbionConvert.PNG)
## Post #46
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-09-02T15:55:11+00:00
- Post Title: 

Nice going. 
Have fun with your programming classes!
