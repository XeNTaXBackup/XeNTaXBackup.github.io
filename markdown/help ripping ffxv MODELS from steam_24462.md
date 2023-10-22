## Post #1
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2021-09-06T15:28:05+00:00
- Post Title: help ripping ffxv MODELS from steam

need direction on where to start and what programs and tools needed to rip the assets from the game from steam
## Post #2
- Username: SecaProject
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Apr 11, 2012 1:48 am
- Post datetime: 2021-09-06T19:20:43+00:00
- Post Title: help ripping ffxv MODELS from steam

One message is enough to know if they can help you. Maybe there is still nothing friendly to extract this kind of files, give it some time  
It would also help if you could give some information about the files.
## Post #3
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-09-06T22:42:40+00:00
- Post Title: help ripping ffxv MODELS from steam

> Reply from neonvega ↑Mon Sep 06, 2021 11:28 pm at Mon Sep 06, 2021 11:28 pm
>
> 
...what programs and tools needed...
[https://richwhitehouse.com/index.php?co ... project=91](https://richwhitehouse.com/index.php?content=inc_projects.php&showproject=91)
You can extract all archives with Noesis then load each asset/animation you desire with Noesis by leaving folder structure intact after extraction, Noesis will do the rest for you once you double click on an extracted asset.

have fun
## Post #4
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2021-09-06T23:53:24+00:00
- Post Title: help ripping ffxv MODELS from steam

no Ihave noesis already along with blender just need to know where to go in steam to access them in fbx format
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-09-07T09:07:07+00:00
- Post Title: help ripping ffxv MODELS from steam

> Reply from neonvega ↑Tue Sep 07, 2021 7:53 am at Tue Sep 07, 2021 7:53 am
>
> 
no Ihave noesis already along with blender just need to know where to go in steam to access them in fbx format

Steam doesn't have the games in fbx format, they're inside archives, you use noesis to extract the archives, which extracts into models with custom formats and extensions, then you use noesis to view those and convert them to fbx files.

There aren't any games that store their models in fbx format.
## Post #6
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2021-09-07T22:55:29+00:00
- Post Title: help ripping ffxv MODELS from steam

no I know that ;i was referring to the models themselves within the archives ive read they are already in fbx format  but maybe thats what i was getting at where can i access the archives  within the steam game? if you know well i think the rest i can figure out i just thought ppl had another way to access the models 
like this tool i was looking at : 

[http://modtool.finalfantasyxv.com/en/guide.html](http://modtool.finalfantasyxv.com/en/guide.html) if you scroll over to Mod creation guidlines it talks how models are created as fbx files which is EXACTLY what i need to start the process
## Post #7
- Username: SecaProject
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Apr 11, 2012 1:48 am
- Post datetime: 2021-09-08T00:28:24+00:00
- Post Title: help ripping ffxv MODELS from steam

I think the problem lies in the lack of clarity of your request, what do you need? Extract the models? Visualise them?
Because as lionheartuk said, the game doesn't has the models in FBX format, this mean you extracted them
## Post #8
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-09-08T04:10:21+00:00
- Post Title: help ripping ffxv MODELS from steam

> Reply from neonvega ↑Wed Sep 08, 2021 6:55 am at Wed Sep 08, 2021 6:55 am
>
> 
no I know that ;i was referring to the models themselves within the archives ive read they are already in fbx format  but maybe thats what i was getting at where can i access the archives  within the steam game? if you know well i think the rest i can figure out i just thought ppl had another way to access the models 
like this tool i was looking at : 

http://modtool.finalfantasyxv.com/en/guide.html if you scroll over to Mod creation guidlines it talks how models are created as fbx files which is EXACTLY what i need to start the process
The games models aren't in fbx format, they're in a custom format.

You'll have to use noesis to extract the archives, which will extract into a lot of differently named folders, some names are kind of clear and some aren't, from there find the folder most likely to contain characters, extract the archives inside of there using noesis, then open the extracted files in noesis and you'll be able to convert them to fbx from there.
Should be something like
Program files/steam/ateamapps/common/finalfantasyXV/Datas/Character/nh/n02/model_010 for example
if those aren't all visible you may need to extract the files inside of datas first, they should be .earc files I *think*.
## Post #9
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2021-09-08T22:37:16+00:00
- Post Title: help ripping ffxv MODELS from steam

update so yeah i got around figuring out the tools the archives are a mess you have to dig through them to find models did find the NH folder looking for randolph the quest npc cant seem to find him ; so yeah the models are in earc format and using the ffxv hunter tools turns them into a bin file that I can plug into Noesis but if someone can answer how do I export the models with ingame bones the models just load with an armature with no bones and no textures?; I know the textures have to be unpacked which I can figure out but can anyone tell me how to  port them into blender in fbx format with ingame bones?
## Post #10
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-09-08T23:35:23+00:00
- Post Title: help ripping ffxv MODELS from steam

> Reply from neonvega ↑Thu Sep 09, 2021 6:37 am at Thu Sep 09, 2021 6:37 am
>
> 
update so yeah i got around figuring out the tools the archives are a mess you have to dig through them to find models did find the NH folder looking for randolph the quest npc cant seem to find him ; so yeah the models are in earc format and using the ffxv hunter tools turns them into a bin file that I can plug into Noesis but if someone can answer how do I export the models with ingame bones the models just load with an armature with no bones and no textures?; I know the textures have to be unpacked which I can figure out but can anyone tell me how to  port them into blender in fbx format with ingame bones?

It's been a long time since I tried this, but I think you can do 100% of the process with noesis itself.
I'm pretty sure if you do it that way, using no external tools, you'll be able to get the models with bones.
Noesis can load .earc files, and several other FFXV file formats.
## Post #11
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2021-09-09T00:35:47+00:00
- Post Title: help ripping ffxv MODELS from steam

ok ill try later on but from what it looks like i get bits and pieces of files theres no structure to the folders just mb, nh, cm, uy, um, ym, be,ae and alot of the models are hidden in those folders is there another program i can use to preview the models before hand or do i only have this tool to rely on as far as ripping the models from the game?
## Post #12
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-09-09T02:25:49+00:00
- Post Title: help ripping ffxv MODELS from steam

> Reply from neonvega ↑Thu Sep 09, 2021 8:35 am at Thu Sep 09, 2021 8:35 am
>
> 
ok ill try later on but from what it looks like i get bits and pieces of files theres no structure to the folders just mb, nh, cm, uy, um, ym, be,ae and alot of the models are hidden in those folders is there another program i can use to preview the models before hand or do i only have this tool to rely on as far as ripping the models from the game?
Preview the models beforehand? You mean preview them before extracting them?
I don't believe so no, you have to go through the folders.

There is a structure to the folders, takes a little bit of time to get used to, but theres a structure in there. Just do everything in noesis (i think there are a few non-model file types noesis doesn't support) wherever possible, worth remembering that the files are organized by the people who developed the game, so they all understood the meanings for each abbreviation, for the rest of us we just have to figure it out really, doesn't help that things might also be abbreviations from Japanese.
## Post #13
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-09-09T02:43:22+00:00
- Post Title: help ripping ffxv MODELS from steam

I don't have the data of this game anymore, but I think that this game had two types of files,
one that can be read as it is by Noesis and the other that can be read after expanding with Noesis.
In addition, I remember that it was necessary to refer to the data in the file or change the location of the data for the Ignis file of Episode Ignis.

This game has a lot of modding and extraction, so it may be more useful to search for information rather than asking here.
It's a game with a data size of over 150GB, so no one keeps the data when they stop playing.
## Post #14
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2021-09-09T21:20:00+00:00
- Post Title: help ripping ffxv MODELS from steam

well i kind of need some direction on where to go from where im at ... so im using ffxv hunter to explore the game files in ffxv directory and I know how to extract the earc data and gfxbin files and then load them up in Noesis but they are not loading with any bones just the model itself loads up I can convert into blender just fine as an fbx file but how do I  convert the textures and how do I load the models with their ingame bones is there a script I can use to do that?
## Post #15
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2021-09-09T21:22:45+00:00
- Post Title: help ripping ffxv MODELS from steam

SOLVED
## Post #16
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-09-10T02:36:18+00:00
- Post Title: Re: help ripping ffxv MODELS from steam

> Reply from neonvega ↑Fri Sep 10, 2021 5:22 am at Fri Sep 10, 2021 5:22 am
>
> 
...nothing really is concrete on what to do...///...only ppl who have done this can tell me...
Assuming you extracted it all intact with its file/folder structure using Noesis, as has been previously suggested, numerous times.
All you have to do is double click ANY *.gmdl.gfxbin model with in Noesis, and EVERYTHING loads just fine, animations included, and yes, that means skinned meshes with bones too, otherwise animations would NOT work.
Then, and i cant stress this enough, then and ONLY then you can get your converted/exported precious FBXs.


Extract: (follow steps EXACTLY):
Tools->Batch Process:

1.Input extension: earc
2.Output Extension: extract (doesn't really matter)
3.Output Path: x:\YOU'R\OUTPUT\PATH\ (mind the ending BackSlash, its imperative)
4.Recursive: tick (check)
5.Folder Batch: select the root folder of the game (and you'll see the list populated with the EARC archives ready for extraction in your selected path above)
6.Export: click on it (wait patiently)
7.Done: click on it


Load/Preview:
After extraction above, navigate using Noesis each folder you want to test and double click on the *.gmdl.gfxbin you want to preview/extract.
Or you can also use windows explorer faster and just drag'n'drop in to Noesis's preview window to load each model, click yes to accept and it will load desired model.
For animations, AFTER you load any given character, you drag'n'drop a *.ani animation on to the loaded model in the Noesis preview window, and this time you click NO and animation will be loaded on to the model.
For converting to your long desired FBX, well, i assume you know what to do.

Note: if by any chance you do NOT see any materials loaded in the Noesis preview window of the model, do the following:

Tools->Data Viewer->Persistent Settings->Other->Default preview commands:
by double clicking on it enter value: -ff15materials
These are ALL optional commands for the FFXV game btw and their all annotated accordingly:

```
-ff15pickanim - when loading a model, look around and try to load a random clip.
-ff15noskel - don't attempt skeleton load.
-ff15nospecoccl - don't apply spec occlusion when using -ff15materials.
-ff15occlmap - try to load occlusion maps. requires -ff15materials.
-ff15materials - attempt actually load materials.
-ff15notex - don't attempt to load textures.
-ff15repna - reparent joints outside of the animation hierarchy.
-ff15lowtex - don't prefer _$h textures.
-ff15trnonsphere - force translations to conform to a sphere.
-ff15trnscl <arg> - scale translations.
-ff15addanim - apply animation as additive.
-ff15noscale - don't apply scale.
-ff15notrn - don't apply translation or root motion.
-ff15chp <arg> - supply interim channel pad.
-ff15softhair - force self-sorting soft hair.
```

You can add any commands above with spaces in between them, and you can test what you want for your needs.

have fun
## Post #17
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2021-09-10T14:59:26+00:00
- Post Title: Re: help ripping ffxv MODELS from steam

alright i got it
## Post #18
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2021-09-10T17:43:43+00:00
- Post Title: Re: help ripping ffxv MODELS from steam

> Reply from mono24 ↑Fri Sep 10, 2021 10:36 am at Fri Sep 10, 2021 10:36 am
>
> 
neonvega wrote: ↑Fri Sep 10, 2021 5:22 am
...nothing really is concrete on what to do...///...only ppl who have done this can tell me...
Assuming you extracted it all intact with its file/folder structure using Noesis, as has been previously suggested, numerous times.
All you have to do is double click ANY *.gmdl.gfxbin model with in Noesis, and EVERYTHING loads just fine, animations included, and yes, that means skinned meshes with bones too, otherwise animations would NOT work.
Then, and i cant stress this enough, then and ONLY then you can get your converted/exported precious FBXs.


Extract: (follow steps EXACTLY):
Tools->Batch Process:

1.Input extension: earc
2.Output Extension: extract (doesn't really matter)
3.Output Path: x:\YOU'R\OUTPUT\PATH\ (mind the ending BackSlash, its imperative)
4.Recursive: tick (check)
5.Folder Batch: select the root folder of the game (and you'll see the list populated with the EARC archives ready for extraction in your selected path above)
6.Export: click on it (wait patiently)
7.Done: click on it


Load/Preview:
After extraction above, navigate using Noesis each folder you want to test and double click on the *.gmdl.gfxbin you want to preview/extract.
Or you can also use windows explorer faster and just drag'n'drop in to Noesis's preview window to load each model, click yes to accept and it will load desired model.
For animations, AFTER you load any given character, you drag'n'drop a *.ani animation on to the loaded model in the Noesis preview window, and this time you click NO and animation will be loaded on to the model.
For converting to your long desired FBX, well, i assume you know what to do.

Note: if by any chance you do NOT see any materials loaded in the Noesis preview window of the model, do the following:

Tools->Data Viewer->Persistent Settings->Other->Default preview commands:
by double clicking on it enter value: -ff15materials
These are ALL optional commands for the FFXV game btw and their all annotated accordingly:
Code: Select all-ff15loadlods - load all lod's.
-ff15pickanim - when loading a model, look around and try to load a random clip.
-ff15noskel - don't attempt skeleton load.
-ff15nospecoccl - don't apply spec occlusion when using -ff15materials.
-ff15occlmap - try to load occlusion maps. requires -ff15materials.
-ff15materials - attempt actually load materials.
-ff15notex - don't attempt to load textures.
-ff15repna - reparent joints outside of the animation hierarchy.
-ff15lowtex - don't prefer _$h textures.
-ff15trnonsphere - force translations to conform to a sphere.
-ff15trnscl <arg> - scale translations.
-ff15addanim - apply animation as additive.
-ff15noscale - don't apply scale.
-ff15notrn - don't apply translation or root motion.
-ff15chp <arg> - supply interim channel pad.
-ff15softhair - force self-sorting soft hair.
You can add any commands above with spaces in between them, and you can test what you want for your needs.

have fun

here is my video where im stuck I apologize if im missing a step ive ported from games before so im not sure what the missing link here is im not doing but I swear im doing exactly like you told me to :

[https://www.mediafire.com/file/vb34i4da ... o.mp4/file](https://www.mediafire.com/file/vb34i4dafeil2xu/ffxv_need_help_video.mp4/file)
## Post #19
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2021-09-10T18:24:40+00:00
- Post Title: Re: help ripping ffxv MODELS from steam


## Post #20
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-09-10T21:07:42+00:00
- Post Title: Re: help ripping ffxv MODELS from steam

Do me a huge favor, DELETE your extra posts, merge them, always edit your last post if no one else posted after you, don't spam, its unnecessary, and for crying out loud, EDIT the post [viewtopic.php?p=177940#p177940](https://forum.xentax.com/viewtopic.php?p=177940#p177940), do NOT quote the whole thing, your making a mess.
Because of things like this for the most part many refuse to help, be aware of your actions and always pay attention, don't rush.
## Post #21
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-09-12T04:54:30+00:00
- Post Title: Re: help ripping ffxv MODELS from steam

Ok so i will post this here so others will learn.

> Reply from neonvegaSun Sep 12, 2021 11:42 am at Sun Sep 12, 2021 11:42 am
>
> 
well I did the 2nd extraction can you plz look at the video to see where I went wrong I did your tutorial like 4x the last one I took a small vid of it to show the process of what i was doing on my channel I posted Im not giving up I really desire to learn...
Delete what ever you have extracted and start fresh.
On step 3 you messed up:



error.PNG (172.09 KiB) Viewed 120 times


3.Output Path: x:\YOU'R\OUTPUT\PATH\ (mind the ending BackSlash, its imperative)
By that i meant what is wrote and that is to type "YOUR OUTPUT PATH" NOT what i wrote there, meaning you have to know what HDDs you have available to extract the game assets, i do not recommend on your desktop or C drive where the operating system is.
So from your video looks like you have ONLY one HDD available besides Local Disk C and that is D drive
So your path at step 3 MUST be something like following example: D:\FFXV_ext\, again its just an example, you can make any folder you want, but keep it short.
Root refers to the base of the folder your in, in this case where the game executable is, that's the root folder.
If you do not have enough space on your D drive, as the game i think requires about 200GB for entire game do be extracted.
Just select when you go in to datas folder at step 5 only the characters folder if you only want the characters and nothing else, and then you can follow rest of tutorial.
## Post #22
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2021-09-12T23:10:51+00:00
- Post Title: Re: help ripping ffxv MODELS from steam

ok gotcha; yeah i was wondering about that too,  but i thought it was a command of sort to extract the models; well  ok will try here in a bit again and post my results thank you for your enduring attitude I promise ill get it right if you want a 50$ donation for all this send me your email I feel you deserve something for helping a noob doing all this
## Post #23
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-09-13T22:18:18+00:00
- Post Title: Re: help ripping ffxv MODELS from steam

> Reply from neonvega ↑Mon Sep 13, 2021 7:10 am at Mon Sep 13, 2021 7:10 am
>
> ...if you want a 50$ donation for all this send me your email I feel you deserve something for helping a noob doing all this
I am NOT in to all that (thats what the thumbs up/like button is for), buy the game, support the developers.
And if you say you learnt quite a bit, how about do what i mentioned before, edit your whole quoted post, etc, it is messy
