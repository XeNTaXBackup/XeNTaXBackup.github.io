## Post #1
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-05-09T11:18:36+00:00
- Post Title: View World of ArcheAge

Greetings!

ArcheAge created with CryEngine so I  want to ask you if it is possible that I can load the ArcheAge World from Client into the Editor?

In the Archive are Data like:

game\worlds\main_world\

This folder Contain:

env.xml
lightning.xml
loading.dds
surface.xml
vegation.xml
world.g
world.xml

Folders:
zone
paths
map_data
level_design
houses
cinemas
cells

Do you have any tips for me how to watch the World in the Editor maybe? 

PS: after I copied to Level I can now choose many Level like : @UI_CLIENT and one Level @UI_TEST (this I can load but not see any world)


Why I want? So... because I want to explore:

For more Pictures look Page 2  There also some cool Models that you may Interested.

Areas like this (behind the Guy)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-05-09T13:40:00+00:00
- Post Title: View World of ArcheAge

> Reply from ehnoah
>
> [...]if it is possible that I can load the ArcheAge World from Client into the Editor?Which editor do you speak of? CryEngine 3 sandbox editor?

> PS: after I copied to LevelWhat exactly did you copy?

> I can now choose many Level like : @UI_CLIENT and one Level @UI_TEST (this I can load but not see any world)Where can you choose them? In the File / "Open Level" window of the sandbox editor?
Are they named *.cry or do at least have the signature "PK" at file start (viewing them in a hex editor)?
If so could you upload one level, please? (a small one)
## Post #3
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-05-09T13:57:23+00:00
- Post Title: View World of ArcheAge

Hey I using CrySDK (CryEngine 3 Sandbox?)

The World I copied to the LEVEL.PAK of the Folder (main_world).  After done this I can choose now many @UI_TEXT in the Singleplayer Menu (launched the Launcher.exe so the Game).

I uploaded you a small map (it is a own World but much smaller) main_world look exact same just more CELL etc.

[http://www.multiupload.nl/1K7352KLX2](http://www.multiupload.nl/1K7352KLX2)

Hope you can help me
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-05-09T14:59:40+00:00
- Post Title: View World of ArcheAge

> Reply from ehnoah
>
> The World I copied to the LEVEL.PAK of the Folder (main_world).How did you repack the pak, that's the question! Which tool did you use?

(I don't owe Crysis 3, have the SDK only, but could copy it to Level.pak of Forest sample I think.)
I use PakDecrypt to unpack the level.pak but afaik it's not possible to repack a Crysis 3 pak so far.
Using rc.exe failed for me.

> I uploaded you a small map (it is a own World but much smaller) main_world look exact same just more CELL etc.Thanks!  
("own" World does not mean created by fans or by you, does it?)

> Hope you can help meWe'll see...first I need you to answer my repack question. 

edit: just copied the folder from your .rar into Singleplayer folder. Then I have the entries you mentioned, in the Launcher window. But choosing one makes the launcher crash.
## Post #5
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-05-09T15:03:41+00:00
- Post Title: View World of ArcheAge

I just used WINRAR lol  because I not thinked it change anythink but its so then ...^^

no own World mean you go trough a Portal and you are there its like a Dungeon but it is no dungeon its a "own" World (like the main_world.

Hope you understand 


Edit: Ok I read your edit, so any glue now?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-05-09T17:16:07+00:00
- Post Title: View World of ArcheAge

Hi,
made some tests and first of all let's be honest, I don't think your wish will come true in an easy way.

The easy way being this: XL Games releasing an editor.
(Avatar Reality released an editor suite (for example city editor) for Blue Mars.)

Secondly I found in levelinfo.xml of arce_mall_world: <LevelInfo SandboxVersion="2.3.2.6387"
As for CryEngine 3 this should be something like <LevelInfo SandboxVersion="3.4.5.6492"

So maybe you'd have better luck using the following with sandbox 2.

Finally in sandbox 3 I didn't see any assets of arch_mall_world after having tried out this:

- created a test level in sandbox 3 (will give you a level.pak)
- unpacked the pak
- deleted contents of terrain folder
- copied files of arche_mall_world\cells\003_003\client\terrain into it
- overwrote leveldata.xml in Level folder
- created level.rar
- copied it to CrySDK\Game\Levels\test1
loaded level test1 into editor -> nothing to be seen nor in wireframe mode (F3)

In editor.log there's a hint:
Opening terrain\cover.ctc ...
Error opening terrain texture file: file not found 

But even with the texture being found it wouldn't matter without any mesh.
Which should be provided by heightmap.dat (I guess; not sure)
## Post #7
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-05-09T17:27:07+00:00
- Post Title: View World of ArcheAge

I don't think we can get CrySDK 2.0 so far it seems no way =/ 

Maybe some of the cracks here can help convert files but that is just a wish ^^

But anyway I try to download CryEngine 2..
## Post #8
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-05-09T21:13:55+00:00
- Post Title: View World of ArcheAge

CryEngine 2 load everythink but World is Empty so it seems not load. Only AI Error but AI is nessesary I think?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-05-10T11:55:25+00:00
- Post Title: View World of ArcheAge

> Reply from ehnoah
>
> CryEngine 2 load everythink but World is Empty so it seems not load. Only AI Error but AI is nessesary I think?Empty world is not caused by AI error, I guess.

You could try to search some ArcheAge cgfs, such as
game/objects/env/02_harihara/05_si/si_stonwall02.cgf
game/objects/env/05_nature/08_cry_source/rocks/cliff_rocks/cliff_rock_island.cgf

In SDKs Game folder create a subfolder 'Objects' (big 'O' - this is case sensitive)
and copy the cgfs to it.

Then in SDKs rollup bar/Objects/Geom Entity try to load a cgf.

(I'm restless if this will work at least...)
## Post #10
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-05-10T14:13:22+00:00
- Post Title: View World of ArcheAge

Objects loading work 

But I want load the Map with HeighMap etc^^
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-05-10T15:13:19+00:00
- Post Title: View World of ArcheAge

> Reply from ehnoah
>
> Objects loading workNice go.  

> But I want load the Map with HeighMap etc^^Not that easy I think.
Someone had to transform the ArcheAge heightmaps [http://www.uploadmb.com/dw.php?id=1368198066](http://www.uploadmb.com/dw.php?id=1368198066) into a Crysis hightmap.raw (or 8-bit bitmap).

I guess XL Games modified the heightmap import heavily.
## Post #12
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-05-10T15:56:27+00:00
- Post Title: View World of ArcheAge

Oh miss readed 

Someone of you can transform this for me/us? That would be awesome!
But how I can load Textures / Objects then to the right place? There must a File that save all Possitions or not?

I saw they have files saved in /data/editor but we only have /data/client/ hope we can get some more Information.

PS: It seems there are multiple files in the heightmap.dat so it seems paked but dunno how
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-05-10T16:38:42+00:00
- Post Title: View World of ArcheAge

> Reply from ehnoah
>
> But how I can load Textures / Objects then to the right place? There must a File that save all Possitions or not?entities.xml for example:
  <Entity Name="Light_285" Pos="331.32663,1021.9719,112.47211" Rotate="0.70710671,0,0,-0.70710683" EntityClass="Light" EntityId="5895" EntityGuid="414e41a2945b3841" ViewDistRatio="200" CastShadow="0" Layer="Main">

 <Entity Name="Fish.dolphin_1" Archetype="animals.Fish.dolphin" Pos="663.9787,987.67273,92.340103" EntityClass="Fish" EntityId="5968" EntityGuid="4cb8ffcff8717043" Layer="Main"/>

(Textures are mapped on objects via UV map) .
## Post #14
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-05-10T16:56:26+00:00
- Post Title: View World of ArcheAge

Ah ok but how we force the Game to load all the Files?

We still need the *.cry file or not? And what is thie *.g File? Do you know anyone that we can ask? I would also pay for it if no one want to do it for free :-/
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-05-10T19:34:08+00:00
- Post Title: View World of ArcheAge

> Reply from ehnoah
>
> Ah ok but how we force the Game to load all the Files?Game==CrySDK?
I don't think that we ever get all the files (ambient sound, collisions, navzones etc. pp.) loaded. That would be a tremendous task. (Better create your own game using the SDK.  )

What might be achieveable: to convert hightmaps and load them into the SDK. Then load .cgf entities and place them manually.

> We still need the *.cry file or not?This would be the one of a self created test level.

> And what is thie *.g File?A table of cells; not of special interest imho.

> Do you know anyone that we can ask? I would also pay for it if no one want to do it for free :-/
There are a lot of very talented guys around here in this forum. They share their knowledge because we all share  some modelling interests. I don't think that offering payment is a good idea, but that's up to you.

Better upload some screenshots of ArcheAge cgfs in the SDK to rise some interest.
## Post #16
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-05-10T19:56:00+00:00
- Post Title: Re: View World of ArcheAge

You mean like this? (I am not good at all with this sorry!!!)
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-05-10T21:03:23+00:00
- Post Title: Re: View World of ArcheAge

> Reply from ehnoah
>
> You mean like this? (I am not good at all with this sorry!!!)Well, hmm, first one is ok.
Maybe you could add a nice girl? (WITH clothes, please  ).

And I would recommend to texture the terrain (with grass for example). Not that difficult: here is

a straight forward tut: [http://freesdk.crydev.net/display/SDKDO ... ng+Terrain](http://freesdk.crydev.net/display/SDKDOC2/Painting+Terrain)
You can skip the part with the "low detail texture". Just apply a material.

edit: the naked dwarf? Well, he looks somewhat incomplete...
(and no, I don't want to see him complete.  )
## Post #18
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-05-10T21:10:00+00:00
- Post Title: Re: View World of ArcheAge

Why you not like the Naked Dwarf?!?! ^^
