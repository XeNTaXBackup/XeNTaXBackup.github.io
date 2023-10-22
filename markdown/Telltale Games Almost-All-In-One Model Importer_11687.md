## Post #1
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-07-13T05:44:10+00:00
- Post Title: Telltale Games "Almost-All-In-One" Model Importer

UPDATED 08/09/2022:
Added a whole bunch of bone and texture hashes from Sam & Max: Beyond Time and Space Remastered.
(Yes, I know I should've done this ages ago.)

This script for 3DS Max will import the models from the majority of games that Telltale Games developed, with the original bone structures and rigging information (which by the way was no fun to fix up). This is the result of a year's worth of work... Well, not entirely, I started working on this back in July 2013, left it for a few months in a half-complete state and finished it up way later.



What games will this work with? [PC, unless stated otherwise]:
Back to the Future: The Game (30th Anniversary Edition) [PS4]
Batman: The Telltale Series (Season 1) [PC / PS4]
Batman: The Enemy Within (Season 2) [PC / PS4]
Bone: Out from Boneville
Bone: The Great Cow Race
CSI: 3 Dimensions of Murder
CSI: Hard Evidence
Game of Thrones [PC / PS4]
Jurassic Park: The Game
Law & Order: Legacies
Marvel's Guardians of the Galaxy
Minecraft: Story Mode (Season 1) [PC / PS4]
Poker Night 2
Sam & Max Season 1
Sam & Max Season 2
Sam & Max Save the World (Season 1) Remastered
Sam & Max Beyond Time and Space (Season 2) Remastered
Strong Bad's Cool Game for Attractive People
Tales from the Borderlands [PC / PS4]
Telltale Texas Hold'em
Wallace & Gromit's Grand Adventures, Episodes 1-3
The Walking Dead Season 1 [PC / PS4]
The Walking Dead Season 2 [PC / PS4]
The Walking Dead: A New Frontier (Season 3) [PC / PS4]
The Walking Dead: Michonne
The Walking Dead: The Final Season (Season 4)
The Walking Dead Collection [PS4]
The Walking Dead: The Telltale Definitive Series
The Wolf Among Us [PC / PS4]
What games will this NOT work with (yet?):
Back to the Future: The Game [PC]
CSI: Deadly Intent
CSI: Fatal Conspiracy
Marvel's Guardians of the Galaxy [PS4]
Poker Night at the Inventory
Sam & Max Season 3
Tales of Monkey Island
Wallace & Gromit's Grand Adventures, Episode 4
Pretty much any non-PC/PS4 versions of the above
One of these days I'll figure out what to do with those "Version 1" games.

Decryption key for Sam & Max: Save the World Remastered:

```
ttarchext -k 92CA9A8185E46473A2BFD6D17FC6CB88995A80D8AAC297E796519FA89AD9AE95D776627FB4C4A6B9D6ECA99C6785B3DC92C49E64A0A292
```

Decryption key for Sam & Max: Beyond Time and Space Remastered:

```
ttarchext -k 92CA9A8185E46573A2BFD6D17FC6CB89995A80D8AAC297E797519FA89AD9AE95D777627FB4C4A6B9D6ECAA9C6785B3DC92C49E65A0A292
```

Important things to keep in mind:
You'll need both the *.D3DMesh and *.SKL files, which should be in the same folder. The latter should be in the "data" TTARCHs.
Any bones or texture names that are unknown will be named after the first half of their hash. If their proper names are discovered, they will be added in a future update.
Use the QuickBMS scripts supplied to convert the D3DTX files to DDS, if necessary.
[Download MaxScript](https://github.com/RandomTBush/RTB-3DSMax-Scripts/blob/main/Scripts/TelltaleGames_D3DMesh.ms) [[Older revision/backup from May 30th, 2019](https://mega.nz/file/C1w0FITJ#Ex3Pe7F7TJrWG2HNrJpXd35V2KxqXqegsYsVLPbJA24)]
[Download Hash Databases](https://github.com/RandomTBush/RTB-3DSMax-Scripts/tree/main/Scripts/TelltaleHashDBs)
[Download D3DTX to DDS QuickBMS Scripts](https://mega.nz/#!roYDQR4b!ni8LXMrb3JyInqHaWFLVHMqeL6aDdBHAkGUqAV9YVB4)
[Tip for converting PS4 D3DTX textures](https://forum.xentax.com/viewtopic.php?f=16&t=11687&start=645#p152555)

Please let me know if there are problems importing any of the models using this script, and I'll do what I can to fix it!
## Post #2
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-07-13T14:36:01+00:00
- Post Title: Telltale Games "Almost-All-In-One" Model Importer

Awesome job on this  Question though, I have The Wolf Among Us but im not sure how to extract the ttarch2 files, how would i extract them?

EDIT: I found the ttarchext that works, but it doesnt work when i add the -m command for the dds textures. Also, where are the .skl files found? :/
Nvm, think I just figured it out
## Post #3
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2014-07-14T06:37:24+00:00
- Post Title: Telltale Games "Almost-All-In-One" Model Importer

how did you get dds textures?
## Post #4
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-07-14T06:45:32+00:00
- Post Title: Telltale Games "Almost-All-In-One" Model Importer

I didn't get them yet actually, i've asked on the thread where ttarchext was posted.
## Post #5
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-07-14T08:50:54+00:00
- Post Title: Telltale Games "Almost-All-In-One" Model Importer

> Reply from pepsiguy2
>
> how did you get dds textures?I just spliced the data from the *.d3dtx into a DDS file and trimmed it to the proper resolutions.
## Post #6
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2014-07-14T08:55:33+00:00
- Post Title: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> pepsiguy2 wrote:how did you get dds textures?I just spliced the data from the *.d3dtx into a DDS file and trimmed it to the proper resolutions.

after or before the header?
## Post #7
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-07-14T13:46:40+00:00
- Post Title: Telltale Games "Almost-All-In-One" Model Importer

> Reply from pepsiguy2
>
> RandomTBush wrote:pepsiguy2 wrote:how did you get dds textures?I just spliced the data from the *.d3dtx into a DDS file and trimmed it to the proper resolutions.

after or before the header?After. The largest mipmap is stored at the end of the file. I would advise using that one TextureFinder program to find the starting offset, if you've got it.
## Post #8
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-07-14T17:42:20+00:00
- Post Title: Telltale Games "Almost-All-In-One" Model Importer

I'm confused which part to cut from the d3dtx, ive tried texturefinder, found the correct texture and offset but the file apparently doesnt have that offset in hex editor.
## Post #9
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-07-16T14:18:53+00:00
- Post Title: Telltale Games "Almost-All-In-One" Model Importer

Any help? It's been frustrating me because I want these models and they are not useful without textures :/
## Post #10
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-07-16T18:12:26+00:00
- Post Title: Telltale Games "Almost-All-In-One" Model Importer

I'm thinking of something. Maybe I can set up like what chrrox had for the PSSG script, and locate/extract DDS files that way.
## Post #11
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-07-17T06:08:58+00:00
- Post Title: Telltale Games "Almost-All-In-One" Model Importer

Oh ok thank you
## Post #12
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2014-07-17T13:19:28+00:00
- Post Title: Telltale Games "Almost-All-In-One" Model Importer

> Reply from TRDaz
>
> Any help? It's been frustrating me because I want these models and they are not useful without textures :/

I just gave up and started using Ninja Ripper/Texmod for the textures, lol.
## Post #13
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-07-17T16:37:06+00:00
- Post Title: Telltale Games "Almost-All-In-One" Model Importer

I had a few ninja ripper rips before, that I used for a model, but I feel like thats a tedious way to do it :/
## Post #14
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-07-18T21:50:40+00:00
- Post Title: Telltale Games "Almost-All-In-One" Model Importer

I've looked through the D3DTX files, and I've now added a button at the bottom of the pop-up which will allow you to convert the textures into DDS -- just re-download the script in the first post and use that. I know it works with (and will autodetect) DXT1, DXT5, and the greyscale-paletted images for the lines in The Wolf Among Us. Please inform me if you find a texture it doesn't work with -- I've only tested it with a handful of them!
## Post #15
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-07-18T22:10:01+00:00
- Post Title: Telltale Games "Almost-All-In-One" Model Importer

Thank you!! Ill test that out later, thanks for doing that!
## Post #16
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-07-18T22:33:11+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

I just did a quickfix for the script -- I swapped out the import window for the D3DTX converter for an alternative one that lets you pick and import more than one texture file at a time. Just be wary that if it finds a file that wasn't extracted correctly (which I've noticed ttarchext.exe tends to do), it'll crap itself and you'll have to force 3DS Max to shut down before it overloads. I'll try setting up a failsafe so that won't happen (my coding ain't perfect, but I think it's something to do with the ReadFixedString command), but for now just be wary of that.

(EDIT: Whoops. I goofed with the image size detection, I had the height and width values flip-flopped. This has been fixed now.)
(EDIT 2: And another quick fix which should stop inexplicable crashes.)
(EDIT 3: Seems there's a glitch with it -- don't convert over 500 textures at a time. Convert less than that, then restart 3DS Max to prevent errors.)
## Post #17
- Username: VoxBombarde
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 01, 2014 9:45 am
- Post datetime: 2014-07-20T04:08:12+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Hey RTB I've just started using the script and so far its worked with pretty much anything I've thrown at it....... except these 3 models.
These models - obj_carclassic(a/b/c) give me an error when I import them (--No "+" function for undefined) and after that it imports the bones but not the mesh.

I run 3ds max 2012 64 bit if you need to know.
I really wanted this car above everything else so I hope you can help.
[Screenshot 2014-07-19 23.00.41.png](https://xentaxbackup.github.io/file/7590_Screenshot 2014-07-19 23.00.41.png)
## Post #18
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-07-20T05:48:01+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from VoxBombarde
>
> Hey RTB I've just started using the script and so far its worked with pretty much anything I've thrown at it....... except these 3 models.
These models - obj_carclassic(a/b/c) give me an error when I import them (--No "+" function for undefined) and after that it imports the bones but not the mesh.

I run 3ds max 2012 64 bit if you need to know.
I really wanted this car above everything else so I hope you can help.I think I fixed it now. It had something to do with the hastily-done unknown-data bypass I did in the scripting (it seemed to be the exact same size in every single model I had looked at!). I rewrote it so that it actually parses it properly and I was able to import those three models. As always, re-download the script in the first post for the fixes!
## Post #19
- Username: VoxBombarde
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 01, 2014 9:45 am
- Post datetime: 2014-07-20T16:00:50+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Thanks a lot! Worked like a charm! Expect a flood of Sam and Max stuff in the SFM workshop because I think it works well with the tf2niverse.
## Post #20
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2014-07-21T04:20:41+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Am I missing something? All textures I try to convert end up as a 0kb dds file.
## Post #21
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-07-23T05:13:05+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from pepsiguy2
>
> Am I missing something? All textures I try to convert end up as a 0kb dds file.Send me one of the .D3DTX files you're trying to convert, just so I can check to see if they were exported correctly.
## Post #22
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-07-28T20:08:48+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

I've updated the scripts again. I've included a version that doesn't pre-allocate the memory so that people with 32-bit 3DS Max should be able to use it now, and after checking some files that a friend sent to me I've also updated The Walking Dead Season 2 and The Wolf Among Us's importers to accomodate any "5VSM" headers it finds.

(EDIT: And I goofed. If you downloaded it before, re-download it and it should actually work this time.)
## Post #23
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2014-08-01T10:44:24+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Trying to test the maxscript but I can't for the life of me find the .skl files off the extracted .ttarch2 files
## Post #24
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-08-01T12:21:45+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from artworkplay
>
> Trying to test the maxscript but I can't for the life of me find the .skl files off the extracted .ttarch2 filesFor The Walking Dead Season 2, they are in the WalkingDead_pc_WalkingDead20*_data.ttarch2 archive. For The Wolf Among Us, it's in Fables_pc_Fables10*_data.ttarch2. Of course, the * would be a number from 1-5.
## Post #25
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2014-08-02T00:19:41+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> artworkplay wrote:Trying to test the maxscript but I can't for the life of me find the .skl files off the extracted .ttarch2 filesFor The Walking Dead Season 2, they are in the WalkingDead_pc_WalkingDead20*_data.ttarch2 archive. For The Wolf Among Us, it's in Fables_pc_Fables10*_data.ttarch2. Of course, the * would be a number from 1-5.
I had hoped it wasn't that file (WolfAmongUs) I am getting a lenc/lua file can't be decrypted error using ttarchext to extract.


EDIT my bad. I was using the wrong syntax. data had extracted without errors now.

EDIT 2 : Maxscript works beautifully for TWAU characters with single meshes. Small UV fixes are also very easy to do. Just one texture problem for me though, when exporting  characters "ink/line" .d3dtx textures all I get is a black .dds file (no mask on the alpha if there is supposed to be one). Is there a workaround for this?
## Post #26
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2014-08-06T07:17:26+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> pepsiguy2 wrote:Am I missing something? All textures I try to convert end up as a 0kb dds file.Send me one of the .D3DTX files you're trying to convert, just so I can check to see if they were exported correctly.
[http://www.mediafire.com/download/qdra2 ... /brock.rar](http://www.mediafire.com/download/qdra2c247l2mcvq/brock.rar)

Happens with any game i try.
## Post #27
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-08-06T20:30:41+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Pfft, I should have known. It's pretty much the opposite of the last problem that was reported involving The Walking Dead Season 2 / The Wolf Among Us models. Basically, instead of having a header, these don't. This confused my clumsy scripting, so I've added another check, which will fix Poker Night 2's headerless textures at least. If anything else crashes, send me the problematic textures through a PM.

> Reply from artworkplay
>
> EDIT 2 : Maxscript works beautifully for TWAU characters with single meshes. Small UV fixes are also very easy to do. Just one texture problem for me though, when exporting  characters "ink/line" .d3dtx textures all I get is a black .dds file (no mask on the alpha if there is supposed to be one). Is there a workaround for this?It may be because they're "paletted" DDS files. I can only get them to load up correctly in Photoshop -- Paint Shop Pro and VTFEdit both won't accept it. If you would like, I can convert the lines textures into PNG and send them to ya in a PM.

But yeah. The "Layer 2" polygon groups use the line texturing instead, which for most characters has different UV mapping (hence why I doubled it up upon importing in the first place).
## Post #28
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2014-08-22T08:43:04+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

i still get a 0kb dds file, i have no idea what im doing wrong. even on the textures i uploaded for you. what the hell? Im using max 2014 if it matters.
## Post #29
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-08-22T20:27:41+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from pepsiguy2
>
> i still get a 0kb dds file, i have no idea what im doing wrong. even on the textures i uploaded for you. what the hell? Im using max 2014 if it matters.I... really don't know. I'll have to pick up a later version of 3DS Max (I've only got 2009 and 2010) and check for myself, I think they may not read the MaxScript write coding properly...

(EDIT: I have come to the conclusion that later versions of 3DS Max are royally screwed up. It just won't work in 2013 or 2015, no matter what I do... You might have to locate an earlier version (pre-2012?) of 3DS Max for this right now, I have honestly no way of knowing how to fix this. Sorry...)
## Post #30
- Username: Cappu
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 06, 2014 12:10 am
- Post datetime: 2014-10-08T12:23:09+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Sometimes models are composed of multiple parts/meshes (head, legs, etc.) it is possible to import multiple files at once?

The script works great! good job!
## Post #31
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-10-08T16:47:09+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Cappu
>
> Sometimes models are composed of multiple parts/meshes (head, legs, etc.) it is possible to import multiple files at once?

The script works great! good job!I could try writing up a separate importing function soon, which'll allow you to pick the bone structure first and then all of the bodygroups you want to import in a separate popup afterwards. I should be able to get that done sometime in the next few days.
## Post #32
- Username: jmgg
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Sep 16, 2013 4:20 am
- Post datetime: 2014-11-25T11:35:03+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

I have tried import models fromTelltale Texas Hold'em but 3d max not work with this files. I have imported several models from others games with success. can you fix the script or say me what I do wrong. thanks!
## Post #33
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-11-25T17:25:14+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jmgg
>
> I have tried import models fromTelltale Texas Hold'em but 3d max not work with this files. I have imported several models from others games with success. can you fix the script or say me what I do wrong. thanks!Send me one of the D3DMESH files you're using, they may be a bit different than the ones I've used.
## Post #34
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-11-25T17:38:45+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> jmgg wrote:I have tried import models fromTelltale Texas Hold'em but 3d max not work with this files. I have imported several models from others games with success. can you fix the script or say me what I do wrong. thanks!Send me one of the D3DMESH files you're using, they may be a bit different than the ones I've used.Hello, my friend, thank you very much for the great work, I found a file error, now upload sample
[Bone The Great Cow Race.rar](https://xentaxbackup.github.io/file/8144_Bone The Great Cow Race.rar)
## Post #35
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-11-25T22:46:46+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Yeah, the models you sent me have some differences to the ones I've got for whatever reason. I've added some additional checks into the script, and it should work for those two games at least (and at least the model you posted here for Bone). If there are any others that don't work, please send them to me so I can fix my script up some more. I'll have the updated version of the script up sometime tomorrow, I just need to fix up the rigging for 3DS Max 2013 and up first, while I'm at it.

(EDIT: Hrm, having a bit of trouble getting it working. Please stand by.)
## Post #36
- Username: Cappu
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 06, 2014 12:10 am
- Post datetime: 2014-11-27T11:35:40+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> I could try writing up a separate importing function soon
Thank you. It will be interesting. 
I found a simple way to connect the different parts of the model. The script already has the necessary functionality to do it. Just needed time to understand it.

Another question: is there a way to import an animation to 3DS MAX (or converted to bvh-format), or it is very difficult ?
## Post #37
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2014-12-03T01:15:19+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Game of Thrones support?

[Tyrion](https://www.dropbox.com/s/iduwll4xw0js6sg/GOT_Tyrion.rar?dl=0)
## Post #38
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-12-03T01:40:24+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Looks like both Tales from the Borderlands and Game of Thrones use more-or-less the same model format, which is a variant of The Wolf Among Us's (the ".SKL" setup is the exact same, for example). I'll see if I can add support for it soon, and I'll also add in the batch-importer that I've nearly forgotten about at the same time. Dunno if I can get 3DS Max 2013+ support yet, it seems kinda complex for an average user like myself to implement.

The textures, however, I'll need to research more since it's different (again) and makes the script crash when I try using it to convert 'em.
## Post #39
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2014-12-03T05:06:55+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Awesomesauce RandomTBush. Hoping for good news
## Post #40
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-12-04T05:18:55+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Most models from TftBL and GoT now work with my importer (of course, including UV mapping, bone structures and rigging), and so does the multi-D3DMesh importer for the rest of the scripts, then I'll figure out what needs to be done to get those textures converted.

Update should be available within the next few days, for sure.
## Post #41
- Username: jediyoshi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 11, 2014 3:15 pm
- Post datetime: 2014-12-04T06:00:41+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> Most models from TftBL and GoT now work with my importer (of course, including UV mapping, bone structures and rigging), and so does the multi-D3DMesh importer for the rest of the scripts, then I'll figure out what needs to be done to get those textures converted.

Update should be available within the next few days, for sure.

Sounds great. We can finally live in a world where there are Borderlands weapon models to use.
## Post #42
- Username: jmgg
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Sep 16, 2013 4:20 am
- Post datetime: 2014-12-04T07:07:14+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Awesome RandomTBush!!
## Post #43
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-12-04T23:08:30+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Scripts are now updated. Changes are as follows:
Changed the method of importing for the newer games -- it now asks for an *.SKL first (which you can skip if the models don't have 'em), and then gives you a second prompt afterwards for one or more D3DMesh files, so you can import a character and their bodygroups (or an entire scene) all at once.
Added support for importing models from Tales from the Borderlands and Game of Thrones (though not fully tested -- let me know if something errors!).
Also added another texture converter for Tales from the Borderlands and Game of Thrones (different enough from the others, can't autodetect). Doesn't work in newer 3DS Max versions for whatever reason...
Fixed SBCG4AP's importer that I accidentally broke in the previous revision.
Added some extra detection for Telltale Texas Hold-em and Bone: The Great Cow Race (or at least for the files jmgg and raykingnihong sent me). Again, let me know if it still needs fixing!
Still no proper support for 3DS Max 2013+ yet, so it'll apply the rigging to the wrong bones in those versions, sorry. I'll see if I can fix this before the year's over, but I would recommend finding an earlier version to at least import the files (which you can then save and work on in your later versions) until I get it fixed.

Download link's the same as it was before, in the first post.
## Post #44
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2014-12-04T23:38:01+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

My day just got better. Stuck at work right now so I'll have to download and check out later tonight. Big thank you for your continued work on Telltale games.
## Post #45
- Username: jediyoshi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 11, 2014 3:15 pm
- Post datetime: 2014-12-05T02:28:23+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Where does the Textures folder go exactly? Got them converted and the rigged model up but having issues getting textures auto applied. Thanks
## Post #46
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-12-05T03:12:23+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jediyoshi
>
> Where does the Textures folder go exactly? Got them converted and the rigged model up but having issues getting textures auto applied. ThanksIf you want the textures to auto-load, make a new folder called "Textures" in the same folder as the D3DMesh/SKL files (sorry, I'm a neat freak) and put the DDS files in there. Unfortunately, this only works for the older Telltale games in the list, because for whatever reason they changed it to "hashed" names in The Wolf Among Us and onward, which means you'll have to apply those textures to the models manually. If someone else can figure out how to decipher those into proper filenames, then the same thing could be done for the bone names as well.
## Post #47
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2014-12-05T08:41:48+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

The script has worked on the Borderlands models I've tried so far in Max10 (haven't looked at them all). Wondering how you extracted the Game of Thrones files though. Aluigi's ttarchext doesn't seem to support it yet (unless I'm blind on the latest version).
## Post #48
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-12-05T09:39:30+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from ssringo
>
> The script has worked on the Borderlands models I've tried so far in Max10 (haven't looked at them all). Wondering how you extracted the Game of Thrones files though. Aluigi's ttarchext doesn't seem to support it yet (unless I'm blind on the latest version).I used the key that Haoose posted [in this topic](http://forum.xentax.com/viewtopic.php?p=101225#p101225) to unpack the archives.
## Post #49
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2014-12-05T22:18:49+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Thanks for help Random. Tried a few GoT models this morning and they all imported (Max10). Will have more time over the weekend to test them out.
## Post #50
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2014-12-06T05:31:09+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Spent a bit more time with the GoT models. They're importing just fine and textures apply properly. I have run into one issue though and I'm not sure if it's an importer issue or something I can just fix myself (I'm no expert either). Here is a screen of Mira's model



As you can see, her arm is quite blocky. I also saw this on Cersei's hands.

Edit: I thought forum would scale down the image automatically. Resized it so it's not so massive but you can still see the issue.
## Post #51
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-12-06T07:50:04+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from ssringo
>
> Spent a bit more time with the GoT models. They're importing just fine and textures apply properly. I have run into one issue though and I'm not sure if it's an importer issue or something I can just fix myself (I'm no expert either). Here is a screen of Mira's model

*image*

As you can see, her arm is quite blocky. I also saw this on Cersei's hands.

Edit: I thought forum would scale down the image automatically. Resized it so it's not so massive but you can still see the issue.
That's actually how some of the models are for some reason, but the normals (which I'm not sure how to import correctly for most of the games) mask that. It's actually fairly easy to fix. Add a "Vertex Weld" modifier and put the threshold to about 0.000001 or so, just enough so that it won't weld things it's not supposed to, and then drag it underneath the "Skin" modifier. This should fix the blockiness. You'll have to do this for each polygon group individually, but it shouldn't take more than a minute.
## Post #52
- Username: Cappu
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 06, 2014 12:10 am
- Post datetime: 2014-12-06T20:28:17+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

The script works fine. I got one error while importing this file: sk54_kroger_head.d3dmesh (Tales from the Borderlands)
The error occurs on the 3ds Max 2015 and 2009.



0001.jpg (23.97 KiB) Viewed 184 times


The file that is causing the error, I attached to next post
## Post #53
- Username: Cappu
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 06, 2014 12:10 am
- Post datetime: 2014-12-06T20:29:34+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

The file.
[sk54_kroger_head.zip](https://xentaxbackup.github.io/file/8210_sk54_kroger_head.zip)
## Post #54
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-12-06T22:01:22+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Cappu
>
> The script works fine. I got one error while importing this file: sk54_kroger_head.d3dmesh (Tales from the Borderlands)
The error occurs on the 3ds Max 2015 and 2009.
*image*
The file that is causing the error, I attached to next post
Fixed it! It was due to a vertex length setup that I didn't have programmed in, re-download the script and it should import just fine now!
## Post #55
- Username: Cappu
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 06, 2014 12:10 am
- Post datetime: 2014-12-06T22:39:30+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

It works without errors. Thank you.
## Post #56
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-01-07T22:06:42+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

I've added support for Law & Order Legacies and Jurassic Park now.
## Post #57
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-03-05T04:53:44+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

I've finally found the proper values for correcting the UV mapping for Telltale's newer games (Jurassic Park/Law & Order Legacies, Poker Night 2, The Walking Dead Season 1/2, The Wolf Among Us and Tales from the Borderlands/Game of Thrones), there should be no more issues with it now. Re-download the not-even-bothered-to-be-encrypted-this-time-since-it's-pointless script for that.

If there's any other problems, let me know so I can fix it.
## Post #58
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-03-05T08:09:14+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Hi RandomTBush My friend, thank you very much for the great work
## Post #59
- Username: Nerd42
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 14, 2011 1:03 pm
- Post datetime: 2015-03-17T00:34:27+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

I'm trying to extract textures from Poker Night 2. Not models ... just textures. I guess the trouble is the d3dtx files are missing some kind of header? Will this script add that header?
## Post #60
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-03-17T00:44:52+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Nerd42
>
> I'm trying to extract textures from Poker Night 2. Not models ... just textures. I guess the trouble is the d3dtx files are missing some kind of header? Will this script add that header?
It should, yes, as long as you use the right option for it (and don't try to convert more than 500 at a time). Either way, now that I understand how QuickBMS works, I'll be writing up a conversion script for that program sometime soon, if the 3DS Max one doesn't work for you.
## Post #61
- Username: Nerd42
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 14, 2011 1:03 pm
- Post datetime: 2015-03-17T00:50:51+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> Nerd42 wrote:I'm trying to extract textures from Poker Night 2. Not models ... just textures. I guess the trouble is the d3dtx files are missing some kind of header? Will this script add that headerIt should, yes, as long as you use the right option for it (and don't try to convert more than 500 at a time). Either way, now that I understand how QuickBMS works, I'll be writing up a conversion script for that program sometime soon, if the 3DS Max one doesn't work for you.I've never used 3DS Max but I might give it a try. Looking forward to seeing your QuickBMS script! I'd be interested to see what it does, even if 3DS Max ends up working for me.

(later edit) Oh ... 3DS Max is a commercial program and pretty big. Maybe it'd be better to just wait for your QuickBMS script so I don't have to bother getting it just for this.
## Post #62
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2015-03-29T00:31:53+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Heya, so I'm also having a bit of a problem regarding the textures. I try to convert the .d3dtx files, but I end up with only 0 byte .dds files.
Any ideas what the problem could be? Using Max 2013
## Post #63
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-03-29T00:37:01+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from riccochet
>
> Heya, so I'm also having a bit of a problem regarding the textures. I try to convert the .d3dtx files, but I end up with only 0 byte .dds files.
Any ideas what the problem could be? Using Max 2013I've noticed that 3DS Max 2013 and up don't work with that texture converter for whatever reason. I'll have a QuickBMS alternative for that sometime soon, before the month's over.
## Post #64
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2015-03-29T00:39:19+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

I see, thanks for the reply.
## Post #65
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-04-20T01:43:42+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

I'm getting an error with a model from Tales from the Borderlands. I tried both episode 1 and 2 (in case something changed) and the same error pops up each time. The model is called "sk55_yvette". It's the only model that has this issue (of the 10 or so I've looked at). Here is a screen of the error that pops up after selecting the mesh and skeleton. Using Max2010

[http://i.imgur.com/WefBDeZ.png?1](http://i.imgur.com/WefBDeZ.png?1)

Edit: looks like the same issue that Cappu posted about with a different model on page 4. I can upload the mesh/skeleton if needed.
## Post #66
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2015-05-23T17:58:40+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

When I try to do the Barbasol canister parts or the Binoculars from Jurassic Park I get a "unable to convert:undefined to type interger" I'm using 3DS Max 2013, I can't find SKL files for any of the files in this ZIP. Also textures don't load for the signs. Not sure what I'm missing and would rather not go through the hassle of getting 3DS Max 2012. 
[http://www.uploadmb.com/dw.php?id=1432403163](http://www.uploadmb.com/dw.php?id=1432403163)
## Post #67
- Username: averykid
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 13, 2015 6:53 am
- Post datetime: 2015-07-12T22:56:25+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Hello!
So i have two problems with TFTBL models:
Firstly i cant see the skeletons via importing it
Its not auto-applying their textures
If i try it manually they are not fitting.

Can you help me to do these with Future Fiona & Future Rhys?
## Post #68
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2015-07-25T14:38:05+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from averykid
>
> Hello!
Its not auto-applying their textures
If i try it manually they are not fitting.

Latest version of the script should fit the textures correctly.

Small tip: Delete "Layer 2" meshes by going through Tools > New Scene Explorer... 

Those are duplicates that have no use whatsoever, this should fix the improper texture mapping.
## Post #69
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-07-25T19:29:36+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from averykid
>
> Hello!
So i have two problems with TFTBL models:
Firstly i cant see the skeletons via importing it
Its not auto-applying their textures
If i try it manually they are not fitting.

Can you help me to do these with Future Fiona & Future Rhys?
Unfortunately, I haven't figured out the auto-application of the textures in newer Telltale games. I blame the fact they went for material hashes instead of filenames like they did for their older titles. And in response to the post above, the "Layer 2" polygon groups are usually used for things like the lines on the characters from The Wolf Among Us, check the UV mapping to see if it's different or not before deleting them, they may be useful.

And as for the issues people have been having with various models, I'll fix them as soon as I'm able to. Been having a really crummy month, so I haven't felt like doing anything of the sort. Sorry.

...and I realized I never posted the QuickBMS texture converter in this topic, [here it is](https://dl.dropboxusercontent.com/u/27874399/Telltale_D3DTX.zip).
## Post #70
- Username: globan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 24, 2015 5:16 am
- Post datetime: 2015-07-25T22:03:14+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Hi,
I have been trying to get the GOT models for some time now and I was fortunate enough to find your thread and Telltale Almost-All-In-One Model Importer.
I have managed to import Tyrion (not from the game, the script window importer is desperately blank whan I select Game Of Thrones ) but from a file I found on the web ( attached link


Capture2.JPG (20.75 KiB) Viewed 99 times

).
3DS 2011 imports the model okay but  there are no textures.

Can you help me understand what I am doing wrong and how to fix my problem? I would really like to have this character.
Thank you in advance.
## Post #71
- Username: OoFiLoO
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 15, 2015 3:49 pm
- Post datetime: 2015-08-07T06:11:01+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Hi! your script is amazing.. but..
the old script release (about TWD2 series) has correct bones weights but wrong uvs.. the updated script you released has correct uvs but wrong bones weights.. can you fix it please? 
Thank you in advance
## Post #72
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-08-07T06:30:30+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

I never got a chance to incorporate that fix into the main script. I made a terrible mistake when fixing up the UV mapping for the other formats since I absent-mindedly copy-pasted the vertex information from the later, fixed games without correcting the rigging information. This revision should fix that problem:

[http://www.mediafire.com/?sxmel1ksxlkica6](http://www.mediafire.com/?sxmel1ksxlkica6)

Next time, I'll test to make sure everything's working before doing another full-scale modification like that. But anyway, now that my computer's no longer crapping out on me every few minutes, I'll start fixing the certain Jurassic Park models that won't import and the newest texture files that won't convert.
## Post #73
- Username: OoFiLoO
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 15, 2015 3:49 pm
- Post datetime: 2015-08-07T06:33:41+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> I never got a chance to incorporate that fix into the main script (I made a terrible mistake when fixing up the UV mapping for the other formats), but this should fix that problem:

http://www.mediafire.com/?sxmel1ksxlkica6

Now that my computer's no longer crapping out on me every few minutes, I'll start fixing the certain Jurassic Park models and the newest texture files not working right.

Thank you very much!!
So i have to use that hotfix as a standalone script?
## Post #74
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-08-07T07:57:42+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from OoFiLoO
>
> RandomTBush wrote:I never got a chance to incorporate that fix into the main script (I made a terrible mistake when fixing up the UV mapping for the other formats), but this should fix that problem:

http://www.mediafire.com/?sxmel1ksxlkica6

Now that my computer's no longer crapping out on me every few minutes, I'll start fixing the certain Jurassic Park models and the newest texture files not working right.

Thank you very much!!
So i have to use that hotfix as a standalone script?You can use that script for now as a replacement until I update the main script. I don't think I broke anything else by fixing the TWD2 importing problems.
## Post #75
- Username: OoFiLoO
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 15, 2015 3:49 pm
- Post datetime: 2015-08-07T10:15:34+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> OoFiLoO wrote:RandomTBush wrote:I never got a chance to incorporate that fix into the main script (I made a terrible mistake when fixing up the UV mapping for the other formats), but this should fix that problem:

http://www.mediafire.com/?sxmel1ksxlkica6

Now that my computer's no longer crapping out on me every few minutes, I'll start fixing the certain Jurassic Park models and the newest texture files not working right.

Thank you very much!!
So i have to use that hotfix as a standalone script?You can use that script for now as a replacement until I update the main script. I don't think I broke anything else by fixing the TWD2 importing problems.

Works perfectly! Again Thank you very much!
## Post #76
- Username: averykid
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 13, 2015 6:53 am
- Post datetime: 2015-08-19T19:50:30+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

what can i do with this error? Happens with TFTBL Yvette & Springs!
## Post #77
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-10-17T08:57:53+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from ssringo
>
> I'm getting an error with a model from Tales from the Borderlands. I tried both episode 1 and 2 (in case something changed) and the same error pops up each time. The model is called "sk55_yvette". It's the only model that has this issue (of the 10 or so I've looked at). Here is a screen of the error that pops up after selecting the mesh and skeleton. Using Max2010

http://i.imgur.com/WefBDeZ.png?1

Edit: looks like the same issue that Cappu posted about with a different model on page 4. I can upload the mesh/skeleton if needed.
> Reply from averykid
>
> 
what can i do with this error? Happens with TFTBL Yvette & Springs!Sorry for the wait, but both of these issues should now be fixed with the model-importing script (and both stemmed from the same problem of me being a dumb fart and forgetting to set up some arrays correctly). And I also added support for Minecraft: Story Mode... I know someone'd want those at least.

Speaking of, I've fixed the respective texture-extraction script since Telltale inexplicably changed some things around in the later episodes.

[http://www.mediafire.com/?6m509o6ynr4zsgf](http://www.mediafire.com/?6m509o6ynr4zsgf)

...I'm still looking into fixing the Jurassic Park / Law & Order: Legacies part of the importer, turns out there's more issues with that script than I thought...
## Post #78
- Username: mtmb
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 11, 2015 3:42 pm
- Post datetime: 2015-10-17T18:32:52+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

everything works fine! 
Vasquez has blocky face and same w/ Yvette's skirt, fixed via Vertex Weld.
thank you!!
 
btw some "detail" textures exporting all black, w/ almost invisible lines, in any way. For example ["sk55_fiona_hatHair_detail"](http://s013.radikal.ru/i325/1510/1c/19f9e736039c.png)
is there a way to fix it somewhere in graphic editors?
thanks again!
## Post #79
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-10-17T18:52:39+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from mtmb
>
> btw some "detail" textures exporting all black, w/ almost invisible lines, in any way. For example "sk55_fiona_hatHair_detail"
is there a way to fix it somewhere in graphic editors?
thanks again!Ah, for that, the lines are stored in the alpha channel for the detail texture. Just split that into a separate image and you should have [something like this](http://i.imgur.com/mGLPyan.png).
## Post #80
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-10-19T10:20:32+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Just posting to say that I've almost gotten the model formatting down for the Back to the Future: The Game models... but only for the ones from the 30th Anniversary edition on the Xbox 360, since those are using a variation on the format used for Tales from the Borderlands and Game of Thrones this time, and not the buggery format in the PC version that they also used for Wallace & Gromit, Tales of Monkey Island and Sam & Max Season 3. I still haven't figured those out yet.



Just need to figure out how the bone weights are stored, first, then I'll add support for that to the script set.

(EDIT: And I'm stuck. Even doing a direct comparison between the same model from both the PC and Xbox 360 models from Tales from the Borderlands side-by-side, I still can't tell how the bone weights are set up...)


Left section is for PC, right is for Xbox 360. 0x10-0x17 correspond to the bone weights on the PC version (short / 65535 = weight), but I can't figure out the 360 version's (0x0C-0x0F, I think, the bone IDs are right before 'em for both). If anyone can help me with that, I would really appreciate it!)

(EDIT 2: Shucks. So much for getting fully-functional support for that game done by October 21st. Outta time.)
## Post #81
- Username: tetTris11
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 25, 2015 4:54 pm
- Post datetime: 2015-10-25T09:14:51+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

could I have a bit of help? i'm having a few problems with it, i'm trying to extract some of the poker night 2 models (mostly the portal 2 claptrap model/skin) the problems i'm getting is upon extracting 5_cpoker2_pc_txmesh i didn't get any .skl files, i'm also not entirely sure how to go about the textures, from looking through the thread there's supposedly meant to be a button at the bottom of the pop-up which isn't there for me, sorry i'm not very good at this sort of stuff :\
## Post #82
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-10-25T15:22:25+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from tetTris11
>
> could I have a bit of help? i'm having a few problems with it, i'm trying to extract some of the poker night 2 models (mostly the portal 2 claptrap model/skin) the problems i'm getting is upon extracting 5_cpoker2_pc_txmesh i didn't get any .skl files, i'm also not entirely sure how to go about the textures, from looking through the thread there's supposedly meant to be a button at the bottom of the pop-up which isn't there for me, sorry i'm not very good at this sort of stuff :\The .SKL files you're looking for are in 2_cpoker2_pc_data.ttarch, and don't worry about the old 3DS Max texture converter entirely since the QuickBMS script (Telltale_D3DTX_PN2_TWD_TWAU.bms) works better anyway, use that script on the .D3DTX files and it should convert them to .DDS.

...But now that you mention it, I actually had to go fix something with that script. Redownload before using it to import the models, I accidentally made the same mistake that I made with The Walking Dead Season 2's models earlier and didn't notice.
## Post #83
- Username: tetTris11
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 25, 2015 4:54 pm
- Post datetime: 2015-10-26T06:18:58+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> tetTris11 wrote:could I have a bit of help? i'm having a few problems with it, i'm trying to extract some of the poker night 2 models (mostly the portal 2 claptrap model/skin) the problems i'm getting is upon extracting 5_cpoker2_pc_txmesh i didn't get any .skl files, i'm also not entirely sure how to go about the textures, from looking through the thread there's supposedly meant to be a button at the bottom of the pop-up which isn't there for me, sorry i'm not very good at this sort of stuff :\The .SKL files you're looking for are in 2_cpoker2_pc_data.ttarch, and don't worry about the old 3DS Max texture converter entirely since the QuickBMS script (Telltale_D3DTX_PN2_TWD_TWAU.bms) works better anyway, use that script on the .D3DTX files and it should convert them to .DDS.

...But now that you mention it, I actually had to go fix something with that script. Redownload before using it to import the models, I accidentally made the same mistake that I made with The Walking Dead Season 2's models earlier and didn't notice.

thanks, the only problem i'm getting now is quickbms doesn't like the .bms script, or it doesn't like the texture i'm not too sure, the error it spat out was:
Error: [myfseek] the offset 0xa2420315 in the file 0 can't be reached
Last script line before the error or that produced the error:
34 goto texnamelength 0 SEEK_CUR
## Post #84
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-10-26T15:07:26+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from tetTris11
>
> RandomTBush wrote:tetTris11 wrote:could I have a bit of help? i'm having a few problems with it, i'm trying to extract some of the poker night 2 models (mostly the portal 2 claptrap model/skin) the problems i'm getting is upon extracting 5_cpoker2_pc_txmesh i didn't get any .skl files, i'm also not entirely sure how to go about the textures, from looking through the thread there's supposedly meant to be a button at the bottom of the pop-up which isn't there for me, sorry i'm not very good at this sort of stuff :\The .SKL files you're looking for are in 2_cpoker2_pc_data.ttarch, and don't worry about the old 3DS Max texture converter entirely since the QuickBMS script (Telltale_D3DTX_PN2_TWD_TWAU.bms) works better anyway, use that script on the .D3DTX files and it should convert them to .DDS.

...But now that you mention it, I actually had to go fix something with that script. Redownload before using it to import the models, I accidentally made the same mistake that I made with The Walking Dead Season 2's models earlier and didn't notice.

thanks, the only problem i'm getting now is quickbms doesn't like the .bms script, or it doesn't like the texture i'm not too sure, the error it spat out was:
Error: [myfseek] the offset 0xa2420315 in the file 0 can't be reached
Last script line before the error or that produced the error:
34 goto texnamelength 0 SEEK_CURSend me the file and I'll take a look, perhaps it's got a different header compared to the ones I've got.

(EDIT: Actually, it was because I goofed with translating the script from MaxScript to QuickBMS, it's fixed now.)
## Post #85
- Username: Yhrite
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 31, 2015 9:50 pm
- Post datetime: 2015-10-31T13:55:38+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

All the "adv_" textures I try and convert from Tales from the Borderlands always seem to output like this

I wasn't sure if this is a type of texture that just can't be converted or if it might just be a bug with the .bms script?
## Post #86
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-10-31T17:54:10+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

No, that's correct. That's a lightmap texture, those would be used with the Layer 2 polygon groups for area models.
## Post #87
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2015-11-02T21:32:33+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Somebody please tell me how to get SKL and D3DMesh files?
## Post #88
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-11-02T22:37:33+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from lyutor1945
>
> Somebody please tell me how to get SKL and D3DMesh files?Already mentioned it a few times earlier. The D3DMesh and D3DTX files are in the archives with "txmesh" at the end, and the SKL files are in the archives that have "data" as the suffix. Use TTArchExt to extract 'em.
## Post #89
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2015-11-02T23:07:28+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> lyutor1945 wrote:Somebody please tell me how to get SKL and D3DMesh files?Already mentioned it a few times earlier. The D3DMesh and D3DTX files are in the archives with "txmesh" at the end, and the SKL files are in the archives that have "data" as the suffix. Use TTArchExt to extract 'em.
Can you tell me a bit about how to do this and a link to a working extractor, if possible.
## Post #90
- Username: tetTris11
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 25, 2015 4:54 pm
- Post datetime: 2015-11-03T06:40:34+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

ha! got it going now (forgot to mention earlier)

do you think you might have anything for Maya? i'm not a 3DsMAX user but i have it in case, directly exporting a model to a .FBX causes Maya to crash, iv tried this with both 2013 and 2012 versions of Maya, exporting the model into a .SMD and re-importing then exporting as a .FBX seems to work but it doesn't work for TFTBL models, when i export the model as the .SMD and re-import it the mesh doesn't show up, and exporting, re-importing and exporting again with other formats doesn't seem to work
## Post #91
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2015-11-05T12:07:35+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Hey RTB, is it possible for you to check the UV mapping with Minecraft: Story Mode? All the models seems to have the need to be re-mapped (which gives a horrible result).

Using 3DS Max 2009 if that helps.
## Post #92
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2015-11-13T08:22:21+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Hi, everyone!! The models from "The wolf among us" and "Game of Thrones"  extracted excellent, but I have a problem with "Tale from the borderlands" models. Some of them are not opened and receive this error.Maybe somebody knows how to fix it?
## Post #93
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2015-11-14T12:26:03+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from lyutor1945
>
> Hi, everyone!! The models from "The wolf among us" and "Game of Thrones"  extracted excellent, but I have a problem with "Tale from the borderlands" models. Some of them are not opened and receive this error.Maybe somebody knows how to fix it?

-snip-

From what source did you download the game? Is it the untouched Steam ones or is it the repack?
## Post #94
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2015-11-14T19:23:33+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from meganmi
>
> lyutor1945 wrote:Hi, everyone!! The models from "The wolf among us" and "Game of Thrones"  extracted excellent, but I have a problem with "Tale from the borderlands" models. Some of them are not opened and receive this error.Maybe somebody knows how to fix it?

-snip-

From what source did you download the game? Is it the untouched Steam ones or is it the repack?

Repaсk. Do you think the problems in this?
## Post #95
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2015-11-15T14:53:34+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from lyutor1945
>
> meganmi wrote:lyutor1945 wrote:Hi, everyone!! The models from "The wolf among us" and "Game of Thrones"  extracted excellent, but I have a problem with "Tale from the borderlands" models. Some of them are not opened and receive this error.Maybe somebody knows how to fix it?

-snip-

From what source did you download the game? Is it the untouched Steam ones or is it the repack?

Repaсk. Do you think the problems in this?

Yes.

That's why I never download Repacks, they change some of the file's data and that's why they never import correctly.
## Post #96
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-11-15T16:11:21+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from meganmi
>
> Yes.

That's why I never download Repacks, they change some of the file's data and that's why they never import correctly.I'm not sure it's because of that. I had a repacked download of Tales from the Borderlands for model research before I was gifted it on Steam, and the model files seemed to be the same (I did have to change the texture converter, but that might've been Telltale updating the format mid-season).

Send me what you've got and I'll take a look and see what went wrong.
## Post #97
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2015-11-17T13:47:21+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Here is the issue I was referring to.
[MCSM_Olivia.rar](https://xentaxbackup.github.io/file/10032_MCSM_Olivia.rar)
## Post #98
- Username: radtad
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 07, 2015 1:26 pm
- Post datetime: 2015-12-07T05:30:19+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Okay so I'm trying to apply a texture to a GOT model..I used the script to turn the d3d into dds but this comes up when I try to apply it to the part of the model..
## Post #99
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-01-13T00:32:31+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Seems like I've fixed the UV mapping for Minecraft: Story Mode now, Telltale changed it all of a sudden to outright use half-float values instead of the way they had it before (multiplying the short values by a separate modifier).


Re-download the script to fix that problem. Sorry for the wait, November/December was pretty taxing for me outside of my hobbies.
## Post #100
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2016-01-16T11:43:48+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> Seems like I've fixed the UV mapping for Minecraft: Story Mode now, Telltale changed it all of a sudden to outright use half-float values instead of the way they had it before (multiplying the short values by a separate modifier).
-snip-

Re-download the script to fix that problem. Sorry for the wait, November/December was pretty taxing for me outside of my hobbies.

It's alright, I know you're a pretty busy person.   thanks for fixing it!
## Post #101
- Username: CrizArtEX
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 15, 2016 2:12 am
- Post datetime: 2016-01-20T17:27:50+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Well, i noticed that .d3dtx files converted to .dds would take with bad result, the image seen corrupt. But Some files Minecraft: Story Mode would work 100% converting to .dds. But some way, ¿what will i do for fix this? i want convert to .dds all .d3dtx files. 

I tried using QuickBMS for it.

Sorry for my english 

Here an example:
[skM1_jesse.png](https://xentaxbackup.github.io/file/10341_skM1_jesse.png)
## Post #102
- Username: fodrom
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 28, 2016 1:06 am
- Post datetime: 2016-02-28T13:10:44+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Heh! Thanks man, thats very cool!
I was suffering when I ripped models with 3d-Ripper. 
Two questions.
You will be modify the script for TWD-Michonne? 
How import files  3dmesh to 3dsMax if they haven't skl files?
## Post #103
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-02-28T18:25:12+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from fodrom
>
> Heh! Thanks man, thats very cool!
I was suffering when I ripped models with 3d-Ripper. 
Two questions.
You will be modify the script for TWD-Michonne? 
How import files  3dmesh to 3dsMax if they haven't skl files?
1. I'm working on the importer for The Walking Dead: Michonne, but Telltale changed the format up a whole lot again so it's gonna take longer than expected.
2. If the model you want to import doesn't have an .SKL file to go with it, simply cancel the first window, and then pick the models on the second window.
## Post #104
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-04-05T17:49:52+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Updated the script again, Tydeus informed me that there were some The Walking Dead Season 1 / 300 Days models that were broken, thankfully that was an easy fix (I goofed with one of the vertex buffer setups). This should fix the rigging issues with characters like Dan, David and Justin in particular (and probably a few others).
## Post #105
- Username: Eredus
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 08, 2015 7:39 pm
- Post datetime: 2016-04-21T16:33:55+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

The UVs for scene/area files for The Walking Dead season 1 have been mostly broken from what I've seen. The vertices are usually bunched up in the corner or stretched horribly in one direction or the other.

These examples are from adv_savannahsewers_meshesa.d3dmesh from episode 4: [http://i.imgur.com/n9oGHqU.jpg](http://i.imgur.com/n9oGHqU.jpg)

I'm using 3ds max 2009 64-bit to import.
## Post #106
- Username: Super Ninja Fat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 06, 2016 10:19 am
- Post datetime: 2016-05-06T02:29:33+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Hey RandomTBush, I hope this question isn't too far off topic to be disruptive to the forum:

I'm starting to make animations in Source Filmmaker of some voice overs of Sam and Max comics, and want to use locations from Telltale's Sam & Max Season One. I am using your tool to import several parts of the office, but since it is rendered out of several models, I have to piece the scene together myself. A friend told me that it might be possible to find a file in the game that places these models in their correct places.

Do you know if there is any way to import these models to place them in the way it is rendered in-game? I've already tried using 3d Ripper DX to rip a full scene of the office from the game and gave up in favor of this approach.


P.S. I'm new to messing around with TellTale's files/using 3ds max, so any kind of help would be appreciated.
## Post #107
- Username: Khellendros
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 21, 2016 7:58 pm
- Post datetime: 2016-07-21T12:05:56+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Hi guys, I found this forum through a google image search of Bossanova so I'm probably not the most informed user to mess with importing models from games.
I'm planning a cosplay (probably the biggest I'm tackling yet) of Bossanova and I'm looking for as much reference as I can.
I'm willing to learn to use modeling programs and all that but the most I've come close to 3D modeling is SketchUp.
I've already downloaded the scripts from the first post but where can I find resources to learn how to use it?

Thank you all very much



PS: My goal is to be able to export some pieces of the costume so that I could use Pepakura (best case scenario) but high res images could also do
## Post #108
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2016-08-04T08:39:13+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Perhaps this can help
[http://evgeniynoname.deviantart.com/art ... -556335626](http://evgeniynoname.deviantart.com/art/XNALara-Model-TftB-Bossanova-556335626)

Now I'm hoping for Batman support.
## Post #109
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-08-04T08:46:18+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

And if the XNALara model posted above doesn't work, I'll see what I can do about getting a rip of said model up on The Models Resource later. As for adding support for the Telltale Batman game, it's definitely on my to-do list, but I still need to get TWD:Michonne's model format figured out first (since it might be a variant of that).

(EDIT: Yep, everything for the Batman model format's changed around again, and on top of that, the header states "6VSM" instead of "5VSM". Fun.)

As for piecing together scenes, I'll be looking into adding a .SCENE importer (I think that's what it's for) later. And double-checking all of the other importers to make sure I didn't accidentally break anything else.
## Post #110
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2016-08-04T22:11:26+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Sweet! Looking forward to the new version
## Post #111
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2016-09-21T10:31:13+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

hi, just checking in to find out if there was any progress?
## Post #112
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2016-09-23T21:41:16+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from riccochet
>
> hi, just checking in to find out if there was any progress?
I can wait for batman telltale.
## Post #113
- Username: mcemily
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 12, 2016 1:40 pm
- Post datetime: 2016-11-12T06:13:01+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Thanks so much for creating this tool, RandomTBush! 

I ran into the same error that lyutor1945 reported on some Tales from the Borderlands models, "array index must be positive number, got: 0"

In my case, the model in question was Moxxi from Tales from the Borderlands. I'm using 3dsMax 2012, if that info is useful at all. 

Here's her [skl and d3dmesh file](https://drive.google.com/open?id=0B-yZUCUP3CLsZGlSVzAwdXdrYjA).
## Post #114
- Username: Dionyseuss
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 07, 2016 6:57 am
- Post datetime: 2016-11-30T20:02:27+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

I am also getting this error with Game of Thrones mobile skinned models. 

Static props import fine, but for skinned characters I just get the bones.

Any ideas about a workaround?



GoT_rig.jpg (169.33 KiB) Viewed 139 times
## Post #115
- Username: CaptainCaboose
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 02, 2016 7:45 pm
- Post datetime: 2016-12-02T11:50:33+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Ok, I am very new to 3DS max and models and that, but I have managed to get the files for game of thrones models, I am able to import the mesh and bones into 3ds max but I dont know how to import the textures, I am using 3DS max 2016, any help is appreciated
## Post #116
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2016-12-22T05:58:04+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

The Walking Dead: A New Frontier has the same header as Batman; 6VSM. 

Hey RTB, how's the script going? Any progress?
## Post #117
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2016-12-28T06:28:42+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Hopefully the release of the walking dead season 3 has sort of... rekindled this project (and hopefully there'll be an update for the Michonne game someday?). This tool is great and I'm not sure what I'd do without it.
## Post #118
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-12-28T17:52:47+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Don't worry, I haven't abandoned this script, I still have intentions to bring it up-to-date. I'll be working on it again in January.
## Post #119
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2016-12-28T21:18:07+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> Don't worry, I haven't abandoned this script, I still have intentions to bring it up-to-date. I'll be working on it again in January.
I love you mate!
## Post #120
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-01-16T00:28:24+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Question - is the next update going to be released once the importer is compatible for all the games it's not yet compatible with (Michonne, Batman, Walking Dead 3), or will it be updated for each game over time?
## Post #121
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-01-16T00:39:02+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> Question - is the next update going to be released once the importer is compatible for all the games it's not yet compatible with (Michonne, Batman, Walking Dead 3), or will it be updated for each game over time?I probably won't have 'em all ready at once, so yeah, there'll be intermittent updates for the script as each game's finished up.
## Post #122
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2017-01-17T19:51:12+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> jayko wrote:Question - is the next update going to be released once the importer is compatible for all the games it's not yet compatible with (Michonne, Batman, Walking Dead 3), or will it be updated for each game over time?I probably won't have 'em all ready at once, so yeah, there'll be intermittent updates for the script as each game's finished up.

Thanks mate! I am going waiting.
## Post #123
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-01-30T21:36:59+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Is an end-of-the-month progress report possible to keep us in the loop (even if it's just an estimated percentage or something)? 

I'm not really sure what the process is but it'd be interesting to see how updating differs between games, because it seems as if the more recent ones have been harder to crack
## Post #124
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-01-31T01:47:44+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> Is an end-of-the-month progress report possible to keep us in the loop (even if it's just an estimated percentage or something)? 

I'm not really sure what the process is but it'd be interesting to see how updating differs between games, because it seems as if the more recent ones have been harder to crackUh... I don't really have much of a progress report right now, but anyway, I've started working on the TWD: Michonne format first (again) since it seems to be less complex compared to the Batman/TWD3 one, but I'm currently scratching my head trying to figure out how the two main header information chunks are parsed this time around, it's completely different than any of the other Telltale games beforehand where it was mainly just minor changes between 'em if anything. Which means that I do indeed have to rewrite a huge chunk of the script just for those. Fun. At least the bone structures are unchanged, so that's half of the complications removed.

Overall, I'd say about 30%. More than it was earlier, but not by too much. Not planning on giving up, of course, I've had to work with much worse before.

And yeah, I'll see if I can fix the problems with some of the other models not importing correctly, too. Must be something else important I might've skimmed past with the script that's preventing them from importing correctly.

(EDIT: Subsections and hashed names everywhere, seems like things are being set up by pure nonsense as far as I'm concerned! This better not be leading me into a figurative dead-end...)
## Post #125
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-01-31T13:16:00+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> Uh... I don't really have much of a progress report right now, but anyway, I've started working on the TWD: Michonne format first (again) since it seems to be less complex compared to the Batman/TWD3 one, but I'm currently scratching my head trying to figure out how the two main header information chunks are parsed this time around, it's completely different than any of the other Telltale games beforehand where it was mainly just minor changes between 'em if anything. Which means that I do indeed have to rewrite a huge chunk of the script just for those. Fun. At least the bone structures are unchanged, so that's half of the complications removed.

Overall, I'd say about 30%. More than it was earlier, but not by too much. Not planning on giving up, of course, I've had to work with much worse before.

And yeah, I'll see if I can fix the problems with some of the other models not importing correctly, too. Must be something else important I might've skimmed past with the script that's preventing them from importing correctly.

Sounds good to me - while I don't have much of an understanding of the process, I can see it's the sort of thing with dead ends, workarounds and probably a lot of trial and error. I wish you luck with the rest of the update; hopefully there aren't too many hurdles left, and I'll have to shoot you a donation or something as thanks for your hard work... when I come into some money XD It's the least I can do considering how often I hope to use the importer.

> Reply from RandomTBush
>
> (EDIT: Subsections and hashed names everywhere, seems like things are being set up by pure nonsense as far as I'm concerned! This better not be leading me into a figurative dead-end...)

Considering what I've read about Telltale's interior workings as a company, this makes a lot of sense - they seem like a bit of a mess, apparently constantly shifting people around onto different parts of a project and letting others finish stuff off, so that might explain the problems you're having. There's all the remnants of the old setup (I assume), plus around ten separate people have probably worked on what you're dealing with now. Their glassdoor.com page is... depressing.
## Post #126
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-01-31T22:38:29+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Good news -- finally got something working for the Walking Dead: Michonne models.


Got a model (Michonne's face) to import with the rigging on the correct bones now (the weightmap's shown in the above image). Problem is, the UV mapping's still buggered (Seriously, though -- what's the point of having a short-value set up for 'em that has to be multiplied by an external value? What's the benefit of using those over full-floats or even half-floats?) and I have yet to find where the polygon split/vertex buffer information is stored, so that's all manually set up for now. Hrm. Still, at least I know it's definitely possible to get these models extracted. I'll continue working on this, hopefully I can have the script updated within a week if things don't go horribly wrong.

(EDIT: About half of the model's parts import automatically now, but others still won't. I'm getting there, slowly but surely!)
(EDIT 2: Just about done now, only things I have left to do now are to figure out the UV mapping, and make sure other models are working fine.)
## Post #127
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-02-01T15:05:32+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> Good news -- finally got something working for the Walking Dead: Michonne models.


Got a model (Michonne's face) to import with the rigging on the correct bones now (the weightmap's shown in the above image). Problem is, the UV mapping's still buggered (Seriously, though -- what's the point of having a short-value set up for 'em that has to be multiplied by an external value? What's the benefit of using those over full-floats or even half-floats?) and I have yet to find where the polygon split/vertex buffer information is stored, so that's all manually set up for now. Hrm. Still, at least I know it's definitely possible to get these models extracted. I'll continue working on this, hopefully I can have the script updated within a week if things don't go horribly wrong.

(EDIT: About half of the model's parts import automatically now, but others still won't. I'm getting there, slowly but surely!)
(EDIT 2: Just about done now, only things I have left to do now are to figure out the UV mapping, and make sure other models are working fine.)
I look forward to this. Wait. Is the script updated with fixed normals or is it just me?
## Post #128
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-02-01T15:05:56+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Holy moly, man, you work fast! Nice job!

Some observations I've noticed, the model appears to be much larger than previous telltale titles based on the size of 3DS Max's grid, and there's a bone at between the two feet which I assume is like an anchor/parent that moves the whole model?
## Post #129
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-02-01T15:26:49+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> Some observations I've noticed, the model appears to be much larger than previous telltale titles based on the size of 3DS Max's grid, and there's a bone at between the two feet which I assume is like an anchor/parent that moves the whole model?Nah, it's the same size as it's always been. I just added an extra "root" bone and scaled it up to 100x for readability just for those pics (since 3DS Max doesn't work well with tiny models).
## Post #130
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-02-02T11:47:56+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Decided to take a bit of a detour to work on the Batman format instead. Just like I thought, it's definitely a variant on the Michonne format. Took all the header-parsing code that I did for that, changed a few things since there were indeed some differences, and...


...but I'm still trying to figure out why the UV mapping for those both aren't importing correctly.
## Post #131
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-02-02T13:28:14+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

It's based purely on the fact that Batman and TWD3 both use the 'updated' engine, but I have a feeling those models are set up very similarly too?
## Post #132
- Username: Cappu
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 06, 2014 12:10 am
- Post datetime: 2017-02-02T15:49:57+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> It's based purely on the fact that Batman and TWD3 both use the 'updated' engine

TWD S3 textures for new engine also has a different look ((
I hope there will be a new script for QuickBMS
## Post #133
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-02-02T17:11:28+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Cappu
>
> jayko wrote:It's based purely on the fact that Batman and TWD3 both use the 'updated' engine

TWD S3 textures for new engine also has a different look ((
I hope there will be a new script for QuickBMSYou're in luck, I have an updated set of QuickBMS scripts for that.
[https://mega.nz/#!fpZ3TBZb!ukbamTp-2qRp ... k4_Xfi2Hng](https://mega.nz/#!fpZ3TBZb!ukbamTp-2qRp_w4GO1PwGv0vUlM63am06k4_Xfi2Hng)

The "gobo" textures don't convert correctly yet, though. Gotta figure out what's up with those.

(EDIT: Fixed the scripts so that headered textures extract properly now.)
## Post #134
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-02-02T18:09:50+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> You're in luck, I have an updated set of QuickBMS scripts for that.
https://mega.nz/#!q9YS1ZbY!wy1TBOGWQtIM ... 9PAjrSA_JY

The "gobo" textures don't convert correctly yet, though. Gotta figure out what's up with those.

They don't appear to be working for me:


Mayyyybe the input has to be a folder instead of a specific file? But I'm a pleb so I thought I'd come ask for advice before doing anything dumb.
## Post #135
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-02-02T18:16:06+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> RandomTBush wrote:You're in luck, I have an updated set of QuickBMS scripts for that.
https://mega.nz/#!q9YS1ZbY!wy1TBOGWQtIM ... 9PAjrSA_JY

The "gobo" textures don't convert correctly yet, though. Gotta figure out what's up with those.

They don't appear to be working for me:


Mayyyybe the input has to be a folder instead of a specific file? But I'm a pleb so I thought I'd come ask for advice before doing anything dumb.Dangit, sounds like yet another case of inconsistent files between versions (wouldn't be the first time -- I've seen headered and unheadered versions of models that were from the same game, grumble grumble). Send me one of 'em through a PM so I can take a look. Or it could be that I goofed somewhere, though I was able to convert the textures for myself. Either way, I'll fix it.

But you were using the script correctly, judging by the screenshot, it's just that something went wrong (as usual).
## Post #136
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-02-02T20:31:06+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> Dangit, sounds like yet another case of inconsistent files between versions (wouldn't be the first time -- I've seen headered and unheadered versions of models that were from the same game, grumble grumble). Send me one of 'em through a PM so I can take a look. Or it could be that I goofed somewhere, though I was able to convert the textures for myself. Either way, I'll fix it.

But you were using the script correctly, judging by the screenshot, it's just that something went wrong (as usual).Just as I figured, the textures had headers on 'em, which the script wasn't expecting. Dunno why the ones I used didn't have 'em when I extracted 'em myself, but it was a simple fix. Re-download the scripts and the textures should now properly extract:
[https://mega.nz/#!fpZ3TBZb!ukbamTp-2qRp ... k4_Xfi2Hng](https://mega.nz/#!fpZ3TBZb!ukbamTp-2qRp_w4GO1PwGv0vUlM63am06k4_Xfi2Hng)

Thanks for bringing it up, jayko!
## Post #137
- Username: Cappu
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 06, 2014 12:10 am
- Post datetime: 2017-02-02T23:18:15+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

textures with a base color converted well, but the texture with black lines (sk62_clementine_accessories_detail.dds, sk62_clementine_babyCarrier_detail.dds and so on with _detail at the end) were converted incorrectly. they can be opened in photoshop, but they don't have an alpha channel where there should be black lines stroke and the picture is either all black or with random stripes. it seems these _detail files into something significantly different from other
## Post #138
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-02-03T09:24:12+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Cappu
>
> textures with a base color converted well, but the texture with black lines (sk62_clementine_accessories_detail.dds, sk62_clementine_babyCarrier_detail.dds and so on with _detail at the end) were converted incorrectly. they can be opened in photoshop, but they don't have an alpha channel where there should be black lines stroke and the picture is either all black or with random stripes. it seems these _detail files into something significantly different from otherTry using Noesis to convert those. They're using either the ATI1 DDS format (1 channel, greyscale-only) or ATI2 (2 channel, red/green), which many programs seem to have trouble opening. The latter may not be entirely correct compared to the former, but it's the only format that showed a proper image for those kinds of textures. I may have to look into it a bit more later.
## Post #139
- Username: Cappu
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 06, 2014 12:10 am
- Post datetime: 2017-02-03T14:48:17+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> Try using Noesis to convert those.
with Noesis all these files opened correctly, I was able to convert these files to tga format. Thank you.
## Post #140
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-02-03T16:29:04+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Cappu
>
> RandomTBush wrote:Try using Noesis to convert those.
with Noesis all these files opened correctly, I was able to convert these files to tga format. Thank you.
Do you have a link to Noesis? I'm having the same problem with TWD3 detail textures but I want to make sure I'm looking for the right program first.
## Post #141
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-02-03T16:51:00+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> Do you have a link to Noesis? I'm having the same problem with TWD3 detail textures but I want to make sure I'm looking for the right program first.You can find it on [Rich Whitehouse's page](http://richwhitehouse.com/index.php?content=inc_projects.php), first result on Google when you look up "Noesis program".
## Post #142
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-02-03T17:35:01+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> jayko wrote:Do you have a link to Noesis? I'm having the same problem with TWD3 detail textures but I want to make sure I'm looking for the right program first.You can find it on Rich Whitehouse's page, first result on Google when you look up "Noesis program".
Well *now* I feel silly. I'm so clueless about a lot of this stuff - haven't had a lot of luck with the textures, either. Glad that's all behind me, now, though XD
## Post #143
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2017-02-05T17:25:17+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> Decided to take a bit of a detour to work on the Batman format instead. Just like I thought, it's definitely a variant on the Michonne format. Took all the header-parsing code that I did for that, changed a few things since there were indeed some differences, and...


...but I'm still trying to figure out why the UV mapping for those both aren't importing correctly.

It´s working properly now?
## Post #144
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-02-05T19:07:53+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from logansan25
>
> It´s working properly now?

I think it's just the texture mapping that needs to be fixed and then the TWDM update is done at least. Don't take my word for it, though.
## Post #145
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-02-06T04:09:06+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> logansan25 wrote:It´s working properly now?

I think it's just the texture mapping that needs to be fixed and then the TWDM update is done at least. Don't take my word for it, though.Yep. I'm seriously having a hard time trying to figure out why this isn't importing correctly. It better not be something like a minimum/maximum texture clamp that I need to locate and calculate...



This is currently the closest I've got. For some reason, it's centered (but only for certain models!) and even if it was aligned correctly, the height isn't correct (it basically takes up the whole canvas size, including the part for the hands at the bottom of the texture). Once I get that figured out, both of the new importers will be ready.
## Post #146
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-02-06T15:59:28+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> Yep. I'm seriously having a hard time trying to figure out why this isn't importing correctly. It better not be something like a minimum/maximum texture clamp that I need to locate and calculate...



This is currently the closest I've got. For some reason, it's centered (but only for certain models!) and even if it was aligned correctly, the height isn't correct (it basically takes up the whole canvas size, including the part for the hands at the bottom of the texture). Once I get that figured out, both of the new importers will be ready.

I know you can do it, man - you've nailed everything else so once you hit your stride you'll be done in no time 

As for 'both' importers, does this mean that there's going to be a TWDM one, while Batman and TWD3 share the same one?
## Post #147
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2017-02-08T14:59:54+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> jayko wrote:logansan25 wrote:It´s working properly now?

I think it's just the texture mapping that needs to be fixed and then the TWDM update is done at least. Don't take my word for it, though.Yep. I'm seriously having a hard time trying to figure out why this isn't importing correctly. It better not be something like a minimum/maximum texture clamp that I need to locate and calculate...



This is currently the closest I've got. For some reason, it's centered (but only for certain models!) and even if it was aligned correctly, the height isn't correct (it basically takes up the whole canvas size, including the part for the hands at the bottom of the texture). Once I get that figured out, both of the new importers will be ready.

Hi RandomTBush i want to ask you a question, is it possible to somehow export Animations from telltale games(i mean .anm and .chore files), it would be really awesome if you add "Export Animation" to your script!
## Post #148
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-02-08T22:20:10+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Maximmum
>
> Hi RandomTBush i want to ask you a question, is it possible to somehow export Animations from telltale games(i mean .anm and .chore files), it would be really awesome if you add "Export Animation" to your script!

As amazing as that would be, I think exporting animations is an entirely different ballgame to models and textures. But that's just my basic understanding - you'd have to hear confirmation from the man himself.
## Post #149
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-02-10T00:48:48+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Does anyone have these textures for Kenny (TWD2) The Face texture from Episode 2, The bandage texture without the blood, body texture from Episode 2, body texture covered in blood, and body texture from Episode 4, and the bandage detail texture?

Head: 

Body: 

Bandage:
## Post #150
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-02-10T21:07:10+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Escope12
>
> Does anyone have these textures for Kenny (TWD2)

Got some of them for you, I'm either not sure what the others meant or couldn't access them:

> Reply from Escope12
>
> The bandage texture without the blood,
[http://i.imgur.com/rleKr9X.png](http://i.imgur.com/rleKr9X.png)

> Reply from Escope12
>
> body texture covered in blood,
[http://i.imgur.com/EkLjBep.png](http://i.imgur.com/EkLjBep.png)

> Reply from Escope12
>
> and body texture from Episode 4
[http://i.imgur.com/Coz1rA8.png](http://i.imgur.com/Coz1rA8.png)
## Post #151
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-02-10T21:12:39+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> Escope12 wrote:Does anyone have these textures for Kenny (TWD2)

Got some of them for you, I'm either not sure what the others meant or couldn't access them:
Escope12 wrote:The bandage texture without the blood,
http://i.imgur.com/rleKr9X.png
Escope12 wrote:body texture covered in blood,
http://i.imgur.com/EkLjBep.png
Escope12 wrote:and body texture from Episode 4
http://i.imgur.com/Coz1rA8.png
Thanks. The Bandage Detail Texture is the texture for the bandage with the lines and the face texture from Episode 2 is also what I'm looking for. You can use this to extract the textures so you don't have to use Texmod. [https://mega.nz/#!fpZ3TBZb!ukbamTp-2qRp ... k4_Xfi2Hng](https://mega.nz/#!fpZ3TBZb!ukbamTp-2qRp_w4GO1PwGv0vUlM63am06k4_Xfi2Hng)
## Post #152
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-02-10T21:35:36+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> Maximmum wrote:Hi RandomTBush i want to ask you a question, is it possible to somehow export Animations from telltale games(i mean .anm and .chore files), it would be really awesome if you add "Export Animation" to your script!

As amazing as that would be, I think exporting animations is an entirely different ballgame to models and textures. But that's just my basic understanding - you'd have to hear confirmation from the man himself.Precisely. I have absolutely no knowledge as to how to read animations, let alone set up 3DS Max's keyframing and such through the MaxScript, so right now I won't be able to do that.
## Post #153
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-02-12T00:20:58+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> It better not be something like a minimum/maximum texture clamp that I need to locate and calculate...

I hope not, but I have a horrible feeling this may be the case. If I've learned anything, it's that this sort of thing is rarely straightforward XD

But it seems like the current version is at least functional with the aid of the UVW unwrap modifier?
## Post #154
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-02-15T04:31:02+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

I use 3DS Max 2015 to import The Walking Dead Season 2 models and the rigging worked fine.
## Post #155
- Username: littlepeggy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 28, 2017 1:46 am
- Post datetime: 2017-02-16T23:59:41+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

It's so exciting seeing all the progress being made on the importer over the past few weeks   It's been hard to wait patiently since I'm such an anxious person, but I know it'll be worth it. I just wanted to make a post expressing my thanks to you rtb and all your hard work for us (it's taken me a while to make this post because I've been nervous lol). Hope you've been well!
## Post #156
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-02-19T20:08:23+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Has there been any progress since the last update? I've got a job interview tomorrow so my nerves are acting up a bit and it's leaving me a bit concerned - hopefully nothing bad has happened IRL and everything's okay on your end :O
## Post #157
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-02-19T20:44:51+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

I wish the script can import the models with fixed Normals. I tried to fix the normals myself but no dice.
## Post #158
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-02-19T22:01:48+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> Has there been any progress since the last update? I've got a job interview tomorrow so my nerves are acting up a bit and it's leaving me a bit concerned - hopefully nothing bad has happened IRL and everything's okay on your end :OI'm still here thankfully, but I unfortunately haven't had much luck with fixing the UV mapping issue yet. But I'm obviously not gonna let that defeat me since it's the only thing left that I need to fix for the importer before I can release the update.

Good luck with your job interview tomorrow!

> Reply from Escope12
>
> I wish the script can import the models with fixed Normals. I tried to fix the normals myself but no dice.Frankly I'm not sure how they're stored in most of Telltale's games, but I'll look into that again sometime later, after the TWD3/Batman and Michonne importers are finished.
## Post #159
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-02-20T02:29:47+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

What about the materials? Do you just drag and drop the textures on the model manually? Sorry if I'm asking too much.
## Post #160
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-02-20T02:50:52+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Escope12
>
> What about the materials? Do you just drag and drop the textures on the model manually? Sorry if I'm asking too much.You'll have to, yes. Telltale changed it to use filename hashes or something of that sort, because where there used to be proper names in some of their earlier games, it's turned into seemingly-random, 8-byte strings -- likewise for bone names. There's nothing I can do about that currently, or even in the foreseeable future, if you need to get the proper materials (like the right eye textures) for things you're better off comparing with a Ninja Ripper dump.
## Post #161
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-02-20T20:15:52+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Is anyone having trouble with the characters jaw bones from The Walking Dead Season 2?
## Post #162
- Username: Cappu
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 06, 2014 12:10 am
- Post datetime: 2017-02-20T20:44:10+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Escope12
>
> Is anyone having trouble with the characters jaw bones from The Walking Dead Season 2?

Yes, but it's easy to fix. I found problems not only with the lower jaw, but also with fingers. 3DS MAX has all the tools to fix it. In the world nothing is perfect. In the case TWD S2... you will have to rename all bones of the skeleton after importing the model, find the right textures, set materials and fix minor problems on a mesh.
## Post #163
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-02-20T22:20:05+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Cappu
>
> Escope12 wrote:Is anyone having trouble with the characters jaw bones from The Walking Dead Season 2?

Yes, but it's easy to fix. I found problems not only with the lower jaw, but also with fingers. 3DS MAX has all the tools to fix it. In the world nothing is perfect. In the case TWD S2... you will have to rename all bones of the skeleton after importing the model, find the right textures, set materials and fix minor problems on a mesh.
Which 3DS Max version are you using?
## Post #164
- Username: Cappu
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 06, 2014 12:10 am
- Post datetime: 2017-02-20T22:49:25+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Escope12
>
> Which 3DS Max version are you using?
2017 of course. I see no reason to be stuck on the old version, the script works well in 2017.
## Post #165
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-02-21T00:03:45+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Cappu
>
> Escope12 wrote:Which 3DS Max version are you using?
2017 of course. I see no reason to be stuck on the old version, the script works well in 2017.
Do you have a tutorial on how to do it? With images maybe?
## Post #166
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-02-21T00:08:45+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Escope12
>
> Is anyone having trouble with the characters jaw bones from The Walking Dead Season 2?If it's related to the jaw bones being separate from the lower lip bones and whatnot, that's normal. There shouldn't be any problems with importing bone structures since there's only so much information they carry (almost all of which read by my script, including the parenting).
## Post #167
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-02-21T00:50:00+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> Escope12 wrote:Is anyone having trouble with the characters jaw bones from The Walking Dead Season 2?If it's related to the jaw bones being separate from the lower lip bones and whatnot, that's normal. There shouldn't be any problems with importing bone structures since there's only so much information they carry (almost all of which read by my script, including the parenting).
Oh okay. I was gonna make Facial Expressions for Kenny since I'm planning on importing him over Snake for SSBB.
## Post #168
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-02-21T00:57:57+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Escope12
>
> RandomTBush wrote:Escope12 wrote:Is anyone having trouble with the characters jaw bones from The Walking Dead Season 2?If it's related to the jaw bones being separate from the lower lip bones and whatnot, that's normal. There shouldn't be any problems with importing bone structures since there's only so much information they carry (almost all of which read by my script, including the parenting).Oh okay. I was gonna make Facial Expressions for Kenny since I'm planning on importing him over Snake for SSBB.Just use the "Select and Link" button to attach 'em all to the jaw bone and manipulate 'em that way, it'd be much easier to pose that way.
## Post #169
- Username: Cappu
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 06, 2014 12:10 am
- Post datetime: 2017-02-21T22:37:51+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Escope12
>
> Do you have a tutorial on how to do it? With images maybe?
Yes, I have the tutorial, but it is in Russian. I tried to write it in simple words, so Google-translator translates it with almost no semantic errors: [link](http://translate.googleusercontent.com/translate_c?depth=1&hl=ru&rurl=translate.google.com&sl=ru&sp=nmt4&tl=en&u=http://rg-3d.ru/tutorials/).
## Post #170
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2017-02-22T10:17:38+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Cappu
>
> Escope12 wrote:Do you have a tutorial on how to do it? With images maybe?
Yes, I have the tutorial, but it is in Russian. I tried to write it in simple words, so Google-translator translates it with almost no semantic errors: link.
Here is a bit better translation:
1. Instruments

To extract 3D Models from Telltale Games archives you will need atleast two instruments:

1) Telltale archives extractor "Telltale TTARCH files extractor/rebuilder" from Luigi Auriemma. This is cmd.exe program. It almost always updates, by it's author, you can always find the latest version here: [http://aluigi.altervista.org/papers.htm#others-file](http://aluigi.altervista.org/papers.htm#others-file)


"Telltale TTARCH files extractor/rebuilder" Download link is in the description of it's website

2) RandomTBrush script for 3DS MAX, that allows you to import meshes and their armature. Not all TTG games are work with this script. The list is here [viewtopic.php?f=16&t=11687](http://forum.xentax.com/viewtopic.php?f=16&t=11687)


Besides script for 3DS MAX, in archive you can also find a program called "QuickBMS". You will need this scripts and the program itself for convert textures from the latest TTG games. If you can't "QuickBMS" in archive, then most likely scenario is that the creator has update the archive and create a different link for it, look for the latest message on the forum or the first pages to ind new links for it.

You can download "QuickBMS" here: [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)



Just like the script for 3DS Max, scripts for "QuickBMS" are different for different games, so you should look better in their descriptions.

Just like additional instrument to work with models in 3DS MAX you might also need to download a script called "Quadrangulate". All meshes, that you import in 3DS MAX will be divided in to triangles, This is okay for games that was optimized to use in Video Games. But if you planned to use this models for different purposes, for example, to render animation, then it will be much better for you if you divide models in rectangles. And exactly for this you might need this script. It's free, and you can download it here: 
[http://www.scriptspot.com/3ds-max/scripts/quadrangulate](http://www.scriptspot.com/3ds-max/scripts/quadrangulate)



Translated by me Maximmum, a.k.a. Rhysha, a.k.a. Max, a.k.a. Alien!
## Post #171
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-02-22T18:19:20+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> I'm still here thankfully, but I unfortunately haven't had much luck with fixing the UV mapping issue yet. But I'm obviously not gonna let that defeat me since it's the only thing left that I need to fix for the importer before I can release the update.

Good luck with your job interview tomorrow!

Thanks, man - it's looking good so far, just gotta wait for a call back now.

I have to say I admire your determination to find a solution to the problem; it's very encouraging. I assume it's a trial-and-error process and probably quite tedious so I'm grateful you're taking the time to do that. If I were in your place it probably would've beat me long ago XD
## Post #172
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-03-01T22:05:48+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Hey! Looking good so far. I don't suppose you have any plans to go back to TWD season 1 afterwards do you? There are a bunch of issues with various props/scenery. Some of it isnt that hard to work around at the moment, but there's various parts of maps that are slightly dodgy lol.
## Post #173
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-03-02T01:01:02+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Tydeus
>
> Hey! Looking good so far. I don't suppose you have any plans to go back to TWD season 1 afterwards do you? There are a bunch of issues with various props/scenery. Some of it isnt that hard to work around at the moment, but there's various parts of maps that are slightly dodgy lol.Yeah, I do have plans to go back and update/fix up other parts of the script later (like adding normals and such), but it won't be in the same update as the Batman/TWD3 implementation... whenever I get that fully figured out, that is. Just be sure to let me know which model files in particular have the problems so I can use those as a reference point.
## Post #174
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-03-02T21:41:12+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Yeah thats cool, like I said a lot of the stuff have a simple work around. A lot of the texture faults can be fixed using a combination of UVW Mapping and Unwrap UVW and others can be replaced using other props, but there are a bunch of stuff that I just give up on lol. I'll let you know once you get to that stage!  I should maybe make a list.
## Post #175
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2017-03-05T09:21:13+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Hi RandomTBush, i want to ask you, is it possible and could you try to make a option to not only export the model but also, import the model in Telltale Engine to d3dmesh and skl format, because that would have been really awesome
## Post #176
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-03-05T15:15:11+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Man the UV mapping seems to be a pain. I still have faith! ;_;
## Post #177
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-03-05T19:08:18+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> Man the UV mapping seems to be a pain. I still have faith! ;_;

I was messing with the Episode 5 Boat Shed yesterday (obj_boathouseinterior105.d3dmesh), I was trying to get all the props textures to line up. I did everything okayish, and when I got to the shelving unit I gave it up as a bad job. Luckily the episode 4 shed works, theres just no props inside. I think the props are in other maps though so thats fine.
## Post #178
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-03-06T16:07:46+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Tydeus
>
> jayko wrote:Man the UV mapping seems to be a pain. I still have faith! ;_;

I was messing with the Episode 5 Boat Shed yesterday (obj_boathouseinterior105.d3dmesh), I was trying to get all the props textures to line up. I did everything okayish, and when I got to the shelving unit I gave it up as a bad job. Luckily the episode 4 shed works, theres just no props inside. I think the props are in other maps though so thats fine.

I was referring to the next update, but yeah... the environment models can be a pain in the bum.
## Post #179
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-03-06T19:38:28+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Just (and finally) figured out how to fix things being improperly rigged in 3DS Max 2012 and above (2015's specific rigging issues were the most annoying to fix), so that'll be in the next update, too.
## Post #180
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-03-06T22:07:51+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> Just (and finally) figured out how to fix things being improperly rigged in 3DS Max 2012 and above (2015's specific rigging issues were the most annoying to fix), so that'll be in the next update, too.

I saw the words 'finally' and 'fix' and my heart jumped into my throat... but unfortunately it wasn't the fix I was praying for XD

Fortunately for me, however, I use the 2010 version so rigging's always been fine on my end, which is nice!
## Post #181
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-03-06T22:41:50+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> RandomTBush wrote:Just (and finally) figured out how to fix things being improperly rigged in 3DS Max 2012 and above (2015's specific rigging issues were the most annoying to fix), so that'll be in the next update, too.

I saw the words 'finally' and 'fix' and my heart jumped into my throat... but unfortunately it wasn't the fix I was praying for XD

Fortunately for me, however, I use the 2010 version so rigging's always been fine on my end, which is nice!Yeah, hence why I normally referred others to using an older version, thankfully I won't have to now. It amazes me how Autodesk manages to break things with the later versions -- first it was 2012/2013 alphabetizing the bones and therefore breaking the arrays, then it was 2015/2016 automatically assigning extra rigging to whatever bones were nearby (can't say much about 2014, nobody I know uses it and I don't have it either). It almost seems like they're breaking things on purpose sometimes. Sheesh.

But yeah, I'll get back to figuring out the UV mapping shenanigans hopefully soon. I'll probably have to resort to modifying the various float values in the headers until I find something that breaks the UVs in-game before I'm able to finally fix the script and release it.

> Reply from Maximmum
>
> Hi RandomTBush, i want to ask you, is it possible and could you try to make a option to not only export the model but also, import the model in Telltale Engine to d3dmesh and skl format, because that would have been really awesomeNot for a long time. There are way too many unknowns in the headers for the models, and with the way the materials and bone names and such are hashed, it's pretty much impossible to make custom models without reverse-engineering the model format completely, or by getting Telltale's tools somehow.
## Post #182
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2017-03-07T14:33:38+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Maximmum
>
> Hi RandomTBush, i want to ask you, is it possible and could you try to make a option to not only export the model but also, import the model in Telltale Engine to d3dmesh and skl format, because that would have been really awesomeNot for a long time. There are way too many unknowns in the headers for the models, and with the way the materials and bone names and such are hashed, it's pretty much impossible to make custom models without reverse-engineering the model format completely, or by getting Telltale's tools somehow.[/quote]

Damn, that's really shame   , i think we need a hacker who can stole Telltale Engine from them (and also all beta versions of all their games, especially Wolfy with it's Brannigan storyline, and TWDS2 with it's dark atmosphere, stolen by Sam hat and fishing at end of ep 1 and many other things i could list them forever)
## Post #183
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-03-19T19:53:02+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Hopefully it won't be too long now - I'll be starting work soon provided all goes well and I was hoping to have time to work with the scripts ; _ ;
## Post #184
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-03-21T05:23:54+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

How can I blend Kenny's Body texture with his Body detail texture in 3DS Max?
## Post #185
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2017-03-21T09:56:24+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

The thing that bothers me the most is the release of GotG, which would most likely have a different format than Batman/TWD3.
## Post #186
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-03-21T16:57:30+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Escope12
>
> How can I blend Kenny's Body texture with his Body detail texture in 3DS Max?
The easiest way to do it is open up both textures in an image editing program (GIMP/Paint.NET/Photoshop etc.) and set the detail texture's blend mode to 'multiply', then export the whole thing as a separate image and use that as the texture.

> Reply from meganmi
>
> The thing that bothers me the most is the release of GotG, which would most likely have a different format than Batman/TWD3.

God yeah, let's hope that comes as a separate update to the TWDM/TWD3 stuff XD
## Post #187
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-03-21T17:37:12+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> God yeah, let's hope that comes as a separate update to the TWDM/TWD3 stuff XDYeah, the Guardians of the Galaxy format (whatever it is) will have to wait until I get the others done first, needless to say.
## Post #188
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-03-21T17:41:44+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> jayko wrote:God yeah, let's hope that comes as a separate update to the TWDM/TWD3 stuff XDYeah, the Guardians of the Galaxy format (whatever it is) will have to wait until I get the others done first, needless to say.
It's almost like Telltale changes up their format every game just to mess with you - though, I suppose that's just them implementing anti-hacking measures or something, like with how they prevented Texmod from working with the Borderlands and Game of Thrones games.
## Post #189
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-03-21T21:25:21+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> RandomTBush wrote:jayko wrote:God yeah, let's hope that comes as a separate update to the TWDM/TWD3 stuff XDYeah, the Guardians of the Galaxy format (whatever it is) will have to wait until I get the others done first, needless to say.
It's almost like Telltale changes up their format every game just to mess with you - though, I suppose that's just them implementing anti-hacking measures or something, like with how they prevented Texmod from working with the Borderlands and Game of Thrones games.

im just here waiting for it to work with batman o3o
## Post #190
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-03-21T22:16:10+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from AstroStormz
>
> im just here waiting for it to work with batman o3o
iirc batman and twd3 have the same model format, so batman should work with the next update too ; )
## Post #191
- Username: Konnie
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 23, 2017 11:33 pm
- Post datetime: 2017-03-23T15:52:03+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Hello, I have recently got around to using the importer for Game of Thrones, it all works fine but I have no idea how I can convert the .d3dtx files into .dds.

I have attempted to find the download for TTG tools as many people suggested it but I couldn't find it and I have no idea how to work QuickBMS (I'm a noobie)

Thank you.
## Post #192
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-03-23T17:30:26+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Konnie
>
> Hello, I have recently got around to using the importer for Game of Thrones, it all works fine but I have no idea how I can convert the .d3dtx files into .dds.

I have attempted to find the download for TTG tools as many people suggested it but I couldn't find it and I have no idea how to work QuickBMS (I'm a noobie)

Thank you.I've updated the first post with the QuickBMS script for that which I linked to a few pages ago (the abbreviations should give away what game it's for, you'd want to use "Telltale_D3DTX_TftBL_GoT_MCSM" for that). Dunno why I didn't do so earlier.

Either way, QuickBMS is easy to use. Double-click the program, then select the script you want to use (it'll be a .BMS file, same one I mentioned above), then the files you want to convert (the ones with .D3DTX extensions), and finally the folder you want to extract the files to, in that order. If done correctly, you should have .DDS files in the output folder.
## Post #193
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-03-27T15:50:41+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

I'm like 99.9% certain, but I just want to check the BMS scripts will work for the textures in TWD3 Ep3 when it's released tomorrow? I'm pretty sure that will be the case unless they happen to drastically alter how the textures are set up for whatever reason.

(Also is the UV mapping still being troublesome?)
## Post #194
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-03-31T02:00:03+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> I'm like 99.9% certain, but I just want to check the BMS scripts will work for the textures in TWD3 Ep3 when it's released tomorrow?

Okay I just checked and it doesn't appear to be working (again). Bloody Telltale changing up layouts and stuff : P
## Post #195
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-03-31T04:46:48+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Does anyone have the normal map body texture for Doug?
## Post #196
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2017-04-01T16:40:45+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Escope12
>
> Does anyone have the normal map body texture for Doug?
there isn't one, but you can always generate it!
## Post #197
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-04-01T18:36:19+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Maximmum
>
> Escope12 wrote:Does anyone have the normal map body texture for Doug?
there isn't one, but you can always generate it!
Yeah, [Normal Map Online](http://cpetry.github.io/NormalMap-Online/) is probably the best place for that.
## Post #198
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2017-04-09T03:51:02+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Hi RandomTBush, i just wanted to ask you, maybe you should release the script with Unfixable UVs because it's not too hard to manually fix them but it would be great to have atleast that version while you'll be fixing them in script, because many of us already can't wait to to release and wait for about 4 months for it already! So i hope you understand us
## Post #199
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-04-10T03:30:09+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Maximmum
>
> Hi RandomTBush, i just wanted to ask you, maybe you should release the script with Unfixable UVs because it's not too hard to manually fix them but it would be great to have atleast that version while you'll be fixing them in script, because many of us already can't wait to to release and wait for about 4 months for it already! So i hope you understand us

I'd absolutely love a temporary version even if it is kind of broken, but things appear to have slowed down quite a bit since March, which makes me worry. 

I really hope it isn't dead...
## Post #200
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-10T03:44:19+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> Maximmum wrote:Hi RandomTBush, i just wanted to ask you, maybe you should release the script with Unfixable UVs because it's not too hard to manually fix them but it would be great to have atleast that version while you'll be fixing them in script, because many of us already can't wait to to release and wait for about 4 months for it already! So i hope you understand us  

I'd absolutely love a temporary version even if it is kind of broken, but things appear to have slowed down quite a bit since March, which makes me worry. 

I really hope it isn't dead...It's not dead, I just haven't had any time to work on it lately.
## Post #201
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-04-10T21:56:37+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> It's not dead, I just haven't had any time to work on it lately.

Ah, okay - my apologies for being so persistent about it.
## Post #202
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-21T20:18:21+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Looks like the model format for Marvel's Guardians of the Galaxy is changed around enough that the scripting I set up for Batman just crashes 3DS Max, which means I'm gonna have to write up even more changes to work with that game's models. Argh... I'll definitely leave that until I can get everything else figured out.

At least the bone structures and textures are unchanged (except for a few textures that seem to be using odd formats). But still, this is getting annoying.

(EDIT: Went back to working on the Walking Dead Season 3 models and now I realized that there's level-of-detail meshes that I gotta set up support for or else other parts won't import correctly. Good grief.)
## Post #203
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-22T18:58:27+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Aaaaaaaaaalmost, but not quite there. The UV mapping isn't quite right for his left leg. Hrm... At least I can confirm that the UV mapping is in fact based off a minimum/maximum clamp (the values range from 0-65535, regardless of where they are situated on the texture, so I can use Javier's necklace or shirt tag as a reference point to finally get this problem fixed since I don't have as much information to parse through for those.
## Post #204
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-04-22T22:10:45+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

I'll be sending you my good vibes in hope this works out -- and that telltale doesn't decide to send any more trickery your way.
## Post #205
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-22T23:43:12+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Well, I just found out where the UV mapping clamps are stored. They're right above the vertex header information, as float values I just shrugged off thinking they were just basic bounding box information (two sets, one for start, one for multiplier). And here I just spent the past eight or so hours parsing the material/shader header chunks because I thought it was located there. ...Excuse me while I die.

(I'll start implementing the calculations after I've screamed into a pillow or something, and hopefully this'll mean that I'll have the next version ready within a few days since that was the only thing holding me back!)

(EDIT: It's working!)


Now I just need to set the script up so that it detects vertex colouring correctly (instead of as a UV mapping layer), then transfer the changes to the Batman and Michonne portion of the script, and then test it with a buncha models.
## Post #206
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-04-22T23:57:21+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> Well, I just found out where the UV mapping clamps are stored. They're right above the vertex header information, as float values I just shrugged off thinking they were just basic bounding box information (two sets, one for start, one for multiplier). And here I just spent the past eight or so hours parsing the material/shader header chunks because I thought it was located there. ...Excuse me while I die.

(I'll start implementing the calculations after I've screamed into a pillow or something, and hopefully this'll mean that I'll have the next version ready within a few days since that was the only thing holding me back!)
I wish you best luck. You're doing a good job with this.
## Post #207
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-23T05:12:09+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

[And another progress report!](https://twitter.com/RandomTBush/status/856012423370858496) (Yes, this means that all four of the recent games should be supported in the next update!)

Once I've made sure things are working alright, I'll go back and fix up a few of the other importers now that I have better knowledge of the header information, hopefully fixing up those problematic models that wouldn't import beforehand.
## Post #208
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-04-23T07:29:42+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Some of the female characters in TWD2 have UV issues with their eyelashes.
## Post #209
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2017-04-23T07:43:12+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Thank You! So much for this really) Though i can't wait and i already make myself ANF Clem model, by using Ninja Ripper, you've probs seen it already i released it a month ago for XNALara, L4D2, SFM and e.t.c., but still Thank You for doing this because ripping with Ninja Ripper is total pain in the a*s(finding all body parts in extraction folder, collect them in one, fixing broken UVs e.t.c. I was ready to literally kill myself lol  ) so Thank You Very Much, now with ur plugin it will be much easier to rip all other models)
## Post #210
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-04-23T10:12:14+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> And another progress report! (Yes, this means that all four of the recent games should be supported in the next update!)

Once I've made sure things are working alright, I'll go back and fix up a few of the other importers now that I have better knowledge of the header information, hopefully fixing up those problematic models that wouldn't import beforehand.

Awesome job, man!

Would the problematic models include those old TWD2 and TWAU location models where the UV Mapping is a bit buggy, or does the header information apply to the models like Felix from TFTBL where an error message would come up while importing? (I've also found the ANF ep3 textures don't convert correctly but that might just be me like last time instead of the BMS Script.)

Just curious either way (and definitely not meaning to pile on the work) - looking forward to the update!
## Post #211
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-23T20:10:19+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> RandomTBush wrote:And another progress report! (Yes, this means that all four of the recent games should be supported in the next update!)

Once I've made sure things are working alright, I'll go back and fix up a few of the other importers now that I have better knowledge of the header information, hopefully fixing up those problematic models that wouldn't import beforehand.

Awesome job, man!

Would the problematic models include those old TWD2 and TWAU location models where the UV Mapping is a bit buggy, or does the header information apply to the models like Felix from TFTBL where an error message would come up while importing? (I've also found the ANF ep3 textures don't convert correctly but that might just be me like last time instead of the BMS Script.)

Just curious either way (and definitely not meaning to pile on the work) - looking forward to the update!Almost certainly, yes. The way I was reading it before used just the vertex sizes as a reference point, which is actually incorrect. There's actually a section just above the polygon information which I've got set up for Batman/TWD3/TWDM/GotG which dictates what kinds of things are stored in those vertex buffers. With any luck, the older formats will be set up the same way, and I can transfer the coding over to those to fix the importing issues for good.
## Post #212
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-04-23T20:46:23+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> And another progress report! (Yes, this means that all four of the recent games should be supported in the next update!)

Hah you're awesome! although now that means I'm going to have to buy the games for the PC! *shakes fist*
## Post #213
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-24T05:54:05+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Figured I'd give the importer a new look since I'm overhauling a lot of things.


Personally, I think it's way better than the way it was before.


(Don't get excited about the Back to the Future importer being there yet, it's a placeholder until I can get [the 30th Anniversary Edition's rigging bullcrap figured out](http://forum.xentax.com/viewtopic.php?p=111235#p111235), it'll be removed before release.)
## Post #214
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-04-24T07:34:20+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

It looks cool  are they both optional? Also, will this still work for the 2009 version of 3ds?
## Post #215
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-24T07:38:50+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Tydeus
>
> It looks cool  are they both optional? Also, will this still work for the 2009 version of 3ds?The "disable" options on the bottom? Yeah. Vertex colours are disabled by default since it makes most models pure black, and LODs (which only apply to Batman, TWD3 and GotG) I don't think most people would be interested in (and make things take longer to load), but both can be re-enabled by unchecking their respective boxes.

And yeah, it should still work in 2009, I don't have it installed on my computer (I'm using the next one up, 2010), but I don't think I've added anything that's not already in 2009's MaxScript setup. And it should also work properly in 2012 and 2015 and such since I'm rewriting a bunch of things to accommodate their... er... "quirks" (bugs).
## Post #216
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-04-24T11:07:14+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> Tydeus wrote:It looks cool  are they both optional? Also, will this still work for the 2009 version of 3ds?The "disable" options on the bottom? Yeah.
I meant the two versions of the interface, one with just text and the other with icons  but I was going to ask about those options at the bottom. 

The second picture looks pretty much like the one we have now but blue, but I kinda like it
## Post #217
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-24T18:16:34+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Tydeus
>
> RandomTBush wrote:Tydeus wrote:It looks cool  are they both optional? Also, will this still work for the 2009 version of 3ds?The "disable" options on the bottom? Yeah. 
I meant the two versions of the interface, one with just text and the other with icons  but I was going to ask about those options at the bottom. 

The second picture looks pretty much like the one we have now but blue, but I kinda like itAh. Well, the colour scheme will actually vary, mine there's blue since I customized the colours of 3DS Max's UI (I prefer looking at that over longer periods of time compared to the default grey), but I suppose it wouldn't hurt to include both UIs, just in case people prefer the text-based menu options instead (or the icons don't work).
## Post #218
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2017-04-24T20:56:51+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Oh my God! Amazing tool!
## Post #219
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-04-24T20:59:25+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

It's just my luck that as soon as we enter what seems to be the home stretch, my 3DS Max decides "a license error has occured."

This is what I get for updating my PC.

EDIT: Fixed it, but hell if I'm ever letting Windows update again after that hassle.
## Post #220
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-04-24T23:08:01+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

When the new version of the tool gets released I'm gonna do an edit for TWD2 Kenny with TWDM Randall's clothes.

Edit: I'm having trouble extracting the ttarch2 files from The Walking Dead Michonne. I get this error. What do I do?
## Post #221
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2017-04-25T15:25:04+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Don't use 24 since it's for a different game.
## Post #222
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-25T21:52:03+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

[https://mega.nz/#!qkR0nJCZ!ImhNfUDaxL0n ... F1WjadV-Eg](https://mega.nz/#!qkR0nJCZ!ImhNfUDaxL0nN4dQahniuGQO3DGHfFrguF1WjadV-Eg)

Since it's gonna take me another week or two to rewrite all my older, frankly-hackish-at-times importers, I thought I'd set up a separate script with just the new stuff for now. So yeah, the script above will work with Batman: The Telltale Series, Marvel's Guardians of the Galaxy, The Walking Dead: A New Frontier and The Walking Dead: Michonne... but nothing else for now. Just use the old script for those until I get 'em brought up to standards. There's one bug that I know of that I'll have to address later -- any models that have over 65,535 vertex points (eg. adv_virginiaRailroad_meshesD in TWD3) won't import because Telltale thought it'd be a good idea to use short values for those polygon faces with an extra modifier (a crapton of long values that are either "-1" or "0", which don't seem to match up... what?!?) instead of just extending it to use long values. I don't understand why, they do have a value for face buffer lengths in the headers...

I've also fixed up a miscalculation with my .D3DTX QuickBMS script, so the textures from TWD: A New Frontier's third episode should extract now:
[https://mega.nz/#!T0gnCBCK!ZDMRxZTrTFeq ... aLqKDAvFow](https://mega.nz/#!T0gnCBCK!ZDMRxZTrTFeqMtiJ7JWZU-SLXjGN4Rtp7aLqKDAvFow)

Still haven't found out how to get the "gobo" and "lightprobe" textures to extract correctly yet, but I'll work on that after I've got the MaxScript fully updated.

As always, lemme know if something's broken with the new stuff.
## Post #223
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-04-25T23:07:56+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Awesome!

Done a little bit of testing - TWD3 models seem to be working fine, but TWDM's UV mapping seems a bit dodgy. Some work okay with the use of a bit of UVW Unwrapping (which is inconvenient but still workable):



While others appear a bit more difficult:



I'll do a bit more research and find out if it's specific models or if this extends to a lot/all of them and then maybe that will help identify the issue.
## Post #224
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-25T23:25:22+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from jayko
>
> Awesome!

Done a little bit of testing - TWD3 models seem to be working fine, but TWDM's UV mapping seems a bit dodgy. Some work okay with the use of a bit of UVW Unwrapping (which is inconvenient but still workable):

*image*

While others appear a bit more difficult:

*image*

I'll do a bit more research and find out if it's specific models or if this extends to a lot/all of them and then maybe that will help identify the issue.
Whoops! Seems I accidentally labelled the wrong kind of UV formats used for those, they should've been read as short signed integers, not short unsigned integers as they were there.

Re-download the script, should be working now. Thanks for letting me know!
[https://mega.nz/#!qkR0nJCZ!ImhNfUDaxL0n ... F1WjadV-Eg](https://mega.nz/#!qkR0nJCZ!ImhNfUDaxL0nN4dQahniuGQO3DGHfFrguF1WjadV-Eg)
## Post #225
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-04-26T00:04:23+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> jayko wrote:Awesome!

Done a little bit of testing - TWD3 models seem to be working fine, but TWDM's UV mapping seems a bit dodgy. Some work okay with the use of a bit of UVW Unwrapping (which is inconvenient but still workable):

*image*

While others appear a bit more difficult:

*image*

I'll do a bit more research and find out if it's specific models or if this extends to a lot/all of them and then maybe that will help identify the issue.
Whoops! Seems I accidentally labelled the wrong kind of UV formats used for those, they should've been read as short signed integers, not short unsigned integers as they were there.

Re-download the script, should be working now. Thanks for letting me know!
https://mega.nz/#!CpoUyCqL!r3fAturSXwYt ... Jm3piSi7p4

Thanks for the speedy fix! Tremendous work you've done here, man -- can't commend you enough. I'll be sure to shoot you a donation or something for your hard work when some cash comes my way. All that work deserves reward, I'd say : )
## Post #226
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-04-26T04:01:17+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> jayko wrote:Awesome!

Done a little bit of testing - TWD3 models seem to be working fine, but TWDM's UV mapping seems a bit dodgy. Some work okay with the use of a bit of UVW Unwrapping (which is inconvenient but still workable):

*image*

While others appear a bit more difficult:

*image*

I'll do a bit more research and find out if it's specific models or if this extends to a lot/all of them and then maybe that will help identify the issue.
Whoops! Seems I accidentally labelled the wrong kind of UV formats used for those, they should've been read as short signed integers, not short unsigned integers as they were there.

Re-download the script, should be working now. Thanks for letting me know!
https://mega.nz/#!CpoUyCqL!r3fAturSXwYt ... Jm3piSi7p4Thank you for the fix. It really worked. I was thinking about donating to you.
## Post #227
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2017-04-26T10:21:12+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Thank you! 
All works perfectly, but the bms scripts doesn't extract correctly the "detail" textures. All works fine.
I missed something?
## Post #228
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-26T19:42:44+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from fil1969
>
> Thank you! 
All works perfectly, but the bms scripts doesn't extract correctly the "detail" textures. All works fine.
I missed something?Try using Noesis to convert those. It may look like they don't extract correctly, but that's because they're an unusual format -- either ATI1 (one-channel DDS), ATI2 (two-channel DDS) or even a greyscaled, paletted one. Most image-viewing programs actually don't support those properly, but Noesis works.

...Unless there is actually one that doesn't extract correctly, in that case I'll need to take a look at the script again.

Also, progress report -- I've gotten the scripts for Minecraft: Story Mode, Tales from the Borderlands / Game of Thrones, The Walking Dead Season 2 and The Wolf Among Us (which now that I've fixed up I realize is actually the exact same format as TWD2's) all fixed up now, once I get Poker Night 2 re-done I'll upload another WIP script for that.
## Post #229
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2017-04-26T22:11:33+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

Anyone got the key for extracting the files from batman with the ttarchext.exe?
## Post #230
- Username: Zombieali2000
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 08, 2014 6:07 am
- Post datetime: 2017-04-26T22:18:19+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

This isnt a question about the script, But its a question about ttarchext.
Everytime i run it it has 0 problems. But when i go to check my output folder its empty! any idea why?
## Post #231
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-26T22:18:39+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from riccochet
>
> Anyone got the key for extracting the files from batman with the ttarchext.exe?The latest TTArchExt should already support it, as game ID 60.

Anyway, time for another WIP! The UI's been changed over to the new one now. Any icons that are blank are for ones that aren't fixed up yet.
[https://mega.nz/#!qkR0nJCZ!ImhNfUDaxL0n ... F1WjadV-Eg](https://mega.nz/#!qkR0nJCZ!ImhNfUDaxL0nN4dQahniuGQO3DGHfFrguF1WjadV-Eg)

The newly-revised older game importers now parse their vertex buffers correctly, normals are now applied, and the rigging fixes for 3DS Max 2012/2015 have been implemented. In other words, it should work a lot better now.
## Post #232
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2017-04-26T23:18:36+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

That worked thanks... I'm not finding any .skl files though... everything else extracts. Am I missing a step?
## Post #233
- Username: Zombieali2000
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 08, 2014 6:07 am
- Post datetime: 2017-04-26T23:26:20+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from riccochet
>
> That worked thanks... I'm not finding any .skl files though... everything else extracts. Am I missing a step?
Yeah im not seeing any .SKL Files either D: (WD:ANF)
## Post #234
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-26T23:29:34+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from Zombieali2000
>
> riccochet wrote:That worked thanks... I'm not finding any .skl files though... everything else extracts. Am I missing a step?
Yeah im not seeing any .SKL Files either D: (WD:ANF)Oddly enough, the SKL files aren't grouped with the models in the "_txmesh" archives, they're in the "_data" files instead.
## Post #235
- Username: Zombieali2000
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 08, 2014 6:07 am
- Post datetime: 2017-04-26T23:30:50+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> Zombieali2000 wrote:riccochet wrote:That worked thanks... I'm not finding any .skl files though... everything else extracts. Am I missing a step?
Yeah im not seeing any .SKL Files either D: (WD:ANF)Oddly enough, the SKL files aren't grouped with the models in the "_txmesh" archives, they're in the "_data" files instead.
Hmm. i went through all of the data files and didnt see any? Any idea which specific one it is?
EDIT! nvm found them.
## Post #236
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2017-04-27T04:56:29+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from RandomTBush
>
> fil1969 wrote:Thank you! 
All works perfectly, but the bms scripts doesn't extract correctly the "detail" textures. All works fine.
I missed something?Try using Noesis to convert those. It may look like they don't extract correctly, but that's because they're an unusual format -- either ATI1 (one-channel DDS), ATI2 (two-channel DDS) or even a greyscaled, paletted one. Most image-viewing programs actually don't support those properly, but Noesis works.

...Unless there is actually one that doesn't extract correctly, in that case I'll need to take a look at the script again.

Also, progress report -- I've gotten the scripts for Minecraft: Story Mode, Tales from the Borderlands / Game of Thrones, The Walking Dead Season 2 and The Wolf Among Us (which now that I've fixed up I realize is actually the exact same format as TWD2's) all fixed up now, once I get Poker Night 2 re-done I'll upload another WIP script for that.

Yes, i figured later after my post.. sorry for reporting it as bug.
Anyway, about sceneries, is possible an autotexturing on import? I will take ages do all by hand! 
Again thank you so much!
## Post #237
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-27T05:56:19+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from fil1969
>
> Anyway, about sceneries, is possible an autotexturing on import? I will take ages do all by hand! 
Again thank you so much!Unfortunately, no. Ever since The Walking Dead Season 2 / The Wolf Among Us, every single game of theirs resorted to hashes instead of proper file names for textures (likewise, they started doing so for bone names with SBCG4AP and onward), which means unless I can figure out the algorithm used, it's currently impossible for me to determine which texture should be used...
## Post #238
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-27T07:11:06+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

[https://mega.nz/#!qkR0nJCZ!ImhNfUDaxL0n ... F1WjadV-Eg](https://mega.nz/#!qkR0nJCZ!ImhNfUDaxL0nN4dQahniuGQO3DGHfFrguF1WjadV-Eg)

Re-implemented importing for Law and Order: Legacies / Jurassic Park and The Walking Dead Season 1. The models that used to crash 3DS Max with the former importer should be working fine now, there was a pretty nasty bug which I had to fix for material reading that caused an overflow.

Just got Bone, CSI, Sam & Max, SBCG4AP and Texas Hold'em left to fix up. They'll need more work than the rest, so it might be a bit longer.
## Post #239
- Username: MrUncleBingo
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Apr 24, 2017 10:58 am
- Post datetime: 2017-04-27T07:48:26+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

This shows up every time I try to open a D3DMESH. model of "Batman The TellTale Series" on 3DSMax (I Have the 2010 Version).
No matter what model of that game is (I tried with Catwoman, Batman, Gadgets, Vicky Vale, Environtments, etc...) and that kind of error shows up every time.

Any clue on what I'm doing wrong? It's an issue or the Script? My 3DSMax is trolling me?
## Post #240
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-27T07:54:42+00:00
- Post Title: Re: Telltale Almost-All-In-One Model Importer

> Reply from MrUncleBingo
>
> *image*

This shows up every time I try to open a D3DMESH. model of "Batman The TellTale Series" on 3DSMax (I Have the 2010 Version).
No matter what model of that game is (I tried with Catwoman, Batman, Gadgets, Vicky Vale, Environtments, etc...) and that kind of error shows up every time.

Any clue on what I'm doing wrong? It's an issue or the Script? My 3DSMax is trolling me?How strange. Send me one of those D3DMesh files (with the cooresponding .SKL) and I'll take a look, because it's definitely working over on my end (and I'm even using the same 3DS Max version, so it's definitely not because of that).
## Post #241
- Username: MrUncleBingo
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Apr 24, 2017 10:58 am
- Post datetime: 2017-04-27T08:00:52+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> MrUncleBingo wrote:*image*

This shows up every time I try to open a D3DMESH. model of "Batman The TellTale Series" on 3DSMax (I Have the 2010 Version).
No matter what model of that game is (I tried with Catwoman, Batman, Gadgets, Vicky Vale, Environtments, etc...) and that kind of error shows up every time.

Any clue on what I'm doing wrong? It's an issue or the Script? My 3DSMax is trolling me?How strange. Send me one of those D3DMesh files (with the cooresponding .SKL) and I'll take a look, because it's definitely working over on my end (and I'm even using the same 3DS Max version, so it's definitely not because of that).

Here: [http://www.mediafire.com/file/8gg3bgmre ... Output.rar](http://www.mediafire.com/file/8gg3bgmreto4snk/Output.rar)

There's Catwoman, all D3DMesh and SKL files included.
## Post #242
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-27T08:45:27+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from MrUncleBingo
>
> Here: http://www.mediafire.com/file/8gg3bgmre ... Output.rar

There's Catwoman, all D3DMesh and SKL files included.Well, this sucks. They're certainly different than what I've got.



There's a whole lot of differences with the headers, but the actual polygon/vertex information seems to be identical. I don't get it, but it absolutely looks like Telltale's making it difficult for me.

Either way, looks like I've got more work to do... At least the SKL files seem to be unchanged. But just to make sure, were these from something other than the Steam PC version (which I've been working with)?
## Post #243
- Username: MrUncleBingo
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Apr 24, 2017 10:58 am
- Post datetime: 2017-04-27T08:53:01+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I downloaded the game vía Mega, not Steam. Still is PC Version of course. I Can't play it because my PC can't support it enough (Or it can, but consumes around like the 90% of my PC CPU/Memory). I supposed maybe it will have problems, but like the version I downloaded it's a full one (ISO) and not a Rip Version or a Portable one, I don't think it's a problem of this specifical version, I hope. 

Also I extracted all the models fine with the TTArchExt (D3DMeshes, SKLetons, etc...), so I don't know really, this is the first time I try to extract models from a Game by myself, I don't know how this works, but after see the images you posted, I think I will have to wait a little more to make models of that Batman game.
## Post #244
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-27T09:50:42+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from MrUncleBingo
>
> I downloaded the game vía Mega, not Steam. Still is PC Version of course. I Can't play it because my PC can't support it enough (Or it can, but consumes around like the 90% of my PC CPU/Memory). I supposed maybe it will have problems, but like the version I downloaded it's a full one (ISO) and not a Rip Version or a Portable one, I don't think it's a problem of this specifical version, I hope. 

Also I extracted all the models fine with the TTArchExt (D3DMeshes, SKLetons, etc...), so I don't know really, this is the first time I try to extract models from a Game by myself, I don't know how this works, but after see the images you posted, I think I will have to wait a little more to make models of that Batman game.So a non-Steam version doesn't have the same files? That makes this case even more unusual, then. Regardless, I'll do what I can to make those work in the morning.
## Post #245
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2017-04-27T10:52:31+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Another problem with TWD Michonne.. the skeleton, according with the meshes, is imported in little size.. if you need i can give you pics.
Just tell me if is only is a my problem.
I use max 2011
## Post #246
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-27T11:22:45+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

@MrUncleBingo: Decided to check more thoroughly anyway (who needs sleep, am I ri--zzzzzzzzzzzzzzz). Seems almost all of the changes are in the way it reads the LOD information, for some reason. Hrm. I'll need to research that some more and find out why that is, but for now I added a hacky workaround which'll break out of the loop and skips the rest of the information if it detects something unexpected, for that and the others using the same base format (TWD3 and GotG).

[https://mega.nz/#!qkR0nJCZ!ImhNfUDaxL0n ... F1WjadV-Eg](https://mega.nz/#!qkR0nJCZ!ImhNfUDaxL0nN4dQahniuGQO3DGHfFrguF1WjadV-Eg)

Let me know if that works for you now.

> Reply from fil1969
>
> Another problem with TWD Michonne.. the skeleton, according with the meshes, is imported in little size.. if you need i can give you pics.
Just tell me if is only is a my problem.
I use max 2011Just the skeleton, or the models too? Because that's actually normal, the scale for the models is incredibly tiny. I don't really feel like adjusting the script to make 'em like 100x larger at the moment since I'd probably break a bunch of things in the process.

(EDIT: Never mind that last part, turns out it was really easy and I ended up doing so anyway. )
## Post #247
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2017-04-27T11:44:54+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> @MrUncleBingo: Decided to check more thoroughly anyway (who needs sleep, am I ri--zzzzzzzzzzzzzzz). Seems almost all of the changes are in the way it reads the LOD information, for some reason. Hrm. I'll need to research that some more and find out why that is, but for now I added a hacky workaround which'll break out of the loop and skips the rest of the information if it detects something unexpected, for that and the others using the same base format (TWD3 and GotG).

https://mega.nz/#!uoZG0SgL!SlY30IU_Cf9D ... GUgNUk-hoo

Let me know if that works for you now.
fil1969 wrote:Another problem with TWD Michonne.. the skeleton, according with the meshes, is imported in little size.. if you need i can give you pics.
Just tell me if is only is a my problem.
I use max 2011Just the skeleton, or the models too? Because that's actually normal, the scale for the models is incredibly tiny. I don't really feel like adjusting the script to make 'em like 100x larger at the moment since I'd probably break a bunch of things in the process.
Wait, i mean only Michonne character! Not all from TwD-Michonne!   Yes the script imports in tiny size, but is not a problem. With Michonne character, the skeleton is little more than the meshes. The other characters , till now, are perfect.
## Post #248
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2017-04-27T13:26:31+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Zombieali2000 wrote:riccochet wrote:That worked thanks... I'm not finding any .skl files though... everything else extracts. Am I missing a step?
Yeah im not seeing any .SKL Files either D: (WD:ANF)Oddly enough, the SKL files aren't grouped with the models in the "_txmesh" archives, they're in the "_data" files instead.
Hmmm..  that's the first thing I when I saw no skl files.. but all it extracts is some wav and .bank files.. im probably doing something wrong. I'll take another crack at it later and let you know. Thanks for the speedy replies and changes
## Post #249
- Username: mcemily
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 12, 2016 1:40 pm
- Post datetime: 2017-04-27T13:35:40+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I'm getting a runtime error when I try to run the latest WIP script.

"Runtime error: Can't load Button images: bitmap: "TelltaleIcons\WalkingDead1.bmp"
## Post #250
- Username: MrUncleBingo
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Apr 24, 2017 10:58 am
- Post datetime: 2017-04-27T18:15:22+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> @MrUncleBingo: Decided to check more thoroughly anyway (who needs sleep, am I ri--zzzzzzzzzzzzzzz). Seems almost all of the changes are in the way it reads the LOD information, for some reason. Hrm. I'll need to research that some more and find out why that is, but for now I added a hacky workaround which'll break out of the loop and skips the rest of the information if it detects something unexpected, for that and the others using the same base format (TWD3 and GotG).

https://mega.nz/#!uoZG0SgL!SlY30IU_Cf9D ... GUgNUk-hoo

Let me know if that works for you now.
fil1969 wrote:Another problem with TWD Michonne.. the skeleton, according with the meshes, is imported in little size.. if you need i can give you pics.
Just tell me if is only is a my problem.
I use max 2011Just the skeleton, or the models too? Because that's actually normal, the scale for the models is incredibly tiny. I don't really feel like adjusting the script to make 'em like 100x larger at the moment since I'd probably break a bunch of things in the process.


It worked! I export her to FBX, then used Noesis to export her to mesh.ascii, and now it's for XPS!
The only problem is I don't know how to extract the textures (I have the script for that, I just need to find the steps to extract them), but I will solve that probably in little time.

Still I will check another models later and tell you if they work too. Thanks !
## Post #251
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-27T20:19:55+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from mcemily
>
> I'm getting a runtime error when I try to run the latest WIP script.

"Runtime error: Can't load Button images: bitmap: "TelltaleIcons\WalkingDead1.bmp"Did you re-extract the "TelltaleIcons" folder, too? The icon for that was added in said update, and you'll need to re-extract that to make sure it's there.

> Reply from MrUncleBingo
>
> The only problem is I don't know how to extract the textures (I have the script for that, I just need to find the steps to extract them), but I will solve that probably in little time.

Still I will check another models later and tell you if they work too. Thanks !Just use QuickBMS with the "Telltale_D3DTX_Batman_GotG_TWD3.bms" script on the first post (in the "Download D3DTX to DDS QuickBMS Script" link), and run that on the *.d3dtx files, and you should get a bunch of DDS files. You'll have to manually apply them, unfortunately, but the filenames should help you figure out what goes where. Glad the model importer works for you, though!

Anyway, I'll add a model scale modifier into the next update since it's not really that difficult to implement after all. Default will be 100x size, but you'll be able to set it to whatever you want.
## Post #252
- Username: mcemily
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 12, 2016 1:40 pm
- Post datetime: 2017-04-27T23:43:27+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Did you re-extract the "TelltaleIcons" folder, too? The icon for that was added in said update, and you'll need to re-extract that to make sure it's there.

Haha, well, that was easy enough. My bad. 

Now that I can run the script... could you explain what the various options for the UV layers mean? 

Also... still can't get TFTBL's Moxxi model to work with this new version. Here's a screengrab of the resulting error:

[https://www.dropbox.com/s/j5o7u9cpa4ksf ... r.jpg?dl=0](https://www.dropbox.com/s/j5o7u9cpa4ksfvr/moxxiError.jpg?dl=0)

And here's her mesh and skl file if you want to take a look at them: [https://www.dropbox.com/s/ziheenys8o2km ... i.zip?dl=0](https://www.dropbox.com/s/ziheenys8o2kmgm/moxxi.zip?dl=0)
## Post #253
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-28T00:47:45+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from mcemily
>
> Now that I can run the script... could you explain what the various options for the UV layers mean? 

Also... still can't get TFTBL's Moxxi model to work with this new version. Here's a screengrab of the resulting error:

https://www.dropbox.com/s/j5o7u9cpa4ksf ... r.jpg?dl=0

And here's her mesh and skl file if you want to take a look at them: https://www.dropbox.com/s/ziheenys8o2km ... i.zip?dl=0"Merge" means it sets up the separate UV mapping layers appropriately, on the same mesh. "Split" means it uses the old behaviour, where separate UV mapping layers are put onto duplicate meshes, and "No" means it's ignored completely.

And dangit, I knew there was something I'd forgotten to check. There's no differences with the model you uploaded compared to what I've extracted already this time, but there's something unusual about her model in general. For some reason, there doesn't seem to be any rigging information stored in her model -- vertex buffer #1 only has vertex positions, normals and an unknown float value (either "1" or "0"), and vertex buffer #2 only contains UV mapping, binormals and tangents (or at least, I think they are, I honestly don't know what those are for).

Knowing my luck, it's probably located in a different file. Either way, I'll go figure out what the heck's going on with that.
## Post #254
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-04-28T01:17:44+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

It might be just me and I did something wrong, and so far I've only tried the Michonne model, but her eyes dont seem to have any colour, the whites of her eyes are still white but as you can see, they're pure black. It looks different on the picture with blue eyes, you can sort of see the iris colour around the edges, it looks like the pupils have dilated.

Brown
[https://puu.sh/vysrq/377f3c98bd.png](https://puu.sh/vysrq/377f3c98bd.png)

Blue
[https://puu.sh/vysGJ/0e5153c463.png](https://puu.sh/vysGJ/0e5153c463.png)

I took the pictures within XNALara, for the model I used sk55_michonne_eyesMouth.d3dmesh
## Post #255
- Username: MrUncleBingo
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Apr 24, 2017 10:58 am
- Post datetime: 2017-04-28T01:59:08+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> mcemily wrote:I'm getting a runtime error when I try to run the latest WIP script.

"Runtime error: Can't load Button images: bitmap: "TelltaleIcons\WalkingDead1.bmp"Did you re-extract the "TelltaleIcons" folder, too? The icon for that was added in said update, and you'll need to re-extract that to make sure it's there.
MrUncleBingo wrote:The only problem is I don't know how to extract the textures (I have the script for that, I just need to find the steps to extract them), but I will solve that probably in little time.

Still I will check another models later and tell you if they work too. Thanks !Just use QuickBMS with the "Telltale_D3DTX_Batman_GotG_TWD3.bms" script on the first post (in the "Download D3DTX to DDS QuickBMS Script" link), and run that on the *.d3dtx files, and you should get a bunch of DDS files. You'll have to manually apply them, unfortunately, but the filenames should help you figure out what goes where. Glad the model importer works for you, though!

Anyway, I'll add a model scale modifier into the next update since it's not really that difficult to implement after all. Default will be 100x size, but you'll be able to set it to whatever you want.

Thanks again !! Finally I made Catwoman for XPS!! (Kinda Hard the first time, but with time probably I gonna do more faster. Remembers me all the process to make Dragon Ball Xenoverse once again LOL!)
## Post #256
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-28T06:56:52+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Okay, I feel I'm gonna be asking a stupid question here, but... does Moxxi actually show up in Tales from the Borderlands, or is she only heard in the game? Because her model's one of the very few that seems to have that issue (the others being skB0_battleDroid_hologram and sk54_hyperionSuit_headE), even in the XBox 360 version. I haven't gotten a chance to play through it yet, but a quick Google search doesn't really come up with anything. I'm almost certain the reason why her model doesn't have rigging information because her model was never implemented. If that's the case, you're better off using her respective model from Poker Night 2, since it's almost the same as the one in TftBL.

That being said, at least I've updated the script again to fix that dumb bug where importing a skeleton with an unrigged model would cause it to error. Dunno how I missed that. And the scale modifier's there now, too.
[https://mega.nz/#!qkR0nJCZ!ImhNfUDaxL0n ... F1WjadV-Eg](https://mega.nz/#!qkR0nJCZ!ImhNfUDaxL0nN4dQahniuGQO3DGHfFrguF1WjadV-Eg)

This should be the last update before I get the rest of the games done.
## Post #257
- Username: Cappu
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 06, 2014 12:10 am
- Post datetime: 2017-04-28T13:49:08+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> does Moxxi actually show up in Tales from the Borderlands?
No ))

I encountered a problem when importing along with the skeleton - lost some meshes. It seems that the script throws them for some reason. This happens with models from 4 episode ANF (TWD S3). If I do import the same without a skeleton, then nothing is lost.
## Post #258
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-04-28T14:04:10+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Okay, I feel I'm gonna be asking a stupid question here, but... does Moxxi actually show up in Tales from the Borderlands, or is she only heard in the game?I think they reference her once and theres some pictures of her.

> Reply from RandomTBush
>
> This should be the last update before I get the rest of the games done.Does this include the problems I was having with Michonne's eyes?
## Post #259
- Username: mcemily
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 12, 2016 1:40 pm
- Post datetime: 2017-04-28T14:07:07+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> "Merge" means it sets up the separate UV mapping layers appropriately, on the same mesh. "Split" means it uses the old behaviour, where separate UV mapping layers are put onto duplicate meshes, and "No" means it's ignored completely.

And dangit, I knew there was something I'd forgotten to check. There's no differences with the model you uploaded compared to what I've extracted already this time, but there's something unusual about her model in general. For some reason, there doesn't seem to be any rigging information stored in her model -- vertex buffer #1 only has vertex positions, normals and an unknown float value (either "1" or "0"), and vertex buffer #2 only contains UV mapping, binormals and tangents (or at least, I think they are, I honestly don't know what those are for).

Knowing my luck, it's probably located in a different file. Either way, I'll go figure out what the heck's going on with that.

Ah, thanks for the definitions. And thanks for looking into that model! Moxxi never actually made an appearance in the game (aside from voice-over lines, anyway), so I wouldn't be surprised if her model sort of ended up abandoned along the way.
## Post #260
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-28T22:17:35+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> RandomTBush wrote:Okay, I feel I'm gonna be asking a stupid question here, but... does Moxxi actually show up in Tales from the Borderlands, or is she only heard in the game?I think they reference her once and theres some pictures of her.
RandomTBush wrote:This should be the last update before I get the rest of the games done.Does this include the problems I was having with Michonne's eyes?Yeah, that would definitely explain it, then. 

And as for the eyes, I think it's because of a shader effect. I'll have to check for myself.

> Reply from Cappu
>
> RandomTBush wrote:does Moxxi actually show up in Tales from the Borderlands?
No ))

I encountered a problem when importing along with the skeleton - lost some meshes. It seems that the script throws them for some reason. This happens with models from 4 episode ANF (TWD S3). If I do import the same without a skeleton, then nothing is lost.I'll double-check to make sure I haven't broken anything in the process of adding the fix.
## Post #261
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-04-29T12:57:38+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I'm encountering errors when importing any model from GotG. Not sure if this is a known bug or not.
[Capture.PNG](https://xentaxbackup.github.io/file/12832_Capture.PNG)
## Post #262
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-04-29T17:48:33+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I decided to have a look at some other TWD Michonne models to see if their eyes are the same and found this on the Alex model. His head doesnt show up afterwards so I assume it's his head (sk56_alex_head.d3dmesh).



I gave the others a quick look, I may have missed some like the Crabbers, but they look fine (other than the eyes).

Edit: Actually I think the version of Mario's 3DS to XNA I have is causing the problem with the eyes. Does anybody have an earlier version of his script I can use?
## Post #263
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-29T21:05:35+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from TRDaz
>
> I'm encountering errors when importing any model from GotG. Not sure if this is a known bug or not.
> Reply from Tydeus
>
> I decided to have a look at some other TWD Michonne models to see if their eyes are the same and found this on the Alex model. His head doesnt show up afterwards so I assume it's his head (sk56_alex_head.d3dmesh).Send both of them my way and I'll take a look, since I just tested and they're both working on my end. Wouldn't surprise me if it was another variant again.

> Reply from Tydeus
>
> Does this include the problems I was having with Michonne's eyes?Also just found out why this was happening for you and not for me. There's inverted faces for the irises, and I have the "Backface Cull on Object Creation" option enabled.

Left is without Backface Cull enabled, right is with.
## Post #264
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-04-29T21:53:15+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Send both of them my way, and I'll take a look. Wouldn't surprise me if it was another variant again.
Here is one skl and a few meshes, it seems to happen with all models for some reason, even Rocket (was surprised since you managed to import him with the screenshot you showed for progress) [https://www.dropbox.com/s/7z1vkmlr2w86l ... a.rar?dl=0](https://www.dropbox.com/s/7z1vkmlr2w86lc2/Gamora.rar?dl=0)

Batman seems to be working great though!
## Post #265
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-04-29T22:12:24+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Send both of them my way and I'll take a lookHere you go  I saved it with the textures too. [https://1drv.ms/u/s!AhWqylP2yJI3gmHxwAVIadbPe_Ed](https://1drv.ms/u/s!AhWqylP2yJI3gmHxwAVIadbPe_Ed)

> Reply from RandomTBush
>
> Also just found out why this was happening for you and not for me. There's inverted faces for the irises, and I have the "Backface Cull on Object Creation" option enabled. Left is without Backface Cull enabled, right is with.Ah, I thought that could've been on my end. I saved it to XNA using noesis and the eyes are fine.
## Post #266
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-29T22:14:27+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from TRDaz
>
> RandomTBush wrote:Send both of them my way, and I'll take a look. Wouldn't surprise me if it was another variant again.
Here is one skl and a few meshes, it seems to happen with all models for some reason, even Rocket (was surprised since you managed to import him with the screenshot you showed for progress) https://www.dropbox.com/s/7z1vkmlr2w86l ... a.rar?dl=0

Batman seems to be working great though!WHOOPS! Again! Turns out I accidentally broke that with the WIP script I uploaded, it's currently working fine on my debug script.

[https://mega.nz/#!qkR0nJCZ!ImhNfUDaxL0n ... F1WjadV-Eg](https://mega.nz/#!qkR0nJCZ!ImhNfUDaxL0nN4dQahniuGQO3DGHfFrguF1WjadV-Eg)

Sorry about that! I also went and re-enabled all of the older games. They're still using the old reading setups for now, but they've at least got the rigging fixes for Max 2012/2015 and such applied. I'll be working on re-parsing those next (since there's still quite a bit that end up breaking the script, like sk04_hoodedone.d3dmesh from Bone: Out from Boneville).

> Reply from Tydeus
>
> RandomTBush wrote:Send both of them my way and I'll take a lookHere you go  I saved it with the textures too. https://1drv.ms/u/s!AhWqylP2yJI3gmHxwAVIadbPe_EdAh, right. I see the problem. For whatever reason, the sk56_alex_eyesMouth.d3dmesh file is essentially empty. The script's getting caught on that since there's nothing to read in it, since the model parts are merged with the "head" mesh instead.
## Post #267
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-04-29T22:32:35+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

No problem! Thanks for the quick fix!
## Post #268
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-04-30T01:02:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> There's inverted faces for the irises, and I have the "Backface Cull on Object Creation" option enabled.I think I've always had that enabled but I'm fairly certain now that the problem is with the latest version of the xna converter script. The oldest version doesnt like the new models, and the new version does some other weird stuff. Noesis works perfectly 

> Reply from RandomTBush
>
> Ah, right. I see the problem. For whatever reason, the sk56_alex_eyesMouth.d3dmesh file is essentially empty.Yep! works perfectly without the eyesmouth!  you're awesome.
## Post #269
- Username: Konnie
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 23, 2017 11:33 pm
- Post datetime: 2017-04-30T17:15:33+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hey guys, I'm having problems with ttarchext.. I used it before to extract GoT files and it worked perfectly but ever since I deleted it and now wanting to get Guardians of the Galaxy models, when I run the program (ttarchext.exe), it just opens for 1 second and closes not allowing me to view the game ID, etc.
Anyways I can go around this or fix it?
Thank you!
## Post #270
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-04-30T18:35:35+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Konnie
>
> when I run the program (ttarchext.exe), it just opens for 1 second and closes not allowing me to view the game ID, etc. Anyways I can go around this or fix it?

Start > Run/search and then type in "CMD" without the quotations and drag and drop ttarchext.exe on to it. I dont think GotG appears on the list though, at least not the version I have.
## Post #271
- Username: mcemily
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 12, 2016 1:40 pm
- Post datetime: 2017-04-30T18:39:32+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Konnie
>
> Hey guys, I'm having problems with ttarchext.. I used it before to extract GoT files and it worked perfectly but ever since I deleted it and now wanting to get Guardians of the Galaxy models, when I run the program (ttarchext.exe), it just opens for 1 second and closes not allowing me to view the game ID, etc.
Anyways I can go around this or fix it?
Thank you!

What I did was to create a batch file. I've actually got two. One is just to see the games list and so on, to get the game numbers and the option letter codes I need. 

Open notepad and type this:
ttarchext.exe
pause

Save the file as a .bat file (I called mine ttg_games_info.bat). Then drop this .bat file in the same folder as ttarch.exe. Instead of running ttarch.exe, double-click this batch file to run it instead. It will run ttarch.exe for you, but the window will stay open so you can actually see the games list and so on (you'll have to scroll up a bit when the window opens).

The second batch file has the actual extraction info (source file location, output location, the game number, etc.) You'll need to extract both data.ttarch2 and txmesh.ttarch2 files in order to get all the files you need. You can either edit one batch file as you go, switching from data to txmesh, or you can create separate ones. Your call.

I don't know what GotG's number is (the version of ttarch.exe I have only goes up to TWD:Michonne, which is 59), but my guess would be either 60 or 61, so your batch file to extract the data archive (maybe call it extract_data_files.bat) might read:
ttarchext.exe -m 60 "location\of\file\you\want\to\extract\name_of_file_data.ttarch2" "location\you\want\to\save\extracted\files"

And your batch file to extract the txmesh archive (maybe call it extract_mesh_files.bat) might read:
ttarchext.exe -m 60 "location\of\file\you\want\to\extract\name_of_file_txmesh.ttarch2" "location\you\want\to\save\extracted\files"

Obviously, you'll need to replace the text within the "" to actual file locations. And if 60 is the wrong number try 61. These batch files work like the first one. Instead of running ttarch.exe, double-click the batch file and it'll open ttarch.exe for you and extract the files to the location you specifed.  

Hope this explanation made sense!
## Post #272
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-04-30T18:51:17+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> Konnie wrote:when I run the program (ttarchext.exe), it just opens for 1 second and closes not allowing me to view the game ID, etc. Anyways I can go around this or fix it?

Start > Run/search and then type in "CMD" without the quotations and drag and drop ttarchext.exe on to it. I dont think GotG appears on the list though, at least not the version I have.Yeah, GotG's not programmed into it yet, but [the key for it was posted here](http://forum.xentax.com/viewtopic.php?p=129856#p129856).
## Post #273
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-05-03T00:59:09+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Aaaaaaaaaalmost done revising the older importers now. The only thing I need to do for those is figure out how the normals are supposed to be read (2 bytes for three values? This is gonna take a while), and then I can upload the proper update for the script. I even fixed up the problem with various models in Strong Bad's Cool Game for Attractive People Episode 1:


Top is before, bottom is after. For some reason, a bunch of models in that game use triangle strips all of a sudden (and only for like 20-30 polygons out of the entire model), when none of Telltale's other games do (well, out of the ones supported at least). Thankfully one of the normally-unused header sections helped me out with that. And I also optimized the importer so well that the one function now works for 13 games/episodes at once (Hold'em, both of Bone's episodes, CSI episodes 3 and 4, the entirety of Sam & Max Season 1, and Season 2 episodes 1 and 2) instead of those all being different options, so that's pretty cool (and helps cut down the near-redundancy).

(EDIT: Well, the normals are certainly annoying to work with. Trying to figure out the pattern here, using a sphere (light_point.d3dmesh) as a reference point. Hrm...)

```
[-1,0,0] - 0x5F80 - 0101 1111 1000 0000
[0,1,0] - 0x7FBF - 0111 1111 1011 1111
[0,-1,0] - 0x003F - 0000 0000 0011 1111
[0,0,1] - 0x1FBF - 0001 1111 1011 1111
[0,0,-1] - 0x5FBF - 0101 1111 1011 1111

[0.25,0.951057,0.181636] - 0x3DCF - 0011 1101 1100 1111

[-0.25,0.951057,0.181636] - 0x3DAF - 0011 1101 1010 1111
[0.25,-0.951057,0.181636] - 0x01CF - 0000 0001 1100 1111
[0.25,0.951057,-0.181636] - 0x7DCF - 0111 1101 1100 1111

[-0.25,-0.951057,0.181636] - 0x01AF - 0000 0001 1010 1111
[0.25,-0.951057,-0.181636] - 0x41CF - 0100 0001 1100 1111
[-0.25,0.951057,-0.181636] - 0x7DAF - 0111 1101 1010 1111

[-0.25,-0.951057,-0.181636] - 0x41AF - 0100 0001 1010 1111
```


(EDIT 2: Nearly there! I figured out how to calculate the X and Y normal positions, but I'm stuck on the Z, which makes it look broken from the front but fine from the back.)
## Post #274
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-05-04T14:51:00+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Ah, I was going to write down which models I found faulty in the older games I worked on. I havent got through that many Walking Dead season 1 props/maps but I've found one or two problems if you want to have a look. There's maybe 4 character models in season 2 I found to be an issue too.

I can't say I've bothered with normal maps, they dont seem to make that much difference to me xD I probably should maybe.
## Post #275
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-05-04T15:12:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> Ah, I was going to write down which models I found faulty in the older games I worked on. I havent got through that many Walking Dead season 1 props/maps but I've found one or two problems if you want to have a look. There's maybe 4 character models in season 2 I found to be an issue too.

I can't say I've bothered with normal maps, they dont seem to make that much difference to me xD I probably should maybe.Well, if you can make a list of 'em for me to check, that'd be helpful so I can make sure I've squashed whatever bugs are left in the importer before I upload the next revision (which might be a while, still).
## Post #276
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-05-04T19:05:15+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Tydeus wrote:Ah, I was going to write down which models I found faulty in the older games I worked on. I havent got through that many Walking Dead season 1 props/maps but I've found one or two problems if you want to have a look. There's maybe 4 character models in season 2 I found to be an issue too.

I can't say I've bothered with normal maps, they dont seem to make that much difference to me xD I probably should maybe.Well, if you can make a list of 'em for me to check, that'd be helpful so I can make sure I've squashed whatever bugs are left in the importer before I upload the next revision (which might be a while, still).At the moment with TWD season 1, I've only managed to get through the first episode prop and map wise, but I did jump to episode 4 and 5 to steal things from the Savannah map so the list is pretty short. 

Season 1 is just texture issues.

Season 1 Episode 1
obj_sawhand
obj_copcar
obj_copcarcrash
adv_motorinn_meshesa
adv_motorinn_meshesd

Episode 4
adv_savannahstreets_meshesd

Episode 5
obj_boathouse105

I think a few pages back someone had an issue with the savannah sewer map textures too.

Season 2 Episode 1:
sk56_clementineFlashback
sk54_troy
sk54_troy_gun

Episode 3:
sk54_carver203_headDamageA
sk54_carver203_gun

Episode 4:
sk18_raccoon
sk54_nickZombie_headDamageA to C

I'm a bit of a noob, but I think it's weight issues with these. Rotate a few parts and you'll not miss it. Flashback Clem's hair is the problem, if you rotate bone5 on the raccoon it sort of splinters a lot. With Carver and nickZombie I loaded up their extra heads, it's definitely (maybe) their damaged heads.

With Troy, it's more of the same, but the gun in the holster wouldn't map correctly, unless I was using the wrong texture. I had the same issue with Jane and Carver's revolver too, so maybe it's just me getting the wrong texture.
## Post #277
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-05-04T19:08:41+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> RandomTBush wrote:Tydeus wrote:Ah, I was going to write down which models I found faulty in the older games I worked on. I havent got through that many Walking Dead season 1 props/maps but I've found one or two problems if you want to have a look. There's maybe 4 character models in season 2 I found to be an issue too.

I can't say I've bothered with normal maps, they dont seem to make that much difference to me xD I probably should maybe.Well, if you can make a list of 'em for me to check, that'd be helpful so I can make sure I've squashed whatever bugs are left in the importer before I upload the next revision (which might be a while, still).At the moment with TWD season 1, I've only managed to get through the first episode prop and map wise, but I did jump to episode 4 and 5 to steal things from the Savannah map so the list is pretty short. 

Season 1 is just texture issues.

Season 1 Episode 1
obj_sawhand
obj_copcar
obj_copcarcrash
adv_motorinn_meshesa
adv_motorinn_meshesd

Episode 4
adv_savannahstreets_meshesd

Episode 5
obj_boathouse105

I think a few pages back someone had an issue with the savannah sewer map textures too.

Season 2 Episode 1:
sk56_clementineFlashback
sk54_troy
sk54_troy_gun

Episode 3:
sk54_carver203_headDamageA
sk54_carver203_gun

Episode 4:
sk18_raccoon
sk54_nickZombie_headDamageA to C

I'm a bit of a noob, but I think it's weight issues with these. Rotate a few parts and you'll not miss it. Flashback Clem's hair is the problem, if you rotate bone5 on the raccoon it sort of splinters a lot. With Carver and nickZombie I loaded up their extra heads, it's definitely (maybe) their damaged heads.

With Troy, it's more of the same, but the gun in the holster wouldn't map correctly, unless I was using the wrong texture. I had the same issue with Jane and Carver's revolver too, so maybe it's just me getting the wrong texture.
Have you tried it with Doug from Episode 1 of Season 1?
## Post #278
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-05-04T21:21:08+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> Have you tried it with Doug from Episode 1 of Season 1?He's not my type, *peter griffin laugh* but yeah, I didnt have any problem with the season 1 models other than David, but RTB fixed that for me  I've shared them all on my deviantart page, they all seem to work! [http://akandrov.deviantart.com/](http://akandrov.deviantart.com/)

obj_sawhand was easy enough for me to fix, it took a while though.
before: [https://puu.sh/u1ksV/fad319a148.jpg](https://puu.sh/u1ksV/fad319a148.jpg)
after: [https://puu.sh/u1HVy/f93941efa1.png](https://puu.sh/u1HVy/f93941efa1.png)

and I sort of built a police car [https://puu.sh/u3Fgn/1a7a51e9ef.png](https://puu.sh/u3Fgn/1a7a51e9ef.png) but I'm probably missing something.
## Post #279
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-05-05T00:49:01+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> At the moment with TWD season 1, I've only managed to get through the first episode prop and map wise, but I did jump to episode 4 and 5 to steal things from the Savannah map so the list is pretty short. 

Season 1 is just texture issues.

*list*

I think a few pages back someone had an issue with the savannah sewer map textures too.

*another list*

I'm a bit of a noob, but I think it's weight issues with these. Rotate a few parts and you'll not miss it. Flashback Clem's hair is the problem, if you rotate bone5 on the raccoon it sort of splinters a lot. With Carver and nickZombie I loaded up their extra heads, it's definitely (maybe) their damaged heads.

With Troy, it's more of the same, but the gun in the holster wouldn't map correctly, unless I was using the wrong texture. I had the same issue with Jane and Carver's revolver too, so maybe it's just me getting the wrong texture.Have you been using the recent WIP script for those? Looks like I've already fixed those issues.  (The UV mapping problems in particular with the first TWD season were definitely because they used a different type, but the script should support those now.)

And the texture for Troy's gun seems to be obj_pistolColtPython, as it's the only one that matches the UV mapping.
## Post #280
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-05-05T10:19:10+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Have you been using the recent WIP script for those? Looks like I've already fixed those issues.  (The UV mapping problems in particular with the first TWD season were definitely because they used a different type, but the script should support those now.)

And the texture for Troy's gun seems to be obj_pistolColtPython, as it's the only one that matches the UV mapping.Most were before the new script, season 1 in 2015 and season 2 was finished the day you uploaded the script  I didn't actually know season 1/2 and the other games were working with the new script, I never tried!

I'll go look
## Post #281
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-05-05T11:07:10+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> RandomTBush wrote:Have you been using the recent WIP script for those? Looks like I've already fixed those issues.  (The UV mapping problems in particular with the first TWD season were definitely because they used a different type, but the script should support those now.)

And the texture for Troy's gun seems to be obj_pistolColtPython, as it's the only one that matches the UV mapping.Most were before the new script, season 1 in 2015 and season 2 was finished the day you uploaded the script  I didn't actually know season 1/2 and the other games were working with the new script, I never tried!

I'll go lookDon't blame ya for not knowing, [I kinda snuck it in not too long ago](http://forum.xentax.com/viewtopic.php?p=130082#p130082) when I was doing rapid-fire updates, heh.
## Post #282
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-05-05T12:39:44+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Don't blame ya for not knowing, I kinda snuck it in not too long ago when I was doing rapid-fire updates, heh.Ah! I missed that one  you've been busy! Everything works! and you even made it so the season 1 alphas are transparent, that saves even more time! Does it make any different to use merge or split other than creating separate layers btw?
## Post #283
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-05-05T13:35:57+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> Does it make any different to use merge or split other than creating separate layers btw?Nah, not really. The "split" option's mainly there for debugging purposes now, since it's good for checking if models have more than one UV mapping layer, or for anyone who might have preferred it the old way. Frankly, I'm not even sure if there's a difference speed-wise between importing with and without the UVs in general, the option's mainly there "just because". So yeah, it's pretty much unnecessary to change it.

Either way, it wouldn't make that much of a difference for character models, since any extra layers are normally identical since they're used for the "detail" textures more often than not -- The Wolf Among Us is the only one that I can think of that it's necessary to use since it's got differences with its UVs for those. Map models, on the other hand, would use it for their lightmaps texture... but I think there's something else that's not being calculated correctly for those since the UVs don't line up, so I'll have to take another look at it later (if there's enough demand, personally I feel getting a .SCENE importer is more important, but that'll happen later).
## Post #284
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-05-05T14:07:00+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Either way, it wouldn't make that much of a difference for character models, since any extra layers are normally identical since they're used for the "detail" textures more often than not -- The Wolf Among Us is the only one that I can think of that it's necessary to use since it's got differences with its UVs for those. Map models, on the other hand, would use it for their lightmaps texture... but I think there's something else that's not being calculated correctly for those since the UVs don't line up, so I'll have to take another look at it later (if there's enough demand, personally I feel getting a .SCENE importer is more important, but that'll happen later).Oh, so the details on the Wolf Among Us uses them? I've been adding the layers together within photoshop, but TWAU have them all weird and all over the place. If thats the case that'll be the next thing I play with! 

A scene importer would be something I'd be interested in, wouldnt that just be the same as loading the map meshes though? Oh and since TWD season 2+ doesnt have the textures pre-applied, is there any way to tell what texture goes where other than just guessing?
## Post #285
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-05-05T14:14:47+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> Oh, so the details on the Wolf Among Us uses them? I've been adding the layers together within photoshop, but TWAU have them all weird and all over the place. If thats the case that'll be the next thing I play with! 

A scene importer would be something I'd be interested in, wouldnt that just be the same as loading the map meshes though? Oh and since TWD season 2+ doesnt have the textures pre-applied, is there any way to tell what texture goes where other than just guessing?Yeah. Take Bigby's face model, for example, and you'll see exactly what I mean by that:

Left is the default, right is on the 3rd UV layer (for the "inkLinesHead" texture, for some reason there isn't a second layer). Frankly I'd use the Render to Texture method in 3DS Max to transfer the latter onto the main texture.

And yeah, the scene importer would basically do that, but it would also move all of the parts into the right spots, and import map props and such. Hopefully it shouldn't be too complex to figure out. As for the textures, not right now unfortunately, but if I ever figure out what kind of method they use to convert the texture names into the 8-byte hex doohickeys, I can start setting up a list to compare it to (like I have for the standard bones currently).
## Post #286
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-05-06T12:48:22+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Gah. I'm having too much trouble trying to figure out how the Z position for normals are stored, and frankly I'd rather get back to working on other things that I've been neglecting, so I'll just release it as-is for now since it's technically not a "WIP" anymore.
[https://mega.nz/#!npxnDAYI!PxjAzFz8Aw-N ... gTQGjeK2B8](https://mega.nz/#!npxnDAYI!PxjAzFz8Aw-Nr1Q_ApIvIWz3AAJqwYKmLgTQGjeK2B8)

```
Revised the UI to be more polished.
Added support for Batman: The Telltale Series, Marvel's Guardians of the Galaxy, The Walking Dead: A New Frontier and TWD: Michonne.
Changed bone numbers to bone checksums instead.
Added a ton of replacement bone names to replace the checksums, anything that doesn't have an official name will display numbers instead.
Optimized polygon group importing a bit so things will load a bit faster.
Fixed rigging being broken in one way or another for newer 3DS Max versions.
Updated the heck out of all of the older importers so that nothing should error anymore.
Fixed certain SBCG4AP Episode 1 models with triangle strips (eg. adv_strongbadhouseinterior_meshesa/c) so they are no longer missing polygons.

Known bugs:
Most of the top row of importers don't import with their normals. I'm still trying to figure out how to get those working...
ui_dealerbutton in Telltale Texas Hold'em doesn't work because it uses a different format for some reason.
Models with over 65,535 vertex points (eg. adv_virginiaRailroad_meshesD in TWD3) won't import due to awkward setups.

Oddities:
skB3_moxxi and skB0_battleDroid_hologram in TftBL both have no rigging. This isn't the fault of the importer, it's just the way they are.
```
So yeah. Enjoy! I'll probably make a new, better image for the first post sometime later this week or the next.

(And yes, I had to revise the UI again due to the unexpected optimization earlier. It'll do.)
## Post #287
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-05-06T14:40:37+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Yeah. Take Bigby's face model, for example, and you'll see exactly what I mean by that:

Left is the default, right is on the 3rd UV layer (for the "inkLinesHead" texture, for some reason there isn't a second layer). Frankly I'd use the Render to Texture method in 3DS Max to transfer the latter onto the main texture.I see what you mean, I just had a quick look at one of the models. This is good  at least with the inklineshead I'd be able to manually do it maybe. I havent touched the render to texture thing but I think I know how to use it lol maybe. The details would be an alpha thing right?

Scene sounds like something I'd definitely use! Prop sounds like it'd be exactly the same as doing it the usual way. I cant remember what the other files are now  for some reason I figured scene would be an actual scene with characters and everything lol.
## Post #288
- Username: thongTk
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun May 07, 2017 3:26 pm
- Post datetime: 2017-05-07T07:35:26+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

sorry if this is a noob question, but how do you know what textures the objects use? specifically the walking dead a new frontier's environment models or whatever they're called
## Post #289
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-05-07T08:26:41+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from thongTk
>
> sorry if this is a noob question, but how do you know what textures the objects use? specifically the walking dead a new frontier's environment models or whatever they're calledAlready answered this earlier, so I'll quote myself.
> Reply from RandomTBush
>
> fil1969 wrote:Anyway, about sceneries, is possible an autotexturing on import? I will take ages do all by hand! 
Again thank you so much!Unfortunately, no. Ever since The Walking Dead Season 2 / The Wolf Among Us, every single game of theirs resorted to hashes instead of proper file names for textures (likewise, they started doing so for bone names with SBCG4AP and onward), which means unless I can figure out the algorithm used, it's currently impossible for me to determine which texture should be used...For now, your best option is to guess what textures they use based on their filenames, or if that doesn't work, look for any textures that would match the UV mapping, and the numbers at the end are for their material IDs (i.e. two groups with "3" would share the same texture). Not much else I can do about that at the moment, unfortunately.
## Post #290
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-05-07T21:36:32+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Anyone have any idea how to fix alpha stuff? I seem to be having trouble with Pete's hair from TWD Michonne.

[https://puu.sh/vIRPL/790f499a62.png](https://puu.sh/vIRPL/790f499a62.png)

Edit: I found the issue, a few of my recent models were made using the merged UV option, I started to notice other texture issues when ported into XNA such as a triangle in their left eye, for Siddiq I had some black square texture on his leg, odd stuff like that. When I tried split, or none, the issue had gone. Which is kinda odd since only 6 of the models have the problem. hmm.
## Post #291
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-05-08T05:07:42+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> Anyone have any idea how to fix alpha stuff? I seem to be having trouble with Pete's hair from TWD Michonne.

https://puu.sh/vIRPL/790f499a62.png

Edit: I found the issue, a few of my recent models were made using the merged UV option, I started to notice other texture issues when ported into XNA such as a triangle in their left eye, for Siddiq I had some black square texture on his leg, odd stuff like that. When I tried split, or none, the issue had gone. Which is kinda odd since only 6 of the models have the problem. hmm.
I had that issue with Kenny's model from TWD2 but I fixed it by choosing No UV Layers.
## Post #292
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-05-10T01:01:17+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> Edit: I found the issue, a few of my recent models were made using the merged UV option, I started to notice other texture issues when ported into XNA such as a triangle in their left eye, for Siddiq I had some black square texture on his leg, odd stuff like that. When I tried split, or none, the issue had gone. Which is kinda odd since only 6 of the models have the problem. hmm.Hm, I guess that would be a good enough reason as any to disable it. How odd. If you wanna make that the default for importing your models, go to line 542 (should start with "radiobuttons tglUVLayers") and add "default:3" to the end of it.
## Post #293
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-05-10T12:59:03+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Hm, I guess that would be a good enough reason as any to disable it. How odd. If you wanna make that the default for importing your models, go to line 542 (should start with "radiobuttons tglUVLayers") and add "default:3" to the end of it.I've noticed there's no problems using mariokart's 3ds to xna script other than the eyes I brought up before though, so it might be something messing up when exporting as fbx or something.

Is there any way to set the default scale too?
## Post #294
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-05-10T13:04:02+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> Is there any way to set the default scale too?Of course, go to line 545 (a few lines down from the one I mentioned earlier), which should start with "spinner spnModelScale". Then for the "range: [1,99999,100]" section, just change the third number from 100 to whatever you want the default size to be.
## Post #295
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2017-05-12T13:20:02+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I wanted to ask like - is there any way i could find what textures using what model, because i'm gonna rip the whole Prescott location, and it'll be a complete f*** up to look what textures goes to what model in such a big location? Because there is a hundreds of them in ttarches in not all of them could be name to be related with Prescott it could be just - "brickwall.d3dtx" for example.
## Post #296
- Username: PixelBoyZ69
- Rank: n00b
- Number of posts: 13
- Joined date: Sat May 13, 2017 2:05 am
- Post datetime: 2017-05-14T03:03:15+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Minecraft story mode anyone?

Is anyone know where is the male edition of Jesse? Just extracted the .SKL last night but it always appear as Female Jesse
## Post #297
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-05-14T21:23:56+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

That sounds like a problem I keep forgetting about with TWD 400 Days lol, Eddie's mesh files are fine but I can't find his skl file at all.
## Post #298
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-05-14T21:51:26+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> That sounds like a problem I keep forgetting about with TWD 400 Days lol, Eddie's mesh files are fine but I can't find his skl file at all.According to sk54_eddie.prop, he uses "sk54_lee.skl" for his bone structure.

Since the .PROP files are what's used to build the models in-game, it's worth checking in cases like this when they use bone structures that don't match their file names.

(EDIT: Oh crap! I noticed there was a rigging problem with his model, all because of a goof in the script! I've updated my script to fix that issue now.)
[https://mega.nz/#!npxnDAYI!PxjAzFz8Aw-N ... gTQGjeK2B8](https://mega.nz/#!npxnDAYI!PxjAzFz8Aw-Nr1Q_ApIvIWz3AAJqwYKmLgTQGjeK2B8)
## Post #299
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2017-05-15T12:41:56+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hi RandomTBush, i need ur help with one glitch please, so my problem is i ripped Conrad's bar location from ANF and everything looks fine, besides one thing when ig o to the texture mode i get this glitch:
Image
And it doesn't matter if i apply material to model or not, it's have this glitch, I applied texture only to "Phantom Punch" machine for now just to show you that even if i apply texture to mesh it's still colored, i tried to add light sources in scene but it doesn't change anything, so i hope you know how to fix this, because i never had such problem with anything before!

EDIT: Nevermind problem solved
## Post #300
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-05-15T21:37:58+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

When I extracted Samantha Fairbanks's head texture, it was completely transparent.
## Post #301
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-05-15T23:58:34+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Since the .PROP files are what's used to build the models in-game, it's worth checking in cases like this when they use bone structures that don't match their file names.Ah, how would I open a .Prop file? Something like Notepadd++?
## Post #302
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-05-16T00:01:46+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> RandomTBush wrote:Since the .PROP files are what's used to build the models in-game, it's worth checking in cases like this when they use bone structures that don't match their file names.Ah, how would I open a .Prop file? Something like Notepadd++?Yeah, that'd work. It'd be in plaintext, you'd just have to look past all the random symbols until you see something with ".skl" at the end. Otherwise you'd use a hex editor to look through 'em.
## Post #303
- Username: PixelBoyZ69
- Rank: n00b
- Number of posts: 13
- Joined date: Sat May 13, 2017 2:05 am
- Post datetime: 2017-05-17T12:23:21+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I need some guidance, i just don't understand what should i do after extracting the .d3dtx to .dds, and what should i do with PROP and SKL files and how to open it in 3DS, sorry if this sounds like noob question because i'm a beginner in this forum (PM me if necessary)
## Post #304
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-05-18T00:34:08+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hm, for some reason the texture of the Layer_3's for Bigby doesnt all line up correctly. I did figure out the render to texture too but certain meshes creates a blank file as if there's nothing there. I guess I could always map the hair to the detail map rather than the other way around, though the texture messes up slightly, white dots everywhere 


> Reply from PixelBoyZ69
>
> I need some guidance, i just don't understand what should i do after extracting the .d3dtx to .dds, and what should i do with PROP and SKL files and how to open it in 3DS, sorry if this sounds like noob question because i'm a beginner in this forum (PM me if necessary)Once you've downloaded the script from the first page (TelltaleGames_D3DMesh) save it to your 3DS scripts folder, mine is C:\Program Files (x86)\Autodesk\3ds Max 2009\Scripts for example. Once in 3DS, click MAXScript at the top of the page, goto Run and run the script. Once you've selected which game you want, the script will ask you for the skl file first, and then the d3dmesh files after that, and it should load  then you can drag and drop the dds files to the model, obviously head goes with the head model etc.

I've probably missed something.
## Post #305
- Username: PixelBoyZ69
- Rank: n00b
- Number of posts: 13
- Joined date: Sat May 13, 2017 2:05 am
- Post datetime: 2017-05-18T10:30:45+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> Hm, for some reason the texture of the Layer_3's for Bigby doesnt all line up correctly. I did figure out the render to texture too but certain meshes creates a blank file as if there's nothing there. I guess I could always map the hair to the detail map rather than the other way around, though the texture messes up slightly, white dots everywhere 

PixelBoyZ69 wrote:I need some guidance, i just don't understand what should i do after extracting the .d3dtx to .dds, and what should i do with PROP and SKL files and how to open it in 3DS, sorry if this sounds like noob question because i'm a beginner in this forum (PM me if necessary)Once you've downloaded the script from the first page (TelltaleGames_D3DMesh) save it to your 3DS scripts folder, mine is C:\Program Files (x86)\Autodesk\3ds Max 2009\Scripts for example. Once in 3DS, click MAXScript at the top of the page, goto Run and run the script. Once you've selected which game you want, the script will ask you for the skl file first, and then the d3dmesh files after that, and it should load  then you can drag and drop the dds files to the model, obviously head goes with the head model etc.

I've probably missed something.

Thanks, now i just need to put the .dds file to 3ds max but unfortunately i don't know how
## Post #306
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-05-19T10:32:33+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from PixelBoyZ69
>
> Thanks, now i just need to put the .dds file to 3ds max but unfortunately i don't know howWell, what I've been doing is dragging them from the folder they're stored in, directly onto the model within 3ds max.
## Post #307
- Username: PixelBoyZ69
- Rank: n00b
- Number of posts: 13
- Joined date: Sat May 13, 2017 2:05 am
- Post datetime: 2017-05-20T16:14:17+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> PixelBoyZ69 wrote:Thanks, now i just need to put the .dds file to 3ds max but unfortunately i don't know how Well, what I've been doing is dragging them from the folder they're stored in, directly onto the model within 3ds max.

so... I drag and drop the .DDS file, but what happen is: [https://youtu.be/wQUzXv6Vcyk](https://youtu.be/wQUzXv6Vcyk)
## Post #308
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-05-21T19:35:55+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hey Random, I don't suppose you could fix the mapping with Bigby's Layer 3's could you? The face maps line up perfectly, I think most of the "WolfOut" textures are fine too, but the Wolf and the Bigby model, not so much.
## Post #309
- Username: Cappu
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 06, 2014 12:10 am
- Post datetime: 2017-05-31T13:04:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

quickbms's script (Telltale_D3DTX_Batman_GotG_TWD3.bms) can't convert new fifth episode's (A New Frontier​) textures. Telltale again change something in the file format ((
## Post #310
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2017-05-31T13:38:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Cappu
>
> quickbms's script (Telltale_D3DTX_Batman_GotG_TWD3.bms) can't convert new fifth episode's (A New Frontier​) textures. Telltale again change something in the file format ((
Works fine for me.
## Post #311
- Username: Cappu
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 06, 2014 12:10 am
- Post datetime: 2017-05-31T17:30:06+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko
>
> Works fine for me.

thanks for the reply. checked all again and found what the problem was. everything works ))
## Post #312
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-05-31T17:44:51+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Cappu
>
> jayko wrote:Works fine for me.

thanks for the reply. checked all again and found what the problem was. everything works ))Outdated version, I presume? Since there was the one glitch with Episodes 3 and 4 that I'd fixed earlier, after all.
## Post #313
- Username: Cappu
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 06, 2014 12:10 am
- Post datetime: 2017-05-31T18:42:34+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Outdated version, I presume?
No, there is just one file (goboRichmondApartments.d3dtx) that created an error and did not allow quickbms to convert rest of textures.
## Post #314
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-05-31T19:55:11+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Cappu
>
> RandomTBush wrote:Outdated version, I presume?
No, there is just one file (goboRichmondApartments.d3dtx) that created an error and did not allow quickbms to convert rest of textures.
Ah, that would explain it. I still need to update the script to export those and the lightprobe textures correctly (they contain multiple textures, which causes my script to error with 'em), might have some time later this week to do so.
## Post #315
- Username: PixelBoyZ69
- Rank: n00b
- Number of posts: 13
- Joined date: Sat May 13, 2017 2:05 am
- Post datetime: 2017-06-04T00:14:22+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Jesse face and mouth mesh are very messed up. Trying to fix this like 20 Times and always fail. I'm using 3DS Max 2017
[http://i.imgur.com/yUw0d7J.png](http://i.imgur.com/yUw0d7J.png)

My next step: installing 3DS Max 2009, and now i can't put the .dds textures into the models
[http://i.imgur.com/MxcwhUT.png](http://i.imgur.com/MxcwhUT.png)

Any help?
## Post #316
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-06-04T09:51:32+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from PixelBoyZ69
>
> Jesse face and mouth mesh are very messed up. Trying to fix this like 20 Times and always fail. I'm using 3DS Max 2017
http://i.imgur.com/yUw0d7J.png

My next step: installing 3DS Max 2009, and now i can't put the .dds textures into the models
http://i.imgur.com/MxcwhUT.png

Any help?Everything's working fine on my end.


And, uh, I can already see what's wrong with the second image, it's not because you're using too new of a 3DS Max version (it really shouldn't matter at this point as long as you're using something newer than 3DS Max 9), it's because you're trying to drag-and-drop the D3DTX files onto the model. You'll need to convert those to DDS first using the respective QuickBMS script before they can be used. And also try resizing the texture to about 16 times or so of its original size (using bilinear or pixel filtering, not smart-size) or disable texture filtering to make it look better.

...And on another note, if Telltale's indeed got three more projects they're working on at once, I've gonna need to update my script again sooner rather than later. Hopefully they won't be too difficult to support now that I have a better understanding of everything.
## Post #317
- Username: PixelBoyZ69
- Rank: n00b
- Number of posts: 13
- Joined date: Sat May 13, 2017 2:05 am
- Post datetime: 2017-06-05T07:24:02+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> it's because you're trying to drag-and-drop the D3DTX files onto the model
Welp, i didn't notice...   . Thanks anyway

> And also try resizing the texture to about 16 times or so of its original size (using bilinear or pixel filtering, not smart-size) or disable texture filtering to make it look better.
How? Did i need another editing application (such as Photoshop) or resize it in 3DS Max? And where is "Disable Texture Filtering" Options are located?

> ...And on another note, if Telltale's indeed got three more projects they're working on at once, I've gonna need to update my script again sooner rather than later.
Telltale are working for Tales of Borderlands Season 2, Minecraft Story Mode Season 2 and also James Bond - A Telltale Series. MCSM S2 just got rated by NZ and AU. I don't know much about Borderlands and James Bond Series, so... i have no idea (Edit: Borderlands Season 2 and James Bond Series are not yet confirmed)
## Post #318
- Username: mcemily
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 12, 2016 1:40 pm
- Post datetime: 2017-06-05T17:19:27+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from PixelBoyZ69
>
> Telltale are working for Tales of Borderlands Season 2, Minecraft Story Mode Season 2 and also James Bond - A Telltale Series. MCSM S2 just got rated by NZ and AU. I don't know much about Borderlands and James Bond Series, so... i have no idea (Edit: Borderlands Season 2 and James Bond Series are not yet confirmed)

Not to take this forum off-topic, but could you point me to whatever source mentioned Borderlands S2 and James Bond being in the works? I can only find mention of the Minecraft S2 being rated by AU/NZ. I know you said the other two aren't confirmed, but I'd be happy with even unconfirmed rumors/leaks of a Borderlands S2!
## Post #319
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-06-05T19:24:02+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from mcemily
>
> PixelBoyZ69 wrote:Telltale are working for Tales of Borderlands Season 2, Minecraft Story Mode Season 2 and also James Bond - A Telltale Series. MCSM S2 just got rated by NZ and AU. I don't know much about Borderlands and James Bond Series, so... i have no idea (Edit: Borderlands Season 2 and James Bond Series are not yet confirmed)

Not to take this forum off-topic, but could you point me to whatever source mentioned Borderlands S2 and James Bond being in the works? I can only find mention of the Minecraft S2 being rated by AU/NZ. I know you said the other two aren't confirmed, but I'd be happy with even unconfirmed rumors/leaks of a Borderlands S2!Well, it seems that Tales from the Borderlands 2 might've been disproved according to another tweet from the same guy who posted the original leak, with the original assets used for that.
[https://twitter.com/AnEvilHag/status/871101569290383360](https://twitter.com/AnEvilHag/status/871101569290383360)

So that might also mean that Solstice isn't a thing, either. But it's only like a week away from E3, so we'll see what happens then.
## Post #320
- Username: mcemily
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 12, 2016 1:40 pm
- Post datetime: 2017-06-05T19:47:33+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> mcemily wrote:PixelBoyZ69 wrote:Telltale are working for Tales of Borderlands Season 2, Minecraft Story Mode Season 2 and also James Bond - A Telltale Series. MCSM S2 just got rated by NZ and AU. I don't know much about Borderlands and James Bond Series, so... i have no idea (Edit: Borderlands Season 2 and James Bond Series are not yet confirmed)

Not to take this forum off-topic, but could you point me to whatever source mentioned Borderlands S2 and James Bond being in the works? I can only find mention of the Minecraft S2 being rated by AU/NZ. I know you said the other two aren't confirmed, but I'd be happy with even unconfirmed rumors/leaks of a Borderlands S2!Well, it seems that Tales from the Borderlands 2 might've been disproved according to another tweet from the same guy who posted the original leak, with the original assets used for that.
https://twitter.com/AnEvilHag/status/871101569290383360

So that might also mean that Solstice isn't a thing, either. But it's only like a week away from E3, so we'll see what happens then.

Ah, yeah... that looks like a "wishful thinking" fan render to me.    As you say... we'll see what Telltale has to say for themselves at E3.
## Post #321
- Username: PixelBoyZ69
- Rank: n00b
- Number of posts: 13
- Joined date: Sat May 13, 2017 2:05 am
- Post datetime: 2017-06-05T22:51:17+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Actually i just want to ask about this, but its ok, at least we know that Borderlands S2 are fake, and Solstice isn't a thing, but who knows?  

> And also try resizing the texture to about 16 times or so of its original size (using bilinear or pixel filtering, not smart-size) or disable texture filtering to make it look better.
How?
## Post #322
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-06-05T23:06:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from PixelBoyZ69
>
> And also try resizing the texture to about 16 times or so of its original size (using bilinear or pixel filtering, not smart-size) or disable texture filtering to make it look better.How?Use an image-editing program, of course. I'd suggest GIMP if you want something worthwhile that's free.
## Post #323
- Username: PixelBoyZ69
- Rank: n00b
- Number of posts: 13
- Joined date: Sat May 13, 2017 2:05 am
- Post datetime: 2017-06-06T14:19:13+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> PixelBoyZ69 wrote:And also try resizing the texture to about 16 times or so of its original size (using bilinear or pixel filtering, not smart-size) or disable texture filtering to make it look better.How?Use an image-editing program, of course. I'd suggest GIMP if you want something worthwhile that's free.

Uhh... I don't understand these stuff   .Is there any tutorial about how to resizing texture using bilinear/ pixel filtering (Photoshop/ GIMP) on Youtube? That would be helpful
## Post #324
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2017-06-12T14:28:47+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hi there RandomTBrush, so i have a little problem here, i import Clem model with ur script(but this problem is actually with any model i import) but it looks like this:


So as you can see some of the models have black color, and even if apply material and texture of this model, the black colour still be there, and the texture will be very dark because of it, i tried to make these black models white (in both 3DS Max and Blender) but with no luck, i tried everything, but the model still stands black. Also one thing - if export this model to .obj, and import back, these black colors will gone and become white, but this would not work out for me, because if i import it to any other format than .obj, i will loose the Armature and vertexes things! So i hope you can help me with that!
## Post #325
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-06-12T20:26:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum
>
> Hi there RandomTBrush, so i have a little problem here, i import Clem model with ur script(but this problem is actually with any model i import) but it looks like this:
*image*

So as you can see some of the models have black color, and even if apply material and texture of this model, the black colour still be there, and the texture will be very dark because of it, i tried to make these black models white (in both 3DS Max and Blender) but with no luck, i tried everything, but the model still stands black. Also one thing - if export this model to .obj, and import back, these black colors will gone and become white, but this would not work out for me, because if i import it to any other format than .obj, i will loose the Armature and vertexes things! So i hope you can help me with that!Did you enable the "Enable vertex colours?" option? That's normal, if that's the case. I'm not sure what those are used for in most of the models I've looked at, hence why it's disabled by default.

Alternatively, you can add a "Vertex Paint" modifier to all of the polygon sections, and then click the third box at the top to disable previewing for those.
## Post #326
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2017-06-13T12:41:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Maximmum wrote:Hi there RandomTBrush, so i have a little problem here, i import Clem model with ur script(but this problem is actually with any model i import) but it looks like this:
*image*

So as you can see some of the models have black color, and even if apply material and texture of this model, the black colour still be there, and the texture will be very dark because of it, i tried to make these black models white (in both 3DS Max and Blender) but with no luck, i tried everything, but the model still stands black. Also one thing - if export this model to .obj, and import back, these black colors will gone and become white, but this would not work out for me, because if i import it to any other format than .obj, i will loose the Armature and vertexes things! So i hope you can help me with that!Did you enable the "Enable vertex colours?" option? That's normal, if that's the case. I'm not sure what those are used for in most of the models I've looked at, hence why it's disabled by default.

Alternatively, you can add a "Vertex Paint" modifier to all of the polygon sections, and then click the third box at the top to disable previewing for those.

Yep you're right, i went to the Vertex Paint mode and quickly paint all black models to white    Thank You very much
## Post #327
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-06-20T22:56:58+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

RTB, Clementine's tongue rotates wired when I rotate the jaw bone.
## Post #328
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-06-20T23:25:05+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> RTB, Clementine's tongue rotates wired when I rotate the jaw bone.this is how model been done for animation purpose. there's nothing RTB can do about it.
## Post #329
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-06-20T23:27:50+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tosyk
>
> Escope12 wrote:RTB, Clementine's tongue rotates wired when I rotate the jaw bone.this is how model been done for animation purpose. there's nothing RTB can do about it.^ This. If it's not the vertex points stretching oddly (which shouldn't happen anymore), then it's probably intentional.
## Post #330
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-06-21T00:16:22+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Tosyk wrote:Escope12 wrote:RTB, Clementine's tongue rotates wired when I rotate the jaw bone.this is how model been done for animation purpose. there's nothing RTB can do about it.^ This. If it's not the vertex points stretching oddly (which shouldn't happen anymore), then it's probably intentional.
That's strange. Thanks for telling me.
## Post #331
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-07-02T22:29:41+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Quick question, not sure if it's been asked, but is there a quicker way to get the details onto the textures for Walking Dead New Frontier? I've been adding a white layer and using one of the effects to get the usual we had in TWD2.

Also I've noticed some of the details are messed up, Hector's head details are all black with like a bunch of staggered yellow lines down the side, like as if I printed it out and the ink is running low  and theres others that are entirely light blue with no lines, all without alpha channels.
## Post #332
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-07-03T23:37:32+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Also, some of the vehicles in season 1, the bones dont work. I think the police car for example, not sure about the others since I did those bones myself. And this may be part of the known issue listed on the first page, but the airportExterior doesnt want to load.

headerskip = (readlong f #unsigned - 4) + (ftell f) with error message -- No ""-"" function for undefined. 

Not too sure whats going on with those detail textures still, half of them are messed up. Has anyone came across the texture issue?
## Post #333
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-07-10T22:04:15+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I know that I reported this earlier but there is something wrong with Edith's eyelash UV's. Is this possible to fix?
## Post #334
- Username: mcemily
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 12, 2016 1:40 pm
- Post datetime: 2017-07-20T01:25:13+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I'm getting an error with "adv_vaultInterior_meshesA.d3dmesh" in ep. 5 of Tales from the Borderlands.  When I try to import it into 3dsMax (2012 version, if that matters), I get "--Unable to convert: [0,0,0] to type: Float"

Edited to Add:

I get the same error with the following Vault-related meshes:

obj_floatingPlatformNewAVaultInterior (ditto for PlatformNew B, C)
obj_floatingStairsNewAVaultInterior (ditto for B, C, D, E, F, G)
obj_mainHallwayVaultInterior
## Post #335
- Username: Kett
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 12, 2014 5:16 am
- Post datetime: 2017-08-08T17:48:13+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

When I try to convert textures from Minecraft: Story Mode, few objects and most characters end up like this:



It seems that the first line of the texture is extracted, and then it stops
## Post #336
- Username: Marusero
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jan 15, 2012 4:12 am
- Post datetime: 2017-08-10T19:35:14+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Can anybody help me?
I'm trying to edit *.font and *.d3dtx version PS3 game TWD Season One.
Only I do not get anyone.
## Post #337
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-08-12T23:52:52+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> I know that I reported this earlier but there is something wrong with Edith's eyelash UV's. Is this possible to fix?
I think you may not be using the right texture for that. If there are UV mapping issues, it would affect the entire model and not just a portion of it (the vertex buffer is the same throughout the entire model, after all). Either way, I'll look into that as well and report back if something is indeed wrong.

> Reply from Kett
>
> When I try to convert textures from Minecraft: Story Mode, few objects and most characters end up like this:



It seems that the first line of the texture is extracted, and then it stopsHm, just making sure, are you using the right script (Telltale_D3DTX_TftBL_GoT_MCSM) with the most recent version of QuickBMS? If not, sounds like something I'll need to look into as well. (Or maybe because they're treated as full RGBA32 DDS textures that some programs can't read properly? Could be a lot of things.)

> Reply from Tydeus
>
> Quick question, not sure if it's been asked, but is there a quicker way to get the details onto the textures for Walking Dead New Frontier? I've been adding a white layer and using one of the effects to get the usual we had in TWD2.

Also I've noticed some of the details are messed up, Hector's head details are all black with like a bunch of staggered yellow lines down the side, like as if I printed it out and the ink is running low  and theres others that are entirely light blue with no lines, all without alpha channels.You might be able to do the former using the "Composite" material format if you're doing so for renders.

As for the latter, I think that's actually normal since the red and green store different information (basically like a mask texture), but I'm gonna check those out again later just to make sure I'm reading them correctly (and that they're not SNORM being read as UNORM and such).

> Reply from Tydeus
>
> Also, some of the vehicles in season 1, the bones dont work. I think the police car for example, not sure about the others since I did those bones myself. And this may be part of the known issue listed on the first page, but the airportExterior doesnt want to load.

headerskip = (readlong f #unsigned - 4) + (ftell f) with error message -- No ""-"" function for undefined. 

Not too sure whats going on with those detail textures still, half of them are messed up. Has anyone came across the texture issue?
> Reply from mcemily
>
> I'm getting an error with "adv_vaultInterior_meshesA.d3dmesh" in ep. 5 of Tales from the Borderlands.  When I try to import it into 3dsMax (2012 version, if that matters), I get "--Unable to convert: [0,0,0] to type: Float"

Edited to Add:

I get the same error with the following Vault-related meshes:

obj_floatingPlatformNewAVaultInterior (ditto for PlatformNew B, C)
obj_floatingStairsNewAVaultInterior (ditto for B, C, D, E, F, G)
obj_mainHallwayVaultInteriorI'll look into fixing up those problems soon, since I also gotta fix up the importing functionality for Batman: The Enemy Within after all (Minecraft: Story Mode Season 2 works with the Guardians of the Galaxy importer, so I don't need to do much else for that). That, and fix up some of the map models not importing correctly for GotG (they were working before I'd implemented the one alternate model fix earlier, hrm...).

Needless to say, I'll post the update when it's ready.
## Post #338
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-08-14T02:31:29+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Quick progress report since it's gonna be a little bit longer than expected:

Got most models from Batman: The Enemy Within working with the script now (with both bones and meshes at the same time, the current problem was from me mislabelling one of the values, whoops!). Some still don't want to work correctly though (e.g. sk61_batman201_handsBatTech), so I'll be fixing that up first before posting the script update.

@Tydeus: I've fixed the rigging issue with the cop car in TWD Season 1 (and certainly any others with that same problem). Turns out that one of the values I had listed as "unknown2" is actually used as the bone ID for single-bind models, so I'll need to apply the same changes to the other model importers where applicable. Always nice to find out what unknowns are actually for. Not sure what's going in with the airportExterior models yet, but it's probably not working because there's something unexpected in the headers. Hopefully won't be too difficult to fix.

@mcemily: I'm not sure why those models aren't working for you, I tried the same ones from my collection and they all seemed to import fine. Send me the ones you've got through a PM so I can compare, hopefully it's not another variant format again...

@escope12: Yeah, you're definitely using the wrong texture, "sk55_guardWellington_hairAlpha" is the correct one. As I've said before, if you're unsure as to what texture to use, try looking through the textures and find the one that matches the UV mapping.
## Post #339
- Username: Kett
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 12, 2014 5:16 am
- Post datetime: 2017-08-14T16:52:21+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Hm, just making sure, are you using the right script (Telltale_D3DTX_TftBL_GoT_MCSM) with the most recent version of QuickBMS? If not, sounds like something I'll need to look into as well. (Or maybe because they're treated as full RGBA32 DDS textures that some programs can't read properly? Could be a lot of things.)

Yeah, using the most recent version, and the size of these files is also alot smaller than the others.
## Post #340
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-08-14T18:40:30+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Kett
>
> Hm, just making sure, are you using the right script (Telltale_D3DTX_TftBL_GoT_MCSM) with the most recent version of QuickBMS? If not, sounds like something I'll need to look into as well. (Or maybe because they're treated as full RGBA32 DDS textures that some programs can't read properly? Could be a lot of things.)

Yeah, using the most recent version, and the size of these files is also alot smaller than the others.Hrm, so smaller than 4.12KB, then? Send both the D3DTX and DDS files my way so I can have a look.
## Post #341
- Username: takiya
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 12, 2017 4:00 am
- Post datetime: 2017-08-23T06:56:11+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Telltale_D3DTX_TFTBL_GoT_MCSM can not be used for minecraft story mode season 2


please help me -_-
## Post #342
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-08-23T08:38:28+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from takiya
>
> Telltale_D3DTX_TFTBL_GoT_MCSM can not be used for minecraft story mode season 2

please help me -_-I already know about that, I'll have an updated script for that at the same time as the MaxScript update.
## Post #343
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-08-25T04:44:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Tydeus wrote:--snip-- stuff here about detail maps in new frontierYou might be able to do the former using the "Composite" material format if you're doing so for renders.

As for the latter, I think that's actually normal since the red and green store different information (basically like a mask texture), but I'm gonna check those out again later just to make sure I'm reading them correctly (and that they're not SNORM being read as UNORM and such).Thanks for the reply, my PC died a while back so I didnt see this message, but I asked around and found a solution to the issue. The detail map how I described it with Hectors head, I think it was intended to be like that for the game but I needed to run the texture through Noesis and re-save it in order to get the result I wanted. (matching all the other detail maps), so everything is fine on that front.
## Post #344
- Username: PixelBoyZ69
- Rank: n00b
- Number of posts: 13
- Joined date: Sat May 13, 2017 2:05 am
- Post datetime: 2017-08-25T06:24:57+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> takiya wrote:Telltale_D3DTX_TFTBL_GoT_MCSM can not be used for minecraft story mode season 2

please help me -_-I already know about that, I'll have an updated script for that at the same time as the MaxScript update.

Wait, wait... If you want to open the character files, you also need to Extract the game files first (You recommended TTARCHEXT right? I used that for Extracting the files). But, the problem is, TTARCHEXT seems doesn't support MCSM Season 2 (Yes, because i've seen the page before and it doesn't mention MCSM Season 2 in "Supported Games" list)

And, when you will release the updated script?
## Post #345
- Username: sandex7978
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Aug 19, 2017 3:44 pm
- Post datetime: 2017-08-28T10:39:09+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hi, RTB. I read through the thread and you are clearly always on top of issues so I am thinking that this new problem is possibly my dumb dumb doing. But I don't know how. I keep getting a "putarray" error. It doen't matter what file I try to extract or what accepted options I use, it comes out the same. I have many gb of free space on all my drives so that is definitely not the issue.

I have some experience with qbms but am by no means an expert so idk wtf the issue is. Me, my pc, qbms, the script, the game, the silver surfer, ,some potatoes.....  all are potential bandits as far as I am concerned until you tell me otherwise. Thanks, mane, the script looks doper than roper, I just want a little taste....
## Post #346
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2017-09-25T15:20:06+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

So how's the progress on Batman: The Enemy Within importer goes? Really want to export some models from it, especially Harley from upcoming episode 2!
## Post #347
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-09-30T22:45:55+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Would it be possible to add an option to use PNG instead of DDS Textures for the 3DS Max Script?
## Post #348
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-09-30T23:29:06+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> Would it be possible to add an option to use PNG instead of DDS Textures for the 3DS Max Script?I've already implemented that in the work-in-progress script update. (Still doesn't work with newer games, though.)

> Reply from Maximmum
>
> So how's the progress on Batman: The Enemy Within importer goes? Really want to export some models from it, especially Harley from upcoming episode 2!I should have some more time later this coming week to work on it, and once I've got the last problems fixed the update should be out soon after.
## Post #349
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-10-02T17:12:45+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Escope12 wrote:Would it be possible to add an option to use PNG instead of DDS Textures for the 3DS Max Script?I've already implemented that in the work-in-progress script update. (Still doesn't work with newer games, though.)
Is it because of the material hash that we can't figure out yet? I might be wrong though.
## Post #350
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-10-03T02:03:53+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Does anyone know how to fix the detail textures for The Walking Dead: A New Frontier?
## Post #351
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-10-03T20:13:42+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> Is it because of the material hash that we can't figure out yet? I might be wrong though.Well, yeah. If anyone's good at debugging and can figure out the hashing algorithm used for the bone names and most likely the texture names (e.g. "root" = 0x765BA466632FD7A5, "spine1" = 0x617CC8ECC1D6CE76, "spine2" = 0x9B42935906C7EC4A, etc.), then I can do a batch-conversion of all of the texture names from the newer games and fix this issue.

> Reply from Escope12
>
> Does anyone know how to fix the detail textures for The Walking Dead: A New Frontier?Already answered that:

> Reply from RandomTBush
>
> Tydeus wrote:...

Also I've noticed some of the details are messed up, Hector's head details are all black with like a bunch of staggered yellow lines down the side, like as if I printed it out and the ink is running low  and theres others that are entirely light blue with no lines, all without alpha channels....

As for the latter, I think that's actually normal since the red and green store different information (basically like a mask texture), but I'm gonna check those out again later just to make sure I'm reading them correctly (and that they're not SNORM being read as UNORM and such).
## Post #352
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-10-03T20:23:55+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Escope12 wrote:Is it because of the material hash that we can't figure out yet? I might be wrong though.Well, yeah. If anyone's good at debugging and can figure out the hashing algorithm used for the bone names and most likely the texture names (e.g. "root" = 0x765BA466632FD7A5, "spine1" = 0x617CC8ECC1D6CE76, "spine2" = 0x9B42935906C7EC4A, etc.), then I can do a batch-conversion of all of the game's texture names and fix this issue.
Escope12 wrote:Does anyone know how to fix the detail textures for The Walking Dead: A New Frontier?Already answered that:
RandomTBush wrote:Tydeus wrote:...

Also I've noticed some of the details are messed up, Hector's head details are all black with like a bunch of staggered yellow lines down the side, like as if I printed it out and the ink is running low  and theres others that are entirely light blue with no lines, all without alpha channels....

As for the latter, I think that's actually normal since the red and green store different information (basically like a mask texture), but I'm gonna check those out again later just to make sure I'm reading them correctly (and that they're not SNORM being read as UNORM and such).Looks like I’ll have to wait a little bit. I really hope someone can help debug the material hash.
## Post #353
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-10-04T07:12:18+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Alright, looks like the script's in working order for the Batman: The Enemy Within models now. Once I get the texture-conversion script done for Minecraft: Season 2 (and after I've adjusted a couple more things), I'll be releasing the update!
## Post #354
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-10-04T17:44:17+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> Does anyone know how to fix the detail textures for The Walking Dead: A New Frontier?I told you about that on DeviantArt, open the broken textures in Noesis and export them back as DDS, they should be fine after that.
## Post #355
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-10-05T00:14:55+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> Escope12 wrote:Does anyone know how to fix the detail textures for The Walking Dead: A New Frontier?I told you about that on DeviantArt, open the broken textures in Noesis and export them back as DDS, they should be fine after that.
It's a bad idea to export to DDS, because of recompression and quality loss, it's better to export to something lossless, like PNG, then reassign.
## Post #356
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-10-05T00:44:58+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Script's been updated now!

```
Added some more options to change texture format (from DDS to PNG), path (either in the same folder or in a separate "Textures" folder), and outputting debug crap if you want.
Fixed rigging for single-bind models for The Walking Dead Season 1 models (e.g. the cop car).
Re-fixed maps and such not loading properly for TWDS3, Batman S1 and GotG due to accidentally breaking it in the previous update. Whoops!
```

[https://mega.nz/#!X9oSlTLC!2-K7JYcGobjr ... -5stmRUyoA](https://mega.nz/#!X9oSlTLC!2-K7JYcGobjrEJ_MRn4kyCCXb5-ZK-Yt9-5stmRUyoA)
(EDIT: If you downloaded it earlier, please re-download, as I accidentally broke the TWD3 importer!)
(EDIT 2: And if you downloaded it before 10/10/2017, please re-redownload it as I'm a twit and made a stupid mistake.)

And here's the updated QuickBMS script pack for the textures for Batman: TEW and MCSM:S2. Turns out I didn't need to write a new script, I just needed to adjust a few things with the current one.
[https://mega.nz/#!35xByISR!R9ExvMyMqtUf ... HGNBv65HDw](https://mega.nz/#!35xByISR!R9ExvMyMqtUfBQe-OuYaSw3AOmNU1ZP2zHGNBv65HDw)
## Post #357
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-10-05T03:06:30+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Andrakann
>
> Tydeus wrote:Escope12 wrote:Does anyone know how to fix the detail textures for The Walking Dead: A New Frontier?I told you about that on DeviantArt, open the broken textures in Noesis and export them back as DDS, they should be fine after that.
It's a bad idea to export to DDS, because of recompression and quality loss, it's better to export to something lossless, like PNG, then reassign.I was just saying in general rather than listing the other formats, but it's only the detail maps. I can't say it really matters about those.

> Reply from RandomTBush
>
> Re-fixed maps and such not loading properly for GotG due to accidentally breaking it in the previous update. Whoops![/code]Does that include the map stuff from TWD3 too? I havent got to that game yet but I remember there was an issue with that.
## Post #358
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-10-05T03:19:36+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Which quickbms script do I use to convert The Walking Dead Season 1 textures from D3DTX to DDS?
## Post #359
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-10-05T04:21:00+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> Which quickbms script do I use to convert The Walking Dead Season 1 textures from D3DTX to DDS?Doesn't TTArchExt have the ability to automatically convert those?
## Post #360
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-10-05T04:35:42+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Tydeus wrote:Does that include the map stuff from TWD3 too? I havent got to that game yet but I remember there was an issue with that....Ah, crap, I completely forgot to check that (and it turns out I accidentally broke it further!), so I'll go fix that up ASAP.
Escope12 wrote:Which quickbms script do I use to convert The Walking Dead Season 1 textures from D3DTX to DDS?Doesn't TTArchExt have the ability to automatically convert those?
I’m not sure. I’ve used Telltale Explorer to convert them to dds.
## Post #361
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-10-05T04:52:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> Does that include the map stuff from TWD3 too? I havent got to that game yet but I remember there was an issue with that....Ah, crap, I completely forgot to check that (and it turns out I accidentally broke it further!).

Script's fixed now! Sorry about that! And yeah, it should be working now as it was due to the same problem that the GotG models had.
[https://mega.nz/#!X9oSlTLC!2-K7JYcGobjr ... -5stmRUyoA](https://mega.nz/#!X9oSlTLC!2-K7JYcGobjrEJ_MRn4kyCCXb5-ZK-Yt9-5stmRUyoA)
## Post #362
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-10-05T17:37:59+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Ah, crap, I completely forgot to check that (and it turns out I accidentally broke it further!).

Script's fixed now! Sorry about that! And yeah, it should be working now as it was due to the same problem that the GotG models had.
https://mega.nz/#!78wkHZBB!xB8sOiwMOd5t ... 2_V4jOSk8Mno worries!  although now it means I have no excuse to put off TWD3 =/ lol

> Reply from Escope12
>
> RandomTBush wrote:Escope12 wrote:Which quickbms script do I use to convert The Walking Dead Season 1 textures from D3DTX to DDS?Doesn't TTArchExt have the ability to automatically convert those?I’m not sure. I’ve used Telltale Explorer to convert them to dds.I've had issues in the past trying to convert them to DDS with the TTArch thing myself, I think it brings up errors, but yeah Telltale Explorer works fine for the older games.
## Post #363
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2017-10-06T13:10:17+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Could somebody explain to me how exactly does this new option option works(the one where you can choose DDS or PNG), it can import meshes with textures already applied on it right? If so how can i do that? I already tried to put d3dtx files in the same folder as the .ms script, but it didn't applied textures automatically on mesh, then i tried to put all meshes, skl and d3dtx files in the folder where .ms file is located and it didn't worked out too! 

P:S Also if i understand it all wrong, and i need to apply textures myself, i have one problem with it now, with the very new TTG games came out, there is that new texture files all models have now which looks something like that
sometexturename_microdetail_mask,
sometexturename_microdetail_spec,
sometexturename_anisotropymask,
sometexturename_anisotropytangent
and also some face textures called
sometexturename_headwrinkle_nm,
sometexturename_headwrinklea_mask,
sometexturename_headwrinkleb_mask.
So what i'm asking is, how do i apply them on basic textures? or on model? (but applying on textures will be better for porting purposes though, for which i actually need it)
And i really need to apply them, cuz textures looks different from ingame if you don't apply these ones on them!
PP:S Just if you curious, i am extracting Batman: The Enemy Within meshes (currently it's Harley, but i'm also planning to export all other Pact members(including goons) some items, and The Pact subway lair)
## Post #364
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-10-08T22:50:14+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum
>
> Could somebody explain to me how exactly does this new option option works(the one where you can choose DDS or PNG), it can import meshes with textures already applied on it right? If so how can i do that?The older games like TWD season 1, Poker Night 2 etc come with pre-applied textures. I think the DDS or PNG thing is to search the folder specifically for that format, otherwise it doesnt really matter? I can't be sure about that.

For the later games, I tend to just drag and drop the textures onto specific parts of the model and hope for the best lol. The most part it's straight forward naming though, stuff like mask, bump, spec etc, you could open the material editor (hotkey M in 3ds max) and goto maps, I tend to leave those myself though, I probably shouldnt. I think for things like head wrinkle etc, those are just alternate skin textures usually like with The Walking Dead you have blood and tears, or a zombie face, and the details are those comic type lines on the characters. If you load the characters in using split, those additional mesh layers go with that, but if you can find a way to overlay the textures in photoshop or something, it'd be much better.

I suck at describing things
## Post #365
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-10-09T22:51:55+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I don’t know if I can post this here but I started a Model Ripping Project for Telltale Games if anyone is interested in helping out. [https://www.vg-resource.com/thread-3062 ... #pid630088](https://www.vg-resource.com/thread-30621-post-630088.html#pid630088)
## Post #366
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-10-10T01:43:35+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum
>
> Could somebody explain to me how exactly does this new option option works(the one where you can choose DDS or PNG), it can import meshes with textures already applied on it right? If so how can i do that? I already tried to put d3dtx files in the same folder as the .ms script, but it didn't applied textures automatically on mesh, then i tried to put all meshes, skl and d3dtx files in the folder where .ms file is located and it didn't worked out too! 

P:S Also if i understand it all wrong, and i need to apply textures myself, i have one problem with it now, with the very new TTG games came out, there is that new texture files all models have now which looks something like that
sometexturename_microdetail_mask,
sometexturename_microdetail_spec,
sometexturename_anisotropymask,
sometexturename_anisotropytangent
and also some face textures called
sometexturename_headwrinkle_nm,
sometexturename_headwrinklea_mask,
sometexturename_headwrinkleb_mask.
So what i'm asking is, how do i apply them on basic textures? or on model? (but applying on textures will be better for porting purposes though, for which i actually need it)
And i really need to apply them, cuz textures looks different from ingame if you don't apply these ones on them!
PP:S Just if you curious, i am extracting Batman: The Enemy Within meshes (currently it's Harley, but i'm also planning to export all other Pact members(including goons) some items, and The Pact subway lair)Sure, I'll explain things a bit.

Basically, the changes made were to match a few of my other scripts a bit more. Let's just say you were importing Max's model from Sam & Max, and the folder it's in is as follows (doesn't need to be the same as the MaxScript):
```
C:\Models\Sam & Max S1\E1\sk22_max.d3dmesh
```

With the new menu options, this is where it'll look for the textures for that:

```
DDS / Textures = C:\Models\Sam & Max S1\E1\Textures\sk22_max.dds
PNG / Relative = C:\Models\Sam & Max S1\E1\sk22_max.png
PNG / Textures = C:\Models\Sam & Max S1\E1\Textures\sk22_max.png
```

The DDS / Textures combination is how it worked before the recent update. But yeah, there isn't a way to directly read D3DTX files, so you'll still need to convert those with either Telltale Explorer, or TTArchExt and one of my QuickBMS scripts. That being said, here's all of the games that don't work with automatically applying textures (I'll probably add some kinda note for 'em in a later update):
```
Batman: The Enemy Within (Season 2)
Marvel's Guardians of the Galaxy
Minecraft: Story Mode
Minecraft: Story Mode Season 2
Tales from the Borderlands
The Walking Dead: Season 2
The Walking Dead: A New Frontier (Season 3)
The Walking Dead: Michonne
The Wolf Among Us
(And basically any other new Telltale game that is released)
```


As for all of the additional texture types, unfortunately I haven't done too much in the way of model renders or shaders so I can't say for sure what would be the proper way to apply them to the model.
## Post #367
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-10-10T06:13:11+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Something is wrong with the Clementine Hat UV from the first Clementine flashback from The Walking Dead Season 2.
## Post #368
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-10-10T06:31:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> Something is wrong with the Clementine Hat UV from the first Clementine flashback from The Walking Dead Season 2.Nope, you're just using the wrong texture. The one for that model is "obj_hatClementineBloody".


This is why I mentioned earlier to try matching up the UV mapping to whatever texture matches it, you'll have a better understanding of 'em if you do.
## Post #369
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-10-10T13:46:48+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Escope12 wrote:Something is wrong with the Clementine Hat UV from the first Clementine flashback from The Walking Dead Season 2. 
Nope, you're just using the wrong texture. The one for that model is "obj_hatClementineBloody".


This is why I mentioned earlier to try matching up the UV mapping to whatever texture matches it, you'll have a better understanding of 'em if you do.I thought I was using the right texture for that.

Edit: I get this error when I try to import Alvin's Model from The Walking Dead Season 2.
## Post #370
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-10-11T01:04:51+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

```
Fixed importing models with vertex colours enabled because I'm a dumb fart who doesn't test everything.
```

[https://mega.nz/#!X9oSlTLC!2-K7JYcGobjr ... -5stmRUyoA](https://mega.nz/#!X9oSlTLC!2-K7JYcGobjrEJ_MRn4kyCCXb5-ZK-Yt9-5stmRUyoA)

Yep. Accidentally broke vertex colour importing. Don'tcha love hotfixes?
## Post #371
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2017-10-12T14:45:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Maximmum wrote:Could somebody explain to me how exactly does this new option option works(the one where you can choose DDS or PNG), it can import meshes with textures already applied on it right? If so how can i do that? I already tried to put d3dtx files in the same folder as the .ms script, but it didn't applied textures automatically on mesh, then i tried to put all meshes, skl and d3dtx files in the folder where .ms file is located and it didn't worked out too! 

P:S Also if i understand it all wrong, and i need to apply textures myself, i have one problem with it now, with the very new TTG games came out, there is that new texture files all models have now which looks something like that
sometexturename_microdetail_mask,
sometexturename_microdetail_spec,
sometexturename_anisotropymask,
sometexturename_anisotropytangent
and also some face textures called
sometexturename_headwrinkle_nm,
sometexturename_headwrinklea_mask,
sometexturename_headwrinkleb_mask.
So what i'm asking is, how do i apply them on basic textures? or on model? (but applying on textures will be better for porting purposes though, for which i actually need it)
And i really need to apply them, cuz textures looks different from ingame if you don't apply these ones on them!
PP:S Just if you curious, i am extracting Batman: The Enemy Within meshes (currently it's Harley, but i'm also planning to export all other Pact members(including goons) some items, and The Pact subway lair)Sure, I'll explain things a bit.

Basically, the changes made were to match a few of my other scripts a bit more. Let's just say you were importing Max's model from Sam & Max, and the folder it's in is as follows (doesn't need to be the same as the MaxScript):Code: Select allC:\Models\Sam & Max S1\E1\sk22_max.d3dmesh
With the new menu options, this is where it'll look for the textures for that:
Code: Select allDDS / Relative = C:\Models\Sam & Max S1\E1\sk22_max.dds
DDS / Textures = C:\Models\Sam & Max S1\E1\Textures\sk22_max.dds
PNG / Relative = C:\Models\Sam & Max S1\E1\sk22_max.png
PNG / Textures = C:\Models\Sam & Max S1\E1\Textures\sk22_max.png
The DDS / Textures combination is how it worked before the recent update. But yeah, there isn't a way to directly read D3DTX files, so you'll still need to convert those with either Telltale Explorer, or TTArchExt and one of my QuickBMS scripts. That being said, here's all of the games that don't work with automatically applying textures (I'll probably add some kinda note for 'em in a later update):Code: Select allBatman: The Telltale Series
Batman: The Enemy Within (Season 2)
Marvel's Guardians of the Galaxy
Minecraft: Story Mode
Minecraft: Story Mode Season 2
Tales from the Borderlands
The Walking Dead: Season 2
The Walking Dead: A New Frontier (Season 3)
The Walking Dead: Michonne
The Wolf Among Us
(And basically any other new Telltale game that is released)

As for all of the additional texture types, unfortunately I haven't done too much in the way of model renders or shaders so I can't say for sure what would be the proper way to apply them to the model.
Alright i think i understand it now, thank you for that "massive" explanation
## Post #372
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-10-20T13:04:35+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Has anybody had an issue getting specific maps into XNALara? I've had trouble with the Walking Dead season 1 map "adv_cancergrouphideoutroof". I've only tried porting it once but I figured before doing it again I'd ask. So the issue I'm having is something like "Destination array is not long enough to copy all the items in the collection. Check array index and length."

Edit:
I've narrowed down the problem to adv_cancergrouphideoutroof_meshesa.d3dmesh. First XNALara will say that it doesnt like meshesa_4 or 23, or 29, and removing those will just say "Unknown ascii". Could somebody else see if they can get this specific mesh in XNA? It's really annoying.

Edit #2:
Saving as Obj instead comes up with a warning while saving that 2 texture coords are out of range. Opening in XNALara will say.
[https://puu.sh/y3SiS/ebe080e2c1.png](https://puu.sh/y3SiS/ebe080e2c1.png)

Edit #3:
I've got it! it was one of the white boards around the bottom of the hospital, removing that fixes all my problems.
[https://puu.sh/y3T3P/0aabd53cd9.png](https://puu.sh/y3T3P/0aabd53cd9.png)
## Post #373
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-10-28T23:00:58+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Same issue on the 400 Days Truckstop Interior (chapter 5), Mesh E.

Lots of issues with that one. No errors, just issues.. well apart from that one error.
## Post #374
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-10-29T09:13:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> Same issue on the 400 Days Truckstop Interior (chapter 5), Mesh E.

Lots of issues with that one. No errors, just issues.. well apart from that one error.
There are most likely textures not auto assigned so xps errors on it or doesn't load it. Rather than deleting those meshes just assign the textures manually.
## Post #375
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-11-07T04:14:02+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from o0Crofty0o
>
> There are most likely textures not auto assigned so xps errors on it or doesn't load it. Rather than deleting those meshes just assign the textures manually.I never tried that, but they did already have textures applied to them. I can usually port models without textures though. I think the map itself was a bit messed up and I'm a noob, when I tried to merge all the parts all the vertices merged weirdly, like a giant criss-cross all across the map. At least that 400 Days map.
## Post #376
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-11-12T00:35:58+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Does anybody know if there's a way to know which textures a map uses other than guessing?
## Post #377
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-11-19T20:49:33+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Can someone help me please? I used the quickbms script to convert the d3dtx to dds and this is what it looks like  
there is a thick black line running through it and i dont know why or what i am doing wrong. This is from batman enemy within

Problem was fixed it seems the problem was that i was overwriting the files from episode 2 to episode 1
## Post #378
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-12-04T19:35:31+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

This may sound like a weird question but Telltale is releasing The Walking Dead Collection Remastered tomorrow and the characters have high poly models and Hi-res textures. Will it be possible to extract those?
## Post #379
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-12-04T19:57:24+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> This may sound like a weird question but Telltale is releasing The Walking Dead Collection Remastered tomorrow and the characters have high poly models and Hi-res textures. Will it be possible to extract those?If it's not on PC, then it's not likely right now, partly because it's gonna be difficult to extract from the PS4 version (and XB1's currently impossible), and I'd most likely need to rewrite everything to support 'em since the model files in the console versions of Telltale's games are set up differently than the PC version's (I still haven't fixed the rigging on the 360's BttF re-release yet!).
## Post #380
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-12-04T21:27:37+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Escope12 wrote:This may sound like a weird question but Telltale is releasing The Walking Dead Collection Remastered tomorrow and the characters have high poly models and Hi-res textures. Will it be possible to extract those?If it's not on PC, then it's not likely right now, partly because it's gonna be difficult to extract from the PS4 version (and XB1's currently impossible), and I'd most likely need to rewrite everything to support 'em since the model files in the console versions of Telltale's games are set up differently than the PC version's (I still haven't fixed the rigging on the 360's BttF re-release yet!).
It’s only on PS4 and Xbox One. I was hoping it would get a PC Version.
## Post #381
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-12-04T23:55:22+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I was able to rip all the characters from The Walking Dead: Season 2. I'm gonna rip from The Walking Dead: Michonne & The Walking Dead: Season 1.
## Post #382
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-12-16T20:23:49+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I was trying to rip Bigby's model from The Wolf Among Us & I split the UV Layers to apply the line textures to the objects that said Layer 3 and this happened. I don't know if I'm using the wrong textures or if it's a bug.
## Post #383
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2017-12-23T21:14:17+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> I was trying to rip Bigby's model from The Wolf Among Us & I split the UV Layers to apply the line textures to the objects that said Layer 3 and this happened. I don't know if I'm using the wrong textures or if it's a bug.

I just edited the UVW Layer (or w/e it's called on 3ds) and stretched it a little.
## Post #384
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2017-12-23T21:22:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Uh... Did I break the scaling for secondary UV mapping layers? I'll go see what I can do to fix that up, since the additional layers should've lined up fine (and did in a previous update).
## Post #385
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-12-25T00:17:17+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Uh... Did I break the scaling for secondary UV mapping layers? I'll go see what I can do to fix that up, since the additional layers should've lined up fine (and did in a previous update).
I think so. I only tested it out with Bigby's model from The Wolf Among Us.
## Post #386
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2018-01-04T16:57:41+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> RandomTBush wrote:Uh... Did I break the scaling for secondary UV mapping layers? I'll go see what I can do to fix that up, since the additional layers should've lined up fine (and did in a previous update).
I think so. I only tested it out with Bigby's model from The Wolf Among Us.The issue is with (I think) that specific Bigby model, and the wolf he turns into at the end of the story. Though I cant be sure if the wolf's detail lines are mirrored rather than just out of place.
## Post #387
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-01-04T17:44:00+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> Escope12 wrote:RandomTBush wrote:Uh... Did I break the scaling for secondary UV mapping layers? I'll go see what I can do to fix that up, since the additional layers should've lined up fine (and did in a previous update).
I think so. I only tested it out with Bigby's model from The Wolf Among Us.The issue is with (I think) that specific Bigby model, and the wolf he turns into at the end of the story. Though I cant be sure if the wolf's detail lines are mirrored rather than just out of place.
I think it’s out of place. Hopefully RTB can fix it.
## Post #388
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2018-01-04T18:56:08+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Okay, yeah, I definitely found the problem.



Turns out I had the wrong order for the UV mapping scale values (apparently it's 1-4-2-3 instead of 1-2-3-4?). I'm gonna check a bunch more things just to make sure (basically I gotta batch-process everything to see if I can find any models that don't just have "1" for its 2nd and 4th layers), then I'll upload the fix.

(EDIT: Welp, found a few models that cause the script to error, so I gotta work on fixing that too.)
## Post #389
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-01-04T19:29:42+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Okay, yeah, I definitely found the problem.



Turns out I had the wrong order for the UV mapping scale values (apparently it's 1-4-2-3 instead of 1-2-3-4?). I'm gonna check a bunch more things just to make sure (basically I gotta batch-process everything to see if I can find any models that don't just have "1" for its 2nd and 4th layers), then I'll upload the fix.

(EDIT: Welp, found a few models that cause the script to error, so I gotta work on fixing that too.)
Does this happen with the models from The Walking Dead Season 2 when you split the UV Layers as well?
## Post #390
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2018-01-04T22:09:34+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> Does this happen with the models from The Walking Dead Season 2 when you split the UV Layers as well?Maybe, it is identical to The Wolf Among Us's, after all.

Anyway, script's fixed... I think.

```
Fixed models with vertex colours causing the script to pause for certain importers due to accidentally leaving in a break command.
```

[https://mega.nz/#!ngBHFbAZ!TiapExUQ-yCE ... L5NUqn3Wtc](https://mega.nz/#!ngBHFbAZ!TiapExUQ-yCEV4XAXUK72vq4h966PlmWXL5NUqn3Wtc)
## Post #391
- Username: takiyaGenji
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 07, 2018 7:58 am
- Post datetime: 2018-01-21T11:46:30+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

can help should use which format dds minecraft story mode season 2 


thanks
## Post #392
- Username: Kaizo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 12, 2018 4:25 am
- Post datetime: 2018-02-11T20:29:50+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Wait. You got the entire skin? when i put skM1_jesse201_clothesA.d3dtx through the program I only got a 64x64 image with 1 line [https://imgur.com/a/LSVuX](https://imgur.com/a/LSVuX)
## Post #393
- Username: Kaizo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 12, 2018 4:25 am
- Post datetime: 2018-02-13T13:58:20+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Can anyone assist on the single line issue? I saw a post a few pages back that the creator had updated the script. So I tried that one but I get the same result.
## Post #394
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2018-03-03T10:58:47+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Oh hey, turns out that the PlayStation 4 version of Back to the Future: The Game (30th Anniversary Edition) actually has models that can be properly read (compared to the 360 version's which were practically impossible to figure out the rigging for), and are using almost the same format as Minecraft: Story Mode, so I was able to implement support for it pretty quickly (I just needed to add a one-byte signed normals format)!... but now I gotta figure out how to get its textures exported/converted correctly since (they're using the basic PS4 swizzle). Hrm.
(EDIT: Looks like a combination of the MC:SM script which I'll be uploading a fix for soon, and [chrrox's DDS-to-GTF script](http://forum.xentax.com/viewtopic.php?p=137757#p137757) seems to work for that!)


Until then, the PC version's textures seem to work! But yeah, I'll be uploading the updated script soon! (Man, I really wish that I can figure out the other games someday...)

> Reply from Kaizo
>
> Wait. You got the entire skin? when i put skM1_jesse201_clothesA.d3dtx through the program I only got a 64x64 image with 1 line https://imgur.com/a/LSVuX
Late reply, but send me the D3DTX files so I can take a look and compare 'em with what I've got.

(EDIT: Wait! I have a feeling I might know why that's broken. I'll be uploading an updated script later for you to try out.)
## Post #395
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-03-03T16:42:06+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Oh hey, turns out that the PlayStation 4 version of Back to the Future: The Game (30th Anniversary Edition) actually has models that can be properly read (compared to the 360 version's which were practically impossible to figure out the rigging for), and are using almost the same format as Minecraft: Story Mode, so I was able to implement support for it pretty quickly (I just needed to add a one-byte signed normals format)!... but now I gotta figure out how to get its textures exported/converted correctly since (they're using the basic PS4 swizzle). Hrm.


Until then, the PC version's textures seem to work! But yeah, I'll be uploading the updated script soon! (Man, I really wish that I can figure out the other games someday...)
Kaizo wrote:Wait. You got the entire skin? when i put skM1_jesse201_clothesA.d3dtx through the program I only got a 64x64 image with 1 line https://imgur.com/a/LSVuX
Late reply, but send me the D3DTX files so I can take a look and compare 'em with what I've got.I don’t know if I should ask but how did you get the files from the PlayStation 4 Version?
## Post #396
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2018-03-03T21:32:34+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> I don’t know if I should ask but how did you get the files from the PlayStation 4 Version?Same way other games are extracted -- exploits! This is something you'll need to research on your own.

Anyway, update time!

```
Fixed D3DTX-to-DDS QuickBMS scripts so that file size is applied properly, whoops!
```

For the PS4 version of Back to the Future, you'll want to use the "_BttFPS4" script with the D3DTX files to get (broken) DDS files, and then use [chrrox's QuickBMS script](http://www.gildor.org/smf/index.php?topic=5999.msg26641#msg26641) to convert those to GNF, and then finally Noesis to convert 'em to PNG.

[Download MaxScript](https://mega.nz/#!i9g1kYgA!EhmHaSd0VYMOaZ8SAPKXUSgunnmWJXl0Jn4P4Z19iCw)
[Download D3DTX to DDS QuickBMS Script](https://mega.nz/#!roYDQR4b!ni8LXMrb3JyInqHaWFLVHMqeL6aDdBHAkGUqAV9YVB4)

@Kaizo: Try the updated QuickBMS script above and let me know if it works! Turns out that I had completely forgotten to fill in part of the DDS file where the filesize was supposed to be kept, which might have been causing that glitch.
## Post #397
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-03-03T21:41:14+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I might try and get the game files from The Walking Dead: The Telltale Series Collection from the PS4 Version because it has visually enhanced versions of The Walking Dead: Season 1, 400 Days, Season 2, Michonne and The Walking Dead: A New Frontier.
## Post #398
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2018-03-03T22:15:31+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> I might try and get the game files from The Walking Dead: The Telltale Series Collection from the PS4 Version because it has visually enhanced versions of The Walking Dead: Season 1, 400 Days, Season 2, Michonne and The Walking Dead: A New Frontier.With any luck, those might work right off the bat with the Batman/GotG importer, considering I'd only needed to add in one thing for the BttF stuff.
## Post #399
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-03-03T22:20:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Escope12 wrote:I might try and get the game files from The Walking Dead: The Telltale Series Collection from the PS4 Version because it has visually enhanced versions of The Walking Dead: Season 1, 400 Days, Season 2, Michonne and The Walking Dead: A New Frontier.With any luck, those might work right off the bat with the Batman/GotG importer, considering I'd only needed to add in one thing for the BttF stuff.

Anyway, added a fixed version of the BttF script to the previous post, since the height and width on the original one were being read in the wrong order!
I agree since The Walking Dead: The Telltale Series Collection is only on PS4 & Xbox One and I doubt it’s getting ported to the PC.
## Post #400
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2018-03-04T17:06:48+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Just tested the PlayStation 4 versions of both The Wolf Among Us and Batman: The Telltale Series. The Wolf Among Us works just fine, but Batman doesn't. Hrm. I know it's not that necessary to fix it since the PC version works already, but it's still something I feel needs to be looked into for compatibility's sake.

(EDIT: Tales from the Borderlands's PS4 version works, too!)
## Post #401
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-03-04T20:09:29+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Just tested the PlayStation 4 versions of both The Wolf Among Us and Batman: The Telltale Series. The Wolf Among Us works just fine, but Batman doesn't. Hrm. I know it's not that necessary to fix it since the PC version works already, but it's still something I feel needs to be looked into for compatibility's sake.Did you test this on PlayStation 4 versions of Telltale’s The Walking Dead?
## Post #402
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2018-03-07T20:41:29+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hello, I used your BMs script to convert TWD A New frontier's D3DTX to DDS, but how to convert DDS back to D3DTX format for please?
## Post #403
- Username: Kaizo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 12, 2018 4:25 am
- Post datetime: 2018-03-13T22:09:00+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

@RandomTBush
First of all thank you very much for updating the script so fast! I actually couldn't remember the website for a few weeks since I reset my machine "Who takes the time to uninstall everything you don't need when factory reset does it all for you!" - Kaizo
Hah, Anyways I did manage to get it to extract textures correctly but I wanted to see if you could assist me with exporting, editing and re-importing textures to Minecraft: Story Mode Season 2.
I have wanted to do this for awhile now but there are no tutorials on Youtube for it. If you can please contact me at
Discord = Kaizo#9322
or in messages.
Again thank you so much for the help updating the script!
-Kaizo
## Post #404
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2018-03-19T05:43:06+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Just tested a few more PS4 ports now.

Marvel's Guardians of the Galaxy (Episode 1) = Errors. Guess that means I should spend some more time refining the importers for that and Batman since it's tripping over the hacky workarounds I set up...
Minecraft: Story Mode = Works!
The Walking Dead: Season 1 = Also works! But you need to use the Season 2 or The Wolf Among Us importer for the models, and for the textures you'll need to use the respective QuickBMS script for the D3DTX-to-DDS first, [chrrox's DDS-to-GNF](http://www.gildor.org/smf/index.php?topic=5999.msg26641#msg26641) script after and finally Noesis to convert the GNFs to PNG. Long process, but it's worth it as a number of textures (namely normal maps and textures with transparency) are higher-resolution than in the PC version.

> Reply from martanius
>
> Hello, I used your BMs script to convert TWD A New frontier's D3DTX to DDS, but how to convert DDS back to D3DTX format for please?
> Reply from Kaizo
>
> @RandomTBush
First of all thank you very much for updating the script so fast! I actually couldn't remember the website for a few weeks since I reset my machine "Who takes the time to uninstall everything you don't need when factory reset does it all for you!" - Kaizo
Hah, Anyways I did manage to get it to extract textures correctly but I wanted to see if you could assist me with exporting, editing and re-importing textures to Minecraft: Story Mode Season 2.
I have wanted to do this for awhile now but there are no tutorials on Youtube for it. If you can please contact me at
Discord = Kaizo#9322
or in messages.
Again thank you so much for the help updating the script!
-KaizoHm, haven't really thought about that kinda thing yet. I suppose it should be possible, but I'll definitely need some time to write up something to reverse the process, converting DDS back into D3DTX. I'll let you know if I happen to make any progress on that sometime later.
## Post #405
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-19T14:10:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> .... for the textures you'll need to use the respective QuickBMS script for the D3DTX-to-DDS first, chrrox's DDS-to-GNF script after and finally Noesis to convert the GNFs to PNG. Long process, but it's worth it ....
i could probably help you refine this process to just opening the d3dtx with Noesis and reading the needed info then
building the gnf header on the fly and finally display it all in one step, but i need to see some of those samples.
## Post #406
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2018-03-19T21:29:34+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from AceWell
>
> RandomTBush wrote:.... for the textures you'll need to use the respective QuickBMS script for the D3DTX-to-DDS first, chrrox's DDS-to-GNF script after and finally Noesis to convert the GNFs to PNG. Long process, but it's worth it ....
i could probably help you refine this process to just opening the d3dtx with Noesis and reading the needed info then
building the gnf header on the fly and finally display it all in one step, but i need to see some of those samples.I've got it covered, don't worry. I'm just gonna re-purpose the Crash N-Sane Trilogy texture script I wrote for those.
## Post #407
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-19T22:50:24+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

okay, i'm not worried, i'm still going to do it for fun though, so if anyone 
has some PS4 "Back to the Future" *.d3dtx samples please upload them.  

edit
okay i got samples, i will post the Noesis script in a new thread when done.
## Post #408
- Username: Kaizo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 12, 2018 4:25 am
- Post datetime: 2018-03-23T17:43:27+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

@RandomTBush I wish it was as simple as it was for MCSM s1, you just use uMod and select textutes.
My confusion is what is what in the dds file (what body part is what body part) and what files to use and how to reimport them
## Post #409
- Username: PixelBoyZ69
- Rank: n00b
- Number of posts: 13
- Joined date: Sat May 13, 2017 2:05 am
- Post datetime: 2018-04-01T11:19:20+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

How to fix the mouth?
## Post #410
- Username: Kaizo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 12, 2018 4:25 am
- Post datetime: 2018-04-07T18:55:10+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Any update @RandomTBush?
## Post #411
- Username: Kaizo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 12, 2018 4:25 am
- Post datetime: 2018-04-20T19:39:37+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

@RandomTBush, Do you by chance have any update? Also, If you can add me on discord. Kaizo#9322
## Post #412
- Username: FlareRC
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 22, 2018 8:00 pm
- Post datetime: 2018-04-22T13:12:46+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hi there. I'm pretty much of a noob. But is it possible to import adv dds to adv models?
## Post #413
- Username: Kaizo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 12, 2018 4:25 am
- Post datetime: 2018-05-19T20:56:53+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Anyone have any update? I have the dds file retextured and ready to be imported, just no idea how.
## Post #414
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2018-07-26T13:14:42+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hey RTB! I have some .d3dtx samples from the Remastered Collection, hopefully you'd check them out. The models are fine as they're the same format as Batman:TEW (Season 2).  

[D3DTX Samples](https://mega.nz/#!Y6YgXS6T!uCd11Mft9eu3-NYRLJOwyYK_VBd-JTMTP6QJgEyFXiA)
## Post #415
- Username: Zombieali2000
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 08, 2014 6:07 am
- Post datetime: 2018-08-09T16:13:08+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Heres some mesh files from the Finale season of the Walking dead on PC.
[https://mega.nz/#!N65G0AoA!e_rMdpSWiMA9 ... kZGNMdc0DU](https://mega.nz/#!N65G0AoA!e_rMdpSWiMA9PH3NLJhv_e_rQXEogpK4xkZGNMdc0DU)

None of the current scripts open these. Textures convert fine though with the Batman season 2 script.
## Post #416
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2018-08-09T16:53:22+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Already got 'em myself, Zombieali2000, but thanks anyway. Hopefully I'll have some time later this month to get those working properly, since they changed the formats up yet again (for what may apparently the last time, if that Unity rumor is true?). Likewise for the texture formats that meganmi posted. Heck, I should look into revising all of my texture scripts in general, since I never implemented mipmap support and such.
## Post #417
- Username: Zombieali2000
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 08, 2014 6:07 am
- Post datetime: 2018-08-09T17:30:04+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Already got 'em myself, Zombieali2000, but thanks anyway. Hopefully I'll have some time later this month to get those working properly, since they changed the formats up yet again (for what may apparently the last time, if that Unity rumor is true?). Likewise for the texture formats that meganmi posted. Heck, I should look into revising all of my texture scripts in general, since I never implemented mipmap support and such.
Ah okay! Good to hear!
Hopefully you get a script update soon! Cant wait to rip these models.
## Post #418
- Username: PixelBoyZ69
- Rank: n00b
- Number of posts: 13
- Joined date: Sat May 13, 2017 2:05 am
- Post datetime: 2018-08-18T18:08:07+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Already got 'em myself, Zombieali2000, but thanks anyway. Hopefully I'll have some time later this month to get those working properly, since they changed the formats up yet again (for what may apparently the last time, if that Unity rumor is true?). Likewise for the texture formats that meganmi posted. Heck, I should look into revising all of my texture scripts in general, since I never implemented mipmap support and such.

Yes, it's been confirmed that they're going to switch their engine to Unity.
## Post #419
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2018-08-19T01:21:58+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I dont suppose you ever figured out the textures for the later games did you? It would make those maps a whole lot easier to port if the textures were already applied
## Post #420
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-08-27T18:20:55+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Already got 'em myself, Zombieali2000, but thanks anyway. Hopefully I'll have some time later this month to get those working properly, since they changed the formats up yet again (for what may apparently the last time, if that Unity rumor is true?). Likewise for the texture formats that meganmi posted. Heck, I should look into revising all of my texture scripts in general, since I never implemented mipmap support and such.
I wonder why they always change the format for their games? Don’t they sue the same engine?
## Post #421
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2018-09-01T11:24:08+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> RandomTBush wrote:Already got 'em myself, Zombieali2000, but thanks anyway. Hopefully I'll have some time later this month to get those working properly, since they changed the formats up yet again (for what may apparently the last time, if that Unity rumor is true?). Likewise for the texture formats that meganmi posted. Heck, I should look into revising all of my texture scripts in general, since I never implemented mipmap support and such.
I wonder why they always change the format for their games? Don’t they sue the same engine?

*New iterations of the same engine.
## Post #422
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-09-01T11:49:09+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from meganmi
>
> Escope12 wrote:RandomTBush wrote:Already got 'em myself, Zombieali2000, but thanks anyway. Hopefully I'll have some time later this month to get those working properly, since they changed the formats up yet again (for what may apparently the last time, if that Unity rumor is true?). Likewise for the texture formats that meganmi posted. Heck, I should look into revising all of my texture scripts in general, since I never implemented mipmap support and such.
I wonder why they always change the format for their games? Don’t they sue the same engine?

*New iterations of the same engine.
I didn’t know that. That’s interesting.
## Post #423
- Username: fobk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 06, 2017 6:03 pm
- Post datetime: 2018-09-10T07:11:22+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Is there a tutorial anywhere on how to use the ttarchext cause I cannot figure this thing out.
## Post #424
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2018-09-12T10:40:30+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from fobk
>
> Is there a tutorial anywhere on how to use the ttarchext cause I cannot figure this thing out.
put ttarchext in the folder where ttarch files are. From command prompt: type ttarchext  then press return
you will see all the available commands
every supported game , has a id number, for example: TWD season 2 is 55
so write: ttarchext  -m (this is the parameter to extract all) 55 (is the id of twd season2) then write the name of the ttarch file for example WD4_pc_WalkingDead401_data.ttarch2 then write where you want them extracted, example c:\twd ( before you have to create the twd directory in c:) then press return.
so: the syntax will be this: ttarchext  -m  55 WD4_pc_WalkingDead401_data.ttarch2 c:\twd

Hope this will help you.
## Post #425
- Username: fobk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 06, 2017 6:03 pm
- Post datetime: 2018-09-12T11:19:12+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from fil1969
>
> fobk wrote:Is there a tutorial anywhere on how to use the ttarchext cause I cannot figure this thing out.
put ttarchext in the folder where ttarch files are. From command prompt: type ttarchext  then press return
you will see all the available commands
every supported game , has a id number, for example: TWD season 2 is 55
so write: ttarchext  -m (this is the parameter to extract all) 55 (is the id of twd season2) then write the name of the ttarch file for example WD4_pc_WalkingDead401_data.ttarch2 then write where you want them extracted, example c:\twd ( before you have to create the twd directory in c:) then press return.
so: the syntax will be this: ttarchext  -m  55 WD4_pc_WalkingDead401_data.ttarch2 c:\twd

Hope this will help you.
I'm actually stuck at the first part, when I try to open ttarchext the command window opens for a second then immediately closes.
## Post #426
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2018-09-12T16:12:18+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from fobk
>
> I'm actually stuck at the first part, when I try to open ttarchext the command window opens for a second then immediately closes.You can either Start > run > cmd and drag and drop ttarchext into it. Or you can create a batch file within the ttarchext folder.

Open notepad and type the following:
@echo off
mkdir "1"
for %%i in (*.ttarch2) DO ttarchext.exe -m 55 "%%i" "TWD"

save as anything, for this one I just named it Batch - TWD2 but you need to end it with .bat

Then you can just click that and it'll do the work for you.

Not sure if thats the right way to do it but it works fine for me.
## Post #427
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2018-09-12T17:40:48+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from fobk
>
> fil1969 wrote:fobk wrote:Is there a tutorial anywhere on how to use the ttarchext cause I cannot figure this thing out.
put ttarchext in the folder where ttarch files are. From command prompt: type ttarchext  then press return
you will see all the available commands
every supported game , has a id number, for example: TWD season 2 is 55
so write: ttarchext  -m (this is the parameter to extract all) 55 (is the id of twd season2) then write the name of the ttarch file for example WD4_pc_WalkingDead401_data.ttarch2 then write where you want them extracted, example c:\twd ( before you have to create the twd directory in c:) then press return.
so: the syntax will be this: ttarchext  -m  55 WD4_pc_WalkingDead401_data.ttarch2 c:\twd

Hope this will help you.
I'm actually stuck at the first part, when I try to open ttarchext the command window opens for a second then immediately closes.

you don't have directly double click on ttarchext, but open it from command prompt
## Post #428
- Username: fobk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 06, 2017 6:03 pm
- Post datetime: 2018-09-12T23:32:15+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> fobk wrote:I'm actually stuck at the first part, when I try to open ttarchext the command window opens for a second then immediately closes.You can either Start > run > cmd and drag and drop ttarchext into it. Or you can create a batch file within the ttarchext folder.

Open notepad and type the following:
@echo off
mkdir "1"
for %%i in (*.ttarch2) DO ttarchext.exe -m 55 "%%i" "TWD"

save as anything, for this one I just named it Batch - TWD2 but you need to end it with .bat

Then you can just click that and it'll do the work for you.

Not sure if thats the right way to do it but it works fine for me.
It worked for me, thank you.
## Post #429
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2018-09-22T00:50:31+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Well, uh... [This has certainly gotten awkward](https://www.usgamer.net/articles/report-telltale-games-shutting-down-the-wolf-among-us-2-and-stranger-things-canceled).

...

I guess I'll pick up work on this again after the second and final episode of TWD releases. If something's gonna get finished, it might as well be my script set.
## Post #430
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2018-09-22T03:38:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Well, uh... This has certainly gotten awkward.

...

I guess I'll pick up work on this again after the second and final episode of TWD releases. If something's gonna get finished, it might as well be my script set.

It sucks that the series is going that way, still looking forward to the update RTB.
## Post #431
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-09-22T18:47:58+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Well, uh... This has certainly gotten awkward.

...

I guess I'll pick up work on this again after the second and final episode of TWD releases. If something's gonna get finished, it might as well be my script set.
I wonder if it’ll include The Walking Dead: Collection?
## Post #432
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2018-09-23T10:38:38+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> RandomTBush wrote:Well, uh... This has certainly gotten awkward.

...

I guess I'll pick up work on this again after the second and final episode of TWD releases. If something's gonna get finished, it might as well be my script set.
I wonder if it’ll include The Walking Dead: Collection?
That already works with the Batman: The Enemy Within script
## Post #433
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-09-23T13:12:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from meganmi
>
> Escope12 wrote:RandomTBush wrote:Well, uh... This has certainly gotten awkward.

...

I guess I'll pick up work on this again after the second and final episode of TWD releases. If something's gonna get finished, it might as well be my script set.
I wonder if it’ll include The Walking Dead: Collection?
That already works with the Batman: The Enemy Within script
Speaking of, I hate to ask this but does anyone have these assets for The Walking Dead: Collection and are they extracted?
## Post #434
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2018-09-24T12:24:54+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Welp, just discovered something I should have realized a long time ago while looking at the models from the TWD final season demo -- there is a version number in the same location in the header I could've used all along! So I went back to check the rest, and here's a list of all the ones I've got currently (all PC unless stated otherwise). This also explains why I was able to group a few of the games together:

```
Bone: Out from Boneville / The Great Cow Race
CSI: 3 Dimensions of Murder / Hard Evidence
Sam & Max: Save the World / Beyond Time and Space
Telltale Texas Hold'em

"ERTM" (a.k.a. "Version 0.5"):
Strong Bad's Cool Game for Attractive People
Wallace & Gromit's Grand Adventures

Version 1:
Back to the Future: The Game
CSI: Deadly Intent / Fatal Conspiracy
Poker Night at the Inventory
Sam & Max: The Devil's Playhouse
Tales of Monkey Island

Version 2:
Jurassic Park: The Game
Law & Order: Legacies

Version 5: The Walking Dead: Season 1

Version 12: Poker Night 2

Version 13: The Wolf Among Us

Version 14:
The Walking Dead: Season 1 [PS4]
The Walking Dead: Season 2

Version 17:
Back to the Future: The Game (30th Anniversary) [360 / PS4]
Game of Thrones
Tales from the Borderlands [PC / 360]

Version 18: Minecraft: Story Mode

Version 25: The Walking Dead: Michonne

Version 33: Batman: The Telltale Series [PS4, earlier PC???]

Version 36: Batman: The Telltale Series

Version 37:
Minecraft: Story Mode [Switch]
The Walking Dead: A New Frontier

Version 42: Guardians of the Galaxy: The Telltale Series

Version 45:
Batman: The Enemy Within
Minecraft: Story Mode – Season Two

Version 46: The Walking Dead Collection [PS4]

Version 55: The Walking Dead: The Final Season
```


Man, I'm gonna need a bigger hard drive if I plan on checking every other version in existence. But this also explains why the other Batman models I was sent earlier weren't compatible -- they were of an earlier version compared to what I had (33 instead of 36). And naturally, all of the games I've been unable to figure out are all "Version 1". Go figure. On the bright side, this means I can actually make the next script update autodetect the formats!
## Post #435
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-09-25T01:41:44+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Guys. Telltale posted an update. [https://twitter.com/telltalegames/statu ... 15905?s=21](https://twitter.com/telltalegames/status/1044370808657915905?s=21)
## Post #436
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2018-09-29T22:48:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Good news! With the assistance of daemon1/id-daemon, I can finally add proper auto-importing for the textures in Telltale's newer games! Turns out that the "confusing" hashing for them (and the bone names) is just CRC-64.

Yep. I'm a dunce for not realizing that. Go figure.

So yeah, I'll have to build a list of all the hashes and their respective filenames from The Wolf Among Us and beyond to be included in the next update. But with that done, there's only five major things planned that are left to implement -- TWD: Final Season support, optimizing the importers so they all import as one polygon group (instead of individual ones, which should speed things up), adding support for those pesky "Version 1" games, general optimization / redundancy trimming, and if it's not too difficult SCENE support. The latter three I'll probably have in a later update.

(EDIT: Fixed phrasing.)
## Post #437
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-09-29T22:54:23+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Good news! With the assistance of daemon1/id-daemon, I can finally add proper auto-importing for the textures in Telltale's newer games! Turns out that the "confusing" hashing for them (and the bone names) is just CRC-64.

Yep. I'm a dunce for not realizing that. Go figure.

So yeah, I'll have to build a list of all the hashes and their respective filenames from The Wolf Among Us and beyond to be included in the next update. But with that done, there's only four major things left to implement -- TWD: Final Season support, optimizing the importers so the models import all on the same mesh, adding support for those pesky "Version 1" games, general optimization, and possibly SCENE support. The latter three I'll probably have in a later update.
Nice. This is great. I might have to update all my model rips.
## Post #438
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2018-09-30T00:17:11+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Good news! With the assistance of daemon1/id-daemon, I can finally add proper auto-importing for the textures in Telltale's newer games! Turns out that the "confusing" hashing for them (and the bone names) is just CRC-64.

Yep. I'm a dunce for not realizing that. Go figure.Holy crap this is excellent news, I can finally port the walking dead season 2 maps without going insane!
## Post #439
- Username: stuffed
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 30, 2018 11:09 am
- Post datetime: 2018-09-30T03:12:29+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hey there, first post here 

Does this work with any version of 3DS Max? Sorry if this is the wrong place to be asking
## Post #440
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-09-30T03:46:40+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from stuffed
>
> Hey there, first post here 

Does this work with any version of 3DS Max? Sorry if this is the wrong place to be asking
It works for 3ds Max 2015 and older versions. Ithink.
## Post #441
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2018-09-30T03:58:04+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from stuffed
>
> Hey there, first post here 

Does this work with any version of 3DS Max? Sorry if this is the wrong place to be askingI've written it using Max 2010, but I've applied some bits of coding to fix issues in newer versions (namely the bug where it applies rigging incorrectly). So yeah, it should theoretically work in any version. I'll be testing everything with Max 2018 later after I've finished the script update just to make sure.
## Post #442
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2018-10-02T12:04:07+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> RandomTBush wrote:Good news! With the assistance of daemon1/id-daemon, I can finally add proper auto-importing for the textures in Telltale's newer games! Turns out that the "confusing" hashing for them (and the bone names) is just CRC-64.

Yep. I'm a dunce for not realizing that. Go figure.Holy crap this is excellent news, I can finally port the walking dead season 2 maps without going insane!
Same, gonna import Batman The Enemy Within levels with this update!
## Post #443
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-10-02T21:41:27+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum
>
> Tydeus wrote:RandomTBush wrote:Good news! With the assistance of daemon1/id-daemon, I can finally add proper auto-importing for the textures in Telltale's newer games! Turns out that the "confusing" hashing for them (and the bone names) is just CRC-64.

Yep. I'm a dunce for not realizing that. Go figure.Holy crap this is excellent news, I can finally port the walking dead season 2 maps without going insane!
Same, gonna import Batman The Enemy Within levels with this update!
I’m gonna extract the character models from The Walking Dead: Collection with this update.
## Post #444
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2018-10-03T21:04:44+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> 
I’m gonna extract the character models from The Walking Dead: Collection with this update.

Oh, man, the higher res textures and higher poly models would be great to have. It's a shame I don't own the collection
## Post #445
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-10-04T13:44:28+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko
>
> Escope12 wrote:
I’m gonna extract the character models from The Walking Dead: Collection with this update.

Oh, man, the higher res textures and higher poly models would be great to have. It's a shame I don't own the collection
Me neither because I don’t have a PS4.
## Post #446
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2018-10-06T10:25:38+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Ah can't wait for that update
## Post #447
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-10-11T22:18:33+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Skybound got the license for Telltale’s The Walking Dead and are going to finish working on the last 2 Episodes of The Walking Dead: The Final Season. [https://twitter.com/skyboundgames/statu ... 34626?s=21](https://twitter.com/skyboundgames/status/1048735364452634626?s=21)
## Post #448
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2018-10-11T22:22:18+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> Skybound got the license for Telltale’s The Walking Dead and are going to finish working on the last 2 Episodes of The Walking Dead: The Final Season. https://twitter.com/skyboundgames/statu ... 34626?s=21Bah, you told me that days ago! I thought there was an update for a second, pfft.
## Post #449
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-10-11T22:26:53+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> Escope12 wrote:Skybound got the license for Telltale’s The Walking Dead and are going to finish working on the last 2 Episodes of The Walking Dead: The Final Season. https://twitter.com/skyboundgames/statu ... 34626?s=21Bah, you told me that days ago! I thought there was an update for a second, pfft.
Just wanted to put it here for everyone else.
## Post #450
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2018-10-12T16:36:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> Tydeus wrote:Escope12 wrote:Skybound got the license for Telltale’s The Walking Dead and are going to finish working on the last 2 Episodes of The Walking Dead: The Final Season. https://twitter.com/skyboundgames/statu ... 34626?s=21Bah, you told me that days ago! I thought there was an update for a second, pfft.Just wanted to put it here for everyone else.heh, as Bigby would say "Relax, it was a joke!"
## Post #451
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2018-10-24T11:10:57+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

So how is it all going?
## Post #452
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2018-10-25T16:08:32+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum
>
> So how is it all going?I think it's going to be a while, he said something about the filenames for all of the textures or something (among other things), so I cant see it being a quick job
## Post #453
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-10-28T01:26:42+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> Maximmum wrote:So how is it all going?  I think it's going to be a while, he said something about the filenames for all of the textures or something (among other things), so I cant see it being a quick job
I hope we get an update on it soon.
## Post #454
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2018-11-19T13:46:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Don't wanna be annoying but i hope everything is going well with the update?
## Post #455
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-11-28T19:24:58+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum
>
> Don't wanna be annoying but i hope everything is going well with the update?
I hope everything goes well with the update as well.
## Post #456
- Username: MachoBrizzin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 02, 2018 12:00 pm
- Post datetime: 2018-12-02T04:38:36+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

None of us mean to be a bother, but how's the update coming along?
## Post #457
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2018-12-16T09:05:27+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Is it still alive?
## Post #458
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2018-12-16T11:24:53+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

It's barely been 3 months lol, I'm sure he'll let us know when it's done! I actually almost forgot about it myself. 

Oh hey, did they release episode 3 of the Final Season? I've been meaning to look that up.
## Post #459
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2018-12-16T16:52:48+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> It's barely been 3 months lol, I'm sure he'll let us know when it's done! I actually almost forgot about it myself. 

Oh hey, did they release episode 3 of the Final Season? I've been meaning to look that up.

Episode 3 is releasing next month, January 15.
## Post #460
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2018-12-16T17:30:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum
>
> Is it still alive?Yeah, I just haven't had time to work on it yet due to other things taking away my spare time recently.
## Post #461
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2018-12-17T15:00:46+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Maximmum wrote:Is it still alive?Yeah, I just haven't had time to work on it yet due to other things taking away my spare time recently.
Ah ok, it's fine then, was just wondering what's going on! And also can't wait for it =)
## Post #462
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-12-17T15:12:29+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> Maximmum wrote:Is it still alive?Yeah, I just haven't had time to work on it yet due to other things taking away my spare time recently.
Take all the time you need.
## Post #463
- Username: kaputjan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 21, 2018 8:31 am
- Post datetime: 2018-12-21T00:35:12+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

In order to bump and make relevant this thread, I post this comment!

Thank you to Random Talking Bush, not so Random   , because I like this talking one   .

Hope to see the next update for the final season!
## Post #464
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2018-12-21T00:48:02+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from kaputjan
>
> In order to bump and make relevant this thread, I post this comment!Haha, I was half expecting "How about now? have you finished yet?"

Looking back through these recent posts, thats basically all thats been said.
## Post #465
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-12-21T20:07:56+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Should the script be called Telltale Games “All-In-One” Model Importer now since Telltale Games has completely shut down?
## Post #466
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2018-12-22T09:15:00+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> Should the script be called Telltale Games “All-In-One” Model Importer now since Telltale Games has completely shut down?Not until I can get [those pesky "Version 1" games](http://forum.xentax.com/viewtopic.php?p=144364#p144364) figured out.
## Post #467
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2018-12-22T09:54:11+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> Should the script be called Telltale Games “All-In-One” Model Importer now since Telltale Games has completely shut down?
Well the games these tool are being used to extract items from were made by Telltale, so even if their studio shut down why shouldn't the tool be named after them?
## Post #468
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2018-12-22T19:43:56+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum
>
> Escope12 wrote:Should the script be called Telltale Games “All-In-One” Model Importer now since Telltale Games has completely shut down?Well the games these tool are being used to extract items from were made by Telltale, so even if their studio shut down why shouldn't the tool be named after them?I was always under the impression that "Almost" referred to the games in the "will not work" list, rather than any naming constraints or because there's more games coming out. Plus I remember some other stuff he wanted adding like the scene importer.

I think there's a chance Skybound might make more games since their gaming studio is only just starting out too, I'd prefer them to go back to the Walking Dead season 1/2 style of things, also make a Doctor Who and Supernatural game
## Post #469
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2018-12-22T22:35:21+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus
>
> Maximmum wrote:Escope12 wrote:Should the script be called Telltale Games “All-In-One” Model Importer now since Telltale Games has completely shut down?Well the games these tool are being used to extract items from were made by Telltale, so even if their studio shut down why shouldn't the tool be named after them?I was always under the impression that "Almost" referred to the games in the "will not work" list, rather than any naming constraints or because there's more games coming out. Plus I remember some other stuff he wanted adding like the scene importer.

I think there's a chance Skybound might make more games since their gaming studio is only just starting out too, I'd prefer them to go back to the Walking Dead season 1/2 style of things, also make a Doctor Who and Supernatural game
I would love to see Skybound Games go back to the Season 1/2 Style of Telltale’s The Walking Dead for future games.
## Post #470
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-01-16T12:42:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Don't wanna be annoying, and i really thank you for doing this RandomTBrush, but i can't wait to export that S4 Lee flashback model! =D
## Post #471
- Username: Smolgreen
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 10, 2018 8:19 am
- Post datetime: 2019-01-16T20:35:18+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum
>
> Don't wanna be annoying, and i really thank you for doing this RandomTBrush, but i can't wait to export that S4 Lee flashback model! =D
Yeah, the final season assets look pretty good! 
looking forward to tools being out
## Post #472
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-01-20T22:37:55+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Smolgreen
>
> Maximmum wrote:Don't wanna be annoying, and i really thank you for doing this RandomTBrush, but i can't wait to export that S4 Lee flashback model! =D
Yeah, the final season assets look pretty good! 
looking forward to tools being outI'm still actually 50/50 myself on this whole look. Lee looks awesome, but given that this is the only season that uses this art style, it means you cant exactly use him with that much stuff. Either they should remake TWD1-3 in the same engine, or remake 3 and 4 in the 1-2 engine. They might! who knows, it's skybound after all.
## Post #473
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-01-22T16:55:05+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Well honestly in my opinion S4 have best Telltale's Art style and graphics ever!
## Post #474
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-01-24T04:26:05+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I thought there was an update about the 3ds Max Script a second ago but I guess not. I'll have to wait longer.
## Post #475
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-01-26T19:32:32+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I didn't noticed this until now but is this normal or is this a rigging error on all Walking Dead Models?
## Post #476
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-02-01T07:25:44+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> I didn't noticed this until now but is this normal or is this a rigging error on all Walking Dead Models?
Oh wow, i never had such problem though
## Post #477
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-02-03T03:30:26+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum
>
> Escope12 wrote:I didn't noticed this until now but is this normal or is this a rigging error on all Walking Dead Models?


Oh wow, i never had such problem though
This happens when you rotate both spine1 & pelvis bone to 180.
## Post #478
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-02-03T18:29:50+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12
>
> Maximmum wrote:Escope12 wrote:I didn't noticed this until now but is this normal or is this a rigging error on all Walking Dead Models?Oh wow, i never had such problem thoughThis happens when you rotate both spine1 & pelvis bone to 180.In what scenario would you rotate those bones 180 degrees though?
## Post #479
- Username: NormalMap
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 01, 2017 5:22 pm
- Post datetime: 2019-02-10T18:42:20+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Guys, is there any way to import .d3dmesh from The Walking Dead: The Final Season now?
## Post #480
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2019-02-11T07:32:42+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from NormalMap
>
> Guys, is there any way to import .d3dmesh from The Walking Dead: The Final Season now?

No.
## Post #481
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-02-11T22:42:45+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from NormalMap
>
> Guys, is there any way to import .d3dmesh from The Walking Dead: The Final Season now?Not yet, would've gotten around to doing so earlier but a couple of recent game releases (including but not limited to Super Smash Bros. Ultimate and Kingdom Hearts III) took away the spare time I've had recently.

But now I should have time to work on that again. Aiming for a script update before the end of the month.
## Post #482
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-02-13T09:58:37+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush
>
> NormalMap wrote:Guys, is there any way to import .d3dmesh from The Walking Dead: The Final Season now?Not yet, would've gotten around to doing so earlier but a couple of recent game releases (including but not limited to Super Smash Bros. Ultimate and Kingdom Hearts III) took away the spare time I've had recently.

But now I should have time to work on that again. Aiming for a script update before the end of the month.
Oh thanks RTB you are doing god's work! Can't wait for it! Also you said that the new release of script will allow to import models with textures already applied to model? If that's true that would be great aswell!
## Post #483
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-02-14T11:53:11+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum
>
> Also you said that the new release of script will allow to import models with textures already applied to model? If that's true that would be great aswell!Yeah. Thanks to daemon1 for pointing me in the right direction, I've generated a list of all of the texture hashes for the games which match the ones in the D3DMesh files, and once I've added in coding to read the material groups for those, everything should work just like the older games do.
## Post #484
- Username: genius326
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 31, 2019 6:41 pm
- Post datetime: 2019-02-16T18:52:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

When will you update it so we can make some Season 4 models?
## Post #485
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-02-16T22:10:21+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from genius326 ↑Sun Feb 17, 2019 2:52 am at Sun Feb 17, 2019 2:52 am
>
> 
When will you update it so we can make some Season 4 models?I think thats what he's currently doing.

I cant wait  I'm going to port all the walking dead season 2 maps first
## Post #486
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-03-03T03:27:07+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Any updates? I'm really anxious to start some projects with TWD:Final Season models, so sorry if this is annoying to see.
## Post #487
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-03-09T14:11:04+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Sun Mar 03, 2019 11:27 am at Sun Mar 03, 2019 11:27 am
>
> 
Any updates? I'm really anxious to start some projects with TWD:Final Season models, so sorry if this is annoying to see.

I'm pretty sure the work on the tool is going well!
## Post #488
- Username: voxeltrance
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 13, 2019 1:05 pm
- Post datetime: 2019-03-15T09:21:13+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

deleted
## Post #489
- Username: weirdsciencex
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 23, 2019 9:17 am
- Post datetime: 2019-03-15T10:35:04+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from voxeltrance ↑Fri Mar 15, 2019 5:21 pm at Fri Mar 15, 2019 5:21 pm
>
> 
I don't want to be *that* person but Is there still no way to read files from TFS? With this tool or another? I'm super excited to work on some stuff with that game.

I know what you mean, I've researched all ways of doing this but I'm at a loss, I can extract the models but from there I can't import them into anything, it would be nice to get a status update, I was hoping to get some rendering done before the final episode but that's not looking likely now
## Post #490
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2019-03-15T14:05:57+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Yes, there is currently no way to extract models from TFS since RTB hasn't updated the tool yet. Best to be patient, the update will come when it's ready.
## Post #491
- Username: voxeltrance
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 13, 2019 1:05 pm
- Post datetime: 2019-03-16T19:29:28+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

deleted
## Post #492
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-03-16T21:59:28+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Yeah, sorry, I kinda bit off more than I can chew due to trying to also add automatic material-importing for the older games at the same time. I'll at least get the TWD: Final Season's support done first (which will have the material support at least) when I've got free time again, and then release another update later for the rest of 'em just so you guys don't have to wait too much much longer for that.
## Post #493
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-03-17T12:50:22+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Welp, apparently 3DS Max doesn't like having a massive "case of" list of texture hash-and-name equivalents in its MaxScripts -- having just one whole game's worth (out of 14) makes it crash upon trying to load the script.

Is there another method of comparing names from a list, or am I just outta luck here? I suppose if I can't implement that directly into my script, I can still supply a list of them separately that you'll need to manually compare to. Still, this is what I get for trying to do too much, I guess.
## Post #494
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-03-20T10:36:38+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Just wanted to thank you for doing all this, i hope if you will be able to fix this error with textures importing automatically you will also make the support of it not only in TWD: The Final Season but for Batman: The Enemy Within aswell In the next release of the script? I just really want to rip some locations from The Enemy Within, but it's hard to manually look through what textures fit to where in each mesh of each level because they are usually not named the same as level meshes named.
## Post #495
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2019-03-20T16:03:12+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Maybe a script that would output all the required textures into a .txt file, might be a good middle-ground.
## Post #496
- Username: stuffed
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 30, 2018 11:09 am
- Post datetime: 2019-03-23T20:31:08+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hey  is it possible to import a d3d mesh with the script without having to choose an skl file? I’m planning to extract objects from Sam and max’s office, but it asks for an skl file for every d3d mesh I import.
## Post #497
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-03-23T21:50:13+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from stuffed ↑Sun Mar 24, 2019 4:31 am at Sun Mar 24, 2019 4:31 am
>
> Hey  is it possible to import a d3d mesh with the script without having to choose an skl file? I’m planning to extract objects from Sam and max’s office, but it asks for an skl file for every d3d mesh I import.Yep, just hit "Cancel" on that window and it'll import without a bone structure.
## Post #498
- Username: stuffed
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 30, 2018 11:09 am
- Post datetime: 2019-03-24T01:12:09+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

D'oh, I should've tested it more thoroughly haha. Thank you!
## Post #499
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-03-26T06:27:21+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

So... The series is over. Clem's story is over.
Many tears were shed tonight.
## Post #500
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-03-26T10:10:13+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Now i can't wait for a tool even more to also have these 2 models of Clem this episode introduced  Esp. flashback one!
## Post #501
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-03-27T03:34:17+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Man, what a good season. Looking forward to getting to grips with these models even though the textures seem to get more complicated to both convert and actually use with each game.
## Post #502
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-03-27T03:45:48+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I’m gonna miss Lee, Kenny, Clementine and other characters in The Walking Dead. I wanted to see a sequel for The Walking Dead: Michonne but I don’t think that’s gonna happen because a lot of people hated that game.
## Post #503
- Username: voxeltrance
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 13, 2019 1:05 pm
- Post datetime: 2019-03-27T20:58:24+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

deleted
## Post #504
- Username: MachoBrizzin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 02, 2018 12:00 pm
- Post datetime: 2019-03-27T21:09:44+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12 ↑Wed Mar 27, 2019 11:45 am at Wed Mar 27, 2019 11:45 am
>
> 
I’m gonna miss Lee, Kenny, Clementine and other characters in The Walking Dead. I wanted to see a sequel for The Walking Dead: Michonne but I don’t think that’s gonna happen because a lot of people hated that game.

The saddest part of this is that those characters will soon just fade into our memories. Years from now, the game's subreddit will probably be dead. I mean, the games are finished. The story is done. Now we all move on. It's just gonna be memories from here on out... That hurts the most.

Man, I hope the update comes soon!
## Post #505
- Username: voxeltrance
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 13, 2019 1:05 pm
- Post datetime: 2019-03-27T21:16:52+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

deleted
## Post #506
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-03-27T21:36:28+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from voxeltrance ↑Thu Mar 28, 2019 5:16 am at Thu Mar 28, 2019 5:16 am
>
> 
MachoBrizzin wrote: ↑Thu Mar 28, 2019 5:09 am
Escope12 wrote: ↑Wed Mar 27, 2019 11:45 am
I’m gonna miss Lee, Kenny, Clementine and other characters in The Walking Dead. I wanted to see a sequel for The Walking Dead: Michonne but I don’t think that’s gonna happen because a lot of people hated that game.


The saddest part of this is that those characters will soon just fade into our memories. Years from now, the game's subreddit will probably be dead. I mean, the games are finished. The story is done. Now we all move on. It's just gonna be memories from here on out... That hurts the most.

Man, I hope the update comes soon!


this is exactly why we need an update as soon as possible *cough cough* so we can make stuff before the entire community is gone *cough, wheeze, cough cough*
I’m sure we’ll get an update soon. Please be patient.
## Post #507
- Username: voxeltrance
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 13, 2019 1:05 pm
- Post datetime: 2019-03-27T21:47:10+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

deleted
## Post #508
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-03-28T19:24:44+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from MachoBrizzin ↑Thu Mar 28, 2019 5:09 am at Thu Mar 28, 2019 5:09 am
>
> 
Escope12 wrote: ↑Wed Mar 27, 2019 11:45 am
I’m gonna miss Lee, Kenny, Clementine and other characters in The Walking Dead. I wanted to see a sequel for The Walking Dead: Michonne but I don’t think that’s gonna happen because a lot of people hated that game.

Years from now, the game's subreddit will probably be dead.I think the saddest part here is you had to go mention reddit *shudder*

Skybound who're responsible for the Walking Dead comics did open up a studio and were the ones who finished the game (Is the last episode out yet btw?), so chances of getting more TWD games is kinda pretty high. Though in the style of Telltale? Who knows. Maybe it'll be those lame FPS games that nobody ever talks about.

Just wondering though, a few posts back RTD mentioned 3DS Max crashing, does that mean he cant do auto port with materials? I wonder if he loads all the mesh parts at the same time, I find some maps refuse to load if you do it that way, you end up having to run a 3ds clean up thing to free the memory quite frequently.
## Post #509
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-03-28T19:30:03+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Fri Mar 29, 2019 3:24 am at Fri Mar 29, 2019 3:24 am
>
> Just wondering though, a few posts back RTD mentioned 3DS Max crashing, does that mean he cant do auto port with materials? I wonder if he loads all the mesh parts at the same time, I find some maps refuse to load if you do it that way, you end up having to run a 3ds clean up thing to free the memory quite frequently.Apparently it doesn't crash in 3DS Max 2018, so I'm guessing something was fixed between 2015 (second latest version I've got installed) and then. But then again I haven't added *all* of them yet, so I could end up re-breaking it.

But since you mentioned it ("loads all the mesh parts at the same time"), I really should optimize the importing function itself at some point in time to import everything as a single mesh instead of separate ones. ...After the Final Season script update, though, I've been procrastinating too much.
## Post #510
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-03-28T20:15:34+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Fri Mar 29, 2019 3:30 am at Fri Mar 29, 2019 3:30 am
>
> 
Tydeus wrote: ↑Fri Mar 29, 2019 3:24 amJust wondering though, a few posts back RTD mentioned 3DS Max crashing, does that mean he cant do auto port with materials? I wonder if he loads all the mesh parts at the same time, I find some maps refuse to load if you do it that way, you end up having to run a 3ds clean up thing to free the memory quite frequently.Apparently it doesn't crash in 3DS Max 2018, so I'm guessing something was fixed between 2015.Heh I just noticed I called you RTD, old Doctor Who habit (Russell T Davies). How about the earlier versions? I never bothered upgrading after 2009 lol.

For some reason I procrastinate playing games, I have an unopened Uncharted 4 to play and a whole backlog of games to buy
## Post #511
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-03-28T20:54:37+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Now I’m wondering if The Walking Dead: Season 2, The Walking Dead: Michonne and The Walking Dead: A New Frontier will ever be ported to the Nintendo Switch in the future?
## Post #512
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-03-28T21:55:56+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Fri Mar 29, 2019 4:15 am at Fri Mar 29, 2019 4:15 am
>
> Heh I just noticed I called you RTD, old Doctor Who habit (Russell T Davies). How about the earlier versions? I never bothered upgrading after 2009 lol.

For some reason I procrastinate playing games, I have an unopened Uncharted 4 to play and a whole backlog of games to buyHah, just another one in the list of how many times my name's been misspelled. It's all good. 

Anyway, I primarily use 3DS Max 2010, so technically my scripts should work with 2009 and anything afterwards (I've even had to apply hacky fixes for some newer versions). That being said, I think I've actually got an idea of how to make this work.
## Post #513
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-03-29T16:24:15+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Would you guys like me to convert any Walking Dead models for MMD? I already converted Season 2 Kenny & Season 2 Clementine for MMD.
## Post #514
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-03-29T18:14:08+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I hope to see some progress soon. As well as the person above, I primarily use MMD/Blender for my models and renders. This season has a lot of interesting characters.
## Post #515
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-03-29T21:59:26+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Sat Mar 30, 2019 2:14 am at Sat Mar 30, 2019 2:14 am
>
> 
I hope to see some progress soon. As well as the person above, I primarily use MMD/Blender for my models and renders. This season has a lot of interesting characters.If you have any requests, DM me about it.
## Post #516
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-03-30T18:29:09+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Fri Mar 29, 2019 5:55 am at Fri Mar 29, 2019 5:55 am
>
> Hah, just another one in the list of how many times my name's been misspelled. It's all good.

Personally I used to read it as RandomTBrush, completely ignorant of the fact all your profile pics are of a bush.
## Post #517
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-03-30T20:37:48+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Sun Mar 31, 2019 2:29 am at Sun Mar 31, 2019 2:29 am
>
> Personally I used to read it as RandomTBrush, completely ignorant of the fact all your profile pics are of a bush.Haha same, I thought.. hang on, random talking brush? that makes no sense! then again neither does bush  lol
## Post #518
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-01T23:17:59+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Gosh, I can't wait to rip these. I still have hope.
## Post #519
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-02T00:36:57+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Tue Apr 02, 2019 7:17 am at Tue Apr 02, 2019 7:17 am
>
> 
Gosh, I can't wait to rip these. I still have hope.

I know right? As someone who leans towards making custom characters and stuff, Season 3's models are surprisingly limited in number. Season 4 will really open up more opportunities for sure. I guess all we can do is keep the thread active and hope haha.
## Post #520
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-02T03:03:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Tue Apr 02, 2019 8:36 am at Tue Apr 02, 2019 8:36 am
>
> 
sugarysyringe wrote: ↑Tue Apr 02, 2019 7:17 am
Gosh, I can't wait to rip these. I still have hope.


I know right? As someone who leans towards making custom characters and stuff, Season 3's models are surprisingly limited in number. Season 4 will really open up more opportunities for sure. I guess all we can do is keep the thread active and hope haha.Technically keeping the thread active only really works if there's multiple people releasing updates or content lol. 

Not sure how Season 4 will be any different for customs though tbh since there's even less characters that appear in the game, there's one or two that appear for like 5 seconds and surely there's some unused ones in the files but compared to season 3, you're not really any better off.

That last episode was kind of a let down too, I was expecting some sort of conclusion to the series and not just the season. Showing us where everybody from the series ended up would've been nice, which means us getting new versions of old characters. Sadly they didnt go that direction and it was contained to its own season. Luckily if we get to have the textures applied to maps and stuff, I can recreate the game how I think it should've been done.
## Post #521
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-02T03:30:45+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Tue Apr 02, 2019 11:03 am at Tue Apr 02, 2019 11:03 am
>
> 
jayko wrote: ↑Tue Apr 02, 2019 8:36 am
sugarysyringe wrote: ↑Tue Apr 02, 2019 7:17 am
Gosh, I can't wait to rip these. I still have hope.


I know right? As someone who leans towards making custom characters and stuff, Season 3's models are surprisingly limited in number. Season 4 will really open up more opportunities for sure. I guess all we can do is keep the thread active and hope haha.
Technically keeping the thread active only really works if there's multiple people releasing updates or content lol. 

Not sure how Season 4 will be any different for customs though tbh since there's even less characters that appear in the game, there's one or two that appear for like 5 seconds and surely there's some unused ones in the files but compared to season 3, you're not really any better off.

That last episode was kind of a let down too, I was expecting some sort of conclusion to the series and not just the season. Showing us where everybody from the series ended up would've been nice, which means us getting new versions of old characters. Sadly they didnt go that direction and it was contained to its own season. Luckily if we get to have the textures applied to maps and stuff, I can recreate the game how I think it should've been done.

The closest we'd get to "new versions" of old characters, would be the TWDG Collection. I remember seeing pictures of a higher poly Christa and Chuck, and I can only assume that's what they were used for. Anyway, as for keeping the thread alive, I can only hope that RTB is making some swell progress.
## Post #522
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-02T03:36:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Tue Apr 02, 2019 11:30 am at Tue Apr 02, 2019 11:30 am
>
> The closest we'd get to "new versions" of old characters, would be the TWDG Collection. I remember seeing pictures of a higher poly Christa and Chuck, and I can only assume that's what they were used for. Anyway, as for keeping the thread alive, I can only hope that RTB is making some swell progress.I wouldn't really call them high poly though myself, they're just the season 2 models with slightly better quality textures. Though I'd prefer that over what we got in season 3.

Also, swell.
## Post #523
- Username: Azumi87
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 14, 2016 8:13 am
- Post datetime: 2019-04-02T21:13:46+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I'm not sure what the policy is here regarding links but i've ripped the txmesh and data files from the final season episodes, spent a stupid amount of time sorting each mesh, texture, and skeleton files into their respective character folders, zipped them up, and uploaded to Mega ready for download for those that want them while we wait for RTB to update the importer, the D3DTX files have already been run through Quick BMS but if you'd prefer the raw versions i can upload those, if links are indeed not allowed then by all means PM me and i'll provide you with them.
## Post #524
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-03T01:02:20+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Azumi87 ↑Wed Apr 03, 2019 5:13 am at Wed Apr 03, 2019 5:13 am
>
> 
I'm not sure what the policy is here regarding links but i've ripped the txmesh and data files from the final season episodes, spent a stupid amount of time sorting each mesh, texture, and skeleton files into their respective character folders, zipped them up, and uploaded to Mega ready for download for those that want them while we wait for RTB to update the importer, the D3DTX files have already been run through Quick BMS but if you'd prefer the raw versions i can upload those, if links are indeed not allowed then by all means PM me and i'll provide you with them.Hmm, I might be interested, I dont actually own the Final Season on PC, I tend to buy the games later on PC after playing them on the PS3/4 so it ends up being kinda expensive lol (depending on how long I leave it). Though I still might end up getting it for the maps anyway.
## Post #525
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-03T01:24:54+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Azumi87 ↑Wed Apr 03, 2019 5:13 am at Wed Apr 03, 2019 5:13 am
>
> 
I'm not sure what the policy is here regarding links but I've ripped the txmesh and data files from the final season episodes, spent a stupid amount of time sorting each mesh, texture, and skeleton files into their respective character folders, zipped them up, and uploaded to Mega ready for download for those that want them while we wait for RTB to update the importer, the D3DTX files have already been run through Quick BMS but if you'd prefer the raw versions I can upload those, if links are indeed not allowed then by all means PM me and I'll provide you with them.

I'm sure everyone on this thread would be 100% interested in this! As long as it's related to the forum, I'm sure that you'd be allowed to post it. (As it also aids us in this project )
## Post #526
- Username: Azumi87
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 14, 2016 8:13 am
- Post datetime: 2019-04-03T02:26:18+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Ok here are the links for the files, if anything doesn't work or is missing then please let me know and i'll try to sort it.

EP1 - [https://mega.nz/#!N0xQjQ6R!H8OzAaPkDxew ... sclKa1HQzA](https://mega.nz/#!N0xQjQ6R!H8OzAaPkDxewzruYOGYyqGUsLbn8PKwXJsclKa1HQzA)
EP2 - [https://mega.nz/#!5wZDEK7S!2LWBvjheM_w3 ... t2VBpv4JFA](https://mega.nz/#!5wZDEK7S!2LWBvjheM_w3CmauZrLHx2qAw0Lsuzq1At2VBpv4JFA)
EP3 - [https://mega.nz/#!E5QRQIjT!bgvl3SqqDFLy ... 0_Kotr9Rg4](https://mega.nz/#!E5QRQIjT!bgvl3SqqDFLyGeH4jvwmhmxBL4rmgkgIq0_Kotr9Rg4)
EP4 - [https://mega.nz/#!hwBT1CSD!Aj8ZAe0AJA7i ... qYJ-pmH_EE](https://mega.nz/#!hwBT1CSD!Aj8ZAe0AJA7iCBqsN3lHZald74GNCfubrqYJ-pmH_EE)

Edit: Forgot the links with the decryption key
## Post #527
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-04-03T02:46:26+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Azumi87 ↑Wed Apr 03, 2019 10:26 am at Wed Apr 03, 2019 10:26 am
>
> 
Ok here are the links for the files, if anything doesn't work or is missing then please let me know and i'll try to sort it.

EP1 - https://mega.nz/#!N0xQjQ6R
EP2 - https://mega.nz/#!5wZDEK7S
EP3 - https://mega.nz/#!E5QRQIjT
EP4 - https://mega.nz/#!hwBT1CSD

Nice.
## Post #528
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-03T03:10:40+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Azumi87 ↑Wed Apr 03, 2019 10:26 am at Wed Apr 03, 2019 10:26 am
>
> 
Ok here are the links for the files, if anything doesn't work or is missing then please let me know and i'll try to sort it.

EP1 - https://mega.nz/#!N0xQjQ6R
EP2 - https://mega.nz/#!5wZDEK7S
EP3 - https://mega.nz/#!E5QRQIjT
EP4 - https://mega.nz/#!hwBT1CSD

Sounds pretty useful - but a decryption key is required to download them haha.
## Post #529
- Username: Azumi87
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 14, 2016 8:13 am
- Post datetime: 2019-04-03T03:21:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Wed Apr 03, 2019 11:10 am at Wed Apr 03, 2019 11:10 am
>
> 

Sounds pretty useful - but a decryption key is required to download them haha.

oops! give me a sec and i'll sort it

Edit: Ok should be good now
## Post #530
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-03T07:52:33+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Gosh, i'm smiling so hard just look at these files.
## Post #531
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-03T17:57:00+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Wonder if all that being more organised will help RTB test stuff easier? Means you don't have to scroll through all those files - it'd at least save time haha.
## Post #532
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-03T19:28:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Thu Apr 04, 2019 1:57 am at Thu Apr 04, 2019 1:57 am
>
> 
Wonder if all that being more organised will help RTB test stuff easier? Means you don't have to scroll through all those files - it'd at least save time haha.

I think with them being more organized, it could easily become less time-consuming at the very least.
## Post #533
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-03T19:45:18+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Thu Apr 04, 2019 3:28 am at Thu Apr 04, 2019 3:28 am
>
> 
jayko wrote: ↑Thu Apr 04, 2019 1:57 am
Wonder if all that being more organised will help RTB test stuff easier? Means you don't have to scroll through all those files - it'd at least save time haha.


I think with them being more organized, it could easily become less time-consuming at the very least.I wouldnt say it was all that time-consuming though, I usually separate them all myself but it only really makes a difference for when you have to place the textures yourself. If the textures are going to be automatic like season 1 etc, then you'd be required to place them all in a folder called "textures" (I think), so all you'd really need to separate are the d3dmesh and the skl. Plus I'd assume RTB owns the games anyway 

I'm looking forward to grabbing the season 4 maps but I'm going to work through from season 2 first, it's going to be fun  (I'm weird)
## Post #534
- Username: genius326
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 31, 2019 6:41 pm
- Post datetime: 2019-04-03T20:53:45+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Can someone tell me exactly what thosr files are? I wanna keep my modder friend updated and I wanna tell him exactly what it is. Help me out here?
## Post #535
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-03T21:15:17+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from genius326 ↑Thu Apr 04, 2019 4:53 am at Thu Apr 04, 2019 4:53 am
>
> 
Can someone tell me exactly what thosr files are? I wanna keep my modder friend updated and I wanna tell him exactly what it is. Help me out here?It's the character mesh, rig and textures for season 4. Some props included too.
## Post #536
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-03T22:16:40+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

My god, those zips are so useful. I've always found that my folders are super unorganized so having everything converted and sorted at once saves me making a mess of yet another game. Great job, Azumi87!
## Post #537
- Username: Azumi87
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 14, 2016 8:13 am
- Post datetime: 2019-04-04T01:39:47+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Thu Apr 04, 2019 6:16 am at Thu Apr 04, 2019 6:16 am
>
> 
My god, those zips are so useful. I've always found that my folders are super unorganized so having everything converted and sorted at once saves me making a mess of yet another game. Great job, Azumi87!

Thanks jayko, you're welcome
## Post #538
- Username: The Polish Army
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 01, 2019 12:03 am
- Post datetime: 2019-04-04T20:41:36+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

It's for The Walking Dead The Final Season??
## Post #539
- Username: Azumi87
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 14, 2016 8:13 am
- Post datetime: 2019-04-04T21:41:56+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from The Polish Army ↑Fri Apr 05, 2019 4:41 am at Fri Apr 05, 2019 4:41 am
>
> 
It's for The Walking Dead The Final Season??

Yes
## Post #540
- Username: quinlinkin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 28, 2019 3:41 pm
- Post datetime: 2019-04-05T04:27:22+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

please excuse my general lack of know-how about all of this, but with the impending update to the model importer, will we then be able to use these season 4 files with xnalara? or are these files not compatible with that specific program regardless of the update?
## Post #541
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-05T04:33:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from quinlinkin ↑Fri Apr 05, 2019 12:27 pm at Fri Apr 05, 2019 12:27 pm
>
> 
please excuse my general lack of know-how about all of this, but with the impending update to the model importer, will we then be able to use these season 4 files with xnalara? or are these files not compatible with that specific program regardless of the update?

I'm assuming the tool will export the models to an FBX format, or some other usable format.
I don't know anything about XNA, I used it a long time ago, but I never made models for it . Sorry I can't be of help.
## Post #542
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2019-04-05T09:03:29+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from quinlinkin ↑Fri Apr 05, 2019 12:27 pm at Fri Apr 05, 2019 12:27 pm
>
> 
please excuse my general lack of know-how about all of this, but with the impending update to the model importer, will we then be able to use these season 4 files with xnalara? or are these files not compatible with that specific program regardless of the update?

The update will be so that you can import the models into 3DS Max, to which you can then convert into a format that XNALara can open.
## Post #543
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-05T15:19:18+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from quinlinkin ↑Fri Apr 05, 2019 12:27 pm at Fri Apr 05, 2019 12:27 pm
>
> 
please excuse my general lack of know-how about all of this, but with the impending update to the model importer, will we then be able to use these season 4 files with xnalara? or are these files not compatible with that specific program regardless of the update?Once the files are in 3DS, what I do is goto file > export and save as fbx (though I think you need to download the file extension? I forget), then what I do to get into XNA is download Noesis and convert FBX to mesh.ascii

I'll end up getting everything and sharing it for XNA anyway 
[https://www.deviantart.com/akandrov](https://www.deviantart.com/akandrov)

I uploaded quite a bit there but I gave up temporarily to wait for the update lol
## Post #544
- Username: The Polish Army
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 01, 2019 12:03 am
- Post datetime: 2019-04-05T16:05:13+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

If i download for episode 4, it means that i download for the others too?
## Post #545
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-05T16:30:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from The Polish Army ↑Sat Apr 06, 2019 12:05 am at Sat Apr 06, 2019 12:05 am
>
> 
If i download for episode 4, it means that i download for the others too?

You'd only get what's in the files for episode 4, so you'd get most of the stuff but it'd miss out stuff like the Lee and Clementine flashback models and characters who don't appear in the episode. It doesn't take too long to download all 4 zips and I'd recommend merging all the folders so you have one folder per character with everything in it.
## Post #546
- Username: The Polish Army
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 01, 2019 12:03 am
- Post datetime: 2019-04-05T16:35:52+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Sat Apr 06, 2019 12:30 am at Sat Apr 06, 2019 12:30 am
>
> 
The Polish Army wrote: ↑Sat Apr 06, 2019 12:05 am
If i download for episode 4, it means that i download for the others too?


You'd only get what's in the files for episode 4, so you'd get most of the stuff but it'd miss out stuff like the Lee and Clementine flashback models and characters who don't appear in the episode. It doesn't take too long to download all 4 zips and I'd recommend merging all the folders so you have one folder per character with everything in it.

OK, thanks
## Post #547
- Username: The Polish Army
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 01, 2019 12:03 am
- Post datetime: 2019-04-05T17:53:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Maybe you know how to import/export these files into 3ds max?? Because I would like to use the Louis model in a different game (as a mod).
## Post #548
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-05T18:56:46+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from The Polish Army ↑Sat Apr 06, 2019 1:53 am at Sat Apr 06, 2019 1:53 am
>
> 
Maybe you know how to import/export these files into 3ds max?? Because I would like to use the Louis model in a different game (as a mod).

That's what we're waiting on the importer update to be able to do. Hopefully it's not too far away.
## Post #549
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-06T17:36:40+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I hope it's out sometime soon. I just love how the final season looks, compared to the other seasons.
## Post #550
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-07T20:14:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Sun Apr 07, 2019 1:36 am at Sun Apr 07, 2019 1:36 am
>
> 
I hope it's out sometime soon. I just love how the final season looks, compared to the other seasons.

Me too. I think the best we can do is keep the thread active and let RTB know we're looking forward to the update.
## Post #551
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-04-07T20:28:48+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Good news, I found a method that works for the texture names:



Compiling the respective hash-and-filename pairs into a separate "database" binary file and then building an array through the script does the trick! I honestly don't know why I didn't try doing this earlier.

But yeah, TWD: The Final Season will be the first to use this in the upcoming update (as well as the model optimizations), and I'll go back to the older games and give them the same treatment later (as I mentioned earlier).
## Post #552
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-07T22:02:15+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Mon Apr 08, 2019 4:28 am at Mon Apr 08, 2019 4:28 am
>
> 
Compiling the respective hash-and-filename pairs into a separate "database" binary file and then building an array through the script does the trick! I honestly don't know why I didn't try doing this earlier. I honestly dont know why either! (I had no idea what you said lol, maybe)

This is great news, I was wanting to start on the older games myself but it makes no difference to me
## Post #553
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-08T01:49:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I have no idea what this means, but I'm excited to see some progress!
## Post #554
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-04-08T02:00:11+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I’m looking forward to it.
## Post #555
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-04-08T13:07:04+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Mon Apr 08, 2019 9:49 am at Mon Apr 08, 2019 9:49 am
>
> I have no idea what this means, but I'm excited to see some progress!Basically, instead of having a ton of value checks added directly to the script itself like I have for the bone names currently:

```
	case of (
	default: (BoneName = ("Bone " + bk1 as string))
	(bk1 == 1985717350):(BoneName = "root")
	(bk1 == 1635567852):(BoneName = "spine1")
	(bk1 == -1690135719):(BoneName = "spine2")
	(bk1 == 849913290):(BoneName = "spine3")
	(bk1 == -959180128):(BoneName = "spine4")
	(bk1 == 1866343475):(BoneName = "spine5")
	(bk1 == -1795129466):(BoneName = "spine6")
	(bk1 == -147023454):(BoneName = "neck")
	(et cetera, et cetera)
)

```

...I can just simplify the script to the following instead:

```
for x = 1 to TexHashNum do(
	TexHash2 = readlong db
	TexHash1 = readlong db
	TexString = readstring db
	append TexHash_array (TexHash_struct TexHash1:TexHash1 TexHash2:TexHash2 TexString:TexString)
)
```

...and supply these additional files with the next script version, which are read in a similar manner to the model files themselves:

(Most of those are currently empty until I generate the pairs for the rest of the games, but you get the idea, I think.)
## Post #556
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-08T13:56:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

So this would provide a list of all textures required for each import? (Or auto-apply them if they're already converted and in the correct directory maybe??)

If that's the case then I honestly couldn't be more glad about it - just spent two days trawling through all the textures for one of TWD3's Richmond sets and applying them by hand. It was a pretty rough experience haha
## Post #557
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-08T16:02:11+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Mon Apr 08, 2019 9:07 pm at Mon Apr 08, 2019 9:07 pm
>
> 
sugarysyringe wrote: ↑Mon Apr 08, 2019 9:49 amI have no idea what this means, but I'm excited to see some progress!Basically, instead of having a ton of value checks added directly to the script itself like I have for the bone names currently:
Code: Select allfn BoneRename bk1 = (
	case of (
	default: (BoneName = ("Bone " + bk1 as string))
	(bk1 == 1985717350):(BoneName = "root")
	(bk1 == 1635567852):(BoneName = "spine1")
	(bk1 == -1690135719):(BoneName = "spine2")
	(bk1 == 849913290):(BoneName = "spine3")
	(bk1 == -959180128):(BoneName = "spine4")
	(bk1 == 1866343475):(BoneName = "spine5")
	(bk1 == -1795129466):(BoneName = "spine6")
	(bk1 == -147023454):(BoneName = "neck")
	(et cetera, et cetera)
)

...I can just simplify the script to the following instead:
Code: Select allTexHashNum = readlong db
for x = 1 to TexHashNum do(
	TexHash2 = readlong db
	TexHash1 = readlong db
	TexString = readstring db
	append TexHash_array (TexHash_struct TexHash1:TexHash1 TexHash2:TexHash2 TexString:TexString)
)
...and supply these additional files with the next script version, which are read in a similar manner to the model files themselves:

(Most of those are currently empty until I generate the pairs for the rest of the games, but you get the idea, I think.)

Ahh, I see! Thanks for taking the time to explain
## Post #558
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-04-08T16:30:24+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Mon Apr 08, 2019 9:56 pm at Mon Apr 08, 2019 9:56 pm
>
> So this would provide a list of all textures required for each import? (Or auto-apply them if they're already converted and in the correct directory maybe??)

If that's the case then I honestly couldn't be more glad about it - just spent two days trawling through all the textures for one of TWD3's Richmond sets and applying them by hand. It was a pretty rough experience hahaYeah, it'd auto-apply them. Just tested the process using Bigby's model and a database of all of The Wolf Among Us's D3DTX files (the one listed as "v13Tex.HashDB" in my previous pic) since I had 'em handy at the time, and it assigned all of the textures correctly. But I'll actually need to fix said material importer because I accidentally broke map importing for that game in the process, whoops.
## Post #559
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-08T19:35:11+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

How would this work in regards to the "filename.dds" and the complementary "filename_detail.dds", "filename_nm.dds", "filename_spec.dds" files? Would they also be auto applied? I've usually got by by saving a new image with detail file as a multiply layer on top of the main texture in an image editor (a lot of my processes with the models, especially edited ones are extremely jury rigged ).
## Post #560
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-08T20:41:57+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Tue Apr 09, 2019 3:35 am at Tue Apr 09, 2019 3:35 am
>
> 
How would this work in regards to the "filename.dds" and the complementary "filename_detail.dds", "filename_nm.dds", "filename_spec.dds" files? Would they also be auto applied? I've usually got by by saving a new image with detail file as a multiply layer on top of the main texture in an image editor (a lot of my processes with the models, especially edited ones are extremely jury rigged ).I think it's potentially going to be like season 1 of TWD, you'll have filename.dds applied, perhaps Wolf Among Us will have _details applied, but I tend to do the same as you lol. In fact I'm going through all of the character models of Tales from the Borderlands and merging the details. I would've potentially uploaded the models last year, or the year before if it was more like Season 1, those were already merged with the main texture!
## Post #561
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-04-09T09:38:04+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Tue Apr 09, 2019 4:41 am at Tue Apr 09, 2019 4:41 am
>
> 
jayko wrote: ↑Tue Apr 09, 2019 3:35 am
How would this work in regards to the "filename.dds" and the complementary "filename_detail.dds", "filename_nm.dds", "filename_spec.dds" files? Would they also be auto applied? I've usually got by by saving a new image with detail file as a multiply layer on top of the main texture in an image editor (a lot of my processes with the models, especially edited ones are extremely jury rigged ).
I think it's potentially going to be like season 1 of TWD, you'll have filename.dds applied, perhaps Wolf Among Us will have _details applied, but I tend to do the same as you lol. In fact I'm going through all of the character models of Tales from the Borderlands and merging the details. I would've potentially uploaded the models last year, or the year before if it was more like Season 1, those were already merged with the main texture!
How about _microDetail_mask, _microDetail_spec, _anisotropyMask and _anisotropyTangent textures which are applied to many models(mostly character models) in Batman: The Enemy Within? I really hope you will be able to make them autoimport aswell, since Batman: TEW is where i wanna rip most of the stuff now from, it's just manually looking for textures for each character, levels and objects textures takes too much time so i'm waiting for your script, so i hope in the upcoming update you will also add support to Batman:TEW textures automimport, not only to TWD: S4!
## Post #562
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-10T13:19:02+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum ↑Tue Apr 09, 2019 5:38 pm at Tue Apr 09, 2019 5:38 pm
>
>  i hope in the upcoming update you will also add support to Batman:TEW textures automimport, not only to TWD: S4!

On the last page he said TWD4 would have it in the coming update and then later on he'd backdate it to previous games. Based on how much changes between games it seems like a lot of work to get it all out in one update, and we don't wanna pile too much on top of what he's already working on haha.
## Post #563
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-04-11T18:43:37+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Wed Apr 10, 2019 9:19 pm at Wed Apr 10, 2019 9:19 pm
>
> ...and we don't wanna pile too much on top of what he's already working on haha.

Oops.

(For comparison, there was roughly 24KB worth in the script before.)

> Reply from Maximmum ↑Tue Apr 09, 2019 5:38 pm at Tue Apr 09, 2019 5:38 pm
>
> 
Tydeus wrote: ↑Tue Apr 09, 2019 4:41 am
jayko wrote: ↑Tue Apr 09, 2019 3:35 am
How would this work in regards to the "filename.dds" and the complementary "filename_detail.dds", "filename_nm.dds", "filename_spec.dds" files? Would they also be auto applied? I've usually got by by saving a new image with detail file as a multiply layer on top of the main texture in an image editor (a lot of my processes with the models, especially edited ones are extremely jury rigged ).
I think it's potentially going to be like season 1 of TWD, you'll have filename.dds applied, perhaps Wolf Among Us will have _details applied, but I tend to do the same as you lol. In fact I'm going through all of the character models of Tales from the Borderlands and merging the details. I would've potentially uploaded the models last year, or the year before if it was more like Season 1, those were already merged with the main texture!

How about _microDetail_mask, _microDetail_spec, _anisotropyMask and _anisotropyTangent textures which are applied to many models(mostly character models) in Batman: The Enemy Within? I really hope you will be able to make them autoimport aswell, since Batman: TEW is where i wanna rip most of the stuff now from, it's just manually looking for textures for each character, levels and objects textures takes too much time so i'm waiting for your script, so i hope in the upcoming update you will also add support to Batman:TEW textures automimport, not only to TWD: S4!It's only going to be the diffuse maps for now until I can determine what's used to identify normal maps, etc. At least the filenames are similar enough that you shouldn't have too much trouble applying those manually using the diffuse-only bases.
## Post #564
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-11T19:45:06+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Fri Apr 12, 2019 2:43 am at Fri Apr 12, 2019 2:43 am
>
> 
jayko wrote: ↑Wed Apr 10, 2019 9:19 pm...and we don't wanna pile too much on top of what he's already working on haha.

Oops.

(For comparison, there was roughly 24KB worth in the script before.)

Oh jeez, you've gone positively ham there - three and a half times bigger than it was! I have to say it's surprising how much the texture assigning stuff has increased the size compared to what's required to import fully rigged models. I would have thought the latter was more intensive!
## Post #565
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-11T19:51:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Ahh, I get excited every time I see a notification from this forum.
## Post #566
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-04-11T19:53:03+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Fri Apr 12, 2019 3:45 am at Fri Apr 12, 2019 3:45 am
>
> RandomTBush wrote: ↑Fri Apr 12, 2019 2:43 am
jayko wrote: ↑Wed Apr 10, 2019 9:19 pm...and we don't wanna pile too much on top of what he's already working on haha.

Oops.

(For comparison, there was roughly 24KB worth in the script before.)
Oh jeez, you've gone positively ham there - three and a half times bigger than it was! I have to say it's surprising how much the texture assigning stuff has increased the size compared to what's required to import fully rigged models. I would have thought the latter was more intensive!No kidding. I just spent the last few days re-downloading all of the games and making sure I had absolutely everything extracted. After all of the texture name databases I've built for the script, that's another 8.8MB combined (plus an optional "all-in-one" fallback that's almost 7MB). Definitely making the next update worth it.
## Post #567
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-11T21:23:03+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

"No kidding. I just spent the last few days re-downloading all of the games and making sure I had absolutely everything extracted. After all of the texture name databases I've built for the script, that's another 8.8MB combined (plus an optional "all-in-one" fallback that's almost 7MB). Definitely making the next update worth it."

Do you have any idea as to when the script will be ready? It's just that seeing all the progress is really nice.
## Post #568
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-12T03:23:26+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Just wondering, did you ever figure out what the .scene files were used for? I assumed it was something like the .skl but for maps maybe, I kinda enjoy sticking the maps together where ever it's needed though. (unless it's in like 500,000 pieces like Mass Effect lol)
## Post #569
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-04-14T04:11:18+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Fri Apr 12, 2019 11:23 am at Fri Apr 12, 2019 11:23 am
>
> Just wondering, did you ever figure out what the .scene files were used for? I assumed it was something like the .skl but for maps maybe, I kinda enjoy sticking the maps together where ever it's needed though. (unless it's in like 500,000 pieces like Mass Effect lol)Er... Not just yet, I need to do a lot more research on those first.

> Reply from sugarysyringe ↑Fri Apr 12, 2019 5:23 am at Fri Apr 12, 2019 5:23 am
>
> Do you have any idea as to when the script will be ready? It's just that seeing all the progress is really nice.I'm workin' hard on it right now and making good progress. Since the last time I posted, I've added another couple hundred bone names, resulting in well over 6,000 currently identified (but that's where I'm gonna stop for now before I get too side-tracked again), and also updated the script to use that database instead of the embedded names.

And, despite saying I wasn't going to do so just yet, I've decided to add in auto-texturing for the other games after all. I've currently got it working for the v13 (The Wolf Among Us), v14 (The Walking Dead Season 2), v17 (Game of Thrones / Tales from the Borderlands / Back to the Future [PS4]), v18 (Minecraft: Story Mode) and v25 games (TWD: Michonne). So far, so good, just need to do the same for v36 (Batman: The Telltale Series), v37 (TWD Season 3), v42 (Guardians of the Galaxy), v45 (Batman: The Enemy Within, Minecraft: Story Mode Season 2) and v46 (TWD Collection, Batman: The Telltale Series again*), and then finish up the last things for The Final Season, and then it'll finally be ready.

Needless to say, if I can't get this done in the next week or so, I'm gonna be upset with myself. And yet again, thanks for being patient with me.





* (Oh yeah, and fun fact. Something I learned the other day when working on the texture hash databases -- Batman: The Telltale Series is the only game that they released that had not one, but two revisions to its model format during development, going from v33 to v36 after release of Episode 5 (which is also what had caused my confusion earlier), and then again from v36 to v46 after they inexplicably updated the game again [about half a year later](https://steamdb.info/depot/498241/manifests/), which actually makes it a format newer than its sequel, and thankfully was already supported due to being the same version as TWD Collection.)
## Post #570
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-14T04:14:04+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sun Apr 14, 2019 12:11 pm at Sun Apr 14, 2019 12:11 pm
>
> 
Tydeus wrote: ↑Fri Apr 12, 2019 11:23 amJust wondering, did you ever figure out what the .scene files were used for? I assumed it was something like the .skl but for maps maybe, I kinda enjoy sticking the maps together where ever it's needed though. (unless it's in like 500,000 pieces like Mass Effect lol)Er... Not just yet, I need to do a lot more research on those first.
sugarysyringe wrote: ↑Fri Apr 12, 2019 5:23 amDo you have any idea as to when the script will be ready? It's just that seeing all the progress is really nice.I'm workin' hard on it right now and making good progress. Since the last time I posted, I've added another couple hundred bone names, resulting in well over 6,000 currently identified (but that's where I'm gonna stop for now before I get too side-tracked again), and also updated the script to use that database instead of the embedded names.

And, despite saying I wasn't going to do so just yet, I've decided to add in auto-texturing for the other games after all. I've currently got it working for the v13 (The Wolf Among Us), v14 (The Walking Dead Season 2), v17 (Game of Thrones / Tales from the Borderlands / Back to the Future [PS4]), v18 (Minecraft: Story Mode) and v25 games (TWD: Michonne). So far, so good, just need to do the same for v36 (Batman: The Telltale Series), v37 (TWD Season 3), v42 (Guardians of the Galaxy), v45 (Batman: The Enemy Within, Minecraft: Story Mode Season 2) and v46 (TWD Collection, Batman: The Telltale Series again*), and then finish up the last things for The Final Season, and then it'll finally be ready.

Needless to say, if I can't get this done in the next week or so, I'm gonna be upset with myself. And yet again, thanks for being patient with me.





* (Oh yeah, and fun fact. Something I learned the other day when working on the texture hash databases -- Batman: The Telltale Series is the only game that they released that had not one, but two revisions to its model format during development, going from v33 to v36 after release of Episode 5 (which is also what had caused my confusion earlier), and then again from v36 to v46 after they inexplicably updated the game again about half a year later, which actually makes it a format newer than its sequel, and thankfully was already supported due to being the same version as TWD Collection.)

This is all such exciting news!! I want to stop and take a moment to, once again, appreciate all the work you've done thus far. You're making this possible, my dude. Keep on chugging and you'll be there in no time!
## Post #571
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-14T06:38:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sun Apr 14, 2019 12:11 pm at Sun Apr 14, 2019 12:11 pm
>
> I'm workin' hard on it right now and making good progress. Since the last time I posted, I've added another couple hundred bone names, resulting in well over 6,000 currently identified (but that's where I'm gonna stop for now before I get too side-tracked again), and also updated the script to use that database instead of the embedded names.

-Snip-Holy crap you're awesome. 6,000 bones though? That's mental. Is it that many because all the games use a different.. I dunno (lol) for the bones?

I'm looking forward to grabbing those season 2, michonne and wolf maps! Maybe even Borderlands  this is going to be fun!
## Post #572
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-14T16:00:34+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I didn't realise it was potentially so close! You're a wizard, RTB, I'm super grateful for your work and the effort you put into it. You're doing a great job, man.
## Post #573
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-04-14T17:10:26+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Sun Apr 14, 2019 2:38 pm at Sun Apr 14, 2019 2:38 pm
>
> Holy crap you're awesome. 6,000 bones though? That's mental. Is it that many because all the games use a different.. I dunno (lol) for the bones?Technically, yes. Up until Batman: The Telltale Series, all of the face bones for a character had their name prefixed to them (I assume that's so that their faces don't break if they load someone else's animations). For example:

```
clementine_browCenter_R
clementine_browInner_L
clementine_browInner_R
clementine_browOuter_L
clementine_browOuter_R
clementine_cheekUpper_L
clementine_cheekUpper_R
clementine_cheek_L
clementine_cheek_R
clementine_eyelidLower_L
clementine_eyelidLower_R
clementine_eyelidUpper_L
clementine_eyelidUpper_R
clementine_eyePivot_L
clementine_eyePivot_R
clementine_eyePupil_L
clementine_eyePupil_R
clementine_eye_L
clementine_eye_R
clementine_jaw
clementine_mouthCorner_L
clementine_mouthCorner_R
clementine_mouthLowerInner_L
clementine_mouthLowerInner_R
clementine_mouthLowerOuter_L
clementine_mouthLowerOuter_R
clementine_mouthUpperInner_L
clementine_mouthUpperInner_R
clementine_mouthUpperOuter_L
clementine_mouthUpperOuter_R
clementine_nose_L
clementine_nose_R
clementine_tongue
```


And since almost every character from Jurassic Park to TWD: Michonne has the same naming scheme for their face bones (give or take a few due to restructuring between games), that's where about 70% of those names came from.
## Post #574
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-04-15T01:39:01+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Man, Batman's material setups were pretty annoying to work with, but it looks like I got it figured out. Here's hoping the last few games won't take me as long to write up (I started working on this shortly after my previous post, and just finished it a few minutes ago as of this post).

And also proof I'm not spouting hot air regarding adding texture support. 

(EDIT: TWD Season 3 has the exact same material setups, how convenient!)
## Post #575
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-15T02:28:59+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Mon Apr 15, 2019 9:39 am at Mon Apr 15, 2019 9:39 am
>
> 


Man, Batman's material setups were pretty annoying to work with, but it looks like I got it figured out. Here's hoping the last few games won't take me as long to write up (I started working on this shortly after my previous post, and just finished it a few minutes ago as of this post).

And also proof I'm not spouting hot air regarding adding texture support.

Wow, that's really something! Can't wait to see more, man.
## Post #576
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-15T03:01:52+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Mon Apr 15, 2019 9:39 am at Mon Apr 15, 2019 9:39 am
>
> 
And also proof I'm not spouting hot air regarding adding texture support.I dunno, you could've got that from anywhere 

It's looking great! I cant wait
## Post #577
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-15T11:18:27+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Oh man, this is really exciting. This update is gonna feel like a whole new tool!

Time to start converting every .d3dtx I have in advance, I'd say!
## Post #578
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-04-15T16:59:03+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Mon Apr 15, 2019 7:18 pm at Mon Apr 15, 2019 7:18 pm
>
> 
Time to start converting every .d3dtx I have in advance, I'd say!

Do you even have to? Wouldn't the script auto convert textures when importing them?
## Post #579
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-04-15T16:59:50+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Mon Apr 15, 2019 9:39 am at Mon Apr 15, 2019 9:39 am
>
> 


Man, Batman's material setups were pretty annoying to work with, but it looks like I got it figured out. Here's hoping the last few games won't take me as long to write up (I started working on this shortly after my previous post, and just finished it a few minutes ago as of this post).

And also proof I'm not spouting hot air regarding adding texture support. 

(EDIT: TWD Season 3 has the exact same material setups, how convenient!)

Oh nice one! Is that from Season 1 or Season 2 Batman?
## Post #580
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-04-15T18:58:41+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum ↑Tue Apr 16, 2019 12:59 am at Tue Apr 16, 2019 12:59 am
>
> 
jayko wrote: ↑Mon Apr 15, 2019 7:18 pm
Time to start converting every .d3dtx I have in advance, I'd say!


Do you even have to? Wouldn't the script auto convert textures when importing them?You'll probably want to wait before you do that, I'm gonna be giving my texture-conversion scripts an update sometime afterward to fix up their remaining issues (as well as retain their mipmaps). Either way it still wouldn't import the D3DTX files directly, it'd still need to be converted to DDS/PNG first as it's always been.

> Reply from Maximmum ↑Tue Apr 16, 2019 12:59 am at Tue Apr 16, 2019 12:59 am
>
> Oh nice one! Is that from Season 1 or Season 2 Batman?Season 1 (The Telltale Series), I'll be working on doing the same for The Enemy Within later today.

(EDIT: Looks like the rest of the games up to The Final Season are identical, material-wise! So in that case, looks like there's only one thing left for the script...!)
## Post #581
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-15T21:12:26+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Tue Apr 16, 2019 2:58 am at Tue Apr 16, 2019 2:58 am
>
> 
Looks like the rest of the games up to The Final Season are identical, material-wise! So in that case, looks like there's only one thing left for the script...!Not to jinx you or anything lol, but it's usually when you're about to finish that you hear people saying "My hdd broke" or something along those lines lol
## Post #582
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-04-15T21:32:58+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Tue Apr 16, 2019 5:12 am at Tue Apr 16, 2019 5:12 am
>
> Not to jinx you or anything lol, but it's usually when you're about to finish that you hear people saying "My hdd broke" or something along those lines lolGawd, I hope not, the drive I've been currently using is less than a year old, and I've been making it a habit to make backups of my projects across multiple drives.
## Post #583
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-16T01:15:38+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Seeing the script become closer to being finished is really exciting!
## Post #584
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-04-16T15:53:11+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Tue Apr 16, 2019 9:15 am at Tue Apr 16, 2019 9:15 am
>
> 
Seeing the script become closer to being finished is really exciting!

I'm pretty sure we don't have to wait long now
## Post #585
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-16T16:50:59+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum ↑Tue Apr 16, 2019 11:53 pm at Tue Apr 16, 2019 11:53 pm
>
> 
sugarysyringe wrote: ↑Tue Apr 16, 2019 9:15 am
Seeing the script become closer to being finished is really exciting!


I'm pretty sure we don't have to wait long now

Yeah it's looking like the autotexturing is going smoothly, just need so see what the sitch is on importing twd4 models I believe (which might be a bit more finnicky).
## Post #586
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-04-16T18:47:35+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I might have to update all of the characters I extracted from The Walking Dead: Season 2 when this script comes out.
## Post #587
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-17T16:39:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12 ↑Wed Apr 17, 2019 2:47 am at Wed Apr 17, 2019 2:47 am
>
> 
I might have to update all of the characters I extracted from The Walking Dead: Season 2 when this script comes out.

I don't think I got the chance to even rip S2 characters, I'll definitely have to do that after the S4 characters.
## Post #588
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-04-17T20:46:42+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Thu Apr 18, 2019 12:39 am at Thu Apr 18, 2019 12:39 am
>
> 
Escope12 wrote: ↑Wed Apr 17, 2019 2:47 am
I might have to update all of the characters I extracted from The Walking Dead: Season 2 when this script comes out.


I don't think I got the chance to even rip S2 characters, I'll definitely have to do that after the S4 characters.
You don’t have to worry about that because I already ripped all of the S2 Characters and uploaded them to the Models Resource.
## Post #589
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-04-17T21:10:40+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Now comes the fun part -- debugging (a.k.a. testing absolutely everything). Seeya again tomorrow-ish.

(EDIT: Or maybe a bit later than that, the last few issues might take a bit longer to fix up...)
## Post #590
- Username: Zombieali2000
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 08, 2014 6:07 am
- Post datetime: 2019-04-17T21:21:38+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Yasss! So excited! Thank you!
## Post #591
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-17T21:33:05+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Remember the days when we thought TFS would never be finished?? Well...
Needless to say, I'm literally crying look at this model oh my gosh. I'm so excited.
## Post #592
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-04-18T09:09:40+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Thu Apr 18, 2019 5:33 am at Thu Apr 18, 2019 5:33 am
>
> 
Remember the days when we thought TFS would never be finished?? Well...
Needless to say, I'm literally crying look at this model oh my gosh. I'm so excited.

It's so well detailed compared to other seasons aswell, S4 have the best graphics that Telltale Tool can only have!
And yeah can't wait for the release!!!
## Post #593
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-18T17:50:51+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum ↑Thu Apr 18, 2019 5:09 pm at Thu Apr 18, 2019 5:09 pm
>
> 
sugarysyringe wrote: ↑Thu Apr 18, 2019 5:33 am
Remember the days when we thought TFS would never be finished?? Well...
Needless to say, I'm literally crying look at this model oh my gosh. I'm so excited.


It's so well detailed compared to other seasons aswell, S4 have the best graphics that Telltale Tool can only have!
And yeah can't wait for the release!!!

It really is! S4 is so pretty, graphics wise. The animation got so much better too.
## Post #594
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-18T17:57:24+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Fri Apr 19, 2019 1:50 am at Fri Apr 19, 2019 1:50 am
>
> 
It really is! S4 is so pretty, graphics wise. The animation got so much better too.Kinda weird that they were planning on changing the engine and method of doing things though, thats the main reason they went under (that and not a lot of people where buying their games), they spent quite a bit on upgrading their stuff. 

I would love to have seen where they'd take the Walking Dead series in a new engine, sure Clem's TWD was over but they said they might not be completely done with the franchise, but yep, they're totally done with everything now  at least Skybound can take it over.
## Post #595
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-18T18:10:37+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Fri Apr 19, 2019 1:57 am at Fri Apr 19, 2019 1:57 am
>
> 
sugarysyringe wrote: ↑Fri Apr 19, 2019 1:50 am
It really is! S4 is so pretty, graphics wise. The animation got so much better too.
Kinda weird that they were planning on changing the engine and method of doing things though, thats the main reason they went under (that and not a lot of people where buying their games), they spent quite a bit on upgrading their stuff. 

I would love to have seen where they'd take the Walking Dead series in a new engine, sure Clem's TWD was over but they said they might not be completely done with the franchise, but yep, they're totally done with everything now  at least Skybound can take it over.

True. Did you see the info about the Definitive Series? It's pretty much the TWD collection, but it includes TFS, and upgraded graphics for all previous seasons. New character animations and lip sync, etc.
## Post #596
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-18T23:28:28+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Fri Apr 19, 2019 2:10 am at Fri Apr 19, 2019 2:10 am
>
> 
Tydeus wrote: ↑Fri Apr 19, 2019 1:57 am
sugarysyringe wrote: ↑Fri Apr 19, 2019 1:50 am
It really is! S4 is so pretty, graphics wise. The animation got so much better too.
Kinda weird that they were planning on changing the engine and method of doing things though, thats the main reason they went under (that and not a lot of people where buying their games), they spent quite a bit on upgrading their stuff. 

I would love to have seen where they'd take the Walking Dead series in a new engine, sure Clem's TWD was over but they said they might not be completely done with the franchise, but yep, they're totally done with everything now  at least Skybound can take it over.
True. Did you see the info about the Definitive Series? It's pretty much the TWD collection, but it includes TFS, and upgraded graphics for all previous seasons. New character animations and lip sync, etc.Yeah but I didnt really think much to it, all they're really going to do is give us The Walking Dead Collection with the addition of The Final Season. The only real reason to buy them would be for the gifts, although if they were to say that all of the seasons will be remade in the style of TFS then sure I'd buy that right away, but it's really there to trick us into giving them more money lol
## Post #597
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-18T23:51:48+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Fri Apr 19, 2019 7:28 am at Fri Apr 19, 2019 7:28 am
>
> 
sugarysyringe wrote: ↑Fri Apr 19, 2019 2:10 am
Tydeus wrote: ↑Fri Apr 19, 2019 1:57 am
Kinda weird that they were planning on changing the engine and method of doing things though, thats the main reason they went under (that and not a lot of people where buying their games), they spent quite a bit on upgrading their stuff. 

I would love to have seen where they'd take the Walking Dead series in a new engine, sure Clem's TWD was over but they said they might not be completely done with the franchise, but yep, they're totally done with everything now  at least Skybound can take it over.
True. Did you see the info about the Definitive Series? It's pretty much the TWD collection, but it includes TFS, and upgraded graphics for all previous seasons. New character animations and lip sync, etc.
Yeah but I didnt really think much to it, all they're really going to do is give us The Walking Dead Collection with the addition of The Final Season. The only real reason to buy them would be for the gifts, although if they were to say that all of the seasons will be remade in the style of TFS then sure I'd buy that right away, but it's really there to trick us into giving them more money lol

Oh i'm sadly not buying it until it has a separate digital release, because of how expensive it is. But there are still some things being worked out. It could be a big cash grab but i'm happy to see TWD still getting some love.
## Post #598
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-19T15:57:01+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Fri Apr 19, 2019 7:51 am at Fri Apr 19, 2019 7:51 am
>
> 
Oh i'm sadly not buying it until it has a separate digital release, because of how expensive it is. But there are still some things being worked out. It could be a big cash grab but i'm happy to see TWD still getting some love.If they do release it separately, I already own TWD for the PS3, PS4 and PC, as well as TWD's collection for the PS4. It'd have to be in the same style as Season 4 if I was going to buy it again lol.
## Post #599
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-04-19T16:49:55+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hope the release of the new version will be somewhere tomorrow or so))
## Post #600
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-04-19T17:00:29+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum ↑Sat Apr 20, 2019 12:49 am at Sat Apr 20, 2019 12:49 am
>
> 
Hope the release of the new version will be somewhere tomorrow or so))I kinda hope it's not until sometime next month, I have plans! And Days Gone is out
## Post #601
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-19T17:37:32+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I hope the script is out soon, and I wonder what issues RTB had to figure out. (<< talking about his post edit.)
## Post #602
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-04-19T18:19:10+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Sat Apr 20, 2019 1:00 am at Sat Apr 20, 2019 1:00 am
>
> 
Maximmum wrote: ↑Sat Apr 20, 2019 12:49 am
Hope the release of the new version will be somewhere tomorrow or so))
I kinda hope it's not until sometime next month, I have plans! And Days Gone is out

Oh no what do you mean next month? He said he is testing it already, which means a few days to week at max!
## Post #603
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-04-19T20:53:30+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Sat Apr 20, 2019 1:37 am at Sat Apr 20, 2019 1:37 am
>
> I hope the script is out soon, and I wonder what issues RTB had to figure out. (<< talking about his post edit.)It's because of the rigging... again. :/

The phrase "why fix what isn't broken" doesn't apply to them, they changed it to something new yet again, and I'm still trying to figure out how it's supposed to work. And here I was thinking that the rest of the scripting was going to be easy.
## Post #604
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-19T21:01:26+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sat Apr 20, 2019 4:53 am at Sat Apr 20, 2019 4:53 am
>
> 
sugarysyringe wrote: ↑Sat Apr 20, 2019 1:37 amI hope the script is out soon, and I wonder what issues RTB had to figure out. (<< talking about his post edit.)It's because of the rigging... again. :/

The phrase "why fix what isn't broken" doesn't apply to them, they changed it to something new yet again, and I'm still trying to figure out how it's supposed to work. And here I was thinking that the rest of the scripting was going to be easy.

Gosh, that sounds tedious. I hope you figure it out!
## Post #605
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-20T04:11:33+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sat Apr 20, 2019 4:53 am at Sat Apr 20, 2019 4:53 am
>
> It's because of the rigging... again. :/

The phrase "why fix what isn't broken" doesn't apply to them, they changed it to something new yet again, and I'm still trying to figure out how it's supposed to work. And here I was thinking that the rest of the scripting was going to be easy.

Man, they don't make it easy for anyone. But I suppose with ripping game assets that's the nature of the beast, let alone getting them into a usable state.

At least this is potentially the last time you'll have to fiddle about with their rigging, given Telltale's circumstances.
## Post #606
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-04-20T05:23:11+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Sat Apr 20, 2019 12:11 pm at Sat Apr 20, 2019 12:11 pm
>
> 
RandomTBush wrote: ↑Sat Apr 20, 2019 4:53 amIt's because of the rigging... again. :/

The phrase "why fix what isn't broken" doesn't apply to them, they changed it to something new yet again, and I'm still trying to figure out how it's supposed to work. And here I was thinking that the rest of the scripting was going to be easy.


Man, they don't make it easy for anyone. But I suppose with ripping game assets that's the nature of the beast, let alone getting them into a usable state.

At least this is potentially the last time you'll have to fiddle about with their rigging, given Telltale's circumstances.
Probs not the last time, there will also be a Definitive Edition for which they will probs change format once again. Of course if they won't and they keep the same S4 format for it then that would be great!
## Post #607
- Username: GillMart
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 20, 2019 1:52 pm
- Post datetime: 2019-04-20T06:04:24+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I'm new to this, I'm just wondering if a new version of ttarchext has been updated for The Final Season.
## Post #608
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-04-20T08:28:55+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from GillMart ↑Sat Apr 20, 2019 2:04 pm at Sat Apr 20, 2019 2:04 pm
>
> I'm new to this, I'm just wondering if a new version of ttarchext has been updated for The Final Season.There isn't, but you can extract them by using the "-K" option with this:

> Reply from Maximmum ↑Thu Aug 09, 2018 10:03 pm at Thu Aug 09, 2018 10:03 pm
>
> Here's the key: 96CA999F8DDA9A87D7CDD9986295AAB8D59596E5A4B99BD0C9559F8590CDCD9FC8B39993C6C49DA0A5A4CFCDA39DBBDDACA78B94D4A66F
## Post #609
- Username: GillMart
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 20, 2019 1:52 pm
- Post datetime: 2019-04-20T16:18:39+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Thanks a million!
## Post #610
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-20T17:17:18+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum ↑Sat Apr 20, 2019 1:23 pm at Sat Apr 20, 2019 1:23 pm
>
> 
Probs not the last time, there will also be a Definitive Edition for which they will probs change format once again. Of course if they won't and they keep the same S4 format for it then that would be great!

They already said it's just the Collection models, so there's no change except for maybe textures.
## Post #611
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-04-20T17:23:29+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Sun Apr 21, 2019 1:17 am at Sun Apr 21, 2019 1:17 am
>
> 
Maximmum wrote: ↑Sat Apr 20, 2019 1:23 pm
Probs not the last time, there will also be a Definitive Edition for which they will probs change format once again. Of course if they won't and they keep the same S4 format for it then that would be great!


They already said it's just the Collection models, so there's no change except for maybe textures.

Pretty sure they aren't telling us everything, they probs still gonna improve models in some way, and textures would probs all be S4-ish!
## Post #612
- Username: Smolgreen
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 10, 2018 8:19 am
- Post datetime: 2019-04-20T18:33:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum ↑Sun Apr 21, 2019 1:23 am at Sun Apr 21, 2019 1:23 am
>
> 
jayko wrote: ↑Sun Apr 21, 2019 1:17 am
Maximmum wrote: ↑Sat Apr 20, 2019 1:23 pm
Probs not the last time, there will also be a Definitive Edition for which they will probs change format once again. Of course if they won't and they keep the same S4 format for it then that would be great!


They already said it's just the Collection models, so there's no change except for maybe textures.


Pretty sure they aren't telling us everything, they probs still gonna improve models in some way, and textures would probs all be S4-ish!

I highly doubt it works that way.
doing texturing in a completely different style on almost decade old assets is not really comparable to doing them fresh, with proper team for the task.
## Post #613
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-04-20T18:49:12+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Do you guys think they would upscale the textures from The Collection to make them 4K Ultra HD Textures?
## Post #614
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-20T19:52:45+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I suppose we don't know how the Definitive Edition will actually look in terms of assets until we see it... which in retrospect is kinda scummy for them to charge so much without even showing screenshots of what you're buying.
## Post #615
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-20T20:59:34+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Sun Apr 21, 2019 3:52 am at Sun Apr 21, 2019 3:52 am
>
> 
I suppose we don't know how the Definitive Edition will actually look in terms of assets until we see it... which in retrospect is kinda scummy for them to charge so much without even showing screenshots of what you're buying.

True. At least with the Collection, comparisons were presented.
## Post #616
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-04-20T23:13:34+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I don’t understand why they have to make it so expensive.
## Post #617
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-04-21T01:42:14+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12 ↑Sun Apr 21, 2019 7:13 am at Sun Apr 21, 2019 7:13 am
>
> 
I don’t understand why they have to make it so expensive.

I mean telltale's games never sold well after twd1, and I expect the same is true of twd4 even in spite of the publicity it got out of telltale's closure. Can't blame skybound for trying to make as much money as they possibly can.
## Post #618
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-04-21T03:11:01+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Sun Apr 21, 2019 9:42 am at Sun Apr 21, 2019 9:42 am
>
> 
Escope12 wrote: ↑Sun Apr 21, 2019 7:13 am
I don’t understand why they have to make it so expensive.


I mean telltale's games never sold well after twd1, and I expect the same is true of twd4 even in spite of the publicity it got out of telltale's closure. Can't blame skybound for trying to make as much money as they possibly can.
I feel like people were boycotting Telltale.
## Post #619
- Username: Azumi87
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 14, 2016 8:13 am
- Post datetime: 2019-04-21T11:25:59+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sat Apr 20, 2019 4:28 pm at Sat Apr 20, 2019 4:28 pm
>
> 
GillMart wrote: ↑Sat Apr 20, 2019 2:04 pmI'm new to this, I'm just wondering if a new version of ttarchext has been updated for The Final Season.There isn't, but you can extract them by using the "-K" option with this:
Maximmum wrote: ↑Thu Aug 09, 2018 10:03 pmHere's the key: 96CA999F8DDA9A87D7CDD9986295AAB8D59596E5A4B99BD0C9559F8590CDCD9FC8B39993C6C49DA0A5A4CFCDA39DBBDDACA78B94D4A66F

If you don't manage to get it working Gill i've got them all uploaded and sorted into neat little folders for each episode that i did a couple of weeks ago back on page 36.
## Post #620
- Username: The Polish Army
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 01, 2019 12:03 am
- Post datetime: 2019-04-22T22:19:11+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Work on, dude
## Post #621
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-04-25T08:13:58+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Any follow-ups with the script?
## Post #622
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-04-26T17:20:14+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hello, I just went through the whole topic, and it's pretty good. The guy is doing a great job! Now, I wanted to know when the script will be released, the new update so we can import The final Season d3dmesh to 3d max. Hopefully it won't take longer, and thanks for making the script.
## Post #623
- Username: Tecosaurus
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 25, 2019 5:08 pm
- Post datetime: 2019-04-28T04:38:34+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Even though it's harder than you expected it to be, I know that you're doing the lords work and I know you'll get it done in the foreseeable future! Keep up the good work!
## Post #624
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-04-29T23:35:05+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hello, I wanted to ask if someone has The Walking Dead The Final Season Clementines new character in .fbx or any other 3d model format. If anyone has it, please let me, I really needed it so badly.

Thanks in advance.
## Post #625
- Username: voxeltrance
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 13, 2019 1:05 pm
- Post datetime: 2019-04-30T00:58:00+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

deleted
## Post #626
- Username: Smolgreen
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 10, 2018 8:19 am
- Post datetime: 2019-05-01T22:44:49+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Yeah, hopefully the difficulties ensuing from S4 decypher aren't too cumbersome, looking forward to the script update too
## Post #627
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-05-01T22:46:37+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Smolgreen ↑Thu May 02, 2019 6:44 am at Thu May 02, 2019 6:44 am
>
> 
Yeah, hopefully the difficulties ensuing from S4 decypher aren't too cumbersome, looking forward to the script update too

Same. I love the feel and style of S4. I really hope it's not too much for him to handle atm. It's been a bit since he's hopped in the forum.
## Post #628
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-05-02T00:25:03+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Thu May 02, 2019 6:46 am at Thu May 02, 2019 6:46 am
>
> Same. I love the feel and style of S4. I really hope it's not too much for him to handle atm. It's been a bit since he's hopped in the forum.lol patience young grasshopper, he's been gone like 2 weeks. It just means he's either busy, or playing games
## Post #629
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-05-02T00:28:28+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Thu May 02, 2019 8:25 am at Thu May 02, 2019 8:25 am
>
> 
sugarysyringe wrote: ↑Thu May 02, 2019 6:46 amSame. I love the feel and style of S4. I really hope it's not too much for him to handle atm. It's been a bit since he's hopped in the forum.lol patience young grasshopper, he's been gone like 2 weeks. It just means he's either busy, or playing games

I hope he finishes it by the end of this month, really really need it. I am very thankful for his work and effort and hope he'll be able to finish it by the end of this month.
## Post #630
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-02T03:02:45+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I should have some time next week to try again with figuring out this rigging nonsense.
## Post #631
- Username: Tecosaurus
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 25, 2019 5:08 pm
- Post datetime: 2019-05-02T07:35:05+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Thu May 02, 2019 11:02 am at Thu May 02, 2019 11:02 am
>
> 
I should have some time next week to try again with figuring out this rigging nonsense.

Good luck! You're doing the lords work here! Take all of the time you need!
## Post #632
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-05-03T16:22:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

My bet is that the update will be released somewhere in the middle of the month!
## Post #633
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-05-03T17:00:50+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum ↑Sat May 04, 2019 12:22 am at Sat May 04, 2019 12:22 am
>
> 
My bet is that the update will be released somewhere in the middle of the month!

I hope
## Post #634
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-05-10T06:03:52+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Anything this week?
## Post #635
- Username: Tecosaurus
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 25, 2019 5:08 pm
- Post datetime: 2019-05-10T13:34:55+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Annie2 ↑Fri May 10, 2019 2:03 pm at Fri May 10, 2019 2:03 pm
>
> 
Anything this week?

RTB said he may have had time to work on it this week. All we can do is hope for good progress! But as the famous Chef God once, said "You can have it now, or you can have it right" 

With a little patience, we'll have a top notch script ready for us to use in no time!
## Post #636
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-05-10T14:25:22+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tecosaurus ↑Fri May 10, 2019 9:34 pm at Fri May 10, 2019 9:34 pm
>
> 
Annie2 wrote: ↑Fri May 10, 2019 2:03 pm
Anything this week?


RTB said he may have had time to work on it this week. All we can do is hope for good progress! But as the famous Chef God once, said "You can have it now, or you can have it right" 

With a little patience, we'll have a top notch script ready for us to use in no time!

Gordon?
## Post #637
- Username: Migga
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 11, 2019 12:41 am
- Post datetime: 2019-05-10T16:42:36+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Chef God Omar
## Post #638
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-05-11T02:38:01+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tecosaurus ↑Fri May 10, 2019 9:34 pm at Fri May 10, 2019 9:34 pm
>
> 
Annie2 wrote: ↑Fri May 10, 2019 2:03 pm
Anything this week?


RTB said he may have had time to work on it this week. All we can do is hope for good progress! But as the famous Chef God once, said "You can have it now, or you can have it right" 

With a little patience, we'll have a top notch script ready for us to use in no time!

Nicely said, lol.
## Post #639
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-05-11T02:53:32+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I get the impression that each one of these comments are (not so) cleverly disguised bumps lol.
## Post #640
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-11T11:13:41+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

*shrug*

Either way, I'm back to work on this finally. And thankfully I found a model that's pretty much identical between TWD3 and TWD4 (the hare), so that seems like the best starting point for determining how to fix this issue.

(EDIT: I'm definitely getting somewhere with this now! I've so far got two-bone weights reading correctly.)
## Post #641
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-05-11T13:50:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sat May 11, 2019 7:13 pm at Sat May 11, 2019 7:13 pm
>
> 
*shrug*

Either way, I'm back to work on this finally. And thankfully I found a model that's pretty much identical between TWD3 and TWD4 (the hare), so that seems like the best starting point for determining how to fix this issue.

(EDIT: I'm definitely getting somewhere with this now! I've so far got two-bone weights reading correctly.)

That hare has really been through the ringer in terms of reuse. Started off in Game of Thrones, got reused for TWD3, then again for TWD4. I don't think telltale ever reused a model that much (maybe the raven from TWD got reused in TWAU and GOT??)

Regardless, glad to see you're making progress and I hope the rest remains as straightforward!
## Post #642
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-11T15:08:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

The rigging issue has finally been solved. I'll just copy-paste my comments from the script regarding it:

> "Why fix what isn't broken?" didn't apply to Telltale, it seems.
>
> This was way too frustrating to figure out, so I'll grumble here to explain how this crap works.
>
> First, you have to read all four weight bytes as a "long" value, and then break that apart into 2/10/10/10-bit binary segments.
>
> Those are used for weights 2, 4, 3 and 2 respectively. Why is 2 listed twice? The upper 2 bits add an extra 0.125 each to the second weight's value (0.375 max).
>
> And then the three sets of 10 bits each are the weights in descending order (#4 -> #3 -> #2), and need to be divided by 1023 (0x3FF) and then again for the following:
>
> 2nd = divide by 8 (0.125 max) + 0.125/0.25/0.375 from the upper bits, 3rd = divide by 3 (0.333 max), 4th = divide by 4 (0.25 max).
>
> And finally weight #1 is the remainder, 1.0 minus #2, #3 and #4 combined.
>
> In retrospect, I can see how this works... but what, exactly, was the problem with using float values for this sorta thing again???
>
> Either way, thanks to that recycled hare model for being there, making me not want to rip out my hair.
Or, in scripting terms:

```
Weight2 = (((bit.and (WeightVars) 0x3FF) as float / 1023) / 8) + ((bit.shift WeightVars -30) as float / 8)
Weight3 = ((bit.and (bit.shift WeightVars -10) 0x3FF) as float / 1023) / 3
Weight4 = ((bit.and (bit.shift WeightVars -20) 0x3FF) as float / 1023) / 4
Weight1 = (1 as float - Weight2 - Weight3 - Weight4)
```


Now once I get static meshes working correctly, I can finally release the update! @_@
## Post #643
- Username: Smolgreen
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 10, 2018 8:19 am
- Post datetime: 2019-05-11T17:24:12+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sat May 11, 2019 11:08 pm at Sat May 11, 2019 11:08 pm
>
> 
The rigging issue has finally been solved. I'll just copy-paste my comments from the script regarding it:
"Why fix what isn't broken?" didn't apply to Telltale, it seems.
This was way too frustrating to figure out, so I'll grumble here to explain how this crap works.
First, you have to read all four weight bytes as a "long" value, and then break that apart into 2/10/10/10-bit binary segments.
Those are used for weights 2, 4, 3 and 2 respectively. Why is 2 listed twice? The upper 2 bits add an extra 0.125 each to the second weight's value (0.375 max).
And then the three sets of 10 bits each are the weights in descending order (#4 -> #3 -> #2), and need to be divided by 1023 (0x3FF) and then again for the following:
2nd = divide by 8 (0.125 max) + 0.125/0.25/0.375 from the upper bits, 3rd = divide by 3 (0.333 max), 4th = divide by 4 (0.25 max).
And finally weight #1 is the remainder, 1.0 minus #2, #3 and #4 combined.
In retrospect, I can see how this works... but what, exactly, was the problem with using float values for this sorta thing again???
Either way, thanks to that recycled hare model for being there, making me not want to rip out my hair.
Or, in scripting terms:
Code: Select allWeightVars = readlong f
Weight2 = (((bit.and (WeightVars) 0x3FF) as float / 1023) / 8) + ((bit.shift WeightVars -30) as float / 8)
Weight3 = ((bit.and (bit.shift WeightVars -10) 0x3FF) as float / 1023) / 3
Weight4 = ((bit.and (bit.shift WeightVars -20) 0x3FF) as float / 1023) / 4
Weight1 = (1 as float - Weight2 - Weight3 - Weight4)

Now once I get static meshes working correctly, I can finally release the update! @_@

Nice!
Really looking forward to it
## Post #644
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-05-11T20:20:03+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sat May 11, 2019 11:08 pm at Sat May 11, 2019 11:08 pm
>
> 
The rigging issue has finally been solved. I'll just copy-paste my comments from the script regarding it:
"Why fix what isn't broken?" didn't apply to Telltale, it seems.
This was way too frustrating to figure out, so I'll grumble here to explain how this crap works.
First, you have to read all four weight bytes as a "long" value, and then break that apart into 2/10/10/10-bit binary segments.
Those are used for weights 2, 4, 3 and 2 respectively. Why is 2 listed twice? The upper 2 bits add an extra 0.125 each to the second weight's value (0.375 max).
And then the three sets of 10 bits each are the weights in descending order (#4 -> #3 -> #2), and need to be divided by 1023 (0x3FF) and then again for the following:
2nd = divide by 8 (0.125 max) + 0.125/0.25/0.375 from the upper bits, 3rd = divide by 3 (0.333 max), 4th = divide by 4 (0.25 max).
And finally weight #1 is the remainder, 1.0 minus #2, #3 and #4 combined.
In retrospect, I can see how this works... but what, exactly, was the problem with using float values for this sorta thing again???
Either way, thanks to that recycled hare model for being there, making me not want to rip out my hair.
Or, in scripting terms:
Code: Select allWeightVars = readlong f
Weight2 = (((bit.and (WeightVars) 0x3FF) as float / 1023) / 8) + ((bit.shift WeightVars -30) as float / 8)
Weight3 = ((bit.and (bit.shift WeightVars -10) 0x3FF) as float / 1023) / 3
Weight4 = ((bit.and (bit.shift WeightVars -20) 0x3FF) as float / 1023) / 4
Weight1 = (1 as float - Weight2 - Weight3 - Weight4)

Now once I get static meshes working correctly, I can finally release the update! @_@

Great! You are making very good process
## Post #645
- Username: Diatribal
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 20, 2010 7:48 pm
- Post datetime: 2019-05-11T21:54:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Wondering if any of you kind folks could help me please?

I've managed to extract and import the d3dmesh and skl files from Back to the Future PS4 version, but when I used quickbms to convert the D3Dtx files, it did it, but the converted dds files were all scrambled and screwed up? Am I doing something wrong, or is it a limitation of the Telltale_D3DTX_TftBL_GoT_MCSM_BttFPS4.bms script? It should work right?

Any help much appreciated!

Here's what the DDS's look like:



Thank you!
## Post #646
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-11T22:52:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Diatribal ↑Sun May 12, 2019 5:54 am at Sun May 12, 2019 5:54 am
>
> Wondering if any of you kind folks could help me please?

I've managed to extract and import the d3dmesh and skl files from Back to the Future PS4 version, but when I used quickbms to convert the D3Dtx files, it did it, but the converted dds files were all scrambled and screwed up? Am I doing something wrong, or is it a limitation of the Telltale_D3DTX_TftBL_GoT_MCSM_BttFPS4.bms script? It should work right?

Any help much appreciated!

Here's what the DDS's look like:

*image*

Thank you!I'll need to write up an alternative script for those to treat them as GNF files instead of DDS, since they use the PS4's swizzling format.

Anyway, there seems to be only two more little things that came up that I need to adjust before I can release the script -- while static meshes work now, there's a few that won't for some reason. It's always gotta be something.
## Post #647
- Username: Diatribal
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 20, 2010 7:48 pm
- Post datetime: 2019-05-11T23:24:27+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sun May 12, 2019 6:52 am at Sun May 12, 2019 6:52 am
>
> 
I'll need to write up an alternative script for those to treat them as GNF files instead of DDS, since they use the PS4's swizzling format.

Anyway, there seems to be only two more little things that came up that I need to adjust before I can release the script -- while static meshes work now, there's a few that won't for some reason. It's always gotta be something.

Hey RandomTBush! What a legend! Thank you very much for kindly responding so quick, I am really grateful. Also really grateful for your awesome scripts!

Ahhh okay, so I don't think it's anything that I'm doing wrong? That's a relief. Will I need to convert them from GNF files to DDS/png for 3ds Max?

Also, I'm not sure if I need a game number for a separate part of the game files called BTTF_ps4_Shared_txmesh.ttarch2? I used 41 which was the same for Episode 1 and it seemed to extract the models without any problems, although the bones looked very slightly out of alignment? Again, might be more of my inexperience than anything?

Anyway, thanks again for your awesome work and kind willingness to help, I really appreciate it!

Look forward to your next release!
## Post #648
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-12T00:27:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Guess what time it is~

[https://mega.nz/#!LkB3iArL!4THSfnCXshsR ... aTxzPboO8M](https://mega.nz/#!LkB3iArL!4THSfnCXshsRHGoDtHiW6AmY5bUxwWWcdaTxzPboO8M)

Changelist:
Finally added support for The Walking Dead: The Final Season.
Added automatic texture importing for the rest of the games, thanks to daemon1 for pointing me in the right direction!
Added a ton of bone names, validated using the method used for the above.
Added model version auto-detection so the per-game options are no longer necessary, UI rearranged accordingly.
Fixed support for Batman: The Telltale Series in the process of the above change.

Make sure the "TelltaleHashDBs" folder is located in the root of your 3DS Max's "Scripts" folder, or else the script will error. You can also delete the "TelltaleIcons" folder as it's no longer necessary.

Next thing I'll be doing is fixing up the D3DTX scripts (especially considering there's a bunch from Season 4 that don't work), but I think I'm gonna take a little time off due to how much time I've spent on this script in the past few months. As always, please let me know if there are any other issues. (EDIT: And do those optimizations I meant to do earlier, I was more concerned with getting TWD4's support done first and foremost.)

> Reply from Diatribal ↑Sun May 12, 2019 7:24 am at Sun May 12, 2019 7:24 am
>
> Ahhh okay, so I don't think it's anything that I'm doing wrong? That's a relief. Will I need to convert them from GNF files to DDS/png for 3ds Max?

Also, I'm not sure if I need a game number for a separate part of the game files called BTTF_ps4_Shared_txmesh.ttarch2? I used 41 which was the same for Episode 1 and it seemed to extract the models without any problems, although the bones looked very slightly out of alignment? Again, might be more of my inexperience than anything?Yeah, you'll be able to use Noesis to convert them afterwards no problem.

And as for the game numbers, I think you can just use any number for console games, I don't recall them having any sort of encryption (only the PC versions do, oddly enough).
## Post #649
- Username: Tecosaurus
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 25, 2019 5:08 pm
- Post datetime: 2019-05-12T00:32:55+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Thank You so much!!!

Wow, it must feel so good that you saw this through until the end. Now that Telltale has unfortunately shutdown and the script is updated for The Final Season, with only a few things you aim to fix up here and there, it must feel like you've fulfilled your ultimate goal!

Congratulations and good luck with your future endeavors!
## Post #650
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-05-12T00:50:42+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Awesome work. Now I’ll be able to update all of my model rips.

Edit: Also does this mean that we can extract models from The Walking Dead: Collection? The visually enchanced versions?
## Post #651
- Username: voxeltrance
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 13, 2019 1:05 pm
- Post datetime: 2019-05-12T01:01:46+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

deleted
## Post #652
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-12T01:13:40+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12 ↑Sun May 12, 2019 8:50 am at Sun May 12, 2019 8:50 am
>
> Edit: Also does this mean that we can extract models from The Walking Dead: Collection? The visually enchanced versions?Yep, technically that was already supported in the previous update if you used the Batman S2 option, but now it's automatic. Textures, however, aren't until I get the GNF-based scripts done.
## Post #653
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-05-12T01:26:00+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sun May 12, 2019 9:13 am at Sun May 12, 2019 9:13 am
>
> 
Escope12 wrote: ↑Sun May 12, 2019 8:50 amEdit: Also does this mean that we can extract models from The Walking Dead: Collection? The visually enchanced versions?Yep, technically that was already supported in the previous update if you used the Batman S2 option, but now it's automatic. Textures, however, aren't until I get the GNF-based scripts done.

I’ll wait for the GNF-based scripts first before extracting from The Walking Dead: Collection.

Edit: I hate asking this but did anyone extract the game files from The Walking Dead: Collection?
## Post #654
- Username: Zombieali2000
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Sep 08, 2014 6:07 am
- Post datetime: 2019-05-12T02:32:39+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Thank you! I can finally start my XPS Pack for the Finale season!
## Post #655
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-05-12T05:47:46+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sun May 12, 2019 8:27 am at Sun May 12, 2019 8:27 am
>
> 
Guess what time it is~

https://mega.nz/#!LkB3iArL!4THSfnCXshsR ... aTxzPboO8M

Changelist:
Finally added support for The Walking Dead: The Final Season.
Added automatic texture importing for the rest of the games, thanks to daemon1 for pointing me in the right direction!
Added a ton of bone names, validated using the method used for the above.
Added model version auto-detection so the per-game options are no longer necessary, UI rearranged accordingly.
Fixed support for Batman: The Telltale Series in the process of the above change.

Make sure the "TelltaleHashDBs" folder is located in the root of your 3DS Max's "Scripts" folder, or else the script will error. You can also delete the "TelltaleIcons" folder as it's no longer necessary.

Next thing I'll be doing is fixing up the D3DTX scripts (especially considering there's a bunch from Season 4 that don't work), but I think I'm gonna take a little time off due to how much time I've spent on this script in the past few months. As always, please let me know if there are any other issues. (EDIT: And do those optimizations I meant to do earlier, I was more concerned with getting TWD4's support done first and foremost.)
Diatribal wrote: ↑Sun May 12, 2019 7:24 amAhhh okay, so I don't think it's anything that I'm doing wrong? That's a relief. Will I need to convert them from GNF files to DDS/png for 3ds Max?

Also, I'm not sure if I need a game number for a separate part of the game files called BTTF_ps4_Shared_txmesh.ttarch2? I used 41 which was the same for Episode 1 and it seemed to extract the models without any problems, although the bones looked very slightly out of alignment? Again, might be more of my inexperience than anything?Yeah, you'll be able to use Noesis to convert them afterwards no problem.

And as for the game numbers, I think you can just use any number for console games, I don't recall them having any sort of encryption (only the PC versions do, oddly enough).

Oh yes! Thank you so much for this!!!
## Post #656
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-05-12T06:16:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

One more question though is how exactly to auto-import textures? I'm guessing you just have to just .dds or .png files in the same folder as .d3dmesh-es you are importing right?
## Post #657
- Username: Diatribal
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 20, 2010 7:48 pm
- Post datetime: 2019-05-12T07:55:34+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sun May 12, 2019 8:27 am at Sun May 12, 2019 8:27 am
>
> 
Guess what time it is~

It's time to say "thank you very much!"

Wow, I'm blown away by how quick and determined you have been to help everyone out here! I'm extremely grateful.

Completely understand why you need to take a well deserved break from all of this and patiently await the D3DTX (GNF) script(s)...

Kudos and good karma!
## Post #658
- Username: Diatribal
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 20, 2010 7:48 pm
- Post datetime: 2019-05-12T07:57:34+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum ↑Sun May 12, 2019 2:16 pm at Sun May 12, 2019 2:16 pm
>
> 
One more question though is how exactly to auto-import textures? I'm guessing you just have to just .dds or .png files in the same folder as .d3dmesh-es you are importing right?

I think either that, or put all .dds .png in a folder called Textures
## Post #659
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-05-12T08:22:10+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Currently making Violet, and I just have to say, i've never been so incredibly happy. Thank you so much for your hard work, RTB.
## Post #660
- Username: Diatribal
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 20, 2010 7:48 pm
- Post datetime: 2019-05-12T08:56:44+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

RandomTBush You're even more awesome than I thought!

In exploring this thread a little deeper, I discovered that you have already solved the PS4 texture issue in a previous post!

> Reply from RandomTBush ↑Sat Mar 03, 2018 6:58 pm at Sat Mar 03, 2018 6:58 pm
>
> 
Oh hey, turns out that the PlayStation 4 version of Back to the Future: The Game (30th Anniversary Edition) actually has models that can be properly read (compared to the 360 version's which were practically impossible to figure out the rigging for), and are using almost the same format as Minecraft: Story Mode, so I was able to implement support for it pretty quickly (I just needed to add a one-byte signed normals format)!... but now I gotta figure out how to get its textures exported/converted correctly since (they're using the basic PS4 swizzle). Hrm.
(EDIT: Looks like a combination of the MC:SM script which I'll be uploading a fix for soon, and chrrox's DDS-to-GTF script seems to work for that!)


Until then, the PC version's textures seem to work! But yeah, I'll be uploading the updated script soon! (Man, I really wish that I can figure out the other games someday...)

For anyone interested, I used RandomTBush's technique above which has worked perfectly for extracting the PS4 D3DTX textures

• Use [chrrox's DDS-to-GNF script](http://forum.xentax.com/viewtopic.php?p=137757#p137757) to convert (fix) the exported (scrambled) dds textures to GNF format. (Copy the text into a notepad document and save as anyfilename, All files and add the .bms extension to the end of the filename)

• Use [Noesis](http://www.richwhitehouse.com/filemirror/noesisv4401.zip) to convert the converted GNF textures to dds

• Put these dds textures in a folder called Textures

Just need to figure out how to batch convert in Noesis... [Edit: Tools > Batch Process  ]
## Post #661
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-12T12:09:02+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Diatribal ↑Sun May 12, 2019 4:56 pm at Sun May 12, 2019 4:56 pm
>
> RandomTBush You're even more awesome than I thought!

In exploring this thread a little deeper, I discovered that you have already solved the PS4 texture issue in a previous post!Haha, whoops! I completely forgot about that! I'll go add a link to this in the first post.

> Reply from Maximmum ↑Sun May 12, 2019 2:16 pm at Sun May 12, 2019 2:16 pm
>
> One more question though is how exactly to auto-import textures? I'm guessing you just have to just .dds or .png files in the same folder as .d3dmesh-es you are importing right?Yep. By default, the textures will be read from DDS files in the same folder as the D3DMesh files, but there are menu options to change that to look for PNGs, or read from a separate "Textures" folder like the original versions of the script.
## Post #662
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-05-12T13:04:02+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sun May 12, 2019 8:27 am at Sun May 12, 2019 8:27 am
>
> 
Guess what time it is~

https://mega.nz/#!LkB3iArL!4THSfnCXshsR ... aTxzPboO8M

Changelist:
Finally added support for The Walking Dead: The Final Season.
Added automatic texture importing for the rest of the games, thanks to daemon1 for pointing me in the right direction!
Added a ton of bone names, validated using the method used for the above.
Added model version auto-detection so the per-game options are no longer necessary, UI rearranged accordingly.
Fixed support for Batman: The Telltale Series in the process of the above change.

Make sure the "TelltaleHashDBs" folder is located in the root of your 3DS Max's "Scripts" folder, or else the script will error. You can also delete the "TelltaleIcons" folder as it's no longer necessary.

Next thing I'll be doing is fixing up the D3DTX scripts (especially considering there's a bunch from Season 4 that don't work), but I think I'm gonna take a little time off due to how much time I've spent on this script in the past few months. As always, please let me know if there are any other issues. (EDIT: And do those optimizations I meant to do earlier, I was more concerned with getting TWD4's support done first and foremost.)
Diatribal wrote: ↑Sun May 12, 2019 7:24 amAhhh okay, so I don't think it's anything that I'm doing wrong? That's a relief. Will I need to convert them from GNF files to DDS/png for 3ds Max?

Also, I'm not sure if I need a game number for a separate part of the game files called BTTF_ps4_Shared_txmesh.ttarch2? I used 41 which was the same for Episode 1 and it seemed to extract the models without any problems, although the bones looked very slightly out of alignment? Again, might be more of my inexperience than anything?Yeah, you'll be able to use Noesis to convert them afterwards no problem.

And as for the game numbers, I think you can just use any number for console games, I don't recall them having any sort of encryption (only the PC versions do, oddly enough).

WOW! THANK YOU SO MUCH I'VE BEEN WAITING SO LONG FOR THIS, THANK YOU A LOT
## Post #663
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-05-12T13:30:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Amazing work, RTB!

Just one question; does the script auto-apply 'sub'textures such as the 'detail', 'ao' and 'brushnormal' textures - and do they work properly? I could never figure out how to get them to do so myself, they never seemed to have an effect.
## Post #664
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-05-12T13:36:24+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Sun May 12, 2019 9:30 pm at Sun May 12, 2019 9:30 pm
>
> 
Amazing work, RTB!

Just one question; does the script auto-apply 'sub'textures such as the 'detail', 'ao' and 'brushnormal' textures - and do they work properly? I could never figure out how to get them to do so myself, they never seemed to have an effect.
Yes it does auto apply textures if you do it like on these pictures: 

Put the Textures Folder with all textures for that character you want to import in where the Meshes are:


And select these options on the Script in 3D Max (You need to select DDS if your textures are in .dds format, if its in .png select PNG):



It should auto apply the texture to the 3d model!
## Post #665
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-12T14:12:48+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Sun May 12, 2019 9:30 pm at Sun May 12, 2019 9:30 pm
>
> Just one question; does the script auto-apply 'sub'textures such as the 'detail', 'ao' and 'brushnormal' textures - and do they work properly? I could never figure out how to get them to do so myself, they never seemed to have an effect.Sub-textures? Unfortunately not at this moment, especially since some models use a whole lot. However, you can view all of the textures a specific material uses if you enable the "Print debug" option and look in the listener window after importing a model, which will give you something like this:

```
"10fb176f b7821ec8: sk62_clementine400_headwrinkleb_mask"
"1e3f6b9f 2550389d: sk62_clementine400_head_nm"
"2aa89260 d8661f89: sk62_clementine400_head_grime"
"36170f97 445b6e2e: sk62_clementine400_headdecal"
"7498a5f1 b80ad419: sk62_clementine400_head_bnm"
"8648fa82 d1dbee1a: sk62_clementine400_head"
"9cf676c6 403c9784: sk62_clementine400_headdecal_nm"
"a13d14fb b436f23b: sk62_clementine400_headwrinkle_nm"
"a1f1257a 331854c4: sk62_clementine400_headdecalmask"
"d5b57775 db361670: sk62_clementine400_head_spec"
"d7ea3553 4dbc457d: sk62_clementine400_headwrinklea_mask"
"ff787a61 eac8a5b5: sk62_clementine400_head_ink"
```


Yeah. Not exactly something that I'd easily be able to interpret via material settings.
## Post #666
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-05-12T14:31:13+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Did anyone notice that some of the characters’ bones names are something like “0x87c318c2” or “0xbf4a0925” or something like that?
## Post #667
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-05-12T14:39:26+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12 ↑Sun May 12, 2019 10:31 pm at Sun May 12, 2019 10:31 pm
>
> 
Did anyone notice that some of the characters’ bones names are something like “0x87c318c2” or “0xbf4a0925” or something like that?

Yeah
## Post #668
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-05-12T14:40:30+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Annie2 ↑Sun May 12, 2019 10:39 pm at Sun May 12, 2019 10:39 pm
>
> 
Escope12 wrote: ↑Sun May 12, 2019 10:31 pm
Did anyone notice that some of the characters’ bones names are something like “0x87c318c2” or “0xbf4a0925” or something like that?


Yeah

I wonder what those mean?
## Post #669
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-12T14:49:01+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12 ↑Sun May 12, 2019 10:40 pm at Sun May 12, 2019 10:40 pm
>
> Annie2 wrote: ↑Sun May 12, 2019 10:39 pmEscope12 wrote: ↑Sun May 12, 2019 10:31 pmDid anyone notice that some of the characters’ bones names are something like “0x87c318c2” or “0xbf4a0925” or something like that?YeahI wonder what those mean?Means I don't have the actual bone names for those set up, so it displays the first four bytes of its hash instead. [Basically relates to what I mentioned earlier regarding the old "BoneRename" command](https://forum.xentax.com/viewtopic.php?p=150723#p150723), even though I have 6,253 bones named (you can have a look at "BoneNames.txt" in the hashes subfolder to see a full list), there's still around 10,272 that aren't as their names aren't quite as obvious to figure out.
## Post #670
- Username: Diatribal
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 20, 2010 7:48 pm
- Post datetime: 2019-05-12T14:55:51+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jayko ↑Sun May 12, 2019 9:30 pm at Sun May 12, 2019 9:30 pm
>
> 
Amazing work, RTB!

Just one question; does the script auto-apply 'sub'textures such as the 'detail', 'ao' and 'brushnormal' textures - and do they work properly? I could never figure out how to get them to do so myself, they never seemed to have an effect.

That would certainly be a “perfect world” scenario, but I think that’s expecting a little too much to expect the script to be able to decipher, separate and apply the separate maps! You’ve got to do some work manually! LOL I think we’re incredibly lucky to have a script that can save us having to apply all of the diffuse maps alone! You’ll be expecting an auto-render button next?! hahaha
## Post #671
- Username: The Polish Army
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 01, 2019 12:03 am
- Post datetime: 2019-05-12T15:53:50+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Importer are working only with 3dsmax 2019 or with other version?
## Post #672
- Username: jayko
- Rank: advanced
- Number of posts: 62
- Joined date: Wed Dec 28, 2016 2:25 pm
- Post datetime: 2019-05-12T16:26:40+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sun May 12, 2019 10:12 pm at Sun May 12, 2019 10:12 pm
>
> 
jayko wrote: ↑Sun May 12, 2019 9:30 pmJust one question; does the script auto-apply 'sub'textures such as the 'detail', 'ao' and 'brushnormal' textures - and do they work properly? I could never figure out how to get them to do so myself, they never seemed to have an effect.Sub-textures? Unfortunately not at this moment, especially since some models use a whole lot. However, you can view all of the textures a specific material uses if you enable the "Print debug" option and look in the listener window after importing a model, which will give you something like this:
Code: Select all"Material hash: 52a09151 f1c3f2c7, Count = 12, Offset = 904"
"10fb176f b7821ec8: sk62_clementine400_headwrinkleb_mask"
"1e3f6b9f 2550389d: sk62_clementine400_head_nm"
"2aa89260 d8661f89: sk62_clementine400_head_grime"
"36170f97 445b6e2e: sk62_clementine400_headdecal"
"7498a5f1 b80ad419: sk62_clementine400_head_bnm"
"8648fa82 d1dbee1a: sk62_clementine400_head"
"9cf676c6 403c9784: sk62_clementine400_headdecal_nm"
"a13d14fb b436f23b: sk62_clementine400_headwrinkle_nm"
"a1f1257a 331854c4: sk62_clementine400_headdecalmask"
"d5b57775 db361670: sk62_clementine400_head_spec"
"d7ea3553 4dbc457d: sk62_clementine400_headwrinklea_mask"
"ff787a61 eac8a5b5: sk62_clementine400_head_ink"

Yeah. Not exactly something that I'd easily be able to interpret via material settings.

Ah, the print debug should be super useful then! 

I suppose I just need to figure out how to make the subtextures actually do much of anything as they've always seemes to have precious little effect. Maybe the render settings I'm using don't compliment them very well.
## Post #673
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-12T16:31:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from The Polish Army ↑Sun May 12, 2019 11:53 pm at Sun May 12, 2019 11:53 pm
>
> Importer are working only with 3dsmax 2019 or with other version?I used 3DS Max 2010 to write and test the script and added fixes specifically for newer versions, so it should work just fine in 2019.
## Post #674
- Username: CartoonCG
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 29, 2019 3:04 am
- Post datetime: 2019-05-12T17:22:54+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I'm a bit stuck on the auto tx importer here; this is what I get when I use the print debug and when I open MAXscript listener

 "Importing sk54_carlos.d3dmesh (Version 14)..."
"Model start = 211L"
"Count = 7"
"Model info start = 263L"
"Model info start = 539L"
"Model info start = 815L"
"Model info start = 1091L"
"Model info start = 1367L"
"Model info start = 1643L"
"Model info start = 1919L"
"Header B start = 2195L"
"Header C (Bone IDs) start = 2203L"
"Count = 2"
"Header D start = 7819L"
"Header E start = 7827L"
"Header F start = 7835L"
"Header G start = 7843L"
"Header H (Material Info) start = 7851L"
"Header I start = 8835L"
"UV Multipliers = 1 (1.0, 1.0), 2 (1.0, 1.0), 3 (1.0, 1.0), 4 (1.0, 1.0)"
"Header J start = 8867L"
"Header K start = 8875L"
"Face info start = 8888L"
"Vertex Buffer start = 42794L"
"Vertex Offset = 0, Count = 3, Format = 1"
"UV Offset = 12, Count = 2, Format = 4"
"Normals Offset = 36, Count = 3, Format = 4"
"Weights Offset = 24, Count = 4, Format = 5"
"Bones Offset = 20, Count = 4, Format = 8"
"Unknown1 Offset = 32, Count = 1, Format = 1"
"Binormals? Offset = 52, Count = 4, Format = 4"
"Tangents? Offset = 44, Count = 3, Format = 4"
"UV3 Offset = 16, Count = 2, Format = 4"
"Vertex start = 42962L"
"End of file = 272462L"
(Polygon_Info_Struct VertexMin:1 VertexMax:220 PolygonStart:1 PolygonCount:288 FacePointCount:864 MatNum:5 BoneSetNum:1)
(Polygon_Info_Struct VertexMin:3529 VertexMax:3825 PolygonStart:289 PolygonCount:220 FacePointCount:660 MatNum:6 BoneSetNum:1)
(Polygon_Info_Struct VertexMin:3338 VertexMax:3528 PolygonStart:509 PolygonCount:140 FacePointCount:420 MatNum:3 BoneSetNum:1)
(Polygon_Info_Struct VertexMin:3009 VertexMax:3337 PolygonStart:649 PolygonCount:534 FacePointCount:1602 MatNum:2 BoneSetNum:1)
(Polygon_Info_Struct VertexMin:1982 VertexMax:3008 PolygonStart:1183 PolygonCount:1577 FacePointCount:4731 MatNum:1 BoneSetNum:1)
(Polygon_Info_Struct VertexMin:1065 VertexMax:1981 PolygonStart:2760 PolygonCount:1614 FacePointCount:4842 MatNum:4 BoneSetNum:1)
(Polygon_Info_Struct VertexMin:221 VertexMax:1064 PolygonStart:4374 PolygonCount:1276 FacePointCount:3828 MatNum:4 BoneSetNum:2)
"Importing sk54_carlos203_body.d3dmesh (Version 14)..."
"Model start = 219L"
"Count = 6"
"Model info start = 271L"
"Model info start = 547L"
"Model info start = 823L"
"Model info start = 1099L"
"Model info start = 1375L"
"Model info start = 1651L"
"Header B start = 1927L"
"Header C (Bone IDs) start = 1935L"
"Count = 1"
"Header D start = 5419L"
"Header E start = 5427L"
"Header F start = 5435L"
"Header G start = 5443L"
"Header H (Material Info) start = 5451L"
"Header I start = 6435L"
"UV Multipliers = 1 (1.0, 1.0), 2 (1.0, 1.0), 3 (1.0, 1.0), 4 (1.0, 1.0)"
"Header J start = 6467L"
"Header K start = 6475L"
"Face info start = 6488L"
"Vertex Buffer start = 32558L"
"Vertex Offset = 0, Count = 3, Format = 1"
"UV Offset = 12, Count = 2, Format = 4"
"Normals Offset = 36, Count = 3, Format = 4"
"Weights Offset = 24, Count = 4, Format = 5"
"Bones Offset = 20, Count = 4, Format = 8"
"Unknown1 Offset = 32, Count = 1, Format = 1"
"Binormals? Offset = 52, Count = 4, Format = 4"
"Tangents? Offset = 44, Count = 3, Format = 4"
"UV3 Offset = 16, Count = 2, Format = 4"
"Vertex start = 32726L"
"End of file = 209846L"
(Polygon_Info_Struct VertexMin:1 VertexMax:297 PolygonStart:1 PolygonCount:220 FacePointCount:660 MatNum:6 BoneSetNum:1)
(Polygon_Info_Struct VertexMin:2733 VertexMax:2952 PolygonStart:221 PolygonCount:288 FacePointCount:864 MatNum:5 BoneSetNum:1)
(Polygon_Info_Struct VertexMin:2542 VertexMax:2732 PolygonStart:509 PolygonCount:140 FacePointCount:420 MatNum:3 BoneSetNum:1)
(Polygon_Info_Struct VertexMin:2213 VertexMax:2541 PolygonStart:649 PolygonCount:534 FacePointCount:1602 MatNum:2 BoneSetNum:1)
(Polygon_Info_Struct VertexMin:298 VertexMax:1324 PolygonStart:1183 PolygonCount:1577 FacePointCount:4731 MatNum:1 BoneSetNum:1)
(Polygon_Info_Struct VertexMin:1325 VertexMax:2212 PolygonStart:2760 PolygonCount:1584 FacePointCount:4752 MatNum:4 BoneSetNum:1)
"Importing sk54_carlos203_hands.d3dmesh (Version 14)..."
"Model start = 220L"
"Count = 1"
"Model info start = 272L"
"Header B start = 548L"
"Header C (Bone IDs) start = 556L"
"Count = 1"
"Header D start = 2584L"
"Header E start = 2592L"
"Header F start = 2600L"
"Header G start = 2608L"
"Header H (Material Info) start = 2616L"
"Header I start = 2880L"
"UV Multipliers = 1 (1.0, 1.0), 2 (1.0, 1.0), 3 (1.0, 1.0), 4 (1.0, 1.0)"
"Header J start = 2912L"
"Header K start = 2920L"
"Face info start = 2933L"
"Vertex Buffer start = 10781L"
"Vertex Offset = 0, Count = 3, Format = 1"
"UV Offset = 12, Count = 2, Format = 4"
"Normals Offset = 36, Count = 3, Format = 4"
"Weights Offset = 24, Count = 4, Format = 5"
"Bones Offset = 20, Count = 4, Format = 8"
"Unknown1 Offset = 32, Count = 1, Format = 1"
"Binormals? Offset = 44, Count = 4, Format = 4"
"UV3 Offset = 16, Count = 2, Format = 4"
"Vertex start = 10949L"
"End of file = 55669L"
(Polygon_Info_Struct VertexMin:1 VertexMax:860 PolygonStart:1 PolygonCount:1306 FacePointCount:3918 MatNum:1 BoneSetNum:1)
"Done! (19.333 Seconds)"

I cant tell where to find the texture and also when I export in obj file format it dosent ask for the right texture name instead its replace with random letters and number.

Im trying to export the adv maps 3d models like carver's camp (the Howe's exterior) and Carlos from S2 TWD.

any clue of what im doing wrong

(EDIT: I did a recheck....what im trying to do is to get it auto apply when I import TWDS2 levels/character but I get nothing....I usally export to obj and usally does it by itself for season 1 TWD but now it ask for a texture that has its name randomize and here is where im stuck at I get a grey model and the debug listener list no texture that has importer and yes I have the model and texture in one folder and I try sub folder....im stupid when stuff like this happened plz help me)
## Post #675
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-05-12T22:29:15+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hi guys, I just had a question. If I now use like for example Clementines character in a game that I have been privately working on, and release the game but other players wont be able to use Clementines character in the game, only game developer will be able to. Will I still get in trouble for it? Will I get sued for using her character in my game?
## Post #676
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-05-12T22:45:13+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Annie2 ↑Mon May 13, 2019 6:29 am at Mon May 13, 2019 6:29 am
>
> 
Hi guys, I just had a question. If I now use like for example Clementines character in a game that I have been privately working on, and release the game but other players wont be able to use Clementines character in the game, only game developer will be able to. Will I still get in trouble for it? Will I get sued for using her character in my game?You're fine as long as you dont make money doing it.

Also holy shit, RTD finished it?! I've been playing Days Gone for like 24hrs straight and completely missed it lol.
## Post #677
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-05-13T00:16:46+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Is it also possible to get the animations of the Characters of The Walking Dead: The final season into 3dmax?

Edit: I assume "CLEMENTINE-IDLES.prop" are the animations? But is it possible to import it to 3d max?
## Post #678
- Username: Über Winfrey
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Nov 16, 2018 7:38 am
- Post datetime: 2019-05-13T00:31:07+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

anyone happen to know what texture Lee uses for his hair strands, I've dumped the files and haven't seen a d3dtx for it, I've tried other character's files to see if maybe he reuses them but so far came back negative.

Edit: I figured it out, he uses Aj's Hair texture
## Post #679
- Username: ChoChoCup
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 13, 2019 9:00 am
- Post datetime: 2019-05-13T01:03:12+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Does anyone have a collection of telltale models? (unconverted) im looking for models for every game. (if not,i'd be looking for TWD Season 1-4 + Michonne And Minecraft Story Mode Season 1 And 2.) I'd like to convert these for programs (With credit.) if anyone has some,PLEASE send me a link/download.
## Post #680
- Username: Diatribal
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 20, 2010 7:48 pm
- Post datetime: 2019-05-13T06:17:48+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Annie2 ↑Mon May 13, 2019 6:29 am at Mon May 13, 2019 6:29 am
>
> 
Hi guys, I just had a question. If I now use like for example Clementines character in a game that I have been privately working on, and release the game but other players wont be able to use Clementines character in the game, only game developer will be able to. Will I still get in trouble for it? Will I get sued for using her character in my game?

Hmmm, I am no legal expert, but... I would definitely not use a character model from another game developer in your game! Even if it is only available to other developers, if your game goes out to the public and someone manages to mod your game or look inside the game code and discover a game model from another game, that could be a very costly mistake! GTA San Andreas ["Hot Coffee"](https://en.wikipedia.org/wiki/Hot_Coffee_mod) is a perfect example, the developers put a sex scene in the game and didn't remove it when the game was released. Game modders discovered it and how to access it and unless I am mistaken, Rockstar took a pretty heavy hit for it. There were lawsuits and I think it even went as far as Hilary Clinton!

Of course, the choice is yours, but I would definitely not release your game to the public with a Telltale model in it. If it is just for the developers, then why don't you just do a developer version of the game that doesn't go out to the public? Use any number of copyrighted models in that version.
## Post #681
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-05-13T11:39:51+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Diatribal ↑Mon May 13, 2019 2:17 pm at Mon May 13, 2019 2:17 pm
>
> 
Annie2 wrote: ↑Mon May 13, 2019 6:29 am
Hi guys, I just had a question. If I now use like for example Clementines character in a game that I have been privately working on, and release the game but other players wont be able to use Clementines character in the game, only game developer will be able to. Will I still get in trouble for it? Will I get sued for using her character in my game?


Hmmm, I am no legal expert, but... I would definitely not use a character model from another game developer in your game! Even if it is only available to other developers, if your game goes out to the public and someone manages to mod your game or look inside the game code and discover a game model from another game, that could be a very costly mistake! GTA San Andreas "Hot Coffee" is a perfect example, the developers put a sex scene in the game and didn't remove it when the game was released. Game modders discovered it and how to access it and unless I am mistaken, Rockstar took a pretty heavy hit for it. There were lawsuits and I think it even went as far as Hilary Clinton!

Of course, the choice is yours, but I would definitely not release your game to the public with a Telltale model in it. If it is just for the developers, then why don't you just do a developer version of the game that doesn't go out to the public? Use any number of copyrighted models in that version.

You are right, thank you.
## Post #682
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-05-15T04:49:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I keep getting an error when trying to convert D3DTX Textures into DDS with the Quickbms Scripts.
## Post #683
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-05-15T08:16:06+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Annie2 ↑Mon May 13, 2019 7:39 pm at Mon May 13, 2019 7:39 pm
>
> 
Diatribal wrote: ↑Mon May 13, 2019 2:17 pm
Annie2 wrote: ↑Mon May 13, 2019 6:29 am
Hi guys, I just had a question. If I now use like for example Clementines character in a game that I have been privately working on, and release the game but other players wont be able to use Clementines character in the game, only game developer will be able to. Will I still get in trouble for it? Will I get sued for using her character in my game?


Hmmm, I am no legal expert, but... I would definitely not use a character model from another game developer in your game! Even if it is only available to other developers, if your game goes out to the public and someone manages to mod your game or look inside the game code and discover a game model from another game, that could be a very costly mistake! GTA San Andreas "Hot Coffee" is a perfect example, the developers put a sex scene in the game and didn't remove it when the game was released. Game modders discovered it and how to access it and unless I am mistaken, Rockstar took a pretty heavy hit for it. There were lawsuits and I think it even went as far as Hilary Clinton!

Of course, the choice is yours, but I would definitely not release your game to the public with a Telltale model in it. If it is just for the developers, then why don't you just do a developer version of the game that doesn't go out to the public? Use any number of copyrighted models in that version.


You are right, thank you.

No he's actually wrong, as long as you don't have money from this game and release for free you won't be sued, i know lots of examples so don't worry and please release it, i'm now kind of hyped about it and would really love to play it))  
You don't hype up somebody about the game you make and then says you won't release it
## Post #684
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-05-15T13:38:01+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum ↑Wed May 15, 2019 4:16 pm at Wed May 15, 2019 4:16 pm
>
> 
Annie2 wrote: ↑Mon May 13, 2019 7:39 pm
Diatribal wrote: ↑Mon May 13, 2019 2:17 pm


Hmmm, I am no legal expert, but... I would definitely not use a character model from another game developer in your game! Even if it is only available to other developers, if your game goes out to the public and someone manages to mod your game or look inside the game code and discover a game model from another game, that could be a very costly mistake! GTA San Andreas "Hot Coffee" is a perfect example, the developers put a sex scene in the game and didn't remove it when the game was released. Game modders discovered it and how to access it and unless I am mistaken, Rockstar took a pretty heavy hit for it. There were lawsuits and I think it even went as far as Hilary Clinton!

Of course, the choice is yours, but I would definitely not release your game to the public with a Telltale model in it. If it is just for the developers, then why don't you just do a developer version of the game that doesn't go out to the public? Use any number of copyrighted models in that version.


You are right, thank you.


No he's actually wrong, as long as you don't have money from this game and release for free you won't be sued, i know lots of examples so don't worry and please release it, i'm now kind of hyped about it and would really love to play it))  
You don't hype up somebody about the game you make and then says you won't release it

Oh, so good. There won't be any problems as long as I don't make any money of it, good to know that! .

The game that I am working on is based on a fictional war between NATO and Soviet Union, but there will be characters that are not related to the story that the game is based on, such as The Joker, Clown, Santa man, Snowman etc.. and if you guys say that it won't be a problem having Clementine in it, then her character will be a part of that. Of course there will be credit given to the game, TWD and Telltale.

And I wouldn't be surprised if some of you here have already heard of RSR, it's a old project that I have been working on since 2015.

The game is on IndieDB, I'll show soon screenshots and videos of the gameplay, maybe I'll show Clementine in some of the gameplays too :
[https://www.indiedb.com/games/red-squad-reborn](https://www.indiedb.com/games/red-squad-reborn)
## Post #685
- Username: Diatribal
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 20, 2010 7:48 pm
- Post datetime: 2019-05-16T06:49:36+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum ↑Wed May 15, 2019 4:16 pm at Wed May 15, 2019 4:16 pm
>
> No he's actually wrong, as long as you don't have money from this game and release for free you won't be sued, i know lots of examples so don't worry and please release it, i'm now kind of hyped about it and would really love to play it))  
You don't hype up somebody about the game you make and then says you won't release it

Perhaps if you're so willing to irresponsibly offer your "professional legal advice", you could explain your professional background or how you are so certain that a game developer could use intellectually protected, copyrighted material from another game studio?!! Please enlighten us to these "lots of examples" that you mention where a game studio or developer has used copyrighted assets from another studio, without permission, legally??? I am sorry, but I suspect that you don't know what you are talking about, at all. I also suspect that you're probably some irresponsible teenager/kid who is more "hyped" about playing an unreleased game than you are about the developer putting themselves at legal risk by releasing a game that uses copyrighted material!

I can't wait to hear of these examples of games that have been legally released, that use other copyrighted assets from other games, without permission!
## Post #686
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-05-16T11:30:44+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Diatribal ↑Thu May 16, 2019 2:49 pm at Thu May 16, 2019 2:49 pm
>
> 
Maximmum wrote: ↑Wed May 15, 2019 4:16 pmNo he's actually wrong, as long as you don't have money from this game and release for free you won't be sued, i know lots of examples so don't worry and please release it, i'm now kind of hyped about it and would really love to play it))  
You don't hype up somebody about the game you make and then says you won't release it  


Perhaps if you're so willing to irresponsibly offer your "professional legal advice", you could explain your professional background or how you are so certain that a game developer could use intellectually protected, copyrighted material from another game studio?!! Please enlighten us to these "lots of examples" that you mention where a game studio or developer has used copyrighted assets from another studio, without permission, legally??? I am sorry, but I suspect that you don't know what you are talking about, at all. I also suspect that you're probably some irresponsible teenager/kid who is more "hyped" about playing an unreleased game than you are about the developer putting themselves at legal risk by releasing a game that uses copyrighted material!

I can't wait to hear of these examples of games that have been legally released, that use other copyrighted assets from other games, without permission!

At this point I don't really know to believe who and to say who is right or wrong, but thanks guys for your advices, really. No need to get mad over it or anything, I don't want this to go from a question that I asked to a problem between you guys.

Anyway, have a good day
## Post #687
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-05-16T14:55:24+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Diatribal ↑Thu May 16, 2019 2:49 pm at Thu May 16, 2019 2:49 pm
>
> 
Maximmum wrote: ↑Wed May 15, 2019 4:16 pmNo he's actually wrong, as long as you don't have money from this game and release for free you won't be sued, i know lots of examples so don't worry and please release it, i'm now kind of hyped about it and would really love to play it))  
You don't hype up somebody about the game you make and then says you won't release it  
Perhaps if you're so willing to irresponsibly offer your "professional legal advice", you could explain your professional background or how you are so certain that a game developer could use intellectually protected, copyrighted material from another game studio?!! Please enlighten us to these "lots of examples" that you mention where a game studio or developer has used copyrighted assets from another studio, without permission, legally??? I am sorry, but I suspect that you don't know what you are talking about, at all. I also suspect that you're probably some irresponsible teenager/kid who is more "hyped" about playing an unreleased game than you are about the developer putting themselves at legal risk by releasing a game that uses copyrighted material!

I can't wait to hear of these examples of games that have been legally released, that use other copyrighted assets from other games, without permission!Didnt you basically start out by saying you're not a legal expert? Yet somehow he needs to be one? I'm no legal expert either and dont assume that what I'm talking about is 100% correct.. Oh and when did he say "without permission", I must've missed that part, also there's not really been any game developer to release games for free and use somebody elses work because it's just easier making your own work than using somebody elses. (also why does everybody call somebody an immature kid when told they're wrong? If this were facebook, you'd be insulting his profile picture lol).

What you said has no real value, sure it was actually a thing that happened but I think it was only a legal issue due to the game being sold as *shrug* an 18? (I forget the american age ratings) rather than an R. But back then there was that lawyer who went after every video game that could potentially be modded to include sex, like the Sims.. but that guy was eventually banned from taking matters like that to court. (unless he was disbarred completely). You could also make the case that people could potentially extract the models from your game and sell them, you'd be to blame for that more than the sex thing.

Technically it's illegal to use any video game property free or otherwise without proper permission as it states in every Terms of Service in any video game. All games state in their TOS that:
"you may not: copy the Software except to make archival or backup copies as may be permitted by law; modify or adapt the Software or merge it into another program or create derivative works based on the Software; reverse engineer, disassemble, decompile or make any attempt to discover the source code of the Software; exploit the Software or any of its parts for any commercial purpose"

[https://telltale.com/tos/](https://telltale.com/tos/)

There's been a few modders on dA who've actually asked for permission to extract models and use in programs like XNALara or Garry's Mod and been granted it, though I dont think they've been allowed to share them, there's also a lot of modders on dA who've been asked to take down their content by Sony, Nintendo etc, and eventually banned from the website (I think there's like a 3 strikes policy). So asking them for permission first is the way to go. Though in this case it'll be Skybound you'll need to ask.
## Post #688
- Username: Diatribal
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 20, 2010 7:48 pm
- Post datetime: 2019-05-16T23:31:03+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Thu May 16, 2019 10:55 pm at Thu May 16, 2019 10:55 pm
>
> Didnt you basically start out by saying you're not a legal expert? Yet somehow he needs to be one? I'm no legal expert either and dont assume that what I'm talking about is 100% correct.. Oh and when did he say "without permission", I must've missed that part, also there's not really been any game developer to release games for free and use somebody elses work because it's just easier making your own work than using somebody elses. (also why does everybody call somebody an immature kid when told they're wrong? If this were facebook, you'd be insulting his profile picture lol).

What you said has no real value, sure it was actually a thing that happened but I think it was only a legal issue due to the game being sold as *shrug* an 18? (I forget the american age ratings) rather than an R. But back then there was that lawyer who went after every video game that could potentially be modded to include sex, like the Sims.. but that guy was eventually banned from taking matters like that to court. (unless he was disbarred completely). You could also make the case that people could potentially extract the models from your game and sell them, you'd be to blame for that more than the sex thing.

Technically it's illegal to use any video game property free or otherwise without proper permission as it states in every Terms of Service in any video game. All games state in their TOS that:
"you may not: copy the Software except to make archival or backup copies as may be permitted by law; modify or adapt the Software or merge it into another program or create derivative works based on the Software; reverse engineer, disassemble, decompile or make any attempt to discover the source code of the Software; exploit the Software or any of its parts for any commercial purpose"

https://telltale.com/tos/

There's been a few modders on dA who've actually asked for permission to extract models and use in programs like XNALara or Garry's Mod and been granted it, though I dont think they've been allowed to share them, there's also a lot of modders on dA who've been asked to take down their content by Sony, Nintendo etc, and eventually banned from the website (I think there's like a 3 strikes policy). So asking them for permission first is the way to go. Though in this case it'll be Skybound you'll need to ask.

I literally cannot be bothered to waste any more of my time writing and defending the interests of someone who has been irresponsibly misinformed. You're clearly unable to recognise my decency and good intention of looking out for Annie2 from potential future damages based on the inexperienced brain-farts of yourself and Maximmum:

> Reply from Tydeus ↑Mon May 13, 2019 6:45 am at Mon May 13, 2019 6:45 am
>
> 
You're fine as long as you dont make money doing it.

> Reply from Tydeus ↑Thu May 16, 2019 10:55 pm at Thu May 16, 2019 10:55 pm
>
> I'm no legal expert either and dont assume that what I'm talking about is 100% correct..
Annie2 had asked a question and whilst I am no legal professional and stated that in my reply, it doesn't mean that I am inexperienced enough not to know that what she was asking was most likely illegal. She asked a question and I answered it. I didn't have to answer it at all, I could've just ignored it. What Annie2 decides to do with my answer is completely up to her/him, as are the consequences of her/his decision. It won't affect me either way, but I thought I would offer a friendly word of advice for consideration, as there are potential legal risks.

> Reply from Tydeus
>
> Oh and when did he say "without permission"
He didn't say "without permission", but he answered Annie2's question which was about using game assets without permission and he answered it "wrong" himself, as you actually proved in your response!  

> Reply from Tydeus
>
> Technically it's illegal to use any video game property free or otherwise without proper permission as it states in every Terms of Service in any video game. All games state in their TOS that:
"you may not: copy the Software except to make archival or backup copies as may be permitted by law; modify or adapt the Software or merge it into another program or create derivative works based on the Software; reverse engineer, disassemble, decompile or make any attempt to discover the source code of the Software; exploit the Software or any of its parts for any commercial purpose"

https://telltale.com/tos/

Hahaha, I would say that "what you said has no real value", but in fact all you've done is reinforce my point!  Even using legal ToS to make my point even more valid!    I think you're a bit confused as to who's side you're on?!  

Anyway, I'll sign off with more of your "valuable" confusions...

> Reply from Tydeus ↑Mon May 13, 2019 6:45 am at Mon May 13, 2019 6:45 am
>
> 
You're fine as long as you dont make money doing it.

> Reply from Tydeus ↑Thu May 16, 2019 10:55 pm at Thu May 16, 2019 10:55 pm
>
> I'm no legal expert either and dont assume that what I'm talking about is 100% correct..

> Reply from Tydeus
>
> 
So asking them for permission first is the way to go. Though in this case it'll be Skybound you'll need to ask.
## Post #689
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-05-17T00:06:35+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Okay, pretend I'm "The Dude" from Big Lebowski on how my "calm" is 24/7, I never intend to upset anybody or act like I'm raging or anything. This is just me explaining what I said because I'm not a dick. Your "good intentions" turned into insults so I commented.

I get it, you feel backed into a corner assuming I'm trying to defend someone or insult your intelligence or whatever. I didnt back anybody up other than the fact that you where being a little bitch about it. (especially with the "hahaha " messages, whats that? "ner ner ner I'm right and you're wrong!" that's pretty immature) 

> Reply from Tydeus ↑Thu May 16, 2019 10:55 pm at Thu May 16, 2019 10:55 pm
>
> Didnt you basically start out by saying you're not a legal expert? Yet somehow he needs to be one? -snip- (also why does everybody call somebody an immature kid when told they're wrong? If this were facebook, you'd be insulting his profile picture lol).I said "You're fine as long as you dont make money doing it." which is correct, and the short answer, but asking them for permission first is the way to go to avoid companies who might be butthurt about using property like that. 

"what you said has no real value" was in relation to the "Hot Coffee" comment, that doesnt have any merrit. It was just some asshat trying to find a way to hurt various game developers. Jack somebody.. I forget. But what I said had no reinforcement to what you said, just that it's a non-issue because anything can be turned into anything. I dont think it's possible to be sued if you#ve released something for free, unless it was offensive in some way.

Basically, only a little of what I said was directed at you, I was just explaining the "long answer", which obviously said you're right, and again no I wasnt saying you were wrong on all occasions.

But whatever, act superior if you'd like, I was just taken the wrong way. I cba with any further discussions, lets try not get this thread closed. At least send PMs.
## Post #690
- Username: sugarysyringe
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Feb 15, 2018 1:06 pm
- Post datetime: 2019-05-17T02:15:14+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Instead of fighting, I have a question. Is there a way to separate UVs in blender or 3ds max? I'm porting the TWD:TFS models to MMD, and MMD struggles with transparency unless the hair mesh or whatever is split up into every possible section. Buuut the hair's uv is overlapping a lot, making it hard to do so.
## Post #691
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-05-17T04:42:02+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Fri May 17, 2019 10:15 am at Fri May 17, 2019 10:15 am
>
> 
Instead of fighting, I have a question. Is there a way to separate UVs in blender or 3ds max? I'm porting the TWD:TFS models to MMD, and MMD struggles with transparency unless the hair mesh or whatever is split up into every possible section. Buuut the hair's uv is overlapping a lot, making it hard to do so.
Try split the meshes.
## Post #692
- Username: Diatribal
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 20, 2010 7:48 pm
- Post datetime: 2019-05-17T08:06:30+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Fri May 17, 2019 8:06 am at Fri May 17, 2019 8:06 am
>
> 
Okay, pretend I'm "The Dude" from Big Lebowski...

Aww how cute! You want to pretend to be a movie character!  

> Reply from Tydeus ↑Fri May 17, 2019 8:06 am at Fri May 17, 2019 8:06 am
>
> I get it, you feel backed into a corner

Again, you're confused "Dude", very confused! I don't feel backed into anything, least of all any corners, or your pathetic failed attempts to be offensive:

> Reply from Tydeus ↑Fri May 17, 2019 8:06 am at Fri May 17, 2019 8:06 am
>
> you where being a little bitch about it.

I was where??  (thanks for the laugh!) Such a brave little keyboard warrior aren't you? That took some courage for you to write that didn't it!

> Reply from Tydeus ↑Fri May 17, 2019 8:06 am at Fri May 17, 2019 8:06 am
>
> Your "good intentions" turned into insults so I commented.

You're a sensitive little lamb aren't you? What exactly did I write that was offensive? Offensive to who? You or the person that I wrote it to? Is Maximmum incapable of writing himself if he feels that he has been offended? Anyway, as you're so certain that Maximmum felt as wounded as you do about my comment, then perhaps you'd like to clarify exactly what it was that I said that was insulting to him?
## Post #693
- Username: Diatribal
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 20, 2010 7:48 pm
- Post datetime: 2019-05-17T08:10:30+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from sugarysyringe ↑Fri May 17, 2019 10:15 am at Fri May 17, 2019 10:15 am
>
> 
Instead of fighting, I have a question. Is there a way to separate UVs in blender or 3ds max? I'm porting the TWD:TFS models to MMD, and MMD struggles with transparency unless the hair mesh or whatever is split up into every possible section. Buuut the hair's uv is overlapping a lot, making it hard to do so.

You could try UVW Unwrap modifier in 3DS Max. Open UV Editor, select all polygons and select Mapping > Flatten Mapping... There are other options in the UV Editor which might help you separate the UV's into islands and group them.
## Post #694
- Username: Diatribal
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Apr 20, 2010 7:48 pm
- Post datetime: 2019-05-17T11:19:52+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Anyway, f'k all of this negativity, I only really intended to thank RandomTBush for all of his hard work and dedication to helping others out. I've been struggling to extract the models from BTTF for a while and RTB solved it within a few hours of me asking questions! Exceptionally cool!

Thanks again!
## Post #695
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-05-17T13:10:14+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Annie2 ↑Thu May 16, 2019 7:30 pm at Thu May 16, 2019 7:30 pm
>
> 
Diatribal wrote: ↑Thu May 16, 2019 2:49 pm
Maximmum wrote: ↑Wed May 15, 2019 4:16 pmNo he's actually wrong, as long as you don't have money from this game and release for free you won't be sued, i know lots of examples so don't worry and please release it, i'm now kind of hyped about it and would really love to play it))  
You don't hype up somebody about the game you make and then says you won't release it  


Perhaps if you're so willing to irresponsibly offer your "professional legal advice", you could explain your professional background or how you are so certain that a game developer could use intellectually protected, copyrighted material from another game studio?!! Please enlighten us to these "lots of examples" that you mention where a game studio or developer has used copyrighted assets from another studio, without permission, legally??? I am sorry, but I suspect that you don't know what you are talking about, at all. I also suspect that you're probably some irresponsible teenager/kid who is more "hyped" about playing an unreleased game than you are about the developer putting themselves at legal risk by releasing a game that uses copyrighted material!

I can't wait to hear of these examples of games that have been legally released, that use other copyrighted assets from other games, without permission!  


At this point I don't really know to believe who and to say who is right or wrong, but thanks guys for your advices, really. No need to get mad over it or anything, I don't want this to go from a question that I asked to a problem between you guys.

Anyway, have a good day

I'm gonna tell you this, just don't worry about this legal bullshit, only some particular devs care when you make a free game with their content, CAPCOM is a great example, but i would anyway love to see and play the game you are doing since it includes Clem =)
## Post #696
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-05-19T23:24:20+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Maximmum ↑Fri May 17, 2019 9:10 pm at Fri May 17, 2019 9:10 pm
>
> 
Annie2 wrote: ↑Thu May 16, 2019 7:30 pm
Diatribal wrote: ↑Thu May 16, 2019 2:49 pm


Perhaps if you're so willing to irresponsibly offer your "professional legal advice", you could explain your professional background or how you are so certain that a game developer could use intellectually protected, copyrighted material from another game studio?!! Please enlighten us to these "lots of examples" that you mention where a game studio or developer has used copyrighted assets from another studio, without permission, legally??? I am sorry, but I suspect that you don't know what you are talking about, at all. I also suspect that you're probably some irresponsible teenager/kid who is more "hyped" about playing an unreleased game than you are about the developer putting themselves at legal risk by releasing a game that uses copyrighted material!

I can't wait to hear of these examples of games that have been legally released, that use other copyrighted assets from other games, without permission!  


At this point I don't really know to believe who and to say who is right or wrong, but thanks guys for your advices, really. No need to get mad over it or anything, I don't want this to go from a question that I asked to a problem between you guys.

Anyway, have a good day 


I'm gonna tell you this, just don't worry about this legal bullshit, only some particular devs care when you make a free game with their content, CAPCOM is a great example, but i would anyway love to see and play the game you are doing since it includes Clem =)

I'm glad someone likes the idea of it . You can join the discord server of the game, only if you want to, there you will know when it releases and you can suggest more ideas if you have, just anything you have on your mind, we can discuss there 
[https://discordapp.com/invite/EbvYTEm](https://discordapp.com/invite/EbvYTEm)
## Post #697
- Username: Tecosaurus
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 25, 2019 5:08 pm
- Post datetime: 2019-05-20T04:32:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Has anybody gotten any luck with the walker textures? I'm able to import the models fine, but after using the QuickBMS script on the textures, the Diffuse materials just seem Deep Fried and unusable. 

Thanks!
## Post #698
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-05-20T08:33:14+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tecosaurus ↑Mon May 20, 2019 12:32 pm at Mon May 20, 2019 12:32 pm
>
> 
Has anybody gotten any luck with the walker textures? I'm able to import the models fine, but after using the QuickBMS script on the textures, the Diffuse materials just seem Deep Fried and unusable. 

Thanks!

what problem with texture? can i see?
## Post #699
- Username: Tecosaurus
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 25, 2019 5:08 pm
- Post datetime: 2019-05-20T11:04:06+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from fil1969 ↑Mon May 20, 2019 4:33 pm at Mon May 20, 2019 4:33 pm
>
> 
Tecosaurus wrote: ↑Mon May 20, 2019 12:32 pm
Has anybody gotten any luck with the walker textures? I'm able to import the models fine, but after using the QuickBMS script on the textures, the Diffuse materials just seem Deep Fried and unusable. 

Thanks!


what problem with texture? can i see?

It's like they all have a really intense red filter. Here are a couple examples [https://imgur.com/a/8siqhUU](https://imgur.com/a/8siqhUU)
## Post #700
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2019-05-20T12:26:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tecosaurus ↑Mon May 20, 2019 7:04 pm at Mon May 20, 2019 7:04 pm
>
> 
fil1969 wrote: ↑Mon May 20, 2019 4:33 pm
Tecosaurus wrote: ↑Mon May 20, 2019 12:32 pm
Has anybody gotten any luck with the walker textures? I'm able to import the models fine, but after using the QuickBMS script on the textures, the Diffuse materials just seem Deep Fried and unusable. 

Thanks!


what problem with texture? can i see?


It's like they all have a really intense red filter. Here are a couple examples https://imgur.com/a/8siqhUU

Looks like that's how they really are. The game uses this texture to color the walkers in-game, this might be a mask texture. Don't quote me on that though, but based on multiple games that I've extracted from, this seems to be the case.
## Post #701
- Username: Tecosaurus
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 25, 2019 5:08 pm
- Post datetime: 2019-05-20T23:28:41+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from meganmi ↑Mon May 20, 2019 8:26 pm at Mon May 20, 2019 8:26 pm
>
> 
Tecosaurus wrote: ↑Mon May 20, 2019 7:04 pm
fil1969 wrote: ↑Mon May 20, 2019 4:33 pm


what problem with texture? can i see?


It's like they all have a really intense red filter. Here are a couple examples https://imgur.com/a/8siqhUU


Looks like that's how they really are. The game uses this texture to color the walkers in-game, this might be a mask texture. Don't quote me on that though, but based on multiple games that I've extracted from, this seems to be the case.

I figured it must have been intentional to some extent. Mask texture does make sense though, thanks for shedding some light on this!
## Post #702
- Username: thongTk
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun May 07, 2017 3:26 pm
- Post datetime: 2019-05-21T02:00:48+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

anyone have a clue as to how they blend textures?
for instance this is the default textures without the other texture blending over it:

where this is the intended look from the game:


they do this for a lot of textures so if anyone has an idea i'd be greatful
## Post #703
- Username: Matryoshka
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 22, 2019 7:32 pm
- Post datetime: 2019-05-22T11:51:10+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

greetings. textures can't add to mesh automatically because this... all textures named just like that... what i'm doing wrong?   [](https://radikal.ru)
## Post #704
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-22T13:04:04+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Matryoshka ↑Wed May 22, 2019 7:51 pm at Wed May 22, 2019 7:51 pm
>
> greetings. textures can't add to mesh automatically because this... all textures named just like that... what i'm doing wrong?Huh, are most of the bones on a model properly named at least? If not, then you might not have the TelltaleHashDBs folder in the right location -- it should be in a folder location like this:

```
C:\Program Files\Autodesk\3ds Max 2010\Scripts
```

...well, based on whichever 3DS Max version you have and drive letters, of course. But yeah, if the folder is there, it should be able to parse the texture names just fine, it shouldn't be falling back to those hashed names like that. Perhaps I should make a revision to the script so that you can choose a folder to search in if it doesn't automatically find it somehow.

Or if it is, maybe try running 3DS Max as an administrator? Could be a dumb permissions issue.
## Post #705
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-05-24T19:09:18+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Did anyone else get this message from this random kid?

(I am posting here because I am sure a lot of people that wrote on this topic has received this message) 

DO NOT CLICK ON THE LINK IN THE MESSAGE, IT'S MOST LIKELY A IP GRABBER!!!!!!
## Post #706
- Username: Smolgreen
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 10, 2018 8:19 am
- Post datetime: 2019-05-27T16:02:29+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

could anyone link me to the tool that is used to get the game files to a format that the importer can read?
## Post #707
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-27T16:22:34+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Smolgreen ↑Tue May 28, 2019 12:02 am at Tue May 28, 2019 12:02 am
>
> could anyone link me to the tool that is used to get the game files to a format that the importer can read?All you need for that is [aluigi's "Telltale TTARCH files extractor/rebuilder"  program](https://aluigi.altervista.org/papers.htm#others), the files you'll need will be in the TTARCH archives with "txmesh" (models - *.D3DMESH / textures - *.D3DTX) and "data" (bone structures / *.SKL) as suffixes.

I'll go add the blowfish key for The Final Season into the first post, since I see the program hasn't been updated with it yet (the rest is all there by the looks of it).
## Post #708
- Username: srdrabx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 25, 2019 2:31 am
- Post datetime: 2019-05-27T16:30:31+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Tue May 28, 2019 12:22 am at Tue May 28, 2019 12:22 am
>
> 
All you need for that is aluigi's "Telltale TTARCH files extractor/rebuilder"  program, the files you'll need will be in the TTARCH archives with "txmesh" (models / textures) and "data" (bone structures) as suffixes.

I'll go add the blowfish keys for The Final Season into the first post in a moment, since I see the program hasn't been updated with it yet (the rest is all there by the looks of it).

But you also have to convert them to .DDS, right?
## Post #709
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-27T16:32:17+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from srdrabx ↑Tue May 28, 2019 12:30 am at Tue May 28, 2019 12:30 am
>
> But you also have to convert them to .DDS, right?Yeah, the program doesn't do so automatically, so just use the QuickBMS scripts I have for those in the first post. As I mentioned earlier, I'll give 'em some polishing sometime later to work better (with TFS especially).
## Post #710
- Username: Ariclue
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 31, 2019 2:50 am
- Post datetime: 2019-05-30T18:53:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I can't seem to extract the textures with from one of the files (obj_pianoBench.d3dmesh) with QuickBMS.
It gives me this error message:

```
       Can't read 1 bytes from offset 656d645b.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0     0%   32         40578      . offset 656d645b

Last script line before the error or that produced the error:
  27  get flag byte
```


I don't know what to do here, any help would be appreciated.


Thanks in advance,
-Ari
## Post #711
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-30T20:10:54+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Ariclue ↑Fri May 31, 2019 2:53 am at Fri May 31, 2019 2:53 am
>
> I can't seem to extract the textures with from one of the files (obj_pianoBench.d3dmesh) with QuickBMS.
It gives me this error message:

*code snip*

I don't know what to do here, any help would be appreciated.


Thanks in advance,
-AriThe script only works with D3DTX files, not D3DMESH files (those ones are the models, not the textures). Unfortunately I can't add anything to the script to tell the difference, so it's best to separate those into a separate folder first before batch-converting them.
## Post #712
- Username: Ariclue
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 31, 2019 2:50 am
- Post datetime: 2019-05-30T20:15:05+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Fri May 31, 2019 4:10 am at Fri May 31, 2019 4:10 am
>
> 
Ariclue wrote: ↑Fri May 31, 2019 2:53 amI can't seem to extract the textures with from one of the files (obj_pianoBench.d3dmesh) with QuickBMS.
It gives me this error message:

*code snip*

I don't know what to do here, any help would be appreciated.


Thanks in advance,
-AriThe script only works with D3DTX files, not D3DMESH files (those ones are the models, not the textures). Unfortunately I can't add anything to the script to tell the difference, so it's best to separate those into a separate folder first before batch-converting them.

I managed to get the model into 3DS Max, though it doesn't have any textures.. I found the same file in the extracted data folder but it has the .PROP format. Is there anything I could do with that?
## Post #713
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-30T21:40:18+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Ariclue ↑Fri May 31, 2019 4:15 am at Fri May 31, 2019 4:15 am
>
> I managed to get the model into 3DS Max, though it doesn't have any textures.. I found the same file in the extracted data folder but it has the .PROP format. Is there anything I could do with that?The PROP files aren't necessary for importing models (and I never did check through 'em to see if there was anything useful). Check the Asset Tracking window (in File > Manage/Reference, but the shortcut is Shift+T), check to see where the textures are being read from and what their filenames are (click the Refresh button if nothing shows up). They should be located in the same folder as the D3DMESH file(s) you imported (or a "Textures" subfolder if the respective option was changed), and have a proper filename instead of an 8-letter jumble.
## Post #714
- Username: Ariclue
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 31, 2019 2:50 am
- Post datetime: 2019-05-30T21:47:40+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Fri May 31, 2019 5:40 am at Fri May 31, 2019 5:40 am
>
> 
Ariclue wrote: ↑Fri May 31, 2019 4:15 amI managed to get the model into 3DS Max, though it doesn't have any textures.. I found the same file in the extracted data folder but it has the .PROP format. Is there anything I could do with that?The PROP files aren't necessary for importing models (and I never did check through 'em to see if there was anything useful). Check the Asset Tracking window (in File > Manage/Reference, but the shortcut is Shift+T), check to see where the textures are being read from and what their filenames are (click the Refresh button if nothing shows up). They should be located in the same folder as the D3DMESH file(s) you imported (or a "Textures" subfolder if the respective option was changed), and have a proper filename instead of an 8-letter jumble.

This is what it shows me: (File Missing)
## Post #715
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-31T00:30:14+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

*sigh* Script update.

```
Added a failsafe should the hash databases not be in the expected folder.
```

[https://mega.nz/#!Gs4khKqT!I_Le6211gRCo ... 7KBEougLsM](https://mega.nz/#!Gs4khKqT!I_Le6211gRCoTwGIaShA0TMeHgRP9-EX57KBEougLsM)

Try this. 

> Reply from thongTk ↑Tue May 21, 2019 10:00 am at Tue May 21, 2019 10:00 am
>
> anyone have a clue as to how they blend textures?
for instance this is the default textures without the other texture blending over it:
*image 1*
where this is the intended look from the game:
*image 2*

they do this for a lot of textures so if anyone has an idea i'd be greatfulSince I missed this earlier, I'm sure that some of the other hashes used with the materials (of which only one is used for the diffuse currently) are meant for additional UV mapping layers (which are merged with their respective meshes), but I haven't been able to determine which ones yet. I might have some time again later to give it a look-over, see if it's something I can implement.
## Post #716
- Username: Ariclue
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 31, 2019 2:50 am
- Post datetime: 2019-05-31T01:17:31+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Fri May 31, 2019 8:30 am at Fri May 31, 2019 8:30 am
>
> 
*sigh* Script update.
Code: Select allAdded a failsafe should the hash databases not be in the expected folder.
https://mega.nz/#!Gs4khKqT!I_Le6211gRCo ... 7KBEougLsM

Try this. 
thongTk wrote: ↑Tue May 21, 2019 10:00 amanyone have a clue as to how they blend textures?
for instance this is the default textures without the other texture blending over it:
*image 1*
where this is the intended look from the game:
*image 2*

they do this for a lot of textures so if anyone has an idea i'd be greatfulSince I missed this earlier, I'm sure that some of the other hashes used with the materials (of which only one is used for the diffuse currently) are meant for additional UV mapping layers (which are merged with their respective meshes), but I haven't been able to determine which ones yet. I might have some time again later to give it a look-over, see if it's something I can implement.

Thank you, that worked! I really appreciate it.
## Post #717
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-05-31T01:26:40+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Ariclue ↑Fri May 31, 2019 9:17 am at Fri May 31, 2019 9:17 am
>
> Thank you, that worked! I really appreciate it.Ah, good! Glad it seemed to be a simple fix.
## Post #718
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2019-06-01T07:58:06+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hey RTB, your .bms script for textures doesn't seem to work on these three textures. (It gives out an error.) 

[https://mega.nz/#!0EoVFYjJ!DuXRhq3ShsD_ ... 0oUasQKo4Q](https://mega.nz/#!0EoVFYjJ!DuXRhq3ShsD_OaIciydU4I0FvHf1-Sb940oUasQKo4Q)
## Post #719
- Username: GrimTheReaper92
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 05, 2019 8:40 pm
- Post datetime: 2019-06-05T13:00:58+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hi Everyone,
Quick question to everyone.
There is a way to export animation to with Characters model?
Thanks!
## Post #720
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-06-06T06:43:37+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from GrimTheReaper92 ↑Wed Jun 05, 2019 9:00 pm at Wed Jun 05, 2019 9:00 pm
>
> 
Hi Everyone,
Quick question to everyone.
There is a way to export animation to with Characters model?
Thanks!

I asked this question before, since nobody replied, I don't think it's possible to do this yet. Only RandomTBrush can have a answer to this, you'll have to wait until the man himself replies.
## Post #721
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-06-06T06:45:21+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Here's a picture of the Clementine that will be in the game that I am working, it's not the complete version.

Once it appears in the game, credits will be given to Telltale and RandomTBush. (No money will be made of this)






When adding the ink, it wasn't 100% the same as on the original game. So I opened the file in photoshop and only selected the white areas and left all the black and a bit of the grey areas out:





After doing this, it looked pretty similar to the original one you see in the game, you can do this with all the other ink textures.
## Post #722
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-06-06T16:29:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

looks like she fell into a barrel of ash!
## Post #723
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-06-06T21:23:03+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from GrimTheReaper92 ↑Wed Jun 05, 2019 9:00 pm at Wed Jun 05, 2019 9:00 pm
>
> Hi Everyone,
Quick question to everyone.
There is a way to export animation to with Characters model?
Thanks!I've already answered this before, so I'll just quote what I said earlier:

> Reply from RandomTBush ↑Sat Feb 11, 2017 5:35 am at Sat Feb 11, 2017 5:35 am
>
> 
jayko wrote:Maximmum wrote:Hi RandomTBush i want to ask you a question, is it possible to somehow export Animations from telltale games(i mean .anm and .chore files), it would be really awesome if you add "Export Animation" to your script!

As amazing as that would be, I think exporting animations is an entirely different ballgame to models and textures. But that's just my basic understanding - you'd have to hear confirmation from the man himself.Precisely. I have absolutely no knowledge as to how to read animations, let alone set up 3DS Max's keyframing and such through the MaxScript, so right now I won't be able to do that.
## Post #724
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2019-06-08T17:34:32+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Annie2 ↑Thu Jun 06, 2019 2:45 pm at Thu Jun 06, 2019 2:45 pm
>
> 
Here's a picture of the Clementine that will be in the game that I am working, it's not the complete version.

Once it appears in the game, credits will be given to Telltale and RandomTBush. (No money will be made of this)






When adding the ink, it wasn't 100% the same as on the original game. So I opened the file in photoshop and only selected the white areas and left all the black and a bit of the grey areas out:





After doing this, it looked pretty similar to the original one you see in the game, you can do this with all the other ink textures.

I can't wait to try that game out, hope you will release it publicly!
## Post #725
- Username: DioBrando
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 06, 2010 11:59 am
- Post datetime: 2019-06-13T01:49:57+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

3575478484.JPG (86.03 KiB) Viewed 265 times


Does anyone know why when I export to Maya from 3ds Max some of the skinning is messed up? Like a few verts didn't get bound at all. I tried it in Maya 2016 and 2018 and got the same.
## Post #726
- Username: Annie2
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 09, 2019 8:40 am
- Post datetime: 2019-06-13T20:06:02+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from DioBrando ↑Thu Jun 13, 2019 9:49 am at Thu Jun 13, 2019 9:49 am
>
> 
3575478484.JPG
Does anyone know why when I export to Maya from 3ds Max some of the skinning is messed up? Like a few verts didn't get bound at all. I tried it in Maya 2016 and 2018 and got the same.

Have you exported it as .FBX and opened in maya? If yes and this happened, maybe try exporting as another 3d format, and see how it goes with those. Because this happened once to me and I exported as another 3d format, and it worked fine after that.
## Post #727
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2019-06-15T18:41:53+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

There are direct scene transfer available [Max<>Maya](https://knowledge.autodesk.com/support/3ds-max/learn-explore/caas/sfdcarticles/sfdcarticles/Transfering-a-3ds-Max-scene-to-Maya-and-vice-versa.html).
## Post #728
- Username: srdrabx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 25, 2019 2:31 am
- Post datetime: 2019-06-26T09:55:49+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Is there any way to use .anm files?
## Post #729
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-06-26T16:08:29+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from srdrabx ↑Wed Jun 26, 2019 5:55 pm at Wed Jun 26, 2019 5:55 pm
>
> Is there any way to use .anm files?No, this was answered literally a few posts ago, on this same page.

> Reply from RandomTBush ↑Fri Jun 07, 2019 5:23 am at Fri Jun 07, 2019 5:23 am
>
> 
GrimTheReaper92 wrote: ↑Wed Jun 05, 2019 9:00 pmHi Everyone,
Quick question to everyone.
There is a way to export animation to with Characters model?
Thanks!I've already answered this before, so I'll just quote what I said earlier:
RandomTBush wrote: ↑Sat Feb 11, 2017 5:35 am
jayko wrote:

As amazing as that would be, I think exporting animations is an entirely different ballgame to models and textures. But that's just my basic understanding - you'd have to hear confirmation from the man himself.Precisely. I have absolutely no knowledge as to how to read animations, let alone set up 3DS Max's keyframing and such through the MaxScript, so right now I won't be able to do that.
## Post #730
- Username: ThePlayaJam765
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 19, 2019 9:17 pm
- Post datetime: 2019-07-19T13:24:32+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

So, I was importing some models from Minecraft: Story Mode from both seasons.

All Season One models import correctly.

Most Season Two models import correctly, but some of them come up with an error saying:



I have very little knowledge of 3DS Max in general. (In the past, I always used Blender or Cinema 4d, but I downloaded 3DS Max specifically to use this script) However, details that I can provide is that I am using 3DS Max 2020.

Any help would be appreciated.
## Post #731
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-07-19T14:26:40+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from ThePlayaJam765 ↑Fri Jul 19, 2019 9:24 pm at Fri Jul 19, 2019 9:24 pm
>
> 
So, I was importing some models from Minecraft: Story Mode from both seasons.

All Season One models import correctly.

Most Season Two models import correctly, but some of them come up with an error saying:

*image*

I have very little knowledge of 3DS Max in general. (In the past, I always used Blender or Cinema 4d, but I downloaded 3DS Max specifically to use this script) However, details that I can provide is that I am using 3DS Max 2020.

Any help would be appreciated.Yeah, I'm aware of that issue (I accidentally caused it by not fully testing material importing for that game specifically, oops!), hopefully I'll have some time to work on a fix for that in the next few days.
## Post #732
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-08-09T20:56:27+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I found a rigging error with Season 2 Kenny’s model from The Walking Dead Collection where if you rotate its leg_l bone and leg_r bone, the shoes have this error.
## Post #733
- Username: chjkjjk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 12, 2019 4:12 pm
- Post datetime: 2019-08-12T08:15:13+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

could someone please tell me how this works? i don't have any program to open the .bms/.ms files with. i just found out about this forum from a reddit post where there was louis' letter to clem and i thought it was interesting
## Post #734
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-08-12T10:33:47+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from chjkjjk ↑Mon Aug 12, 2019 4:15 pm at Mon Aug 12, 2019 4:15 pm
>
> 
could someone please tell me how this works? i don't have any program to open the .bms/.ms files with. i just found out about this forum from a reddit post where there was louis' letter to clem and i thought it was interesting

for BMS you need Aluigi QuickBMS extractor
[https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)

MS are  Autodesk 3ds Max scripts, you need 3dMax in order to open them.
## Post #735
- Username: Ariclue
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 31, 2019 2:50 am
- Post datetime: 2019-08-20T20:19:11+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

For some reason, extracting the textures for the KnifeKABAR doesn't work with QuickBMS though all previous textures I tried extracting did.
## Post #736
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-08-20T20:25:39+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

It's not much of an issue imo, but I've found that the Season 4 Dorm map floor's UV Map or something is a bit dodgy towards the main enterance. By dodgy I mean it just stops trying to texture completely. Though it's not an issue because the Episode 4 version of the map works pretty fine so I'm just using that.

I didnt realise how boring season 4 was until I started working on the maps lol.
## Post #737
- Username: Tomasseligmann
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 07, 2019 11:12 am
- Post datetime: 2019-09-07T03:14:48+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hello! I am completely new at this and I'm trying to get a hand at the Jurassic Park the Game models and I have no idea how to use this software, can anyone pleas be kind enough to guide me in what to do??? THANK YOU!
## Post #738
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-09-09T17:17:36+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Is anyone excited for The Walking Dead: The Telltale Definitive Series?
## Post #739
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-09-09T17:32:34+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12 ↑Tue Sep 10, 2019 1:17 am at Tue Sep 10, 2019 1:17 am
>
> Is anyone excited for The Walking Dead: The Telltale Definitive Series?Not really, no, there's nothing new added other than the season 4 comic style. This entire thing is just to make money back on what they lost bailing out Telltale for the final season. We've had way too many rereleases with hardly anything added to it!

A few people have had early releases already and it's full of bugs, like characters not having their detail lines added or the season 4 comic filter not being applied lol
## Post #740
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-09-09T17:42:18+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Tue Sep 10, 2019 1:32 am at Tue Sep 10, 2019 1:32 am
>
> 
Escope12 wrote: ↑Tue Sep 10, 2019 1:17 amIs anyone excited for The Walking Dead: The Telltale Definitive Series?Not really, no, there's nothing new added other than the season 4 comic style. This entire thing is just to make money back on what they lost bailing out Telltale for the final season. We've had way too many rereleases with hardly anything added to it!

A few people have had early releases already and it's full of bugs, like characters not having their detail lines added or the season 4 comic filter not being applied lol

Do you think people are gonna boycott it?
## Post #741
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-09-09T17:49:24+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12 ↑Tue Sep 10, 2019 1:42 am at Tue Sep 10, 2019 1:42 am
>
> 
Tydeus wrote: ↑Tue Sep 10, 2019 1:32 am
Escope12 wrote: ↑Tue Sep 10, 2019 1:17 amIs anyone excited for The Walking Dead: The Telltale Definitive Series?Not really, no, there's nothing new added other than the season 4 comic style. This entire thing is just to make money back on what they lost bailing out Telltale for the final season. We've had way too many rereleases with hardly anything added to it!

A few people have had early releases already and it's full of bugs, like characters not having their detail lines added or the season 4 comic filter not being applied lol


Do you think people are gonna boycott it?Of course not, people are going to buy Walking Dead games no matter who makes it. Basically everybody in the Walking Dead game reddit page are buying it regardless. My only interest in it at this point would be the models simply because I already own the games, maybe 3 versions of the games with very little difference. lol

Also to be fairly honest, I didnt really like Clementine's story, I was hoping we'd move on from her a whole lot sooner, like a good cutoff point would've been her safety at Wellington.
## Post #742
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-09-09T19:54:31+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I'm not sure if it's been posted here before but the Telltale Explorer updated earlier this year if anybody is interested. It just saves time if you're wanting one model.

[https://quickandeasysoftware.net/new-ve ... r-released](https://quickandeasysoftware.net/new-version-of-telltale-explorer-released)
## Post #743
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-09-09T20:08:29+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Tue Sep 10, 2019 1:49 am at Tue Sep 10, 2019 1:49 am
>
> 
Escope12 wrote: ↑Tue Sep 10, 2019 1:42 am
Tydeus wrote: ↑Tue Sep 10, 2019 1:32 am
Not really, no, there's nothing new added other than the season 4 comic style. This entire thing is just to make money back on what they lost bailing out Telltale for the final season. We've had way too many rereleases with hardly anything added to it!

A few people have had early releases already and it's full of bugs, like characters not having their detail lines added or the season 4 comic filter not being applied lol


Do you think people are gonna boycott it?Of course not, people are going to buy Walking Dead games no matter who makes it. Basically everybody in the Walking Dead game reddit page are buying it regardless. My only interest in it at this point would be the models simply because I already own the games, maybe 3 versions of the games with very little difference. lol

Also to be fairly honest, I didnt really like Clementine's story, I was hoping we'd move on from her a whole lot sooner, like a good cutoff point would've been her safety at Wellington.

Why didn’t you like Clementine’s story if you don’t mind me asking?
## Post #744
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2019-09-09T20:50:17+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12 ↑Tue Sep 10, 2019 4:08 am at Tue Sep 10, 2019 4:08 am
>
> Why didn’t you like Clementine’s story if you don’t mind me asking?She's a boring character and it was too much of the same thing, ending with more of the same thing where she finds a group and basically becomes the leader, but still has to literally do everything for everybody. They didnt add anything to the character at all other than "yep she can still take care of herself" lol.

If they did leave it at season 2, they could've followed Kenny, or Christa, or just follow Javier without needing the Clementine story, and season 4 could've finished with Javier
## Post #745
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-09-11T14:52:57+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Anyone know the blowfish key for the defintive series (key to ttarch extract)? How can we unlock this one and who to contact for more information?
## Post #746
- Username: Rapetacular
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 14, 2018 10:45 am
- Post datetime: 2019-09-12T05:46:22+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12 ↑Wed Sep 11, 2019 10:52 pm at Wed Sep 11, 2019 10:52 pm
>
> 
Anyone know the blowfish key for the defintive series (key to ttarch extract)? How can we unlock this one and who to contact for more information?

I second this, I think a lot of folks are in dire need for it. I gots a mission to uphold!   
So far extracting stuff from the previous game has been a breeze (Thanks RandomTBush!)
## Post #747
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2019-09-12T15:59:59+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12 ↑Wed Sep 11, 2019 10:52 pm at Wed Sep 11, 2019 10:52 pm
>
> 
Anyone know the blowfish key for the defintive series (key to ttarch extract)? How can we unlock this one and who to contact for more information?

Here ya go.

```
96CA999F8DDA9A87D7CDD9BB93D1BEC0D79171DC9ED98DD0D18CD8C3A0B0C695C39C93BBCCCCA7D3B9D9D9D08E93BEDAAED18D77D5D3A3
```
## Post #748
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-09-12T16:41:37+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from meganmi ↑Thu Sep 12, 2019 11:59 pm at Thu Sep 12, 2019 11:59 pm
>
> 
Escope12 wrote: ↑Wed Sep 11, 2019 10:52 pm
Anyone know the blowfish key for the defintive series (key to ttarch extract)? How can we unlock this one and who to contact for more information?


Here ya go.
Code: Select all96CA999F8DDA9A87D7CDD9BB93D1BEC0D79171DC9ED98DD0D18CD8C3A0B0C695C39C93BBCCCCA7D3B9D9D9D08E93BEDAAED18D77D5D3A3

Thanks but how do I use this?
## Post #749
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-09-13T03:20:24+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Well, looks like despite the Definitive Edition models using v55 again (same version as Final Season, naturally), they still changed things around just enough that I'm going to have to fix it. Jeez, how appropriate that even after their closure, Telltale still torments me in zombie form.

Plus, uh, I still gotta fix importing for Minecraft: Story Mode Season 2. Been slacking majorly there.
## Post #750
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2019-09-13T03:35:26+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Fri Sep 13, 2019 11:20 am at Fri Sep 13, 2019 11:20 am
>
> 
Well, looks like despite the Definitive Edition models using v55 again (same version as Final Season, naturally), they still changed things around just enough that I'm going to have to fix it. Jeez, how appropriate that even after their closure, Telltale still torments me in zombie form.

Plus, uh, I still gotta fix importing for Minecraft: Story Mode Season 2. Been slacking majorly there.

Did you know that Telltale Games is being revived by another company?
## Post #751
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2019-09-13T06:55:07+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12 ↑Fri Sep 13, 2019 12:41 am at Fri Sep 13, 2019 12:41 am
>
> 
Thanks but how do I use this?

```
ttarchext.exe -k 96CA999F8DDA9A87D7CDD9BB93D1BEC0D79171DC9ED98DD0D18CD8C3A0B0C695C39C93BBCCCCA7D3B9D9D9D08E93BEDAAED18D77D5D3A3 0 "input .ttarch2" "output folder"
```
## Post #752
- Username: inter9429
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 06, 2014 1:14 am
- Post datetime: 2019-09-26T22:18:56+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I have already translated all the games in the previous versions.  
How can I make translations for the final season work?
## Post #753
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-12-13T15:16:30+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

So The Wolf Among Us 2 was just re-announced last night. Man, the ride never ends, does it?

...That being said, I'm still alive! I would've had the update for my script fixing the MCSM2 / TWD Definitive models by now, but the past few months for me have been kinda disastrous. Hopefully I'll have it ready before the year's over!

(EDIT: ...and probably yet another Batman update by the sounds of it.)
## Post #754
- Username: dixen18
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 10, 2016 2:41 pm
- Post datetime: 2019-12-18T05:05:07+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Key for Batman The Telltale Series Shadows Edition, please
## Post #755
- Username: ThePlayaJam765
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 19, 2019 9:17 pm
- Post datetime: 2019-12-20T13:03:53+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Fri Dec 13, 2019 11:16 pm at Fri Dec 13, 2019 11:16 pm
>
> 
So The Wolf Among Us 2 was just re-announced last night. Man, the ride never ends, does it?

...That being said, I'm still alive! I would've had the update for my script fixing the MCSM2 / TWD Definitive models by now, but the past few months for me have been kinda disastrous. Hopefully I'll have it ready before the year's over!

(EDIT: ...and probably yet another Batman update by the sounds of it.)

Glad to hear it.

(BTW, I'm using the older version of the script, the one without automatic material importing as a workaround for now until you can fix the current script on that issue.)
## Post #756
- Username: thongTk
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun May 07, 2017 3:26 pm
- Post datetime: 2020-04-04T11:20:46+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Is the script for the definitive edition still being worked on?
## Post #757
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-04-04T18:09:31+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from thongTk ↑Sat Apr 04, 2020 7:20 pm at Sat Apr 04, 2020 7:20 pm
>
> Is the script for the definitive edition still being worked on?Yeah, I still have plans to work on that.
## Post #758
- Username: Bleech
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 17, 2020 1:26 am
- Post datetime: 2020-04-17T15:17:27+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

@RandomTBush Just to let you know, on your QuickBMS script to extract dds files from d3dtx files from MCSM S2 and some others, at the top of the file you said there was a problem with it and it didnt load and I tried and yeah it didnt. But I went through your quick BMS code and made some changed and put it into java (Im loading mesh and textures into minecraft which is in java), but for some reason it imports and works in java so If you want me to send you the java code maybe you could see the difference and fix it (the problem was importing atlas and gobo).

Also could you please tell me how you find out all of the hash offsets in the mesh files? Like how did you find out the format and the process you did to do that
## Post #759
- Username: junminlee2004
- Rank: n00b
- Number of posts: 13
- Joined date: Fri May 08, 2020 3:08 am
- Post datetime: 2020-05-07T19:11:07+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I just want to ask a quick question, how do you import both the textures and the texture details into the models? I can currently only import textures.
## Post #760
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2020-06-03T17:31:06+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from junminlee2004 ↑Fri May 08, 2020 3:11 am at Fri May 08, 2020 3:11 am
>
> I just want to ask a quick question, how do you import both the textures and the texture details into the models? I can currently only import textures.

I dont know if there's a correct way to do it, but I just overlay the main textures with the details.
## Post #761
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2020-06-21T04:20:39+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hi guys. I made a little tutorial on how to fix the torso rigging error for the characters in 3ds Max from Telltale Games. 

Link to tutorial: [https://imgur.com/gallery/qimgqEB](https://imgur.com/gallery/qimgqEB)
## Post #762
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2020-06-21T21:33:28+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12 ↑Sun Jun 21, 2020 12:20 pm at Sun Jun 21, 2020 12:20 pm
>
> Hi guys. I made a little tutorial on how to fix the torso rigging error for the characters in 3ds Max from Telltale Games. 

Link to tutorial: https://imgur.com/gallery/qimgqEBThats not really an error is it? Usually bones in 3D Max doesnt move if connected to a root bone, removing the link to the root tends to break the model.

Just wondering though, I've been looking through the Final Season textures and all the zombie textures seem to be red, as if it was a mask texture, is there any way to fix this?

[](https://puu.sh/FYZ40/9e59a373af.png)
## Post #763
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2020-06-21T21:36:08+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Mon Jun 22, 2020 5:33 am at Mon Jun 22, 2020 5:33 am
>
> 
Escope12 wrote: ↑Sun Jun 21, 2020 12:20 pmHi guys. I made a little tutorial on how to fix the torso rigging error for the characters in 3ds Max from Telltale Games. 

Link to tutorial: https://imgur.com/gallery/qimgqEBThats not really an error is it? Usually bones in 3D Max doesnt move if connected to a root bone, removing the link to the root tends to break the model.

Just wondering though, I've been looking through the Final Season textures and all the zombie textures seem to be red, as if it was a mask texture, is there any way to fix this?

When I looked at it, the torso's were rigged to the "root" bone.
## Post #764
- Username: frostbone25
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 24, 2020 11:49 pm
- Post datetime: 2020-06-24T16:16:08+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sun Apr 05, 2020 2:09 am at Sun Apr 05, 2020 2:09 am
>
> 
thongTk wrote: ↑Sat Apr 04, 2020 7:20 pmIs the script for the definitive edition still being worked on?Yeah, I still have plans to work on that.

Hey @RandomTBush , I wanted to notify you the best I can (as a fellow programmer, but not in MaxScript though but I'll do my best) about an issue I stumbled upon when I wanted to import a mesh that is specific to the definitive edition (specifically the menu scene, with Clementine's house which I wanted to extract and prep for others to use just for fun). I'm aware you have plans on updating the script to work properly on definitive edition but you haven't posted any updates in a while.

Anyways, when importing a definitive edition specific mesh It seems like the script is struggling to parse the vertex buffer information from the d3dmesh file. At line 16437 in the script, specifically in 'Section 11C' (good thing you marked it because your script is awfully long), when it enters the switch statement 'MeshFlag1' it fails to hit any of the cases and defaults to your throw statement and of course the rest of the script is unable to proceed then since its unable to parse and set any values regarding the vertex buffer. My guess would be that in the definitive edition, the "MeshFlag1" values you are trying to parse have changed and it's unable to meet any of the cases, or the order in which the file is structured has changed where the data is and its unable to parse it then. I'm currently looking into it the best I can with my prior knowledge and seeing if I can solve it, and if I do ill be sure to let you know, but I wanted to let you know with as much info as I can provide about the issue so that you yourself can find it easily and solve it. Thank you!
## Post #765
- Username: frostbone25
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 24, 2020 11:49 pm
- Post datetime: 2020-06-24T19:11:48+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Note: I was able to get the meshes to import by getting rid of the 'throw' exceptions just by commenting them out just to see if the script would be able to import the mesh at all. It worked of course, but that was only a 'bandaid' on the issue and the meshes UV maps unfortunately are messed up, still looking into it though.
## Post #766
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-06-25T07:48:24+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from frostbone25 ↑Thu Jun 25, 2020 12:16 am at Thu Jun 25, 2020 12:16 am
>
> RandomTBush wrote: ↑Sun Apr 05, 2020 2:09 amthongTk wrote: ↑Sat Apr 04, 2020 7:20 pmIs the script for the definitive edition still being worked on?Yeah, I still have plans to work on that.


Hey @RandomTBush , I wanted to notify you the best I can (as a fellow programmer, but not in MaxScript though but I'll do my best) about an issue I stumbled upon when I wanted to import a mesh that is specific to the definitive edition (specifically the menu scene, with Clementine's house which I wanted to extract and prep for others to use just for fun). I'm aware you have plans on updating the script to work properly on definitive edition but you haven't posted any updates in a while.

Anyways, when importing a definitive edition specific mesh It seems like the script is struggling to parse the vertex buffer information from the d3dmesh file. At line 16437 in the script, specifically in 'Section 11C' (good thing you marked it because your script is awfully long), when it enters the switch statement 'MeshFlag1' it fails to hit any of the cases and defaults to your throw statement and of course the rest of the script is unable to proceed then since its unable to parse and set any values regarding the vertex buffer. My guess would be that in the definitive edition, the "MeshFlag1" values you are trying to parse have changed and it's unable to meet any of the cases, or the order in which the file is structured has changed where the data is and its unable to parse it then. I'm currently looking into it the best I can with my prior knowledge and seeing if I can solve it, and if I do ill be sure to let you know, but I wanted to let you know with as much info as I can provide about the issue so that you yourself can find it easily and solve it. Thank you!
> Reply from frostbone25 ↑Thu Jun 25, 2020 3:11 am at Thu Jun 25, 2020 3:11 am
>
> Note: I was able to get the meshes to import by getting rid of the 'throw' exceptions just by commenting them out just to see if the script would be able to import the mesh at all. It worked of course, but that was only a 'bandaid' on the issue and the meshes UV maps unfortunately are messed up, still looking into it though.Hooray for sloppy coding! I'll be sure to address this properly when I finally get time to work on the script again. Hopefully next month, if things don't go downhill again.
## Post #767
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2020-07-17T21:18:08+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Just wondering, did the model scale change between versions? I tend to go with scale 1 for some reason (I dunno) and adjust it in the program I use later, the old version used to be at my scale at 127.55, but the new version doesnt reach that until 3227.55

Also, how do I turn these textures "normal" ?
## Post #768
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-07-27T15:32:08+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Sat Jul 18, 2020 5:18 am at Sat Jul 18, 2020 5:18 am
>
> Just wondering, did the model scale change between versions? I tend to go with scale 1 for some reason (I dunno) and adjust it in the program I use later, the old version used to be at my scale at 127.55, but the new version doesnt reach that until 3227.55

Also, how do I turn these textures "normal" ?

*image*I don't think so, only thing I did was add a modifier and set it to 100 times scale (or "100.0") by default since they're difficult to work with in their original sizing. Other than that, it's likely caused by Max's unit scale having been changed at some point.

As for the textures, there's some kind of material blending going in there involving the red/green/blue channels. I'm not exactly sure what would need to be done to get those looking correct, but perhaps I can do some more thorough investigation into material properties later.

...

Anyway, me being the lazy slob that I am, instead of actually scripting stuff I decided to go back and improve upon the bone name hashes list instead. In the past few days I've added a whopping 5,649 more names (for comparison, the original list has 6,253), bringing it up to 11,902! Now most TWD Final Season characters for instance are only missing 4 bone names (one left/right pair for face bones, one left/right pair for hands). Whoo, progress! Finally!
## Post #769
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2020-07-27T16:23:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Mon Jul 27, 2020 11:32 pm at Mon Jul 27, 2020 11:32 pm
>
> 
Tydeus wrote: ↑Sat Jul 18, 2020 5:18 amJust wonderingI don't think so, only thing I did was add a modifier and set it to 100 times scale (or "100.0") by default since they're difficult to work with in their original sizing. Other than that, it's likely caused by Max's unit scale having been changed at some point.Ah, it's probably down to the FBX measurement thing, it's currently on inches, I dont remember if I used anything else.

> Reply from RandomTBush ↑Mon Jul 27, 2020 11:32 pm at Mon Jul 27, 2020 11:32 pm
>
> Anyway, me being the lazy slob that I am, instead of actually scripting stuff I decided to go back and improve upon the bone name hashes list instead.Thats awesome! Although that would mean redoing all of the telltale models I have lol

I've been meaning to redo season 1 and 2 anyway
## Post #770
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-07-27T17:18:39+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Tue Jul 28, 2020 12:23 am at Tue Jul 28, 2020 12:23 am
>
> RandomTBush wrote: ↑Mon Jul 27, 2020 11:32 pmAnyway, me being the lazy slob that I am, instead of actually scripting stuff I decided to go back and improve upon the bone name hashes list instead.Thats awesome! Although that would mean redoing all of the telltale models I have lol

I've been meaning to redo season 1 and 2 anywayIf you want the proper bone names for everything, perhaps. 

Thankfully there aren't a whole lot of characters left in Season 1/2 that are missing bone names now, I'll see about finding the rest of those in due time (there's about 30 left in S1 and 26 in S2, with most of those belonging to the zombies' faces). In the meantime, if you want to see some of the work I've done already regarding the bone names, you can replace the BoneNames.HashDB file with this one: [https://mega.nz/file/78I2kagK#wfwFAt8g9 ... qOBxS4h6yQ](https://mega.nz/file/78I2kagK#wfwFAt8g9wfZWU7xkCyzZ_XcafRQuNy-GqOBxS4h6yQ) .

(EDIT: Found the two hand bones -- "wristAttach_L" and "wristAttach_R"! I've updated the hash list with the new names, plus a few others.)
## Post #771
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2020-07-27T18:22:41+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Tue Jul 28, 2020 1:18 am at Tue Jul 28, 2020 1:18 am
>
> If you want the proper bone names for everything, perhaps.thanks dude  how are you doing it? renaming them one by one? or is there like a system or something?

I think I might rename some of them I have manually probably Michonne onwards. I've been wanting to do S1 and 2 again due to using a different exporting script that kinda shredded the mesh parts, it makes headhacks a little tricky lol.
## Post #772
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-07-27T18:39:02+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Tue Jul 28, 2020 2:22 am at Tue Jul 28, 2020 2:22 am
>
> RandomTBush wrote: ↑Tue Jul 28, 2020 1:18 amIf you want the proper bone names for everything, perhaps. thanks dude  how are you doing it? renaming them one by one? or is there like a system or something?

I think I might rename some of them I have manually probably Michonne onwards. I've been wanting to do S1 and 2 again due to using a different exporting script that kinda shredded the mesh parts, it makes headhacks a little tricky lol.daemon1 clued me in a while back that the texture and bone names used CRC64 hashes, so basically what I've been doing is keeping a list of all of the unknown hashes (there's approximately 4,600 remaining, with over a thousand of those being just from Game of Thrones), and throwing combinations of words and numbers together to see which ones end up being matches to said CRC64 hashes. It's definitely been successful for the most part, considering that the majority of the remaining names are for the props (which vary wildly in naming schemes) and not the characters (which follow similar naming patterns).

But yeah, next revision of the script definitely won't have the "shredded mesh parts" problem since I'm working on optimizing the outputs into a single mesh instead of individual polygon groups. But since I need to do so for each individual version setup, it's gonna take a bit still.
## Post #773
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2020-07-27T19:32:54+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Tue Jul 28, 2020 2:39 am at Tue Jul 28, 2020 2:39 am
>
> But yeah, next revision of the script definitely won't have the "shredded mesh parts" problem since I'm working on optimizing the outputs into a single mesh instead of individual polygon groups. But since I need to do so for each individual version setup, it's gonna take a bit still.Oh no by that I mean I used to use a 3ds to xna script in the past that made the mesh parts shredded, like you'd have part of the face and torso stuck together, or a leg and a hand, but I use fbx to export with and it exports how it appears in 3ds so it's fine really.

Oh I almost forgot, TWD season 4's Zombie400_zombieA to J doesnt seem to load for me, just wondering if it's a problem on my end or not
## Post #774
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-07-27T19:57:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Tue Jul 28, 2020 3:32 am at Tue Jul 28, 2020 3:32 am
>
> 
RandomTBush wrote: ↑Tue Jul 28, 2020 2:39 amBut yeah, next revision of the script definitely won't have the "shredded mesh parts" problem since I'm working on optimizing the outputs into a single mesh instead of individual polygon groups. But since I need to do so for each individual version setup, it's gonna take a bit still.Oh no by that I mean I used to use a 3ds to xna script in the past that made the mesh parts shredded, like you'd have part of the face and torso stuck together, or a leg and a hand, but I use fbx to export with and it exports how it appears in 3ds so it's fine really.

Oh I almost forgot, TWD season 4's Zombie400_zombieA to J doesnt seem to load for me, just wondering if it's a problem on my end or notAhhh, I see what you mean now.

And it seems like their models are working on my end, it just takes an awfully long time to import them (two-and-a-half minutes for one), particularly because their models have so many duplicated vertices (121,547 verts for zombieA, with only 20,788 being used). I'm hoping when I've got the script optimized that won't be an issue.

(EDIT: Got the last face bones! eyeCornerOuter_L and eyeCornerOuter_R!)
## Post #775
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-07-30T18:15:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Making good progress with bringing down the "unknown" bone names for characters now, grand total's now 12,157 (+255 compared to the first update). Just for fun, here's a breakdown of how many bone names are currently missing from each respective game (numbers are for characters / props respectively):

```
Batman - Season 1: The Telltale Series: 43 / 458
Batman - Season 2: The Enemy Within: 41 / 370
Game of Thrones: 29 / 1025 (!)
Guardians of the Galaxy: 67 / 246
Jurassic Park: 57 / 44
Law & Order Legacies: 33 / 2
Minecraft: Story Mode - Season 1: 114 / 300
Minecraft: Story Mode - Season 2: 53 / 18
Poker Night 2: 24 / 46
Tales from the Borderlands: 23 / 539
The Walking Dead - Michonne: 21 / 242
The Walking Dead - Season 1: 12 / 202
The Walking Dead - Season 2: 6 / 26
The Walking Dead - Season 3: A New Frontier: 33 / 99
The Walking Dead - The Final Season: 12 / 86
The Wolf Among Us: 99 / 235
```


The props are obviously not on a high priority, because good lord look at how many of those some of the games have.

(EDIT: Updated the totals like I did in my later post.)
## Post #776
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2020-07-30T18:31:38+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Damn thats fast work 

The props do repeat a lot too between seasons (probably), the bone names for those arent really that important to me at least, but character bones make it easy to save and load poses
## Post #777
- Username: daniar23337
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 31, 2020 9:38 am
- Post datetime: 2020-07-31T01:53:52+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

1. how do I export models that don't have .skl file?(Buildings, props, etc.)
2. How do I port an fbx format model to d3dmesh?
## Post #778
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-07-31T02:31:44+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from daniar23337 ↑Fri Jul 31, 2020 9:53 am at Fri Jul 31, 2020 9:53 am
>
> 1. how do I export models that don't have .skl file?(Buildings, props, etc.)
2. How do I port an fbx format model to d3dmesh?1. Just select the model(s) you want to import, then when it asks for a .SKL file just cancel and it'll import without it.
2. There's too many unknown values in the D3DMesh format to be able to make a model exporter, that's something I won't be able to do unfortunately.
## Post #779
- Username: daniar23337
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 31, 2020 9:38 am
- Post datetime: 2020-08-01T00:51:40+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Fri Jul 31, 2020 10:31 am at Fri Jul 31, 2020 10:31 am
>
> 
daniar23337 wrote: ↑Fri Jul 31, 2020 9:53 am1. how do I export models that don't have .skl file?(Buildings, props, etc.)
2. How do I port an fbx format model to d3dmesh?1. Just select the model(s) you want to import, then when it asks for a .SKL file just cancel and it'll import without it.
2. There's too many unknown values in the D3DMesh format to be able to make a model exporter, that's something I won't be able to do unfortunately.
[https://youtu.be/y5QMDZsYy94](https://youtu.be/y5QMDZsYy94)
nothing is happening
## Post #780
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2020-08-01T03:01:41+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from daniar23337 ↑Sat Aug 01, 2020 8:51 am at Sat Aug 01, 2020 8:51 am
>
> https://youtu.be/y5QMDZsYy94
nothing is happeningI'm curious, does the same thing happen when you try loading a model that has an skl file?

I'm not sure if it's a thing at all but maybe the script needs to be inside the 3ds max script folder?
## Post #781
- Username: daniar23337
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 31, 2020 9:38 am
- Post datetime: 2020-08-01T19:54:15+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Sat Aug 01, 2020 11:01 am at Sat Aug 01, 2020 11:01 am
>
> 
daniar23337 wrote: ↑Sat Aug 01, 2020 8:51 amhttps://youtu.be/y5QMDZsYy94
nothing is happening
I'm curious, does the same thing happen when you try loading a model that has an skl file?

I'm not sure if it's a thing at all but maybe the script needs to be inside the 3ds max script folder?

if i port with a bone, everything works
## Post #782
- Username: daniar23337
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 31, 2020 9:38 am
- Post datetime: 2020-08-01T20:15:50+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Sat Aug 01, 2020 11:01 am at Sat Aug 01, 2020 11:01 am
>
> 
daniar23337 wrote: ↑Sat Aug 01, 2020 8:51 amhttps://youtu.be/y5QMDZsYy94
nothing is happening
I'm curious, does the same thing happen when you try loading a model that has an skl file?

I'm not sure if it's a thing at all but maybe the script needs to be inside the 3ds max script folder?

please note if i port characters that have bones,but do not select the sql file,then they are ported
## Post #783
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-08-02T02:12:59+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

^ Okay, I think I have an idea as to what may be causing that, and I'll look into fixing it with the upcoming update.

----------

Anyway, I've added close to five thousand more bone names to the script, bringing the grand total to 17,571. And in the process I've got the first game with no missing bone hashes now! Where'd they come from? Well, there is one set of games that I haven't added support for yet. Here's the remaining counts for those:

```
CSI: Fatal Conspiracy: NONE MISSING!
Poker Night at the Inventory: 31 / 0
Sam & Max: The Devil's Playhouse: 167 / 71
Tales of Monkey Island: 53 / 177
Wallace & Gromit's Grand Adventures: 1/ 12
```

Now whether I'll be able to finally add importing support for those is another thing entirely...

(EDIT: And now I've gotten the last two for the other CSI game and another 200. Yay.)
(EDIT 2: I am an actual idiot and didn't realize Wallace & Gromit's bone names were in plaintext in the D3DMesh files. So yeah, there's a bunch right there that I added just from those, and the totals above updated.)
## Post #784
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-08-02T23:16:48+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from daniar23337 ↑Sat Aug 01, 2020 8:51 am at Sat Aug 01, 2020 8:51 am
>
> https://youtu.be/y5QMDZsYy94
nothing is happeningJust wanted to say that I found the source of this issue now, and it wasn't quite what I was expecting. The fix for this will be in the next update, but if you want to get 'em working ahead of time, do a search for:

```
if VerNum == 49 do (VerNum = 0)
```

and change that to:

```
if (VerNum == 48) or (VerNum == 49) do (VerNum = 0)
```


Turns out it was something I broke when I was adjusting auto-detection for "Version 0" models earlier -- I had the script check for "Version 49" models since that's the byte used in the headers for those where the version number would be in later revisions... but models without rigging (like the one in your video) use "48" for that instead, and it triggered the "Unknown version" catch which explains why they weren't importing. I've added a check for that (since it's safe to say "Version 48" was never used for any other games), it seems they're all working as intended now, with and without bones.
## Post #785
- Username: daniar23337
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 31, 2020 9:38 am
- Post datetime: 2020-08-03T06:23:05+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Thank you very much!:D [https://imgur.com/a/pdnUh0l](https://imgur.com/a/pdnUh0l)
## Post #786
- Username: daniar23337
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 31, 2020 9:38 am
- Post datetime: 2020-08-06T10:20:15+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

There is another problem:
There is a png texture next to the d3dmesh model,but it is not displayed in 3ds max
[https://youtu.be/6X_eQP0ZsGY](https://youtu.be/6X_eQP0ZsGY)

p. s Everything works fine on other models

UPD:Solved,im stupid
## Post #787
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2020-09-09T19:20:13+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I dont suppose there's any plans on a blender plugin is there? Does blender even do plugins?

Not that I need one, it's just incase 3ds max decides to bugger up.
## Post #788
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-10-17T05:04:50+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

This only took me an eternity ("an eternity" being roughly three months in duration):

> Reply from Changelog
>
> Added support for Strong Bad's Cool Game for Attractive People Episodes 2-5, and Wallace & Gromit's Grand Adventures Episodes 1-3. "Version 1" games are still unsupported though...
Added support for The Walking Dead: The Telltale Definitive Series models. Can you believe that the only reason they weren't working was because I had the script check the wrong mesh flags for The Final Season's importer? Go figure.
Script was tidied up a lot, shaving off about 100KB of redundant coding which is redundant (mainly due to the change below).
Models and materials are now grouped together and import as a single mesh group and Multi-Material respectively, greatly improving importing times.
Added over 10,000 new bone names to the hash database, and as a result most characters are no longer missing any bone names!
Added the texture names from Batman: Shadows Edition (both Season 1 and 2) and The Walking Dead: The Telltale Definitive Series to the hash database, along with a couple dozen missing (unused?) names.
Rearranged the texture hashes list so that "color_" names (specifically "color_000", used for "null" entries) are read first and lightmaps last, which speeds up texture-to-hash pairing significantly.
Textures used for material sets are now properly paired and print to the Listener window by default, and diffuse colors are automatically applied to the materials for earlier games (namely TWD Season 1).
Rewrote the way "Version 0" vertex buffers are read, now additional UV layers (mainly used for bake maps) will import instead of being skipped.
Fixed unrigged "Version 0" game models not importing due to a mistake in the script with automatic version-detection (Thanks, daniar23337!).
Fixed an issue where zero-length texture names (".d3dtx", seen in obj_c3nursebeds and obj_c5contractorpokertable in CSI 3) caused the script to get confused and error.
Fixed obj_chairLoungeB and sk80_pomPom having broken rigging in SBCG4AP Ep. 1 due to an issue with bone hash case-sensitivity ("pompom" != "pomPom").
Re-fixed models with single-bind rigging from The Walking Dead Season 1, which was accidentally broken since the May 11th, 2019 update.
Fixed "Version 12" models with ".PROP" information in their headers, now every model from Poker Night 2 is functional and imports without issues (60 were previously broken).
Fixed models with an invalid material ID not importing (i.e. "adv_previouslyOn204_hardwareStoreExteriorRearFoliageBrushA" from TWD Season 2).
Fixed a mistake with bone auto-detection for "Version 17" models (Game of Thrones's horse and most "skB0" models from Tales from the Borderlands).
Technically added support for "Version 38" models (TWD Season 3's "EOS" / "UpdatedMeshes" archives), which are practically identical to the "Version 37" format. Support is support, though.
Invalid / missing materials will now be listed as "undefined" so the script doesn't error (e.g. Minecraft Story Mode: Season 2 character models).
Fixed an oversight with "Version 45" models (Batman: The Enemy Within) with no UV mapping channels (e.g. various "fx_" models) which caused the script to crash.
Or tl;dr for the important stuff: Added support for SBCG4AP Episodes 2-5, Wallace & Gromit Episodes 1-3 (the last of the "Version 0" games, in other words) and The Walking Dead: The Telltale Definitive Series, plus Poker Night 2 now fully works and I optimized the crap out of things in general. Plus bugfixes, bugfixes, bugfixes, and did I mention bugfixes? But enough talk, enjoy!

[https://mega.nz/file/GoxUjDIK#eRNDzrWm8 ... Lh0LcK1do0](https://mega.nz/file/GoxUjDIK#eRNDzrWm8eYab7ezpgUqwSx62UFnOV_SELh0LcK1do0)
## Post #789
- Username: frostbone25
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 24, 2020 11:49 pm
- Post datetime: 2020-10-17T15:49:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hey, lovely job with the new update! I was sure it was dead but I geuss your still kicking  

I extracted and tried importing the menu map from the definitive edition and the UV maps are correct now! So nice to see that it works flawlessly. While preparing the map I noticed that there are still some several unknown hashes with this mesh. So during the process in which I relinked the textures back, I managed to match most of them with their respective ones. Here is the list of the texture hashes tied with the textures that I could match it with.

34d0e3a6 - env_branchAtlasA
80c071ab - obj_chairPlasticA
43d42360 - obj_sunshadeClemHouse
5287b73a - tile_trimWoodClemHouse404
71ec0e86 - env_clementineHouseInterior400TableChair_atlas
34f27f88 - env_clementineHouseInterior400MicrowaveSink_atlas
f491b2a0 - env_clementineHouseInterior400DoorAppliances_atlas
527fa55f - env_clementineHouseInterior400Furniture_atlas
13a1b3d0 - env_clementineHouseInterior400RugPlant_atlas
b944e4a9 - tile_clementineHouseInterior400KitchenTile
27ce3274 - tile_clementineHouseInterior400WallpaperStriped
e3606a53 - tile_clementineHouseInterior400KitchenWall
52318c25 - tile_clementineHouseInterior400KitchenFloor
49d8bc12 - env_clementineHouseInterior400PhotoFlower_atlas
44200b0d - env_clementineHouseInterior400CabinetArt_atlas
5287b73a - tile_trimWoodClemHouse404
97ba72d7 - tile_poolWallHorizontalBClemHouse
e21dc545 - env_treeLineA
634dad2c - tile_wallExteriorAClemHouse
434bd21a - tile_roadDamagedClemHouse
40f63afb - env_clementineHouseInterior400StairCounter_atlas
bfbe6ef- tile_poolWallHorizontalClemHouse

not 100% certain, but textures seem to match
d9e59a11 - tile_glassTruckForestShackA
33f1d874 - tile_concreteBrokenAClemHouse
c0d40cb3 - tile_groundGrassDeadC
8e7a796b - tile_trimMetalForestShackA
a167ba1 - tile_concreteBrokenCClemHouse
83bb32b - tile_groundGrassDeadA
## Post #790
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2020-10-17T16:52:29+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sat Oct 17, 2020 1:04 pm at Sat Oct 17, 2020 1:04 pm
>
> 
This only took me an eternity ("an eternity" being roughly three months in duration):
Changelog wrote:
Fixed "Version 12" models with ".PROP" information in their headers, now every model from Poker Night 2 is functional and imports without issues (60 were previously broken).I cant say I noticed any issues with the props from Poker Night 2, maybe some loaded without textures like the Jukebox but other than that I think I got everything out okay.

You're awesome  I bet you'll feel lost now that you've done everything lol.
## Post #791
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-10-17T21:16:45+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from frostbone25 ↑Sat Oct 17, 2020 11:49 pm at Sat Oct 17, 2020 11:49 pm
>
> I extracted and tried importing the menu map from the definitive edition and the UV maps are correct now! So nice to see that it works flawlessly. While preparing the map I noticed that there are still some several unknown hashes with this mesh. So during the process in which I relinked the textures back, I managed to match most of them with their respective ones. Here is the list of the texture hashes tied with the textures that I could match it with.

*files*D'oh! I think I know why. Were you manually assigning the texture hash database when you started up the script? I changed the name for the hash database a while back to "TexNames.HashDB" instead of being "vALLTex.HashDB" (a remnant from when I used to have those split on a per-version basis, which was a bad idea), and it turns out I forgot to update it for the manual lookup. Re-download the script and try it again, if it's reading the correct list then the Listener window should say the following:

```
"Texture hash total: 151245"
```


Because yeah, there shouldn't actually be a whole lot of models that are missing filenames (there's only five I found in The Final Season -- adv_boardingSchoolDorm_meshesAFloor, obj_hammer, obj_pianoKey, ui_constellation_capillium and ui_constellation_oculus), and I think whatever should actually be left over might not even exist in the first place.

> Reply from Tydeus ↑Sun Oct 18, 2020 12:52 am at Sun Oct 18, 2020 12:52 am
>
> I cant say I noticed any issues with the props from Poker Night 2, maybe some loaded without textures like the Jukebox but other than that I think I got everything out okay.

You're awesome  I bet you'll feel lost now that you've done everything lol.I'm guessing you somehow didn't import any of the broken models, heh. Here's a list of all of the ones that crashed the script previously:

```
fx_fogground.d3dmesh
fx_lightbeamdust.d3dmesh
fx_lightshaftadd.d3dmesh
fx_overlayeyesblink.d3dmesh
obj_buttondealer.d3dmesh
obj_cardpoker.d3dmesh
obj_celebritypokerroomexterior.d3dmesh
obj_celebritypokerroomexteriorgrate.d3dmesh
obj_chairpokerheavy.d3dmesh
obj_chairpokermax.d3dmesh
obj_chairpokerstrongbad.d3dmesh
obj_chairpokertycho.d3dmesh
obj_elevatorinventory.d3dmesh
obj_elevatorinventory_doorleft.d3dmesh
obj_elevatorinventory_doorright.d3dmesh
obj_fanblades.d3dmesh
obj_glasspokermartini.d3dmesh
obj_painting.d3dmesh
obj_shovelpoopsmith.d3dmesh
obj_signinventory.d3dmesh
ui_logoblocker.d3dmesh
ui_logoblocker_alpha.d3dmesh
ui_menusettings_volumeiconhigh.d3dmesh
ui_menusettings_volumeiconlow.d3dmesh
ui_menusettings_volumescroll.d3dmesh
ui_menusettings_volumeticker.d3dmesh
ui_menu_arrow.d3dmesh
ui_menu_background.d3dmesh
ui_menu_buttonplaygame.d3dmesh
ui_menu_buttonsettings.d3dmesh
ui_menu_pane.d3dmesh
ui_menu_rule.d3dmesh
ui_menu_settings_resolution.d3dmesh
ui_menu_tab.d3dmesh
ui_menu_title.d3dmesh
ui_player_background.d3dmesh
ui_player_button.d3dmesh
ui_player_buttonhelp.d3dmesh
ui_player_buttonhelpfiller.d3dmesh
ui_player_buttonraiseminus.d3dmesh
ui_player_buttonraiseplus.d3dmesh
ui_player_sidepotbubble.d3dmesh
ui_player_sidepotbubble_border.d3dmesh
ui_player_sidepot_icon.d3dmesh
ui_player_sliderbutton.d3dmesh
ui_player_slider_background.d3dmesh
ui_puzzleindex_scrollarrow.d3dmesh
ui_puzzleindex_scrollbar.d3dmesh
ui_puzzle_button.d3dmesh
ui_puzzle_buttonarrow.d3dmesh
ui_statisticstempbg.d3dmesh
ui_status_activeplayer.d3dmesh
ui_status_activeplayer_border.d3dmesh
ui_status_background.d3dmesh
ui_status_backgroundcardhand.d3dmesh
ui_status_border.d3dmesh
ui_status_iconsuit.d3dmesh
ui_status_showdownhandcorner.d3dmesh
ui_status_showdownhandmiddle.d3dmesh
```


And, well... not quite. There's a reason it's still an "Almost-All-in-One" script, I'm still struggling to figure out the mesh compression that's used with the "Version 1" games (Back to the Future's PC version, CSI 5 and 6, Poker Night 1, Sam & Max Season 3, Tales of Monkey Island and the fourth episode of Wallace & Gromit's Grand Adventures). I've actually got the backend for importing those games set up, so once I finally figure out how to decompress those correctly, then I'll have done everything.
## Post #792
- Username: frostbone25
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 24, 2020 11:49 pm
- Post datetime: 2020-10-18T00:38:00+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> D'oh! I think I know why. Were you manually assigning the texture hash database when you started up the script? @RandomTBush

Yeah I had to select the texture file manually, I assumed you included the up to date file in your download? I didn't add anything to the HashDB file. I just simply exported the model after conversion from Max and was just assigning textures inside of Unity3d, and for the materials that just had a hash name I just went through the S4 texture 'dump' that I had and went through the textures until I found one that matched, there were only a few I think that I couldn't for certain say that the texture belonged. I put the list together and figured you would likely find it useful and you could add it to your HashDB if you don't already have them.

EDIT: Should have read more  but just realized you put out a quick fix that alleviates that issue. So thanks for that!

The final result - [https://www.reddit.com/r/TheWalkingDead ... one_model/](https://www.reddit.com/r/TheWalkingDeadGame/comments/jcynec/clementines_house_s4_telltales_all_in_one_model/)
## Post #793
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-10-19T22:42:24+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Oh boy, another quickfix.

> Reply from Changelog
>
> Fixed SKL files being broken for Strong Bad's CG4AP Episodes 2-5 and Wallace & Gromit, I accidentally removed a line of code I shouldn't have before the previous update's release.
Nice going breaking one of your new features, RTB. :V

[https://mega.nz/file/GoxUjDIK#eRNDzrWm8 ... Lh0LcK1do0](https://mega.nz/file/GoxUjDIK#eRNDzrWm8eYab7ezpgUqwSx62UFnOV_SELh0LcK1do0)

Hopefully I won't have to push out another update again so soon.
## Post #794
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-11-10T01:39:34+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Sweet mother of double jeopardy backstroking in butterscotch! Looks like I've got another game to add support for soon -- Sam & Max Season 1's getting a remaster all of a sudden! Best case scenario is I only need to add the bone and texture hashes when it's released in December (the former should be easy, since I can refer back to the original). Worst case scenario? I spend another three months on the next script update.
## Post #795
- Username: Strick
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 22, 2020 1:37 pm
- Post datetime: 2020-11-22T06:23:02+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hello! When a PC-version support of BTTF:The Game will be released?
## Post #796
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-11-23T08:58:07+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Strick ↑Sun Nov 22, 2020 2:23 pm at Sun Nov 22, 2020 2:23 pm
>
> Hello! When a PC-version support of BTTF:The Game will be released?I'm not exactly sure when that's going to happen (since it's part of that one group of models I've yet to crack the formatting for), but I believe the PS4 version's models are identical anyway, so if you pair those with the PC version's textures it should work as a suitable alternative. Send me a PM if you're interested, and I'll hook you up with the model files from that version.
## Post #797
- Username: Strick
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 22, 2020 1:37 pm
- Post datetime: 2020-11-23T12:51:15+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

OK, I sent to you a message.
## Post #798
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-11-25T01:13:45+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Tue Oct 20, 2020 6:42 am at Tue Oct 20, 2020 6:42 am
>
> Hopefully I won't have to push out another update again so soon.Welp, looks like I did have to update it again after all, and it's not because of Sam & Max... yet.

```
Fixed SKL files being broken for Back to the Future's PS4 version (thanks, Strick!).
```

[https://mega.nz/file/GoxUjDIK#eRNDzrWm8 ... Lh0LcK1do0](https://mega.nz/file/GoxUjDIK#eRNDzrWm8eYab7ezpgUqwSx62UFnOV_SELh0LcK1do0)
## Post #799
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-12-02T22:26:57+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

*snip, decided to merge the two posts*
## Post #800
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-12-03T06:21:04+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Good news, everyone! It was the "best case scenario" after all! Sam & Max Save the World Remastered's models work right off the bat with my script, no changes necessary! (Here's a quick comparison of Sam's model [from the original](https://i.imgur.com/4HLdIz0.png) and [from the remaster](https://i.imgur.com/eWqdGLu.png).)

Since TTArchExt doesn't have support for this game at the time of this post, here's the Blowfish key needed to extract the TTARCH files:

```
92CA9A8185E46473A2BFD6D17FC6CB88995A80D8AAC297E796519FA89AD9AE95D776627FB4C4A6B9D6ECA99C6785B3DC92C49E64A0A292
```


And here's the update! 

```
Added a whole bunch of bone and texture hashes from Sam & Max: Save the World Remastered.
```

[https://mega.nz/file/GoxUjDIK#eRNDzrWm8 ... Lh0LcK1do0](https://mega.nz/file/GoxUjDIK#eRNDzrWm8eYab7ezpgUqwSx62UFnOV_SELh0LcK1do0)
(...can I even call it a script update if I didn't update the script itself?  )

Either way, there's apparently a single bone name for Sam that I can't figure out... not that it matters in this case since it doesn't seem to be rigged to anything on his model (and in fact was one added specifically for Season 3. Hmmmm...). And a few texture names from adv_toyMafiaExterior_bearHeadDamaged.d3dmesh, adv_tvAuditionRoom_meshesA.d3dmesh and obj_lincolnMemorial.d3dmesh seem to not exist in the game's files, so I'm not sure what's up with those. Everything else is accounted for, though.

Also, it's funny how things have come full-circle now. Sam & Max Season 1 was one of the first games I implemented, and now it's the latest one I've added.
## Post #801
- Username: daniar23337
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 31, 2020 9:38 am
- Post datetime: 2020-12-07T12:55:36+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

1. how export d3dtx files from S&M save the world remastered to dds?(i trying using quickbms,but i get black image [https://imgur.com/MrlBgjN](https://imgur.com/MrlBgjN))
2. When I import Sam model (with all parts) with bones, I get the error: [https://imgur.com/k0EPbvc](https://imgur.com/k0EPbvc) (if I import without bones, then everything is fine)
## Post #802
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2020-12-07T20:51:00+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from daniar23337 ↑Mon Dec 07, 2020 8:55 pm at Mon Dec 07, 2020 8:55 pm
>
> 
1. how export d3dtx files from S&M save the world remastered to dds?(i trying using quickbms,but i get black image https://imgur.com/MrlBgjN)
2. When I import Sam model (with all parts) with bones, I get the error: https://imgur.com/k0EPbvc (if I import without bones, then everything is fine)1. I haven't used IrfanView, but I think it might be incompatible with ATI2-based DDS files. Try using Noesis to preview it, if it works there then use it to convert the file to PNG. If not, then try re-exporting it with the "Telltale_D3DTX_Batman_GotG_TWD3_MCSM2.bms" script.
2. That's odd, I've never seen that issue before. What version of 3DS Max are you using?

(EDIT: Rephrased #1, I think I know why now.)
## Post #803
- Username: daniar23337
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 31, 2020 9:38 am
- Post datetime: 2020-12-10T03:03:54+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I managed to get the dds, edit it, and compile it back to d3dtx .But when I collect ttarch2 file with edited d3dtx(SM1_Compressed. ttarch2(I don't remember the exact name,because away from computer) ,but game does not see this ttarch2 file [https://imgur.com/iG24jZL](https://imgur.com/iG24jZL) .What settings should I choose when compiling an archive?(version,encrypted lua etc)(im ussing ttg tool )

P.s Solved this problem
## Post #804
- Username: Hakka
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 10, 2021 5:27 am
- Post datetime: 2021-02-09T21:50:27+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hello all,

Perhaps it is a question completely 'out of line' here, but here goes nothing.
I recently bought a 3D printer (which is amazing), went wilde with it, and also scavaging the internet for models of my favorite games. The Walking dead is one of them.

Somehow, for the Walking Dead I only can find one printable model, so I started thinking. Perhaps it is possible to get a usable model from the game. Played around with recording gameplay footage and tried to convert that, which turned out unusable. But this idea landed me after a seemingly endless search, by accident on this forum.

Amazing work by the way, to 'grab' the models from the game.  

I've (tried to) read how to open the models as provided in the 4 dropbox downloads. I failed.
By now I tried: 3D Max Pro (trail version, could not get script to work though), Sketchup, Blender 2.8, Blender 2.9 (both with XNALaraMesh), MeshMixer, Lolblender, AutoDesk, Spin3D, Wings 3D, Tinkercad and several online convert sites. All failed   .

Before I try even further (although no idea what program is left) in an area in which I am not even remotely familiar, I would like to ask your advice.
Can anybody indicate if it is even possible to convert/combine/merge the .skl/.3D3ds & texture files of the Walking Dead into a printable 3D model (.stl file)?

Kind regards,
Paul
## Post #805
- Username: jollyvb
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 24, 2021 3:14 am
- Post datetime: 2021-02-23T19:52:32+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Wanted to report an error when importing The Wolf Among Us meshes.

Tried importing two meshes - adv_bigbyApartment_meshesA.d3dmesh (cancelled choosing the .skl file since it didn't have one) and when that didn't work I tried a random character (sk54_crane.d3dmesh with respective sk54_crane.skl file). With each, the same error occured:

-- Unknown property: "twoSided" in sk_sharedparts_mouth:Physical Material (for Crane)

-- Unknown property: "twoSided" in env_bigbyaptwallkitchenright:Physical Material (for the apartment)

[https://imgur.com/D19wYvo](https://imgur.com/D19wYvo)


Fresh install of 3dsmax and the latest version of this plugin as of today. Tried looking if anyone had a similar issue in the comments but couldn't find any.

Thanks in advance for the help
## Post #806
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2021-02-24T08:15:23+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

For anyone having issues with importing the model due to issues such as the "twoSided" one that jollyvb's having in the previous post, could you try this tweaked version of the script and let me know if it fixes it for you? Sounds like the cause of the issue is Autodesk automatically forcing materials to be Physical by default instead of Standard (and therefore applies settings that don't exist with Physical), so I've added a line that switches it back to Standard before applying textures.

[https://mega.nz/file/vxQBwK5b#p9MPmPS6U ... 97iIEAVpuA](https://mega.nz/file/vxQBwK5b#p9MPmPS6UqFaEcghpJ-poLQzv63RYq-no97iIEAVpuA)

(EDIT: Seems functional, so I'll make this the "update post".)

```
Fixed models refusing to import in 3DS Max 2021 (the "twoSided" error was due to it trying to apply "Standard" material settings to a "Physical" material, which apparently is the new default).
```
## Post #807
- Username: Bleech
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 17, 2020 1:26 am
- Post datetime: 2021-02-24T15:28:48+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

just want to let u know about telltales file headers, the headers are metastreams which hold metadata (obivously) such as class names etc (seen in earlier meta binary - MBIN - meta streams) with newer meta stream version 5 and 6s (msv5,msv6) they crc64 the LOWER case class name, followed by a 4 byte version crc i think after. have u had any luck with that value? ive looked in the executables and ive found it must be some sort of version crc because in old games where the typename (the class which is now crc64ed) i found 'mTypeName' along with 'mVersionCrc' and in newer games 'mTypeNameCrc' and 'mVersionCrc', which makes sense because the new games have crc64 of the class (typename) but the whole the time version was still crced. Ive tried tons of polynomials and crc32 algos (its 4 bytes) and stil no luck. however i know it must bc the crc of it because even in the new games in the executable you can find '%s(%s).vers' whch is yes the format of a .vers file name (for example d3dmesh(vyss41).vers and d3dmesh(6lovtd).vers from old games). i found the .vers just show the format of the file which is very helpful for you which you im guessing may have used. anyway, my question is do you have any idea on that 4 byte value after  the typename? ive tried lower, upper and normal cases on the file name. i even found the crc32 tables in the executable and made sure its the correct one and it is. it must be the input data. as an example, 'd3dmesh(6lovtd).vers' has the version in the header (not in the metastream right after it!) '399229969' which should in theory be the crc of the file name or maybe the '6lovtd' but i have no clue what that value means either (i tried crcing it). files that use that vers format then have that value from the .vers after the typename, as you can see in an MBIN d3dmesh, 'class D3DMesh', 399229969. so that has to be the VERSION of it. even checked with new games the version changed per d3dmesh version (which is also a value in the d3dmesh header not in the metastream). like d3dmesh version 18s, if you look in mcsm and batman which both use v18 you can see the number after the typename crc is the SAME but different on non v18 meshes. i tried crcing 18 (although notice its %s in the .vers filename?) and everything. no luck. any ideas? (the reason i want to know is because the newer games dont have .vers, so how can i get that value for the header, since older games have .vers which has that value)
## Post #808
- Username: jollyvb
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 24, 2021 3:14 am
- Post datetime: 2021-02-24T18:26:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Wed Feb 24, 2021 4:15 pm at Wed Feb 24, 2021 4:15 pm
>
> 
For anyone having issues with importing the model due to issues such as the "twoSided" one that jollyvb's having in the previous post, could you try this tweaked version of the script and let me know if it fixes it for you? Sounds like the cause of the issue is Autodesk automatically forcing materials to be Physical by default instead of Standard (and therefore applies settings that don't exist with Physical), so I've added a line that switches it back to Standard before applying textures.

https://mega.nz/file/WgwSCRbJ#kp_TYe57A ... CweHgKh8kk

It works now!    For both Crane and the apartment. I'm having some issues with the textures, but those I can handle with Telltale Explorer. Thanks for the fast response!
## Post #809
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2021-02-25T02:21:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from jollyvb ↑Thu Feb 25, 2021 2:26 am at Thu Feb 25, 2021 2:26 am
>
> It works now!    For both Crane and the apartment. I'm having some issues with the textures, but those I can handle with Telltale Explorer. Thanks for the fast response!Excellent, sounds like I've found the fix for my other scripts with the same issue, then! I'll go add the updated script to first post now.
## Post #810
- Username: ohyeahbeepboop
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 08, 2021 2:44 pm
- Post datetime: 2021-04-08T06:47:11+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

When will Season 3 of Sam and Max be supported? Do you plan to make it supported? I've been trying to convert the meshes from d3d for days now and it won't work. I'm trying to get them into Blender but nothing I'm doing is working :/
## Post #811
- Username: Bleech
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 17, 2020 1:26 am
- Post datetime: 2021-04-12T23:18:13+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

im looking thru ur code for d3dmesh, ive been working on [https://github.com/LucasSaragosa/LibTelltale](https://github.com/LucasSaragosa/LibTelltale) for the last couple of months, there is a lot of stuff i recognize in d3dmesh i think i could help u understand a abit more about the format dm if u are interested

For example: u read a property set (.prop) from a map of materails to mat info and here (converted to java):
'if(matsecthash1.equals("52a09151")&&matsecthash2.equals("f1c3f2c7"))-- Way too many smaller variants, I'll only list the important ones.'

Your just comparing the CRC64 of 'handle<t3texture>'. this is a propertyset type. a handle<T> is a reference to a file telltale uses and when serialized its a crc hash
## Post #812
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-04-25T16:36:25+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I'm using 3DS Max 2018, when I go to import any model from Back to the Future it either freezes and crashes or doesn't import the skeleton anymore. Both the D3DMesh and .skl files are in the same folder as well, not sure what's going on here.
## Post #813
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2021-04-26T19:08:29+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

The last few updates seem to merge the mesh together, it's kinda not really helpful lol. Plus I've noticed it disregards any skl file for at least the zombies of the final season. I've not checked the others, that game was kinda bad anyways
## Post #814
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-04-26T19:22:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Tue Apr 27, 2021 3:08 am at Tue Apr 27, 2021 3:08 am
>
> 
The last few updates seem to merge the mesh together, it's kinda not really helpful lol. Plus I've noticed it disregards any skl file for at least the zombies of the final season. I've not checked the others, that game was kinda bad anyways

It seems to disregard skl files entirely, I'm having a similar issue with Back to the Future stuff and I tried to import Marty with his skl, but it only imported the mesh without any skeleton or weights. Some models just plain stopped working like Doc Brown where nothing is imported, hope he sees and fixes this.

Using Max 2018 btw.
## Post #815
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2021-04-26T21:23:57+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Using Max 2018 btw.I should add I'm using Max 2009.

I'm currently using the script dated 05/2019 and things seem to work fine for that one, the script I'm having issue on is the 24/02/2021. The odd merged mesh part issue is also in 19/10/2020.
## Post #816
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-04-27T13:32:26+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Tue Apr 27, 2021 5:23 am at Tue Apr 27, 2021 5:23 am
>
> 
Using Max 2018 btw.I should add I'm using Max 2009.

I'm currently using the script dated 05/2019 and things seem to work fine for that one, the script I'm having issue on is the 24/02/2021. The odd merged mesh part issue is also in 19/10/2020.

Do you think you can share the script that works for you? I can't find any older versions of the script and it might also work for me.
## Post #817
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-04-29T17:48:00+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Sun Jul 13, 2014 1:44 pm at Sun Jul 13, 2014 1:44 pm
>
> 
UPDATED 02/24/2021:
Fixed models refusing to import in 3DS Max 2021 (the "twoSided" error was due to it trying to apply "Standard" material settings to a "Physical" material, which apparently is the new default).

This script for 3DS Max will import the models from the majority of games that Telltale Games developed, with the original bone structures and rigging information (which by the way was no fun to fix up). This is the result of a year's worth of work... Well, not entirely, I started working on this back in July 2013, left it for a few months in a half-complete state and finished it up way later.



What games will this work with? [PC, unless stated otherwise]/b]
Back to the Future: The Game (30th Anniversary Edition) [PS4]
Batman: The Telltale Series (Season 1) [PC / PS4]
Batman: The Enemy Within (Season 2) [PC / PS4]
Bone: Out from Boneville
Bone: The Great Cow Race
CSI: 3 Dimensions of Murder
CSI: Hard Evidence
Game of Thrones [PC / PS4]
Jurassic Park: The Game
Law & Order: Legacies
Marvel's Guardians of the Galaxy
Minecraft: Story Mode (Season 1) [PC / PS4]
Poker Night 2
Sam & Max Save the World Remastered
Sam & Max Season 1
Sam & Max Season 2
Strong Bad's Cool Game for Attractive People
Tales from the Borderlands [PC / PS4]
Telltale Texas Hold'em
Wallace & Gromit's Grand Adventures, Episodes 1-3
The Walking Dead Season 1 [PC / PS4]
The Walking Dead Season 2 [PC / PS4]
The Walking Dead: A New Frontier (Season 3) [PC / PS4]
The Walking Dead: Michonne
The Walking Dead: The Final Season (Season 4)
The Walking Dead Collection [PS4]
The Walking Dead: The Telltale Definitive Series
The Wolf Among Us [PC / PS4]

What games will this NOT work with (yet?):
Back to the Future: The Game [PC]
CSI: Deadly Intent
CSI: Fatal Conspiracy
Marvel's Guardians of the Galaxy [PS4]
Poker Night at the Inventory
Sam & Max Season 3
Tales of Monkey Island
Wallace & Gromit's Grand Adventures, Episode 4
Pretty much any non-PC/PS4 versions of the above
One of these days I'll figure out what to do with those "Version 1" games.

Decryption key for Sam & Max: Save the World Remastered:
Code: Select allttarchext -k 92CA9A8185E46473A2BFD6D17FC6CB88995A80D8AAC297E796519FA89AD9AE95D776627FB4C4A6B9D6ECA99C6785B3DC92C49E64A0A292
Important things to keep in mind:
You'll need both the *.D3DMesh and *.SKL files, which should be in the same folder. The latter should be in the "data" TTARCHs.
Any bones or texture names that are unknown will be named after the first half of their hash. If their proper names are discovered, they will be added in a future update.
Use the QuickBMS scripts supplied to convert the D3DTX files to DDS, if necessary.
Download MaxScript
Download D3DTX to DDS QuickBMS Scripts
Tip for converting PS4 D3DTX textures

Please let me know if there are problems importing any of the models using this script, and I'll do what I can to fix it!

Could you take a look at our issues me and the other user are having? I'm not getting any of the .skl files to work with the mesh files and some mesh files don't import at all anymore now. I don't know if it's because of the latest script or my Max version.

Game: Back to the Future PS4

Max: 2018 version
## Post #818
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2021-05-19T08:20:56+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

That's strange, I could've sworn I fixed it for the Back to the Future models already... Those *are* indeed the PS4 models that are being imported and not the PC version's, correct? Either way, send me some samples via PM so I compare with what I've got, and see exactly what I (almost certainly) screwed up. Trying to maintain 16-and-a-half different revisions without accidentally breaking something is proving to be quite the ordeal...

In the meantime, I added the older version of my script to the first post, from before I revamped / optimized everything if you want to try that out.

> Reply from Tydeus ↑Tue Apr 27, 2021 5:23 am at Tue Apr 27, 2021 5:23 am
>
> The odd merged mesh part issue is also in 19/10/2020.Yeah, uh... that's intentional. That was part of the whole optimization process I did with the recent revision since it was faster to build a single mesh instead of several, broken-up ones, but if it was apparently better that way then I guess I'll need to re-implement an option for that in the next update. 

> Reply from ohyeahbeepboop ↑Thu Apr 08, 2021 2:47 pm at Thu Apr 08, 2021 2:47 pm
>
> When will Season 3 of Sam and Max be supported? Do you plan to make it supported? I've been trying to convert the meshes from d3d for days now and it won't work. I'm trying to get them into Blender but nothing I'm doing is working :/Can't say for sure, I never did figure out how to decompress the vertex buffers, and I'm definitely not smart enough to debug/decompile the EXEs to figure out how it's done.
## Post #819
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2021-05-21T23:22:14+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Wed May 19, 2021 4:20 pm at Wed May 19, 2021 4:20 pm
>
> Yeah, uh... that's intentional. That was part of the whole optimization process I did with the recent revision since it was faster to build a single mesh instead of several, broken-up ones, but if it was apparently better that way then I guess I'll need to re-implement an option for that in the next update.Oh, I dunno, it's probably fine maybe, I assume programs like XNALara will break up the model based on textures used, but I like to do headswaps and whatnot.

Although it does make it easier with them being in parts due to models using several texture maps for the face, like a bleeding face/zombie etc.
## Post #820
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2021-05-22T06:44:24+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Tydeus ↑Sat May 22, 2021 7:22 am at Sat May 22, 2021 7:22 am
>
> Oh, I dunno, it's probably fine maybe, I assume programs like XNALara will break up the model based on textures used, but I like to do headswaps and whatnot.

Although it does make it easier with them being in parts due to models using several texture maps for the face, like a bleeding face/zombie etc.And, thinking about it, having separate materials is also how the "bodygroups" for the SBCG4AP models work (face textures and Strong Bad's other set of boxing gloves, for instance), so yeah I can definitely understand why it'd be good to have those split up.

But yeah, go figure, the issues stem from my admittedly-crappy coding, so I'll work on undoing some of the changes I made to get those working again soon.
## Post #821
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-05-29T22:27:54+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Is there any reason meshes import with split pieces? Is there a way to import with everything as one mesh or at least pieces like the body and the head, instead of the head being split into multiple meshes and such? Importing for BTTF PS4.
## Post #822
- Username: Coverop
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jun 17, 2014 5:41 pm
- Post datetime: 2021-06-03T19:58:47+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I'm having difficulties with converting .d3dtx to .dds
I've used TellTale Explorer, but It can't convert everything in one go, tho It's possible to convert most of it.

I tried QuickBSM but I can't find a version for Sam & Max Remastered.
Does anyone else have this issue?
## Post #823
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2021-06-05T18:31:43+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Assasinge ↑Sun May 30, 2021 6:27 am at Sun May 30, 2021 6:27 am
>
> 
Is there any reason meshes import with split pieces? Is there a way to import with everything as one mesh or at least pieces like the body and the head, instead of the head being split into multiple meshes and such? Importing for BTTF PS4.I used to have the problem when using Mario's 3DS to XNALara. The entire model would look like it was ran through a blender, or paper shredder. A few of my earlier models are like that.
## Post #824
- Username: Snipy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 10, 2021 12:06 am
- Post datetime: 2021-07-09T16:11:45+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hi, I beg you to help. I use 3ds max and tellatale exporter, but when I export models from game of thrones, it wants textures of type 8382s38s.dds. but the exported textures from the game have normal names, I do everything the same. I tried 3ds max 2010, version 2021 and it still wants a different texture name than the correct one. For other games, thank you normally. I need an export game of thrones. Thank you very much
## Post #825
- Username: daniar23337
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 31, 2020 9:38 am
- Post datetime: 2021-08-05T15:03:09+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Coverop ↑Fri Jun 04, 2021 3:58 am at Fri Jun 04, 2021 3:58 am
>
> 
I'm having difficulties with converting .d3dtx to .dds
I've used TellTale Explorer, but It can't convert everything in one go, tho It's possible to convert most of it.

I tried QuickBSM but I can't find a version for Sam & Max Remastered.
Does anyone else have this issue?

use telltale_d3dtx_batman_gotg_twd3_mcsm2.bms
## Post #826
- Username: frostbone25
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 24, 2020 11:49 pm
- Post datetime: 2021-09-11T22:13:15+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hopefully, this goes through, but I sent a DM RTB regarding your script and questions about its code.
## Post #827
- Username: tehsuparhackr
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 31, 2021 12:22 pm
- Post datetime: 2021-10-31T04:26:54+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Since this needs both the .d3dmesh and .skl files, does this mean importing models that doesn't have a .skl with it is impossible? I found one of these in the Wallace & Gromit Grand Adventures demo on PC. It's called "tempdummybox.d3dmesh" and searching all the .ttarch files in the game's directory showed that this model doesn't have one. Importing into 3DS Max when it asks for a .skl file I have to hit cancel since it didn't have one then it of course shows an error since it couldn't find one. Another one I found like this was from Sam & Max Season 2 Episode 1 (Windows version). The model being "obj_sammaxofficestreet.d3dmesh" which again doesn't have the .skl file. Any way to fix this?
## Post #828
- Username: daniar23337
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 31, 2020 9:38 am
- Post datetime: 2021-10-31T08:27:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from tehsuparhackr ↑Sun Oct 31, 2021 12:26 pm at Sun Oct 31, 2021 12:26 pm
>
> 
Since this needs both the .d3dmesh and .skl files, does this mean importing models that doesn't have a .skl with it is impossible? I found one of these in the Wallace & Gromit Grand Adventures demo on PC. It's called "tempdummybox.d3dmesh" and searching all the .ttarch files in the game's directory showed that this model doesn't have one. Importing into 3DS Max when it asks for a .skl file I have to hit cancel since it didn't have one then it of course shows an error since it couldn't find one. Another one I found like this was from Sam & Max Season 2 Episode 1 (Windows version). The model being "obj_sammaxofficestreet.d3dmesh" which again doesn't have the .skl file. Any way to fix this? Skip the skl file, just click import without the skl file. Obj d3dxmeshes does not have an skl file
## Post #829
- Username: tehsuparhackr
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 31, 2021 12:22 pm
- Post datetime: 2021-10-31T08:46:47+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from daniar23337 ↑Sun Oct 31, 2021 4:27 pm at Sun Oct 31, 2021 4:27 pm
>
> 
tehsuparhackr wrote: ↑Sun Oct 31, 2021 12:26 pm
Since this needs both the .d3dmesh and .skl files, does this mean importing models that doesn't have a .skl with it is impossible? I found one of these in the Wallace & Gromit Grand Adventures demo on PC. It's called "tempdummybox.d3dmesh" and searching all the .ttarch files in the game's directory showed that this model doesn't have one. Importing into 3DS Max when it asks for a .skl file I have to hit cancel since it didn't have one then it of course shows an error since it couldn't find one. Another one I found like this was from Sam & Max Season 2 Episode 1 (Windows version). The model being "obj_sammaxofficestreet.d3dmesh" which again doesn't have the .skl file. Any way to fix this?
 Skip the skl file, just click import without the skl file. Obj d3dxmeshes does not have an skl file

Imported the dummy model that didn't have the .skl file, when it asked for the .skl file I could only cancel or close that window which then gives an error and doesn't let me import. I don't see an option to skip the .skl file at all.
## Post #830
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2021-12-09T16:43:38+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

And thus I have risen from the dust once again, due to the release of another game for me to work with.

Sam & Max: Beyond Time and Space Remastered blowfish key:

```
92CA9A8185E46573A2BFD6D17FC6CB89995A80D8AAC297E797519FA89AD9AE95D777627FB4C4A6B9D6ECAA9C6785B3DC92C49E65A0A292
```

It's ever-so-slightly different than Save the World Remastered's key, every 7th out of 9 bytes it's one value higher.

I'll have an update to my script files in the upcoming days, to add new bone and texture hashes like last time (the models themselves work regardless), and to finally made the fixes I should've done months ago. The latter would've been done way earlier, but it doesn't help that I've just been so mentally exhausted the past few months...
## Post #831
- Username: tehsuparhackr
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 31, 2021 12:22 pm
- Post datetime: 2021-12-09T19:13:04+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Fri Dec 10, 2021 12:43 am at Fri Dec 10, 2021 12:43 am
>
> 
And thus I have risen from the dust once again, due to the release of another game for me to work with.

Sam & Max: Beyond Time and Space Remastered blowfish key:
Code: Select all92CA9A8185E46573A2BFD6D17FC6CB89995A80D8AAC297E797519FA89AD9AE95D777627FB4C4A6B9D6ECAA9C6785B3DC92C49E65A0A292
It's ever-so-slightly different than Save the World Remastered's key, every 7th out of 9 bytes it's one value higher.

I'll have an update to my script files in the upcoming days, to add new bone and texture hashes like last time (the models themselves work regardless), and to finally made the fixes I should've done months ago. The latter would've been done way earlier, but it doesn't help that I've just been so mentally exhausted the past few months...
That was fast
## Post #832
- Username: Ironcarnage101
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 31, 2021 7:45 am
- Post datetime: 2021-12-10T00:07:24+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Does anyone know if I can import ripped assets in Blender somehow? I unfortunately don't have access to 3DsMax. It's been annoying since I've been wanting to rip the maps from Jurassic Park: The Game as well. If someone could help that would be great
## Post #833
- Username: frostbone25
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 24, 2020 11:49 pm
- Post datetime: 2021-12-10T06:20:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Ironcarnage101 ↑Fri Dec 10, 2021 8:07 am at Fri Dec 10, 2021 8:07 am
>
> 
Does anyone know if I can import ripped assets in Blender somehow? I unfortunately don't have access to 3DsMax. It's been annoying since I've been wanting to rip the maps from Jurassic Park: The Game as well. If someone could help that would be great

Without 3DS Max, unfortunately, "Currently" there is no way to do it in another program. RTB wrote this script in MaxScript and it will only work in 3DS Max. 

However, I did initially try to take his script and convert it into a standalone C# program which was a chore, to say the least... I got close to finishing it however there were some hiccups that I had to ask RTB about via DM about his script and what exactly he was doing at certain parts (which he still hasn't gotten back to me about it). I still have the app however I quickly shoved that aside because one of my mates has been hard at work reverse-engineering some of the telltale game formats, namely the .d3dmesh being one of them - [https://github.com/LucasSaragosa/Tellta ... /D3DMesh.h](https://github.com/LucasSaragosa/TelltaleToolLib/blob/master/Src/Types/D3DMesh.h)

The version is based on the walking dead definitive edition (Namely because it accidentally shipped with a PDB meaning it makes it very easy to peek into the actual functions that serialize/deserialize every format) 

I don't imagine you to be a programmer but if anyone wants to take a stab at writing a converter you sure can as the D3DMESH format is detailed here 
- [https://github.com/LucasSaragosa/Tellta ... /D3DMesh.h](https://github.com/LucasSaragosa/TelltaleToolLib/blob/master/Src/Types/D3DMesh.h) - While the version that I linked won't 100% match the old version (again its based off the walking dead definitive edition which is obviously way newer than the Jurassic park files) The general structure is still roughly the same. I just haven't had the time currently to get around to writing that converter app (and some other things)

P.S. I suggest you take a look at that header file RTB to help clean up your maxscript. You can also ask me questions about some parts of the file (or Bleech who is the lad who wrote that - [memberlist.php?mode=viewprofile&u=87713](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=87713) )
## Post #834
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2021-12-10T15:31:19+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from frostbone25 ↑Fri Dec 10, 2021 2:20 pm at Fri Dec 10, 2021 2:20 pm
>
> However, I did initially try to take his script and convert it into a standalone C# program which was a chore, to say the least... I got close to finishing it however there were some hiccups that I had to ask RTB about via DM about his script and what exactly he was doing at certain parts (which he still hasn't gotten back to me about it).Yeah, I'm sorry about that. There's a lot of things that I've been meaning to do that I keep forgetting about, I'll get back to you regarding that sometime soon.
## Post #835
- Username: Yekulten
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 08, 2022 12:39 am
- Post datetime: 2022-02-07T16:43:15+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

How do I use this exactly?
## Post #836
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2022-03-15T20:09:20+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Yekulten ↑Tue Feb 08, 2022 12:43 am at Tue Feb 08, 2022 12:43 am
>
> 
How do I use this exactly?

You need 3ds Max and you have to run the script.
## Post #837
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2022-04-12T18:13:12+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Question for RTB, Did you ever find the exact bone name for "0xb59f22bc"? It's something I've been curious about.
## Post #838
- Username: hotgoblin
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Apr 15, 2012 1:52 am
- Post datetime: 2022-06-04T10:27:18+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

would be cool to get the support for the PC version of BTTF
## Post #839
- Username: StarDotCob
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 20, 2022 12:28 am
- Post datetime: 2022-07-19T16:32:54+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Escope12 ↑Wed Mar 16, 2022 4:09 am at Wed Mar 16, 2022 4:09 am
>
> 
Yekulten wrote: ↑Tue Feb 08, 2022 12:43 am
How do I use this exactly?


You need 3ds Max and you have to run the script.

I could use a little help with this. I've got the extracted telltale model, but I have no way to run this script. I don't have access to 3D Studio Max and I'm operating off of a MAC computer.
## Post #840
- Username: Franco
- Rank: beginner
- Number of posts: 37
- Joined date: Sat May 28, 2022 7:03 am
- Post datetime: 2022-08-04T18:24:14+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hello, what is the archive key for Save the World Remastered? None of the commands work for this game.
Sample files are here, can you help please.

[https://www.mediafire.com/file/n63mtx50 ... stered.rar](https://www.mediafire.com/file/n63mtx50b9s1hej/Save_the_World_Remastered.rar)
## Post #841
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2022-08-04T19:35:10+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Franco ↑Fri Aug 05, 2022 2:24 am at Fri Aug 05, 2022 2:24 am
>
> Hello, what is the archive key for Save the World Remastered? None of the commands work for this game.
Sample files are here, can you help please.

https://www.mediafire.com/file/n63mtx50 ... stered.rarThe decryption key for it is listed in the first post.

Also, somewhat related, but yeah I know I've been slacking with updating this script to have proper filenames for Sam & Max Season 2 Remastered. Perhaps I'll do that sometime later this month before I start working on any other adjustments to the script.
## Post #842
- Username: Franco
- Rank: beginner
- Number of posts: 37
- Joined date: Sat May 28, 2022 7:03 am
- Post datetime: 2022-08-04T22:33:02+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Fri Aug 05, 2022 3:35 am at Fri Aug 05, 2022 3:35 am
>
> 
Franco wrote: ↑Fri Aug 05, 2022 2:24 amHello, what is the archive key for Save the World Remastered? None of the commands work for this game.
Sample files are here, can you help please.

https://www.mediafire.com/file/n63mtx50 ... stered.rarThe decryption key for it is listed in the first post.

Also, somewhat related, but yeah I know I've been slacking with updating this script to have proper filenames for Sam & Max Season 2 Remastered. Perhaps I'll do that sometime later this month before I start working on any other adjustments to the script.

This works very well. Sorry it's my fault I tried the wrong one. Thank you very much.
## Post #843
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2022-08-09T19:14:46+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from Franco ↑Fri Aug 05, 2022 6:33 am at Fri Aug 05, 2022 6:33 am
>
> This works very well. Sorry it's my fault I tried the wrong one. Thank you very much.Can't say I blame you for mixing it up when both of the remasters have nearly-identical keys, heh.

Anyway, this is super-late, but here's an update to the script's hash databases specifically for Sam & Max: Beyond Time and Space Remastered. No rewriting / additional bugfixing just yet, unfortunately haven't had the motivation for that kind of thing recently.

```
(Yes, I know I should've done this ages ago.)
```

[https://mega.nz/file/30xERBJL#nqGfoLOyx ... N2hY4vorCQ](https://mega.nz/file/30xERBJL#nqGfoLOyxGPnlir7mxAartozDW8f4N7sKN2hY4vorCQ)

As the saying goes, better late than never, right? Either way I still don't know what Sam's last bone ("0xf3b77e5b") is supposed to be named, if it weren't for that there'd be no missing hashes for either of the remastered releases. Hrm. Guess I'll have to wait until Season 3 before I get my answer to that question.
## Post #844
- Username: Franco
- Rank: beginner
- Number of posts: 37
- Joined date: Sat May 28, 2022 7:03 am
- Post datetime: 2022-08-23T11:31:16+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from RandomTBush ↑Wed Aug 10, 2022 3:14 am at Wed Aug 10, 2022 3:14 am
>
> 
Franco wrote: ↑Fri Aug 05, 2022 6:33 amThis works very well. Sorry it's my fault I tried the wrong one. Thank you very much.  Can't say I blame you for mixing it up when both of the remasters have nearly-identical keys, heh.

Anyway, this is super-late, but here's an update to the script's hash databases specifically for Sam & Max: Beyond Time and Space Remastered. No rewriting / additional bugfixing just yet, unfortunately haven't had the motivation for that kind of thing recently.
Code: Select allAdded a whole bunch of bone and texture hashes from Sam & Max: Beyond Time and Space Remastered.
(Yes, I know I should've done this ages ago.)
https://mega.nz/file/30xERBJL#nqGfoLOyx ... N2hY4vorCQ

As the saying goes, better late than never, right? Either way I still don't know what Sam's last bone ("0xf3b77e5b") is supposed to be named, if it weren't for that there'd be no missing hashes for either of the remastered releases. Hrm. Guess I'll have to wait until Season 3 before I get my answer to that question.

Sorry for seeing you late. Thanks for your interest and concern. Your work helps us a lot
## Post #845
- Username: Wilps
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 06, 2020 2:31 am
- Post datetime: 2022-09-03T15:43:45+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Hello, can you help me?

The problem occurs with converting BTTF PS4 *.d3dtx files.

Example of a problem:
[https://1.downloader.disk.yandex.ru/pre ... e=1349x652](https://1.downloader.disk.yandex.ru/preview/b3c65993d96941aa3e561b51d92759afc6aeba3607beea86e6576a5012ac44c6/inf/g33YUcevGbRn8SDQARdJtsxn4j9a_gaWlRkH95H83gElAOrwSAPpNdmL6pSxlZniWxtyANn6uSSiX2Mwm3WiaA%3D%3D?uid=34056953&filename=_DaPzXWHjV8.jpg&disposition=inline&hash=&limit=0&content_type=image%2Fjpeg&owner_uid=34056953&tknv=v2&size=1349x652)

Files:
1. BTTF_ps4_BackToTheFuture101_txmesh.ttarch2 (extract .d3dtx files tools Telltale TTARCH files extractor/rebuilder 0.3.2 (parameters extract: ttarchext.exe 41 "C:\BTTF\BTTF_ps4_BackToTheFuture101_txmesh.ttarch2" "C:\BTTF\BTTF_ps4_BackToTheFuture101_txmesh")) 
2. adv_docBrownLab_meshesA_000.d3dtx (Used BMS script: Telltale_D3DTX_TftBL_GoT_MCSM_BttFPS4.bms)
3. adv_docBrownLab_meshesA_000.dds (Output DDS file with artifacts)

Archive:
[https://disk.yandex.ru/d/cb-ABcY4gJZEwA](https://disk.yandex.ru/d/cb-ABcY4gJZEwA)

Used versions PS4 game (I can personally provide links to these pkg. If you need it.):
Back to the Future The Game 30th Anniversary Edition [CUSA02972] [EU] 1.01v / Fake PKG 
Back to the Future The Game 30th Anniversary Edition [CUSA02924] [USA] 1.01v / Fake PKG

To unpack PKG, I used the PS4 PKG Tool (latest version).

Maybe someone can share BTTF_ps4_BackToTheFuture10*_txmesh.ttarch2 all episodes?
## Post #846
- Username: Wilps
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 06, 2020 2:31 am
- Post datetime: 2022-09-04T11:12:54+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Is it possible to edit textures? Convert DDS to D3DTX?
## Post #847
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-09-04T14:36:39+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

i was hoping there's a Noesis Import for Telltale Game Models and Textures.
Is there some?
## Post #848
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2022-09-19T21:23:02+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

> Reply from tritterman ↑Sun Sep 04, 2022 10:36 pm at Sun Sep 04, 2022 10:36 pm
>
> 
i was hoping there's a Noesis Import for Telltale Game Models and Textures. Is there some? What do you mean? Instead of having to use 3DS Max?
## Post #849
- Username: micTronic
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Dec 16, 2020 6:28 am
- Post datetime: 2022-10-17T21:58:46+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I suppose there is no plan to add Tales of Monkey Island to the list?  It's one of my all-time favorites, but there's just so little documentation on its model / map formats as it's one of the older games. A freecam would have been awesome as well (there is one for Tales from the Borderlands).
## Post #850
- Username: Jerry Seinfeld
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 17, 2023 9:05 am
- Post datetime: 2023-03-17T01:10:30+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

What's the deal with the Wallace and Gromit models being funky? It looks fine in 3DS Max 2012 but when it goes into Blender he looks like he imploded!
## Post #851
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-07-18T11:46:39+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

can anyone explain to me how to import batman models with telltale all in all importer?
I see this window


whatever I choose there I get this error:


p.s.: 3ds max 2016, win11
## Post #852
- Username: Tydeus
- Rank: veteran
- Number of posts: 96
- Joined date: Sun Aug 30, 2015 7:34 pm
- Post datetime: 2023-08-05T22:04:57+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

I'm not sure if I'm using an old one, but the plugin is from 2022.

But anyways, a lot of the scenery/prop bones from TWD Season 2 dont work, like the trees and whatnot.. at the very least (so far) for the LakeWoodsCellar and Truck. At the moment though I'm wanting to get obj_boxCardBoardWD and I'll get this error for the skl

(I forgot the BBCode to resize, sorry)
## Post #853
- Username: tehsuparhackr
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 31, 2021 12:22 pm
- Post datetime: 2023-08-27T07:51:45+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Any chance the importer plugin will get a Blender variant seeing how I don't own 3DS Max lol
## Post #854
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2023-09-02T00:05:06+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

i agree with him I need a Blender or Noesis Plugin to Read .D3DMesh on the App.
## Post #855
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2023-10-17T23:52:22+00:00
- Post Title: Re: Telltale Games "Almost-All-In-One" Model Importer

Sorry I don't have any progress updates on fixing existing issues. Things happened and I lost several script updates (including one for this) in a hard drive failure a few months back (I never expected that to happen without warning, and didn't think to back those up), and I've been demotivated because of which... and the sudden decision of the XeNTaX forums being shut down doesn't help either.

So I'm just gonna state that I've moved my MaxScripts over to GitHub to give them a more permanent home, any potential updates will be posted there:
[MaxScript](https://github.com/RandomTBush/RTB-3DSMax-Scripts/blob/main/Scripts/TelltaleGames_D3DMesh.ms) 
[Hash Databases](https://github.com/RandomTBush/RTB-3DSMax-Scripts/tree/main/Scripts/TelltaleHashDBs)

*shrug*
