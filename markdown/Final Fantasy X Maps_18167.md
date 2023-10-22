## Post #1
- Username: Pintozoz
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 02, 2018 3:13 am
- Post datetime: 2018-06-01T11:26:06+00:00
- Post Title: Final Fantasy X Maps

Hey everyone !

I'm currently working on this big musical project based on FFX and for the video I thought it'd be really cool if I could somehow create "exclusive" visuals which look like they come directly from the game 
And for that my idea is to rebuild entire maps from the game using the original files.

I've managed to extract some .smd and all of the textures thanks to various techniques found on this board, but one crucial thing is missing, that is the UV maps !
Without them these are just giant, very tedious puzzles to solve and so I was wondering if there was any way to get them ?

Any help is welcome !

Having a camera wander through Beside Island would be especially cool for example :

[](https://postimg.cc/image/9j69ygh47/)

[](https://postimg.cc/image/4fk27ip87/) [](https://postimg.cc/image/67d12fgav/) [](https://postimg.cc/image/d2s7o9c47/) [](https://postimg.cc/image/6p34kzzif/)
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-01T14:24:06+00:00
- Post Title: Final Fantasy X Maps

From which FFX version are you extracting the models? From the original PS2 version or from the remaster? I think FFX is available on 4-5 platforms now 

I haven't used it myself, but daemon1's tool should be able to extract the models with UVs from the pc remaster of the game : [viewtopic.php?f=16&t=16930](http://forum.xentax.com/viewtopic.php?f=16&t=16930)
## Post #3
- Username: Pintozoz
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 02, 2018 3:13 am
- Post datetime: 2018-06-01T15:14:14+00:00
- Post Title: Final Fantasy X Maps

These are from the PC version !
And I actually used daemon1's tool to extract them ^^
But sadly they don't seem to export UVs for the maps
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-01T15:45:48+00:00
- Post Title: Final Fantasy X Maps

> Reply from Pintozoz
>
> 
But sadly they don't seem to export UVs for the maps
Can you post some sample game files then?
## Post #5
- Username: Pintozoz
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 02, 2018 3:13 am
- Post datetime: 2018-06-01T16:32:26+00:00
- Post Title: Final Fantasy X Maps

Sure !
Here's Beside Island : [http://www.mediafire.com/file/6pvhu0acp ... Island.zip](http://www.mediafire.com/file/6pvhu0acpnwecr9/Besaid%20Island.zip)
It's in several formats ( .blend, .dae and .smd ) plus the textures and a screen of what it should look like !
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-01T16:55:13+00:00
- Post Title: Final Fantasy X Maps

> Reply from Pintozoz
>
> 
It's in several formats ( .blend, .dae and .smd ) plus the textures and a screen of what it should look like !
I meant the original file from the game, probably with the "dae.phyre" extension or something.
## Post #7
- Username: Pintozoz
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 02, 2018 3:13 am
- Post datetime: 2018-06-01T17:22:54+00:00
- Post Title: Final Fantasy X Maps

Oh yeah ! Here you go : [http://www.mediafire.com/file/a477v4ntd ... bsvr00.zip](http://www.mediafire.com/file/a477v4ntdreo6b3/bsvr00.zip)
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-01T18:40:13+00:00
- Post Title: Final Fantasy X Maps

There seems to be nothing wrong with daemon1's tool. I am reading exactly the same data for UVs.

The uvs are not wrong, but they are drawn on top of each other. I have checked the maps from another Phyre game I worked on (Secret of Mana), and the uvs are also like that.



I think you can split the mesh into smaller parts to solve the problem.
## Post #9
- Username: Pintozoz
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 02, 2018 3:13 am
- Post datetime: 2018-06-02T00:29:54+00:00
- Post Title: Final Fantasy X Maps

Oh yeah you are right, UVs are OK !
The problem is that none of the textures are linked, and that means dozens and dozens of textures to relink for some of these maps... which is ilke one hell of a puzzle to solve ^^
## Post #10
- Username: Pintozoz
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 02, 2018 3:13 am
- Post datetime: 2018-06-04T17:29:42+00:00
- Post Title: Final Fantasy X Maps

> Reply from akderebur
>
> There seems to be nothing wrong with daemon1's tool. I am reading exactly the same data for UVs.

The uvs are not wrong, but they are drawn on top of each other. I have checked the maps from another Phyre game I worked on (Secret of Mana), and the uvs are also like that.

Did you have any issues texture-wise with SoM ?
I really wonder if there's a way to get those FFX textures linked cause I'd like to use several of these maps and it would save me a lot of time...
## Post #11
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-04T17:46:27+00:00
- Post Title: Final Fantasy X Maps

> Reply from Pintozoz
>
> 
Did you have any issues texture-wise with SoM ?
I really wonder if there's a way to get those FFX textures linked cause I'd like to use several of these maps and it would save me a lot of time...
No issues with the textures, but I applied them manually. There is probably a table that links meshes to materials, and materials to textures, but I haven't researched that far. I am mainly interested in character models, and applying them manually isn't too much of a problem.

I can see how it is a huge problem for the maps. With that many meshes, it would take some time.
## Post #12
- Username: simlucrato
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 24, 2016 10:12 pm
- Post datetime: 2018-07-29T11:17:11+00:00
- Post Title: Final Fantasy X Maps

Hello , did you find a solution to get UV Maps i'm quite tired to link each texture randomly until it works ^^
## Post #13
- Username: simlucrato
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 24, 2016 10:12 pm
- Post datetime: 2018-08-06T12:53:55+00:00
- Post Title: Final Fantasy X Maps

Managed to get maps with uv's and textures !  here is besaid temple if you want : [http://www.mediafire.com/file/eaxyy43zb ... Temple.rar](http://www.mediafire.com/file/eaxyy43zb7z8zhw/Besaid+Temple.rar)
## Post #14
- Username: Bazza
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 31, 2019 1:15 pm
- Post datetime: 2019-02-01T01:46:30+00:00
- Post Title: Final Fantasy X Maps

> Reply from simlucrato
>
> Managed to get maps with uv's and textures !  here is besaid temple if you want : http://www.mediafire.com/file/eaxyy43zb ... Temple.rar
Excellent!

Here's what it looks like, assets as they came, with a better camera/HDR/postFX system in place.  


If you're able to release some other areas of Besaid, I'd be more than happy to re-render them!
[Besaid_test_baseline_small.jpg](https://xentaxbackup.github.io/file/15627_Besaid_test_baseline_small.jpg)
## Post #15
- Username: Bazza
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 31, 2019 1:15 pm
- Post datetime: 2019-02-05T04:21:28+00:00
- Post Title: Final Fantasy X Maps

Changed a few things, trying out a new post tonemapper, and fixed the double-sided tree leaves.



Besaid_test_baseline2_small.jpg (87.61 KiB) Viewed 263 times



Still a few problems, mostly to do with normals.  The ground I think wasn't lit in realtime, and with baked static lightmapping normals weren't a concern, likely the same with the huts/houses.  As long as the edges matched up at the seams with the lightmaps, you'd never notice.

And honestly, the trees need to be replaced.  They're always the weakest link on older titles, and have none of the data or detail a modern system can use.
## Post #16
- Username: Bazza
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 31, 2019 1:15 pm
- Post datetime: 2019-03-15T04:36:01+00:00
- Post Title: Re: Final Fantasy X Maps

Allowed myself new trees, but kept the original grass textures (albeit with new quad placement, as GPU compute particles with the new Unity VFX system).

Added new (freely available, UAS) palm trees and bushes with custom shader for wind movement / translucence
Added custom shader for flags/banners, with wind movement / translucence
Moved from old quad-based terrain to splatmap terrain system (saves draw calls, simplifies everything)
Slight adjustments to tonemapping settings.

Enjoy!



Entrance_LQ.jpg (181.24 KiB) Viewed 212 times



EDIT:  This will be it for my Besaid Temple.  I've got a few more screenshots at higher res but I'm saving them for later use.  I can't really go much further without changing the geometry; weak points are the houses, props, etc.  Grass sprites are also a major weak point, they were authored for a very archaic type of use.
## Post #17
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-03-15T09:20:42+00:00
- Post Title: Re: Final Fantasy X Maps

> Reply from Bazza ↑Fri Mar 15, 2019 12:36 pm at Fri Mar 15, 2019 12:36 pm
>
> 
Allowed myself new trees, but kept the original grass textures (albeit with new quad placement, as GPU compute particles with the new Unity VFX system).

Added new (freely available, UAS) palm trees and bushes with custom shader for wind movement / translucence
Added custom shader for flags/banners, with wind movement / translucence
Moved from old quad-based terrain to splatmap terrain system (saves draw calls, simplifies everything)
Slight adjustments to tonemapping settings.

Enjoy!

Entrance_LQ.jpg

EDIT:  This will be it for my Besaid Temple.  I've got a few more screenshots at higher res but I'm saving them for later use.  I can't really go much further without changing the geometry; weak points are the houses, props, etc.  Grass sprites are also a major weak point, they were authored for a very archaic type of use.

Blender hates me because I barely can do that. I can just import a simple model & export it.
And 3D Max have not being too good for render either way.


Now, about the background models:

I kind recommend use NinjaRipper, as it does extract the whole scene with each model with the accurate texture route.
The only drag back, it is that you will need to put it on Forced the NinjaRipper and press it around 4-20 times in each background for get a 100% background models (and 2000+ pieces).
## Post #18
- Username: Bazza
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 31, 2019 1:15 pm
- Post datetime: 2019-03-15T09:25:52+00:00
- Post Title: Re: Final Fantasy X Maps

I have the background models, but they are barely acceptable at a PS2 level.  Honestly they're not really usable, so I changed them.

There is actually the very background trees in my scene, but I moved them further back from the level so they're almost silhouettes in the fog
## Post #19
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-03-26T21:31:40+00:00
- Post Title: Re: Final Fantasy X Maps

> Reply from Bazza ↑Fri Mar 15, 2019 5:25 pm at Fri Mar 15, 2019 5:25 pm
>
> 
I have the background models, but they are barely acceptable at a PS2 level.  Honestly they're not really usable, so I changed them.

There is actually the very background trees in my scene, but I moved them further back from the level so they're almost silhouettes in the fog

I was more talking about the light effect for make it look so realistic and that the texture blend correctly with the lights.
I've try that on 3D Max and I always get horrible result, specially on the texture that they end changing of color accord to the light its used (Daylight system on Mental.Ray. I've try with Vray, but it gives the same result).
## Post #20
- Username: Nexus Elite
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 16, 2011 1:36 am
- Post datetime: 2019-05-22T03:27:59+00:00
- Post Title: Re: Final Fantasy X Maps

was there anyways to extract the maps from the HD remaster?
## Post #21
- Username: Bazza
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 31, 2019 1:15 pm
- Post datetime: 2019-05-22T03:58:09+00:00
- Post Title: Re: Final Fantasy X Maps

> Reply from Darkhowlings ↑Wed Mar 27, 2019 5:31 am at Wed Mar 27, 2019 5:31 am
>
> 
Bazza wrote: ↑Fri Mar 15, 2019 5:25 pm
I have the background models, but they are barely acceptable at a PS2 level.  Honestly they're not really usable, so I changed them.

There is actually the very background trees in my scene, but I moved them further back from the level so they're almost silhouettes in the fog  


I was more talking about the light effect for make it look so realistic and that the texture blend correctly with the lights.
I've try that on 3D Max and I always get horrible result, specially on the texture that they end changing of color accord to the light its used (Daylight system on Mental.Ray. I've try with Vray, but it gives the same result).

The lighting is in Unity (2018, HDRP).  It uses 'baked realtime' bounced lighting, light probes for small objects (like pots and baskets, etc) and I did some adjustment to the skybox levels so it functions (kinda) like a HDRI for good ambient lighting.  

So it's a bit of work to set up, but it got me nice and soft ambient light, and can actually with with a time-of-day system!
## Post #22
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-05-22T14:00:07+00:00
- Post Title: Re: Final Fantasy X Maps

> Reply from Bazza ↑Fri Mar 15, 2019 5:25 pm at Fri Mar 15, 2019 5:25 pm
>
> 
The lighting is in Unity (2018, HDRP).  It uses 'baked realtime' bounced lighting, light probes for small objects (like pots and baskets, etc) and I did some adjustment to the skybox levels so it functions (kinda) like a HDRI for good ambient lighting.  

So it's a bit of work to set up, but it got me nice and soft ambient light, and can actually with with a time-of-day system!

Ok, you just lost me.
To really know if its 3D max or Blender what are you talking right now
## Post #23
- Username: Bazza
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 31, 2019 1:15 pm
- Post datetime: 2019-05-23T02:58:23+00:00
- Post Title: Re: Final Fantasy X Maps

> Reply from Darkhowlings ↑Wed May 22, 2019 10:00 pm at Wed May 22, 2019 10:00 pm
>
> 
Bazza wrote: ↑Fri Mar 15, 2019 5:25 pm
The lighting is in Unity (2018, HDRP).  It uses 'baked realtime' bounced lighting, light probes for small objects (like pots and baskets, etc) and I did some adjustment to the skybox levels so it functions (kinda) like a HDRI for good ambient lighting.  

So it's a bit of work to set up, but it got me nice and soft ambient light, and can actually with with a time-of-day system!


Ok, you just lost me.
To really know if its 3D max or Blender what are you talking right now

It's not 3DS Max or Blender.

I'm using Unity3d, Version 2018.3, with the High-Definition-Render-Pipeline.
## Post #24
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-05-23T14:24:51+00:00
- Post Title: Re: Final Fantasy X Maps

> Reply from Bazza ↑Fri Mar 15, 2019 5:25 pm at Fri Mar 15, 2019 5:25 pm
>
> ]

Ok, you just lost me.
To really know if its 3D max or Blender what are you talking right now

It's not 3DS Max or Blender.

I'm using Unity3d, Version 2018.3, with the High-Definition-Render-Pipeline.
[/quote]

I see, I will give a try.
And thanks for respond!
## Post #25
- Username: momentai1018
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 17, 2019 9:20 am
- Post datetime: 2019-09-17T04:35:23+00:00
- Post Title: Re: Final Fantasy X Maps

I'm currently a noob at this stuff, but I'm learning and right now I'm using Roblox Studio to try and create an online blitzball. I'm currently having to make all my meshes, but I saw this and wanted to know if theres a way for me to use ffx in game map and structure models to use as mesh for my game?
## Post #26
- Username: Weignerm
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 26, 2019 2:44 am
- Post datetime: 2021-08-20T16:09:25+00:00
- Post Title: Re: Final Fantasy X Maps

I'm making a remake of Final Fantasy 10 in unreal engine 5. I'm having issues with getting the Textures though. can any of you help?
