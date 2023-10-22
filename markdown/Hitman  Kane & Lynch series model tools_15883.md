## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-16T20:26:24+00:00
- Post Title: Hitman / Kane & Lynch series model tools

Hitman Absolution, Sniper Challenge archive/model/texture tools.

1. Drop .pc_resourcelib onto Hitman5.exe. It will extract all resources from it. Corresponding .pc_headerlib files must be in the same dir. The tool will search all .pc_headerlib files for needed information.

2. Drop .TEXT file onto Hitman5DDS.exe. It will convert all textures to DDS or TGA.

3. Drop .BORG file onto Hitman5Model.exe. Corresponding .PRIM file must be there too. <BORG>/<PRIM> files will be near each other (in pairs). This will produce SMD model with skeleton and all lods. You can separate them by materials. Later I will maybe make an option to skip low lods or something.

Cloth support (model tool). If some .CLOS files will be there too, they will be converted to static .OBJ files with cloth geometry. Cloth driver will be present in a main SMD model. This driver will have weights and move with the skeleton. You should be able to apply driver movements to actual cloth model after that. Note: The geometry generation algorythm was not completely reversed so some minor errors may appear. 

Sniper Challenge separate archive/model tools are used same way as for absolution, textures can be extracted with Hitman5DDS.

Currently the tool will ONLY unpack segments if some skeletal models will be there. This is only about 300 packages from all 5000 (according to headers). So if you run it on all of them, 300 folders will be created. After that, you can find the model name in MATI files as material name will include it.


[hitman5.rar](https://xentaxbackup.github.io/file/12736_hitman5.rar)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-16T20:26:55+00:00
- Post Title: Hitman / Kane & Lynch series model tools

Hitman 4 (Blood Money), Kane & Lynch 2 model tools.

Usage: Drop .PRP file onto the tool or use command line, .PRM file must be in the same dir.

The tool only currently unpacks animated characters, and not all of them work. Mostly human models. Each model can be repeated with variations or without, because of game files structure. One model usually will contain many clothes variations. Filename includes material number followed by model variation.


[hitman4.rar](https://xentaxbackup.github.io/file/12501_hitman4.rar)
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-16T20:27:31+00:00
- Post Title: Hitman / Kane & Lynch series model tools

Hitman 2/3  models.

Usage: Drop .PRM file onto the tool or use command line, .GMS file must be in the same dir.

I had no time to reverse their properties tree, so the tool only currently unpacks animated characters, like humans, pigs, rats, birds etc. The possible names are dumped into names.txt file.



Hitman 1 tools here: [viewtopic.php?f=16&t=15695](http://forum.xentax.com/viewtopic.php?f=16&t=15695)
[hitman2_3.rar](https://xentaxbackup.github.io/file/12500_hitman2_3.rar)
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-18T13:59:08+00:00
- Post Title: Hitman / Kane & Lynch series model tools

Hitman 4 / Kane & Lynch 2 tools posted.
## Post #5
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-02-19T02:19:13+00:00
- Post Title: Hitman / Kane & Lynch series model tools

Oh my god. I didn't think Hitman would ever get modeling tools and we'd be stuck with .obj rips and fan rigs. Time to get to work downloading these games.
## Post #6
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2017-02-19T06:33:10+00:00
- Post Title: Hitman / Kane & Lynch series model tools

This is awesome!

Seems like UV's are Vert Flipped on some models?

If source was published could this eventually lead to geometry mods for Blood Money?

Also if it's not too much trouble would it be possible to get a obj or FBX version as well?
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-19T06:57:44+00:00
- Post Title: Hitman / Kane & Lynch series model tools

obj tool for hitman 4 existed for 10 years, made in 2006.

And I'm never working with fbx because its very unstable and non-standard format.

> Reply from hhchunter
>
> could this eventually lead to geometry mods?

Geometry formats are mostly simple. So yes, modding is very possible.
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-23T14:03:46+00:00
- Post Title: Hitman / Kane & Lynch series model tools

Hitman 2/3 tools posted. 

Hitman 4 tools updated: skeletons mirrored to correct right handed coordinate system. Normals added.

So now all hitmans from 1 to 4 are covered. Only absolution left. Will be ready soon.
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-25T20:15:00+00:00
- Post Title: Hitman / Kane & Lynch series model tools

ok i have very good progress on all variations of glacier engine, so I will probably be able to get all models with skeletons and proper names for Absolution, and probably for 2016 game too.
## Post #10
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-02-25T20:21:28+00:00
- Post Title: Hitman / Kane & Lynch series model tools

Looking good! From the professional point of view it's also nice to have all the LODs of the game model. I hope you willing to lying your hands on the items/vehicles/static as well — they're great in the last 2 games.
## Post #11
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-25T23:44:27+00:00
- Post Title: Hitman / Kane & Lynch series model tools

> Reply from daemon1
>
> ok i have very good progress on all variations of glacier engine, so I will probably be able to get all models with skeletons and proper names for Absolution, and probably for 2016 game too.

For what it's worth, I already created a model converter for Hitman 2016. But I didn't bother with weights and skeletons, so if you add that, would be nice.  If you can read python, my script will probably help you a lot with the format. It's quite close to Deus Ex: Mankind Divided since they use the same engine. That's why I always try to release source code, so others can learn and improve for the benefit of all 

[viewtopic.php?p=126983#p126983](http://forum.xentax.com/viewtopic.php?p=126983#p126983)
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-26T06:20:07+00:00
- Post Title: Hitman / Kane & Lynch series model tools

> Reply from volfin
>
> I already created a model converter for Hitman 2016.
Yes I know, but my main point is to add skeletons and sort everything out with names, and this is completely absent in your script as we know.

I can read python, but from my experience, its usually easier to research the format myself, than read someone else's code. Especially considering the fact, that I already researched Absolution and it seems completely the same as 2016.
## Post #13
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-26T16:29:15+00:00
- Post Title: Hitman / Kane & Lynch series model tools

No problem.
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-26T17:43:14+00:00
- Post Title: Hitman / Kane & Lynch series model tools

Actually sometimes I can't understand even my own code after a while. It's just like I better grasp the data than the code.

Absolution tools posted in the thread start.
## Post #15
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-02-26T19:34:22+00:00
- Post Title: Hitman / Kane & Lynch series model tools

Thank you for the new tools. A couple questions:

-That's a LOT of files to go through. Any way to find out what's what without going through the whole process?
-Is there a way to convert textures?

EDIT: Referring to Absolution
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-26T20:01:16+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from ssringo
>
> Thank you for the new tools. A couple questions:

-That's a LOT of files to go through. Any way to find out what's what without going through the whole process?
-Is there a way to convert textures?

EDIT: Referring to Absolution

Currently the tool will ONLY unpack segments if some skeletal models will be there. This is only about 300 packages from all 5000 (according to headers). So if you run it on all of them, 300 folders will be created. At least I hope so, because I don't have the game, only 2 files I was provided.

After that, you can find the model name in MATI files as material name will include it.

Textures probably can be converted with 2016 game tool. If not, let me know.
## Post #17
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2017-02-27T11:11:16+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from daemon1
>
> sort everything out with names, and this is completely absent in your script as we know.

> Reply from daemon1
>
> you can find the model name in MATI files as material name will include it

I think they're also stored else where as well, and they might not all be present.

From my understanding it should be easier to do this for Absolution than HITMAN. Absolution has finished development & support now, so changes to the archives/files are minimal.

Getting file names would require to my knowledge, getting hashes from the game files once extracted?
Some of which are stored in files extracted, which you can find with a string search of "[assembly:/"

Then creating some sort of list and matching it to the HashID?
I'm not sure how you would go about matching the filenames to the hashID's in the archive however.

Either way I think naming the files might have to be done in the original QuickBMS script or a whole brand new tool altogether like you proposed.

Looking forward to what you come up with if you decide to go ahead with it.
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-27T15:49:01+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from hhchunter
>
> I think they're also stored else where as well
No, they are NOT.

I've researched all hitman games from 1 to 6 (2016) and I'm telling you: glacier engine does not need names, so they are not present in game files. It was like that in all their games. Let me give you an example:

There are 2 guards on a level. Each of them stored in properties tree of the level with its own position (x,y,z) and links to model, animation set, behavior script etc.

So these 2 guards may have absolutely different models (with no names), and the same animations and scripts. So there's no way to give them names, other that "1" and "2".

But in every game there are some clues that can be used to name models. In hitman 4 I used animation names, as they were more descriptive than script names. Like "scientist" or "SWAT". In 2&3 I just dropped all animation/script names in a text file for you to choose. In hitman 1 I used folder names. Notice that everything above (folders, anims, scripts) may be the same for different models, so this is only a clue, not an exact name.

Now to present time.

The main problem in absolution was to split packages into sections, such as models and textures. And I was able to do this. Now in 2016 its the opposite: I need to connect sections into packages, so you can tell which textures go with which model. This info is stored in properties tree. I've seen this a year ago when I first researched the new game.

> Reply from hhchunter
>
> a string search of "[assembly:/"
Yes, but assembly names for all 5000 main game packages look like: 
[[assembly:/Common/PC.layoutconfig].pc_layoutdef](0645).pc_resourcelib
which is not a very descriptive name, right?

So for Absolution and 2016 games, material names are really the best chance to identify models. And this is already done for Absolution.
## Post #19
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-27T17:42:33+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Interesting, I'll have to see if that applies to Deus Ex as well, it uses Glacier and it desperately needs filenames.
## Post #20
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2017-02-28T02:55:11+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from daemon1
>
> hhchunter wrote:I think they're also stored else where as well
No, they are NOT.

I've researched all hitman games from 1 to 6 (2016) and I'm telling you: glacier engine does not need names, so they are not present in game files. It was like that in all their games. Let me give you an example:

There are 2 guards on a level. Each of them stored in properties tree of the level with its own position (x,y,z) and links to model, animation set, behavior script etc.

So these 2 guards may have absolutely different models (with no names), and the same animations and scripts. So there's no way to give them names, other that "1" and "2".

But in every game there are some clues that can be used to name models. In hitman 4 I used animation names, as they were more descriptive than script names. Like "scientist" or "SWAT". In 2&3 I just dropped all animation/script names in a text file for you to choose. In hitman 1 I used folder names. Notice that everything above (folders, anims, scripts) may be the same for different models, so this is only a clue, not an exact name.

Now to present time.

The main problem in absolution was to split packages into sections, such as models and textures. And I was able to do this. Now in 2016 its the opposite: I need to connect sections into packages, so you can tell which textures go with which model. This info is stored in properties tree. I've seen this a year ago when I first researched the new game.
hhchunter wrote:a string search of "[assembly:/"
Yes, but assembly names for all 5000 main game packages look like: 
[[assembly:/Common/PC.layoutconfig].pc_layoutdef](0645).pc_resourcelib
which is not a very descriptive name, right?

So for Absolution and 2016 games, material names are really the best chance to identify models. And this is already done for Absolution.

Ah miss-understanding. I thought you meant the actual proper filenames, instead of the Material ID such as "shotgun_stealth_a_receiver_a.mi"

I was thinking in terms of all the filenames, for things beyond just models.
## Post #21
- Username: YourImaginaryFriend
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Mar 14, 2016 5:57 pm
- Post datetime: 2017-03-01T06:26:46+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Thank you for the tools. Finally being able to obtain these models with good weighting and correct scale is quite impressive.

There are some issues I discovered while messing with them:

- UVs have incorrect scale/position in some cases. Arms seem to be a common example



- Sanchez's rigging ended up bugged, compared to others




- Some physics-enabled meshes (jackets, Victoria's hair) are missing.

Example files: [http://www3.zippyshare.com/v/qojhi12M/file.html](http://www3.zippyshare.com/v/qojhi12M/file.html)
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-01T15:36:32+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from YourImaginaryFriend
>
> Some physics-enabled meshes (jackets, Victoria's hair) are missing.

That's because they are not present in the mesh. They are probably stored in special cloth containers. Will need to be researched if its possible to convert them.
## Post #23
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-02T05:33:34+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

This may seem like a noob question, but how do I go about removing the excess lower LOD meshes. They all appear to be connected, but I can't figure out how to separate things to get to the best quality model parts.
[Capture.JPG](https://xentaxbackup.github.io/file/12547_Capture.JPG)
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-02T15:39:56+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from trexjones
>
> how do I go about removing the excess lower LOD meshes

In blender you can:
select model, go to EDIT mode (tab)
press "P" and click "by material"

this will split the model into submeshes 

p.s. tools will be updated soon with texture converter and better model support.
## Post #25
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-03T03:38:45+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from daemon1
>
> trexjones wrote:how do I go about removing the excess lower LOD meshes

In blender you can:
select model, go to EDIT mode (tab)
press "P" and click "by material"

this will split the model into submeshes 

p.s. tools will be updated soon with texture converter and better model support.

Ah! Fantastic! I was just trying to figure out the 2016 texture tool for this...! Looking forward to it! Thanks again, man!
## Post #26
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-11T16:10:12+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

for interested here's something usefull to handle the original game unpacked archives

edit: it's for absolution


 model_sorter_v0.1.cmd.zip
(8.34 KiB) Downloaded 98 times


>[latest version of unpacker scripts here](http://forum.xentax.com/viewtopic.php?p=128638#p128638)<
## Post #27
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-03-11T18:31:48+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from Tosyk
>
> for interested here's something usefull to handle the original game unpacked archives

Which game is that for?
## Post #28
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-11T19:29:42+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from volfin
>
> Tosyk wrote:for interested here's something usefull to handle the original game unpacked archivesWhich game is that for?oh, yeah, it's for absolution.
[IMG_12032017_123908_0.jpg](https://xentaxbackup.github.io/file/12612_IMG_12032017_123908_0.jpg)
## Post #29
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-12T13:56:08+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

All Absolution tools updated.

1. Main tool. Now outputs borg/prim files with same name, so you can make batch conversion.

2. DDS tool for textures.

3. Model tool Now only takes 1 parameter: BORG. PRIM file must have same number (this is done with new main tool). UV scales must be fixed. 

I also checked Sanchez, and must say I don't see how it can be broken with my tool. This must be original game error.
## Post #30
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-13T22:23:03+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

continue working in file sorter for absolution.
[model_sorter_v0.2.cmd.zip](https://xentaxbackup.github.io/file/12623_model_sorter_v0.2.cmd.zip)
## Post #31
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-14T00:47:13+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

I hate to sound like a dummy, Tosyk, but how do I use the model sorter?
## Post #32
- Username: YourImaginaryFriend
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Mar 14, 2016 5:57 pm
- Post datetime: 2017-03-14T10:58:00+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Is there a chance of adding Sniper Challenge support? It has several models that are missing in main game, like Birdie.
## Post #33
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-14T11:04:57+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from trexjones
>
> I hate to sound like a dummy, Tosyk, but how do I use the model sorter?well,
first you need to unpack all the game archives with unpacker from the first post;
then put 'model_sorter_v0.2.cmd' into <you_hitman_game_root_folder>\runtime\ and run;
after that all (actually almost all 'cause I'm still in working on the sorter — atm 87% done) the game assets will be sorted

you can use it in unfinished state or after I finish it, anyway it shouldn't conflict.

>[latest version of unpacker scripts here](http://forum.xentax.com/viewtopic.php?p=128638#p128638)<
## Post #34
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-14T11:07:02+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from YourImaginaryFriend
>
> Is there a chance of adding Sniper Challenge support? It has several models that are missing in main game, like Birdie.so you saying that archive unpacker doesn't work with SC?
## Post #35
- Username: YourImaginaryFriend
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Mar 14, 2016 5:57 pm
- Post datetime: 2017-03-14T11:33:04+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Yes, the tool crashes
## Post #36
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-14T12:12:50+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Thanks Tosyk! 

And yeah, it's not completely compatible. I noticed a lot of the female meshes are coming out funny and not alligned properly or distorted, but Daemon's looking into it.
## Post #37
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-14T12:52:15+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from YourImaginaryFriend
>
> Yes, the tool crashesif you want SC to be supported you need to pass daemon sample files, don't you think he want to download the game just for you?

> Reply from trexjones
>
> Thanks Tosyk!
And yeah, it's not completely compatible. I noticed a lot of the female meshes are coming out funny and not alligned properly or distorted, but Daemon's looking into it.yeah, I know, he already fixed uv distortion, but my sorter-tool is beyond the processes daemon's tools do.
## Post #38
- Username: YourImaginaryFriend
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Mar 14, 2016 5:57 pm
- Post datetime: 2017-03-14T22:11:13+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

My mistake. Here are samples if needed [http://www95.zippyshare.com/v/ONrTvlGx/file.html](http://www95.zippyshare.com/v/ONrTvlGx/file.html)
## Post #39
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-15T00:47:51+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Here's final version of filesorter for absolution (PC, tested on final steam version but should work on any) I worked on. It will unpack and sort all the assets of the original game and DLCs.
how to use:
unpack all the files from h5_asset_unpacker_and_sorter.zip into <your_hitman_game_root_folder>\runtime\
put Hitman5.exe from first post into <your_hitman_game_root_folder>\runtime\
on this step you have 3 .cmd files and 1 .exe file in runtime folder;
run 01_h5_move_bad_archives.cmd — it will move all the bad (not unpackable and ones with error) .pc_resourcelib files into temp folders:
all the neccecary folders will be creaeted at this step;
wait till the process is finished;
[you should omit this step for now, do it as described here] run 02_h5_unpack_pc_resourcelib.cmd — it will find and unpack all valid .pc_resourcelib files:
you'll get a bunch of different nameless files;
wait till the process is finished;
run 03_h5_asset_sorter.cmd — it will sort all the assets so you can find them in <your_hitman_game_root_folder>\runtime\unp\
wait till the process is finished;
run 04_h5_move_bad_archives_back.cmd to move bad .pc_resourcelib files back:
wait till the process is finished;
play the game normaly.

After all the steps you can convert models and textures with the tools from first post of this thread.
Note that this process will work from <your_hitman_game_root_folder>\runtime\ folder only. Also if you moved any of the archives manually filesorter may not find them.

Many of the archives cannot be unpacked due to the Hitman5.exe archive unpacker incompleation (compleation of which is beyond my possibilities), that's why I moved them into temp directories. if they be able to be unpacked someday I will update filesorter. You can also pass not unpackable files to daemon so he can reverse them.

p.s.: Please report me on errors.
[h5_asset_unpacker_and_sorter.zip](https://xentaxbackup.github.io/file/12624_h5_asset_unpacker_and_sorter.zip)
## Post #40
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-15T15:14:12+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

I'm currently working on cloth data from Absolution. They have special cloth engine unique only for Absolution. I've seen no other game like this. Even new 2016 hitman has all clothes as usual meshes. But in Absolution, jackets, ties and other cloth meshes no NOT exist in game files. Instead, they're built on the fly with their cloth engine, using special cloth generation tables.

So even to get one, initial geometry shape for it, I will need to reproduce their cloth engine and implement it in my tool. This may take weeks or even months.
## Post #41
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-16T03:18:19+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Hey Tosyk -- I tried your new tools, but ran in to a couple of problems.

I did everything exactly as you stated, but none of the files actually got unpacked or sorted. The first cmd worked -- the move_bad_archives worked fine, but after that, all that happened was the appearance of a "unp" folder, with the animals, characters, foliage, garbage, props, vehicles, weapons folders inside, but none of the archives ended up in those folders... any idea what I might be doing wrong?
## Post #42
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-16T10:00:34+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from trexjones
>
> Hey Tosyk -- I tried your new tools, but ran in to a couple of problems.

I did everything exactly as you stated, but none of the files actually got unpacked or sorted. The first cmd worked -- the move_bad_archives worked fine, but after that, all that happened was the appearance of a "unp" folder, with the animals, characters, foliage, garbage, props, vehicles, weapons folders inside, but none of the archives ended up in those folders... any idea what I might be doing wrong?didn't you forgot to put hitman5.exe into runtime folder? can I see a screenshot of your runtime folder?
## Post #43
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-16T11:49:45+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Sure thing... Here's what it looks like...
[shot.JPG](https://xentaxbackup.github.io/file/12630_shot.JPG)
## Post #44
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-16T13:18:51+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from trexjones
>
> Sure thing... Here's what it looks like...seems like everything is correct at the screenshot. So you saying "bad" archives (.pc_resourcelib) were moved to the folders, right? Next you run second script and it return... an error or what? Is it doing something?

p.s.: is this PC version, right?
## Post #45
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-16T14:39:56+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

So, I run the unpack_pc_resoucelib.cmd and this is what comes up in response...


run2.JPG (53 KiB) Viewed 290 times



And correct the bad archives seem to go into their correct places...
## Post #46
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-16T14:45:56+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

find.JPG (54.9 KiB) Viewed 494 times

And this is what comes up when I run the asset sorter cmd...
All PC version too!



find.JPG (54.9 KiB) Viewed 494 times
## Post #47
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-16T15:30:50+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

trexjones, this is very odd. can I see screenshot of you runtime\common\pc.layoutconfig\ folder?
I check it again at home.

edit:
okay, I know what's going on. it's on the Hitman5.exe side. You probably should unpack all the archives manually.
Just put h5_unpack_pc_resourcelib.cmd along with Hitman5.exe into the folder where .pc_resourcelib you want to unpack and run the .cmd
[h5_unpack_pc_resourcelib.zip](https://xentaxbackup.github.io/file/12638_h5_unpack_pc_resourcelib.zip)
## Post #48
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-22T17:07:28+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

After 10 days of research I'm already getting something close to original cloth objects. Still need more time to make it actually working.
## Post #49
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2017-03-23T03:06:53+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from daemon1
>
> After 10 days of research I'm already getting something close to original cloth objects. Still need more time to make it actually working.

Should/Would this work with/for Deus Ex Mankind Divided?
## Post #50
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-23T04:22:49+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from hhchunter
>
> Should/Would this work with/for Deus Ex Mankind Divided?

Are there any .CLOS files in Deus Ex Mankind Divided?
## Post #51
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-03-25T09:55:22+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Awesome
I have tested your tools 

Work perfect with character models but almost crash with convert item and weapon models ;-;
## Post #52
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-03-26T13:02:03+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Um... There is some problem with character hands after converted
Can you fix it?
## Post #53
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-26T13:24:53+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

what game?
## Post #54
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-03-26T15:07:34+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Hitman Absolution, check samurai costume in mission 8, you will see
## Post #55
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-26T15:46:05+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from ngovandang
>
> Hitman Absolution

yes i know. Absolution has some issues. But now I'm working on cloths for it. Wait until I finish it. Then I can check meshes again.
## Post #56
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-03-27T01:48:51+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from daemon1
>
> 
yes i know. Absolution has some issues. But now I'm working on cloths for it. Wait until I finish it. Then I can check meshes again.
 uhm.
## Post #57
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-29T19:56:05+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

The new experimental Absolution model tool with cloth support. The geometry generation algorythm was not completely reversed so some minor errors may appear.

Usage as usual: Drop .BORG file onto Hitman5Model.exe. Corresponding .PRIM file must be there too.

But if some .CLOS files will be there too, they will be converted to static .OBJ files with cloth geometry. Cloth driver (left picture) will be present in a main SMD model. This driver will have weights and move with the skeleton. You should be able to apply driver movements to actual cloth model after that (right picture).
## Post #58
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-30T19:51:07+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

And this new version should FIX the incorectly scaled submeshes too. Like these for example


[Hitman5Model.rar](https://xentaxbackup.github.io/file/12723_Hitman5Model.rar)
## Post #59
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-03-31T14:16:51+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

XD what the heck? Original Diana model is nude?

 Thank for updated. It's fix Samurai outfit's hand
Hope you got an other solution on jackets ;o; it's hard to work with parent these OBJ files
## Post #60
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-31T14:23:40+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from ngovandang
>
> it's hard to work with parent these OBJ filesit's not if you using 3d max
## Post #61
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-31T15:11:10+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from ngovandang
>
> Hope you got an other solution on jackets

What are you talking about? This is how they are in this game. They are not like in other games (part of normal weighted mesh), they are generated by the engine.
## Post #62
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-03-31T15:13:56+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from daemon1
>
> 
What are you talking about? This is how they are in this game. They are not like in other games (part of normal weighted mesh), they are generated by the engine.
.o. Oh I see
Just forget it xD
Um... I'm having a trouble
Can you tell me which files constain 47 head textures? Default with bar code tattoo and band-aid?
## Post #63
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-31T15:40:53+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from ngovandang
>
> 
Can you tell me which files constain 47 head textures? Default with bar code tattoo and band-aid?

i have no idea
## Post #64
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-03-31T15:50:02+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from daemon1
>
> 
i have no idea
:crying:
## Post #65
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-02T11:08:34+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Sniper Challenge tools added to the first post.
## Post #66
- Username: Nightstalkery
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 17, 2014 7:14 pm
- Post datetime: 2017-06-14T15:36:49+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from daemon1
>
> Hitman 2/3  models.

Usage: Drop .PRM file onto the tool or use command line, .GMS file must be in the same dir.

I had no time to reverse their properties tree, so the tool only currently unpacks animated characters, like humans, pigs, rats, birds etc. The possible names are dumped into names.txt file.



Hitman 1 tools here: viewtopic.php?f=16&t=15695
This is truly golden. Will you ever find time for static objects though?
## Post #67
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-15T15:07:52+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from Nightstalkery
>
> Will you ever find time for static objects though?

I doubt that.
## Post #68
- Username: Nightstalkery
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 17, 2014 7:14 pm
- Post datetime: 2017-06-17T15:13:30+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from daemon1
>
> Nightstalkery wrote:Will you ever find time for static objects though?

I doubt that.
That's a real shame. It's just cloth simulated objects like Hitman's tie won't import. Guess you have to make sacrifices when it comes to such tools.
## Post #69
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-17T18:21:21+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from Nightstalkery
>
>  It's just cloth simulated objects like Hitman's tie won't import.

these are not statics. cloth is different. can you give examples?
## Post #70
- Username: boldie
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 24, 2018 10:09 pm
- Post datetime: 2018-04-26T12:56:47+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Hello. I have a question unrelated to your model extraction tools.
I'm currently researching the ways to mod hitman 2 a little.

> Reply from daemon1
>
> 
There are 2 guards on a level. Each of them stored in properties tree of the level with its own position (x,y,z) and links to model, animation set, behavior script etc.

Do you have any description for those property trees and it's format? 

My dream - a full map editor, with the ability to import new maps (like an old Edit4O7 project), is a very hard task, and seems impossible. 

I'd like to know how to search for positions of guards in the files and modify them. Also I'd like to add more guards to the level, even without patrol paths - do you think it's possible? What's more importantly, I want to extract the behaivour script of each npc and modify it, or at least extract. In hitman: c47 they are present in archives, but in h2 I only saw global variables for script and it's path (this is inside .gms files). I haven't yet found solutions to any of those problems.

I think these little things will bring some life in these old games, but I'm struggling with file format, so I'm asking for help. 

How hard it will be, to correctly implement aforementioned mods?


I pm'd you with more detailed description few days ago. Thanks in advance!!
## Post #71
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-26T15:38:08+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from boldie
>
> Hello. I have a question unrelated to your model extraction tools.
i dont have time to look into that, and i dont remember anything about hitman now
i worked with dozens of games after that, you have to understand
## Post #72
- Username: boldie
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 24, 2018 10:09 pm
- Post datetime: 2018-04-26T20:04:26+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from daemon1
>
> boldie wrote:Hello. I have a question unrelated to your model extraction tools.
i dont have time to look into that, and i dont remember anything about hitman now
i worked with dozens of games after that, you have to understand

That's fine. I realize it's a bit different topic, but I didn't find any more info about scripts other than your post. But if you can, and will find time, it would be cool if you can upload subproduct of your hitman research like notes on format... because at my current level I don't understand even about property tree
## Post #73
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-26T20:16:48+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from boldie
>
>  it would be cool if you can upload subproduct of your hitman research like notes on format...
I'm not making any notes on formats. Also I dont need IDA or any other disassembler to reverse game code. Looking into code in case of simple formats like hitman is a waste of time. All was done by analysing of data files themselves.
## Post #74
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-08-03T15:38:31+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Whenever I try to unpack the Hitman: Absolution files (using a batch script I created that runs it on all files), I keep getting the error "Can't find header for given resource". This repeats for almost all files, leaving only 20 or so folders. Inside the folders, the .MATI files don't have the name, instead having random numbers like 0025.
## Post #75
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-03T16:59:30+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

i dont think the game was updated in last year
it means either some files are missing, or your script is wrong
must be about 300 folders after extraction
## Post #76
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-08-03T18:39:27+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

If it matters, I'm using a cracked copy, but would having a legit version work? Because I might just buy it off Steam (it's cheap).
## Post #77
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-03T19:27:30+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

should work on all versions
## Post #78
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-08-03T20:24:15+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Just bought the game for $3. Still getting the same error.

Batch script:

```
	Hitman5.exe "%%A"
	) 
pause
```


EDIT: Fixed it by following the instructions here: [viewtopic.php?p=128691#p128691](http://forum.xentax.com/viewtopic.php?p=128691#p128691)
## Post #79
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2019-03-02T11:57:55+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

How do i get the textures out for Hitman 3?
They don't come out with the models when dropping the PRM onto the tool
## Post #80
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-03-02T13:03:10+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

i dont remember, they were extracted by some other tool (not mine)
hope someone who used my tools can answer
## Post #81
- Username: impala97
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 09, 2019 8:50 pm
- Post datetime: 2019-09-09T13:12:46+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Hi, I've been messing with HBM files and I want to know if there is a way to pack everything back
## Post #82
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-06-22T01:58:50+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from daemon1 ↑Fri Feb 17, 2017 4:26 am at Fri Feb 17, 2017 4:26 am
>
> 
Hitman 4 (Blood Money), Kane & Lynch 2 model tools.

Usage: Drop .PRP file onto the tool or use command line, .PRM file must be in the same dir.

The tool only currently unpacks animated characters, and not all of them work. Mostly human models. Each model can be repeated with variations or without, because of game files structure. One model usually will contain many clothes variations. Filename includes material number followed by model variation.

Not sure if I'm dong something wrong or not but in M05 (Mission: A New Life) his suit is open, however when I extract Hitman's model from it and import smd into Blender his tie is missing. Is this an error on my part or the tool? Or his tie is somewhere else?
## Post #83
- Username: EveryCafe44
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 14, 2021 4:01 am
- Post datetime: 2021-08-07T14:19:15+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

I was sent here by TSelman61 over at DA. But I was hoping to find a way to get a few in game absolution posters at the vixen club! Why them specifically is for a project over at a wiki. I've been trying to find tools so I could possible extract these in-game posters and then make them a JPG but to no avail. I'm actually at a loss! I will try this as soon as I can.
## Post #84
- Username: Vogelez
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 19, 2021 10:57 pm
- Post datetime: 2021-12-19T15:09:08+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

hi, could anyone explain why Hitman2.exe and Hitman3.exe crushes in 1 second after I open it? I want to try redo 3d-models in Contracts game. Thx.
## Post #85
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-12-19T15:38:26+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from Vogelez ↑Sun Dec 19, 2021 11:09 pm at Sun Dec 19, 2021 11:09 pm
>
> 
hi, could anyone explain why Hitman2.exe and Hitman3.exe crushes in 1 second after I open it? I want to try redo 3d-models in Contracts game. Thx.

this is because you dont read how to use them
## Post #86
- Username: Vogelez
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 19, 2021 10:57 pm
- Post datetime: 2021-12-20T14:04:23+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Ye, u right, sry for carelessness. My english is not prefect at all. Is there any tutorial or options how to change , for example, 3d models in one Hitman Contracts level to another? For example, like make biker guards and civilians in Meat King party like it was in BETA preview?
## Post #87
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-12-20T14:11:40+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from Vogelez ↑Mon Dec 20, 2021 10:04 pm at Mon Dec 20, 2021 10:04 pm
>
> 
Is there any tutorial or options how to change , for example, 3d models in one Hitman Contracts level to another?
i don't know if any of such things exist
## Post #88
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2021-12-22T11:58:58+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Exist there any maptool for any hitman?
## Post #89
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-05-10T16:01:08+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from Tosyk ↑Wed Mar 15, 2017 8:47 am at Wed Mar 15, 2017 8:47 am
>
> 
Here's final version of filesorter for absolution (PC, tested on final steam version but should work on any) I worked on. It will unpack and sort all the assets of the original game and DLCs.
how to use:
unpack all the files from h5_asset_unpacker_and_sorter.zip into <your_hitman_game_root_folder>\runtime\
put Hitman5.exe from first post into <your_hitman_game_root_folder>\runtime\
on this step you have 3 .cmd files and 1 .exe file in runtime folder;
run 01_h5_move_bad_archives.cmd — it will move all the bad (not unpackable and ones with error) .pc_resourcelib files into temp folders:
all the neccecary folders will be creaeted at this step;
wait till the process is finished;
[you should omit this step for now, do it as described here] run 02_h5_unpack_pc_resourcelib.cmd — it will find and unpack all valid .pc_resourcelib files:
you'll get a bunch of different nameless files;
wait till the process is finished;
run 03_h5_asset_sorter.cmd — it will sort all the assets so you can find them in <your_hitman_game_root_folder>\runtime\unp\
wait till the process is finished;
run 04_h5_move_bad_archives_back.cmd to move bad .pc_resourcelib files back:
wait till the process is finished;
play the game normaly.

After all the steps you can convert models and textures with the tools from first post of this thread.
Note that this process will work from <your_hitman_game_root_folder>\runtime\ folder only. Also if you moved any of the archives manually filesorter may not find them.

Many of the archives cannot be unpacked due to the Hitman5.exe archive unpacker incompleation (compleation of which is beyond my possibilities), that's why I moved them into temp directories. if they be able to be unpacked someday I will update filesorter. You can also pass not unpackable files to daemon so he can reverse them.

p.s.: Please report me on errors.

Even though I followed this guide exactly and did the step 2 part as shown in the other post I keep getting a bunch "Can't find header for given resource" when I run the unpack tool. What do i do?
## Post #90
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2022-05-10T16:55:11+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from FWhyKay ↑Wed May 11, 2022 12:01 am at Wed May 11, 2022 12:01 am
>
> 
Tosyk wrote: ↑Wed Mar 15, 2017 8:47 am
Here's final version of filesorter for absolution (PC, tested on final steam version but should work on any) I worked on. It will unpack and sort all the assets of the original game and DLCs.
<...>

Even though I followed this guide exactly and did the step 2 part as shown in the other post I keep getting a bunch "Can't find header for given resource" when I run the unpack tool. What do i do?unfortunately turned out that everyone have their own hashes, so it's impossible to predict the filenames which this method is based on.
## Post #91
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-05-14T18:07:30+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from Tosyk ↑Wed May 11, 2022 12:55 am at Wed May 11, 2022 12:55 am
>
> 
FWhyKay wrote: ↑Wed May 11, 2022 12:01 am
Tosyk wrote: ↑Wed Mar 15, 2017 8:47 am
Here's final version of filesorter for absolution (PC, tested on final steam version but should work on any) I worked on. It will unpack and sort all the assets of the original game and DLCs.
<...>

Even though I followed this guide exactly and did the step 2 part as shown in the other post I keep getting a bunch "Can't find header for given resource" when I run the unpack tool. What do i do?
unfortunately turned out that everyone have their own hashes, so it's impossible to predict the filenames which this method is based on.

Huh that's weird...can you explain what you mean by, "everyone has their own hashes"? Are you saying everyone's copy of the game somehow has different files or something?
## Post #92
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2022-05-14T21:02:41+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from FWhyKay ↑Sun May 15, 2022 2:07 am at Sun May 15, 2022 2:07 am
>
> 
Tosyk wrote: ↑Wed May 11, 2022 12:55 am
FWhyKay wrote: ↑Wed May 11, 2022 12:01 am

Even though I followed this guide exactly and did the step 2 part as shown in the other post I keep getting a bunch "Can't find header for given resource" when I run the unpack tool. What do i do?
unfortunately turned out that everyone have their own hashes, so it's impossible to predict the filenames which this method is based on.


Huh that's weird...can you explain what you mean by, "everyone has their own hashes"? Are you saying everyone's copy of the game somehow has different files or something?sorry, but yes, everyone could have own hashes for game files
## Post #93
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-05-30T16:27:17+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from daemon1 ↑Fri Feb 17, 2017 4:26 am at Fri Feb 17, 2017 4:26 am
>
> 
Hitman 4 (Blood Money), Kane & Lynch 2 model tools.

Usage: Drop .PRP file onto the tool or use command line, .PRM file must be in the same dir.

The tool only currently unpacks animated characters, and not all of them work. Mostly human models. Each model can be repeated with variations or without, because of game files structure. One model usually will contain many clothes variations. Filename includes material number followed by model variation.

Blood Money tool does not extract 47's tie or anything with cloth physics:



Please fix this.
## Post #94
- Username: GIZZY
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 25, 2020 1:58 am
- Post datetime: 2022-08-31T22:20:35+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Hi I was wondering if there was a way to get the textures out of Kane & Lynch 2? I can't seem to find a tool that does so.
## Post #95
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2022-09-01T07:42:42+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from GIZZY ↑Thu Sep 01, 2022 6:20 am at Thu Sep 01, 2022 6:20 am
>
> 
Hi I was wondering if there was a way to get the textures out of Kane & Lynch 2? I can't seem to find a tool that does so.you can only rip them, unfortunately.
## Post #96
- Username: whynotll83
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 19, 2019 4:30 pm
- Post datetime: 2022-09-01T23:01:57+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

There is a tool to extract absolution textures, why is there not a tool for kane and lynch 2 textures? dragging the file to hitman5dds doesn't work.
knl2.exe only extracts models.
## Post #97
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2022-09-02T07:38:23+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from whynotll83 ↑Fri Sep 02, 2022 7:01 am at Fri Sep 02, 2022 7:01 am
>
> 
There is a tool to extract absolution textures, why is there not a tool for kane and lynch 2 textures? dragging the file to hitman5dds doesn't work.
knl2.exe only extracts models.there will be no updates, I'm afraid. We have to deal with what we have.
## Post #98
- Username: Pablo1989
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 29, 2018 12:07 am
- Post datetime: 2022-12-20T23:42:24+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Hello

Can somebody tell me how rip Hitman 2: Silent Assasin sceneries?
Because i saw this
[https://www.deviantart.com/lezisell/art ... -327089587](https://www.deviantart.com/lezisell/art/Hitman-2-Gontranno-monastery-327089587)

Mainly I would care about those from the Anathema mission.
## Post #99
- Username: playfdg
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 14, 2022 9:27 pm
- Post datetime: 2023-02-24T16:34:33+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from Pablo1989 ↑Wed Dec 21, 2022 7:42 am at Wed Dec 21, 2022 7:42 am
>
> 
Hello

Can somebody tell me how rip Hitman 2: Silent Assasin sceneries?
Because i saw this
https://www.deviantart.com/lezisell/art ... -327089587

Mainly I would care about those from the Anathema mission.

Did you find out how to do this?
## Post #100
- Username: Shynn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 29, 2018 10:13 pm
- Post datetime: 2023-03-08T08:56:52+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from playfdg ↑Sat Feb 25, 2023 12:34 am at Sat Feb 25, 2023 12:34 am
>
> 
Pablo1989 wrote: ↑Wed Dec 21, 2022 7:42 am
Hello

Can somebody tell me how rip Hitman 2: Silent Assasin sceneries?
Because i saw this
https://www.deviantart.com/lezisell/art ... -327089587

Mainly I would care about those from the Anathema mission.


Did you find out how to do this?

It worked with Ninjaripper but it was the disorder on Blender ^^
Someone have a solution ? An other extractor or solution to organize the scene on BLENDER ?
Ty
## Post #101
- Username: pavle
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 28, 2019 2:50 pm
- Post datetime: 2023-07-05T17:31:33+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from daemon1 ↑Thu Mar 23, 2017 1:07 am at Thu Mar 23, 2017 1:07 am
>
> 
After 10 days of research I'm already getting something close to original cloth objects. Still need more time to make it actually working.

I converted whole CLOS from Hitman Absolution to XML: [https://pastebin.com/RKJcVW2D](https://pastebin.com/RKJcVW2D) and I refactored decompiled code from your Hitman5Model app: [https://pastebin.com/vRs7vz7j](https://pastebin.com/vRs7vz7j)
Can you exaplain me what are you doing in that code and what are binding offsets and why you use only 6 binding offsets instead of 16 (<ARRAY name="bindingOffsets" array_type="ARRAY" array_primitiveCount="16" array_count="27008">) from each row?
## Post #102
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-08T06:40:01+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

> Reply from pavle ↑Thu Jul 06, 2023 1:31 am at Thu Jul 06, 2023 1:31 am
>
> 
Can you exaplain me what are you doing in that code
I dont remember
## Post #103
- Username: indianaliam1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 31, 2022 9:35 am
- Post datetime: 2023-07-13T16:17:25+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

hey ok funny story but does any of this stuff work for kane and lynch dead men? the second game already had most of it's character models ripped out but dead men is only preserved in the form of fucking gmod ragdolls on garrysmods.org (no, seriously)

will the blood money one work on dead men or was the guy making the tools just not interested in the first kane and lynch at all
## Post #104
- Username: deathstorm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 25, 2022 1:03 am
- Post datetime: 2023-08-12T21:29:06+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Hi, i know it's been a while since these tools were updated but i'd like to ask if you're going to work on them any further ? It would've been great if these tools were able to extract static models such as vehicles and guns. Also, i'm pretty sure i've seen Ballers SD model from H2SA in one of the Hitman: The Hitting videos on YT, and i'd like to know if there are any other tools that can extract gun models. Anyways thank you for these awesome programs.
## Post #105
- Username: Nevox
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 27, 2022 2:36 am
- Post datetime: 2023-10-13T19:00:25+00:00
- Post Title: Re: Hitman / Kane & Lynch series model tools

Hi i have flollow all the steps for extract models but cannot find all the models only a parts if still work in 2023?
