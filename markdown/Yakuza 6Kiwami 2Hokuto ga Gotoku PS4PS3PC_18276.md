## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-06-24T08:39:39+00:00
- Post Title: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

Yakuza 6/Yakuza 0/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC tools.
Supports skinned and static models, level assets. May work with other games.

Drop GMD file onto the tool and it will export model as ASCII and skeleton as SMD.
ASCII will have extended info for correct bone rotations. Noesis plugin that reads them is included.

Up to 3 UV pairs supported in ASCII


cloth and hair bones will also work:



[Yakuza6.rar](https://xentaxbackup.github.io/file/14713_Yakuza6.rar)
## Post #2
- Username: WPH93
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Feb 13, 2017 12:31 am
- Post datetime: 2018-06-24T14:30:50+00:00
- Post Title: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

coooooooooooooool спасибо
## Post #3
- Username: Shinteo
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Apr 06, 2016 11:26 am
- Post datetime: 2018-07-22T22:08:00+00:00
- Post Title: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

I am unable to find the map mesh files. Looking for the Sunshine orphanage specifically. Does anyone have any idea where to get them?
## Post #4
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2018-07-23T10:32:26+00:00
- Post Title: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

> Reply from Shinteo
>
> I am unable to find the map mesh files. Looking for the Sunshine orphanage specifically. Does anyone have any idea where to get them?

Should be in the stage folder as "st_asagao.par".
## Post #5
- Username: CreaseInTime
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 13, 2016 11:59 am
- Post datetime: 2018-08-02T01:43:32+00:00
- Post Title: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

Just attempted to use this with the .gmd files for Yakuza 0 on PC and it crashes, are the files different between PS4 and PC?
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-05T18:09:21+00:00
- Post Title: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

Tool updated. Support for models with 65k+ vertices.
Yakuza 0 support (use be (big endian) version).
Probably will work with any game on that engine now.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-06T06:44:13+00:00
- Post Title: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

a little update:
fixed materials in "be" version
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-08T09:25:48+00:00
- Post Title: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

I have reports that this tool now works with almost all PS3/PS4/PC games on this engine.
## Post #9
- Username: Hatredboy
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jul 21, 2017 7:48 am
- Post datetime: 2018-08-11T05:06:06+00:00
- Post Title: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

> Reply from daemon1
>
> Yakuza 6/Yakuza 0/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC tools.
Supports skinned and static models, level assets. May work with other games.

Drop GMD file onto the tool and it will export model as ASCII and skeleton as SMD.
ASCII will have extended info for correct bone rotations. Noesis plugin that reads them is included.

Up to 3 UV pairs supported in ASCII


cloth and hair bones will also work:

Hi,I love Yakuza game series! I would like to convert Yakuza 5 and Yakuza Kiwami 2 to xps! Although,I'm new around this forum,I need to know how. What is GMD file? I never seen that nor heard of it. Does it not involved Blender or 3d Max? I have downloaded you shared the rar so what do I need to do with it? Please reply me back as you got this!
## Post #10
- Username: Shinteo
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Apr 06, 2016 11:26 am
- Post datetime: 2018-10-19T04:40:13+00:00
- Post Title: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

Currently, the only way is to drag each .gmd one by one? Is there a way to batch process everything?
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-19T15:45:23+00:00
- Post Title: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

use batch command line options, there are many
## Post #12
- Username: Shinteo
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Apr 06, 2016 11:26 am
- Post datetime: 2018-10-19T17:10:29+00:00
- Post Title: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

Another issue. After using Noesis to open the .acsii file and converting them to .obj, there is no corresponding .mtl file. Meaning I have to assign textures manually. Is there a better way to do this part of the operation? I tried converting to fbx, but blender isn't able to open the file then. Said something about the file version is different or somesuch. Convert to .dae, and it doesn't have textures assigned too.

Also, do you happen to know what all those textures correspond to? 
As an example, in one part of c_aw_ayako_materials, the following was found.

sm_4
---------------
0: c_aw_ayako_wear_di
1: c_aw_ayako_wear_mt
2: c_aw_ayako_wear_tn
3: c_aw_ayako_shirt_rd
4: default_z
5: c_com_cottond_rt
6: ---
7: ---

I can find the textures easily enough, but how those textures interact with each other is the unknown part. Does anyone have any idea?
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-19T17:38:27+00:00
- Post Title: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

the tool does not assign textures
## Post #14
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2018-10-24T22:21:07+00:00
- Post Title: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

Sorry,where is the GMD file in Yakuza 0? I have PC version but the only GMD file that i found is on minigame folder. The chara folder and other folder only consist of *.par file extension. When i drag and drop the *.par file into the tools it crash immediately..
## Post #15
- Username: lezisell
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 08, 2012 5:57 pm
- Post datetime: 2018-11-01T07:45:08+00:00
- Post Title: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

I have trouble importing this into 3ds max 2011 x32.



234523452345.png (231.99 KiB) Viewed 2026 times
## Post #16
- Username: Starbrain
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 27, 2017 7:41 pm
- Post datetime: 2018-12-05T13:08:47+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

I have tested the tool with various level assets from Yakuza 0 and a lot of the meshes don't have any uv maps at all, while smaller objects are randomly okay. In another thread someone posted a Blender script for gmd files, but it has massive problems with static meshes, so it isn't an alternative. 
Also, is there any chance for material support in the future? In the par archive, there are simple txt files for each mesh, that list all textures for every material with correct texture names, so maybe this information can be processed somehow.
## Post #17
- Username: graphitero
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 08, 2017 12:23 am
- Post datetime: 2018-12-26T01:33:21+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

There is any 3ds script to import map files from it ?
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-19T12:23:50+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

Fix for some models not working before.
[Yakuza6.rar](https://xentaxbackup.github.io/file/15513_Yakuza6.rar)
## Post #19
- Username: EwwGin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 29, 2019 10:29 pm
- Post datetime: 2019-01-30T19:34:11+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

The attachment is to be inserted into Neosis>plugins>python ya?
yeah.. sor, very new. x)
## Post #20
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-30T23:53:47+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

> Reply from EwwGin
>
> The attachment is to be inserted into Neosis>plugins>python ya?
If your talking about fmt_xps_ascii.py from first post then yes.
Other than that the exe is independent and you use that first to gain access to converted assets.
## Post #21
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2019-07-08T10:25:59+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

Any idea if this tools work for Judge Eyes/Judgment models?
## Post #22
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2019-07-08T11:58:20+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

Nobody has files for that game so no one can test.
## Post #23
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2020-03-10T05:12:22+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

> Reply from Shinteo ↑Fri Oct 19, 2018 12:40 pm at Fri Oct 19, 2018 12:40 pm
>
> 
Currently, the only way is to drag each .gmd one by one? Is there a way to batch process everything?

Hi, write this in notepad then save it as "bat"
Put the file you created where the .gmd files are along with yakuza6.exe by daemon1

```
for %%a in (*.gmd) do Yakuza6 "%%a"
```
## Post #24
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2020-08-15T15:21:12+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

I can confirm the tools with for Judge Eyes/Judgment, atleast for characters, no issues so far.
## Post #25
- Username: KvngJ
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 22, 2020 1:22 pm
- Post datetime: 2020-09-22T05:26:53+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

> Reply from Andelx ↑Sat Aug 15, 2020 11:21 pm at Sat Aug 15, 2020 11:21 pm
>
> 
I can confirm the tools with for Judge Eyes/Judgment, atleast for characters, no issues so far.
Can you convert Yagami's model to a xps or a fbx format to use it in blender?
## Post #26
- Username: foulveins
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Apr 19, 2018 7:19 am
- Post datetime: 2020-11-09T20:29:22+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

Can also confirm these work with Yakuza 7: Like a Dragon.
## Post #27
- Username: Hatredboy
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jul 21, 2017 7:48 am
- Post datetime: 2021-02-04T18:13:20+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

Hey, what about Yakuza & Yakuza 2 HD edition game files eh?
## Post #28
- Username: reanimate
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 16, 2011 2:27 pm
- Post datetime: 2021-07-20T12:03:38+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

> Reply from Shinteo ↑Fri Oct 19, 2018 12:40 pm at Fri Oct 19, 2018 12:40 pm
>
> 
Currently, the only way is to drag each .gmd one by one? Is there a way to batch process everything?
Here's another alternative, put the Yakuza6_exe file and this Bat file in the root folder of the unpacked files ie inside the "tops" folder. This will loop through the folder and convert each gmd file using the tool.

Just replace the [PATH to Yakuza Tool] with the location where you place the tool

```
call :recursiveConvert
goto :eof

:recursiveConvert
rem Do whatever you want here over the files of this subdir, for example:
for %%f in (*.gmd) do "[PATH to Yakuza Tool]\Yakuza6.exe" %%f
for /D %%d in (*) do (
    cd %%d
    call :recursiveConvert
    cd ..
)
exit /b

```
## Post #29
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-09-30T17:39:11+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

The new models/format for the latest Virtua Fighter 5 that was re-done using the Yakuza engine looks awesome (*.par containers, *.gmd models and *.dds textures), and the increase in model/texture quality is quite noticeable compared to previous VF5 versions:




pai.jpg (229.81 KiB) Viewed 255 times
## Post #30
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-09-30T17:41:28+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

pai_face.jpg (136.2 KiB) Viewed 254 times
## Post #31
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-09-30T17:42:03+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

virtua fighter esports.
Animations can be loaded with the same minmode plugin as Project Diva, but with IK settings required.
I've been trying to set the IK for Diva animations for some time, but I haven't tried it successfully.
By the time the Crystalized Rain tutorial was left, everyone seemed to be able to convert it...

The *.gmt animation in the motion folder is a Yakuza file. It's like the wreckage of the transition to the dragon engine.
The animation is called from the vf5 *.farc.

As a first step, put kg_hara_y under n_hara_cp.
By swapping this hierarchy for the time being, the rough motion and root motion will work properly.
The bone with _cp is presumed to be an IK bone, but even if you actually constrain it to ude, te, sune or asi
I don't seem to get good results.
## Post #32
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-09-30T19:04:14+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

> Reply from einherjar007 ↑Fri Oct 01, 2021 1:42 am at Fri Oct 01, 2021 1:42 am
>
> 
virtua fighter esports.
Animations can be loaded with the same minmode plugin as Project Diva, but with IK settings required.
I've been trying to set the IK for Diva animations for some time, but I haven't tried it successfully.
By the time the Crystalized Rain tutorial was left, everyone seemed to be able to convert it...

The *.gmt animation in the motion folder is a Yakuza file. It's like the wreckage of the transition to the dragon engine.
The animation is called from the vf5 *.farc.

As a first step, put kg_hara_y under n_hara_cp.
By swapping this hierarchy for the time being, the rough motion and root motion will work properly.
The bone with _cp is presumed to be an IK bone, but even if you actually constrain it to ude, te, sune or asi
I don't seem to get good results.

I find it kinda annoying that they decided to subdivide all the models THAT much into individual body parts as compared to how it was before
## Post #33
- Username: lezisell
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 08, 2012 5:57 pm
- Post datetime: 2021-10-18T12:48:06+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

Can someone please explain me how to convert Kenzan GMD models (this tool doesn't open them) and extract VF5 models from Y6? Thank you.
## Post #34
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2021-12-11T02:15:18+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

where can the files be found for yakuza judgement be found? i need the game files in order to extract
## Post #35
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2021-12-11T02:16:23+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

i mean lost judgement that is can someone link the game files?
## Post #36
- Username: Mochi655
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 05, 2018 10:59 pm
- Post datetime: 2022-02-20T21:50:48+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

I can't extract this file from Lost Judgment with the program. (bg_oosanbashi_a_01_3f[h])
## Post #37
- Username: foulveins
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Apr 19, 2018 7:19 am
- Post datetime: 2022-02-26T23:28:54+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

> Reply from Mochi655 ↑Mon Feb 21, 2022 5:50 am at Mon Feb 21, 2022 5:50 am
>
> 
I can't extract this file from Lost Judgment with the program. (bg_oosanbashi_a_01_3f[h])

a handful of stages from 7 onwards can't be exported via this, nor the [blender importer](https://github.com/theturboturnip/yk_gmd_io), due to "vertices with bone weights". 

i've brought this up before with the creator of the .gmd blender addon, but unsure if anything came of it as of yet. educated guess is something to do with cloth in those stages -- you won't be able to export the backrooms of the kabuki theater in 7 either
## Post #38
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2022-04-02T19:21:33+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

can i ask after downloading the PAK files from the web what do I do next? is there a batch process im supposed to do with noesis or there some tool i need to access the smd assets?
## Post #39
- Username: HotDaniel
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 02, 2019 9:41 am
- Post datetime: 2023-07-18T02:46:24+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

I know this is an older/dead board but does anyone know how difficult it would be to relink textures without having to manually link every single one?
## Post #40
- Username: foulveins
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Apr 19, 2018 7:19 am
- Post datetime: 2023-08-10T21:51:18+00:00
- Post Title: Re: Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4/PS3/PC

i just do the big brain thing of using either texcop for character models ([https://github.com/Timo654/gmdTexcop](https://github.com/Timo654/gmdTexcop)) or for stages, literally dropping all the textures from texture .par files into the directory where the .gmd is lol
