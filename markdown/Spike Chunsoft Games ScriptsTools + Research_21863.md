## Post #1
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2020-03-10T09:05:39+00:00
- Post Title: Spike Chunsoft Games Scripts/Tools + Research

---‐----------------------------------------------------------------
UPDATE: A NOESIS SCRIPT TO LOAD BOTH MESHES + TEXTURES - HERE
---‐----------------------------------------------------------------

This is a thread for some lastest Spike Chunsoft games as well as my scripts + tools based on what I've researched. And my apologies to all who have been waiting for this so long. I haven't been available for ages.

-------PREVIEW--------
Images:


Videos:
[One Punch Man: AHNK](https://youtu.be/We8rqnQU33w)
[One Piece Burning Blood](https://youtu.be/Cm9bDcudmMY)


-------INSTRUCTIONS--------
Extract files:
- Use QuickBMS and cmp_scz to decompressed the original files (npk, npki, npkv)
- Rename files to their original name (including extension)

Open models in Noesis
- Put fmt_SpikeGames_npk.py to ../Noesis/python/plugins
- Navigate to the location of files, and open .npk file

Get 2nd model
- Drag & drop .npk file to NPKCutter.exe
- The extracted .npk file (xxx_2nd_model.npk) are ready to open
Note: If nothing happened, it doesn't have 2nd model

Extract textures
- Drag & drop .npk file to NPKVExtractor.exe
- Choose a platform (texture swizzle)
- The textures will be extracted

Extract textures for 2nd model:
- Do Get 2nd model first
- After "x_2ndmodel" files appear, do Extract textures and it will also generate "x_2ndmodel.npkv" if other "x_2ndmodel" files exists
- Drag & drop "x_2ndmodel.npk"
Note: Those steps are dumb due to my laziness, sorry for that  

Note: Make sure that all required file with the corresponding name are in the same folder with .npk file

-------GAMES--------
- One Punch Man: A Hero Nobody Knows (PS4)
- One Piece Burning Blood (PC)(PSP) - (Not sure if it works with all models)
- J-Stars Victory VS+ (PS3) - (Code refactoring - Nearly done)
- Dangaronpa V3 (WIP)

-------KNOWN ISSUES--------
- There might be some versions of the game on different platforms that I haven't tested
- PS3 Swizzle in NPKVExtract.exe is yet functional
- No textures/materials supported as it's kinda difficult to make them correspond to the submeshes
- NPKVExtract is not able to extract textures of 2nd model yet. (Solved)
- The script works with skeletal model only

-------CREDITS--------
Special thanks to:
- Aluigi for QuickBMS script.
- Chroxx, episoder, shakotay2, Turk645, and BigChillGhost for their useful help and references for reading & parsing data.
- Josune Kitsune for his detailed structure of the file done by his research.
- Demonslayerx8, JosuneKitsune, and the others to test and help me improve the script.

-------UPDATES--------
-(Fix) 10/03/2020
-(Fix) 11/03/2020

P/s: Feel free to report any issues/problems with error image or help me improve the scripts. This is my first time uploading scripts/tools, please forgive me for any inconvenience and enjoy.
[SPC_NPK.zip](https://xentaxbackup.github.io/file/17698_SPC_NPK.zip)
## Post #2
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-03-10T11:16:57+00:00
- Post Title: Spike Chunsoft Games Scripts/Tools + Research

Thank you very much for sharing this tool   
I assume this uses the PS4 files?
## Post #3
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2020-03-10T11:34:13+00:00
- Post Title: Spike Chunsoft Games Scripts/Tools + Research

> Reply from Eag1e ↑Tue Mar 10, 2020 7:16 pm at Tue Mar 10, 2020 7:16 pm
>
> 
I assume this uses the PS4 files?

Yes, check the Games section, I did mention the platform of games on that list.

P/s: Updated the script!
## Post #4
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-03-10T12:01:26+00:00
- Post Title: Spike Chunsoft Games Scripts/Tools + Research

Helped Hiroshi (andy) with all the One Punch Man model tests, along with testing updated scripts. Pretty much most of the models will now work, the NPKV tool he made will have to be updated to work with 2nd models tho, which he'll do later.
Chars with 2nd model



Accessory


Item


I'd help with J-Stars Victory VS+, but I don't have the files for that game.
## Post #5
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2020-03-11T00:43:25+00:00
- Post Title: Spike Chunsoft Games Scripts/Tools + Research

UPDATE!
Now the bones and their name will correspond to the correct side of submesh (xxx_L will be on the left side, and xxx_R will be on the right side)

Thanks to JosuneKitsune for that.

UPDATE #2:
Now using local space instead of world space since it had many issues about the positions

Thanks to Demonslayerx8 and his friend.

UPDATE #3:
Added a script for PSP files for anyone who is interested.
## Post #6
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-03-11T07:08:32+00:00
- Post Title: Spike Chunsoft Games Scripts/Tools + Research

Thanks for all the updates, appreciate it!
## Post #7
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2020-03-11T13:42:20+00:00
- Post Title: Spike Chunsoft Games Scripts/Tools + Research

UPDATE:
- Outputs of NPKCutter are better than the older one.
- Able to get textures of 2nd models now ( with many dumb steps)
- Add a mini tool for renaming the decompressed files, just drag & drop
- (Quick fix) Fix NPKVExtractor to get the correct "xxx_k.bmp" textures
## Post #8
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2020-03-12T02:02:57+00:00
- Post Title: Spike Chunsoft Games Scripts/Tools + Research

#UPDATE:
Since the external programs are confusing, I'm working on my Noesis script to make it handle both textures and 2nd model in .npk.
Works well with both OPBB and OPM at the moment (can import meshes, textures, skeletons), and it's still in development.

Some previews:

Saitama - chr000.npk - OPM



Bentham - character_031.npk
## Post #9
- Username: ChaoticFusion40
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 01, 2019 3:42 pm
- Post datetime: 2020-03-12T03:14:11+00:00
- Post Title: Spike Chunsoft Games Scripts/Tools + Research

if anyone wants to create a script to convert these to gxt or png here are all the model files for reference.

[https://drive.google.com/file/d/1qvSRBS ... sp=sharing](https://drive.google.com/file/d/1qvSRBSnkbHkC6_G9jxb_R5SVBhTKpB5k/view?usp=sharing)
## Post #10
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-03-12T06:55:13+00:00
- Post Title: Spike Chunsoft Games Scripts/Tools + Research

> Reply from ChaoticFusion40 ↑Thu Mar 12, 2020 11:14 am at Thu Mar 12, 2020 11:14 am
>
> 
if anyone wants to create a script to convert these to gxt or png here are all the model files for reference.

https://drive.google.com/file/d/1qvSRBS ... sp=sharingWhat game is that from?

edit:
oh OPBB [PSP]

anyways, helped with figuring the textures for J-Stars

15 - DXT1
17 - DXT5
19 - unsure??

just unsure about the normal maps.... which is 19, but any texture format just breaks it besides DXT5
## Post #11
- Username: ChaoticFusion40
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 01, 2019 3:42 pm
- Post datetime: 2020-03-12T11:11:54+00:00
- Post Title: Spike Chunsoft Games Scripts/Tools + Research

One Piece Burning Blood.
## Post #12
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-14T20:38:33+00:00
- Post Title: Spike Chunsoft Games Scripts/Tools + Research

I was doing my own script for Spike Chunsoft's fighting games that use the .npk format (OPBB/OPM), it extracted the textures and meshes in one go, but I was missing the bones and weights, so when Hiroshi released this I adapted a portion of his code into mine. So with his permission I'm posting my script to extract textures, models, bones, weights and Form Changes. Thanks Hiroshi without your code this wouldn't be possible.

The script supports OPBB PC and OPM PS4 .npk files, you need to have the uncompressed .npk, .npki and .npkv files in the same folder for this to work.






---------------------------------------------------UPDATE---------------------------------------------------

Added support for characters with more than 2 forms







---------------------------------------------------UPDATE---------------------------------------------------

Fixed some UVs issues



---------------------------------------------UPDATE May 2021---------------------------------------------

Fixed more UVs issues


[fmt_SpikeChunsoftFTG_npk.7z](https://xentaxbackup.github.io/file/20106_fmt_SpikeChunsoftFTG_npk.7z)
## Post #13
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2020-03-16T16:21:24+00:00
- Post Title: Spike Chunsoft Games Scripts/Tools + Research

Damn, pretty amazing progress.
## Post #14
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2020-03-16T19:46:29+00:00
- Post Title: Spike Chunsoft Games Scripts/Tools + Research

I was trying your noesis plugin on the OPM .npk files. First difference is that the headers read as "$CMP" instead of "npak", so the script wont even start. After changing this stuff on line 12 there is another error while reading the vertex data, shown in the screenshot. All the files are in the same folder. I'll keep trying for a bit.

Update: I am a moron, my files were still compressed!

Tips for decompressing with quickbms and the cmp_scz.bms script:
There will be duplicate .dat files, choose [r] (rename) as the desired action for all
then batch renaming everything
chr0000_model.npa -> chr0000_model.npk
chr0000_model.dat -> chr0000_model.npki
and the bms autorenamed chr0000_model_00000001.dat -> chr0000_model.npkv
## Post #15
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-18T01:42:40+00:00
- Post Title: Spike Chunsoft Games Scripts/Tools + Research

I've updated the script to handle characters with more than 2 forms [viewtopic.php?f=16&t=21863#p160926](https://forum.xentax.com/viewtopic.php?f=16&t=21863#p160926)
## Post #16
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-03-20T10:43:00+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

For anyone that wants the raw, decompressed PS4 files, [here ya go](https://mega.nz/#F!chkDBTxD!WZeGRBIXFkwaxod68unxUw). Has all the characters and items, there's too many avatar and accessories for me to decompressed and fix the names + extensions, I'll probably get around to doing that at some point in the next few days.

Do note, it does not include animation files, just the npk, npki, and npkv.
## Post #17
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-03-21T21:59:03+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from JosouKitsune ↑Sun Mar 15, 2020 4:38 am at Sun Mar 15, 2020 4:38 am
>
> 
I was doing my own script for Spike Chunsoft's fighting games that use the .npk format (OPBB/OPM), it extracted the textures and meshes in one go, but I was missing the bones and weights, so when Hiroshi released this I adapted a portion of his code into mine. So with his permission I'm posting my script to extract textures, models, bones, weights and Form Changes. Thanks Hiroshi without your code this wouldn't be possible.

The script supports OPBB PC and OPM PS4 .npk files, you need to have the uncompressed .npk, .npki and .npkv files in the same folder for this to work.






---------------------------------------------------UPDATE---------------------------------------------------

Added support for characters with more than 2 forms

Tool works great! just one question, how do you get the 2nd models to work on Marco for example? I don't think the second form got out when extracting the npk with Noesis
## Post #18
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-21T22:35:09+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from Eag1e ↑Sun Mar 22, 2020 5:59 am at Sun Mar 22, 2020 5:59 am
>
> 

Tool works great! just one question, how do you get the 2nd models to work on Marco for example? I don't think the second form got out when extracting the npk with Noesis

In the Export media window Advanced options -modelindex 1
## Post #19
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-03-22T01:27:21+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from JosouKitsune ↑Sun Mar 22, 2020 6:35 am at Sun Mar 22, 2020 6:35 am
>
> 
Eag1e wrote: ↑Sun Mar 22, 2020 5:59 am

Tool works great! just one question, how do you get the 2nd models to work on Marco for example? I don't think the second form got out when extracting the npk with Noesis  


In the Export media window Advanced options -modelindex 1

Ah that worked, thank you!
## Post #20
- Username: amestrisx
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 09, 2015 3:27 am
- Post datetime: 2020-03-23T02:58:26+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

i dont want to be that guy but i never worked with ps4 file before....so.... i need the disc? or there is someway to download the rom (im not asking for links since i guess is forbidden) just want to know that
## Post #21
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-23T06:40:06+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from amestrisx ↑Mon Mar 23, 2020 10:58 am at Mon Mar 23, 2020 10:58 am
>
> 
i dont want to be that guy but i never worked with ps4 file before....so.... i need the disc? or there is someway to download the rom (im not asking for links since i guess is forbidden) just want to know that

demonslayer already shared the uncompressed files a few posts above.
## Post #22
- Username: amestrisx
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 09, 2015 3:27 am
- Post datetime: 2020-03-23T23:59:48+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from JosouKitsune ↑Mon Mar 23, 2020 2:40 pm at Mon Mar 23, 2020 2:40 pm
>
> 
amestrisx wrote: ↑Mon Mar 23, 2020 10:58 am
i dont want to be that guy but i never worked with ps4 file before....so.... i need the disc? or there is someway to download the rom (im not asking for links since i guess is forbidden) just want to know that


demonslayer already shared the uncompressed files a few posts above.

omg didnt saw that, thank you and thank you @Demoslayer
## Post #23
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-03-24T06:28:36+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

no problem
## Post #24
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-04-07T06:21:17+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from Eag1e ↑Sun Mar 22, 2020 9:27 am at Sun Mar 22, 2020 9:27 am
>
> 
Ping

Fixed the UV issue Eag1e.
[viewtopic.php?f=16&t=21863#p160926](https://forum.xentax.com/viewtopic.php?f=16&t=21863#p160926)
## Post #25
- Username: kenji69
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jul 23, 2020 6:31 pm
- Post datetime: 2020-07-23T10:37:48+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

Hi, how did you export cpk file ? I tryed with quickbms with cmp_scz.bms but It didn't work...
## Post #26
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-07-23T23:12:33+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from kenji69 ↑Thu Jul 23, 2020 6:37 pm at Thu Jul 23, 2020 6:37 pm
>
> 
Hi, how did you export cpk file ? I tryed with quickbms with cmp_scz.bms but It didn't work...

You can try any CPK tool out there, but I recommend [XV2 CPK Browser](https://xenoversemods.com/mods/cpk-browser-view-and-extract-files/)
## Post #27
- Username: kenji69
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jul 23, 2020 6:31 pm
- Post datetime: 2020-07-24T15:01:28+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from JosouKitsune ↑Fri Jul 24, 2020 7:12 am at Fri Jul 24, 2020 7:12 am
>
> 
kenji69 wrote: ↑Thu Jul 23, 2020 6:37 pm
Hi, how did you export cpk file ? I tryed with quickbms with cmp_scz.bms but It didn't work...


You can try any CPK tool out there, but I recommend XV2 CPK Browser

I have tryed but i got pak file with CPK Tool, the aim of using quickbms with the script is to have npk file. We can't open pak files, but it seems that's not the case with npk files.
## Post #28
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-07-24T19:42:20+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from kenji69 ↑Fri Jul 24, 2020 11:01 pm at Fri Jul 24, 2020 11:01 pm
>
> 

I have tryed but i got pak file with CPK Tool, the aim of using quickbms with the script is to have npk file. We can't open pak files, but it seems that's not the case with npk files.

What game are you trying to extract? OPBB or OPM?
Extracting OPBB gives scz files and OPM npk, npki, npkv files.
## Post #29
- Username: kenji69
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jul 23, 2020 6:31 pm
- Post datetime: 2020-07-25T06:39:13+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from JosouKitsune ↑Sat Jul 25, 2020 3:42 am at Sat Jul 25, 2020 3:42 am
>
> 
kenji69 wrote: ↑Fri Jul 24, 2020 11:01 pm

I have tryed but i got pak file with CPK Tool, the aim of using quickbms with the script is to have npk file. We can't open pak files, but it seems that's not the case with npk files.


What game are you trying to extract? OPBB or OPM?
Extracting OPBB gives scz files and OPM npk, npki, npkv files.

I'm trying OPM and J Star victory, both give me pak file with CPK tool's.
## Post #30
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-07-25T15:11:10+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from kenji69 ↑Sat Jul 25, 2020 2:39 pm at Sat Jul 25, 2020 2:39 pm
>
> 

I'm trying OPM and J Star victory, both give me pak file with CPK tool's.

It's weird that you get pak files from OPM but demonslayerx8 has already uploaded the files [here](https://forum.xentax.com/viewtopic.php?f=16&t=21863&p=165280#p161105).

And J-Stars pak files are impossible to extract at the moment, since nobody has cracked the decompression method, however me and Andy97/hiroshi got the raw files through the RPCS3 emulator, I've uploaded the decompressed files and proper script for it [here](https://www.mediafire.com/file/lftuffoh9h64ru5/JSTARS_Models.7z/file/).
## Post #31
- Username: kenji69
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jul 23, 2020 6:31 pm
- Post datetime: 2020-07-27T09:24:16+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from JosouKitsune ↑Sat Jul 25, 2020 11:11 pm at Sat Jul 25, 2020 11:11 pm
>
> 
kenji69 wrote: ↑Sat Jul 25, 2020 2:39 pm

I'm trying OPM and J Star victory, both give me pak file with CPK tool's.


It's weird that you get pak files from OPM but demonslayerx8 has already uploaded the files here.

And J-Stars pak files are impossible to extract at the moment, since nobody has cracked the decompression method, however me and Andy97/hiroshi got the raw files through the RPCS3 emulator, I've uploaded the decompressed files and proper script for it here.

Thank you for the files , We will see if someone can export files for J Star Victory.
## Post #32
- Username: Garbobby
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 22, 2020 2:05 pm
- Post datetime: 2020-10-23T08:15:23+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

sorry if this is a really ignorant question I'm very new to all this. 

I've managed to extract the OP:BB models to .fbx and the textures to .png but the textures are not applied to the models. Am I missing a step here or do I have to go through and recreate the materials in blender?

thanks for all the tools and info so far!
## Post #33
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-10-23T14:49:15+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from Garbobby ↑Fri Oct 23, 2020 4:15 pm at Fri Oct 23, 2020 4:15 pm
>
> 
You'll have to create the material yourself.
## Post #34
- Username: Garbobby
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 22, 2020 2:05 pm
- Post datetime: 2020-10-23T21:48:04+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from JosouKitsune ↑Fri Oct 23, 2020 10:49 pm at Fri Oct 23, 2020 10:49 pm
>
> 
Garbobby wrote: ↑Fri Oct 23, 2020 4:15 pm

You'll have to create the material yourself.

ah just a little bit of extra work then, tysm for helping
## Post #35
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2021-04-22T15:53:02+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from JosouKitsune ↑Sun Mar 15, 2020 4:38 am at Sun Mar 15, 2020 4:38 am
>
> 
I was doing my own script for Spike Chunsoft's fighting games that use the .npk format (OPBB/OPM), it extracted the textures and meshes in one go, but I was missing the bones and weights, so when Hiroshi released this I adapted a portion of his code into mine. So with his permission I'm posting my script to extract textures, models, bones, weights and Form Changes. Thanks Hiroshi without your code this wouldn't be possible.

The script supports OPBB PC and OPM PS4 .npk files, you need to have the uncompressed .npk, .npki and .npkv files in the same folder for this to work.






---------------------------------------------------UPDATE---------------------------------------------------

Added support for characters with more than 2 forms







---------------------------------------------------UPDATE---------------------------------------------------

Fixed some UVs issues

Hello there, it's been a while, I recently started looking at the OPBB files again and I found out there are more models with meshes that have messed up UV's, for example Timeskip Luffy's Jacket and Belt, it's character_022, would you be able to fix these as well? 
apologies for bothering and thank you in advance
## Post #36
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2021-05-11T22:30:05+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

> Reply from Eag1e ↑Thu Apr 22, 2021 11:53 pm at Thu Apr 22, 2021 11:53 pm
>
> 

Hello there, it's been a while, I recently started looking at the OPBB files again and I found out there are more models with meshes that have messed up UV's, for example Timeskip Luffy's Jacket and Belt, it's character_022, would you be able to fix these as well? 
apologies for bothering and thank you in advance

Sorry for the late response and update, just checked the site yesterday, the script is updated now.
[viewtopic.php?f=16&t=21863#p160926](https://forum.xentax.com/viewtopic.php?f=16&t=21863#p160926)
## Post #37
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2021-09-12T04:13:14+00:00
- Post Title: Re: Spike Chunsoft Games Scripts/Tools + Research

Hello there, I'm not sure if you guys are still updating the script?
I was wondering if it was possible to have the One Punch Man PC game supported to be able to get the DLC character's models more easily?
I've been trying to get them for a while now, especially Garou, but I haven't been able to find PS4 DLC files and I'm not even sure if the PS4 DLC files are supported ^^;
Sorry for bothering if this isn't possible to add right now, but thank you for what the scripts are able to do already right now!
