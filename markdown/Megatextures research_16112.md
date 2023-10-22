## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-09T20:31:59+00:00
- Post Title: Megatextures research

Hello everyone.

After I did lots of research in sound formats, archives, models and animations I finally decided to get to most complicated task I've heard of: Megatextures.

This is current state of research: Doom/Evil Within/Wolfenstein tools are available here: [http://aviacreations.com/wraith/](http://aviacreations.com/wraith/)# 

And that's how it all started back in march'2017: after a couple of weeks I was able to reverse the modified version of HDP they used and decompress tiles. The devs improved the coding algorithm in compare to standard HDP. 

Now I see that tiles are actually in correct order inside of megatexture as expected. This is just a random set of tiles taken from the middle of Wolfenstein Old Blood .pages file. I combined them manually, wanted to check the result as soon as possible
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-10T09:53:29+00:00
- Post Title: Megatextures research

Checked Doom. For each texture I'm getting 3 images 4 channels each. Not sure yet where is what, just got them for the first time, the whole process takes a minute. This is so slow, because its only a test tool now.

So I think this will work for all megatextured games.
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-04-10T15:21:18+00:00
- Post Title: Megatextures research

This is an epic job! Thanks a lot. Especially for DOOM
## Post #4
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-04-10T16:12:18+00:00
- Post Title: Megatextures research

Good work. I could never get past the Codec, as that kind of thing was (and is) over my head. I look forward to seeing the final results.  

As an aside, While Doom and Wolfenstein both use HDP, there's another game using Megatextures, The Evil Within.  However, as far as I know, it's the only game that doesn't use HDP, They chose to use  DCT instead.

enum pageCompression_t
{
    COMP_INVALID = 0x0,
    COMP_NONE = 0x1,
    COMP_DXT = 0x2,
    COMP_LZW = 0x3,
    COMP_DCT = 0x4,
    COMP_HDP = 0x5,
    COMP_JXR = 0x6,
    COMP_MAX_COMPRESSIONS = 0x7,
};

[viewtopic.php?f=10&t=12110](http://forum.xentax.com/viewtopic.php?f=10&t=12110)
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-10T19:58:06+00:00
- Post Title: Megatextures research

Normal maps also look ok
## Post #6
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-04-10T22:41:44+00:00
- Post Title: Megatextures research

this is amazing! 

your tool is able to extract a certain set of textures for a specific model or the entire vmtr, like the tool released by m0xf?
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-11T06:14:28+00:00
- Post Title: Megatextures research

My tool is able to extract anything in any order. You can get one texture of your choice, or ALL textures for one or all models or world. You can also grab the whole vmtr, which I don't see any useful, because it will be all in random order, why can anyone even need that?

You can surely extract the whole megatexture, or only the biggest MIP of it, with all tiles in correct order. But since many parts of megatexture are repeated, or not used (black squares), this texture will be even bigger than the whole vmtr.

Also, it will not require game exe, or running game, and will work with all games using HDP textures.

p.s. i have an idea. I can make a test to check if there are any parts of megatexture not used by any model. Like a search for hidden textures.
## Post #8
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-04-11T11:28:03+00:00
- Post Title: Megatextures research

> Reply from daemon1
>
> My tool is able to extract anything in any order. You can get one texture of your choice, or ALL textures for one or all models or world. You can also grab the whole vmtr, which I don't see any useful, because it will be all in random order, why can anyone even need that?

You can surely extract the whole megatexture, or only the biggest MIP of it, with all tiles in correct order. But since many parts of megatexture are repeated, or not used (black squares), this texture will be even bigger than the whole vmtr.

Also, it will not require game exe, or running game, and will work with all games using HDP textures.

p.s. i have an idea. I can make a test to check if there are any parts of megatexture not used by any model. Like a search for hidden textures.

obviously that export a specific texture or a specific set of textures is more convenient than export the entire megatexture, this will help a lot, even in future games 

I remember that the other tool doesn't export some pages from virtual textures like the alpha and the metalness pages (vmtrpower and vmtrcover) can you extract all pages, right? not only specular, diffuse and normal?
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-11T11:45:48+00:00
- Post Title: Megatextures research

> Reply from luxox18
>
> I remember that the other tool doesn't export some pages
What do you mean by the other tool? I don't know any tool that can export Doom textures. Do you?

As for layers, I'm not sure what is metalness or power. But yes, I can export all layers.
## Post #10
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-04-11T17:10:48+00:00
- Post Title: Megatextures research

I think he means the tool for Wolfenstein. There was a tool by m0xf which hooked into the game to extract vmtrs.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-11T20:52:40+00:00
- Post Title: Megatextures research

> Reply from volfin
>
> I think he means the tool for Wolfenstein. There was a tool by m0xf which hooked into the game to extract vmtrs.

I didn't check all layers in Wolfenstein yet. I was talking about Doom.
## Post #12
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-04-11T21:18:20+00:00
- Post Title: Megatextures research

yes, I was referring about the wolfenstein tool but I was extrapolating that situation to the Doom textures.

also, thanks for this tool. finally a solution for obtain virtual textures directly and easily.
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-12T04:09:20+00:00
- Post Title: Megatextures research

> Reply from luxox18
>
> yes, I was referring about the wolfenstein tool but I was extrapolating that situation to the Doom textures.

also, thanks for this tool. finally a solution for obtain virtual textures directly and easily.

Sure 

You don't have to extrapolate here. All games have slightly different formats. I'm checking other games meanwhile.
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-12T09:13:55+00:00
- Post Title: Megatextures research

Ok that DCT compression from Evil Within is much simpler than HDP. I've already cracked it. Here's some random part decoded from an_emergency_call_vmtr.pages, still need to browse megatexture correctly, but this will not take much time.

Note that color conversion may be incorrect, I just applied standard YUV to RGB.
[firstevil.jpg](https://xentaxbackup.github.io/file/12766_firstevil.jpg)
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-12T11:25:10+00:00
- Post Title: Megatextures research

yes, something may be wrong with colors. This is pl00 face, head, coat and cloth, which i believe must be the hero.
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-12T14:48:59+00:00
- Post Title: Re: Megatextures research

I think now its correct
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-12T16:21:54+00:00
- Post Title: Re: Megatextures research

Yes must be about correct. There are different YUV to RGB variants, need to choose one.
## Post #18
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-04-12T17:14:18+00:00
- Post Title: Re: Megatextures research

Here's some reference pics from the game:
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-13T15:15:16+00:00
- Post Title: Re: Megatextures research

> Reply from volfin
>
> Here's some reference pics from the game:

Oh, its HER jeans  Now I see its all correct.
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-15T15:18:55+00:00
- Post Title: Re: Megatextures research

Working on models.
## Post #21
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-04-15T15:25:16+00:00
- Post Title: Re: Megatextures research

> Reply from daemon1
>
> Working on models.for what game?
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-15T16:34:32+00:00
- Post Title: Re: Megatextures research

> Reply from Tosyk
>
> for what game?

This one is from Doom. But must work similar with other ID games.
## Post #23
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-04-15T17:58:52+00:00
- Post Title: Re: Megatextures research

But what about id Tech 4 games? From what I`ve heard, some of these games using that engine used Megatextures as well.
## Post #24
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-04-15T18:30:29+00:00
- Post Title: Re: Megatextures research

Id Tech 4 was the engine used for Doom 3.  But at that time, it was only used for the map environment. Models and Characters still used traditional textures. So it's not applicable.  With Tech 5, they expanded megatexture to Characters and Objects. Which is the problem being addressed here.
## Post #25
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-04-15T18:43:55+00:00
- Post Title: Re: Megatextures research

> Reply from volfin
>
> Id Tech 4 was the engine used for Doom 3.  But at that time, it was only used for the map environment. Models and Characters still used traditional textures. So it's not applicable.  With Tech 5, they expanded megatexture to Characters and Objects. Which is the problem being addressed here.Yeah but at the time the MegaTexture concept did not exist until Enemy Territory Quake Wars came in.
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-15T18:56:22+00:00
- Post Title: Re: Megatextures research

> Reply from AnonBaiter
>
> But what about id Tech 4 games? From what I`ve heard, some of these games using that engine used Megatextures as well.

I can look at those too. After id tech 6 and 5.
## Post #27
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-04-15T21:25:29+00:00
- Post Title: Re: Megatextures research

Brink's graphic is most interesting for me
## Post #28
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-04-15T21:39:23+00:00
- Post Title: Re: Megatextures research

> Reply from Tosyk
>
> Brink's graphic is most interesting for me

according to Wikipedia:

> Brink, which uses a heavily modified version of id Tech 4 also uses virtual texturing. While the implementation is different from MegaTexture, it was inspired by it.

So yeah that would probably be a whole other kettle of fish 

Of course Wikipedia is often wrong, like where they say:

> All id Tech 5 and id Tech 6 games use MegaTexture, with the exception of The Evil Within which uses a new renderer.
Wrong. it's just a different encoding. Still uses MegaTexture.
## Post #29
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-04-15T21:50:57+00:00
- Post Title: Re: Megatextures research

if I remember, there is a command for Brink that allows to dump all textures as a big tile
## Post #30
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2017-04-15T22:01:38+00:00
- Post Title: Re: Megatextures research

Great work!  I'm glad to see someone conquer Megatextures for Doom
## Post #31
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-04-16T07:32:41+00:00
- Post Title: Re: Megatextures research

> Reply from luxox18
>
> if I remember, there is a command for Brink that allows to dump all textures as a big tilecan you give more information on this?
## Post #32
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-04-16T09:48:30+00:00
- Post Title: Re: Megatextures research

> Reply from Tosyk
>
> luxox18 wrote:if I remember, there is a command for Brink that allows to dump all textures as a big tilecan you give more information on this?

all idtech games with virtualtextures have a command that allows you to dump all textures from a scene in form of a big tile (diffuse, specular and normal) like the Wolfenstein new order tool by m0xf. 

In almost all games this command is locked.
In the alpha version of Doom the command was enabled but you only obtain three big back dds tiles.

for Brink the command is writeVirtualPageFile 0 or 1 or 2 , each number is a mip, zero is the highest mip but I think that the game crashes.

also there is other command called writeImage where you can obtain a texture if you know the exact name in game files from materials.
## Post #33
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-04-16T12:22:08+00:00
- Post Title: Re: Megatextures research

If you want only characters textures, quickbms script extracting them in small packages (.unknown extension and hash as a name) - each set of textures for character, though they are headerless. I made script for them long ago, can't find it unfortunatelly, only for models.

Here's an example of texture set file.

[https://www.sendspace.com/file/n5m0l4](https://www.sendspace.com/file/n5m0l4)

And here's how they comes out

[https://www.sendspace.com/file/7il0ji](https://www.sendspace.com/file/7il0ji)
## Post #34
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-04-16T17:42:11+00:00
- Post Title: Re: Megatextures research

> Reply from zaramot
>
> If you want only characters textures, quickbms script extracting them in small packages (.unknown extension and hash as a name) - each set of textures for character, though they are headerless. I made script for them long ago, can't find it unfortunatelly, only for models.

Here's an example of texture set file.

https://www.sendspace.com/file/n5m0l4

And here's how they comes out

https://www.sendspace.com/file/7il0jithanks, where can I find script for models?
## Post #35
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-18T20:56:14+00:00
- Post Title: Re: Megatextures research

I was able to pack Megatextures back into the game 

[https://youtu.be/j98grTHAvns](https://youtu.be/j98grTHAvns)
## Post #36
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-04-18T22:32:34+00:00
- Post Title: Re: Megatextures research

Now that's even more impressive than decoding them. Nice job.
## Post #37
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-04-25T15:46:23+00:00
- Post Title: Re: Megatextures research

So is it near to release? I look every day to see.
## Post #38
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-25T16:48:41+00:00
- Post Title: Re: Megatextures research

> Reply from volfin
>
> So is it near to release? I look every day to see.

Must be soon. We still have some issues with normals, and you know I HATE normals, mean vertex normals in a model. They just dont work normally in blender if you know what i mean.

If we can't figure it out any soon, we'll just release it like that.
## Post #39
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-04-25T17:23:10+00:00
- Post Title: Re: Megatextures research

> Reply from daemon1
>
> volfin wrote:So is it near to release? I look every day to see.   

Must be soon. We still have some issues with normals, and you know I HATE normals, mean vertex normals in a model. They just dont work normally in blender if you know what i mean.

If we can't figure it out any soon, we'll just release it like that.

Yep I can't say I've ever had any success with importing vertex normal in blender. the closest was what I did with Far Cry Primal, and it's still not exactly right. Keep up the good work.
## Post #40
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-25T17:54:21+00:00
- Post Title: Re: Megatextures research

A little progress report

[https://www.youtube.com/watch?v=5_l4ikND7tc](https://www.youtube.com/watch?v=5_l4ikND7tc)
## Post #41
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-27T18:27:40+00:00
- Post Title: Re: Megatextures research

You can expect the tool release very soon now, maybe even today. And while you wait, here's The brief history of megatexture research.

March 22nd

The first look into mega2 files. I found they contain tons of small pieces - tiles. From xentax thread I got info that's probably HDP or JXR compression. After downloading HDP specs and sources it becomes clear why nobody was able to decode it before. Walls of code. Very complicated algorithm, even having the specs.

March 25th

I found decoding routine in Doom and got the first tile decoded by it from memory.



Making standard headers for the raw data (with all available options tried) surely fails.



March 26-30th

I needed to finish cloth extraction for Hitman 5, and D-Walker animations for MGSV, so nothing was done here.

April 3rd

After some days of studying the format specs and raw data I came to conclusion that it was modified, non standard HDP format. So the only way to decode it was to carefully study their routine step-by-step and find what exactly was changed. But it looked so tangled up even after some debugging and multiple reading through the doc, that I said: "no. its TOO complex. i think i wont be able to do this"

April 7th

After some more debugging and studying, and changing the code, the very first monochrome tile was decoded. I couldn't believe it first, but it couldn't be just by accident. This was correctly decoded tile.



April 8th

More in-depth research showed that most changes were made deep inside of the adaptive variable-length bitstream reading which mostly concerned colored images. Some changes found, and I could decode about half of the image, and then it fails:



April 9th

Lots of hard work to dig into the very core of this crazy algorithm, many more changes were found and at some point I got this:



This was the very first 3-channel tile (not very colorful, but its colored) decoded from megatexture. After that, It was all history. Just some little tweaks and checks, was a little bit different in all games, but the problem was finally solved. You can count, it took 13 days.
## Post #42
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-29T05:36:36+00:00
- Post Title: Re: Megatextures research

Tool released (early beta) [http://aviacreations.com/wraith](http://aviacreations.com/wraith)
## Post #43
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-04-29T07:05:06+00:00
- Post Title: Re: Megatextures research

So this looks to support Doom only. When will Evil Within support be coming?
## Post #44
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-29T07:22:19+00:00
- Post Title: Re: Megatextures research

> Reply from volfin
>
> So this looks to support Doom only. When will Evil Within support be coming?

Yes, Evil Within is also planned. Please understand, we can't support all games at once, we need to do them one by one.
## Post #45
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-04-29T20:31:01+00:00
- Post Title: Re: Megatextures research

Are you going to support other model formats? I use Blender and 3dsMax, not Maya. 

Edit: nevermind, I see now you can choose the file format on the file Pane. Derp.
## Post #46
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2017-04-30T03:40:37+00:00
- Post Title: Re: Megatextures research

Amazing! Thank you this is fantastic, works great
## Post #47
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-04-30T16:34:37+00:00
- Post Title: Re: Megatextures research

Amazing tool! Congrats with the epic job and it's release:) Does anyone encountered problems extracting DLC multiplayer armor? I tried to extract robotic_set1 and it comes without textures. Though, robotic_set2 extracting with textures.
## Post #48
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-30T16:51:08+00:00
- Post Title: Re: Megatextures research

> Reply from zaramot
>
> Amazing tool! Congrats with the epic job and it's release:) Does anyone encountered problems extracting DLC multiplayer armor? I tried to extract robotic_set1 and it comes without textures. Though, robotic_set2 extracting with textures.

can you give a model name/path? because i can't find them in the tree
## Post #49
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-04-30T18:21:25+00:00
- Post Title: Re: Megatextures research

Thanks a lot for fast reply Daemon1!   Unfortunately, I'm on different PC now, so can't tell you exactly the path - but name was robotic_set1, it's in the same place as all MP armors are (templar, uac etc). But! It might be, that you don't have them because they are from DLC unto the evil, and I'm pretty sure they aren't included in main DOOM game. It's not free DLC and it was released few month after main game with few maps and 4 new armor sets.
## Post #50
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-30T19:56:27+00:00
- Post Title: Re: Megatextures research

> Reply from zaramot
>
> Thanks a lot for fast reply Daemon1!   Unfortunately, I'm on different PC now, so can't tell you exactly the path - but name was robotic_set1, it's in the same place as all MP armors are (templar, uac etc). But! It might be, that you don't have them because they are from DLC unto the evil, and I'm pretty sure they aren't included in main DOOM game. It's not free DLC and it was released few month after main game with few maps and 4 new armor sets.

Everybody has them because you can encounter the guys who bought them in MP game.

We'll check that.
## Post #51
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-05-11T17:26:38+00:00
- Post Title: Re: Megatextures research

Any progress on the Evil Within tool?
## Post #52
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-05-11T17:52:25+00:00
- Post Title: Re: Megatextures research

we are still gathering feedback for doom. Most of research for EW is completed though, only need to make tool now.
## Post #53
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-05-12T12:00:22+00:00
- Post Title: Re: Megatextures research

Hey daemon1! Is there a way to extract textures for robotic_set1 (cooked/model/models/characters/mp/robotic_set1)? I used updated version of doom's Wraight with no luck. I guess, it's something different, than with other models and their missing textures. Thanks
## Post #54
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-05-13T13:42:09+00:00
- Post Title: Re: Megatextures research

> Reply from zaramot
>
> Hey daemon1! Is there a way to extract textures for robotic_set1
Looks like texture names for mp sets are combined by the game somehow. The material does not correspond to real texture. But yes, there's a way to extract it. .vmtr is a text file. Change name for some other texture to be robotic set1, and tool will extract that texture for you. Note that you have to reload tool after you make changes to vmtr.
## Post #55
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-05-14T14:59:03+00:00
- Post Title: Re: Megatextures research

Meanwhile I'm back to Evil Within megatextures. Unlike Doom, they have 8 images, and all different format. So I need to do some tests. This is for example some weapon. Diffuse 3ch, normal 2ch, and specular 1ch. There are 2 more images for this one, working on those.
## Post #56
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-05-14T17:16:06+00:00
- Post Title: Re: Megatextures research

Now for faces I'm getting diffuse, normal, 1 or 2 masks, and sometimes secondary diffuse and normal with veins (not for this one)
## Post #57
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-05-15T00:47:39+00:00
- Post Title: Re: Megatextures research

the last one is probably a translucency map for simulated subsurface scattering.  note how the earlobes and nose are more transparent than the rest.
## Post #58
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-05-15T16:00:23+00:00
- Post Title: Re: Megatextures research

ok it looks like i can now decode all images from EW. Still not sure about color conversions, may need to go into the code again, anyway, soon we'll be making a new tool for EW, similar to Doom.
## Post #59
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-05-15T16:36:22+00:00
- Post Title: Re: Megatextures research

> Reply from daemon1
>
> ok it looks like i can now decode all images from EW. Still not sure about color conversions, may need to go into the code again, anyway, soon we'll be making a new tool for EW, similar to Doom.

Yeah I was thinking the Diffuse up there seemed a bit too reddish.  But still, awesome work, keep it up.
## Post #60
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2017-05-15T20:44:49+00:00
- Post Title: Re: Megatextures research

This tool works so well. I'm curious, is there any plan of adding support for Wolfenstein The New Order?
## Post #61
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-05-20T13:59:12+00:00
- Post Title: Re: Megatextures research

Finally found a problem that was causing the face to be too red. Fixed now.
## Post #62
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-06-07T21:15:06+00:00
- Post Title: Re: Megatextures research


## Post #63
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-06-15T17:41:37+00:00
- Post Title: Re: Megatextures research

Any updates on the Evil Within tool?  They just announced at E3 that The Evil Within 2 is coming out this year.  It put this fresh in my mind.
## Post #64
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-15T17:55:59+00:00
- Post Title: Re: Megatextures research

> Reply from volfin
>
> Any updates on the Evil Within tool?

we're working on it
## Post #65
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2017-06-16T13:12:21+00:00
- Post Title: Re: Megatextures research

hey daemon1 great work on cracking the megatextures case. does your tool support RAGE? didn't see anything in the previous posts about RAGE. it's id tech 5
## Post #66
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-16T15:09:08+00:00
- Post Title: Re: Megatextures research

it will probably support it after EW
## Post #67
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2017-06-25T05:37:44+00:00
- Post Title: Re: Megatextures research

any news about tew support?
## Post #68
- Username: spartan1096
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 17, 2017 12:20 pm
- Post datetime: 2017-06-25T07:01:38+00:00
- Post Title: Re: Megatextures research

Will it support Wolfenstein the Old Blood？
## Post #69
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-25T08:11:57+00:00
- Post Title: Re: Megatextures research

yes it will
but there's no estimate time
## Post #70
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-01T16:56:38+00:00
- Post Title: Re: Megatextures research

After a few days of struggling with Wolfenstein Old Blood special image types, now i can decode them.
## Post #71
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-07-01T21:44:37+00:00
- Post Title: Re: Megatextures research

I thought Old Blood was the same format as The New Order.  In the past I've been able to decode Old blood with the New Order exe and tool (M0xf's tool). But maybe it was just luck that the tool supported both formats.
## Post #72
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-02T07:33:28+00:00
- Post Title: Re: Megatextures research

> Reply from volfin
>
> I thought Old Blood was the same format as The New Order.

Yes, but I was talking about formats specific to both Wolfensteins. All this time I was unable to decode their normal maps. I started checking them only this week. I thought it was just a little tweak, but not.

Again, they had a lot of differences from standard HDP. I had to make changes in about 10 different places in HDP code to make it work.
## Post #73
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-02T10:35:53+00:00
- Post Title: Re: Megatextures research

Rage. Only diffuse HDP decodes. Normal and specular are different again.
## Post #74
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-15T14:07:39+00:00
- Post Title: Re: Megatextures research

EW progress. Animations are working. [https://youtu.be/84SQr3Rgcrc](https://youtu.be/84SQr3Rgcrc)
## Post #75
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-07-15T16:27:13+00:00
- Post Title: Re: Megatextures research

Oh you're going for the whole pie, Now I see why it's taking so long.  Very nice work!
## Post #76
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-15T17:17:39+00:00
- Post Title: Re: Megatextures research

> Reply from volfin
>
> Oh you're going for the whole pie, Now I see why it's taking so long.  Very nice work!

Thanks, but that's not the reason why it's taking long. We have our ways
## Post #77
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-07-16T02:27:14+00:00
- Post Title: Re: Megatextures research

> Reply from daemon1
>
> volfin wrote:Oh you're going for the whole pie, Now I see why it's taking so long.  Very nice work!Thanks, but that's not the reason why it's taking long. We have our waysWell, I`m a bit worried over how is this research going to be.
## Post #78
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-16T06:09:04+00:00
- Post Title: Re: Megatextures research

> Reply from AnonBaiter
>
> Well, I`m a bit worried over how is this research going to be.

What worries you?
## Post #79
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-07-17T18:40:53+00:00
- Post Title: Re: Megatextures research

> Reply from daemon1
>
> AnonBaiter wrote:Well, I`m a bit worried over how is this research going to be.What worries you?Different beliefs over how one should get a "game".
## Post #80
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-07-18T02:44:46+00:00
- Post Title: Re: Megatextures research

I don't think anyone cares how you get a game. Unless I missed something.
## Post #81
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-07-18T19:01:55+00:00
- Post Title: Re: Megatextures research

> Reply from volfin
>
> I don't think anyone cares how you get a game. Unless I missed something.Yeah, you're right. It's just paranoia on my end.

EDIT: Actually, you're wrong. There is a reason why I'm being this doubtful.

In case you didn't notice, to use Wraith you need to have obtained a purchased copy of the game through Steam. You can't use Wraith with a pirated copy of the game, and if you do so the tool decides to throw a temper tantrum about it. Apparently the author of the tool decided that Wraith is for people who buy games only. Yes I get it discussing pirated stuff is against the rules of this site but if only you people knew anything at all about how the gaming industry is currently headed then YOU WOULDN'T FUCK THE PIRATES OVER SINCE THEY'RE ALSO PART OF THE GAMING COMMUNITY!

Enjoy your paid mods, microtransactions, overpaid DLCs, DRMs, copy protection schemes, pre-paid schemes and other stuff that is dominating games that don't need it. I just want to do file format research, for fuck sake.
## Post #82
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-07-24T15:41:52+00:00
- Post Title: Re: Megatextures research

Nevermind about my previous post, it's just me rambling about stuff.
## Post #83
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-08-03T15:40:33+00:00
- Post Title: Re: Megatextures research

Evil Within tool is out.

[http://aviacreations.com/wraith/](http://aviacreations.com/wraith/)
## Post #84
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-08-03T17:38:32+00:00
- Post Title: Re: Megatextures research

Whoot!, looks amazing. I can't wait to try it out.
## Post #85
- Username: WPH93
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Feb 13, 2017 12:31 am
- Post datetime: 2017-08-06T15:23:13+00:00
- Post Title: Re: Megatextures research

> Reply from daemon1
>
> 

Evil Within tool is out.

http://aviacreations.com/wraith/
Hi，daemon1，I cannot open this tool.When I double click WraithLaura.exe,nothing happened.  What can I do?My system is Win10 X64 Family vision.
## Post #86
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-08-06T15:54:00+00:00
- Post Title: Re: Megatextures research

> Reply from WPH93
>
> Hi，daemon1，I cannot open this tool.When I double click WraithLaura.exe,nothing happened.  What can I do?My system is Win10 X64 Family vision.

check your system/app logs

also can be your security software is blocking it for some reason
## Post #87
- Username: WPH93
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Feb 13, 2017 12:31 am
- Post datetime: 2017-08-07T04:06:18+00:00
- Post Title: Re: Megatextures research

> Reply from daemon1
>
> WPH93 wrote:Hi，daemon1，I cannot open this tool.When I double click WraithLaura.exe,nothing happened.  What can I do?My system is Win10 X64 Family vision. 

check your system/app logs

also can be your security software is blocking it for some reason

Thanks，daemon1 ，it works very well now.   .
## Post #88
- Username: alexio614
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 03, 2016 10:13 pm
- Post datetime: 2017-08-26T12:06:31+00:00
- Post Title: Re: Megatextures research

Will this ever support id Tech 4 games? What comes to my mind is mostly Brink...
## Post #89
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-08-27T06:18:56+00:00
- Post Title: Re: Megatextures research

> Reply from alexio614
>
> Will this ever support id Tech 4 games? What comes to my mind is mostly Brink...
brink has an option to save textures. check this thread
## Post #90
- Username: alexio614
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 03, 2016 10:13 pm
- Post datetime: 2017-08-27T15:23:19+00:00
- Post Title: Re: Megatextures research

> Reply from daemon1
>
> alexio614 wrote:Will this ever support id Tech 4 games? What comes to my mind is mostly Brink...
brink has an option to save textures. check this thread

I saw the console command, but what about meshes and animations? Or am I missing something?
## Post #91
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-08-27T15:35:46+00:00
- Post Title: Re: Megatextures research

> Reply from alexio614
>
> but what about meshes and animations? Or am I missing something?

I don't know. If you sure there's no tool for it, I can support it someday.
## Post #92
- Username: alexio614
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 03, 2016 10:13 pm
- Post datetime: 2017-08-27T18:36:25+00:00
- Post Title: Re: Megatextures research

> Reply from daemon1
>
> alexio614 wrote:but what about meshes and animations? Or am I missing something?

I don't know. If you sure there's no tool for it, I can support it someday.

All of the threads from either Facepunch or here seem to stop at the megatexture problem, so I really hope you'll get to it in the future!
## Post #93
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-13T15:34:42+00:00
- Post Title: Re: Megatextures research

> Reply from alexio614
>
> All of the threads from either Facepunch or here seem to stop at the megatexture problem, so I really hope you'll get to it in the future!

WHAT??? I solved the Megatexture problem months ago. This thread is about this, and also my thread on facepunch.

update: getting Evil Within 2 megatextures
## Post #94
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-14T15:22:48+00:00
- Post Title: Re: Megatextures research


## Post #95
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-23T20:22:25+00:00
- Post Title: Re: Megatextures research

Wraith Laura tool for EW now supports both EW1 & EW2.

Same place: [http://aviacreations.com/wraith/](http://aviacreations.com/wraith/)#

Not all megatexture layers are extracted yet, but its planned in next versions.
## Post #96
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2018-01-18T19:18:40+00:00
- Post Title: Re: Megatextures research

> Reply from daemon1
>
> Wraith Laura tool for EW now supports both EW1 & EW2.

Same place: http://aviacreations.com/wraith/#

Not all megatexture layers are extracted yet, but its planned in next versions.

thank U！ these are great tools, keep going
## Post #97
- Username: SecretAgent2001
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Oct 18, 2016 11:18 am
- Post datetime: 2018-01-26T03:28:54+00:00
- Post Title: Re: Megatextures research

Any progress with WTNO and WTOB .pages texture extracting yet?
## Post #98
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-26T15:47:14+00:00
- Post Title: Re: Megatextures research

> Reply from SecretAgent2001
>
> Any progress with WTNO and WTOB .pages texture extracting yet?
i did tests, it all works, but had no time to implement it into the tool
## Post #99
- Username: SecretAgent2001
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Oct 18, 2016 11:18 am
- Post datetime: 2018-01-26T21:03:31+00:00
- Post Title: Re: Megatextures research

Well, since there are no other methods of extracting the .pages files (yes, I tried m0xf's tool), and you don't have time coding up the extraction capabilities into the tool, could I PM you a .pages file I'd like to extract instead?
## Post #100
- Username: calypsoup
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Sep 12, 2016 3:51 am
- Post datetime: 2018-07-26T19:58:50+00:00
- Post Title: Re: Megatextures research

is it possible to extract sounds like voices, bgms etc from evil within 2 ?
## Post #101
- Username: Koralan
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 10, 2019 10:28 pm
- Post datetime: 2019-01-16T14:39:02+00:00
- Post Title: Re: Megatextures research

> Reply from daemon1
>
> i did tests, it all works, but had no time to implement it into the tool

Hello. Can we hope to get Wolfenstein TNO and TOB .pages extractor?
## Post #102
- Username: Goldo Golderson
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 17, 2019 11:04 pm
- Post datetime: 2019-01-17T15:14:08+00:00
- Post Title: Re: Megatextures research

> Reply from Koralan
>
> daemon1 wrote:i did tests, it all works, but had no time to implement it into the tool

Hello. Can we hope to get Wolfenstein TNO and TOB .pages extractor?

Registered just to say - yeah, I'm also would very like to see such tool, and I think, this not only me, seen many folks who really dying for it.
## Post #103
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-17T15:59:22+00:00
- Post Title: Re: Megatextures research

i dont think there are many people who want these games
## Post #104
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2019-01-17T16:23:23+00:00
- Post Title: Re: Megatextures research

> Reply from Goldo Golderson
>
> Koralan wrote:daemon1 wrote:i did tests, it all works, but had no time to implement it into the tool

Hello. Can we hope to get Wolfenstein TNO and TOB .pages extractor?

Registered just to say - yeah, I'm also would very like to see such tool, and I think, this not only me, seen many folks who really dying for it.

Pretty sure WraithColossus already works with these. the formats aren't that different.
## Post #105
- Username: Koralan
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 10, 2019 10:28 pm
- Post datetime: 2019-01-17T19:08:18+00:00
- Post Title: Re: Megatextures research

> Pretty sure WraithColossus already works with these. the formats aren't that different.
It is a beautiful program for TNC, but for TNO and TOB... 
Unfortunately - no, it don't. The first thing I personally have done, before going on forum - tried to use it.
## Post #106
- Username: ajax1313
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 02, 2018 7:03 pm
- Post datetime: 2019-01-18T20:27:49+00:00
- Post Title: Re: Megatextures research

hi. i've searched every .resources archive for Wolfstein TNC, but it seems there are lot's of lower res textures ? Not sure how to extract higher textures for stuff ?
## Post #107
- Username: lolznoboz
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Nov 22, 2018 8:52 am
- Post datetime: 2019-07-26T03:09:55+00:00
- Post Title: Re: Megatextures research

> Reply from ajax1313 ↑Sat Jan 19, 2019 4:27 am at Sat Jan 19, 2019 4:27 am
>
> 
hi. i've searched every .resources archive for Wolfstein TNC, but it seems there are lot's of lower res textures ? Not sure how to extract higher textures for stuff ?
im pretty sure the game uses detail textures to make the textures look better
so is it possible to get those textures?

also when will there be a .pages extractor for both wtno and wtob
## Post #108
- Username: Koralan
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 10, 2019 10:28 pm
- Post datetime: 2019-07-29T10:06:32+00:00
- Post Title: Re: Megatextures research

We can only hope about such extractor.
## Post #109
- Username: lolznoboz
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Nov 22, 2018 8:52 am
- Post datetime: 2019-08-01T23:25:56+00:00
- Post Title: Re: Megatextures research

> Reply from Koralan ↑Mon Jul 29, 2019 6:06 pm at Mon Jul 29, 2019 6:06 pm
>
> 
We can only hope about such extractor.
i wonder why
## Post #110
- Username: lolznoboz
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Nov 22, 2018 8:52 am
- Post datetime: 2019-08-03T05:12:37+00:00
- Post Title: Re: Megatextures research

also i think someone that is able to extract the files should post a extracted folder of the textures because m0xfs tool doesnt work for most people
## Post #111
- Username: CloudyMosy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 02, 2020 2:03 am
- Post datetime: 2020-09-20T14:38:59+00:00
- Post Title: Re: Megatextures research

> Reply from daemon1 ↑Mon Apr 10, 2017 4:31 am at Mon Apr 10, 2017 4:31 am
>
> 
Hello everyone.

After I did lots of research in sound formats, archives, models and animations I finally decided to get to most complicated task I've heard of: Megatextures.

This is current state of research: Doom/Evil Within/Wolfenstein tools are available here: http://aviacreations.com/wraith/# 

And that's how it all started back in march'2017: after a couple of weeks I was able to reverse the modified version of HDP they used and decompress tiles. The devs improved the coding algorithm in compare to standard HDP. 

Now I see that tiles are actually in correct order inside of megatexture as expected. This is just a random set of tiles taken from the middle of Wolfenstein Old Blood .pages file. I combined them manually, wanted to check the result as soon as possible
Sorry for necro-ing, but just wanna ask that what's the status for the Wolfenstein The New Order extractor? Wolfenstein The New Colossus (Wraith Colossus) works nicely, but I've been waiting for such an extractor for Wolfenstein The New Order or more like Wraith New Order since 2017 but I wish you luck if you are working on it
## Post #112
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-09-20T14:42:53+00:00
- Post Title: Re: Megatextures research

> Reply from CloudyMosy ↑Sun Sep 20, 2020 10:38 pm at Sun Sep 20, 2020 10:38 pm
>
> 
Sorry for necro-ing, but just wanna ask that what's the status for the Wolfenstein The New Order extractor? Wolfenstein The New Colossus (Wraith Colossus) works nicely, but I've been waiting for such an extractor for Wolfenstein The New Order or more like Wraith New Order since 2017 but I wish you luck if you are working on it

Unfortunately, there were many games with megatextures, and i got tired of them, so Wolfenstein The New Order was never completed.
## Post #113
- Username: lolznoboz
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Nov 22, 2018 8:52 am
- Post datetime: 2020-09-23T04:02:03+00:00
- Post Title: Re: Megatextures research

> Reply from daemon1 ↑Sun Sep 20, 2020 10:42 pm at Sun Sep 20, 2020 10:42 pm
>
> 
CloudyMosy wrote: ↑Sun Sep 20, 2020 10:38 pm
Sorry for necro-ing, but just wanna ask that what's the status for the Wolfenstein The New Order extractor? Wolfenstein The New Colossus (Wraith Colossus) works nicely, but I've been waiting for such an extractor for Wolfenstein The New Order or more like Wraith New Order since 2017 but I wish you luck if you are working on it  


Unfortunately, there were many games with megatextures, and i got tired of them, so Wolfenstein The New Order was never completed.

yea someone is gonna need to post an entire folder with all of the textures in it since the m0xf tool dont work
## Post #114
- Username: Farrarie
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Mar 19, 2017 6:00 pm
- Post datetime: 2021-03-11T08:50:56+00:00
- Post Title: Re: Megatextures research

WraithRevenant dont extract normap maps from doom 2016, how can I get the normal maps ?
## Post #115
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-03-11T11:06:28+00:00
- Post Title: Re: Megatextures research

> Reply from Farrarie ↑Thu Mar 11, 2021 4:50 pm at Thu Mar 11, 2021 4:50 pm
>
> 
WraithRevenant dont extract normap maps from doom 2016, how can I get the normal maps ?
WraithRevenant must extract normap maps
## Post #116
- Username: Farrarie
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Mar 19, 2017 6:00 pm
- Post datetime: 2021-03-13T15:39:07+00:00
- Post Title: Re: Megatextures research

> Reply from daemon1 ↑Thu Mar 11, 2021 7:06 pm at Thu Mar 11, 2021 7:06 pm
>
> 
WraithRevenant must extract normap maps
It extract diffuse, spec and mask textures, but not normal maps sadly.
## Post #117
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-03-13T16:55:12+00:00
- Post Title: Re: Megatextures research

> Reply from Farrarie ↑Sat Mar 13, 2021 11:39 pm at Sat Mar 13, 2021 11:39 pm
>
> 
daemon1 wrote: ↑Thu Mar 11, 2021 7:06 pm
WraithRevenant must extract normap maps

It extract diffuse, spec and mask textures, but not normal maps sadly.
it extracts normap maps too. Check again, they must be there in some files or channels.
## Post #118
- Username: lolznoboz
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Nov 22, 2018 8:52 am
- Post datetime: 2022-01-09T19:59:00+00:00
- Post Title: Re: Megatextures research

> Reply from Farrarie ↑Thu Mar 11, 2021 4:50 pm at Thu Mar 11, 2021 4:50 pm
>
> 
WraithRevenant dont extract normap maps from doom 2016, how can I get the normal maps ?

Normalmap is in the alpha channel of the diffuse and specular textures

You have to combine them, the specular's alpha as the green channel, and the diffuse's alpha as the red channel
## Post #119
- Username: Phobos90
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 22, 2018 2:57 pm
- Post datetime: 2022-07-20T06:25:24+00:00
- Post Title: Re: Megatextures research

Hello!

I've been the whole day scouting awesome Xentax for every piece of reference to RAGE and thanks to that I managed to get .resource extracted and have models in usable formats for characters and weapons. 

The missing piece of the puzzle is textures, and reading this thread was very exiting for the possibility that the tool reaches RAGE, I'm sad to read it ended development before that.


Is there any uplifting info regarding being able to access RAGE's textures or should I drop this venture for now?
## Post #120
- Username: mmmniple
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 30, 2020 7:13 pm
- Post datetime: 2022-10-17T10:24:28+00:00
- Post Title: Re: Megatextures research

Hello , i dont know if this can help but they are a unity pluggin which has also the source code included called "AmplifyTextyure2" which is used for creating megatextures on unity games. One example is the game Disco Elyseum backgrounds.

they are a trial version you can find here 


[https://amplify.pt/amplify-texture-2-pu ... ent-trial/](https://amplify.pt/amplify-texture-2-public-development-trial/)

[http://amplify.pt/wp-content/download/A ... itypackage](http://amplify.pt/wp-content/download/AmplifyTextureTrial.unitypackage)

i hope this can help
