## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-02T08:16:48+00:00
- Post Title: Deus Ex Mankind Divided

Deus Ex Mankind Divided tools (models+cloth+hairs)

Both tools are made to work with files made by Sir Kane's extractor (renamed or not).

1. Model/cloth tool - DXMDmodel.exe

- for models, select 2 corresponding files (PRIM & BORG) and drop them onto the tool - it will make ASCII & SMD model. Both will have skeleton, but as usual, ASCII will hold all UV pairs.

- for cloth, drop APEX file onto the tool - it will make ASCII cloth with skeleton. This skeleton will be compatible with main model, but no proper bone rotations, so load main model first, and then append cloth to it.

2. PureHair tool - PureHair.exe (will also work with Tomb Raider)

Drop PHHA hair file (the biggest of 3) onto the tool - it will make ASCII & OBJ files with hair. OBJ will have edges (lines). You can build mesh of desired thickness from it. ASCII will have simple triangles built on same vertices. Its very thin, and can be improved later (if i will have time). The real game builds 2 triangles for each vertex, so it works as intended.



Hair will have submeshes:



Both main model & cloth are weighted to the skeketon:


[DXMDmodel.rar](https://xentaxbackup.github.io/file/14709_DXMDmodel.rar)
## Post #2
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-08-03T19:33:42+00:00
- Post Title: Deus Ex Mankind Divided

Sir Kane's unpacker makes a text file with the names of all the files, NameMap.txt.  However none of the names in this file even contain the word "Borg". So i'm a bit confused where we find the 'borg' files.

Edit: I figured out the answer.



This is by the internal file tag, which is stored backward. So you'll have to hexedit each file to figure out which are the right ones to use.
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-03T20:01:04+00:00
- Post Title: Deus Ex Mankind Divided

unfortunately i've never seen files made with that unpacker 

but after renaming there are 2 files with the word "weightedprim" for each skeletal model
these 2 files (inside of the engine) have types BORG (bone/rig) & PRIM (primitive)

p.s. you dont have to hexedit them, because it doesn't matter in which order you use them with the tool
## Post #4
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-08-03T20:52:00+00:00
- Post Title: Deus Ex Mankind Divided

I found an issue with the model unpacker. On the character "Ivan Berk"  (\characters\resources\secondary_characters\ivan\ivan.wl2_) The BORG/PRIM model.

It's not decoding right, you can see many vaules in the Ascii file and SMD file are unusually large:
ASCII:


SMD:


The APEX and hair work fine, and everything has worked fine for other characters so far, so must be something special about this one character.
## Post #5
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-08-03T21:23:25+00:00
- Post Title: Deus Ex Mankind Divided

Oh also seems APEX UVs are flipped from what the textures are:



not hard to fix in blender but FYI
## Post #6
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2018-08-04T15:24:52+00:00
- Post Title: Deus Ex Mankind Divided

I really can't thank you enough for the PureHair tool - it's so great to finally have the beautiful hair from RotTR!
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-04T20:17:08+00:00
- Post Title: Deus Ex Mankind Divided

..
## Post #8
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-08-04T23:10:10+00:00
- Post Title: Deus Ex Mankind Divided

> Reply from daemon1
>
> new test version to support Ivan and maybe more models of that type

Yep that worked for Ivan. many thanks.
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-05T07:45:13+00:00
- Post Title: Deus Ex Mankind Divided

ok main post updated with this version
## Post #10
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-08-06T18:46:28+00:00
- Post Title: Deus Ex Mankind Divided

It seems I've found one more problem with the exporter. 

there are some accessories that won't export anything, it just produces a 0 byte file.  for example:

characters\resources\kit_systems\male\prague_police\prag_police_accessories\prag_police_helmet_a.wl2_
characters\resources\kit_systems\male\prague_police\prag_police_accessories\prag_police_helmet_a_opened.wl2_


Also here are some views of finished models from the tool, thanks for all your efforts.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-06T19:04:49+00:00
- Post Title: Deus Ex Mankind Divided

> Reply from volfin
>
> there are some accessories that won't export anything, it just produces a 0 byte file.
these are probably static models, and this tool is only made for skeletals, which have BORG file.
## Post #12
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-08-06T20:14:12+00:00
- Post Title: Deus Ex Mankind Divided

> Reply from daemon1
>
> volfin wrote:there are some accessories that won't export anything, it just produces a 0 byte file.
these are probably static models, and this tool is only made for skeletals, which have BORG file.

yeah it seems they don't have BORG. I guess i'll see if i can hack my old importer to do them, I need the helmet to complete the police character  

Edit: actually it worked with no modification. yay!
## Post #13
- Username: ajax1313
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 02, 2018 7:03 pm
- Post datetime: 2018-08-07T16:58:38+00:00
- Post Title: Deus Ex Mankind Divided

anyone having trouble importing ? when importing from .bin in blender, models appear incomplete ?
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-08T08:30:01+00:00
- Post Title: Deus Ex Mankind Divided

> Reply from ajax1313
>
> anyone having trouble importing ? when importing from .bin in blender, models appear incomplete ?
don't import .bin in blender, why do you need that?
## Post #15
- Username: ajax1313
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 02, 2018 7:03 pm
- Post datetime: 2018-08-15T16:37:09+00:00
- Post Title: Deus Ex Mankind Divided

after some time, i figured it out. but now i'm having trouble locating model files for shadow child and other DLC characters.
## Post #16
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2018-08-15T17:22:15+00:00
- Post Title: Re: Deus Ex Mankind Divided

> Reply from ajax1313
>
> after some time, i figured it out. but now i'm having trouble locating model files for shadow child and other DLC characters.
You have to extract the folder "Deus Ex Mankind Divided\DLC\runtime\" those files will have the DLC characters.
## Post #17
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-08-15T18:23:20+00:00
- Post Title: Re: Deus Ex Mankind Divided

> Reply from ajax1313
>
> after some time, i figured it out. but now i'm having trouble locating model files for shadow child and other DLC characters.

yes I don't think you can get the DLC stuff, the unpacker doesn't handle those or probably the names file doesn't have DLC names.
## Post #18
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2018-08-30T07:56:28+00:00
- Post Title: Re: Deus Ex Mankind Divided

> Reply from volfin
>
> ajax1313 wrote:after some time, i figured it out. but now i'm having trouble locating model files for shadow child and other DLC characters.

yes I don't think you can get the DLC stuff, the unpacker doesn't handle those or probably the names file doesn't have DLC names.
Sir Kane's unpacker works fine with DLCs. They have their own Namemap after extraction and the renamer script works too so you can have all dlc models.
## Post #19
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-08-30T16:30:24+00:00
- Post Title: Re: Deus Ex Mankind Divided

> Reply from o0Crofty0o
>
> volfin wrote:ajax1313 wrote:after some time, i figured it out. but now i'm having trouble locating model files for shadow child and other DLC characters.

yes I don't think you can get the DLC stuff, the unpacker doesn't handle those or probably the names file doesn't have DLC names.
Sir Kane's unpacker works fine with DLCs. They have their own Namemap after extraction and the renamer script works too so you can have all dlc models.

Really? I didn't know that.I'll have to give it a try i guess.
## Post #20
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2019-03-17T11:33:14+00:00
- Post Title: Re: Deus Ex Mankind Divided

Hello, I need some help, I test that tool and have some problems.

I export .apx file from DEMD tool, and choose to export PRIM - DEMD Native Model (.bin), after I got vaclav.apb and vaclav.bin, when I drop vaclav.apb on DXMDmodel.exe, I got smd and ascii files with 0 bytes...
here is screen: [http://prntscr.com/mz0hn2](http://prntscr.com/mz0hn2)
when I drop only vaclav.bin I got ascii model with 600kb, but dont have smd..
here is screen: [http://prntscr.com/mz0hy3](http://prntscr.com/mz0hy3)

what Im doing wrong?
## Post #21
- Username: axtry
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 07, 2020 2:49 pm
- Post datetime: 2020-05-16T00:00:35+00:00
- Post Title: Re: Deus Ex Mankind Divided

Hello, 
I'm desperately looking for DXMD models for 3 years and I found this tutorial, but I don't understand nothing. I mean, I don't even know how to get in the first step.
1. I can't find anything like Sir Kane's extractor
2. I tried quickbms, but I have no idea how it works and what file should I select to export the stuff
3. I have 0 experience with hex editor and I didn't get it how it works from any tutorial
I really don't know what to do and nobody from xentax discord was able to help me. If anyone would be able to make more complex tutorial I would be so grateful.
## Post #22
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2020-05-16T15:15:13+00:00
- Post Title: Re: Deus Ex Mankind Divided

[https://deus-ex-3d-models.tumblr.com/](https://deus-ex-3d-models.tumblr.com/)

you can find older posts in the "Archive" section.
## Post #23
- Username: axtry
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 07, 2020 2:49 pm
- Post datetime: 2020-05-21T13:52:28+00:00
- Post Title: Re: Deus Ex Mankind Divided

> Reply from volfin ↑Sat May 16, 2020 11:15 pm at Sat May 16, 2020 11:15 pm
>
> 
https://deus-ex-3d-models.tumblr.com/

you can find older posts in the "Archive" section.

Links are not working and owner of the page is not responding + few main characters are not there at all.
## Post #24
- Username: DeepWeeb
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 12, 2019 7:13 am
- Post datetime: 2020-05-23T06:34:39+00:00
- Post Title: Re: Deus Ex Mankind Divided

I have been checking the ripping guide myself too, and I already got past DEMD database part with all the extracted files and the like.
But I'm struggling with the .prim and .borg part, as DEMD database only allows for the files to be extracted AND converted, meaning that even if I'm able to locate the files I need, I can't get them. And I really need both files for the model to be rigged.
## Post #25
- Username: axtry
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 07, 2020 2:49 pm
- Post datetime: 2020-05-28T13:17:38+00:00
- Post Title: Re: Deus Ex Mankind Divided

I have the same problem. Thanks to the databse I can locate the prim files but I have no idea how to find borg files
## Post #26
- Username: Tenshinen
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 26, 2020 6:23 am
- Post datetime: 2020-07-26T05:39:53+00:00
- Post Title: Re: Deus Ex Mankind Divided

Manually find BORG by searching NameMap.txt for the exact model you're looking at in DEMD Database. The hex string is the name of the file in your extract, and should have a GROB header.


Also what do I do with ASCII files? I want Jensen's coat but I don't know how to import it into blender?
## Post #27
- Username: XanderRomanov
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 17, 2020 10:44 pm
- Post datetime: 2020-12-17T15:13:55+00:00
- Post Title: Re: Deus Ex Mankind Divided

Hello, gentlemen. I recently decided to get myself tattoo as the one Hector Guerrero(aka Oscar Mejia) has. I started making some sketches to understand how it goes, but there are some moments which are unclear to me and I realized that my job would be way easier if I could get my hands on character's textures. But I came across the problem of not knowing how to and not being able to extract textures from the game, and studying this problem led me to this forum. I've seen you people doing such things and that's why I think you might be the right people to help. Is there anybody willing to help the artist in need, please? All I'm asking for is to get one texture of a character, and then my little dream can become true.
## Post #28
- Username: XanderRomanov
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 17, 2020 10:44 pm
- Post datetime: 2020-12-17T17:53:12+00:00
- Post Title: Re: Deus Ex Mankind Divided

Nevermind, already got it!
## Post #29
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2021-04-01T09:28:20+00:00
- Post Title: Re: Deus Ex Mankind Divided

> Reply from volfin ↑Sat May 16, 2020 11:15 pm at Sat May 16, 2020 11:15 pm
>
> 
https://deus-ex-3d-models.tumblr.com/

you can find older posts in the "Archive" section.

Hi! 
First of all wanted to thank you for the tool for Deus Ex Mankind Divided! Im a noob in this community and I´m using Sir Kane unpacker, but just after unpacking it I get an error and I cannot progress, here are screenshots of what happens, could you please help me a little?
I think that the NameMap.txt. is not getting created but I have no idea why or how to fix it.
## Post #30
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-04-05T22:13:08+00:00
- Post Title: Re: Deus Ex Mankind Divided

Is there a way to fix how the Purehair tool for the edge version of the hairs basically seperates the first vertices from the rest of the edge collections? At least this is happening with Shadow of the Tomb Raider. It makes it so that the scalp is more visible than it is supposed if there are no extra vertices going all the way to the head. You can kind of fix this by converting the edge-object to curves, selecting the first points and extruding, but it makes the lines go in wrong directions since the starting vertices are moved uniformally.

I kind of fixed the issue with the standard ponytail, but good luck doing the same with the mud hair version.
## Post #31
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2021-06-26T13:41:30+00:00
- Post Title: Re: Deus Ex Mankind Divided

> Reply from MaZTeR ↑Tue Apr 06, 2021 6:13 am at Tue Apr 06, 2021 6:13 am
>
> 
Is there a way to fix how the Purehair tool for the edge version of the hairs basically seperates the first vertices from the rest of the edge collections? At least this is happening with Shadow of the Tomb Raider. It makes it so that the scalp is more visible than it is supposed if there are no extra vertices going all the way to the head. You can kind of fix this by converting the edge-object to curves, selecting the first points and extruding, but it makes the lines go in wrong directions since the starting vertices are moved uniformally.

I kind of fixed the issue with the standard ponytail, but good luck doing the same with the mud hair version.

hey i wanted to ask, how do you actually get the .phha files that are needed for the pure hair tool? I'm trying with Rise of the Tomb Raider but DRMDumper doesn't give me any .phha files.
## Post #32
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-06-26T22:10:32+00:00
- Post Title: Re: Deus Ex Mankind Divided

> Reply from OriginOfWaves ↑Sat Jun 26, 2021 9:41 pm at Sat Jun 26, 2021 9:41 pm
>
> 
MaZTeR wrote: ↑Tue Apr 06, 2021 6:13 am
Is there a way to fix how the Purehair tool for the edge version of the hairs basically seperates the first vertices from the rest of the edge collections? At least this is happening with Shadow of the Tomb Raider. It makes it so that the scalp is more visible than it is supposed if there are no extra vertices going all the way to the head. You can kind of fix this by converting the edge-object to curves, selecting the first points and extruding, but it makes the lines go in wrong directions since the starting vertices are moved uniformally.

I kind of fixed the issue with the standard ponytail, but good luck doing the same with the mud hair version.


hey i wanted to ask, how do you actually get the .phha files that are needed for the pure hair tool? I'm trying with Rise of the Tomb Raider but DRMDumper doesn't give me any .phha files.

I'm presuming Rise works the same as Shadow, so open up the archive  that has Lara's hair (for SOTR, there's the normal ponytail and the "mudthing" hair from the Porvenir Oilfields chapter). The purehair is in the DTP folder. Then use the tool to extract the biggest file. If I remember correctly, it makes 3 different files, one is which the game uses as a reference to build the hair system made from splines that the tool converts to edges and another that turns the hair into triangular faces, which you really shouldn't use since the normals are broken and lighting goes all over the place.

I used the edge version to turn them into sheets with Blender and then add custom hair textures that I made to resemble the in-game purehair as closely as I could, though I still need to adjust it:
