## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-19T20:33:37+00:00
- Post Title: Horizon Zero Dawn

Horizon Zero Dawn tools. 

Tool with animation support (2 versions) published below - [viewtopic.php?p=151255#p151255](https://forum.xentax.com/viewtopic.php?p=151255#p151255) and [viewtopic.php?p=151411#p151411](https://forum.xentax.com/viewtopic.php?p=151411#p151411)

Tool for PC - [viewtopic.php?p=167228#p167228](https://forum.xentax.com/viewtopic.php?p=167228#p167228)









Extracting resources:
===============================================================
0. you need oo2core_5_win64.dll in the same folder with the tool
Its in almost any big game now, easy to find. Probably other versions will work too, if you rename them

1. you need to place the tool in your "packed_pink" horizon folder, or better, i recommend using included ini file (just change your folder). If you use this INI  - you can use the tool from any folder.
Note: remove PATCH.BIN from the folder, or the tool will crash

2. first thing you need to extract is resource list.
To do this, just run the tool. It will create a text file list. I recommend sorting this list  so you can make better selections of what you want to extract. I sort it in excel. It also allows to make filters in it

3. if you want to extract some resource, run
horizon /e resourcename

4. for batch extract, create a text file with a list of what you want to extract, and run
horizon /x list.txt

5. horizon /p list.txt - same as /x, but dump files with directory structure
===============================================================


Convertion:
===============================================================
Now after you extract some res, converting is simple.
Just drag resource of the EXE and it will:
- extract model if res has models
- extract textures if it has textures
- extract skeletons if it has skeletons


Extracting characters with skeleton:
===============================================================
1. place all parts of a character in one folder, and run horizon on all of them
2. a file called "matrices" will be created and UPDATED in the process with all the bone matrices present in all parts
3. put corresponding skeleton file to the same folder and run horizon on it
4. copy-paste skeleton into model parts so they will be complete working models
===============================================
important warning! if you plan to export another model after that, DELETE that "matrices" file before doing it, or this will lead to a complete mess!


Extracting robots
===============================================================
This is most complicated thing. Unlike characters, they have destructible parts, and these parts are connected to animation skeleton. This means, to get model fully working, 4 sources are required:

- matrices from mesh parts (same as characters)
- mesh skeleton (same as characters)
- animation skeleton (ragdoll)
- robot helper bones

you need to place all these files in the same folder:

1. mesh parts usually contained in /animation/parts/ folder
2. half of robots have 2 skeleton files: mesh_skeleton_rootbone & skeleton_rootbone
you need mesh_skeleton_rootbone
3. ragdoll is in robot template file from entities/characters/robots/templates/archetypes/ folder
4. each robot has a file called robot_modelhelpers - this one contains helper bones info

Once you have all these, you can start with convertion

step 1:
Run horizon on all parts files. This will create matrices as it was before

step 2:
Run horizon on template file. This will extract animation skeleton from it.
(you dont need ascii and smd files generated, delete them. They are only useful if you want to experiment with animation only)
So you have .animskel file now in the same folder.

step 3: run this:
horizon [mesh_skeleton] [animskel] > a.bat
this will create FULL robot skeleton both in SMD & ASCII and also A.BAT file

-------------------------
At this time you have info which robot parts are destructibles, and which are normal weighted meshes. You need to treat them differently from now on. Destructibles will be static meshes, and they are all listed in A.BAT file. All others are normal weighted meshes.
You can already use normal weighted meshes as before, but for destructibles you need to perform additional step 4.
-------------------------

step 4:
Open A.BAT file, and replace all "_helper" strings with ".core". This probably could be done automatically on export, but the thing is, I'm not sure all helper bones will always be called the same as helper MESHES. So I'm leaving this to the users at least for now.
Run this .BAT file.

-------------------------
Now after running this file, if there were no errors, you will have all destructible parts property placed and weighted to correct bones.
Note: sometimes there will be destructible parts missing. This means helper bones were created for them, but later the devs decided not to have them in game.
-------------------------

to load all destructible parts as one file:
========================================================
Merge all ASCII files into one as text file, then copypaste skeleton into it.
Then count submeshes (it will correspond to number of "material" string)
and put a number of submeshes after the skeleton (before all the actual data).
This number will correspond to number of "material" string in all files.
Same for SMD files, just no need to count submeshes.
[horizon.rar](https://xentaxbackup.github.io/file/14144_horizon.rar)
## Post #2
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2018-02-20T02:32:35+00:00
- Post Title: Horizon Zero Dawn

> Reply from daemon1
>
> Horizon Zero Dawn tools will be posted here after some testing.
Files for the game are already published on the net.

another great job, congratulations!

where can I download the game's files from?
## Post #3
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-02-20T16:28:15+00:00
- Post Title: Horizon Zero Dawn

Эх, как всегда радуешь нас своими работами, спасибо тебе за возможность извлечь модельки из главных эксклюзивов PS4.
Теперь осталось лишь обзавестись дампами этой игры.
И дождаться релиза Horizon Zero Dawn tools.
## Post #4
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-02-20T17:09:38+00:00
- Post Title: Horizon Zero Dawn

Can you publish your tools for the PS4 along with the source code? I would like to know a couple of points, for example, algorithm of convert textures?
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-21T15:21:16+00:00
- Post Title: Horizon Zero Dawn

> Reply from amzerof6
>
> daemon1 wrote:where can I download the game's files from?
check the usual places where you can get PS4 files
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-21T15:21:44+00:00
- Post Title: Horizon Zero Dawn

> Reply from Crazy31139
>
> Теперь осталось лишь обзавестись дампами этой игры.
Ну с этим проблем быть не должно, всё уже на торрентах
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-21T15:22:55+00:00
- Post Title: Horizon Zero Dawn

> Reply from erik945
>
> Can you publish your tools for the PS4 along with the source code? I would like to know a couple of points, for example, algorithm of convert textures?
No. PS4 texture swizzling was known for some time already, you can see it in other people's tools with source code
## Post #8
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2018-02-22T09:42:59+00:00
- Post Title: Horizon Zero Dawn

> Reply from daemon1
>
> Horizon Zero Dawn tools will be posted here after some testing.
Files for the game are already published on the net.

Video showing the process of destructible parts placing: https://youtu.be/rsbwOuqor3c

daemon1,да ты просто герой!!:) С ума сойти модели из Zero Dawn. День стал намного лучше:)
## Post #9
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2018-02-26T19:32:48+00:00
- Post Title: Horizon Zero Dawn

It would be most amazing if you can support animation for this game. This game has the best.

Thanks

Ps. please let us know when your tools are avail. I'd love to try them.
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-27T16:23:33+00:00
- Post Title: Horizon Zero Dawn

> Reply from UberBlack
>
> It would be most amazing if you can support animation for this game
I don't think it will be possible
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-28T16:14:25+00:00
- Post Title: Horizon Zero Dawn

> Reply from UberBlack
>
> It would be most amazing if you can support animation for this game.
On a second thought, it looks like they are using morpheme, an animation engine I already reversed before. And it means it will probably be possible to extract.
## Post #12
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2018-03-01T03:56:08+00:00
- Post Title: Horizon Zero Dawn

> Reply from daemon1
>
> UberBlack wrote:It would be most amazing if you can support animation for this game.
On a second thought, it looks like they are using morpheme, an animation engine I already reversed before. And it means it will probably be possible to extract.

WOW, that's amazing news. I didn't know you reversed morpheme. There is a lot of cool games with great animation that use this system.

I can't wait to test your blender plugin.
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-01T15:48:19+00:00
- Post Title: Horizon Zero Dawn

> Reply from UberBlack
>
> WOW, that's amazing news. I didn't know you reversed morpheme.
Yes, I did that almost 2 years ago. There were very few comments, so I thought nobody needed that. Check out this list of my works, its outdated, but still... [viewtopic.php?f=16&t=14970](http://forum.xentax.com/viewtopic.php?f=16&t=14970)

> Reply from UberBlack
>
> I can't wait to test your blender plugin.
I never make blender plugins. I export to universal formats so you can import into maya, 3ds, blender, or any other program or convert with noesis to any other format.
## Post #14
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2018-03-01T17:26:45+00:00
- Post Title: Horizon Zero Dawn

Perfect. Thanks for the thread, I will test your plugin. I have been looking for something like this for a long time. Thanks for all your work on it.
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-01T19:58:53+00:00
- Post Title: Horizon Zero Dawn

Ok here we go, animations are working 

[https://youtu.be/jWPuixyQLmc](https://youtu.be/jWPuixyQLmc)
## Post #16
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2018-03-01T23:16:47+00:00
- Post Title: Re: Horizon Zero Dawn

Wow, that's super. Thanks. When do you think we can play with it?
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-02T15:53:16+00:00
- Post Title: Re: Horizon Zero Dawn

its hard to say
## Post #18
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2018-03-05T01:19:27+00:00
- Post Title: Re: Horizon Zero Dawn

Wow another good work !! nice job !
## Post #19
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2018-03-07T20:16:38+00:00
- Post Title: Re: Horizon Zero Dawn

Take your time, there is no rush. I saw your video on Killzone. Was that Shadow Fall? Great job.
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-08T06:05:18+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from UberBlack
>
> Take your time, there is no rush. I saw your video on Killzone. Was that Shadow Fall? Great job.
yes its Shadow Fall, i wanted to check if other decima games will work
## Post #21
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2018-03-13T16:05:52+00:00
- Post Title: Re: Horizon Zero Dawn

Are you also going to support Shadow Fall along with Horizon?
Are there other games that your support might work on?
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-13T16:27:16+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from UberBlack
>
> Are you also going to support Shadow Fall along with Horizon?
Are there other games that your support might work on?
you're only interested in animations ?
## Post #23
- Username: kidling
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 15, 2015 11:34 am
- Post datetime: 2018-03-14T01:15:31+00:00
- Post Title: Re: Horizon Zero Dawn

wow, congratulations! these animations of horizon are amazing!
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-31T14:57:40+00:00
- Post Title: Re: Horizon Zero Dawn

Finally this day has come. First tool version published. You'll see its a bit complicated, especially robots. Good luck.

You must be able to extract characters, animals, weapons and robots fully weighted and working.


Animation tool is still in progress: (NSFW) [https://www.youtube.com/watch?v=m5nh9q1LPcs](https://www.youtube.com/watch?v=m5nh9q1LPcs)
As you can see, not all of them are working correctly now.
## Post #25
- Username: Blorbster
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Mar 24, 2018 11:33 pm
- Post datetime: 2018-03-31T16:27:42+00:00
- Post Title: Re: Horizon Zero Dawn

I'm getting a consistent crash when trying to extract the resource list:

```
   at System.ThrowHelper.ThrowArgumentException(ExceptionResource resource)
   at System.Collections.Generic.Dictionary`2.Insert(TKey key, TValue value, Boolean add)
   at System.Collections.Generic.Dictionary`2.Add(TKey key, TValue value)
   at ?????????????????????????????????????????.?????????????????????????????????????????(String[] )
```

If it helps, this is using CUSA01021, the European release.
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-31T16:29:18+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Blorbster
>
> I'm getting a consistent crash when trying to extract the resource list:
Code: Select allUnhandled Exception: System.ArgumentException: An item with the same key has already been added.
   at System.ThrowHelper.ThrowArgumentException(ExceptionResource resource)
   at System.Collections.Generic.Dictionary`2.Insert(TKey key, TValue value, Boolean add)
   at System.Collections.Generic.Dictionary`2.Add(TKey key, TValue value)
   at ?????????????????????????????????????????.?????????????????????????????????????????(String[] )
If it helps, this is using CUSA01021, the European release.
sorry forgot to say, remove PATCH.BIN, its not yet supported
## Post #27
- Username: Blorbster
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Mar 24, 2018 11:33 pm
- Post datetime: 2018-03-31T16:45:05+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1
>
> Blorbster wrote:I'm getting a consistent crash when trying to extract the resource list:
Code: Select allUnhandled Exception: System.ArgumentException: An item with the same key has already been added.
   at System.ThrowHelper.ThrowArgumentException(ExceptionResource resource)
   at System.Collections.Generic.Dictionary`2.Insert(TKey key, TValue value, Boolean add)
   at System.Collections.Generic.Dictionary`2.Add(TKey key, TValue value)
   at ?????????????????????????????????????????.?????????????????????????????????????????(String[] )
If it helps, this is using CUSA01021, the European release.
sorry forgot to say, remove PATCH.BIN, its not yet supported
I don't actually have a patch.bin in my dump. The full contents of packed_pink are as listed:

```
initial_english.bin
initial_french.bin
initial_german.bin
initial_italian.bin
remainder.bin
remainder_english.bin
remainder_french.bin
remainder_german.bin
remainder_italian.bin
```

And outside of that directory the only .bin file is eboot.bin.
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-31T16:56:31+00:00
- Post Title: Re: Horizon Zero Dawn

...
## Post #29
- Username: Blorbster
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Mar 24, 2018 11:33 pm
- Post datetime: 2018-03-31T17:06:27+00:00
- Post Title: Re: Horizon Zero Dawn

No improvement, unfortunately. The error happens even with initial.bin as the only file in the directory.
## Post #30
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-31T17:39:19+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Blorbster
>
> No improvement, unfortunately. The error happens even with initial.bin as the only file in the directory.
and no subfolders?
## Post #31
- Username: Blorbster
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Mar 24, 2018 11:33 pm
- Post datetime: 2018-03-31T17:56:05+00:00
- Post Title: Re: Horizon Zero Dawn

No subfolders inside packed_pink. If I point the .ini directly to the packed_pink folder, instead of the main unpacked directory, I get this:

```
   at ?????????????????????????????????????????.?????????????????????????????????????????(Byte[] , Int64 , Byte[] , Int64 , UInt32 , UInt32 , UInt64 , UInt32 , UInt32 , UInt32 , UInt32 , UInt32 , UInt32 , UInt32 )
   at ?????????????????????????????????????????.?????????????????????????????????????????(String , MemoryStream )
   at ?????????????????????????????????????????.?????????????????????????????????????????(String[] )
```
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-31T18:19:46+00:00
- Post Title: Re: Horizon Zero Dawn

good. it means you need oo2core_5_win64.dll
i can't post it here, it will be agaist rules
## Post #33
- Username: Blorbster
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Mar 24, 2018 11:33 pm
- Post datetime: 2018-03-31T18:26:59+00:00
- Post Title: Re: Horizon Zero Dawn

I already have it- I got it from Warframe.

EDIT: Found a fix! For whatever reason, Warframe's oo2core_5_win64.dll didn't work, but it has a copy of version 6 as well- renaming oo2core_6 to oo2core_5 and using that dll worked.
## Post #34
- Username: redtank
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 28, 2016 3:15 am
- Post datetime: 2018-04-01T00:19:42+00:00
- Post Title: Re: Horizon Zero Dawn

Hi, is there anyone know that how to extract PS4 pkg file for this game?

I tried pkgdec.exe and unpkg_PS4.py, but only get some bin files and xml, cannot get content.

any other tools?
## Post #35
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-04-01T06:28:34+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from redtank
>
> Hi, is there anyone know that how to extract PS4 pkg file for this game?

I tried pkgdec.exe and unpkg_PS4.py, but only get some bin files and xml, cannot get content.

any other tools?
Fake_PKG_Generator is the one that extracts the PKGs that it was initially created with, it will NOT work with retail PKGs of the game, so make sure to get the right one.
## Post #36
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2018-04-01T08:56:05+00:00
- Post Title: Re: Horizon Zero Dawn

Thank you for this tool!

Is it possible to extract music, voices etc. with this tool? 
I tried it out but under "localized/..." I only got some *.core. Dropping them on horizon.exe doesn't do anything.
Then under "sounds/..." I got a lot of footsteps and explosions in "/effects/.../wav" but no voices.
And in "sounds/music/..." I got too few tracks to account for the whole OST.

Is the tool ignoring "initial_english.bin" and "remainder_english.bin" - I suspected them containing the voices.

I'm not complaining or anything, just asking!
## Post #37
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-01T10:35:29+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Raban
>
> Is it possible to extract music, voices etc. with this tool?
the tool is not ignoring anything. It takes all BIN files in the folder.

Music is contained in 2 huge stream files 1 GB in size each. I did not make any support for their extraction yet.

As for voices, i didn't check them.
## Post #38
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-04-01T18:06:26+00:00
- Post Title: Re: Horizon Zero Dawn

I'm sorry for the stupid question
Somebody figured, how to add a head to the model
Manually adjust (move,rotate), or there is a easier method ?
[image.jpg](https://xentaxbackup.github.io/file/14155_image.jpg)
## Post #39
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-04-01T20:54:57+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from redtank
>
> Hi, I get the Fake_PKG_Generator but have no idea how to extract pkg with it, cannot find tutorials about that, could u help me out? 
thanks!
Open: orbis-pub-chk.exe
Click ADD IMAGE: then select the downloaded PKG.
Click EXTRACT FILES: Enter Pssscode then click EXTRACT.
Select desired files then click START.
## Post #40
- Username: redtank
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 28, 2016 3:15 am
- Post datetime: 2018-04-01T23:01:46+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from mono24
>
> redtank wrote:Hi, I get the Fake_PKG_Generator but have no idea how to extract pkg with it, cannot find tutorials about that, could u help me out? 
thanks!
Open: orbis-pub-chk.exe
Click ADD IMAGE: then select the downloaded PKG.
Click EXTRACT FILES: Enter Pssscode then click EXTRACT.
Select desired files then click START.

Thanks!
## Post #41
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2018-04-02T14:53:46+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from mono24
>
> redtank wrote:Hi, I get the Fake_PKG_Generator but have no idea how to extract pkg with it, cannot find tutorials about that, could u help me out? 
thanks!
Open: orbis-pub-chk.exe
Click ADD IMAGE: then select the downloaded PKG.
Click EXTRACT FILES: Enter Pssscode then click EXTRACT.
Select desired files then click START.

And where get that passcode?
## Post #42
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-04-02T16:54:29+00:00
- Post Title: Re: Horizon Zero Dawn

when i extract the resource list  - File not found in cache!
many parts of models are not available: Rost head, Teersa head,
don't extract textures aloychild hair and many shaders.
[screenshot.jpg](https://xentaxbackup.github.io/file/14158_screenshot.jpg)
## Post #43
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-02T17:08:04+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Crazy31139
>
> when i extract the resource list  - File not found in cache!
many parts of models are not available: Rost head, Teersa head,
don't extract textures aloychild hair and many shaders.
i need exact resource names
## Post #44
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-04-02T17:28:03+00:00
- Post Title: Re: Horizon Zero Dawn

models/characters/humans/hair/aloychild/textures/aloychild_basecolor_set00
models/characters/humans/hair/aloychild/textures/aloychild_set00
## Post #45
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-02T17:33:41+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Crazy31139
>
> models/characters/humans/hair/aloychild/textures/aloychild_basecolor_set00
models/characters/humans/hair/aloychild/textures/aloychild_set00
i forgot about those.
set00 is single texture, not a set actually.
i will support those later.

what about Rost head ?
## Post #46
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-02T17:51:15+00:00
- Post Title: Re: Horizon Zero Dawn

rost head is fine for me, teersa also
## Post #47
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-04-02T20:05:24+00:00
- Post Title: Re: Horizon Zero Dawn

I'm sorry, with a head Rost all fine
Teersa head until I found, thought that out of the error - File not found in cache!
## Post #48
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2018-04-03T19:09:07+00:00
- Post Title: Re: Horizon Zero Dawn

How do I extract animation?
## Post #49
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-03T19:13:20+00:00
- Post Title: Re: Horizon Zero Dawn

Animation tool is still in progress. (not published)
## Post #50
- Username: Shinteo
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Apr 06, 2016 11:26 am
- Post datetime: 2018-04-04T16:46:48+00:00
- Post Title: Re: Horizon Zero Dawn

Hi

I got the ps4 ISO files, but have no idea how to proceed from there. Any advice would be appreciated.
## Post #51
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-04-05T03:51:01+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Shinteo
>
> Hi
I got the ps4 ISO files, but have no idea how to proceed from there. Any advice would be appreciated.
Umm, I assume you meant PS4 PKG, correct?
If so, you need Fake_PKG_Generator to extract the PKG game files from it.
You will find everything you need on psxhax website, including proper game that works with Fake_PKG_Generator.
Just use Google to find what you need, posting here direct links are against the rules.
## Post #52
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-04-05T06:32:55+00:00
- Post Title: Re: Horizon Zero Dawn

Thanks for the tools again.
Has anyone found a model of power armor in the bunker (staticl, but full model of armor)?
PS answer - futuresoldier

Do you can explain the line
"4.copy-paste skeleton into model parts"
I need to open skeleton.ascii, copy all the contents, open body.ascii and insert it there?
To the beginning or the end?
## Post #53
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2018-04-07T00:27:52+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from erik945
>
> Thanks for the tools again.
Has anyone found a model of power armor in the bunker (staticl, but full model of armor)?
PS answer - futuresoldier

Do you can explain the line
"4.copy-paste skeleton into model parts"
I need to open skeleton.ascii, copy all the contents, open body.ascii and insert it there?
To the beginning or the end?

Hey It took me a while to figure it out.. What he means is your want to copy the skeleton from the SMD.
To the mesh SMD. Then open the SMD in your fav viewer. Mine is Noesis, then you will see the mesh
with skeleton applied. Also you have to copy that skeleton from that SMD to all parts of the mesh.

I hope that helps.
## Post #54
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-07T05:53:19+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from erik945
>
> To the beginning or the end?
To the beginning
## Post #55
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2018-04-07T07:32:17+00:00
- Post Title: Re: Horizon Zero Dawn

I really don't want to get on anyone's nerves here, least of all appear ungrateful. But are there any news concerning the extraction of the voice-files?

It's (obviously) totally fine if those aren't a priority or all together not possible. I just would like to know if I did something wrong when I tried or if I can forget about it.
## Post #56
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-04-07T07:50:03+00:00
- Post Title: Re: Horizon Zero Dawn

Thanks for the help, guys!
I prefer ascii format but unfortunately the importer for max has one problem that leads to errors. I wrote a little fork script, if anyone should - let me know, I'll upload it.

Next problem 
"step 3: run this:
horizon [mesh_skeleton] [animskel] > a.bat
this will create FULL horse skeleton both in SMD & ASCII and also A.BAT file"
this creates an empty bat file
For example, for a scout, I converted all parts, copied a skeleton into the folder with them and call

```
E:\horizon\Horizon.exe E:\hz\Image0\packed_pink\models\AAcharacters\robots\scout\animation\parts\mesh_skeleton_rootbone.core E:\hz\Image0\packed_pink\entities\characters\robots\templates\archetypes\scouttemplate.core_0.animskel> E:\scout.bat
```


Bat is empty. Maybe it need a flag, or something?

Also where is Aloy facemodel?
## Post #57
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-07T08:12:18+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from erik945
>
> Bat is empty.
because tool cant find robot modelhelpers
## Post #58
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-04-07T08:43:34+00:00
- Post Title: Re: Horizon Zero Dawn

No, list of files in folder:


matrices
scouttemplate.core_0.animskel
body.core.ascii
bodyplate.core.ascii
eye.core.ascii
firesheets.core.ascii
focus_elements_lx.core.ascii
l_bodyplate.core.ascii
l_headplate.core.ascii
l_hipplate.core.ascii
mesh_skeleton_rootbone.core.ascii
parts.core.ascii
r_bodyplate.core.ascii
r_headplate.core.ascii
r_hipplate.core.ascii
replacementmesh.core.ascii
vines_corrupted.core.ascii
vines_hacked.core.ascii
body.core
bodyplate.core
eye.core
firesheets.core
focus_elements_lx.core
l_bodyplate.core
l_headplate.core
l_hipplate.core
mesh_skeleton_rootbone.core
mesh_skeleton_rootbone_posedeformer.core
parts.core
r_bodyplate.core
r_headplate.core
r_hipplate.core
replacementmesh.core
robot_modelhelpers.core
skeleton_rootbone.core
skeleton_rootbone_helpers.core
vines_corrupted.core
vines_hacked.core
body.core.smd
bodyplate.core.smd
eye.core.smd
firesheets.core.smd
focus_elements_lx.core.smd
l_bodyplate.core.smd
l_headplate.core.smd
l_hipplate.core.smd
mesh_skeleton_rootbone.core.smd
parts.core.smd
r_bodyplate.core.smd
r_headplate.core.smd
r_hipplate.core.smd
replacementmesh.core.smd
vines_corrupted.core.smd
vines_hacked.core.smd
body.core_materials.txt
bodyplate.core_materials.txt
eye.core_materials.txt
firesheets.core_materials.txt
focus_elements_lx.core_materials.txt
l_bodyplate.core_materials.txt
l_headplate.core_materials.txt
l_hipplate.core_materials.txt
parts.core_materials.txt
r_bodyplate.core_materials.txt
r_headplate.core_materials.txt
r_hipplate.core_materials.txt
replacementmesh.core_materials.txt
vines_corrupted.core_materials.txt
vines_hacked.core_materials.txt
## Post #59
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-07T09:11:30+00:00
- Post Title: Re: Horizon Zero Dawn

bat file can only be empty if tool can't find or open robot_modelhelpers.core file

your settings or command line somehow prevents the tool from opening it
## Post #60
- Username: propguy42
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 17, 2018 12:37 am
- Post datetime: 2018-04-18T05:06:36+00:00
- Post Title: Re: Horizon Zero Dawn

Anybody have the file names for Rost the spear and the shadow sharpshot bow on hand I would really appreciate the help
## Post #61
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2018-05-18T18:04:36+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1
>
> Ok here we go, animations are working 

https://youtu.be/jWPuixyQLmc

Can you do the same for quantum break? would pay you if you could...
## Post #62
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2018-05-18T18:19:07+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1
>
> UberBlack wrote:Are you also going to support Shadow Fall along with Horizon?
Are there other games that your support might work on?
you're only interested in animations ?

same here. If i can get animations to Horizon then i can recreate it... Either that or Quantum Break.

> Reply from daemon1
>
> Animation tool is still in progress. (not published)

When do you plan on releasing the tool?
## Post #63
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-18T18:35:55+00:00
- Post Title: Re: Horizon Zero Dawn

what do you mean "recreate it" ?

Quantum Break is using morpheme, so must be easy to extract.

But i'm not working on it now, have to finish other projects
also i'm not accepting payments
## Post #64
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2018-05-18T18:52:41+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1
>
> what do you mean "recreate it" ?
I mean just that. recreating specific missions using Unreal engine 4. I already have all the models and textures for Quantum break. I have been waiting to get the animations so i can recreate parts of the game with equal or superior graphical fidelity (UE4). Think about a multiplayer online version of quantum break awesome powers. That's are what i'm aiming for.

The way i see it, recreating games does more to help me enhance my gaming development skills. Its good practice and good hobby just as game RE improves your reverse engineering skills as a whole.

> Reply from daemon1
>
> 
Quantum Break is using morpheme, so must be easy to extract.

But i'm not working on it now, have to finish other projects
also i'm not accepting payments

Not payments. But If you can get it done, i will definitely donate to you.
Its an amazing thing what you are doing. You're breaking new ground.

Whether its quantum break or Horizon, it doesn't matter. They are two great visually acclaimed games that i would love to recreate.
## Post #65
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2018-05-19T03:25:56+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1
>
> Quantum Break is using morpheme, so must be easy to extract.

is there a quick way to tell if their implementation of morpheme is different from what you did for bio-shock infinite

[viewtopic.php?f=16&t=14970](http://forum.xentax.com/viewtopic.php?f=16&t=14970)
## Post #66
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-19T07:28:05+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Bladers
>
> Think about a multiplayer online version of quantum break
When I think about this, first thing I imagine is MS or SONY shutting it down and threatening with lawsuits.

> Reply from Bladers
>
> Not payments. But If you can get it done, i will definitely donate to you.
Thanks, but I'm not accepting donations either.
I can surely extract animations. Problem is, there are so many things I could do that its hard to choose.
## Post #67
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-19T07:29:44+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Bladers
>
> is there a quick way to tell if their implementation of morpheme is different from what you did for bio-shock infinite
I bet it will be closer to horizon than to bioshock.
Yes there is a quick way. I need a sample model and a few animations for that.
## Post #68
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2018-05-19T20:33:09+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1
>
> 
When I think about this, first thing I imagine is MS or SONY shutting it down and threatening with lawsuits.

The problem is, most people who do stuff like this  first create a big hoopla and buzz about it. which in turns generate a whole bunch of following yielding a community. Which ofcourse gets the interested parties involved. By the time the project is in 50% completion, it gets C&D'd like clock work.

What they should have done is kept the whole progress under wraps and announce it close or on the release date and release it (including on torrents.)
You can't C&D anonymous and once its on the net, you can't get rid of it because the internet never forgets!

> Reply from daemon1
>
> 
I can surely extract animations. Problem is, there are so many things I could do that its hard to choose.

I hope i can persuade you.
here is jack's model and animation
[http://www.mediafire.com/file/a1ttec294 ... ackjoy.zip](http://www.mediafire.com/file/a1ttec2945ni39k/jackjoy.zip)


Just being able to remake a mission or even a single cinematic scene to showcase what can be done in UE4 would be amazing.
been waiting 2 years to make use of this. 
[https://abload.de/img/joyceitrv5.png](https://abload.de/img/joyceitrv5.png)
## Post #69
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-20T16:41:47+00:00
- Post Title: Re: Horizon Zero Dawn

ok i checked animations
its like in between of bioshock & horizon
i can do that, not sure when i will have time
but whats your plan about this?



do you have another model to test, without cloth ?
## Post #70
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2018-05-20T18:34:48+00:00
- Post Title: Re: Horizon Zero Dawn

Cool thats great to hear!

And Yeah I can get you another model that doesn't have animated cloth as soon as I get home. However, I don't think there's a nude model unfortunately or atleast I haven't checked.

Now concerning Jack's jacket. Are you saying that you wouldn't be able to port his animation correctly based on that picture? Or are you wondering about my plans to handle the jacket for proper physics movement in game?
## Post #71
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-20T19:19:37+00:00
- Post Title: Re: Horizon Zero Dawn

i could extract animation correctly with this model, but jacket will impede the process of visual checking

i dont necessarily need nude model, there must be some without physics driven meshes
## Post #72
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2018-05-21T05:30:21+00:00
- Post Title: Re: Horizon Zero Dawn

[http://www.mediafire.com/file/4ug52pbhghogru6/paul.zip](http://www.mediafire.com/file/4ug52pbhghogru6/paul.zip)

I see, well here's paul's tshirt model and some animations.
Let me know if that's good or not.
## Post #73
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-21T15:16:31+00:00
- Post Title: Re: Horizon Zero Dawn

FBX is useless
i need original model and skeleton
## Post #74
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2018-05-21T16:05:58+00:00
- Post Title: Re: Horizon Zero Dawn

Sorry, here are all the raw files.

[http://www.mediafire.com/file/fl4f6oaba ... wfiles.zip](http://www.mediafire.com/file/fl4f6oabafaxw8a/rawfiles.zip)
## Post #75
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-21T16:22:18+00:00
- Post Title: Re: Horizon Zero Dawn

ok good
## Post #76
- Username: khovasapian
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 30, 2017 8:23 pm
- Post datetime: 2018-05-28T13:10:29+00:00
- Post Title: Re: Horizon Zero Dawn

Any updates on the animation tool? Looking forward to testing it.
## Post #77
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-28T15:12:02+00:00
- Post Title: Re: Horizon Zero Dawn

i'm busy with other games
this will be done later
## Post #78
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2018-06-02T18:08:30+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1
>
> i'm busy with other games
this will be done later

Hey daemon1, i wanna ask you the same thing i asked another guy...

is there an indepth tutorial out there? I'm a software engineer so its not like im a novice. I could easily learn if pointed to the right direction.
I want to be able to just get any model i want from any game without bothering people. for example the new Detroit game.
## Post #79
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-06-02T18:31:36+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Bladers
>
> for example the new Detroit game.
bad example
i dont think detroit will be available any soon
its on the newest FW
## Post #80
- Username: DigitalZky
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 18, 2017 9:26 am
- Post datetime: 2018-06-04T04:34:32+00:00
- Post Title: Re: Horizon Zero Dawn

Hello, sorry for the stupid question but I simply have no idea what to run for extracting resources, the .exe file? the .ini?
## Post #81
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2018-06-06T03:57:27+00:00
- Post Title: Re: Horizon Zero Dawn

The utility crash down when tries create list of game resources: CLR20r3, System.IO.DirectoryNotFound.

oo2core_5_win64.dll - 892 kb (913 408 bytes), CRC32 is 5E9C5B59.
OS - Windows 7 x64 SP1

Directory and structure:

```
\localcachepink
\movies
\packed_pink
\sce_module
\sce_sys
eboot.bin
sce_discmap.plt
title-id.txt
horizon tool usage.txt
Horizon.exe
horizon.ini
oo2core_5_win64.dll
robots.txt
```


What I need to do to make the utility working or the problem is something different (compatible files from specific version of the game for example)?
## Post #82
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-06-06T05:32:56+00:00
- Post Title: Re: Horizon Zero Dawn

в пункте 1 инструкции написано:

1. you need to place the tool in your "packed_pink" horizon folder ...
Note: remove PATCH.BIN from the folder, or the tool will crash

то есть надо запускать из папки "packed_pink"
## Post #83
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2018-06-16T14:11:07+00:00
- Post Title: Re: Horizon Zero Dawn

damn it, remedy beat me to it!

[https://www.youtube.com/watch?v=2p3jktqhp4g](https://www.youtube.com/watch?v=2p3jktqhp4g)

[https://www.youtube.com/watch?v=ZLGltC28sfw#t=2m30s](https://www.youtube.com/watch?v=ZLGltC28sfw#t=2m30s)
## Post #84
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-06-24T07:41:05+00:00
- Post Title: Re: Horizon Zero Dawn

Hello, you planing update tool to Horizon Zero Dawn Complete Edition 
Using Horizon.exe create res.txt is normal, file more bigger (DLC content)
Tools crash, extract only part files
I understand that you are busy at the moment, 
I wanted to ask if you plan on maintaining Horizon Zero Dawn Complete Edition 
Thank you so much for great job, 
and for the help in the decision of the arisen questions
## Post #85
- Username: heraros
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 26, 2014 7:12 am
- Post datetime: 2018-07-11T18:55:10+00:00
- Post Title: Re: Horizon Zero Dawn

Hello guys
I need aloy's animation ... Can you create a link for download please ?
## Post #86
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-07-11T23:25:22+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from heraros
>
> Hello guys
I need aloy's animation ... Can you create a link for download please ?
Ooooh, you'll be so disappointed to find out that it doesn't exist, yet, well it does, but in-game only, for now, maybe? who knows.

PS: And I desperately need a vacation, id love one to be honest, can anyone send me a ticked pretty please.
## Post #87
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-07-12T06:53:26+00:00
- Post Title: Re: Horizon Zero Dawn

I join to the question about the Complete Edition ...
## Post #88
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-12T15:15:52+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Crazy31139
>
> Hello, you planing update tool to Horizon Zero Dawn Complete Edition
i dont know
## Post #89
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2018-08-02T11:09:04+00:00
- Post Title: Re: Horizon Zero Dawn

There is a death stranding easter egg within the game. The handcuffs from the first trailer. Has anyone had any luck finding the model?
## Post #90
- Username: hardie360
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 29, 2018 3:24 pm
- Post datetime: 2018-08-11T10:56:49+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from octaviousrex
>
> There is a death stranding easter egg within the game. The handcuffs from the first trailer. Has anyone had any luck finding the model?
Try "packed_pink/models/pickups/kojima_assets_not_for_internal_use/shackles"

I can't get a model to extract but I'm using the Complete edition files so you might have better luck.
## Post #91
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-11T17:11:02+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from hardie360
>
> models/pickups/kojima_assets_not_for_internal_use/shackles"

its not because of Complete edition 
this asset is Havok asset, so its not converted with the tool
## Post #92
- Username: hardie360
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 29, 2018 3:24 pm
- Post datetime: 2018-08-16T09:17:13+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1
>
> hardie360 wrote:models/pickups/kojima_assets_not_for_internal_use/shackles"


its not because of Complete edition 
this asset is Havok asset, so its not converted with the tool
That makes more sense.

Is there actually any reason for Complete Edition files to not work? I've tried extracting a few parts of the scorcher and it seemed to work fine.
## Post #93
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-16T10:05:29+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from hardie360
>
> Is there actually any reason for Complete Edition files to not work? I've tried extracting a few parts of the scorcher and it seemed to work fine.
i have no idea
i never tried anything yet
## Post #94
- Username: herbalist
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 08, 2018 9:46 pm
- Post datetime: 2018-11-08T13:53:32+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1
>
> hardie360 wrote:Is there actually any reason for Complete Edition files to not work? I've tried extracting a few parts of the scorcher and it seemed to work fine.
i have no idea
i never tried anything yet

HZD:CE works, incl. DLC files for the most part, about two dozen files fail to extract.

Is there any reason why the executable is so heavily obfuscated? I want to make some changes to show me which objects fail but it just turns out as gibberish.

Edit: for those still having crashes on start, point it to the packed_pink folder, not the CUSA folder. It tries to load the EBOOT.bin file and crashes.
## Post #95
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-08T15:48:13+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from herbalist
>
> Is there any reason why

Yes, there is.
Its because one paid tool author used my research to sell and promote his paid tool.
He did it at least once, with overwatch, maybe more.
Ever since then i never publish any sources.
## Post #96
- Username: herbalist
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 08, 2018 9:46 pm
- Post datetime: 2018-11-08T17:38:20+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1
>
> herbalist wrote:Is there any reason why

Yes, there is.
Its because one paid tool author used my research to sell and promote his paid tool.
He did it at least once, with overwatch, maybe more.
Ever since then i never publish any sources.

Was that the "3D model converter" guy in the Facepunch thread that didn't understand anything?

In any case, can you give more details whenever a "Failed to find object" error happens?
## Post #97
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-08T18:11:49+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from herbalist
>
> Was that the "3D model converter" guy in the Facepunch thread that didn't understand anything?

In any case, can you give more details whenever a "Failed to find object" error happens?

no that was another one, but you never know, maybe its all the same guy

"Failed to find object"  - what is this about?
## Post #98
- Username: herbalist
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 08, 2018 9:46 pm
- Post datetime: 2018-11-08T18:57:32+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1
>
> herbalist wrote:Was that the "3D model converter" guy in the Facepunch thread that didn't understand anything?

In any case, can you give more details whenever a "Failed to find object" error happens?

no that was another one, but you never know, maybe its all the same guy

"Failed to find object"  - what is this about?

I tried exporting all files by just loading the entire res.txt file, it kept saying something like that for 20 or so files but I don't know which.
## Post #99
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-08T19:24:42+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from herbalist
>
> I tried exporting all files by just loading the entire res.txt file, it kept saying something like that for 20 or so files but I don't know which.
it can be because these files are not present in the game
or because patch is not supported
## Post #100
- Username: iLeonidze
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 06, 2019 2:08 am
- Post datetime: 2019-04-07T14:10:32+00:00
- Post Title: Re: Horizon Zero Dawn

Thanks for an amazing job!

I am experiencing difficulty on the "Extracting characters with skeleton" step: after exporting game sources I got lot of .core files. I can extract SMD opening this .core via Horizon executable, but I can't understand what means "place all parts of a character in one folder, and run horizon on all of them". Aloy character files are scattered and it is not clear what exactly to be used. Probably it's because I'm still new to this issue.

I understand that the topic is very outdated, and probably the author put all the files in the far box, but I would be happy to see some example of exporting Aloy model. daemon1, can you? Or may be there some video with the process exists?

Also, I am unable to extract the localization voices. Does anyone have any success with this? I would love to dig further the sources of this game, if the author could share the source code of the tool.
## Post #101
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-07T15:41:09+00:00
- Post Title: Re: Horizon Zero Dawn

hope someone else can help
## Post #102
- Username: sxlhyh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 21, 2019 4:35 pm
- Post datetime: 2019-04-08T10:41:29+00:00
- Post Title: Re: Horizon Zero Dawn

hello, daemon1~
i drag resource of the Horizon.exe, but show "System.NullReferenceException"
.core files name: 
models/eco_assets/trees/banana_tree/components/banana_tree_b001_c002_resource
models/eco_assets/trees/weeping_willow/components/weepingwillow_b001_c001_resource
 
Thanks for your job!
## Post #103
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-18T16:01:09+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from sxlhyh ↑Mon Apr 08, 2019 6:41 pm at Mon Apr 08, 2019 6:41 pm
>
> 
hello, daemon1~
i drag resource of the Horizon.exe, but show "System.NullReferenceException"
.core files name: 
models/eco_assets/trees/banana_tree/components/banana_tree_b001_c002_resource
models/eco_assets/trees/weeping_willow/components/weepingwillow_b001_c001_resource
 
Thanks for your job!
work fine here:
## Post #104
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-18T18:29:59+00:00
- Post Title: Re: Horizon Zero Dawn

Animation tool is finally finished!

It will be posted here after some testing
## Post #105
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-20T19:23:30+00:00
- Post Title: Re: Horizon Zero Dawn

Updated tool with animation support and support for all textures export.

To extract animations:

1. Extract animation manager  (with /e command)

animation managers can be found in models/animation_managers/characters/

2. Extract skeleton. You can use animation skeleton or mesh skeleton

read how to get mesh skeletons in the first post

animation skeletons are in template files:
- for robots its in entities/characters/robots/templates/archetypes/
- for animals - in entities/animals/
- for humans - entities/characters/components/humanoidragdollcomponents
 (humanoidragdollcomponents has 2 skeletons with same name for male, female & child)

3. Extract animations from animation manager

drop animation manager onto the tool, this will extract all animations into "anim" folder
getting proper animation names will be supported later.

4. Convert animations. There are 2 options:

a) Horizon [animation] [animskel] 

This will extract animation with skeleton in rest pose and make proper SMD file.

b) Horizon [animation] or just drop animation (.morpheme) file onto the tool

This will extract only animation. This option will allow you to merge all animations into one file. To make proper SMD, you'll have to copypaste the skeleton from animation skeleton SMD or mesh skeleton SMD to the beginning of the animation SMD file.

======================================
Notes:

- most ingame animations are morpheme, and can be extracted with this tool
- some ingame animations and all cutscenes are in decima engine anim format, and can't be converted
- some animations are additive, they cannot be extracted properly
- the only non-supported robot is scout (watcher), will be fixed soon
[Horizon.rar](https://xentaxbackup.github.io/file/16060_Horizon.rar)
## Post #106
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-22T06:59:04+00:00
- Post Title: Re: Horizon Zero Dawn

New version will be published soon:

- animation names
- support for animations of human interacting with a robot (riding, attacks)
- scout support
## Post #107
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2019-04-22T18:17:58+00:00
- Post Title: Re: Horizon Zero Dawn

Thanks a lot for the effort in making these tools. Is anyone planning to port the models from this game? A while back there was a couple of models available in deviantArt in the xnalara section but haven't see any new ones for a while. Anyone willing to port as this game has got some amazing models?
## Post #108
- Username: Nguyen Thanh Tùng
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jan 12, 2019 8:53 am
- Post datetime: 2019-04-23T00:00:42+00:00
- Post Title: Re: Horizon Zero Dawn

Hi, is there anyone know that how to extract PS4 pkg file for this game?
## Post #109
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-04-23T06:52:05+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Nguyen Thanh Tùng ↑Tue Apr 23, 2019 8:00 am at Tue Apr 23, 2019 8:00 am
>
> 
Hi, is there anyone know that how to extract PS4 pkg file for this game?
That depends, a retail Sony PKG is impossible with out its key, a fake PKG on the other hand is different, so pick that one, plenty info on Google how to achieve it in both obtaining a fake PS4 PKG of the game and how to unpack it.
## Post #110
- Username: Nguyen Thanh Tùng
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jan 12, 2019 8:53 am
- Post datetime: 2019-04-23T12:26:22+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from mono24 ↑Tue Apr 23, 2019 2:52 pm at Tue Apr 23, 2019 2:52 pm
>
> 
Nguyen Thanh Tùng wrote: ↑Tue Apr 23, 2019 8:00 am
Hi, is there anyone know that how to extract PS4 pkg file for this game?

That depends, a retail Sony PKG is impossible with out its key, a fake PKG on the other hand is different, so pick that one, plenty info on Google how to achieve it in both obtaining a fake PS4 PKG of the game and how to unpack it.
You can ask for a link, I have no experience with ps4, Can you give me the download link?
[ewqrewe.png](https://xentaxbackup.github.io/file/16096_ewqrewe.png)
## Post #111
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-23T16:15:45+00:00
- Post Title: Re: Horizon Zero Dawn

New tool version with improved animations support.

There are some important changes, so i decided to post this new version separately. After testing some robots, we found that most robot animation packages include about a half robot anims, and the other half is animations of a human interacting with that robot (riding, attacks etc). These required special treatment. The process remains the same, except extracting animation manager (step 3 in previous post).

When extracting animation manager, tool will now make 2 text files: 

1. _anims_by_name.txt - this is list of all animation system elements with original names. They include parameters, groups, switches, all kind of data used in animation engine. Some of them will have links to actual animations, sometimes several. This is an example:



2. _anims_by_id.txt - reference list of all animation files with names used in previous list. If you sort that list, you can see where each file is used. Or use it to make batch-rename of the files to the names you want.

Tool will also create a number of "bone_setup" files which are needed to correctly convert animations to SMD. Some animations will work without them (like it was before), but many will require them to be in the same folder.

Animation files will be named with internal numbers instead of hashes. Each file will have sequential number (used in text lists described above) and bone setup number. For example in horse animation package there will be 180 animations ending with "5" which are horse animations, and 130 ones ending with "8" which are animations of aloy riding the horse. You can use this to sort the files so you can convert using correct skeleton.
[Horizon.rar](https://xentaxbackup.github.io/file/16092_Horizon.rar)
## Post #112
- Username: Nguyen Thanh Tùng
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jan 12, 2019 8:53 am
- Post datetime: 2019-04-23T17:31:16+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Wed Apr 24, 2019 12:15 am at Wed Apr 24, 2019 12:15 am
>
> 
New tool version with improved animations support.

There are some important changes, so i decided to post this new version separately. After testing some robots, we found that most robot animation packages include about a half robot anims, and the other half is animations of a human interacting with that robot (riding, attacks etc). These required special treatment. The process remains the same, except extracting animation manager (step 3 in previous post).

When extracting animation manager, tool will now make 2 text files: 

1. _anims_by_name.txt - this is list of all animation system elements with original names. They include parameters, groups, switches, all kind of data used in animation engine. Some of them will have links to actual animations, sometimes several. This is an example:





2. _anims_by_id.txt - reference list of all animation files with names used in previous list. If you sort that list, you can see where each file is used. Or use it to make batch-rename of the files to the names you want.

Tool will also create a number of "bone_setup" files which are needed to correctly convert animations to SMD. Some animations will work without them (like it was before), but many will require them to be in the same folder.

Animation files will be named with internal numbers instead of hashes. Each file will have sequential number (used in text lists described above) and bone setup number. For example in horse animation package there will be 180 animations ending with "5" which are horse animations, and 130 ones ending with "8" which are animations of aloy riding the horse. You can use this to sort the files so you can convert using correct skeleton.

how to extract it ??
## Post #113
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-04-23T17:56:05+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Nguyen Thanh Tùng ↑Wed Apr 24, 2019 1:31 am at Wed Apr 24, 2019 1:31 am
>
> how to extract it ??
First post has all information you need, links are NOT allowed to be posted, simply google how to get a fake PKG of the game and how to extract it, then extract the PKG, you cant just expect everything to be handed out to you, do some search.
## Post #114
- Username: GuillermoGatoto
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 09, 2018 1:56 pm
- Post datetime: 2019-04-24T02:56:12+00:00
- Post Title: Re: Horizon Zero Dawn

Hi! 

Does anyone know how to access the voice files? 

I can't seem to find them after extracting everything with the tool. I think only sound effects like robot sounds and footsteps are extracted. 

Thanks!
## Post #115
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-04-24T06:41:17+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from GuillermoGatoto ↑Wed Apr 24, 2019 10:56 am at Wed Apr 24, 2019 10:56 am
>
> Does anyone know how to access the voice files?
Besides what you already have, nothing else is supported by the extraction tool.
## Post #116
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-24T15:13:48+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from GuillermoGatoto ↑Wed Apr 24, 2019 10:56 am at Wed Apr 24, 2019 10:56 am
>
> 
Hi! 

Does anyone know how to access the voice files? 

I can't seem to find them after extracting everything with the tool. I think only sound effects like robot sounds and footsteps are extracted. 

Thanks!
Voice files are extracted.
## Post #117
- Username: usabdt
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Sep 21, 2018 4:28 am
- Post datetime: 2019-05-02T02:55:09+00:00
- Post Title: Re: Horizon Zero Dawn

I do this right ??
[00000.png](https://xentaxbackup.github.io/file/16144_00000.png)
## Post #118
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2019-05-03T20:06:30+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Sun Apr 21, 2019 3:23 am at Sun Apr 21, 2019 3:23 am
>
> 
- most ingame animations are morpheme, and can be extracted with this tool
- some ingame animations and all cutscenes are in decima engine anim format, and can't be converted
- some animations are additive, they cannot be extracted properly
- the only non-supported robot is scout (watcher), will be fixed soon

Awesome job as always. Will see how i can work with this.
I also noticed that this uses morpheme (which QB uses). So it safe to say that this code can be adopted to handle quantum break for example? 
But again, this is good, i will see how i can leverage this.
## Post #119
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-05-03T20:18:16+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Bladers ↑Sat May 04, 2019 4:06 am at Sat May 04, 2019 4:06 am
>
> 
So it safe to say that this code can be adopted to handle quantum break for example?
No. I already checked QB and its using different type or morpheme compression, which was never seen in horizon
## Post #120
- Username: usabdt
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Sep 21, 2018 4:28 am
- Post datetime: 2019-05-03T21:31:51+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Blorbster ↑Sun Apr 01, 2018 12:45 am at Sun Apr 01, 2018 12:45 am
>
> 
daemon1 wrote:Blorbster wrote:I'm getting a consistent crash when trying to extract the resource list:
Code: Select allUnhandled Exception: System.ArgumentException: An item with the same key has already been added.
   at System.ThrowHelper.ThrowArgumentException(ExceptionResource resource)
   at System.Collections.Generic.Dictionary`2.Insert(TKey key, TValue value, Boolean add)
   at System.Collections.Generic.Dictionary`2.Add(TKey key, TValue value)
   at ?????????????????????????????????????????.?????????????????????????????????????????(String[] )
If it helps, this is using CUSA01021, the European release.
sorry forgot to say, remove PATCH.BIN, its not yet supported
I don't actually have a patch.bin in my dump. The full contents of packed_pink are as listed:
Code: Select allinitial.bin
initial_english.bin
initial_french.bin
initial_german.bin
initial_italian.bin
remainder.bin
remainder_english.bin
remainder_french.bin
remainder_german.bin
remainder_italian.bin
And outside of that directory the only .bin file is eboot.bin.

How to recover from this error?
[12345.png](https://xentaxbackup.github.io/file/16158_12345.png)
## Post #121
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-05-04T06:23:55+00:00
- Post Title: Re: Horizon Zero Dawn

what error exactly?
## Post #122
- Username: usabdt
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Sep 21, 2018 4:28 am
- Post datetime: 2019-05-04T06:49:01+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Sat May 04, 2019 2:23 pm at Sat May 04, 2019 2:23 pm
>
> 
what error exactly?

I don't see the file oo2core_5_win64.dll and PATCH.BIN
## Post #123
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-05-04T08:01:02+00:00
- Post Title: Re: Horizon Zero Dawn

you need to find oo2core_5_win64.dll somewhere
all modern games use oodle
## Post #124
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2019-06-06T17:32:44+00:00
- Post Title: Re: Horizon Zero Dawn

Hi, you planing support textures set00.core
many texture hair in set00
## Post #125
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-06-07T15:57:55+00:00
- Post Title: Re: Horizon Zero Dawn

they're already supported
## Post #126
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2019-06-08T03:20:43+00:00
- Post Title: Re: Horizon Zero Dawn

Thank you, did not watch the new version tool.
## Post #127
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2019-06-29T11:19:15+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Wed Apr 24, 2019 12:15 am at Wed Apr 24, 2019 12:15 am
>
> 
New tool version with improved animations support.

First of all: A huge thank you. What you've made possible is truly astonishing!   

Secondly, I would like to ask if facial animations are supported. The .animskel from "humanoidragdollcomponents.core" does not include the bones for the head, nor do the animation files from "maincharacter.core" seem to have anything to do with facial animations.
## Post #128
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-06-29T11:21:17+00:00
- Post Title: Re: Horizon Zero Dawn

can't seem to get this to work
I tried running it on the pkg  and on the extracted pkg files (via the ini - cache not found)
I am using the complete edition

> Reply from daemon1 ↑Wed Apr 24, 2019 12:15 am at Wed Apr 24, 2019 12:15 am
>
> 
New tool version with improved animations support.
windows claims this is a virus and wont let me extract
## Post #129
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-06-29T12:03:13+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Raban ↑Sat Jun 29, 2019 7:19 pm at Sat Jun 29, 2019 7:19 pm
>
> 
Secondly, I would like to ask if facial animations are supported.
i never checked them, so i can't tell
## Post #130
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-06-29T12:04:11+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from JohnHudeski ↑Sat Jun 29, 2019 7:21 pm at Sat Jun 29, 2019 7:21 pm
>
> 
windows claims this is a virus and wont let me extract
its not a virus.
either disable antivirus or dont use the tool
## Post #131
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-06-29T13:42:39+00:00
- Post Title: Re: Horizon Zero Dawn

Yikes. I know its probably not a virus I just wanted to know how to circumvent windows blocking it without disabling the entire AV
or if anyone experienced that



ITE2A8K - Imgur.png (9.53 KiB) Viewed 227 times



I'll add even my browser claimed the latest update was a virus
## Post #132
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-06-29T14:17:54+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from JohnHudeski ↑Sat Jun 29, 2019 9:42 pm at Sat Jun 29, 2019 9:42 pm
>
> 
I'll add even my browser claimed the latest update was a virus
just dont use it then
## Post #133
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-06-29T15:45:13+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Sat Jun 29, 2019 10:17 pm at Sat Jun 29, 2019 10:17 pm
>
> 
JohnHudeski wrote: ↑Sat Jun 29, 2019 9:42 pm
I'll add even my browser claimed the latest update was a virus

just dont use it then

lmao. No need to be a big girl's blouse about it
## Post #134
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-06-29T21:36:25+00:00
- Post Title: Re: Horizon Zero Dawn

Could anyone PM me a link for the Horizon Zero Dawn Files?
## Post #135
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-06-29T22:38:17+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from nightwolf1982 ↑Sun Jun 30, 2019 5:36 am at Sun Jun 30, 2019 5:36 am
>
> 
Could anyone PM me a link for the Horizon Zero Dawn Files?
For this particular game you can get them yourself, they are all over the internet, they are not like the exclusive ones that require a higher exploited firmware.
## Post #136
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2019-06-30T12:54:52+00:00
- Post Title: Re: Horizon Zero Dawn

No matter what I do, when playing an animation everything is always messed up. Does somebody know what's the reason behind this? 

When extracting the models I used their corresponding "mesh_skeleton_rootbone" and converted the smd via Noesis (current) to fbx. When converting the .morpheme file I used "humanoidragdollcomponents.core_2.animskel" (I tried the other two as well but the "..._2.animskel" seems to be the right one) like this:"horizon 0761_02.morpheme humanoidragdollcomponents.core_2.animskel".


Is perhaps something wrong with the weight paint, because I also noticed that not all vertices of the hairmesh where assigned to their vertex group, but that was easy to remedy since they had only one.




screen.jpg (56.69 KiB) Viewed 363 times
## Post #137
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-06-30T14:03:11+00:00
- Post Title: Re: Horizon Zero Dawn

Cloth and other physic-driven parts are not controlled by animation.
So you have to do something about it yourself. Weight them, apply some physics or such.
## Post #138
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2019-06-30T14:24:19+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Sun Jun 30, 2019 10:03 pm at Sun Jun 30, 2019 10:03 pm
>
> 
Cloth and other physic-driven parts are not controlled by animation.
So you have to do something about it yourself. Weight them, apply some physics or such.

I realize I'm out of my depths here, but wouldn't that mean that these parts don't get deformed at all instead of being distorted by the animation - there's not a single part of the model that get's deformed correctly in its entirety. You're saying it looks the very same at your end?
## Post #139
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-06-30T14:41:28+00:00
- Post Title: Re: Horizon Zero Dawn

no, most parts are ok on my end, i'm not sure whats going on on your picture, its hard to say
are you sure you added all outfit parts to matrices before extracting final model?
this can lead to only base model weighted correctly
## Post #140
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2019-06-30T14:47:23+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Sun Jun 30, 2019 10:41 pm at Sun Jun 30, 2019 10:41 pm
>
> 
are you sure you added all outfit parts to matrices before extracting final model?

I assumed that the matrices file get's updated or the necessary information added to it everytime I use horizon.exe on one of the core files containing relevant mesh-data. 

Do I have to do this manually, like unpack the first .core, move it and its matrices-file somewhere else, then unpack the second one and copy the content of the new matrices-file to the old one and then in the end - when I unpack rootskeleton - move the fully updated matrices-file back into the directory where the horizon.exe is?

The way I do it is the following: I run horizon on the relevant ressource, meaning "horizon /e models/characters/humans/aloyundergarment/animation/parts/aloyhair_ct_a_lx", "horizon /e models/characters/humans/aloyundergarment/animation/parts/aloyundergarment_ct_a_lx" and "horizon /e models/characters/humans/aloyundergarment/animation/skeletons/mesh_skeleton_rootbone". Then I drag and drop "aloyundergarment_ct_a_lx.core", "aloyhair_ct_a_lx" and finally "mesh_skeleton_rootbone.core" on "horizon.exe". Each time I get an .ascii, a .smd, plus the file matrices becomes bigger. The I copy the content of the skeleton-smd-file and paste that at the top of every other .smd-file. Then I use noesis to load the models and export them as fbx.
## Post #141
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-06-30T17:08:24+00:00
- Post Title: Re: Horizon Zero Dawn

ok it seems outfits weighthing is more complex than i expected
sorry, i can't help you
## Post #142
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2019-07-02T18:37:01+00:00
- Post Title: Re: Horizon Zero Dawn

After seeing your video in which you show the animations working with the default female body-model, I tried that one out and still have the same problem, which is just puzzling - is there anything else one needs to do to get this working? 


Also, when converting from .smd to .fbx Noesis is always giving me this error: "Error: Unexpected syntax in skeleton definition." Is this what's causing problems?
When pasting the data from the "mesh_skeleton_rootbone.core.smd" I always paste it in its entirety - is that correct or do I perhaps have to omit stuff like "version 1" or "nodes" or delete these from the .smd I paste into?

Edit: 
Thanks to nightwolf1982 I can rule out that this is what's causing the issue.
To get rid of the error one must indeed delete "version 1" and "nodes" from the beginning of the mesh-file the skeleton is pasted into.
## Post #143
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-07-03T02:22:56+00:00
- Post Title: Re: Horizon Zero Dawn

Oooooookay, I think I'm getting the hang of these models, at least, I've got a working model for Child Aloy, except for her head.  I can't seem to find either the child version or the adult version of Aloy's head.  Only the baby version so far.
## Post #144
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-07-03T04:28:14+00:00
- Post Title: Re: Horizon Zero Dawn

Never mind, figured it out!
## Post #145
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-07-03T20:39:27+00:00
- Post Title: Re: Horizon Zero Dawn

Should I be concerned?

> E:\HZD>Horizon.exe /p list.txt
>
> File not found in cache! animation_objects/me_guard/animations/me_guard_stand_idle2negative.core
>
> File not found in cache! cinematics/cinematic_object_collections/scenes/mq09_cut_anotherhatch_objects.core
>
> File not found in cache! cinematics/cinematic_object_collections/scenes/mq09_cut_meetinghades_objects.core
>
> File not found in cache! cinematics/cinematic_object_collections/scenes/mq09_ressurectedwarbot_objects.core
>
> File not found in cache! cinematics/mainquests/mq090_cut_anotherhatch/mq09_audioseq_anotherhatch.core
>
> File not found in cache! cinematics/mainquests/mq090_cut_anotherhatch/mq090cutanotherhatch.core
>
> File not found in cache! cinematics/mainquests/mq090_cut_anotherhatch/mq090cutanotherhatch_facts.core
>
> File not found in cache! entities/collectables/collactable_vantage/collectable_vantage_04.core
>
> File not found in cache! entities/crowdsetups/setups/nora/mothers_heart/mq6_7_grief/mq6_7_grief_cemetarycrowd.core
>
> File not found in cache! entities/crowdsetups/setups/nora/mothers_heart/mq6_7_grief/mq6_7_grief_socialareacrowd.core
>
> File not found in cache! entities/crowdsetups/setups/nora/mothers_watch/motherswatch_spawnsetups.core
>
> File not found in cache! entities/smartobjects/commercial_location/trade_desire/travelmerch/animations/travel_merch_f_attractfar.core
>
> File not found in cache! entities/smartobjects/leisure_location/entertainment_desire/kidsitlow/so_kidsitlow.core
>
> File not found in cache! entities/smartobjects/leisure_location/entertainment_desire/kidsitlow/so_kidsitlow_facts.core
>
> File not found in cache! entities/smartobjects/leisure_location/entertainment_desire/matriarchsermon/animations/matriarchsermon_f_idle.core
>
> File not found in cache! entities/smartobjects/leisure_location/entertainment_desire/matriarchsermon/animations/matriarchsermon_f_idle1.core
>
> File not found in cache! entities/smartobjects/leisure_location/entertainment_desire/matriarchsermon/animations/matriarchsermon_f_idle2.core
>
> File not found in cache! entities/smartobjects/leisure_location/entertainment_desire/matriarchsermon/animations/matriarchsermon_f_idle3.core
>
> File not found in cache! entities/smartobjects/leisure_location/entertainment_desire/matriarchsermon/animations/matriarchsermon_f_mount.core
>
> File not found in cache! entities/smartobjects/misc_location/beg_desire/begstnd/variations/so_begstnd_rv.core
>
> File not found in cache! entities/smartobjects/misc_location/beg_desire/begstnd/variations/so_begstnd_rv_facts.core
>
> File not found in cache! entities/smartobjects/motherswatch_prayercrowd/griefkneel/griefkneel_grandprayer.core
>
> File not found in cache! entities/smartobjects/motherswatch_prayercrowd/griefkneel/griefkneel_grandprayer_facts.core
>
> File not found in cache! entities/smartobjects/motherswatch_prayercrowd/griefstnd_grandprayer.core
>
> File not found in cache! entities/smartobjects/motherswatch_prayercrowd/griefstnd_grandprayer_facts.core
>
> File not found in cache! entities/smartobjects/motherswatch_prayercrowd/matriarchsermon/matriarchsermon_grandprayer.core
>
> File not found in cache! entities/smartobjects/motherswatch_prayercrowd/matriarchsermon/matriarchsermon_grandprayer_facts.core
>
> File not found in cache! entities/smartobjects/motherswatch_prayercrowd/praying_grandprayer.core
>
> File not found in cache! entities/smartobjects/motherswatch_prayercrowd/praying_grandprayer_facts.core
>
> File not found in cache! entities/smartobjects/no_desire/nora/no_triage/no_triage.core
>
> File not found in cache! entities/smartobjects/no_desire/nora/no_triage/no_triage_facts.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leather_work_m_bevel.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leather_work_m_bo_neutral.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leather_work_m_bo_positive.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leather_work_m_dismount.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leather_work_m_holeleft.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leather_work_m_idle2negative.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leather_work_m_mount.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leather_work_m_mount_2.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leather_work_m_negative.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leather_work_m_negative2idle.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leather_work_m_pickup.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leather_work_m_putdown.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leather_work_m_score.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leather_work_m_soak.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leather_work_m_stamp.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leatherwork_f_dismount.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leatherwork_f_idle.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leatherwork_f_idle1.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leatherwork_f_idle2.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leatherwork_f_idle3.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leatherwork_f_idle4.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leatherwork_f_pickup.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/animations/leatherwork_f_putdown.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/so_leatherworker.core
>
> File not found in cache! entities/smartobjects/work_location/work_desire/artisans/leatherworker/so_leatherworker_facts.core
>
> File not found in cache! entities/spawnsetups/characters/shops/shop_vendor_instances/shop_vendor_trader_mesacity_market_01.core
>
> File not found in cache! entities/spawnsetups/characters/shops/shop_vendor_instances/shop_vendor_trader_mesacity_market_03.core
>
> File not found in cache! entities/spawnsetups/characters/shops/shop_vendor_instances/shop_vendor_trader_mesacity_market_05.core
## Post #146
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-07-04T02:36:51+00:00
- Post Title: Re: Horizon Zero Dawn

This was asked before, but how do I combine the head and bodies?  Specifically, how do I merge the skeletons in Blender?
## Post #147
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2019-07-04T09:35:47+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from nightwolf1982 ↑Thu Jul 04, 2019 10:36 am at Thu Jul 04, 2019 10:36 am
>
> 
This was asked before, but how do I combine the head and bodies?  Specifically, how do I merge the skeletons in Blender?

To the best of my knowledge:

case I Both models share the very same skeleton, i.e. exact same bones OR they share at least one bone and you don't care about loosing the functionality of the others:

Once you've both imported - best in different collections - you unparent one mesh, i.e. the one you want to transfer, from its skeleton by Alt+P (Object Mode) -> clear and keep transfrom -> select that mesh and press CTRL+A -> apply all transforms -> with that mesh selected, select the other armature which thus becomes the active object -> press CTRL+P and parent -> go to the modifier-tab and update the object of the armature-modifier.

case II You want to transfer and integrate bones from one armature into another:

First make sure you know where the new bones have to be placed in terms of the bone-hierarchy of the skeleton you want to transfer them into, meaning determine which bone will be the parent of those bones. Preferably both armatures share some or at least one bone - which is actually the case here as both have the neck-bones.
In Edit Mode select inside the outliner-tab all the bones you want to transfer (remember that you can invert a selection by pressing CTRL+I). Make sure your cursor is inside the viewport-tab, press P -> seperate bones. You should now have an entire new armature listed in your outliner. Go into Object Mode select it and then select the armature you want to place the bones into. Now press CTRL+J to join both. The bones of the armature you've just had created should now be listed right under rootBone with their hierarchy intact. Still in Edit Mode, select the one on top of the hierarchy, i.e. the one that is listed right under rootBone, and then their new parent bone. Make sure your cursor is inside the viewport-tab and then press CTRL+P -> parent  (I have found it best to choose the keep offset option).

---------------------------------------------------------------------------------------------------------------------

The redfox-model, for example, is playing its animations just fine, meaning no issues whatsoever. Unfortunately the same can't be said about any of the human models including defaultmale and defaultfemale (haven't tested robots yet):




Scene.jpg (36.16 KiB) Viewed 267 times
## Post #148
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-07-11T04:54:15+00:00
- Post Title: Re: Horizon Zero Dawn

Ran into a small issue.  While trying to texture Child Aloy's eyebrows, I discovered that the SMD extraction didn't include the UVs for the eyebrows.  I haven't run into anything else with this issue, and I can get the missing UVs from the ascii export, but it'll be something to keep an eye out for.
## Post #149
- Username: seearele
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 14, 2019 5:15 pm
- Post datetime: 2019-08-14T09:33:02+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Wed Apr 24, 2019 11:13 pm at Wed Apr 24, 2019 11:13 pm
>
> 
GuillermoGatoto wrote: ↑Wed Apr 24, 2019 10:56 am
Hi! 

Does anyone know how to access the voice files? 

I can't seem to find them after extracting everything with the tool. I think only sound effects like robot sounds and footsteps are extracted. 

Thanks!

Voice files are extracted.

Please clarify how can voice files should be extracted - there is nothing about it in instruction.

First of all I can't understand where is .core files for the localized sentences. I suppose there should be thousands of such files, but I searched for them in sounds/ and localized/ directories - seems there is nothing here.

Secondly, I found something similar to music, but this is can not be extracted too. For example I found a file packed_pink/sounds/music/credits/wav/credits_thematic.core - nothing extracted. The same problem with credits.soundbank.core, real .soundbank is not extracted for me.

Is there anyone who succeeded to get the original voice/music files?
## Post #150
- Username: iLeonidze
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 06, 2019 2:08 am
- Post datetime: 2019-08-14T15:41:54+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from seearele ↑Wed Aug 14, 2019 5:33 pm at Wed Aug 14, 2019 5:33 pm
>
> 
daemon1 wrote: ↑Wed Apr 24, 2019 11:13 pm
GuillermoGatoto wrote: ↑Wed Apr 24, 2019 10:56 am
Hi! 

Does anyone know how to access the voice files? 

I can't seem to find them after extracting everything with the tool. I think only sound effects like robot sounds and footsteps are extracted. 

Thanks!

Voice files are extracted.


Please clarify how can voice files should be extracted - there is nothing about it in instruction.

First of all I can't understand where is .core files for the localized sentences. I suppose there should be thousands of such files, but I searched for them in sounds/ and localized/ directories - seems there is nothing here.

Secondly, I found something similar to music, but this is can not be extracted too. For example I found a file packed_pink/sounds/music/credits/wav/credits_thematic.core - nothing extracted. The same problem with credits.soundbank.core, real .soundbank is not extracted for me.

Is there anyone who succeeded to get the original voice/music files?

I'm trying to figure this out for a weeks, it seems that tool does not support for that and that’s why. Let’s go to file localized\sentences\aigenerated\aloy\sentences.core. As I suppose most .core files do not contain any real data inside, but have a lot of meta information, for example describing relationships between objects in game engine, but this «sentences.core» file seems contains something interesting. If we will dive into it we will find that this file have relationships between sentences and their voice acting. It seems that the voice id is as follows: SENTENCE_00357891-7f50-4b77-879c-423156afd227 where 00357891-7f50-4b77-879c-423156afd227 is the unique identifier of the object in the data engine of the game and SENTENCE is the object type. Also we can see that there is a link to the directory localized/voices/aloy. And actually we have such .core file. I will make the assumption that localized/voices/aloy is another object and should contain a lot of SENTENCE objects. It seems that there should be voice files in a very large number. In theory, this should be unpacked, but for some reason this does not happen. Also in the .core file itself there is no information about its contents, there are only language translations. I tried to search with a hex editor in all .bin files, but it seems that they are somehow obfuscated or packed and it does not work to find the occurrences. It would be much easier to understand what is in the .bin files, but the author did not publish the source code of his tool.

@daemon1 please help us. Maybe we are doing something wrong? Can you or somebody else show us an example of how to extract voice files correctly? Instruction/vid or something like that?
## Post #151
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2019-08-22T13:54:22+00:00
- Post Title: Re: Horizon Zero Dawn

Awesome work as usual  Thanks for the tools.

Do I need to convert or run the .dds texture files? For the robot models the extracted dds files are working but when I try one of the static mesh I can't see any image data even though the dds file is around 25mb.
Mesh that I extracted is from: models/building_blocks/foundry/door/components/door_b015_c001_resource
The materials txt indicate that texture is in: models/building_blocks/foundry/door/textures/door_b015_set
That set extracts three dds files 
door_b015_set00_type_3_dx10
door_b015_set01_type_1_dx10
door_b015_set02_type_132_dx10

However I am not able to get any image data from any of these files. How should I go about extracting textures for static meshes?

Similarly for robot models, for stalker: models/characters/robots/stalker/animation/parts/body
I am extracting textures from: models/characters/robots/stalker/textures/revision/stalker_set
Which gives me:
stalker_set00_type_3_dx10
stalker_set01_type_1
stalker_set02_type_132_dx10
Out of the above, _type_1 is fine (diffuse ma). However the other two files are not readable  Assume these are the normal and metal/roughness map?
## Post #152
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-08-22T23:46:07+00:00
- Post Title: Re: Horizon Zero Dawn

Files that end with 'dx10' are encoded in a newer dds format that for some reason hasn't been widely implemented in image editing software (like GIMP).  The only option is to convert these files using a program like Noesis (which CAN open newer dds formats), or get the Photoshop plugin.
## Post #153
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2019-08-23T07:25:56+00:00
- Post Title: Re: Horizon Zero Dawn

Thanks! I can extract those dds images using Noesis.

> Reply from nightwolf1982 ↑Fri Aug 23, 2019 7:46 am at Fri Aug 23, 2019 7:46 am
>
> 
Files that end with 'dx10' are encoded in a newer dds format that for some reason hasn't been widely implemented in image editing software (like GIMP).  The only option is to convert these files using a program like Noesis (which CAN open newer dds formats), or get the Photoshop plugin.
## Post #154
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2019-09-05T09:11:43+00:00
- Post Title: Re: Horizon Zero Dawn

1. you need to place the tool in your "packed_pink" horizon folder, or better, i recommend using included ini file (just change your folder). If you use this INI - you can use the tool from any folder.

can anyone please share this .ini file?
## Post #155
- Username: iLeonidze
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 06, 2019 2:08 am
- Post datetime: 2019-09-06T06:30:46+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from parttimegamer15 ↑Thu Sep 05, 2019 5:11 pm at Thu Sep 05, 2019 5:11 pm
>
> 
1. you need to place the tool in your "packed_pink" horizon folder, or better, i recommend using included ini file (just change your folder). If you use this INI - you can use the tool from any folder.

can anyone please share this .ini file?

This file included in archive attached to first post in topic
## Post #156
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2019-09-19T21:29:31+00:00
- Post Title: Re: Horizon Zero Dawn

How I got mine to work is I made a run.bat file and typed "horizon /p list.txt" this then just ran it and it dumped all my files.
[](https://ibb.co/jTQxkh0)

still having problems getting all of the .core files to extract. Most of the ones I try say asset.skipped. Or it gives me a 0bit .smd file. So I'm not sure If I'm doing it wrong or if the tool just needs updated. 
[](https://ibb.co/WFsgbHn)
Here is the extracted model of the Hyena. 
But for some reason I cant find the textures to him. 
[](https://imgbb.com/)
Then I was able to get Direwolf and his texture map but it seems really dark compared to the game. Maybe the original DDS compression ? 
[](https://ibb.co/0B2nX58)
## Post #157
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-09-20T03:17:22+00:00
- Post Title: Re: Horizon Zero Dawn

I managed to get the Hyena textures no problem.  They should be in the packed_pink\models\characters\robots\hyena\textures folder (after extracting them from the game archives).
## Post #158
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2019-09-20T07:04:02+00:00
- Post Title: Re: Horizon Zero Dawn

Yeah I found everything, I now have all the models and animations. Now I'm trying to merge the acsii files together for the bone/animation data.
## Post #159
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2019-10-21T19:12:10+00:00
- Post Title: Re: Horizon Zero Dawn

pls anybody send me ingame subtitles font tnx tnx
## Post #160
- Username: Sinnery32
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jan 05, 2017 3:24 pm
- Post datetime: 2019-11-10T20:22:20+00:00
- Post Title: Re: Horizon Zero Dawn

Всем привет, ребята, кто мне может объяснить как достать скелет персонажа ? 
Я до сих пор не могу понять в чем дело.... 
Буду очень благодарен если кто то детально объяснить что нужно сделать )


Hello everyone, guys, who can explain to me how to get a skeleton of a character?
I still can’t understand what’s the matter ....
I would be very grateful if someone would explain in detail what needs to be done)
## Post #161
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2019-11-10T22:57:22+00:00
- Post Title: Re: Horizon Zero Dawn

You have to have the rootbone and other bone file, open them in an editor, merge together. Then run Horizon on it should produce what you need. Everything is explained in the tutorial pretty clearly.
## Post #162
- Username: Sinnery32
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jan 05, 2017 3:24 pm
- Post datetime: 2019-11-11T17:58:41+00:00
- Post Title: Re: Horizon Zero Dawn

I am a little amateur in this, you can explain again ...
Only with an action plan.
I beg you.
## Post #163
- Username: mostlyhuman
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 01, 2018 9:42 am
- Post datetime: 2020-01-22T09:09:29+00:00
- Post Title: Re: Horizon Zero Dawn

Im having the same 0KB smd issue, how did you overcome this?

Getting this error when i try to unpack a .core file
Unhandled Exception: System.NullReferenceException: Object reference not set to an instance of an object.
   at ?????????????????????????????????????????.?????????????????????????????????????????(String[] )
## Post #164
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-02-06T15:50:13+00:00
- Post Title: Re: Horizon Zero Dawn

Thank you very much for the tool daemon1  . 
I extracted all resources on my packed_pink folder, and now i have a few folders on it, at this poit all good, but i don't know where are the models stored. For example where are the model of Aloy? How can I extract it and open with Noesis? 
Thanks!!
## Post #165
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-02-11T08:10:39+00:00
- Post Title: Re: Horizon Zero Dawn

After spending many hours trying to extract the models and thanks to the invaluable help of [Raban](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=63017), I leave you a small mini guide for people like me who are starting on this.

My big problem was the copy of the game, I tried with a PKG of the edition European Complete Edition and as a result it generated empty models. I lost a couple of hours on it, because I thought the problem was mine, but no, it must be that the Daemon tool is not compatible with this version of the game. So i reomend use a copy of the European Standard version (Code: CUSA07319), you can get from the original disk with an a hacked PS4 o try to find an a Fake PKG of the Game (41 GB Aprox)

We will need this software: 

1- Oviusly the daemon1's tool [ i use this version](https://forum.xentax.com/viewtopic.php?f=16&t=17726&start=105#p151411)
2- The latest version of PKG tool, [ you can get it here](https://github.com/pearlxcore/PS4-PKG-Tool/releases)
3- The latest version of [noesis](https://richwhitehouse.com/index.php?content=inc_projects.php) for show and export the models
4- A lot of patience, the process is tedious   

1- The first thing we you need is extract the PKG, for this we use PS4 PKG Tool, is easy, open the folder were are stored the PKG > Right click on the game > Extract PKG Contents.
2- Now get the daemon1 tool and put it inside  "packet_pink" folder.
3- Edit (or create if not exist) the file horizon.ini, and paste inside it the path to the packet_pink folder (including "packet_pink")
4- Open the tool, if we do correctly the tool was generate one big file "res.txt"
5- You can filter the file to be alone with what we want to extract. You can use Excel to filter this.
6- Now i copy paste the PM that [Raban](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=63017) sent me, I asked him as an example the model of the red fox.

> 1. create a .txt-file, name it "list" and place it in the folder where Daemon's horizon.exe is
>
> 
>
> 2. paste these lines into that .txt:
>
> models/characters/animals/redfox/animation/parts/redfox_lx
>
> models/characters/animals/redfox/animation/skeletons/skeleton_rootbone
>
> 
>
> 3. run horizon from windows-command-line like this "horizon /x list.txt"
>
> 
>
> 4. you should now have some .core-files
>
> 
>
> 5. drag and drop redfox_lx.core on horizon.exe; you should get
>
> redfox_lx.core.smd
>
> redfox_lx.core.mesh.ascii
>
> a matrices file
>
> and a bunch of txt which contain the ressource paths for the textures (you can paste those in a new list.txt afterwards)
>
> 
>
> 6. now drag and drop skeleton_rootbone.core on horizon.exe; this should yield:
>
> skeleton_rootbone.core.smd
>
> skeleton_rootbone.core.mesh.ascii
>
> 
>
> 7. open "skeleton_rootbone.core.smd" with the notepad and copy everything that's in there
>
> 
>
> 8. open "redfox_lx.core.smd" with the notepad and paste what you've copied - be careful though you probably have to delete some lines from the target or source file (I think the source already had the header in there);
>
> it should look like this:
>
> version 1
>
> nodes
>
> 0 ...
>
> 1 ...
>
> ... (listing all the bones)
>
> end
>
> skeleton
>
> time 0 (meaning the bind pose of the skeleton)
>
> 0 ...
>
> 1 ...
>
> ... (listing of Rot and Loc of each bone for that pose, meaning their default position)
>
> end
>
> triangles (now begins the description of the geometry that stuff is what's already written in)
>
> assets/bla/blabla
>
> 0 ...
>
> 0 ...
>
> 0 ...
>
> ...
>
> end
>
> 
>
> 8.5. make sure you don't have any repeating lines; having the lines "end|skeleton" two times in the file is a big no-no
>
> 
>
> 9. you should be good to go now

Now we can get the model with bones, so we can load it in Noesis. So open noesis, and navigate to the packet_pink folder, and open redfox smd file. And that it, if you do correctly you can see the fox.

Now we can export it to use in Blender for example. To do it, in Noesis select File > Export..., and select as Collada. In blender create a new scene, remove de default cube, and import this exported file on it. 

PD> If you extract the textures, you can use it directly in the latest version of Blender. This is an example of result (Remember, I'm noob in 3D design   )



PD2> Many thanks especially to Raban for the help provided and to Daemon1 for his fantastic tool
## Post #166
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2020-02-11T22:57:36+00:00
- Post Title: Re: Horizon Zero Dawn

There are source tools available that allow you to import smd files directly into blender.
## Post #167
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-02-12T07:23:38+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from nightwolf1982 ↑Wed Feb 12, 2020 6:57 am at Wed Feb 12, 2020 6:57 am
>
> 
There are source tools available that allow you to import smd files directly into blender.

I did not know, I am very new to this.
## Post #168
- Username: stab2486
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 27, 2020 6:14 am
- Post datetime: 2020-03-01T20:24:35+00:00
- Post Title: Re: Horizon Zero Dawn

Having problems with the SMD files generated by horizon.exe. Either they're empty (usually for the body.core files), or, when I open them up in notepad, all the coordinates for the vertices are just a bunch of 0s. So far I've tried this on the Behemoth, the Strider, the Grazer, the Scrapper, and the Thunderjaw, has anyone else found that certain models just won't extract? I've tried the standard edition (CUSA07319) and the complete edition (CUSA10212).
## Post #169
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-03T07:37:00+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from stab2486 ↑Mon Mar 02, 2020 4:24 am at Mon Mar 02, 2020 4:24 am
>
> 
Having problems with the SMD files generated by horizon.exe. Either they're empty (usually for the body.core files), or, when I open them up in notepad, all the coordinates for the vertices are just a bunch of 0s. So far I've tried this on the Behemoth, the Strider, the Grazer, the Scrapper, and the Thunderjaw, has anyone else found that certain models just won't extract? I've tried the standard edition (CUSA07319) and the complete edition (CUSA10212).
You can follow [ this post ](https://forum.xentax.com/viewtopic.php?f=16&t=17726&start=150#p159845) but, i still have the same problems with many models, the SMD have a bunch of 0s. It would be helpful if Daemon or Raban told us what is the gamecode they used to do their tests...
## Post #170
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-03-03T15:01:21+00:00
- Post Title: Re: Horizon Zero Dawn

i dont know which code i used, was too long ago
## Post #171
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2020-03-04T15:02:56+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from gokuhs ↑Tue Mar 03, 2020 3:37 pm at Tue Mar 03, 2020 3:37 pm
>
> 
 It would be helpful if Daemon or Raban told us what is the gamecode they used to do their tests...

Sorry, I don't have the files anymore and don't remember the CUSA-code. 

I can tell you via pm from where I obtained the files, If you want to check yourself. Though I don't know if the links are still alive.
## Post #172
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-03-04T17:06:41+00:00
- Post Title: Re: Horizon Zero Dawn

you can find decrypted pkg on rutracker.org
## Post #173
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-05T07:30:48+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from erik945 ↑Thu Mar 05, 2020 1:06 am at Thu Mar 05, 2020 1:06 am
>
> 
you can find decrypted pkg on rutracker.org
Yes, but our problem is what version of the game was used to create the extraction tool.
## Post #174
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-03-05T08:13:48+00:00
- Post Title: Re: Horizon Zero Dawn

Well, only the author can tell you this. As far I remember, the tool worked with this version of the game.
But I can’t vouch - it has long been.
## Post #175
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-05T08:19:17+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from erik945 ↑Thu Mar 05, 2020 4:13 pm at Thu Mar 05, 2020 4:13 pm
>
> 
Well, only the author can tell you this. As far I remember, the tool worked with this version of the game.
But I can’t vouch - it has long been.

But you try to extract various models? Because we have the problem that it apparently works, but the files it generates are invalid. And it does not happen with everyone, with some it works well (for example the fox I have posted) but others does not work..
## Post #176
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-03-05T08:35:06+00:00
- Post Title: Re: Horizon Zero Dawn

I don’t remember, and I don't studied all the models thoroughly.
Sorry.
## Post #177
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-03-05T15:40:47+00:00
- Post Title: Re: Horizon Zero Dawn

Actually, the tool MUST work with any version of the game, and for ALL models. I dont know how it could be possible that something is NOT working. At least everything I tried worked fine.
## Post #178
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-05T16:01:02+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Thu Mar 05, 2020 11:40 pm at Thu Mar 05, 2020 11:40 pm
>
> 
Actually, the tool MUST work with any version of the game, and for ALL models. I dont know how it could be possible that something is NOT working. At least everything I tried worked fine.

As I told you by PM, my first intent with a version of the game with expansion was not able to extract the fox, I had the error that told you that it generates the files with 0s, instead with another version of the game i can extract it, following the same steps on the same files. But I still have the problem with many other models, the tool generate files with all positions in 0s...

I also appreciate your great effort creating the tool, and for that I was trying to find the same version you used to create the tool. Maybe it's because of the S.O. or maybe it's because of the oo2core_5_win64.dll file
## Post #179
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-03-05T17:32:43+00:00
- Post Title: Re: Horizon Zero Dawn

it can't be oo2core_5_win64.dll
i dont know what is S.O.
if you have 0's, the tool must give you some error
## Post #180
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-06T07:29:49+00:00
- Post Title: Re: Horizon Zero Dawn

I'm downloading another copy of the game, this afternoon if it finish i try again and tell you all steps i follow and all output of the tool If it's any help. Thanks daemon
## Post #181
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-03-06T08:17:30+00:00
- Post Title: Re: Horizon Zero Dawn

I have just tested the files mentioned in post above and all 5 robots are extracted and also converting just fine, you guys need to be more specific what is your problem, extraction and conversion are two different processes, no matter what.

And following exact steps that are posted by daemon1 will give you correct extracted and converted assets.
If it matters, I just tested a Complete Edition of the game.
## Post #182
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-06T11:42:14+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from mono24 ↑Fri Mar 06, 2020 4:17 pm at Fri Mar 06, 2020 4:17 pm
>
> 
I have just tested the files mentioned in post above and all 5 robots are extracted and also converting just fine, you guys need to be more specific what is your problem, extraction and conversion are two different processes, no matter what.

And following exact steps that are posted by daemon1 will give you correct extracted and converted assets.
If it matters, I just tested a Complete Edition of the game.

I think I have followed the steps well. In [this post](https://forum.xentax.com/viewtopic.php?f=16&t=17726&start=150#p159845) I try to make a small step by step guide. But for example with the fox it has worked (and some other animals, I tried and it worked) but for other models it did not.

As I tell Daemon I am downloading a new copy, as soon as I have it I try again and post here all the information I can. (Whether it works or doesn't work)
## Post #183
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-03-06T15:11:45+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from gokuhs ↑Fri Mar 06, 2020 7:42 pm at Fri Mar 06, 2020 7:42 pm
>
> ...but for other models it did not.
What are the names of assets that do NOT work?
## Post #184
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-07T13:06:56+00:00
- Post Title: Re: Horizon Zero Dawn

Ok this morning  the donwload finished and I extracted the PKG with PS4.PKG.Tool, and this are my steeps.

1- I copy inside packed_ping horizon.exe and oo2core_5_win64.dll, and i create new file horizon.ini and put in it the full path to the folder.
2- On CMD console i run horizon.exe without arguments, don't produce any output, and generate res.txt correctly
3- I filter the file and generate the file "aloy.txt" (i attached it to this post). I'm trying to extract all parts of Aloy character. May be fault parts, i don't know.
4- I create a new folder, and move Horizon.exe, Horizon.ini, oo2core_5_win64.dll, and aloy.txt inside it
5- In cmd console i change to the new directory and i execute Horizon.exe /x aloy.txt. In the  cmd don't get any output, and it extract all .core files.
6- Now I execute horizon over all .core files. I use this: for /f %f in ('dir /b *.core') do Horizon.exe %f. I have multiple outputs on the console, and some files crashing the app, for example Horizon.exe mesh_skeleton_rootbone.core with error : 
Excepción no controlada: System.IndexOutOfRangeException: Índice fuera de los límites de la matriz. (In English: "Unhandled Exception: System.IndexOutOfRangeException: Index was outside the bounds.")
Others files for example Horizon.exe skirtflapd_ct_a_lx.core crash the tool but don't get any error on the console
7- Ok, let's check with noesis. In Aloy_ct_a_lx have the body with the customer. In mode.core.smd i have the hair. But all other models are empty. May be this is correct. But for example, where is the head?
8- Finding in res.txt i find various "heads" in models\characters\humans\heads\female\* ok i try to extract the file models\characters\humans\heads\female\ambert\animation\parts\head_lx.core, and i attached the wrong generated smd file. 

At this point i'm struck, i can associate textures in blender to this part and work fine, but i can't find the rest parts, and i don't know if is my fault or some other problem... 

Dameon1 I see in your first post you can extracted aloy, but i don't understand if i'm doing something wrong or is other problem.

> Reply from mono24 ↑Fri Mar 06, 2020 11:11 pm at Fri Mar 06, 2020 11:11 pm
>
> 
What are the names of assets that do NOT work?
In this latest version i downloaded (CUSA07319 Ver 1.00 and 40.11GB) most of other models works, for the example in other copies i can't extract the rabbit animal, but in this is working well... except for the head of Aloy, but i think is my problem I don't know where are stored the files...
[resources_files.zip](https://xentaxbackup.github.io/file/17645_resources_files.zip)
## Post #185
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-03-07T14:31:07+00:00
- Post Title: Re: Horizon Zero Dawn

i have NO IDEA how can you get those empty files
send me your oodle5 dll
or check that S.O. whatever it is
## Post #186
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-07T16:13:05+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Sat Mar 07, 2020 10:31 pm at Sat Mar 07, 2020 10:31 pm
>
> 
i have NO IDEA how can you get those empty files
send me your oodle5 dll
or check that S.O. whatever it is

Ok, i will send you my oodle5.dll by PM, my S.O. is Win7 installed on a VirtualBox. I try with Win10 with the same result. (Virtualized too)
## Post #187
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-03-07T17:05:49+00:00
- Post Title: Re: Horizon Zero Dawn

your oodle is fine
try deleting all files from packed_pink, except 2:

initial.bin
remainder.bin
## Post #188
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2020-03-07T18:34:24+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from gokuhs ↑Sat Mar 07, 2020 9:06 pm at Sat Mar 07, 2020 9:06 pm
>
> 
except for the head of Aloy, but i think is my problem I don't know where are stored the files...

If I remember correctly it's these (named after the actress Hannah Hoekstra):

models/characters/humans/heads/female/hannah/animation/parts/head_lx
models/characters/humans/heads/female/hannah/animation/parts/neckscar_fresh_lx
models/characters/humans/heads/female/hannah/animation/skeletons/skeleton_c_spine_sjnt_4
models/characters/humans/heads/female/hannah/textures/aloyheadcap_set
models/characters/humans/heads/female/hannah/textures/hannah_head_a_set
models/characters/humans/heads/female/hannah/textures/hannah_head_b_set
models/characters/humans/heads/female/hannah/textures/hannah_head_set
## Post #189
- Username: stab2486
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 27, 2020 6:14 am
- Post datetime: 2020-03-08T19:52:19+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Sat Mar 07, 2020 10:31 pm at Sat Mar 07, 2020 10:31 pm
>
> 
i have NO IDEA how can you get those empty files
send me your oodle5 dll
or check that S.O. whatever it is

Would you mind looking at my dll too? I tried PMing it, but the site says it's an invalid format. Also, I forgot to mention, I've been using the first version of horizon.exe since my Anti Virus keeps flagging the updated versions for whatever reason.
## Post #190
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-03-09T05:52:02+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from stab2486 ↑Mon Mar 09, 2020 3:52 am at Mon Mar 09, 2020 3:52 am
>
> 
Would you mind looking at my dll too? I tried PMing it, but the site says it's an invalid format. Also, I forgot to mention, I've been using the first version of horizon.exe since my Anti Virus keeps flagging the updated versions for whatever reason.
as i said before, dll can't be a problem
but just in case, i asked to check it too, and as expected, it was not a problem
## Post #191
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-09T07:33:02+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Raban ↑Sun Mar 08, 2020 2:34 am at Sun Mar 08, 2020 2:34 am
>
> 
If I remember correctly it's these (named after the actress Hannah Hoekstra):

models/characters/humans/heads/female/hannah/animation/parts/head_lx
models/characters/humans/heads/female/hannah/animation/parts/neckscar_fresh_lx
models/characters/humans/heads/female/hannah/animation/skeletons/skeleton_c_spine_sjnt_4
models/characters/humans/heads/female/hannah/textures/aloyheadcap_set
models/characters/humans/heads/female/hannah/textures/hannah_head_a_set
models/characters/humans/heads/female/hannah/textures/hannah_head_b_set
models/characters/humans/heads/female/hannah/textures/hannah_head_set
YES!! It's works!! As I assumed the fault was mine, I feel ashamed. I didn't realize they were the names of the actors and actresses. Seriously, THANK YOU VERY MUCH!

> Reply from daemon1 ↑Sun Mar 08, 2020 1:05 am at Sun Mar 08, 2020 1:05 am
>
> 
your oodle is fine
try deleting all files from packed_pink, except 2:

initial.bin
remainder.bin
Sorry for the dizziness I've given you these days. Deleted the rest of the files has also worked for what helps me save space. Thank you also for your efforts
## Post #192
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-03-09T07:47:15+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from gokuhs ↑Mon Mar 09, 2020 3:33 pm at Mon Mar 09, 2020 3:33 pm
>
> 
Sorry for the dizziness I've given you these days.
you still dont answer if you got things working.
ALL files should export without ANY errors, and no zeroes inside, including skirtflaps and all other model files.
You must never run the tool on all files in one folder, because it will cause errors with skeletons and resulting skeletons will be broken.
But if you dont need skeletons, it may be ok, but still must be no files with zeroes.

So, can you answer, do you still have files with zeroes?
## Post #193
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-09T11:15:13+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Mon Mar 09, 2020 3:47 pm at Mon Mar 09, 2020 3:47 pm
>
> 
you still dont answer if you got things working.
Yes for the example was post Raban i can extract all without problems.

> Reply from daemon1 ↑Mon Mar 09, 2020 3:47 pm at Mon Mar 09, 2020 3:47 pm
>
> 
ALL files should export without ANY errors, and no zeroes inside, including skirtflaps and all other model files.
You must never run the tool on all files in one folder, because it will cause errors with skeletons and resulting skeletons will be broken.
But if you dont need skeletons, it may be ok, but still must be no files with zeroes.

So, can you answer, do you still have files with zeroes?

Ok, Ok, I have filter the file and left only this:

> models/characters/humans/aloy/animation/parts/aloy_ct_a_lx
>
> models/characters/humans/aloy/animation/parts/aloyhair_ct_a_lx
>
> models/characters/humans/aloy/animation/skeletons/mesh_skeleton_rootbone

And i can extract the model and the hair without problem drag and drop one by one of cores file. And don't generate any file with zeros. May be the problem was is It's what you say, I try to extract files that have nothing to do with each other...

With this in mind, I no longer have the problem of generating files with zeros.
## Post #194
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-03-09T11:39:44+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from gokuhs ↑Mon Mar 09, 2020 7:15 pm at Mon Mar 09, 2020 7:15 pm
>
> 
With this in mind, I no longer have the problem of generating files with zeros.
Impossible. This cannot be.
Yesterday I tried  running on all files in your "aloy.txt" and there was no single file with zeros.
So we still dont know the reason of your problem with files with zeros.

It means you still have it.
## Post #195
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-09T12:13:52+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Mon Mar 09, 2020 7:39 pm at Mon Mar 09, 2020 7:39 pm
>
> 
Impossible. This cannot be.
Yesterday I tried  running on all files in your "aloy.txt" and there was no single file with zeros.
So we still dont know the reason of your problem with files with zeros.

It means you still have it.

Ok, with the aloy.txt file i was attached before I execute Horizon.exe /x aloy.txt
And now i execute this: for /f %f in ('dir /b *.core') do Horizon %f

For example,  i get the file aloyna_bags_ct_a_lx.core_0.smd with all trianges with 0 or aloyna_chestplate_ct_a_lx.core_0.smd same, i attached both in the zip file on this post, and the ouput of the cmd console
[aloy.zip](https://xentaxbackup.github.io/file/17659_aloy.zip)
## Post #196
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-03-09T13:13:01+00:00
- Post Title: Re: Horizon Zero Dawn

ok i see that on some files this error occurs during oodle decompression:
System.AccessViolationException ... and something about memory

in all such cases you will get zero filled files.
Problem is, i never got this happen, so i dont know why on your machine its not working.
## Post #197
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-09T13:22:10+00:00
- Post Title: Re: Horizon Zero Dawn

Maybe it is for doing it in batch, and without many having much relation to the previous ones ... but doing it separately and deleting file "matrices" between each one the problem does not happen, or may be is bug on Virtualbox... i don't know...
## Post #198
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-03-09T13:24:24+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from gokuhs ↑Mon Mar 09, 2020 9:22 pm at Mon Mar 09, 2020 9:22 pm
>
> 
Maybe it is for doing it in batch, and without many having much relation to the previous ones ... but doing it separately and deleting file "matrices" between each one the problem does not happen, or may be is bug on Virtualbox... i don't know...
it can't be batch or relation to the previous ones, or matrices
must be a bug on Virtualbox
## Post #199
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-09T15:47:05+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Mon Mar 09, 2020 9:24 pm at Mon Mar 09, 2020 9:24 pm
>
> 
it can't be batch or relation to the previous ones, or matrices
must be a bug on Virtualbox
This afternoon I will install Windows on an old computer and try.
Meanwhile, If you wish you can try with this model, with any other file i try this:

Horizon.exe /e models/characters/humans/aloycarjastormbringercostume/animation/parts/aloyhair_ct_a_lx
And drag and drop the core file in Horizon.exe. The generated smd is filled with 0 but the tool don't crash.
## Post #200
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-03-09T16:01:34+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from gokuhs ↑Mon Mar 09, 2020 11:47 pm at Mon Mar 09, 2020 11:47 pm
>
> 
Horizon.exe /e models/characters/humans/aloycarjastormbringercostume/animation/parts/aloyhair_ct_a_lx
And drag and drop the core file in Horizon.exe. The generated smd is filled with 0 but the tool don't crash.
works fine as all other files. Its not the tool thats crashing. Its your O.S.
## Post #201
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-09T20:29:05+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Tue Mar 10, 2020 12:01 am at Tue Mar 10, 2020 12:01 am
>
> 
works fine as all other files. Its not the tool thats crashing. Its your O.S.

I begin to think that I have bad luck. I installed Win 10 on my laptop, and i have the same result. And after hitting the shit of Windows Defender (detect your utility as a Trojan) the result I have obtained is the same.

I am going to send you a PM with an a link to my "packed_pink" folder on which I am testing, with the initial.bin and remainder.bin files included. The download is heavy so if you feel like it and are curious, try it with my files. If fails may be you can debug the tool code and find the reason...

If this works for you, I shoot myself in the head.
## Post #202
- Username: ashitaka3369
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jun 29, 2019 5:39 am
- Post datetime: 2020-03-10T08:53:38+00:00
- Post Title: Re: Horizon Zero Dawn

i also try few month ago to extract model from horizon and that also ended with empty files for me, but no one was complaining about it and i was thinking that came from me or an update of the game
## Post #203
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-10T09:31:49+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from ashitaka3369 ↑Tue Mar 10, 2020 4:53 pm at Tue Mar 10, 2020 4:53 pm
>
> 
i also try few month ago to extract model from horizon and that also ended with empty files for me, but no one was complaining about it and i was thinking that came from me or an update of the game
Let's see if with what I have happened if daemon try it, and may be we can identify what the problem. Because it also happens to me and I am using the same copy used by another user of this thread and it worked for him ...
## Post #204
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-03-10T17:13:24+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from gokuhs ↑Tue Mar 10, 2020 4:29 am at Tue Mar 10, 2020 4:29 am
>
> 
I am going to send you a PM with an a link to my "packed_pink" folder on which I am testing, with the initial.bin and remainder.bin

your initial.bin and remainder.bin are both corrupted.   
Whatever you used to get them is broken. Never use that tool.
## Post #205
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-10T19:44:47+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Wed Mar 11, 2020 1:13 am at Wed Mar 11, 2020 1:13 am
>
> 
your initial.bin and remainder.bin are both corrupted.   
Whatever you used to get them is broken. Never use that tool.
I can not believe it. Don't tell me I've wasted a lot of time when the extraction tool is failing?   
I take advantage of that since I have installed Windows to extract the PKG again...
## Post #206
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-10T23:59:27+00:00
- Post Title: Re: Horizon Zero Dawn

Yes! Now i can extract the model without problem! I use another program  to extract it! 
I use to extract it PS4PKGViewer by LMAN, and for now 0 problems
Many thanks for your help Daemon1 and for your contributions.
## Post #207
- Username: stab2486
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 27, 2020 6:14 am
- Post datetime: 2020-03-11T02:35:09+00:00
- Post Title: Re: Horizon Zero Dawn

Sweet! Just tried switching to the PS4PKGViewer like gokuhs did and it just did the trick. Little bit disappointed though to see just how much of the detail is all normal mapping, though it seems there's options to convert normal maps into height maps. Either way, big thanks daemon1! As an artist I've been super interested in using the machines for reference and kitbashing, and this is a huge help. I was worried I'd have to try photogrammetry, which probably wouldn't really even work with the limited photomode in the game. Next up, seeing if I can generate complete models with skeletons, without any trouble.
## Post #208
- Username: stab2486
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 27, 2020 6:14 am
- Post datetime: 2020-03-15T20:07:03+00:00
- Post Title: Re: Horizon Zero Dawn

ThunderJaw_01.jpg (200.17 KiB) Viewed 192 times



Put together a Thunder Jaw model manually. Couldn't get horizon to generate the full model with the skeleton and weighted parts, but I think that was probably because I ran horizon on the .core model files before putting the skeleton_rootbone and .animskel files in the same folder. 

Edit: Ran horizon on parts .core files after moving mesh_skeleton_rootbone, .animskel, and robot_modelhelpers into the folder. The .bat isn't empty, it just says "File not found: [mesh_skeleton]"

Also, has anyone tried looking for Cauldron model files?
## Post #209
- Username: rushard
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 24, 2020 8:08 pm
- Post datetime: 2020-03-24T12:31:36+00:00
- Post Title: Re: Horizon Zero Dawn

How can I get sound files from the game?
## Post #210
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-03-26T21:39:57+00:00
- Post Title: Re: Horizon Zero Dawn

A script for batch file extraction.
You will need the original daemon1's tool.
Edit the "INTERFACE" section:
Select the paths to the tool and files, select the steps (True - execute, False - skip).
Step 0 and 1 need to be performed once, then you can just turn them off
(step_0_create_res_file = False
step_1_unpack_bin = False)
resources are extracted to the tool_path
Models and textures will be converted ONLY from the work_dir folder (now configured for robot scout)
In the process of step 3, the script creates skel_work folders - for skeletons and join_geo - for finished geometry combined with skeletons.
These models are referred to as __join __ (the name of the used skeleton ) and include all fragments from the parts folder.

step4_convert_robots - the most complex, I recommend converting only one robot at a time. Disable this step when it is not needed - otherwise it will try to convert each character as a robot, this can lead to errors.
To perform step 4, you must first perform step 3. Make sure step_3_generate_chars = True
The operation of the algorithms is tied to folder names. Better not rename them if you are not sure.
specify the path to the folder for the templates in the variables robot_template_dir and robot_template_dlc_dir

After successful completion of step 4, in the join_geo folder will be created files the __1_joinRobot_static_zero_skeleton, __2_joinRobot_skin_custom_skeleton, __3_joinRobot_fix_skeleton.
You must  sequentially load them into your 3d editor (max, blender, etc). Make sure that when loading skeleton only it pose are updated, the skeleton itself should not be loaded again - otherwise you will get three copies of it.
First load __1_joinRobot_static_zero_skeleton first - it contains destructible parts of the robot
Second load __2_joinRobot_skin_custom_skeleton second - contains the base of the robot
Third load __3_joinRobot_fix_skeleton - fixes the position of bones and destructible parts
Now you must have correct model of robot

During the script operation, may appear windows with error (crash Horizon) - this is normal. The script itself will close them.
During all the work of the programs, you will need the source *.bin files - never remove them.
Make sure that no extraneous .bin files get into the folder with source *.bin files - this can lead to errors.
Tested on python 3.7, but should work on older 3.x

Good luck.
[unpacker_hz_v34.7z](https://xentaxbackup.github.io/file/17817_unpacker_hz_v34.7z)
## Post #211
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-03-26T21:45:28+00:00
- Post Title: Re: Horizon Zero Dawn

preview:
[demo.png](https://xentaxbackup.github.io/file/17814_demo.png)
## Post #212
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-03-27T07:42:02+00:00
- Post Title: Re: Horizon Zero Dawn

Thanks erik945 i try it as soon as I have a while
## Post #213
- Username: rushard
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 24, 2020 8:08 pm
- Post datetime: 2020-03-27T13:08:30+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from erik945 ↑Fri Mar 27, 2020 5:39 am at Fri Mar 27, 2020 5:39 am
>
> 
A script for batch file extraction.
You will need the original daemon1's tool.
Edit the "INTERFACE" section:
Select the paths to the tool and files, select the steps (True - execute, False - skip).
Step 0 and 1 need to be performed once, then you can just turn them off
(step_0_create_res_file = False
step_1_unpack_bin = False)
resources are extracted to the tool_path
Models and textures will be converted ONLY from the work_dir folder (now configured for robot scout)
In the process of step 3, the script creates skel_work folders - for skeletons and join_geo - for finished geometry combined with skeletons.
These models are referred to as __join __ (the name of the used skeleton ) and include all fragments from the parts folder.

step4_convert_robots - the most complex, I recommend converting only one robot at a time. Disable this step when it is not needed - otherwise it will try to convert each character as a robot, this can lead to errors.
To perform step 4, you must first perform step 3. Make sure step_3_generate_chars = True
The operation of the algorithms is tied to folder names. Better not rename them if you are not sure.
specify the path to the folder for the templates in the variables robot_template_dir and robot_template_dlc_dir

After successful completion of step 4, in the join_geo folder will be created files the __1_joinRobot_static_zero_skeleton, __2_joinRobot_skin_custom_skeleton, __3_joinRobot_fix_skeleton.
You must  sequentially load them into your 3d editor (max, blender, etc). Make sure that when loading skeleton only it pose are updated, the skeleton itself should not be loaded again - otherwise you will get three copies of it.
First load __1_joinRobot_static_zero_skeleton first - it contains destructible parts of the robot
Second load __2_joinRobot_skin_custom_skeleton second - contains the base of the robot
Third load __3_joinRobot_fix_skeleton - fixes the position of bones and destructible parts
Now you must have correct model of robot

During the script operation, may appear windows with error (crash Horizon) - this is normal. The script itself will close them.
During all the work of the programs, you will need the source *.bin files - never remove them.
Make sure that no extraneous .bin files get into the folder with source *.bin files - this can lead to errors.
Tested on python 3.7, but should work on older 3.x

Good luck.

Thanks for your decision!  Maybe you know where background music is stored?
## Post #214
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-03-27T15:59:52+00:00
- Post Title: Re: Horizon Zero Dawn

Not sure, maybe
...\Image0\packed_pink\sounds\music\... ?
## Post #215
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2020-07-30T10:16:09+00:00
- Post Title: Re: Horizon Zero Dawn

Horizon is coming to PC would it be possible to get an update for PC?
## Post #216
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2020-07-30T10:20:59+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Faithfullfaun ↑Thu Jul 30, 2020 6:16 pm at Thu Jul 30, 2020 6:16 pm
>
> 
Horizon is coming to PC would it be possible to get an update for PC?

And it may even have better graphics
## Post #217
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2020-08-10T04:12:39+00:00
- Post Title: Re: Horizon Zero Dawn

Any word on a PC Tool? And please allow it to extract all files from game and repack. I love to work on a visual mod.
## Post #218
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-08-10T08:04:36+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from d875j ↑Mon Aug 10, 2020 12:12 pm at Mon Aug 10, 2020 12:12 pm
>
> 
Any word on a PC Tool? And please allow it to extract all files from game and repack. I love to work on a visual mod.
[https://github.com/Jayveer/Decima-Explorer](https://github.com/Jayveer/Decima-Explorer)
## Post #219
- Username: sgiath
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 15, 2012 12:25 am
- Post datetime: 2020-08-11T10:37:06+00:00
- Post Title: Re: Horizon Zero Dawn

Any news on extracting sounds from the PC version?
I think that nobody got the music files from the PS4 version...
## Post #220
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2020-08-12T03:19:59+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from qs12 ↑Mon Aug 10, 2020 4:04 pm at Mon Aug 10, 2020 4:04 pm
>
> 
d875j wrote: ↑Mon Aug 10, 2020 12:12 pm
Any word on a PC Tool? And please allow it to extract all files from game and repack. I love to work on a visual mod.

https://github.com/Jayveer/Decima-Explorer

Awesome but now i have another road block. Can't edit the .core files for visuals for the game. Love to edit these to push visuals.
## Post #221
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2020-08-12T07:07:42+00:00
- Post Title: Re: Horizon Zero Dawn

anyway for extract audio sound
## Post #222
- Username: mathieuraw22
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 16, 2020 4:05 pm
- Post datetime: 2020-08-16T14:27:21+00:00
- Post Title: Re: Horizon Zero Dawn

I don't know how to do to extract so if someone can send me Aloy files with texture and cetera. Like that I import direct in 3DS max, thnaks.
## Post #223
- Username: JavedWilde
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 18, 2020 7:24 pm
- Post datetime: 2020-08-18T12:30:21+00:00
- Post Title: Re: Horizon Zero Dawn

Im geting this error
im trying to extract files from the pc version

I used DecimaExplorer by Jayveer to extract the core files

but have no clue how to proceed from there
any help
## Post #224
- Username: JavedWilde
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 18, 2020 7:24 pm
- Post datetime: 2020-08-18T12:32:33+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from mathieuraw22 ↑Sun Aug 16, 2020 10:27 pm at Sun Aug 16, 2020 10:27 pm
>
> 
I don't know how to do to extract so if someone can send me Aloy files with texture and cetera. Like that I import direct in 3DS max, thnaks.

i found this
[https://www.deviantart.com/luxox005/art ... -730788272](https://www.deviantart.com/luxox005/art/Horizon-Zero-Dawn-Aloy-730788272)
## Post #225
- Username: MrMendelli
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 19, 2020 8:15 am
- Post datetime: 2020-08-19T01:54:11+00:00
- Post Title: Re: Horizon Zero Dawn

I don't know if you still watch this thread, but it seems like it was last active recently. Are there plans for PC support? Will the tool eventually be open source?
## Post #226
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-08-19T02:52:58+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from MrMendelli ↑Wed Aug 19, 2020 9:54 am at Wed Aug 19, 2020 9:54 am
>
> 
I don't know if you still watch this thread, but it seems like it was last active recently. Are there plans for PC support? Will the tool eventually be open source?
[https://github.com/Jayveer/Decima-Explorer](https://github.com/Jayveer/Decima-Explorer) this is the only thing at the moment there's no telling when daemon will make this and Death Stranding pc supported
## Post #227
- Username: JavedWilde
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 18, 2020 7:24 pm
- Post datetime: 2020-08-19T07:08:25+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from JavedWilde ↑Tue Aug 18, 2020 8:30 pm at Tue Aug 18, 2020 8:30 pm
>
> 
Im geting this error
im trying to extract files from the pc version

I used DecimaExplorer by Jayveer to extract the core files

but have no clue how to proceed from there
any help

Ok, so I've managed to get rid of the error and has successfully extracted an SMD and ASCII file
no I have no clue wat to do next, how do I open an SMD/ascii file

> Merge all ASCII files into one as text file, then copypaste skeleton into it.
>
> Then count submeshes (it will correspond to number of "material" string)
>
> and put a number of submeshes after the skeleton (before all the actual data).
>
> This number will correspond to number of "material" string in all files.
>
> Same for SMD files, just no need to count submeshes.
its just for combining i think, how to open one tho (EDIT, Im dumb af, I was just one google search away, imma try to use blender source tools and see how that goes)

for people who are trying to extract it from PC,
in the horizon.ini folder, point the locations to <Game Location>\Packed_DX12 and remove everything except initial.bin
Run Horizon and extract the files from there 

for some reason, core files extracted from Decima Explorer did not work by dragging and dropping

Also, instead of oo2core_5_win64.dll, use oo2core_6_win64.dll, just change the name, weirdly, 5 didn't work for me, 6 did
## Post #228
- Username: JavedWilde
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 18, 2020 7:24 pm
- Post datetime: 2020-08-19T10:49:06+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from gokuhs ↑Tue Feb 11, 2020 4:10 pm at Tue Feb 11, 2020 4:10 pm
>
> 
After spending many hours trying to extract the models and thanks to the invaluable help of Raban, I leave you a small mini guide for people like me who are starting on this.

My big problem was the copy of the game, I tried with a PKG of the edition European Complete Edition and as a result it generated empty models. I lost a couple of hours on it, because I thought the problem was mine, but no, it must be that the Daemon tool is not compatible with this version of the game. So i reomend use a copy of the European Standard version (Code: CUSA07319), you can get from the original disk with an a hacked PS4 o try to find an a Fake PKG of the Game (41 GB Aprox)

We will need this software: 

1- Oviusly the daemon1's tool  i use this version
2- The latest version of PKG tool,  you can get it here
3- The latest version of noesis for show and export the models
4- A lot of patience, the process is tedious   

1- The first thing we you need is extract the PKG, for this we use PS4 PKG Tool, is easy, open the folder were are stored the PKG > Right click on the game > Extract PKG Contents.
2- Now get the daemon1 tool and put it inside  "packet_pink" folder.
3- Edit (or create if not exist) the file horizon.ini, and paste inside it the path to the packet_pink folder (including "packet_pink")
4- Open the tool, if we do correctly the tool was generate one big file "res.txt"
5- You can filter the file to be alone with what we want to extract. You can use Excel to filter this.
6- Now i copy paste the PM that Raban sent me, I asked him as an example the model of the red fox.

1. create a .txt-file, name it "list" and place it in the folder where Daemon's horizon.exe is

2. paste these lines into that .txt:
models/characters/animals/redfox/animation/parts/redfox_lx
models/characters/animals/redfox/animation/skeletons/skeleton_rootbone

3. run horizon from windows-command-line like this "horizon /x list.txt"

4. you should now have some .core-files

5. drag and drop redfox_lx.core on horizon.exe; you should get
redfox_lx.core.smd
redfox_lx.core.mesh.ascii
a matrices file
and a bunch of txt which contain the ressource paths for the textures (you can paste those in a new list.txt afterwards)

6. now drag and drop skeleton_rootbone.core on horizon.exe; this should yield:
skeleton_rootbone.core.smd
skeleton_rootbone.core.mesh.ascii

7. open "skeleton_rootbone.core.smd" with the notepad and copy everything that's in there

8. open "redfox_lx.core.smd" with the notepad and paste what you've copied - be careful though you probably have to delete some lines from the target or source file (I think the source already had the header in there);
it should look like this:
version 1
nodes
0 ...
1 ...
... (listing all the bones)
end
skeleton
time 0 (meaning the bind pose of the skeleton)
0 ...
1 ...
... (listing of Rot and Loc of each bone for that pose, meaning their default position)
end
triangles (now begins the description of the geometry that stuff is what's already written in)
assets/bla/blabla
0 ...
0 ...
0 ...
...
end

8.5. make sure you don't have any repeating lines; having the lines "end|skeleton" two times in the file is a big no-no

9. you should be good to go now


Now we can get the model with bones, so we can load it in Noesis. So open noesis, and navigate to the packet_pink folder, and open redfox smd file. And that it, if you do correctly you can see the fox.

Now we can export it to use in Blender for example. To do it, in Noesis select File > Export..., and select as Collada. In blender create a new scene, remove de default cube, and import this exported file on it. 

PD> If you extract the textures, you can use it directly in the latest version of Blender. This is an example of result (Remember, I'm noob in 3D design   )



PD2> Many thanks especially to Raban for the help provided and to Daemon1 for his fantastic tool

The file redfox_lx doesn't create anything when dragged onto horizon.exe, same goes for any file which is a mesh
in case of skeletons, it does create an ascii and smd file

I tried doing the same with aloyna_bags_ct_a_lx.core that I found in this thread. that worked, tho it created a blank smd file

I guess the PC version wont work.
## Post #229
- Username: MrMendelli
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 19, 2020 8:15 am
- Post datetime: 2020-08-20T05:21:46+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from qs12 ↑Wed Aug 19, 2020 10:52 am at Wed Aug 19, 2020 10:52 am
>
> 
MrMendelli wrote: ↑Wed Aug 19, 2020 9:54 am
I don't know if you still watch this thread, but it seems like it was last active recently. Are there plans for PC support? Will the tool eventually be open source?

https://github.com/Jayveer/Decima-Explorer this is the only thing at the moment there's no telling when daemon will make this and Death Stranding pc supported

Thanks for the quick reply. This looks promising.
## Post #230
- Username: zero
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 09, 2015 3:04 am
- Post datetime: 2020-08-20T06:40:02+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from qs12 ↑Wed Aug 19, 2020 10:52 am at Wed Aug 19, 2020 10:52 am
>
> 
MrMendelli wrote: ↑Wed Aug 19, 2020 9:54 am
I don't know if you still watch this thread, but it seems like it was last active recently. Are there plans for PC support? Will the tool eventually be open source?

https://github.com/Jayveer/Decima-Explorer this is the only thing at the moment there's no telling when daemon will make this and Death Stranding pc supported

Thanks everyone that has been working on this kind of tools.

I can confirm that this tool works in the pc version.

Now the daemon horizon tool we can get the animations or the skeleton no problem from the pc version.

However the models we can't it does nothing lol.

I hope daemon adds support to his wonderful tool.

I can help with whatever I can files, the pc full game on steam you name it. Just pm and I will do what I can.

Thanks everyone and keep up that awesome work.
## Post #231
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-08-20T12:54:07+00:00
- Post Title: Re: Horizon Zero Dawn

i will get back to this as soon as i have time
## Post #232
- Username: mcmanus82
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Dec 12, 2017 9:45 pm
- Post datetime: 2020-08-27T13:43:22+00:00
- Post Title: Re: Horizon Zero Dawn

Hi

I'm currently looking for the face paint / makeup for Aloy and other characters, so i thought i would give this a try.
I followed the instructions in the "Guide" post, here is what I'm  using:
PS4 HZD (Code: CUSA07319)
Tried all 3 versions of the tool
I'm mainly interested in textures so that's what i checked,
These worked / extracted fine:
Redfox textures from the guide post (models/characters/animals/redfox/texture/redfox_set)
Aloy base head textures. (models/characters/humans/heads/female/hannah/textures/hannah_head_set / head_a_set / head_b_set)
A random bow textures were fine too.

I honestly do not know if I'm doing something wrong or the tool simple cannot handle these types of texture sets(see below), any help would be welcome.
Here is a list of what didn't work:

Blank(black) textures.
models/characters/humans/eclipsedigger/textures/diggermaskchampion/diggermaskchampion_set
models/characters/humans/banukshaman/textures/sharedparts/replacementparts/replacementparts_set
models/characters/humans/heads/female/karib/textures/karibel_head_set
models/characters/humans/heads/female/karib/textures/karibel_head_a_set
models/characters/humans/heads/female/karib/textures/karibel_head_b_set
models/characters/humans/baseparts/decals/facepaint_nora_rost/facepaint_nora_rost_set
0 byte everything (ascii,mat,smd)after core extraction.
models/characters/humans/eclipsedigger/animation/parts/diggermaskchampion_ct_a_lx
Corrupted or blank(black) textures.
models/characters/humans/heads/female/ambert/textures/amber_head_set
No error or log line but no files produced.
models/characters/humans/heads/female/ambert/textures/amber_head_a_set
models/characters/humans/heads/female/ambert/textures/amber_head_b_set
models/characters/humans/baseparts/decals/facepaint_eclipseb/facepaint_eclipseb_set
models/characters/humans/tenakthhunter/textures/tenakthmale body/tenakthmaletiling_set
Blank core file(only containing zeros)
models/characters/humans/baseparts/decals/vanashahood/vanashahood_set
models/characters/humans/baseparts/decals/facepaint_tenaktha/facepaint_tenaktha_set
models/characters/humans/baseparts/decals/facepaint_noraoutcasta/facepaint_noraoutcasta_set
models/characters/humans/baseparts/decals/facepaint_aloynorab/facepaint_aloynorab_set
models/characters/humans/vanasha/textures/body/vanashabody_set
models/characters/humans/vanasha/textures/body/vanashabodycards_set
Unhandled Exception: System.AccessViolationException: Attempted to read or write protected memory.
models/characters/humans/vanasha/animation/parts/vanashabody_ct_a_lx
models/characters/humans/vanasha/animation/parts/vanashaveil_ct_a_lx
## Post #233
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-08-27T14:13:07+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from mcmanus82 ↑Thu Aug 27, 2020 9:43 pm at Thu Aug 27, 2020 9:43 pm
>
> 
I followed the instructions in the "Guide" post, here is what I'm  using:
PS4 HZD (Code: CUSA07319)
Your problem is incorrectly extracted PS4 HZD package.
## Post #234
- Username: mcmanus82
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Dec 12, 2017 9:45 pm
- Post datetime: 2020-08-27T14:21:46+00:00
- Post Title: Re: Horizon Zero Dawn

I used PS4 PKG Tool 6.4 right click and extract content. It finished successfully. So what program / version should i use? (The latest one on github does not have an extract context menu option)
## Post #235
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-08-27T23:02:38+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from mcmanus82 ↑Thu Aug 27, 2020 10:21 pm at Thu Aug 27, 2020 10:21 pm
>
> ...So what program / version should I use? (The latest one on github does not have an extract context menu option)
Avoid at all costs the GitHub what ever PKG extractor you found they always give errors and users have problems, for old FakePKGs that where available for firmware exploited up to 5.05 use (new FakePKGs built for exploited firmware on 6.72 it wont work, use instead Fake_PKG_Generator v3.38+):
[https://sites.google.com/site/theleeche ... 4pkgviewer](https://sites.google.com/site/theleecherman/ps4pkgviewer)
BUT, if you really want to be sure nothing is corrupted look on Google for the official Sony (yet patched by hackers) Fake_PKG_Generator v3.38+

have fun
## Post #236
- Username: zero
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 09, 2015 3:04 am
- Post datetime: 2020-09-02T08:44:40+00:00
- Post Title: Re: Horizon Zero Dawn

Thanks again to everyone that keeps working on this awesome tools.


ekey
Daemond1
codeman
mariokart64
chorrox
zaramot


and so may other great coders that keep bringing tools to this great community THANKS

i am trying to get some models from Horizon Zero Dawn but the current tool is only for ps4

Now I would go and buy the console and the games but I already spent some money in Epic store, Origins, Steam and some other Big Stores
so buying the game is not the problem but wasting money in the console it really is.

I stopped buying consoles after ps3 because after a few years something else comes along and we have to buy everything again which may be doable
but the current epidemic we are going thru and the economy is not good.

Plus my life right now it is in the pc because of the mods.

I am working in a special mod but I can't get it moving due to the lack of 3d models.

Someone could pm to debate about this I can help back. 





Thanks in advance and keep up that awesome work
## Post #237
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2020-09-03T20:24:02+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from JavedWilde ↑Wed Aug 19, 2020 3:08 pm at Wed Aug 19, 2020 3:08 pm
>
> 
JavedWilde wrote: ↑Tue Aug 18, 2020 8:30 pm
Im geting this error
im trying to extract files from the pc version

I used DecimaExplorer by Jayveer to extract the core files

but have no clue how to proceed from there
any help



Ok, so I've managed to get rid of the error and has successfully extracted an SMD and ASCII file
no I have no clue wat to do next, how do I open an SMD/ascii file
Merge all ASCII files into one as text file, then copypaste skeleton into it.
Then count submeshes (it will correspond to number of "material" string)
and put a number of submeshes after the skeleton (before all the actual data).
This number will correspond to number of "material" string in all files.
Same for SMD files, just no need to count submeshes.
its just for combining i think, how to open one tho (EDIT, Im dumb af, I was just one google search away, imma try to use blender source tools and see how that goes)

for people who are trying to extract it from PC,
in the horizon.ini folder, point the locations to <Game Location>\Packed_DX12 and remove everything except initial.bin
Run Horizon and extract the files from there 

for some reason, core files extracted from Decima Explorer did not work by dragging and dropping

Also, instead of oo2core_5_win64.dll, use oo2core_6_win64.dll, just change the name, weirdly, 5 didn't work for me, 6 did

How did you extract the core file? I can get the core file well, but im lost from there lol
## Post #238
- Username: blonzarg
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 13, 2020 4:44 am
- Post datetime: 2020-09-10T18:41:10+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from JavedWilde ↑Tue Aug 18, 2020 8:30 pm at Tue Aug 18, 2020 8:30 pm
>
> 

Ok, so I've managed to get rid of the error and has successfully extracted an SMD and ASCII file

I'm getting the same error, could you explain how you fixed it?
Or has anyone managed to extract meshes from the PC version?
Cheers
## Post #239
- Username: LuckyCat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 15, 2020 8:58 am
- Post datetime: 2020-09-15T02:06:41+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from blonzarg ↑Fri Sep 11, 2020 2:41 am at Fri Sep 11, 2020 2:41 am
>
> 
JavedWilde wrote: ↑Tue Aug 18, 2020 8:30 pm

Ok, so I've managed to get rid of the error and has successfully extracted an SMD and ASCII file


I'm getting the same error, could you explain how you fixed it?
Or has anyone managed to extract meshes from the PC version?
Cheers

I've tried everything, including removing all other language files like the author said. No luck.
If it's a tool made using .Net, then someone can easily decompile and adjust it.
## Post #240
- Username: AtomicJunkie
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 08, 2020 8:26 pm
- Post datetime: 2020-09-16T11:29:41+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from zero ↑Thu Aug 20, 2020 2:40 pm at Thu Aug 20, 2020 2:40 pm
>
> 
qs12 wrote: ↑Wed Aug 19, 2020 10:52 am
MrMendelli wrote: ↑Wed Aug 19, 2020 9:54 am
I don't know if you still watch this thread, but it seems like it was last active recently. Are there plans for PC support? Will the tool eventually be open source?

https://github.com/Jayveer/Decima-Explorer this is the only thing at the moment there's no telling when daemon will make this and Death Stranding pc supported


Thanks everyone that has been working on this kind of tools.

I can confirm that this tool works in the pc version.

Now the daemon horizon tool we can get the animations or the skeleton no problem from the pc version.

However the models we can't it does nothing lol.

I hope daemon adds support to his wonderful tool.

I can help with whatever I can files, the pc full game on steam you name it. Just pm and I will do what I can.

Thanks everyone and keep up that awesome work.

I've checked some *.core files in the folder sounds. There are subfolders called wav. Core files in these subfolders seems to be MP3 Audio format. (Try open these files your preferred Wave editor)
If you simple rename it, you should get all the sound files.
## Post #241
- Username: AtomicJunkie
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 08, 2020 8:26 pm
- Post datetime: 2020-09-16T13:04:05+00:00
- Post Title: Re: Horizon Zero Dawn

This blender script snaps all the floating parts to their corresponding helper bones.
Additionally it adds a arrmature constraint to these parts so that they move with the armature.

```

# get the first armature in scene (blender valve importer names armatures after first imported filename)
for obj in bpy.context.scene.objects:
    if obj.type == 'ARMATURE':
        arma = obj
        break

# iterate through all bones from that armature
for b in arma.pose.bones:
    
    # get helper bones
    if b.name.endswith("_helper"):
    
        # remove unneccessary filename parts
        b.name = b.name.replace("_Lx","")
        
        # new variable to better compare bones with meshes
        bonename = b.name.replace("_helper","")
        
        # iterate through all the scenes objects
        for obj in bpy.context.scene.objects:
            
            # continue if object is a mesh
            if obj.type == 'MESH':
        
                # compare if mesh name matches bone name (bone: head_helper; mesh: head)
                if obj.name.casefold().startswith(bonename.casefold()):
                
                    # apply the ccordinates of the bone tail to the mesh
                    obj.location = b.head
                    
                    # clear existing constraints
                    obj.constraints.clear()
                    
                    # add a new armature constraint with bone target (used for animation)
                    con = obj.constraints.new('ARMATURE')
                    btg = con.targets.new()
                    btg.target = arma
                    btg.subtarget = b.name

# reset location of armature to 0 (needed for some characters)                
arma.location = (0,0,0)

```


Some example: [https://youtu.be/d38kQcLxEBo](https://youtu.be/d38kQcLxEBo)
## Post #242
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-09-16T15:04:26+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from AtomicJunkie ↑Wed Sep 16, 2020 9:04 pm at Wed Sep 16, 2020 9:04 pm
>
> 
This blender script snaps all the floating parts to their corresponding helper bones.
Additionally it adds a arrmature constraint to these parts so that they move with the armature.

I dont know why this script is needed, my tool already puts all parts to their corresponding helper bones and connects helper bones to main armature.

Only if you dont use the tool as intended and only extract individual parts.
## Post #243
- Username: AtomicJunkie
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 08, 2020 8:26 pm
- Post datetime: 2020-09-16T16:19:23+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Wed Sep 16, 2020 11:04 pm at Wed Sep 16, 2020 11:04 pm
>
> 
I dont know why this script is needed, my tool already puts all parts to their corresponding helper bones and connects helper bones to main armature.

Only if you dont use the tool as intended and only extract individual parts.

I use your tool without the bat file generation you mentioned in one of your first posts.
Because that didn't work for me. Is this still implemented? Maybe I'm using it wrong.

Anyway after copying the skeleton in the smd file via script, I can import them into blender and even use the animations.
## Post #244
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-09-16T16:34:50+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from AtomicJunkie ↑Thu Sep 17, 2020 12:19 am at Thu Sep 17, 2020 12:19 am
>
> 
I use your tool without the bat file generation you mentioned in one of your first posts.
Because that didn't work for me. Is this still implemented? Maybe I'm using it wrong.
Yes, that bat file is supposed to do that. And yes, it must still work, because game formats were never changed since the beginning.
## Post #245
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-09-29T15:41:47+00:00
- Post Title: Re: Horizon Zero Dawn

I'm working on tool version for PC. Not much changes, testing it now, must not take long.
## Post #246
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-09-30T06:11:00+00:00
- Post Title: Re: Horizon Zero Dawn

Ok here's PC tool.

Usage is same as PS4. Someone said it doesnt work with oodle5, so i made it with oodle7, even though i think you can use other verisons renaming the .DLL as usual.

I checked a few models, textures and animations, they all look exactly same as on PS4. No quality difference.
So I dont know why files are 10GB bigger.

If anything will not work, let me know.
[Horizon_pc.7z](https://xentaxbackup.github.io/file/18785_Horizon_pc.7z)
## Post #247
- Username: AtomicJunkie
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 08, 2020 8:26 pm
- Post datetime: 2020-09-30T07:23:50+00:00
- Post Title: Re: Horizon Zero Dawn

Damn, you're quick.   Thanks again for sharing.

Tested the new PC tool on the Watcher. It works like a charm.

Some small issue: The Batch file genrator still creates the batch file with horizon instead of your new file name horizon_pc.

I also thought there are some high res textures in the PC version. But HZD was already optimized for 4K on the PS4 pro.
## Post #248
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-09-30T07:57:39+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from AtomicJunkie ↑Wed Sep 30, 2020 3:23 pm at Wed Sep 30, 2020 3:23 pm
>
> 
Some small issue: The Batch file genrator still creates the batch file with horizon instead of your new file name horizon_pc.
ok. will fix it later.

> Reply from AtomicJunkie ↑Wed Sep 30, 2020 3:23 pm at Wed Sep 30, 2020 3:23 pm
>
> 
I also thought there are some high res textures in the PC version.
Possible. Maybe main characters are already highest res on both platforms, but smaller, less important objects can be better on PC. Everyone is free to check it out.

Also I noticed vertex normals are not 10-bit packed, but full 16-bit or even 32-bit on PC. Not a big difference either.
## Post #249
- Username: zero
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 09, 2015 3:04 am
- Post datetime: 2020-09-30T22:14:22+00:00
- Post Title: Re: Horizon Zero Dawn

You are freaking awesome mate. Thank you very much.

You should check your pm box once in a while I know you must have like a million pms but still.

Thanks again

"Edit"

Am I the only one that is getting empty cores or blue or black dds?

It took me a while but I figure out the way to use it now I am getting empty files

Is there some step that I am missing or is something else that I need to do?

Can some one share a .bat file from pc extraction if they have it working please
## Post #250
- Username: funjord
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 10, 2020 1:41 am
- Post datetime: 2020-10-10T02:17:50+00:00
- Post Title: Re: Horizon Zero Dawn

It crashes every time I try and use it with the pc version
## Post #251
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2020-10-14T18:32:27+00:00
- Post Title: Re: Horizon Zero Dawn

Aloy Shield-Weaver.jpg (238.08 KiB) Viewed 1798 times

Big Thanx Daemon1 for the tool   
with your help we can extract models from this game.
## Post #252
- Username: AtomicJunkie
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 08, 2020 8:26 pm
- Post datetime: 2020-10-14T20:26:20+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Crazy31139 ↑Thu Oct 15, 2020 2:32 am at Thu Oct 15, 2020 2:32 am
>
> 
Aloy Shield-Weaver.jpgBig Thanx Daemon1 for the tool   
with your help we can extract models from this game.

Hey, is this a stock photo?
If not how did you get the texture for the hair right?
## Post #253
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2020-10-15T16:43:01+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from AtomicJunkie ↑Thu Oct 15, 2020 4:26 am at Thu Oct 15, 2020 4:26 am
>
> 
Crazy31139 wrote: ↑Thu Oct 15, 2020 2:32 am
Aloy Shield-Weaver.jpgBig Thanx Daemon1 for the tool   
with your help we can extract models from this game.


Hey, is this a stock photo?
If not how did you get the texture for the hair right?
No, I rendered in Marmoset toolbag 3
I recolored hair texture myself
## Post #254
- Username: misterhister
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 06, 2020 5:52 am
- Post datetime: 2020-11-05T22:34:34+00:00
- Post Title: Re: Horizon Zero Dawn

i read all the things and i tried pasting the horizon_pc.exe file in the games folder right where oo2core_3_win64.dll is . I executed the file and nothing happened . i tried doing the same while the game is open too . would you please help me ? i am a noob in these stuff .
## Post #255
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-11-05T23:04:23+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from misterhister ↑Fri Nov 06, 2020 6:34 am at Fri Nov 06, 2020 6:34 am
>
> 
i read all the things and i tried pasting the horizon_pc.exe file in the games folder right where oo2core_3_win64.dll is . I executed the file and nothing happened . i tried doing the same while the game is open too . would you please help me ? i am a noob in these stuff .
That means you did step 2 from description on first page about extraction, now continue doing rest of steps and you'll get there, just read carefully and follow through.
## Post #256
- Username: funjord
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 10, 2020 1:41 am
- Post datetime: 2020-11-10T01:30:56+00:00
- Post Title: Re: Horizon Zero Dawn

I get file could not be previewed after running the a.BAT on Noesis
## Post #257
- Username: Spartan019
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Sep 21, 2014 9:46 am
- Post datetime: 2020-12-08T08:02:39+00:00
- Post Title: Re: Horizon Zero Dawn

I should preface this my stating for the record that I am, in fact, an idiot.
But!
On the PC version...

So I've got the oo2core_5_win64.dll and the horizon_pc.exe in the localacheDX12 folder - when I run the latter all I've getting is a repeated message of "Unexpected packed size!" and "Unexpected packed size"

Am I doing this wrong?
As another in this thread did - I pinched the oo2core_8 file from warframe and renamed it. Unsure if that's the issue.

Halp?
## Post #258
- Username: AtomicJunkie
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 08, 2020 8:26 pm
- Post datetime: 2020-12-08T11:07:48+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Spartan019 ↑Tue Dec 08, 2020 4:02 pm at Tue Dec 08, 2020 4:02 pm
>
> 
I should preface this my stating for the record that I am, in fact, an idiot.
But!
On the PC version...

So I've got the oo2core_5_win64.dll and the horizon_pc.exe in the localacheDX12 folder - when I run the latter all I've getting is a repeated message of "Unexpected packed size!" and "Unexpected packed size"

Am I doing this wrong?
As another in this thread did - I pinched the oo2core_8 file from warframe and renamed it. Unsure if that's the issue.

Halp?

You must not use the tool in the game folder directly. Copy only the files Initial.bin, DLC1.bin and Remainder.bin into another folder and try the horizon_pc there. You can use the horizon.ini to specify the location of your copied files.
See first post in this thread. Workflow is similiar to PS4 version. You can use the oo2core file from the game itself and rename it. This worked for me very well.
## Post #259
- Username: Spartan019
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Sep 21, 2014 9:46 am
- Post datetime: 2020-12-08T22:36:47+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from AtomicJunkie ↑Tue Dec 08, 2020 7:07 pm at Tue Dec 08, 2020 7:07 pm
>
> 

You must not use the tool in the game folder directly. Copy only the files Initial.bin, DLC1.bin and Remainder.bin into another folder and try the horizon_pc there. You can use the horizon.ini to specify the location of your copied files.
See first post in this thread. Workflow is similiar to PS4 version. You can use the oo2core file from the game itself and rename it. This worked for me very well.

That's got it! Danke!
I renamed the hzd oo2core_3 as 7 this time and the tool happily spat out a res.text file.
## Post #260
- Username: mrj
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 19, 2020 3:15 pm
- Post datetime: 2020-12-19T08:21:43+00:00
- Post Title: Re: Horizon Zero Dawn

Hi ! I am new to this stuff, I have been trying to extract audio files from HZD. I have core files but I don't know how to convert them to typical audio formats. Is it possible? Thanks.

Edit: Wow, I just had to rename core to wav. thanks for the extraction tools anyways !
## Post #261
- Username: Lukas0122
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 22, 2020 12:06 am
- Post datetime: 2020-12-24T00:51:08+00:00
- Post Title: Re: Horizon Zero Dawn

1.question why when i convert .core files to dds, dds are broken(like for horse i have only usable 3 diffuse textures) and other are some broken textures. Is there way to repair it?
2.questions I tried to get horse armature,but i am confused how to write to cmd this "horizon [mesh_skeleton] [animskel] > a.bat" for horse(also horse dont have in blender any vertex group).PC version
## Post #262
- Username: sgiath
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 15, 2012 12:25 am
- Post datetime: 2020-12-27T13:33:27+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from mrj ↑Sat Dec 19, 2020 4:21 pm at Sat Dec 19, 2020 4:21 pm
>
> 
Hi ! I am new to this stuff, I have been trying to extract audio files from HZD. I have core files but I don't know how to convert them to typical audio formats. Is it possible? Thanks.

Edit: Wow, I just had to rename core to wav. thanks for the extraction tools anyways !

Do you have the resourcenames of the music? I'm not able to get it, just the loading music. The rest of files that I'm extracting is 1Kb or 4Kb... it's frustating...
## Post #263
- Username: roslairy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 04, 2021 5:26 pm
- Post datetime: 2021-01-08T07:14:14+00:00
- Post Title: Re: Horizon Zero Dawn

Got head mesh with weighted skeleton on PC version, thanks
## Post #264
- Username: markfisher
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 08, 2021 3:07 am
- Post datetime: 2021-01-09T23:32:54+00:00
- Post Title: Re: Horizon Zero Dawn

So far most of this has been working for me, with a single exception. I am not able to extract any of the robot helper bones. When I run robot.helpers.core  through Horizon_pc nothing happens. It is the same for skeleton_rootbone_helpers.core, and this has happened on every machine that I have tried so far. I have been otherwise able to extract the body, components and the mesh_skeleton_rootbone.core (main skeleton). 

Possibly related, when I run the command "Horizon_pc.exe [mesh_skeleton] [animskel] >A.bat" it is unable to find the file [mesh_skeleton].

Does anyone here have any suggestions? I would be incredibly excited to get these working. Where it stands, I could manually place each component, but that wouldn't be ideal.
## Post #265
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-01-10T07:09:15+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from markfisher ↑Sun Jan 10, 2021 7:32 am at Sun Jan 10, 2021 7:32 am
>
> 
When I run robot.helpers.core  through Horizon_pc nothing happens
I never said you have to do that. This file is needed, but you dont have to run it through Horizon_pc.

executing "Horizon_pc.exe [mesh_skeleton] [animskel] >A.bat" means you have to put real file names as parameters.
## Post #266
- Username: markfisher
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 08, 2021 3:07 am
- Post datetime: 2021-01-10T20:07:18+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Sun Jan 10, 2021 3:09 pm at Sun Jan 10, 2021 3:09 pm
>
> 
executing "Horizon_pc.exe [mesh_skeleton] [animskel] >A.bat" means you have to put real file names as parameters.

Thank you, I am brand new to this so I am not used to the syntax yet. Since I have seen this question before, I'll add what I did here. 
In this specific case, I am trying to extract the charger (goat) and execute:
"Horizon_pc.exe mesh_skeleton_rootbone.core horsetemplate.core_0.animskel > a.bat"
That generated the correct bat file that I could then edit per the instructions. 

Now the only issue I have left is trying to get the destructible parts properly applied to the mesh, and this is probably a syntax issue as well. I am using the smd files so that they can be directly imported into blender. I copied and pasted the skeleton into the main body file (and that works great) but when I paste the parts at the end of the file they are placed at the origin instead of the associated helper bones. There is a blender script posted earlier that does this, but they don't always move correctly when placed that way. Is there a specific syntax to follow, or am I missing something else here?
## Post #267
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-01-10T20:11:38+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from markfisher ↑Mon Jan 11, 2021 4:07 am at Mon Jan 11, 2021 4:07 am
>
> 
Now the only issue I have left is trying to get the destructible parts properly applied to the mesh
i'm not sure which step did you miss, because you didnt say exactly what you did, but most probably you didnt have robot_modelhelpers in the same folder, so it was not used during conversion.
## Post #268
- Username: markfisher
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 08, 2021 3:07 am
- Post datetime: 2021-01-10T21:38:27+00:00
- Post Title: Re: Horizon Zero Dawn

Here is what I did, step by step.

ran Horizon_pc.exe to extract res file. 
Using that list, created a text file to extract everything for the charger (goat) and named it Charger.txt

models/characters/robots/goat/animation/parts/body
models/characters/robots/goat/animation/parts/eye_lx
models/characters/robots/goat/animation/parts/goat_lefthorn_lx
models/characters/robots/goat/animation/parts/goat_lefthorndes_lx
models/characters/robots/goat/animation/parts/goat_righthorn_lx
models/characters/robots/goat/animation/parts/goat_righthorndes_lx
models/characters/robots/goat/animation/parts/platebody01_lx
models/characters/robots/goat/animation/parts/platehead01_lx
models/characters/robots/goat/animation/parts/platehead02_lx
models/characters/robots/goat/animation/parts/platehead03_lx
models/characters/robots/goat/animation/parts/plateleg01_lx
models/characters/robots/goat/animation/parts/plateleg02_lx
models/characters/robots/goat/animation/parts/plateleg03_lx
models/characters/robots/goat/animation/parts/plateleg04_lx
models/characters/robots/goat/animation/parts/plateleg05_lx
models/characters/robots/goat/animation/parts/plateleg06_lx
models/characters/robots/goat/animation/parts/plateleg07_lx
models/characters/robots/goat/animation/parts/plateleg08_lx
models/characters/robots/goat/animation/parts/plateleg09_lx
models/characters/robots/goat/animation/parts/plateleg10_lx
models/characters/robots/goat/animation/parts/plateleg11_lx
models/characters/robots/goat/animation/parts/plateleg12_lx
models/characters/robots/goat/animation/parts/plateneck01_lx
models/characters/robots/goat/animation/parts/plateneck02_lx
models/characters/robots/goat/animation/parts/plateneck03_lx
models/characters/robots/goat/animation/parts/plateneck04_lx
models/characters/robots/goat/animation/parts/plateneck05_lx
models/characters/robots/goat/animation/parts/plateneck06_lx
models/characters/robots/canisters/model/parts/horse_goat_canister_fuel
models/characters/robots/goat/animation/skeletons/mesh_skeleton_rootbone
models/characters/robots/goat/animation/skeletons/skeleton_rootbone_helpers
entities/characters/robots/templates/archetypes/horsetemplate
models/characters/robots/goat/animation/robot_modelhelpers --I was missing this before. 

executed Horizon_pc.exe /e Charger.txt to extract the core files, one by one. (can they all be extracted at once?) 
Dragged each part file into horizon_pc, one by one. (can they all be extracted at once?) 
Run Horizon_pc on template file

Execute "Horizon_pc.exe mesh_skeleton_rootbone.core horsetemplate.core_0.animskel > a.bat"
Change the "_helper" strings to ".core" strings in a.bat
Run a.bat (I am not sure if this is running successfully, what should I see as an output?)

When combining parts, should I be putting the destructible and main body together into one smd file? Pasting the skeleton into the body file has been working.

I noticed I am missing the blaze canister, will this (and other similar parts) also automatically be added if I extract them along side everything else? ---Edit--- Added the blaze canister to the list.
## Post #269
- Username: Neil187
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 28, 2019 10:43 am
- Post datetime: 2021-01-21T21:29:38+00:00
- Post Title: Re: Horizon Zero Dawn

Hey everyone,

I'm sorry if I am missing something blatantly obvious, but here is my issue:

I could not get .core files using this tool, so I used DecimaExplorer to extract everything at once. Now that I have the core files, I need to extract from those using horizon_pc. When I drag/drop a core file onto the exe, nothing happens at all. I do not even get an error message. I used the .dll from Horizon to extract everything and the file is also in the same folder as the exe. Can anyone think of where I'm going wrong?

Thank you, by the way, for putting work into this tool.
## Post #270
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-01-22T06:18:31+00:00
- Post Title: Re: Horizon Zero Dawn

Sounds like its the way you unpacked the game.. unpack your packed pink folder then run batch file on the archive using horizion.exe 

put horizon.exe into your folder along with oodle
run horizon.exe
this will make a list.txt file
now run
horizon /x list.txt
*edit list.txt for resource you want or extract all*
I run a batch file on them..
my .bat
for %%i in (*.core) do /r C:\Users\******\Horizon\Image0\packed_pink\horizon.exe "%%i"
or cmd 
horizon.exe /x list.txt
all there is to it  

works the same way with death stranding
## Post #271
- Username: LingeringHum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jan 22, 2021 8:41 am
- Post datetime: 2021-01-23T22:27:38+00:00
- Post Title: Re: Horizon Zero Dawn

Hello All,

I'm new here and yup as you may have guessed I a, running into a few issues and was wondering If someone could point me in the right Direction.
I have read all the pages in this thread numerous times, and think I have a grasp on the processes, but I am getting a mixed up or something isn't quite working.

For Reference I am interested in getting my hands on all of the robot models with Textures.  Looking at the animations could be fun, but I am mostly focussed on looking at the meshes and all of the textures.
I have a copy of the Complete Edition on Steam (PC) installed and have been trying to work from that.

So far I have copied (DLC1.bin, Initial.bin, Remainder.bin) to a folder on my desktop.  I have then tried using Daemons Tool and Decima Explorer (I use the GUI version) to generate interrogate the folder, make a res list and generate the .core files - Both methods seems to work and I get a folder with subfolders and .core files in each - happy days!

Next as I understand it, I need to extract the data from these .core files and I have been trying to use Daemons Horizon_pc.exe which I found on pg 17 of this thread.  Again I am new to this, so please correct me if I am wrong anywhere, but I beleive in order to use Daemons tool, I need to place a copy of his .exe and copy of oo2core_5_win64.dll in the same folder as the .core file? I didn't have a copy of the oo2core file, so I googled it and picked up a file from dll_files.com ( I noticed everyone says there is a copy of this file in most new games, I saw horizon had oo2core3 so didn't think that would work? - Anyway, I copied the files and then started dragging each of the .core files to the Horizon_pc.exe file.  After a second or two, files appeared, such as .smd and .ascii and the odd .txt files - The thing is, all of the generated files state hey are all 0KB. 

Using the example from JavidWilde on pg16, I decided to try the process on the redfox model, just to see If i can get the process to work before looking at the robots.  The file I am trying is :
models\characters\animals\redfox\animation\parts\redfox_lx.core - I can see the .core file is 490KB on my file.
After dragging this file to the Horizon_pc.exe, I get the following files: 
redfox_lx.core_0.ascii (0KB)
redfox_lx.core_0.smd (0KB)
redfox_lx.core_materials.txt (0KB)

I do notice however that when the black (cmd?) window appears, I see the message:
Redfox_La
File not found in cache! models/characters/animals/redfox/animation/parts/redfox_lx.core stream

I find this happen on any of the .core files I have tried with exception to the models/characters/animals/redfox/texture/redfox_set.core When I drag this file onto the Horizon_pc.exe file I get a new subfolder created called (Textures) and 3 files in that (redfox_set00_type_3_dx10.dds (340KB) redfox_set01_type_1.dds (340KB) redfox_set02_type_13.dds(40.1KB) - All of these files are just black in previews? - Not really sure If they are broke or If I have to do anything else to them?
Also the other file that seems to work is models/characters/animals/redfox/animation/skeletons/skeleton_rootbone.core  The files I get from this are: skeleton_rootbone.core.ascii (3KB) & skeleton_rootbone.core.smd(4KB)

Am I missing something obvious? do I have all the required files in the folder to use the tool correctly? or am I just messing the whole sequence up?  Could it be the .dll file I downloaded?

Any help would be much appreciated

As I say I am just looking for the robot meshes and textures.  As a 3D Artist and Animator myself, I always like to look at the things, reverse engineer some of the modelling decisions and compare my own work to others to improve.

I know it is cheeky to ask if anyone could just give me the models and textures so I am trying my best to figure this out and do the work myself.  However If I cannot get this to work, would anyone be willing to share files?

Many Thanks and hope to hear from someone soon

Ryan
## Post #272
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2021-01-24T04:45:35+00:00
- Post Title: Re: Horizon Zero Dawn

oo2core_5_win64.dll needs to be in the same location as horizon_pc.exe; do the textures load in an image editor like Gimp or Photoshop?
## Post #273
- Username: LingeringHum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jan 22, 2021 8:41 am
- Post datetime: 2021-01-24T14:38:52+00:00
- Post Title: Re: Horizon Zero Dawn

Hey thanks for the reply,
Yeah I can confirm that I had a copy of that file in the same dir/folder as the .exe and .core file when  I dragged it on to the .exe file.   It's strange as it looks like it's trying to do something and makes the files, but they are all blank.  I haven't tried to open the texture files, apart from just in photo viewer - they just showed black.  I'll boot up photoshop and see if I get anything. I also just tried renaming them to .png .jpg and .tif to see if that worked but nope.

Any more ideas would be very welcome

Cheers
Ryan
## Post #274
- Username: itscommonera
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 25, 2021 1:23 am
- Post datetime: 2021-01-24T17:30:12+00:00
- Post Title: Re: Horizon Zero Dawn

Hi, please tell me is there any reason this is being read as a Trojan?
## Post #275
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2021-01-24T20:55:07+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from LingeringHum ↑Sun Jan 24, 2021 10:38 pm at Sun Jan 24, 2021 10:38 pm
>
> 
Hey thanks for the reply,
Yeah I can confirm that I had a copy of that file in the same dir/folder as the .exe and .core file when  I dragged it on to the .exe file.   It's strange as it looks like it's trying to do something and makes the files, but they are all blank.  I haven't tried to open the texture files, apart from just in photo viewer - they just showed black.  I'll boot up photoshop and see if I get anything. I also just tried renaming them to .png .jpg and .tif to see if that worked but nope.

Any more ideas would be very welcome

Cheers
Ryan

There may be a problem with the .core files then, either they're corrupted or missing data.
## Post #276
- Username: LingeringHum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jan 22, 2021 8:41 am
- Post datetime: 2021-01-24T23:00:18+00:00
- Post Title: Re: Horizon Zero Dawn

Hey All,
So I think I figured Out what I was doing wrong!

I went back to try and export the red fox model again and this time after I created the .core files, I took all of the core files out of the subfolders and put them directly in a main root folder along with the DLC1.bin, Initial.bin, Remainder.bin.  
I made sure I had a copy of Daemons Horizon_pc.exe and a copy of oo2core_7_win64.dll ( I just renamed the _5_ copy I downloaded before)
I then dragged and dropped each .core file in succession onto the Horizon_pc.exe file and this time when it spat out files, they were no longer 0KB each.
I booted up a copy of Noesis which someone suggested was a model viwer etc and low and behold I had the fox model.
Using the advise from before in the thread, I did the text editing for the skeleton_rootbone.core.smd and redfox_lx.core_0.smd and bam, I could see in Noesis new option because the rig was now present.  
I exported the model - with Rig to .fbx and then imported into Max 2017 (need to get a newer copy heh) and yup theres the mesh, rigged amd ready to rock!
I applied the textures - Needed a bit of playing as the main texture was backward (Just did a quick mesh flip horizontally in UV Unwrap and its looks fine.
Added the texture to the fur mesh and applied the alpha channel.
Setup for a quick render - Not great results as the texture looks washed out. Removed the fur mesh and texture and the base mesh again looks washed out ( the eyes are not dark, but almost grey - weird!  Looks fine in the viewport with crisp dark material - may do some investigation on that, but more interested in having a go with the Robots now.

{EDIT] - worked out the washed texture issue - Just me being daft - Forgot to put the Ambient Color to Black - It was on Grey hence the washed out Look!

I know someone mentioned that the robots are more difficult, do to the destructive mesh elements which have to be attached.  I'll have to go back and read the whole thread again to see If I can work it out after doing the whole skeleton.smd edits.

I quickly got the base mesh for the Long Legs into Max (yay) and then tried to add one of the panels - The panel just came in at the root 0,0,0 so I am doing something wrong

Thanks everyone for the help so far, I'm sure I'll be asking more question in due course!

Cheers

Ryan
## Post #277
- Username: sihuhu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 09, 2020 9:52 am
- Post datetime: 2021-02-03T11:42:08+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from LingeringHum ↑Mon Jan 25, 2021 7:00 am at Mon Jan 25, 2021 7:00 am
>
> 
Hey All,
So I think I figured Out what I was doing wrong!

I went back to try and export the red fox model again and this time after I created the .core files, I took all of the core files out of the subfolders and put them directly in a main root folder along with the DLC1.bin, Initial.bin, Remainder.bin.  
I made sure I had a copy of Daemons Horizon_pc.exe and a copy of oo2core_7_win64.dll ( I just renamed the _5_ copy I downloaded before)
I then dragged and dropped each .core file in succession onto the Horizon_pc.exe file and this time when it spat out files, they were no longer 0KB each.
I booted up a copy of Noesis which someone suggested was a model viwer etc and low and behold I had the fox model.
Using the advise from before in the thread, I did the text editing for the skeleton_rootbone.core.smd and redfox_lx.core_0.smd and bam, I could see in Noesis new option because the rig was now present.  
I exported the model - with Rig to .fbx and then imported into Max 2017 (need to get a newer copy heh) and yup theres the mesh, rigged amd ready to rock!
I applied the textures - Needed a bit of playing as the main texture was backward (Just did a quick mesh flip horizontally in UV Unwrap and its looks fine.
Added the texture to the fur mesh and applied the alpha channel.
Setup for a quick render - Not great results as the texture looks washed out. Removed the fur mesh and texture and the base mesh again looks washed out ( the eyes are not dark, but almost grey - weird!  Looks fine in the viewport with crisp dark material - may do some investigation on that, but more interested in having a go with the Robots now.

{EDIT] - worked out the washed texture issue - Just me being daft - Forgot to put the Ambient Color to Black - It was on Grey hence the washed out Look!

I know someone mentioned that the robots are more difficult, do to the destructive mesh elements which have to be attached.  I'll have to go back and read the whole thread again to see If I can work it out after doing the whole skeleton.smd edits.

I quickly got the base mesh for the Long Legs into Max (yay) and then tried to add one of the panels - The panel just came in at the root 0,0,0 so I am doing something wrong

Thanks everyone for the help so far, I'm sure I'll be asking more question in due course!

Cheers

Ryan

Yes, you are right, .core file path need  same as .bin file.
## Post #278
- Username: NoireHawk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 03, 2018 9:52 pm
- Post datetime: 2021-02-08T09:09:35+00:00
- Post Title: Re: Horizon Zero Dawn

I'm trying to pull out all the files related to the holograms and their animations. from PC version of game 1.0.10.4 (6260111_(44375)_win_gog) 

I copied three files to separate folder (DLC1.bin , Initial.bin , Remainder.bin) 
also downloaded a file named oo2core_5_win64 and renamed it, replacing 5 with 7 in the name. 

So, pulled out only textures, and only one works, other 5 when opened in GIMP gives an error. Used daemon1 pc tool, decima-explorer... nothing new 

folder screenshot > [https://imgur.com/SkXrpuv](https://imgur.com/SkXrpuv) 

I tried to find PKG CUSA07319, to make the same thing but all the torrents are dead
## Post #279
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-02-08T10:08:51+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from NoireHawk ↑Mon Feb 08, 2021 5:09 pm at Mon Feb 08, 2021 5:09 pm
>
> 
So, pulled out only textures, and only one works, other 5 when opened in GIMP gives an error.
seems GIMP doesnt support modern textures. Find something proper to open them.
## Post #280
- Username: LingeringHum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jan 22, 2021 8:41 am
- Post datetime: 2021-02-08T15:33:26+00:00
- Post Title: Re: Horizon Zero Dawn

Hey All,

So I have been playing around with extracting the models and textures and even the animations of the robots for 2 weeks or so now and I think I have the basic premise down. - I am able to get models in 3DMax and texture them - happy days!
I am however a bit confused about one or two things and wondered if anyone else has run into them.
When I extract the skeletons for some of the larger robots, such as behemoth, Thunderjaw, I have noticed that some of the bones for the destructable objects are placed in really weird positions. The the case of the thuderJaw, many of the bones for the neck section plates are set to 0 in the X plane and randomly dotted around. This means when i then come along aand snap the neckplate meshes to the helpers - most are hidden inside the main meshes and I am having to move the helpers manually and trying to line them up by eye.  Is there a skeleton file that has all the bones in the correct default postion?



bonepositions.PNG (153.62 KiB) Viewed 472 times



I have included links for the skeleton_rootbone.core of the ThuderJaw that I have extracted for reference:
.smd - https://drive.google.com/file/d/18rx_Hv ... sp=sharing
.fbx - https://drive.google.com/file/d/17Y2-oX ... sp=sharing
As you will be able to see on the ThunderJaws Left had side 2 of the upper neck plate bones are positioned "correctly" where as, all of the other plates are not. - Any Ideas?
 How are people actually getting the destructable parts to appear in the correct positions weighted.  In reading the thread, some have mentioned adding the skeleton code to the start of the parts code in the .smd files and for some of the bits (such as the canisters on the neck of the behemouth) this works!, but many of the bits just appear at 0,0,0 right in the same spot as the root bone.  I have then manually snapped, aligned and linked these pieces to the corresponding helper bone.  Is this right or am I missing something obvious or left a step out?
How are people applying the animations to the extracted models and model skelton.  As mentioned following the steps outlined in this thread, I have managed to extract, both models and and animations and can import them in 3DMax.  I know others are using different 3D software, but how are you applying the animations to your meshes?  The only way I have managed to get results is by manually snapping/aligning and linking the weighted mesh skeleton to the animated IK/FK skeleton.  As both meshes have different amount of bones and different names (I know some match) has anyone got a better suggestion on how to achieve this? I have access to 3DsMax, Maya and Blender so if another software can do this more easily, I am open all ears!


Any help would be greatly appreciated and thank you all for the help and support so far
Cheers
Ryan
## Post #281
- Username: LingeringHum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jan 22, 2021 8:41 am
- Post datetime: 2021-02-09T12:22:33+00:00
- Post Title: Re: Horizon Zero Dawn

Hey All,

Ok here's any even easier question  - Once you extract your .core files and place them into the same folder, is there a particular sequence I should follow, of dragging them onto horizon_pc.exe, in order to get the skelton(rig) to build correctly and so that all bones (helpers) appear in the correct locations?

Also has anyone tried to export the Snapmaw (BeachLizard)?  This one is very confusing as the plates and parts numbers do not seem to match the naming conventions of the rig that I have pulled out.  The rig/skeleton mentions no plates and even the animated skeletons do not seem to have positions to place the destructables.

Cheers
## Post #282
- Username: zensiert
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 14, 2021 6:54 am
- Post datetime: 2021-03-19T06:05:28+00:00
- Post Title: Re: Horizon Zero Dawn

Hi, im kinda lost.
this is my folder:
* DLC1.bin
* horizon.ini
* Horizon_pc.exe
* Initial.bin
* oo2core_5_win64.dll
* Remainder.bin

and the ini file holds the steam download folder:
C:\Program Files (x86)\Steam\steamapps\common\Horizon Zero Dawn *with \n at the end

but the tool just runs for 2 sec and stops.
I appreciate all help.
## Post #283
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-03-19T10:02:42+00:00
- Post Title: Re: Horizon Zero Dawn

tool can't just stop
must be an error message
## Post #284
- Username: U653748
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 05, 2015 5:33 am
- Post datetime: 2021-03-20T11:00:01+00:00
- Post Title: Re: Horizon Zero Dawn

Greetings all, been playing the game over again to both enjoy the game and see what models i wanted to extract, while playing frozen wilds i came across the drone hangar near the dam and went looking for the drone model itself seen here: [https://static.wikia.nocookie.net/horiz ... 1125134448](https://static.wikia.nocookie.net/horizonzerodawn/images/8/8b/A_Secret_Shared.png/revision/latest?cb=20171125134448)

one of the references i was able to find was a folder named "droneplatform" however upon dragging the .core file on to the horizon tool nothing happened which leads me to believe that maybe there was no model there. i did do a search for other drone references but only found the ones for the cauldrons and what would appear to be the rail parts resource you're meant to get for a quest related to the hangar, the latter came out at 0 kb. Has anyone else perhaps came across the drone in their travels among the HZD files?
## Post #285
- Username: Py0
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 27, 2021 10:53 pm
- Post datetime: 2021-03-29T10:32:05+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from zensiert ↑Fri Mar 19, 2021 2:05 pm at Fri Mar 19, 2021 2:05 pm
>
> 
Hi, im kinda lost.
this is my folder:
* DLC1.bin
* horizon.ini
* Horizon_pc.exe
* Initial.bin
* oo2core_5_win64.dll
* Remainder.bin

and the ini file holds the steam download folder:
C:\Program Files (x86)\Steam\steamapps\common\Horizon Zero Dawn *with \n at the end

but the tool just runs for 2 sec and stops.
I appreciate all help.

I'm having the same problem, even tried copying the .bin files to another computer but same result.
I have tried oo2core_x_win64.dll versions 3 (from game), 5, 6, 7 and also renaming all versions to _5 and _7 but no luck with either the original Horizon.exe or Horizon_pc.exe.
All files are in the one folder, and I put the path in horizon.ini as well.
Also tried in the game Packed_DX12 folder.

The error is always:

```
   at System.ThrowHelper.ThrowArgumentException(ExceptionResource resource)
   at System.Collections.Generic.Dictionary`2.Insert(TKey key, TValue value, Boolean add)
   at System.Collections.Generic.Dictionary`2.Add(TKey key, TValue value)
   at ?????????????????????????????????????????.?????????????????????????????????????????(String[] )
```


I've tried the previous suggestions in this thread but nothing seems to work.
Any ideas would be greatly appreciated!
## Post #286
- Username: Flaymez
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 05, 2021 9:19 pm
- Post datetime: 2021-04-05T13:20:51+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Py0 ↑Mon Mar 29, 2021 6:32 pm at Mon Mar 29, 2021 6:32 pm
>
> 
zensiert wrote: ↑Fri Mar 19, 2021 2:05 pm
Hi, im kinda lost.
this is my folder:
* DLC1.bin
* horizon.ini
* Horizon_pc.exe
* Initial.bin
* oo2core_5_win64.dll
* Remainder.bin

and the ini file holds the steam download folder:
C:\Program Files (x86)\Steam\steamapps\common\Horizon Zero Dawn *with \n at the end

but the tool just runs for 2 sec and stops.
I appreciate all help.


I'm having the same problem, even tried copying the .bin files to another computer but same result.
I have tried oo2core_x_win64.dll versions 3 (from game), 5, 6, 7 and also renaming all versions to _5 and _7 but no luck with either the original Horizon.exe or Horizon_pc.exe.
All files are in the one folder, and I put the path in horizon.ini as well.
Also tried in the game Packed_DX12 folder.

The error is always:
Code: Select allUnhandled Exception: System.ArgumentException: An item with the same key has already been added.
   at System.ThrowHelper.ThrowArgumentException(ExceptionResource resource)
   at System.Collections.Generic.Dictionary`2.Insert(TKey key, TValue value, Boolean add)
   at System.Collections.Generic.Dictionary`2.Add(TKey key, TValue value)
   at ?????????????????????????????????????????.?????????????????????????????????????????(String[] )

I've tried the previous suggestions in this thread but nothing seems to work.
Any ideas would be greatly appreciated!

Having the same issue, same error. Hopefully someone has an idea for what we can do?
## Post #287
- Username: ZanglorOfCats
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 10, 2021 10:07 pm
- Post datetime: 2021-04-11T18:02:24+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Flaymez ↑Mon Apr 05, 2021 9:20 pm at Mon Apr 05, 2021 9:20 pm
>
> 
Py0 wrote: ↑Mon Mar 29, 2021 6:32 pm
zensiert wrote: ↑Fri Mar 19, 2021 2:05 pm
Hi, im kinda lost.
this is my folder:
* DLC1.bin
* horizon.ini
* Horizon_pc.exe
* Initial.bin
* oo2core_5_win64.dll
* Remainder.bin

and the ini file holds the steam download folder:
C:\Program Files (x86)\Steam\steamapps\common\Horizon Zero Dawn *with \n at the end

but the tool just runs for 2 sec and stops.
I appreciate all help.


I'm having the same problem, even tried copying the .bin files to another computer but same result.
I have tried oo2core_x_win64.dll versions 3 (from game), 5, 6, 7 and also renaming all versions to _5 and _7 but no luck with either the original Horizon.exe or Horizon_pc.exe.
All files are in the one folder, and I put the path in horizon.ini as well.
Also tried in the game Packed_DX12 folder.

The error is always:
Code: Select allUnhandled Exception: System.ArgumentException: An item with the same key has already been added.
   at System.ThrowHelper.ThrowArgumentException(ExceptionResource resource)
   at System.Collections.Generic.Dictionary`2.Insert(TKey key, TValue value, Boolean add)
   at System.Collections.Generic.Dictionary`2.Add(TKey key, TValue value)
   at ?????????????????????????????????????????.?????????????????????????????????????????(String[] )

I've tried the previous suggestions in this thread but nothing seems to work.
Any ideas would be greatly appreciated!


Having the same issue, same error. Hopefully someone has an idea for what we can do?
I had the same issue until I changed the `.ini` file to reference the folder containing the `DLC1.bin`, `Initial.bin`, and `Remainder.bin` files (so the folder that the `.ini` file itself is in for the above example), *not* the steam folder. The `Patch.bin` and `FGRWin32.bin` files contain items that result in duplicate keys, so if they are in the search folder specified in the `.ini` (or below: search appears to be recursive) this will break the tool
## Post #288
- Username: BioGenx2b
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 20, 2021 3:17 am
- Post datetime: 2021-04-19T20:11:15+00:00
- Post Title: Re: Horizon Zero Dawn

I'm trying to use this tool to extract the audio from the PC game (voice lines, music loops), but most of it appears to be unusable. Only a sliver of those files are actually playable, the rest appear to be stubs.

Effects though, those are coming in just fine mostly.

Any ideas?
## Post #289
- Username: tskune
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 07, 2021 4:16 pm
- Post datetime: 2021-05-09T09:15:42+00:00
- Post Title: Re: Horizon Zero Dawn

I have some questions. Let me start with what I currently understand:

> Reply from daemon1 ↑Tue Feb 20, 2018 4:33 am at Tue Feb 20, 2018 4:33 am
>
> 
step 1:
Run horizon on all parts files. This will create matrices as it was before

This means I want to run horizon, or in my case horizon_pc, on all the parts files.

> Reply from daemon1 ↑Tue Feb 20, 2018 4:33 am at Tue Feb 20, 2018 4:33 am
>
> 
step 2:
Run horizon on template file. This will extract animation skeleton from it.
(you dont need ascii and smd files generated, delete them. They are only useful if you want to experiment with animation only)
So you have .animskel file now in the same folder.

This wants me to get  the .animskel file.
-Side question: Do I need the ascii and smd files if I want to create my own animations, or only if I want to use the premade animations?

> Reply from daemon1 ↑Tue Feb 20, 2018 4:33 am at Tue Feb 20, 2018 4:33 am
>
> 
step 3: run this:
horizon [mesh_skeleton] [animskel] > a.bat
this will create FULL robot skeleton both in SMD & ASCII and also A.BAT file

Here we want to use both a mesh skeleton and the .animskel file to create a.bat.
Where does the mesh skeleton come from? Is it like with the characters?

> Reply from daemon1 ↑Tue Feb 20, 2018 4:33 am at Tue Feb 20, 2018 4:33 am
>
> 
Extracting characters with skeleton:
===============================================================
1. place all parts of a character in one folder, and run horizon on all of them
2. a file called "matrices" will be created and UPDATED in the process with all the bone matrices present in all parts
3. put corresponding skeleton file to the same folder and run horizon on it
4. copy-paste skeleton into model parts so they will be complete working models
===============================================

Here we're supposed to run horizon on the skeleton file, which for robots is presumably the mesh_skeleton_rootbone file, and then copy-paste the skeleton file into the part files.
-Side note: My understanding is that we're supposed to copy-paste the skeleton file to the top of the parts files.
In the instructions for the robot models this step seems to be implied.

> Reply from daemon1 ↑Tue Feb 20, 2018 4:33 am at Tue Feb 20, 2018 4:33 am
>
> 
- matrices from mesh parts (same as characters)
- mesh skeleton (same as characters)

The questions I have are:
I̶s̶ ̶t̶h̶e̶ ̶p̶r̶o̶c̶e̶s̶s̶ ̶w̶i̶t̶h̶ ̶t̶h̶e̶ ̶r̶o̶b̶o̶t̶ ̶s̶k̶e̶l̶e̶t̶o̶n̶ ̶t̶h̶e̶ ̶s̶a̶m̶e̶ ̶a̶s̶ ̶w̶i̶t̶h̶ ̶t̶h̶e̶ ̶c̶h̶a̶r̶a̶c̶t̶e̶r̶ ̶s̶k̶e̶l̶e̶t̶o̶n̶?̶
I̶s̶ ̶i̶t̶ ̶t̶h̶e̶ ̶i̶m̶p̶l̶i̶e̶d̶ ̶p̶a̶r̶t̶ ̶o̶f̶ ̶s̶t̶e̶p̶ ̶1̶?̶ ̶(̶M̶e̶a̶n̶i̶n̶g̶:̶ ̶D̶o̶ ̶I̶ ̶e̶x̶t̶r̶a̶c̶t̶ ̶t̶h̶e̶ ̶p̶a̶r̶t̶s̶ ̶a̶n̶d̶ ̶t̶h̶e̶ ̶s̶k̶e̶l̶e̶t̶o̶n̶ ̶b̶e̶f̶o̶r̶e̶ ̶t̶h̶e̶ ̶a̶n̶i̶m̶a̶t̶i̶o̶n̶ ̶s̶k̶e̶l̶e̶t̶o̶n̶?̶)̶
D̶o̶ ̶I̶ ̶p̶u̶t̶ ̶t̶h̶e̶ ̶s̶k̶e̶l̶e̶t̶o̶n̶ ̶t̶e̶x̶t̶ ̶a̶t̶ ̶t̶h̶e̶ ̶t̶o̶p̶ ̶o̶f̶ ̶t̶h̶e̶ ̶p̶a̶r̶t̶ ̶f̶i̶l̶e̶s̶?̶
Do I need the ascii and smd files from the template if I am going to make new animations, or only needed when using premade animations?

Edit:
I've managed to get all the destructible parts to line up with the model. But, when I ran a.bat on the eye model, the main larger mesh got removed. I'm not sure what I did wrong and I'm wondering if anyone has had this issue, or possibly a way to fix it.

Edit 2:
I have also gotten the model rigged with the skeleton. So all I need now is to fix the eye, as mentioned above, as well as to figure out how to get all the textures into blender. If anyone could help me with that it would be greatly appreciated.
## Post #290
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2021-06-01T12:23:50+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from BioGenx2b ↑Tue Apr 20, 2021 4:11 am at Tue Apr 20, 2021 4:11 am
>
> 
Effects though, those are coming in just fine mostly.
Any ideas?
[viewtopic.php?f=16&t=17726&p=139223&hilit=music#p139223](https://forum.xentax.com/viewtopic.php?f=16&t=17726&p=139223&hilit=music#p139223)
Apparently everything except sounds is still not supported by the tool.
## Post #291
- Username: jungljuice
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 14, 2021 12:34 pm
- Post datetime: 2021-08-14T04:38:05+00:00
- Post Title: Re: Horizon Zero Dawn

Hey guys, I am trying to turn off the battle music (the music that starts playing when enemies appear on screen/when you are fighting) and that the normal ambient music keeps playing. How would i go about doing this?

(p.s first post, hi all)
## Post #292
- Username: Rvel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 22, 2021 9:25 pm
- Post datetime: 2021-08-30T14:13:07+00:00
- Post Title: Re: Horizon Zero Dawn

Is there any way to extract models using a Mac? 
I'm looking for the Talanah model, but haven't been able to get this working in a virtual machine.
## Post #293
- Username: Kar7hr7
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 16, 2021 3:01 pm
- Post datetime: 2021-10-02T19:32:08+00:00
- Post Title: Re: Horizon Zero Dawn

I cannot extract the model's textures 
DDS is broken 
Please, can you help? I don't understand what i should do
## Post #294
- Username: flyzealot001
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 21, 2021 3:54 am
- Post datetime: 2021-10-20T19:54:58+00:00
- Post Title: Re: Horizon Zero Dawn

thank you ~!~!
## Post #295
- Username: souta0201
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 14, 2021 9:15 pm
- Post datetime: 2021-11-15T08:59:22+00:00
- Post Title: Re: Horizon Zero Dawn

I would like you to make a video of the robot model, texture, and even the extraction of animation.
## Post #296
- Username: zsjcoral
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Dec 13, 2021 6:15 pm
- Post datetime: 2021-12-14T08:01:19+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Py0 ↑Mon Mar 29, 2021 6:32 pm at Mon Mar 29, 2021 6:32 pm
>
> 
zensiert wrote: ↑Fri Mar 19, 2021 2:05 pm
Hi, im kinda lost.
this is my folder:
* DLC1.bin
* horizon.ini
* Horizon_pc.exe
* Initial.bin
* oo2core_5_win64.dll
* Remainder.bin

and the ini file holds the steam download folder:
C:\Program Files (x86)\Steam\steamapps\common\Horizon Zero Dawn *with \n at the end

but the tool just runs for 2 sec and stops.
I appreciate all help.


I'm having the same problem, even tried copying the .bin files to another computer but same result.
I have tried oo2core_x_win64.dll versions 3 (from game), 5, 6, 7 and also renaming all versions to _5 and _7 but no luck with either the original Horizon.exe or Horizon_pc.exe.
All files are in the one folder, and I put the path in horizon.ini as well.
Also tried in the game Packed_DX12 folder.

The error is always:
Code: Select allUnhandled Exception: System.ArgumentException: An item with the same key has already been added.
   at System.ThrowHelper.ThrowArgumentException(ExceptionResource resource)
   at System.Collections.Generic.Dictionary`2.Insert(TKey key, TValue value, Boolean add)
   at System.Collections.Generic.Dictionary`2.Add(TKey key, TValue value)
   at ?????????????????????????????????????????.?????????????????????????????????????????(String[] )

I've tried the previous suggestions in this thread but nothing seems to work.
Any ideas would be greatly appreciated!
Me too. Does anyone have a solution? thank you very much
## Post #297
- Username: Sideromelane
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 12, 2022 4:40 am
- Post datetime: 2022-01-11T21:17:02+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from zsjcoral ↑Tue Dec 14, 2021 4:01 pm at Tue Dec 14, 2021 4:01 pm
>
> 
Py0 wrote: ↑Mon Mar 29, 2021 6:32 pm
zensiert wrote: ↑Fri Mar 19, 2021 2:05 pm
Hi, im kinda lost.
this is my folder:
* DLC1.bin
* horizon.ini
* Horizon_pc.exe
* Initial.bin
* oo2core_5_win64.dll
* Remainder.bin

and the ini file holds the steam download folder:
C:\Program Files (x86)\Steam\steamapps\common\Horizon Zero Dawn *with \n at the end

but the tool just runs for 2 sec and stops.
I appreciate all help.


I'm having the same problem, even tried copying the .bin files to another computer but same result.
I have tried oo2core_x_win64.dll versions 3 (from game), 5, 6, 7 and also renaming all versions to _5 and _7 but no luck with either the original Horizon.exe or Horizon_pc.exe.
All files are in the one folder, and I put the path in horizon.ini as well.
Also tried in the game Packed_DX12 folder.

The error is always:
Code: Select allUnhandled Exception: System.ArgumentException: An item with the same key has already been added.
   at System.ThrowHelper.ThrowArgumentException(ExceptionResource resource)
   at System.Collections.Generic.Dictionary`2.Insert(TKey key, TValue value, Boolean add)
   at System.Collections.Generic.Dictionary`2.Add(TKey key, TValue value)
   at ?????????????????????????????????????????.?????????????????????????????????????????(String[] )

I've tried the previous suggestions in this thread but nothing seems to work.
Any ideas would be greatly appreciated!

Me too. Does anyone have a solution? thank you very much

My first comment on this forum, I signed up as I wanted to extract the game files. But also i just found a 'fix' for this exact issue! 

Run the horizon.exe withOUT DLC1.bin or Patch.bin. One of those two is crashing the tool. 

I copied Initial.bin and Remainder.bin to a seperate folder with the Horizon exe and oo2core dll and it works.
## Post #298
- Username: player12341
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Jan 16, 2022 10:46 pm
- Post datetime: 2022-01-16T23:07:04+00:00
- Post Title: Re: Horizon Zero Dawn

hi I am new to this stuff I have successfully got the res.txt file by using horizon tool but I am stuck on step3. if you want to extract some resource, run
horizon /e resourcename
where should I write the horizon /e resourcename thing please guide me
## Post #299
- Username: player12341
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Jan 16, 2022 10:46 pm
- Post datetime: 2022-01-19T08:52:32+00:00
- Post Title: Re: Horizon Zero Dawn

hi I am stuck in step3 of the guide where I have to write horizon /e resourcename in cmd I guess? and it will be like 
directory where horizon tool is then /e then resourcename
like in cmd 
d\games\horizon zero dawn\packed_pink\horizon.exe /e resourcename is this correct cause every time I do this in cmd no message appears and cmd shifts to next line as I press enter please help me and guide me where I am making mistake.
## Post #300
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-19T12:14:57+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from player12341 ↑Wed Jan 19, 2022 4:52 pm at Wed Jan 19, 2022 4:52 pm
>
> 
hi I am stuck in step3 of the guide where I have to write horizon /e resourcename in cmd I guess? and it will be like 
directory where horizon tool is then /e then resourcename
like in cmd 
d\games\horizon zero dawn\packed_pink\horizon.exe /e resourcename is this correct cause every time I do this in cmd no message appears and cmd shifts to next line as I press enter please help me and guide me where I am making mistake.
this doesnt make any sense
can you make a screenshot?
## Post #301
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-19T12:19:37+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Sideromelane ↑Wed Jan 12, 2022 5:17 am at Wed Jan 12, 2022 5:17 am
>
> 
But also i just found a 'fix' for this exact issue! 
Run the horizon.exe withOUT DLC1.bin or Patch.bin. One of those two is crashing the tool.
This is actually stated in the very first message in the first page!
## Post #302
- Username: player12341
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Jan 16, 2022 10:46 pm
- Post datetime: 2022-01-20T16:18:09+00:00
- Post Title: Re: Horizon Zero Dawn

How to use the horizon.exe tool step by step and extract 3d models from horizon zero dawn video tutorial:-

[https://youtu.be/9p7u8Bo-Noc](https://youtu.be/9p7u8Bo-Noc)
## Post #303
- Username: Fattishman
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 23, 2022 1:31 am
- Post datetime: 2022-01-22T17:39:16+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Wed Sep 30, 2020 2:11 pm at Wed Sep 30, 2020 2:11 pm
>
> 
Ok here's PC tool.

Usage is same as PS4. Someone said it doesnt work with oodle5, so i made it with oodle7, even though i think you can use other verisons renaming the .DLL as usual.

I checked a few models, textures and animations, they all look exactly same as on PS4. No quality difference.
So I dont know why files are 10GB bigger.

If anything will not work, let me know.

Windows blocks the download...
## Post #304
- Username: player12341
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Jan 16, 2022 10:46 pm
- Post datetime: 2022-01-22T17:49:04+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Fattishman ↑Sun Jan 23, 2022 1:39 am at Sun Jan 23, 2022 1:39 am
>
> 
daemon1 wrote: ↑Wed Sep 30, 2020 2:11 pm
Ok here's PC tool.

Usage is same as PS4. Someone said it doesnt work with oodle5, so i made it with oodle7, even though i think you can use other verisons renaming the .DLL as usual.

I checked a few models, textures and animations, they all look exactly same as on PS4. No quality difference.
So I dont know why files are 10GB bigger.

If anything will not work, let me know.


Windows blocks the download...
turn off your windows antivirus for a bit as the tool downloads and then use the tool correctly by following video tutorial:-
[https://youtu.be/9p7u8Bo-Noc](https://youtu.be/9p7u8Bo-Noc)
## Post #305
- Username: 萌新小强
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 26, 2021 5:41 pm
- Post datetime: 2022-02-10T07:40:50+00:00
- Post Title: Re: Horizon Zero Dawn

animation_managers\characters\humanoids\player\female\anim 
export animation error It's all messed up Can you help me see?
[1943_02.7z](https://xentaxbackup.github.io/file/21756_1943_02.7z)
## Post #306
- Username: player12341
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Jan 16, 2022 10:46 pm
- Post datetime: 2022-02-13T07:24:32+00:00
- Post Title: Re: Horizon Zero Dawn

HI GUYS THIS IS THE VIDEO TUTORIAL ON HOW TO CORRECTLY EXTRACT ANIMATIONS FROM HORIZON ZERO DAWN USING THE TOOL:

[https://youtu.be/kaKdZ_YbH5I](https://youtu.be/kaKdZ_YbH5I)
## Post #307
- Username: player12341
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Jan 16, 2022 10:46 pm
- Post datetime: 2022-02-13T07:25:54+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from 萌新小强 ↑Thu Feb 10, 2022 3:40 pm at Thu Feb 10, 2022 3:40 pm
>
> 
animation_managers\characters\humanoids\player\female\anim 
export animation error It's all messed up Can you help me see?

follow this video to correctly export animation from horizon zero dawn 

[https://youtu.be/kaKdZ_YbH5I](https://youtu.be/kaKdZ_YbH5I)
## Post #308
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-02-13T13:21:37+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from player12341 ↑Sun Feb 13, 2022 3:25 pm at Sun Feb 13, 2022 3:25 pm
>
> ...follow this video to correctly export animation from horizon zero dawn ...
You don't need to double post for that, one post would have been enough even if it was in response to the user in need.

Also you could have simplified this a bit and make a batch file ".bat" using notepad, to speed things up if you want to 

```
for %%a in (*.core) do Horizon_pc.exe "%%a"
```

or if you run it directly from cmd through that folder, when you hold "shift" you select "Open command window here"
then paste this and run also as a batch:

```
for %a in (*.core) do Horizon.exe "%a"
```

noticed the difference? batch file requires two "%%" while the other option only one "%"
## Post #309
- Username: Geraltz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 14, 2022 5:35 am
- Post datetime: 2022-02-13T22:51:57+00:00
- Post Title: Re: Horizon Zero Dawn

Hi everyone! I was wondering if there is a chance we could get the source code of the horizon tool? I am not interested in the textures of the game but rather in the code of the game itself, specifically the way it generates modification boxes in shops or the way modifications and modification boxes work in general. I have extracted the .core files necessary but now I can't view them because the tool only extracts the files that are tied to the textures and now I'm stuck. Thank you daemon1 for making this tool and hope anyone can help me out. Cheers!
## Post #310
- Username: HowdyNeighbor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 11, 2022 1:58 am
- Post datetime: 2022-02-13T22:52:38+00:00
- Post Title: Re: Horizon Zero Dawn

Howdy, forum lurker here.  Stumbled upon this tool a couple of months ago with the goal of generating 3D-printable meshes for personal use, ideally in poses according to exciting "action stances" from animation files.

I've worked via trial & error through everything up to just after daemon's Step 4:

> Reply from daemon1 ↑Tue Feb 20, 2018 4:33 am at Tue Feb 20, 2018 4:33 am
>
> 

step 4:
Open A.BAT file, and replace all "_helper" strings with ".core". This probably could be done automatically on export, but the thing is, I'm not sure all helper bones will always be called the same as helper MESHES. So I'm leaving this to the users at least for now.
Run this .BAT file.

I'm working with the horse/Strider model right now and have a folder full of extracted ascii and smd files for the body part, 24 "plate/eye" parts, and the canister_fuel part.  I've also successfully generated the a.bat and mesh_skeleton_rootbone.core.ascii and mesh_skeleton_rootbone.core.smd files from Step 3--they have nonzero file sizes.  I replaced "_helper" strings with ".core" for all 24 items listed in the a.bat file, as in Step 4.  Note that the fuel canister is missing from the a.bat list. How does that get placed and weighted to the model?


Running the a.bat file updates the mesh_skeleton_rootbone.core.ascii and .smd files.  I am now confused by the following directions:

> Reply from daemon1 ↑Tue Feb 20, 2018 4:33 am at Tue Feb 20, 2018 4:33 am
>
> 

to load all destructible parts as one file:
========================================================
Merge all ASCII files into one as text file, then copypaste skeleton into it.
Then count submeshes (it will correspond to number of "material" string)
and put a number of submeshes after the skeleton (before all the actual data).
This number will correspond to number of "material" string in all files.
Same for SMD files, just no need to count submeshes.
Which ASCII files are getting merged, and should the combined file still be another ASCII file (or is just .txt okay)?  Are the prior 25 part's ASCIIs just merged e.g., by using "copy [A]+[ B]+[C] [outputABC]" in the command prompt?  Does the entire content of the mesh_skeleton_rootbone.core.ascii file get pasted to the beginning of this new merged file?  Do any lines need to be deleted like we did when combining the mesh and skeleton smd files from a simple animal model?

What is meant by

> Reply from daemon1 ↑Tue Feb 20, 2018 4:33 am at Tue Feb 20, 2018 4:33 am
>
> 

and put a number of submeshes after the skeleton (before all the actual data).
This number will correspond to number of "material" string in all files.

I count the string "material" 31 times if I merge ASCIIs and paste the mesh_skeleton_rootbone.core.ascii text to a combined file as I asked about above.  What is the exact text I need to enter after the text copied from the mesh_skeleton_rootbone.core.ascii file to represent this 31 submesh number?

Next, I assume the SMD merging is the same as for simple animal models, in that we'll copy the text from mesh_skeleton_rootbone.core.smd and paste it to the beginning of a combined mesh smd file, being sure to delete "version 1" and "nodes".  Will that combined mesh file also be a merger of all 25 part's SMD files, or do any other problematic lines need to be deleted too?

If I can accomplish this much, will that final combined SMD file display correctly as a complete model in Noesis--body, removable parts, and skeleton?  Does the program somehow distinguish between the core body and removable parts as seen in Daemon1's video https://www.youtube.com/watch?v=rsbwOuqor3c?  or will it interpret it as one mesh piece?

Lastly, why does the ascii file need to be merged if we're only opening an smd file for exporting a mesh model?

-----------------------------------
Appreciate all of the work you all have done.  Glad to see some friendly, repeating helpers on here too.  I don't have any programming experience, but I work with technical writing and have written up detailed directions for how I've gotten this far.  If I can accomplish these last conversion steps and then figure out animation extraction, I'd be happy to share my SOP with the forum.  Perhaps it would help solve the most common "stuck. Help!?" questions.

Cheers y'all!
## Post #311
- Username: Juanrc
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 20, 2022 8:51 am
- Post datetime: 2022-02-21T03:23:23+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from HowdyNeighbor ↑Mon Feb 14, 2022 6:52 am at Mon Feb 14, 2022 6:52 am
>
> 
Howdy, forum lurker here.  Stumbled upon this tool a couple of months ago with the goal of generating 3D-printable meshes for personal use, ideally in poses according to exciting "action stances" from animation files.

I've worked via trial & error through everything up to just after daemon's Step 4:
daemon1 wrote: ↑Tue Feb 20, 2018 4:33 am

step 4:
Open A.BAT file, and replace all "_helper" strings with ".core". This probably could be done automatically on export, but the thing is, I'm not sure all helper bones will always be called the same as helper MESHES. So I'm leaving this to the users at least for now.
Run this .BAT file.


I'm working with the horse/Strider model right now and have a folder full of extracted ascii and smd files for the body part, 24 "plate/eye" parts, and the canister_fuel part.  I've also successfully generated the a.bat and mesh_skeleton_rootbone.core.ascii and mesh_skeleton_rootbone.core.smd files from Step 3--they have nonzero file sizes.  I replaced "_helper" strings with ".core" for all 24 items listed in the a.bat file, as in Step 4.  Note that the fuel canister is missing from the a.bat list. How does that get placed and weighted to the model?


Running the a.bat file updates the mesh_skeleton_rootbone.core.ascii and .smd files.  I am now confused by the following directions:
daemon1 wrote: ↑Tue Feb 20, 2018 4:33 am

to load all destructible parts as one file:
========================================================
Merge all ASCII files into one as text file, then copypaste skeleton into it.
Then count submeshes (it will correspond to number of "material" string)
and put a number of submeshes after the skeleton (before all the actual data).
This number will correspond to number of "material" string in all files.
Same for SMD files, just no need to count submeshes.

Which ASCII files are getting merged, and should the combined file still be another ASCII file (or is just .txt okay)?  Are the prior 25 part's ASCIIs just merged e.g., by using "copy [A]+[ B]+[C] [outputABC]" in the command prompt?  Does the entire content of the mesh_skeleton_rootbone.core.ascii file get pasted to the beginning of this new merged file?  Do any lines need to be deleted like we did when combining the mesh and skeleton smd files from a simple animal model?

What is meant by
daemon1 wrote: ↑Tue Feb 20, 2018 4:33 am

and put a number of submeshes after the skeleton (before all the actual data).
This number will correspond to number of "material" string in all files.


I count the string "material" 31 times if I merge ASCIIs and paste the mesh_skeleton_rootbone.core.ascii text to a combined file as I asked about above.  What is the exact text I need to enter after the text copied from the mesh_skeleton_rootbone.core.ascii file to represent this 31 submesh number?

Next, I assume the SMD merging is the same as for simple animal models, in that we'll copy the text from mesh_skeleton_rootbone.core.smd and paste it to the beginning of a combined mesh smd file, being sure to delete "version 1" and "nodes".  Will that combined mesh file also be a merger of all 25 part's SMD files, or do any other problematic lines need to be deleted too?

If I can accomplish this much, will that final combined SMD file display correctly as a complete model in Noesis--body, removable parts, and skeleton?  Does the program somehow distinguish between the core body and removable parts as seen in Daemon1's video https://www.youtube.com/watch?v=rsbwOuqor3c?  or will it interpret it as one mesh piece?

Lastly, why does the ascii file need to be merged if we're only opening an smd file for exporting a mesh model?

-----------------------------------
Appreciate all of the work you all have done.  Glad to see some friendly, repeating helpers on here too.  I don't have any programming experience, but I work with technical writing and have written up detailed directions for how I've gotten this far.  If I can accomplish these last conversion steps and then figure out animation extraction, I'd be happy to share my SOP with the forum.  Perhaps it would help solve the most common "stuck. Help!?" questions.

Cheers y'all!

That would be great, I am stuck after extracting the models, also there are a lot of robots wuth no mesh_skeleton_rootbone and only have skeleton_rootbone, already managed to import the mesh files to blender, but the destructible ones dont import at the desired location but at the origin (0,0). any help would be great
## Post #312
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-02-21T09:15:20+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Juanrc ↑Mon Feb 21, 2022 11:23 am at Mon Feb 21, 2022 11:23 am
>
> 
there are a lot of robots wuth no mesh_skeleton_rootbone and only have skeleton_rootbone
when i said that "half of robots have 2 skeleton files", i meant IF a robot has 2 skeleton files, THEN you need to use mesh_skeleton_rootbone.
If robot has only one skeleton, that one is ok to use with the tool.
## Post #313
- Username: jimmy12345
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 06, 2021 12:24 pm
- Post datetime: 2022-02-24T06:55:44+00:00
- Post Title: Re: Horizon Zero Dawn

hello and extracted the raptor model
but only the files
body.core_0.smd AND antennas.core_0.smd
they open me
in their correct coordinates
all the rest of the list appears in the center of the model out of its original place and without a skeleton... as if it were a foreign model...

can someone help me to solve this problem?
how I do this? someone help me?
[https://www.youtube.com/watch?v=rsbwOuqor3c](https://www.youtube.com/watch?v=rsbwOuqor3c)

I have managed to extract models and textures using these guides

extract models
[https://www.youtube.com/watch?v=9p7u8Bo-Noc](https://www.youtube.com/watch?v=9p7u8Bo-Noc)
extract animations
[https://www.youtube.com/watch?v=kaKdZ_YbH5I](https://www.youtube.com/watch?v=kaKdZ_YbH5I)

Everything in the guides went well... or not?

I can't understand how
bring the armor parts to their actual position
Can someone give me a clearer guide?
I'm ultra noob...

I tried to follow this guide
[viewtopic.php?f=16&t=17726](https://forum.xentax.com/viewtopic.php?f=16&t=17726)
the final steps explains how

 but I can't get it right.
to which file do I change from _helper to .core?
How or when is the a.bat file created?

I'm using blender latest version with the tool to import smd in its latest version... will that be a problem?

thank you all for your valuable help
## Post #314
- Username: newhere4
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Mar 01, 2022 10:23 am
- Post datetime: 2022-03-01T02:27:30+00:00
- Post Title: Re: Horizon Zero Dawn

Hi, new here. Wondering how soon we can expect tools and models from the second game Forbidden West, thank you.
## Post #315
- Username: jimmy12345
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 06, 2021 12:24 pm
- Post datetime: 2022-03-01T04:18:47+00:00
- Post Title: Re: Horizon Zero Dawn

well, if you already bought it on steam you could try using the tool just to see if it works... who knows maybe we'll get lucky and if it works 
 if it doesn't work we'll have to wait to see if daemon1 surprises us with another tool.
## Post #316
- Username: newhere4
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Mar 01, 2022 10:23 am
- Post datetime: 2022-03-01T19:53:56+00:00
- Post Title: Re: Horizon Zero Dawn

Sadly Forbidden West won't be on Steam for at least a few years so I'm hoping Daemon can create some tools this year since the game is available on PS4, the models are fantastic and I really want older Aloy.
## Post #317
- Username: jimmy12345
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 06, 2021 12:24 pm
- Post datetime: 2022-03-02T22:45:49+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from newhere4 ↑Wed Mar 02, 2022 3:53 am at Wed Mar 02, 2022 3:53 am
>
> 
Sadly Forbidden West won't be on Steam for at least a few years so I'm hoping Daemon can create some tools this year since the game is available on PS4, the models are fantastic and I really want older Aloy.

well you can try to search the internet for the ps4 game and extract the files, to test if it works...
## Post #318
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-03-07T19:14:35+00:00
- Post Title: Re: Horizon Zero Dawn

Yes i'm kind of working on it. But the format is heavily changed, so i will need more time.
## Post #319
- Username: newhere4
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Mar 01, 2022 10:23 am
- Post datetime: 2022-03-07T22:17:22+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Tue Mar 08, 2022 3:14 am at Tue Mar 08, 2022 3:14 am
>
> 
Yes i'm kind of working on it. But the format is heavily changed, so i will need more time.

Thank you so much! I can't wait for the day these models can be ripped, you are hero to all of us!
## Post #320
- Username: pointytundra654
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 08, 2022 12:55 pm
- Post datetime: 2022-03-08T05:35:16+00:00
- Post Title: Re: Horizon Zero Dawn

so i did this 0. you need oo2core_5_win64.dll in the same folder with the tool
Its in almost any big game now, easy to find. Probably other versions will work too, if you rename them

1. you need to place the tool in your "packed_pink" horizon folder, or better, i recommend using included ini file (just change your folder). If you use this INI - you can use the tool from any folder.
Note: remove PATCH.BIN from the folder, or the tool will crash

2. first thing you need to extract is resource list.
To do this, just run the tool. It will create a text file list when i run the tool it is empty if i click on File and i select Packed_DX12 or LocalCacheDX12 it says no items match your search what am i doing wrong not very good at this the game is Horizon Zero Dawn
## Post #321
- Username: gzgtwz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 17, 2022 10:17 am
- Post datetime: 2022-03-08T09:37:21+00:00
- Post Title: Re: Horizon Zero Dawn

The smd format which is currently used with the extract tool seems not supporting the second uv channel, which is used to sample alpha channels in character's hair or furry parts on body. Is there a plan to deal with this?

====================

Found it in the ascii file generated by your great tool. I'll deal with it myself. Thanks again for this.
## Post #322
- Username: KukuruzkO
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 04, 2022 10:30 pm
- Post datetime: 2022-03-10T04:18:16+00:00
- Post Title: Re: Horizon Zero Dawn

Hello everyone
faced with such a problem:

Horizon_pc [mesh_skeleton] [animskel] > a.bat - does not work.
Perhaps someone knows how to find a solution to this problem?
## Post #323
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2022-03-10T21:31:19+00:00
- Post Title: Re: Horizon Zero Dawn

This awesome. Thanks so much for your work!

> Reply from daemon1 ↑Tue Mar 08, 2022 3:14 am at Tue Mar 08, 2022 3:14 am
>
> 
Yes i'm kind of working on it. But the format is heavily changed, so i will need more time.
## Post #324
- Username: Lampookie
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 01, 2022 7:46 am
- Post datetime: 2022-03-11T11:43:02+00:00
- Post Title: Re: Horizon Zero Dawn

Hey, If anyone could help me figure this conundrum out that would be great!

I have successfully extracted the 3d asset for the Longleg robot and attached all parts to a rigged skeleton.

However, there are a few texture questions I need to ask help with. I have extracted the textures from:
models/characters/robots/longlegbird/textures/longleg_set

I have 3 textures from this, named
longleg_set00_type_3_dx10.dds <--- Normal map
longleg_set01_type_1.dds <--- Albedo//diffuse whatever you wanna call it.
longleg_set02_type_132_dx10 <--- RGB masks

The RGB masks and albedo came out really good, however the normal map comes out really corrupted, no matter what program I use to open it. Ill attach pictures of it to give you an idea, ill 25% res them so its not as big too.

The masks I assume are for metallic and roughness but I'm not sure.

As for the Normal map, all other normals were exported from other sets just fine but this one has insanely low opacity and seams really corrupted. I have tried multiple conversion methods but I dont think that will mater since even the dds preview is the same.

TLDR: If someone could extract these correctly and give them to me that would solve my issue, also explaining what the rgb mask is for would be greatly appreciated
## Post #325
- Username: Lampookie
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 01, 2022 7:46 am
- Post datetime: 2022-03-11T20:33:26+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from KukuruzkO ↑Thu Mar 10, 2022 12:18 pm at Thu Mar 10, 2022 12:18 pm
>
> 
Hello everyone
faced with such a problem:

Horizon_pc [mesh_skeleton] [animskel] > a.bat - does not work.
Perhaps someone knows how to find a solution to this problem?

Some things to try are:
Try moving all the files including the horizon.exe files and your inital.bin and stuff into the same folder, if not try moving them all into another folder inside packed_pink.

If that doesnt work and its just not changing the files or creating an .animskel file then try pasting the commands in the original first post guide by Daemon1.

If you already have your .animskel file and wish to just merge the mesh and armature into a weighted .fbx you need to open the animskel file with a text viewer ie: notepad and copy everything inside. Then paste that whole block of text into your main mesh file, should be the largest .smd file you have, so at the top of the .smd file press enter to create a new line and ctrl + v.

Save that file and refresh your noesis viewer. It should be weighted, as for parts I honestly just manually export each one from noesis and import them as fbx into blender, line up the helper bone names with the mesh it corresponds to and move each mesh in object mode so you still see the origin point, line up that origin point to the crosshair of each helper bone. If you need more info on this feel free to dm me.
## Post #326
- Username: 92engineeringstacy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 16, 2022 10:17 pm
- Post datetime: 2022-03-16T14:20:50+00:00
- Post Title: Re: Horizon Zero Dawn

Has anyone had any luck with being able to extract the model for a FAS- Horus (Metal Devil)?
## Post #327
- Username: newhere4
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Mar 01, 2022 10:23 am
- Post datetime: 2022-03-16T15:21:35+00:00
- Post Title: Re: Horizon Zero Dawn

Forbidden West has a bunch of Horus around the map and Daemon is working on a tool for it, I think the first game only had one or two right? Might be worth to wait for the new tool.
## Post #328
- Username: 92engineeringstacy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 16, 2022 10:17 pm
- Post datetime: 2022-03-16T15:36:03+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from newhere4 ↑Wed Mar 16, 2022 11:21 pm at Wed Mar 16, 2022 11:21 pm
>
> 
Forbidden West has a bunch of Horus around the map and Daemon is working on a tool for it, I think the first game only had one or two right? Might be worth to wait for the new tool.

That is awesome news!  Yeah, there are definitely more in HFW.  I have just stumbled upon this forum and thread and got really excited that models could be extracted like this.  I will keep an eye on this thread and hope that way smarter person makes a tool that can manage that.  Thank you for the reply!
## Post #329
- Username: newhere4
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Mar 01, 2022 10:23 am
- Post datetime: 2022-03-16T16:27:32+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from 92engineeringstacy ↑Wed Mar 16, 2022 11:36 pm at Wed Mar 16, 2022 11:36 pm
>
> 
newhere4 wrote: ↑Wed Mar 16, 2022 11:21 pm
Forbidden West has a bunch of Horus around the map and Daemon is working on a tool for it, I think the first game only had one or two right? Might be worth to wait for the new tool.


That is awesome news!  Yeah, there are definitely more in HFW.  I have just stumbled upon this forum and thread and got really excited that models could be extracted like this.  I will keep an eye on this thread and hope that way smarter person makes a tool that can manage that.  Thank you for the reply!

I am sure Daemon can get us a tool to rip the models this year, he is fantastic!
## Post #330
- Username: Lampookie
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 01, 2022 7:46 am
- Post datetime: 2022-03-18T11:35:26+00:00
- Post Title: Re: Horizon Zero Dawn

I am double posting about this problem since I am still dealing with it and trying to chip some new info off every day.

How do I get the Longleg normal map out without it looking like ass? What is is about dx10 dds files that my computer or the tool doesnt like? Is anyone able to rip it for me and keep the normal map in tact?
## Post #331
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-03-18T15:37:46+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Lampookie ↑Fri Mar 18, 2022 7:35 pm at Fri Mar 18, 2022 7:35 pm
>
> 
I am double posting about this problem since I am still dealing with it and trying to chip some new info off every day.

How do I get the Longleg normal map out without it looking like ass? What is is about dx10 dds files that my computer or the tool doesnt like? Is anyone able to rip it for me and keep the normal map in tact?
Longleg normal map extracts correctly. People wont be able to help you if you dont describe what you did and whats wrong with that texture for you.
## Post #332
- Username: Lampookie
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 01, 2022 7:46 am
- Post datetime: 2022-03-19T17:38:42+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Fri Mar 18, 2022 11:37 pm at Fri Mar 18, 2022 11:37 pm
>
> 
Lampookie wrote: ↑Fri Mar 18, 2022 7:35 pm
I am double posting about this problem since I am still dealing with it and trying to chip some new info off every day.

How do I get the Longleg normal map out without it looking like ass? What is is about dx10 dds files that my computer or the tool doesnt like? Is anyone able to rip it for me and keep the normal map in tact?

Longleg normal map extracts correctly. People wont be able to help you if you dont describe what you did and whats wrong with that texture for you.

I already posted what I did and how the normal map came out, It is low opacity and very corrupted in both dds format and png. I even asked a friend to do it and he got the same result. Idk what you did to make that texture come out fine but what bothers me it that both me and my friend got the same results, 2 working textures but a broken normal map. Could you send me a link to download the normal map file for the longlegbird set please?
## Post #333
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-03-19T18:12:01+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Lampookie ↑Sun Mar 20, 2022 1:38 am at Sun Mar 20, 2022 1:38 am
>
> 
I already posted what I did and how the normal map came out, It is low opacity and very corrupted in both dds format and png. I even asked a friend to do it and he got the same result. Idk what you did to make that texture come out fine but what bothers me it that both me and my friend got the same results, 2 working textures but a broken normal map. Could you send me a link to download the normal map file for the longlegbird set please?
can you post a screenshot? corrupted how?
## Post #334
- Username: newhere4
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Mar 01, 2022 10:23 am
- Post datetime: 2022-03-20T03:27:00+00:00
- Post Title: Re: Horizon Zero Dawn

I get so excited every time I see this thread bumped haha
## Post #335
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-03-20T16:06:52+00:00
- Post Title: Re: Horizon Zero Dawn

I decided to make a new thread for forbidden west, because its so different, and will require another approach in almost everything.
Here is the link:

[viewtopic.php?f=16&t=25164](https://forum.xentax.com/viewtopic.php?f=16&t=25164)
## Post #336
- Username: lili2corne
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 18, 2022 3:07 pm
- Post datetime: 2022-03-26T15:54:39+00:00
- Post Title: Re: Horizon Zero Dawn

Hi,

thank you very much for this incredible tool!

I have however difficulty to understand how to have the model of a robot with all the destructible parts in 1 file (no animation or anything) for 3D printing

thank you !
## Post #337
- Username: Knichtus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 24, 2022 10:28 am
- Post datetime: 2022-03-29T20:48:59+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Wed Sep 30, 2020 2:11 pm at Wed Sep 30, 2020 2:11 pm
>
> 
Ok here's PC tool.

Usage is same as PS4. Someone said it doesnt work with oodle5, so i made it with oodle7, even though i think you can use other verisons renaming the .DLL as usual.

I checked a few models, textures and animations, they all look exactly same as on PS4. No quality difference.
So I dont know why files are 10GB bigger.

If anything will not work, let me know.

Hi! New here and wanted to use your tool but windows and my browser won't let me download it. Windows Defend keeps showing me that is has a trojan attached to it, just wanted to see if what its considering a 'Trojan' is just what is necessary for the tool to work or if a new version maybe needs to be uploaded:
## Post #338
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-03-30T02:00:35+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Knichtus ↑Wed Mar 30, 2022 4:48 am at Wed Mar 30, 2022 4:48 am
>
> ...just wanted to see if what its considering a 'Trojan' is just what is necessary for the tool to work...
[viewtopic.php?p=181233#p181233](https://forum.xentax.com/viewtopic.php?p=181233#p181233)
## Post #339
- Username: Lampookie
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 01, 2022 7:46 am
- Post datetime: 2022-03-30T06:51:45+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from daemon1 ↑Sun Mar 20, 2022 2:12 am at Sun Mar 20, 2022 2:12 am
>
> 
Lampookie wrote: ↑Sun Mar 20, 2022 1:38 am
I already posted what I did and how the normal map came out, It is low opacity and very corrupted in both dds format and png. I even asked a friend to do it and he got the same result. Idk what you did to make that texture come out fine but what bothers me it that both me and my friend got the same results, 2 working textures but a broken normal map. Could you send me a link to download the normal map file for the longlegbird set please?

can you post a screenshot? corrupted how?

Screenshot wont embed for some reason. I attached it to the last 2 messages, to explain it it looks like this [https://imgur.com/a/iIgmhlW](https://imgur.com/a/iIgmhlW)

I put a black background on because its really transparrent
## Post #340
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-03-30T07:09:26+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Lampookie ↑Wed Mar 30, 2022 2:51 pm at Wed Mar 30, 2022 2:51 pm
>
> 
Screenshot wont embed for some reason. I attached it to the last 2 messages, to explain it it looks like this https://imgur.com/a/iIgmhlW
I put a black background on because its really transparrent
ok it seems your conversion program is wrong. I can recommend using microsoft's Texconv.
## Post #341
- Username: foobs
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 28, 2022 10:05 am
- Post datetime: 2022-03-30T07:59:40+00:00
- Post Title: Re: Horizon Zero Dawn

Hey Daemon great program I really enjoy using it. 

I'm a PS4 user and everything seems to be focused on PC is there any chance you can help me import already meshed textures and files such as mods from Nexus mods back into a PS4 version of Horizon Zero Dawn. I made a few attempts already but they seem to not want to work or they come out pretty haphazard and crazy.
As in I'm looking at Aloy walk around looking like a porcupine. I'm trying to see if I can install the casual outfit look for alloy on my PS4 that's been jailbroken.

Second question I have can I use the pack dx12 file format create and install it into the PS4 version of the directory where the game is located place the files there like any other mod will that work as well or is that just a pipe dream that's used for steam type games only??

Any help would be really really appreciated
## Post #342
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-03-30T08:04:54+00:00
- Post Title: Re: Horizon Zero Dawn

You answered your question yourself. Its so much easier to do mods on PC, thats why almost nobody try it with PS4. I also have no time to experiment with this.
## Post #343
- Username: foobs
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 28, 2022 10:05 am
- Post datetime: 2022-03-30T08:09:25+00:00
- Post Title: Re: Horizon Zero Dawn

Okay thanks for the reply appreciate it.
## Post #344
- Username: lili2corne
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 18, 2022 3:07 pm
- Post datetime: 2022-05-03T16:26:18+00:00
- Post Title: Re: Horizon Zero Dawn

Hi, can you explain how to combine all parts destructibles in one file ? i have don't understand this part of this amazing work !

Thanks
## Post #345
- Username: mithkr67
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 08, 2022 10:51 pm
- Post datetime: 2022-07-08T16:18:39+00:00
- Post Title: Re: Horizon Zero Dawn

Any idea, why the 6 tail bones (see attached picture) are not connected to animation bones and therefore not follow the animation. The tail sticks to the same position when horse is moving.


Horse animation.jpg (240.13 KiB) Viewed 89 times
## Post #346
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-07-08T19:58:28+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from mithkr67 ↑Sat Jul 09, 2022 12:18 am at Sat Jul 09, 2022 12:18 am
>
> 
Any idea, why the 6 tail bones (see attached picture) are not connected to animation bones and therefore not follow the animation. The tail sticks to the same position when horse is moving.Horse animation.jpg
Those are physics bones if i remember correctly, only supported in-game during play, you must re-parent them to the main skeleton, in order to get them moved around with the actor, but they will still have no animation applied to them i think, i kind of forgot how that goes to be honest.
Unless you missed a step during setup?
## Post #347
- Username: Kyoon
- Rank: n00b
- Number of posts: 16
- Joined date: Mon May 03, 2021 6:45 am
- Post datetime: 2022-08-11T20:48:28+00:00
- Post Title: Re: Horizon Zero Dawn

I'm trying to extract voices from the PC version but it seems Decima-Explorer can't extract everything, is there any tool that can help extract sound/voices files from the .bin files?
## Post #348
- Username: Caia
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 03, 2021 3:40 am
- Post datetime: 2022-08-13T09:39:18+00:00
- Post Title: Re: Horizon Zero Dawn

Trying to extract the Tallneck.

I've followed the instructions up to the part where you have to 
"run <the tool> on template file <snip> So you have .animskel file".

No .animskel appears however, and I have no idea what's causing it to fail. The template file in question is comgiraffetemplate.core, if anyone could help I'd really appretiate it!
## Post #349
- Username: Blorbster
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Mar 24, 2018 11:33 pm
- Post datetime: 2022-08-28T00:18:20+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from oake ↑Fri Aug 12, 2022 4:48 am at Fri Aug 12, 2022 4:48 am
>
> 
I'm trying to extract voices from the PC version but it seems Decima-Explorer can't extract everything, is there any tool that can help extract sound/voices files from the .bin files?

I wrote some Python scripts to do this, you can get those [here](https://github.com/Bearborg/decima-scripts/tree/main/sentence_dumper).
## Post #350
- Username: Kyoon
- Rank: n00b
- Number of posts: 16
- Joined date: Mon May 03, 2021 6:45 am
- Post datetime: 2022-08-28T15:40:30+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Blorbster ↑Sun Aug 28, 2022 8:18 am at Sun Aug 28, 2022 8:18 am
>
> 
oake wrote: ↑Fri Aug 12, 2022 4:48 am
I'm trying to extract voices from the PC version but it seems Decima-Explorer can't extract everything, is there any tool that can help extract sound/voices files from the .bin files?


I wrote some Python scripts to do this, you can get those here.

Thanks, it helped extract the languages.bin files, but I can't extract the sounds with "sentence_dumper.py", they are all ".stream" files not ".core", sentence_dumper does nothing at all.
But it worked fine with a "wav scanner" script, sounds are working fine
## Post #351
- Username: Blorbster
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Mar 24, 2018 11:33 pm
- Post datetime: 2022-08-28T23:04:47+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from oake ↑Sun Aug 28, 2022 11:40 pm at Sun Aug 28, 2022 11:40 pm
>
> 
Blorbster wrote: ↑Sun Aug 28, 2022 8:18 am
oake wrote: ↑Fri Aug 12, 2022 4:48 am
I'm trying to extract voices from the PC version but it seems Decima-Explorer can't extract everything, is there any tool that can help extract sound/voices files from the .bin files?


I wrote some Python scripts to do this, you can get those here.


Thanks, it helped extract the languages.bin files, but I can't extract the sounds with "sentence_dumper.py", they are all ".stream" files not ".core", sentence_dumper does nothing at all.
But it worked fine with a "wav scanner" script, sounds are working fine

The .core files contain metadata (filenames, etc.) for the .stream files, and you should be able to extract the .cores normally with Decima Explorer without using the scripts. Glad it helped though!
## Post #352
- Username: Kyoon
- Rank: n00b
- Number of posts: 16
- Joined date: Mon May 03, 2021 6:45 am
- Post datetime: 2022-08-29T20:18:16+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Blorbster ↑Mon Aug 29, 2022 7:04 am at Mon Aug 29, 2022 7:04 am
>
> 
oake wrote: ↑Sun Aug 28, 2022 11:40 pm
Blorbster wrote: ↑Sun Aug 28, 2022 8:18 am


I wrote some Python scripts to do this, you can get those here.


Thanks, it helped extract the languages.bin files, but I can't extract the sounds with "sentence_dumper.py", they are all ".stream" files not ".core", sentence_dumper does nothing at all.
But it worked fine with a "wav scanner" script, sounds are working fine


The .core files contain metadata (filenames, etc.) for the .stream files, and you should be able to extract the .cores normally with Decima Explorer without using the scripts. Glad it helped though!

I mean there's no .core file at all in the 3 "language".bin and your scripts or Decima Explorer can't extract the .stream files (or I didn't find how)
But I still succeeded in extracting them, that's the main point. Unfortunately all sounds in .stream files have no "name" having thousands of sounds from Aloy without knowing what is what is kind of painful, but at least it's kind of well organized contrary to some games like Assassin's Creed

Edit: I totally forgot about the .core extracted from the main .bin files. Is it possible to extract the .stream using the .core file and getting names from each sound in the .stream file?
## Post #353
- Username: voidrayer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 30, 2022 8:04 am
- Post datetime: 2022-08-30T01:22:38+00:00
- Post Title: Re: Horizon Zero Dawn

Hello I'm attempting to extract the model and textures of Aloy's spear and war bow. What directory are they located in?
## Post #354
- Username: Blorbster
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Mar 24, 2018 11:33 pm
- Post datetime: 2022-08-30T16:29:11+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from oake ↑Tue Aug 30, 2022 4:18 am at Tue Aug 30, 2022 4:18 am
>
> 
Edit: I totally forgot about the .core extracted from the main .bin files. Is it possible to extract the .stream using the .core file and getting names from each sound in the .stream file?

Yep, that's what sentence_dumper.py does. If you have the .core files extracted from the main .bins in the same folder as their matching .streams, you should just need to run sentence_dumper on the .core and it will locate the .streams automatically and dump from them.
## Post #355
- Username: Kyoon
- Rank: n00b
- Number of posts: 16
- Joined date: Mon May 03, 2021 6:45 am
- Post datetime: 2022-08-31T01:22:32+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Blorbster ↑Wed Aug 31, 2022 12:29 am at Wed Aug 31, 2022 12:29 am
>
> 
oake wrote: ↑Tue Aug 30, 2022 4:18 am
Edit: I totally forgot about the .core extracted from the main .bin files. Is it possible to extract the .stream using the .core file and getting names from each sound in the .stream file?


Yep, that's what sentence_dumper.py does. If you have the .core files extracted from the main .bins in the same folder as their matching .streams, you should just need to run sentence_dumper on the .core and it will locate the .streams automatically and dump from them.

It didn't work for me when I tried so I thought it wasn't possible, but I understood why it didn't work. I chose a different "hzd_root_path" because I just wanted to extract the voices separately and it messed up everything with the script
Sounds with name is a blessing, thank you. Too bad there're many games where it's not possible
## Post #356
- Username: victortrifan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 24, 2022 8:52 pm
- Post datetime: 2022-09-28T15:35:17+00:00
- Post Title: Re: Horizon Zero Dawn

> Reply from Juanrc ↑Mon Feb 21, 2022 11:23 am at Mon Feb 21, 2022 11:23 am
>
> 
HowdyNeighbor wrote: ↑Mon Feb 14, 2022 6:52 am
Howdy, forum lurker here.  Stumbled upon this tool a couple of months ago with the goal of generating 3D-printable meshes for personal use, ideally in poses according to exciting "action stances" from animation files.

I've worked via trial & error through everything up to just after daemon's Step 4:
daemon1 wrote: ↑Tue Feb 20, 2018 4:33 am

Is there a solution to this magnificent topic? Thank you kindly!

step 4:
Open A.BAT file, and replace all "_helper" strings with ".core". This probably could be done automatically on export, but the thing is, I'm not sure all helper bones will always be called the same as helper MESHES. So I'm leaving this to the users at least for now.
Run this .BAT file.


I'm working with the horse/Strider model right now and have a folder full of extracted ascii and smd files for the body part, 24 "plate/eye" parts, and the canister_fuel part.  I've also successfully generated the a.bat and mesh_skeleton_rootbone.core.ascii and mesh_skeleton_rootbone.core.smd files from Step 3--they have nonzero file sizes.  I replaced "_helper" strings with ".core" for all 24 items listed in the a.bat file, as in Step 4.  Note that the fuel canister is missing from the a.bat list. How does that get placed and weighted to the model?


Running the a.bat file updates the mesh_skeleton_rootbone.core.ascii and .smd files.  I am now confused by the following directions:
daemon1 wrote: ↑Tue Feb 20, 2018 4:33 am

to load all destructible parts as one file:
========================================================
Merge all ASCII files into one as text file, then copypaste skeleton into it.
Then count submeshes (it will correspond to number of "material" string)
and put a number of submeshes after the skeleton (before all the actual data).
This number will correspond to number of "material" string in all files.
Same for SMD files, just no need to count submeshes.

Which ASCII files are getting merged, and should the combined file still be another ASCII file (or is just .txt okay)?  Are the prior 25 part's ASCIIs just merged e.g., by using "copy [A]+[ B]+[C] [outputABC]" in the command prompt?  Does the entire content of the mesh_skeleton_rootbone.core.ascii file get pasted to the beginning of this new merged file?  Do any lines need to be deleted like we did when combining the mesh and skeleton smd files from a simple animal model?

What is meant by
daemon1 wrote: ↑Tue Feb 20, 2018 4:33 am

and put a number of submeshes after the skeleton (before all the actual data).
This number will correspond to number of "material" string in all files.


I count the string "material" 31 times if I merge ASCIIs and paste the mesh_skeleton_rootbone.core.ascii text to a combined file as I asked about above.  What is the exact text I need to enter after the text copied from the mesh_skeleton_rootbone.core.ascii file to represent this 31 submesh number?

Next, I assume the SMD merging is the same as for simple animal models, in that we'll copy the text from mesh_skeleton_rootbone.core.smd and paste it to the beginning of a combined mesh smd file, being sure to delete "version 1" and "nodes".  Will that combined mesh file also be a merger of all 25 part's SMD files, or do any other problematic lines need to be deleted too?

If I can accomplish this much, will that final combined SMD file display correctly as a complete model in Noesis--body, removable parts, and skeleton?  Does the program somehow distinguish between the core body and removable parts as seen in Daemon1's video https://www.youtube.com/watch?v=rsbwOuqor3c?  or will it interpret it as one mesh piece?

Lastly, why does the ascii file need to be merged if we're only opening an smd file for exporting a mesh model?

-----------------------------------
Appreciate all of the work you all have done.  Glad to see some friendly, repeating helpers on here too.  I don't have any programming experience, but I work with technical writing and have written up detailed directions for how I've gotten this far.  If I can accomplish these last conversion steps and then figure out animation extraction, I'd be happy to share my SOP with the forum.  Perhaps it would help solve the most common "stuck. Help!?" questions.

Cheers y'all!


That would be great, I am stuck after extracting the models, also there are a lot of robots wuth no mesh_skeleton_rootbone and only have skeleton_rootbone, already managed to import the mesh files to blender, but the destructible ones dont import at the desired location but at the origin (0,0). any help would be great
## Post #357
- Username: ninetalescommander
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Aug 14, 2018 8:02 am
- Post datetime: 2022-10-07T00:28:21+00:00
- Post Title: Re: Horizon Zero Dawn

I'm really stuck; Basically I've managed to get the .core files and I'm able to use the tool to get the SMD files. My problem is actually exporting them in a combined format.
I've tried dragging and dropping the .core files into both Horizon and Horizon_PC but no matter what, they just remain separated. Am I supposed to use a command prompt? Or is there something wrong I'm doing? I have managed to get the "Matrices" file to appear but from there, the guide is abit vague on exactly how it's done.

Any help?
## Post #358
- Username: JP111555
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 28, 2022 10:31 pm
- Post datetime: 2022-11-01T23:50:27+00:00
- Post Title: Re: Horizon Zero Dawn

Ight, I have been trying to extract the full Thunderjaw rig from Horizon Zero Dawn with all the plates using the Daemon tool. However, whenever I do this the helper bones are always messed up thus prohibiting me from actually putting any plates on the rig. I have been doing this for a while now and have ended up merging all the part smd files and ascill files but to no avail. At this point any help is really appreciated. I have been asking around about this but really haven't gotten any answers. I really want to make this work, biggest thing that I may be doing wrong is the file merging but at this point I have 0 clue.
[Screenshot 2022-11-01 194912.jpg](https://xentaxbackup.github.io/file/22988_Screenshot 2022-11-01 194912.jpg)
## Post #359
- Username: bhuvahh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 07, 2022 6:09 pm
- Post datetime: 2022-11-07T10:22:01+00:00
- Post Title: Re: Horizon Zero Dawn

I really don't want to get on anyone's nerves here, least of all appear ungrateful. But are there any news concerning the extraction of the voice-files?

charter spectrum login

attwifimanager
## Post #360
- Username: grawiorum
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 05, 2017 1:09 am
- Post datetime: 2022-12-18T06:45:15+00:00
- Post Title: Re: Horizon Zero Dawn

Получилось 
blender-2.79

[https://mega.nz/folder/RRgUnKDK#wibUwyOycmD6qJXCrYrBSA](https://mega.nz/folder/RRgUnKDK#wibUwyOycmD6qJXCrYrBSA)

Инструкция на Русском
[https://mega.nz/file/gVwmmYRS#SVb0P_wB9 ... c_ARdrqyss](https://mega.nz/file/gVwmmYRS#SVb0P_wB9OEGTaG4NHqm-OJoVXhpO4dtAc_ARdrqyss)
[1671311197.grawiorum_untitled.jpg](https://xentaxbackup.github.io/file/23141_1671311197.grawiorum_untitled.jpg)
## Post #361
- Username: soopytwist
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 02, 2017 1:58 am
- Post datetime: 2023-04-22T20:07:42+00:00
- Post Title: Re: Horizon Zero Dawn

Anyone care to explain what's happening here?
[https://imgur.com/YZJunno](https://imgur.com/YZJunno)
## Post #362
- Username: guiltytrace
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2020 11:18 am
- Post datetime: 2023-05-10T23:50:11+00:00
- Post Title: Re: Horizon Zero Dawn

I understand the same or a similar process should work with Death Stranding (PC), but I'm surprised no one is talking about that more--here or anywhere, for that matter.

In my DS root folder, I have oo2core_7_win64.dll, the ds.exe, the bink and compiler .dll's; and the binaries are kept in \data. Jayveer's Decima Explorer allows file browsing and extraction, but as you guessed, everything extracted is .core. I've hoped the Explorer would bypass the text document/batch file requirement demonstrated in that YouTube tute, but dragging anything to horizon_pc.exe results in Unexpected Pack Size and Unexpected Pack Offset errors in command prompt. Do I have to do the text/batch file steps after all?
## Post #363
- Username: squishypawb
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 11, 2023 6:45 am
- Post datetime: 2023-09-12T01:25:25+00:00
- Post Title: Re: Horizon Zero Dawn

Hi,
Stumbled upon this forum post recently while looking for ways to extract models from HZD. I'm somewhat new to 3D modeling and programming.
I recently downloaded the version of Horizon.exe from [viewtopic.php?p=151411#p151411](https://forum.xentax.com/viewtopic.php?p=151411#p151411). I decompressed the .rar and placed Horizon.exe in a separate folder with copies of DLC1.bin, Initial.bin, Remainder.bin, and oo2core_5_win64.dll, as instructed. The DLC1.bin, Initial.bin, and Remainder.bin were acquired from the Complete Edition installed through Steam.
I followed steps 1-5 of extracting files from the .bins. I now have some .core files extracted for Aloy. Specifically, I have the following files:
models/characters/humans/aloy/animation/modelpartresource
models/characters/humans/aloy/animation/skeletons/mesh_skeleton_rootbone
models/characters/humans/aloynoraarmourcostume/animation/modelpartresource
models/characters/humans/aloynoraarmourcostume/animation/parts/neckscar_fresh_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/neckscar_healed_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/seekermark_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/skeletons/mesh_skeleton_rootbone
models/characters/humans/baseparts/aloyneckscar/textures/aloyneckscar_fresh_set
models/characters/humans/baseparts/aloyneckscar/textures/aloyneckscar_old_set
models/characters/humans/heads/female/aloy/animation/skeletons/skeleton_c_spine_sjnt_4
models/characters/humans/aloy/animation/skeletons/skeleton_rootbone_helpers
models/characters/humans/hair/aloy/textures/aloy_hair_base_set00
models/characters/humans/hair/aloy/textures/aloy_hair_set00
models/characters/humans/heads/female/aloy/textures/aloy_eyebrows_set
models/characters/humans/heads/female/aloy/textures/aloy_eyelashes_set
models/characters/humans/heads/female/hannah/textures/aloyheadcap_set
models/characters/humans/heads/female/aloy/animation/animations/eyeclosed
models/characters/humans/hair/aloy/model/aloysimmaterial
models/characters/humans/hair/aloy/model/model
models/characters/humans/hair/aloy/textures/temp/aloy_hair_bead_set
shaders/character/textures/specular_ramp_aloytrail
models/characters/humans/aloy/animation/parts/aloy_ct_a_lx
models/characters/humans/aloy/animation/parts/aloyhair_ct_a_lx
models/characters/humans/aloy/animation/parts/skirtflapa_ct_a_lx
models/characters/humans/aloy/animation/parts/skirtflapc_ct_a_lx
models/characters/humans/aloy/animation/parts/skirtflapd_ct_a_lx
models/characters/humans/aloy/animation/parts/skirtflape_ct_a_lx
models/characters/humans/aloy/animation/parts/skirtflapf_ct_a_lx
models/characters/humans/aloy/animation/parts/skirtflapg_ct_a_lx
models/characters/humans/aloy/animation/partsets
models/characters/humans/aloy/animation/skeletons/mesh_skeleton_rootbone_posedeformer
models/characters/humans/aloy/textures/aloy_carbonfibreweave_set
models/characters/humans/aloy/textures/aloy_set
models/characters/humans/aloynoraarmourcostume/textures/aloyna/aloynatilling_set
models/characters/humans/aloynoraarmourcostume/textures/aloynabags/aloynabags_set
models/characters/humans/aloy/animation/character
models/characters/humans/hair/aloy/textures/aloy_hair_base_set
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyhair_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyna_armguard_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyna_bags_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyna_base_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyna_bracerbase_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyna_bracerhigh_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyna_chestplate_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyna_discheadband_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyna_glove_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyna_highfurshawl_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyna_kneepads_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyna_midponcho_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyna_plateheadband_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyna_quiver_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyna_skirt_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/parts/aloyna_skirtplates_ct_a_lx
models/characters/humans/aloynoraarmourcostume/animation/partsets
models/characters/humans/aloynoraarmourcostume/animation/skeletons/mayagraph
models/characters/humans/aloynoraarmourcostume/animation/skeletons/mesh_skeleton_rootbone_posedeformer
models/characters/humans/aloynoraarmourcostume/textures/aloyna/aloyna_set
models/characters/humans/aloynoraarmourcostume/textures/aloynaheadband/aloynaheadband_set

I moved all of the files to the same folder containing Horizon.exe and the .bin files listed previously. However, drag-and-dropping the flies on Horizon.exe produces no output, no .ascii files, no .smd files, and no "matrices" files. I also tried running the command "Horizon.exe [FileNameHere.core]" in a command terminal, but there was also no output, no .ascii files, no .smd files, and no "matrices" file.
When I ran the command and passed one of the "mesh_skeleton_rootbone.core" files in as input, Horizon.exe successfully produces a .ascii and .smd file. However, when I opened the .smd file in a notepad, a lot of the values in the file were set to zero.
I also attempted to download Horizon_pc.7z from [viewtopic.php?p=167228#p167228](https://forum.xentax.com/viewtopic.php?p=167228#p167228), but doing so causes both Chrome and Windows 10 to flag it as a "virus" and stop the download. I downloaded it through Mozilla as a workaround, but attempting to decompress the file results in 7Zip returning an error claiming that there is a virus inside. As a result, I am currently only able to work with Horizon.exe.
I'm not sure where to go from my current state. I'm genuinely at a loss, and would really appreciate some help.
## Post #364
- Username: 90SK
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 19, 2023 5:51 am
- Post datetime: 2023-09-18T23:08:30+00:00
- Post Title: Re: Horizon Zero Dawn

PAGE17: 

> Reply from daemon1 ↑Wed Sep 30, 2020 2:11 pm at Wed Sep 30, 2020 2:11 pm
>
> 
Ok here's PC tool.

Usage is same as PS4. Someone said it doesnt work with oodle5, so i made it with oodle7, even though i think you can use other verisons renaming the .DLL as usual.

I checked a few models, textures and animations, they all look exactly same as on PS4. No quality difference.
So I dont know why files are 10GB bigger.

If anything will not work, let me know.

^ This archive has a virus now, looks like.
I believe this tool is a step in part of the research to make retexture mods for Horizon Zero Dawn.

Research So Far on Horizon Zero Dawn retexturing:

STEP 1.

Texture Explorer Program:

https://visualstudio.microsoft.com/downloads/
^ This link will give Microsoft Visual Studio 2022 Community Edition. It will allow you to access the HzD Texture Explorer Below.

STEP 2.

> HzDTextureExplorer. Texture Explorer for Horizon Zero Dawn files. Can view Textures in a HzD core file, export as dds, and reimport dds. Uses Pfim and ImageSharp. Features. Open HzD core files containing textures and preview them. You can also drop a core file on the program to open it; Export textures to dds

https://github.com/torandi/HzDTextureEx ... SnippetTab

^ If you're unclear on how to download this, click the green button that says "Code" on the right and click "Download ZIP" in its menu.
Microsoft Visual Studio will be needed to run the Texture Explorer
If it doesn't work in Visual Studio, try installing this:
https://dotnet.microsoft.com/en-us/download/dotnet/7.0

^ This is the step I'm stuck on. (EDIT: The needed program is Blender, not Visual Studio)


STEP 3.
Graphics Program: 

GIMP 2.10.22 , a Linux Graphic Editing Program cross-compatible with Windows all versions:
https://www.gimp.org/downloads/
https://itechhacks.com/install-dds-plugin-for-gimp/

^ With this, you can edit the textures. Leave the .dds files uncompressed when exporting.

10/2/23

To import/export textures from Horizon Zero Dawn, you can use the HZDMeshTool. This is a Blender addon that allows you to import and export textures from Horizon Zero Dawn’s .core format 12.

Here are the steps to install and use the tool:

Download the HZDMeshTool from GitHub.
In Blender, open the User Preferences and go to the Add-ons tab.
Click on Install and select the HZDMeshTool.zip file.
Enable the addon.
Go to the Scene Properties tab.
As of version 1.3, you can extract textures from the game files by enabling the Extract Texture checkbox in the tool 1. If enabled, the tool will extract every texture used by the imported mesh part to the Workspace directory. You can click the checkered icon next to the mesh import button to see the textures used 1.
I hope this helps!
