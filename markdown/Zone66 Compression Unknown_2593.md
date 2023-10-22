## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-04-23T06:11:17+00:00
- Post Title: Zone66 Compression Unknown

Here are some examples of the Z66 compression. The music is suspected to be either XMI, MID, or possibly from the size a form of MOD.

It's an old game mind you but it is still considered to be a very good arcade topdown shooter/bomber.
[PREFS.rar](https://xentaxbackup.github.io/file/1135_PREFS.rar)
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-01T02:03:00+00:00
- Post Title: Zone66 Compression Unknown

Also, as in the other thread a demo of the game can be found here: [http://www.dosgamesarchive.com/download/game/182](http://www.dosgamesarchive.com/download/game/182)

Hope this helps.
## Post #3
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-05-03T08:13:25+00:00
- Post Title: Zone66 Compression Unknown

I fumbled around with the decompression of the Z66 files.
It seems to be either some kind of LZ(W)- or RLE-based-compression.
The first 4 bytes are the size of the decompressed data, after this the compressed data follows as bitstream where the bits are read bytewise from MSB to LSB.
For now I found out that bit 0 indicates that a literal byte follows in the next 8 bits. I'm not quite sure yet what bit 1 means.
It could also be that it's LZW compressed, this would also work with the first few bytes. I'll need to dig deeper
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-03T08:58:19+00:00
- Post Title: Zone66 Compression Unknown

Hey thanks!  The compression used by Zone 66 has been a roadblock in more extensive modding.
## Post #5
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-05-05T00:40:26+00:00
- Post Title: Zone66 Compression Unknown

LZW it is. More tomorrow
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-05T02:18:03+00:00
- Post Title: Zone66 Compression Unknown

I'll wait patiently for further results. I know a little about the LZW compression and it is good to hear somthing familiar.
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-07T18:30:03+00:00
- Post Title: Zone66 Compression Unknown

Sorry for the double-post, just checking if there is any update on that compression. I guess there have been some delays, somthing popping up and things like that right? Same here if that is the case.
## Post #8
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-05-07T20:37:14+00:00
- Post Title: Zone66 Compression Unknown

It's almost done but as you said, something popped up 
I'll try to get it done this week.
Also I need to test it with all the files. There's a slightly different decompression routine in the Exe and I'm not sure if it's used. If it is used, then there's no way of telling which routine is used on which files aside from testing manually. But that shouldn't be a big problem.
I also looked at the decompressed files and how hard it would be to make a map-editor. But nothing much yet.
## Post #9
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-07T20:45:05+00:00
- Post Title: Zone66 Compression Unknown

I have managed some slight map editing but it was just fooling around blindly. XD Well I thought somthing happened thats why I didn't say anything a few days ago. For me there is graduation rehearsal then graduation itself. So I have to get ready for that. O_o

As for the different compression, how troublesome might it be?
## Post #10
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-05-07T21:14:29+00:00
- Post Title: Zone66 Compression Unknown

Not much. The only difference is one value used in the LZW decompression.
It's the maximum dictionary size. In the code I currently use it's max. 13 bits, in the other code 14 bits. That's all I can see so far.

I just threw together a sucky [map viewer](http://img171.imageshack.us/my.php?image=suckyya3.png). Works ok so far but some tiles seem wrong. I use the MAPA.Z66 and MAPAGRFX.Z66 files and there's probably more stuff in the other files.
## Post #11
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-07T22:04:39+00:00
- Post Title: Zone66 Compression Unknown

Woah... that looks pretty good so far  but yeah, some of the tiles are a bit wrong. If it'll help I could give screenshots of places and you could compare.

I didn't think you'd try this too. You have really suprised me in all seriousness. In a good way.
## Post #12
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-05-07T22:19:01+00:00
- Post Title: Zone66 Compression Unknown

In MAPADAT.Z66 are the animations of the tiles. These values translate to the actual tile to use.
Well, more tomorrow I hope.
## Post #13
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-05-08T07:11:43+00:00
- Post Title: Zone66 Compression Unknown

I found out more. The [map looks much nicer now](http://img522.imageshack.us/img522/3213/map1au9.png) 
[map1au9.png](https://xentaxbackup.github.io/file/1218_map1au9.png)
## Post #14
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-08T09:36:29+00:00
- Post Title: Zone66 Compression Unknown

Sure does!  It's looking very nice now.
## Post #15
- Username: triton
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Mar 05, 2007 10:41 am
- Post datetime: 2007-05-09T08:52:30+00:00
- Post Title: Zone66 Compression Unknown

Great job, john_doe!
## Post #16
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-09T20:10:28+00:00
- Post Title: 

Yeah, it is very impressive. I played this game a lot when I was young and have been holding onto it since. But I think it's about time to open new doors for it.
## Post #17
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-13T08:08:13+00:00
- Post Title: 

Hey, if you need any other map packs to look at and cross-examine I can provide them. Also that recent screen is darn accurate.  I'll see if I can find that spot somtime or if Ardent wants he could.

Btw, how easy will it be to make custom graphics for a map and etc? Custom sounds and music? To make a map viewer the graphics must be of a readable format.
## Post #18
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-05-13T16:35:34+00:00
- Post Title: 

Sorry that I haven't released the decompression tool yet. It works so far but crashes with the problem I mentioned before (the different max. dictionary size in the LZW decompressor). I want it to detect automatically which value is used somehow.

And yes, it's basically possible to modify the graphics. The tile graphics are simply a big file with 32x32 tiles one after the other without any kind of additional compression or other data. So it would be easy to convert this to BMP and vice versa or similar.

I also found out how to decompress the sprites, it's a very simple RLE-variant.

I have no clue yet what format is used for the music. Sounds like MOD or similar.
## Post #19
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-13T16:58:44+00:00
- Post Title: 

Thats what I figured. Somthing like music module. MOD is the most common.

Edit: Well, just certain questions popped into my head about it is all. It was a few things I thought of because of further map editing and custom ship graphics would be neat. Thanks for the answer.
## Post #20
- Username: Ardent
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Apr 06, 2007 4:23 am
- Post datetime: 2007-05-14T02:43:57+00:00
- Post Title: 

My specialty is with editing.  I could make new tiles, sprites, AIs, etc...  If you show me how to unlock these treasures, it wouldn't take long for me to figure it all out.  (I might even be able to fix that stupid level 2 bug )
Memory scanning is a natural talent as well, though I've not been able to find any use for it besides cheating... 

[edit]
I've found the spot where the map viewer was centered on.  it showed the north-western corner of an island in the north-western corner of the map.  For some reason we need this information?

> Reply from Darkfox
>
> ... Also that recent screen is darn accurate.  I'll see if I can find that spot somtime or if Ardent wants he could...
[/edit]
[game_013.png](https://xentaxbackup.github.io/file/1156_game_013.png)
## Post #21
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-14T05:05:03+00:00
- Post Title: 

Level 2 bug? Which exactly is this?

Edit: I didn't look too deeply but it should be fixable since it's map related.
## Post #22
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-05-21T02:36:07+00:00
- Post Title: 

Nice find in the screenshot. Say john_doe, you want me to put up another map pack for cross reference sake to see if it remains constant throughout? Also, how does the maps handle spawn points (where the enemies lift off the landing pad)? I was never able to figure that one out.

Edit: Oh yeah. Have you been able to see the overlay objects or however they are called? Like the clouds that float by? Thats another one thats been itching at me. >_< You've made more progress than me on this, I managed to edit small portions of the map but you have managed to make a map viewer, even though simple as you say. Then again this is why I'm in college. 

Edit 2: No I'm not trying to push or anything. Purely out of curiousity's sake I ask these things. And I wondered if you needed another map pack to help because the demo only has the first map. I figured that would be restrictive. I'm still going to be patient for a release.
## Post #23
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-06-12T15:57:31+00:00
- Post Title: 

Hope this is alright but I've been wondering if your alright there? Haven't seen nor heard much of you recently. I have those other maps if you want to examine those as well. Demo only has the first map, so if it'd help you any just ask.
## Post #24
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-06-12T19:07:49+00:00
- Post Title: 

Hi,

No worries, I've just been busy with some other stuff. 

I've made a little sprite viewer some time ago, it works quite well so far.
There's still the problem with the different LZW values...probably I'll just have to hard-code a list of filenames and note which version of the algorithm to use...

Oh, and I got the full version, and so far the level viewer seems to work on the other maps, too.
I'm still not sure where the other objects you mentioned, like clouds etc, are placed/defined in the map file, or the enemy spawn points.

Well, that's it so far. If I find some more time I'll try to either add something to the Wiki or at least release some notes/source.
## Post #25
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-06-12T20:34:19+00:00
- Post Title: 

Alright, cool.  Hm, wonder why different values were used.
## Post #26
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2007-06-14T13:27:47+00:00
- Post Title: 

Hi,

I'm also extremely  interested in your findings. I know this game (I even own  the full version, which was IIRC very hard to come by here in Germany) and I remember trying to figure out the file formats some years ago.

Have you taken a look at the other files, besides maps and sprites? I guess most of them are compressed in the same way.

Some trivia:
* The music is probably indeed in MOD format, or at least in some other tracked format. The game was programmed by two guys from the scene group "Renaissance", namely Tran aka Tomasz Pytel and CCCatch aka Kenny Chou. Everyone in the scene used tracked music back then 
* There were severyal versions of the game released. The early versions did have a very special protected-mode memory manager and only ran without EMS and XMS drivers loaded (i.e. pure DOS). In a later release (maybe a re-release?) they switched to the PMODE/W extender, which allowed the game to run fine with EMS memory installed.
## Post #27
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-06-18T22:14:33+00:00
- Post Title: 

I've done some stuff with the ships and figured out a means of adding in custom packages without having to replace currently existing ones. Replacing stuff can be really annoying and limiting and I'm glad it's possible to do without.
## Post #28
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-28T16:57:03+00:00
- Post Title: 

Any updates or anything? There seems to have been great strides since the beginning but I was asked, sorta, to check in and see how things are going. I do think compression would have to be the most difficult portion of Zone 66 but you seem to have taken great strides with it so how is it going?
## Post #29
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-09-30T19:57:43+00:00
- Post Title: 

Sorry to bump but has there been any progress. I can understand time constraints now that college has restarted I just wonder where things are at this time. I haven't been able to pick up on this for a while myself, thought I'd wait for a while and not try to mess anything up until I was certain. XD

I'm not trying to rush but it's been a while since a progress update on the compression and map data.
