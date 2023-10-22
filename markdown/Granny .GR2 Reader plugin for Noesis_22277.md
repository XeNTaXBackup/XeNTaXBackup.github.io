## Post #1
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-06-13T18:59:25+00:00
- Post Title: Granny .GR2 Reader plugin for Noesis

Hi,

It all started about 4 months ago when Baldur's Gate 3 was presented, after doing some research  i found that Larian Studios have used Granny format for all there latest games, so i took a gamble and started working on this   
So after months of work I am happy to present my Granny .GR2 Reader plugin for Noesis.  
This plugin has been built to be as generic as possible to support most games and existing variations.

Supported:
1.Skinned + Static Meshes ( 2 UV channels , Normals, Skin Weights)
2.Skeleton
3.Animations - Supported animation includes all knows types including old .gr2 versions.
I have tested on multiple games (see complete list below) , 95% of tested animations work.

Script Options:
Script has a few option that can be found at lines 25-28:
SKELETON_LOAD  -    for loading paired skeleton file change value to 1
ANIMATION_MODE  -  switch between Animation modes, 1 - load paired animation file, 2 - load animation from main file, 0 - disable animation loading
MERGE_SCENE = when set to 1 means merge is active, 0 merge is disabled, should be used only with animation mode 2, will merge all models + skeleton + animation in chosen file to 1 model/Scene 
ANIMATION_TRACK = For files with multiple animation tracks, choose with track to load
MULTIFILE - Multiple option to merge all gr2 files in folder

Material parsing + Auto texturing 
Supported for:
Diablo II: Resurrected
Baldur's Gate III - still needs work

Compression and Usage:
Plugin supports all known compression methods.
Please note that in order to read compressed meshes you need to have a granny2.dll in you Noesis main folder - not all granny2.dll versions support BitKnit compression, if you don’t have one please don’t ask me for a copy.

a nice dance from DOS2:


A carrier from Civ6:


A Minotaur from Neverwinter nights 2:


A Demon from DOS


Here is a list of tested games - some like Neverwinter nights and Divinity: Original Sin were heavily tested since I own the games, others were tested with very few samples I found online or this forum.

Tested Games:
1. Divinity: Original Sin
2. Divinity: Original Sin 2 
3. Neverwinter Nights 2
4. The Elder Scrolls Online
5. EVE Online 
6. Silent Hunter 5
7. Metin2
8. Evil Genius
9. Winter X-Games: Snocross 
10. Sid Meier's Civilization V 
11. Sid Meier's Civilization VI
12. Sacred 2 
13. Generic GR2 files supplied with Granny viewer
14. Demigod 
15. Dungeon Lord
15. Dungeon Siege 3
16. Sevencore MMO 
17. Söldner - Secret Wars
18. Lionheart
19. Beyond Divinity
20. Medal Of Honor
21. Double Dragon Neon
22. Dragon Commander
23. Mechassault 2: Lone Wolf 
24. Amy (PS3)
25. Cars (2006)
26. Stronghold 2 
27. CivCity Rome 
28. Age of Empires III 
29. Age of Empires Online
30. Diablo II: Resurrected
31. Baldur's Gate III

Credits:
Credit to norbyte from DOS fourm - his source code for gr2 to collada was my main reference for Animation phrasing and debugging my own code, can be found at [https://github.com/Norbyte/lslib](https://github.com/Norbyte/lslib)

Version 1.2.1 
all details about update can be found here: [viewtopic.php?f=16&t=22277&start=33](https://forum.xentax.com/viewtopic.php?f=16&t=22277&start=33)


 fmt_GR2reader121.rar
(18.14 KiB) Downloaded 934 times



Version 1.35
can be found here: [viewtopic.php?f=16&t=22277&start=283](https://forum.xentax.com/viewtopic.php?f=16&t=22277&start=283)
## Post #2
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-06-13T19:40:58+00:00
- Post Title: Granny .GR2 Reader plugin for Noesis

I can't wait to Test this with Winter xgames snocross models
## Post #3
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-06-14T00:42:58+00:00
- Post Title: Granny .GR2 Reader plugin for Noesis

Thanks for the tool, it's nice to know someone's "working" to hopefully make BD3 files readable in the future  

Yet i'll have to ask:
I've a bunch of games made with granny engine, many openable with Granny viewer but ofc not exportable~
Now i only preserved the game files for some of them so maybe the missing granny2.dll (from the same game) is the problem i'll see tomorrow.
Here's a list of the "working one" they were quick tests, so not everything may be working correctly.

Demigod: meshes/animation loading correctly.

Dungeon Lord - Steam edition: meshes/animations seems to be loading correctly.

Dungeon Siege 3: animations are working correctly but there's no model... now if my memory serves right the models had a different format than granny, that's why i didn't keep them.

Lionheart: some meshes/animation working. Few animations are throwing errors (nothing special anyway).

Sacred 2: Some animations are working correctly, few are broken, some simply throw an error when loaded together with the model.

Sevencore: it's an old mmo from gpotato/webzen it has closed down. Anyway, meshes/animations are loading so it's good. for ppl interested... try searching the client on the net, worst case i'll upload the extracted files.

Söldner - Secret Wars: Animations are working, but not many meshes are loading (not like there're that many...)


Strange one:
Legend - Hand of God: even with the granny2.dll the game is throwing me this error

> Detected file type: GR2 Reader
>
> Format not supported
>
> Traceback (most recent call last):
>
>   File "C:\Users\LoremIpsum\Downloads\noesisv4417\plugins\python\fmt_GR2reader.py", line 3247, in noepyLoadModel
>
>     for model in Models:
>
> TypeError: 'int' object is not iterable

Would you mind giving some of them a look or you prefer to focus on other things? Don't wana press you, really, just asking.
Thank you again for your time and tool~

Extra: Here's a list of granny using games [http://www.radgametools.com/granny/customers.html](http://www.radgametools.com/granny/customers.html)
## Post #4
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-06-14T05:43:07+00:00
- Post Title: Granny .GR2 Reader plugin for Noesis

Allanoon,
 Thanks for all the testing, i will update the list of tested games.

> Thanks for the tool, it's nice to know someone's "working" to hopefully make BD3 files readable in the future
i must admit i dont have a clue what game you are talking about 

> Söldner - Secret Wars: Animations are working, but not many meshes are loading (not like there're that many...)
if meshes are not loading then there is no mesh data in file, if you think that there is a mesh upload a few samples.

> Legend - Hand of God: even with the granny2.dll the game is throwing me this error
if you notice you are getting error "Format not supported" these means Magic string of the file isnt recognized its probably an easy fix

Please upload samples for all files that are not working and i will take a look (Sacred 2,Lionheart, etc..)
## Post #5
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-06-14T09:09:23+00:00
- Post Title: Granny .GR2 Reader plugin for Noesis

So I gave the snocross models a test, and after i select the corresponding animation .gr2 file i get this error:

It continues to ask me if I want to export anyway, but its not able to do so.

Did you test the games files with a different version?

Heres a mesh:
[https://cdn.discordapp.com/attachments/ ... Punk_H.GR2](https://cdn.discordapp.com/attachments/628005960471805972/721649998059667516/Punk_H.GR2)

and heres a anim file:
[https://cdn.discordapp.com/attachments/ ... t_Idle.GR2](https://cdn.discordapp.com/attachments/628005960471805972/721650075431993424/Punk_CharSelect_Idle.GR2)

Thanks for you work on this format man! 


EDIT:
Guess what dumb Henchman800 forgot! Yeah....putting the granny2.dll in noesis main folder.....
## Post #6
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-06-14T09:30:41+00:00
- Post Title: Granny .GR2 Reader plugin for Noesis

> So I gave the snocross models a test, and after i select the corresponding animation .gr2 file i get this error:
just looking at the error, it not finding your granny2.dll file
did you place it in the main Noesis folder?
## Post #7
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-06-14T10:14:36+00:00
- Post Title: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Sun Jun 14, 2020 5:30 pm at Sun Jun 14, 2020 5:30 pm
>
> 
just looking at the error, it not finding your granny2.dll file
did you place it in the main Noesis folder?

Haha yeah, I posted this as an edit in my previous post ^^
Thanks for the reply though!

Is there an easier method to extract the textures from gr2 files other than with the granny viewer in combination with a graphics ripper?

One more thing:
since you were so successful with the .gr2 format, i was hoping that you know how to handle granny archives aswell.
all the cool sled model of snocross are in this file:
[https://we.tl/t-DgiLqDvxmJ](https://we.tl/t-DgiLqDvxmJ)
I'm assuming they contain .gr2 files aswell.
It would be hella awesome if you could have a look at it!
## Post #8
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-06-14T15:30:58+00:00
- Post Title: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Sun Jun 14, 2020 2:59 am at Sun Jun 14, 2020 2:59 am
>
> 
Hi [...] 

So after months of work I am happy to present my Granny .GR2 Reader plugin for Noesis.  
This plugin has been built to be as generic as possible to support most games and existing variations [...]

I've no words 

Thanks jayn23 for all the effort you are putting, and to share your works with us    

I've read you didn't completely test all  the game in the list since for some of them you owned just some sample. 
If you need more sample from the game you choosed in order to make your script complete, we will send you what you need.


Greetings, 
Drawing
## Post #9
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-06-14T16:46:12+00:00
- Post Title: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Sun Jun 14, 2020 1:43 pm at Sun Jun 14, 2020 1:43 pm
>
> 
Allanoon,
 Thanks for all the testing, i will update the list of tested games.
Thanks for the tool, it's nice to know someone's "working" to hopefully make BD3 files readable in the future 
i must admit i dont have a clue what game you are talking about 

Please upload samples for all files that are not working and i will take a look (Sacred 2,Lionheart, etc..)

My pleasure   
I meant Baldur's Gate 3, BG3, but sleepiness got me and i wrote BD3 lol

Here're the files:
[http://www.mediafire.com/file/5aglxehpj ... le.7z/file](http://www.mediafire.com/file/5aglxehpjcjcn1w/Games_file.7z/file)

There're also Beyond Divinity and Medal of Honor Pacific Assault whose files are giving errors.
Sacred 2 have plenty of model/anims so i only put a few.
## Post #10
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-06-14T18:18:57+00:00
- Post Title: Granny .GR2 Reader plugin for Noesis

> Reply from Henchman800 ↑Sun Jun 14, 2020 6:14 pm at Sun Jun 14, 2020 6:14 pm
>
> 
all the cool sled model of snocross are in this file:
https://we.tl/t-DgiLqDvxmJ
I'm assuming they contain .gr2 files aswell.
It would be hella awesome if you could have a look at it!

I Think i Found a solution...
[https://www.softpedia.com/get/System/Fi ... ctor.shtml](https://www.softpedia.com/get/System/File-Management/RezExtractor.shtml)
Imma Test it tonight!
## Post #11
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-06-14T21:43:54+00:00
- Post Title: Granny .GR2 Reader plugin for Noesis

> Here're the files:
>
> http://www.mediafire.com/file/5aglxehpj ... le.7z/file
>
> 
>
> There're also Beyond Divinity and Medal of Honor Pacific Assault whose files are giving errors.
>
> Sacred 2 have plenty of model/anims so i only put a few.

Beyond Divinity - fixed.
Scared 2 - i have identified main issue and working on a fix should be done in a day or 2.
Medal of Honor - has an annoying issue where 1 model has 2 skeleton, while building the script i assumed 1 skeleton per model (model could have multiple mesh of course), ill see if i can do an easy fix for it, but if i have  to rewrite to much code i will skip this for now at least.
ESO - i was conntacted via PM about some static meshes not working, i have looked at them and my output is identical to what granny viewer is getting but some data is not working correctly (for me and granny viewer), i can get vertex + faces working but normals and uv are corrupted or in weird format. 
Legend - Hand of God - i only took  a 1 minute look but it dosent look like a granny file , maybe they just have extra header and granny data is somewhere inside, i will take a better look once i am done with sacred 2.

once i am done with all fixes i will upload a new version
## Post #12
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2020-06-15T03:59:51+00:00
- Post Title: Granny .GR2 Reader plugin for Noesis

I was trying out your plugin on a WayForward game (Double Dragon Neon), and I get this error.

Any Ideas?

[http://www.mediafire.com/file/vepmp92r4 ... er.7z/file](http://www.mediafire.com/file/vepmp92r4z7esfn/New_folder.7z/file) - links to gr2 files
## Post #13
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-06-15T09:14:08+00:00
- Post Title: Granny .GR2 Reader plugin for Noesis

> I was trying out your plugin on a WayForward game (Double Dragon Neon), and I get this error.

try disabling animation mode, and see if it loads mesh and skeleton, i see error is occurring in animation data process stage.

anyway it seems i have a big backlog of errors to go over and will take some time  

> So I gave the snocross models a test,
HI Henchman800

can you confirm if  games works with aniamtion?
id like to update tested games list if yes, Thanks
## Post #14
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-06-15T18:45:26+00:00
- Post Title: Granny .GR2 Reader plugin for Noesis

Small update:

Beyond Divinity - fixed.
Scared 2 - fixed
Lionheart - fixed
Söldner - Secret Wars - all meshes are loading for me, and i didnt do anything, maybe it was one of the other fixes??   

> Strange one:
>
> Legend - Hand of God: even with the granny2.dll the game is throwing me this error
Legend - Hand of God - is a Granny file, just missing the header,  but in this post [viewtopic.php?t=3045](https://forum.xentax.com/viewtopic.php?t=3045)  its stated that this files contain the header and magic i am looking for..so why isnt it in your sample files? without the header i can identify this as granny file

still working on other games will see what i can do..
## Post #15
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-06-15T21:22:25+00:00
- Post Title: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Tue Jun 16, 2020 2:45 am at Tue Jun 16, 2020 2:45 am
>
> 
Strange one:
Legend - Hand of God: even with the granny2.dll the game is throwing me this error
Legend - Hand of God - is a Granny file, just missing the header,  but in this post viewtopic.php?t=3045  its stated that this files contain the header and magic i am looking for..so why isnt it in your sample files? without the header i can identify this as granny file

still working on other games will see what i can do..

What's funny is that i've a bms script but can't remember where i got it, i didn't make a thread either... anyway here it is:

> get NAME basename
>
> string NAME += ".pak.dat"
>
> 
>
> Open FDSE NAME 1
>
> 
>
> get FILES long 1
>
> 
>
> for i = 0 < FILES
>
>    getct NAME string 0x0d 1
>
>    get TRAIL  byte 1
>
>    get SIZE   long 1
>
>    get OFFSET long 1
>
>    get DUMMY  long 1
>
> 
>
>    log NAME OFFSET SIZE
>
> next i

I made some "i hardly know what i'm doing experiments"   :
Following that link i checked bot model and animations pak but the Hexes he's mentioning are only in the model.pak ... well, no problem, i tried with VGMtoolbox and got some files... interesting enough they only seems to be armor pieces (so static meshes?) also same meshes had different sizes meaning things are lost inside them.

Then i looked at the model (gargoyle one) looked how his Hex ended and from Model.pak tried cutting from the supposed header "B867 B0CA F86D B10F 8472" to the gargyole hex end, the resulting file would load but only showed a white rectangle~ 

Dunno what infos you can get from that ^ anyway... I also found this 

> viewtopic.php?p=27117#p27117
that should be able to extract the files, unfortunately it only works with 32 bit system.

Here:

> http://www.mediafire.com/file/q8bhn0jiq ... rt.7z/file
Are Legend models/animations .pak and .dat if you want to directly check them + In the ESO folders the first files loads and are armor pieces and such, other files throw... yep, errors.
Apologize for the useless blabbing and thank you.

Edit: Another header that's commonly used is "29 DE 6C C0 BA A4 53 2B 25 F5 B7 A5 F6 66 E2 EE" and too is present into the model.pak, animations still got nothing... on a better "view" i noticed that the armor/weapons loaded do load the skeletons.
## Post #16
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-06-16T20:02:13+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Here:
>
> http://www.mediafire.com/file/q8bhn0jiq ... rt.7z/file
>
> Are Legend models/animations .pak and .dat if you want to directly check them + In the ESO folders the first files loads and are armor pieces and such, other files throw... yep, errors.
>
> Apologize for the useless blabbing and thank you.
>
> 
>
> Edit: Another header that's commonly used is "29 DE 6C C0 BA A4 53 2B 25 F5 B7 A5 F6 66 E2 EE" and too is present into the model.pak, animations still got nothing... on a better "view" i noticed that the armor/weapons loaded do load the skeletons.

i looked at the bms script and data models.pak and managed to load some models manually by adding a header.
"29 DE 6C C0 BA A4 53 2B 25 F5 B7 A5 F6 66 E2 EE" and "B867 B0CA F86D B10F 8472" are both 32 bit litle endian magic for granny header,
but they are only part of the header, if someone can show me an example how to have the bms script write these bytes to each file extracted we can get it working.

as for a progress update:
ESO - all files a loading, so no more crashing   , on the down side many of the meshes have corrupted UV , as i stated before my output is identical to that of granny viewer so its not my script, they must have made some custom changes to the file.
animation also seems to work, some files contain multiple animation  - i only load the first one. 

> I was trying out your plugin on a WayForward game (Double Dragon Neon), and I get this error.
Double Dragon Neon - this game is just built unprofessionally if you ask me   for example 1 file contained 46 animation , multiple textures and materials 123 models (multiple mesh for each model)  and 3 skeletons, noesis cant handle so many apparently:


from the samples provided only 1 is loading the others just have to many models...

last game to tackle is Medal of Honor, then i am taking a break  

ill upload new version once  i do some testing make sure i didnt break other stuff that was working
## Post #17
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2020-06-17T00:32:00+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

How do I apply textures to the model? I'm trying with Dragon Commander. Model/Animations works perfect, but can't find a way to apply textures...
## Post #18
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-06-17T07:43:43+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> How do I apply textures to the model? I'm trying with Dragon Commander. Model/Animations works perfect, but can't find a way to apply textures...

Glad to here another Larian Studios games is working, unfortunately most games using Granny format dont store texture/Material data in file 
but use some other systems to mange this. this means for each game i would need to build its own "module" to support auto texturing.
that isnt possible with number of games using this format so i decided to add texture support only for very specific games,
currently planned only BG3  

It would be very easy to manually apply textures in 3ds max or blender.
## Post #19
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-06-17T09:37:40+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Mon Jun 15, 2020 5:14 pm at Mon Jun 15, 2020 5:14 pm
>
> 
HI Henchman800

can you confirm if  games works with aniamtion?
id like to update tested games list if yes, Thanks

Yo!
So the plugin imports characters and animation files as described.
Mesh import works flawlessly!
Character models and their idle animations make no problem when importing:


Map objects, like the fishing bear and the chinese warriors seem to have problems though.
The bears skeleton and animation are looking fine! The skinning though seems to make problems:

(Don't mind the artifacts in the gifs....this is just because i reduced info and used heavy compression)

The chinese warrior does nothing and no animation is playing at all. are the gr2-files treating character and map meshes with animations differently?


well this is at least what i found out 
i've attatched the bears and warriors mesh and animation files here:
[https://cdn.discordapp.com/attachments/ ... amples.zip](https://cdn.discordapp.com/attachments/628005960471805972/722745578865295411/Snocross_GR2-Samples.zip)

Having a look at my topic about Winter X-Games Snocross right here:
[viewtopic.php?f=16&t=21279](https://forum.xentax.com/viewtopic.php?f=16&t=21279)
I found a clumbsy way to export the textures from the .gr2 files. Do you happen to know an easier way for doing so?

And did you have a look at the .REZ archive? sadly the extractor i found online doesn't recognize it as a valid rez-file :-/

Hope I could help with my little research,

PEACE
## Post #20
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-06-17T12:33:21+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Wed Jun 17, 2020 4:02 am at Wed Jun 17, 2020 4:02 am
>
> 
i looked at the bms script and data models.pak and managed to load some models manually by adding a header.
"29 DE 6C C0 BA A4 53 2B 25 F5 B7 A5 F6 66 E2 EE" and "B867 B0CA F86D B10F 8472" are both 32 bit litle endian magic for granny header,
but they are only part of the header, if someone can show me an example how to have the bms script write these bytes to each file extracted we can get it working.

as for a progress update:
ESO - all files a loading, so no more crashing   , on the down side many of the meshes have corrupted UV , as i stated before my output is identical to that of granny viewer so its not my script, they must have made some custom changes to the file.
animation also seems to work, some files contain multiple animation  - i only load the first one.

Unfortunately i've 0 knowledge of these things. IF there's only the need to add one of those headers i wouldn't mind doing it manually since the files are nicely sorted too but that doesn't seems to be the case right? I'll try looking around the net for a solution~
OT question regarding ESO, the files you got from other ppl had names?
## Post #21
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-06-17T18:36:30+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I want to thank you guys for all the help and testing you are doing would have taken me weeks to do.

> The chinese warrior does nothing and no animation is playing at all. are the gr2-files treating character and map meshes with animations differently?

i checked the animation and it only has 1 frame, so it is static, i checked with my best friend Granny viewer    and it is indeed showing the exact same "static animation"

as for the bear i checked the weights and they are applied correctly, what i think is wrong is the axis the mesh is created on, and the one the animation is are not the same causing this distorted mesh. i dont think its fixable sorry

> well this is at least what i found out 
>
> Having a look at my topic about Winter X-Games Snocross right here:
>
> viewtopic.php?f=16&t=21279
>
> I found a clumbsy way to export the textures from the .gr2 files. Do you happen to know an easier way for doing so?
>
> 
>
> And did you have a look at the .REZ archive? sadly the extractor i found online doesn't recognize it as a valid rez-file :-/
>
> 
>
> Hope I could help with my little research,

i took a look at you "clumbsy way" unfortunately i cant help since textures in file are stored in compressed .bik format which i have no clue how to read.
regarding the .REZ archive, each game has its own archive, as far as i know there are no official GR2 Archive, and trying to reverse this would be  instead of working on improving my gr2 reader, what i can say is it looks to be compressed with zlib you can try aluigi tool to decompress all files and take a look if the first 16 bytes for those files is the same as other files, if  yes they are granny files.

> Unfortunately i've 0 knowledge of these things. IF there's only the need to add one of those headers i wouldn't mind doing it manually since the files are nicely sorted too but that doesn't seems to be the case right? I'll try looking around the net for a solution~
>
> OT question regarding ESO, the files you got from other ppl had names?

If you find an example how to do this, i can write header that basically does nothing and skips to the data section, in a format that my script can work. but there is no rush i have more than enough bugs to deal with   
and no ESO files were just numbers.

i actually own ESO and tried extracting the files myself but failed miserably with this error, do you know what i am doing wrong?
## Post #22
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-06-17T20:31:53+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Thu Jun 18, 2020 2:36 am at Thu Jun 18, 2020 2:36 am
>
> 
The chinese warrior does nothing and no animation is playing at all. are the gr2-files treating character and map meshes with animations differently?

i checked the animation and it only has 1 frame, so it is static, i checked with my best friend Granny viewer    and it is indeed showing the exact same "static animation"

as for the bear i checked the weights and they are applied correctly, what i think is wrong is the axis the mesh is created on, and the one the animation is are not the same causing this distorted mesh. i dont think its fixable sorry
well this is at least what i found out 
Having a look at my topic about Winter X-Games Snocross right here:
viewtopic.php?f=16&t=21279
I found a clumbsy way to export the textures from the .gr2 files. Do you happen to know an easier way for doing so?

And did you have a look at the .REZ archive? sadly the extractor i found online doesn't recognize it as a valid rez-file :-/

Hope I could help with my little research,


i took a look at you "clumbsy way" unfortunately i cant help since textures in file are stored in compressed .bik format which i have no clue how to read.
regarding the .REZ archive, each game has its own archive, as far as i know there are no official GR2 Archive, and trying to reverse this would be  instead of working on improving my gr2 reader, what i can say is it looks to be compressed with zlib you can try aluigi tool to decompress all files and take a look if the first 16 bytes for those files is the same as other files, if  yes they are granny files.

Thanks for taking the time man!
## Post #23
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2020-06-18T02:09:09+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

"i actually own ESO and tried extracting the files myself but failed miserably with this error, do you know what i am doing wrong?"

You need to put the path to ESO in quotes because there are spaces in the folder name, so:

C:\>YourPathToESOExecutable\EsoExtractData "D:\SteamLibrary\steamapps\common\Zenimax Online\The Elder Scrolls Online\game\client\game.mnf" \export\pathToYourExportFolderProbablyAlsoInQuotes\

Also, the extraction tool available at [https://www.esoui.com/downloads/info125 ... tData.html](https://www.esoui.com/downloads/info1258-EsoExtractData.html) only extracts a few files with the proper names for me.  The rest are numbers with correct extension, so you have to manually rename them. Still, I've managed to find many of the correct textures and apply them to meshes captured by Ninja Ripper, but it would be so much better to be able to convert the files directly from the GR2s.  Thanks for all your work on this,
## Post #24
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-06-18T13:28:47+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> You need to put the path to ESO in quotes because there are spaces in the folder name, so:
>
> 
>
> C:\>YourPathToESOExecutable\EsoExtractData "D:\SteamLibrary\steamapps\common\Zenimax Online\The Elder Scrolls Online\game\client\game.mnf" \export\pathToYourExportFolderProbablyAlsoInQuotes\

thanks for the tip, ill try it out as soon as i get back home from work

ill take a look if i can figure out why the UV are corrupted , but my main focus is getting the meshes and animations working correctly.

> captured by Ninja Ripper, but it would be so much better to be able to convert the files directly from the GR2s. Thanks for all your work on this,
do you have by any chance a model you ripped using ninja ripper with correct UV and and its corresponding gr2 file?
i am  looking at the data and the uv and normal data isnt making sense to me.
its a 36 bytes block
12 - Bytes - positions
4 bytes  FF FF FF FF 
10 Bytes yields numbers that cant be UV or Normal's like nan - file is telling me these 12 bytes are the noramls
2 bytes FF FF
8 Bytes - yields numbers that cant be UV  like nan - and this looks like uv if i were getting reasonable numbers
## Post #25
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2020-06-20T02:55:36+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> do you have by any chance a model you ripped using ninja ripper with correct UV and and its corresponding gr2 file?

I sent you a PM
## Post #26
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-06-25T14:16:09+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Here is my updated script

Iv have made many bug and feature fixes some of them include:

1. fixed rare instance that mesh data was being deleted by the script before being processed by noesis
2. fixed rare issue where some data could be read as big endian rather than small endian
3. added support for dynamic amount of weights - previously was only 4 any other number would cause a crash
4. added support for files with multiple animation in file - currently i read only first animation data
5. added support for files with multiple skeletons under the same model (in all cases were dummy bones )
6. re did my animation and skeleton building ,fixed many issues but caused some issues with models that previously worked, to address this 
i added at line 21 SKELETON_DEBUG = 0, if you skeleton inst loading correctly try changing this to SKELETON_DEBUG = 1.
only game i know this affects is Winter X-Games: Snocross, this game should be run in Mode = 1

and many other fixes... 

known issues:
1. rigid bodies (like props, guns etc..) that dont have wights dont attach to model - will be fixed in future update.
2. few animations dont work correctly
3. ESO models + skeletons + animations seem to work , uv and normals are still corrupted
4. files with to many models give error and crash - i will see in the future what can be done about it

i am currently planning as a future update to redo a very big part of the code to support user control over multiple animation, and just to make the code cleaner, currently it is a huge mess   , but that is probably weeks away.

please check this update and let me know if everything works
## Post #27
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-06-25T15:26:11+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thx for the Work jayn.

Btw can anyone share ESO Client?
## Post #28
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-06-26T18:20:51+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thanks for the update jayn, it's working nicely!   
Yet a question regarding ESO, or maybe it's a noesis use that i can't remember. I see that the game divides the skeleton from the meshes (ex. dat 108, mesh 128084-085 got the skeleton at 128297) but i can't "merge" them, so the meshes aren't rigged if i extract them. Is there some command i'm missing?

Also from a fast look:
Dat 000 to 095 there're some random .dds and files which i dunno what use they have.
096 to 100 have .gr2 animation files.
101 to 104 some dunno files.
105 to 117 there're .gr2 model files (mounts, enemies, equipments).
118 to 128-129 There're like pictures and maps .dds
130 to 158 seems to contain models textures .dds
159 to 180~ still textures but i think they're Static meshes one .dds
Then i stopped~
## Post #29
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-06-27T17:58:43+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Thanks for the update jayn, it's working nicely! 
>
> Yet a question regarding ESO, or maybe it's a noesis use that i can't remember. I see that the game divides the skeleton from the meshes (ex. dat 108, mesh 128084-085 got the skeleton at 128297) but i can't "merge" them, so the meshes aren't rigged if i extract them. Is there some command i'm missing?

Glad its working correctly, it took me over a week to fix a bug that was causing 30% of animations from  beyond divinity  to "explode" lol
i nearly gave up. now that almost everything seems to be working i am going to work an adding new features.

let me know if i understand correctly,
your saying mesh and skeleton files are stored in different files the same way for most other games mesh/skeleton and animation are stored in different files? but i have some samples that mesh and skeleton are on the same file...
i guess i can add on option to load a skeleton file separately from mesh file, just upload a few samples for me to test with please.
## Post #30
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-06-27T21:33:24+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Sun Jun 28, 2020 1:58 am at Sun Jun 28, 2020 1:58 am
>
> 
Glad its working correctly, it took me over a week to fix a bug that was causing 30% of animations from  beyond divinity  to "explode" lol
i nearly gave up. now that almost everything seems to be working i am going to work an adding new features.

let me know if i understand correctly,
your saying mesh and skeleton files are stored in different files the same way for most other games mesh/skeleton and animation are stored in different files? but i have some samples that mesh and skeleton are on the same file...
i guess i can add on option to load a skeleton file separately from mesh file, just upload a few samples for me to test with please.

Basically yeah
Also may i ask the "names" of the files you got? The only full meshes i found are like pets/mounts/enemies not based on the characters races and all were always boneless. They're easily findable as the file size is around 200kb-1mb~
[https://www.mediafire.com/file/xpdkuj8y ... e.rar/file](https://www.mediafire.com/file/xpdkuj8yxh5dln3/ElderScrollOnline.rar/file)
Apologize if they're only a few, i'll look for more if you need, matching should be correct.
And as always, thank you for your time
## Post #31
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-06-28T19:39:01+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Also may i ask the "names" of the files you got? The only full meshes i found are like pets/mounts/enemies not based on the characters races and all were always boneless. They're easily findable as the file size is around 200kb-1mb~

the start at 106615 and end at 113529 - many are just static mesh, but some are animated like a castle exploding animation etc...
the only characters that i have tested are samples i found online.

> Apologize if they're only a few, i'll look for more if you need, matching should be correct.
>
> And as always, thank you for your time

i am happy someone is finding this useful .
## Post #32
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2020-06-28T22:29:12+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> i am happy someone is finding this useful

I am definitely loving this tool. I put ESO aside for the moment and concentrated on Divinity Original Sin 2.  Unlike most I am usually more interested in the backgrounds and static meshes and everything works perfectly for that game. Thanks again
## Post #33
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-06-29T09:03:08+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> I am definitely loving this tool. I put ESO aside for the moment and concentrated on Divinity Original Sin 2. Unlike most I am usually more interested in the backgrounds and static meshes and everything works perfectly for that game. Thanks again

Happy to here it    
if your using using those static meshes to render sceneries etc.. post some pics of your work,  a while ago someone sent renders he did using my warhammer script and that was really cool.

Specifically for DOS2 i  am thinking of adding  in the future (when i am done reworking my script) auto texturing support, assuming i can figure it out.
## Post #34
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-07-09T20:00:27+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Version 1.2 released:
Script is in first post
[viewtopic.php?f=16&t=22277&start=0](https://forum.xentax.com/viewtopic.php?f=16&t=22277&start=0)

Changes:
1. "Under the hood" - re wrote hundreds lines of code - code is now much cleaner, and allows for much easier integration of new features.
2. Added option to load Paired skeleton file, you can now load mesh from one file and skeleton from another file.
3. Added option to merge entire Scene/File to one model - this means that all models/skeletons/and animation will load at once, this will allow to overcome issue that noesis cant load to many Models at once,(Double Dragon Neon samples are now working).
4. Added option to choose which animation track to load for files containing multiple animations.
5. Rigid meshes are now bound correctly to bones (no more static eyes while body is moving or gun staying static while hand is moving).
6. Fixed Orientation issue that was affecting a few skeletons (only Winter X-Games: Snocross to be honest).
7. Meshes are now separated by polygroups - this was added due to some games assigning UV by polygroups instead of using multiple UV channels - now uv for these models will load correctly.
8. some bug fixes i introduced in my previous update.

*As far as all my testing has Gone:
Meshes - works 100%  - not including UV of static ESO meshes
Skeletons - works 100%
Animations - 98 samples out of about 100 tested worked correctly, i would love to get some help with those that dont as i have no clue how to fix them

All Features Usage:
SKELETON_LOAD = 0    #for loading paired skeleton file change value to 1
ANIMATION_MODE = 2   #switch between Animation modes, 1 - load paired animation file, 2 - load animation from main file, 0 - disable animation loading
MERGE_SCENE = 1      #if set  = 1 means merge is active, 0 merge is disabled, should be used only with animation mode 2, will merge all models + skeleton + animation in chosen file to 1 model/Scene 
ANIMATION_TRACK = 1  #for files with multiple animations - choose animation to load, 1 - will load first animation, 2 second animation etc... , in case you choose a animation number that dosent exist it will default to first animation

Known issues:
1. those 2 animation that dont work correctly.
2. Files that were created with different orientation for example mesh with Z as up vector and skeleton file with X as up vector (apply's to animation as well) dont load correctly, i have tried and so far failed to get to work correctly - this is seen with bear model from Winter X-Games: Snocross.

new script is posted in first post - all older version are deleted,
if no bugs are found by you guys i will consider this release the finale one until BG3 is released - at that time i will try to add auto-texturing support for the game (still hoping its in .GR2 format )

Please report any bugs you might encounter 

some pics to illustrate new features:
Using old script you would get chair and granny on separate scenes and eyes and jewelry were static while rest of body was moving.
Now with merge feature turned on: 


user control over Animation track :
first picked track 1 - 

then picked track 3 -
## Post #35
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-07-13T12:53:02+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Ehi Jayn i checked some DDN and ESO files this week.
Double Dragon seems to work nicely, i only had an issue with 1 animation not loading for a model, throwing this error



But sincerly w/e~

For ESO i'm slowing "checking" all the animations when i've time. I've incurred in 2 errors from time to time.
Note i'm loading the anims on the skeletons i've linked in my previous post so they're not the correct ones.


Could this error be caused by the completely wrong skeleton of a model? As from the debug log i see that it immediately throws it.

The other one is this, from the debug log i see that it's loading the tracks but it throws the error at a certain point.

> ........
>
> Track.Name mshBn_hairSide_R
>
> len 97
>
> i at lease make it here
>
> Track.Name mshBn_index01_L
>
> len 97
>
> i at lease make it here
>
> Track.Name mshBn_index01_R
>
> len 97
>
> i at lease make it here
>
> Track.Name mshBn_index02_L
>
> len 97
>
> i at lease make it here
>
> Track.Name mshBn_index02_R
>
> len 97
>
> i at lease make it here
>
> Track.Name mshBn_index03_L
>
> len 97
>
> i at lease make it here
>
> Track.Name mshBn_index03_R
>
> len 97
>
> i at lease make it here
>
> Track.Name mshBn_loinCloth01_B
>
> len 97
>
> i at lease make it here
>
> Track.Name mshBn_loinCloth01_F
>
> len 97
>
> i at lease make it here
>
> Track.Name mshBn_loinCloth02_B
>
> len 97
>
> i at lease make it here
>
> Track.Name mshBn_loinCloth02_F
>
> len 97
>
> i at lease make it here
>
> Track.Name mshBn_mouthRoot
>
> len 97
>
> i at lease make it here
>
> bad translation
>
> Traceback (most recent call last):
>
>   File "C:\Users\LoremIpsum\Downloads\noesisv4417\plugins\python\fmt_GR2reader.py", line 3261, in noepyLoadModel
>
>     anims,frameRate = animation(model,bones, ANIMATION_MODE, None,frameRate)
>
>   File "C:\Users\LoremIpsum\Downloads\noesisv4417\plugins\python\fmt_GR2reader.py", line 3153, in animation
>
>     Dummy.PositionCurve.Controls , Dummy.PositionCurve.Knots = GetTranslation(Track.PositionCurve)
>
> TypeError: 'NoneType' object is not iterable

My doubts are that i'm getting these errors 'cause i'm using the wrong skeletons... but others "near" animations works fine and they kinda seems to be in a row...

Here are a few granny2 eso files.
[https://www.mediafire.com/file/cdyhh108 ... rs.7z/file](https://www.mediafire.com/file/cdyhh108zzlgrtb/errors.7z/file)
## Post #36
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-07-13T20:07:29+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> My doubts are that i'm getting these errors 'cause i'm using the wrong skeletons... but others "near" animations works fine and they kinda seems to be in a row...

well the problem was with my code i missed an if condition, it was an animation type that is so rarely used i didn't have enough references.
anyway all ESO anim are working now,

can you please upload  Double Dragon  file that is giving you that error? i want my script to be as good as possible.
thnaks
## Post #37
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-07-13T22:26:57+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Sure, i couldn't find other tracks giving the error from the ones i checked :\
The one is n° 34.
[https://www.mediafire.com/file/pocvkjkc ... DN.7z/file](https://www.mediafire.com/file/pocvkjkcj1l93k1/DDN.7z/file)
## Post #38
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-07-14T18:49:38+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I wish all bugs were this easy to fix   

Version 1.2.1 updated in main post  - ESO and DDN are working correctly now
## Post #39
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2020-07-15T18:18:48+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

@jayn23
Hey, great plug-in it works verry well for the games i've tested so far.
I do have a game called AoE Online and also uses .gr2 format + .gr2.precomp files. Not sure what those are exactly.
I tried opening the .gr2 file but Noesis throws out an error:
[https://imgur.com/xmKBjwK](https://imgur.com/xmKBjwK)
Not sure what it means...
Are you willing to take a look at the files?
[https://mega.nz/folder/iIlXzJYL#9NSg8CNlKMSBpC7Dq3gxyA](https://mega.nz/folder/iIlXzJYL#9NSg8CNlKMSBpC7Dq3gxyA)

Regards,
## Post #40
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-07-16T18:10:23+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Hey, great plug-in it works verry well for the games i've tested so far.
>
> I do have a game called AoE Online and also uses .gr2 format + .gr2.precomp files. Not sure what those are exactly.
>
> I tried opening the .gr2 file but Noesis throws out an error:

Hi,

error says its not finding your granny2.dll file needed for compressed .gr2 files.
i am guessing other games you tested had uncompressed gr2 files, make sure to put the file in you main noesis folder.
by the way can you update which games you have tested?

I did find that one of you files dosent load since it uses bytes instead of floats for vertices - never seen this before, i will update my code to support this in the future

heres your gurd tower by the way
## Post #41
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2020-07-16T19:50:22+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hey,
Yes only the death_anim.gr2 loads into Noesis, all the other ones gives me an error.
But like you said it uses bytes instead of floats for vertices. I'm already glad you know what the issue was and that you will include it in your script.
If i find more games with .gr2 format, i'll update it here! 

Thanks,
## Post #42
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-07-23T11:17:47+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Can anyone post a Link for EOS Client?

Thx!
## Post #43
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-08-04T18:16:14+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thank you for this great Noesis script, really nice work.
I tried on the game called Cars from 2006 and models/animations work nicely.

Also wanted to try other games, unfortunately there's no unpacker/extractor for them so its a dead end.
## Post #44
- Username: DarthKiller454
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 25, 2016 10:49 am
- Post datetime: 2020-08-14T02:09:33+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

So I got around testing this little piece with CivCity Rome and Stronghold 2 and Legends. 
Everything works with meshes, rigging and they have proper re-exportable results allowing me to edit the core-meshes.

I however ran into an issue when I tried to export a .gr2 attack animation cause I wanted to reduce it's frames so the animation is played faster.
 (Yeah, weird that the animation length is tied to the framecount but it seems it is)

The "core" animation still existed and was perfectly previewable in Noesis. I also assured that the animation itself wasn't weirdly broken and with some .gr2 exporter for good ol' 3dsmax7 I tested the resulting export but the result was always corrupted to some point.

SMD: the 6th frame aswell as some distortion starting from like the 18th frame caused the animation to weirdly mirror itself aswell as do some unintended backflip fallover feetkick while swinging a sword.

FBX: All bones seem to not be connected to each-other, After exporting is as smd (from where I expect it to work better). I can see that the core animation itself is there but the root-bone is not being exported with and thus the very "motion" is missing

DAE. This one looked promising.. Everything looked fine in blender except it was upside down. Getting it upwards caused some similar issues with that backflipping to reappear again. Once exported I noticed how for some reason no bone was moving except the very root bip01 one. Weird.

I have attached the files I used and maybe you can explain what went wrong.
[civcityanim.rar](https://xentaxbackup.github.io/file/18601_civcityanim.rar)
## Post #45
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-08-14T05:11:30+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> DAE. This one looked promising.. Everything looked fine in blender except it was upside down. Getting it upwards caused some similar issues with that backflipping to reappear again. Once exported I noticed how for some reason no bone was moving except the very root bip01 one. Weird.

Hi,

my script only handles the import of gr2 data and does nothing for the export that is done by the built in plugins of noesis, but i did do some experimenting. on 3DS MAX since that is my goto 3D modeling software ,
importing with DAE gave me that same backflip you described, i then downloaded the openCollada plugin and used it to import the DAE instead of the built in plugin and it worked perfectly, but wiredly enough after exporing and reimporting an edited version animation was all wrong...
## Post #46
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-09-07T17:22:13+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Thu Jun 18, 2020 2:36 am at Thu Jun 18, 2020 2:36 am
>
> 


i took a look at you "clumbsy way" unfortunately i cant help since textures in file are stored in compressed .bik format which i have no clue how to read.
If you dump the texture as a bik file?
RAD has free tools to convert them to many different formats.

VERY nice work you've done here Mate!
  

Just looking at your script I see brilliance!
## Post #47
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2020-09-08T04:03:52+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

This tool looks very promising! One question tho. I KNOW I've played some games that use this engine, but I don't know which ones, and I know that I wanted models from those games. Does anyone have a decent list of the games that use the Granny Engine?
## Post #48
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-09-08T04:48:13+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> If you dump the texture as a bik file?
>
> RAD has free tools to convert them to many different formats.
>
> 
>
> VERY nice work you've done here Mate!
>
>   
>
> 
>
> Just looking at your script I see brilliance!

Thanks a lot mate means a lot coming from a gr2 master   

since i have you here, i wonder if i posted those few animations that dont work correctly maybe you can give me an idea where the problem is 
and how to fix them.

Regarding the textures 
Do you mean i could extract the compressed texture data, write it to a file and use a conversion tool..interesting but wouldn't i need to manually add a specific header?
or do you mean the tool can extract directly from the gr2 file?
I actually have a bik source files from a game that had all it source leaked years a ago, but i never tried writing a script for it was just to lazy  


> This tool looks very promising! One question tho. I KNOW I've played some games that use this engine, but I don't know which ones, and I know that I wanted models from those games. Does anyone have a decent list of the games that use the Granny Engine?
they have on the official site a partial list of games using the granny format
[http://www.radgametools.com/granny/customers.html#games](http://www.radgametools.com/granny/customers.html#games)
## Post #49
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-09-08T22:09:43+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Tue Sep 08, 2020 12:48 pm at Tue Sep 08, 2020 12:48 pm
>
> 


Thanks a lot mate means a lot coming from a gr2 master   

since i have you here, i wonder if i posted those few animations that dont work correctly maybe you can give me an idea where the problem is 
and how to fix them.

You got me on the animation stuff so I do believe your a GR2 Master yourself!
 

Yeah. I can check those other files and see if I spot something.
## Post #50
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-09-08T23:19:46+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

For some info on GR2 files here's my 010 header information.

// Define structures for Magic Block, header and Section Indexes in Gr2 files

typedef struct {   // GR2fh
    quad   GR2Magic[2]<hidden=true>;
    UINT   HeaderSize<comment="Size of all information before the start of Section 0">;
    LONG   Unknown_info[3]<hidden=true,format=hex>;
} GR2FILEHEADER;

typedef struct {    // GR2ih
    UINT  File_format_revision <format=decimal>;
    UINT  File_Size_in_bytes;
    UINT  CRC <format=hex,comment="CRC of file (from begin of section array up to EoF). Algoritm CRC-32">;
    UINT  SectionArrayOffset <bgcolor=0xffffb0,fgcolor=cRed,comment="Offset to section array">;
    UINT  SectionArrayCount <comment="Total number of sections">;
    UINT  Unknowns[4]<hidden=true,format=hex>;
    UINT  Tag<format=hex>;
    UINT  Unknown[8]<hidden=true,format=hex>;
} GR2INFOHEADER;

typedef struct {   // Sectionsinfo
    UINT  Format<comment="Compression Format">;
    UINT  Pointer<format=hex,bgcolor=cLtGreen,comment="Start of section data">;
    UINT  True_Block_Size_in_file<comment="Compressed Data size">;
    UINT  Block_Size_In_file<comment="Actual amount of Data uncompressed">;
    UINT  Internal_Alignment<comment="offset">;
    UINT  Unknown[2]<bgcolor=cLtYellow,hidden=true>;
    UINT  Another_Pointer<format=hex,bgcolor=cLtGreen,comment="Will explain at a later date">;
    UINT  WTH[3]<bgcolor=cLtYellow,hidden=true>;
} SECTIONS;

/*Sections as used in SH5 GR2 files.
  NOt all GR2 files follow this layout.

         0 - MainSection
	 1 - RigidVertexSection
	 2 - RigidIndexSection
	 3 - DeformableVertexSection
	 4 - DeformableIndexSection
	 5 - TextureSection
	 6 - DiscardableSection
	 7 - UnloadedSection */


Now I have MUCH more information in other files used in 010 if you need that.
## Post #51
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-09-09T11:14:49+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Yeah. I can check those other files and see if I spot something.

Thanks a lot for taking a look at it   , i really tried everything but couldn't get these to work, and obviously they work perfectly in the granny viewer...

So here is a sample of gr2 file where animation isn't working correctly:
i try to show in the gif below, at frame 0 skeleton looks correct - so i am loading the skeleton/frame 0 correctly.
you will notice that both files have the same issue where 1 side seems to function correctly while the other is all messed up







 v_Wuestenspinne_run_bh.rar
(25.6 KiB) Downloaded 19 times
## Post #52
- Username: CBack
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 31, 2014 10:22 am
- Post datetime: 2020-10-02T10:50:07+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hey jayn, thanks a lot for this amazing plugin and for your hard work on it!

I have a request regarding The Elder Scrolls Online GR2 animations. Could you, please, add support for exporting it to FBX at some point?

Currently when I try to view them in Noesis, it says that the file cannot be viewed but offers to try and export it but, unfortunately, the export doesn't work as no matter which export options I choose, nothing happens and the file just doesn't get created.

I attach a couple of ESO animation files and a skeleton that seems to work well with them in Granny Viewer in case you don't have access to the game or don't want to unpack the files yourself.

Let me know if you need anything else. Thanks again!
[eso_animation.rar](https://xentaxbackup.github.io/file/18791_eso_animation.rar)
## Post #53
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-10-02T14:33:17+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Hey jayn, thanks a lot for this amazing plugin and for your hard work on it!
>
> 
>
> I have a request regarding The Elder Scrolls Online GR2 animations. Could you, please, add support for exporting it to FBX at some point?
>
> 
>
> Currently when I try to view them in Noesis, it says that the file cannot be viewed but offers to try and export it but, unfortunately, the export doesn't work as no matter which export options I choose, nothing happens and the file just doesn't get created.
>
> 
>
> I attach a couple of ESO animation files and a skeleton that seems to work well with them in Granny Viewer in case you don't have access to the game or don't want to unpack the files yourself.
>
> 
>
> Let me know if you need anything else. Thanks again!

Hi CBack
I took a look at your samples and both seem to work fine, make sure your have animation mode set to "1" and try loading it.
also make sure you are using the latest version of the script 1.2.1.
## Post #54
- Username: CBack
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 31, 2014 10:22 am
- Post datetime: 2020-10-02T16:55:56+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Fri Oct 02, 2020 10:33 pm at Fri Oct 02, 2020 10:33 pm
>
> 
Hey jayn, thanks a lot for this amazing plugin and for your hard work on it!

I have a request regarding The Elder Scrolls Online GR2 animations. Could you, please, add support for exporting it to FBX at some point?

Currently when I try to view them in Noesis, it says that the file cannot be viewed but offers to try and export it but, unfortunately, the export doesn't work as no matter which export options I choose, nothing happens and the file just doesn't get created.

I attach a couple of ESO animation files and a skeleton that seems to work well with them in Granny Viewer in case you don't have access to the game or don't want to unpack the files yourself.

Let me know if you need anything else. Thanks again!

Hi CBack
I took a look at your samples and both seem to work fine, make sure your have animation mode set to "1" and try loading it.
also make sure you are using the latest version of the script 1.2.1.
How do I set the animation mode to "1"? I can't seem to figure it out on my own and good ol Google doesn't help either
## Post #55
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-10-02T18:58:58+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from CBack ↑Sat Oct 03, 2020 12:55 am at Sat Oct 03, 2020 12:55 am
>
> 
How do I set the animation mode to "1"? I can't seem to figure it out on my own and good ol Google doesn't help either
Notepad/Notepad++/Python etc and edit line below.



Capture.PNG (41.43 KiB) Viewed 171 times
## Post #56
- Username: CBack
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 31, 2014 10:22 am
- Post datetime: 2020-10-02T21:48:48+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from mono24 ↑Sat Oct 03, 2020 2:58 am at Sat Oct 03, 2020 2:58 am
>
> 
CBack wrote: ↑Sat Oct 03, 2020 12:55 am
How do I set the animation mode to "1"? I can't seem to figure it out on my own and good ol Google doesn't help either 

Notepad/Notepad++/Python etc and edit line below.

Yes, that did the trick. Thank you!
## Post #57
- Username: CBack
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 31, 2014 10:22 am
- Post datetime: 2020-10-05T14:39:59+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hey jayn, I have one more question if you don't mind.

Would it somehow be possible to load skeleton and animation data from GR2 but load meshes from another format, say OBJ?

The reason I'm asking is because I'd like to apply animations to humanoid characters in the Elder Scrolls Online but the problem with them is that they are generated in-game from many separate pieces so it's not really possible to manually replicate them outside the game. I can get their full models with Ninja Ripper in OBJ format but they lack bones, of course.

If this is something that you can look into, I attach a basic humanoid mesh, a skeleton that visually seems to fit it and a basic idle animation that seems to work great with that skeleton.
[ESO - humanoid mesh, skeleton, animation.rar](https://xentaxbackup.github.io/file/18799_ESO - humanoid mesh, skeleton, animation.rar)
## Post #58
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-10-05T17:50:02+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Would it somehow be possible to load skeleton and animation data from GR2 but load meshes from another format, say OBJ?

unfortunately using ninja ripper wouldn't preserve the weights data needed to bind skeleton to the mesh.
i know its a big hassle but your going to have to load all of the meshes separately using my script to preserve skin data, or if you know you way around 3ds max/blender you could easily skin the obj mesh  to skeleton.

sorry i couldn't be of more help
## Post #59
- Username: CBack
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 31, 2014 10:22 am
- Post datetime: 2020-10-05T17:53:45+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Tue Oct 06, 2020 1:50 am at Tue Oct 06, 2020 1:50 am
>
> 
Would it somehow be possible to load skeleton and animation data from GR2 but load meshes from another format, say OBJ?

unfortunately using ninja ripper wouldn't preserve the weights data needed to bind skeleton to the mesh.
i know its a big hassle but your going to have to load all of the meshes separately using my script to preserve skin data, or if you know you way around 3ds max/blender you could easily skin the obj mesh  to skeleton.

sorry i couldn't be of more help

No worries, thanks for the explanation!

In that case, a different question - is it possible to load several GR2 meshes in one scene in Noesis using your script?
## Post #60
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-10-05T22:08:47+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Well not with my script as is, but It would be possible to add a feature like that to my script,

I currently have some personnel issues preventing me form working on the script, but i will try to add it in the future
## Post #61
- Username: CBack
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 31, 2014 10:22 am
- Post datetime: 2020-10-06T09:31:43+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Tue Oct 06, 2020 6:08 am at Tue Oct 06, 2020 6:08 am
>
> 
Well not with my script as is, but It would be possible to add a feature like that to my script,

I currently have some personnel issues preventing me form working on the script, but i will try to add it in the future

Sure, no problem. Take as much time as you need. Personal life absolutely does come first.
## Post #62
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-10-06T10:55:25+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from CBack ↑Tue Oct 06, 2020 5:31 pm at Tue Oct 06, 2020 5:31 pm
>
> 
jayn23 wrote: ↑Tue Oct 06, 2020 6:08 am
Well not with my script as is, but It would be possible to add a feature like that to my script,

I currently have some personnel issues preventing me form working on the script, but i will try to add it in the future


Sure, no problem. Take as much time as you need. Personal life absolutely does come first.

Depending on how the script is made you may want to try this : [https://github.com/RoadTrain/noesis-plu ... elmerge.py](https://github.com/RoadTrain/noesis-plugins-official/blob/master/Rich/tool_modelmerge.py)

Put it in the plugins folder
Then right click on the file and choose merge
It'll load all the files with the same extension that are next to it
Check the bone merging options in the script to avoid having duplicates if relevant
## Post #63
- Username: CBack
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 31, 2014 10:22 am
- Post datetime: 2020-10-06T21:52:14+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Joschka ↑Tue Oct 06, 2020 6:55 pm at Tue Oct 06, 2020 6:55 pm
>
> 
Depending on how the script is made you may want to try this : https://github.com/RoadTrain/noesis-plu ... elmerge.py

Put it in the plugins folder
Then right click on the file and choose merge
It'll load all the files with the same extension that are next to it
Check the bone merging options in the script to avoid having duplicates if relevant

Yes, it works! It doesn't let me load animation though as for some reason it's now required to be loaded in the .sis format but it does seem to work for merging meshes with skeletons, which is what I really need.
## Post #64
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-08T11:24:06+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Any news directly on Baldurs Gate 3?
## Post #65
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-10-08T12:19:58+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Any news directly on Baldurs Gate 3?

Well I did take a quick look at the archive .pak files they are compressed and i am not sure what type of compression was used, i know how to identify and work mostly with .zlib compression.

If anyone here is willing/able to take a look i can upload a sample.
## Post #66
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2020-10-10T21:52:34+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Where do i need to put the granny2.dll file? it gives me long error logs. I was trying to open snocross models in noesis
## Post #67
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-10-11T13:35:06+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> here do i need to put the granny2.dll file? it gives me long error logs. I was trying to open snocross models in noesis
needs to be in same folder as noesis.exe file


I checked BG3.exe file and it does indeed contain references to granny .gr2 files so I am confident the game uses granny format - just need help extracting the data since I have very little experience with compressed archives

i will try later today to upload a sample in a dedicated thread for BG3
## Post #68
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-11T14:04:02+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Try also on zenhax. They work well with archives.
## Post #69
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-10-11T14:23:54+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Try also on zenhax. They work well with archives.

seems like Ekey already cracked this one 
[https://zenhax.com/viewtopic.php?f=9&t=14229](https://zenhax.com/viewtopic.php?f=9&t=14229)

IT WORKS I CHECKED
## Post #70
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-11T14:56:12+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Nice news!
## Post #71
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-11T20:38:04+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I try load model, get error:
Detected file type: GR2 Reader
Traceback (most recent call last):
  File "D:\noesisv4433\plugins\python\fmt_GR2reader121.py", line 3261, in noepyLoadModel
    Models = GR2Reader(data)  
  File "D:\noesisv4433\plugins\python\fmt_GR2reader121.py", line 2705, in GR2Reader
    AllDecompressedData += GR2decompress(DecompressedData,ComperesedData,section.decompressed_size,section.data_size,section)
  File "D:\noesisv4433\plugins\python\fmt_GR2reader121.py", line 2584, in GR2decompress
    beginDecompressProc = lib['_GrannyBeginFileDecompression@24']
  File "D:\noesisv4433\Plugins\python\core321.zip\ctypes\__init__.py", line 358, in __getitem__
AttributeError: function '_GrannyBeginFileDecompression@24' not found

Do I use uncorrect version of granny2.dll or what?

Can you say the size and version of the file your use?
Thanks.
## Post #72
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-10-12T05:50:05+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> I try load model, get error:
>
> Detected file type: GR2 Reader
>
> Traceback (most recent call last):
>
> File "D:\noesisv4433\plugins\python\fmt_GR2reader121.py", line 3261, in noepyLoadModel
>
> Models = GR2Reader(data)
>
> File "D:\noesisv4433\plugins\python\fmt_GR2reader121.py", line 2705, in GR2Reader
>
> AllDecompressedData += GR2decompress(DecompressedData,ComperesedData,section.decompressed_size,section.data_size,section)
>
> File "D:\noesisv4433\plugins\python\fmt_GR2reader121.py", line 2584, in GR2decompress
>
> beginDecompressProc = lib['_GrannyBeginFileDecompression@24']
>
> File "D:\noesisv4433\Plugins\python\core321.zip\ctypes\__init__.py", line 358, in __getitem__
>
> AttributeError: function '_GrannyBeginFileDecompression@24' not found
>
> 
>
> Do I use uncorrect version of granny2.dll or what?

They are using BitKnit2 Compression, most granny2.dll dont support this - you need to find a .dll that supports it
## Post #73
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-12T06:03:16+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Yes I understand this.
Obviously, you have this file.
Can you provide the following information so that I understand what to look for.

In general, the script works fine with BG3 models, or does it need to be improved?
[granny2.png](https://xentaxbackup.github.io/file/18810_granny2.png)
## Post #74
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-10-12T06:16:48+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

So far everything i have tested works, except the red dragon which gives a python error and crashes.
I dont have time to debug issues for at least a week but then I will take a look why the dragon is crashing.
Also many creatures seem to be missing there .gr2 files - maybe they are being extracted to a different location - dont know

here's the BG3 Owlbear


which model are you getting your error with? my granny version is 2.11.8


> Can you provide the following information so that I understand what to look for.
Open you .dll file in hex editor and search for "_GrannyBeginFileDecompression" if it contain this string it should work - if it does not than you need a different version
## Post #75
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-12T07:50:21+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Many thanks! I already found.
I was getting errors on all models as I used v. 2.9.12.0 (easy to find on the net)
Judging by the information from here [http://www.radgametools.com/granny/history.html](http://www.radgametools.com/granny/history.html)
BitKnit 2 is added in version  2.11.0.0 release 2015/11/03

I found the required dll version here (already compiled, exactly 2.11.8.0,   size 672 256 bytes)
[https://github.com/nikita322/GrannyConverter2.11.8](https://github.com/nikita322/GrannyConverter2.11.8)
Everything works with it.

Thanks again, will wait for the dragon's update.
## Post #76
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2020-10-16T15:32:27+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thanks for the script jayn23, most useful. One thing I have noticed though is that meshes appear to be X-flipped (something that LSLib does as well, despite having a setting for it). It's clearly noticeable on non-symmetrical meshes (like certain hairstyles) when comparing them to the originals in-game.
## Post #77
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-10-17T18:46:10+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Thanks for the script jayn23, most useful. One thing I have noticed though is that meshes appear to be X-flipped (something that LSLib does as well, despite having a setting for it). It's clearly noticeable on non-symmetrical meshes (like certain hairstyles) when comparing them to the originals in-game.

The problem is, the format is used by100's of games each with there own engine etc.. so everyone exports there models in what ever way there engine renders the 3d meshes, I have no way of knowing for each game if it is flipped or not, I tried in the past to add a feature where you choose if you want to flip the model, the reason I didn't add this already is because it messes up the animations for some reason...
## Post #78
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-10-23T00:55:23+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

It messes up animations because they work with the models as are.
The Game engine renders things flipped one way or the other.

That's like asking why some models export inverted and Z is messed up but show fine in the Game.
## Post #79
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-10-23T05:37:17+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> It messes up animations because they work with the models as are.
>
> The Game engine renders things flipped one way or the other.
>
> 
>
> That's like asking why some models export inverted and Z is messed up but show fine in the Game.

Thanks, i assumed as much , but i did try to flip mesh, skeleton and animations all separately that's why i hoped if i change them all in the same way it would work, i tried to do this with my total war Warhammer script as well a few months ago animation exploded  

It seems i still have a lot to learn of game engines and renders
## Post #80
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2020-10-30T10:02:02+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Does anyone know how the face textures are done for companions? There doesnt seem to be any Diffuse Textures for them.
## Post #81
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-10-31T20:01:00+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Be more specific on the Game.
## Post #82
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2020-11-03T05:07:04+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Sorry, Baldur's Gate 3
## Post #83
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-11-07T23:14:43+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Fri Aug 14, 2020 1:11 pm at Fri Aug 14, 2020 1:11 pm
>
> 
DAE. This one looked promising.. Everything looked fine in blender except it was upside down. Getting it upwards caused some similar issues with that backflipping to reappear again. Once exported I noticed how for some reason no bone was moving except the very root bip01 one. Weird.

Hi,

my script only handles the import of gr2 data and does nothing for the export that is done by the built in plugins of noesis, but i did do some experimenting. on 3DS MAX since that is my goto 3D modeling software ,
importing with DAE gave me that same backflip you described, i then downloaded the openCollada plugin and used it to import the DAE instead of the built in plugin and it worked perfectly, but wiredly enough after exporing and reimporting an edited version animation was all wrong...

I dunno if it could help but I found that noesis export fbx version 7.7.0 , actually only recent version of 3dstudio max support it, most of older one support 7.4.0. 
3dsm is my goto software too and I was experiencing "empty" .fbx exported from noesis, that was because I was using and old version of 3dsm that didn't recognize that version , with 2017 I can import correctly fbx exported by noesis.
## Post #84
- Username: Predator0000
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-11-08T16:46:08+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I deleted the link thank you  
[AMY PS3 Noesis GR2.jpg](https://xentaxbackup.github.io/file/18995_AMY PS3 Noesis GR2.jpg)
## Post #85
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-08T17:15:26+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> hi i cant open the GR2 model even the PSSG textures ... AMY PS3 game. you are a programmer possible to make a Noesis script for the GR2 model is the PSSG texture also possible for the animations in GR2 Thank you models Amy gr2, textures in pssg and animations in gr2 please I just want help

I didn't look at your sample, but based on my knowledge is because PS3 uses big endian while PC uses little endian.
my script was written to support only little endian.
ill check how much work it is to get console versions to work (i did do some work on this in the past but never really tested it), if its not to much work ill do it this week along with my promised feature for loading multiple meshes.
## Post #86
- Username: Predator0000
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-11-08T17:32:35+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Mon Nov 09, 2020 6:49 am at Mon Nov 09, 2020 6:49 am
>
> 

I didn't look at your sample, but based on my knowledge is because PS3 uses big endian while PC uses little endian.
my script was written to support only little endian.
ill check how much work it is to get console versions to work (i did do some work on this in the past but never really tested it), if its not to much work ill do it this week along with my promised feature for loading multiple meshes.Thank you absolutely It's really kind of you I absolutely hope you can do it I would like to read all the models of this game with the animations,

and all textures

in Noesis 

Thank you
## Post #87
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-11-08T17:51:02+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Drawing ↑Sun Nov 08, 2020 7:14 am at Sun Nov 08, 2020 7:14 am
>
> 

I dunno if it could help but I found that noesis export fbx version 7.7.0 , actually only recent version of 3dstudio max support it, most of older one support 7.4.0. 
3dsm is my goto software too and I was experiencing "empty" .fbx exported from noesis, that was because I was using and old version of 3dsm that didn't recognize that version , with 2017 I can import correctly fbx exported by noesis.

Just to explain better:

When I used to export from noesis in .DAE i was experiencing the same backflip problem jayn23 stated. 
I used the FBX export option but the file generated were not recognized by 3dsm. Later I found that the files were not load in 3dsm simply because was a 7.7.0 and my old 3dsm didn't recognize it. With 3dsm 2017 the 7.7.0 FBX were opened and no backflip during animation 
This works for every model you want to export and not just for those related with this plugin.

sorry for repetition but I saw my message wasn't clear.
## Post #88
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-08T22:49:30+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Thank you absolutely It's really kind of you I absolutely hope you can do it I would like to read all the models of this game with the animations,
>
> 
>
> and all textures
>
> 
>
> in Noesis
>
> 
>
> Thank you

I remembered why i didn't do it in the first place, i couldn't get the decompression function to work correctly, it giving me an error as if my input is incorrect.

05SpeedMaster, do you by any chance know if console version uses a different granny.dll version or any other reason why it wont work.
i have tried changing everything to big endian, everything seems to be reading correctly (version, compression, CRC all the offsets etc..) but decompress function isn't working
## Post #89
- Username: Predator0000
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-11-09T17:06:04+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Mon Nov 09, 2020 6:49 am at Mon Nov 09, 2020 6:49 am
>
> 

I remembered why i didn't do it in the first place, i couldn't get the decompression function to work correctly, it giving me an error as if my input is incorrect.I wanted to thank you for your help, I really appreciate thank you I can't wait to test your script in Noesis Thank you
## Post #90
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-11-10T21:54:04+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Mon Nov 09, 2020 6:49 am at Mon Nov 09, 2020 6:49 am
>
> 


05SpeedMaster, do you by any chance know if console version uses a different granny.dll version or any other reason why it wont work.
i have tried changing everything to big endian, everything seems to be reading correctly (version, compression, CRC all the offsets etc..) but decompress function isn't working
Kind of looking at the AMY file linked.
Haven't tried it with your Noesis stuff but it appears like a normal GR2 and opens fine in several versions of grannyviewer I have.
 I even ran a CRC check on the files and they are correct. 
(Some GR2 files report a bad CRC and will not open even in Grannyviewer! I broke that problem a long time ago!)
1st thought is that maybe some stuff is stored in different sections from the most common sections used.
I'll look closer in the next several days as I have some free time.
## Post #91
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-10T22:17:54+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Kind of looking at the AMY file linked.
>
> Haven't tried it with your Noesis stuff but it appears like a normal GR2 and opens fine in several versions of grannyviewer I have.
>
> I even ran a CRC check on the files and they are correct.
>
> (Some GR2 files report a bad CRC and will not open even in Grannyviewer! I broke that problem a long time ago!)
>
> 1st thought is that maybe some stuff is stored in different sections from the most common sections used.
>
> I'll look closer in the next several days as I have some free time.

Its defiantly not a CRC error, you can see that in granny viewer and i am getting the same values as granny viewer.
I am getting the same error i got when i started using ctypes in python and i was sending the wrong parameters to the GrannyDecompressData@32 function (i was sending a bytesarray of the wrong size)

if my script were in C++ it would have been easier
## Post #92
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-11-10T22:30:41+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Line 3267 is the error I get.
## Post #93
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-11-10T23:32:16+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I cant seem to load the smurfs sample, since is PS3 i wonder maybe due to endianness?
Can you please take a look if you have some time.


 sample.zip
(195.19 KiB) Downloaded 18 times



```
Format not supported
Traceback (most recent call last):
  File "C:\noesis\plugins\python\fmt_GR2reader121.py", line 3267, in noepyLoadModel
    for model in Models:
TypeError: 'int' object is not iterable
```
## Post #94
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-11T08:45:44+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Line 3267 is the error I get.

> CODE: SELECT ALL
>
> 
>
> Detected file type: GR2 Reader
>
> Format not supported
>
> Traceback (most recent call last):
>
>   File "C:\noesis\plugins\python\fmt_GR2reader121.py", line 3267, in noepyLoadModel
>
>     for model in Models:
>
> TypeError: 'int' object is not iterable

If you notice right under "Detected file type:..." it says Format not supported, when that happens it returns a 0 for the entire function and for model in Models becomes for 0 in models, ill fix it so that dosent happen again.

I will upload a debug version  later today where everything is changed to big endian and all parameters are printed out, hopefully that will help pin point the issue.

> I cant seem to load the smurfs sample, since is PS3 i wonder maybe due to endianness?
>
> Can you please take a look if you have some time.

Its the exact same issue i am having with sample by Predator0000, first issue is that magic wasn't recognized by the script so it didnt know its a big endian format, but fixing it manually and adjusting my script to big endian didnt help because for some reason it crashes when it reaches the decompress function i am using from granny2.dll
## Post #95
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-11T09:36:18+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Here is the debug version,
This currently does not work so no point in downloading unless you can help solve the issue, but any help is welcome    

What i did :
Ignore missing magic number (for now its always set to big endian)
change from little endian to big endian.
Enabled Debug console for noesis
Printed out all variables until decompression function where it crashes.
Added in line 2732 a return  command so all printed data can be viewed, if it reaches function on line 2733 noesis crashes in it wont continue.
## Post #96
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-11-12T01:09:48+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Wed Nov 11, 2020 5:36 pm at Wed Nov 11, 2020 5:36 pm
>
> ...unless you can help solve the issue, but any help is welcome   ...
I am no reverser and all i can do is provide the output on many samples i tried, a lot of reversers here can help of course if they want to or if you contact them i guess? Someone like chrrox, Joschka or even Noesis developer himself can provide better assistance i think.

```
header size 456
header.format 0
version 7
file_size 216772
crc32 4182555030
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 200824
decompressed_size 490904
alignment 4
first16bit 92760
first8bit 92760
relocations_offset 201684
relocations_count 721
marshallings_offset 210336
marshallings_count 4


Starting new section
compression 2
data_offset 201280
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 210400
relocations_count 0
marshallings_offset 210400
marshallings_count 0


Starting new section
compression 2
data_offset 201280
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 210400
relocations_count 0
marshallings_offset 210400
marshallings_count 0


Starting new section
compression 2
data_offset 201280
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 210400
relocations_count 0
marshallings_offset 210400
marshallings_count 0


Starting new section
compression 2
data_offset 201280
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 210400
relocations_count 0
marshallings_offset 210400
marshallings_count 0


Starting new section
compression 0
data_offset 201280
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 210400
relocations_count 0
marshallings_offset 210400
marshallings_count 0


Starting new section
compression 2
data_offset 201280
data_size 404
decompressed_size 16576
alignment 4
first16bit 16576
first8bit 16576
relocations_offset 210400
relocations_count 531
marshallings_offset 216772
marshallings_count 0


Starting new section
compression 2
data_offset 201684
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 216772
relocations_count 0
marshallings_offset 216772
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 1208996
crc32 2354326072
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 1184516
decompressed_size 3014440
alignment 4
first16bit 503920
first8bit 503920
relocations_offset 1185376
relocations_count 1437
marshallings_offset 1202620
marshallings_count 4


Starting new section
compression 2
data_offset 1184972
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 1202684
relocations_count 0
marshallings_offset 1202684
marshallings_count 0


Starting new section
compression 2
data_offset 1184972
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1202684
relocations_count 0
marshallings_offset 1202684
marshallings_count 0


Starting new section
compression 2
data_offset 1184972
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 1202684
relocations_count 0
marshallings_offset 1202684
marshallings_count 0


Starting new section
compression 2
data_offset 1184972
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1202684
relocations_count 0
marshallings_offset 1202684
marshallings_count 0


Starting new section
compression 0
data_offset 1184972
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1202684
relocations_count 0
marshallings_offset 1202684
marshallings_count 0


Starting new section
compression 2
data_offset 1184972
data_size 404
decompressed_size 16448
alignment 4
first16bit 16448
first8bit 16448
relocations_offset 1202684
relocations_count 526
marshallings_offset 1208996
marshallings_count 0


Starting new section
compression 2
data_offset 1185376
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1208996
relocations_count 0
marshallings_offset 1208996
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 6106464
crc32 2352594078
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 1325480
decompressed_size 2305700
alignment 4
first16bit 54112
first8bit 54112
relocations_offset 6075524
relocations_count 2049
marshallings_offset 6100112
marshallings_count 4


Starting new section
compression 2
data_offset 1325936
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 6100176
relocations_count 0
marshallings_offset 6100176
marshallings_count 0


Starting new section
compression 2
data_offset 1325936
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 6100176
relocations_count 0
marshallings_offset 6100176
marshallings_count 0


Starting new section
compression 2
data_offset 1325936
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 6100176
relocations_count 0
marshallings_offset 6100176
marshallings_count 0


Starting new section
compression 2
data_offset 1325936
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 6100176
relocations_count 0
marshallings_offset 6100176
marshallings_count 0


Starting new section
compression 0
data_offset 1325936
data_size 4749192
decompressed_size 4749192
alignment 4
first16bit 0
first8bit 0
relocations_offset 6100176
relocations_count 0
marshallings_offset 6100176
marshallings_count 0


Starting new section
compression 2
data_offset 6075128
data_size 396
decompressed_size 16352
alignment 4
first16bit 16352
first8bit 16352
relocations_offset 6100176
relocations_count 524
marshallings_offset 6106464
marshallings_count 0


Starting new section
compression 2
data_offset 6075524
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 6106464
relocations_count 0
marshallings_offset 6106464
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 199352
crc32 2977333219
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 12248
decompressed_size 39916
alignment 4
first16bit 13916
first8bit 13916
relocations_offset 187912
relocations_count 475
marshallings_offset 193612
marshallings_count 7


Starting new section
compression 2
data_offset 12704
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 193724
relocations_count 0
marshallings_offset 193724
marshallings_count 0


Starting new section
compression 2
data_offset 12704
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 193724
relocations_count 0
marshallings_offset 193724
marshallings_count 0


Starting new section
compression 2
data_offset 12704
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 193724
relocations_count 0
marshallings_offset 193724
marshallings_count 0


Starting new section
compression 2
data_offset 12704
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 193724
relocations_count 0
marshallings_offset 193724
marshallings_count 0


Starting new section
compression 0
data_offset 12704
data_size 174816
decompressed_size 174816
alignment 4
first16bit 0
first8bit 0
relocations_offset 193724
relocations_count 0
marshallings_offset 193724
marshallings_count 0


Starting new section
compression 2
data_offset 187520
data_size 392
decompressed_size 14496
alignment 4
first16bit 14496
first8bit 14496
relocations_offset 193724
relocations_count 469
marshallings_offset 199352
marshallings_count 0


Starting new section
compression 2
data_offset 187912
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 199352
relocations_count 0
marshallings_offset 199352
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 2776564
crc32 3391606108
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 873808
decompressed_size 2414928
alignment 4
first16bit 384540
first8bit 754192
relocations_offset 2272928
relocations_count 33273
marshallings_offset 2672204
marshallings_count 5966


Starting new section
compression 2
data_offset 874264
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 2767660
relocations_count 0
marshallings_offset 2767660
marshallings_count 0


Starting new section
compression 2
data_offset 874264
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 2767660
relocations_count 0
marshallings_offset 2767660
marshallings_count 0


Starting new section
compression 2
data_offset 874264
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 2767660
relocations_count 0
marshallings_offset 2767660
marshallings_count 0


Starting new section
compression 2
data_offset 874264
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 2767660
relocations_count 0
marshallings_offset 2767660
marshallings_count 0


Starting new section
compression 0
data_offset 874264
data_size 1398128
decompressed_size 1398128
alignment 4
first16bit 0
first8bit 0
relocations_offset 2767660
relocations_count 0
marshallings_offset 2767660
marshallings_count 0


Starting new section
compression 2
data_offset 2272392
data_size 536
decompressed_size 23424
alignment 4
first16bit 23424
first8bit 23424
relocations_offset 2767660
relocations_count 742
marshallings_offset 2776564
marshallings_count 0


Starting new section
compression 2
data_offset 2272928
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 2776564
relocations_count 0
marshallings_offset 2776564
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 1976756
crc32 1386804283
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 523280
decompressed_size 1116632
alignment 4
first16bit 114168
first8bit 178532
relocations_offset 1922308
relocations_count 3413
marshallings_offset 1963264
marshallings_count 409


Starting new section
compression 2
data_offset 523736
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 1969808
relocations_count 0
marshallings_offset 1969808
marshallings_count 0


Starting new section
compression 2
data_offset 523736
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1969808
relocations_count 0
marshallings_offset 1969808
marshallings_count 0


Starting new section
compression 2
data_offset 523736
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 1969808
relocations_count 0
marshallings_offset 1969808
marshallings_count 0


Starting new section
compression 2
data_offset 523736
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1969808
relocations_count 0
marshallings_offset 1969808
marshallings_count 0


Starting new section
compression 0
data_offset 523736
data_size 1398128
decompressed_size 1398128
alignment 4
first16bit 0
first8bit 0
relocations_offset 1969808
relocations_count 0
marshallings_offset 1969808
marshallings_count 0


Starting new section
compression 2
data_offset 1921864
data_size 444
decompressed_size 17920
alignment 4
first16bit 17920
first8bit 17920
relocations_offset 1969808
relocations_count 579
marshallings_offset 1976756
marshallings_count 0


Starting new section
compression 2
data_offset 1922308
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1976756
relocations_count 0
marshallings_offset 1976756
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 1447468
crc32 1082396615
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 139664
decompressed_size 497160
alignment 4
first16bit 188308
first8bit 227104
relocations_offset 1189280
relocations_count 16499
marshallings_offset 1387268
marshallings_count 3245


Starting new section
compression 2
data_offset 140120
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 1439188
relocations_count 0
marshallings_offset 1439188
marshallings_count 0


Starting new section
compression 2
data_offset 140120
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1439188
relocations_count 0
marshallings_offset 1439188
marshallings_count 0


Starting new section
compression 2
data_offset 140120
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 1439188
relocations_count 0
marshallings_offset 1439188
marshallings_count 0


Starting new section
compression 2
data_offset 140120
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1439188
relocations_count 0
marshallings_offset 1439188
marshallings_count 0


Starting new section
compression 0
data_offset 140120
data_size 1048656
decompressed_size 1048656
alignment 4
first16bit 0
first8bit 0
relocations_offset 1439188
relocations_count 0
marshallings_offset 1439188
marshallings_count 0


Starting new section
compression 2
data_offset 1188776
data_size 504
decompressed_size 21504
alignment 4
first16bit 21504
first8bit 21504
relocations_offset 1439188
relocations_count 690
marshallings_offset 1447468
marshallings_count 0


Starting new section
compression 2
data_offset 1189280
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1447468
relocations_count 0
marshallings_offset 1447468
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 1587496
crc32 3695687553
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 119696
decompressed_size 275300
alignment 4
first16bit 86464
first8bit 119800
relocations_offset 1518816
relocations_count 4471
marshallings_offset 1572468
marshallings_count 517


Starting new section
compression 2
data_offset 120152
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 1580740
relocations_count 0
marshallings_offset 1580740
marshallings_count 0


Starting new section
compression 2
data_offset 120152
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1580740
relocations_count 0
marshallings_offset 1580740
marshallings_count 0


Starting new section
compression 2
data_offset 120152
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 1580740
relocations_count 0
marshallings_offset 1580740
marshallings_count 0


Starting new section
compression 2
data_offset 120152
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1580740
relocations_count 0
marshallings_offset 1580740
marshallings_count 0


Starting new section
compression 0
data_offset 120152
data_size 1398208
decompressed_size 1398208
alignment 4
first16bit 0
first8bit 0
relocations_offset 1580740
relocations_count 0
marshallings_offset 1580740
marshallings_count 0


Starting new section
compression 2
data_offset 1518360
data_size 456
decompressed_size 17472
alignment 4
first16bit 17472
first8bit 17472
relocations_offset 1580740
relocations_count 563
marshallings_offset 1587496
marshallings_count 0


Starting new section
compression 2
data_offset 1518816
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1587496
relocations_count 0
marshallings_offset 1587496
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 546632
crc32 1032698123
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 119924
decompressed_size 253540
alignment 4
first16bit 78216
first8bit 78216
relocations_offset 514116
relocations_count 2123
marshallings_offset 539592
marshallings_count 68


Starting new section
compression 2
data_offset 120380
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 540680
relocations_count 0
marshallings_offset 540680
marshallings_count 0


Starting new section
compression 2
data_offset 120380
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 540680
relocations_count 0
marshallings_offset 540680
marshallings_count 0


Starting new section
compression 2
data_offset 120380
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 540680
relocations_count 0
marshallings_offset 540680
marshallings_count 0


Starting new section
compression 2
data_offset 120380
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 540680
relocations_count 0
marshallings_offset 540680
marshallings_count 0


Starting new section
compression 0
data_offset 120380
data_size 393336
decompressed_size 393336
alignment 4
first16bit 0
first8bit 0
relocations_offset 540680
relocations_count 0
marshallings_offset 540680
marshallings_count 0


Starting new section
compression 2
data_offset 513716
data_size 400
decompressed_size 15424
alignment 4
first16bit 15424
first8bit 15424
relocations_offset 540680
relocations_count 496
marshallings_offset 546632
marshallings_count 0


Starting new section
compression 2
data_offset 514116
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 546632
relocations_count 0
marshallings_offset 546632
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 8312052
crc32 4744665
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 7523196
decompressed_size 13648148
alignment 4
first16bit 45020
first8bit 45020
relocations_offset 8273592
relocations_count 3004
marshallings_offset 8309640
marshallings_count 0


Starting new section
compression 2
data_offset 7523652
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 8309640
relocations_count 0
marshallings_offset 8309640
marshallings_count 0


Starting new section
compression 2
data_offset 7523652
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 8309640
relocations_count 0
marshallings_offset 8309640
marshallings_count 0


Starting new section
compression 2
data_offset 7523652
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 8309640
relocations_count 0
marshallings_offset 8309640
marshallings_count 0


Starting new section
compression 2
data_offset 7523652
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 8309640
relocations_count 0
marshallings_offset 8309640
marshallings_count 0


Starting new section
compression 0
data_offset 7523652
data_size 749712
decompressed_size 749712
alignment 4
first16bit 0
first8bit 0
relocations_offset 8309640
relocations_count 0
marshallings_offset 8309640
marshallings_count 0


Starting new section
compression 2
data_offset 8273364
data_size 228
decompressed_size 5824
alignment 4
first16bit 5824
first8bit 5824
relocations_offset 8309640
relocations_count 201
marshallings_offset 8312052
marshallings_count 0


Starting new section
compression 2
data_offset 8273592
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 8312052
relocations_count 0
marshallings_offset 8312052
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 412464
crc32 2590575078
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 388932
decompressed_size 987544
alignment 4
first16bit 207320
first8bit 207320
relocations_offset 389792
relocations_count 1353
marshallings_offset 406028
marshallings_count 4


Starting new section
compression 2
data_offset 389388
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 406092
relocations_count 0
marshallings_offset 406092
marshallings_count 0


Starting new section
compression 2
data_offset 389388
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 406092
relocations_count 0
marshallings_offset 406092
marshallings_count 0


Starting new section
compression 2
data_offset 389388
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 406092
relocations_count 0
marshallings_offset 406092
marshallings_count 0


Starting new section
compression 2
data_offset 389388
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 406092
relocations_count 0
marshallings_offset 406092
marshallings_count 0


Starting new section
compression 0
data_offset 389388
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 406092
relocations_count 0
marshallings_offset 406092
marshallings_count 0


Starting new section
compression 2
data_offset 389388
data_size 404
decompressed_size 16576
alignment 4
first16bit 16576
first8bit 16576
relocations_offset 406092
relocations_count 531
marshallings_offset 412464
marshallings_count 0


Starting new section
compression 2
data_offset 389792
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 412464
relocations_count 0
marshallings_offset 412464
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 1033760
crc32 4148269757
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 291220
decompressed_size 864980
alignment 4
first16bit 174368
first8bit 579676
relocations_offset 816472
relocations_count 13954
marshallings_offset 983920
marshallings_count 2689


Starting new section
compression 2
data_offset 291676
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 1026944
relocations_count 0
marshallings_offset 1026944
marshallings_count 0


Starting new section
compression 2
data_offset 291676
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1026944
relocations_count 0
marshallings_offset 1026944
marshallings_count 0


Starting new section
compression 2
data_offset 291676
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 1026944
relocations_count 0
marshallings_offset 1026944
marshallings_count 0


Starting new section
compression 2
data_offset 291676
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1026944
relocations_count 0
marshallings_offset 1026944
marshallings_count 0


Starting new section
compression 0
data_offset 291676
data_size 524328
decompressed_size 524328
alignment 4
first16bit 0
first8bit 0
relocations_offset 1026944
relocations_count 0
marshallings_offset 1026944
marshallings_count 0


Starting new section
compression 2
data_offset 816004
data_size 468
decompressed_size 17632
alignment 4
first16bit 17632
first8bit 17632
relocations_offset 1026944
relocations_count 568
marshallings_offset 1033760
marshallings_count 0


Starting new section
compression 2
data_offset 816472
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1033760
relocations_count 0
marshallings_offset 1033760
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 978008
crc32 1158797737
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 268156
decompressed_size 794044
alignment 4
first16bit 166008
first8bit 470420
relocations_offset 793420
relocations_count 11779
marshallings_offset 934768
marshallings_count 2269


Starting new section
compression 2
data_offset 268612
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 971072
relocations_count 0
marshallings_offset 971072
marshallings_count 0


Starting new section
compression 2
data_offset 268612
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 971072
relocations_count 0
marshallings_offset 971072
marshallings_count 0


Starting new section
compression 2
data_offset 268612
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 971072
relocations_count 0
marshallings_offset 971072
marshallings_count 0


Starting new section
compression 2
data_offset 268612
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 971072
relocations_count 0
marshallings_offset 971072
marshallings_count 0


Starting new section
compression 0
data_offset 268612
data_size 524328
decompressed_size 524328
alignment 4
first16bit 0
first8bit 0
relocations_offset 971072
relocations_count 0
marshallings_offset 971072
marshallings_count 0


Starting new section
compression 2
data_offset 792940
data_size 480
decompressed_size 17984
alignment 4
first16bit 17984
first8bit 17984
relocations_offset 971072
relocations_count 578
marshallings_offset 978008
marshallings_count 0


Starting new section
compression 2
data_offset 793420
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 978008
relocations_count 0
marshallings_offset 978008
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 1220900
crc32 2670510535
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 331604
decompressed_size 806452
alignment 4
first16bit 242504
first8bit 460756
relocations_offset 856864
relocations_count 23709
marshallings_offset 1141372
marshallings_count 4543


Starting new section
compression 2
data_offset 332060
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 1214060
relocations_count 0
marshallings_offset 1214060
marshallings_count 0


Starting new section
compression 2
data_offset 332060
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1214060
relocations_count 0
marshallings_offset 1214060
marshallings_count 0


Starting new section
compression 2
data_offset 332060
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 1214060
relocations_count 0
marshallings_offset 1214060
marshallings_count 0


Starting new section
compression 2
data_offset 332060
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1214060
relocations_count 0
marshallings_offset 1214060
marshallings_count 0


Starting new section
compression 0
data_offset 332060
data_size 524328
decompressed_size 524328
alignment 4
first16bit 0
first8bit 0
relocations_offset 1214060
relocations_count 0
marshallings_offset 1214060
marshallings_count 0


Starting new section
compression 2
data_offset 856388
data_size 476
decompressed_size 17760
alignment 4
first16bit 17760
first8bit 17760
relocations_offset 1214060
relocations_count 570
marshallings_offset 1220900
marshallings_count 0


Starting new section
compression 2
data_offset 856864
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 1220900
relocations_count 0
marshallings_offset 1220900
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 811108
crc32 1070289332
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 246332
decompressed_size 565860
alignment 4
first16bit 171768
first8bit 301304
relocations_offset 596800
relocations_count 13708
marshallings_offset 761296
marshallings_count 2688


Starting new section
compression 2
data_offset 246788
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 804304
relocations_count 0
marshallings_offset 804304
marshallings_count 0


Starting new section
compression 2
data_offset 246788
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 804304
relocations_count 0
marshallings_offset 804304
marshallings_count 0


Starting new section
compression 2
data_offset 246788
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 804304
relocations_count 0
marshallings_offset 804304
marshallings_count 0


Starting new section
compression 2
data_offset 246788
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 804304
relocations_count 0
marshallings_offset 804304
marshallings_count 0


Starting new section
compression 0
data_offset 246788
data_size 349552
decompressed_size 349552
alignment 4
first16bit 0
first8bit 0
relocations_offset 804304
relocations_count 0
marshallings_offset 804304
marshallings_count 0


Starting new section
compression 2
data_offset 596340
data_size 460
decompressed_size 17568
alignment 4
first16bit 17568
first8bit 17568
relocations_offset 804304
relocations_count 567
marshallings_offset 811108
marshallings_count 0


Starting new section
compression 2
data_offset 596800
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 811108
relocations_count 0
marshallings_offset 811108
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 4347236
crc32 3039442099
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 3361624
decompressed_size 5041416
alignment 4
first16bit 9356
first8bit 9356
relocations_offset 4337276
relocations_count 629
marshallings_offset 4344824
marshallings_count 0


Starting new section
compression 2
data_offset 3362080
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 4344824
relocations_count 0
marshallings_offset 4344824
marshallings_count 0


Starting new section
compression 2
data_offset 3362080
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 4344824
relocations_count 0
marshallings_offset 4344824
marshallings_count 0


Starting new section
compression 2
data_offset 3362080
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 4344824
relocations_count 0
marshallings_offset 4344824
marshallings_count 0


Starting new section
compression 2
data_offset 3362080
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 4344824
relocations_count 0
marshallings_offset 4344824
marshallings_count 0


Starting new section
compression 0
data_offset 3362080
data_size 974968
decompressed_size 974968
alignment 4
first16bit 0
first8bit 0
relocations_offset 4344824
relocations_count 0
marshallings_offset 4344824
marshallings_count 0


Starting new section
compression 2
data_offset 4337048
data_size 228
decompressed_size 5824
alignment 4
first16bit 5824
first8bit 5824
relocations_offset 4344824
relocations_count 201
marshallings_offset 4347236
marshallings_count 0


Starting new section
compression 2
data_offset 4337276
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 4347236
relocations_count 0
marshallings_offset 4347236
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 412464
crc32 2590575078
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 388932
decompressed_size 987544
alignment 4
first16bit 207320
first8bit 207320
relocations_offset 389792
relocations_count 1353
marshallings_offset 406028
marshallings_count 4


Starting new section
compression 2
data_offset 389388
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 406092
relocations_count 0
marshallings_offset 406092
marshallings_count 0


Starting new section
compression 2
data_offset 389388
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 406092
relocations_count 0
marshallings_offset 406092
marshallings_count 0


Starting new section
compression 2
data_offset 389388
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 406092
relocations_count 0
marshallings_offset 406092
marshallings_count 0


Starting new section
compression 2
data_offset 389388
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 406092
relocations_count 0
marshallings_offset 406092
marshallings_count 0


Starting new section
compression 0
data_offset 389388
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 406092
relocations_count 0
marshallings_offset 406092
marshallings_count 0


Starting new section
compression 2
data_offset 389388
data_size 404
decompressed_size 16576
alignment 4
first16bit 16576
first8bit 16576
relocations_offset 406092
relocations_count 531
marshallings_offset 412464
marshallings_count 0


Starting new section
compression 2
data_offset 389792
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 412464
relocations_count 0
marshallings_offset 412464
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 4409668
crc32 1030689437
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 3617172
decompressed_size 6388380
alignment 4
first16bit 36068
first8bit 36068
relocations_offset 4378504
relocations_count 2396
marshallings_offset 4407256
marshallings_count 0


Starting new section
compression 2
data_offset 3617628
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 4407256
relocations_count 0
marshallings_offset 4407256
marshallings_count 0


Starting new section
compression 2
data_offset 3617628
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 4407256
relocations_count 0
marshallings_offset 4407256
marshallings_count 0


Starting new section
compression 2
data_offset 3617628
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 4407256
relocations_count 0
marshallings_offset 4407256
marshallings_count 0


Starting new section
compression 2
data_offset 3617628
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 4407256
relocations_count 0
marshallings_offset 4407256
marshallings_count 0


Starting new section
compression 0
data_offset 3617628
data_size 760648
decompressed_size 760648
alignment 4
first16bit 0
first8bit 0
relocations_offset 4407256
relocations_count 0
marshallings_offset 4407256
marshallings_count 0


Starting new section
compression 2
data_offset 4378276
data_size 228
decompressed_size 5824
alignment 4
first16bit 5824
first8bit 5824
relocations_offset 4407256
relocations_count 201
marshallings_offset 4409668
marshallings_count 0


Starting new section
compression 2
data_offset 4378504
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 4409668
relocations_count 0
marshallings_offset 4409668
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 4980408
crc32 3801495534
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 3081652
decompressed_size 6472816
alignment 4
first16bit 33800
first8bit 33800
relocations_offset 4951008
relocations_count 2249
marshallings_offset 4977996
marshallings_count 0


Starting new section
compression 2
data_offset 3082108
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 4977996
relocations_count 0
marshallings_offset 4977996
marshallings_count 0


Starting new section
compression 2
data_offset 3082108
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 4977996
relocations_count 0
marshallings_offset 4977996
marshallings_count 0


Starting new section
compression 2
data_offset 3082108
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 4977996
relocations_count 0
marshallings_offset 4977996
marshallings_count 0


Starting new section
compression 2
data_offset 3082108
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 4977996
relocations_count 0
marshallings_offset 4977996
marshallings_count 0


Starting new section
compression 0
data_offset 3082108
data_size 1868672
decompressed_size 1868672
alignment 4
first16bit 0
first8bit 0
relocations_offset 4977996
relocations_count 0
marshallings_offset 4977996
marshallings_count 0


Starting new section
compression 2
data_offset 4950780
data_size 228
decompressed_size 5824
alignment 4
first16bit 5824
first8bit 5824
relocations_offset 4977996
relocations_count 201
marshallings_offset 4980408
marshallings_count 0


Starting new section
compression 2
data_offset 4951008
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 4980408
relocations_count 0
marshallings_offset 4980408
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 35756
crc32 4264538520
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 23912
decompressed_size 71940
alignment 4
first16bit 16624
first8bit 16624
relocations_offset 24772
relocations_count 379
marshallings_offset 29320
marshallings_count 4


Starting new section
compression 2
data_offset 24368
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 29384
relocations_count 0
marshallings_offset 29384
marshallings_count 0


Starting new section
compression 2
data_offset 24368
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 29384
relocations_count 0
marshallings_offset 29384
marshallings_count 0


Starting new section
compression 2
data_offset 24368
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 29384
relocations_count 0
marshallings_offset 29384
marshallings_count 0


Starting new section
compression 2
data_offset 24368
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 29384
relocations_count 0
marshallings_offset 29384
marshallings_count 0


Starting new section
compression 0
data_offset 24368
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 29384
relocations_count 0
marshallings_offset 29384
marshallings_count 0


Starting new section
compression 2
data_offset 24368
data_size 404
decompressed_size 16576
alignment 4
first16bit 16576
first8bit 16576
relocations_offset 29384
relocations_count 531
marshallings_offset 35756
marshallings_count 0


Starting new section
compression 2
data_offset 24772
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 35756
relocations_count 0
marshallings_offset 35756
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable
Detected file type: GR2 Reader
header size 456
header.format 0
version 7
file_size 6096444
crc32 2655721302
sections_offset 72
sections_count 8
type_section 6
type_offset 0
root_section 0
root_offset 0
Starting new section
compression 2
data_offset 456
data_size 5315004
decompressed_size 8801516
alignment 4
first16bit 35768
first8bit 35768
relocations_offset 6065400
relocations_count 2386
marshallings_offset 6094032
marshallings_count 0


Starting new section
compression 2
data_offset 5315460
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 6094032
relocations_count 0
marshallings_offset 6094032
marshallings_count 0


Starting new section
compression 2
data_offset 5315460
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 6094032
relocations_count 0
marshallings_offset 6094032
marshallings_count 0


Starting new section
compression 2
data_offset 5315460
data_size 0
decompressed_size 0
alignment 32
first16bit 0
first8bit 0
relocations_offset 6094032
relocations_count 0
marshallings_offset 6094032
marshallings_count 0


Starting new section
compression 2
data_offset 5315460
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 6094032
relocations_count 0
marshallings_offset 6094032
marshallings_count 0


Starting new section
compression 0
data_offset 5315460
data_size 749712
decompressed_size 749712
alignment 4
first16bit 0
first8bit 0
relocations_offset 6094032
relocations_count 0
marshallings_offset 6094032
marshallings_count 0


Starting new section
compression 2
data_offset 6065172
data_size 228
decompressed_size 5824
alignment 4
first16bit 5824
first8bit 5824
relocations_offset 6094032
relocations_count 201
marshallings_offset 6096444
marshallings_count 0


Starting new section
compression 2
data_offset 6065400
data_size 0
decompressed_size 0
alignment 4
first16bit 0
first8bit 0
relocations_offset 6096444
relocations_count 0
marshallings_offset 6096444
marshallings_count 0


Traceback (most recent call last):
  File "C:\noesis\plugins\python\Debug_GR2readerBig.py", line 3297, in noepyLoadModel
    for model in Models:
TypeError: 'NoneType' object is not iterable

```

Noesis doesn't crashes at all btw, only output above is shown in debug window, that's it.
## Post #97
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-12T06:05:05+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> I am no reverser and all i can do is provide the output on many samples i tried, a lot of reversers here can help of course if they want to or if you contact them i guess? Someone like chrrox, Joschka or even Noesis developer himself can provide better assistance i think.

Thanks for trying to help I appreciate it.
the reason its not crashing for you is because i added a return command 1 line above where it crashes so we can view the debug output,
If i would let it continue noesis would crash and we wouldn't be able to see any of the debug output.

I am going to try today one of the other .gr2 tools found on the web, if they work it will help figure out my problem.
## Post #98
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-12T14:17:51+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

It just hit me that while i am sending all the correct parameters to the decompress function, it itself is reading all the compressed data in little endian and that's why its crashing, there is no way for me to tell the function to do it otherwise.

If anyone can send a granny2.dll used with a PS3 that would be great, if PS3 embedd granny in .exe file it might be a problem
Only other solution would be if you had a source and could build it while its defined to read big endian.


Edit:
My knowledge in C++ is very limited but i assume you define endianness within the function? globally? or do use some kind of swap function?
## Post #99
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-11-12T14:39:53+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Maybe you could endian swap the compressed data before sending it to the decompressing function.

```
compressedBytes = rapi.swapEndianArray(compressedBytes, 4)
```
## Post #100
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-12T14:47:47+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Maybe you could endian swap the compressed data before sending it to the decompressing function.

Thanks a lot just might work
## Post #101
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-13T08:26:04+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Maybe you could endian swap the compressed data before sending it to the decompressing function.
>
> CODE: SELECT ALL
>
> 
>
> compressedBytes = rapi.swapEndianArray(compressedBytes, 4)

Still crashing unfortunately, 
Joschka, correct me if i am wrong but the 4 means it takes a chunk of 4 bytes each and swaps the order correct?
but if some of the parameters are shorts for example that would mess up the function, its only a guess but its my best one as to why i am still crashing.
## Post #102
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-11-13T09:43:44+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Exactly, that was a dumb idea indeed as that compressed stream probably has short or bitpacked fields that would need to be swapped accordingly.
So unless you swap the whole stream manually (you probably don't want to do that unless the layout is very simple) I think you'll probably need to find a big endian decompressing function as you said.
## Post #103
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-11-13T14:54:29+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hello! I am really loving this plugin so far. Was curious if support for Mechassault 2: Lone Wolf for the Original Xbox will be added? I attached some sample files and even a script that was used on files from Oddworld: Stranger's Wrath. 
The reason I attached the script is because unlike most of the .GR2 files here that also include a mesh, these .GR2 files contain solely animation/skeleton data. In the case of Stranger's Wrath the meshes were found in .geo.meshinfo files and for Mechassault 2, the meshes are in .MGModel files (just mesh data).


[Here are the animation samples from Mechassault 2: Lone Wolf.](https://mega.nz/file/9Z5WhC7I#0lFeK8kaekHIzmj97XNrEZPEuf_RLRIwwu_3MpSWzsE)


 Blender249[Oddworld Stranger's Wrath][PC][SMD][2016-06-04].7z
(53.61 KiB) Downloaded 16 times


If you need any more information regarding this I'd be happy to help!
## Post #104
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-11-13T19:34:59+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Concerning the AMY files:
I see a DiffuseColor0 thrown in the PrimaryVertexData info
Could that be a stumble point?
## Post #105
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-14T17:27:17+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Concerning the AMY files:
>
> I see a DiffuseColor0 thrown in the PrimaryVertexData info
>
> Could that be a stumble point?

It defiantly was the big endian thing, started looking a decompression function and noticed there is a bytes-reversed option there when i swapped the 0 to 1 is worked no more crashing, should have looked at the functions more closely from the start, this is what happens when you dont touch something for a few months i guess   

any way the code still has issues but i am confident i can fix them 

> Hello! I am really loving this plugin so far. Was curious if support for Mechassault 2: Lone Wolf for the Original Xbox will be added? I attached some sample files and even a script that was used on files from Oddworld: Stranger's Wrath.
>
> The reason I attached the script is because unlike most of the .GR2 files here that also include a mesh, these .GR2 files contain solely animation/skeleton data. In the case of Stranger's Wrath the meshes were found in .geo.meshinfo files and for Mechassault 2, the meshes are in .MGModel files (just mesh data).

I am currently working on adding support for console versions once thats done most games should work,  many games use granny only for skeleton/animation data - that's supported by script.
## Post #106
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-14T21:28:07+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Here you go Amy file working   
Ill do some more tests make sure i didn't break anything and upload updated version tomorrow or on Monday
Edit:
Tested Animation and works as well.



> I cant seem to load the smurfs sample, since is PS3 i wonder maybe due to endianness?
>
> Can you please take a look if you have some time.

> Hello! I am really loving this plugin so far. Was curious if support for Mechassault 2: Lone Wolf for the Original Xbox will be added? I attached some sample files and even a script that was used on files from Oddworld: Stranger's Wrath.
>
> The reason I attached the script is because unlike most of the .GR2 files here that also include a mesh, these .GR2 files contain solely animation/skeleton data. In the case of Stranger's Wrath the meshes were found in .geo.meshinfo files and for Mechassault 2, the meshes are in .MGModel files (just mesh data).

mono24, Pepsee,
Your samples are working as well but one picture is enough
## Post #107
- Username: Predator0000
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-11-15T15:11:54+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I absolutely wanted to thank you for the great job you did and the time you were able to put into it Thank you very much and thank you to others on hand for AMY I really can't wait to test it It's a shame the textures are not taken into account with Noesis Do you know which tool I can use for textures
## Post #108
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-15T19:11:33+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> I absolutely wanted to thank you for the great job you did and the time you were able to put into it Thank you very much and thank you to others on hand for AMY I really can't wait to test it It's a shame the textures are not taken into account with Noesis Do you know which tool I can use for textures

Happy to help

Here's the updated script with console version support, if something dosent work please let me know
## Post #109
- Username: Predator0000
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-11-15T21:25:23+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Mon Nov 16, 2020 3:11 am at Mon Nov 16, 2020 3:11 am
>
> 
Happy to help

Here's the updated script with console version support, if something dosent work please let me knowhi thanks i can't open the model and animation it opens a page when i click on AMY.gr2
even for the animations if I close the page it does that

possible to tell me how to do also with the texture
the script works with all Models and animations or not

jayn23 you can also make the textures posible with Noesis please I don't know how I will do for the textures 
[AMY Noesis.jpg](https://xentaxbackup.github.io/file/19032_AMY Noesis.jpg)
## Post #110
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-15T21:53:17+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

This error means the script cant find granny2.dll 
Make sure you place the file in same folder as noesis.exe
I only tested 2-3 animations but it should work for all models and animation

Regarding textures, i dont have plans so support textures for any game except baldur's gate 3 - dont know when ill add it but i have no plans for other games sorry.
maybe you can try the Graphic file formats section and post samples i am sure someone can help
## Post #111
- Username: Predator0000
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-11-15T21:58:20+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

you can give me the file granny2.dll please I will see for the texture
## Post #112
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-15T22:01:45+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

There is a link on page 5 i think by erik945
## Post #113
- Username: Predator0000
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-11-15T22:03:57+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thank you
## Post #114
- Username: Predator0000
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-11-15T22:06:03+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hi possible to share it please I always have the same message when I click on the Model Amy.gr2 in Noesis I have the granny2.dll
[granny2.png](https://xentaxbackup.github.io/file/19035_granny2.png)
## Post #115
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-16T13:47:03+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Script has multiple option at lines 25 - 28.
You need to open script with notepad++ or some other editor and change values.
Change animation mode to 0 and it will work,
While animation is set to 1 when you click amy.gr2 you ill be asked for a second animation file to load if you select a file with no animation I guessing that's what giving you the issues.
## Post #116
- Username: Predator0000
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-11-16T13:56:22+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thank you for your help
## Post #117
- Username: Predator0000
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-11-16T21:25:43+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hi jayn23 can you tell me what is this error and how to fix it
[Noesis.png](https://xentaxbackup.github.io/file/19038_Noesis.png)
## Post #118
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-16T21:47:04+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> No worries, thanks for the explanation!
>
> 
>
> In that case, a different question - is it possible to load several GR2 meshes in one scene in Noesis using your script?

I have started working on this feature and was hoping someone can provide some samples of multiple gr2 meshes the comprise a single model and possibly a skeleton.

i have a basic setup working but need some samples to fine tune it.

Thanks


> Hi jayn23 can you tell me what is this error and how to fix it
it means the file you are trying to load has to many meshes for noesis to handle - this a noesis issue.
set MERGE_SCENE = 1 in option it fix it for you
## Post #119
- Username: Predator0000
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-11-16T22:14:05+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Mon Nov 16, 2020 3:11 am at Mon Nov 16, 2020 3:11 am
>
> 
it means the file you are trying to load has to many meshes for noesis to handle - this a noesis issue.
set MERGE_SCENE = 1 in option it fix it for youthank you I define it or in the options of Noesis
## Post #120
- Username: Predator0000
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-11-17T16:10:32+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Mon Nov 16, 2020 3:11 am at Mon Nov 16, 2020 3:11 am
>
> 
it means the file you are trying to load has to many meshes for noesis to handle - this a noesis issue.
set MERGE_SCENE = 1 in option it fix it for youHi jean 23 possible to tell me or in the options of Noesis for this order MERGE_SCENE = 1
[Noesis.png](https://xentaxbackup.github.io/file/19043_Noesis.png)
## Post #121
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-17T18:13:03+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

You can look at the first post of this thread, it contains all the script options available.
MERGE_SCENE = 1 is an option in script you need to change just like you did animation using notepad++
## Post #122
- Username: Predator0000
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-11-18T07:56:47+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

OK, thanks
## Post #123
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-11-22T10:41:29+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Version 1.2.6 Release

New Option added:
MULTIFILE 
set to 0 - Deactivated
set to 1 - Merges all meshes and skeletons of all .gr2 files in selected folder.
set to 2 - Merges all meshes of all .gr2 files in selected folder.
set to 3 - Merges all skeletons of all .gr2 files in selected folder.

This Feature hasn't been tested much, really i only tested on 3 models using all different options so hopefully it works without any issues  
[fmt_GR2reader126.rar](https://xentaxbackup.github.io/file/19060_fmt_GR2reader126.rar)
## Post #124
- Username: Predator0000
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2020-11-23T20:08:19+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Sun Nov 22, 2020 6:41 pm at Sun Nov 22, 2020 6:41 pm
>
> 
Version 1.2.6 Release

New Option added:
MULTIFILE 
set to 0 - Deactivated
set to 1 - Merges all meshes and skeletons of all .gr2 files in selected folder.
set to 2 - Merges all meshes of all .gr2 files in selected folder.
set to 3 - Merges all skeletons of all .gr2 files in selected folder.

This Feature hasn't been tested much, really i only tested on 3 models using all different options so hopefully it works without any issues

thanks
## Post #125
- Username: Mogrem
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 26, 2020 4:26 pm
- Post datetime: 2020-11-26T09:53:28+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thanks for the tool!

Does anyone know what to do with all the tiny .bin files that get extracted alongside models for Baldur's Gate 3? I can't seem to figure them out.
## Post #126
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-12-15T18:48:26+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

What version of 3D Max do you use?
I get crashes with 3D Max 2010 trying to import the FBX and DAE files?
## Post #127
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-12-17T16:01:10+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Drawing ↑Mon Nov 09, 2020 1:51 am at Mon Nov 09, 2020 1:51 am
>
> 
Drawing wrote: ↑Sun Nov 08, 2020 7:14 am

I dunno if it could help but I found that noesis export fbx version 7.7.0 , actually only recent version of 3dstudio max support it, most of older one support 7.4.0. 
3dsm is my goto software too and I was experiencing "empty" .fbx exported from noesis, that was because I was using and old version of 3dsm that didn't recognize that version , with 2017 I can import correctly fbx exported by noesis.


Just to explain better:

When I used to export from noesis in .DAE i was experiencing the same backflip problem jayn23 stated. 
I used the FBX export option but the file generated were not recognized by 3dsm. Later I found that the files were not load in 3dsm simply because was a 7.7.0 and my old 3dsm didn't recognize it. With 3dsm 2017 the 7.7.0 FBX were opened and no backflip during animation 
This works for every model you want to export and not just for those related with this plugin.

sorry for repetition but I saw my message wasn't clear.

looks like darwing got things working with max 2017

i myself use max 2018
## Post #128
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-12-19T13:01:37+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Wed Dec 16, 2020 2:48 am at Wed Dec 16, 2020 2:48 am
>
> 
What version of 3D Max do you use?
I get crashes with 3D Max 2010 trying to import the FBX and DAE files?

That happen because noesis export standardly fbx 7.7 version that is not supported by old 3d studio max. the solution could be update your 3d studio max OR in advance option in Noesis select a previous fbx version. Mono explained in a post how to do it in this post

[viewtopic.php?p=168554#p168554](https://forum.xentax.com/viewtopic.php?p=168554#p168554)
## Post #129
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-12-20T00:52:40+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

What I did was just remove the FBX and replace it with the 2014 in optional folder then renamed it.
It does open now but still need to do more tests.
## Post #130
- Username: Exit93
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 04, 2021 4:19 am
- Post datetime: 2021-01-24T13:01:30+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Great plugin, It's saving me a lot of time

However, I'm having problems with a few models from Metin2
Here are a couple of examples: [https://mega.nz/file/ypx0VDLD#RQk02TXJT ... WMYktonpcc](https://mega.nz/file/ypx0VDLD#RQk02TXJTQgt-dqcq9wIgZJuzpOYIETydWMYktonpcc)

Lemures_boss has a weird problem with the animation where the whole right arm is ignored (it should keep its weapon on its shoulder)

Assassin gets weirder, while the animation is buggy too, a few bones get flipped (see attached screenshot). This happens with many models, mainly player character models.
This happens only when exporting in FBX, it works fine with DAE. However, converting from DAE to FBX makes the problem reappear.
This may sound like a non-issue but very few animations work in collada.

Any Idea on how to fix these?
Now I read the topic and I know you don't really know how to fix the animations, but maybe you have some ideas on the flipped bones problem?
I'm a developer myself so if you could suggest even only where to look it would be of great help

Thanks in advance
[2021-01-24 13_54_35-Untitled - Autodesk 3ds Max 2017.png](https://xentaxbackup.github.io/file/19377_2021-01-24 13_54_35-Untitled - Autodesk 3ds Max 2017.png)
## Post #131
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-01-25T21:11:03+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Exit93 ↑Sun Jan 24, 2021 9:01 pm at Sun Jan 24, 2021 9:01 pm
>
> 
Great plugin, It's saving me a lot of time

However, I'm having problems with a few models from Metin2
Here are a couple of examples: https://mega.nz/file/ypx0VDLD#RQk02TXJT ... WMYktonpcc

Lemures_boss has a weird problem with the animation where the whole right arm is ignored (it should keep its weapon on its shoulder)

Assassin gets weirder, while the animation is buggy too, a few bones get flipped (see attached screenshot). This happens with many models, mainly player character models.
This happens only when exporting in FBX, it works fine with DAE. However, converting from DAE to FBX makes the problem reappear.
This may sound like a non-issue but very few animations work in collada.

Any Idea on how to fix these?
Now I read the topic and I know you don't really know how to fix the animations, but maybe you have some ideas on the flipped bones problem?
I'm a developer myself so if you could suggest even only where to look it would be of great help

Thanks in advance

Hi Exit93, glad your finding my script useful, 

I think i have an answer as to why this happens but no answer how to fix it,
take a look at the link it will at least get you started at what i think is the problem.
in order to fix it i think you best bet is contacting noesis creator on xentax discord , he answers questions and provides help when asked, and he is by far more knowledgeable than me.

[https://blender.stackexchange.com/quest ... to-another](https://blender.stackexchange.com/questions/48311/why-is-my-animation-performing-weird-rotation-from-one-frame-to-another)

edit:
Just to clarify FBX uses Euler as far as i know
## Post #132
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-01-25T22:11:21+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hey, I'm really loving this but really looking forward to some love for Mechassault 2 and some support be added for the animation .GR2 files. So far I can only open up and preview the base skeleton, but animations are another story.. I attached some skeletons and animations for a more in-depth analysis.
Thanks yet again for this great plugin!

Here are the animation samples:
[https://mega.nz/file/9Z5WhC7I#0lFeK8kae ... u_3MpSWzsE](https://mega.nz/file/9Z5WhC7I#0lFeK8kaekHIzmj97XNrEZPEuf_RLRIwwu_3MpSWzsE)
[MA2_GR2_Skeleton.png](https://xentaxbackup.github.io/file/19397_MA2_GR2_Skeleton.png)
## Post #133
- Username: Ivan04
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 31, 2019 4:05 am
- Post datetime: 2021-01-25T23:19:55+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hearing about getting some use for .gr2 files is amazing, thank you so much for this, it creates hopes which I never thought I would have. Agreeing with Pepsee, Mechassault 2 would do a really great addition for supported files aswell, being it one of those I never thought I would consider, but now things are turning in a bright direction and it make an amazing addition to the list.
## Post #134
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-01-28T20:35:10+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Has any progress been made? I'm really excited at least the skeletons are viewable/exportable.
## Post #135
- Username: MadCat NovaCat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 08, 2021 8:48 pm
- Post datetime: 2021-02-08T12:57:38+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hello there, I've been looking around the internet for .GR2 format help and I saw this thread a while back and thought nobody would bring up Mechassault so I just never bothered.. Now that I know people are actively interested in this game I had to make an account to ask for support for this format, that game was my childhood.
## Post #136
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-02-10T18:53:30+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Pepsee ↑Tue Jan 26, 2021 6:11 am at Tue Jan 26, 2021 6:11 am
>
> 
Hey, I'm really loving this but really looking forward to some love for Mechassault 2 and some support be added for the animation .GR2 files. So far I can only open up and preview the base skeleton, but animations are another story.. I attached some skeletons and animations for a more in-depth analysis.
Thanks yet again for this great plugin!

Here are the animation samples:
https://mega.nz/file/9Z5WhC7I#0lFeK8kae ... u_3MpSWzsE

Hi,

I have tried using vtr_skeleton with vtr_run and with vtr_walk and animations seems to work with both of them, can you please let me know which animations aren't working and what skeleton is associated with the animation.

edit:
also tried P_G_skeleton with P_G_run_pilot and aniamtion works great
## Post #137
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-02-11T07:40:18+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

What version of the script? Latest release?
## Post #138
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-02-12T13:02:26+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thank you so much for your support and implication! Finally able to properly port this to Garry's Mod, now I'm going to try to have them scripted so people can have chaotic PVP/PVE fun with them!
## Post #139
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-02-12T13:04:49+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Version 1.2.6.1 Release

Thanks to Pepsee i found a missing parameter when converting old type animations to new type that i haven't encountered yet,  
now all tested Mechassault 2 animations work.
## Post #140
- Username: noire90
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 13, 2020 7:49 am
- Post datetime: 2021-02-20T10:41:44+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

It is possible to import scene maps from Divinity Original Sin 2 with this plugin?
## Post #141
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-02-20T21:57:50+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from noire90 ↑Sat Feb 20, 2021 6:41 pm at Sat Feb 20, 2021 6:41 pm
>
> 
It is possible to import scene maps from Divinity Original Sin 2 with this plugin?

Well my intrest is more with charecter models so i have only tested those, but if the scene maps are in .gr2 format i dont see any reason they wont work.
## Post #142
- Username: TheFalcon19
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 25, 2019 9:42 pm
- Post datetime: 2021-02-27T03:21:54+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Looked into some ESO models that have the uv issue and it looks like they simply have the two uv channels in shorts instead of floats.
## Post #143
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-03-01T19:36:04+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from TheFalcon19 ↑Sat Feb 27, 2021 11:21 am at Sat Feb 27, 2021 11:21 am
>
> 
Looked into some ESO models that have the uv issue and it looks like they simply have the two uv channels in shorts instead of floats.

Hi TheFalcon19,

In the past i remembered checking UV for shorts and i didnt find anything, but thanks to your post i decided to take another look,
at first i didnt find anything until i rememberedi reading somewhere about normlizing shorts to get floats or something similer, once  i went down that path i figured it out , goes to show you what exprience gives you   

by the way it works with signed shorts only from what i tested.

ill be uploading a new version in a day or so.
## Post #144
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-03-02T08:48:32+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Version 1.2.7 Release

1. Now supports UV for ESO static meshes 
2. Added Support for Bauldrs Gate 3 .PAK files archive - has known issue with LowTex.pak - files are extracted but they arent usable , seem to be missing  headers at the very least, anyway i dont have any plans to try and get them working.

edit:
I forgot to add that in order to get UV for ESO static meshes i added a game tag, GAME_TAG_ESO_STATIC = 1 since there was no way for the script to tell the diffrence between these meshes and any other.
its currently on by deafult and should not cause any issues for most games, but if any game get distorted UV try diabling it.

The Support for BG3 .PAK was added, to make script a bit more about BG3 which was my main reason for making it, and to get some practice with  Archives and lz4 compression.

I have a weird issue with extractor, maybe someone can help me figure out what the issue is.
as you can see in gif below, when i double click file for export in runs thru the entire script without actually exporting the data.
i can then export normaly, and when i close the extractor it again runs thru the entire script without actually exporting the data.
as you can imagine for big files it causes a huge delay in loading and when closing as we actually run thru the file 3 times.



Extractor code:

```
from math import *
from inc_noesis import *
import struct
import os
import io


def registerNoesisTypes(): 
    handle = noesis.register("Bauldrs Gate 3 Archive", ".pak")
    noesis.setHandlerExtractArc(handle, extractPAK)
    #opens debug consle
    noesis.logPopup()
    return 1
    
def noepyCheckType(data):
    '''Verify that the format is supported by this plugin. Default yes'''
    return 1
    

#get file and directory names from string 
def getfilename(name):
    array = name.split('/')
    filename = array[len(array)-1]
    num = len(name) - len(filename)
    directoryname = name[:num]

    return filename, directoryname

    
    
def extractPAK(fileName, fileLen, justChecking):
        

        
def extractPAK(fileName, fileLen, justChecking):
                   
    with open(fileName, "rb") as f:
        
        if justChecking:
            return 1
                
        f.seek(4,0) # magic
        version = struct.unpack("<I",f.read(4))[0] 

        #Get file names and parameters
        table_offset = struct.unpack("<Q",f.read(8))[0]
        f.seek(table_offset,0)
        NumFiles = struct.unpack("<I",f.read(4))[0] 
        CompressedSize = struct.unpack("<I",f.read(4))[0] 

        #Save current location
        TableOffset = f.tell()
        UncompressedSize = NumFiles * 296
        
        #Decompress using lz4.block format
        DecompressedData = rapi.decompLZ4(f.read(CompressedSize),UncompressedSize)

        #Convert data to IO format       
        DecompressStream = NoeBitStream(bytes(DecompressedData), NOE_LITTLEENDIAN)
        
        for i in range(NumFiles): 
            string = noeStrFromBytes(DecompressStream.readBytes(256), "UTF8")
            offset = DecompressStream.readUInt64()
            CompressedSize = DecompressStream.readUInt64()
            UncompressedSize = DecompressStream.readUInt64()
            dummy = DecompressStream.readUInt64()
            crc = DecompressStream.readUInt()
            dummy = DecompressStream.readUInt()

            f.seek(offset,0)
            #if file is compressed

            if UncompressedSize != 0 and fileName[-10:] != 'LowTex.pak':       
                FileDecompressedData = rapi.decompLZ4(f.read(CompressedSize),UncompressedSize)

            else:
                #data is not compressed
                #print("uncompressed file" + string)
                FileDecompressedData = f.read(CompressedSize)

            filename, directoryname = getfilename(string)
            print("{} {}".format(i,directoryname + filename))
            rapi.exportArchiveFile(directoryname + filename , FileDecompressedData)  
            
        
    return 1   
```
## Post #145
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2021-03-03T12:52:52+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Amazing work!  For some reason when I try to export any ESO static mesh, Noesis crashes. I am experimenting to see if I can figure it out.  Thanks for your work

Edit: I'm an idiot, was using old version of Noesis.  Works great
## Post #146
- Username: kodachrome
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 31, 2017 8:11 am
- Post datetime: 2021-03-31T23:49:24+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Is Noesis with this Plugin meant to be able to preview/view GR2 files? In Baldurs Gate 3, want to extract character models for 3D Printing. 
I have tried two Granny2.dll files and both give an error 


Kinda looks like a 64bit dll in a 32bit application error..


I do not have this problem with Norbytes LSLib on the same files, using the same Granny2.dll file??
[https://github.com/Norbyte/lslib](https://github.com/Norbyte/lslib)


EDIT: Looks like this DLL build works:
[https://github.com/nikita322/GrannyConverter2.11.8](https://github.com/nikita322/GrannyConverter2.11.8)
## Post #147
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-01T04:19:39+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from kodachrome ↑Thu Apr 01, 2021 7:49 am at Thu Apr 01, 2021 7:49 am
>
> 
Is Noesis with this Plugin meant to be able to preview/view GR2 files? In Baldurs Gate 3, want to extract character models for 3D Printing. 
I have tried two Granny2.dll files and both give an error 


Kinda looks like a 64bit dll in a 32bit application error..


I do not have this problem with Norbytes LSLib on the same files, using the same Granny2.dll file??
https://github.com/Norbyte/lslib


EDIT: Looks like this DLL build works:
https://github.com/nikita322/GrannyConverter2.11.8

You are correct, noesis is a 32bit application therefore i was able to add support only for 32bit granny2.dll, you need to find a different version, then it will work for you just make sure its one that supports BitKnit compression, there is a link somewhere in this thread, (by the way i Norbytes tool uses 64 bit Granny )

Nevermind i see you found it on your own  - ill leave my answer for future refernce
## Post #148
- Username: kodachrome
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 31, 2017 8:11 am
- Post datetime: 2021-04-03T06:02:35+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thanks for the reply, yep got that working. 

Do Animations work for BG2? Trying to get one of Laezel's animations as an exportable pose. Enabled Animations in the Python script, open "GTY_F_NKD_Head_Laezel.GR2" , select the same file for animations (the GR2 file also contains the animations right? This is in the _Anims folder) but Noesis gives this error:
## Post #149
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-03T18:57:42+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from kodachrome ↑Sat Apr 03, 2021 2:02 pm at Sat Apr 03, 2021 2:02 pm
>
> 
Thanks for the reply, yep got that working. 

Do Animations work for BG2? Trying to get one of Laezel's animations as an exportable pose. Enabled Animations in the Python script, open "GTY_F_NKD_Head_Laezel.GR2" , select the same file for animations (the GR2 file also contains the animations right? This is in the _Anims folder) but

Yes most animations work, i did find a few that were really messed up, i have a theory its beacuse they have really high oversampelling that my interpolation isnt handeling well enough, but i never tested it.

I took a look at "GTY_F_NKD_Head_Laezel.GR2"  and it does not contain any animation data, as far as i can remember animation are always on seperate files from the mesh. i manged to find an animation file that worked with the head, but almost all i tried seemed to do nothing.
tested all of them with granny viewer , so no issue with my script just need to find the correct files.
## Post #150
- Username: kodachrome
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 31, 2017 8:11 am
- Post datetime: 2021-04-04T03:13:37+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Just so I can see the workflow working.. can you give me a suggested BG3 model and anim file that does work in Granny viewer?

thanks
## Post #151
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-04T12:02:44+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from kodachrome ↑Sun Apr 04, 2021 11:13 am at Sun Apr 04, 2021 11:13 am
>
> 
Just so I can see the workflow working.. can you give me a suggested BG3 model and anim file that does work in Granny viewer?

thanks

Well tons of animations work with my script, but if you want an example:

mesh + skeleton file
Proxy_BUGBEAR_A.GR2

Animation
BUGBEAR_Rig_DFLT_CMBT_Skill_Javelin_Throw_01_Attack.GR2

as for the granny viewer all meshes seem black (my guess is since BG3 dosent store normals for mesh), so you wont be able to see mesh very well unless  you uncheck Solid fill under mesh display. 

On a side note, I am working on adding texture support for BG3, if you have some experience with applaying PBR textures to meshs and know which channel stores what data etc.. that would be very helpfull
## Post #152
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-04-18T06:52:38+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Diablo 2 Resurrected is also use some kind of .gr2 (but named .model) model. Is it possible for you to add support of this game? 



If you want, I can send you some example files.
## Post #153
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-18T07:24:30+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ivenend ↑Sun Apr 18, 2021 2:52 pm at Sun Apr 18, 2021 2:52 pm
>
> 
Diablo 2 Resurrected is also use some kind of .gr2 (but named .model) model. Is it possible for you to add support of this game? 

If you want, I can send you some example files.

Sure Post some samples and i will take a look at it
## Post #154
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-04-18T07:44:19+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Sun Apr 18, 2021 3:24 pm at Sun Apr 18, 2021 3:24 pm
>
> 
Ivenend wrote: ↑Sun Apr 18, 2021 2:52 pm
Diablo 2 Resurrected is also use some kind of .gr2 (but named .model) model. Is it possible for you to add support of this game? 

If you want, I can send you some example files.


Sure Post some samples and i will take a look at it
[https://drive.google.com/file/d/1M70iiR ... BYboM/view](https://drive.google.com/file/d/1M70iiRA3A3YOOzbspk6Ixsvq8zOBYboM/view)
## Post #155
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-18T20:41:20+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ivenend ↑Sun Apr 18, 2021 3:44 pm at Sun Apr 18, 2021 3:44 pm
>
> 
jayn23 wrote: ↑Sun Apr 18, 2021 3:24 pm
Ivenend wrote: ↑Sun Apr 18, 2021 2:52 pm
Diablo 2 Resurrected is also use some kind of .gr2 (but named .model) model. Is it possible for you to add support of this game? 

If you want, I can send you some example files.


Sure Post some samples and i will take a look at it

https://drive.google.com/file/d/1Hx9Ire ... sp=sharing

I cant access the files using your link, please fix it or give me premission to files.
## Post #156
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-04-19T00:46:06+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Mon Apr 19, 2021 4:41 am at Mon Apr 19, 2021 4:41 am
>
> 
Ivenend wrote: ↑Sun Apr 18, 2021 3:44 pm
jayn23 wrote: ↑Sun Apr 18, 2021 3:24 pm


Sure Post some samples and i will take a look at it

https://drive.google.com/file/d/1M70iiR ... sp=sharing


I cant access the files using your link, please fix it or give me premission to files.
Sorry, please try this link:
[https://drive.google.com/file/d/1M70iiR ... BYboM/view](https://drive.google.com/file/d/1M70iiRA3A3YOOzbspk6Ixsvq8zOBYboM/view)
or
[https://www.dropbox.com/sh/c4i8hjym4hav ... 5SROa?dl=0](https://www.dropbox.com/sh/c4i8hjym4hav6p9/AABJ0oIewt3w-TIiONcF5SROa?dl=0)
## Post #157
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-19T18:40:32+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Ill be adding support for .model in my next update, should be coming in next few days - its has a ton of new or improved features 
all depends how fast i can iron out the bugs..
## Post #158
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2021-04-20T02:11:24+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Since i'd ask later anyway...  
Here a few enemies files which also have skeleton and anim files~

[https://www.mediafire.com/file/ubml1rk2 ... y.rar/file](https://www.mediafire.com/file/ubml1rk25gm9cl6/enemy.rar/file)
## Post #159
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-20T19:48:37+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Allanoon ↑Tue Apr 20, 2021 10:11 am at Tue Apr 20, 2021 10:11 am
>
> 
Since i'd ask later anyway...  
Here a few enemies files which also have skeleton and anim files~

https://www.mediafire.com/file/ubml1rk2 ... y.rar/file

Regarding Diablo 2 Resurrected support, i got mesh, skeleton and animtions working but there is a big problem...  
The mesh and skeleton sizes are misaligned by thousends so a typical vertcie would be 4000 and the corresponding bone would be 0.8, by manuualy finding the right relation everything works, the problem is every mesh is scaled differently in relation to skeleton.
So we need to find where this is stored, if you can find any files relating to these creatures please upload and i will look for something..

by the way if someone can tell me what format the textures are i can auto texture support here, i looked at it , seems like RGBA no compression but i couldnt find the right format to display it correctly.
## Post #160
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2021-04-20T22:37:27+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Wed Apr 21, 2021 3:48 am at Wed Apr 21, 2021 3:48 am
>
> 

Regarding Diablo 2 Resurrected support, i got mesh, skeleton and animtions working but there is a big problem...  
The mesh and skeleton sizes are misaligned by thousends so a typical vertcie would be 4000 and the corresponding bone would be 0.8, by manuualy finding the right relation everything works, the problem is every mesh is scaled differently in relation to skeleton.
So we need to find where this is stored, if you can find any files relating to these creatures please upload and i will look for something..

by the way if someone can tell me what format the textures are i can auto texture support here, i looked at it , seems like RGBA no compression but i couldnt find the right format to display it correctly.

1st thing 1st... thanks are in order   
Regarding the files, i uploaded what for my "no knowledge" could make sense.
[https://www.mediafire.com/file/wv2j05s0 ... ta.7z/file](https://www.mediafire.com/file/wv2j05s0guxxcu5/data.7z/file)
## Post #161
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-04-21T16:09:59+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Wed Apr 21, 2021 3:48 am at Wed Apr 21, 2021 3:48 am
>
> 
Allanoon wrote: ↑Tue Apr 20, 2021 10:11 am
Since i'd ask later anyway...  
Here a few enemies files which also have skeleton and anim files~

https://www.mediafire.com/file/ubml1rk2 ... y.rar/file


by the way if someone can tell me what format the textures are i can auto texture support here, i looked at it , seems like RGBA no compression but i couldnt find the right format to display it correctly.

Unfortunately we still didn't work out how to open .texture files yet.
## Post #162
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-04-23T11:55:25+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Allanoon ↑Wed Apr 21, 2021 6:37 am at Wed Apr 21, 2021 6:37 am
>
> 
jayn23 wrote: ↑Wed Apr 21, 2021 3:48 am

Regarding Diablo 2 Resurrected support, i got mesh, skeleton and animtions working but there is a big problem...  
The mesh and skeleton sizes are misaligned by thousends so a typical vertcie would be 4000 and the corresponding bone would be 0.8, by manuualy finding the right relation everything works, the problem is every mesh is scaled differently in relation to skeleton.
So we need to find where this is stored, if you can find any files relating to these creatures please upload and i will look for something..

by the way if someone can tell me what format the textures are i can auto texture support here, i looked at it , seems like RGBA no compression but i couldnt find the right format to display it correctly.


1st thing 1st... thanks are in order   
Regarding the files, i uploaded what for my "no knowledge" could make sense.
https://www.mediafire.com/file/wv2j05s0 ... ta.7z/file

The files in "Global" folder are not relate to 3D model at all.
## Post #163
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-04-24T09:19:19+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Not sure if it can help, but it seems that using this setting in Rawtex can somewhat convert a D2R .texture file.
with setting BC3, 1024x1024 and offset 0x7c


[https://i.imgur.com/FJoUc7H.jpg](https://i.imgur.com/FJoUc7H.jpg)
## Post #164
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-24T18:45:27+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ivenend ↑Sat Apr 24, 2021 5:19 pm at Sat Apr 24, 2021 5:19 pm
>
> 
Not sure if it can help, but it seems that using this setting in Rawtex can somewhat convert a D2R .texture file.
with setting BC3, 1024x1024 and offset 0x7c


https://i.imgur.com/FJoUc7H.jpg

Thanks, 
i just saw the discord disscusion and template provided by Zee, i havent tried yet but that should be more than enough to get textures working.

Edit:
Textures are now working on a texture only script, i will need a bit more time to get them implemented in the GR2 script, plus i will be loading only albedo and normal maps as i have no clue how to load PBR in noesis.

Edit2:
Thanks to Zee on discord server i now have the scale issue fixed
## Post #165
- Username: ithamar73
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 24, 2019 7:23 am
- Post datetime: 2021-04-24T19:22:59+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hi, I was looking at the game Carnivores Dinosaur Hunter Reborn, and it uses GR2 files as well, though they are the Big Endian kind. Are you interested in adding support for that, or accepting patches for those?
I've attached a sample in case you are interested.
[revolver.zip](https://xentaxbackup.github.io/file/19949_revolver.zip)
## Post #166
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-24T20:08:29+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from ithamar73 ↑Sun Apr 25, 2021 3:22 am at Sun Apr 25, 2021 3:22 am
>
> 
Hi, I was looking at the game Carnivores Dinosaur Hunter Reborn, and it uses GR2 files as well, though they are the Big Endian kind. Are you interested in adding support for that, or accepting patches for those?
I've attached a sample in case you are interested.

Big Endian is already supported by my script, and your sample works  - no work needed
## Post #167
- Username: ithamar73
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 24, 2019 7:23 am
- Post datetime: 2021-04-24T21:30:32+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Sun Apr 25, 2021 4:08 am at Sun Apr 25, 2021 4:08 am
>
> 
Big Endian is already supported by my script, and your sample works  - no work needed

Oh man, I now see I was not using the latest version of your plugin, I downloaded the one from this thread but there are 2 more versions linked below it (in other topics) 

My apologies and thanks for your awesome work!
## Post #168
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-25T19:28:28+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Since i am taking my time with the new update i thought ill show some of the progress done in action.
Everything D2R is working excluding meshes that have multiple materials per polygroup which is a real pain in the ass to fix without breaking other things, if i dont get it soon ill just realse as is and update someday if ever   




Credit to Zee for providing texture format
[https://github.com/CucFlavius/Zee-010-T ... Texture.bt](https://github.com/CucFlavius/Zee-010-Templates/blob/main/DiabloIIResurrected_Texture.bt)
## Post #169
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-04-26T15:51:38+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Mon Apr 26, 2021 3:28 am at Mon Apr 26, 2021 3:28 am
>
> 
Since i am taking my time with the new update i thought ill show some of the progress done in action.
Everything D2R is working excluding meshes that have multiple materials per polygroup which is a real pain in the ass to fix without breaking other things, if i dont get it soon ill just realse as is and update someday if ever   




Credit to Zee for providing texture format
https://github.com/CucFlavius/Zee-010-T ... Texture.bt

for now here is the texture only script
fmt_D2R _texture.rar

Wow, that looks great! 
Zee also provided information of D2R models, model sections and shader, would those help? [https://github.com/CucFlavius/Zee-010-Templates](https://github.com/CucFlavius/Zee-010-Templates)
## Post #170
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-26T16:08:19+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ivenend ↑Mon Apr 26, 2021 11:51 pm at Mon Apr 26, 2021 11:51 pm
>
> 
Zee also provided information of D2R models, model sections and shader, would those help? https://github.com/CucFlavius/Zee-010-Templates

Well i already had models and models section so no need, and shaders are out of scope for the script.
I manged to get multiple materials set by polygroups, now my only issue is how to get Autotexturing for D2R to work with Autotexturing for BG3 as they both conflict in quite a few places.
## Post #171
- Username: zelibobo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 30, 2019 8:32 pm
- Post datetime: 2021-04-27T05:20:30+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Mon Apr 26, 2021 3:28 am at Mon Apr 26, 2021 3:28 am
>
> 
for now here is the texture only script
fmt_D2R _texture.rar
  You can see what is wrong in your free time:

data\hd\bvt\textures\default_thickness.texture

It looks like you need to add exceptions.
app Raw texture cooker extracted this file offset 0x7c
## Post #172
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-04-27T08:32:54+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from zelibobo ↑Tue Apr 27, 2021 1:20 pm at Tue Apr 27, 2021 1:20 pm
>
> 
jayn23 wrote: ↑Mon Apr 26, 2021 3:28 am
for now here is the texture only script
fmt_D2R _texture.rar

  You can see what is wrong in your free time:

data\hd\bvt\textures\default_thickness.texture

It looks like you need to add exceptions.
app Raw texture cooker extracted this file offset 0x7c

Can’t open the images you posted
## Post #173
- Username: zelibobo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 30, 2019 8:32 pm
- Post datetime: 2021-04-27T11:02:08+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Can’t open the images you posted
 Changed image hosting...
## Post #174
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-27T11:16:29+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from zelibobo ↑Tue Apr 27, 2021 1:20 pm at Tue Apr 27, 2021 1:20 pm
>
> 
  You can see what is wrong in your free time:

 Yup i know whats wrong, can you please upload a sample so i can test new version
## Post #175
- Username: zelibobo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 30, 2019 8:32 pm
- Post datetime: 2021-04-27T11:20:39+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Yup i know whats wrong, can you please upload a sample so i can test new version
[default_thickness.zip](https://www.mediafire.com/file/itf30rz7qctuzgp/default_thickness.zip/file)
## Post #176
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-27T12:00:29+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from zelibobo ↑Tue Apr 27, 2021 7:20 pm at Tue Apr 27, 2021 7:20 pm
>
> 

 Yup i know whats wrong, can you please upload a sample so i can test new version

default_thickness.zip

Thanks,

Updated script in original post
## Post #177
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-28T20:03:03+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Version 1.3

Changelist:

New/Improved Features:

MULTIFILE - Completly rewrote code to load and combine multiple .gr2 files.
New version now works with paired animation and paired skeleton options.
Weight and Bone Binding Auto correction - if a bone bindings refers to a bone that dosent exist or weights are 0 for the only bone that 
exists script will automaticly find the closest bone that exists and assign it to vertcie.
Will now load files in selected directory only, old code unintentionally also loaded files in any existing sub directories.
New option when merging multiple files:
SMART_DETECTION = 0 - What old script did, just combines everything Blindly.
SMART_DETECTION = 1 - Check and remove any duplicate bones by name only (should be used for files containing similar skeletons)
SMART_DETECTION = 2 - Check and remove any duplicate bones by name and comparing InverseWorld transform matrix.

Script now loads meshes properly when a polygroup has multiple materials.
Multiple small bug fixes

Baldur's Gate 3:
Upadted .PAK extractor to work with texture.pak archive post Patch 4 update.
Using a new Version of noesis seems to have fixed the old issue where file would load multiple time during extraction.

Added Initial Support for Auto Texturing  - Currently only loads Albedo and Normal Maps.
Requierments:
GAMETAG_BG3_TEXTURES = 1 must be set to 1 in order to load textures
BG3 PATH must be updated in script
Shared.pak and Textures.pak must be unpacked

Known issues:
When Extracting texture.pak it will show a false error, just press OK and it will continue exporting archive. 
Auto Texturing is still very buggy and dosent always find and set the correct texture.
its also very slow and could take up to 15 seconds to load.
I am currently rewriting the enire Autotexturing script to be both faster and more effective but it will take some time. 

Age of Empires 3/ Online:
Games are now fully supported.
Added Support for FD format based on source code by kangcliff 
[https://github.com/kangcliff/Age-of-Empires-III](https://github.com/kangcliff/Age-of-Empires-III)


Diablo II: Resurrected
Added Support for .model;.skeleton;.animations; .texture formats.
for Auto Texturing to work files should be  in textures directory or it wont find them. 
Only Normal and Albedo maps are loaded.
For each Creature there is one file that contains all animations, you can use the ANIMATION_TRACK option to choose which track to load.

Example use for new MULTIFILE and BG3 Features
with the following Option set:
MULTIFILE = 1 
SMART_DETECTION = 1
ANIMATION_MODE = 1
GAMETAG_BG3_TEXTURES = 1

Placed the follwoing .gr2 files in chosen folder.
MINOTAUR_ARM_Bracers_A.GR2
MINOTAUR_ARM_Chest_A.GR2
MINOTAUR_ARM_Footwear_A.GR2
MINOTAUR_ARM_Skirt_A.GR2
MINOTAUR_Body_A.GR2
MINOTAUR_Body_A_Fur.GR2
MINOTAUR_Head_A.GR2
MINOTAUR_Head_A_Fur.GR2
MINOTAUR_Head_A_Horns.GR2

In Seperate location placed:
MINOTAUR_Rig_DFLT_LOCO_Sprint_F_CMBT_01.GR2

Now when running script we choose the folder with all of the MINOTAUR parts, it will merge all meshes and bones into a single Model seperated by sub mehes and a single skeleton, by turning on SMART_DETECTION = 1 any bones with duplicate names are deleted.
ANIMATION_MODE = 1 will now allow us to pair the new combined model with an animation file.
GAMETAG_BG3_TEXTURES = 1 will attempet to auto texture model.

And here is the Result:

[fmt_GR2reader13.rar](https://xentaxbackup.github.io/file/19977_fmt_GR2reader13.rar)
## Post #178
- Username: zelibobo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 30, 2019 8:32 pm
- Post datetime: 2021-04-29T09:07:39+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I apologize. Take a look in your spare time. Thank you.


[download ~86kb](https://www.mediafire.com/file/5yvhbx1w5x5cqen/standard_spheres_lod0.zip/file)
## Post #179
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-29T11:00:54+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from zelibobo ↑Thu Apr 29, 2021 5:07 pm at Thu Apr 29, 2021 5:07 pm
>
> 
I apologize. Take a look in your spare time. Thank you.


download ~86kb

This isnt a problem with the script just a noesis limitation for loading to many models at once.
To bypass this issue simply set option MERGE_SCENE = 1 and it will merge all models and allow file to load.
## Post #180
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-04-29T11:28:15+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thanks for your hard work, the new plugin generally works fine. But there is a small issue:

the normal (UV?) seems kind of broken on some models, like this:


The normal of the same model looks fine if I export the model to DAE with LSLIB([https://github.com/Norbyte/lslib](https://github.com/Norbyte/lslib)):


The sword model I shown above is this one: [https://drive.google.com/file/d/1jWXzVm ... sp=sharing](https://drive.google.com/file/d/1jWXzVm6e65jAP3Z-gf2Qsgi3S3_A67P5/view?usp=sharing)

BTW, would you like to join our D2R modding discord? We have many discussion of D2R model and texture there: [https://discord.gg/fXpPPd6fUm](https://discord.gg/fXpPPd6fUm)
## Post #181
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-29T11:50:46+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ivenend ↑Thu Apr 29, 2021 7:28 pm at Thu Apr 29, 2021 7:28 pm
>
> 
Thanks for your hard work, the new plugin generally works fine. But there is a small issue:

The sword model I shown above is this one: https://drive.google.com/file/d/1jWXzVm ... sp=sharing

BTW, would you like to join our D2R modding discord? We have many discussion of D2R model and texture there: https://discord.gg/fXpPPd6fUm

how did you convert using LSLIB?  it just gives me an error that positions need to be a VECTOR 3  while here we have a VECTOR 4.
can you tell me what the vert count is with the version from LSLIB?

Joined your Discord by the way , for now i just lurk
## Post #182
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-04-29T11:57:37+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Thu Apr 29, 2021 7:50 pm at Thu Apr 29, 2021 7:50 pm
>
> 

can you tell me what the vert count is with the version from LSLIB?

Joined your Discord by the way , for now i just lurk

On April 20th, Norbyte added a preliminary support for D2R .model on github. It is not a "release" version so you need to compile it by yourself.

[https://github.com/Norbyte/lslib/issues ... -823177875](https://github.com/Norbyte/lslib/issues/67#issuecomment-823177875)
[https://github.com/Norbyte/lslib/commit ... 70de45c661](https://github.com/Norbyte/lslib/commit/feb8350d2ef952c5ee6024090821d270de45c661)
## Post #183
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-29T12:24:59+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ivenend ↑Thu Apr 29, 2021 7:57 pm at Thu Apr 29, 2021 7:57 pm
>
> 
jayn23 wrote: ↑Thu Apr 29, 2021 7:50 pm

can you tell me what the vert count is with the version from LSLIB?

Joined your Discord by the way , for now i just lurk  


On April 20th, Norbyte added a preliminary support for D2R .model on github. It is not a "release" version so you need to compile it by yourself.

https://github.com/Norbyte/lslib/issues ... -823177875
https://github.com/Norbyte/lslib/commit ... 70de45c661

Thanks i managed to build LSLIB.
Edit:
It seems i was mistaken as vertcie count for my mesh and and from LSLIB is the same, the vertcies are unwelded on the seam we see on the mesh for both scripts, so i am not sure why its looks like that on mine, maybe its related to normals or Tangents after all...
## Post #184
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-04-29T20:32:18+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Nice work Mate!
Just Down Loaded the latest version and started playing with it.
Of course I work with Silent Hunter 5 and have a few questions.
Can a way be added to ignore some 3D meshes and not load them?
## Post #185
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-29T21:08:14+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Fri Apr 30, 2021 4:32 am at Fri Apr 30, 2021 4:32 am
>
> 
Nice work Mate!
Just Down Loaded the latest version and started playing with it.
Of course I work with Silent Hunter 5 and have a few questions.
Can a way be added to ignore some 3D meshes and not load them?

Thanks   
Well that depends how do you plan on filtering these meshes? by poly count, name, order?
I assume you want to filter out LOD and keep only high poly meshes?

if you have some way to filter these meshes I can do it.

can you post a sample, and explain what you want to ignore?
## Post #186
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-04-30T15:41:52+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Here's a sample. I included a txt that lists the Meshes to skip by name.
It would be better if We could edit the mesh to skip names.
I could then write a script for 010 to do quick edits as I need them.


[https://www.mediafire.com/file/d1mln1ea ... e.zip/file](https://www.mediafire.com/file/d1mln1eahjby0t2/Example_File.zip/file)
## Post #187
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-01T20:07:40+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Fri Apr 30, 2021 11:41 pm at Fri Apr 30, 2021 11:41 pm
>
> 
Here's a sample. I included a txt that lists the Meshes to skip by name.
It would be better if We could edit the mesh to skip names.
I could then write a script for 010 to do quick edits as I need them.


https://www.mediafire.com/file/d1mln1ea ... e.zip/file

Here you go, iv included a few options to choose from

Version 1.3.1

Fixed Normals for Diablo II: Resurrected
Added option to exclude loading meshes using a file, file must be called 'mesh.txt' and loacted in main Noesis folder
SKIP_MESH = 1 - skip by mesh name
SKIP_MESH = 2 - skip if mesh name starts with string in file
SKIP_MESH = 3 - skip if mesh name ends with string in file



 fmt_GR2reader131.rar
(27.54 KiB) Downloaded 92 times
## Post #188
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-05-02T00:18:01+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Sun May 02, 2021 4:07 am at Sun May 02, 2021 4:07 am
>
> 




Version 1.3.1

Fixed Normals for Diablo II: Resurrected

It works great! Thank you! 

--------------

BTW Is it possible for you to make your D2R_texture plugin also supports exporting an image to .texture?

-------------

A general GR2 (Granny 3D) question: 

Anyone here knows why some GR2 have opacity alpha channel enable, while some don't? How to know if a GR2 has opacity enable through reading information in Granny Viewer?
## Post #189
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-02T14:01:16+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ivenend ↑Sun May 02, 2021 8:18 am at Sun May 02, 2021 8:18 am
>
> 

--------------

BTW Is it possible for you to make your D2R_texture plugin also supports exporting an image to .texture?

-------------

A general GR2 (Granny 3D) question: 

Anyone here knows why some GR2 have opacity alpha channel enable, while some don't? How to know if a GR2 has opacity enable through reading information in Granny Viewer?

I can try tp do an export to .texture, but i have never done texture data export,so no guarantees, ill probably need some help
with mip maps, and understanding how to recreate them in noesis.

What exactly are you talking about opacity channel? your mean if .gr2 includs data if texture files have opacity enables? if yes thats probably in the Extended Data.
post a smaple with and a smpale without and i can take a look.
## Post #190
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-05-02T14:19:25+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Sun May 02, 2021 10:01 pm at Sun May 02, 2021 10:01 pm
>
> 
Ivenend wrote: ↑Sun May 02, 2021 8:18 am

--------------

BTW Is it possible for you to make your D2R_texture plugin also supports exporting an image to .texture?

-------------

A general GR2 (Granny 3D) question: 

Anyone here knows why some GR2 have opacity alpha channel enable, while some don't? How to know if a GR2 has opacity enable through reading information in Granny Viewer?


I can try tp do an export to .texture, but i have never done texture data export,so no guarantees, ill probably need some help
with mip maps, and understanding how to recreate them in noesis.

What exactly are you talking about opacity channel? your mean if .gr2 includs data if texture files have opacity enables? if yes thats probably in the Extended Data.
post a smaple with and a smpale without and i can take a look.

Thanks!

--------------

Some GR2 will consider the alpha channel of alb.texture as opacity channel, so if there are black part in this alpha channel, the according part of the model will be transparent in game. I call this type of GR2 type A.

Some GR2 will NOT consider the alpha channel of alb.texture as opacity channel, so even if there are black part in this alpha channel, the model will have no transparent part in game. I call this type of GR2 type B.

Here are examples. yew_wand_lod0.model is type A, great_sword_lod0.model is type B.
[https://drive.google.com/file/d/1SQMaEQ ... sp=sharing](https://drive.google.com/file/d/1SQMaEQlJ11YLiuU6gOdGJhn37IhP6KjW/view?usp=sharing)

I want to know what makes the difference. And if it is possible to change it (maybe through Hex edit?).

For now, I suspect the difference is in this information in Granny Viewer:
## Post #191
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-02T16:36:38+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

It is possible to edit the values with a Hex Editor, Yes.
The problem is HOW to locate the exact values to edit.
I have a template for GR2 files for 010 SweetScape that I'll check.
I have downloaded your examples to look at.

And I love the new ability to skip meshes! Saves SO much time working with the files.
 

I'm doing a quick Script for 010 to change option settings.
Just because I'm lazy that way.
## Post #192
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-05-03T12:33:31+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Mon May 03, 2021 12:36 am at Mon May 03, 2021 12:36 am
>
> 
It is possible to edit the values with a Hex Editor, Yes.
The problem is HOW to locate the exact values to edit.
I have a template for GR2 files for 010 SweetScape that I'll check.
I have downloaded your examples to look at.

And I love the new ability to skip meshes! Saves SO much time working with the files.
 

I'm doing a quick Script for 010 to change option settings.
Just because I'm lazy that way.

Thanks for your help. 

Actually I have tried a bit hex edit. While I'm probably still far from located the exact values, I think the bigger problem would be the CRC check of GR2 files. Nearly every time after I did a hex edit, Granny Viewer says that the file fail its CRC check and the game refuse to load the file. Thus I can not even know if I have edit the exact value or not.

Do you have any idea how to defeat the CRC check of GR2?
## Post #193
- Username: timtim
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 21, 2012 2:49 am
- Post datetime: 2021-05-03T13:11:13+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I tried to view|convert GR2 Age of Empires 3 - Definitive Edition files in Noesis 4.442 both with both Reader plugin ver. 1.2.1 and ver. 1.3 but it wasn't successful. 
I tried different ways: before and after [https://github.com/nikita322/GrannyConverter2.11.8](https://github.com/nikita322/GrannyConverter2.11.8), without/with additional copying granny2.lib from nikita322 converter but it always ends with this error:
## Post #194
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-05-03T13:18:49+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from timtim ↑Mon May 03, 2021 9:11 pm at Mon May 03, 2021 9:11 pm
>
> 
I tried to view|convert GR2 Age of Empires 3 - Definitive Edition files in Noesis 4.442 both with both Reader plugin ver. 1.2.1 and ver. 1.3 but it wasn't successful. 
I tried different ways: before and after https://github.com/nikita322/GrannyConverter2.11.8, without/with additional copying granny2.lib from nikita322 converter but it always ends with this error:

You probably just need a v2.11.8 granny2.dll.

With this version of granny2.DLL in your Noesis folder, you can open GR2 from Age of Empires 3 - Definitive Edition directly.
## Post #195
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-03T13:32:23+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ivenend ↑Mon May 03, 2021 8:33 pm at Mon May 03, 2021 8:33 pm
>
> 
Do you have any idea how to defeat the CRC check of GR2?
I have a Script for 010 that will check AND correct the CRC.
## Post #196
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-03T13:45:40+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Mon May 03, 2021 9:32 pm at Mon May 03, 2021 9:32 pm
>
> 
Ivenend wrote: ↑Mon May 03, 2021 8:33 pm
Do you have any idea how to defeat the CRC check of GR2?

I have a Script for 010 that will check AND correct the CRC.

If needed I can add CRC correction option to my script shouldn't be to difficult
## Post #197
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-05-03T13:49:04+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Mon May 03, 2021 9:32 pm at Mon May 03, 2021 9:32 pm
>
> 
Ivenend wrote: ↑Mon May 03, 2021 8:33 pm
Do you have any idea how to defeat the CRC check of GR2?

I have a Script for 010 that will check AND correct the CRC.



Is it possible for you to share your script?

Or could you tell me where is CRC information in GR2 and from where to where the CRC will check, so I can caculate by myself? 

BTW I think GR2 use CRC-32, right?
## Post #198
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-03T13:55:56+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Skip the first 104 bytes and do a CRC-32
The CRC is at 28h

And older version of AOE3 started the CRC count by skipping the first 88 bytes.
## Post #199
- Username: timtim
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 21, 2012 2:49 am
- Post datetime: 2021-05-03T14:00:25+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ivenend ↑Mon May 03, 2021 9:18 pm at Mon May 03, 2021 9:18 pm
>
> 
timtim wrote: ↑Mon May 03, 2021 9:11 pm
I tried to view|convert GR2 Age of Empires 3 - Definitive Edition files in Noesis 4.442 both with both Reader plugin ver. 1.2.1 and ver. 1.3 but it wasn't successful. 
I tried different ways: before and after https://github.com/nikita322/GrannyConverter2.11.8, without/with additional copying granny2.lib from nikita322 converter but it always ends with this error:



You probably just need a v2.11.8 granny2.dll.

With this version of granny2.DLL in your Noesis folder, you can open GR2 from Age of Empires 3 - Definitive Edition directly.

Still no luck, with granny2.dll only in plugins folder Noesis doesn't see gr2 files as known format. Here is two versions of the same model for reference - original and converted v2.11.8 gr2:
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1LVw2CXRT4dmhvWOgJ52lwR6L9qp3EEpp?usp=sharing)
## Post #200
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-03T14:05:44+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Both open for me.
granny2.dll needs to be in the noesis folder with Noesis.exe
NOT in the plug ins folder
## Post #201
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-05-03T14:28:43+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Mon May 03, 2021 9:55 pm at Mon May 03, 2021 9:55 pm
>
> 
The CRC is at 28h

Thanks.

I'm a noob, so sorry for further questions:

With your help, I sucessfully find out the CRC of great_sword_lod0.model (file included in my previous examples.rar). It is the 34 12 D1 B1, that's exactly the CRC shows up on Granny Viewer.


> Reply from 05SpeedMaster ↑Mon May 03, 2021 9:55 pm at Mon May 03, 2021 9:55 pm
>
> 
Skip the first 104 bytes and do a CRC-32

Does "Skip the first 104 bytes" means select start form byte 105[69h] and to the end of the file?
I did an CRC 32(both big Edian and little edian) in 010 Editor and the result is this, which doesn't match the 34 12 D1 B1. What did I do wrong?
## Post #202
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-03T14:30:04+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Ivenend,

Your example files are compressed so hex editing is not going to work.
## Post #203
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-03T14:33:33+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Delete the 1st 104 bytes then CRC-32
## Post #204
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-03T14:39:15+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

//-----------------------------------
// v3.2.2 Script File
//
// File:     GR2Checksum.1sc
// Revision: 2.0
// Purpose: Opens a GR2, performs the CRC32 checksum, and then closes the file.
//----------------------------------------------------------------------------------

TOpenFileNames f = InputOpenFileNames("Open File", "GR2 Files ( *.gr2 )|All Files ( *.* )");
  if (f.count == 0) return;
  int i, n;
  n = FileCount();
  for(i = 0; i < f.count; i++)
{
    FileOpen(f.file.filename);
//Can lock to only certian GR2 files these being SH5
    //if (ReadQuad(00h) != 3122020088697118249 || ReadQuad(08h) != -1233310138417810139) {
  		//if (ReadQuad(00h) != 1130805896766580664 || ReadQuad(08h) != 2161755714778591876) {
  			//MessageBox(idOk, "Error", "File is not GR2 or corrupted!");
  	    //return;
  	  //};
    //};
  	if (ReadInt(20h) < 7) {	MessageBox(idOk, "Error", "Old version of file!");
      return;
    };
 };
if (!IsLittleEndian()) LittleEndian();
  int32 existCRC[f.count], calcCRC[f.count], editCRC[f.count];
  OutputPaneClear();
  for (i = 0; i < f.count; i++)
  {
    FileSelect(i + n);
    existCRC = ReadInt(28h);
    calcCRC = Checksum(CHECKSUM_CRC32, 68h, (FileSize() - 104));
    Printf(f.file.filename + ":   Existing CRC - %x\n", existCRC);
    Printf(f.file.filename + ":   Calculated CRC - %x\n", calcCRC);
    if (existCRC != calcCRC) {
      if (MessageBox(idYes|idNo, "Attention", f.file.filename + "\n\nThe existing CRC is not \nequal to the calculated CRC !\nWould you like to edit ?") == idYes)
      {
        WriteInt(28h, calcCRC[i]);
        FileSave();
        editCRC[i] = ReadInt(28h);
        Printf(f.file[i].filename + ":   Edited CRC - %x\n", editCRC[i]);
      };
    };
  };
  if (MessageBox(idYes|idNo, "Attention", "Would you like to close files ?") == idYes)
  {
    for(i = 0; i < f.count; i++) {
      FileSelect(i + n);
      FileClose();
    };
  };
  return;
## Post #205
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-05-03T14:52:22+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Mon May 03, 2021 10:30 pm at Mon May 03, 2021 10:30 pm
>
> 
Ivenend,

Your example files are compressed so hex editing is not going to work.

That's sad.
Thank you anyway! Learned a lot from you about how CRC work in GR2.

Is it possible to decompress a BitKnit 2 compressed GR2?
## Post #206
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-03T14:57:05+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

//-----------------------------------
//--- 010 Editor v3.2.2 Binary Template
//
// File:          GR2Template.bt
// Author:        Privateer / TheDarkWraith
// Special Thanks to:  Anvart
// Revision:      1
// Purpose:       Defines a template for understanding GR2 files.
//
// Structues built from info obtained from Granny Viewer 2.8.33.0
// and the Granny Change log.
//-----------------------------------

#include "Header.h"


//---------------------------------------------

// Define the headers
LittleEndian(); 
SetBackColor( cLtRed );
GR2FILEHEADER GR2fh<hidden=false>;

SetBackColor( cBlue );
GR2INFOHEADER GR2_Info;
SetBackColor( cLtBlue );

// Display The Sections Information
SetBackColor( cRed );
SECTIONS SectionInfo[8];


++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
//Header.h
// Define structures for Magic Block, header and Section Indexes in Gr2 files

typedef struct {   // GR2fh
    quad   GR2Magic[2]<hidden=true>;
    UINT   HeaderSize<comment="Size of all information before the start of Section 0">;
    LONG   Unknown_info[3]<hidden=true,format=hex>;
} GR2FILEHEADER;

typedef struct {    // GR2ih
    UINT  File_format_revision <format=decimal>;
    UINT  File_Size_in_bytes;
    UINT  CRC <format=hex,comment="CRC of file (from begin of section array up to EoF). Algoritm CRC-32">;
    UINT  SectionArrayOffset <bgcolor=0xffffb0,fgcolor=cRed,comment="Offset to section array">;
    UINT  SectionArrayCount <comment="Total number of sections">;
    UINT  Unknowns[4]<hidden=true,format=hex>;
    UINT  Tag<format=hex>;
    UINT  Unknown[8]<hidden=true,format=hex>;
} GR2INFOHEADER;

typedef struct {   // Sectionsinfo
    UINT  Format<comment="Compression Format">;
    UINT  Pointer<format=hex,bgcolor=cLtGreen,comment="Start of section data">;
    UINT  True_Block_Size_in_file<comment="Compressed Data size">;
    UINT  Block_Size_In_file<comment="Actual amount of Data uncompressed">;
    UINT  Internal_Alignment<comment="offset">;
    UINT  Unknown[2]<bgcolor=cLtYellow,hidden=true>;
    UINT  Another_Pointer<format=hex,bgcolor=cLtGreen,comment="Will explain at a later date">;
    UINT  WTH[3]<bgcolor=cLtYellow,hidden=true>;
} SECTIONS;

/*Sections as used in SH5 GR2 files.
  NOt all GR2 files follow this layout.

         0 - MainSection
	 1 - RigidVertexSection
	 2 - RigidIndexSection
	 3 - DeformableVertexSection
	 4 - DeformableIndexSection
	 5 - TextureSection
	 6 - DiscardableSection
	 7 - UnloadedSection */
## Post #207
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-05-03T16:44:30+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Mon May 03, 2021 10:30 pm at Mon May 03, 2021 10:30 pm
>
> 
Ivenend,

Your example files are compressed so hex editing is not going to work.

I managed to decompressed the two example files   
[https://drive.google.com/file/d/1HSnr67 ... sp=sharing](https://drive.google.com/file/d/1HSnr67pt2iJF6S8rwmnOGLksJpfhFojd/view?usp=sharing)

Could you or Jayn please check these files and see if you can find the opacity enable value?
## Post #208
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-03T17:07:38+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I need a better explanation of where you are finding the values in GrannyViewer.
The complete path to follow.
## Post #209
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-05-03T17:33:52+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Tue May 04, 2021 1:07 am at Tue May 04, 2021 1:07 am
>
> 
I need a better explanation of where you are finding the values in GrannyViewer.
The complete path to follow.

Material List - the last one in the list of material - right click - view in detail - ExtendedData
## Post #210
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-03T21:34:29+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ivenend ↑Sun May 02, 2021 8:18 am at Sun May 02, 2021 8:18 am
>
> 
--------------

BTW Is it possible for you to make your D2R_texture plugin also supports exporting an image to .texture?

-------------

Well i got it working, had to do some reasrch, at least i finally know what MipMpas are now  
Let me know if exported textures are read correctly by game engine.

Before exporting image you must specify what format you want, can be done in 2 ways:
by invoking option in advanced option, or by editing script end choosing a TEX_TYPE.
Normal maps have red and green channels swapped in game, if you need to sawp channels you can invoke swizzle command.
Available Commands:
-DXT1
-DXT5
-BC4
-RGBA32
-SWIZZLE 


Script now supports import/export for .texture
new version in a later post
## Post #211
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-05-04T02:53:44+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Tue May 04, 2021 5:34 am at Tue May 04, 2021 5:34 am
>
> 
Ivenend wrote: ↑Sun May 02, 2021 8:18 am
--------------

BTW Is it possible for you to make your D2R_texture plugin also supports exporting an image to .texture?

-------------


Well i got it working, had to do some reasrch, at least i finally know what MipMpas are now  
Let me know if exported textures are read correctly by game engine.

Before exporting image you must specify what format you want, can be done in 2 ways:
by invoking option in advanced option, or by editing script end choosing a TEX_TYPE.
Normal maps have red and green channels swapped in game, if you need to sawp channels you can invoke swizzle command.
Available Commands:
-DXT1
-DXT5
-BC4
-RGBA32
-SWIZZLE 


Script now supports import/export for .texture
fmt_D2R_texture.rar

I exported an .texture to PNG or DDS, without doing any modification, then re-export the PNG/DDS back to .texture with command -DXT5.

Not sure what's wrong but when I loaded the re-exported .texture in game, the game immediately crash...   
Also the orginal .texture and re-exported texture look very different in HEXEditor...

[https://drive.google.com/file/d/1m0EIpO ... sp=sharing](https://drive.google.com/file/d/1m0EIpOCwHNsC1ucOX-TrTfVVuD811kfO/view?usp=sharing)
## Post #212
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-04T05:37:32+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ivenend ↑Tue May 04, 2021 10:53 am at Tue May 04, 2021 10:53 am
>
> 

I exported an .texture to PNG or DDS, without doing any modification, then re-export the PNG/DDS back to .texture with command -DXT5.

Not sure what's wrong but when I loaded the re-exported .texture in game, the game immediately crash...   
Also the orginal .texture and re-exported texture look very different in HEXEditor...

https://drive.google.com/file/d/1m0EIpO ... sp=sharing

Well this sucks   
i took a look at hex for both and does seem that most of the data is the same, there are always reapting 6 bytes the are different
Data in red is identical, Data in green is repetative and different.
its probably some encoding issue, i tried all Encoding in noesis that i know of, nothing worked.

Can you find a texture map that is type 31 (RGBA format)
and Uplaod or check by your self if data in hex is the same? i want to make sure its just the encoding.
In my script i dont create MipMpas under 16 bye size but that shouldt affect anything in theory...

Original:


Exported:
## Post #213
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-05-04T06:39:47+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Tue May 04, 2021 1:37 pm at Tue May 04, 2021 1:37 pm
>
> 

Well this sucks   
i took a look at hex for both and does seem that most of the data is the same, there are always reapting 6 bytes the are different
Data in red is identical, Data in green is repetative and different.
its probably some encoding issue, i tried all Encoding in noesis that i know of, nothing worked.

Can you find a texture map that is type 31 (RGBA format)
and Uplaod or check by your self if data in hex is the same? i want to make sure its just the encoding.
In my script i dont create MipMpas under 16 bye size but that shouldt affect anything in theory...

Original:


Exported:

RGBA  is still DXT5 but with an alpha channel, right? I believe this one is a RGBA: [https://drive.google.com/file/d/1_F_egU ... sp=sharing](https://drive.google.com/file/d/1_F_egUG2BQJavguaj3xdzOPvT7suNhu1/view?usp=sharing)

I‘m going out now, will do more test on RGBA later tonight.
## Post #214
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-04T08:10:47+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ivenend ↑Tue May 04, 2021 2:39 pm at Tue May 04, 2021 2:39 pm
>
> 

RGBA  is still DXT5 but with an alpha channel, right? I believe this one is a RGBA: https://drive.google.com/file/d/1_F_egU ... sp=sharing

I‘m going out now, will do more test on RGBA later tonight.

RGBA is raw texture, bytes 5,6 comprise the texture type for example in weapon_yew_wand_alb.texture the bytes are 3E 00 that gives us  62 which means it is a DXT5.
I am looking for something that will be a 31 type so I can check if reexporting a image that is not encoded will work.
can you try inserting to game a texture exported as RGBA? and see if it crashes?
## Post #215
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-05-04T08:41:34+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Tue May 04, 2021 4:10 pm at Tue May 04, 2021 4:10 pm
>
> 


RGBA is raw texture, bytes 5,6 comprise the texture type for example in weapon_yew_wand_alb.texture the bytes are 3E 00 that gives us  62 which means it is a DXT5.
I am looking for something that will be a 31 type so I can check if reexporting a image that is not encoded will work.

31 should be 1f in hex right? All textures in D2R I found so far are 3D, 3E, 39(very few), 3A(very few)

> Reply from jayn23 ↑Tue May 04, 2021 4:10 pm at Tue May 04, 2021 4:10 pm
>
> 


can you try inserting to game a texture exported as RGBA? and see if it crashes?

How? Using command -RGBA32?

EDIT: 
Tried exported an texture with  command -RGBA32. [https://drive.google.com/file/d/15Lx34R ... sp=sharing](https://drive.google.com/file/d/15Lx34RKXvhNTWiF_RQEFftb39uMDU7Yw/view?usp=sharing)

The re-exported file is bigger than the original one (4097KB vs 1366KB). 

Interestingly, some re-exported texture still crashes the game ; some would not crash the game, but the colour is obviously broken XD


EDIT2:
the wand should look like this normally BTW



EDIT3:
I already figured out how to enable alpha channel transparency of a .MODEL trough Hex editing. Thanks for all people helped me in this thread!
## Post #216
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-04T21:59:49+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

After finding some RGBA samples to test i can confirm that RGBA32 are byte for byte exactly the same for original and exported .texture. 
next step it getting it in game and checking how it looks.

I updated the script with some new things i found today that were unkonws until now.
there is a variable that chnages based on MipCount until now i was inserting a hard coded number, but now with enough samples i found how to calculate it. maybe that was cusing some textures to crash while others were ok.

the only thing that i am ignoring now is the last 3 Mip Maps they are always 3 maps size of 16 each ones gives different data.
you would expect only 1 map of each size so not sure what the other 2 maps are.


Edit:
Added new version that will teach me to post at 1 am next time 



 fmt_D2R_texture.rar
(1.62 KiB) Downloaded 113 times
## Post #217
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-05-04T23:36:14+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Wed May 05, 2021 5:59 am at Wed May 05, 2021 5:59 am
>
> 
After finding some RGBA samples to test i can confirm that RGBA32 are byte for byte exactly the same for original and exported .texture. 
next step it getting it in game and checking how it looks.

I updated the script with some new things i found today that were unkonws until now.
there is a variable that chnages based on MipCount until now i was inserting a hard coded number, but now with enough samples i found how to calculate it. maybe that was cusing some textures to crash while others were ok.

the only thing that i am ignoring now is the last 3 Mip Maps they are always 3 maps size of 16 each ones gives different data.
you would expect only 1 map of each size so not sure what the other 2 maps are.

Great!

Did you updated the script in the original post? The attachment in the original post seems to be the same.

Is it possible that the other 2 maps be alpha maps? When I tested the wand texture re-exported with RGBA32, which doesn't crash the game but has wrong colour, I found it the transparency of the model on main menu (probably load the "main" map), and in actual game (probably load one of the Mip map) are different, so I guess there might be something relate to alpha channel of the Mip maps.
## Post #218
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-05T04:01:26+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ivenend ↑Wed May 05, 2021 7:36 am at Wed May 05, 2021 7:36 am
>
> 
Great!

Did you updated the script in the original post? The attachment in the original post seems to be the same.

Is it possible that the other 2 maps be alpha maps? When I tested the wand texture re-exported with RGBA32, which doesn't crash the game but has wrong colour, I found it the transparency of the model on main menu (probably load the "main" map), and in actual game (probably load one of the Mip map) are different, so I guess there might be something relate to alpha channel of the Mip maps.

sorry i thought i updated the original post with script but i at 1 am you forgot things i guess..
Added attachment of new verision to previous post.

If the RGBA32 textures still look wired in game with new version, then its probably due to other settings on .gr2 or .json files.
as i said with new version at least RGBA was byte for byte when converted to .dds and then back to RGBA32
## Post #219
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-05-05T05:48:24+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Wed May 05, 2021 12:01 pm at Wed May 05, 2021 12:01 pm
>
> 
Ivenend wrote: ↑Wed May 05, 2021 7:36 am
Great!

Did you updated the script in the original post? The attachment in the original post seems to be the same.

Is it possible that the other 2 maps be alpha maps? When I tested the wand texture re-exported with RGBA32, which doesn't crash the game but has wrong colour, I found it the transparency of the model on main menu (probably load the "main" map), and in actual game (probably load one of the Mip map) are different, so I guess there might be something relate to alpha channel of the Mip maps.



sorry i thought i updated the original post with script but i at 1 am you forgot things i guess..
Added attachment of new verision to previous post.

If the RGBA32 textures still look wired in game with new version, then its probably due to other settings on .gr2 or .json files.
as i said with new version at least RGBA was byte for byte when converted to .dds and then back to RGBA32

Your plugin wroks perfect now! What a great step of D2R modding!
## Post #220
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2021-05-07T15:27:40+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

@jayn23

Sorry to bother you again, but it seems that the plugin may have some small problem on normal (_nrm) textures.

Here is a test, I convert the weapon_shadowfang_nrm.texture to dds, without edit and convert back to .texture. As you can see in the image, it is not totally "broken", but it looks... different...


I'm not sure if it is a problem only appear on normal textures, but for now, I only notice that on normal textures.

As this issue looks most obvious on far camera, in which the game will load a mipmap of the texture. I suspect if there is some mipmap information lost/distorted during .texture->.dds or during .dds->.texture

Example files:
[https://drive.google.com/file/d/1ZGFJrP ... sp=sharing](https://drive.google.com/file/d/1ZGFJrPgGncvBs-bLmVZNZhE5nvfafJUt/view?usp=sharing)
put weapon_shadowfang_nrm.texture in D:\D2R_alpha\Data\hd\items\weapon\sword\shadowfang
put Assassin.d2s in C:\Users\[your name]\Saved Games\Diablo II Resurrected Tech Alpha

Edit:
another test on weapon_claymore_nrm.texture, more obvious
## Post #221
- Username: Rushster
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 08, 2021 9:55 pm
- Post datetime: 2021-05-08T17:12:41+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Awesome work guys. Got this working today but I have a question.

In the D2R folders where there are multiple model files such as "special", "legs", "arm" etc. How do you combine these to make a complete model in the viewer and then apply the animation?

Thanks in advance.
## Post #222
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-08T18:23:54+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ivenend ↑Fri May 07, 2021 11:27 pm at Fri May 07, 2021 11:27 pm
>
> 
@jayn23

Sorry to bother you again, but it seems that the plugin may have some small problem on normal (_nrm) textures.

Here is a test, I convert the weapon_shadowfang_nrm.texture to dds, without edit and convert back to .texture. As you can see in the image, it is not totally "broken", but it looks... different...


I'm not sure if it is a problem only appear on normal textures, but for now, I only notice that on normal textures.

As this issue looks most obvious on far camera, in which the game will load a mipmap of the texture. I suspect if there is some mipmap information lost/distorted during .texture->.dds or during .dds->.texture

Answered you on Discord

> Reply from Rushster ↑Sun May 09, 2021 1:12 am at Sun May 09, 2021 1:12 am
>
> 
Awesome work guys. Got this working today but I have a question.

In the D2R folders where there are multiple model files such as "special", "legs", "arm" etc. How do you combine these to make a complete model in the viewer and then apply the animation?

Thanks in advance.

Yes you can use MULTIFILE option and paired animtion option to get it working.
In the 1.3 version release i showed an example how to do this with BG3, its the exact same thing here..
## Post #223
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-08T19:21:47+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Another samll update to script - as usual for past releases i did not do much  testing so if anything used to work and now dosent let me know..

Version 1.32

Added Auto Texturing support for Silent Hunter 5: Battle of the Atlantic.
Textures must be in the same directory of .gr2 file.
Diffuse,AO and Normal maps are loaded.
GAME_TAG_SH5 - should be enabled

New Option:
CRC_CORRECTION - if turned on and file CRC does not match calculated CRC script will overwrite file.
Depending on file location you might have to load noesis with Admin privleges to get working. 
At least for first few files you do this i would recommend backing them up just incase.. 

Added new options based on Built In Noesis functions:
MESH_OPTIMIZE - Optmize mesh, remove duplictae vertcies etc..
S_NORMALS - Smooth Normals, can be used if you think Normals arent being loaded correctly.

Replaceing crashing with those ununderstandable errors, added messages letting you know whats wrong, script will end once message is displayed.  

Granny2.dll is ot found 


Bitknit compression not supported
## Post #224
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-08T19:49:48+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Nice! 
Will test!
## Post #225
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-09T17:45:00+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

My hat is off to Master jayn23!


There was an issue with the SH5 animations and skip mesh.
jayn23 fixed that! Fantastic work Mate!
## Post #226
- Username: vssrc
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 20, 2020 1:54 pm
- Post datetime: 2021-05-10T06:43:03+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

hey everyone, I'm on noesisv4442, GR2reader132 and granny2.dll 2.11.8.0 (from link on page5, copied to root noesis folder). 

Attempting to open a .model file asks for the animation file and then throws the Cant locate granny2.dll error. Any suggestions on getting this to work? Thanks!
## Post #227
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-10T06:59:20+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from vssrc ↑Mon May 10, 2021 2:43 pm at Mon May 10, 2021 2:43 pm
>
> 
hey everyone, I'm on noesisv4442, GR2reader132 and granny2.dll 2.11.8.0 (from link on page5, copied to root noesis folder). 

Attempting to open a .model file asks for the animation file and then throws the Cant locate granny2.dll error. Any suggestions on getting this to work? Thanks!

you need to place it in the main folder where noesis.exe is

edit:
sorry i see you said its already in root directory, try one of the older versions  see if they work
## Post #228
- Username: vssrc
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 20, 2020 1:54 pm
- Post datetime: 2021-05-10T07:44:07+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

@jayn23 : Thanks, it would be great if someone could share a granny2.dll that is confirmed to be working. the page 5 one unfortunately isn't working in combination with the versions of noesis/GR2 reader plugin I mentioned.
## Post #229
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-10T09:30:49+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from vssrc ↑Mon May 10, 2021 3:44 pm at Mon May 10, 2021 3:44 pm
>
> 
@jayn23 : Thanks, it would be great if someone could share a granny2.dll that is confirmed to be working. the page 5 one unfortunately isn't working in combination with the versions of noesis/GR2 reader plugin I mentioned.

The one on page 5 should work, did you try an earlier version 1.3? or even 1.2 from first page just to see if it works?
make sure you delete the current script before putting in the 1.2 or 1.3
## Post #230
- Username: vssrc
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 20, 2020 1:54 pm
- Post datetime: 2021-05-10T10:15:06+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Mon May 10, 2021 5:30 pm at Mon May 10, 2021 5:30 pm
>
> 
vssrc wrote: ↑Mon May 10, 2021 3:44 pm
@jayn23 : Thanks, it would be great if someone could share a granny2.dll that is confirmed to be working. the page 5 one unfortunately isn't working in combination with the versions of noesis/GR2 reader plugin I mentioned.


The one on page 5 should work, did you try an earlier version 1.3? or even 1.2 from first page just to see if it works?
make sure you delete the current script before putting in the 1.2 or 1.3

Thanks so much, that did it. I went back to 1.31 and no issues now. Cheers
## Post #231
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-10T11:03:17+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from vssrc ↑Mon May 10, 2021 6:15 pm at Mon May 10, 2021 6:15 pm
>
> 
jayn23 wrote: ↑Mon May 10, 2021 5:30 pm
vssrc wrote: ↑Mon May 10, 2021 3:44 pm
@jayn23 : Thanks, it would be great if someone could share a granny2.dll that is confirmed to be working. the page 5 one unfortunately isn't working in combination with the versions of noesis/GR2 reader plugin I mentioned.


The one on page 5 should work, did you try an earlier version 1.3? or even 1.2 from first page just to see if it works?
make sure you delete the current script before putting in the 1.2 or 1.3


Thanks so much, that did it. I went back to 1.31 and no issues now. Cheers

Now i need to check why 1.32 isnt working
## Post #232
- Username: ahmet123
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 14, 2021 4:07 pm
- Post datetime: 2021-05-10T14:36:11+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

first of all thank you for creating this reader. i really appreciate it.

but i cant export singe file metin2 animations, which settings do i need to turn on?
and exported metin2 files are sideways (90 degree on Z)

thank you
## Post #233
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-10T16:27:28+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from ahmet123 ↑Mon May 10, 2021 10:36 pm at Mon May 10, 2021 10:36 pm
>
> 
first of all thank you for creating this reader. i really appreciate it.

but i cant export singe file metin2 animations, which settings do i need to turn on?
and exported metin2 files are sideways (90 degree on Z)

thank you

if i remember correctly metin2 animation files dont contain mesh or skeleton so there is nothing to export.
to export an animation you need at the very least to load a skeleton with the animation then you can export to FBX or DAE.

regrding the exported position, every game does it differently, and currently my script dosent identify initial position, maybe i can add that in a future update
## Post #234
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-10T19:10:57+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

When exporting with FBX or DAE you can select the rotate 90 degree option.
Some Games use a Z up, others use a Y up.
## Post #235
- Username: ahmet123
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 14, 2021 4:07 pm
- Post datetime: 2021-05-10T20:36:45+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

when i select the rotate 90 degree option it makes character upside down.

and i guess i found a bug.
 in this animation assassins feets are stable and body moving but when loaded or exported, feets are starting to move.

files:
[https://www.mediafire.com/file/ayvasn9l ... n.zip/file](https://www.mediafire.com/file/ayvasn9ludufe2x/assassin.zip/file)
## Post #236
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-11T18:00:17+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Mon May 10, 2021 7:03 pm at Mon May 10, 2021 7:03 pm
>
> 
Now i need to check why 1.32 isnt working

It's something with the try: you placed on the decompress in 132?
Debug gives me no feed back.

On how the meshes are stored in a GR2?
Look at ArtToolinfo
UpVector, BackVector, RightVector.

Now the GrannyViewer always shows a model in a proper orientation based on that information is my opinion.
Export the meshes? They are as saved in the GR2 which does not match the Vectors in some cases.
## Post #237
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-11T21:41:36+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Wed May 12, 2021 2:00 am at Wed May 12, 2021 2:00 am
>
> 
jayn23 wrote: ↑Mon May 10, 2021 7:03 pm
Now i need to check why 1.32 isnt working  


It's something with the try: you placed on the decompress in 132?
Debug gives me no feed back.

On how the meshes are stored in a GR2?
Look at ArtToolinfo
UpVector, BackVector, RightVector.

Now the GrannyViewer always shows a model in a proper orientation based on that information is my opinion.
Export the meshes? They are as saved in the GR2 which does not match the Vectors in some cases.

Maybe you can help me,

i started working at auto orintation based on art tool info data, i create a matrix from UpVector, BackVector, RightVector and multiply the first bone of the skeleton - that fixes the skeleton orintation, i use the same matrix for mesh - which fixes the mesh orintation but for some reason normals get inverted now.
so i used a wind command noesis has and that fixes it until i apply an animation then normals are flipped again no matter what i do..

i am i doing the transformation wrong? why are the normals fliping
## Post #238
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-12T16:41:29+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Sent you a PM.
## Post #239
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-12T21:11:50+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from ahmet123 ↑Tue May 11, 2021 4:36 am at Tue May 11, 2021 4:36 am
>
> 
and i guess i found a bug.
 in this animation assassins feets are stable and body moving but when loaded or exported, feets are starting to move.
That's the animation itself as in the wait.gr2 file.

I've done a few tests and the adjusted files don't have that side to side sway.
Can you provide a different animation for this model?
## Post #240
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-12T21:16:03+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Thu May 13, 2021 5:11 am at Thu May 13, 2021 5:11 am
>
> 
ahmet123 wrote: ↑Tue May 11, 2021 4:36 am
and i guess i found a bug.
 in this animation assassins feets are stable and body moving but when loaded or exported, feets are starting to move.

That's the animation itself as in the wait.gr2 file.

I've done a few tests and the adjusted files don't have that side to side sway.
Can you provide a different animation for this model?

what adjustements did you do to the file?
## Post #241
- Username: ahmet123
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 14, 2021 4:07 pm
- Post datetime: 2021-05-12T22:23:40+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Thu May 13, 2021 5:11 am at Thu May 13, 2021 5:11 am
>
> 
ahmet123 wrote: ↑Tue May 11, 2021 4:36 am
and i guess i found a bug.
 in this animation assassins feets are stable and body moving but when loaded or exported, feets are starting to move.

That's the animation itself as in the wait.gr2 file.

I've done a few tests and the adjusted files don't have that side to side sway.
Can you provide a different animation for this model?

here you go
[https://www.mediafire.com/file/58wqjerq ... y.zip/file](https://www.mediafire.com/file/58wqjerqr0k3cmp/asas_sway.zip/file)
and thanks for helping
## Post #242
- Username: Rushster
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 08, 2021 9:55 pm
- Post datetime: 2021-05-12T23:30:25+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Was there a final fix for the 1.3.2 missing granny.dll file issue?
## Post #243
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-13T09:55:43+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Rushster ↑Thu May 13, 2021 7:30 am at Thu May 13, 2021 7:30 am
>
> 
Was there a final fix for the 1.3.2 missing granny.dll file issue?

I havent released it yet, just download 1.31 for now, for some reason sometimes its dosent look in the root direcory as it should so next update i explictly give the script noesis main path.
## Post #244
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-13T23:53:17+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Thu May 13, 2021 5:55 pm at Thu May 13, 2021 5:55 pm
>
> 
I havent released it yet, just download 1.31 for now, for some reason sometimes its dosent look in the root direcory as it should so next update i explictly give the script noesis main path.
That's what I did to a copy to solve the problem.
## Post #245
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-05-17T17:54:06+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Going to give a Big Thank You for your script again.
Now my Goal is to convert the SH5 animations to the SH4 way of doing animations.
So far, as I learn enough Python to be dangerous, I'm zeroing in on how to get the data I want.

Thank You again Mate!
## Post #246
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2021-05-20T13:20:44+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

How i can unpack Diablo 2 resurrected data.XXX files? What tools?
Thanks.

answer:
Casc Viever
## Post #247
- Username: okami29
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Mar 09, 2017 8:57 pm
- Post datetime: 2021-05-21T19:10:03+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

So the Noesis plugin works fine for D2R to see and export models and animations.
However when importing animations for Tyrael with ANIMATION_MODE = 1 (data\hd\character\npc\tyrael1\animation) there is only 1 frame and the character doesn't move.
I tried changing ANIMATION_TRACK to 1 or 2 but it doesn't change.
It seems the animation is supposed to affect bothe the model and the wings but nothing happens.
## Post #248
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-22T18:20:10+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from okami29 ↑Sat May 22, 2021 3:10 am at Sat May 22, 2021 3:10 am
>
> 
So the Noesis plugin works fine for D2R to see and export models and animations.
However when importing animations for Tyrael with ANIMATION_MODE = 1 (data\hd\character\npc\tyrael1\animation) there is only 1 frame and the character doesn't move.
I tried changing ANIMATION_TRACK to 1 or 2 but it doesn't change.
It seems the animation is supposed to affect bothe the model and the wings but nothing happens.

Normaly its best to upload samples   
but luckly i already have the files for this, i checked them out and i suspect they are simply not ready as they have almost no track data.
## Post #249
- Username: okami29
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Mar 09, 2017 8:57 pm
- Post datetime: 2021-05-22T20:46:44+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Sun May 23, 2021 2:20 am at Sun May 23, 2021 2:20 am
>
> 
Normaly its best to upload samples   
but luckly i already have the files for this, i checked them out and i suspect they are simply not ready as they have almost no track data.
That's strange because in game he is moving and his wings are also moving so the animations exist (at the end of this video for example : [https://youtu.be/GmVrBTDPB0s?t=15493](https://youtu.be/GmVrBTDPB0s?t=15493)).
## Post #250
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-22T21:48:08+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from okami29 ↑Sun May 23, 2021 4:46 am at Sun May 23, 2021 4:46 am
>
> 
jayn23 wrote: ↑Sun May 23, 2021 2:20 am
Normaly its best to upload samples   
but luckly i already have the files for this, i checked them out and i suspect they are simply not ready as they have almost no track data.

That's strange because in game he is moving and his wings are also moving so the animations exist (at the end of this video for example : https://youtu.be/GmVrBTDPB0s?t=15493).

Ok i stand corrected, i was looking at neutral animation, it has 4 different tracks, Torso, wings,mesh_main and root i looke at the first 3 which have almost 0 data, but the root track has alot of data, still not sure why its not working ill take a look at it.
## Post #251
- Username: ahmet123
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 14, 2021 4:07 pm
- Post datetime: 2021-05-24T09:14:06+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

hey any news on swaying bug that i mentioned earliler?
and are there any links that we can support you for your contributions to this community?
## Post #252
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-24T09:35:31+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from ahmet123 ↑Mon May 24, 2021 5:14 pm at Mon May 24, 2021 5:14 pm
>
> 
hey any news on swaying bug that i mentioned earliler?
and are there any links that we can support you for your contributions to this community?

I fixed the bug that was causing it, still working on some other features before a new update is released..
And no links but Thanks anyway
## Post #253
- Username: ahmet123
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 14, 2021 4:07 pm
- Post datetime: 2021-05-25T14:51:58+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

hey good news! or bad if you hate bugs... i found a new bug.
seems to be about left and sticking out things

i selected slow animations for you to clearly see.

[https://www.mediafire.com/folder/w1b0xa ... mation_bug](https://www.mediafire.com/folder/w1b0xa0yfv51i/animation_bug)

i hope it helps you and solves problems not only in metin2 but also in other games too
thanks for looking into it
## Post #254
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-25T19:37:05+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from ahmet123 ↑Tue May 25, 2021 10:51 pm at Tue May 25, 2021 10:51 pm
>
> 
hey good news! or bad if you hate bugs... i found a new bug.
seems to be about left and sticking out things

i selected slow animations for you to clearly see.

https://www.mediafire.com/folder/w1b0xa ... mation_bug

i hope it helps you and solves problems not only in metin2 but also in other games too
thanks for looking into it

I have actually encountered this bug in the past where only left side of animation is acting strange, but i never managed to find the bug,
These are files with uncompressed quaternions and knots, maybe someone else can take a look...
## Post #255
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2021-05-31T11:52:42+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

[](https://gifyu.com/image/ozDM)

My two cents 
Noesis Script for D2R UI files (* .sprite)
Icons for weapons, armor, spells, panels, etc. from here
data \ data \ hd \ global \ ui
[fmt_D2R_sprite.7z](https://xentaxbackup.github.io/file/20233_fmt_D2R_sprite.7z)
## Post #256
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-31T13:56:20+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from erik945 ↑Mon May 31, 2021 7:52 pm at Mon May 31, 2021 7:52 pm
>
> 


My two cents 
Noesis Script for D2R UI files (* .sprite)
Icons for weapons, armor, spells, panels, etc. from here
data \ data \ hd \ global \ ui

Very cool,

This remindes me i need to release an uodated version for the .texture script..
## Post #257
- Username: MorgothZeONE
- Rank: advanced
- Number of posts: 51
- Joined date: Tue May 24, 2016 7:59 am
- Post datetime: 2021-05-31T15:20:58+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

i tried using this tool for Carnivores Reborn .GR2 files, but i keep getting an error, and looking into it i found that Carnivores .GR2 files are marked as "Big Endian format" where as this tool only supports the "Little Endian format"

here's some .GR2's from the game for you to test on [https://drive.google.com/file/d/1nRltcs ... Qfw3q/view](https://drive.google.com/file/d/1nRltcseTI9WCc-J1SeuKU9I1WfhQfw3q/view)
## Post #258
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-31T15:28:09+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from MorgothZeONE ↑Mon May 31, 2021 11:20 pm at Mon May 31, 2021 11:20 pm
>
> 
i tried using this tool for Carnivores Reborn .GR2 files, but i keep getting an error, and looking into it i found that Carnivores .GR2 files are marked as "Big Endian format" where as this tool only supports the "Little Endian format"

here's some .GR2's from the game for you to test on https://drive.google.com/file/d/1nRltcs ... Qfw3q/view

Actually my script supports Big Endian format and all the samples i tried worked for me, many of them just contain animation without model/mesh data so they might seem not to work.
## Post #259
- Username: MorgothZeONE
- Rank: advanced
- Number of posts: 51
- Joined date: Tue May 24, 2016 7:59 am
- Post datetime: 2021-05-31T19:42:48+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

huh odd, i guess i may be doing something wrong on my end i suppose causing the error
## Post #260
- Username: MorgothZeONE
- Rank: advanced
- Number of posts: 51
- Joined date: Tue May 24, 2016 7:59 am
- Post datetime: 2021-05-31T20:07:59+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Mon May 31, 2021 11:28 pm at Mon May 31, 2021 11:28 pm
>
> 
MorgothZeONE wrote: ↑Mon May 31, 2021 11:20 pm
i tried using this tool for Carnivores Reborn .GR2 files, but i keep getting an error, and looking into it i found that Carnivores .GR2 files are marked as "Big Endian format" where as this tool only supports the "Little Endian format"

here's some .GR2's from the game for you to test on https://drive.google.com/file/d/1nRltcs ... Qfw3q/view


Actually my script supports Big Endian format and all the samples i tried worked for me, many of them just contain animation without model/mesh data so they might seem not to work.

i definatly feel like i'm doing something wrong, i'm using the most recent version of noesis so maybe that's also causing an issue but i can't be too sure
## Post #261
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-05-31T21:28:36+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from MorgothZeONE ↑Tue Jun 01, 2021 4:07 am at Tue Jun 01, 2021 4:07 am
>
> 
jayn23 wrote: ↑Mon May 31, 2021 11:28 pm
MorgothZeONE wrote: ↑Mon May 31, 2021 11:20 pm
i tried using this tool for Carnivores Reborn .GR2 files, but i keep getting an error, and looking into it i found that Carnivores .GR2 files are marked as "Big Endian format" where as this tool only supports the "Little Endian format"

here's some .GR2's from the game for you to test on https://drive.google.com/file/d/1nRltcs ... Qfw3q/view


Actually my script supports Big Endian format and all the samples i tried worked for me, many of them just contain animation without model/mesh data so they might seem not to work.


i definatly feel like i'm doing something wrong, i'm using the most recent version of noesis so maybe that's also causing an issue but i can't be too sure

This error means its not finding the granny2.dll file.
Make sure its in the noesis main folder
## Post #262
- Username: MorgothZeONE
- Rank: advanced
- Number of posts: 51
- Joined date: Tue May 24, 2016 7:59 am
- Post datetime: 2021-05-31T22:40:44+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

that worked (and i feel stupid for putting the .dll in the plugins folder [insert facepalm gif here])

thanks
## Post #263
- Username: zelibobo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 30, 2019 8:32 pm
- Post datetime: 2021-06-04T10:16:18+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from erik945 ↑Mon May 31, 2021 7:52 pm at Mon May 31, 2021 7:52 pm
>
> 


My two cents 
Noesis Script for D2R UI files (* .sprite)
Icons for weapons, armor, spells, panels, etc. from here
data \ data \ hd \ global \ ui
data \ data \ hd \ global \ ui \ loading \ *.*
I can not see the files.
## Post #264
- Username: Test2007
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 19, 2018 3:33 am
- Post datetime: 2021-06-06T12:20:19+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hello!Files from Hellgate:London have extension .am and .wm but in xml written .gr2
Example [https://drive.google.com/file/d/1qd_Fbm ... sp=sharing](https://drive.google.com/file/d/1qd_FbmzVVfx7t7lFC6zTNVsimP_JqAMT/view?usp=sharing)
## Post #265
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-06-06T15:42:57+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

The .am file points to
data\units\items\weapons\agitator\agitator_mesh.gr2

Sure you have the right files?
## Post #266
- Username: Test2007
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 19, 2018 3:33 am
- Post datetime: 2021-06-06T19:17:16+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Sun Jun 06, 2021 11:42 pm at Sun Jun 06, 2021 11:42 pm
>
> 
The .am file points to
data\units\items\weapons\agitator\agitator_mesh.gr2

Sure you have the right files?

Hellgate gamearchive dont have .gr2 format,I think .am and .wm 
its archived or compressed .gr2
## Post #267
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-06-06T21:02:42+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Test2007 ↑Mon Jun 07, 2021 3:17 am at Mon Jun 07, 2021 3:17 am
>
> 
05SpeedMaster wrote: ↑Sun Jun 06, 2021 11:42 pm
The .am file points to
data\units\items\weapons\agitator\agitator_mesh.gr2

Sure you have the right files?


Hellgate gamearchive dont have .gr2 format,I think .am and .wm 
its archived or compressed .gr2

iv never seen Havok and granny files togther so thats you first sign  

its not a granny file, dosent look like one at all, plus its a really easy format i already manually loaded the mesh.
open a thread about it, i am sure someone will help.
## Post #268
- Username: andrew21022
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 11, 2019 3:23 am
- Post datetime: 2021-06-08T07:22:56+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

hello,sir,im trying to was trying to get those models from diablo2 resurrected but stuck with this error,can't figure out the next steps to solve it [[https://sun9-11.userapi.com/impg/EHRmny ... type=album](https://sun9-11.userapi.com/impg/EHRmnyGsuHsvI0h7XCS5GiLiuoxTuN48pRCRvg/635DCk_7EoY.jpg?size=410x389&quality=96&sign=0e5f6ed1afb6f01de336a1bf51fbc0e8&type=album)]
## Post #269
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-06-08T07:36:48+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from andrew21022 ↑Tue Jun 08, 2021 3:22 pm at Tue Jun 08, 2021 3:22 pm
>
> 
hello,sir,im trying to was trying to get those models from diablo2 resurrected but stuck with this error,can't figure out the next steps to solve it [https://sun9-11.userapi.com/impg/EHRmny ... type=album]

the granny2.dll version you are using is to old and dosent support bitknit compression , there is a link somewhere in this thread to a newer version that does
## Post #270
- Username: andrew21022
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 11, 2019 3:23 am
- Post datetime: 2021-06-08T18:36:51+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

im using granny.dll 2.11.8  and still getting the same error (with plugin fmt_GR2reader132.py it looks like [[https://s3.gifyu.com/images/ezgif.com-g ... ad9d6c.gif](https://s3.gifyu.com/images/ezgif.com-gif-maker22a9e4f61aad9d6c.gif)][[https://sun9-15.userapi.com/impg/NnUJKI ... type=album](https://sun9-15.userapi.com/impg/NnUJKIZDJj29GidxU55idXiUaSq6FPW045yvKA/oMXczQvYlkc.jpg?size=762x341&quality=96&sign=46a4c5ad71e61b321daf14536336683b&type=album)]
## Post #271
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-06-08T21:27:26+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

My granny2.dll only shows as 657 KB
Your granny2.dll shows 785 KB

Something is off.
## Post #272
- Username: andrew21022
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 11, 2019 3:23 am
- Post datetime: 2021-06-10T06:25:33+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

[[https://sun9-24.userapi.com/impg/G6QDZQ ... type=album](https://sun9-24.userapi.com/impg/G6QDZQG9NG9HE8aYch7wMdAeNFt8gm1c8HtcuA/TyJD0fXrAd0.jpg?size=2040x859&quality=96&sign=21e614b6f15d0c9ce6f6815016a7c19f&type=album)] keep getting same issue even with granny2.dll v2.11.8 and fmt_GR2reader131
## Post #273
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-06-10T18:10:31+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from andrew21022 ↑Thu Jun 10, 2021 2:25 pm at Thu Jun 10, 2021 2:25 pm
>
> 
[https://sun9-24.userapi.com/impg/G6QDZQ ... type=album] keep getting same issue even with granny2.dll v2.11.8 and fmt_GR2reader131

This error looks like a invalid win32 application, i guess your using 64 bit version of noesis, but the granny2.dll is 32 bit.
try using 32 bit executable.
## Post #274
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-06-11T00:17:29+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

For my purposes the 64 bit version works fine even with the 32 bit granny2.dll
I don't have his game files to test though.
## Post #275
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-06-11T00:41:04+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Go to line 49 in the 131 plug in and enable debug.
        #noesis.logPopup()

Change that to 
        noesis.logPopup()
## Post #276
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-06-11T08:16:15+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Fri Jun 11, 2021 8:17 am at Fri Jun 11, 2021 8:17 am
>
> 
For my purposes the 64 bit version works fine even with the 32 bit granny2.dll
I don't have his game files to test though.

Well thats because Silent Hunter 5 Uses uncompressed granny files, so your not using the .dll
## Post #277
- Username: Ace94
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 11, 2020 4:32 am
- Post datetime: 2021-06-13T04:17:40+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Any idea how I can get the diffuse textures for Baldurs Gate 3 for the companions? There isn't any when I extracted the texture.pak
## Post #278
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-06-13T04:52:45+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ace94 ↑Sun Jun 13, 2021 12:17 pm at Sun Jun 13, 2021 12:17 pm
>
> 
Any idea how I can get the diffuse textures for Baldurs Gate 3 for the companions? There isn't any when I extracted the texture.pak

Hi,

To the best of my knowlage companions dont use BM maps. instead they use CLEA and HMVY maps.
Based on data from BG3 Discord:

MSK Maps:
R - Cavity or pores
G - Eyebrows/beard mask
B - Lips/gloss mask 
A - AO

CLEA Maps:
R - Hemoglobin 
G - Melаnin
B - Vein
A - Yellowing
## Post #279
- Username: Ace94
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 11, 2020 4:32 am
- Post datetime: 2021-06-13T06:52:14+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Sun Jun 13, 2021 12:52 pm at Sun Jun 13, 2021 12:52 pm
>
> 
Ace94 wrote: ↑Sun Jun 13, 2021 12:17 pm
Any idea how I can get the diffuse textures for Baldurs Gate 3 for the companions? There isn't any when I extracted the texture.pak


Hi,

To the best of my knowlage companions dont use BM maps. instead they use CLEA and HMVY maps.
Based on data from BG3 Discord:

MSK Maps:
R - Cavity or pores
G - Eyebrows/beard mask
B - Lips/gloss mask 
A - AO

CLEA Maps:
R - Hemoglobin 
G - Melаnin
B - Vein
A - Yellowing
Thank you for the reply. I am a newb, so I don't really know how to use the CLEA and MSK maps properly in Blender to show off the normal skin/face textures.
## Post #280
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-06-13T08:10:30+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ace94 ↑Sun Jun 13, 2021 2:52 pm at Sun Jun 13, 2021 2:52 pm
>
> 
Thank you for the reply. I am a newb, so I don't really know how to use the CLEA and MSK maps properly in Blender to show off the normal skin/face textures.

I dont use blender so cant help you with that,
[https://discord.com/channels/9892218274 ... 8819477515](https://discord.com/channels/98922182746329088/767804218819477515) -BG3 modding Discord, can probably help you
## Post #281
- Username: RechtUndUnordnung
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 14, 2021 2:09 am
- Post datetime: 2021-06-13T19:38:20+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hey   
first of all: Thanks jayn for this amazing tool. I've been searching something like this for years now to convert gr2 into fbx easily to be able to play with it in Unity, Blender and similar - and finally found this here. It's simply amazing!

I now attempted loading / converting some Metin2 gr2 models and animations as I still had them lying around and it works just fine in majority of the cases. I just noticed something slightly weird with some of the animations. Without any knowledge on how animations actually work, I would describe the problem as if "the animation would use the wrong fixed/origin point".

Here is two gifs, one from Noesis, one from gr2 viewer.
noesis: [https://i.epvpimg.com/piyagab.gif](https://i.epvpimg.com/piyagab.gif) (ignore the missing textures)
gr2 viewer: [http://epvpimg.com/PkV3aab](http://epvpimg.com/PkV3aab)

You can see that in the noesis version, it kinda looks like the character is tied up on is head, which remains more or less fixed, and its feet are dangling around where in the original version (gr2 viewer), the feet are fixed to the ground, don't move and the rest of the body moves in relation to that.

Any idea what the issue here might be and how difficult it would be to fix that?

Cheers - and again, thanks a lot for everything that has been done so far on this tool and what you will still do in the future 

Edit; Shame on me for not reading the rest of the thread. It seems like others have asked this question before - but I don’t really understand the conclusion you came to. If there is no fix yet, can you roughly point me to what functionality is responsible for loading this / what would potentially messing that up?
## Post #282
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-06-14T06:42:37+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from RechtUndUnordnung ↑Mon Jun 14, 2021 3:38 am at Mon Jun 14, 2021 3:38 am
>
> 
Hey   
first of all: Thanks jayn for this amazing tool. I've been searching something like this for years now to convert gr2 into fbx easily to be able to play with it in Unity, Blender and similar - and finally found this here. It's simply amazing!

I now attempted loading / converting some Metin2 gr2 models and animations as I still had them lying around and it works just fine in majority of the cases. I just noticed something slightly weird with some of the animations. Without any knowledge on how animations actually work, I would describe the problem as if "the animation would use the wrong fixed/origin point".

Here is two gifs, one from Noesis, one from gr2 viewer.
noesis: https://i.epvpimg.com/piyagab.gif (ignore the missing textures)
gr2 viewer: http://epvpimg.com/PkV3aab

You can see that in the noesis version, it kinda looks like the character is tied up on is head, which remains more or less fixed, and its feet are dangling around where in the original version (gr2 viewer), the feet are fixed to the ground, don't move and the rest of the body moves in relation to that.

Any idea what the issue here might be and how difficult it would be to fix that?

Cheers - and again, thanks a lot for everything that has been done so far on this tool and what you will still do in the future 

Edit; Shame on me for not reading the rest of the thread. It seems like others have asked this question before - but I don’t really understand the conclusion you came to. If there is no fix yet, can you roughly point me to what functionality is responsible for loading this / what would potentially messing that up?

Happy to see my script being used more and more   
regarding that floating bug, i already fixed it - new update should be realsing soon, animation still isnt perfect tho, i have some bugs i have been unable to fix unfoutanatly.
## Post #283
- Username: RechtUndUnordnung
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 14, 2021 2:09 am
- Post datetime: 2021-06-14T09:21:59+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Wow. Thanks a lot, that’s pretty amazing. Looking forward to the new version then.  if there is anything that can be done to contribute to your work, share it pls.
## Post #284
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-06-15T18:27:56+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I have a new update for you, one i am pretty proud of   
This has alot of firsts for me, first time using Ghidra and decompiled code from source, debugging Aseembly code and generaly just alot of research.
To the best of my knowlage this is the first script that can now decompress BINK format along with many other new features.

Change List:

1. Added Auto Texturing for all .gr2 files with embeded textures including the following formats : RGBA32, DXT1/3/5 and BINK. so now games like Winter X-Games: Snocross can directly load/export textures from noesis without any 3rd party ripping tools.
Currebtly Turned on by Deafult, can be disabled with the following Option.
GAME_TAG_GRANNY = True

2. new option, allows to transform any loaded file to any coordinate system and UnitsPerMeter of your choosing, 
Currently by default all files are converted to native noesis coordinate  system where meshes will always be facing forward.
just an example of usefulness, if by some mistake a mesh and animation file where created in a different system the script will automaticly transform both to same system and allow for animation to work correctly with the mesh.
or if your exporting for a specific game in a different system you can easily adjust before exporting.

TRANSFORM_FILE

RightVector =   [1,0,0]
UpVector =       [0,1,0]
BackVector =    [0,0,1]
UnitsPerMeter_new = 1.0

3. Adedd support for 64 bit Noesis- script will automatically recognize which system you are using and search for a compatible .dll file.
for 32 bit - granny2.dll
for 64 bit - granny2_x64.dll

4. Added QTangent Support for Baldur Gate 3.

5. Enabled Tangents in Script.

6. Fixed a bug with Old Animation to New format conversion function - should fix those floaty issues.

7. Added Initial Placement for Animation - while playining animations models will now load in the correct position in relation to world and other models of a scene.

8. Added absolute path to Noesis Main Folder for Granny2.dll and Mesh.txt files - should always look in correct path now.

9. Rewrote some code and memory optimzations on multiple functions.

10. Added some debug options, i dont expect almost anyone to use but why not right...
DISABLE_ALPHA  - Disables Alpha blending when loading textures usefull for some games where alpha causes mesh to be transparent
LOAD_POINT_CLOUD  - Load only mesh Vertcies.
DEBUG_NORMALS - Load Normals as colors.









 fmt_GR2reader135.rar
(31.56 KiB) Downloaded 1795 times
## Post #285
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-06-15T21:39:38+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Wed Jun 16, 2021 2:27 am at Wed Jun 16, 2021 2:27 am
>
> 
...
3. Adedd support for 64 bit Noesis- script will automatically recognize which system you are using and search for a compatible .dll file.
for 32 bit - granny2.dll
for 64 bit - granny2_x64.dll
...
I have never seen granny2 64-bit dll, care to name a game or two that has it?
## Post #286
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-06-15T21:42:19+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from mono24 ↑Wed Jun 16, 2021 5:39 am at Wed Jun 16, 2021 5:39 am
>
> 
jayn23 wrote: ↑Wed Jun 16, 2021 2:27 am
...
3. Adedd support for 64 bit Noesis- script will automatically recognize which system you are using and search for a compatible .dll file.
for 32 bit - granny2.dll
for 64 bit - granny2_x64.dll
...

I have never seen granny2 64-bit dll, care to name a game or two that has it?

i think i got mine from ESO
## Post #287
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-06-16T23:22:37+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from mono24 ↑Wed Jun 16, 2021 5:39 am at Wed Jun 16, 2021 5:39 am
>
> 

I have never seen granny2 64-bit dll, care to name a game or two that has it?
## Post #288
- Username: okami29
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Mar 09, 2017 8:57 pm
- Post datetime: 2021-06-20T14:13:56+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thank you for this new version. Are you still planning to fix the issue with Tyrael wings animations  (or waiting for the full release ) ?
## Post #289
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-06-20T19:17:45+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from okami29 ↑Sun Jun 20, 2021 10:13 pm at Sun Jun 20, 2021 10:13 pm
>
> 
Thank you for this new version. Are you still planning to fix the issue with Tyrael wings animations  (or waiting for the full release ) ?

To be honest totaly forgot about that, since i deleted diablo until full game realeases, please uplaod samples both mesh and animations and  ill take a look
## Post #290
- Username: okami29
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Mar 09, 2017 8:57 pm
- Post datetime: 2021-06-21T06:12:29+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Mon Jun 21, 2021 3:17 am at Mon Jun 21, 2021 3:17 am
>
> 
okami29 wrote: ↑Sun Jun 20, 2021 10:13 pm
Thank you for this new version. Are you still planning to fix the issue with Tyrael wings animations  (or waiting for the full release ) ?


To be honest totaly forgot about that, since i deleted diablo until full game realeases, please uplaod samples both mesh and animations and  ill take a look
Here
[Link](https://mega.nz/file/d19yUIoB#wTj5cSAkEG4R1fLzTgxKe1RCs1kVFE8Kj0uCmATcpg8)
## Post #291
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-06-21T08:35:55+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from okami29 ↑Mon Jun 21, 2021 2:12 pm at Mon Jun 21, 2021 2:12 pm
>
> 
jayn23 wrote: ↑Mon Jun 21, 2021 3:17 am
okami29 wrote: ↑Sun Jun 20, 2021 10:13 pm
Thank you for this new version. Are you still planning to fix the issue with Tyrael wings animations  (or waiting for the full release ) ?


To be honest totaly forgot about that, since i deleted diablo until full game realeases, please uplaod samples both mesh and animations and  ill take a look

Here
Link

Well it does work 
 the skeleton embedded with the mesh file dosent work with the animation correctly , but the independent skeleton file does.
Just use the SKELETON_LOAD option to load the skeleton with the animatiom track set to 3, the other tracks are empty (just contain a static pose)
if you want to load it with mesh like i did, use MULTIFILE = 2 to merge meshes.
## Post #292
- Username: okami29
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Mar 09, 2017 8:57 pm
- Post datetime: 2021-06-21T15:36:32+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

ty
## Post #293
- Username: chachachat
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 22, 2017 10:56 pm
- Post datetime: 2021-06-22T15:54:23+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from okami29 ↑Mon Jun 21, 2021 2:12 pm at Mon Jun 21, 2021 2:12 pm
>
> 
jayn23 wrote: ↑Mon Jun 21, 2021 3:17 am
okami29 wrote: ↑Sun Jun 20, 2021 10:13 pm
Thank you for this new version. Are you still planning to fix the issue with Tyrael wings animations  (or waiting for the full release ) ?


To be honest totaly forgot about that, since i deleted diablo until full game realeases, please uplaod samples both mesh and animations and  ill take a look

Here
Link

Dead link
## Post #294
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2021-06-29T09:02:52+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Can you try this model? D2R, iron golem.
[https://www.dropbox.com/s/o2u3vyjxvv1br ... em.7z?dl=0](https://www.dropbox.com/s/o2u3vyjxvv1brj2/irongolem.7z?dl=0)

```
  File "E:\noesisv4442\plugins\python\fmt_GR2reader135.py", line 5210, in noepyLoadModel
    ctx = rapi.rpgCreateContext()
RuntimeError: Hit MAX_CONCURRENT_RPGEO_CONTEXTS!


```

Thank you/
## Post #295
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-06-29T16:09:50+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from erik945 ↑Tue Jun 29, 2021 5:02 pm at Tue Jun 29, 2021 5:02 pm
>
> 
Can you try this model? D2R, iron golem.

Thank you/

its a noesis thing, this error happens when the .gr2 file contains to many unique models, just use the MERGE_SCENE option to combine all models.
## Post #296
- Username: boskee
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 04, 2021 6:55 pm
- Post datetime: 2021-07-04T11:53:26+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hello,

While reading terrain model from Diablo 2 Resurrected using v1.3.5 I ran into this problem:

> Detected file type: GR2 Reader
>
> Traceback (most recent call last):
>
>   File "noesisv4451\plugins\python\fmt_GR2reader135.py", line 5199, in noepyLoadModel
>
>     Models = GR2Reader(data)  
>
>   File "noesisv4451\plugins\python\fmt_GR2reader135.py", line 4327, in GR2Reader
>
>     Models = extractData(StructHeaders)
>
>   File "noesisv4451\plugins\python\fmt_GR2reader135.py", line 3216, in extractData
>
>     for Tex in model.MeshBindings.Mesh.MaterialBindings.Material.Maps:
>
> TypeError: 'dummy_member' object is not iterable

I fixed it by replacing "else:" on line 3213 with the following condition, but I'm sure there's a better way to deal with it

```
    #for mesh with single material
```
## Post #297
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-07-04T12:04:26+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from boskee ↑Sun Jul 04, 2021 7:53 pm at Sun Jul 04, 2021 7:53 pm
>
> 
Hello,

While reading terrain model from Diablo 2 Resurrected using v1.3.5 I ran into this problem:
Detected file type: GR2 Reader
Traceback (most recent call last):
  File "noesisv4451\plugins\python\fmt_GR2reader135.py", line 5199, in noepyLoadModel
    Models = GR2Reader(data)  
  File "noesisv4451\plugins\python\fmt_GR2reader135.py", line 4327, in GR2Reader
    Models = extractData(StructHeaders)
  File "noesisv4451\plugins\python\fmt_GR2reader135.py", line 3216, in extractData
    for Tex in model.MeshBindings.Mesh.MaterialBindings.Material.Maps:
TypeError: 'dummy_member' object is not iterable

I fixed it by replacing "else:" on line 3213 with the following condition, but I'm sure there's a better way to deal with it
Code: Select allelif type(model.MeshBindings[i].Mesh.MaterialBindings.Material.Maps) == list:
    #for mesh with single material

Thanks for sharing,
please upload the sample that gave this error, ill take a look
## Post #298
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2021-07-18T21:11:55+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hi Jayn,

I can't tell you how much I appreciate this tool. 

I notice that the UVs for ESO statics are still strange. They seem to be off in random ways.

I have uploaded a test sample with files for comparison. (model file converted using your tool (with strange UVs), and the same model obtained using Ninja Ripper with the correct UVs for comparison, exported as an OBJ, etc.)  

Side note for anyone trying this: With Ninja Ripper in max you need to tile your textures 32 times in both directions to get correct UVs for ESO statics.  I use UVW Xform modifier.

[https://www.sendspace.com/file/lln8p6](https://www.sendspace.com/file/lln8p6)
## Post #299
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-07-20T09:39:52+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from zardalu ↑Mon Jul 19, 2021 5:11 am at Mon Jul 19, 2021 5:11 am
>
> 
Hi Jayn,

I can't tell you how much I appreciate this tool. 

I notice that the UVs for ESO statics are still strange. They seem to be off in random ways.

I have uploaded a test sample with files for comparison. (model file converted using your tool (with strange UVs), and the same model obtained using Ninja Ripper with the correct UVs for comparison, exported as an OBJ, etc.)  

Side note for anyone trying this: With Ninja Ripper in max you need to tile your textures 32 times in both directions to get correct UVs for ESO statics.  I use UVW Xform modifier.

https://www.sendspace.com/file/lln8p6

Hi,

Sorry for the late response, ill take a look and see if i can figure it out. i am kind a busy with real life for now so it will probably be a few weeks if i can find the issue very quickly. 

can you please upload a different sample idealy with a small amount of meshes and less vertcies, for some reason this file is taking forever to load each time, guess my 6 year old computer is starting to show its age
## Post #300
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2021-07-21T15:48:32+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thanks Jayn,

Here is a batch of smaller files, all related:

[https://www.sendspace.com/file/ws4o9h](https://www.sendspace.com/file/ws4o9h)

Let me know if this helps or if anything else is needed,
## Post #301
- Username: DerTree
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 17, 2019 9:35 pm
- Post datetime: 2021-07-31T00:59:46+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

With your new script, models are way smaller after importing in 3ds max or blender. I found a setting called "UnitsPerMeter_new = 1.0" which could be the problem. Any idea what could be a number that is equal to the size used in the scripts before?
## Post #302
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-07-31T19:09:42+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from DerTree ↑Sat Jul 31, 2021 8:59 am at Sat Jul 31, 2021 8:59 am
>
> 
With your new script, models are way smaller after importing in 3ds max or blender. I found a setting called "UnitsPerMeter_new = 1.0" which could be the problem. Any idea what could be a number that is equal to the size used in the scripts before?

Hi,

most of the time the units per meter parameter is either 1 or 100, you can either disable the Transform feature by setting TRANSFORM_FILE = False
or you could use Granny Viewer to see actuall UnitsPerMeter and set the correct parameter.
when ever i make another update ill add a deafult option that dosent rescale the model.
## Post #303
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-12T22:27:19+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

hi jayn23,

great work! so many games are supported 
unfortunately when I tried it with civ5 leader models the script failed.
can you support this too? or tell me how to convert it if I do something wrong.



Here's the files:
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1ziP7mjXjoAXF11CrYPx5hfNKfkjviBYo?usp=sharing)

edit: units doesn't work too

eidt2:
found that the most updated granny2.dll is from Metin2 (v2.12.0.2)
not sure about granny2_x64.dll tho. the only one I found was in ESO

none of these dll work with Civilization 5 GR2 files
## Post #304
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-08-14T19:28:21+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Tosyk ↑Fri Aug 13, 2021 6:27 am at Fri Aug 13, 2021 6:27 am
>
> 
hi jayn23,

great work! so many games are supported 
unfortunately when I tried it with civ5 leader models the script failed.
can you support this too? or tell me how to convert it if I do something wrong.



Here's the files:
https://drive.google.com/drive/folders/ ... sp=sharing

edit: units doesn't work too

eidt2:
found that the most updated granny2.dll is from Metin2 (v2.12.0.2)
not sure about granny2_x64.dll tho. the only one I found was in ESO

none of these dll work with Civilization 5 GR2 files

Hi,

wired because i remember testing some civ5 units i found online (never owned the game) and they worked, but none of your samples work
ill add it to my list of to do for the next update, but it will take some time probably a few weeks at the very least.
## Post #305
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-14T19:38:22+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Sun Aug 15, 2021 3:28 am at Sun Aug 15, 2021 3:28 am
>
> 
Tosyk wrote: ↑Fri Aug 13, 2021 6:27 am
hi jayn23,

great work! so many games are supported 
unfortunately when I tried it with civ5 leader models the script failed.
can you support this too? or tell me how to convert it if I do something wrong.



Here's the files:
https://drive.google.com/drive/folders/ ... sp=sharing

edit: units doesn't work too

eidt2:
found that the most updated granny2.dll is from Metin2 (v2.12.0.2)
not sure about granny2_x64.dll tho. the only one I found was in ESO

none of these dll work with Civilization 5 GR2 files


Hi,

wired because i remember testing some civ5 units i found online (never owned the game) and they worked, but none of your samples work
ill add it to my list of to do for the next update, but it will take some time probably a few weeks at the very least.thanks man, looking forward for the next update.
btw, can you tell me what granny dll will fit all the games? or, how should I choose the right dll?

p.s.: it's so greate you're step in and supported so many granny model variations, appreciated!
## Post #306
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-08-16T03:56:31+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Tosyk ↑Fri Aug 13, 2021 6:27 am at Fri Aug 13, 2021 6:27 am
>
> 

thanks man, looking forward for the next update.
btw, can you tell me what granny dll will fit all the games? or, how should I choose the right dll?

p.s.: it's so greate you're step in and supported so many granny model variations, appreciated!

I am using granny 2.11.8.0 for 32 and 64 bit
these should work for everything as there have been no major changes to the best of my knowlage

The only thing thats importent is making sure its a .dll with BitKnit compression support, since  that and and texture decompression are the only functions i use the .dll for
## Post #307
- Username: UncleT
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 17, 2021 12:53 am
- Post datetime: 2021-08-16T16:59:12+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hi please can somebody help me I unpacked the game data using cascview tool got the .model files but I can't view them with noises when i enter the folder it's empty can somebody please tell me what's wrong thanks in advance.
## Post #308
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2021-08-18T12:26:03+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

How can i view the animations of Diablo 2 resurrected creature models in 1 scene? I'm not quite sure wich one of these setting needs a 0 or 1..??
MULTIFILE = 0                       
SMART_DETECTION = 0                 
ANIMATION_TRACK = 0               
ANIMATION_MODE = 0                 
SKELETON_LOAD = 0                   
MERGE_SCENE = 1                     
CRC_CORRECTION = 0  

I can get the model to show up but not the bones nor does it play a animation...

So i need to know firstly, the correct settings and then i need to know what i have to load first?
First the model, then if it asks me to Select the folder that containes wanted .GR2 files, should i select the skeleton folder or the animation folder?
Or should I first load the skeleton folder and then if it asks me to Select the folder that containes wanted .GR2 files I select the main folder wich contains the model?
I'm a bit confused on the excact steps to wich folder to point to..

Regards,
## Post #309
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2021-08-18T13:59:48+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from WollieWoltaz ↑Wed Aug 18, 2021 8:26 pm at Wed Aug 18, 2021 8:26 pm
>
> 
...

The settings explanation can be a lil "overwhelming" at first. 
You should go with
MULTIFILE = 0
SMART_DETECTION = 1
ANIMATION_TRACK = X   --> you need to change this and reload plugin to cycle animations, it'll ask for files again. Unless there's another method to cycle animation as my plugin is old and i've to update it   

ANIMATION_MODE = 1   --> if you leave it @ 0 you're telling the program not to load animations. 1 is to load animations outside the 1st loaded file. 2 is to load animations directly from the 1st main file.

SKELETON_LOAD = 0   --> If 0 it mean that skeleton and meshes are inside the same file, otherwise if the skeleton and meshes are separate you go with 1 and have to load it too (Ex. Elder Scroll Online)
MERGE_SCENE = 2

With these settings you'll first load the wanted meshes+skeleton, then another window will pop and ask for the animation file.
## Post #310
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2021-08-18T15:00:22+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I've done what you subscribed and i tried 0,1,2 for animation mode, with 0 no animations are there and with 1 or 2 i'm getting an error. In the error it talks about AnimationMode.. so that's why i tried fiddling around with that but to no afail.
I even tried switching files around because all the files are in seperate folders when extracted with CascView, but I could not get it to work, so i put every file in 1 folder (mesh/skeleton/animation) but it still does not work. I can't get the animations to work.
I tried every animation track as well but that didn't worked either.

Could you tell me if you have all the needed files in seperate folders or everything in 1 main folder?

(I extracted the "Hydra1" creature btw... maybe that specific creature does not work?)

Maybe it's better if you could show a little preview video of the import process? That would be verry helpfull not only for me but for others as well!

Thanks for answering so far,
## Post #311
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2021-08-18T16:31:26+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from WollieWoltaz ↑Wed Aug 18, 2021 11:00 pm at Wed Aug 18, 2021 11:00 pm
>
> 
...

Well, After various trial and some "wtf" moment, i can safely say that the latest plugin (1.35) gives me this error when trying to load a D2R animation:

> Traceback (most recent call last):
>
>   File "C:\Users\LoremIpsum\Downloads\noesisv4417\plugins\python\fmt_GR2reader.py", line 5228, in noepyLoadModel
>
>     anims,frameRate = animation(anim_data,bones, ANIMATION_MODE, model,frameRate)
>
>   File "C:\Users\LoremIpsum\Downloads\noesisv4417\plugins\python\fmt_GR2reader.py", line 5113, in animation
>
>     InitialPlacement = model.Trackgroups.InitialPlacement[value]
>
> TypeError: 'Transform' object does not support indexing

While the old one i got, V1.3 does not.
Could you try the attached one first?
[fmt_GR2reader 1.3.rar](https://xentaxbackup.github.io/file/20637_fmt_GR2reader 1.3.rar)
## Post #312
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2021-08-18T17:28:20+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Yes the latest version throughs out an error indeed.
The script you send, (v1.3) works! The animation is playing as well!

Don't know what the issue is!

btw..
How can I cycle through animations or can I only import 1 animation at the time?
And are there multiple animations in 1 track or is it 1 animaton per track?
## Post #313
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-18T17:45:28+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Does anyone know what Medal Of Honor game is supported as stated in the first reply of this topic?
## Post #314
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2021-08-18T20:41:48+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Tosyk ↑Thu Aug 19, 2021 1:45 am at Thu Aug 19, 2021 1:45 am
>
> 
Does anyone know what Medal Of Honor game is supported as stated in the first reply of this topic?

Medal of Honor Pacific Assault of EA games

> Reply from WollieWoltaz ↑Thu Aug 19, 2021 1:28 am at Thu Aug 19, 2021 1:28 am
>
> 
Yes the latest version throughs out an error indeed.
The script you send, (v1.3) works! The animation is playing as well!

Don't know what the issue is!

btw..
How can I cycle through animations or can I only import 1 animation at the time?
And are there multiple animations in 1 track or is it 1 animaton per track?

'Am happy that is working, you've to import 1 at time, just change the n° of ANIMATION_TRACK and reload the plugin through Tool-> Reload Plugin, if it's playing the 1st animation it mean that the track ended.
## Post #315
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-18T21:10:38+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Allanoon ↑Thu Aug 19, 2021 4:41 am at Thu Aug 19, 2021 4:41 am
>
> 
Tosyk wrote: ↑Thu Aug 19, 2021 1:45 am
Does anyone know what Medal Of Honor game is supported as stated in the first reply of this topic?


Medal of Honor Pacific Assault of EA gameswait but this one is on LithTech engine by Monolith, not granny

edit:
How to load models from lionhart?
[2021-08-19 00.26.16.jpg](https://xentaxbackup.github.io/file/20639_2021-08-19 00.26.16.jpg)
## Post #316
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2021-08-18T21:36:01+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

@ Allanoon
Okay that'll work! Thanks.
Do you know if the method for Diablo 2 res is the same as for Baldurs Gate 3 or Divinity original sin?
You ever tried those games?
## Post #317
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2021-08-19T11:05:15+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Tosyk ↑Thu Aug 19, 2021 5:10 am at Thu Aug 19, 2021 5:10 am
>
> 
wait but this one is on LithTech engine by Monolith, not granny

Uhm... i checked it here [http://www.radgametools.com/granny/customers.html#games](http://www.radgametools.com/granny/customers.html#games) And i do have a folder with MoH granny models but i unistalled the game so i'm unsure 'bout the game name   

> Reply from Tosyk ↑Thu Aug 19, 2021 5:10 am at Thu Aug 19, 2021 5:10 am
>
> 
How to load models from lionhart?

Regarding lionhart i'm loading the files just fine (using latest plugin 1.35). I had to disable merge scene to load animations too (1st select model, then type * in file name so you can see the animations and load them)
Settings were like this
MULTIFILE = 0                       
SMART_DETECTION = 1                 
ANIMATION_TRACK = 1                 
ANIMATION_MODE = 1                 
SKELETON_LOAD = 0                 
MERGE_SCENE = 0                    
CRC_CORRECTION = 0

> Reply from WollieWoltaz ↑Thu Aug 19, 2021 5:36 am at Thu Aug 19, 2021 5:36 am
>
> 
@ Allanoon
Okay that'll work! Thanks.
Do you know if the method for Diablo 2 res is the same as for Baldurs Gate 3 or Divinity original sin?
You ever tried those games?

You welcome.
And yes i did check those games but i don't have them at hand atm, from what i remember they've single animations so you simply have to load them 1 by one (or maybe you can load all of them trough some of the options, never bothered checking  )
## Post #318
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-19T11:23:23+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Allanoon ↑Thu Aug 19, 2021 7:05 pm at Thu Aug 19, 2021 7:05 pm
>
> 
Tosyk wrote: ↑Thu Aug 19, 2021 5:10 am
wait but this one is on LithTech engine by Monolith, not granny


Uhm... i checked it here http://www.radgametools.com/granny/customers.html#games And i do have a folder with MoH granny models but i unistalled the game so i'm unsure 'bout the game nameyeah, that's what I thought. I wonder what is the exact game name — it could be a mobile game or nintendo 3ds game, probably script author could explain more

> Reply from Allanoon ↑Thu Aug 19, 2021 7:05 pm at Thu Aug 19, 2021 7:05 pm
>
> Tosyk wrote: ↑Thu Aug 19, 2021 5:10 am
How to load models from lionhart?


Regarding lionhart i'm loading the files just fine (using latest plugin 1.35). I had to disable merge scene to load animations too (1st select model, then type * in file name so you can see the animations and load them)
Settings were like this
MULTIFILE = 0                       
SMART_DETECTION = 1                 
ANIMATION_TRACK = 1                 
ANIMATION_MODE = 1                 
SKELETON_LOAD = 0                 
MERGE_SCENE = 0                    
CRC_CORRECTION = 0oh, so that's why I can't load any game on granny with this script so far... thanks mate, good to know.
as I understand I need to prepare somekind of presset for each game
## Post #319
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2021-08-19T11:46:41+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Tosyk ↑Thu Aug 19, 2021 7:23 pm at Thu Aug 19, 2021 7:23 pm
>
> 
Allanoon wrote: ↑Thu Aug 19, 2021 7:05 pm
Tosyk wrote: ↑Thu Aug 19, 2021 5:10 am
wait but this one is on LithTech engine by Monolith, not granny


Uhm... i checked it here http://www.radgametools.com/granny/customers.html#games And i do have a folder with MoH granny models but i unistalled the game so i'm unsure 'bout the game name   yeah, that's what I thought. I wonder what is the exact game name — it could be a mobile game or nintendo 3ds game, probably script author could explain more

> Reply from Allanoon ↑Mon Jun 15, 2020 12:46 am at Mon Jun 15, 2020 12:46 am
>
> 
There're also Beyond Divinity and Medal of Honor Pacific Assault whose files are giving errors.

Found this in one of my initial posts so i can confirm that it's MoH Pacific Assault   . Maybe they planned to use Lithtech and then went with granny, like with Ragnarok Online 2 that should have used granny and it's gamebryo instead.
## Post #320
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-19T16:32:17+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Allanoon ↑Thu Aug 19, 2021 7:46 pm at Thu Aug 19, 2021 7:46 pm
>
> Found this in one of my initial posts so i can confirm that it's MoH Pacific Assault   . Maybe they planned to use Lithtech and then went with granny, like with Ragnarok Online 2 that should have used granny and it's gamebryo instead.actually they are not. as said on wikipedia and also I extracted this game at that time and I know exactly how it was made. also allied assault was on quake 3 engine. it confuses me even more. mysterious medal of honor on granny engine
## Post #321
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-19T20:04:54+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Allanoon ↑Thu Aug 19, 2021 7:05 pm at Thu Aug 19, 2021 7:05 pm
>
> 
Regarding lionhart i'm loading the files just fine (using latest plugin 1.35). I had to disable merge scene to load animations too (1st select model, then type * in file name so you can see the animations and load them)
Settings were like this
MULTIFILE = 0                       
SMART_DETECTION = 1                 
ANIMATION_TRACK = 1                 
ANIMATION_MODE = 1                 
SKELETON_LOAD = 0                 
MERGE_SCENE = 0                    
CRC_CORRECTION = 0that doesn't work unfortunately. when I choose any model with this settings the noesis suggest me to load the exact file only. there's no option to load only model and anything else doesn't work
[Clipboard01.jpg](https://xentaxbackup.github.io/file/20640_Clipboard01.jpg)
## Post #322
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-19T20:16:39+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

okay, more about lionheart.
x64 granny dll doesn't work at all.

x32 version tho work ONLY if I:
1. load Amir.MODEL.GR2 first
2. copy Amir.MODEL.GR2 and rename it to Attack01.MODEL.GR2
3. then in noesis where the plugin ask me to load file with same extension but expect animation file I give it Attack01.MODEL.GR2

so only by this way the plugin will spit a model into noesis viewer. Also there's no possibility to load only a model. Is there's a fix to it?
[2021-08-19 23.13.11.jpg](https://xentaxbackup.github.io/file/20642_2021-08-19 23.13.11.jpg)
## Post #323
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2021-08-20T01:21:28+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Tosyk ↑Fri Aug 20, 2021 4:16 am at Fri Aug 20, 2021 4:16 am
>
> 
okay, more about lionheart.
x64 granny dll doesn't work at all.

x32 version tho work ONLY if I:
1. load Amir.MODEL.GR2 first
2. copy Amir.MODEL.GR2 and rename it to Attack01.MODEL.GR2
3. then in noesis where the plugin ask me to load file with same extension but expect animation file I give it Attack01.MODEL.GR2

so only by this way the plugin will spit a model into noesis viewer. Also there's no possibility to load only a model. Is there's a fix to it?

To load only the model, simply double click it, and then close the windows or press ESC.
Also no need to rename the model if you want anim+model. Load 1 animation, then type * in "File Name" -> Enter , and you'll see all the files in the folder, pick the model and you're good to go.
[Type.png](https://xentaxbackup.github.io/file/20648_Type.png)
## Post #324
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-20T06:31:04+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Allanoon ↑Fri Aug 20, 2021 9:21 am at Fri Aug 20, 2021 9:21 am
>
> Also no need to rename the model if you want anim+model. Load 1 animation, then type * in "File Name" -> Enter , and you'll see all the files in the folder, pick the model and you're good to go.yeah, I tried that but it doesn't work:
[2021-08-20 09.30.23.jpg](https://xentaxbackup.github.io/file/20649_2021-08-20 09.30.23.jpg)
## Post #325
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2021-08-20T11:14:47+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Tosyk ↑Fri Aug 20, 2021 2:31 pm at Fri Aug 20, 2021 2:31 pm
>
> 
Allanoon wrote: ↑Fri Aug 20, 2021 9:21 amAlso no need to rename the model if you want anim+model. Load 1 animation, then type * in "File Name" -> Enter , and you'll see all the files in the folder, pick the model and you're good to go.
yeah, I tried that but it doesn't work:

Dang, I've no idea on why it's working for me then
## Post #326
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-20T12:28:01+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Allanoon ↑Fri Aug 20, 2021 7:14 pm at Fri Aug 20, 2021 7:14 pm
>
> 
Tosyk wrote: ↑Fri Aug 20, 2021 2:31 pm
Allanoon wrote: ↑Fri Aug 20, 2021 9:21 amAlso no need to rename the model if you want anim+model. Load 1 animation, then type * in "File Name" -> Enter , and you'll see all the files in the folder, pick the model and you're good to go.
yeah, I tried that but it doesn't work:


Dang, I've no idea on why it's working for me thenI think it's a matter of file handling only. hope jayn23 gonna fix this when he get time.
## Post #327
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-21T17:28:28+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I have a suggestion to jayn23 on how to load different games without changing the script manually. Instead the options may be applied like it does for \Noesis\plugins\python\fmt_ue4.py.

Also, to convert animations from specific game of a specific character and to prevent of several popup oppening the model with needed skeleton could be specified with an option as well. For example like:

```
-useskeletonfrom "J:\Games\SoldnerSecretWars\game\soldner1\Soldiers\Soldier_China.GR2"
```


p.s.: I'm writing CMD tools and these options would be amazing to have just to simplify resource vieweing and conversion.
## Post #328
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-08-21T18:18:15+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

There is the very real possibility that some files named as a GR2 file are not standard.
This was shown long ago with SWTOR.

Headers are correct but storage of the information was done in a different way.
Instead of floats? We found half floats and such.

Granny is made to be customizable so take that into account.
## Post #329
- Username: Neo210
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 31, 2016 4:15 am
- Post datetime: 2021-08-22T00:52:24+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Maybe someone smarter than me can help me. I'm trying to get the DIablo 2 files also. I downloaded the game files this weekend for the free play weekend. My understanding is

Ladik's CASC viewer 2.3.0.249 x64

extracted an entire folder of enemies or NPC or players then
Noesis 4.456 x64  to view the files. Installed the granny reader plugin 1.3 extracted the zip file and placed the py script in plugins > python folder. 
my GR2reader.py settings are 

MULTIFILE = 1
SMART_DETECTION = 1
SKELETON_LOAD = 0 
ANIMATION_MODE = 1 
MERGE_SCENE = 2
ANIMATION_TRACK = 1
GAME_TAG_ESO_STATIC = 0 
GAMETAG_BG3_TEXTURES = 0

Then open noesis64 browsing to the folders extracted from CASC "character>NPC>Akara>torso_lod0.model"
Then a window opens looking for *animations so I go into the NPC>Akara>animation folder and select "combined.animations"

Now previously it threw some manner of python error "traceback" now it just says OPEN FOLDER "select folder that containes wanted .GR2 files" Browse OK Cancel

If I just hit ok it says 
"Traceback (most recent call last):
file "plugins\python\fmt_GR2reader.py", 
kube 4497, in noepuLoadModel
 for fileName in os.listdir(MeshDir):
WindowsError: [Error 3] The system cannot find the path specified: ' '  
If I instead just point it to my D2 files directory I get (got too lazy to type more error code)

[https://ibb.co/Z8rvnVw](https://ibb.co/Z8rvnVw)

Anyway since everyone else has this working. I believe I am doing something wrong so I included all programs and versions (which I re-downloaded freshly today Aug 21st 2021.

Also I'm afraid someone is going to tell me there is a way to highlight and copy my error messages instead of typing them out.
## Post #330
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2021-08-22T04:14:51+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I'm in no way "understand" these errors so i'm just assuming:

Did you try with Noesis.exe and not the 64 bit version? To me the x64 version is not loading 'hem models.

> Reply from Neo210 ↑Sun Aug 22, 2021 8:52 am at Sun Aug 22, 2021 8:52 am
>
> 
Now previously it threw some manner of python error "traceback" now it just says OPEN FOLDER "select folder that containes wanted .GR2 files" Browse OK Cance

This is because you're using the multifile option, so basically after chosing a mesh and the animation it's telling you "where are all the files i need to combine located?", if you don't give a location it throws an error if you put the folder it should load all the meshes inside and combine them.
You could try disable Multifile (Aka, put MULTIFILE = 0 MIND if you do while noesis is open and running you've to do Tools -> Reload plugin)
and see if it loads the single file

> Reply from Neo210 ↑Sun Aug 22, 2021 8:52 am at Sun Aug 22, 2021 8:52 am
>
> 
If I instead just point it to my D2 files directory I get (got too lazy to type more error code)

https://ibb.co/Z8rvnVw

This seems caused by the Smart Detection + Multifile basicaly  combining the meshes + skeletons, removing the duplicated skeletons and giving an error for reasons unknown to me. Again try with Multifile option off or with smart detection off and see if it's working.

Also are you getting errors even with other models? As even with those options ^ Akara it's loading fine for me.
## Post #331
- Username: Neo210
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 31, 2016 4:15 am
- Post datetime: 2021-08-22T15:26:34+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Yes. I get error. I can't open anything. So I was afraid I am doing the steps wrong or something. Since it's working for everyone except me. I changed Multifile = 0 and restarted Noesis. Also Tried Noesis regular and Noesis_64 same results. 

This is my error.
[https://i.ibb.co/TrJNTgJ/error1.jpg](https://i.ibb.co/TrJNTgJ/error1.jpg)
Same error on any Diablo 2 model. I don't know if it matters but the only Granny.dll files I had were for Ducktales. I know everyone is saying use ESO but I don't have that and I couldn't find them for download. All the old mediafire links are dead.
## Post #332
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-23T21:34:21+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I need help with this. better solution for this..png (129.23 KiB) Viewed 239 times
## Post #333
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-23T21:41:58+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

also i don't see textures in noesis when i import gr2
## Post #334
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-23T22:25:29+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Version 1.2.1 doesn't have textures for viewing can you help me? Please?
## Post #335
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-23T22:25:49+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I can't use 1.3.5.
## Post #336
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-23T22:35:16+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

So help me get 1.3.5. Soultion on the reply on the so i can use 1.3.5 now.
## Post #337
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-23T22:52:03+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

You're taking Forever. i just need to import gr2 files but this happened. 
GrannyBeginFileDecompression@24' not found
## Post #338
- Username: Neo210
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 31, 2016 4:15 am
- Post datetime: 2021-08-24T01:32:21+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I got a better Granny2.dll and it solved my problem.
## Post #339
- Username: UncleT
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 17, 2021 12:53 am
- Post datetime: 2021-08-24T15:55:57+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Neo210 ↑Tue Aug 24, 2021 9:32 am at Tue Aug 24, 2021 9:32 am
>
> 
I got a better Granny2.dll and it solved my problem.

Would you mind sharing it with us?
## Post #340
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-24T15:59:26+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from UncleT ↑Tue Aug 24, 2021 11:55 pm at Tue Aug 24, 2021 11:55 pm
>
> 
Neo210 wrote: ↑Tue Aug 24, 2021 9:32 am
I got a better Granny2.dll and it solved my problem.


Would you mind sharing it with us?I don't think it'a allowed here
## Post #341
- Username: UncleT
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 17, 2021 12:53 am
- Post datetime: 2021-08-24T16:01:36+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Tosyk ↑Tue Aug 24, 2021 11:59 pm at Tue Aug 24, 2021 11:59 pm
>
> 
UncleT wrote: ↑Tue Aug 24, 2021 11:55 pm
Neo210 wrote: ↑Tue Aug 24, 2021 9:32 am
I got a better Granny2.dll and it solved my problem.


Would you mind sharing it with us?
I don't think it'a allowed here
Can you send it in a private message please?
## Post #342
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-08-24T21:40:26+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Allanoon ↑Thu Aug 19, 2021 12:31 am at Thu Aug 19, 2021 12:31 am
>
> 
WollieWoltaz wrote: ↑Wed Aug 18, 2021 11:00 pm
...


Well, After various trial and some "wtf" moment, i can safely say that the latest plugin (1.35) gives me this error when trying to load a D2R animation:
Traceback (most recent call last):
  File "C:\Users\LoremIpsum\Downloads\noesisv4417\plugins\python\fmt_GR2reader.py", line 5228, in noepyLoadModel
    anims,frameRate = animation(anim_data,bones, ANIMATION_MODE, model,frameRate)
  File "C:\Users\LoremIpsum\Downloads\noesisv4417\plugins\python\fmt_GR2reader.py", line 5113, in animation
    InitialPlacement = model.Trackgroups.InitialPlacement[value]
TypeError: 'Transform' object does not support indexing

While the old one i got, V1.3 does not.
Could you try the attached one first?

Hi,

Which error are you getting with latest version? can you upload sample? ill take a look and see what i broke  

edit:
Wow just noticed i missed 2 full pages, i am kind of lost as to what dosent work and whats been solved without me, anyone care to summerize
## Post #343
- Username: Neo210
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 31, 2016 4:15 am
- Post datetime: 2021-08-25T03:12:41+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from tritterman ↑Wed Aug 25, 2021 6:23 am at Wed Aug 25, 2021 6:23 am
>
> 
Neo210 wrote: ↑Tue Aug 24, 2021 9:32 am
I got a better Granny2.dll and it solved my problem.


You can send it to my mailbox. my Account is ***@*** and the Password is ****.

I hope this isn't real. Edit out your info!
## Post #344
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2021-08-25T06:25:44+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Wed Aug 25, 2021 5:40 am at Wed Aug 25, 2021 5:40 am
>
> 
Allanoon wrote: ↑Thu Aug 19, 2021 12:31 am
WollieWoltaz wrote: ↑Wed Aug 18, 2021 11:00 pm
...


Well, After various trial and some "wtf" moment, i can safely say that the latest plugin (1.35) gives me this error when trying to load a D2R animation:
Traceback (most recent call last):
  File "C:\Users\LoremIpsum\Downloads\noesisv4417\plugins\python\fmt_GR2reader.py", line 5228, in noepyLoadModel
    anims,frameRate = animation(anim_data,bones, ANIMATION_MODE, model,frameRate)
  File "C:\Users\LoremIpsum\Downloads\noesisv4417\plugins\python\fmt_GR2reader.py", line 5113, in animation
    InitialPlacement = model.Trackgroups.InitialPlacement[value]
TypeError: 'Transform' object does not support indexing

While the old one i got, V1.3 does not.
Could you try the attached one first?


Hi,

Which error are you getting with latest version? can you upload sample? ill take a look and see what i broke  

edit:
Wow just noticed i missed 2 full pages, i am kind of lost as to what dosent work and whats been solved without me, anyone care to summerize

Hi jayn, hope you're doing well   
The problem should have been the wrong granny.dll version, i guess solved by getting it from ESO...  
...and the fact that 1.35 plugin is having problem loading the animations of D2R (models + textures loads just fine, the animation error is the one in my quote), temporary solved by using 1.3 .

I said trial and wtf because i didn't know that noesis would load the python plugins even from the "base" folder (they also have preference over the python folder) So i had the old noesis i use which seemingly worked and the newest one didn't... i couldn't understand why till i discovered the noobish arcanum   

[https://www.mediafire.com/file/s4lzytrn ... es.7z/file](https://www.mediafire.com/file/s4lzytrn4s4ovyc/samples.7z/file) here 2 samples~
## Post #345
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-08-25T11:43:53+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Allanoon ↑Wed Aug 25, 2021 2:25 pm at Wed Aug 25, 2021 2:25 pm
>
> 
jayn23 wrote: ↑Wed Aug 25, 2021 5:40 am
Allanoon wrote: ↑Thu Aug 19, 2021 12:31 am


Well, After various trial and some "wtf" moment, i can safely say that the latest plugin (1.35) gives me this error when trying to load a D2R animation:



While the old one i got, V1.3 does not.
Could you try the attached one first?


Hi,

Which error are you getting with latest version? can you upload sample? ill take a look and see what i broke  

edit:
Wow just noticed i missed 2 full pages, i am kind of lost as to what dosent work and whats been solved without me, anyone care to summerize  


Hi jayn, hope you're doing well   
The problem should have been the wrong granny.dll version, i guess solved by getting it from ESO...  
...and the fact that 1.35 plugin is having problem loading the animations of D2R (models + textures loads just fine, the animation error is the one in my quote), temporary solved by using 1.3 .

I said trial and wtf because i didn't know that noesis would load the python plugins even from the "base" folder (they also have preference over the python folder) So i had the old noesis i use which seemingly worked and the newest one didn't... i couldn't understand why till i discovered the noobish arcanum   

https://www.mediafire.com/file/s4lzytrn ... es.7z/file here 2 samples~

Hi, its been a while ha 
hope you are well as well

well both samples are working for me without any fixes or changes...so i cant debug anything   
anyway going thru the posts i notice most of you have MERGE_SCENE = 1 , its really not needed for most cases and i would turn it off unless you are trying to comine multiple models in the same file
## Post #346
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2021-08-25T13:09:54+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Wed Aug 25, 2021 7:43 pm at Wed Aug 25, 2021 7:43 pm
>
> 
Hi, its been a while ha 
hope you are well as well

well both samples are working for me without any fixes or changes...so i cant debug anything   
anyway going thru the posts i notice most of you have MERGE_SCENE = 1 , its really not needed for most cases and i would turn it off unless you are trying to comine multiple models in the same file
  Yeah... it seems it was the MERGE_SCENE option...

 *away*
## Post #347
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-25T20:45:36+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

i still get the error when i try Merge scene 1.
## Post #348
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-25T20:52:43+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

It's Here. error nowsias.png (14.57 KiB) Viewed 145 times
## Post #349
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-25T22:10:50+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

It happened when i enter Spongebob Models from Granny 3d engine 2 viewing.
## Post #350
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-08-26T05:06:25+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from tritterman ↑Thu Aug 26, 2021 6:10 am at Thu Aug 26, 2021 6:10 am
>
> 
It happened when i enter Spongebob Models from Granny 3d engine 2 viewing.

The decompression@24 error means it identified the compression at bitknit but current .dll dosent have the required functions to decompress it.
Iv seen someone already post that a new .dll version solved his issues and it should...

you can upload you sample and ill see if there is anything special about it.
## Post #351
- Username: Neo210
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 31, 2016 4:15 am
- Post datetime: 2021-08-26T21:08:41+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I have a question about the Diablo 2 files, maybe someone can help me. Since I can now open them in noesis I noticed that the sorceress doesn't load or export textures for the body. If I load the sorceress head only the hair is textured the head torso arms and legs (that also load) are not. It's not a super huge problem, except that the texture doesn't get converted and exported. If it did I could just manually add the texture in blender. It seems also that all of the "light" armor options for sorceress do not load textures. If there is a way to just convert the .texture files that would help me also. 

TL:DR -light armor sorceress textures do not load or export also head and body textures. All sorceress files with *_lit_LOD_* do not load. 



samples:

[https://privfile.com/download.php?fid=6 ... 4-OTYzOQ==](https://privfile.com/download.php?fid=6127ff91bbd04-OTYzOQ==)
## Post #352
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-27T01:21:30+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

do you have the new dll file?
## Post #353
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-27T11:02:01+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

how do models get exported without the Cubes?
## Post #354
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-29T11:55:17+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Cubes preview
[how to get rid of the cubes.png](https://xentaxbackup.github.io/file/20710_how to get rid of the cubes.png)
## Post #355
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-29T11:58:36+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

please contact me back.
## Post #356
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-29T13:57:52+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from tritterman ↑Sun Aug 29, 2021 7:55 pm at Sun Aug 29, 2021 7:55 pm
>
> 
Cubes previewI think this is specific objects (cubes) of that particulaer game. it can't be fixed. you will need remove them manually in blender, 3ds max, cinema4d or whatever
## Post #357
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-08-29T14:05:37+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

SKIP_MESH Option may be what you need.
Send me that GR2 file and I'll look at it.
## Post #358
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-31T00:32:34+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Skip Mesh Option?
## Post #359
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-08-31T19:28:43+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I offered to look at your files.
That way I could give you a quick answer.
The Skip Mesh option is explained in this tread so I'll not go back over past posts.
Send me a link to the files or read the thread.
## Post #360
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-31T22:08:45+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

ok.
## Post #361
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-31T22:14:53+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

neptune_model.zip
i need King Neptune to have cubes removed and Textures added. (89.68 KiB) Downloaded 21 times
## Post #362
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-31T22:30:49+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

boypat_model.zip
skip mesh for boypatrick. (96.59 KiB) Downloaded 18 times
## Post #363
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-08-31T22:31:53+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

oldlady_model.zip
same for this old lady. (99.69 KiB) Downloaded 19 times
## Post #364
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-09-01T00:02:58+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from tritterman ↑Wed Sep 01, 2021 6:31 am at Wed Sep 01, 2021 6:31 am
>
> 
oldlady_model.ziphave you ever been to any forum? man, please keep your thoughts within a single message, edit previous if needed. don't let admin get on you and shoot us down!
## Post #365
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-09-01T15:42:46+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

allright i'm sorry.
## Post #366
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-09-01T15:51:13+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

i just wanted to learn about Skip Mesh Option.
## Post #367
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-09-01T20:02:58+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

In the GR2 python script is the Option SKIP_MESH=
Set it to SKIP_MESH=2

Then make a text file named mesh.txt

Add the line
Bo to that text file.
Put the mesh.txt in the root folder with the granny2.dll
That will stop the loading of boxes and bones meshes.

Look at the files with Granny viewer to find which meshes to add to future lists.
## Post #368
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-09-01T20:18:41+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Now as to the textures. Those are in the GR2 files stored in a bink 4 compression format.
This plug in will not extract the textures.

Should you be using the 3D mesh in a different program after exporting from Noesis?
Open the file with Granny viewer and do a screen capture of the textures and adjust in your 3D model program of choice.

One can grab the bink files with a hex editor and then use other RAD tools to convert but I'm positive that is WAY above your skill level.
## Post #369
- Username: Walter Hawkwood
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 05, 2011 1:22 am
- Post datetime: 2021-09-02T15:56:32+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hi! The plugin works great with most AoE3 Definitive Edition gr2 files, but on certain files produces an error "Tried to set offset beyond buffer size" (see below)





A couple of such problematic files attached to the post. Tried with both 32- and 64-bit version.
[askari.zip](https://xentaxbackup.github.io/file/20729_askari.zip)
## Post #370
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-09-02T17:16:36+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Thu Sep 02, 2021 4:18 am at Thu Sep 02, 2021 4:18 am
>
> 
Now as to the textures. Those are in the GR2 files stored in a bink 4 compression format.
This plug in will not extract the textures.

Should you be using the 3D mesh in a different program after exporting from Noesis?
Open the file with Granny viewer and do a screen capture of the textures and adjust in your 3D model program of choice.

One can grab the bink files with a hex editor and then use other RAD tools to convert but I'm positive that is WAY above your skill level.

This actually incorrect   
my last update added support for bink 4 format textures, just try youll see, took a lot RE would gidrah i might add... but it works
## Post #371
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-09-02T17:17:39+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Walter Hawkwood ↑Thu Sep 02, 2021 11:56 pm at Thu Sep 02, 2021 11:56 pm
>
> 
Hi! The plugin works great with most AoE3 Definitive Edition gr2 files, but on certain files produces an error "Tried to set offset beyond buffer size" (see below)

A couple of such problematic files attached to the post. Tried with both 32- and 64-bit version.

thanks for reporting this, and uplaoding samples - ill add to my to do list for next update
## Post #372
- Username: Walter Hawkwood
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 05, 2011 1:22 am
- Post datetime: 2021-09-02T18:53:36+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Realized only one file got attached to the previous post. Here is another just in case.
[genitour.zip](https://xentaxbackup.github.io/file/20730_genitour.zip)
## Post #373
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-09-03T21:02:32+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Fri Sep 03, 2021 1:16 am at Fri Sep 03, 2021 1:16 am
>
> 
This actually incorrect   
my last update added support for bink 4 format textures, just try youll see, took a lot RE would gidrah i might add... but it works
Sorry about that! I haven't grabbed the updates since you sent me the special version I'm using.
## Post #374
- Username: mertko
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 17, 2021 10:07 pm
- Post datetime: 2021-09-17T16:38:28+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Greetings, I was using GAME_TAG_SH5 to load up Granny files from non Silent Hunter games as well. Most of the time it works fine but for some Granny files it fails to load the entire file if texture files are present inside the same folder as the Granny file. Without the texture files present the Granny file itself loads well. When it fails to load the textures it gives the following error:

WARNING: Could not load external texture
Traceback (most recent call last):
  File "D:\Granny\Noesis\plugins\python\fmt_GR2reader135.py", line 5220, in noepyLoadModel
    texList, matList = LoadMeshData(model)
  File "D:\Granny\Noesis\plugins\python\fmt_GR2reader135.py", line 4876, in LoadMeshData
    texListTemp,material  = GetTexturesSH5(MeshMat.Maps,Mesh_Name,MatCount,texList)
  File "D:\Granny\Noesis\plugins\python\fmt_GR2reader135.py", line 546, in GetTexturesSH5
    tex.name = baseName[:-4]
AttributeError: 'NoneType' object has no attribute 'name'

I would be glad if this can be fixed and can you please tell me in what other ways I can load the textures of the granny files I open?

Edit:
I share link of the file I've uploaded below (It was 1.7MB in size but XeNTaX said it was too big to attach):

"elf_shop" is the main file containig the mesh, "wait" and "wait2" are animation files and ".dds" files are textures of different parts of the model.

[https://www.swisstransfer.com/d/47c0698 ... 28242e2fd9](https://www.swisstransfer.com/d/47c0698b-5ac2-4f15-9125-bd28242e2fd9)
## Post #375
- Username: Farrarie
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Mar 19, 2017 6:00 pm
- Post datetime: 2021-09-22T22:36:47+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thanks for the amazing tool
## Post #376
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2021-09-27T14:13:26+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hello to everyone. 
Thanks to a friend of mine, I was able to extract the files of the game "Diablo II Resurrected". with "CascView"
But unfortunately I can't move forward anymore. 
I am getting such a problem.

Is there a solution to this?

here are some examples. --> [https://www.mediafire.com/file/77j1ttyu ... on.7z/file](https://www.mediafire.com/file/77j1ttyuyxntt6x/amazon.7z/file)
## Post #377
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2021-09-28T23:42:05+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hi TSelman61X.  I think this is because of your granny2.dll version.  I will send you a DM.
## Post #378
- Username: Lexxon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 18, 2016 1:59 am
- Post datetime: 2021-09-29T05:51:46+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Quick question regarding Diablo 2 Resurrected... has anyone been able to access the textures for weapons and items?
## Post #379
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2021-09-29T20:28:50+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Yes, I had no problems converting almost all textures from env, items, characters, objects.  Weapons models and textures are in data\hd\items\weapon\(WeaponName).

They can be viewed/exported with jayn23's plugin.
## Post #380
- Username: Lexxon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 18, 2016 1:59 am
- Post datetime: 2021-09-30T06:20:41+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from zardalu ↑Thu Sep 30, 2021 4:28 am at Thu Sep 30, 2021 4:28 am
>
> 
Yes, I had no problems converting almost all textures from env, items, characters, objects.  Weapons models and textures are in data\hd\items\weapon\(WeaponName).

They can be viewed/exported with jayn23's plugin.

Hmm...I am very confused, then.  Nearly all character and armor models extract with their textures for me, but weapons, items, and environmental objects do not.  The .texture files are definitely being extracted, but for some reason Noesis isn't seeing them.
## Post #381
- Username: bulldoozer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 15, 2019 6:01 pm
- Post datetime: 2021-09-30T17:19:28+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hi, i'm trying to load my sorceress .model files in noesis. apparently i need the Granny2.dll file but i can't find it anywhere. Sorry in advance for any inconvenience I'm not really sure if i'm following the right steps to do this xD thanks in advance
## Post #382
- Username: naster
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 05, 2021 8:50 am
- Post datetime: 2021-10-05T01:53:25+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from zardalu ↑Thu Sep 30, 2021 4:28 am at Thu Sep 30, 2021 4:28 am
>
> 
Yes, I had no problems converting almost all textures from env, items, characters, objects.  Weapons models and textures are in data\hd\items\weapon\(WeaponName).

They can be viewed/exported with jayn23's plugin.

Would you be kind enough to make a little procedure for a new comers like me on how to extract D2R textures?

This is what I did : 
- Download CASC Viewer : [http://www.zezula.net/en/casc/main.html](http://www.zezula.net/en/casc/main.html)
- Extract the folder with CASC : E:\Program Files (x86)\Diablo2Beta\Diablo II Resurrected\Data
- Download NOESIS : [https://richwhitehouse.com/index.php?co ... sv4458.zip](https://richwhitehouse.com/index.php?content=inc_projects.php&filemirror=noesisv4458.zip)
- Download jayn23's plugin : [download/file.php?id=20312](https://forum.xentax.com/download/file.php?id=20312)
- Move jayn23's script to : noesisv\plugins\python\fmt_GR2reader135.py
- Move granny2.dll to the root of : noesisv


Now what do I do with .model and .texture files.
I want to extract one front image per item.

Thanks!
## Post #383
- Username: Lexxon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 18, 2016 1:59 am
- Post datetime: 2021-10-05T07:25:12+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from naster ↑Tue Oct 05, 2021 9:53 am at Tue Oct 05, 2021 9:53 am
>
> 

Would you be kind enough to make a little procedure for a new comers like me on how to extract D2R textures?
...

Now what do I do with .model and .texture files.
I want to extract one front image per item.

Thanks!

If you load the .model files in Noesis and then export the model to another format, the Noesis script will automatically export the .texture files in .png format.  This is assuming, of course, that the assigned .texture files are in their proper sub-directory... which is the problem I was having earlier with weapons and items.  The CASC Viewer was not extracting their textures into a separate sub-directory, so I had to make one and put them there manually.

If there is another way to view and convert D2R textures in Noesis, I am not aware of it; I am rather noobish myself.
## Post #384
- Username: jimhsu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 08, 2015 3:17 am
- Post datetime: 2021-10-11T02:28:09+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Looks like ORM (AO/roughness/metalness) maps aren't being extracted with the plugin for D2R. Any way to get those?

Manual extraction by renaming the orm file to alb worked.
[o.jpg](https://xentaxbackup.github.io/file/21017_o.jpg)
## Post #385
- Username: DirtyApparition
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 12, 2021 1:03 am
- Post datetime: 2021-10-11T18:55:29+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hello. Trying to get the D2R models to load up in Noesis. I have extracted the Data folder from D2R directory with Cascview. I have placed jayn23s plugin in the plugin folder and I have found some granny2.dll from the internet but I suspect it is not the correct one.

```
Traceback (most recent call last):
  File "D:\Model Ripping\neosis\plugins\python\fmt_GR2reader135.py", line 5199, in noepyLoadModel
    Models = GR2Reader(data)  
  File "D:\Model Ripping\neosis\plugins\python\fmt_GR2reader135.py", line 4204, in GR2Reader
    TempAllDecompressedData = GR2decompress(DecompressedData,ComperesedData,section.decompressed_size,section.data_size,section)
  File "D:\Model Ripping\neosis\plugins\python\fmt_GR2reader135.py", line 4024, in GR2decompress
    beginDecompressProc = lib['_GrannyBeginFileDecompression@24']
  File "D:\Model Ripping\neosis\Plugins\python\core321.zip\ctypes\__init__.py", line 358, in __getitem__
AttributeError: function '_GrannyBeginFileDecompression@24' not found
```


Is what shows up in the debug window and error window. Any help? I really want to try to extract these to STL for my 3d printer. Thank you.
## Post #386
- Username: lanzajamones
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 18, 2012 6:38 am
- Post datetime: 2021-10-13T10:33:57+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from zardalu ↑Wed Sep 29, 2021 7:42 am at Wed Sep 29, 2021 7:42 am
>
> 
Hi TSelman61X.  I think this is because of your granny2.dll version.  I will send you a DM.
I have the same error
## Post #387
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-10-13T22:35:29+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

[https://www.mediafire.com/file/a46htm9y ... 2.dll/file](https://www.mediafire.com/file/a46htm9ygoebobq/granny2.dll/file)
## Post #388
- Username: DirtyApparition
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 12, 2021 1:03 am
- Post datetime: 2021-10-14T00:32:35+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Thu Oct 14, 2021 6:35 am at Thu Oct 14, 2021 6:35 am
>
> 
https://www.mediafire.com/file/a46htm9y ... 2.dll/file

TY
## Post #389
- Username: lanzajamones
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 18, 2012 6:38 am
- Post datetime: 2021-10-14T10:56:25+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Thu Oct 14, 2021 6:35 am at Thu Oct 14, 2021 6:35 am
>
> 
https://www.mediafire.com/file/a46htm9y ... 2.dll/file

thx!
## Post #390
- Username: RobertPaulson
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 16, 2021 2:54 pm
- Post datetime: 2021-10-16T07:15:39+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

hi! another d2r fan here! I am more of a nob and I'm not sure what to do with the .pu file I got. Do I need to install python and run some interpreter just to extract the dll from the script? I placed it in the install dir of the Noesis but nothing happened. the .model files are still not recognized. halp please. I would like to work on this under win10, however I have Fedora as well if that makes it easier by any chance...

edit: nvm I just placed it in the python folder   now it works!

I guess I wasn't after .model files after all   
Does anyone know where the files that dictate the inventory view of the items are located in d2r? I wanted to check the dc6 files but I can't find a working editor for these and afaik those are for legacy....

Edit: hi again I found the sprite files!  yey. Sorry for spam. 

Thanks for the tool, I think I will end up using it once I get familiar more with this environment!
## Post #391
- Username: RobertPaulson
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 16, 2021 2:54 pm
- Post datetime: 2021-10-17T00:52:31+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from erik945 ↑Mon May 31, 2021 7:52 pm at Mon May 31, 2021 7:52 pm
>
> 


My two cents 
Noesis Script for D2R UI files (* .sprite)
Icons for weapons, armor, spells, panels, etc. from here
data \ data \ hd \ global \ ui

HI, its me again. Sorry for silly question but How do I edit .sprite? I managed to open it, export it in different format but how do I go about importing it or saving it in .sprite after I've done my edits? thank you, and thanks for all these tools!
## Post #392
- Username: brayan81curu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 12, 2021 1:47 am
- Post datetime: 2021-10-28T20:08:00+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Someone knows use of the D2R textures _ktint, i manage to asseble in unity a shader that maps correctly _alb, _norm, and _orm(occlusion,roughness,metallic) but ktint no idea...
## Post #393
- Username: brayan81curu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 12, 2021 1:47 am
- Post datetime: 2021-10-28T20:15:07+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Example image



D2R_Unity3D.jpg (155.35 KiB) Viewed 342 times
## Post #394
- Username: Meva
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 18, 2021 7:35 am
- Post datetime: 2021-11-04T08:38:17+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

hi, im have this error, exist plugin for 64 bits? where downloand, no found .. sorry
## Post #395
- Username: Meva
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 18, 2021 7:35 am
- Post datetime: 2021-11-04T14:00:36+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hi, now possible open models .GR2, but no see textures, any solution ? thanks..
## Post #396
- Username: LxXDINJIN
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 04, 2021 11:33 pm
- Post datetime: 2021-11-05T06:30:26+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I need help, friend! Can you provide a convenient batch conversion. Texture function? Or you can let noesis preview the function of. Texture file separately!
## Post #397
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2021-11-29T00:54:31+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Just posting here to say that the granny2_x64.dll from [Anno 1404](https://store.steampowered.com/app/1281630/Anno_1404__History_Edition/) works.
## Post #398
- Username: Sotek
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 10, 2021 8:31 pm
- Post datetime: 2021-12-11T16:11:55+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I've been trying everything to extract ESO meshes of characters, props and monsters to tinker with for 3D sculpting and printing. Thank you very much
## Post #399
- Username: Geo99
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 08, 2022 5:44 pm
- Post datetime: 2022-01-08T23:44:34+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Meva ↑Thu Nov 04, 2021 10:00 pm at Thu Nov 04, 2021 10:00 pm
>
> 
Hi, now possible open models .GR2, but no see textures, any solution ? thanks..

any update on the texture for .gr2 ?
## Post #400
- Username: Swift12
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Oct 21, 2014 3:43 am
- Post datetime: 2022-01-26T22:20:46+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Sorry, total noob here, I downloaded Noesis and that GR2 plugin to try and open the Diablo II Resurrected models. I extracted them via Casc Viewer, but they are not in GR2 format, they are just called ****.model. How do I get them into GR2 format?

Thanks.
## Post #401
- Username: Neverstops577
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Nov 16, 2016 9:27 am
- Post datetime: 2022-01-27T23:20:50+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Swift12 ↑Thu Jan 27, 2022 6:20 am at Thu Jan 27, 2022 6:20 am
>
> 
Sorry, total noob here, I downloaded Noesis and that GR2 plugin to try and open the Diablo II Resurrected models. I extracted them via Casc Viewer, but they are not in GR2 format, they are just called ****.model. How do I get them into GR2 format?

Thanks.

You rename the .model to .gr2. I don't know why they're in .model but it's the same, so yeah.
## Post #402
- Username: Swift12
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Oct 21, 2014 3:43 am
- Post datetime: 2022-01-28T11:51:12+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Neverstops577 ↑Fri Jan 28, 2022 7:20 am at Fri Jan 28, 2022 7:20 am
>
> 
Swift12 wrote: ↑Thu Jan 27, 2022 6:20 am
Sorry, total noob here, I downloaded Noesis and that GR2 plugin to try and open the Diablo II Resurrected models. I extracted them via Casc Viewer, but they are not in GR2 format, they are just called ****.model. How do I get them into GR2 format?

Thanks.


You rename the .model to .gr2. I don't know why they're in .model but it's the same, so yeah.
Thanks. Renamed them, but get a Python error message when I try to open. 



error.JPG (45.44 KiB) Viewed 143 times



By the way, did anyone come up with a way to view modular characters from Diablo II Resurrected? I mean WoWHead and PureDiablo managed to do it somehow seeing as how they uploaded videos of the models during the beta already...
## Post #403
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2022-01-30T12:24:38+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> You rename the .model to .gr2. I don't know why they're in .model but it's the same, so yeah.
You don't need to rename the files, and probably shouldn't.  jayn23 plugin can read .model files directly. If you have the texture in a "textures" folder in the same directory as the model, then the model will show up in Noesis as textured for most character models.

> By the way, did anyone come up with a way to view modular characters from Diablo II Resurrected?
jayn23's plugin can read all of the character models from the game. Some, like the zombies, come in parts which you would need to add together in 3d modeling software.
## Post #404
- Username: Swift12
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Oct 21, 2014 3:43 am
- Post datetime: 2022-01-30T14:53:06+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from zardalu ↑Sun Jan 30, 2022 8:24 pm at Sun Jan 30, 2022 8:24 pm
>
> 
 You rename the .model to .gr2. I don't know why they're in .model but it's the same, so yeah.
You don't need to rename the files, and probably shouldn't.  jayn23 plugin can read .model files directly. If you have the texture in a "textures" folder in the same directory as the model, then the model will show up in Noesis as textured for most character models.
I tried that, nothing shows up. Maybe I don't have the right GR2 dll? Which folder do I need to put that dll in, anyway?


> By the way, did anyone come up with a way to view modular characters from Diablo II Resurrected?
jayn23's plugin can read all of the character models from the game. Some, like the zombies, come in parts which you would need to add together in 3d modeling software.
[/quote]
Do I need to put his plugin under Noesis\plugins\python\ to work? I assumed so as it has the same python format.
## Post #405
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2022-02-09T05:16:21+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Anyone know how to get the GR2 files from ESO?
## Post #406
- Username: Neverstops577
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Nov 16, 2016 9:27 am
- Post datetime: 2022-02-13T19:15:19+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from zardalu ↑Sun Jan 30, 2022 8:24 pm at Sun Jan 30, 2022 8:24 pm
>
> 
 You rename the .model to .gr2. I don't know why they're in .model but it's the same, so yeah.
You don't need to rename the files, and probably shouldn't.  jayn23 plugin can read .model files directly. If you have the texture in a "textures" folder in the same directory as the model, then the model will show up in Noesis as textured for most character models.
By the way, did anyone come up with a way to view modular characters from Diablo II Resurrected? 
jayn23's plugin can read all of the character models from the game. Some, like the zombies, come in parts which you would need to add together in 3d modeling software.
For some reason i renamed the .model to .gr2 and opened with granny viewer and somehow it worked. I don't know if i remember correctly, but it's strange.
## Post #407
- Username: Swift12
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Oct 21, 2014 3:43 am
- Post datetime: 2022-02-14T14:49:59+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Does not work for me, get an error message.
## Post #408
- Username: ineedaid
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 04, 2022 7:22 am
- Post datetime: 2022-03-03T23:23:34+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

The link is dead, is it posted somewhere else? Thx
## Post #409
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2022-03-07T18:52:24+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

[download/file.php?id=20312](https://forum.xentax.com/download/file.php?id=20312)
## Post #410
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-03-26T21:46:58+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

im getting this error only on this file from winter xgames snocross
DOWNLOAD: [https://cdn.discordapp.com/attachments/ ... cian_h.GR2](https://cdn.discordapp.com/attachments/553220665692651542/957394703953842216/jamacian_h.GR2)

all other .gr2 files work fine for me though
## Post #411
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2022-03-27T19:03:46+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Henchman800 ↑Sun Mar 27, 2022 5:46 am at Sun Mar 27, 2022 5:46 am
>
> 
im getting this error only on this file from winter xgames snocross
DOWNLOAD: https://cdn.discordapp.com/attachments/ ... cian_h.GR2

all other .gr2 files work fine for me though

I would like to help but its working for me, please share a screetshot of the options set in your script
## Post #412
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-03-27T20:04:14+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from jayn23 ↑Mon Mar 28, 2022 3:03 am at Mon Mar 28, 2022 3:03 am
>
> 

I would like to help but its working for me, please share a screetshot of the options set in your script

....i dragged my noesis folder to Desktop and it worked.
Thanks for testing though^^
## Post #413
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-03-30T19:52:28+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hey there, i've got a new computer and i need to get the GR2 reader again.
Can you reupload the file reader to my email or reupload it to the secret website?
## Post #414
- Username: Swift12
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2022-03-31T15:52:29+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from tritterman ↑Thu Mar 31, 2022 3:52 am at Thu Mar 31, 2022 3:52 am
>
> 
Hey there, i've got a new computer and i need to get the GR2 reader again.
Can you reupload the file reader to my email or reupload it to the secret website?

Any tools to be shared should be shared publicly, not to individuals' emails or "secret websites".
## Post #415
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-03-31T16:22:23+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Never mind, about that.
I did something else.
## Post #416
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-03-31T16:23:28+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Im sorry if I needed your help.
But it's over now.
## Post #417
- Username: Dodylectable
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 10, 2021 2:39 am
- Post datetime: 2022-04-06T12:08:41+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hello people, I need a little help here if possible; I've been trying to rip out DJ Hero 1's animations (They use .GR2 format, Xbox 360 version) to FBX but they don't preview or export, The odd thing is that only the skeleton is preview-able and exportable unlike the animations, I'm not sure if I'm missing something or the plugin doesn't support DJH1's (or X360) GR2's, Here's a link for an archive that has Daft Punk's animation files so you guys can take a look and see what could happen, thanks in advance!

[https://drive.google.com/file/d/1Im13yk ... sp=sharing](https://drive.google.com/file/d/1Im13yknEeijp74b1BOhhDpVp9Xy8cUnI/view?usp=sharing)

(Frontend folder has normal idle anims while the Game folder has all in-game anims during a song, both have a copy of the same skeleton file [skeleton.gr2])
## Post #418
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-05-15T17:19:44+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I'm having proplems with anno 1404 .gr2 files:


 n_cardinal_angry_idle.zip
character portrait GR2 (117.46 KiB) Downloaded 24 times


this is the error message when trying to open it:


even granny reader doesnt open it, when i give it a try.
please have a look at this
## Post #419
- Username: Carpethop
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Sep 12, 2011 8:02 pm
- Post datetime: 2022-05-18T19:05:55+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hi, I tried to extract some models from Double Dragon Neon and divinity original sin 2 games, but it only give me this error

I'm using granny2.dll from Double Dragon Neon btw
## Post #420
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2022-05-26T17:37:15+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Henchman800 ↑Mon May 16, 2022 1:19 am at Mon May 16, 2022 1:19 am
>
> 
I'm having proplems with anno 1404 .gr2 files:
n_cardinal_angry_idle

even granny reader doesnt open it, when i give it a try.
please have a look at this
That's only an animation file. There are no meshes in it so nothing to see.
## Post #421
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-05-26T18:46:14+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Fri May 27, 2022 1:37 am at Fri May 27, 2022 1:37 am
>
> 
Henchman800 wrote: ↑Mon May 16, 2022 1:19 am
I'm having proplems with anno 1404 .gr2 files:
n_cardinal_angry_idle

even granny reader doesnt open it, when i give it a try.
please have a look at this

That's only an animation file. There are no meshes in it so nothing to see.
Oh shoot!!
Imma Take another Look at the Files....thanks for the Help man!
## Post #422
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2022-06-02T05:36:17+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I am getting the following error message when I tried ripping models off Agatha Christie: Evil Under the Sun:


I used the granny2.dll that came with the game, copied it to the Noesis root folder, but still no dice.

Here are the model samples for your perusal:
[https://www9.zippyshare.com/v/FHOD1M3I/file.html](https://www9.zippyshare.com/v/FHOD1M3I/file.html)
## Post #423
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2022-06-02T13:26:32+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Your not using the Noesis64.exe I hope.

I've opened the files with Noesis.exe and they open fine.
I get errors with Noesis64.exe because I'm not using a granny2_X64.dll

Even when I do use the granny2_X64.dll with Noesis64.exe the files don't open.
## Post #424
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2022-06-03T00:24:41+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Thu Jun 02, 2022 9:26 pm at Thu Jun 02, 2022 9:26 pm
>
> 
Your not using the Noesis64.exe I hope.

I've opened the files with Noesis.exe and they open fine.
I get errors with Noesis64.exe because I'm not using a granny2_X64.dll

Even when I do use the granny2_X64.dll with Noesis64.exe the files don't open.

I am actually using Noesis.exe as the game I got the models from is 32-bit lel.

EDIT: Tried using 1.2.1 and it now works.
## Post #425
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2022-06-03T14:02:42+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Good! Glad your sorted for now.
I run a Debug version 132 script myself.
If I try using the Noesis64 it throws that same error.
## Post #426
- Username: pastuh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 07, 2022 4:55 am
- Post datetime: 2022-06-07T15:23:57+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Can someone give info about Diablo2 Ressurected models/textures extraction?
Somehow every time I get error..

EDIT: Worked.. downloaded another .dll from this thread

EDIT#2: How to convert from .fbx back to game files? I mean game use such format files: .model and .texture
## Post #427
- Username: Swift12
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Oct 21, 2014 3:43 am
- Post datetime: 2022-06-07T22:07:49+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from pastuh ↑Tue Jun 07, 2022 11:23 pm at Tue Jun 07, 2022 11:23 pm
>
> 
Can someone give info about Diablo2 Ressurected models/textures extraction?
Somehow every time I get error..

EDIT: Worked.. downloaded another .dll from this thread

EDIT#2: How to convert from .fbx back to game files? I mean game use such format files: .model and .texture

Can you tell me exactly HOW you got them to work? I downloaded everything provided in the opening post and still cannot open them...
## Post #428
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2022-06-07T22:35:10+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from pastuh ↑Tue Jun 07, 2022 11:23 pm at Tue Jun 07, 2022 11:23 pm
>
> 
How to convert from .fbx back to game files? I mean game use such format files: .model and .texture

Being those are GR2 files? I've never seen a released way to import to a GR2 except Silent Hunter 5.
## Post #429
- Username: dolan1995
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 18, 2020 3:22 pm
- Post datetime: 2022-06-08T17:06:24+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hi, I used the plugin for Diablo Immortal model files but they seems to fail every time.
Here are the files, gotten from Wowhead's model viewer.
[https://mega.nz/folder/SU0HUALK#TTg11n-zWDZKlLNrCr7Vsg](https://mega.nz/folder/SU0HUALK#TTg11n-zWDZKlLNrCr7Vsg)

Am I missing something that caused this? Or will there be an update to add Diablo Immortal compatibility?
## Post #430
- Username: Swift12
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Oct 21, 2014 3:43 am
- Post datetime: 2022-06-09T13:35:46+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from dolan1995 ↑Thu Jun 09, 2022 1:06 am at Thu Jun 09, 2022 1:06 am
>
> 
Hi, I used the plugin for Diablo Immortal model files but they seems to fail every time.
Here are the files, gotten from Wowhead's model viewer.
https://mega.nz/folder/SU0HUALK#TTg11n-zWDZKlLNrCr7Vsg

Am I missing something that caused this? Or will there be an update to add Diablo Immortal compatibility?

Wait, their model viewer can be downloaded? I have tried but cannot find a link on their site. Can you provide it?
## Post #431
- Username: dolan1995
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 18, 2020 3:22 pm
- Post datetime: 2022-06-09T15:41:57+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Swift12 ↑Thu Jun 09, 2022 9:35 pm at Thu Jun 09, 2022 9:35 pm
>
> 
dolan1995 wrote: ↑Thu Jun 09, 2022 1:06 am
Hi, I used the plugin for Diablo Immortal model files but they seems to fail every time.
Here are the files, gotten from Wowhead's model viewer.
https://mega.nz/folder/SU0HUALK#TTg11n-zWDZKlLNrCr7Vsg

Am I missing something that caused this? Or will there be an update to add Diablo Immortal compatibility?


Wait, their model viewer can be downloaded? I have tried but cannot find a link on their site. Can you provide it?

There's actually no download button, so before loading the viewer you can open the web developer tool, the network tab will cache all the loaded files and then just right click -> save, that's how i got them.

[https://www.wowhead.com/diablo-immortal ... ablo-71815](https://www.wowhead.com/diablo-immortal/npc/diablo-71815)
Here's the link, just click the red "View in 3D" button near top of the page to load the viewer.

You can search for more by going back to
[https://www.wowhead.com/diablo-immortal/npcs](https://www.wowhead.com/diablo-immortal/npcs)
## Post #432
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2022-06-09T18:11:51+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Then the files you linked are not GR2 files.
I looked at them and can tell that in seconds.
## Post #433
- Username: Swift12
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Oct 21, 2014 3:43 am
- Post datetime: 2022-06-10T07:37:33+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from dolan1995 ↑Thu Jun 09, 2022 11:41 pm at Thu Jun 09, 2022 11:41 pm
>
> 
Swift12 wrote: ↑Thu Jun 09, 2022 9:35 pm
dolan1995 wrote: ↑Thu Jun 09, 2022 1:06 am
Hi, I used the plugin for Diablo Immortal model files but they seems to fail every time.
Here are the files, gotten from Wowhead's model viewer.
https://mega.nz/folder/SU0HUALK#TTg11n-zWDZKlLNrCr7Vsg

Am I missing something that caused this? Or will there be an update to add Diablo Immortal compatibility?


Wait, their model viewer can be downloaded? I have tried but cannot find a link on their site. Can you provide it?


There's actually no download button, so before loading the viewer you can open the web developer tool, the network tab will cache all the loaded files and then just right click -> save, that's how i got them.

https://www.wowhead.com/diablo-immortal ... ablo-71815
Here's the link, just click the red "View in 3D" button near top of the page to load the viewer.

You can search for more by going back to
https://www.wowhead.com/diablo-immortal/npcs
Thanks a lot! 
Can their viewer  open Diablo II Resurrected models too? My main goal is opening those but this plugin I downloaded does not work for me.
## Post #434
- Username: dolan1995
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 18, 2020 3:22 pm
- Post datetime: 2022-06-11T05:54:51+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Swift12 ↑Fri Jun 10, 2022 3:37 pm at Fri Jun 10, 2022 3:37 pm
>
> 
dolan1995 wrote: ↑Thu Jun 09, 2022 11:41 pm
Swift12 wrote: ↑Thu Jun 09, 2022 9:35 pm


Wait, their model viewer can be downloaded? I have tried but cannot find a link on their site. Can you provide it?


There's actually no download button, so before loading the viewer you can open the web developer tool, the network tab will cache all the loaded files and then just right click -> save, that's how i got them.

https://www.wowhead.com/diablo-immortal ... ablo-71815
Here's the link, just click the red "View in 3D" button near top of the page to load the viewer.

You can search for more by going back to
https://www.wowhead.com/diablo-immortal/npcs

Thanks a lot! 
Can their viewer  open Diablo II Resurrected models too? My main goal is opening those but this plugin I downloaded does not work for me.

Wasn't the plugin already capable of opening D2R models? It still works fine a few days ago for me.

Could you tell what's the problem with it?
## Post #435
- Username: Swift12
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Oct 21, 2014 3:43 am
- Post datetime: 2022-06-11T08:37:57+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from dolan1995 ↑Sat Jun 11, 2022 1:54 pm at Sat Jun 11, 2022 1:54 pm
>
> 
Swift12 wrote: ↑Fri Jun 10, 2022 3:37 pm
dolan1995 wrote: ↑Thu Jun 09, 2022 11:41 pm


There's actually no download button, so before loading the viewer you can open the web developer tool, the network tab will cache all the loaded files and then just right click -> save, that's how i got them.

https://www.wowhead.com/diablo-immortal ... ablo-71815
Here's the link, just click the red "View in 3D" button near top of the page to load the viewer.

You can search for more by going back to
https://www.wowhead.com/diablo-immortal/npcs

Thanks a lot! 
Can their viewer  open Diablo II Resurrected models too? My main goal is opening those but this plugin I downloaded does not work for me.


Wasn't the plugin already capable of opening D2R models? It still works fine a few days ago for me.

Could you tell what's the problem with it?

I described the issue here: [viewtopic.php?f=16&t=22277&start=390#p181748](https://forum.xentax.com/viewtopic.php?f=16&t=22277&start=390#p181748)

Basically the models show up as xxx.model extension  and the reader cannot open then. I renamed them to GR2 as people advised and that just gave me a Python error message.
## Post #436
- Username: dolan1995
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jul 18, 2020 3:22 pm
- Post datetime: 2022-06-11T12:41:40+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Swift12 ↑Sat Jun 11, 2022 4:37 pm at Sat Jun 11, 2022 4:37 pm
>
> 
dolan1995 wrote: ↑Sat Jun 11, 2022 1:54 pm
Swift12 wrote: ↑Fri Jun 10, 2022 3:37 pm

Thanks a lot! 
Can their viewer  open Diablo II Resurrected models too? My main goal is opening those but this plugin I downloaded does not work for me.


Wasn't the plugin already capable of opening D2R models? It still works fine a few days ago for me.

Could you tell what's the problem with it?


I described the issue here: viewtopic.php?f=16&t=22277&start=390#p181748

Basically the models show up as xxx.model extension  and the reader cannot open then. I renamed them to GR2 as people advised and that just gave me a Python error message.
Might be because the plugin is outdated? The one i'm using is 1.35 while the one you're using seems to be 1.21 based on it's name.
Also there's no also need to rename them, you can just opened the models as .model

[download/file.php?id=20312](https://forum.xentax.com/download/file.php?id=20312)
try this link, it's the version i'm currently using (if you already downloaded it, try go into the python plugins folder and remove the older version)
## Post #437
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2022-06-12T04:31:31+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Swift12 ↑Sat Jun 11, 2022 4:37 pm at Sat Jun 11, 2022 4:37 pm
>
> 

download/file.php?id=20312
try this link, it's the version i'm currently using (if you already downloaded it, try go into the python plugins folder and remove the older version)

Yes, use the latest version of the plugin as dolan says, and also make sure the granny dlls are in the same folder as Noesis.exe.  You do not need to rename the files. I will send you a PM.

Diablo Immortal is not using Granny, and is discussed in this thread:
[viewtopic.php?f=16&t=25495](https://forum.xentax.com/viewtopic.php?f=16&t=25495)
## Post #438
- Username: Swift12
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Oct 21, 2014 3:43 am
- Post datetime: 2022-06-12T20:15:09+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from dolan1995 ↑Sat Jun 11, 2022 8:41 pm at Sat Jun 11, 2022 8:41 pm
>
> 
Swift12 wrote: ↑Sat Jun 11, 2022 4:37 pm
dolan1995 wrote: ↑Sat Jun 11, 2022 1:54 pm


Wasn't the plugin already capable of opening D2R models? It still works fine a few days ago for me.

Could you tell what's the problem with it?


I described the issue here: viewtopic.php?f=16&t=22277&start=390#p181748

Basically the models show up as xxx.model extension  and the reader cannot open then. I renamed them to GR2 as people advised and that just gave me a Python error message.

Might be because the plugin is outdated? The one i'm using is 1.35 while the one you're using seems to be 1.21 based on it's name.
Also there's no also need to rename them, you can just opened the models as .model

download/file.php?id=20312
try this link, it's the version i'm currently using (if you already downloaded it, try go into the python plugins folder and remove the older version)
Thanks a lot! With that python plugin I can finally see the models!
## Post #439
- Username: Aeonx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 15, 2022 2:00 pm
- Post datetime: 2022-08-15T06:11:50+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Doesn't work with Istaria gr2 files.
## Post #440
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2022-08-15T17:49:16+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Aeonx ↑Mon Aug 15, 2022 2:11 pm at Mon Aug 15, 2022 2:11 pm
>
> 
Doesn't work with Istaria gr2 files.
Eample files would help.
## Post #441
- Username: Aeonx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 15, 2022 2:00 pm
- Post datetime: 2022-08-15T22:15:14+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Here are some - J stands for juvenile, m is adult, a is ancient. 

[https://www.mediafire.com/file/dtgkncft ... u.zip/file](https://www.mediafire.com/file/dtgkncftbbodyqu/dragonu_u.zip/file)
## Post #442
- Username: CaptnKoda
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 07, 2018 1:36 am
- Post datetime: 2022-09-13T11:54:32+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Anyone currently using this absolutely wonderful plugin for use with ESO? Wouldn't mind pooling some resources to get this stuff into Blender nice and easy.
## Post #443
- Username: wakawaka69
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 17, 2022 9:42 am
- Post datetime: 2022-09-17T15:43:37+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hello,

I would like to extract and convert GR2 files from Bladur's Gate III (GOG patch 8 release), but I'm getting this error, running Neosis_x64 with granny2_x64.dll from TESO

The error message :

---------------------------
Noesis Python Error
---------------------------
Traceback (most recent call last):
  File "E:\BG3_extract\Neosis\plugins\python\fmt_GR2reader135.py", line 5199, in noepyLoadModel
    Models = GR2Reader(data)  
  File "E:\BG3_extract\Neosis\plugins\python\fmt_GR2reader135.py", line 4204, in GR2Reader
    TempAllDecompressedData = GR2decompress(DecompressedData,ComperesedData,section.decompressed_size,section.data_size,section)
  File "E:\BG3_extract\Neosis\plugins\python\fmt_GR2reader135.py", line 4030, in GR2decompress
    beginDecompressProc = lib['GrannyBeginFileDecompression']
  File "E:\BG3_extract\Neosis\Plugins\python\core321.zip\ctypes\__init__.py", line 358, in __getitem__
AttributeError: function 'GrannyBeginFileDecompression' not found

---------------------------
OK   
---------------------------


Also I can't use LSLib for BG3, ask for granny2.dll, so the 32bit dll.

I tried to rename granny2_x64.dll to granny2.dll but I have an error, seems like BG3 needs the 32bit dll?

I have TESO and got granny2_x64.dll, but I have no idea where I could get granny2.dll legally (I checked in BG3 and DOS:II install paths, but nothing, also searched with app Everything)

Thanks for your help
## Post #444
- Username: CaptnKoda
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 07, 2018 1:36 am
- Post datetime: 2022-09-18T12:57:55+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

It cannot be overstarted the sketchiness of downloading random .dll files from the internet.. But that said, I have a copy of granny2.dll here:

[https://drive.google.com/file/d/1DqZENF ... sp=sharing](https://drive.google.com/file/d/1DqZENFUWfu93LR3Czo_AdKPsEOVkpcTU/view?usp=sharing)
## Post #445
- Username: wakawaka69
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 17, 2022 9:42 am
- Post datetime: 2022-09-18T23:04:36+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thanks, but it doesn't change much

This script still makes the same error as above, if I use the 64 or the 32bit neosis exe
well with 32bit exe it makes a slightly diff error : 

Detected file type: GR2 Reader
Traceback (most recent call last):
  File "E:\BG3_extract\Neosis\plugins\python\fmt_GR2reader135.py", line 5199, in noepyLoadModel
    Models = GR2Reader(data)  
  File "E:\BG3_extract\Neosis\plugins\python\fmt_GR2reader135.py", line 4204, in GR2Reader
    TempAllDecompressedData = GR2decompress(DecompressedData,ComperesedData,section.decompressed_size,section.data_size,section)
  File "E:\BG3_extract\Neosis\plugins\python\fmt_GR2reader135.py", line 4024, in GR2decompress
    beginDecompressProc = lib['_GrannyBeginFileDecompression@24']
  File "E:\BG3_extract\Neosis\Plugins\python\core321.zip\ctypes\__init__.py", line 358, in __getitem__
AttributeError: function '_GrannyBeginFileDecompression@24' not found


lslib/ExportTool tells me that it needs granny2.dll, even though I copied it in the same folder as the exe, and also in Tools folder.
I also "unblocked" the dll in file properties, no diff.

So if anybody knows if BG3 GR2 files needs 32 or 64 bit dll/Neosis exe
Either way I can't do anything with both

Also do I need to change "BG3_PATH" variable value to my actual install path ?
## Post #446
- Username: wakawaka69
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 17, 2022 9:42 am
- Post datetime: 2022-09-18T23:59:46+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Well, looks like the dll from TESO doesn't have the decompression part, checked in HxD.
same for your 32bit dll

I found one with it on a github lmao, anyway, looks like BG3 works/needs a 32bit dll
It works, now I'm just looking through 88k files, hoping to find what I want lmao

smh I found Gale entire body (Proxy_GALE_Fullbody), but not for other companions  
Anybody knows which models are used for each companions in BG3 ? (yes, even the body   )
## Post #447
- Username: KilluaHappy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 16, 2022 10:34 pm
- Post datetime: 2022-09-19T19:22:11+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Possible somehow to create a granny and noesis to fail read him?
## Post #448
- Username: ranvids
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 24, 2020 7:43 am
- Post datetime: 2022-10-05T12:55:02+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

hi Eve Online Files export fine but animations dont play along the mesh. 

I cant see any frames,  when i press play animation ( after i imported the noesis exported gr2>fbx) it just stays still. 

Also looks like the mesh influences are set up correctly ( meaning i can move a mesh piece by moving the skeleton joint)

[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1XkZWMvuVw7rSwkYb8FFuY2jemjWA9SjO?usp=sharing)

At this point i would ask if its possible to export multiple tracks at once! Please!   ( without the need of modify python plugin, reload plugins and export another file by hand

EDIT:

i successfully saw an animation importing by using tracks options, im so happy!
ANIMATION_TRACK = 2  <<< The number of your needed track          
ANIMATION_MODE = 2    <<< this must be 2 in order to work

EDIT: added link to examples , more infos.
## Post #449
- Username: ATGSleg
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 10, 2021 5:10 pm
- Post datetime: 2022-11-04T06:25:58+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Please delete this(my) post.  Thank you.
## Post #450
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-11-04T15:38:49+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I tried to open these .gr2 files form anno 1404 and im getting this error. could yall have a look please?


 s_al_zahir_lod0.zip
Model of Al Zahir (37.1 KiB) Downloaded 22 times
## Post #451
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-11-06T14:51:21+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Henchman800 ↑Fri Nov 04, 2022 11:38 pm at Fri Nov 04, 2022 11:38 pm
>
> 

I tried to open these .gr2 files form anno 1404 and im getting this error. could yall have a look please?
s_al_zahir_lod0.zip

the files can be opened with granny viewer, though.
do i have wrong settings?

EDIT:
evegr2toobj also works:


the games pretty old...
## Post #452
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-06T16:37:33+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Henchman800 ↑Sun Nov 06, 2022 10:51 pm at Sun Nov 06, 2022 10:51 pm
>
> 
the files can be opened with granny viewer, though.
do i have wrong settings?You need the suiting granny2.dll (that supports/contains GrannyBeginFileDecompression) to be copied to the Noesis folder.
## Post #453
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-11-06T21:44:48+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from shakotay2 ↑Mon Nov 07, 2022 12:37 am at Mon Nov 07, 2022 12:37 am
>
> 
You need the suiting granny2.dll (that supports/contains GrannyBeginFileDecompression) to be copied to the Noesis folder.

I tried with this .dll straight from the game:
https://cdn.discordapp.com/attachments/ ... ranny2.dll

to no avail. is there a list of certain granny .dll s?
## Post #454
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-06T23:41:03+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I have no idea. But this "straight from the game" dll doesn't contain "GrannyBeginFileDecompression", so there must be something wrong.
## Post #455
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2022-11-06T23:45:17+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

You probably need the 2.11.8.0 version of granny.dll

Give me an example gr2 from that Game.
## Post #456
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-06T23:53:19+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Mon Nov 07, 2022 7:45 am at Mon Nov 07, 2022 7:45 am
>
> 
You probably need the 2.11.8.0 version of granny.dllThat's correct, sir.
## Post #457
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2022-11-07T00:02:37+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

It's also possible you might need an earlier version of the plug in?
I can't remember all the changes and I also run a custom version of the plug in done for me.
Then I changed things from that to do what I wanted.
## Post #458
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-11-07T00:14:55+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Mon Nov 07, 2022 7:45 am at Mon Nov 07, 2022 7:45 am
>
> 
You probably need the 2.11.8.0 version of granny.dll

Give me an example gr2 from that Game.

i see. imma try different versions of your plugin then.
heres an example .gr2 though:
n_guy_forcas_lod0.zip

EDIT:

version 2.11.8.0 worked for me 

thanks for the help
## Post #459
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2022-11-07T00:20:35+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Yep. Opens fine for me with 2.11.8.0 Granny.dll

My version of the plug in is a special debug version done for me.
Then I changed a few things to extract only needed animation frames information from the debug window.
It skips any blank stuff and is also modified to arrange the out put in a certian format.
I can then take that information, run it through an 010 script I wrote to do new animations in the Silent Hunter 4 format.
## Post #460
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-11-07T08:38:40+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Mon Nov 07, 2022 8:20 am at Mon Nov 07, 2022 8:20 am
>
> 
Yep. Opens fine for me with 2.11.8.0 Granny.dll

My version of the plug in is a special debug version done for me.
Then I changed a few things to extract only needed animation frames information from the debug window.
It skips any blank stuff and is also modified to arrange the out put in a certian format.
I can then take that information, run it through an 010 script I wrote to do new animations in the Silent Hunter 4 format.

That Sounds nice! So you were able to replace sh4 anims already? Id Like to See that in a Video If possible.
## Post #461
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2022-11-07T23:26:13+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I figured out the animations for SH3 and SH4 years ago!
I'm 1 of only 2 people that ever did new animations for SH3.
As far as SH4? I'm the only one that can make or modify the animations.
I even TOLD people how to do it!
## Post #462
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-11-08T07:45:05+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Tue Nov 08, 2022 7:26 am at Tue Nov 08, 2022 7:26 am
>
> 
I figured out the animations for SH3 and SH4 years ago!
I'm 1 of only 2 people that ever did new animations for SH3.
As far as SH4? I'm the only one that can make or modify the animations.
I even TOLD people how to do it!

Damn man...freaking awesome! Guys Like you make this Forum what it is
## Post #463
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2022-11-13T21:32:41+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Did the Silent Hunter stuff since 2005.
Now? I've retired from that and concentrate on building my Air Guns.
## Post #464
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2022-11-17T09:54:51+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Is there a way to import animations from multiple .gr2 files and export them in one animation track?
## Post #465
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2022-11-18T22:30:43+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Read the Options settings available in the python file.
I'm thinking you can do that.
Never actually tried myself and I do run a Custom version of the python file.

I did have a 010 script that made editing the settings real quick and easy but I deleted it.
## Post #466
- Username: Razzoriel
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 20, 2016 5:51 am
- Post datetime: 2023-01-06T21:57:47+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Just a heads-up for anyone that is still trying to work with D2R in all this thread. I was having the exact same error messages others were having, but everything was fixed once I installed a bundle in a website and used the tools provided by them. I am not affiliated by it through any means. The website is the first that pops up when you search on google the following: "jayn23's plugin". It is a dedicated D2R modding website which, again, I am not affiliated nor endorsing, simply spelling it out that it all worked for me and now I have this guy's Noesis copy and another that I use for others.
## Post #467
- Username: sirsmokalot
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 11, 2023 8:40 am
- Post datetime: 2023-01-12T02:59:01+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thank you so much for your work, everything works fine with D2R (win10, py 3.8, JRE & JDK are last official).
Models converted to .stl succesfully - can't wait to print some of them
## Post #468
- Username: Jcbq
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 23, 2022 12:02 pm
- Post datetime: 2023-01-17T19:36:26+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

so i am trying to play with some of the Elder Scrolls Online Meshes and textures, and after acquiring these these tools and parts i can see the meshes but the textures will not load. The meshes can export fine, with rigging on it however it appears that the UVs are either broken or have a single point and Noesis upon model load returns errors like this:

Reading 'F:\Game\ESO Extract\Extract\Live Eso\Granny\Reconstructed\AYL Ayleid\\AYL_DUC_LightFixtureB001_0'...Failed.
Reading 'F:\Game\ESO Extract\Extract\Live Eso\Granny\Reconstructed\AYL Ayleid\\AYL_DUC_LightFixtureB001_1'...Failed.
Reading 'F:\Game\ESO Extract\Extract\Live Eso\Granny\Reconstructed\AYL Ayleid\\AYL_DUC_LightFixtureB001_2'...Failed.

i am at a loss as to where to proceed from here
## Post #469
- Username: leckock
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 04, 2020 11:48 pm
- Post datetime: 2023-02-03T18:43:01+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hello, i tried to load animation from Diablo 2 Ressurected (model : Tyrael), but the result seams strange like weird deformation, it's like the wrong animation is charged. i have 1.35 version of the plugin: 
MULTIFILE = 2                       
SMART_DETECTION = 0                 
ANIMATION_TRACK = 3                 
ANIMATION_MODE = 0                  
SKELETON_LOAD = 1                   
MERGE_SCENE = 0                      
CRC_CORRECTION = 0
## Post #470
- Username: drunknmonkie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 01, 2023 11:17 am
- Post datetime: 2023-03-01T03:32:49+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hi and thanks for putting your time and effort in to this program.

Is there anywhere I can find a tutorial to help me figure out how to use it?

I am trying to get my character from BG3 and I am using noesis but have no idea where to start. 

Any help would be awesome

Thank you!
## Post #471
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-01T04:07:47+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from drunknmonkie ↑Wed Mar 01, 2023 11:32 am at Wed Mar 01, 2023 11:32 am
>
> Is there anywhere I can find a tutorial to help me figure out how to use it?This thread contains 471 posts. There should be enough infos for you - just read them, maybe searching by keywords (granny.dll).
Long story short: copy fmt_GR2reader121.py into Noesis' \plugins\python folder then start Noesis and open the sample of your choice.

> I am trying to get my character from BG3 and I am using noesis but have no idea where to start.How about reading the opening post? 
31. Baldur's Gate III, seems to be supported
## Post #472
- Username: Ifurzzar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 10, 2023 7:37 pm
- Post datetime: 2023-03-24T14:10:15+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hi, first of all, thx for the effort in making this tool, I just wanna report an issue I found when exporting some D2R models, here is the model for a weapon called khalim's flail, but as you can see in my screenshot there is only a handle, the real flail head part is missing, while its full shape is like the second screenshot. I did some research and found this issue is somewhat common in items that has a chain to connect different parts of the item, for example screenshot 3 shows a shield where only the chain is rendered(and the chain itself looks not quite correct), while it actually looks like screenshot 4.
May I kindly ask do you have time to fix this issue? If you do not have time, can you pls give me some directions on how to start parsing the D2R .model file? I am a programmer as well, I can try to learn write a plugin(ideally I want to write a blender plugin to directly read the model into blender!)
thx very much!
[issues.jpg](https://xentaxbackup.github.io/file/23596_issues.jpg)
## Post #473
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-03-24T16:43:12+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Can you link me to those files shown in the photo?

And I haven't seen jayn23 here since August last year. 
He was kind enough to send me a Custom version that allows me to remove unused bones from animation files.
## Post #474
- Username: Moonstrewn
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 22, 2022 10:40 pm
- Post datetime: 2023-07-08T23:11:06+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

With BG3 - I have no issues running the script to extract models, however, when I try to extract textures in the same way I get met with an error. 

I have also tried extracting textures using Norbyte's lslib tool, as well as an older quick BMS script I've had tucked away for BG3. None of those are allowing me to extract all of the textures, just parts of the first texture.pak. Has anyone else run into this and, if so, how did you solve the problem?
[Noesis_zRjeDHaSNQ.png](https://xentaxbackup.github.io/file/24039_Noesis_zRjeDHaSNQ.png)
## Post #475
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-07-10T20:43:16+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I'm not sure what you mean by 'Extracting the texture'
Are you just trying to get the textures without the model?

And what Granny2.dll file version do you have.
## Post #476
- Username: Moonstrewn
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 22, 2022 10:40 pm
- Post datetime: 2023-07-12T07:18:58+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from 05SpeedMaster ↑Tue Jul 11, 2023 4:43 am at Tue Jul 11, 2023 4:43 am
>
> 
I'm not sure what you mean by 'Extracting the texture'
Are you just trying to get the textures without the model?

And what Granny2.dll file version do you have.

Granny2.dll version is 2.11.8!

And I mean extract the files from the texture .paks. It throws me the error in my previous post when I try to extract everything from the textures.pak, and a different error on _2 and _3. On the first textures.pak it gets through about 44 files before that error stops it from doing anything else.

Editing to add - I'm looking for the textures specifically for the Nightsong outfit model. When extracting the models.pak I do have the meshes, but none of the textures related to that mesh! So I figured I needed to dig through the texture .paks to try and locate the relevant files.
[Noesis_aWeGJVimJ6.png](https://xentaxbackup.github.io/file/24065_Noesis_aWeGJVimJ6.png)
## Post #477
- Username: salzwer2
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 19, 2023 7:37 am
- Post datetime: 2023-07-25T00:43:01+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Some D2R-related utilities I've made for myself, but others could find useful:

------------------------------

First of all, some D2R items directories have inconsistent structures: some have the *.model and the *.texture files in the same folder, and some others have the *.model in one place, and the *.textures in a subfolder. The ones with the first structure load as "white" items into Noesis, while the ones with the second load correctly, with their textures and so.

For example, right after extracting the stuff with Cascview, "ancient_armor" loads this cool:


However, "axe" loads this naked:


So I've made a Python script you can run before opening Noesis in order to fix that structure, and ensure all *.texture files are in a subfolder:

```
import os
import sys

### CHANGE THIS!!! ###
# Replace with the path to the folder where you've extracted your data
walk_dir = r'C:\Users\username\Documents\01_extracted_items_folder'

print('walk_dir = ' + walk_dir)
print('walk_dir (absolute) = ' + os.path.abspath(walk_dir))

# For each folder...
for root, subdirs, files in os.walk(walk_dir):
    print('--\nroot = ' + root)
    
    hasTextures = False
    hasModel = False
    hasTexturesSubdir = False
    
    textureArray = []

    # ... check if it has both models and textures mixed
    for filename in files:
        file_path = os.path.join(root, filename)
        file_name, file_extension = os.path.splitext(file_path)
        
        if file_extension == ".model":
            hasModel = True
            print('\t- file %s is a Model (full path: %s)' % (filename, file_path))

        elif file_extension == ".texture":
            hasTextures = True
            textureArray.append(file_path)
            print('\t- file %s is a Texture (full path: %s)' % (filename, file_path))

    for subdir in subdirs:
        if subdir == 'textures':
            hasTexturesSubdir = True
            print('\t- TEXTURES subdirectory ' + subdir)

    # ... and, incase the folder has both models and textures mixed...
    if hasModel and hasTextures:
        texturesPath = root + '\Textures'

        # ... create a "Textures" folder (if it doesn't exists)...
        if not hasTexturesSubdir:
            os.mkdir(texturesPath)
        # ... and move all the textures to the "Textures" folder
        for textureName in textureArray:
            destination = texturesPath + '\\' + os.path.basename(textureName)
            print('\t- %s will be moved to %s' % (textureName, destination))
            os.rename(textureName, destination)

```


After running the script, "axe" will load like this:


Incase you want to run this, ensure you have Python installed ([https://www.tomshardware.com/how-to/ins ... -10-and-11](https://www.tomshardware.com/how-to/install-python-on-windows-10-and-11)). Also ensure you have set the PATH variable, and do this (yeah, pretty sure that if you're here, you don't need this degree of detail, but whatever):
1. Copy all the code and paste it into a text editor (notepad or NP++).
2. Modify the walk_dir to the folder where you've extracted the stuff.
3. Save the file with "*.py" extension somewhere in your hard drive. For example, "moveTextures.py".
4. Open a command prompt in the path where you've saved the *.py file (just browse to the folder and type "cmd" -without quotes- in the address bar).
5. In the black window that pops, write "python3 moveTextures.py".

The script will start running and putting the textures into the place they should be for Noesis GR2 being able to autoload them.

-----------------------------------------

Second: given that the "Export" feature only gives the albedo and normal textures, I've done a slight retouch to the GR2 reader file:

This is how the original 1.35 file is at line 661 and ahead:

```
            if flag != 1: 
                texList.append(tex)
            material.setTexture(TextureName)
            
        if baseName[-3:] == 'nrm':
            if flag != 1:  
                rgba = rapi.imageGetTexRGBA(tex)
                #swap red and alpha channels
                rgba = rapi.imageNormalSwizzle(rgba, tex.width, tex.height, 1, 1, 0)
                tex.pixelData = rgba
                tex.pixelType = noesis.NOESISTEX_RGBA32
                tex.mipCount = 0                        
                texList.append(tex)
            material.setNormalTexture(TextureName)
            
    return texList ,material

```


And this is my version:

```
            if flag != 1: 
                texList.append(tex)
            material.setTexture(TextureName)
            
        if baseName[-3:] == 'orm':
            if flag != 1: 
                texList.append(tex)
            
        if baseName[-3:] == 'nrm':
            if flag != 1:  
                rgba = rapi.imageGetTexRGBA(tex)
                #swap red and alpha channels
                rgba = rapi.imageNormalSwizzle(rgba, tex.width, tex.height, 1, 1, 0)
                tex.pixelData = rgba
                tex.pixelType = noesis.NOESISTEX_RGBA32
                tex.mipCount = 0                        
                texList.append(tex)
            material.setNormalTexture(TextureName)
            
    return texList ,material

```


This way, despite not being loaded at the preview, Noesis will export the *.orm file along the *.alb and *.nrm
## Post #478
- Username: Sinesters
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 23, 2023 12:20 pm
- Post datetime: 2023-08-23T06:42:21+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Do any of you know where are the characters body/heads in the nightmare of Baldrus gate 3 file structure i already found all the creatures armors weapons etc but i cant find the main characters.

Help would be appreciated.
## Post #479
- Username: Canyougiant
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 25, 2023 6:40 pm
- Post datetime: 2023-08-26T18:39:01+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hi,
I am using this script to import the gr2 models and animations from Age of Empires 3: Definitive Edition, but animation isn’t correct, only the whole body is moving. It works in legacy version of the game, which is Age of Empires 3. Apparently, something has changed. Have you ever tested it with Age of Empires: Definitive Edition?
## Post #480
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-08-27T12:53:07+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

it works pretty well with Baldur's Gate 3 characters. I must also note that this is the only tool that converts BG3 models properly with skeleton.
## Post #481
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-08-27T15:16:10+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Canyougiant ↑Sun Aug 27, 2023 2:39 am at Sun Aug 27, 2023 2:39 am
>
> 
Hi,
I am using this script to import the gr2 models and animations from Age of Empires 3: Definitive Edition, but animation isn’t correct, only the whole body is moving. It works in legacy version of the game, which is Age of Empires 3. Apparently, something has changed. Have you ever tested it with Age of Empires: Definitive Edition?

Example Files would get you faster answers.
## Post #482
- Username: Canyougiant
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 25, 2023 6:40 pm
- Post datetime: 2023-08-28T10:13:58+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hi, thanks for the replies!
In the end, I managed to resolve my own issue. It's because the bone names in the model files were not match the ones in the animation files. The bone names in the model files were like "Bip01_L_ForeArm", but it's "Bip01 L ForeArm" in the animation file. I guess maybe granny2.dll allows this inconsistency, so animations can be played successfully. There was a line "t.Name = Transform_Track.Name", I changed it to "t.Name = Transform_Track.Name.replace(' ', '_')". That's it.
## Post #483
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2023-09-02T02:31:48+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Unfortunately, there seems to be a problem with lslib tool skipping some textures. I've tried extracting the texture file for Baldur's Gate 3, but this tool skips several textures that are essential to the model. We need a new lslib tool that extracts all textures. I hope this part will be supplemented someday.
## Post #484
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-09-02T06:07:34+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from uroborostestsubject ↑Sat Sep 02, 2023 10:31 am at Sat Sep 02, 2023 10:31 am
>
> 
Unfortunately, there seems to be a problem with lslib tool skipping some textures. I've tried extracting the texture file for Baldur's Gate 3, but this tool skips several textures that are essential to the model. We need a new lslib tool that extracts all textures. I hope this part will be supplemented someday.if you mean albedo, normal and physic maps they are there but presented as virtual textures
## Post #485
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2023-09-02T06:31:12+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Tosyk ↑Sat Sep 02, 2023 2:07 pm at Sat Sep 02, 2023 2:07 pm
>
> 
uroborostestsubject wrote: ↑Sat Sep 02, 2023 10:31 am
Unfortunately, there seems to be a problem with lslib tool skipping some textures. I've tried extracting the texture file for Baldur's Gate 3, but this tool skips several textures that are essential to the model. We need a new lslib tool that extracts all textures. I hope this part will be supplemented someday.
if you mean albedo, normal and physic maps they are there but presented as virtual textures

Thank you for your answer. In my case, the texture itself to be applied to the extracted meshes is lacking. For example, there is a texture that needs to be applied to the torso, but there is no texture to apply to the head and legs. Would there still be any missing textures in the virtual texture folder in this case?
## Post #486
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-09-02T07:09:22+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from uroborostestsubject ↑Sat Sep 02, 2023 2:31 pm at Sat Sep 02, 2023 2:31 pm
>
> 
Tosyk wrote: ↑Sat Sep 02, 2023 2:07 pm
uroborostestsubject wrote: ↑Sat Sep 02, 2023 10:31 am
Unfortunately, there seems to be a problem with lslib tool skipping some textures. I've tried extracting the texture file for Baldur's Gate 3, but this tool skips several textures that are essential to the model. We need a new lslib tool that extracts all textures. I hope this part will be supplemented someday.
if you mean albedo, normal and physic maps they are there but presented as virtual textures


Thank you for your answer. In my case, the texture itself to be applied to the extracted meshes is lacking. For example, there is a texture that needs to be applied to the torso, but there is no texture to apply to the head and legs. Would there still be any missing textures in the virtual texture folder in this case?
body, head, eye textures are different case. they are mix of masks from textures: _HMVY, _CLEA, _MSK. In this article, devs are explaining how they do this: [https://substance3d.adobe.com/magazine/ ... rs-gate-3/](https://substance3d.adobe.com/magazine/bringing-life-to-legends-character-art-in-baldurs-gate-3/)
## Post #487
- Username: Valoun
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 07, 2023 9:51 pm
- Post datetime: 2023-09-02T12:03:03+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Does anyone know why there are messed up UVs in ESO meshes?
## Post #488
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2023-09-02T12:14:00+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Tosyk ↑Sat Sep 02, 2023 3:09 pm at Sat Sep 02, 2023 3:09 pm
>
> 
uroborostestsubject wrote: ↑Sat Sep 02, 2023 2:31 pm
Tosyk wrote: ↑Sat Sep 02, 2023 2:07 pm
if you mean albedo, normal and physic maps they are there but presented as virtual textures


Thank you for your answer. In my case, the texture itself to be applied to the extracted meshes is lacking. For example, there is a texture that needs to be applied to the torso, but there is no texture to apply to the head and legs. Would there still be any missing textures in the virtual texture folder in this case?

body, head, eye textures are different case. they are mix of masks from textures: _HMVY, _CLEA, _MSK. In this article, devs are explaining how they do this: https://substance3d.adobe.com/magazine/ ... rs-gate-3/

Can I ask you one more question? Currently, the model I want to extract is the creature model. However, as I mentioned before, some of the creature models lack the texture to apply to the meshes. Textures corresponding to some weapons or items were not extracted at all. Should I apply shaders to the meshes of monsters and weapons the way you told me? Or is it a problem with the tool itself that the texture corresponding to the mesh of monsters or weapons is not being extracted?
## Post #489
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-09-02T13:40:02+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from uroborostestsubject ↑Sat Sep 02, 2023 8:14 pm at Sat Sep 02, 2023 8:14 pm
>
> 
Tosyk wrote: ↑Sat Sep 02, 2023 3:09 pm
uroborostestsubject wrote: ↑Sat Sep 02, 2023 2:31 pm


Thank you for your answer. In my case, the texture itself to be applied to the extracted meshes is lacking. For example, there is a texture that needs to be applied to the torso, but there is no texture to apply to the head and legs. Would there still be any missing textures in the virtual texture folder in this case?

body, head, eye textures are different case. they are mix of masks from textures: _HMVY, _CLEA, _MSK. In this article, devs are explaining how they do this: https://substance3d.adobe.com/magazine/ ... rs-gate-3/


Can I ask you one more question? Currently, the model I want to extract is the creature model. However, as I mentioned before, some of the creature models lack the texture to apply to the meshes. Textures corresponding to some weapons or items were not extracted at all. Should I apply shaders to the meshes of monsters and weapons the way you told me? Or is it a problem with the tool itself that the texture corresponding to the mesh of monsters or weapons is not being extracted?once again. Most of the textures are virtual textures. You need to extract them to get all the textures you want - they are there. As for creatures I think they share the same shader technique as characters from _HMVY, _CLEA, _MSK mixing
## Post #490
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2023-09-02T13:46:03+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Tosyk ↑Sat Sep 02, 2023 9:40 pm at Sat Sep 02, 2023 9:40 pm
>
> 
uroborostestsubject wrote: ↑Sat Sep 02, 2023 8:14 pm
Tosyk wrote: ↑Sat Sep 02, 2023 3:09 pm

body, head, eye textures are different case. they are mix of masks from textures: _HMVY, _CLEA, _MSK. In this article, devs are explaining how they do this: https://substance3d.adobe.com/magazine/ ... rs-gate-3/


Can I ask you one more question? Currently, the model I want to extract is the creature model. However, as I mentioned before, some of the creature models lack the texture to apply to the meshes. Textures corresponding to some weapons or items were not extracted at all. Should I apply shaders to the meshes of monsters and weapons the way you told me? Or is it a problem with the tool itself that the texture corresponding to the mesh of monsters or weapons is not being extracted?
once again. Most of the textures are virtual textures. You need to extract them to get all the textures you want - they are there. As for creatures I think they share the same shader technique as characters from _HMVY, _CLEA, _MSK mixing

Thank you so much! I'll have to try it again.
## Post #491
- Username: JKerman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Feb 06, 2021 7:02 am
- Post datetime: 2023-09-08T04:27:24+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Can someone post a copy of the 64 bit version of the granny2 dll? I don't have it, and none of my games do either.
## Post #492
- Username: yukutan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 08, 2023 11:01 pm
- Post datetime: 2023-09-08T16:12:05+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Tosyk ↑Sun Aug 27, 2023 8:53 pm at Sun Aug 27, 2023 8:53 pm
>
> 
it works pretty well with Baldur's Gate 3 characters. I must also note that this is the only tool that converts BG3 models properly with skeleton.

I am trying to find Laezel and Astarion, I have noesis working and I have extracted the game fileswith LSlib, but I'm new to working with models, is there a specific folder or filename type I should be looking for to get the character models...? Thank you very much in advance
## Post #493
- Username: JKerman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Feb 06, 2021 7:02 am
- Post datetime: 2023-09-09T05:13:02+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

I'm getting this error when I try to open a file from BG3 in noesis:

Detected file type: GR2 Reader
Traceback (most recent call last):
  File "C:\Users\XX\Downloads\noesisv4471 (1)\plugins\python\fmt_GR2reader135.py", line 5199, in noepyLoadModel
    Models = GR2Reader(data)  
  File "C:\Users\XX\Downloads\noesisv4471 (1)\plugins\python\fmt_GR2reader135.py", line 4204, in GR2Reader
    TempAllDecompressedData = GR2decompress(DecompressedData,ComperesedData,section.decompressed_size,section.data_size,section)
  File "C:\Users\XX\Downloads\noesisv4471 (1)\plugins\python\fmt_GR2reader135.py", line 4022, in GR2decompress
    lib = ctypes.WinDLL(DLL_PATH + "granny2.dll")
  File "C:\Users\XX\Downloads\noesisv4471 (1)\Plugins\python\core321.zip\ctypes\__init__.py", line 340, in __init__
WindowsError: [Error 193] %1 is not a valid Win32 application
## Post #494
- Username: feldarzt
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 10, 2023 12:09 am
- Post datetime: 2023-09-10T04:20:01+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Wow.
How did you get that model textured? When I'm opening BG3 models in Noesis with the plugin and granny2.dll, I get them with 0 textures associated. 


> Reply from Tosyk ↑Sun Aug 27, 2023 8:53 pm at Sun Aug 27, 2023 8:53 pm
>
> 
it works pretty well with Baldur's Gate 3 characters. I must also note that this is the only tool that converts BG3 models properly with skeleton.
## Post #495
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-09-10T06:04:46+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from feldarzt ↑Sun Sep 10, 2023 12:20 pm at Sun Sep 10, 2023 12:20 pm
>
> 
Wow.
How did you get that model textured? When I'm opening BG3 models in Noesis with the plugin and granny2.dll, I get them with 0 textures associated. 

Tosyk wrote: ↑Sun Aug 27, 2023 8:53 pm
it works pretty well with Baldur's Gate 3 characters. I must also note that this is the only tool that converts BG3 models properly with skeleton.I use this tool to find connection between resources: 
[https://github.com/ShinyHobo/BG3-Modders-Multitool](https://github.com/ShinyHobo/BG3-Modders-Multitool)

But there’s no way to just open model with all the texture applied. It’s manual work to convert textures and combine models
## Post #496
- Username: feldarzt
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 10, 2023 12:09 am
- Post datetime: 2023-09-10T06:45:57+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Sorry if I'm being annoying. I kinda lack experience with the BG3's way of storing models and textures. 

I tried using the Modders Multitool too. When I open the model in its object explorer, I only get the model files listed as being used in the "whole" model, and no textures are mentioned or shown in the 3D preview window. Am I looking in the wrong place or doing something wrong? 

Also... When you mention "manual work to convert textures", do you mean like saturating those weird maps "hidden" in the channels of HMVY textures with appropriate colors and so on? If so, is there a simpler way of doing it rather than photoshopping them and trying to pick the colors necessary by guesswork?


> Reply from Tosyk ↑Sun Sep 10, 2023 2:04 pm at Sun Sep 10, 2023 2:04 pm
>
> 
feldarzt wrote: ↑Sun Sep 10, 2023 12:20 pm
Wow.
How did you get that model textured? When I'm opening BG3 models in Noesis with the plugin and granny2.dll, I get them with 0 textures associated. 

Tosyk wrote: ↑Sun Aug 27, 2023 8:53 pm
it works pretty well with Baldur's Gate 3 characters. I must also note that this is the only tool that converts BG3 models properly with skeleton.



I use this tool to find connection between resources: 
https://github.com/ShinyHobo/BG3-Modders-Multitool

But there’s no way to just open model with all the texture applied. It’s manual work to convert textures and combine models
## Post #497
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-09-10T16:26:37+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from feldarzt ↑Sun Sep 10, 2023 2:45 pm at Sun Sep 10, 2023 2:45 pm
>
> 
Sorry if I'm being annoying. I kinda lack experience with the BG3's way of storing models and textures. 

I tried using the Modders Multitool too. When I open the model in its object explorer, I only get the model files listed as being used in the "whole" model, and no textures are mentioned or shown in the 3D preview window. Am I looking in the wrong place or doing something wrong?characters are using 3 types of texture: skin, eye, clothes. Skin is under the HMVY+CLEA maps, eye is also using a complex shading system, clothes are using virtual textures - you have to manually unpack them first, then look for the textures cuz there are no names. Most of the textures are virtual textures. However, there's a way to name these virtual textures after unpack with [this script](https://discord.com/channels/379359299291578372/905788029107585024/1143662604850573382). After renaming, you'll be able to find corresponding textures by model name, most of the time. Sometimes, female model HUM_F_ uses male's texture named like HUM_M_ etc

> Reply from feldarzt ↑Sun Sep 10, 2023 2:45 pm at Sun Sep 10, 2023 2:45 pm
>
> Also... When you mention "manual work to convert textures", do you mean like saturating those weird maps "hidden" in the channels of HMVY textures with appropriate colors and so on? If so, is there a simpler way of doing it rather than photoshopping them and trying to pick the colors necessary by guesswork?I'm afraid there's no way to AUTO do things. Having the list of models is already a huge gift.

I hope it does make sense.

p.s.: if you want a specific model, check [my deviant page](https://www.deviantart.com/tosyk), maybe you'll find there what you need.
## Post #498
- Username: feldarzt
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 10, 2023 12:09 am
- Post datetime: 2023-09-10T21:15:13+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Yep, that makes sense to me. Thanks a lot for the explanation! It's always great to have someone experienced to show you the ropes 

Also, that's a great DA page! 


> Reply from Tosyk ↑Mon Sep 11, 2023 12:26 am at Mon Sep 11, 2023 12:26 am
>
> 
feldarzt wrote: ↑Sun Sep 10, 2023 2:45 pm
Sorry if I'm being annoying. I kinda lack experience with the BG3's way of storing models and textures. 

I tried using the Modders Multitool too. When I open the model in its object explorer, I only get the model files listed as being used in the "whole" model, and no textures are mentioned or shown in the 3D preview window. Am I looking in the wrong place or doing something wrong?characters are using 3 types of texture: skin, eye, clothes. Skin is under the HMVY+CLEA maps, eye is also using a complex shading system, clothes are using virtual textures - you have to manually unpack them first, then look for the textures cuz there are no names. Most of the textures are virtual textures. However, there's a way to name these virtual textures after unpack with this script. After renaming, you'll be able to find corresponding textures by model name, most of the time. Sometimes, female model HUM_F_ uses male's texture named like HUM_M_ etc
feldarzt wrote: ↑Sun Sep 10, 2023 2:45 pmAlso... When you mention "manual work to convert textures", do you mean like saturating those weird maps "hidden" in the channels of HMVY textures with appropriate colors and so on? If so, is there a simpler way of doing it rather than photoshopping them and trying to pick the colors necessary by guesswork?I'm afraid there's no way to AUTO do things. Having the list of models is already a huge gift.

I hope it does make sense.

p.s.: if you want a specific model, check my deviant page, maybe you'll find there what you need.
## Post #499
- Username: Ecthelia
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 17, 2023 7:40 am
- Post datetime: 2023-09-17T07:49:35+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Tosyk ↑Mon Sep 11, 2023 12:26 am at Mon Sep 11, 2023 12:26 am
>
> 
characters are using 3 types of texture: skin, eye, clothes. Skin is under the HMVY+CLEA maps, eye is also using a complex shading system, clothes are using virtual textures - you have to manually unpack them first, then look for the textures cuz there are no names. Most of the textures are virtual textures. However, there's a way to name these virtual textures after unpack with this script. After renaming, you'll be able to find corresponding textures by model name, most of the time. Sometimes, female model HUM_F_ uses male's texture named like HUM_M_ etc

The link you posted for the script doesn't work if you aren't in that discord. Would you mind posting it here? Or if it's a public server, would you share an invite link?


Thanks so much!
## Post #500
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-09-17T22:35:43+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

> Reply from Ecthelia ↑Sun Sep 17, 2023 3:49 pm at Sun Sep 17, 2023 3:49 pm
>
> 
Tosyk wrote: ↑Mon Sep 11, 2023 12:26 am
characters are using 3 types of texture: skin, eye, clothes. Skin is under the HMVY+CLEA maps, eye is also using a complex shading system, clothes are using virtual textures - you have to manually unpack them first, then look for the textures cuz there are no names. Most of the textures are virtual textures. However, there's a way to name these virtual textures after unpack with this script. After renaming, you'll be able to find corresponding textures by model name, most of the time. Sometimes, female model HUM_F_ uses male's texture named like HUM_M_ etc


The link you posted for the script doesn't work if you aren't in that discord. Would you mind posting it here? Or if it's a public server, would you share an invite link?


Thanks so much!right, here is the invite:
[https://discord.gg/Ne7hfCRj](https://discord.gg/Ne7hfCRj)
## Post #501
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-09-19T19:41:35+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

OK. I keep getting PM's about "Encrypted Files" and how to break into them.
I'm not going to tell you how I can get all the meshes and stuff but I'll tell you this.
They are NOT encrypted!!!! All the information is there!

Here's what happens...........
On export from, say 3D Max, there is options to NOT include information. Like Model name, mesh names, and so on.
Granny Viewer and most other Tools look for the names and such. If not there? You'll see nothing, get nothing!

This seems limited to Metin2 files so far.
## Post #502
- Username: Jawwad
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 16, 2021 12:25 am
- Post datetime: 2023-09-22T20:13:14+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Hello


someone know how to fix this?
## Post #503
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-09-22T23:00:58+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Not enough information to go by.
What Game files? What granny2.dll. And Why version 121 of the script?
## Post #504
- Username: Milkage
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 25, 2023 6:43 pm
- Post datetime: 2023-09-24T12:50:37+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Any idea which part of the hex code is the model list?
## Post #505
- Username: feldarzt
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 10, 2023 12:09 am
- Post datetime: 2023-09-25T12:44:30+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Looks like the invite has expired 
Could you give us another one? I'd love to get that script.

> Reply from Tosyk ↑Mon Sep 18, 2023 6:35 am at Mon Sep 18, 2023 6:35 am
>
> 
Ecthelia wrote: ↑Sun Sep 17, 2023 3:49 pm
Tosyk wrote: ↑Mon Sep 11, 2023 12:26 am
characters are using 3 types of texture: skin, eye, clothes. Skin is under the HMVY+CLEA maps, eye is also using a complex shading system, clothes are using virtual textures - you have to manually unpack them first, then look for the textures cuz there are no names. Most of the textures are virtual textures. However, there's a way to name these virtual textures after unpack with this script. After renaming, you'll be able to find corresponding textures by model name, most of the time. Sometimes, female model HUM_F_ uses male's texture named like HUM_M_ etc


The link you posted for the script doesn't work if you aren't in that discord. Would you mind posting it here? Or if it's a public server, would you share an invite link?


Thanks so much!
right, here is the invite:
https://discord.gg/Ne7hfCRj
## Post #506
- Username: feldarzt
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 10, 2023 12:09 am
- Post datetime: 2023-09-26T12:09:51+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Heck, those so-called virtual textures blow my mind.

Does anyone understand how are they different from the "regular" textures except for having chaotic and non-structured names and in-file placement?
## Post #507
- Username: cvaqabond
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 29, 2023 2:21 am
- Post datetime: 2023-09-28T18:24:19+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Can someone please explain to me how to do this? I've been trying for hours but I can't do it.

I am using 3dsMax 2018 and have all the necessary plugins. However, I don't know how to adapt an animation I found on the internet to a gr2 file. I tried many times in Metin2 but the result is unsuccessful. If there is anyone who can guide me step by step, I would like to thank you very much in advance.

I don't know exactly how I should implement the import and export operations. That's why my character looks like a stickman in the game.
## Post #508
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-09-28T19:00:38+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Example of the files goes a long way to help.
## Post #509
- Username: SphinxRa40
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 05, 2020 10:15 pm
- Post datetime: 2023-10-05T18:28:18+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Thanks for all your work^
Tho of all the games listed, there is sadly no support for the game Rise and Fall?
That game has a GrannySS.dll, tried both scripts and renamed the dll (for 3.5)  but no luck :/
## Post #510
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-10-06T15:25:45+00:00
- Post Title: Re: Granny .GR2 Reader plugin for Noesis

Do you have a sample model file?
The GrannySS.dll is version 2.5.0.11 so it's NOT going to work.

I'd like to check the model files with exporters I wrote.
