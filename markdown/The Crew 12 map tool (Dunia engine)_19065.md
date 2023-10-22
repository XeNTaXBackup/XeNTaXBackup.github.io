## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-12T16:51:25+00:00
- Post Title: The Crew 1/2 map tool (Dunia engine)

The Crew 1/2 map tool

Note: you DONT need to extract ANY files before using the tool, it exports all data right from FAT/DAT files

Whole USA map is split into 20x12 areas (0,0 is south west corner). For the first game, its 19x11 areas.
Each area is square 8x8 sectors.

Notes before using the tool:
- this version works with both games: The Crew 1 and The Crew 2
- you need oo2core_5_win64.dll from the game, place it next to the tool
- edit config.ini (set paramaters)
- edit .ini files with your paths

Usage:  thecrew2map  ax ay sx sy type
ax ay - area coordinates ( x = 0..19,  y = 0..11 )
sx sy - sector coordinates  ( 0..7 )
    (if you set sx=8, sy=8, that will export ALL 64 sectors of an area)
    (if you also set ax=99, ay=99, that will export ALL areas, or even WHOLE game map)
    (you can also set any individual coordinate as you like)
type - with this you can export only one type of objects:
- terrain - terrain mesh (exported separately as .OBJ)
- road - main road
- t1, t2, t3, t4 - four main map object types
- grass - lots of small objects and points (global for the area) - not recommended for extraction
- area - low LOD objects of area (global for the area) - not recommended for extraction
If you dont use type parameter, these will be exported: road,t1,t2,t3,t4 
If you use one of global types (grass or area), sx and sy will be ignored (because these types are for whole area)

Examples:
  thecrewmap  1 3 5 7 t1
  thecrewmap  1 3 5 7 road
  thecrewmap  1 3 5 7

After export, tool will generate:
- ascii files with all map objects (split in 50MB parts)
- transforms text file with hashed names and transform data for all mesh instances
- terrain data: obj file, terrain RAW image and other terrain masks as DDS
- materials and textures lists
- all textures used in selected map part in DX10 format (not including High Resolution textures)

ASCII file will only have the first texture applied for each object. Its usually diffuse map, but sometimes not. This will be fixed later. For auto-loading of textures, you need to replace .XBT extensions to the format you convert them, for example, .PNG 






[thecrewmap.rar](https://xentaxbackup.github.io/file/21310_thecrewmap.rar)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-12T17:36:56+00:00
- Post Title: The Crew 1/2 map tool (Dunia engine)

Tool requires res.bin file, which is generated automatically with a special tool included, you need to place it next to the EXE.
## Post #3
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2018-11-27T19:05:19+00:00
- Post Title: The Crew 1/2 map tool (Dunia engine)

Thanks so much for your effort, please keep working on tools like this!

Are the map geometry files in XBG format?
I'm hoping we can somehow do the same with the map from Watch Dogs, assuming the file format is the same.
## Post #4
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-11-29T00:51:27+00:00
- Post Title: The Crew 1/2 map tool (Dunia engine)

> Reply from CobraGamer
>
> Are the map geometry files in XBG format?
As usual just like many, never bother to read anything, it clearly states above what this is about and what the tool does.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-29T15:39:54+00:00
- Post Title: The Crew 1/2 map tool (Dunia engine)

> Reply from CobraGamer
>
> I'm hoping we can somehow do the same with the map from Watch Dogs, assuming the file format is the same.

The map format includes reading a lot of different info from game archives. Its possible that it can be done with Watch Dogs, but it may require a lot of additional work
## Post #6
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2018-11-30T21:58:35+00:00
- Post Title: The Crew 1/2 map tool (Dunia engine)

@mono24: Does the post contain anything about the map geometry format? No, only that the tool extracts the necessary data directly from the *.dat archives.
## Post #7
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-12-01T12:34:05+00:00
- Post Title: The Crew 1/2 map tool (Dunia engine)

> Reply from CobraGamer
>
> @mono24: Does the post contain anything about the map geometry format? No, only that the tool extracts the necessary data directly from the *.dat archives.

After export, tool will generate:
- ascii files with all map objects (split in 50MB parts)
- obj file with terrain
- materials and textures lists
- all textures used in selected map part in DX10 format
## Post #8
- Username: ShadyDub
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 23, 2018 11:09 pm
- Post datetime: 2018-12-06T01:00:03+00:00
- Post Title: The Crew 1/2 map tool (Dunia engine)

Does this also work for vehicles? I mean, could this tool convert vehicles to obj automatically?
## Post #9
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-12-06T02:26:47+00:00
- Post Title: The Crew 1/2 map tool (Dunia engine)

> Reply from ShadyDub
>
> Does this also work for vehicles? I mean, could this tool convert vehicles to obj automatically?
As the title and description says, it is MAP tool, no vehicle support, maybe in the future.
## Post #10
- Username: ShadyDub
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 23, 2018 11:09 pm
- Post datetime: 2018-12-06T21:47:20+00:00
- Post Title: The Crew 1/2 map tool (Dunia engine)

Thanks, this would be great!
## Post #11
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2018-12-07T19:39:36+00:00
- Post Title: The Crew 1/2 map tool (Dunia engine)

So how can the *.obj and *.ascii files be merged together? There's probably a really obvious way, but I still fail to see it.
## Post #12
- Username: lamping1990
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 12, 2019 5:39 am
- Post datetime: 2019-03-12T08:18:10+00:00
- Post Title: The Crew 1/2 map tool (Dunia engine)

how do you install this to get it to work? trying to extract some map objects
## Post #13
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-03-13T01:35:29+00:00
- Post Title: The Crew 1/2 map tool (Dunia engine)

> Reply from lamping1990 ↑Tue Mar 12, 2019 4:18 pm at Tue Mar 12, 2019 4:18 pm
>
> 
how do you install this to get it to work?
There is nothing to install, it doesn't work that way, all tools released by daemon1 are to be used in windows using CMD prompt, and everything is described in first post.
## Post #14
- Username: nWo51289
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 21, 2019 3:44 am
- Post datetime: 2019-04-08T08:00:24+00:00
- Post Title: The Crew 1/2 map tool (Dunia engine)

Thanks for releasing this tool! How do I import the .ascii files into Blender? Preferably would like to import them into 3ds Max if remotely possible. Thanks
## Post #15
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-04-16T16:58:19+00:00
- Post Title: The Crew 1/2 map tool (Dunia engine)

> Reply from nWo51289 ↑Mon Apr 08, 2019 4:00 pm at Mon Apr 08, 2019 4:00 pm
>
> How do I import the .ascii files into Blender? Preferably would like to import them into 3ds Max if remotely possible. Thanks
You first import them in Blender using XPS XNALara plugin, then you export to your desired format to import it in 3dsMax, yeah I know its not desirable, but there is no other way, that I know of.
## Post #16
- Username: nWo51289
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 21, 2019 3:44 am
- Post datetime: 2019-04-18T13:54:03+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

As mono24 said, if you want to get them into 3ds max follow his steps. Better than no 3ds Max support! Thank you.

> Its usually diffuse map, but sometimes not. This will be fixed later.
Do you have a rough idea when the fix will be implemented?

Is there a way to import the terrain mesh with textures or is that all done in game via shaders?
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-18T15:19:07+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from nWo51289 ↑Thu Apr 18, 2019 9:54 pm at Thu Apr 18, 2019 9:54 pm
>
> 
Do you have a rough idea when the fix will be implemented?
no

> Reply from nWo51289 ↑Thu Apr 18, 2019 9:54 pm at Thu Apr 18, 2019 9:54 pm
>
> 
Is there a way to import the terrain mesh with textures or is that all done in game via shaders?
there is no terrain mesh
there's data to generate terrain with something like a "foliage map" which tells where the terrain is grass, sand, stones and such.
## Post #18
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2019-05-04T20:07:02+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

So the terrain is generated based on those "maps" when starting up the game, or how can I understand that?
## Post #19
- Username: eyewee
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2018 2:46 am
- Post datetime: 2020-01-07T22:45:42+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Hey, thank you for this extractor! I'd like to know how do I automatically apply materials on the mesh?I've batch converted the ascii files into obj with noesis, but when I open them with 3ds max, materials are messed up. I've noticed the materials list generated once extraction from the game is done, how do I use it afterwards with my obj?
## Post #20
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-01-07T23:49:34+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from eyewee ↑Wed Jan 08, 2020 6:45 am at Wed Jan 08, 2020 6:45 am
>
> I'd like to know how do I automatically apply materials on the mesh?
There is no automatic way as the tool doesn't do any of that, I'm afraid the tool isn't finalized as the exported map has a lot of imperfections with the terrain last time I checked months ago, terrain also has no proper UVs that would match its blend maps that unfortunately aren't even exported to be able to use with the textures.
The game has like some blend maps for terrain that each tell what texture uses, some are sand, rocks or for grass, etc. and then all gets nicely tileable on the whole terrain deepening on those blend maps based on area/region, not sure if I explained correctly though.

> Reply from eyewee ↑Wed Jan 08, 2020 6:45 am at Wed Jan 08, 2020 6:45 am
>
> I've batch converted the ascii files into obj with noesis, but when I open them with 3ds max, materials are messed up.
Also very important, I highly recommend to NOT batch convert the ascii to obj , as it also ruins scale and will not match roads anymore, it supposedly should apply textures, but it never worked for me even though you can clearly see textures names in the ascii file structure.
Might be the fact that the script skips them or something.

> Reply from eyewee ↑Wed Jan 08, 2020 6:45 am at Wed Jan 08, 2020 6:45 am
>
> I've noticed the materials list generated once extraction from the game is done, how do I use it afterwards with my obj?
Those text files are for you to open them up individually and hunt them down and import manually to each corresponding mesh, good luck with that, based on my estimates for the whole map if you work non stop you'd be done in about a year or maybe less?
## Post #21
- Username: eyewee
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2018 2:46 am
- Post datetime: 2020-01-12T13:46:09+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Hey thank you for your reply! Actually I wasn't really counting on the terrain itself, I can always  texture it myself, but what was important is infrastructure and buildings, placed the right way and textured... So now I batch exported ascii into fbx and it seems ok to me when I get it open in 3ds max, even if no material is created at all. Doing the whole map btw is not realistic as nobody has time for that amout of work alone. 
However, I think a script could do a good job of applying correct materials and textures in 3ds max, if only somebody could write one.
What about The Crew 1? I've tried using this tool with it but it keeps giving me errors, any idea?
## Post #22
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-01-12T23:19:29+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from eyewee ↑Sun Jan 12, 2020 9:46 pm at Sun Jan 12, 2020 9:46 pm
>
> Actually I wasn't really counting on the terrain itself, I can always texture it myself, but what was important is infrastructure and buildings, placed the right way and textured... So now I batch exported ascii into fbx and it seems ok to me when I get it open in 3ds max, even if no material is created at all. Doing the whole map btw is not realistic as nobody has time for that amount of work alone.
You think texturing the buildings and other assets is complex? That means you haven't dealt with its terrain yet, good luck with that, the only thing that would make terrain easier than rest, is if you have original blend maps, with out it its pure pain, believe me, also imperfections of the terrain I meant by not being accurate to match entirely the roads and map assets.

> Reply from eyewee ↑Sun Jan 12, 2020 9:46 pm at Sun Jan 12, 2020 9:46 pm
>
> ...if only somebody could write one.
Amen to that.

> Reply from eyewee ↑Sun Jan 12, 2020 9:46 pm at Sun Jan 12, 2020 9:46 pm
>
> What about The Crew 1? I've tried using this tool with it but it keeps giving me errors, any idea?
That is what I meant with my comment above, and also as daemon specified the tool is unfinished and only maps/terrain is supported in TC2, vehicles form both games, or TC1 nothing is supported from it, to be honest I too hope one day both games would be fully supported about everything they have, their both amazing in content and scale, a dream for modding assets, art and more.
## Post #23
- Username: eyewee
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2018 2:46 am
- Post datetime: 2020-01-13T15:43:12+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Anyways, where's daemon1 ? Will he ever be updating the tool? At least to support TC1 map?
## Post #24
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-01-14T06:04:21+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from eyewee ↑Mon Jan 13, 2020 11:43 pm at Mon Jan 13, 2020 11:43 pm
>
> 
Anyways, where's daemon1 ? Will he ever be updating the tool? At least to support TC1 map?
He's around as you can see in his comments on the forum, I'm sure if he has something to say about this particular tool he will
## Post #25
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-01-17T15:41:41+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from eyewee ↑Mon Jan 13, 2020 11:43 pm at Mon Jan 13, 2020 11:43 pm
>
> 
Anyways, where's daemon1 ? Will he ever be updating the tool? At least to support TC1 map?
unfortunately i dont know if i will ever be updating the tool
## Post #26
- Username: eyewee
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2018 2:46 am
- Post datetime: 2020-01-17T22:29:03+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from daemon1 ↑Fri Jan 17, 2020 11:41 pm at Fri Jan 17, 2020 11:41 pm
>
> 
eyewee wrote: ↑Mon Jan 13, 2020 11:43 pm
Anyways, where's daemon1 ? Will he ever be updating the tool? At least to support TC1 map?

unfortunately i dont know if i will ever be updating the tool

This is sad news, I had some good ideas for TC1 parts of map in gta5... Well then would you like to share the source code ?
## Post #27
- Username: TGIJ
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 19, 2017 11:13 pm
- Post datetime: 2020-03-19T19:10:57+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

So I'm a little confused and not sure if its working properly for me. I've brought in the oo2core and changed the paths. However, when I launch the tool, it opens for a second then shuts? Not seemingly doing anything. Tried turing of antivirus with no luck on that. 

Any ideas?
## Post #28
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-03-19T19:46:34+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from TGIJ ↑Fri Mar 20, 2020 3:10 am at Fri Mar 20, 2020 3:10 am
>
> 
...when I launch the tool, it opens for a second then shuts?...
...Any ideas?
Um, if you double clicked on it like any regular executable of course it will not work, you run it from command prompt, and follow what daemon1 wrote in his example/tutorial on first post, everything will work if you follow through.

PS
Out of curiosity, for my own amusement if I may? How on earth you managed to stay alive in this forum from the time you joined, and your first question is that? What have you been reading/doing? I just don't get it.
## Post #29
- Username: TGIJ
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 19, 2017 11:13 pm
- Post datetime: 2020-03-20T09:34:00+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from mono24 ↑Fri Mar 20, 2020 3:46 am at Fri Mar 20, 2020 3:46 am
>
> 
TGIJ wrote: ↑Fri Mar 20, 2020 3:10 am
...when I launch the tool, it opens for a second then shuts?...
...Any ideas?

Um, if you double clicked on it like any regular executable of course it will not work, you run it from command prompt, and follow what daemon1 wrote in his example/tutorial on first post, everything will work if you follow through.

PS
Out of curiosity, for my own amusement if I may? How on earth you managed to stay alive in this forum from the time you joined, and your first question is that? What have you been reading/doing? I just don't get it.

Ah thanks, was just me being a idiot   

As for join time, I probably made an account back then and just never became active on the forums I guess? 

Thanks for your help.
## Post #30
- Username: tempaccount555
- Rank: beginner
- Number of posts: 27
- Joined date: Sun May 12, 2019 8:14 pm
- Post datetime: 2020-06-19T03:07:37+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

why i cant work?  i use cmd open will say Exception.ToString()
## Post #31
- Username: georacer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 24, 2017 3:14 am
- Post datetime: 2021-04-30T19:23:03+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Hello, how i'm can batch export ascii with noesis? i'm use latest verion of noesis and xna plugin but getting error when export Thanks.
## Post #32
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2021-05-05T15:21:05+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from daemon1 ↑Thu Nov 29, 2018 11:39 pm at Thu Nov 29, 2018 11:39 pm
>
> 
CobraGamer wrote:I'm hoping we can somehow do the same with the map from Watch Dogs, assuming the file format is the same.

The map format includes reading a lot of different info from game archives. Its possible that it can be done with Watch Dogs, but it may require a lot of additional work

Could you release the source with a simple guide that someone could leverage to potentially recode this to work on watchdogs 1?
Also I'm trying to learn, I have background in C# .NET/JS/Angular and ML. So i can pick up on technical things.
Could you point me to any available online guide that has enough teaching information that could enable someone to be able to eventually make a map tool?
## Post #33
- Username: lamping1990
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 12, 2019 5:39 am
- Post datetime: 2021-05-08T02:56:17+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

i tried to import the ascii files into blender, in which i had nothing show up, is this common, or is there something i need additional for blender, i am trying to get the models from las vegas into obj format, if anyone can help me with this i mainly want the casino models ,as well as freemont street
## Post #34
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-05-09T02:19:02+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from lamping1990 ↑Sat May 08, 2021 10:56 am at Sat May 08, 2021 10:56 am
>
> 
i tried to import the ascii files into blender, in which i had nothing show up, is this common, or is there something i need additional for blender, ...
You need to edit the Draw Distance otherwise nothing will be visible since the assets have in-game coordinates so everything will be outside of the draw distance in the viewport, found a video for you: [https://youtu.be/LDvFUIuxWdQ](https://youtu.be/LDvFUIuxWdQ)
## Post #35
- Username: smite1010
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 26, 2021 12:05 am
- Post datetime: 2021-05-25T16:28:43+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Hey guys, to make this tool works, should I just purchase the crew 2 for PC and start from there?
## Post #36
- Username: CryptoCat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 20, 2021 6:26 am
- Post datetime: 2021-06-01T18:34:02+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from smite1010 ↑Wed May 26, 2021 12:28 am at Wed May 26, 2021 12:28 am
>
> 
Hey guys, to make this tool works, should I just purchase the crew 2 for PC and start from there?

You don't have to buy the game, you can download trial version from UPlay and extract from there. It worked for me
## Post #37
- Username: GuineaTigg
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 07, 2021 8:49 pm
- Post datetime: 2021-06-06T08:06:51+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Does anyone know how to convert the xbt files to a recognisable format? iv found a few diff tools with this format but they either dont work or crash
## Post #38
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-06-06T18:45:53+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from GuineaTigg ↑Sun Jun 06, 2021 4:06 pm at Sun Jun 06, 2021 4:06 pm
>
> 
Does anyone know how to convert the xbt files to a recognisable format? iv found a few diff tools with this format but they either dont work or crash
[viewtopic.php?p=146821#p146821](https://forum.xentax.com/viewtopic.php?p=146821#p146821)
## Post #39
- Username: GuineaTigg
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 07, 2021 8:49 pm
- Post datetime: 2021-06-06T21:22:16+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from mono24 ↑Mon Jun 07, 2021 2:45 am at Mon Jun 07, 2021 2:45 am
>
> 
GuineaTigg wrote: ↑Sun Jun 06, 2021 4:06 pm
Does anyone know how to convert the xbt files to a recognisable format? iv found a few diff tools with this format but they either dont work or crash

viewtopic.php?p=146821#p146821

Iv actually tried this, all i get is a bunch of unreadable DDS files not useable one's 

Thanks for the response though

No idea what im doing wrong as i see alot of mention of deleting lines in Hex until i find DDS but the problem is in alot of these files DDS is the first word in the hex
## Post #40
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-06-07T22:37:29+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from GuineaTigg ↑Mon Jun 07, 2021 5:22 am at Mon Jun 07, 2021 5:22 am
>
> No idea what im doing wrong as i see alot of mention of deleting lines in Hex until i find DDS but the problem is in alot of these files DDS is the first word in the hex
Since your not giving much context to work on, then yes, your doing something wrong since i never, and still have no issues with any of this, once you extract the assets its impossible to see a DDS since all textures start with XBT and its header, then you reach DDS.
Some DDSs can be opened in Noesis but even then their displayed wrong you'll need to use Photoshop and the Intel plugin for it.

But then again, this is the tool that converts everything for you, no need to dump game assets to mess with HEX, you just need the Intel/Photoshop combo for some DDSs.
## Post #41
- Username: CryptoCat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 20, 2021 6:26 am
- Post datetime: 2021-07-31T21:37:05+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from GuineaTigg ↑Mon Jun 07, 2021 5:22 am at Mon Jun 07, 2021 5:22 am
>
> 
mono24 wrote: ↑Mon Jun 07, 2021 2:45 am
GuineaTigg wrote: ↑Sun Jun 06, 2021 4:06 pm
Does anyone know how to convert the xbt files to a recognisable format? iv found a few diff tools with this format but they either dont work or crash

viewtopic.php?p=146821#p146821


Iv actually tried this, all i get is a bunch of unreadable DDS files not useable one's 

Thanks for the response though

No idea what im doing wrong as i see alot of mention of deleting lines in Hex until i find DDS but the problem is in alot of these files DDS is the first word in the hex
If you are talking about the xbt files that the tool extracts, they are already DDS format. You just have to put right ending for file. For example "tex_cardecors_01_n.xbt" -> "tex_cardecors_01_n.dds". You can then open with GIMP.
## Post #42
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-11-29T09:12:09+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

New version posted. 

Changes:
- both games supported (the Crew 1, the Crew 2)
- config file with options
- transforms output
- support for 8-bit heightmaps
- double pres. coordinates
- terrain data: RAW heightmaps, 2 masks DDS (to a folder)
- full map export (99 99 8 8 )
- terrain exported only with "terrain" parameter
- RES.DAT generation tool
## Post #43
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-11-29T09:18:58+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

most important change is adding transform output
---------------------------------
This allows to make scripts for 3d editors or engines like Unity or Unreal to load the map.

config.ini parameters:
--------------------------------------
game 1 or 2
coordinates:
- local - means area coordinates will be at 0,0 - to export sectors from only one area 
- global - means area coordinates, for whole map extraction
next parameter is to set ascii parts size, or no ascii at all:
0 - means no ascii output
100 megabyte split was as usual before
then a list of other files, specific to game 1 or 2, so you can easily switch between games or make 2 folders with separate configs

patch support
---------------------------
if you want patches to work, put _patch files in INI first,
meaning either all patches first, or at least patch file for each FAT/DAT must go before the corresponding main file

RES.BIN generation tool
-------------------------------
drop world.bwo onto the tool, and it will generate "res.bin" to use with the map tool
## Post #44
- Username: iamtolyan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 13, 2021 11:42 pm
- Post datetime: 2021-12-13T15:57:34+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Where can I find the file res2.bin? The tool does not work without this file.
[error.jpg](https://xentaxbackup.github.io/file/21395_error.jpg)
## Post #45
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-12-14T02:51:10+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from iamtolyan ↑Mon Dec 13, 2021 11:57 pm at Mon Dec 13, 2021 11:57 pm
>
> 
Where can I find the file res2.bin? The tool does not work without this file.
[viewtopic.php?p=179959#p179959](https://forum.xentax.com/viewtopic.php?p=179959#p179959)



res.png (16.65 KiB) Viewed 212 times
## Post #46
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-12-14T09:11:00+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from iamtolyan ↑Mon Dec 13, 2021 11:57 pm at Mon Dec 13, 2021 11:57 pm
>
> 
Where can I find the file res2.bin? The tool does not work without this file.
a little mistake in description, i typed res.dat instead of res.bin
## Post #47
- Username: iamtolyan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 13, 2021 11:42 pm
- Post datetime: 2021-12-14T17:19:03+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Good. But what is the "world.bwo" file? I didn't find such a file in the folders with "The Crew 1/2" Maybe these are files "world.dat"/"world.fat" (crew 1) or "usa_world.dat"/"usa_world.fat" (crew 2). I tried dragging these files to the utility "TheCrewRes.exe ", and then the cmd window opens for a second and no files are generated. I look in the task manager, "TheCrewRes.exe " not running/not working. Further, if I put ".dat" files next to "TheCrewRes.exe" and I run it from the command line in the console with administrator rights, for example "TheCrewRes.exe usa_world.dat", then the file "res2.bin" is also not generated and there are no messages in the console. P.S. Path to the utilty = "d:\thecrewmap\", config.ini - default, Previously crew 1.ini and crew 2.ini - corrected only the path to the game, copied the file "oo2core_5_win64.dll " from the folder with the game "The Crew 2", How do I still get the file res2.bin? Please, help.
## Post #48
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-12-14T18:29:31+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from iamtolyan ↑Wed Dec 15, 2021 1:19 am at Wed Dec 15, 2021 1:19 am
>
> 
Good. But what is the "world.bwo" file?
This file is inside one of game archives. Can be extracted with EKey's extractor or BMS script.
Unfortunately i had no time to do a special tool to extract only this file.
## Post #49
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-12-14T21:36:17+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from iamtolyan ↑Wed Dec 15, 2021 1:19 am at Wed Dec 15, 2021 1:19 am
>
> But what is the "world.bwo" file? I didn't find such a file...
project\road66\generated\world.bwo or 5AFAC9A11AA14DF8

TC1 = in global_db_patch.fat/dat
TC2 = in usa_resources_patch.fat/dat

Extractors/Unpackers: [viewtopic.php?p=159199#p159199](https://forum.xentax.com/viewtopic.php?p=159199#p159199)
## Post #50
- Username: epidemick92
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 27, 2021 1:45 am
- Post datetime: 2022-01-06T09:35:21+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

I feel like im doing something wrong.
How do I export the crew 1 map with the tool?
I have the world.bwo file and the res.bin ready to go.
How do set up the coordinates too?
## Post #51
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-07T21:12:22+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from epidemick92 ↑Thu Jan 06, 2022 5:35 pm at Thu Jan 06, 2022 5:35 pm
>
> 
...I have the world.bwo file and the res.bin ready to go....
If you work on TC1 game, make sure the generated res.bin is named res1.bin or res2.bin for TC2 game.
The rest of the details are described already, except for transforms as that's just for those who want to do things from scratch and do not want to use ASCIIs output that are exactly as you see in-game.
## Post #52
- Username: epidemick92
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 27, 2021 1:45 am
- Post datetime: 2022-01-08T08:29:10+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Cool. What now?
Maybe I'm misreading the directions because I have no idea what I'm supposed to do after I have the res file(s)
## Post #53
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-08T15:26:36+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from epidemick92 ↑Sat Jan 08, 2022 4:29 pm at Sat Jan 08, 2022 4:29 pm
>
> 
Cool. What now?
You follow the instructions, you have all you need in that post, including example.
[viewtopic.php?p=145852#p145852](https://forum.xentax.com/viewtopic.php?p=145852#p145852)
As well as: [viewtopic.php?p=179959#p179959](https://forum.xentax.com/viewtopic.php?p=179959#p179959)
## Post #54
- Username: epidemick92
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 27, 2021 1:45 am
- Post datetime: 2022-01-11T07:19:34+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

I see. Now where do i type " thecrew2map ax ay sx sy type?"
In one of the ini's or in CMD?




I am very new to all of this
## Post #55
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-11T20:42:48+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from epidemick92 ↑Tue Jan 11, 2022 3:19 pm at Tue Jan 11, 2022 3:19 pm
>
> In one of the ini's or in CMD?
ini file is the setup for the tool to know with what game to work with or other options as specified.
Those parameters you enter them in command prompt or simply copy that line in a text file using notepad, then rename extension .txt to .bat then run that bat, make sure its located next to ALL required files.
## Post #56
- Username: epidemick92
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 27, 2021 1:45 am
- Post datetime: 2022-01-27T17:44:01+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Should it look like this?
Or should i add more?
[batch.png](https://xentaxbackup.github.io/file/21687_batch.png)
## Post #57
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-27T20:07:32+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from epidemick92 ↑Fri Jan 28, 2022 1:44 am at Fri Jan 28, 2022 1:44 am
>
> 
Should it look like this?
Or should i add more?
Yes, that is correct. You can add as many sectors as you like, even entire area, it is your choice, it will all be converted one after another, each converted sector/area will have in the name the numbers you specify in the .bat file.
## Post #58
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2022-06-09T00:26:48+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

do we have an idea of what the different areas/sectors are?

for example, if I wanted to export the san francisco map, where would that be located?
## Post #59
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-06-09T20:56:01+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from Wakka387 ↑Thu Jun 09, 2022 8:26 am at Thu Jun 09, 2022 8:26 am
>
> do we have an idea of what the different areas/sectors are?
Sure we do, it is even described in first post by the tool dev, the map gets built from bottom left corner, at Area 00-00, each Area has a 8x8=64 sectors, they all load vertically, one above the other, once you build first Area, then you'll immediately realize what goes on top of it, or what it represents assuming you know how the game map looks like, and all its sectors.

> Reply from Wakka387 ↑Thu Jun 09, 2022 8:26 am at Thu Jun 09, 2022 8:26 am
>
> for example, if I wanted to export the san francisco map, where would that be located?
Try to load an entire Area, then you will figure out based on that and try to keep count.
There is no better way to figure out other than loading the assets to identify what is what.

have fun
## Post #60
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2022-06-22T02:05:41+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from mono24 ↑Fri Jun 10, 2022 4:56 am at Fri Jun 10, 2022 4:56 am
>
> 
Wakka387 wrote: ↑Thu Jun 09, 2022 8:26 amdo we have an idea of what the different areas/sectors are?
Sure we do, it is even described in first post by the tool dev, the map gets built from bottom left corner, at Area 00-00, each Area has a 8x8=64 sectors, they all load vertically, one above the other, once you build first Area, then you'll immediately realize what goes on top of it, or what it represents assuming you know how the game map looks like, and all its sectors.
Wakka387 wrote: ↑Thu Jun 09, 2022 8:26 amfor example, if I wanted to export the san francisco map, where would that be located?
Try to load an entire Area, then you will figure out based on that and try to keep count.
There is no better way to figure out other than loading the assets to identify what is what.

have fun
By chance, how do I get the textures to load



I tried converting them to .DDS (using xbt2dds) & changing the format in the .mtl file, yet have not had any success.

second question would be, is there any way of importing multiple ascii files that doesn't crash blender? using the XNALara plugin seems unreliable
## Post #61
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-06-22T16:13:46+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

There is no need for you to quote the whole post, learn to edit it to a minimum.

> Reply from Wakka387 ↑Wed Jun 22, 2022 10:05 am at Wed Jun 22, 2022 10:05 am
>
> By chance, how do I get the textures to load...
You cant, textures aren't loaded automatically, it must be done manually, i know, it sucks.

> Reply from Wakka387 ↑Wed Jun 22, 2022 10:05 am at Wed Jun 22, 2022 10:05 am
>
> ...is there any way of importing multiple ascii files that doesn't crash blender? using the XNALara plugin seems unreliable
Impossible, Blender itself is NOT designed for massive scenes, you can only work on certain sections, one at at time, save progress then move to another section.
## Post #62
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-06-22T17:49:06+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from Wakka387 ↑Wed Jun 22, 2022 10:05 am at Wed Jun 22, 2022 10:05 am
>
> 
By chance, how do I get the textures to load
textures are loaded automatically, but as i said in the 1st post, only 1st texture.
you dont have to edit mtl files for that, it only depends on ascii file, and the plugin you use

> Reply from Wakka387 ↑Wed Jun 22, 2022 10:05 am at Wed Jun 22, 2022 10:05 am
>
> 
second question would be, is there any way of importing multiple ascii files that doesn't crash blender? using the XNALara plugin seems unreliable
XNALara plugin can load multiple ascii files, if they are not too big and you have enough memory
## Post #63
- Username: paypal
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 02, 2022 3:56 pm
- Post datetime: 2022-07-02T20:15:54+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Could somebody possibly make a youtube video on how to do it? Or if anyones avalible to rip detroit and send me the files in a .rar folder, I'll pay.
## Post #64
- Username: jacksaphed
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 19, 2020 8:37 am
- Post datetime: 2023-05-04T14:40:39+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Hi guys, I have tried several times exporting the entire map from TC2 but I have this kind of errors
## Post #65
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-04T19:09:33+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from jacksaphed ↑Thu May 04, 2023 10:40 pm at Thu May 04, 2023 10:40 pm
>
> Hi guys, I have tried several times exporting the entire map from TC2 but I have this kind of errors
Firstly how nice to see some interest in the map tool, awesome, before you proceed, make sure you have several TB of free space or a dedicated HDD of a minimum 8TB, I'm not even joking.

Secondly, what you see in your error it tells you there's a missing archive in your crewX.ini list (X being either 1 o 2 depending which game), probably you have more missing and that was your first error, so make sure your crewX.ini file looks like this, if you want base archives only and no updates or other additions to the game map remove the "patch" archives, if you want EVERYTHING then make sure "patch" archives are FIRST in line before the "base" archives like this:

```
x:\Uplay\The Crew 2\data_win32\gui
x:\Uplay\The Crew 2\data_win32\install_patch
x:\Uplay\The Crew 2\data_win32\install
x:\Uplay\The Crew 2\data_win32\resources_patch
x:\Uplay\The Crew 2\data_win32\resources_hr_patch
x:\Uplay\The Crew 2\data_win32\resources_hr
x:\Uplay\The Crew 2\data_win32\resources
x:\Uplay\The Crew 2\data_win32\scenaric_patch
x:\Uplay\The Crew 2\data_win32\scenaric
x:\Uplay\The Crew 2\data_win32\startup
x:\Uplay\The Crew 2\data_win32\usa_scenaric_patch
x:\Uplay\The Crew 2\data_win32\usa_scenaric
x:\Uplay\The Crew 2\data_win32\usa_resources_patch
x:\Uplay\The Crew 2\data_win32\usa_resources
x:\Uplay\The Crew 2\data_win32\usa_ecosystems_patch
x:\Uplay\The Crew 2\data_win32\usa_ecosystems
x:\Uplay\The Crew 2\data_win32\usa_ecosystems_hr_patch
x:\Uplay\The Crew 2\data_win32\usa_ecosystems_hr
x:\Uplay\The Crew 2\data_win32\usa_00_00_06_05_patch
x:\Uplay\The Crew 2\data_win32\usa_00_00_06_05
x:\Uplay\The Crew 2\data_win32\usa_00_06_06_11_patch
x:\Uplay\The Crew 2\data_win32\usa_00_06_06_11
x:\Uplay\The Crew 2\data_win32\usa_07_00_12_05_patch
x:\Uplay\The Crew 2\data_win32\usa_07_00_12_05
x:\Uplay\The Crew 2\data_win32\usa_07_06_12_11_patch
x:\Uplay\The Crew 2\data_win32\usa_07_06_12_11
x:\Uplay\The Crew 2\data_win32\usa_13_00_19_05_patch
x:\Uplay\The Crew 2\data_win32\usa_13_00_19_05
x:\Uplay\The Crew 2\data_win32\usa_13_06_19_11_patch
x:\Uplay\The Crew 2\data_win32\usa_13_06_19_11
x:\Uplay\The Crew 2\data_win32\usa_world_patch
x:\Uplay\The Crew 2\data_win32\usa_world
x:\Uplay\The Crew 2\data_win32\usa_world_hr_patch
x:\Uplay\The Crew 2\data_win32\usa_world_hr
x:\Uplay\The Crew 2\data_win32\vehicles_resources_patch
x:\Uplay\The Crew 2\data_win32\vehicles_resources
x:\Uplay\The Crew 2\data_win32\vehicles_resources_hr_patch
x:\Uplay\The Crew 2\data_win32\vehicles_resources_hr
```

PS:
When you downloaded the archive there was an example inside to see what you need to add, since some assets are scattered through out entire game, there's no way to tell where so you must add all archives and the tool will search for the needed assets 

Have fun!
## Post #66
- Username: jacksaphed
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 19, 2020 8:37 am
- Post datetime: 2023-05-04T20:01:28+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Hey thanks! Yes very interesting this game map, Im working on a fictional Miami for a proyect and this game looks insane.
Im trying now the list avoiding patches.

I think this going good?

```
E:\Games\The Crew 2\data_win32\install
E:\Games\The Crew 2\data_win32\resources_hr
E:\Games\The Crew 2\data_win32\resources
E:\Games\The Crew 2\data_win32\scenaric
E:\Games\The Crew 2\data_win32\startup
E:\Games\The Crew 2\data_win32\usa_scenaric
E:\Games\The Crew 2\data_win32\usa_resources
E:\Games\The Crew 2\data_win32\usa_ecosystems
E:\Games\The Crew 2\data_win32\usa_ecosystems_hr
E:\Games\The Crew 2\data_win32\usa_00_00_06_05
E:\Games\The Crew 2\data_win32\usa_00_06_06_11
E:\Games\The Crew 2\data_win32\usa_07_00_12_05
E:\Games\The Crew 2\data_win32\usa_07_06_12_11
E:\Games\The Crew 2\data_win32\usa_13_00_19_05
E:\Games\The Crew 2\data_win32\usa_13_06_19_11
E:\Games\The Crew 2\data_win32\usa_world
E:\Games\The Crew 2\data_win32\usa_world_hr
E:\Games\The Crew 2\data_win32\vehicles_resources
E:\Games\The Crew 2\data_win32\vehicles_resources_hr

```
## Post #67
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-04T20:48:01+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from jacksaphed ↑Fri May 05, 2023 4:01 am at Fri May 05, 2023 4:01 am
>
> ...I think this going good?...
Great, yes if you want base game no updates or other additions you remove "patch" archives, your files looks correct, happy exporting, and remember the storage space, you'll need it 

Also, i forgot to mention, start small, few Sectors from an Area, or only the Sectors you need from an Area or are of interest to you to avoid long exporting/loading times, and another important note, the ASCIIs exported do NOT support instances for both objects and materials, everything will be duplicated over and over again depending on the number of instances loaded by that Sector, don't freak out if Blender starts to be slow, load little by little and see how much it can handle based on your computer hardware.
## Post #68
- Username: jacksaphed
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 19, 2020 8:37 am
- Post datetime: 2023-05-04T22:34:44+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Thanks guy! I'll go slowly sector by sector
## Post #69
- Username: Sirhc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 06, 2023 4:14 am
- Post datetime: 2023-05-05T20:29:06+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

I'm working on an Miami based map as well, this is a good starting point but to avoid any legal issues if you decide to use this I suggest replacing as many models with your own or licensed ones you own and you can use the roads as a base layout. I got portions of downtown Miami, south beach and Venetian Islands in UE5. I suggest removing all the trees as they're not instanced (other models are duplicated and not instanced as well but it's not as bad as the trees) and take up a lot of the file size and will not only slow down blender but UE as well. Importing to blender takes about 30-45 minutes per ascii file in 100mb chunks in my case. Miami coordinates are approximately 16, 0, 8, 8 to start. If you're having trouble with coordinates import the map image into photoshop and scale it to a 19x11 canvas (for the crew 1) and use the ruler tool to get an approximate area location. Not all models will import into UE easily so you'll need to do some work in blender. Also the map gets imported off axis (at least for me) so you'll have to use transforms to flip it on the proper axis.
## Post #70
- Username: jacksaphed
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 19, 2020 8:37 am
- Post datetime: 2023-05-06T11:39:56+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Any advice? TC1 or TC2? Some people says "the first game had more realistic models" but i think the TC2 have more acurate textures, bump and spec meaning 

Alright I'll start on these coords, but still having this kind of error, the extraction stops at Area _00_05 Sector 07_07
## Post #71
- Username: jacksaphed
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 19, 2020 8:37 am
- Post datetime: 2023-05-06T12:29:20+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Alright nevermind! my game was broken. Now works everything, waiting the extracted things, almost textures important, building I'll make it by my hand hehe
## Post #72
- Username: Sirhc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 06, 2023 4:14 am
- Post datetime: 2023-05-07T00:18:03+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from jacksaphed ↑Sat May 06, 2023 7:39 pm at Sat May 06, 2023 7:39 pm
>
> 
Any advice? TC1 or TC2? Some people says "the first game had more realistic models" but i think the TC2 have more acurate textures, bump and spec meaning 

Alright I'll start on these coords, but still having this kind of error, the extraction stops at Area _00_05 Sector 07_07

TC1 has better models and more areas in Florida, but TC2 has more accurate textures and models. Venetian Islands is a good example, TC1 has nothing but 2-3 story mansions which is not accurate, TC2 has variety, some 1 story houses, some 2 story, some with big yards and gates, some with no gate at all. But Miami Florida in TC2 seems to be more scaled down than TC1
## Post #73
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-08T00:11:00+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

For TC2 if any of you that plans on using the fully updated game with the patch archives included make sure to follow last paragraph in this post
[viewtopic.php?p=179959#p179959](https://forum.xentax.com/viewtopic.php?p=179959#p179959)

Also i forgot to mention, TC1 has wrong placements for transforms so far it seems on the Z axis only, for exported ASCIIs as well, not fully sure myself yet how bad though or the percentage from whole map, It takes a lot of time to check, so not sure how bad is TC2 or if its wrong at all? So keep that in mind guys.
## Post #74
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-05-09T10:57:33+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Testing a new tool version that supports instances and a new format.
Loading one full sector takes about 1-2 minutes and file sizes are much smaller.
Whole sector export is 10-20 mb because its compressed inside.
## Post #75
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-05-10T19:28:28+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

Another improvement. Now whole AREA loads in 5 minutes.
## Post #76
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-06-06T16:39:05+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

New experimental tool version for The Crew series games, that supports Decima DMF format. Blender add-on for importing the converted DMF map files is located here: [https://github.com/REDxEYE/decima-dmf](https://github.com/REDxEYE/decima-dmf)

In order to take advantage of all optimizations made, and fast import speeds, Blender 3.5.x and up is highly recommended. Loading time can be 10 times longer or even more if you use older version of blender

Usage has remained the same (see 1st message of the thread)



The new format allows for very fast loading times and small file sizes, and also the following:

- Instances support for objects and materials:
each object per Sector or Area is exported once as a master object, and instances are based on each master object,
every single master object is located at the center 0,0,0 and hidden by default upon import,
In order to edit/modify/replace/etc a individual object un-hide that object that is located at 0,0,0 and once you make any changes the instances of that object will follow every change made.
- Material names support:
once a master object is selected for editing, in the material properties you will see the actual material name of that mesh/sub-mesh it has
the companion *_material.txt of that Sector/Area converted, holds the texture names for each material type that particular mesh/sub-mesh of the object, and textures are extracted in the Textures sub-folder created at conversion time at root folder where tool resides.
NOTE: about the textures,
textures extracted are NOT converted and have original *.XBT extension, replace extension with *.DDS and now you have a working texture
some textures are DX10 format and NOT natively supported by most 3D editors, might want to convert them to PNG in a batch using ex. Noesis
keep in mind, textures are NOT applied automatically, they must be applied manually
- The following new files are now needed for the tool to work (included):
dmf.dll - the new format library used for maps export
Newtonsoft.Json.dll for the json format of the new format
zlib.net.dll for compressing the data that makes the DMF small in size.
NOTES: about the usage
the new tool still requires previous files for the conversion to work, nothing has changed besides the new additional needed files above
tool still exports ASCII files, they are very small, can be safely ignored/deleted
- Meshes/objects/XBG files names support and hash filter:

The new config.ini will look like this:

```
global    // local or global sector coordinates
100    // megabytes to split ascii, 0 = no ascii
crew1.ini    // list of FAT/DAT archives
res1.bin    // resource database
list.txt    // hash list
list64.txt    // hash 64 list
8a833b2cf6f3c6b9    // hash filter, 0 = no filter
```

Last two lines are the new additions.
hash 64 list is for meshes/XBG names, if you know them, add them inside that text file, otherwise you will see only HASH instead of a name
hash filter is for exporting only one model (having that hash) and all its instances, be it per Area, Sector or WHOLE game map. 0 means there is no filter, so tool will export everything in the desired Area/Sector as usual
NOTE: about the Area vs Sector difference in size:
Each and every Area has a 8x8 square tiled Sector totaling 64,
If a tree is found in every single Sector of a whole Area and each Sector is exported individually that means we will have 64 unique objects of that tree aka duplicates, and the rest will be instances, thus increasing the size over all.
If an Area is converted than that tree will only be exported once as a unique master object and the rest will be instances of that master tree object, meaning the computer will only need resources to load one tree not 64, making Blender run smoother and using less resources.
NOTE:
*_transforms.txt files are still exported for those who want to convert individual XBGs and venture themselves in using a specific 3D editor or game engine to build the map with their desired assets to even be replaced to their liking while still using same transforms from the game and the tool to convert them is located here:
[viewtopic.php?p=181159#p181159](https://forum.xentax.com/viewtopic.php?p=181159#p181159)
[thecrewmap.7z](https://xentaxbackup.github.io/file/23884_thecrewmap.7z)
## Post #77
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-06-06T16:47:06+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

you can download Newtonsoft DLL from official Newtonsoft.Json page, or get only the version needed for the tool attached here
[Json.7z](https://xentaxbackup.github.io/file/23885_Json.7z)
## Post #78
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-06-06T20:18:42+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

I'd like to post the following notes based on my findings with the new tool posted above by daemon1:

Technical details:

- The Crew:
Converted Areas of the whole game in the new DMF format are 14.1 GB in size.
Converted Sectors of the whole game in the new DMF format are 23.1 GB in size.
Converted terrain in the OBJ format, regardless of Area/Sector option is 117 GB in size.
Total assets/objects used across WHOLE map are 36,138, and 23,671,867 are the total instances, while 33,102 are duplicated**
- The Crew 2:
Converted Areas of the whole game in the new DMF format are 28.2 GB in size.
Converted Sectors of the whole game in the new DMF format are 57.7 GB in size.
Converted terrain in the OBJ format, regardless of Area/Sector option is 135 GB in size.
Total assets/objects used across WHOLE map are 34,128, and 45,381,643 total instances, 62,170 are duplicated**
**based on the updated final versions of the games at the time of this writing

Explanation about the size difference is posted in the: " NOTE: about the Area vs Sector difference in size:" posted above in the new tool post by daemon1

Additional NOTES:
if you desire to import a single whole Area, recommended minimum RAM is at least 32GB, if you want to import 2 Areas or more, 64GB-128GB of RAM, keep in mind Blender itself has it's own limitations as to how many actual triangles a scene may hold, so use caution in that regard
regardless if you know the full path string of a HASH, it will only work on a single HASH at a time inside the config.ini, not the full path string, the game does NOT store those full path strings, they have to be generated/reversed manually and copy them to the list64.txt file only that is used for the names you see in Blender's viewport
the single HASH conversion is also helpful if you desire to convert a single object per WHOLE game and ALL it's instances, of course Area/Sector will work too or any horizontal or vertical combination of Sector per Area, it also offers the freedom in converting ONLY a desired type of an asset from the map, with out the need of the rest of the map assets and their materials, to later on use it in your other 3D editors or game engine or other custom setup you might have, mods, etc.

The following two mapped Areas/Sectors are included for a better understanding of what to convert exactly and where is all located on the maps, i tried  my best to make them as HD as possible with roads, so click on them to see them on imgur at their highest resolution in order to see the smaller digits of every single 64 individual Sectors per each Area.

The Crew


The Crew 2


have fun
## Post #79
- Username: Anthos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 24, 2023 12:04 am
- Post datetime: 2023-07-27T14:41:44+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from daemon1 ↑Tue Nov 13, 2018 1:36 am at Tue Nov 13, 2018 1:36 am
>
> 
Tool requires res2.bin file, which will later be generated automatically, but now you need to place it next to the EXE.
Its bigger than 256k, so get it here: https://zenhax.com/viewtopic.php?f=5&t=8879

Hey, this link is dead
## Post #80
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-27T15:13:30+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from Anthos ↑Thu Jul 27, 2023 10:41 pm at Thu Jul 27, 2023 10:41 pm
>
> 
daemon1 wrote: ↑Tue Nov 13, 2018 1:36 am
Tool requires res2.bin file, which will later be generated automatically, but now you need to place it next to the EXE.
Its bigger than 256k, so get it here: https://zenhax.com/viewtopic.php?f=5&t=8879

Hey, this link is dead
this file is now generated automatically, you dont need to download it
## Post #81
- Username: Anthos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 24, 2023 12:04 am
- Post datetime: 2023-07-27T15:42:18+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

thanks, I just figured it out
## Post #82
- Username: Anthos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 24, 2023 12:04 am
- Post datetime: 2023-07-28T17:02:30+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from daemon1 ↑Thu Jul 27, 2023 11:13 pm at Thu Jul 27, 2023 11:13 pm
>
> 
Anthos wrote: ↑Thu Jul 27, 2023 10:41 pm
daemon1 wrote: ↑Tue Nov 13, 2018 1:36 am
Tool requires res2.bin file, which will later be generated automatically, but now you need to place it next to the EXE.
Its bigger than 256k, so get it here: https://zenhax.com/viewtopic.php?f=5&t=8879

Hey, this link is dead

this file is now generated automatically, you dont need to download it

I am sorry to bother you again, i wanted to ask how could i open ascii files in blender: I tried with XNALara / XPS plugin but it gives me an error (Blender 3.5 ... maybe an older version of blender will solve the problem?).
All the roads and game assets are in the ascii file that is generated, right?
## Post #83
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-29T09:25:06+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from Anthos ↑Sat Jul 29, 2023 1:02 am at Sat Jul 29, 2023 1:02 am
>
> 
how could i open ascii files in blender: I tried with XNALara / XPS plugin but it gives me an error (Blender 3.5 ... maybe an older version of blender will solve the problem?).
All the roads and game assets are in the ascii file that is generated, right?
yes, XNALara / XPS plugin works fine, with all versions of blender, including 3.5, i just checked that again.
## Post #84
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-07-30T22:49:50+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from Anthos ↑Sat Jul 29, 2023 1:02 am at Sat Jul 29, 2023 1:02 am
>
> ...how could i open ascii files in blender: I tried with XNALara / XPS plugin but it gives me an error (Blender 3.5 ... maybe an older version of blender will solve the problem?)...
Whats wrong with: [viewtopic.php?p=192233#p192233](https://forum.xentax.com/viewtopic.php?p=192233#p192233)
## Post #85
- Username: kazumadev3
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 11, 2023 5:22 pm
- Post datetime: 2023-09-11T10:19:16+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

hello to all and already thank you very much for all the work provided! I would like to export only chicago (AREA 11-08 / AREA12-08) but I don't understand how to configure to have only chicago, maybe thecrewmap 11 08 8 8?
## Post #86
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-09-11T22:11:54+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from kazumadev3 ↑Mon Sep 11, 2023 6:19 pm at Mon Sep 11, 2023 6:19 pm
>
> ...(AREA 11-08 / AREA12-08)...
...maybe thecrewmap 11 08 8 8?
Yup, if it will be incomplete, you might need the lower ones too, either way export that and check and see if that's what you really need or more.
If also might be too much data for you, depending on PC specs, do by sector instead of whole area, play around with the export to see what works best for you.
## Post #87
- Username: 1337VIPER
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 17, 2023 2:54 am
- Post datetime: 2023-10-16T20:09:41+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

is there any way to get the exported models at original transform positions in blender and not all stacked on top of each other?
## Post #88
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-10-16T20:17:02+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from 1337VIPER ↑Tue Oct 17, 2023 4:09 am at Tue Oct 17, 2023 4:09 am
>
> 
is there any way to get the exported models at original transform positions in blender and not all stacked on top of each other?
That does not make any sense, can you elaborate what is the problem you are having and what you are trying to do?
I know for a fact the map has EVERY single asset same as in-game with each and every instance.
## Post #89
- Username: 1337VIPER
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 17, 2023 2:54 am
- Post datetime: 2023-10-16T20:47:20+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

when ever I export a full area, everything is relative to 0, 0, 0 in world space, so all the buildings are within eachother at the co-ords of  0,0,0 as seen in the image below 

[https://prnt.sc/bVCp2BOJKlXr](https://prnt.sc/bVCp2BOJKlXr)
## Post #90
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-10-16T20:50:27+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from 1337VIPER ↑Tue Oct 17, 2023 4:47 am at Tue Oct 17, 2023 4:47 am
>
> ...everything is relative to 0, 0, 0 in world space...
I need more context, what tool did you used, there are two of them ASCII output and DMF output with instances (which i recommend).
And most importantly, what is your INI look like?

It looks like based on screenshot you used "local" instead of "global" coordinate system, make sure you change it to "global" not "local"
## Post #91
- Username: 1337VIPER
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 17, 2023 2:54 am
- Post datetime: 2023-10-16T20:56:00+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

ok here is a run through...

config looks like this - [https://prnt.sc/vGVAzNsX7DrD](https://prnt.sc/vGVAzNsX7DrD)

Ran the tool like this - [https://prnt.sc/ZGgWluMwvinu](https://prnt.sc/ZGgWluMwvinu)

got an output like this - [https://prnt.sc/dMRzhs74I2Rf](https://prnt.sc/dMRzhs74I2Rf)

imported to blender like this - [https://prnt.sc/sl82wjVwMwjl](https://prnt.sc/sl82wjVwMwjl)
## Post #92
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-10-16T21:06:19+00:00
- Post Title: Re: The Crew 1/2 map tool (Dunia engine)

> Reply from 1337VIPER ↑Tue Oct 17, 2023 4:56 am at Tue Oct 17, 2023 4:56 am
>
> 
...Ran the tool like this - https://prnt.sc/ZGgWluMwvinu
Ok so based on that it seems you are missing assets, that means you did not add all needed archives to the list, add them and you'll no longer have missing asset like "not found ...".

> Reply from 1337VIPER ↑Tue Oct 17, 2023 4:56 am at Tue Oct 17, 2023 4:56 am
>
> 
...got an output like this - https://prnt.sc/dMRzhs74I2Rf
And based on this output you are using latest DMF tool on TC2 game, good, now what you see is correct, each and every asset is imported once, same way the game loads them in to GPU at 0,0,0, that's correct, then the game code sets them up in to global coordinates as you see them in-game as instances, now go to the right in Blender select ANY of the instances then click on keyboard the Del (.) dot key to take you to that instance then zoom out to see the actual sector/area loaded and all its instances 

That way Blender uses minimum resources to only load the master object once at 0,0,0.
If you need to modify, edit it etc, just select it from 0,0,0 hide the rest, make the changes you need then ALL instances will follow that modification, that's it.
