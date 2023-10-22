## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-05-16T22:29:39+00:00
- Post Title: A Plague Tale: Innocence Tool

UPDATE :  Skinned model are supported now. Support for static meshes is dropped. Download the old version below for loading them.

Here is a tool for extracting models and textures from the ".DPC" files of this game. Only skinned meshes are supported atm.

Tool overview and example exported model





How to use

Load

Browse : For selecting the .DPC file.
List : Found models in the .DPC file will be added to the list. Select one to load it.
Export

NEX : Exports the model in custom binary format (.nex), intended to be loaded by Noesis. Noesis script for this format : Nex Script
SEModel : Exports the model in SEModel (*.semodel) format by dtzxporter. There are import scripts for Maya and Blender 2.79/ 2.80
PNG : Loads all the textures inside the selected file and exports them as PNG. Might take some time.
Note  : Models and textures will be exported into the folder Export.
Download : [https://www.mediafire.com/file/sfxjlwkz ... 2.rar/file](https://www.mediafire.com/file/sfxjlwkzspnrzi7/APTViewer_U2.rar/file)

Old version (OBJ export only) :  [https://www.mediafire.com/file/is0lcudm ... r.rar/file](https://www.mediafire.com/file/is0lcudm2dbnx68/APTViewer.rar/file)
## Post #2
- Username: tpcrew
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jan 08, 2012 7:36 pm
- Post datetime: 2019-05-17T19:48:23+00:00
- Post Title: A Plague Tale: Innocence Tool

Thanks a lot
## Post #3
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2019-05-17T22:09:43+00:00
- Post Title: A Plague Tale: Innocence Tool

Well done, hope bones are supported soon. This is awesome
Thank you
## Post #4
- Username: Ezekiel
- Rank: beginner
- Number of posts: 37
- Joined date: Mon Jan 25, 2016 4:18 am
- Post datetime: 2019-05-18T11:43:54+00:00
- Post Title: A Plague Tale: Innocence Tool

wow, rats of us, I mean Plague Tale tool..
Like Button Destroyed
## Post #5
- Username: ricmetal
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 07, 2018 3:50 am
- Post datetime: 2019-05-21T13:54:15+00:00
- Post Title: A Plague Tale: Innocence Tool

any chance of the tool being able to extract assets like walls and trees?
## Post #6
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-05-21T15:27:38+00:00
- Post Title: A Plague Tale: Innocence Tool

> Reply from ricmetal ↑Tue May 21, 2019 9:54 pm at Tue May 21, 2019 9:54 pm
>
> 
any chance of the tool being able to extract assets like walls and trees?

already supported, but sadly, like Ninja Ripper, all the objects from the scene, are imported in the 0,0,0 coords
## Post #7
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-05-21T15:39:50+00:00
- Post Title: A Plague Tale: Innocence Tool

> Reply from fil1969 ↑Tue May 21, 2019 11:27 pm at Tue May 21, 2019 11:27 pm
>
> 
all the objects from the scene, are imported in the 0,0,0 coords
I am guessing these are from the LEVEL files. I haven't take a look at object placement yet. Noticed some matrix like values in the mesh headers though. They might be related to the placement. I will get to maps eventually.

Currently trying to get the skeleton loading. Having a hard time finding it though. DPC files are made out of chunks and most of them are compressed. Maybe I should make a proper archive decompressor first
## Post #8
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-05-21T17:05:59+00:00
- Post Title: A Plague Tale: Innocence Tool

> Reply from akderebur ↑Tue May 21, 2019 11:39 pm at Tue May 21, 2019 11:39 pm
>
> 
fil1969 wrote: ↑Tue May 21, 2019 11:27 pm
all the objects from the scene, are imported in the 0,0,0 coords

I am guessing these are from the LEVEL files.

 not only, even shared.dpc. only characters loads correctly. but you did a great work with this tool, it saved me a lot of work.
[https://www.deviantart.com/oo-fil-oo/ar ... -797719516](https://www.deviantart.com/oo-fil-oo/art/A-PLAGUE-TALE-INNOCENCE-RIPPING-PROCESS-797719516)
## Post #9
- Username: ricmetal
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 07, 2018 3:50 am
- Post datetime: 2019-05-22T19:33:40+00:00
- Post Title: A Plague Tale: Innocence Tool

some textures appear to be coming out all messed up. ive tried the png extraction twice and the same files are broken.

also, it appears some images are animation frames, possibly dds files broken up into single pngs.
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-05-22T20:34:54+00:00
- Post Title: A Plague Tale: Innocence Tool

> Reply from ricmetal ↑Thu May 23, 2019 3:33 am at Thu May 23, 2019 3:33 am
>
> 
some textures appear to be coming out all messed up.
It only extracts DXT1/5 textures, since characters seems to just use those. If I encounter any other type that seems necessary I can think of adding support. I will take a look at maps soon, maybe they might be using other pixel formats.
## Post #11
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2019-05-23T06:32:03+00:00
- Post Title: A Plague Tale: Innocence Tool

Have anyone find more of NPCs or villager characters yet?
## Post #12
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-05-23T17:05:03+00:00
- Post Title: A Plague Tale: Innocence Tool

> Reply from ngovandang ↑Thu May 23, 2019 2:32 pm at Thu May 23, 2019 2:32 pm
>
> 
Have anyone find more of NPCs or villager characters yet?

hi! i think are in every level file, In Univerity you can find the inquisitor for the second time, like rats are in "shared files" since are everywhere, But i'm not sure. I can't import the obj's level files, it always returns me memory error in every 3d program i try, only Noesis can preview, but always crashes when i try to export.. and i have an I7 with 32gb of ram and a 6gbNvidia videocard.. idk..i will post any progress.

edit: ok, i make it work, I just deleted the generated Mtl file. And i can confirm every npc (animals and chars ) are stored in Level files
[](https://ibb.co/YT05vP0)
[](https://ibb.co/vYSdCrk)
## Post #13
- Username: vvampii
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 12, 2019 12:37 pm
- Post datetime: 2019-05-24T05:17:18+00:00
- Post Title: A Plague Tale: Innocence Tool

> Reply from ngovandang ↑Thu May 23, 2019 2:32 pm at Thu May 23, 2019 2:32 pm
>
> 
Have anyone find more of NPCs or villager characters yet?

i found lord nicholas in level file 'shelter siege'. they are all in level files.
## Post #14
- Username: ricmetal
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 07, 2018 3:50 am
- Post datetime: 2019-05-24T06:17:06+00:00
- Post Title: A Plague Tale: Innocence Tool

how do you get the textures onto the model? i found amisia and textures for her but she's consisted of several mesh groups and they're like a ton of textures. im guessing you spend time getting the textures on the right group of the model?

EDIT:
also, hopefully this tool will support more image files, @akderebur.
looking forwards to having these walls:

and it seems, by sheer unluck, the textures used by them are exactly the ones that came out broken (maybe they didn't get exported at all)

doesn't look bad but..
## Post #15
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2019-05-27T14:29:03+00:00
- Post Title: A Plague Tale: Innocence Tool

can someone fix the tool to have UW scans with assigned material as well as automatic texture overlay?
## Post #16
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-05-30T23:15:38+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

Finally had time to properly look at skeleton data. Finding the data in the archive was actually harder than loading it  I will do some more tests and release an update.
## Post #17
- Username: hashimora
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 03, 2019 3:55 pm
- Post datetime: 2019-06-03T08:37:37+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

anyone know which file contains robert de runes  model ?
Also is there any .bms file to decrypt these dpc files ?
## Post #18
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-03T20:30:05+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

The first post is updated with the new version of the tool. Skeleton/skinning is supported now.

Static mesh support is dropped for the time being. I will take a further look in the map data if I find the time.
## Post #19
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2019-06-04T06:39:35+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

fix the tool to identify the UW map with the assigned material, as well as the automatic texture overlay on other objects.......please.
## Post #20
- Username: raidergale
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 15, 2010 12:52 am
- Post datetime: 2019-06-04T12:43:00+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

Thanks for the updated tool! A weird thing I noticed with the "P_BEATRICE" model is that her facial bones are shifted up slightly compared to where they should be. It's easy to fix manually since they're just shifted on the Z axis, but weird nonetheless. This doesn't seem to happen to the "P_AMICIA" model.

"P_BEATRICE" also has a couple of swizzled textures, I assume due to the fact the tool only exports DXT1/DXT5 textures as you said in the first page. I think they might be her eyelashes/eyeshadow textures, since all the other textures are accounted for.

Other than these things I noticed everything seems to work great, so thanks again!
## Post #21
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-04T14:06:41+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

> Reply from raidergale ↑Tue Jun 04, 2019 8:43 pm at Tue Jun 04, 2019 8:43 pm
>
> 
"P_BEATRICE" model is that her facial bones are shifted up slightly compared to where they should be.

Thanks for reporting. Other characters I have tested were fine. I will double check Beatrice to be sure. What export format/plugin did you use (SEModel or Nex)?

> Reply from raidergale ↑Tue Jun 04, 2019 8:43 pm at Tue Jun 04, 2019 8:43 pm
>
> 
"P_BEATRICE" also has a couple of swizzled textures
I will check that too.

> Reply from ix35 ↑Tue Jun 04, 2019 2:39 pm at Tue Jun 04, 2019 2:39 pm
>
> 
fix the tool to identify the UW map with the assigned material, as well as the automatic texture overlay on other objects.......please.
I don't want to bother with material mappings atm. I might do it eventually, but it is really low priority.
## Post #22
- Username: raidergale
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 15, 2010 12:52 am
- Post datetime: 2019-06-04T15:22:48+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

> Reply from akderebur ↑Tue Jun 04, 2019 10:06 pm at Tue Jun 04, 2019 10:06 pm
>
> Thanks for reporting. Other characters I have tested were fine. I will double check Beatrice to be sure. What export format/plugin did you use (SEModel or Nex)?

I've tried both options, same result. SEModel imported directly to Blender, Nex converted to FBX via Noesis. I've only had time to check P_AMICIA (which was fine) and P_BEATRICE (which had the issue), so I don't know if other models have the same issue

> Reply from akderebur ↑Tue Jun 04, 2019 10:06 pm at Tue Jun 04, 2019 10:06 pm
>
> I will check that too.

Thank you very much!
## Post #23
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2019-06-05T07:19:57+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

no one but you can help us
## Post #24
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-05T22:47:27+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

Small Update : Download link updated in the first post

- Fixed a bug with bone scales
- Fixed a bug with texture identification

"P_BEATRICE" should be exported fine now, in terms of skeleton and textures.
## Post #25
- Username: PsychoFox
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jun 03, 2019 3:53 am
- Post datetime: 2019-06-07T05:47:31+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

Any info on whether it's possible to repack the game with altered models to make outfit mods?
## Post #26
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-07T06:03:21+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

> Reply from PsychoFox ↑Fri Jun 07, 2019 1:47 pm at Fri Jun 07, 2019 1:47 pm
>
> 
Any info on whether it's possible to repack the game with altered models to make outfit mods?
I was thinking about this too. It might actually be possible, but I need someone to make me an altered model  For Hugo hands if possible, that would be easiest to test for a start.

Get in touch with me if you are capable of providing some meshes to test.
## Post #27
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2019-06-19T13:57:32+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

When will the tool update be released? I'm waiting.
## Post #28
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-19T14:23:33+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

> Reply from ix35 ↑Wed Jun 19, 2019 9:57 pm at Wed Jun 19, 2019 9:57 pm
>
> 
When will the tool update be released? I'm waiting.
I am updating my tools when I feel like it. No need for you to wait for it actively  I was only interested in the characters of this game, so the tool is almost complete for me. I might do maps some time, but I am not that willing atm. I can't say if I will ever do them. 

Model/texture repacking is another possible feature, but it would take some time to code properly. Also it seems like there isn't that much interest. Only "PsychoFox" brought that topic up. So unless there is more demand for it, I will probably not add repacking too.
## Post #29
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2019-06-20T16:24:33+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

Listen friend! Please make the instrument complete for me personally. I'll pay for the work.
## Post #30
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2019-06-20T21:12:32+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

Personally, I would like to see support for the static meshes/textures too.
Don't really care if it's the whole map or not, I just find the world in this game really charming.

But these things always take time and it's totally up to akderebur how much he develops his tools hehe
## Post #31
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2019-06-21T11:50:02+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

I agree completely, but for some reason he doesn't want
## Post #32
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2019-06-21T13:09:48+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

> Reply from ix35 ↑Fri Jun 21, 2019 7:50 pm at Fri Jun 21, 2019 7:50 pm
>
> 
I agree completely, but for some reason he doesn't want

Reason being it takes a lot of time to research and develop the tool
## Post #33
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2019-06-22T07:10:46+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

we'll wait.....I hope it works and he hears us.
## Post #34
- Username: smasher248
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 14, 2015 9:52 am
- Post datetime: 2019-06-22T12:27:34+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

I would also love the ability to repack modified models/textures
## Post #35
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2019-06-22T18:30:03+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

нас много))).....и теперь ему не отказать нам....так что ждем обновления)
## Post #36
- Username: smasher248
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 14, 2015 9:52 am
- Post datetime: 2019-06-23T13:11:42+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

> Reply from ix35 ↑Sun Jun 23, 2019 2:30 am at Sun Jun 23, 2019 2:30 am
>
> 
нас много))).....и теперь ему не отказать нам....так что ждем обновления)

Don't be so entitled
## Post #37
- Username: hqqttjiang
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 19, 2012 10:27 am
- Post datetime: 2019-06-23T13:51:48+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

is it posiable to repack back so we can mod the game。
## Post #38
- Username: PsychoFox
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jun 03, 2019 3:53 am
- Post datetime: 2019-06-30T13:30:16+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

From what i understand the author of this tool doesn't want to work on the tool anymore because its too difficult and he thinks the prospect for seeing a modding community is small.
## Post #39
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-30T14:37:08+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

> Reply from PsychoFox ↑Sun Jun 30, 2019 9:30 pm at Sun Jun 30, 2019 9:30 pm
>
> 
From what i understand the author of this tool doesn't want to work on the tool anymore
Actually I am working on reimporting atm. Thank smasher248 for it, since he offered to fund my work. Model reimporting is almost done, textures need a bit more work.

Some of you guys just have to remember that I don't owe anything to anyone here. So don't get surprised when I don't want to spend my time on some feature, just because you want it to happen.
## Post #40
- Username: hqqttjiang
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 19, 2012 10:27 am
- Post datetime: 2019-07-07T07:49:05+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

thanks for the tool and can't wait to see the repack things.
## Post #41
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2019-08-07T17:40:34+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

so will the tool update or not?
## Post #42
- Username: smasher248
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 14, 2015 9:52 am
- Post datetime: 2019-08-08T19:11:45+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

> Reply from ix35 ↑Thu Aug 08, 2019 1:40 am at Thu Aug 08, 2019 1:40 am
>
> 
so will the tool update or not?

Not sure, haven't heard back
## Post #43
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2019-08-25T12:33:15+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

akderebur...............when will you update the instrument?
## Post #44
- Username: hqqttjiang
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 19, 2012 10:27 am
- Post datetime: 2019-08-30T10:43:37+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

cant wait to the repack tool
## Post #45
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2019-08-31T10:31:03+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

it is necessary that the texture is adjusted automatically
## Post #46
- Username: Nguyen Thanh Tùng
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jan 12, 2019 8:53 am
- Post datetime: 2019-09-03T11:22:39+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

How did you find the material map?
## Post #47
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2019-09-03T14:16:20+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

so everyone is looking for it
## Post #48
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-10T12:38:43+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

vThanks for your help
## Post #49
- Username: hqqttjiang
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 19, 2012 10:27 am
- Post datetime: 2019-10-01T07:55:27+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

ANY NEWS for the mod tool?
## Post #50
- Username: smasher248
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 14, 2015 9:52 am
- Post datetime: 2019-10-03T16:48:42+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

> Reply from hqqttjiang ↑Tue Oct 01, 2019 3:55 pm at Tue Oct 01, 2019 3:55 pm
>
> 
ANY NEWS for the mod tool?

It's not happening
## Post #51
- Username: smasher248
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 14, 2015 9:52 am
- Post datetime: 2019-12-01T19:52:42+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

It might be happening actually
## Post #52
- Username: Mayadesk
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Aug 15, 2019 6:32 am
- Post datetime: 2019-12-14T07:22:35+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

tools for text please
## Post #53
- Username: mrmemmo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 25, 2019 5:44 pm
- Post datetime: 2020-04-25T09:26:59+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

you can share source code?
## Post #54
- Username: anonymer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 19, 2020 11:26 am
- Post datetime: 2020-08-04T03:29:01+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

Please help, may i ask what number is the Texture for Vitalis? i can't seem to find his texture & by the time the texture gets to #1000+, my computer crashes
## Post #55
- Username: solidBoy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 07, 2020 3:00 am
- Post datetime: 2020-10-06T19:06:10+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

Ah, what a shame we still cant mod this game. Hopefuly someone finishes the work of this brave man.
## Post #56
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2022-10-30T15:42:59+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

The Requiem is released but it seems that not so many people are interested in this game.
If, by any chance this tool could be updated, it would be really lovely!
Here's what I have got so far:
①By using APT_DPC_Tool by amrshaheen61 [https://github.com/amrshaheen61/APT_DPC_Tool](https://github.com/amrshaheen61/APT_DPC_Tool)
I successfully unpack the dpc files of requiem

②Also noticed that the files are in something like "msh", "mtl", "tex" and "skl"


Unknowing whether it would help or not, I still post it in case anyone is into it.
## Post #57
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2022-10-31T04:57:56+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

How can I view these files now ?
## Post #58
- Username: urao
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 29, 2016 9:14 pm
- Post datetime: 2022-11-19T19:31:16+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

You can use Noesis software.
Regards
## Post #59
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2022-11-20T15:26:50+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

> Reply from urao ↑Sun Nov 20, 2022 3:31 am at Sun Nov 20, 2022 3:31 am
>
> 
You can use Noesis software.
Regards

But it seems that the skeleton doesn't attach to the mesh
## Post #60
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2022-11-23T19:45:50+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

same boat here no skelton comes with models i have the files with me and no hiecharhy
## Post #61
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2022-11-23T19:56:45+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

> Reply from anonymer ↑Tue Aug 04, 2020 11:29 am at Tue Aug 04, 2020 11:29 am
>
> 
Please help, may i ask what number is the Texture for Vitalis? i can't seem to find his texture & by the time the texture gets to #1000+, my computer crashes

i have vitalis and his textures dm for link
## Post #62
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2022-11-23T20:54:08+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

дайте скомпилированный  и скрип на ноезиз

give compiled and squeak on noeziz
## Post #63
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2022-11-25T13:38:35+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

> Reply from ix35 ↑Thu Nov 24, 2022 4:54 am at Thu Nov 24, 2022 4:54 am
>
> 
дайте скомпилированный  и скрип на ноезиз

give compiled and squeak on noeziz

A Plague Tale Support already in noesis out of box, just use [newer](https://richwhitehouse.com/index.php?content=inc_projects.php) version if you don't have it.
## Post #64
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2022-11-26T07:44:55+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

A Plague Tale Support already in noesis out of box, just use [newer](https://richwhitehouse.com/index.php?content=inc_projects.php) version if you don't have it.
[/quote]

как мне распаковать файлы?
how do I unpack the files?
## Post #65
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2022-11-27T08:33:33+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

> Reply from ix35 ↑Sat Nov 26, 2022 3:44 pm at Sat Nov 26, 2022 3:44 pm
>
> 
A Plague Tale Support already in noesis out of box, just use newer version if you don't have it.

как мне распаковать файлы?
how do I unpack the files?
[/quote]

I checked Noesis, and in the file formats there is also the archieve unpacker, I don't have the game, so I can't test it. Let me now if works with new game
## Post #66
- Username: ix35
- Rank: beginner
- Number of posts: 25
- Joined date: Wed May 24, 2017 11:50 pm
- Post datetime: 2022-11-29T20:26:02+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

Кто то поможет мне распкаковать файлы?

Can someone help me unpack the files?
## Post #67
- Username: VladAl
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 05, 2022 3:01 pm
- Post datetime: 2022-12-05T16:04:15+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

Скачайте(Download) APT DPC Tool: [https://github.com/amrshaheen61/APT_DPC ... l.v1.0.zip](https://github.com/amrshaheen61/APT_DPC_Tool/releases/download/v1.0/APT.DPC.Tool.v1.0.zip)
Распакуйте в папку
Откройте папку, запустите исполняемый файл. 
Выберите версию игры. Нажмите кнопку"Export". Найдите в папке с игрой папку DATAS, а в ней - интересующего персонажа. Нажмите Открыть. Вам предложат папку для сохранения, выберите существующую или создайте новую. 
Скачайте  (Download)Noesis: [https://www.richwhitehouse.com/filemirr ... sv4466.zip](https://www.richwhitehouse.com/filemirror/noesisv4466.zip).
Распакуйте в папку. Откройте папку, запустите исполняемый файл Noesis.exe(x86 или x64). Выберите папку(слева), в которую ранее распаковали файлы игры(их много). Сделайте двойной щелчок по любому из файлов, они появились в среднем списке. Если программа не закроется, то справа откроется текстура или 3D объект. В среднем списке нажмите на этом файле на правую кнопку и выберите "Export". Выберите формат, в который хотите сохранить и нажмите кнопку  "Export". Предпочтительнее большие файлы - это текстуры. Что вы будете делать дальше - не совсем понятно. В отличие от первой части персонажи не являются цельными, они состоят из отдельных частей. Текстуры будет некуда наложить. На работу с головами может понадобиться очень много оперативной памяти, можно увеличить файл подкачки. 

p.s. файл Common.dpc  из папки Datas лучше подключить в APT_DPC_Tool.

For  ix35
## Post #68
- Username: ChumpyLump54
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 16, 2022 4:14 pm
- Post datetime: 2022-12-12T16:12:18+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

Any news on the repackaging tool?
## Post #69
- Username: Shinteo
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Apr 06, 2016 11:26 am
- Post datetime: 2023-05-19T05:32:53+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

I have extracted the requiem files, and can view apti_tex textures using Noesis. However, apti_msh mesh will crash Noesis. I already updated it to the latest version of 4.466.

Please advice.
## Post #70
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2023-05-20T13:58:10+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

> Reply from Shinteo ↑Fri May 19, 2023 1:32 pm at Fri May 19, 2023 1:32 pm
>
> 
I have extracted the requiem files, and can view apti_tex textures using Noesis. However, apti_msh mesh will crash Noesis. I already updated it to the latest version of 4.466.

Please advice.

Hi, some models from requiem crash noesis, i only can load head model and this is too much ram usage, requiem don't fully support at this time, and not all model loaded, don't have skeleton and other stuff.
## Post #71
- Username: SheetMan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 26, 2020 4:07 pm
- Post datetime: 2023-09-10T15:00:59+00:00
- Post Title: Re: A Plague Tale: Innocence Tool

I tried to find the model of Beatrice De Rune. Through millions of Noesis crashes and through almost every file from COMMON.DCP (I was sure her model located in this .DCP archive) I only found the face texture and nothing more. There was Amica's, Hugo's, Arno's and the other characters head meshes, but not Beatrice, like she wasn't in the game at all. How is it possible? If anybody have any idea where's the Beatrice's model located, let me know please.
