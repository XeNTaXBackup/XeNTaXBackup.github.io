## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-10-08T14:23:47+00:00
- Post Title: Need help with model format! (.geo.data, .geo.data2, .meshinfo)

Hey guys, sorry to bother, had this really weird issue with these models and I can't get them to import into the Blender Script made by Szkaradek123 years ago. File format is .geo.data, .geo.data2 and .meshinfo. Please help me out, I've searched everywhere and I've been trying to port these since way back in 2012 when I first started porting models from various games.

The game I'm trying to port from is "Oddworld Stranger's Wrath HD", released in 2010 by Oddworld Inhabitants.

Models are mostly map props, static meshes or in a special case, a skeletal mesh of one of the bosses.
I uploaded a .rar file with the models I have trouble with, packed them up nicely, each in their own folder with respective textures converted to .PNG. 
There are 12 models in the pack:
-Cargo Ship
-Boat
-APC

-Dropship

-Dropship (with rockets)

-Hangar Ship

-Flame Turret

-Minecart Turret

-Mortar Turret

-Ball Turret

-Ball Turret (with rockets)

-Elboze Freely


Here's a quick tutorial to get rapidly up to speed with how to use the script:

> 1. install Blender version 249b(32bits) and Python version 26(32bits).
>
> 2. unpack 7z archive and doubleclick file "Blender249.blend"
>
> 3. in Blender Text Window press alt+p and select:
>
> - smb file - it creates new folder *_files
>
> 4. from new folder select file:
>
> - skeleton - we get all textured meshes and bones
>
> - meshinfo - to import geometry if there is any skeleton file
>
> - imageinfo - to convert images
>
> - gr2 - to import animation
>
> 5. if you want import only skeleton, without meshes change line 6 from getAll=1 to getAll=0

Here's a link to the models: [https://mega.nz/#!QFAXxaAB!s2iKOi5hKCJp ... UbN56GCqz0](https://mega.nz/#!QFAXxaAB!s2iKOi5hKCJpuvc-4e6NXuiK0HHKmvsyUUbN56GCqz0)
[Blender249[Oddworld Stranger's Wrath][PC][SMD][2016-06-04].7z](https://xentaxbackup.github.io/file/16870_Blender249[Oddworld Stranger's Wrath][PC][SMD][2016-06-04].7z)
## Post #2
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-10-09T13:41:16+00:00
- Post Title: Need help with model format! (.geo.data, .geo.data2, .meshinfo)

*bump* Any data that seems possible to convert to smd? Any skeletal data anywhere? Or at least a way to export the mesh intact?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-10T17:10:46+00:00
- Post Title: Need help with model format! (.geo.data, .geo.data2, .meshinfo)

> Reply from Pepsee ↑Tue Oct 08, 2019 10:23 pm at Tue Oct 08, 2019 10:23 pm
>
> I uploaded a .rar file with the models I have trouble with
Do you have any .meshinfo sample that extracted correctly? The ones you provided have an empty model.meshList or give an error.

It's near to impossible to debug/trace the script without having a working sample, as simple as this.
## Post #4
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-10-11T11:30:41+00:00
- Post Title: Need help with model format! (.geo.data, .geo.data2, .meshinfo)

Yes, I do: here, in fact: [https://mega.nz/#!gBozEQ6b!Lmg95gHylgry ... Urn8BfShns](https://mega.nz/#!gBozEQ6b!Lmg95gHylgryh1-SAPoabtFXSZS6QlKeTUrn8BfShns)
I included 3 seperate npc folders with .skeleton, .imageinfo and .meshinfo and even .gr2 files that import correctly.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-11T12:36:02+00:00
- Post Title: Need help with model format! (.geo.data, .geo.data2, .meshinfo)

thx! Got the idea of importing vertices and FIs (using hex2obj on paired files):
.



Outlaw_KnifeQuiver.geo.meshinfo.png (38.8 KiB) Viewed 244 times


Now it should become understandable where/why the other .meshinfo/data/data2 files fail on import.
(Guess it's different versions.)
## Post #6
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-10-11T12:52:41+00:00
- Post Title: Need help with model format! (.geo.data, .geo.data2, .meshinfo)

Yeah! The error upon import also takes place on big bundles such as: "lm_level_02_tgl.smb" which may contain some of the data that those models might be searching for? 
Not sure if it's the same issue as for those models, but I uploaded some samples too, just in case, might be of some use to you hopefully:
[https://mega.nz/#!NZwVjSKY!hxIOneKstijz ... sFGxEUZ3zE](https://mega.nz/#!NZwVjSKY!hxIOneKstijzGi1mxgEudfGsG2Fe3SFVRsFGxEUZ3zE)
They seem to be archives containing common/shared assets.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-11T14:09:06+00:00
- Post Title: Need help with model format! (.geo.data, .geo.data2, .meshinfo)

I checked higgins_boat_01.geo.meshinfo (from your opening post?) using hex2obj but the result is not nice:
.



boat_ugly.png (98.24 KiB) Viewed 239 times


Need to recheck when I've more spare time...
## Post #8
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-10-11T14:10:21+00:00
- Post Title: Need help with model format! (.geo.data, .geo.data2, .meshinfo)

Still, that's some great progress! I'll be waiting with huge anticipation to see more of this, thank you so much..
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-18T20:25:29+00:00
- Post Title: Need help with model format! (.geo.data, .geo.data2, .meshinfo)

Those unloadable models have unknown (unk) meshtypes (87 or 120 for example) which are hard to track.
Patching the script is horrible, I stopped it before those unks, so everything after them is lost, even known meshes.

Also it seems that the patching has to be done per model.
.



bossfight_turretcart.png (91.28 KiB) Viewed 200 times
## Post #10
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-10-19T23:04:25+00:00
- Post Title: Need help with model format! (.geo.data, .geo.data2, .meshinfo)

Holy hell, I nearly jumped out of my seat out of joy, that's amazing progress right there!!!
## Post #11
- Username: Fuzzle Guy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 02, 2022 7:50 am
- Post datetime: 2022-08-20T17:49:32+00:00
- Post Title: Need help with model format! (.geo.data, .geo.data2, .meshinfo)

Was a conclusion ever reached on this?

I'm really trying to extract the Live Ammo Nests and anims, but having very little luck.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-20T19:06:41+00:00
- Post Title: Need help with model format! (.geo.data, .geo.data2, .meshinfo)

> Reply from Fuzzle Guy ↑Sun Aug 21, 2022 1:49 am at Sun Aug 21, 2022 1:49 am
>
> 
Was a conclusion ever reached on this?Yeah. Cool script from Mariusz but a shitload of work to patch it for models it was not created to be used with. People generally seem to overread what I wrote:

> Reply from shakotay2 ↑Sat Oct 19, 2019 4:25 am at Sat Oct 19, 2019 4:25 am
>
> Those unloadable models have unknown (unk) meshtypes (87 or 120 for example) which are hard to track.
--------------------------------

> Reply from Fuzzle Guy ↑Sun Aug 21, 2022 1:49 am at Sun Aug 21, 2022 1:49 am
>
> I'm really trying to extract the Live Ammo Nests and anims, but having very little luck.This is because you guys almost always are talking about anims before having a skeleton. Did you care for the bones?
## Post #13
- Username: Fuzzle Guy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 02, 2022 7:50 am
- Post datetime: 2022-08-30T00:24:54+00:00
- Post Title: Need help with model format! (.geo.data, .geo.data2, .meshinfo)

Oh, I didn't over-read it. I'm just very new to 3D - I only started playing with Blender in May. I've learned fast but all this lingo is obviously way above my station at the moment, so I wasn't sure why the unknown meshtypes are hard to track    

The live ammo does have skeletons but importing the gr2 files doesn't seem to do anything. I'm assuming it's a similar issue to the one mentioned in this thread but with animations instead of meshtypes.  So, as best I understand it, if a file doesn't open, it's because data needed for it to run smoothly is hidden within other files ... of which it could be within any?
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-30T05:52:32+00:00
- Post Title: Need help with model format! (.geo.data, .geo.data2, .meshinfo)

> Reply from Fuzzle Guy ↑Tue Aug 30, 2022 8:24 am at Tue Aug 30, 2022 8:24 am
>
> The live ammo does have skeletons but importing the gr2 files doesn't seem to do anything.Parallel to its graphical ui blender 2.49b does open a console window where log lines appear.

btw, guess, you'll need to load a .skeleton file, not a .gr2 file. (dunno about the memory error, see code below)
example npc_16_46.skeleton:

```
0x257L 1 [ 0 ] (737893, 375261130, 0, 20, 16, 1, 1, 1, 1, 3, 0, 0)
0x36dL 2 [ 0 ] (737893, 375261130, 0, 20, 16, 1, 1, 1, 1, 3, 0, 0)
0x489L 3 [ 0 ] (737893, 375261130, 0, 20, 16, 1, 1, 1, 1, 3, 0, 0)
0x59fL 4 [ 0 ] (737893, 375261130, 0, 20, 16, 1, 1, 1, 1, 3, 0, 0)
0x6bbL 5 [ 2 ] (737893, -1373022986, 2, 20, 16, 1, 1, 1, 1, 3, 0, 0)
0x86bL 6 [ 1 ] (1, 1, 1, 1, 3, 0, 0, 1140457472, 1048576000, -1086324736, -1, 0)

Traceback (most recent call last):
  File "starter - turrets-v2.", line 632, in Parser
  File "starter - turrets-v2.", line 234, in meshinfoParser
MemoryError

```

Mariusz' script was designed to work with .skeleton files from Old Generation Files\Original Xbox, afaics.
.



npc_16_46-skeleton.jpg (118.8 KiB) Viewed 94 times



This is a hashlist.txt for npc_16_46.skeleton which I don't remember how it was created:

```
1933479910:wgrndr_rt
50225527:wgrndr_stb
-478461315:wgrndr_spn1
-933883458:wgrndr_spn2
300992683:wgrndr_clvL
1887342079:wgrndr_bcpL
-978192524:wgrndr_clvR
-1539329504:wgrndr_bcpR
-1972955623:wgrndr_lgL
-330876234:wgrndr_shnL
1694896645:wgrndr_nklL
1025623997:wgrndr_bllL
1579559366:wgrndr_lgR
939918697:wgrndr_shnR
-1320735270:wgrndr_nklR
-379520926:wgrndr_bllR
-1420240020:wgrndr_nk
676182801:wgrndr_hd
-531282476:wgrndr_face
2040867814:wgrndr_frmL
-1377561543:wgrndr_frmR
-1779993387:wgrndr_wrstL
1335444843:wgrndr_grbL
1101417226:wgrndr_wrstR
-1680311628:wgrndr_grbR
677665404:wgrndr_grndL
-64658013:wgrndr_grndR
1244016365:wgrndr_jw
-1290459379:wgrndr_lwrLipM
-307225706:wgrndr_mBrwL
972104777:wgrndr_mBrwR
-1510465061:wgrndr_mFng1L
1907957252:wgrndr_mFng1R
617267880:wgrndr_shield
-173511923:wgrndr_tl
356922243:wgrndr_uprLipM
-220404163:grndr_weapnode_melee_wpn1
-819943707:rndr_weapnode_melee_mzzl1
-1810316210:rndr_weapnode_ranged_wpn1
-2127173981:ndr_weapnode_ranged_mzzl1

```
## Post #15
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2023-09-23T13:34:50+00:00
- Post Title: Need help with model format! (.geo.data, .geo.data2, .meshinfo)

Hey, I'm having issues with various formats from both the OG PC Release (OddBoxx release) as well as the Prototype Beta that was released recently (Despite the prototype being somewhat opensource, the formats for models .geo, are still not able to be imported or previewed).

It's frustrating to be stuck here for so long, I've been trying to rip these for the longest time but I've simply been unable to...

[Here is a link to the extracted NPC/Global player bundles from the OG release.](https://mega.nz/file/8V4iGIab#jzJMdWNvYpqdFbMyQLSFUZVNruhPrfxdQN_YuxKsTko)
