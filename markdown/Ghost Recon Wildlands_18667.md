## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-11T17:31:40+00:00
- Post Title: Ghost Recon Wildlands

Ghost Recon Wildlands tool.
Usage:

Step 0: get entities list

Wildlands_list.exe <forge file>

This will output entities list to console. To save it, use this command for example:
Wildlands_list.exe dataPC.forge > entities.txt

Step 1: correct forge.ini file to set which forge files to use and their location.

On the first run, Wildlands_list.exe tool will create a list of assets in all these files. If you change INI, or game will update, you need to delete generated file assets.dat so it will be regenerated.

Note: tool loads FORGE files in order they are listed in INI file, so you have to be sure to put PATCHES FIRST or tool may crash or give incorrect results.

One of DLC files is not compatible with current version, don't add it:DataPC_20_dlc.forge

Step 2: get table tree for some entity (or additionally, create part sets)

Wildlands.exe <entity id>
Wildlands.exe <entity id> <N>
Wildlands.exe <entity id> all

Example: Wildlands.exe 040123B873C > nina.txt
This will output all tables for Nina Flores. For explanation about these tables, see below. You should learn the table tree carefully before trying to export it.

"N" option will generate N random part sets.
"all" option will generate a set big enough to contain every possible part

Step 3: make a .TXT file with what you want to export

After you study the tables, you have to select what you want. You can make comments or change the file as you want. The tool will only use "objects" and "skeletons", all other lines will be ignored. 

You can leave ONE option for each part, or many, but be careful. If you try combining the uncombinable, the result is unpredictable.

The order of skeletons is important. You have to list them in order of the table tree, they will be connected in this order. Like vest connected to main body, then some attach point connected to that vest. Wrong order MAY break them. 

The order of "objects" is not important.

Example file for non-censored version of Nina:

```
044F5D0A89F --> 1e Skeleton GR_UNP_Nina_Head

======= row 100% ======= 040123B8A70 ========
044F5D0ABB5 --> 3 Object UNP_Nina_Body_02
044F5D0AC6C --> e Object UNP_NinaFlores_Shoes
0402FACC80C --> 19 Object UNP_NinaFlores_Eyelashes_LOD0
044F5D0AC04 --> 1 Object UNP_Nina_Head_Chest
04075D34428 --> 12 Object UNP_NinaFlores_Jewelry
044F5D0AC55 --> 2 Object UNP_NinaFlores_Clothes
044F5D0ABE7 --> 13 Object UNP_Nina_EyeTeeth
07C33CC2006 --> 20 Object UNP_Nina_Hair
```

Step 4: export

Wildlands.exe <file.txt>
Drag .TXT file  onto the tool, or run the command above.

This will generate ASCII file with all parts combined. Additional skeletons will be in separate files:
small ASCII will have anim skeleton, SMD will have both animation & mesh skeletons, so applying this as animation you can transform the model to place eyes/teeth/other parts correctly (as shown on these videos [https://youtu.be/IOsBCDMpjXc](https://youtu.be/IOsBCDMpjXc) , [https://youtu.be/hztnjbD07ok](https://youtu.be/hztnjbD07ok)). Don't apply animation to HEAD model, because in most cases it will distort it. Apply only to body/eyes/teeh/weapons.

The fixing process is similar to frostbite face fixing - [https://sta.sh/029zqoqijxmo](https://sta.sh/029zqoqijxmo) (tutorial by Crofty)



You need all skeleton parts and combine them in right order. For example, this one needs 3: main skeleton, head skeleton, and boobs skeleton to work together.



And this combined skeleton is actually working with the model:


[wildlands.rar](https://xentaxbackup.github.io/file/14775_wildlands.rar)
## Post #2
- Username: WPH93
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Feb 13, 2017 12:31 am
- Post datetime: 2018-08-13T05:41:50+00:00
- Post Title: Ghost Recon Wildlands

OMG,it is really amazing.You are so powerful！
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-18T08:52:41+00:00
- Post Title: Ghost Recon Wildlands

Tool is almost finished, adding cloth support and first version will be released this weekend i think.

Meanwhile i'll try explaining how it works, because entity tree in this engine is really complex.

Also I think this will work just the same or with minor changes with all other Anvil games. So I'm starting to gather opinions which game to support next: AC origins, For Honor, Rainbox 6 siege? Maybe something else?
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-18T10:13:16+00:00
- Post Title: Ghost Recon Wildlands

> Reply from daemon1
>
> AC origins, For Honor, Rainbox 6 siege? Maybe something else?
I think AC:Origins or For Honor would be great.
## Post #5
- Username: WPH93
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Feb 13, 2017 12:31 am
- Post datetime: 2018-08-18T10:30:04+00:00
- Post Title: Ghost Recon Wildlands

> Reply from daemon1
>
> Tool is almost finished, adding cloth support and first version will be released this weekend i think.

Meanwhile i'll try explaining how it works, because entity tree in this engine is really complex.

Also I think this will work just the same or with minor changes with all other Anvil games. So I'm starting to gather opinions which game to support next: AC origins, For Honor, Rainbox 6 siege? Maybe something else?
Wow,I think AC Origins would be nice,really like this gameXD.
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-18T10:33:25+00:00
- Post Title: Ghost Recon Wildlands

The structure of Anvil engine entities (concerns most Anvil engine games, at least all latest)

In each game, there is a number of "entities" - characters, weapons, vehicles etc. For example:

```
03F9A402E16    CIV_Worker_craft_M
03F9A402DB7    CIV_Vendor_F
03FBB811130    CIV_Cook_F
03F9A402DD1    CIV_Unoccupied_F
03FBB8110F1    CIV_Cook_M
0FD14BA9B55    RES_ProstitutesNoSwimSuits
07C33C9CBDE    RES_DomesticF
03F9A402E13    CIV_Worker_mine
007F63596F6    GR_PLAYER_Template
11308CA81C4    GR_Avatar_OUTRO
07B1300BC18    UNS_GeneralBajo
07F30225AD2    UNS_MarcusJensen
07ADDE10938    UNS_ElCerebro

```


As you can see, some of them are main characters, and some are generic types of civilians. The main player template is also here.

Now if we look inside of each enitity, there's a whole tree of so called "build tables" to describe it.
Example:

```
asset from package UNS_Antonio
==================================================================================
UNS_Antonio 077639E62A8

3 properties
077639E62A8 (5) 2 default 00000000000 -->
077639E62A8 (5) 3 default 00000000000 -->
077639E62A8 (5) 4 default 00000000000 -->

1 rows
======= row 100% ======= 077639E62A8 ========
077639E6348 --> 2 Table UNS_Antonio_Body
077639E635C --> 3 Table UNS_Antonio_Head
07ADD9005F9 --> 4 Table COMON_MALE

asset from package NPC_MEX_lieutenant_Elite
0132327CC0C Main skeleton
```

This is a root table for Antonio Garcia, we can see it has 3 parts: body, head and some common part, each of them is a table again.
Also there's a link to his base skeleton.

Now if we go down to each part, we can see what it contains:

```
asset from package UNS_Antonio
==================================================================================
UNS_Antonio_Body 077639E6348

6 properties
077639E6348 (5) 2 default 00000000000 -->
077639E6348 (5) 3 default 00000000000 -->
077639E6348 (5) 4 default 00000000000 -->
077639E6348 (5) 5 default 00000000000 -->
077639E6348 (5) 6 default 00000000000 -->
077639E6348 (5) 7 default 00000000000 -->

1 rows
======= row 100% ======= 077639E6348 ========
07A8B300B67 --> 6 Object UNS_Antonio_Santiags
077639E65D9 --> 4 Object UNS_Antonio_Shirt
07A8B300D0C --> 3 Object UNS_Antonio_TorsoPart
077639E65B2 --> 5 Object UNS_Antonio_Jeans
07A8B304568 --> 7 Object UNS_Antonio_HairChest_LOD0
07A8B30152A --> 2 Object UNS_Antonio_Hands
```

Here we can see his body includes "objects" (meshes), namely his boots, shirt, torso, jeans, hands and chest hair.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-18T10:39:42+00:00
- Post Title: Ghost Recon Wildlands

These tables can be simple, but they also can be very complex. So let's check another example:

```
asset from package CIV_Waiter_F
==================================================================================
CIV_FE_shared_Lowerbody 00FF8421BB7

2 properties
00FF8421BB7 (5) 2 default 00000000000 -->
00FF8421BB7 (5) 4 default 00000000000 -->

2 rows
======= row 50% ======= 00FF8421BB7 ========
00FF8421BD9 --> 2 Table CIV_FE_shared_pants
00FF8421C59 --> 4 Table CIV_FE_shared_feet

======= row 50% ======= 00FF8421BB7 ========
00FF8421BDC --> 2 Table CIV_FE_shared_Skirts
00FF8421BDB --> 4 Table CIV_FE_shared_Legs
```

In this example, somewhere on "female waiter" tree there are 2 options:
50% waiters will have pants & feet, and 50% will have skirts & legs.
Each of these is a table again, with all possible combinations of pants and skirts, and there are many.

Why is this important ?

Because anywhere across the tree we can encounter a mesh which needs additional skeleton, and all skeletons introduced in this partucular tree branch, and no others, because others may have different positioned bones with same names.

Like in this example, DJ Perico has a necklace, which requires its own little skeleton, and it can only be properly extracted with all the previous skeletons above the tree:

```
asset from package UNS_DJPerico
==================================================================================
UNS_DJPerico_Accessories 07F30207BBD

4 properties
07F30207BBD (5) 1 default 00000000000 -->
07F30207BBD (5) 2 default 00000000000 -->
07F30207BBD (5) 4 default 00000000000 -->
07F30207BBD (5) 6 default 00000000000 -->

1 rows
======= row 100% ======= 07F30207BBD ========
07F3020B815 --> 1 Object UNS_DJperico_Sunglasses
07F3020B7DB --> 2 Object UNS_DJPerico_Accessories
07F3020BB01 --> 4 Object UNS_DJPerico_Necklace
07F3020BFFD --> 6 Skeleton UNS_DJPericoNecklace_Pendulum
```

As I said before, main player, as expected, has most complex tree with 1000+ tables, about 180 skeletons, and insanely big number of combinations.

One specific variation of npc can have 2-5 skeletons that must be connected together in right order: base body, head, backpack, weapon holster and a few other little things.

Current version of the tool allows to export that all properly with working bones/weights:



This is Sam Fisher player outfit. In addition to body and head, its using a little skeleton for holster:

 

And another skeleton for the back attach points:
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-19T13:05:24+00:00
- Post Title: Ghost Recon Wildlands

Fixed eyes/teeth placing
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-19T18:40:34+00:00
- Post Title: Ghost Recon Wildlands

tool posted
## Post #10
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-19T20:03:13+00:00
- Post Title: Ghost Recon Wildlands

So, I assume in order to get the entities list, I have to drag and drop the forge file I want on top of the windlands_list exe file and after that, it generates the list of the entities to the same folder where the exe is.

Well, for me, it only brings up CMD with some bits of entitiy IDs and then disappears immediately.

I set the forge files' location first to be the one which is my Wildlands' main folder location.

F:/-snip-/common/Wildlands/Forgefilename

And when that didn't work, I copied the forge files to the tool's work folder and set the file path to be the workfolder's. And it didn't work either. I have to be doing something wrong.

I don't have an assets.dat file anywhere.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-19T20:10:25+00:00
- Post Title: Ghost Recon Wildlands

sorry i forgot to mention, list is only printed to console, so to save it, you need to run command like

wildlands_list  datapc.forge  > list.txt

assets.dat will only be created later, when you first try exporting some model
## Post #12
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-19T20:41:30+00:00
- Post Title: Ghost Recon Wildlands

Sorry, I'm kind of a noob with CMD commands. How exactly do I make it so that it outputs the list file to the folder I want after I open up a forge file with the widlands_list.exe file?
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-20T15:35:10+00:00
- Post Title: Ghost Recon Wildlands

```
wildlands_list datapc.forge > list.txt
```


Put this text into a new file called, for example, "0.bat" 
Put this file next to your FORGE, and click on it.
## Post #14
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-20T16:33:55+00:00
- Post Title: Ghost Recon Wildlands

Alright, that worked, I had to put .exe and forge at the ends, but the problem is that it gives me blank results with the main assets folder, which is DataPC.forge.

The files look like this:

```
F:\SteamLibrary\steamapps\common\Wildlands\DataPC
```


```
Wildlands_list.exe DataPC.forge > list.txt
```


It works with DataPC_patch_01.forge, but not with the main assets one.

Edit: Nevermind, I managed to open the main assets folder, but there's probably not even half of the character related meshes listed, such as the "CP, FCP" main character related meshes. Not sure if you have added the support for them or not.
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-20T19:38:03+00:00
- Post Title: Ghost Recon Wildlands

> Reply from MaZTeR
>
> there's probably not even half of the character related meshes listed
This is not a list of MESHES. This is a list of entities. They include ALL of the meshes inside.
For example, CP_ and FCP - are all parts of only one HUGE entity called player_template

Please read the explanation of entity tables in this thread:
[viewtopic.php?p=143324#p143324](http://forum.xentax.com/viewtopic.php?p=143324#p143324)

Also soon I plan to make options to make extract process easier.
## Post #16
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-20T21:40:00+00:00
- Post Title: Re: Ghost Recon Wildlands

Alright I get it now, but what I don't get is that getting the entity tree open requires another batch command, which should reference the main asset archive. And I have no idea how to do that. If I for example copy this line of code:

```
Wildlands.exe DataPC.forge 040123B873C > nina.txt
```


...which you added above and make a new batch file, it simply adds "Reading Forge files..." to that text file instead of giving me the entity tree.

I'm guessing the final tree export to ASCII section also requires a similar command file which needs to reference the DataPC.forge file, so could you also add that command to the bunch?
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-21T04:11:14+00:00
- Post Title: Re: Ghost Recon Wildlands

no, its not required

to get Nina's tree, you have to run command as i said:

```
Wildlands.exe 040123B873C > nina.txt
```
## Post #18
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T08:54:54+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1
>
> no, its not required

to get Nina's tree, you have to run command as i said:
Code: Select allWildlands.exe 040123B873C > nina.txt
Well it doesn't work. It only gives me

```

```


With that entity ID or any to that matter.
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-21T15:41:25+00:00
- Post Title: Re: Ghost Recon Wildlands

what is in your forge.ini file?
## Post #20
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T15:54:31+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1
>
> what is in your forge.ini file?

```
C:\-snip-\Wildlands\DataPC
```


Just that
## Post #21
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T15:57:34+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from MaZTeR
>
> daemon1 wrote:what is in your forge.ini file?
Code: Select allC:\-snip-\Wildlands\DataPC

Just that
Yeah so, adding .forge at the end of DataPC in the forge.ini file fixed the problem, but if i do that before acquiring the entity list, I'm unable to get that list.
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-21T16:15:04+00:00
- Post Title: Re: Ghost Recon Wildlands

forge.ini has absolutely no effect on acquiring the entity list
## Post #23
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T17:19:47+00:00
- Post Title: Re: Ghost Recon Wildlands

Yeah okay so, I managed to list out everything I need from the model I want and export it, but importing it to Blender gives me a line of errors and won't import the model.

This is the content of the text file:

```
07BC85220AA --> 3 Skeleton FCP_Head_Cau_NinaP
079F67C6F95 --> 4 Skeleton FCP_Backpack_Rush24_Position_noVest
079F67C6D9D --> 4 Skeleton FCP_Backpack_Rush24_Position_MediumVestA

======= row 100% ======= 07C33C8D0DD ========
073F1727551 --> c Object FCP_EyeTeeth
07BC8522077 --> 1 Object FCP_Head_Cau_NinaP
07BC852209F --> d Object FCP_EyeLashes_Cau_NinaP
079F67BF2ED --> 1 Object FCP_HairBun
07C33C7BF33 --> 1 Object FCP_Head_HeadSetC
073F172757B --> 1 Object FCP_Torso_FullArms
073F172758D --> 1 Object FCP_Torso_FullArmsNoHANDS
0D385428609 --> 1 Object FCP_Neck_Keffieh_CUSTO
079F67BA510 --> 1 Object CP_Backpack_Rush24
089EC928417 --> 1 Object FCP_Vest_Light511
089EC901C85 --> 1 Object FCP_Visual_A_Sniper_forMediumVest
089EC901AA0 --> 1 Object FCP_Sniper_Comfort_LoadOut_forMediumVest
089EC901B6B --> 1 Object FCP_Grenade_Comfort_LoadOut_forMediumVest
07D86C08900 --> 1 Object FCP_Torso_TankTopA
07D86C0DACE --> 1 Object FCP_Torso_TShirtB
089EC905649 --> 1 Object FCP_Apex_Pants_Holster_KneepadsB
```


The skeletons are in the order as they were originally listed according to their respected numbers of lines.

When I export it, it gives me a 4.21MB big ASCII file as well as a 0kB big SMD file. Also, when it's exporting, it says "Chunk mode not supported".

Edit: Okay I managed to fix the error, I can't apparently export everything at once but only the head and the rest one at a time. However, after I've imported the model to Blender, the skeleton and parts of the head glitch out. I read the Frostbite tool tutorial and did everything up till the import SMD part, except when I do that, the skeleton and model glitch out even further and skipping the frame is no help.

I used this smd import plugin:
[http://steamreview.org/BlenderSourceTools/](http://steamreview.org/BlenderSourceTools/)
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-21T17:46:27+00:00
- Post Title: Re: Ghost Recon Wildlands

You must be able to export all at once.

Player configuration is very complex and its easy to make an error.
You missed skeletons for backpack and holster:

05A633FFE13 Skeleton 2 CP_LegHolster
079F67C6D8B Skeleton 5 FCP_Backpack_Rush24
079F67C73D1 Skeleton 4 FCP_Backpack_Rush24_Position_HeavyVestA

also no legs:
## Post #25
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-21T17:49:22+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from MaZTeR
>
> and skipping the frame is no help.

in this SMD you have to skip 10 frames because i did animation 10 frames long
## Post #26
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T18:04:01+00:00
- Post Title: Re: Ghost Recon Wildlands

Oh, didn't know that. Also, my character should have feet called "FCP_Feet_ShoesA" but I couldn't find them from anywhere.
## Post #27
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T18:08:14+00:00
- Post Title: Re: Ghost Recon Wildlands

I did everything, but it still the entire model looks distorted at frame 10 when I apply the SMD animation to the Amature skeleton root (not the entire model group which is also called the same).

Not sure if it's because I used the SMD importer meant for Source SMDs but I don't think it really matters.
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-21T18:11:41+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from MaZTeR
>
> my character should have feet called "FCP_Feet_ShoesA"
why? there's no model called like that

skeleton must not glitch. if it is, you probably selected wrong skeletons
its hard to say without picture
## Post #29
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T18:14:06+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1
>
> MaZTeR wrote:my character should have feet called "FCP_Feet_ShoesA"
why? there's no model called like that

skeleton must not glitch. if it is, you probably selected wrong skeletons
its hard to say without picture
Apparently they're called "Hiking Shoes" or "Hiking Boots", in Archive_Next they're called "ShoesA".

As for the skeleton, I'll send an image asap.
## Post #30
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T18:16:47+00:00
- Post Title: Re: Ghost Recon Wildlands

Here:


I applied the SMD to the Armature thing before the bone 2C52
## Post #31
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T18:18:05+00:00
- Post Title: Re: Ghost Recon Wildlands

Also, there shouldn't be any wrong skeletons as those were the ones only available. The same issue occurs if I do the same with only the head model + head and main skeleton.
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-21T18:28:30+00:00
- Post Title: Re: Ghost Recon Wildlands

there's only one model named similar: CP_Feet_ShoesA
and they are not used with player:

```
==================================================================================
UNI_sniper_LOWERBODY 047EE65DAA5

2 properties
047EE65DAA5 1 type 5
047EE65DAA5 3 type 5

3 rows
========== row 047EE65DAA5 ==========
03E5D6FF093 Object 3 CP_Feet_ShoesC
0484990A710 Object 1 uni_pantsAH_KP1A

========== row 047EE65DAA5 ==========
014D78B461F Object 3 CP_Feet_ShoesA
0484990A761 Object 1 uni_pantsAL

========== row 047EE65DAA5 ==========
014D78B461F Object 3 CP_Feet_ShoesA
0484990A744 Object 1 uni_pantsAL_KP1B

```


as for skeleton, its really heavily messed up, you did something wrong
it must be looking fully correct even before animation
## Post #33
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T18:34:53+00:00
- Post Title: Re: Ghost Recon Wildlands

I can't figure this out, linking the exported model plus the playertemplate and my own model tree text file here:

[http://www.mediafire.com/file/s9fqkdh8h ... y.zip/file](http://www.mediafire.com/file/s9fqkdh8h69so87/gr_wildlands_ninap_sparky.zip/file)

I forgot to add a hat and glasses earlier which I included in this one.

In the mean time, I'll try searching if I did something wrong with one of the skeletons
## Post #34
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-21T18:52:48+00:00
- Post Title: Re: Ghost Recon Wildlands

sorry i forgot to mention one important thing about player template

since its using male/female/child skeletons, you have to remove main skeleton from 1st line, and use one of these instead:

```

3 properties
07ADD901856 2 type 5
07ADD901856 3 type 2
07ADD901856 4 type 4

3 rows
========== row 07ADD901856 ==========
07834C47958 Table 2 tag_MAL
0132327CC0C Skeleton 3 GR_PC_Skeleton_Average
00000000003  4 ---

========== row 07ADD901856 ==========
07834C47957 Table 2 tag_FEM
00EA138A544 Skeleton 3 GR_PCF_Skeleton_Average
00000000003  4 ---

========== row 07ADD901856 ==========
07ADD9024BD Table 2 tag_CHILD
066A0086957 Skeleton 3 Child_Skeleton
00000000003  4 ---

```


also about applying animation, i think you can't load SMD upon existing ascii skeleton here
because by default ascii and SMD have different UP axis.

so load ASCII, remove its skeleton completely
load SMD, align them, so they will be both standing
then connect ASCII to SMD

sorry i'm very busy adding texture support, i can't explain it in details now
## Post #35
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T19:06:14+00:00
- Post Title: Re: Ghost Recon Wildlands

No problem about the texture support, I can get everything from Archive_Next since apparently it extracts the textures in the highest quality available. The only thing that however would be nice is if it would be possible to apply the camo feature on the base textures as well as the different iris colors for the eye texture without actually editing the textures themselves.

As for the other things mentioned, I'll see if they work for me.
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-21T19:16:34+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from MaZTeR
>
> I can get everything from Archive_Next
you can get new DLC textures with it?
## Post #37
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T19:21:31+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1
>
> MaZTeR wrote:I can get everything from Archive_Next
you can get new DLC textures with it?
If by DLC you mean the new Icons they added in the latest operation (and the icons in general), then yes.
## Post #38
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-21T19:36:47+00:00
- Post Title: Re: Ghost Recon Wildlands

i mean DLC player textures, for example sam fisher outfit
## Post #39
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T19:39:43+00:00
- Post Title: Re: Ghost Recon Wildlands

Yeah the Sam Fisher outfit textures I believe can be extracted. I haven't tried but I don't see why they couldn't be.

Also, I can't figure this out. I used the text file I linked, only that I changed the Main Skeleton from the first line to 
```
00EA138A544 Skeleton 3 GR_PCF_Skeleton_Average
```


And then I first tried the same method as before and the model glitched out as well as the method you mentioned, except after I removed the Armature and imported the SMD, the bones exploded everywhere. Plus I don't think there's a way to import just the skeleton after, unless I have to use the skel.ascii file, to which Blender gives me an error whenever I try importing that.

I'm not that great with Blender in general, just used it to import the Archive_Next models to Max before 

The text file is here:

```
07BC85220AA --> 3 Skeleton FCP_Head_Cau_NinaP
05A633FFE13 Skeleton 2 CP_LegHolster

======= row 100% ======= 07C33C8D0DD ========
073F1727551 --> c Object FCP_EyeTeeth
07BC8522077 --> 1 Object FCP_Head_Cau_NinaP
07BC852209F --> d Object FCP_EyeLashes_Cau_NinaP
079F67BF2ED --> 1 Object FCP_HairBun
07C33C7BF33 --> 1 Object FCP_Head_HeadSetC
03BD501CAB8 --> 1 Object CP_HeadGear_BoonieA
07D86C12AD6 --> 1 Object CP_HeadGear_TacGlassesA
073F172757B --> 1 Object FCP_Torso_FullArms
0D385428609 --> 1 Object FCP_Neck_Keffieh_CUSTO
089EC928417 --> 1 Object FCP_Vest_Light511
089EC901C85 --> 1 Object FCP_Visual_A_Sniper_forMediumVest
089EC901AA0 --> 1 Object FCP_Sniper_Comfort_LoadOut_forMediumVest
089EC901B6B --> 1 Object FCP_Grenade_Comfort_LoadOut_forMediumVest
07D86C08900 --> 1 Object FCP_Torso_TankTopA
07D86C0DACE --> 1 Object FCP_Torso_TShirtB
089EC905649 --> 1 Object FCP_Apex_Pants_Holster_KneepadsB
07C33C6D12F --> 1 Object CP_Shoes_HikingShoes
```


I removed the backpack options because there seemed to be way too many skeletons for it, gonna have to sort out the proper ones later:
## Post #40
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-21T19:45:45+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from MaZTeR
>
> Yeah the Sam Fisher outfit textures I believe can be extracted. I haven't tried but I don't see why they couldn't be.
try that. I dont think archive next can even open new forge files
## Post #41
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T20:16:03+00:00
- Post Title: Re: Ghost Recon Wildlands

I updated the zip file with a new text file of the player model's tree, which contains the proper main player skeleton as well as organized backpack skeletons:
[http://www.mediafire.com/file/s9fqkdh8h ... y.zip/file](http://www.mediafire.com/file/s9fqkdh8h69so87/gr_wildlands_ninap_sparky.zip/file)

I'll try applying the animations one more time today, if that doesn't work, I'm going to manually rotate the skeleton and applying the proper weights on it on Max.
## Post #42
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T20:22:05+00:00
- Post Title: Re: Ghost Recon Wildlands

Nah, still didn't work. I'm going to try to export the non-fixed version of the model to Max and see if I can get it working there, which I doubt without removing the weights and reapplying them, which also forces me to manually adjust the incorrectly placed head meshes.
## Post #43
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-21T20:31:22+00:00
- Post Title: Re: Ghost Recon Wildlands

when loading SMD skeleton in blender, change setting to "new armature" and bones will not explode
## Post #44
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-21T20:44:19+00:00
- Post Title: Re: Ghost Recon Wildlands

I've been wondering, could this be because I have an incorrect version of the ASCII/SMD importers? I'm fairly certain I have the latest version of both, but if you don't have and you've set the tool to support some older version, I can only import the files with that spesific version of XNALara/SMD format importers.

Also, I can't figure out where I can set the "New Armature" to the SMD armature after I've deleted the ASCII skeleton from the scene.
## Post #45
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-22T04:44:02+00:00
- Post Title: Re: Ghost Recon Wildlands

i dont think its the version

> Reply from MaZTeR
>
> Also, I can't figure out where I can set the "New Armature" to the SMD armature after I've deleted the ASCII skeleton from the scene.

its on the left, after you click "import SMD"
## Post #46
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-22T09:22:15+00:00
- Post Title: Re: Ghost Recon Wildlands

Earlier you said I need to connect the ASCII to SMD, presumably meaning the object to armature. How do I exactly do that?

Edit: If I first select both the skeleton and the objects, press CTRL+P and apply "Armature deform", this is the result with the face after setting the scene to keyframe 10:


This is the text file

```
07BC85220AA --> 3 Skeleton FCP_Head_Cau_NinaP
05A633FFE13 --> 2 Skeleton CP_LegHolster
079F67C6F95 --> 4 Skeleton FCP_Backpack_Rush24_Position_noVest
079F67C6D8B --> 5 Skeleton FCP_Backpack_Rush24
079F67C6D9D --> 4 Skeleton FCP_Backpack_Rush24_Position_MediumVestA

======= row 100% ======= 07C33C8D0DD ========
073F1727551 --> c Object FCP_EyeTeeth
07BC8522077 --> 1 Object FCP_Head_Cau_NinaP
07BC852209F --> d Object FCP_EyeLashes_Cau_NinaP
079F67BF2ED --> 1 Object FCP_HairBun
07C33C7BF33 --> 1 Object FCP_Head_HeadSetC
03BD501CAB8 --> 1 Object CP_HeadGear_BoonieA
07D86C12AD6 --> 1 Object CP_HeadGear_TacGlassesA
073F172757B --> 1 Object FCP_Torso_FullArms
0D385428609 --> 1 Object FCP_Neck_Keffieh_CUSTO
079F67BA510 --> 1 Object CP_Backpack_Rush24
089EC928417 --> 1 Object FCP_Vest_Light511
089EC901C85 --> 1 Object FCP_Visual_A_Sniper_forMediumVest
089EC901AA0 --> 1 Object FCP_Sniper_Comfort_LoadOut_forMediumVest
089EC901B6B --> 1 Object FCP_Grenade_Comfort_LoadOut_forMediumVest
07D86C08900 --> 1 Object FCP_Torso_TankTopA
07D86C0DACE --> 1 Object FCP_Torso_TShirtB
089EC905649 --> 1 Object FCP_Apex_Pants_Holster_KneepadsB
07C33C6D12F --> 1 Object CP_Shoes_HikingShoes
```


I tried it both with

```
00EA138A544 --> 3 Skeleton GR_PCF_Skeleton_Average
```


and 

```
0132327CC0C Main skeleton
```
## Post #47
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2018-08-22T10:43:29+00:00
- Post Title: Re: Ghost Recon Wildlands

Well..

> Reply from id-daemon
>
> 
Don't apply animation to HEAD model, because in most cases it will distort it.
## Post #48
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-22T10:47:40+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from o0Crofty0o
>
> Well..
id-daemon wrote:
Don't apply animation to HEAD model, because in most cases it will distort it.
Oh yeah forgot about that part, but I still don't know how to NOT apply the animations along with the skeleton. As I said earlier, I'm not good with Blender.
## Post #49
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2018-08-22T11:56:07+00:00
- Post Title: Re: Ghost Recon Wildlands

Daemon linked this tutorial: [https://sta.sh/029zqoqijxmo](https://sta.sh/029zqoqijxmo)
On your screenshot you already did step 1-3 so follow it from step 4 but do not 'Apply' on head (and if theres other parts that break with the animation)
## Post #50
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-22T12:31:59+00:00
- Post Title: Re: Ghost Recon Wildlands

Nevermind, I'm able to fix the default pose problems and whatnot on 3D Max.
## Post #51
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-22T14:44:44+00:00
- Post Title: Re: Ghost Recon Wildlands

I managed to get my model but I noticed some issues with the weights. And it's something I have to fix myself.

Some of the weights are very sloppy and even I have done better job in my SFM port of the Archive_Next version. The only thing that I'd perhaps take is the head and the backpack. However, even some of the weights on the head are very sloppy, they definetly were meant for headrigs and not for something like this. It has more bones than my version does, so I might just use this one as a reference and copy the UVs to the ones that were broken.
## Post #52
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-22T15:27:35+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from MaZTeR
>
> Some of the weights are very sloppy
These are the weights used in game. If they are sloppy for you, no problem.
## Post #53
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-22T15:54:50+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1
>
> MaZTeR wrote:Some of the weights are very sloppy
These are the weights used in game. If they are sloppy for you, no problem.
Yeah I know, I'm going to intergrate some of the stuff from the new model to my older one and leave the weights I did be.
## Post #54
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-22T20:15:35+00:00
- Post Title: Re: Ghost Recon Wildlands

The new version is on final testing.



New options:
- texture support (all textures used in model exported automatically)
- sets of complete models generated (by tables)
- random sets of models generated (by tables)
- if you make custom set (as before) you don't have to move skeletons to the top anymore
## Post #55
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-23T17:19:57+00:00
- Post Title: Re: Ghost Recon Wildlands

New version published (at first post)

All old features remains the same, with one improvement:
- if you make custom .TXT file (parts set) you don't have to move skeletons to the top anymore

New options:

1. texture support
All textures used in model will be exported to the folder called the same as .TXT file

2. Sets generation
Since table structure may be hard to understand, i added some options for automatic generation of correct entity combinations, which are available when exporting the table tree.

```
Wildlands.exe 07B1DE15496
```
- if you run Wildlands.exe like before, giving it entity code, it will output all tables, but also create one "zero" set, will fully correct .TXT file combining all variations set to first option.

```
Wildlands.exe 07B1DE15496 15
```
- if you use 2nd parameter as number N, it will output all tables, but also create a set of "N" .TXT files containing random sets of combinable parts. All these sets will be correct entities accorging to the tables. You can export these as well as your manually combined .TXT files. This is useful as examples to make your own sets.

```
Wildlands.exe 07B1DE15496 all
```
- if you use 2nd parameter "all", it will output all tables, but also create a set of .TXT files big enough so they will contain every possible combinable part at least in one of the sets. Again, all these sets will be correct entities accorging to the tables. This is useful for people who like to see all possible parts exported.

These "all" combinations of course will not represent all possible combinations of all parts. If we could count, for example, main player options, it would give us probably a million possibilities. Using this option on main player exports 888 files. But every hat, every jacket and backpack will be somewhere in them in correct combination. I mean where will be no model with male head and female body, because its not allowed by the tables.
## Post #56
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-24T15:56:57+00:00
- Post Title: Re: Ghost Recon Wildlands

I've been trying to extract the Santa Blanca leaders and for some reason, I can't export El Sueño, it only exports an empty SMD file and the dat file. Here's the content of the table:

```
041762FB17A Skeleton UNP_Sueno_Head
04303D6871B Skeleton GR_UNP_SuenoCrucifix
012AFB76CCC Skeleton GR_PC_AddonHolsters
0168CB82895 Skeleton GR_PC_AddonProps
012AFB76CC2 Skeleton GR_PC_AddonFakeGun
	
======= row 100% ======= 041762FB0CE ========
07C33C7AF5A Object   UNP_Sueno_Head
07C33C7AFEB Object   UNP_Sueno_EyeTeeth
07C33C7AFF7 Object   UNP_Sueno_Eyelashes
0465A013FCE Object   UNP_Sueno_Necklace
07C33C7AFD9 Object   UNP_Sueno_Hands
0473AF40639 Object   UNP_Sueno_Jacket
0465A013F6C Object   UNP_Sueno_Shoes
07C33C7B013 Object   UNP_Sueno_Pants
```
## Post #57
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-24T19:31:31+00:00
- Post Title: Re: Ghost Recon Wildlands

sueno exports fine here. both on old and newest game versions.
## Post #58
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-24T22:25:30+00:00
- Post Title: Re: Ghost Recon Wildlands

I solved the issue, but there seems to be an issue with the coordinates of the head bones of Sueño. The eyes and the eyelashes do not align properly when I include the SMD meanwhile the teeth seem to work just fine.
## Post #59
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-25T05:30:18+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from MaZTeR
>
> I solved the issue
how did you solve it?
i need it to understand how to solve eyelashes
## Post #60
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-25T09:38:19+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1
>
> MaZTeR wrote:I solved the issue
how did you solve it?
i need it to understand how to solve eyelashes
You mean how I exported the model? I just  moved the sueno text file next to the Wildlands.exe file, but I think you knew this already.

The tool creates a seperate folder for each model set table, which prevents from just moving and dropping the text files onto the .exe because they're in different folders and they need to be in the same folder all the time.

Don't think this information helps with the eyelash issue in any way, but you gotta make it so that the tool exports properly if the trees are in seperate sub-folders but in the same main directory as the tool.
## Post #61
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-25T10:20:01+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from MaZTeR
>
> but I think you knew this already
no, i didn't know why it crashed, because i didn't know how you were running it

and yes, it will not help with eyelashes.
right now i found one trick that can position his eyes closer to proper point, but still a bit incorrect

are there any other models that have this issue?
## Post #62
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-08-25T13:24:49+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1
>
> MaZTeR wrote:but I think you knew this already
no, i didn't know why it crashed, because i didn't know how you were running it

and yes, it will not help with eyelashes.
right now i found one trick that can position his eyes closer to proper point, but still a bit incorrect

are there any other models that have this issue?
As of right now, I haven't seen any other model other than Sueño to have this issue.
## Post #63
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-10-18T15:13:48+00:00
- Post Title: Re: Ghost Recon Wildlands

Was wondering if this supports the extraction of level geometry, since Archive_Next is unable to do that. I was thinking about getting the masoleum interior from the final cinematic cutscene.
## Post #64
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-10-24T19:20:50+00:00
- Post Title: Re: Ghost Recon Wildlands

Been trying to get the Tar-21 but it always breaks during export, no matter what I do.

I've tried the table it gives me automatically labeled "0" as well as a custom one with only duplicates removed.

Here's my custom one:

```

079B66153E3 --> 2 Skeleton W_ASR_TAR21_BarrelMedium
079B66153E0 --> 2 Skeleton W_ASR_TAR21_BarrelShort
0B145420570 --> 2 Skeleton W_ASR_TAR21_coversides
079B661540E --> 2 Skeleton W_ASR_TAR21_laserATPIAL
079B66153E6 --> 2 Skeleton W_ASR_TAR21_Muzzle
079B66153EE --> 3 Skeleton W_ASR_TAR21_suppressor
079B66153EA --> 2 Skeleton W_ASR_TAR21_compensator
079B66153DC --> 2 Skeleton W_ASR_TAR21_magazine
079B6615404 --> 2 Skeleton W_ASR_TAR21_scope_EXPS3
079B6615400 --> 2 Skeleton W_ASR_TAR21_scope_compM4
079B6615408 --> 2 Skeleton W_ASR_TAR21_scopeEXPS3_Mag
07937A2A86F --> 2 Skeleton W_ASR_TAR21_scopeSpecter
099716D77D3 --> 2 Skeleton W_ASR_TAR21_scope_Reflex
099716D77D7 --> 2 Skeleton W_ASR_TAR21_scope_MicroT1
099716D77E1 --> 2 Skeleton W_ASR_TAR21_scope_Kobra
099716D77EB --> 2 Skeleton W_ASR_TAR21_scope_PK-AS
099716D77DB --> 2 Skeleton W_ASR_TAR21_scope_MicroT1_wMAG
099716D77E5 --> 2 Skeleton W_ASR_TAR21_scope_Kobra_wMAG
099716D782F --> 2 Skeleton W_ASR_TAR21_scope_ACOG
079B66153FD --> 2 Skeleton W_ASR_TAR21_ironsights
0B145420573 --> 2 Skeleton W_ASR_TAR21_coverbottom
079B66153F3 --> 2 Skeleton W_ASR_TAR21_foregrip
10EA3502C26 --> 2 Skeleton W_ASR_TAR21_Foregrip_V4
099716F0863 --> 2 Skeleton W_ASR_TAR21_GL1
1016C7670A2 --> 2 Skeleton W_ASR_TAR21_angledForegripV2




079B66152C2 --> 2 Object W_ASR_TAR_Body

079B66152CA --> 1 Object W_ASR_TAR_Barrel

079B66152C6 --> 1 Object W_ASR_TAR_Barrel_short

09971660908 --> 1 Object W_AT_Railcover_Large_Right

03C3F699FFD --> 1 Object W_AT_ATPIAL_laser
1016C70CB0D --> 1 Object W_AT_laser_3DOT

1016C70CB28 --> 1 Object W_AT_rangefinder

079B66152BE --> 1 Object W_ASR_TAR_FlashHider

03C3F699FD5 --> 1 Object W_AT_compensator

079B66152BE --> 1 Object W_ASR_TAR_FlashHider

1016C70CB43 --> 1 Object W_AT_Compensator_V2_556

09971665A94 --> 1 Object W_AT_STANAG_Short

03C3F69A1FA --> 1 Object W_CAR_M4A1_magazine

099716658C3 --> 1 Object W_AT_Stanag_long

0506086DC1D --> 1 Object W_AT_EXPS3-4

0506086C376 --> 1 Object W_AT_scopeCompM4_Sliced
05095FDE4E9 --> 1 Object W_AT_EXPS3-4_withMagnifier
07FD7C0749A --> 1 Object W_AT_scopeSpecterDR
03C3F69A511 --> 1 Object W_AT_scopeReflex_AC11704
07FD7C08F9A --> 1 Object W_AT_scopeMicroT1
07937A28392 --> 1 Object W_AT_scopeKobra
07FD7C09E0B --> 1 Object W_AT_scopePKAS
07937A2D20D --> 1 Object W_AT_scopeMicroT1_withMagnifier
07937A34301 --> 1 Object W_AT_Kobra_withMagnifier
03C3F69A562 --> 1 Object W_AT_scopeAcog_TA31H
079B66152BA --> 5 Object W_ASR_TAR_Ironsights_Folded
079B66152B6 --> 5 Object W_ASR_TAR_Ironsights_Unfolded
0997166090C --> 1 Object W_AT_Railcover_Small_Bottom
03C3F69A011 --> 1 Object W_AT_foregrip_RVG
07FD7C0C64F --> 1 Object W_AT_foreGrip_HK121
1016C70CABB --> 1 Object W_AT_foregrip_V3
1016C70CAD7 --> 1 Object W_AT_foregrip_V4
099716F0892 --> 1 Object W_AT_GL1
1016C70CAF2 --> 1 Object W_AT_Angled_ForeGrip_V2

```


And here's the one it gives me automatically:

```
079B66152C2 Object   W_ASR_TAR_Body
079B66153E3 Skeleton W_ASR_TAR21_BarrelMedium
079B66152CA Object   W_ASR_TAR_Barrel
0B145420570 Skeleton W_ASR_TAR21_coversides
09971660908 Object   W_AT_Railcover_Large_Right
079B66152BE Object   W_ASR_TAR_FlashHider
079B66153E6 Skeleton W_ASR_TAR21_Muzzle
079B66153EE Skeleton W_ASR_TAR21_suppressor
079B66153DC Skeleton W_ASR_TAR21_magazine
09971665A94 Object   W_AT_STANAG_Short
0506086DC1D Object   W_AT_EXPS3-4
079B6615404 Skeleton W_ASR_TAR21_scope_EXPS3
079B66153FD Skeleton W_ASR_TAR21_ironsights
079B66152BA Object   W_ASR_TAR_Ironsights_Folded
0B145420573 Skeleton W_ASR_TAR21_coverbottom
0997166090C Object   W_AT_Railcover_Small_Bottom
079B66153D4 Skeleton W_ASR_TAR21_body

```


Edit: As for the custom one, I forgot to mention I tried to include and exclude the Main skeleton called 000000000 and it didn't work either.
## Post #65
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-24T19:44:54+00:00
- Post Title: Re: Ghost Recon Wildlands

i dont know what are you doing there.



here's 0 variant, works fine for me
skeleton must never be 00000000000

```
03F45CA2F26 Object   WG_AT_scopeCompM4_LOD0
079B6613207 Skeleton WG_ASR_TAR21_scope_COMPM4
03F45CA2F43 Object   WG_AT_ATPIAL_laser_LOD0
079B661321E Skeleton WG_ASR_TAR21_laserAPTIAL
079B66131F7 Skeleton WG_ASR_TAR21_Ironsights
079B6613142 Object   WG_ASR_TAR21_Ironsight_folded_LOD0
079B66131E9 Skeleton WG_ASR_TAR21_Magazine
09971665F59 Object   WG_AT_STANAG_Short_LOD0
079B66131E4 Skeleton WG_ASR_TAR21_trigger
07937A0BA3F Object   WG_AT_TriggerSingle_LOD0
03F45CA2F3E Object   WG_AT_SmallCalibreCompensator_LOD0
079B6613203 Skeleton WG_ASR_TAR21_Compensator
079B66131ED Skeleton WG_ASR_TAR21_Barrel_Short
079B661312E Object   WG_ASR_TAR21_Barrel_Short_LOD0
0B14542056C Skeleton WG_ASR_TAR21_coverbottom
099716606C7 Object   WG_AT_Railcover_Small_Bottom_LOD0
079B66131E0 Skeleton WG_ASR_TAR21_Body
079B6613133 Object   WG_ASR_TAR21_Body_LOD0
079B6613138 Object   WG_ASR_TAR21_Trigger_LOD0

```
## Post #66
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-10-24T19:52:52+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1
>
> i dont know what are you doing there.



here's 0 variant, works fine for me
skeleton must never be 00000000000
Code: Select all03FD2748BA8 Skeleton W_Gunsmith_BaseWeapon
03F45CA2F26 Object   WG_AT_scopeCompM4_LOD0
079B6613207 Skeleton WG_ASR_TAR21_scope_COMPM4
03F45CA2F43 Object   WG_AT_ATPIAL_laser_LOD0
079B661321E Skeleton WG_ASR_TAR21_laserAPTIAL
079B66131F7 Skeleton WG_ASR_TAR21_Ironsights
079B6613142 Object   WG_ASR_TAR21_Ironsight_folded_LOD0
079B66131E9 Skeleton WG_ASR_TAR21_Magazine
09971665F59 Object   WG_AT_STANAG_Short_LOD0
079B66131E4 Skeleton WG_ASR_TAR21_trigger
07937A0BA3F Object   WG_AT_TriggerSingle_LOD0
03F45CA2F3E Object   WG_AT_SmallCalibreCompensator_LOD0
079B6613203 Skeleton WG_ASR_TAR21_Compensator
079B66131ED Skeleton WG_ASR_TAR21_Barrel_Short
079B661312E Object   WG_ASR_TAR21_Barrel_Short_LOD0
0B14542056C Skeleton WG_ASR_TAR21_coverbottom
099716606C7 Object   WG_AT_Railcover_Small_Bottom_LOD0
079B66131E0 Skeleton WG_ASR_TAR21_Body
079B6613133 Object   WG_ASR_TAR21_Body_LOD0
079B6613138 Object   WG_ASR_TAR21_Trigger_LOD0
By the look of it, there are apparently two versions of this, the one I tried to use and the one you used with the beginning WG. I guess the one you used is the one used in the gunsmith, but what is the one I tried to use? I guess it's the world model that is supposed to be connected to the player, I'm not sure.

Edit: The one I used is from DataPC archive and apparently the one you picked up is from DataPC_Extra archive. I'm not sure why the first one doesn't work.
## Post #67
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-24T20:08:12+00:00
- Post Title: Re: Ghost Recon Wildlands

There's no Tar21 in DataPC archive
## Post #68
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-10-24T20:12:25+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1
>
> There's no Tar21 in DataPC archive
Yeah there is, it's called "079B661536E	W_ASR_TAR-21" and it even exported everything, although the positioning of every single piece was incorrect.
## Post #69
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-10-24T21:35:56+00:00
- Post Title: Re: Ghost Recon Wildlands

Okay I'm really confused with this one.

I found the one you opened, however, I can't get it working  at all. Importing the SMD doesn't help because if I append it to the target, the bones mess up and if I apply it as an armature, the objects won't even move when the timeline in moved forward. It doesn't work at all as it does with the character models.
## Post #70
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-25T15:22:44+00:00
- Post Title: Re: Ghost Recon Wildlands

as you can see on the picture, SMD does work. I can't look into the files now.
## Post #71
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-10-28T11:06:30+00:00
- Post Title: Re: Ghost Recon Wildlands

I have a problem, I'm trying to export once again the older models,  but the mesh doesn't even stick to the smd skeleton in any way, no matter if i remove the old armature or leave it intact as well as select only the skeleton or both the skeleton and the mesh. Making the smd as a new armature ends up with the same result and appending it to a target breaks the entire model.

I could really use a video tutorial for getting this tool working properly on Blender.
## Post #72
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-10-29T13:00:27+00:00
- Post Title: Re: Ghost Recon Wildlands

I found out something about the weapons:

It seems that the weapons labeled with the beginning "W_" inside DataPC archive are the LOD models found in the game, which use lower detail versions of the standard models. Some attachments also are "sliced", so they dont even have the full models. The ones inside DataPC_Extra archive with the beginning "WG_" are the ones found from the Gunsmith, which also have much higher detail models. However, it seems that the skeleton found in DataPC_Extra uses incorrect skeleton, as some models become displaced even with the SMD in use, however, with the DataPC skeleton, the models corresponding with the DataPC extra ones will have proper coordinates.

I'm going to try to use the skeleton found from DataPC on the models found in the DataPC_extra archive and see if that fixes the incorrect coordinates.

Edit: No actually, the "W_" weapon models are the models you see in first person mode, hence the reason why some of the models are "sliced".

Edit 2: Alone, the skeletons inside the DataPC archive do not work with the gunsmith models. The skeletons inside DataPC and DataPC_Extra have to be combined so that the WG_XXX -models work properly. However, still some of the models have incorrect coordinates and there's nothing I can do. The initial locations of the models are the reason for that. For example, the short STANAG magazine is way out of place and most of the sights as well.
## Post #73
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-12-05T12:35:21+00:00
- Post Title: Re: Ghost Recon Wildlands

Any idea what skeleton the object "CP_Head_ShortBeard" is supposed to use?

I've tried the head skeleton of the model I'm trying to get, as well as the combinations of that and Main Skeleton, the head skeleton + skeleton "CP_Male_Beard" and finally the head skeleton + skeleton "CP_Male_Beard" and skeletons:
0DDBB68DE36 --> c Skeleton CP_Beard_Memhet
079F67E4237 --> c Skeleton CP_Beard_Cesar
079F67E41BA --> c Skeleton CP_Beard_Afro_Ico
079F67E42E0 --> c Skeleton CP_Beard_Hisp_Ico
0DDBB69079D --> c Skeleton CP_Beard_JustinP

...and none worked. The beard always glitches out completely, and it looks like the reason for it is because the vertices that glitch out are pulled toward the rest pose of the mesh. There should be an additional bone which gets pulled to the center of the head, which is affected by the animation and also affects the non-affected vertices.
## Post #74
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-05T16:59:25+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from MaZTeR
>
> Any idea what skeleton the object "CP_Head_ShortBeard" is supposed to use?

I've tried the head skeleton of the model I'm trying to get, as well as the combinations of that and Main Skeleton, the head skeleton + skeleton "CP_Male_Beard" and finally the head skeleton + skeleton "CP_Male_Beard" and skeletons:
0DDBB68DE36 --> c Skeleton CP_Beard_Memhet
079F67E4237 --> c Skeleton CP_Beard_Cesar
079F67E41BA --> c Skeleton CP_Beard_Afro_Ico
079F67E42E0 --> c Skeleton CP_Beard_Hisp_Ico
0DDBB69079D --> c Skeleton CP_Beard_JustinP

...and none worked. The beard always glitches out completely, and it looks like the reason for it is because the vertices that glitch out are pulled toward the rest pose of the mesh. There should be an additional bone which gets pulled to the center of the head, which is affected by the animation and also affects the non-affected vertices.

what is the entity name that is using that CP_Male_Beard ?
## Post #75
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-12-06T16:50:23+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1
>
> MaZTeR wrote:Any idea what skeleton the object "CP_Head_ShortBeard" is supposed to use?

I've tried the head skeleton of the model I'm trying to get, as well as the combinations of that and Main Skeleton, the head skeleton + skeleton "CP_Male_Beard" and finally the head skeleton + skeleton "CP_Male_Beard" and skeletons:
0DDBB68DE36 --> c Skeleton CP_Beard_Memhet
079F67E4237 --> c Skeleton CP_Beard_Cesar
079F67E41BA --> c Skeleton CP_Beard_Afro_Ico
079F67E42E0 --> c Skeleton CP_Beard_Hisp_Ico
0DDBB69079D --> c Skeleton CP_Beard_JustinP

...and none worked. The beard always glitches out completely, and it looks like the reason for it is because the vertices that glitch out are pulled toward the rest pose of the mesh. There should be an additional bone which gets pulled to the center of the head, which is affected by the animation and also affects the non-affected vertices.

what is the entity name that is using that CP_Male_Beard ?
It's Player_Template.

Also, I managed to kinda manually fix it by saving the weights, removing the skin modifier from the mesh, adjusting the mesh to the approximately correctly location, applying the fix animation onto the player model and then applying the old weights.
## Post #76
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2019-01-12T16:43:20+00:00
- Post Title: Re: Ghost Recon Wildlands

Will the tool in the near future support props?

And is Steep and For Honor on you're list by any chance for upcoming tool?  

Edit*

I found out that the tool dosen't extract all characters anymore
like back when the tool came out

There where 45857 lines that got extracted (Trial Version)

And now it's only 29477 lines that get extracted (Paid Version)

It dosen't give any sense?
## Post #77
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-14T15:51:30+00:00
- Post Title: Re: Ghost Recon Wildlands

1. no i don't plan props any soon

2. i dont know what is Steep
For Honor will not be supported because its not cracked and probably will never be cracked
I can make a tool for some older version of the game (when files were not yet corrupted by protection) but it was about a year ago, and only old models will be present there.

3. I never had any "trial" versions. I always used the tool with full version of the game.
I dont understand what is "45857 lines" ? 
Main game has about 500 entities (including characters, weapons, vehicles, etc), not thousands of them.
## Post #78
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2019-01-14T17:36:17+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1
>
> 1. no i don't plan props any soon

2. i dont know what is Steep
For Honor will not be supported because its not cracked and probably will never be cracked
I can make a tool for some older version of the game (when files were not yet corrupted by protection) but it was about a year ago, and only old models will be present there.

3. I never had any "trial" versions. I always used the tool with full version of the game.
I dont understand what is "45857 lines" ? 
Main game has about 500 entities (including characters, weapons, vehicles, etc), not thousands of them.

Steep is a snowboarding game from Ubisoft and if you want i can give you the game or some of the .forge files?

Now when i tried the full version of the game now it dosen't give me files from the PVP mode
like R6S characters

Wich should be something like this at the begining

======= row 0% ======= 007F63596F6 ========
17023DA9F32 --> 26 Table R6_and_NPC_Gender_MALE
012EBFD679A --> 25 Table GR_PLAYER_INVENTORY_DEFAULT
11F43B78C52 --> 22 Table PVP_PLAYER_Comon
131AC071BE7 --> f Table PVP_R6S_Montagne_Template

Those dosen't show up now when extracting the list as they did when you released the tool
## Post #79
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-14T17:41:03+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1
>
> On the first run, Wildlands_list.exe tool will create a list of assets in all these files. If you change INI, or game will update, you need to delete generated file assets.dat so it will be regenerated.

Have you done this when the game was updated ?
## Post #80
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2019-01-14T17:52:38+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1
>
> daemon1 wrote:On the first run, Wildlands_list.exe tool will create a list of assets in all these files. If you change INI, or game will update, you need to delete generated file assets.dat so it will be regenerated.

Have you done this when the game was updated ?

I did it at first run after i had installed the game
And they weren't there 
Am i the only person this happens for or do other people have this issue too?
## Post #81
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-14T20:26:20+00:00
- Post Title: Re: Ghost Recon Wildlands

i dont know
i dont have r6s characters in my copy of the game
## Post #82
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2019-01-14T21:08:37+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1
>
> i dont know
i dont have r6s characters in my copy of the game

Weird like i still have the old copy of the extract but it would be nice if it could find the new ones

Here are some of them that was on the old extract they still work tho

======= row 0% ======= 007F63596F6 ========
17023DA9F32 --> 26 Table R6_and_NPC_Gender_MALE
11F43B78C52 --> 22 Table PVP_PLAYER_Comon
012EBFD679A --> 25 Table GR_PLAYER_INVENTORY_DEFAULT
13FDAF0ACD5 --> f Table PVP_R6S_Rook_Template

======= row 0% ======= 007F63596F6 ========
17023DA9F32 --> 26 Table R6_and_NPC_Gender_MALE
11F43B78C52 --> 22 Table PVP_PLAYER_Comon
012EBFD679A --> 25 Table GR_PLAYER_INVENTORY_DEFAULT
13FDAF0CD59 --> f Table PVP_R6S_Thermite_Template

======= row 0% ======= 007F63596F6 ========
17023DA9F32 --> 26 Table R6_and_NPC_Gender_MALE
11F43B78C52 --> 22 Table PVP_PLAYER_Comon
012EBFD679A --> 25 Table GR_PLAYER_INVENTORY_DEFAULT
13FDAF0E032 --> f Table PVP_R6S_Pulse_Template

======= row 0% ======= 007F63596F6 ========
17023DA9F80 --> 26 Table R6_and_NPC_Gender_FEMALE
11F43B78C52 --> 22 Table PVP_PLAYER_Comon
012EBFD679A --> 25 Table GR_PLAYER_INVENTORY_DEFAULT
13FDAF16B40 --> f Table PVP_R6S_Ash_Template
## Post #83
- Username: ChenA
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 15, 2016 1:00 am
- Post datetime: 2019-01-24T15:18:29+00:00
- Post Title: Re: Ghost Recon Wildlands

@daemon1 Could you please share the Ghost Recon Wildlands file format？Thanks.
## Post #84
- Username: Citrus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 26, 2017 12:54 pm
- Post datetime: 2019-07-25T13:23:07+00:00
- Post Title: Re: Ghost Recon Wildlands

sorry to be annoying, but i'm having a hard time locating the model for Sam Fisher in the forge files. Can anyone point me in the right direction? Or if anyone's already extracted him?
Thanks
## Post #85
- Username: Naden
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jun 20, 2017 10:09 pm
- Post datetime: 2019-11-07T11:10:08+00:00
- Post Title: Re: Ghost Recon Wildlands

Is it possible to extract static meshes using this tool?
## Post #86
- Username: Citrus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 26, 2017 12:54 pm
- Post datetime: 2020-03-29T07:13:54+00:00
- Post Title: Re: Ghost Recon Wildlands

Does this tool work with Ghost Recon Breakpoint as well? 
EDIT: I don't think it does. Wildlands.exe 1C4A0918BC5 > SamFisher.txt gets me chunk errors.
Unless I've done something wrong. Help would be appreciated
## Post #87
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2020-03-29T12:56:35+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from Citrus ↑Sun Mar 29, 2020 3:13 pm at Sun Mar 29, 2020 3:13 pm
>
> 
Does this tool work with Ghost Recon Breakpoint as well? 
EDIT: I don't think it does. Wildlands.exe 1C4A0918BC5 > SamFisher.txt gets me chunk errors.
Unless I've done something wrong. Help would be appreciated

There are no working tools for Breakpoint
## Post #88
- Username: Hrisenbon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 02, 2020 5:46 pm
- Post datetime: 2020-04-02T09:50:41+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from MaZTeR ↑Tue Aug 21, 2018 5:40 am at Tue Aug 21, 2018 5:40 am
>
> 
Alright I get it now, but what I don't get is that getting the entity tree open requires another batch command, which should reference the main asset archive. And I have no idea how to do that. If I for example copy this line of code:
Code: Select allWildlands.exe DataPC.forge 040123B873C > nina.txt

...which you added above and make a new batch file, it simply adds "Reading Forge files..." to that text file instead of giving me the entity tree.

I'm guessing the final tree export to ASCII section also requires a similar command file which needs to reference the DataPC.forge file, so could you also add that command to the bunch?

I have a similar problem.
How did you solve it?
## Post #89
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2020-04-04T12:38:55+00:00
- Post Title: Re: Ghost Recon Wildlands

I don't understand what the problem was looking back at that comment, but basically, place the names of the archives from which you want to export to the forge.ini file, like this:

.../DataPCpatch.forge
.../DataPC.forge

With the patch files always being first.

Then extract DataPC archive to receive the entity list on a text file.

Then follow the tutorial to get an entity tree and export.

If I remember correctly, you MUST place the export tools to the same folder with the original forge files or else it won't work. Or the same hard drive partition. I'm not sure but at one point when I tried exporting, it just wouldn't work no matter what until I tried exporting within the Wildlands folder.

I probably should write a simplified tutorial which includes getting the character faces right within Blender, because I seem to forget the steps to do so after taking a break for some time. And that Battlefront related tutorial doesn't work fully with this tool if you follow it step by step.
## Post #90
- Username: Hrisenbon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 02, 2020 5:46 pm
- Post datetime: 2020-04-05T05:06:08+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from MaZTeR ↑Sat Apr 04, 2020 8:38 pm at Sat Apr 04, 2020 8:38 pm
>
> 
I don't understand what the problem was looking back at that comment, but basically, place the names of the archives from which you want to export to the forge.ini file, like this:

.../DataPCpatch.forge
.../DataPC.forge

With the patch files always being first.

Then extract DataPC archive to receive the entity list on a text file.

Then follow the tutorial to get an entity tree and export.

If I remember correctly, you MUST place the export tools to the same folder with the original forge files or else it won't work. Or the same hard drive partition. I'm not sure but at one point when I tried exporting, it just wouldn't work no matter what until I tried exporting within the Wildlands folder.

I probably should write a simplified tutorial which includes getting the character faces right within Blender, because I seem to forget the steps to do so after taking a break for some time. And that Battlefront related tutorial doesn't work fully with this tool if you follow it step by step.

I'm sorry for the lack of words...

My problem is that the exported txt shows "Reading forge files...
".
Do you remember how to fix this?
## Post #91
- Username: Hrisenbon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 02, 2020 5:46 pm
- Post datetime: 2020-04-17T19:09:32+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1 ↑Sun Aug 12, 2018 1:31 am at Sun Aug 12, 2018 1:31 am
>
> 
No matter what I try, the .txt generated in Step 2 will show "Reading forge files...".
Somebody help me!
## Post #92
- Username: RickModder
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 22, 2020 4:20 pm
- Post datetime: 2020-04-22T08:25:17+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from MaZTeR ↑Tue Aug 21, 2018 5:40 am at Tue Aug 21, 2018 5:40 am
>
> 
Alright I get it now, but what I don't get is that getting the entity tree open requires another batch command, which should reference the main asset archive. And I have no idea how to do that. If I for example copy this line of code:
Code: Select allWildlands.exe DataPC.forge 040123B873C > nina.txt

...which you added above and make a new batch file, it simply adds "Reading Forge files..." to that text file instead of giving me the entity tree.

I'm guessing the final tree export to ASCII section also requires a similar command file which needs to reference the DataPC.forge file, so could you also add that command to the bunch?

Hi!
I'm trying to convert the assets from this game to GTASA!

How do I import an exported ASCII file into Blender?
Kind community, please help me out.

Thank you!!
## Post #93
- Username: ak79857
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 06, 2020 3:52 am
- Post datetime: 2020-06-07T18:11:56+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1 ↑Sun Aug 12, 2018 1:31 am at Sun Aug 12, 2018 1:31 am
>
> 

With DataPC_GRN_WorldMap.forge doesn't work  
.txt file is empty after list command...
## Post #94
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-03-11T13:08:33+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from ak79857 ↑Mon Jun 08, 2020 2:11 am at Mon Jun 08, 2020 2:11 am
>
> With DataPC_GRN_WorldMap.forge doesn't work  
.txt file is empty after list command...

Yeah it doesn't work on world objects. You need Archive_Next to export some world props and it's a very limited quantity. I managed to extract SPOILER Pac Katari's severed head from the final cutscene SPOILER END from one of the worldmap forge files years ago.
## Post #95
- Username: ak79857
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 06, 2020 3:52 am
- Post datetime: 2022-04-30T11:09:20+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1 ↑Sun Aug 12, 2018 1:31 am at Sun Aug 12, 2018 1:31 am
>
> 

I don't understand how to do a normal pose. The skeleton, which together with the model is curved, and when I import the smd, it turns out this kind of stuff.
[Снимок экрана 2022-04-30 140213.jpg](https://xentaxbackup.github.io/file/22173_Снимок экрана 2022-04-30 140213.jpg)
## Post #96
- Username: ak79857
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 06, 2020 3:52 am
- Post datetime: 2022-04-30T11:10:31+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from daemon1 ↑Sun Aug 12, 2018 1:31 am at Sun Aug 12, 2018 1:31 am
>
> 
[Снимок экрана 2022-04-30 140832.jpg](https://xentaxbackup.github.io/file/22174_Снимок экрана 2022-04-30 140832.jpg)
## Post #97
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2022-04-30T23:56:01+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from ak79857 ↑Sat Apr 30, 2022 7:09 pm at Sat Apr 30, 2022 7:09 pm
>
> 
daemon1 wrote: ↑Sun Aug 12, 2018 1:31 am


I don't understand how to do a normal pose. The skeleton, which together with the model is curved, and when I import the smd, it turns out this kind of stuff.

Import the "broken" model and the skeleton, then import the skeleton which has the animation. Then pose the animated armature so that the final keyframe will align with the front side while the first keyframe will align with the broken model (I can't remember what armature was laying on the ground, but just make sure they match the objects' rotation). Then add armature modifiers to the head objects and any broken objects with the animated armature and move to the animation to the final keyframe to its fixed position (the eyes and mouth move to their proper location). Then apply the armature modifiers to the objects and apply the fixed keyframe as the default for the armature and delete the other keyframes.

Oh and also delete any previous armature modifiers from the objects before you add a new armature modifier.

And as for the armature exploding like that, make sure you import it as a new armature, not append it to the scene.
## Post #98
- Username: ak79857
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 06, 2020 3:52 am
- Post datetime: 2022-07-11T18:16:21+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from MaZTeR ↑Sun May 01, 2022 7:56 am at Sun May 01, 2022 7:56 am
>
> 
ak79857 wrote: ↑Sat Apr 30, 2022 7:09 pm
daemon1 wrote: ↑Sun Aug 12, 2018 1:31 am


I don't understand how to do a normal pose. The skeleton, which together with the model is curved, and when I import the smd, it turns out this kind of stuff.


Import the "broken" model and the skeleton, then import the skeleton which has the animation. Then pose the animated armature so that the final keyframe will align with the front side while the first keyframe will align with the broken model (I can't remember what armature was laying on the ground, but just make sure they match the objects' rotation). Then add armature modifiers to the head objects and any broken objects with the animated armature and move to the animation to the final keyframe to its fixed position (the eyes and mouth move to their proper location). Then apply the armature modifiers to the objects and apply the fixed keyframe as the default for the armature and delete the other keyframes.

Oh and also delete any previous armature modifiers from the objects before you add a new armature modifier.

And as for the armature exploding like that, make sure you import it as a new armature, not append it to the scene.
Please, u can record a video with the full process from importing the model, to the complete fixation of teeth and eyes.?
I read all the messages, tried to do both how you told me and how it is written on the site, but my teeth are crooked anyway, and even my fingers are crooked.
The process, as I understand it, takes only a couple of minutes, but the main thing is to see the order of actions.
## Post #99
- Username: Thighmangler
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 12, 2022 4:28 am
- Post datetime: 2022-07-19T20:44:09+00:00
- Post Title: Re: Ghost Recon Wildlands

is this still working? i dont even get an ascii file when exporting. Honestly this has been really confusing for my dumbass lol. Can someone make a video of their workflow as they extract something from the game?
## Post #100
- Username: ak79857
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 06, 2020 3:52 am
- Post datetime: 2022-07-19T23:13:12+00:00
- Post Title: Re: Ghost Recon Wildlands

Yep. it's still works   
Take this [https://youtu.be/umtc5exojcA](https://youtu.be/umtc5exojcA)

> Reply from Thighmangler ↑Wed Jul 20, 2022 4:44 am at Wed Jul 20, 2022 4:44 am
>
> 
is this still working? i dont even get an ascii file when exporting. Honestly this has been really confusing for my dumbass lol. Can someone make a video of their workflow as they extract something from the game?
## Post #101
- Username: Thighmangler
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 12, 2022 4:28 am
- Post datetime: 2022-08-27T15:57:15+00:00
- Post Title: Re: Ghost Recon Wildlands

> Reply from ak79857 ↑Wed Jul 20, 2022 7:13 am at Wed Jul 20, 2022 7:13 am
>
> 
Yep. it's still works   
Take this https://youtu.be/umtc5exojcA
Thighmangler wrote: ↑Wed Jul 20, 2022 4:44 am
is this still working? i dont even get an ascii file when exporting. Honestly this has been really confusing for my dumbass lol. Can someone make a video of their workflow as they extract something from the game?

Thank you so much. it really does work. now i just need to figure out how export specific player shirts and pants

edit: i can't see the ascii files in Noesis. i can only see and open the skel.smd file. is there something specific i have to do in noesis? or better; can i import the ascii file directly into Blender?


edit again: nvm turns out i need to install [http://xnalara.org/viewtopic.php?t=1139](http://xnalara.org/viewtopic.php?t=1139) this plugin.
