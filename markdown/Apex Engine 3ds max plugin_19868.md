## Post #1
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-03-27T12:03:25+00:00
- Post Title: Apex Engine 3ds max plugin

Following plugin will let you import models from all titles under Apex Engine.

The Hunter: RBM
The Hunter - Primal: RBM
The Hunter - Call of Wild: ADF (modelc, meshc)
Just Cause 2: RBM
Just Cause 3: RBM, ADF (vmodc [StuntAreas])
Just Cause 4: ADF (vmodc [StuntAreas], modelc, meshc)
Mad Max: RBN, RBS
Generation Zero: ADF (modelc, meshc)
RAGE 2: ADF (modelc, meshc)

Enjoy.




Master page.

I will also require from you any and every feedback you can think of.
For plugin, you can create issues in repo.
For everything else here, or on blog. 
Thank you.
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-04-29T16:59:15+00:00
- Post Title: Apex Engine 3ds max plugin

Texture conversion tool has been added.
[https://github.com/PredatorCZ/ApexToolset/releases](https://github.com/PredatorCZ/ApexToolset/releases)
## Post #3
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2019-04-30T13:50:29+00:00
- Post Title: Apex Engine 3ds max plugin

(Just throwing this here in case you missed this title)
Did you try it with Generation Zero? It also runs on the Apex Engine. 

And by the way, awesome release. I'm downloading the games and I'll report any issues.
What do you suggest for extracting the various archives? For example, I cannot find anything for theHunter Primal.

Edit: in fact it's very hard to know what unpacks what. Can you point us to the right direction please?

Thanks!!
## Post #4
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-02T13:22:27+00:00
- Post Title: Apex Engine 3ds max plugin

The Hunter ARC

```
# script for QuickBMS http://quickbms.aluigi.org

endian little
comtype zlib

get arcfile FULLBASENAME
string arcfile += ".arc"
open FDSE arcfile 1

get TAB_SIZE asize
get PAD_SIZE long   # 0x800

for
    savepos CURR_OFF
    if CURR_OFF >= TAB_SIZE
        cleanexit
    endif
    get NAME_CRC long
    get OFFSET long
    get SIZE long
	get dummy long
    goto OFFSET 1
	get SIGN short 1
	goto OFFSET 1
	get SIGN4 long 1
	
	string cstr P "%NAME_CRC%"
	
	if SIGN == 376
		string cstr + ".blz"
		log cstr OFFSET SIZE 1
	else if SIGN4 == 16778241
		string cstr + ".sc"
		log cstr OFFSET SIZE 1
	else if SIGN4 == 67110145	
		string cstr + ".sc2"
		log cstr OFFSET SIZE 1
	else if SIGN4 == 1094993440
		string cstr + ".adf"
		log cstr OFFSET SIZE 1
	else
		log "" OFFSET SIZE 1
	endif
	
next

```


The Hunter Primal ARC

```
# script for QuickBMS http://quickbms.aluigi.org

endian little
comtype zlib

get arcfile FULLBASENAME
string arcfile += ".arc"
open FDSE arcfile 1

get TAB_SIZE asize
get PAD_SIZE long   # 0x800

for
    savepos CURR_OFF
    if CURR_OFF >= TAB_SIZE
        cleanexit
    endif
    get NAME_CRC long
    get OFFSET long
    get SIZE long
    goto OFFSET 1
	get SIGN short 1
	goto OFFSET 1
	get SIGN4 long 1
	
	string cstr P "%NAME_CRC%"
	
	if SIGN == 376
		string cstr + ".blz"
		log cstr OFFSET SIZE 1
	else if SIGN4 == 16778241
		string cstr + ".sc"
		log cstr OFFSET SIZE 1
	else if SIGN4 == 67110145	
		string cstr + ".sc2"
		log cstr OFFSET SIZE 1
	else if SIGN4 == 1094993440
		string cstr + ".adf"
		log cstr OFFSET SIZE 1
	else
		log "" OFFSET SIZE 1
	endif
	
next

```


Not sure who's original author tho, I only modified primal version.

SARC archives from the hunter/primal can be extracted with Gibbed's Just Cause 2 tools.
I expected that Gibbed will release SARC extractor for JC4 and Generation Zero, however there is no such release, so I think I'll just release mine.

ARC archives from the hunter cotw, Generation Zero can be extracted with Gibbed's Just Cause 3 tools. You will need to download mine fork of Just Cause 3 repo, replace bin/project folder with mine and set correct project name in current.txt file, in order to extract correct file names.

You can build dev branch from ApexMax repo, it's fixed for some Generation Zero models to load. Some materials won't load.
## Post #5
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2019-05-04T12:41:14+00:00
- Post Title: Apex Engine 3ds max plugin

Hi,

Thanks for the reply. Sorry I couldn't get back to you earlier.

With your bms script, theHunter and theHunter Primal works 100%.
I tested with several meshes and got everything to work fine, thank you.


@HunterCOTW, apparently you cannot import .MESHC, just .MODELC and these always result in 3ds Max crashing.

Is this how it's supposed to be? After extracting several ARCs I still have a hard time finding .MODELCs, MESHC is more common and their size makes more sense to be a 3D model... But I could be 100% wrong, I'm just guessing here! 
Also there are files with .HRMESHC extension, but I don't think they matter much for now. hehe

And... the texture converter doesn't work for me either using COTW hmddsc files. It always say "Invalid File" on the console. Any clues?

@Generation Zero, I don't have the things I need to build here, but I'm re-downloading the game anyway. We'll see.
## Post #6
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-05T09:10:04+00:00
- Post Title: Apex Engine 3ds max plugin

meshc, modelc and hrmeshc must be together in order to load.
texture converter only accepts ddsc (or dds) files, again ddsc and hmddsc files mush be together in order to extract all data
modelc and meshc tends to be inside SARC archives.
## Post #7
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2019-05-05T15:44:18+00:00
- Post Title: Apex Engine 3ds max plugin

> Reply from PredatorCZ ↑Sun May 05, 2019 5:10 pm at Sun May 05, 2019 5:10 pm
>
> 
meshc, modelc and hrmeshc must be together in order to load.
texture converter only accepts ddsc (or dds) files, again ddsc and hmddsc files mush be together in order to extract all data
modelc and meshc tends to be inside SARC archives.

I used the JustCause3.Unpack on all COTW .ARCs

I got a lot of files, but just 22 .modelc
In comparission, I got 170 .meshc
Having modelc + meshc in the same folder still crashes 3ds here

Similar thing happens to the textures..
Most of my hmddsc does not have a ddsc companions. 


Should I pm you instead of spamming here? lol
## Post #8
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-05T22:48:41+00:00
- Post Title: Apex Engine 3ds max plugin

> Reply from lolwatt ↑Sun May 05, 2019 11:44 pm at Sun May 05, 2019 11:44 pm
>
> 
PredatorCZ wrote: ↑Sun May 05, 2019 5:10 pm
meshc, modelc and hrmeshc must be together in order to load.
texture converter only accepts ddsc (or dds) files, again ddsc and hmddsc files mush be together in order to extract all data
modelc and meshc tends to be inside SARC archives.


I used the JustCause3.Unpack on all COTW .ARCs

I got a lot of files, but just 22 .modelc
In comparission, I got 170 .meshc
Having modelc + meshc in the same folder still crashes 3ds here

Similar thing happens to the textures..
Most of my hmddsc does not have a ddsc companions. 


Should I pm you instead of spamming here? lol

This here.

> Reply from PredatorCZ ↑Sun May 05, 2019 5:10 pm at Sun May 05, 2019 5:10 pm
>
> 
modelc and meshc tends to be inside SARC archives.

in addition most of a ddsc files are inside SARC too

Also you should open Maxscript listener (F11 key), plugin will print any error messages, unfortunetly I didn't secure anitcrash when loading incomplete modelc files. I expected, that most of people will know what files they'll need in order to successfully load stuff.
Apparently I was wrong. 

I wall say it one last time. modelc, meshc and hrmeshc files must be in the same location in order to load.
## Post #9
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-10T11:19:52+00:00
- Post Title: Apex Engine 3ds max plugin

ApexMax V1.4 has been released.

Added material creation for Generation Zero.
Added material creation for The Hunter COtW.
Fixed streamed file linkage for The Hunter COtW.
Fixed crash when loading incomplete stream files for modelc formats.
Fixed crash caused by leftover remap bones, that were not cleaned properly.
Maxscript listener will now show whenever plugin tries to print any information and from now on, user will be always informed properly. User no longer needs to open listener manually.
## Post #10
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-11T09:38:01+00:00
- Post Title: Apex Engine 3ds max plugin

ApexMax V1.5 has been released.

Fixed not loading of RBM, RBN files.
## Post #11
- Username: Ciprianno
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 15, 2019 10:46 am
- Post datetime: 2019-05-15T02:48:12+00:00
- Post Title: Apex Engine 3ds max plugin

How do i import with texture , please help?????????
## Post #12
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2019-05-15T03:18:57+00:00
- Post Title: Apex Engine 3ds max plugin

I'm returning to the same subject.. I don't think the .filelists are complete. 
Are you sure the file dumper is dumping everything we need?

For Generation Zero for example, the characters/robots are complete and everything works.

But if I go to folder -> models\weapons\
All the weapons do not have .meshc and the textures do not have .ddsc, making them impossible to open.

Another instance of this happening, for example, is on \models\manmade\buildings\civilian
All those folders only have .hrmeshc, no .meshc


I could go on with this, but I think you got my point by now..
## Post #13
- Username: Ciprianno
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 15, 2019 10:46 am
- Post datetime: 2019-05-15T03:58:15+00:00
- Post Title: Apex Engine 3ds max plugin

> Reply from lolwatt ↑Wed May 15, 2019 11:18 am at Wed May 15, 2019 11:18 am
>
> 
I'm returning to the same subject.. I don't think the .filelists are complete. 
Are you sure the file dumper is dumping everything we need?

For Generation Zero for example, the characters/robots are complete and everything works.

But if I go to folder -> models\weapons\
All the weapons do not have .meshc and the textures do not have .ddsc, making them impossible to open.

Another instance of this happening, for example, is on \models\manmade\buildings\civilian
All those folders only have .hrmeshc, no .meshc


I could go on with this, but I think you got my point by now..

Use this for extract [https://github.com/kk49/deca/releases](https://github.com/kk49/deca/releases) an you will find all .hrmeshc, and .meshc [](http://www.imagebam.com/image/323f461222274094)
## Post #14
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-15T13:04:41+00:00
- Post Title: Apex Engine 3ds max plugin

> Reply from lolwatt ↑Wed May 15, 2019 11:18 am at Wed May 15, 2019 11:18 am
>
> 
I'm returning to the same subject.. I don't think the .filelists are complete. 
Are you sure the file dumper is dumping everything we need?

For Generation Zero for example, the characters/robots are complete and everything works.

But if I go to folder -> models\weapons\
All the weapons do not have .meshc and the textures do not have .ddsc, making them impossible to open.

Another instance of this happening, for example, is on \models\manmade\buildings\civilian
All those folders only have .hrmeshc, no .meshc


I could go on with this, but I think you got my point by now..

I have all of them.
Are you sure, you're using this? [https://github.com/PredatorCZ/Gibbed.Ju ... Zero/files](https://github.com/PredatorCZ/Gibbed.JustCause3/tree/master/bin/projects/Generation%20Zero/files)
Are you sure, you have Generation Zero set in current.txt?
Do you have this game installed via steam? It works only for them. 
I could post .xml where you can set your own custom game path.
Are you sure, that you extracted ALL SARC files?
## Post #15
- Username: ventuhr
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jan 06, 2017 10:16 pm
- Post datetime: 2019-05-17T06:05:18+00:00
- Post Title: Apex Engine 3ds max plugin

Can anyone confirm if RAGE 2 file structures are that of apex engine instead of Id Tech? if it's true, I wonder if existing apex engine tools works with it.
## Post #16
- Username: Ciprianno
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 15, 2019 10:46 am
- Post datetime: 2019-05-17T06:17:20+00:00
- Post Title: Re: Apex Engine 3ds max plugin

ventuhr     I tried with 2 different tools to extract arhive , but no succes..
## Post #17
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-17T07:07:34+00:00
- Post Title: Re: Apex Engine 3ds max plugin

Archives are similar, if not "same" as those used in Just Cause 4.
## Post #18
- Username: ventuhr
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jan 06, 2017 10:16 pm
- Post datetime: 2019-05-24T15:58:45+00:00
- Post Title: Re: Apex Engine 3ds max plugin

RAGE 2 skeletal mesh sample with texture files included, only General Cross for this one
[https://drive.google.com/file/d/14ZTc4G ... sp=sharing](https://drive.google.com/file/d/14ZTc4Gz2A9TxsV2gDLFQy7Bldfm4Y7sf/view?usp=sharing)

I'll upload more like other skeletal and static ones if needed
## Post #19
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-25T07:48:49+00:00
- Post Title: Re: Apex Engine 3ds max plugin

> Reply from ventuhr ↑Fri May 24, 2019 11:58 pm at Fri May 24, 2019 11:58 pm
>
> 
RAGE 2 skeletal mesh sample with texture files included, only General Cross for this one
https://drive.google.com/file/d/14ZTc4G ... sp=sharing

I'll upload more like other skeletal and static ones if needed

These files are incomplete. You will need meshc, modelc, ddsc files. All of these files are inside ee archive. Those archives cannot be extracted (the header is missing) and I don't know where these data are.

EDIT:
So now I know where these data are, it should be relatively easy to make an extractor.
## Post #20
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-25T15:47:38+00:00
- Post Title: Re: Apex Engine 3ds max plugin

RAGE 2, ee, fl , nl, bl archives now can be extracted with R2SmallArchive.
It's part of Apex Toolset V1.2.
## Post #21
- Username: Ciprianno
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 15, 2019 10:46 am
- Post datetime: 2019-05-25T17:51:55+00:00
- Post Title: Re: Apex Engine 3ds max plugin

I can't extract .ee  with R2SmallArchive   .... , nothing is happen
## Post #22
- Username: rismato
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 06, 2018 6:54 pm
- Post datetime: 2019-05-25T17:57:00+00:00
- Post Title: Re: Apex Engine 3ds max plugin

> Reply from Ciprianno ↑Sun May 26, 2019 1:51 am at Sun May 26, 2019 1:51 am
>
> 
I can't extract .ee  with R2SmallArchive   .... , nothing is happen

Have You config the R2SmallArchive.config?
## Post #23
- Username: Ciprianno
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 15, 2019 10:46 am
- Post datetime: 2019-05-25T19:26:54+00:00
- Post Title: Re: Apex Engine 3ds max plugin

> Reply from rismato ↑Sun May 26, 2019 1:57 am at Sun May 26, 2019 1:57 am
>
> 
Ciprianno wrote: ↑Sun May 26, 2019 1:51 am
I can't extract .ee  with R2SmallArchive   .... , nothing is happen


Have You config the R2SmallArchive.config?
yea...   don't  know how.... , can anyone tell me please?
## Post #24
- Username: ventuhr
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jan 06, 2017 10:16 pm
- Post datetime: 2019-05-26T07:33:59+00:00
- Post Title: Re: Apex Engine 3ds max plugin

Yeah, it doesn't do anything after I dropped .ee files with it.
## Post #25
- Username: rismato
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 06, 2018 6:54 pm
- Post datetime: 2019-05-26T13:56:49+00:00
- Post Title: Re: Apex Engine 3ds max plugin

> Reply from Ciprianno ↑Sun May 26, 2019 3:26 am at Sun May 26, 2019 3:26 am
>
> 
can anyone tell me please?

> Reply from ventuhr ↑Sun May 26, 2019 3:33 pm at Sun May 26, 2019 3:33 pm
>
> 
Yeah, it doesn't do anything after I dropped .ee files with it.

In the configuration file have you enabled the Generate_Log?
## Post #26
- Username: ventuhr
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jan 06, 2017 10:16 pm
- Post datetime: 2019-05-26T16:31:12+00:00
- Post Title: Re: Apex Engine 3ds max plugin

> Reply from rismato ↑Sun May 26, 2019 9:56 pm at Sun May 26, 2019 9:56 pm
>
> 
In the configuration file have you enabled the Generate_Log?

I think I managed to make it work with current settings


Max plugin needs to be updated though, doesn't work (improper file format error) when trying to import mesh, 

Also I think .hrmeshc contains real geometry data that .meshc refers to
## Post #27
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-26T19:08:45+00:00
- Post Title: Re: Apex Engine 3ds max plugin

> Reply from ventuhr ↑Mon May 27, 2019 12:31 am at Mon May 27, 2019 12:31 am
>
> 
Also I think .hrmeshc contains real geometry data that .meshc refers to

modelc contains material data, and refers to meshc.
meshc contains low resolution meshes and refers to hrmeshc
hrmeshc is high resolution mesh, it contains buffers for highest quality meshes.
Multiple modelc files can refer into single meshc file.
hrmeshc files are stored only inside arc files, besause of their size, and because modelc/meshc are duplicated along of many small archives.
Funny thing, is that all collected small archives (~3200) have size ~26GB, after extracting them all, the size of extracted data is ~3GB. This engine seems like a giant bloatware tbh.
## Post #28
- Username: Xulip
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 27, 2019 7:32 am
- Post datetime: 2019-05-26T23:38:00+00:00
- Post Title: Re: Apex Engine 3ds max plugin

> Reply from lolwatt ↑Sat May 04, 2019 8:41 pm at Sat May 04, 2019 8:41 pm
>
> With your bms script, theHunter and theHunter Primal works 100%.
I tested with several meshes and got everything to work fine, thank you.

Hey, can you(or anyone here) help me do this? What do I need to extract Primal files, and how do I do it..? Is it possible to get custom content working in the game, as well(re-compressing or something)..?

Thank you!
## Post #29
- Username: errormdl
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 24, 2017 6:47 am
- Post datetime: 2019-07-24T17:53:05+00:00
- Post Title: Re: Apex Engine 3ds max plugin

Any update on getting the 3ds script to work with Rage 2 models?

here's a link to the bfg extracted if you need something to test with: [https://drive.google.com/file/d/1TDrBb2 ... sp=sharing](https://drive.google.com/file/d/1TDrBb2cmnTyLwD6SjS5WMRT9oFiNfxLK/view?usp=sharing)
## Post #30
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-08-04T18:43:03+00:00
- Post Title: Re: Apex Engine 3ds max plugin

ApexMax V1.6 has been released.

Added RAGE 2 support.
Upgraded to new library build.
Fixed logging for non unicode versions.
Smaller fixes.
## Post #31
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2019-08-12T18:00:21+00:00
- Post Title: Re: Apex Engine 3ds max plugin

*snip*

edit:
*.bsk files for Rage 2 are inside the animations/skeletons folder. everything seems to work now.

keep up the great work!
## Post #32
- Username: Naden
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jun 20, 2017 10:09 pm
- Post datetime: 2019-11-16T09:32:14+00:00
- Post Title: Re: Apex Engine 3ds max plugin

Can you update the max plugin for Max 2020?
Thanks in advance
## Post #33
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-12-01T15:56:31+00:00
- Post Title: Re: Apex Engine 3ds max plugin

ApexMax V1.6.1 has been released.

Added 2020 support.
## Post #34
- Username: Naden
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jun 20, 2017 10:09 pm
- Post datetime: 2019-12-02T18:16:48+00:00
- Post Title: Re: Apex Engine 3ds max plugin

Thanks for the updated version.
## Post #35
- Username: Ciprianno
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 15, 2019 10:46 am
- Post datetime: 2019-12-06T05:09:26+00:00
- Post Title: Re: Apex Engine 3ds max plugin

Can you please update Xplorer plugin for Max 2020?
Thanks.
## Post #36
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-12-07T20:54:47+00:00
- Post Title: Re: Apex Engine 3ds max plugin

> Reply from Ciprianno ↑Fri Dec 06, 2019 1:09 pm at Fri Dec 06, 2019 1:09 pm
>
> 
Can you please update Xplorer plugin for Max 2020?
Thanks.

Xplorer v1.0.1 has been released.

Added support for 2020.
## Post #37
- Username: Naden
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jun 20, 2017 10:09 pm
- Post datetime: 2020-01-17T12:40:19+00:00
- Post Title: Re: Apex Engine 3ds max plugin

Can you also update the HavocMax Plugin to Max 2020?
## Post #38
- Username: Octave
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 22, 2008 3:13 am
- Post datetime: 2020-03-22T17:32:16+00:00
- Post Title: Re: Apex Engine 3ds max plugin

Do you have anything that can process the engine's .streampatch files for terrain? You have some references in your ApexLibrary but I'm unsure how to use it.

```
https://github.com/PredatorCZ/ApexLib/blob/master/src/StreamPatch.cpp
```


I tried compiling the repo in Clion but it keeps failing.

```
https://pastebin.com/LwxHc12P
```
## Post #39
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-03-30T06:25:54+00:00
- Post Title: Re: Apex Engine 3ds max plugin

> Reply from Octave ↑Mon Mar 23, 2020 1:32 am at Mon Mar 23, 2020 1:32 am
>
> 
Do you have anything that can process the engine's .streampatch files for terrain? You have some references in your ApexLibrary but I'm unsure how to use it.
Code: Select allhttps://github.com/PredatorCZ/ApexLib/blob/master/src/StreamPatch.cpp

I tried compiling the repo in Clion but it keeps failing.
Code: Select allhttps://pastebin.com/LwxHc12P

Streampatches are on hold, since I had no experience with marching cubes. I might look at it sometime.

Emulators like cygwin are untested/unsupported, however ApexLib/Tools can be built under Ubuntu with GCC (see travis config).
## Post #40
- Username: jlecoultre
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 20, 2020 4:39 am
- Post datetime: 2022-08-03T18:31:42+00:00
- Post Title: Re: Apex Engine 3ds max plugin

I want to import models from TheHunter COTW but I get this error: "WARNING: [ADF] Uregistered class: AmfMeshHeader (0x6f841426)"

Btw, I extracted the modelc file with DECA. I wonder if I am doing something wrong or maybe the developers modified the format. I can upload the file if needed.
