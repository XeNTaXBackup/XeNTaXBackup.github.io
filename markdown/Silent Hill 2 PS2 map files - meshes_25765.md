## Post #1
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2022-09-02T18:21:50+00:00
- Post Title: Silent Hill 2 PS2 map files - meshes

Hi guys, I was trying to extract meshes from these maps, I can get vertices and UV's but no faces. It seems like all these are in the same block but probably faces are auto generated because I can't find them(I really don't know..)

This is my research:




This map has 3 meshes, are parts of the floor. Here is the sample:
[https://www.mediafire.com/file/xzlkup8v ... t.rar/file](https://www.mediafire.com/file/xzlkup8vfm3878x/SH2PS2MapFormat.rar/file)

Thanks!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-02T19:29:01+00:00
- Post Title: Silent Hill 2 PS2 map files - meshes

Looks like a point cloud skinner couldn't help too much:
.



PointCloudSkinner_SH2.jpg (131.51 KiB) Viewed 479 times
## Post #3
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2022-09-02T22:02:35+00:00
- Post Title: Silent Hill 2 PS2 map files - meshes

> Reply from shakotay2 ↑Sat Sep 03, 2022 3:29 am at Sat Sep 03, 2022 3:29 am
>
> 
Looks like a point cloud skinner couldn't help too much:
.
PointCloudSkinner_SH2.jpg

Interesting.. Is this all three meshes together or just one?
## Post #4
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2022-09-03T01:59:40+00:00
- Post Title: Silent Hill 2 PS2 map files - meshes

There is a tool to extract PS2 meshes, maps, animations.

[https://github.com/Murugo/Misc-Game-Research](https://github.com/Murugo/Misc-Game-Research)
need compilling through
## Post #5
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2022-09-03T02:37:51+00:00
- Post Title: Silent Hill 2 PS2 map files - meshes

> Reply from fullinu ↑Sat Sep 03, 2022 9:59 am at Sat Sep 03, 2022 9:59 am
>
> 
There is a tool to extract PS2 meshes, maps, animations.

https://github.com/Murugo/Misc-Game-Research
need compilling through

Yeah but that only works with SH3 maps. SH2 maps are very similar so maybe in "import_map.py" we can check how faces work.
## Post #6
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2022-09-05T10:52:46+00:00
- Post Title: Silent Hill 2 PS2 map files - meshes

> Reply from roocker666 ↑Sat Sep 03, 2022 10:37 am at Sat Sep 03, 2022 10:37 am
>
> 
Yeah but that only works with SH3 maps. SH2 maps are very similar so maybe in "import_map.py" we can check how faces work.
well, tbh, I was not able to compile tool from github either, so it failing on import tasks
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-05T13:26:09+00:00
- Post Title: Silent Hill 2 PS2 map files - meshes

> Reply from roocker666 ↑Sat Sep 03, 2022 10:37 am at Sat Sep 03, 2022 10:37 am
>
> Yeah but that only works with SH3 maps. SH2 maps are very similarIf so it could be helpful to have an SH3 map sample to understand how import_map.py from the io_sh2_sh3 addon works.
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-09-05T14:44:08+00:00
- Post Title: Silent Hill 2 PS2 map files - meshes

> Reply from roocker666 ↑Sat Sep 03, 2022 2:21 am at Sat Sep 03, 2022 2:21 am
>
> 
This map has 3 meshes. Thanks!
[gitHub link](https://github.com/Murugo/Misc-Game-Research/blob/main/PS2/Silent%20Hill%202%2B3/Blender/addons/io_sh2_sh3/import_map.py)
seems to work  

[fmt_map.zip](https://xentaxbackup.github.io/file/22763_fmt_map.zip)
## Post #9
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2022-09-06T07:42:15+00:00
- Post Title: Silent Hill 2 PS2 map files - meshes

> Reply from Durik256 ↑Mon Sep 05, 2022 10:44 pm at Mon Sep 05, 2022 10:44 pm
>
> 
roocker666 wrote: ↑Sat Sep 03, 2022 2:21 am
This map has 3 meshes. Thanks!

gitHub link
seems to work

Wow!, this is great man. Thank you so much!
## Post #10
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2022-10-09T19:10:55+00:00
- Post Title: Silent Hill 2 PS2 map files - meshes

Does this SH2 script works for all map files? It keeps crashing on 99% of files I try to open
## Post #11
- Username: allanrichmond
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 06, 2023 10:33 am
- Post datetime: 2023-06-06T02:36:31+00:00
- Post Title: Silent Hill 2 PS2 map files - meshes

> Reply from fullinu ↑Sat Sep 03, 2022 9:59 am at Sat Sep 03, 2022 9:59 am
>
> 
There is a tool to extract PS2 meshes, maps, animations.

https://github.com/Murugo/Misc-Game-Research/drift hunters
need compilling through

But only SH3 maps function. Faces may work in "import_map.py" as SH2 maps are comparable.
## Post #12
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-07-17T00:38:03+00:00
- Post Title: Silent Hill 2 PS2 map files - meshes

Hi, sorry for late reply. We have been working on some Noesis scripts for SH2 PS2, SH4 PC and SH4 PS2.

Noesis scripts for SH2/SH4:
[https://github.com/Sparagas/Silent-Hill ... %20Scripts](https://github.com/Sparagas/Silent-Hill/tree/main/Noesis%20-%20Python%20Scripts)

These scripts work with meshes only, So no textures yet... Maybe soon
About SH4 scripts don't use both at the same time, use one or the other because SH4 PS2/PC files are very similar but no the same.
In SH2 PC one map is just one file but in SH2 PS2 one map is made by 1 or more files(between 1 and 4 maybe) so don't forget that.

And here some 010 binary templates about map file formats and more:
[https://github.com/Sparagas/Silent-Hill ... 0Templates](https://github.com/Sparagas/Silent-Hill/tree/main/010%20Editor%20-%20Binary%20Templates)

Special thanks to Durik256, Sparagas, Allen and Murugo.
## Post #13
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2023-07-18T10:57:40+00:00
- Post Title: Silent Hill 2 PS2 map files - meshes

> Reply from roocker666 ↑Mon Jul 17, 2023 8:38 am at Mon Jul 17, 2023 8:38 am
>
> 
Hi, sorry for late reply. We have been working on some Noesis scripts for SH2 PS2, SH4 PC and SH4 PS2.

wow, thank you! This is very cool.
Big props for your command for supporting PS2 versions of the games - I have heard somewhere, that during PC porting some mistakes were made, so PS2 versions have definite models
Vertex colors support very nice



Снимок экрана (1009).png (172.7 KiB) Viewed 224 times


Can we that hope Silent Hill 3 PS2 also will get Noesis script one day?
## Post #14
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-07-19T19:23:08+00:00
- Post Title: Silent Hill 2 PS2 map files - meshes

> Reply from fullinu ↑Tue Jul 18, 2023 6:57 pm at Tue Jul 18, 2023 6:57 pm
>
> 
Can we that hope Silent Hill 3 PS2 also will get Noesis script one day?

SH3 PS2 maps are very similar to SH2, meshes have the same format(vertices & Uvs) but there are some differences in pointers to mesh groups and mesh headers. If we understand those parts then we could create a plugin for Noesis.

I think Murugo already reversed SH3 map file format in "inport_map.py" so that helps a lot. We need to analyze and understand that file.
## Post #15
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2023-07-20T20:30:51+00:00
- Post Title: Silent Hill 2 PS2 map files - meshes

> Reply from fullinu ↑Tue Jul 18, 2023 6:57 pm at Tue Jul 18, 2023 6:57 pm
>
> 
roocker666 wrote: ↑Mon Jul 17, 2023 8:38 am
Hi, sorry for late reply. We have been working on some Noesis scripts for SH2 PS2, SH4 PC and SH4 PS2.

wow, thank you! This is very cool.
Big props for your command for supporting PS2 versions of the games - I have heard somewhere, that during PC porting some mistakes were made, so PS2 versions have definite models
Vertex colors support very nice
Снимок экрана (1009).png
Can we that hope Silent Hill 3 PS2 also will get Noesis script one day?

Faces orientation is not implemented fully yet, so press the face culling button.
Also, I just made Documentation for SH3 PS2 ver, and also HD ver (it needs work. Headers are in Big Endian, but vertices attributes are in Little Endian).
You can check it and use it with 010 Editor:
[https://github.com/Sparagas/Silent-Hill ... )%20map.bt](https://github.com/Sparagas/Silent-Hill/blob/main/010%20Editor%20-%20Binary%20Templates/SH3%20%28PS2%29%20map.bt)
## Post #16
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2023-07-25T18:16:46+00:00
- Post Title: Re: Silent Hill 2 PS2 map files - meshes

It is a little bit buggy, but you can test it:
[https://github.com/Sparagas/Silent-Hill ... %20Plugins](https://github.com/Sparagas/Silent-Hill/tree/main/Noesis%20-%20Python%20Plugins)
## Post #17
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2023-07-27T12:06:53+00:00
- Post Title: Re: Silent Hill 2 PS2 map files - meshes

> Reply from Sparagas ↑Wed Jul 26, 2023 2:16 am at Wed Jul 26, 2023 2:16 am
>
> 
It is a little bit buggy, but you can test it:
https://github.com/Sparagas/Silent-Hill ... %20Plugins

New script working for Silent Hill 3 PS2!



Снимок экрана (1016).png (141.3 KiB) Viewed 301 times
## Post #18
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2023-07-27T21:02:10+00:00
- Post Title: Re: Silent Hill 2 PS2 map files - meshes

Your welcome 
Don't forget to check GitHub for updates and more goodies
## Post #19
- Username: Alvin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 18, 2023 5:55 pm
- Post datetime: 2023-07-30T09:00:00+00:00
- Post Title: Re: Silent Hill 2 PS2 map files - meshes

This is very exciting and an awesome achievement!
So if I'm not mistaken then, Silent Hill 3 has pre-baked lighting for all the map files in vertex color. Then there are real lights that only interact with the characters. And then there's one single light from Heather that adds onto the vertex color of the map, to remove darkness from the vertex colors.

I have two very important suggestions to make. In comparison with Murugo's importer, the scaling is incredibly small. For data transfer to work on my current extractions, to transfer the colors, I need to have similar scaling and position. This wouldn't be an issue for me if it wasn't such an odd decimal scaling factor. The rotation is also completely upside down. In order for correct rotation in Blender, I need to set manual orientation to -Z Forward and -Y Up.

I'm trying to figure out the scaling factor difference. It's scaling it 1000 units (max) up. And then around 32.76. But still not quite. Like I said, an odd decimal number. It's about 98% z-fighting now.
## Post #20
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2023-07-30T14:09:54+00:00
- Post Title: Re: Silent Hill 2 PS2 map files - meshes

Not quite. There are still shadows for static objects (Boot up the game and the first scene in Amusement Park, there are grates, that have shadows). Also, I think vertex colors still work if no flashlight is on.
About the scale - I used the original scale of a game. Maybe Noesis interprets it differently than Blender.
Games use face culling on, and Blender uses face culling off by default. That's why you have Z-fighting. Try to turn it on in Blender.

Yes, the orientation is not correct, because I also used original data from PS2, and for some reason in that game up is -Z and not +Z (and in Noesis it is the opposite, as in the majority of other software/games).
I will correct this in the future.
## Post #21
- Username: Alvin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 18, 2023 5:55 pm
- Post datetime: 2023-07-30T15:03:07+00:00
- Post Title: Re: Silent Hill 2 PS2 map files - meshes

> Not quite. There are still shadows for static objects (Boot up the game and the first scene in Amusement Park, there are grates, that have shadows). Also, I think vertex colors still work if no flashlight is on.
Yes it remains active if there's no light from Heather at all. But maybe it does erase/lighten-up the darkness of the vertex colors in the shader itself. I'm not sure it does this but it remains a very interesting subject.
The vertex color certainly gives this extra 'quality' to the environments. Making them pop even more. Most noticable so far, in the intro mall sequence with Heather on the phone with her dad and meeting Douglas, the increasement of lightness coming from the line strips of light on the ceiling.
And the shadowing it creates at the end of the hallway near the restrooms.

> About the scale - I used the original scale of a game. Maybe Noesis interprets it differently than Blender.
Oh wow. That's pretty cool. They originally used a very small scale to work with then.  

> Games use face culling on, and Blender uses face culling off by default. That's why you have Z-fighting. Try to turn it on in Blender.
No, sorry for confusing you. I want z-fighting, for a very specific reason. I want my map export from Murugo's tool to perfectly line up with your export from Noesis. It's so I can do a data transfer for the vertex color. Basically projecting them onto my previous export. After succeeding with that I will remove your Noesis export from the scene again.

> Yes, the orientation is not correct, because I also used original data from PS2, and for some reason in that game up is -Z and not +Z (and in Noesis it is the opposite, as in the majority of other software/games).
Oh, it's no problem really. You should keep it as is if this is how the game originally is.
## Post #22
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2023-07-30T18:21:03+00:00
- Post Title: Re: Silent Hill 2 PS2 map files - meshes

A lot of games (at least in the past) used vertex colors. So it can compensate for low-resolution textures.
My tool exports also UV texture coordinates. So maybe it will be easier for you just to import mine mesh and apply textures from Murugo's exported models?
## Post #23
- Username: Alvin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 18, 2023 5:55 pm
- Post datetime: 2023-07-30T18:49:09+00:00
- Post Title: Re: Silent Hill 2 PS2 map files - meshes

> A lot of games (at least in the past) used vertex colors. So it can compensate for low-resolution textures.
Yeah, Oot3D and Majora's Mask 3D by Grezzo has them too. Vertex color is a very underutilized powerful tool.
Nowadays more often used for shader tricks I presume. Wind influence on tree meshes, texture splatting on terrain ect..
I know what you mean with old games. But I never found Silent Hill 3 to be low-res. 512x512 and sometimes even 512x1024. (<- rare cases)

I wish I could just use your exports. Unfortunately I already got around 50% of the maps extracted.
And some even have a custom armature set up for them. So redoing them would be a huge hassle.
Then again, if I were to use your extracted versions, I would still need to know the correct scale factor in comparison to my previous exports (also in relation to the character models). I've tried many of scale factors by now:
327.67, 327.726, 327.8
But none of them are quire right to get the vertex colors to transfer 100% correctly.
## Post #24
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2023-07-30T19:27:13+00:00
- Post Title: Re: Silent Hill 2 PS2 map files - meshes

In original PS2 vertices are in int16 (short integer).
So it values goes from -32768 to +32767. It can't get bigger.
(It seems I could have made some bug with scaling after all).

The intended real value is one tile square - 1 meter.
Look in models in wireframe. Best places are flat ground. You will see squares - they are 1 meter.

Try scaling it by the power of 2 (2 8 16 32 etc. Or 1/2 1/4 1/8 etc.)
## Post #25
- Username: riverence
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 05, 2022 11:22 am
- Post datetime: 2023-07-31T19:45:45+00:00
- Post Title: Re: Silent Hill 2 PS2 map files - meshes

yo! there's currently a map editor for the PC port of SH2 that has the capability of exporting custom, edited meshes to the .map format as well as reading existing .map files (with full texture assignments + separate objects intact) and extracting them to the .OBJ file format. i know it's a tiny bit off topic as this thread relates to the PS2 map files but this editor works very well so far and is being consistently updated c:

[https://github.com/pmttavara/ph2](https://github.com/pmttavara/ph2)
## Post #26
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2023-07-31T19:47:27+00:00
- Post Title: Re: Silent Hill 2 PS2 map files - meshes

Wow thanks!
## Post #27
- Username: Alvin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 18, 2023 5:55 pm
- Post datetime: 2023-08-01T09:46:24+00:00
- Post Title: Re: Silent Hill 2 PS2 map files - meshes

I've decided using your tool instead and redo some, if not all the environments once more.
The vertex color is absolutely worth the difference. I just wanted to mention that the uv's are flipped vertically.
Should be an easy fix though, since none of Sh3's uv's go out of the uv bounds. I can simply select all geometry and flip it without a problem.
Here's how the motel scene looks like now with the vertex colors. Still need to fine-tune the dynamic lights.
[Motel.png](https://xentaxbackup.github.io/file/24148_Motel.png)
## Post #28
- Username: Sparagas
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Feb 19, 2016 2:57 am
- Post datetime: 2023-08-01T19:42:12+00:00
- Post Title: Re: Silent Hill 2 PS2 map files - meshes

Looks gorgeous! What program is this?
## Post #29
- Username: Alvin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 18, 2023 5:55 pm
- Post datetime: 2023-08-01T20:07:29+00:00
- Post Title: Re: Silent Hill 2 PS2 map files - meshes

Thanks. I'm using Unity 2019.4 with custom shaders and rendering set to linear color space.
Here's one more:
## Post #30
- Username: Alvin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 18, 2023 5:55 pm
- Post datetime: 2023-08-13T16:13:00+00:00
- Post Title: Re: Silent Hill 2 PS2 map files - meshes

I've gone through all of the MR ones at least. It takes quite some time and effort in getting them one by one.
But I'm beginning to document them all.

MR - Central Square Shopping Centre REAL
_____________________________________________________
mr1f	[1]					
mr2e	[1]										
mr2f	[1]										
mrdf	[1]										
mre1	[1]
mree	[1]						
mref	[1]											
mrfd	[1]
mrfe	[1]											
mrff	[1]											
mr1e	[1]
mr11	[1]
mr12	[1]
mr21	[1]
mr22	[1]
mrd1	[1]
mre2	[1]
mrf1	[1]
mrf2	[1]

	MU - Central Square Shopping Centre OTHERWORLD
_____________________________________________________
mu1d	[0]
mu2d	[?] All Gray except for the elevator's ceiling lights.)
mu2e	[1]
mudf	[0]
mue1	[0]
muee	[-] Not Applicable
muef	[1]
mufd	[0]
mufe	[0]

mu11	[0]
mu12	[0]
mu13	[0]
mu21	[0]
mu22	[0]
mu31	[0]
mu32	[0]
mud1	[0]
mue2	[0]
muf1	[0]
muf2	[0]
muf3	[0]
muff	[0]

mu1e	[0]
mu1f	[1]
mu2f	[1]
mu3f	[1]

	TR - Subway Station [Pla 7 maps, Sta 7 maps, Tra 11 maps]
_____________________________________________________


tre1	[1]
tre2	[0]
tree	[0]
tref	[0]
trf2	[1]
trfe	[1]
trff	[0]

tr1e	[0]
tr1f	[0]
tr2e	[0]
tr2f	[-] Not Applicable
tr11	[1]
tr21	[1]
trf1	[0]

tr1d	[-] Not Applicable
tr3f	[-] Not Applicable
tr13	[-] Not Applicable
tr31	[-] Not Applicable
trd1	[0]
trdd	[-] Not Applicable
trdf	[-] Not Applicable
trf3	[-] Not Applicable
trfd	[0]

	US - Underpass	[Lower 12 maps, Upper 16 maps]
_____________________________________________________
us1d	[0]
us12	[-] Not Applicable
us13	[-] Not Applicable
us22	[-] Not Applicable
us32	[0]
usd1	[0]
usd2	[0]
usdf	[-] Not Applicable
use2	[-] Not Applicable
usf2	[0]
usf3	[-] Not Applicable
usfd	[0]

us1e	[0]
us1f	[-] Not Applicable
us2e	[0]
us2f	[0]
us3e	[0]
us3f	[1]
us11	[0]
us21	[-] Not Applicable
us31	[-] Not Applicable
usde	[-] Not Applicable
use1	[-] Not Applicable
usee	[0]
usef	[-] Not Applicable
usf1	[0] Arrival from station to underpass
usfe	[0]
usff	[-] Not Applicable

	BC - Construction Site
_____________________________________________________
bc1f	[-] Not Applicable
bc11	[?] All Gray
bc12	[-] Not Applicable
bcf1	[1]
bcf2	[1]
bcfe	[0]
bcff	[-] Not Applicable

	BR - Hilltop Center REAL
_____________________________________________________
bre1	[0]
brf1	[0]
brf2	[1]
brf3	[1]

br11	[0]
br12	[0]
br13	[0]
br21	[0]
br22	[0]
br23	[0]
br31	[0]
br32	[0]

br1d	[0]
br1e	[0]
br1f	[0]
br2e	[0]
br2f	[0]
br3e	[0]
br3f	[0]
brff	[0]

	BU - Hilltop Center OTHERWORLD
_____________________________________________________
buee	[0]
buef	[-] Not Applicable
bufe	[-] Not Applicable
buff	[0]

bud1	[0]
bud2	[-] Not Applicable
bue1	[0]
bue2	[0]
buf1	[0]
buf2	[1]

bu11	[0]
bu12	[0]
bu21	[0]
bu22	[0]
bu23	[0]
bu31	[0]

bu1e	[-] Not Applicable
bu1f	[-] Not Applicable
bu2e	[0]
bu2f	[0]
bu3e	[0]
budf	[-] Not Applicable

AM - Daisy Villa Apartment Complex + TG - Bergen Street
_____________________________________________________

tgf1	[1]

am1e	[1]
am1f	[1]
am11	[1]
amf1	[1]
amfe	[1]
amff	[1]

	OT - Motel + TH - Heaven's Night + CC - Silent Hill + CM - On the road
_____________________________________________________
ot1f	[1]

htf1	[1]

cc09	[-] Not Applicable
cc10	[-] Not Applicable
cc19	[-] Not Applicable
cc20	[-] Not Applicable
cc29	[?] All Gray
cc30	[-] Not Applicable
cc35	[-] Not Applicable
cc36	[-] Not Applicable
cc41	[?] All Gray
cc42	[-] Not Applicable
cc43	[-] Not Applicable
cc44	[-] Not Applicable
cc45	[-] Not Applicable
cc46	[-] Not Applicable
cc48	[-] Not Applicable
cc49	[-] Not Applicable
cc51	[?] All Gray
cc52	[-] Not Applicable
cc53	[-] Not Applicable
cc54	[-] Not Applicable
cc56	[-] Not Applicable
cc57	[-] Not Applicable

cmf1	[-] Not Applicable

	HC - Brookhaven Hospital Tunnels
_____________________________________________________
hc1f	[0]
hc11	[0]
hcf1	[0]
hcff	[-] Not Applicable

	HP - Brookhaven Hospital REAL
_____________________________________________________

hpcc	[-] Not Applicable
hpcd	[0]
hpce	[-] Not Applicable
hpdd	[0]
hpee	[0]
hpfe	[0]
hpff	[-] Not Applicable

hpc3	[-] Not Applicable
hpd1	[-] Not Applicable
hpd3	[0]
hpe2	[-] Not Applicable
hpe3	[-] Not Applicable
hpf2	[?] All Gray

hp14	[-] Not Applicable
hp21	[-] Not Applicable
hp21...	[-] Not Applicable
hp22	[-] Not Applicable
hp23	[-] Not Applicable
hp24	[-] Not Applicable
hp34	[-] Not Applicable
hp41	[0]
hp41...	[-] Not Applicable
hp44	[-] Not Applicable
hp53	[0]
hp53...	[?] All Gray

hp1e	[-] Not Applicable
hp1f	[0]
hp2f	[0]
hpdf	[-] Not Applicable
hped	[-] Not Applicable

	HU - Brookhaven Hospital OTHERWORLD
_____________________________________________________

hudd	[0]
hude	[-] Not Applicable
hued	[-] Not Applicable
huee	[0]
huef	[-] Not Applicable
hufd	[?] All Gray
huff	[-] Not Applicable

hue1	[-] Not Applicable
huf1	[-] Not Applicable
huf2	[-] Not Applicable

hu1d	[0]
hu1f	[0]
hu2d	[-] Not Applicable
hu11	[0]
hu12	[-] Not Applicable
hu21	[-] Not Applicable
hu22	[0]
hu31	[0]
hu32	[0]

	TP - Lakeview Amusement Park (TPEA 16 Maps, TPSO 8 Maps, TPWE 6 Maps)
_____________________________________________________
tp2f	[-] Not Applicable
tp12	[1]
tp13	[0]
tp21	[0]
tp22	[0]
tp23	[0]
tp31	[-] Not Applicable
tp33	[0]
tpd3	[-] Not Applicable
tpe2	[0]
tpe3	[0]
tpee	[0]
tpef	[0]
tpf2	[1]
tpf3	[0]
tpfe	[0]

tp1d	[0]
tp1e	[0]
tp2e	[0]
tp3d	[-] Not Applicable
tp3f	[0]
tpde	[0]
tpdf	[1]
tpfd	[0]

tp1f	[0]
tp11	[0]
tpd1	[0]
tpe1	[1]
tpf1	[1]
tpff	[0]

	CR - Church (1 Map) + CULOW Lower Chapel (13 Maps) + CUUP Upper Chapel (12 Maps)
_____________________________________________________

cr11	[1]

cu1d	[0]
cu1e	[0]
cu1f	[1]
cu2e	[0]
cu3e	[-] Not Applicable
cu3f	[0]
cu13	[0]
cu31	[0]
cudf	[?] All Gray
cuee	[0]
cuef	[0]
cufe	[0]
cuff	[0]

cu2f	[-] Not Applicable
cu11	[0]
cu12	[0]
cu21	[0]
cu22	[0]
cud1	[0]
cue1	[0]
cue2	[0]
cuf1	[0]
cuf2	[0]
cuf3	[0]
cufd	[0]

	CZ - Final Boss
_____________________________________________________
cz11	[1]

Not applicable meaning no vertex color data.
Does that really mean that there's no such data in the ps2 release on those maps?
