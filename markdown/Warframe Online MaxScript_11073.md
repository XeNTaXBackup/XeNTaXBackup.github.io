## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-12-23T12:22:48+00:00
- Post Title: Warframe Online MaxScript

Here is a MMO Warframe import script for 3ds Max.
Site: [https://warframe.com](https://warframe.com)
Supported:
Geometry
UV's
Bones+Weights
Not Supported:
Textures
Materials

Here's tool by GMMan [viewtopic.php?f=32&t=10782](http://forum.xentax.com/viewtopic.php?f=32&t=10782) to extract game content from .cache archives

B.Misc.cache - all models
H.Misc.cache - all reference files for models (small files with same name as model files, they should be imported first, then model files)


[Warframe.7z](https://xentaxbackup.github.io/file/6872_Warframe.7z)
## Post #2
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2013-12-23T14:30:57+00:00
- Post Title: Warframe Online MaxScript

Thank you ,really great work! 

Also the animations are really good..but i suppose that obtaining them will remain a dream.

Anyway if u need some sample of dds hd res texures ripped from the game , to compare with these strange .pngs let me know.
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-12-30T11:05:32+00:00
- Post Title: Warframe Online MaxScript

Hi Ares722, have you managed to import models with my script? Did you try it already?
## Post #4
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2013-12-30T16:47:59+00:00
- Post Title: Warframe Online MaxScript

> Reply from zaramot
>
> Hi Ares722, have you managed to import models with my script? Did you try it already?

Yes, I needed a bit of time to associate the two files (model file + reference file) to all the files, anyway the scipt seems work quite well. 
Exept some extra bones,which don't seem connected to the skin weights, all works nicely.

I tried with some models from an old backup of the closed beta and the udated version, and the script works as well.



I will test more files soon. 
Thank you again for the script
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-12-30T19:03:37+00:00
- Post Title: Warframe Online MaxScript

Glad to hear it work fine for you.
## Post #6
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2013-12-31T22:00:54+00:00
- Post Title: Warframe Online MaxScript

I am a bit confused with this script.
For example i am trying to load the ember model, i found it in Lotus>Characters>Tenno>Ember and i can easily load the bones, but how can i load the models? I used the other script but it didnt work on any of them. I know they are named _skel, but i cant find any other model for the ember, except from in that folder D:
Any help would be appreciated, i may have missed something.
Thanks.
## Post #7
- Username: KFK
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 06, 2010 4:46 am
- Post datetime: 2014-01-05T03:21:42+00:00
- Post Title: Warframe Online MaxScript

I get the following error when trying to import the supplied test files in Max 2014 x64.

```
--  Frame:
--   NameSize: undefined
--   x: 2
--   called in x loop; filename: C:\tools\max\3ds Max 2014\scripts\Warframe.ms; position: 3444; line: 146
--  Frame:
--   count: 1634885992
--   longCount: 1191182336
--   x: 1
--   called in i loop; filename: C:\tools\max\3ds Max 2014\scripts\Warframe.ms; position: 3472; line: 148
--  Frame:
--   Mcount: 0
--   i: 1
-- Error occurred during fileIn in #C:\tools\max\3ds Max 2014\scripts\Warframe.ms; line number: 144
>> MAXScript FileIn Exception:
-- Unable to convert: undefined to type: Integer64 <<
```
## Post #8
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-01-05T09:56:12+00:00
- Post Title: Warframe Online MaxScript

Hi KFK, script wouldn't work for max 2014 x64, try max 2009-2012. I'm planning to update script to fix some lines, will try to fix this but no promises, sorry.

TRDaz, after you imported bones with Warframe_bones.ms, you should run Warframe.ms script and again pick small file from H.Misc then choose bigger file from B.Misc (use same files you imported bones from)
## Post #9
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2014-01-05T23:10:00+00:00
- Post Title: Warframe Online MaxScript

I tested your script with some other files.

It seems not work with grineers mask , wepons and levels. So i suppose it doesn't support static meshes yet.

Instead the tested characters/enemies and their bodyparts ( with a weight skin) work fine.
## Post #10
- Username: ineteye
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 09, 2008 8:41 pm
- Post datetime: 2014-01-10T09:05:57+00:00
- Post Title: Warframe Online MaxScript

Hi!

Getting Error with "-- Unable to convert: undefined to type: Integer" both on max 2012 and 2010, WarFrames.ms ..... ???
[error.png](https://xentaxbackup.github.io/file/6913_error.png)
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-01-16T14:00:13+00:00
- Post Title: Warframe Online MaxScript

Hi everyone. I fixed some lines in my script, I think it should solve some issues. I will try to optimize it better, when I finish with other games on evolution engine 


[Script.7z](https://xentaxbackup.github.io/file/6921_Script.7z)
## Post #12
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2014-01-27T22:55:04+00:00
- Post Title: Warframe Online MaxScript

Nice going, just wanted to post a quick tutorial because I could not get it to work first:

1. Load Warframe_Bones.ms
2. Point it to a H.misc.cache file like Inugami_skel.fbx
3. A new dialogue shows up, this time choose Inugami_skel.fbx in B.misc.cache
Bones will be loaded

4. Load Warframe_Online.ms
5. Point it to H.misc.cache file Inugami_skel.fbx
6. A new dialogue shows up, this time choose Inugami_skel.fbx in B.misc.cache
Model will be loaded above bones

Done

Thanks for the effort with this script
## Post #13
- Username: EpicCG
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 23, 2014 4:34 am
- Post datetime: 2014-02-23T05:33:33+00:00
- Post Title: Warframe Online MaxScript

I can get the models and bones loaded into 3DSMax 2014 just fine, however, I can't seem to figure out how Ares722 loaded the details (textures) from his screenshots. Anyone successful with this?

Ares722?
## Post #14
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2014-02-23T15:26:55+00:00
- Post Title: Warframe Online MaxScript

textures are probably ripped with 3d ripper or something
## Post #15
- Username: wjh12338093
- Rank: beginner
- Number of posts: 20
- Joined date: Thu May 01, 2014 9:12 pm
- Post datetime: 2014-05-02T08:44:13+00:00
- Post Title: Warframe Online MaxScript

Excuse me, how can get textures, extract the PNG images。
## Post #16
- Username: wjh12338093
- Rank: beginner
- Number of posts: 20
- Joined date: Thu May 01, 2014 9:12 pm
- Post datetime: 2014-05-05T01:11:59+00:00
- Post Title: Re: Warframe Online MaxScript

Excuse me character models in that folder, can not find ah。

Poor English
## Post #17
- Username: wjh12338093
- Rank: beginner
- Number of posts: 20
- Joined date: Thu May 01, 2014 9:12 pm
- Post datetime: 2014-05-06T05:47:02+00:00
- Post Title: Re: Warframe Online MaxScript

Thank you for the script, it's very good.Thank you very much!
## Post #18
- Username: Biohazardez
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 20, 2014 5:29 am
- Post datetime: 2014-05-16T18:03:49+00:00
- Post Title: Re: Warframe Online MaxScript

this is how you use ninjaripper with warframe.

1. you need to use the warframe.exe in the installation folder (not the launcher.exe or the 64bit version)
(if your using steam it in here ''Steam/steamapps/common/warframe'' )

2. use these arguments ''-cluster:public -fullscreen:0 -dx11:1'' (without '')
if you want to run directx9, use ''-dx11:0''

3. use either ''D3D11 wrapper'' or ''D3D9'' wrapper depending on either you use DirectX 9 or 11

4. just click Run and wait for warframe to launch
(NOTE) if you get blackscreen after it finished loading it means you use the wrong warframe.exe (use the one inside the Public folder if it exists)

5. start ripping & be happy
## Post #19
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2014-05-20T20:22:25+00:00
- Post Title: Re: Warframe Online MaxScript

Cool! I once got banned for using something in the game. Have you experienced anything? I have to much invested in this game to be banned
## Post #20
- Username: Biohazardez
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 20, 2014 5:29 am
- Post datetime: 2014-05-23T06:44:34+00:00
- Post Title: Re: Warframe Online MaxScript

as far as I know you won't be banned for using ninjaripper.

I haven't been banned yet, so if no one else reports about getting a ban from using it, you shouldn't have to worry
## Post #21
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2014-06-06T15:26:38+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from Biohazardez
>
> as far as I know you won't be banned for using ninjaripper.

I haven't been banned yet, so if no one else reports about getting a ban from using it, you shouldn't have to worry

Well I have tried all settings I can now with both exe version and switching between dx11 and dx9 etc. Even went in launcher preferences and changed settings there with multi-thread etc but I dont get any rips. In one of the settings the game freezes for a while but it does not generate either textures nor scene
## Post #22
- Username: MikaKyubi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Sep 20, 2013 10:06 pm
- Post datetime: 2014-09-09T20:30:45+00:00
- Post Title: Re: Warframe Online MaxScript

As to the matter of successfully using NinjaRipper to rip the models and the textures, I've had success with the following:

1) Point NinjaRipper to the Warframe.exe location.  Set it to rip using DirectX 9.

2) Attempt to run it.  You will get an error stating to run Warframe through the launcher.  This is fine.

3) Quit NinjaRipper

4) Load the launcher.  In the launcher, under options, make sure Full Screen is checked, but do not check 64-bit Mode, nor DirectX 10 or DirectX 11 (You want to make it run in DirectX 9 mode for this).

5) Load up NinjaRipper at this point.

6) From the Warframe Launcher, run the game.

7) Find the weapon or Warframe model you intend to rip.  You can either go to your Clan's Dojo, or go into the Codex on your ship

 Use the NinjaRipper hot keys to rip your scene.

9) Your screen will now be black.  Prior to update 14, you could alt-enter to run in a window.  Now this is impossible.  Press Alt-f4 to quit the game on the spot.

10) At this point you can load up 3DStudio Max and point it to the ripped folder.  Be advised, the textures might be flipped, and this can cause texturing problems.

11) I use Noesis at this point and convert to .obj file format, flipping the UV.  I also convert the .dds file into .tga format.

12) All textures ripped in this method need the following done to them to make them usable in any other program:

  a) Diffuse, Specular, and Illumination maps need to have their brightness increased by 100%
  b) Normal maps require their brightness to be increased by 140%

Repeat this procedure as required.

I hope that this information helps.

Sincerely,
Mika Kyubi
## Post #23
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2014-11-06T23:05:35+00:00
- Post Title: Re: Warframe Online MaxScript

Out of curiosity - have you thought about making the script support other evolution engine games as well? Star trek 2013, Dark sector etc.
## Post #24
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-11-07T11:10:47+00:00
- Post Title: Re: Warframe Online MaxScript

Star Trek 2013 - [viewtopic.php?f=16&t=11413&hilit=Star+trek](http://forum.xentax.com/viewtopic.php?f=16&t=11413&hilit=Star+trek)
Dark Sector - [viewtopic.php?f=16&t=11897&hilit=dark+sector](http://forum.xentax.com/viewtopic.php?f=16&t=11897&hilit=dark+sector)
## Post #25
- Username: LogicalEvil
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 16, 2014 1:37 pm
- Post datetime: 2015-01-19T18:14:44+00:00
- Post Title: Re: Warframe Online MaxScript

I'm sorry if this is bumping an old thread, but I've been running into problems using the warframe_online import script. Bones import fine, but when trying to import geometry, it all gets scrunched into a triangle. This is the result of importing Excalibur_skel.fbx
## Post #26
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-01-21T08:49:38+00:00
- Post Title: Re: Warframe Online MaxScript

What tool you used to extract archives? Also, I guess you're using latest game client? If so, it could be, that developers changed format a bit.
## Post #27
- Username: LogicalEvil
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 16, 2014 1:37 pm
- Post datetime: 2015-01-21T12:47:26+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from zaramot
>
> What tool you used to extract archives? Also, I guess you're using latest game client? If so, it could be, that developers changed format a bit.

I used [blog/?p=1081](http://forum.xentax.com/blog/?p=1081) to extract the cache, I also tried importing with both 3ds max 2009 and 2010. I'll attach the models I tried importing.
[Excal.zip](https://xentaxbackup.github.io/file/8532_Excal.zip)
## Post #28
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-01-21T14:12:49+00:00
- Post Title: Re: Warframe Online MaxScript

They changed model format a bit. Here's new script, could cause errors with other models (since, they could change format more)


[Warframe.7z](https://xentaxbackup.github.io/file/8533_Warframe.7z)
## Post #29
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-01-22T19:10:36+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from zaramot
>
> They changed model format a bit. Here's new script, could cause errors with other models (since, they could change format more)Thank you very much for the great work, the script runs very well, but how to extract the texture? Request for help
## Post #30
- Username: Basurci
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 24, 2014 6:26 am
- Post datetime: 2015-02-06T02:21:23+00:00
- Post Title: Re: Warframe Online MaxScript

Hello, update is needed for this script 
Today after new update in warframe some of player model parts are impossible import because of some error.
It's being thrown on this line "str += bit.intAsChar (ReadByte bstream #unsigned) "
I attached sample for it.
Btw any ideas how to import textures with models? I mean for those models that are still unavailable in-game to see.



Any updates coming soon?
[volt.rar](https://xentaxbackup.github.io/file/8612_volt.rar)
## Post #31
- Username: Hive17
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 19, 2014 2:07 am
- Post datetime: 2015-04-02T08:50:21+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from zaramot
>
> They changed model format a bit. Here's new script, could cause errors with other models (since, they could change format more)

The new version of the script breaks UV coordinates. Please, fix it)
## Post #32
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-04-02T10:08:04+00:00
- Post Title: Re: Warframe Online MaxScript

Send me samples of new models, with broken UV's please
## Post #33
- Username: Hive17
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 19, 2014 2:07 am
- Post datetime: 2015-04-02T13:37:16+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from zaramot
>
> Send me samples of new models, with broken UV's please
[Valkyr.rar](https://xentaxbackup.github.io/file/8927_Valkyr.rar)
## Post #34
- Username: HBOSS81
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 22, 2015 9:48 am
- Post datetime: 2015-09-24T00:42:40+00:00
- Post Title: Re: Warframe Online MaxScript

Hey, great scripts! I've managed to successfully get the skeleton's & mesh's for several frames (Umbra included), yet on the "extras" for the loincloth/scarf bones, it seems to have missing bones and bad bone positioning for the correct location of the front/back scarf & world coordinates of said items in its rig. I too, get the broken/unsigned error when i try to load the bones/meshes for the crest item you find in the cloth folder. Also, is it no longer possible to load the textures through the existing scripts you have on here? i get the meshes with no materials by default. just the solid colored versions.
## Post #35
- Username: antoineflemming
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 01, 2014 11:50 am
- Post datetime: 2015-10-23T04:20:28+00:00
- Post Title: Re: Warframe Online MaxScript

So, for a while now I haven't been able to import any Warframe model using The WarframeOnline MaxScript. For those who have been successful, what script are you using and how are you getting it to work?
## Post #36
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-10-23T10:09:20+00:00
- Post Title: Re: Warframe Online MaxScript

For sure, number of updates changed model format, so script wouldn't work with latest version of the game.
## Post #37
- Username: DonacDum
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 29, 2015 1:38 am
- Post datetime: 2015-10-28T17:44:22+00:00
- Post Title: Re: Warframe Online MaxScript

I apologise if I'm bumping an old thread, but whenever I try to run it with Ninja Ripper while using these settings ( -cluster:public -fullscreen:0 -dx11:0) , it says that it is unable to find the PhysX libraries/that I did not install the PhysX drivers correctly.
## Post #38
- Username: xbeton0L
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Dec 16, 2011 10:40 pm
- Post datetime: 2015-12-02T03:54:29+00:00
- Post Title: Re: Warframe Online MaxScript

NinjaRipper aside, good work on the importer. I have a question though. Is it possible to read texture data from the Dx9.cache files so we can bring them into max?

So far I've gotten a bunch of png files and I don't know what to try next. Anyways, I've attached a sample file. Hope it's of some use.
I have the rest of the files from the Tenno folder if you need them.
[ExcaliburMk1_d.7z](https://xentaxbackup.github.io/file/10095_ExcaliburMk1_d.7z)
## Post #39
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2015-12-11T23:27:15+00:00
- Post Title: Re: Warframe Online MaxScript

any chance to support animation?
## Post #40
- Username: Coverop
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jun 17, 2014 5:41 pm
- Post datetime: 2016-04-16T01:44:34+00:00
- Post Title: Re: Warframe Online MaxScript

Hello.

Thank you for creating this script... but unfortunately It is not working for me.
I'm using 3DSmax2012 and 3DSmax2016.

(I've followed the instruction one of the users provided)



I'm not sure where is the mistake... on my side or on the script side.
Maybe my computer is filled with trash...

Please help.
## Post #41
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-16T06:41:49+00:00
- Post Title: Re: Warframe Online MaxScript

Older scripts shouldn't work, try this one instead (with recent game client)
## Post #42
- Username: Coverop
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jun 17, 2014 5:41 pm
- Post datetime: 2016-04-29T19:14:27+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from zaramot
>
> Older scripts shouldn't work, try this one instead (with recent game client)

Thanks for reply... but the script is still not working. I've tried both and both gives me the same error :/
## Post #43
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-29T19:28:02+00:00
- Post Title: Re: Warframe Online MaxScript

Attach here file which gives an error or send in PM.
## Post #44
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-30T12:48:28+00:00
- Post Title: Re: Warframe Online MaxScript

I see developers making tiny changes quite frequently, with updates. This is bad, because I don't think I will try to support and edit model-import script each time. Though, I imported models you sent as a sample, here's a bit edited script, send me more not working models and I will try to finish script for recent game client. And this is it, from that point if script will fail with future updates I'm not going to return to Warframe in the near future.


[Warframe_New.7z](https://xentaxbackup.github.io/file/10858_Warframe_New.7z)
## Post #45
- Username: tathannibal
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 16, 2015 7:05 am
- Post datetime: 2016-10-04T16:21:30+00:00
- Post Title: Re: Warframe Online MaxScript

Evolution Engine Cache Extractor 1.0.1.0 Download not Working.
pls anyone send or share me. Thx

Fixed to Link THX
## Post #46
- Username: EinarTheRed
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 22, 2015 5:00 am
- Post datetime: 2016-12-27T18:56:37+00:00
- Post Title: Re: Warframe Online MaxScript

Ok, so I am sure this is DE updating the model info again, but I cant get the scripts to work at all. Always comes up with the error: Can't convert #() to type int. Any help with this?
## Post #47
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-12-28T19:00:00+00:00
- Post Title: Re: Warframe Online MaxScript

Well, DE doing very bad thing. With each update they change  file-version, it's only two-four bytes but it's spoiling my script:( I don't know if they are still doing it. But if they are doing this, then fixing script each time game is updating, it's not reasonable. I can disable version check in the script, though it will work only for old models, new ones won't import xD
## Post #48
- Username: EinarTheRed
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 22, 2015 5:00 am
- Post datetime: 2016-12-30T16:51:58+00:00
- Post Title: Re: Warframe Online MaxScript

How about like an update every 2 or 3 months, like every really major update? And with it also release one that doesn't do version control, that way it isn't taking up a great deal of your time, but we get one that works for a major update, and if they change things, get one that can last and let us view all but the most recent one. Best of both worlds type of thing. If it isn't asking to much of course.
## Post #49
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-12-30T17:47:15+00:00
- Post Title: Re: Warframe Online MaxScript

I will do this for Valkyr prime blueprints xDD Well, jokes off I will take a look on what I can do, I guess I should make ultimately working tool. Since, I love Warframe as a game, playing it almost every day xD
## Post #50
- Username: EinarTheRed
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 22, 2015 5:00 am
- Post datetime: 2017-01-02T21:46:48+00:00
- Post Title: Re: Warframe Online MaxScript

Me too. These Riven Mods are reinvigorating me for the game, my brother and I are having a blast coming up with stupid and clever ways to beat sortie missions.
## Post #51
- Username: Runerd
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 13, 2017 5:35 am
- Post datetime: 2017-09-16T01:23:35+00:00
- Post Title: Re: Warframe Online MaxScript

Hi and sorry if i'm bumping an old thread, there's anyone still working on the script? I love this game and i'll love if still exists a way to export the models.
## Post #52
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-09-16T18:05:56+00:00
- Post Title: Re: Warframe Online MaxScript

I would return to this game, if there was a proper way to extract textures. Not using NinjaRipper but from archives directly. Otherwise there's no reason to put much efforts into this. Game would die like all other MMOs and you will have useless client, you will have models but without textures they are pointless.
## Post #53
- Username: xbeton0L
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Dec 16, 2011 10:40 pm
- Post datetime: 2018-06-16T11:01:29+00:00
- Post Title: Re: Warframe Online MaxScript

I would like to learn how to do this. I want to help! 

I understand code, but I don't know which levers to pull or buttons to push. In short, I want to get started! I want to learn.
## Post #54
- Username: rareover
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 18, 2018 7:08 am
- Post datetime: 2018-11-20T18:20:31+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from xbeton0L
>
> I would like to learn how to do this. I want to help! 

I understand code, but I don't know which levers to pull or buttons to push. In short, I want to get started! I want to learn.

have you been successful?
## Post #55
- Username: xbeton0L
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Dec 16, 2011 10:40 pm
- Post datetime: 2018-12-13T09:36:07+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from rareover
>
> 
have you been successful?

No. I've asked and asked and asked and asked and asked and I have no idea what to do.
Every resource on the Internet redirects back to Tennogen related items.
It seems the information I need is obfuscated with irrelevant data.

I already know how to read data from a hex editor. I can open any file inside it.
I should also mention that I'm very good with low level languages, such as C and a bit of assembly.
But I have no idea what I'm looking at with these files. And I don't know what to look for.
I have all of the files already extracted. I just need to understand... want to get to the next step...

It is very frustrating not knowing what to do.
Is it true no one wants to help?
## Post #56
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2019-03-22T17:44:47+00:00
- Post Title: Re: Warframe Online MaxScript

The latest version of the extract file import error
## Post #57
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2019-03-24T05:02:12+00:00
- Post Title: Re: Warframe Online MaxScript

Please upgrade this script
## Post #58
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2019-03-24T14:32:38+00:00
- Post Title: Re: Warframe Online MaxScript

This is a new sample.
[sample.zip](https://xentaxbackup.github.io/file/15959_sample.zip)
## Post #59
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2019-03-24T14:37:30+00:00
- Post Title: Re: Warframe Online MaxScript

The engine version is 2019.02.27.16.35
Use the previous script, and then use 3dsmax 2012 and 2014 to import the model to report errors.
[20190324223639.png](https://xentaxbackup.github.io/file/15960_20190324223639.png)
## Post #60
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2019-03-24T16:16:09+00:00
- Post Title: Re: Warframe Online MaxScript

Hi, man.
I use Ninja Ripper 1.7.1, but I can't get the model and texture.
If you can use this tool to extract models and textures, can you tell me how to do it?
Thank you. I like this game. I want to use UE4 to make MOD.
## Post #61
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-04-03T18:38:13+00:00
- Post Title: Re: Warframe Online MaxScript

I presume this will still function on older versions of the game? Perhaps if someone has a backup they could use that.
## Post #62
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-04-18T12:16:29+00:00
- Post Title: Re: Warframe Online MaxScript

Actually that could work. Does anyone have a backup of an older version of the client?
## Post #63
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2019-06-30T14:10:48+00:00
- Post Title: Re: Warframe Online MaxScript

Anyone ever gonna update this again?
Really want to get the models for the new frames.
## Post #64
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-07-01T19:24:44+00:00
- Post Title: Re: Warframe Online MaxScript

The problems are - Warframe don't have that much models + they are for certain people's taste. Also! Problems not just with models but with textures too, I made some crappy tool to convert them (textures I mean) - just to get rhino and ash delux skins (also umbra) not long ago and that's basically all for now!
## Post #65
- Username: xbeton0L
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Dec 16, 2011 10:40 pm
- Post datetime: 2019-08-22T11:34:40+00:00
- Post Title: Re: Warframe Online MaxScript

What about new frames? Wisp, Khora, Octavia and Ivara?

There's tons of new content being added, and it's been a super long time since any updates.

I'd honestly do the work and update it myself, but I don't have the knowledge…
## Post #66
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-09-26T17:25:43+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from zaramot ↑Tue Jul 02, 2019 3:24 am at Tue Jul 02, 2019 3:24 am
>
> 
The problems are - Warframe don't have that much models + they are for certain people's taste. Also! Problems not just with models but with textures too, I made some crappy tool to convert them (textures I mean) - just to get rhino and ash delux skins (also umbra) not long ago and that's basically all for now!

Personally I am not even interested in the frames or weapons, just the enemies and environments.

Sadly I do not have a copy of the client the script was made for, nor have I found anyone who does.
## Post #67
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-09-27T02:33:09+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from Portugalotaku ↑Fri Sep 27, 2019 1:25 am at Fri Sep 27, 2019 1:25 am
>
> Sadly I do not have a copy of the client the script was made for, nor have I found anyone who does.
Last time I checked you do NOT need a special client version in order to have the script working for the game files.
## Post #68
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-09-28T18:28:23+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from mono24 ↑Fri Sep 27, 2019 10:33 am at Fri Sep 27, 2019 10:33 am
>
> 
Portugalotaku wrote: ↑Fri Sep 27, 2019 1:25 amSadly I do not have a copy of the client the script was made for, nor have I found anyone who does.
Last time I checked you do NOT need a special client version in order to have the script working for the game files.

From what I was told the script does not work on the newer versions, so we need an older one.
## Post #69
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-09-29T14:59:48+00:00
- Post Title: Re: Warframe Online MaxScript

Speaking of which, mono24, do you happen to possess a client compatible with the script?
## Post #70
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-15T03:21:46+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from Portugalotaku ↑Sun Sep 29, 2019 10:59 pm at Sun Sep 29, 2019 10:59 pm
>
> 
Speaking of which, mono24, do you happen to possess a client compatible with the script?
Just downloaded latest updated client/files and it looks like indeed script wont work anymore, last time I tried its been few months.
And no, there is no way to get old versions, someone used to make torrents with different build releases, not sure their live anymore, try google.
## Post #71
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-10-16T09:00:02+00:00
- Post Title: Re: Warframe Online MaxScript

That was the first thing I tried, but could not find anything, which is why I asked if you had or knew someone who had a copy. I will continue looking.
## Post #72
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-10-16T20:55:22+00:00
- Post Title: Re: Warframe Online MaxScript

I'm working on updated script for 3d models, so everyone who's interested stay tuned xD
## Post #73
- Username: SwingNinja
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 18, 2019 1:18 am
- Post datetime: 2019-10-17T18:19:38+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from Portugalotaku ↑Wed Oct 16, 2019 5:00 pm at Wed Oct 16, 2019 5:00 pm
>
> 
That was the first thing I tried, but could not find anything, which is why I asked if you had or knew someone who had a copy. I will continue looking.

You could try archive.org. They archive warframe.com
## Post #74
- Username: PA3OP
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 30, 2018 1:49 pm
- Post datetime: 2019-10-20T09:26:59+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from zaramot ↑Thu Oct 17, 2019 4:55 am at Thu Oct 17, 2019 4:55 am
>
> 
I'm working on updated script for 3d models, so everyone who's interested stay tuned xD
Сan’t wait for the update!
## Post #75
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-10-20T12:13:05+00:00
- Post Title: Re: Warframe Online MaxScript

Actually, you could help me out, I could send you script for testing. Just for geometry+uv's in order to test not working models faster. If geometry import is working, everything else will too and after fixing all broken ones, I'll just enable skin and done xD What do you think?!
## Post #76
- Username: PA3OP
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 30, 2018 1:49 pm
- Post datetime: 2019-10-20T13:38:21+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from zaramot ↑Sun Oct 20, 2019 8:13 pm at Sun Oct 20, 2019 8:13 pm
>
> 
Actually, you could help me out, I could send you script for testing. Just for geometry+uv's in order to test not working models faster. If geometry import is working, everything else will too and after fixing all broken ones, I'll just enable skin and done xD What do you think?!
I would love to do it, but I haven’t even downloaded 3DSMAX XD.
## Post #77
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-10-21T13:29:46+00:00
- Post Title: Re: Warframe Online MaxScript

That is great to hear, though I will continue looking for an old version of the client, since there are some things that got removed between then and now.
## Post #78
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-10-26T15:02:35+00:00
- Post Title: Re: Warframe Online MaxScript

Hey! Guys, test this script with warfarme models. It will import only geometry for now (I disabled skin for faster testing), and provide all not working ones. In that way progress will be faster, I'm sure because I got bored testing them lol And switched to Fallout 76 script
[Warframe_Online_UPD.7z](https://xentaxbackup.github.io/file/16944_Warframe_Online_UPD.7z)
## Post #79
- Username: PA3OP
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 30, 2018 1:49 pm
- Post datetime: 2019-10-26T17:27:00+00:00
- Post Title: Re: Warframe Online MaxScript

Is there any way to import models without skeleton? (Like dojo props) 

Also, TnoCarrierShipFinal_skel is broken (H.Misc.cache\Lotus\Objects\Tenno\Ships\CarrierShip)
## Post #80
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-10-27T15:33:57+00:00
- Post Title: Re: Warframe Online MaxScript

For now I focused on updating characters and enemies, flora-fauna xD They are all in "characters" folder. I will think about supporting anything else, like weapons and ships, props or levels. First for me at least are skinned models of characters.
## Post #81
- Username: PA3OP
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 30, 2018 1:49 pm
- Post datetime: 2019-10-27T18:06:41+00:00
- Post Title: Re: Warframe Online MaxScript

Oh, ok. The game files already have models from a future update called "Empyrean". I would like to take a look at these models, so I'll wait for further updates of this script! 
Btw, your script is amazing.
(sry for my English, I used google translator)
## Post #82
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-10-27T18:54:00+00:00
- Post Title: Re: Warframe Online MaxScript

It's okay, English isn't my native language too. I assume you're Russian-speaking person (judging by your nickname), if it's true you could use it in conversation with me, if you will have any difficulties explaining something xD
## Post #83
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-11-08T21:19:34+00:00
- Post Title: Re: Warframe Online MaxScript

Well I am an idiot. I forgot that I had a copy of the client dating from December 2017 in my second computer. I wonder if either the new or old scripts can work with it...
## Post #84
- Username: medcorn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 06, 2020 5:36 pm
- Post datetime: 2020-01-06T22:44:36+00:00
- Post Title: Re: Warframe Online MaxScript

Hey Zaramot, found that your most recent import script doesn't include skeleton support or object support, was wondering if these would be coming? It's fine if you're too busy to update, maybe I can fiddle with the code to make it work.

[https://imgur.com/a/QC5K3sG](https://imgur.com/a/QC5K3sG) Some images of errors I got.
## Post #85
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-01-06T22:55:24+00:00
- Post Title: Re: Warframe Online MaxScript

Yeah, I was really thinking to make script work fine xD One good person helped me with testing, but main trouble (I guess, I bored everyone with this old song lol) it's textures, I figured out (more or less) how to get them, all except normal maps! They're coming out messed up so far (maybe some old ones are okay, but newer not), so I don't know what point to import models is you can't get textures?! Since, I had reports, that ninja ripped stopped working with this game too. If anyone, ANYONE will make proper texture converter (at least for normal maps), I will sit down and update script for models in a few days for sure   I like this game, playing often - not much, but I'm playing it, 24 rank there, so I would like to make script for this game.
## Post #86
- Username: medcorn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 06, 2020 5:36 pm
- Post datetime: 2020-01-06T23:05:52+00:00
- Post Title: Re: Warframe Online MaxScript

I've used Ninjaripper recently, but I can test again.
## Post #87
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-01-06T23:15:09+00:00
- Post Title: Re: Warframe Online MaxScript

Well, it's good news if you did use it! Because, I've had a ton of complains in PM about it's not working anymore xD It might change the approach a bit! If you will confirm it's working, I'll try it myself and then if it's indeed working, then script have much more point. Of course it's not like a good texture converter, but at least I'll make an update for characters and enemies, armors and other attachable objects for warframe's customization, maybe weapons too.
## Post #88
- Username: medcorn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 06, 2020 5:36 pm
- Post datetime: 2020-01-06T23:35:40+00:00
- Post Title: Re: Warframe Online MaxScript

Here's how it works: Warframe prevents you from running it from NinjaRipper by forcing you to use the launcher. However, this can be bypassed.
Open NinjaRipper
Open Warframe Launcher
Click 'Run' in NinjaRipper, set to D3D11 Wrapper. This will tell you to run warframe through the launcher, click OK.
Run Warframe, in fullscreen, through the launcher. Do this without closing NinjaRipper.

Then you can use whatever hotkey you have set to rip all, mine is set to F10. 
Can confirm this method works in the current patch, Empyrean. Really want some skeletons for the models, especially the ones I don't have access to through NinjaRipper anymore. One time only quest stuff.

As for textures from NinjaRipper, Warframe's textures are in a format that is really strange, but can be fixed through clever image editing. You can even use Gimp on it. This is my knowledge so far.
## Post #89
- Username: Gurobase
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 14, 2017 8:13 am
- Post datetime: 2020-01-07T10:41:48+00:00
- Post Title: Re: Warframe Online MaxScript

Warframe's normal maps and id masks for storing roughness/AO/metalness(?) info can be easily exported with Intel's frame analyzer. Can't say the same for tint maps, because those seem to not export at all as of recent (at least when I tried using both the frame analyzer and ninja ripper)
## Post #90
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-01-07T11:09:08+00:00
- Post Title: Re: Warframe Online MaxScript

Ah, so intelGPA working too, well guys it's great. Of course textures from rippers coming okay, textures from archives made by DE aren't like that xD Even mip order there is different, from lowest to biggest.
## Post #91
- Username: medcorn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 06, 2020 5:36 pm
- Post datetime: 2020-01-08T02:42:46+00:00
- Post Title: Re: Warframe Online MaxScript

All of the textures ARE coming out okay from NinjaRipper. Can't say the same for the other one since I haven't used it. The textures for Warframes in particular (not sure about other things) all come in one file except for normal mapping. All the textures, including the tint-masks are in one file, just on the color channels for some reason. 
Excalibur textures, as an example: [https://imgur.com/a/Hu9OoBp](https://imgur.com/a/Hu9OoBp)
The tint masks are all in one layer, and have to be separated into four.
If there is a way to get textures from the cache files of the game as well, it would be much appreciated, as certain things in-game cannot be accessed through NinjaRipper.
## Post #92
- Username: Gurobase
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 14, 2017 8:13 am
- Post datetime: 2020-01-08T07:53:56+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from medcorn ↑Wed Jan 08, 2020 10:42 am at Wed Jan 08, 2020 10:42 am
>
> 
All of the textures ARE coming out okay from NinjaRipper. Can't say the same for the other one since I haven't used it. The textures for Warframes in particular (not sure about other things) all come in one file except for normal mapping. All the textures, including the tint-masks are in one file, just on the color channels for some reason. 
Excalibur textures, as an example: https://imgur.com/a/Hu9OoBp
The tint masks are all in one layer, and have to be separated into four.
If there is a way to get textures from the cache files of the game as well, it would be much appreciated, as certain things in-game cannot be accessed through NinjaRipper.

The grayscale info stored in separate RGB channels on that texture isn't a tint mask.
It's a roughness/AO/probably metallic info stored in an RGB mask. (Maybe specularity map too, needs testing to see which is what tbh)
Not sure about the alpha channel, but that's definitely not a tint mask.
Tint mask has clear red, green and blue separated islands.
Here's an example of an actual tint mask in WF. Clear red, green and blue islands without any detail.
## Post #93
- Username: medcorn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 06, 2020 5:36 pm
- Post datetime: 2020-01-08T10:05:05+00:00
- Post Title: Re: Warframe Online MaxScript

The other textures aren't what I was trying to call a tint mask. The alpha channel when broken into separate layers functions essentially the same, if it isn't a tint mask. This is what I meant. Here, by breaking it up and putting the layers together, then changing their colors:


I've also renamed the layers to their ingame names, and put them over a base texture for reference. By changing the layer modes to overlay, we get a better view:



Maybe I found a dumb way that just works. Unsure. I'm also sure this isn't exactly how it's done. But, with a bit of fiddling with other textures as well I've done things in Blender in the past:




Clearly I need a bit more experience in getting the textures working properly but I've mostly just been screwing around with them.
## Post #94
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-01-09T14:00:44+00:00
- Post Title: Re: Warframe Online MaxScript

Texture tinting is usually done by lerping/mixing.
For example:

```
tint = lerp(color1, color2, R_Channel);
tint = lerp(tint, color3, G_Channel);
tint = lerp(tint, color4, B_Channel);

```

Tint is then multiplied or averaged into diffuse texture, like:

```
//OR by averaging
diffuse = (diffuseTexture + tint) / 2;

```

Whichever looks better.
## Post #95
- Username: medcorn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 06, 2020 5:36 pm
- Post datetime: 2020-01-12T01:04:06+00:00
- Post Title: Re: Warframe Online MaxScript

I've got a question regarding Warframe Operator head models in particular. When the model files are extracted, the H cache has every head type listed, though the B cache only has 6 varying head meshes.

H.Misc.cache

B.Misc.cache


I'm curious as to if the other heads are in some strange way based off the meshes of the 6 available? And if so, how could they be used? If I could access all of the available heads, I could blend them with shape keys or something in a way similar to in-game.

Another odd thing: NinjaRipper will only rip say, female head A or male head A, even if they are not present in the frame. Yet another thing that makes me think they are all based off of one mesh somehow.
## Post #96
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-01-12T01:51:26+00:00
- Post Title: Re: Warframe Online MaxScript

Yup, warframe using morphs, basically base head mesh is the same, that's why NR ripping it too, as you said. Face aren't using facial rig, so basically they don't need specific skeleton and since they have same polygon/vertex count they don't need separate info files, that explain mismatch between two folders - in one there's more files, than in another
## Post #97
- Username: medcorn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 06, 2020 5:36 pm
- Post datetime: 2020-01-12T02:25:04+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from zaramot ↑Sun Jan 12, 2020 9:51 am at Sun Jan 12, 2020 9:51 am
>
> 
Yup, warframe using morphs, basically base head mesh is the same, that's why NR ripping it too, as you said. Face aren't using facial rig, so basically they don't need specific skeleton and since they have same polygon/vertex count they don't need separate info files, that explain mismatch between two folders - in one there's more files, than in another
Now this brings up the question of whether or not it's possible to actually use said morphs, outside of the game? Or is something like this exclusive to the game? Are the files in H.Misc.cache even related to the morphs? The only information I can read in H.Misc.cache on these heads are for textures and shaders.


EDIT: Nevermind, I'm a fool. Found some stuff on morphs in the more generic looking files in those folders. Now, how do they work?

OperatorHeadFemale_skel.fbx
## Post #98
- Username: jetomawolf
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 10, 2019 9:04 pm
- Post datetime: 2020-01-30T11:00:33+00:00
- Post Title: Re: Warframe Online MaxScript

Hi to all,
how can I open fbx (of cache extracted) files?

Thanks to all!
## Post #99
- Username: DFliyerz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 23, 2020 9:54 am
- Post datetime: 2020-06-09T19:04:41+00:00
- Post Title: Re: Warframe Online MaxScript

Hi Zaramot, do you think you could make a version of the MaxScript just for importing props? I've found that trying to get props via ninjaripper is a huge pain due to all the duplicates, and think that using the cache files would make things a lot simpler.
## Post #100
- Username: TheDeadBody
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 02, 2020 8:02 pm
- Post datetime: 2020-07-02T12:09:49+00:00
- Post Title: Re: Warframe Online MaxScript

Could someone rip for me the Nidus Night Hunter skin Model? And one little Question if you havethe Model and texures can you like colour them bc I can't rip them bc Warframe is yelling at bme with Ninjaripper to open in Launcher and shit.. you know.. and second thing I dont have the skin ingame with my cool colours .. (One little texture thing you know)

I would really appriciate it if someone would Rip the Nidus Model with Night Hunter skin on it..
## Post #101
- Username: cyber212
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 05, 2017 7:20 pm
- Post datetime: 2020-08-14T20:58:44+00:00
- Post Title: Re: Warframe Online MaxScript

@zaramot warfame_bones not working 
can you fix it ?
## Post #102
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2020-10-07T06:55:07+00:00
- Post Title: Re: Warframe Online MaxScript

Hello everyone, I'm sorry that I haven't logged in this forum for a long time.Because I was sick, I had an operation, I'm recovering now, it's like a new version of the game, I haven't logged in for a long time.My family won't let me play.They warned me of the need for rest.Thank you for your concern about this topic. Many people have died from the epidemic since last year. I hope you can stay healthy.Let's continue this topic when we have time.
## Post #103
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2021-01-20T16:47:50+00:00
- Post Title: Re: Warframe Online MaxScript

Hey, just wanted to ask if anyone is interested in figuring out how to extract the level tiles. I am willing to pay for it.
## Post #104
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2022-01-07T16:48:11+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from zaramot ↑Mon Dec 23, 2013 8:22 pm at Mon Dec 23, 2013 8:22 pm
>
> 
Here is a MMO Warframe import script for 3ds Max.
Site: https://warframe.com
Supported:
Geometry
UV's
Bones+Weights
Not Supported:
Textures
Materials

Here's tool by GMMan http://forum.xentax.com/viewtopic.php?f=32&t=10782 to extract game content from .cache archives

B.Misc.cache - all models
H.Misc.cache - all reference files for models (small files with same name as model files, they should be imported first, then model files)

Sorry to ping this 9 years later, but I went ahead and downloaded an old copy of the warframe client for compatibility with this script, but it doesn't seem to support static meshes. How would I got about opening those?
## Post #105
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-01-07T17:37:23+00:00
- Post Title: Re: Warframe Online MaxScript

> Reply from Portugalotaku ↑Sat Jan 08, 2022 12:48 am at Sat Jan 08, 2022 12:48 am
>
> 

Sorry to ping this 9 years later, but I went ahead and downloaded an old copy of the warframe client for compatibility with this script, but it doesn't seem to support static meshes. How would I got about opening those?

The tools were updated a while ago, look in the Warframe models discord [https://discord.com/invite/Jk3xA2T](https://discord.com/invite/Jk3xA2T)
