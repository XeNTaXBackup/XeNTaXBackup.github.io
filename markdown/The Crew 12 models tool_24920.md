## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-07T09:33:01+00:00
- Post Title: The Crew 1/2 models tool

The Crew 1/2 tool for models - cars, characters etc

Drop .XBG file onto the tool, use command line or batch convert them.

This will make properly converted models with skeletons and all parts placed to their bones and having weights.

Note that this tool only converts individual XBG files, and both cars and characters are combined from multiple XBG parts, to support many different combinations. Like premium hoods/bumpers etc for cars, and outfits for characters/NPCs. Finding these parts for particular car/char will require parsing archetype files, I will provide tools for that soon.

Examples of complete models:





Characters:




[CrewModel.rar](https://xentaxbackup.github.io/file/21546_CrewModel.rar)
## Post #2
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2022-01-07T14:54:41+00:00
- Post Title: The Crew 1/2 models tool

Thanks for the tool! I can't wait for renamed tool for this game by you. I have question, it's possible to convert parts in fbx format? ASCII for me isn't perfect format.
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-07T16:14:42+00:00
- Post Title: The Crew 1/2 models tool

> Reply from zimex25 ↑Fri Jan 07, 2022 10:54 pm at Fri Jan 07, 2022 10:54 pm
>
> 
Thanks for the tool! I can't wait for renamed tool for this game by you. I have question, it's possible to convert parts in fbx format? ASCII for me isn't perfect format.
1 - what do you mean under "renamed tool" ?
2 - yes, you can use noesis to convert ascii to fbx, but no guarantee it will work correct because fbx isn't good format at all
## Post #4
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2022-01-07T18:27:07+00:00
- Post Title: The Crew 1/2 models tool

> Reply from daemon1 ↑Sat Jan 08, 2022 12:14 am at Sat Jan 08, 2022 12:14 am
>
> 
zimex25 wrote: ↑Fri Jan 07, 2022 10:54 pm
Thanks for the tool! I can't wait for renamed tool for this game by you. I have question, it's possible to convert parts in fbx format? ASCII for me isn't perfect format.

1 - what do you mean under "renamed tool" ?
2 - yes, you can use noesis to convert ascii to fbx, but no guarantee it will work correct because fbx isn't good format at all
This files after dumped using last version of DAT Unpacker, I looking renamed, other tool but I didn't find.
[Bez tytułu.png](https://xentaxbackup.github.io/file/21549_Bez tytułu.png)
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-07T18:53:27+00:00
- Post Title: The Crew 1/2 models tool

> Reply from zimex25 ↑Sat Jan 08, 2022 2:27 am at Sat Jan 08, 2022 2:27 am
>
> 
This files after dumped using last version of DAT Unpacker, I looking renamed, other tool but I didn't find.
You will not need to rename them. Game access files by these hashes. My tool will gather all needed parts for each car and convert them:
[Capture.PNG](https://xentaxbackup.github.io/file/21550_Capture.PNG)
## Post #6
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-07T22:38:33+00:00
- Post Title: The Crew 1/2 models tool

> Reply from zimex25 ↑Sat Jan 08, 2022 2:27 am at Sat Jan 08, 2022 2:27 am
>
> This files after dumped using last version of DAT Unpacker, I looking renamed, other tool but I didn't find.
You need to avoid the DAT Unpacker by Ekey, we recently discovered its NOT extracting properly, especially vehicles patch archive, not sure if other archives have same issue, since Ekey will never update it, you must use the quickbms script for that located here:
[https://aluigi.altervista.org/bms/fat2_fat3.bms](https://aluigi.altervista.org/bms/fat2_fat3.bms)
Also, names will NOT help you here as the tools require to have HASH names.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-08T20:38:11+00:00
- Post Title: The Crew 1/2 models tool

Tools to work with archetype files to get cars/characters combined.

First, get archetype files:

entity\generated\archetypes.entities.bin - main big archetype
entity\generated\server_archetypes.entities.bin - server archetype

Then we need to make a "cache" for archetypes:

crewact_cache.exe - Drop archetypes on it, and it will create 2 cache files: a list of all branches, and all entities in the tree, so it can be loaded and used fast from now on.
.  If cache files already created, it will exit.
.  list.txt is required to work (for this tool and all others below)

------- cars ------

crewact_cartables.exe - create a list of all car tables (from main archetype)
.  this will also take 30 seconds, because it will have to parse whole tree
.  you can hex-edit this list to work with only 1 car or selected cars

crewact_carmodels.exe - output a list of car models (from server archetype)
.  list will be output to console, save it as models.txt
example:  crewact_carmodels.exe server_archetypes.entities.bin > models.txt
important note:  remove incorrect entries in the end, if there will be any

crewact_cars.exe - create .BAT files for all cars based on the tables (from main archetype)
.  these files will have part lists for all cars based on the tables 
.  also outputs all tree entities related to those car parts to console
.  models.txt is required in the same folder to work
crewact_cars_noout.exe - same tool, just no output to console

important note2: models.txt will only work for The Crew 2, so for The Crew 1 if you leave it empty, you can get BAT files, but no car names

------- avatars ------

crewact_avatartables.exe - create a list of all avatar tables (from main archetype)
.  this will also take 30 seconds, because it will have to parse whole tree
.  you can hex-edit this list too

crewact_avatars.exe - create .BAT files for all avatars based on the tables (from main archetype)
.  these files will have part lists for all characters based on the tables 
.  also outputs all tree entities related to console
crewact_avatars_noout.exe - same tool, just no output to console

------- convertion ---------

After that, you can put these BAT files in a folder where you have XBG files, and run them there, it will copy parts for specific cars to their folders. Then you can convert them with model tool.
[crewact.7z](https://xentaxbackup.github.io/file/21554_crewact.7z)
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-08T20:50:00+00:00
- Post Title: The Crew 1/2 models tool

this list.txt is a test file, but it contains enough strings that will make tools work
[list.rar](https://xentaxbackup.github.io/file/21555_list.rar)
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-09T09:15:23+00:00
- Post Title: The Crew 1/2 models tool

Character table system explanation.
Their "inheritance" system is not still clear to me, so i did what i could, and thats why some characters have extra arms/legs etc.

In the archetype tree they have 3 levels of data: tables, slots and renderparts.
1. there are 385 different tables and i'm working from that. Table has a list of slots ("upper body", "feet", "head" etc).
And also each table has its parents (where it can inherit more occupied slots). So i'm collecting all slots from a table and all its parents.
2. slots
Each slot has a list of renderparts. Again, each slot can have parents. So again, i'm collecting all data for particular slot and all its parents and getting a list of renderparts.
3. renderparts
Each part is a mesh description and it contains a link to geometry resource, just like in cars. But this time i'm NOT looking for its parents because it seems they have no inherited data. I may be wrong though.
4. So after I gather all these, i'm making an output of all resources i've found in a BAT file
## Post #10
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2022-01-09T15:02:45+00:00
- Post Title: The Crew 1/2 models tool

After long fight to understood this, finally I get model but after I converted to .obj using Nosesis with XNAaraL plugin, body didn't have UV and have problem with smooth of mesh. Other parts didn't have problem with UV.
[Bez tytułu.jpg](https://xentaxbackup.github.io/file/21563_Bez tytułu.jpg)
## Post #11
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-09T15:15:47+00:00
- Post Title: The Crew 1/2 models tool

> Reply from zimex25 ↑Sun Jan 09, 2022 11:02 pm at Sun Jan 09, 2022 11:02 pm
>
> ...after I converted to .obj using Nosesis with XNAaraL plugin, body didn't have UV and have problem with smooth of mesh. Other parts didn't have problem with UV.
Avoid Noesis at ALL costs, you MUST use Blender.
There is no proper script for ASCIIs for Noesis, or 3dsMax for that matter, only for Blender.
[https://github.com/johnzero7/XNALaraMesh](https://github.com/johnzero7/XNALaraMesh)
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-09T15:29:15+00:00
- Post Title: The Crew 1/2 models tool

> Reply from zimex25 ↑Sun Jan 09, 2022 11:02 pm at Sun Jan 09, 2022 11:02 pm
>
> 
body didn't have UV
Car body parts do NOT have UVs, because they dont use any textures, they dont need them. They are solid colored parts.
## Post #13
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2022-01-09T19:21:05+00:00
- Post Title: The Crew 1/2 models tool

Okay I got this but what about textures? How to find all textures?
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-01-09T19:42:25+00:00
- Post Title: The Crew 1/2 models tool

A tool to scale wheels (rims/tyres)

Its the same tool, you can still use it for ALL models.







if you run it with no parameters, it will think its a usual model
if you run it with 2 parameters, it will think its a tyre
if you run it with 1 parameter, it will think its a rim
because naturally, rims and tyres have to be scaled differently 

for rim scaling 1 parameter:
1. rim size in inches

for tyre scaling 2 parameters:
1. rim size in inches
2. thickness relative scale
meaning scale 1 will not change thickness, scale 2 will make it 2x times thicker

examples, from pictures above, left to right

CrewModel.exe tyre.xbg
standard tyre R18

CrewModel.exe tyre.xbg 20 0,5
it will scale standard r18 tyre to R20 and make it 2 times thinner

CrewModel.exe tyre.xbg 25 2
it will scale standard r18 tyre to R25 and make it 2 times thicker

CrewModel.exe rim.xbg 25
will scale standard rim to R25
[CrewModel.rar](https://xentaxbackup.github.io/file/21566_CrewModel.rar)
## Post #15
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2022-01-09T20:25:57+00:00
- Post Title: The Crew 1/2 models tool

aweseome!

transforming the tires will help on the monstertrucks

delorean is using 25 inches rims

testing around with the thickness also affects the thread

used 1 - 3 - 5 on the first images and scaled them on the x axis - value of 4 almost matches ingame - still need some more tweaks

[https://imgur.com/a/KKJk3Uw](https://imgur.com/a/KKJk3Uw)

[https://imgur.com/y2lR2V3](https://imgur.com/y2lR2V3)

[https://imgur.com/0LJkNzn](https://imgur.com/0LJkNzn)

[https://imgur.com/31SVTq7](https://imgur.com/31SVTq7)

[https://imgur.com/XDqSVdn](https://imgur.com/XDqSVdn)
## Post #16
- Username: Fengo
- Rank: beginner
- Number of posts: 24
- Joined date: Fri Aug 12, 2011 3:02 pm
- Post datetime: 2022-03-21T09:00:19+00:00
- Post Title: Re: The Crew 1/2 models tool

This is amazing. Just a few questions, like where/how do you know which files are XBG files? I used the BMS script and have a bunch of files with no extension. And where do you get the archetype files?
## Post #17
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-03-21T20:55:54+00:00
- Post Title: Re: The Crew 1/2 models tool

> Reply from Fengo ↑Mon Mar 21, 2022 5:00 pm at Mon Mar 21, 2022 5:00 pm
>
> ...I used the BMS script and have a bunch of files with no extension...
[viewtopic.php?p=159199#p159199](https://forum.xentax.com/viewtopic.php?p=159199#p159199)

> Reply from Fengo ↑Mon Mar 21, 2022 5:00 pm at Mon Mar 21, 2022 5:00 pm
>
> ...And where do you get the archetype files?...
[viewtopic.php?p=181205#p181205](https://forum.xentax.com/viewtopic.php?p=181205#p181205)
## Post #18
- Username: Fengo
- Rank: beginner
- Number of posts: 24
- Joined date: Fri Aug 12, 2011 3:02 pm
- Post datetime: 2022-03-22T22:09:20+00:00
- Post Title: Re: The Crew 1/2 models tool

I still have no idea where to get the archetype files, those folders don't exist at all
## Post #19
- Username: eibmoz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 24, 2018 2:11 am
- Post datetime: 2022-04-02T04:16:22+00:00
- Post Title: Re: The Crew 1/2 models tool

i have found archetypes and server archetypes, but i have problem is, when i drag sever archetypes on crewact_carmodels it doesn't create models.txt, then i copy all in cmd and create a notepad models.txt, i have another problem is when i drag archetypes on crewact_cars it only create a empty folder bat
## Post #20
- Username: SanJose
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 10, 2022 7:46 pm
- Post datetime: 2022-06-10T13:49:05+00:00
- Post Title: Re: The Crew 1/2 models tool

Is there any way to separate xbg files for cars from newer patches? For example 1970 Plymouth Roadrunner or Nissan 300ZX?

Or we are forced to check every single file from __Uknown folder?

I know that after release they changed way how the files are read from hashes by the game.
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-06-10T15:19:13+00:00
- Post Title: Re: The Crew 1/2 models tool

you dont have to check hashes anymore.
this tool provides lists for all cars, grouped and properly connected to car names
## Post #22
- Username: SanJose
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 10, 2022 7:46 pm
- Post datetime: 2022-06-11T12:58:52+00:00
- Post Title: Re: The Crew 1/2 models tool

Where should I put those programs from this post?
:[viewtopic.php?p=181205#p181205](https://forum.xentax.com/viewtopic.php?p=181205#p181205)

When I launch any of them, it crashes immediately. I'm working on Win7 maybe that's the problem.

Sorry for noob questions, I was out of the modding business for about 8 years and forgot a lot, so I dont get it how to use them   .

All I got is unpacked and sorted files by The Crew 2 DAT unpacker made bay Ekey. Rest of the files are in __Uknown folder and those are mainly for the cars which were added later into the game.

EDIT:

Oh I see, I need to get the .bin files firstly. Where are they stored? Or how to capture them?

EDIT2:

I got the archetype files, they are located in scenaric.dat and scenaric_patch.dat archives.

Now I got problem. The crewact_cache.exe still crashes for me after drag and drop .bin file on it.

Here's the error description, sorry for polish language:
## Post #23
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-06-11T17:13:24+00:00
- Post Title: Re: The Crew 1/2 models tool

> Reply from SanJose ↑Sat Jun 11, 2022 8:58 pm at Sat Jun 11, 2022 8:58 pm
>
> ...
Now I got problem. The crewact_cache.exe still crashes for me after drag and drop .bin file on it.
...

> Reply from daemon1 ↑Sun Jan 09, 2022 4:38 am at Sun Jan 09, 2022 4:38 am
>
> 
...
.  list.txt is required to work (for this tool and all others below)
...
## Post #24
- Username: SanJose
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 10, 2022 7:46 pm
- Post datetime: 2022-06-12T12:22:57+00:00
- Post Title: Re: The Crew 1/2 models tool

So this set up is incorrect?
list.txt file is in the same folder where the exes are:
## Post #25
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2022-06-12T12:53:57+00:00
- Post Title: Re: The Crew 1/2 models tool

> Reply from SanJose ↑Sun Jun 12, 2022 8:22 pm at Sun Jun 12, 2022 8:22 pm
>
> 
So this set up is incorrect?
list.txt file is in the same folder where the exes are:

I have, for example, the list.txt file contained a space in the file. Because of this, it was not possible to extract.
## Post #26
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-06-12T13:49:06+00:00
- Post Title: Re: The Crew 1/2 models tool

> Reply from SanJose ↑Sun Jun 12, 2022 8:22 pm at Sun Jun 12, 2022 8:22 pm
>
> list.txt file is in the same folder where the exes are:
Rename that to list1.txt and create another new text file and rename it list.txt and test tool again with that empty list file, see if it crashes again.
## Post #27
- Username: SanJose
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 10, 2022 7:46 pm
- Post datetime: 2022-06-13T09:41:06+00:00
- Post Title: Re: The Crew 1/2 models tool

Unfortunately it still crashes   

Tried with empty list.txt file. I even checked the coding of the file (ANSI) and tried with others, still same result.

I think this wil be the Windows 7 fault - too old
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-06-13T10:32:04+00:00
- Post Title: Re: The Crew 1/2 models tool

> Reply from SanJose ↑Mon Jun 13, 2022 5:41 pm at Mon Jun 13, 2022 5:41 pm
>
> 
Unfortunately it still crashes   

Tried with empty list.txt file. I even checked the coding of the file (ANSI) and tried with others, still same result.

I think this wil be the Windows 7 fault - too old
no, i MADE this tool in windows 7, and it always worked.

i see you have "file not found"error
try running from command line to see which file is missing, or read the error in windows application log (event viewer)
## Post #29
- Username: SanJose
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 10, 2022 7:46 pm
- Post datetime: 2022-06-13T12:03:35+00:00
- Post Title: Re: The Crew 1/2 models tool

I found the problem.

The exe files MUST be placed inside folder where the .bin files are unpacked.

I had the tool placed on desktop folder and then drag and drop the .bin file on it, so it had no chance to find the file. Stupid me  

Now it created .bra and .ent files. I will proceed further.

Anyway thanks for helping me guys.

Hmmmm for unknown reason the crewact_carmodels.exe auto-close after reading server_archetypes.entities.bin file, so I got no chance to select all console contents and save them as txt file. I see that it reads model names correctly.
## Post #30
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-06-13T19:29:24+00:00
- Post Title: Re: The Crew 1/2 models tool

> Reply from SanJose ↑Mon Jun 13, 2022 8:03 pm at Mon Jun 13, 2022 8:03 pm
>
> ...Hmmmm for unknown reason the crewact_carmodels.exe auto-close after reading server_archetypes.entities.bin file, so I got no chance to select all console contents and save them as txt file...
You can always direct the output from console to a TXT file, just add at the end of your cmd syntax the following:

```
 >>output.txt
```

The name can be anything, so does the extension, it will be a text format either way.
## Post #31
- Username: SanJose
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 10, 2022 7:46 pm
- Post datetime: 2022-06-14T14:32:22+00:00
- Post Title: Re: The Crew 1/2 models tool

Thanks mono24, this worked for me.

Looks like the tool does not read all cars from "server_archetypes_entities.bin" located in scenaric_patch folder. At least on my end.
In saved file from the cmd.
I cannot find the Plymouth Roadrunner 1970 car.

```
0800000000023A9D        Peugeot_3008_DKR_MAXI_2018_RallyRaid
080000000002663A        Jaguar_CX_75_Concept_2013_Hypercar
08000000000238C0        Porsche_918_Spyder_Hypercar
080000000002310A        Chevrolet_Camaro_Z28_1971_StreetRacing
0800000000022FC0        Ice_Marine_BladeRunner_35_PowerBoat
0800000000022CF0        Default_StreetRacing
0800000000022BB1        RedBull_RB13_FormulaOne
080000000002241D        Supermarine_Spitfire_Mk_IX_Propeller
08000000000231B7        Supermarine_Spitfire_Mk_IX_AirRace
080000000001FB25        Ford_FOCUS_RSRX_Rally
080000000001EC58        Mercedes_XClass_RallyRaid
080000000001EAF0        Ducati_Monster_RallyRaid_EVO1_RallyRaid
080000000001EA9A        Ducati_Hypermotard_RallyRaid_EVO1_RallyRaid
080000000001E991        Jeep_Wrangler_RallyRaid_EVO1_RallyRaid
080000000001E931        Jeep_Grand_Cherokee_RallyRaid_EVO1_RallyRaid
080000000001E8D3        Hummer_H1_Alpha_RallyRaid_EVO1_RallyRaid
080000000001E876        Ford_F150_RAPTOR_2010_RallyRaid_EVO1_RallyRai
080000000001E7D2        Chevrolet_Silverado_2010_RallyRaid_EVO1_Rally
080000000001E6AB        Renault_Megane_RS_2018_StreetRacing
080000000001A60E        Harley_Davidson_StreetGlide_Special_2017_Stre
0800000000019119        OFFSHORE_MK2_PowerBoat
0800000000018C29        Porsche_911_GT3_Cup_2017_TouringCar
0800000000018560        Suzuki_450_RMZ_2016_MotoCross
0800000000017A3E        Audi_R8_V10_Plus_Coupe_StreetRacing
0800000000016F38        Pilatus_PC21_Propeller
0800000000017AC2        Pilatus_PC21_AirRace
0800000000016EAF        Nissan_370Z_Nismo_StreetRacing
080000000001A7FF        Nissan_370Z_Nismo_Drift
0800000000016CC4        Jet_Sprint_IVT_04_JetSprint
0800000000016C9B        Jet_Sprint_IVT_03_JetSprint
0800000000016BE7        Jet_Sprint_IVT_02_JetSprint
080000000002EA3E        Ford_GT_2016_Hypercar
0800000000014768        Harley_Davidson_Iron_883_2017_StreetRacing
080000000001465D        Ferrari_488_GT3_TouringCar
0800000000014444        KTM_450EXC_02_MotoCross
08000000000142A5        Porsche_911_Turbo_1993_StreetRacing
080000000001396C        North_American_P51_Mustang_Strega_Propeller
0800000000017AA6        North_American_P51_Mustang_Strega_AirRace
08000000000136CB        KTM_XBOW_R_StreetRacing
0800000000012D7E        Abarth_124_Spider_StreetRacing
08000000000127DD        OFFSHORE_MK1_PowerBoat
0800000000012234        Ford_Focus_RS_2016_StreetRacing
0800000000011FE8        Ford_F150_Raptor_Race_Truck_2017_RallyRaid
0800000000011EE5        Alfa_Giulia_QV_StreetRacing
0800000000011D52        Honda_NSX_2017_StreetRacing
0800000000011B90        Chevrolet_Impala_1967_StreetRacing
0800000000011BF8        Chevrolet_Impala_1967_TouringCar
0800000000011AC7        Honda_Civic_Type_R_2016_StreetRacing
0800000000011A4A        MV_AGUSTA_BRUTALE_StreetRacing
0800000000011DCC        Ferrari_FXX_K_TouringCar
080000000001181D        Bugatti_Chiron_Hypercar
080000000001173C        Sean_Bull_Design_SBD_01_FormulaOne
0800000000011523        DCB_M31_PowerBoat
080000000001146B        Koenigsegg_Regera_Hypercar
08000000000113CF        Mercedes_C63AMG_S_Coupe_2017_StreetRacing
080000000000CDD9        MV_AGUSTA_F4_RR_StreetRacing
080000000000CB3B        DODGE_CHALLENGER_RT_1970_StreetRacing
080000000000C941        Porsche_911_GT3_RS_2015_StreetRacing
080000000000C83D        Abarth_124_Rally_Rally
080000000000C79D        Lancia_037_Rally
080000000000C592        Aston_Vulcan_TouringCar
080000000000AF8B        Vector_V40R_PowerBoat
080000000000AAB1        Mercedes_C63AMG_TC_TouringCar
080000000000A4C3        Audi_TT_RS_2017_StreetRacing
080000000000A39C        Jaguar_F_Type_SVR_coupe_2017_StreetRacing
0800000000009D8F        Dodge_Challenger_Hellcat_2017_StreetRacing
0800000000009D2B        Lancia_Delta_S4_Rally
0800000000009C4B        Chevrolet_Camaro_ZL1_2017_StreetRacing
0800000000009BC1        Ferrari_365GTB4_TouringCar
0800000000009829        Chevrolet_Camaro_RS_1969_Rally
0800000000009848        Chevrolet_Camaro_RS_1969_RallyRaid
0800000000009853        Chevrolet_Camaro_RS_1969_StreetRacing
08000000000098F7        Chevrolet_Camaro_RS_1969_TouringCar
08000000000095D7        Nissan_GT-R_2016_StreetRacing
0800000000009375        Mazda_MX5_2016_StreetRacing
08000000000093E4        Mazda_MX5_2016_TouringCar
08000000000092E9        Mercedes_GLC_Coupe_StreetRacing
0800000000009263        Mercedes_AMG_GT_StreetRacing
0800000000009295        Mercedes_AMG_GT_TouringCar
08000000000091E9        Maserati_MC12_TouringCar
0800000000009F90        Maserati_MC12_Hypercar
0800000000009066        Lamborghini_Huracan_StreetRacing
080000000000909E        Lamborghini_Huracan_TouringCar
0800000000008FCF        Ferrari_F12_2013_StreetRacing
0800000000008C49        Kawasaki_Ninja_MotoGP
0800000000008C5D        Kawasaki_Ninja_StreetRacing
0800000000008BD2        Ducati_Hypermotard_StreetRacing
0800000000008801        Ducati_Monster_MotoGP
0800000000008807        Ducati_Monster_StreetRacing
080000000000841F        McLaren_P1_Hypercar
080000000000728B        BMW_M2_F87_StreetRacing
0800000000006CD1        Volkswagen_Golf_2014_StreetRacing
0800000000006C4E        TVR_Sagaris_StreetRacing
0800000000006BE3        Saleen_S7_TouringCar
080000000000A0B2        Saleen_S7_Hypercar
0800000000006B36        Spyker_C8_StreetRacing
0800000000006A68        Shelby_GT500_1967_StreetRacing
0800000000006ACC        Shelby_GT500_1967_TouringCar
0800000000012B8D        Shelby_GT500_1967_Drift
08000000000081F0        Pagani_Huayra_Hypercar
0800000000006697        Nissan_R34_Rally
08000000000066B5        Nissan_R34_RallyRaid
08000000000066C3        Nissan_R34_StreetRacing
0800000000006725        Nissan_R34_TouringCar
0800000000013001        Nissan_R34_Drift
080000000001842A        Nissan_R34_Dragster
0800000000022989        Nissan_R34_Monster
08000000000064B0        Nissan_370Z_2013_Rally
08000000000064CB        Nissan_370Z_2013_RallyRaid
08000000000064DF        Nissan_370Z_2013_StreetRacing
080000000000656B        Nissan_370Z_2013_TouringCar
0800000000013076        Nissan_370Z_2013_Drift
0800000000017C6D        Nissan_370Z_2013_Dragster
0800000000019301        Nissan_370Z_2013_Monster
0800000000006364        Nissan_240Z_1970_Rally
0800000000006386        Nissan_240Z_1970_StreetRacing
0800000000006169        Mini_Cooper_S_2010_Rally
080000000000617A        Mini_Cooper_S_2010_StreetRacing
08000000000061B7        Mini_Cooper_S_2010_TouringCar
0800000000006054        Mercedes_SLS_2010_StreetRacing
080000000000608B        Mercedes_SLS_2010_TouringCar
0800000000005F51        Mercedes_SLR722_StreetRacing
0800000000005F87        Mercedes_SLR722_TouringCar
0800000000005E56        Mercedes_SL63AMG_2009_StreetRacing
0800000000005E8F        Mercedes_SL63AMG_2009_TouringCar
0800000000005D45        Mercedes_C63AMG_2012_StreetRacing
0800000000005D68        Mercedes_C63AMG_2012_TouringCar
0800000000005C31        Mercedes_300SLR_StreetRacing
0800000000005C49        Mercedes_300SLR_TouringCar
0800000000009FE8        McLaren_F1_1993_Hypercar
0800000000005A6E        McLaren_12C_TouringCar
08000000000124F5        McLaren_12C_Drift
080000000002EAB1        McLaren_12C_Hypercar
080000000000593B        Maserati_Granturismo_StreetRacing
0800000000005959        Maserati_Granturismo_TouringCar
080000000000583F        Lotus_Evora_StreetRacing
0800000000005745        Lamborghini_Murcielago_StreetRacing
080000000000578B        Lamborghini_Murcielago_TouringCar
0800000000013649        Lamborghini_Murcielago_Drift
08000000000056B4        Lamborghini_Miura_StreetRacing
080000000000A248        Lamborghini_Aventador_Hypercar
0800000000012B4F        Lamborghini_Aventador_Drift
0800000000009F2A        Koenigsegg_Agera_Hypercar
080000000000A596        Koenigsegg_Agera_Drift
0800000000005471        Jeep_Grand_Cherokee_StreetRacing
0800000000022764        Jeep_Grand_Cherokee_Monster
0800000000005297        Hummer_H1_Alpha_RallyRaid
08000000000052A9        Hummer_H1_Alpha_StreetRacing
08000000000198D3        Hummer_H1_Alpha_Monster
0800000000005142        Ford_Shelby_GT500_2013_StreetRacing
0800000000004FA7        Ford_Mustang_GT_2011_Rally
0800000000004FC5        Ford_Mustang_GT_2011_RallyRaid
0800000000004FD9        Ford_Mustang_GT_2011_StreetRacing
080000000000507B        Ford_Mustang_GT_2011_TouringCar
080000000001372E        Ford_Mustang_GT_2011_Drift
080000000001832B        Ford_Mustang_GT_2011_Dragster
08000000000226E6        Ford_Mustang_GT_2011_Monster
0800000000004E51        Ford_GT_2005_StreetRacing
0800000000004E8B        Ford_GT_2005_TouringCar
08000000000135FB        Ford_GT_2005_Drift
0800000000004C8E        Ford_Focus_RS_2010_Rally
0800000000004CAF        Ford_Focus_RS_2010_RallyRaid
0800000000004CBF        Ford_Focus_RS_2010_StreetRacing
0800000000004D17        Ford_Focus_RS_2010_TouringCar
0800000000012E23        Ford_Focus_RS_2010_Drift
08000000000184A9        Ford_Focus_RS_2010_Dragster
0800000000004AA5        Ford_F150_RAPTOR_2010_RallyRaid
0800000000004AB2        Ford_F150_RAPTOR_2010_StreetRacing
0800000000004B12        Ford_F150_RAPTOR_2010_TouringCar
0800000000017954        Ford_F150_RAPTOR_2010_Monster
0800000000009E7F        Ferrari_LAFERRARI_Hypercar
0800000000004845        Ferrari_F40_StreetRacing
080000000000486F        Ferrari_F40_TouringCar
0800000000004752        Abarth_500_StreetRacing
0800000000006F74        Abarth_500_Monster
0800000000004490        Dodge_Challenger_2012_Rally
08000000000044AE        Dodge_Challenger_2012_RallyRaid
08000000000044C1        Dodge_Challenger_2012_StreetRacing
080000000000452D        Dodge_Challenger_2012_TouringCar
0800000000012F82        Dodge_Challenger_2012_Drift
08000000000182AC        Dodge_Challenger_2012_Dragster
0800000000022668        Dodge_Challenger_2012_Monster
080000000000431F        Dodge_Viper_2010_StreetRacing
0800000000004357        Dodge_Viper_2010_TouringCar
0800000000004159        Dodge_Ram_2004_Rally
0800000000004179        Dodge_Ram_2004_RallyRaid
080000000000418C        Dodge_Ram_2004_StreetRacing
08000000000041F3        Dodge_Ram_2004_TouringCar
0800000000003F4C        Dodge_Charger_2012_Rally
0800000000003F6A        Dodge_Charger_2012_StreetRacing
0800000000003FCD        Dodge_Charger_2012_TouringCar
0800000000003D53        Dodge_Charger_1969_Rally
0800000000003D73        Dodge_Charger_1969_StreetRacing
0800000000003DE0        Dodge_Charger_1969_TouringCar
0800000000012EFF        Dodge_Charger_1969_Drift
0800000000003B91        Chrysler_300_SRT8_StreetRacing
0800000000003B0D        Dodge_Viper_2013_StreetRacing
0800000000006EE0        Dodge_Viper_2013_Dragster
080000000001270A        Dodge_Viper_2013_Drift
08000000000038D0        Chevrolet_Corvette_ZR1_StreetRacing
080000000000390B        Chevrolet_Corvette_ZR1_TouringCar
0800000000003704        Chevrolet_Camaro_SS_2010_Rally
0800000000003722        Chevrolet_Camaro_SS_2010_RallyRaid
0800000000003733        Chevrolet_Camaro_SS_2010_StreetRacing
0800000000003795        Chevrolet_Camaro_SS_2010_TouringCar
0800000000012AC4        Chevrolet_Camaro_SS_2010_Drift
08000000000181AD        Chevrolet_Camaro_SS_2010_Dragster
08000000000237A3        Chevrolet_Camaro_SS_2010_Monster
08000000000032F1        Chevrolet_Corvette_C3_StreetRacing
0800000000003272        Chevrolet_Corvette_C2_StreetRacing
0800000000003178        Chevrolet_Corvette_Stingray_2014_StreetRacing
08000000000135A8        Chevrolet_Corvette_Stingray_2014_Drift
080000000001822F        Chevrolet_Corvette_Stingray_2014_Dragster
0800000000002FAD        Cadillac_Escalade_2012_RallyRaid
0800000000002FBA        Cadillac_Escalade_2012_StreetRacing
0800000000003066        Cadillac_Escalade_2012_TouringCar
08000000000026FA        Hover_IVT_01_HoverCraft
0800000000002972        Mini_Countryman_Rally
0800000000002993        Mini_Countryman_RallyRaid
08000000000029A9        Mini_Countryman_StreetRacing
0800000000002888        Lotus_Exige_S_Rally
08000000000028A8        Lotus_Exige_S_StreetRacing
08000000000025FB        Chevrolet_Silverado_2010_RallyRaid
0800000000002609        Chevrolet_Silverado_2010_StreetRacing
0800000000002661        Chevrolet_Silverado_2010_TouringCar
080000000001985F        Chevrolet_Silverado_2010_Monster
08000000000024F1        Cadillac_Eldorado_1957_StreetRacing
08000000000022DA        BMW_Z4_2011_RallyRaid
08000000000022EC        BMW_Z4_2011_StreetRacing
0800000000002423        BMW_Z4_2011_TouringCar
08000000000123D9        BMW_Z4_2011_Drift
0800000000002254        BMW_X6M_E71_StreetRacing
08000000000021E7        BMW_M5_2011_StreetRacing
080000000001246B        BMW_M5_2011_Drift
080000000000216D        Bentley_Continental_2010_StreetRacing
08000000000023B0        Bentley_Continental_2010_TouringCar
08000000000020F6        Aston_Vanquish_StreetRacing
0800000000002082        Aston_V8_Vantage_StreetRacing
0800000000002007        Aston_V12_Zagato_StreetRacing
0800000000001F90        Alfa_8C_StreetRacing
080000000000236D        Alfa_8C_TouringCar
0800000000001F10        Alfa_4C_StreetRacing
080000000000175B        Jet_Sprint_IVT_01_JetSprint
08000000000014F8        Volkswagen_Touareg_2011_RallyRaid
080000000000150C        Volkswagen_Touareg_2011_StreetRacing
0800000000002A37        Pagani_Zonda_TouringCar
080000000000A050        Pagani_Zonda_Hypercar
08000000000013F4        Mazda_RX7_StreetRacing
0800000000006F26        Mazda_RX7_Drift
0800000000001373        Lamborghini_Gallardo_Superleggera_StreetRacin
0800000000002816        Lamborghini_Gallardo_Superleggera_TouringCar
08000000000012C8        Ford_Mustang_GT_2015_StreetRacing
0800000000012E90        Ford_Mustang_GT_2015_Drift
0800000000002745        Ferrari_458_Speciale_TouringCar
0800000000012815        Ferrari_458_Speciale_Drift
080000000002E93A        Ferrari_458_Speciale_Hypercar
08000000000011BE        BMW_M4_F82_StreetRacing
08000000000023ED        BMW_M4_F82_TouringCar
0800000000001051        Helico_IVT_01_Helico
08000000000073D7        Water_Rocket_WR1_PowerBoat
0800000000008CD7        Indian_Chief_Dark_Horse_StreetRacing
0800000000008D59        KTM_1190_RC8_R_2015_MotoGP
0800000000008D6D        KTM_1190_RC8_R_2015_StreetRacing
0800000000001952        Kawasaki_Z1000_MotoGP
0800000000001964        Kawasaki_Z1000_StreetRacing
0800000000000D88        Donzi_27ZR_PowerBoat
0800000000000EAB        Zivko_Edge_540_Propeller
080000000000109D        Zivko_Edge_540_PaintBall
0800000000017AE8        Zivko_Edge_540_AirRace
080000000000970E        Jeep_Wrangler_RallyRaid
0800000000009720        Jeep_Wrangler_StreetRacing
08000000000018A0        Kawasaki_KX450_MotoCross
08000000000018BB        Kawasaki_KX450_RallyRaid
08000000000018C5        Kawasaki_KX450_StreetRacing
08000000000088D3        Ducati_Panigale_MotoGP
08000000000088E1        Ducati_Panigale_StreetRacing
0800000000001BC4        BMW_R1200GS_RallyRaid
0800000000001BDB        BMW_R1200GS_StreetRacing
0800000000001B26        KTM_Superduke_MotoGP
0800000000001B3A        KTM_Superduke_StreetRacing
0800000000001ACD        Ducati_Diavel_MotoGP
0800000000001AD0        Ducati_Diavel_StreetRacing
0800000000001C4F        BMW_S1000RR_MotoGP
0800000000001C61        BMW_S1000RR_StreetRacing
0800000000001CF5        Indian_Scout_StreetRacing
0800000000001AD7        KTM_450EXC_MotoCross
0800000000001ADA        KTM_450EXC_RallyRaid
0800000000001ADD        KTM_450EXC_StreetRacing
08000000000018DE        Kawasaki_H2_MotoGP
08000000000018F2        Kawasaki_H2_StreetRacing
0800000000000E21        Subaru_BRZ_Rally
0800000000000E3E        Subaru_BRZ_StreetRacing
0800000000008A05        Hotrod_A1_StreetRacing
0800000000008AA3        Hotrod_A1_TouringCar
080000000003B668        Hotrod_A1_Monster
080000000007388A        Hotrod_A1_Dragster
0800000000002477        Buggy_A1_RallyRaid
000000000035D148
```


So I opened the server_archetypes.bin file and the entries are there:


Is this correct that the cars from patch cannot be sorted like the others?
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-06-14T16:02:57+00:00
- Post Title: Re: The Crew 1/2 models tool

> Reply from SanJose ↑Tue Jun 14, 2022 10:32 pm at Tue Jun 14, 2022 10:32 pm
>
> 
I cannot find the Plymouth Roadrunner 1970 car.
[p.JPG](https://xentaxbackup.github.io/file/22369_p.JPG)
## Post #33
- Username: SanJose
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 10, 2022 7:46 pm
- Post datetime: 2022-06-14T17:03:24+00:00
- Post Title: Re: The Crew 1/2 models tool

Then why it finds "0800000000002477        Buggy_A1_RallyRaid" or "000000000035D148" which is the last entry on my side. 
Sometimes the last is the Subaru BRZ Rally Raid then the cmd auto-close.
This is how it looks after following all steps:


I'm running out of ideas.
## Post #34
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-06-14T17:51:37+00:00
- Post Title: Re: The Crew 1/2 models tool

> Reply from SanJose ↑Wed Jun 15, 2022 1:03 am at Wed Jun 15, 2022 1:03 am
>
> 
Then why it finds "0800000000002477        Buggy_A1_RallyRaid" or "000000000035D148" which is the last entry on my side. 
Sometimes the last is the Subaru BRZ Rally Raid then the cmd auto-close.
If you get different results every time, it means something intereferes into the process and kills the tool or something.
This must never happen.
## Post #35
- Username: SanJose
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 10, 2022 7:46 pm
- Post datetime: 2022-06-15T10:37:09+00:00
- Post Title: Re: The Crew 1/2 models tool

Will check my antivirus software. AVG is not so friendly for programs from uknown source. This might be the clue why I have so much problems. So shitty  
EDIT:
Well this is not antivirus software. Disabling it did not helped. I will try to find a way to debug the process to get a log or anything, maybe I will find where the problem is .
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-06-15T15:26:00+00:00
- Post Title: Re: The Crew 1/2 models tool

> Reply from SanJose ↑Wed Jun 15, 2022 6:37 pm at Wed Jun 15, 2022 6:37 pm
>
> 
Will check my antivirus software. AVG is not so friendly for programs from uknown source. This might be the clue why I have so much problems. So shitty  
EDIT:
Well this is not antivirus software. Disabling it did not helped. I will try to find a way to debug the process to get a log or anything, maybe I will find where the problem is .
as i said before, log is in windows application log (event viewer)
you dont need to debug it
## Post #37
- Username: SanJose
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 10, 2022 7:46 pm
- Post datetime: 2022-06-17T14:58:57+00:00
- Post Title: Re: The Crew 1/2 models tool

Looks like no log is being created. I've cleared the logs in event viewer then ran the app again and nothing was added. It only captures the log when the cmd crashes.
## Post #38
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-06-17T23:05:27+00:00
- Post Title: Re: The Crew 1/2 models tool

> Reply from SanJose ↑Fri Jun 17, 2022 10:58 pm at Fri Jun 17, 2022 10:58 pm
>
> 
Looks like no log is being created. I've cleared the logs in event viewer then ran the app again and nothing was added. It only captures the log when the cmd crashes.
At the end of your cmd syntax add another line and type:

```
pause
```

then run the process again and post a screenshot with that error that pops up in the cmd window, assuming there is even an error, because at the moment it just sounds a user error, on your part, if that is the case, I'd suggest to starts fresh, retrace your steps and see where your getting stuck and unable to move forward, don't rush and pay close attention.
## Post #39
- Username: SanJose
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 10, 2022 7:46 pm
- Post datetime: 2022-06-20T15:32:08+00:00
- Post Title: Re: The Crew 1/2 models tool

Got it to work finally.

The problem was in Windows DEP settings and Antivirus software. It doesn't allow to read and write data in the folders. Now I got everything sorted out. Even the .bat files are started to working now .
## Post #40
- Username: SanJose
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 10, 2022 7:46 pm
- Post datetime: 2022-06-23T13:51:48+00:00
- Post Title: Re: The Crew 1/2 models tool

Anybody knows where are the additional tuning parts for cars? Like spoilers, rear panels, hoods?

I got 7 .bat executables for each car and I see that there are few tuning parts available. I mean in each created folder there are different parts like wide body, one set of additional bumpers and headlights. But I cannot navigate for the other parts.

Thanks in advance.
