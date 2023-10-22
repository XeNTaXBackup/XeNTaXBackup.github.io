## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-09-09T16:57:49+00:00
- Post Title: Dragon Raja Mesh Importor & Texture Convertor

A Python script for importing skeletal/static meshes and skeletons into Noesis, or converting textures to pvr format. Compatible with uasset files from old version and newer version (where actual data is stored in uexp or ubulk files).


 fmt_DragonRaja_uasset.zip
Updated 2020.04.05 (2.89 KiB) Downloaded 499 times



Instructions:

1. Base packages. Download the obb packages, and unpack the patch obb archive for global version, or the png archives in the res_base folder for Chinese version, with the following QuickBMS script: png/obb unpacker

2. Install the game and download the in-game updates. Copy the following files from the ingameupdate folder: iguf_**.dat, and saved_download_entry.dat. And unpack them with this BMS script: iguf unpacker

3. Merge the extracted files from the above steps. Pay attention to the shared path in case you do it wrong. 

4. Use the Noesis script for assets convertion.


Further notes:
All supported assets are accessed through the uasset files, and for the released version of the game only those with a uexp or/and a ubulk file are supported. The uexp and ubulk files are filtered merely to inform of the files with pair assets.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-09-09T17:00:04+00:00
- Post Title: Dragon Raja Mesh Importor & Texture Convertor

Example:



luoli.png (81.67 KiB) Viewed 2778 times



The skin weights might still have some issues though.
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-09-09T17:14:50+00:00
- Post Title: Dragon Raja Mesh Importor & Texture Convertor

Almost forgot. Get the png unpacker [here](https://forum.xentax.com/viewtopic.php?f=16&t=20716#p154109).
## Post #4
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-09-09T20:06:25+00:00
- Post Title: Dragon Raja Mesh Importor & Texture Convertor

Just tried this out of curiosity with some random KH3 characters and skeletons import excellently while meshes are welcomed with a wall of errors, but nice work as always.
## Post #5
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-10T03:42:26+00:00
- Post Title: Dragon Raja Mesh Importor & Texture Convertor

How to convert this PVR
## Post #6
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-09-10T07:44:27+00:00
- Post Title: Dragon Raja Mesh Importor & Texture Convertor

> Reply from lkw019 ↑Tue Sep 10, 2019 11:42 am at Tue Sep 10, 2019 11:42 am
>
> 
How to convert this PVR
Try Noesis or PVRTexTool.
## Post #7
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-11T03:22:12+00:00
- Post Title: Dragon Raja Mesh Importor & Texture Convertor

> Reply from mono24 ↑Tue Sep 10, 2019 3:44 pm at Tue Sep 10, 2019 3:44 pm
>
> 
lkw019 wrote: ↑Tue Sep 10, 2019 11:42 am
How to convert this PVR

Try Noesis or PVRTexTool.

The data package of the game is incomplete. Can you upload the complete data package?
## Post #8
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-11T04:54:35+00:00
- Post Title: Dragon Raja Mesh Importor & Texture Convertor

> Reply from mono24 ↑Tue Sep 10, 2019 3:44 pm at Tue Sep 10, 2019 3:44 pm
>
> 
lkw019 wrote: ↑Tue Sep 10, 2019 11:42 am
How to convert this PVR

Try Noesis or PVRTexTool.

Or teach me how to get the complete data package. I can see 3.6G files in the simulator, but the DAT format files - iguf_00 and iguf_01 (a total of 3.6G)
## Post #9
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-12T16:35:21+00:00
- Post Title: Dragon Raja Mesh Importor & Texture Convertor

Thank you for your script. Most of the files are OK, but some of them are not exported.
## Post #10
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-12T17:45:07+00:00
- Post Title: Dragon Raja Mesh Importor & Texture Convertor

> Reply from Bigchillghost ↑Tue Sep 10, 2019 12:57 am at Tue Sep 10, 2019 12:57 am
>
> 
A Python script for importing skeletal meshes and skeletons into Noesis, or converting textures to pvr format. Compatible with uasset files from old version and newer version (where actual data is stored in uexp or ubulk files).

How to get complete data package resources?
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-09-13T02:04:32+00:00
- Post Title: Dragon Raja Mesh Importor & Texture Convertor

> Reply from lkw019 ↑Fri Sep 13, 2019 1:45 am at Fri Sep 13, 2019 1:45 am
>
> 
How to get complete data package resources?
I personally don't care since I'm not interested in the game. But guess you'll have to download these data during game play or after installing it.
## Post #12
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-15T15:35:55+00:00
- Post Title: Dragon Raja Mesh Importor & Texture Convertor

Who can help attach the complete resource data package? I have been unable to find the complete data package in the simulator.
## Post #13
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-09-15T23:42:32+00:00
- Post Title: Dragon Raja Mesh Importor & Texture Convertor

> Reply from lkw019 ↑Sun Sep 15, 2019 11:35 pm at Sun Sep 15, 2019 11:35 pm
>
> I have been unable to find the complete data package in the simulator.
Assuming you meant to say emulator, which one your using?
## Post #14
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-16T02:18:08+00:00
- Post Title: Dragon Raja Mesh Importor & Texture Convertor

> Reply from mono24 ↑Mon Sep 16, 2019 7:42 am at Mon Sep 16, 2019 7:42 am
>
> 
lkw019 wrote: ↑Sun Sep 15, 2019 11:35 pmI have been unable to find the complete data package in the simulator.
Assuming you meant to say emulator, which one your using?

Actually, I just wanted to know how you got the data. I only found iguf_00 and iguf_01.dat.
## Post #15
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-16T13:06:51+00:00
- Post Title: Dragon Raja Mesh Importor & Texture Convertor

> Reply from mono24 ↑Mon Sep 16, 2019 7:42 am at Mon Sep 16, 2019 7:42 am
>
> 
lkw019 wrote: ↑Sun Sep 15, 2019 11:35 pmI have been unable to find the complete data package in the simulator.
Assuming you meant to say emulator, which one your using?

Can you help me? I checked the root directory through ROOT in the game simulator and found only iguf_00 and iguf_01.dat. (3.7G files in total)
## Post #16
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-16T13:23:48+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

APK Download Address

[https://dna.qq.com/web201812/main.shtml](https://dna.qq.com/web201812/main.shtml)
## Post #17
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-09-16T16:58:58+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

You need to quit with this ridiculous spamming, learn to edit your last post since no one else replied, no need to make post after post to say something, what a mess.

Looks like your using the PC version.
I asked what emulator your using so we know what path to look for, not sure how different they are, because if you use NOX you need to locate the following folder com.tencent.lzhx and then you can access all the data you  need.
## Post #18
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-09-18T03:20:49+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Unpacker for downloaded data files (*.dat).


 DragonRajaUnpacker_DAT.zip
(834 Bytes) Downloaded 364 times


Note:
1. Place all "iguf_**.dat" files along with "saved_download_entry.dat" in the same path. 
2. Select "saved_download_entry.dat" as the input archive. The script opens it compulsively anyway in case you get the wrong file opened.
3. Keep the output location the same as the input.
## Post #19
- Username: thebannok
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 19, 2019 6:50 am
- Post datetime: 2019-09-19T03:19:36+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

How to. Repack it. To .dat files? I want to retranslate
Some string tex from chinese to eng
## Post #20
- Username: douchi
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 29, 2019 10:24 pm
- Post datetime: 2019-09-29T14:51:27+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Hello, I used your noesisv script to import the scene files in the library. I found that most of the file exports failed. I wondered if you could help update the scene script. I am grateful. I am sorry that my English is not good. I use translation software
Sample File：[https://pan.baidu.com/s/1gRkzQo-msMKV8RcvZrkp8A](https://pan.baidu.com/s/1gRkzQo-msMKV8RcvZrkp8A)    Extract Password:   4aps 

Network disk for the Chinese network disk, if you can not access, please let me know.

I hope to have your help again.
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-10-18T05:53:31+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

A Noesis importer for uexp files containing static meshes like items and scene objects.

Edit: no longer necessary.
## Post #22
- Username: luciferdm
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 20, 2015 10:08 am
- Post datetime: 2020-01-19T08:10:51+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

when I use the script  "DragonRajaUnpacker_DAT" to extract the  downloaded  .dat  file , I get the error  like this "- error  in src\file.c  line 557:fdnum_open()  Error: No such file or directory"
## Post #23
- Username: Quizas30
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 03, 2018 7:44 am
- Post datetime: 2020-03-02T00:57:28+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from luciferdm ↑Sun Jan 19, 2020 4:10 pm at Sun Jan 19, 2020 4:10 pm
>
> 
when I use the script  "DragonRajaUnpacker_DAT" to extract the  downloaded  .dat  file , I get the error  like this "- error  in src\file.c  line 557:fdnum_open()  Error: No such file or directory"

I had the same problem, just extract the files in the same location of the .dat, dont choose another location
## Post #24
- Username: Quizas30
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 03, 2018 7:44 am
- Post datetime: 2020-03-02T02:28:20+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

hey guys, idk if this happend to someone else, but it pop up an error saying "File could not be preview" someone have any idea what im doing wrong? i have the lastest version of noesis, and im using the file to import the mesh
## Post #25
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-03-02T10:11:16+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from Quizas30 ↑Mon Mar 02, 2020 10:28 am at Mon Mar 02, 2020 10:28 am
>
> 
hey guys, idk if this happend to someone else, but it pop up an error saying "File could not be preview" someone have any idea what im doing wrong?
Either you were trying to open the wrong file or the uasset file doesn't have its paired uexp file.
## Post #26
- Username: akanesus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 10, 2018 8:16 am
- Post datetime: 2020-03-03T03:39:58+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

heya! i feel as though i am missing a crucial step and i'm hoping someone can tell me what i missed? managed to get the bms script running and files have been extracted but i'm getting .uexp files under the models and no .uasset. what exactly do i do with the .uexp files in order to view the model?
## Post #27
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-03-03T04:09:22+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Probably you need to download the files in game or they've changed the structure, who knows.
## Post #28
- Username: leecher85
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 20, 2020 6:30 pm
- Post datetime: 2020-03-03T17:15:04+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from akanesus ↑Tue Mar 03, 2020 11:39 am at Tue Mar 03, 2020 11:39 am
>
> 
heya! i feel as though i am missing a crucial step and i'm hoping someone can tell me what i missed?

the storing system for this game gives me cancer
some files are in the .obb others are in the ".png" and finally there are some in the iguf files
you need to extract and merge all of them to be able to do something
## Post #29
- Username: akanesus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 10, 2018 8:16 am
- Post datetime: 2020-03-03T21:21:33+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from leecher85 ↑Wed Mar 04, 2020 1:15 am at Wed Mar 04, 2020 1:15 am
>
> 
akanesus wrote: ↑Tue Mar 03, 2020 11:39 am
heya! i feel as though i am missing a crucial step and i'm hoping someone can tell me what i missed? 


the storing system for this game gives me cancer
some files are in the .obb others are in the ".png" and finally there are some in the iguf files
you need to extract and merge all of them to be able to do something

ah jfc. thanks for the heads up lol i'll give them a look
## Post #30
- Username: akanesus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 10, 2018 8:16 am
- Post datetime: 2020-03-07T20:01:11+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from leecher85 ↑Wed Mar 04, 2020 1:15 am at Wed Mar 04, 2020 1:15 am
>
> 
akanesus wrote: ↑Tue Mar 03, 2020 11:39 am
heya! i feel as though i am missing a crucial step and i'm hoping someone can tell me what i missed? 


the storing system for this game gives me cancer
some files are in the .obb others are in the ".png" and finally there are some in the iguf files
you need to extract and merge all of them to be able to do something
would you happen to know how exactly to extract from the .obb?
## Post #31
- Username: reydria
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 06, 2020 9:06 am
- Post datetime: 2020-03-13T09:14:52+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from akanesus ↑Sun Mar 08, 2020 4:01 am at Sun Mar 08, 2020 4:01 am
>
> 
leecher85 wrote: ↑Wed Mar 04, 2020 1:15 am
akanesus wrote: ↑Tue Mar 03, 2020 11:39 am
heya! i feel as though i am missing a crucial step and i'm hoping someone can tell me what i missed? 


the storing system for this game gives me cancer
some files are in the .obb others are in the ".png" and finally there are some in the iguf files
you need to extract and merge all of them to be able to do something

would you happen to know how exactly to extract from the .obb?

You can use something like, 7zip to extract obb just can’t use windows default
## Post #32
- Username: akanesus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 10, 2018 8:16 am
- Post datetime: 2020-03-13T17:50:27+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from reydria ↑Fri Mar 13, 2020 5:14 pm at Fri Mar 13, 2020 5:14 pm
>
> 


You can use something like, 7zip to extract obb just can’t use windows default

that's what i thought but i get an error saying the main obb cannot be extracted as an archive :/ so i'm guessing they must have done something to it, possibly.
## Post #33
- Username: ophy111
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Dec 08, 2016 3:39 pm
- Post datetime: 2020-03-25T01:40:19+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

EDIT: can confirm the same errors happen with chinese ver. maybe something changed in the .uexp that the noesis plugin doesn't work anymore?


I used these tools to extract fine but there are no other .assets. Whats left for the majority of model data are in the .uexp files. I'm wondering if it's because the global ver and chinese ver are not the same? Can anyone confirm if there's a difference?
## Post #34
- Username: DonSkook
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 05, 2020 10:35 am
- Post datetime: 2020-04-05T04:09:30+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Is it normal that the extracted folder is over 30gb? 

It seems a bit excessive, considering the game is about 4gb.
## Post #35
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-04-05T16:19:29+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from DonSkook ↑Sun Apr 05, 2020 12:09 pm at Sun Apr 05, 2020 12:09 pm
>
> 
Is it normal that the extracted folder is over 30gb? 

It seems a bit excessive, considering the game is about 4gb.

I don't know how you did it, but the total size of all the unpacked data is 11.5 GB or so, including 3.55 GB for the patch obb archive, and 7.96 GB for the two iguf packages. Tested on version 1.0.57.
## Post #36
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-04-05T16:21:11+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Update for Noesis script:
1. Added support for ETC2 RGB/RGBA texture formats for global version game;
2. Added support for static meshes.
## Post #37
- Username: DonSkook
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 05, 2020 10:35 am
- Post datetime: 2020-04-05T19:53:52+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> including 3.55 GB for the patch obb archive

The patch archive I have is about 1.48gb obb file. I guess that's my problem, either it's incomplete or I just can't open it.
## Post #38
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-04-06T02:31:27+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from DonSkook ↑Mon Apr 06, 2020 3:53 am at Mon Apr 06, 2020 3:53 am
>
> 
The patch archive I have is about 1.48gb obb file. I guess that's my problem, either it's incomplete or I just can't open it.
You get to unpack it with the BMS script to reach 3.55 GB. Still, it didn't explain how you generate 30 GB of data.
## Post #39
- Username: DonSkook
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 05, 2020 10:35 am
- Post datetime: 2020-04-06T23:49:57+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from Bigchillghost ↑Mon Apr 06, 2020 10:31 am at Mon Apr 06, 2020 10:31 am
>
> 
DonSkook wrote: ↑Mon Apr 06, 2020 3:53 am
The patch archive I have is about 1.48gb obb file. I guess that's my problem, either it's incomplete or I just can't open it.

You get to unpack it with the BMS script to reach 3.55 GB. Still, it didn't explain how you generate 30 GB of data.

Perhaps because I selected all the .dat files in the BMS script. So it extracted all of them again and again (although I didn't see the difference in files)

If I select only one file, saved_download_entry.dat, it extracts into a more reasonable ~12gb
## Post #40
- Username: Wassep
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 08, 2020 10:34 am
- Post datetime: 2020-05-08T03:43:02+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Hello, I tried to run NOX and couldn't find the com.tencent.lzhx folder. Could anyone possibly rip the Black Cats Kiss outfit for male avi please.
## Post #41
- Username: ofkings
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Jan 01, 2018 7:16 am
- Post datetime: 2020-06-16T12:21:56+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Hello! i extract it wit quickbms, but now i cant preview models in Noesis

And someone got World of Kings to work?
[https://prnt.sc/t0qeq0](https://prnt.sc/t0qeq0)
## Post #42
- Username: shard
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 19, 2020 7:25 am
- Post datetime: 2020-06-17T17:30:12+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from ofkings ↑Tue Jun 16, 2020 8:21 pm at Tue Jun 16, 2020 8:21 pm
>
> 
Hello! i extract it wit quickbms, but now i cant preview models in Noesis

And someone got World of Kings to work?
https://prnt.sc/t0qeq0

I have the same problem, just few models working
## Post #43
- Username: WhatUserName
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jul 10, 2020 2:41 am
- Post datetime: 2020-08-11T22:52:28+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Is there an easy way to extract the contents in batches? Noesis only allows in single files. And umodel doesn't want to extract it because of "missing" files.
## Post #44
- Username: kindland2009
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 13, 2015 10:53 am
- Post datetime: 2020-08-23T13:35:21+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Has anyone yet figured yet if is working or not, i can't seem to make it work, and the game has such beautiful model to play with
## Post #45
- Username: Vajuras
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri May 17, 2019 8:16 am
- Post datetime: 2020-08-24T01:44:24+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

I'm able to get the meshes but how can I get the textures from the .uasset/uexp files?

Edit: Was able to get the textures but I'm kinda a noob at this. What do I do with this texture?
[t_male_weiyi_yurong_tint.png](https://xentaxbackup.github.io/file/18653_t_male_weiyi_yurong_tint.png)
## Post #46
- Username: WhatUserName
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jul 10, 2020 2:41 am
- Post datetime: 2020-08-29T04:11:04+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from Vajuras ↑Mon Aug 24, 2020 9:44 am at Mon Aug 24, 2020 9:44 am
>
> 
I'm able to get the meshes but how can I get the textures from the .uasset/uexp files?

Edit: Was able to get the textures but I'm kinda a noob at this. What do I do with this texture?

What settings did you use to extract the textures?
## Post #47
- Username: Vajuras
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri May 17, 2019 8:16 am
- Post datetime: 2020-08-31T23:29:15+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from WhatUserName ↑Sat Aug 29, 2020 12:11 pm at Sat Aug 29, 2020 12:11 pm
>
> 
Vajuras wrote: ↑Mon Aug 24, 2020 9:44 am
I'm able to get the meshes but how can I get the textures from the .uasset/uexp files?

Edit: Was able to get the textures but I'm kinda a noob at this. What do I do with this texture?


What settings did you use to extract the textures?

I just used noesis to extract it to .pvr and opened it with PVRTexTool to save it as .png
## Post #48
- Username: WhatUserName
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jul 10, 2020 2:41 am
- Post datetime: 2020-09-13T02:44:32+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from Vajuras ↑Tue Sep 01, 2020 7:29 am at Tue Sep 01, 2020 7:29 am
>
> 
WhatUserName wrote: ↑Sat Aug 29, 2020 12:11 pm
Vajuras wrote: ↑Mon Aug 24, 2020 9:44 am
I'm able to get the meshes but how can I get the textures from the .uasset/uexp files?

Edit: Was able to get the textures but I'm kinda a noob at this. What do I do with this texture?


What settings did you use to extract the textures?


I just used noesis to extract it to .pvr and opened it with PVRTexTool to save it as .png

Hey, I forgot to tell you but you can still use umodel for the textures. Just make sure to set it to unreal 4.20
## Post #49
- Username: ナット
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 08, 2020 11:03 pm
- Post datetime: 2020-09-14T05:23:11+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from Bigchillghost ↑Tue Sep 10, 2019 12:57 am at Tue Sep 10, 2019 12:57 am
>
> 
A Python script for importing skeletal/static meshes and skeletons into Noesis, or converting textures to pvr format. Compatible with uasset files from old version and newer version (where actual data is stored in uexp or ubulk files).
fmt_DragonRaja_uasset.zip


Instructions:

1. Base packages. Download the obb packages, and unpack the patch obb archive for global version, or the png archives in the res_base folder for Chinese version, with the following QuickBMS script: png/obb unpacker

2. Install the game and download the in-game updates. Copy the following files from the ingameupdate folder: iguf_00.dat, iguf_01.dat, and saved_download_entry.dat. And unpack them with this BMS script: iguf unpacker

3. Merge the extracted files from the above steps. Pay attention to the shared path in case you do it wrong. 

4. Use the Noesis script for assets convertion.


Further notes:
All supported assets are accessed through the uasset files, and for the released version of the game only those with a uexp or/and a ubulk file are supported. The uexp and ubulk files are filtered merely to inform of the files with pair assets.

When I try to export an .uexp file noesis said that the file couldnt be determined. Can someone tell me why does this happen and how can I fix it?

I got the Python script
## Post #50
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-09-14T10:26:21+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from ナット ↑Mon Sep 14, 2020 1:23 pm at Mon Sep 14, 2020 1:23 pm
>
> 
When I try to export an .uexp file noesis said that the file couldnt be determined. Can someone tell me why does this happen and how can I fix it?
You quoted, but never read, did you?!!
## Post #51
- Username: zxhxy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 08, 2020 4:27 pm
- Post datetime: 2020-10-23T02:14:43+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Error message while using the "DragonRajaUnpacker_DAT" script to unpack the latest version:

Last script line before the error or that produced the error:10 get Len short

So what happens in this case?
## Post #52
- Username: dongch007
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 24, 2017 3:56 pm
- Post datetime: 2021-01-28T08:53:47+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Hi，I have a game developed by same company with Dragon Raja.
Sorry I dont know it's english name. [https://war.qq.com/](https://war.qq.com/)
Can download here [https://war.qq.com/zlkdatasys/mct/d/pla ... ce=android](https://war.qq.com/zlkdatasys/mct/d/play.shtml?device=android)

I use DragonRajaUnpacker.bms extract .png file, but can not open with UEViewer. UEViewer can not detect uasset's engine version.
How can I know is the extract is sucessful or they changed file format?
## Post #53
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-01-28T21:18:01+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from dongch007 ↑Thu Jan 28, 2021 4:53 pm at Thu Jan 28, 2021 4:53 pm
>
> ...but can not open with UEViewer. UEViewer can not detect uasset's engine version.
How can I know is the extract is sucessful or they changed file format?
Noesis works just fine, no clue about why textures wont load though, must be different:
## Post #54
- Username: muze10118
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 29, 2021 8:29 pm
- Post datetime: 2021-02-13T13:29:59+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Hi, there! I have dumb questions.
How to merge the extracted files?
Where to put the files in what path?

I think I made a mistake in step3. Maybe.
I got the model resource, but it cannot be opened.

Sorry, My English is poor.
But I would like to know how to extract the model of this game.
## Post #55
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-25T04:47:01+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from Bigchillghost ↑Tue Sep 10, 2019 12:57 am at Tue Sep 10, 2019 12:57 am
>
> 
Instructions:

1. Base packages. Download the obb packages, and unpack the patch obb archive for global version, or the png archives in the res_base folder for Chinese version, with the following QuickBMS script: png/obb unpacker

2. Install the game and download the in-game updates. Copy the following files from the ingameupdate folder: iguf_00.dat, iguf_01.dat, and saved_download_entry.dat. And unpack them with this BMS script: iguf unpacker

3. Merge the extracted files from the above steps. Pay attention to the shared path in case you do it wrong. 

4. Use the Noesis script for assets convertion.

Hello! thanks @Bigchillghost! I extracted the game files, some models working correctly but other have a very small file size, same for textures, this is normal or I did something wrong extracting them? I did exactly what was wrote :'(.
[error28.png](https://xentaxbackup.github.io/file/19951_error28.png)
## Post #56
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-04-25T10:13:08+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from moonpaladin ↑Sun Apr 25, 2021 12:47 pm at Sun Apr 25, 2021 12:47 pm
>
> I did exactly what was wrote
I see no uexp nor ubulk files for most uassets in your screenshot. Did you unpack all the iguf files?
## Post #57
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-25T16:39:57+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Gonna unpack them again, maybe it didn't update correctly!Thanks Bigchillghost
## Post #58
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-26T01:16:17+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from Bigchillghost ↑Sun Apr 25, 2021 6:13 pm at Sun Apr 25, 2021 6:13 pm
>
> 
moonpaladin wrote: ↑Sun Apr 25, 2021 12:47 pmI did exactly what was wrote

I see no uexp nor ubulk files for most uassets in your screenshot. Did you unpack all the iguf files?

Hello Bigchillghost! well I reinstall the entire game and got "iguf_00.dat", "iguf_01.dat", iguf_02.dat, iguf_03.dat, saved_download_entry.dat, and 1-6 spif_dm_0.dat that are 1 bytes. I were checking the files and it seems that the saved_download_entry.dat is like a listfile, because I unpacked all those .dat files and all contained the same files without any difference. All was good, next step is merging the extracted files with the .obb files, so at this point I encounter a mismatch because the obb files contain more than the extracted files of the .dat, and it happens in all other folders, not only in the mounts. What can be the problem? I updated the game, I were playing a while and no other download appears, maybe I could add the missing models to the path of saved_download_entry.dat? XD.  


error29.png (74.84 KiB) Viewed 147 times
## Post #59
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-04-26T04:34:54+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from moonpaladin ↑Mon Apr 26, 2021 9:16 am at Mon Apr 26, 2021 9:16 am
>
> 
I were checking the files and it seems that the saved_download_entry.dat is like a listfile, because I unpacked all those .dat files and all contained the same files without any difference.
Yes, the iguf files contain the actual data and that's why you should place all iguf dat files in the same folder, along with the entry file. There's no point in "unpacking" every iguf manually, coz you'd be actually unpacking it over and over again.

> Reply from moonpaladin ↑Mon Apr 26, 2021 9:16 am at Mon Apr 26, 2021 9:16 am
>
> at this point I encounter a mismatch because the obb files contain more than the extracted files of the .dat, and it happens in all other folders, not only in the mounts. What can be the problem?
Why'd it be a problem? As long as you can see there're shared directories in both sides you'll know you're doing things correctly.
## Post #60
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-26T04:41:58+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Why'd it be a problem? As long as you can see there're shared directories in both sides you'll know you're doing things correctly.
Well, some models cannot be exported. It seems that obb is version 1.26 and the game is at the 1.25, maybe is for that, that some models are not listed in the .dat file yet.
## Post #61
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-04-26T05:11:51+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from moonpaladin ↑Mon Apr 26, 2021 12:41 pm at Mon Apr 26, 2021 12:41 pm
>
> 
It seems that obb is version 1.26 and the game is at the 1.25
That's not a problem if you were using the same apk for installation.

> Reply from moonpaladin ↑Mon Apr 26, 2021 12:41 pm at Mon Apr 26, 2021 12:41 pm
>
> 
maybe is for that, that some models are not listed in the .dat file yet.
Interesting theory. But that's highly unlikely. If the information is not recorded in the entry, there's no way to tell what a piece of data in the iguf is for, let alone tracking it when you feel the need for it.
## Post #62
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-26T05:37:39+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> That's not a problem if you were using the same apk for installation.
>
> moonpaladin wrote: ↑Mon Apr 26, 2021 12:41 pm 
>
> maybe is for that, that some models are not listed in the .dat file yet.

Hmmm, I tried to install the .xapk from apkpure but it failed, so I download it from playstore. The .obb is exactly the same as the one from apkpure (v1.26), but the version that show ingame its v1.25. I'm gonna wait an update and let see if my theory is correct, otherwise gonna add new entrys to the listfile or make a new one with the models that are not listed, just for test.   . Thanks for the script!
## Post #63
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-27T06:27:09+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> That's not a problem if you were using the same apk for installation.

Bigchillghost! sorry for the pin xD, I were trying to install the chinese apk, and I was able to do that, but when I tried to launch the game application it thrown a bluestack error, maybe do you know why this happens? I were trying some methods but 0 results.   .I'm using windows 7 and got the .apk from here. [https://dna.qq.com/act/1321/a20190618xzz/index.shtml](https://dna.qq.com/act/1321/a20190618xzz/index.shtml)

Thanks!



error29.png (13.56 KiB) Viewed 257 times
## Post #64
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-27T07:58:54+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

To be honest are many models that have not their corresponding uexp or ubulk file, in case of swords like 50% have not.    (Dragon Raja Global from playstore), and some models throw this error, hope you can take a look when you a little time @Bigchillghost . Thank you  

[https://www.mediafire.com/file/r6ucehac ... n.zip/file](https://www.mediafire.com/file/r6ucehacehkw6b0/sword_halloween.zip/file)



error30.png (19.16 KiB) Viewed 250 times
## Post #65
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-28T00:54:02+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from Bigchillghost ↑Mon Apr 26, 2021 1:11 pm at Mon Apr 26, 2021 1:11 pm
>
> 
It seems that obb is version 1.26 and the game is at the 1.25
Well I were able to get the chinese files, at my surprise it has less models than the global and it have the same issue the files extracted of the .dat updates are less than the ones extracted of the models.png, and for my lucky the whale mount that I want,  got not extracted xD. My guess is that is more updates in certain stages of the game, so I need to force all the downloads at the start, gonna be checking how to do it and about the error of the top is still happening in some models. 




error31.png (12.12 KiB) Viewed 235 times
## Post #66
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-28T03:43:54+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Finally I got all the files! I were playing for some hours xD
## Post #67
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-28T06:48:42+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Hello @Bigchillghost, if it helps here are more examples of models that throw error in noesis.  Thanks!

[https://www.mediafire.com/file/f1jf52vw ... s.zip/file](https://www.mediafire.com/file/f1jf52vw70gqq8o/examples.zip/file)
## Post #68
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-02T14:54:12+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Here's the patched script:


 fmt_DragonRaja_uasset.zip
(2.91 KiB) Downloaded 100 times
## Post #69
- Username: Loki2210
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Mar 09, 2019 11:02 pm
- Post datetime: 2021-05-13T19:35:37+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Does anyone of you know why you can't unpack the model.png from the china version anymore? Everytime i try it i become this Error:
[](https://ibb.co/wgMTPdz)
## Post #70
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-14T11:17:49+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

> Reply from Loki2210 ↑Fri May 14, 2021 3:35 am at Fri May 14, 2021 3:35 am
>
> 
Does anyone of you know why you can't unpack the model.png from the china version anymore? Everytime i try it i become this Error
Works fine on my end. In my case the model.png unpacked from the apk is 481 MB whereas in your screenshot that offset indicates the file is over 2 GB. That's not possible. Where did you get that png anyway? As far as I remember there's no png after installating the game.
## Post #71
- Username: Loki2210
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Mar 09, 2019 11:02 pm
- Post datetime: 2021-05-14T21:25:34+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

in the ES Data Explorer in the Files from the App and then Package are the PNG's
[](https://ibb.co/K5tdvXB)

If you want i can upload the File so that you can have a look at it
## Post #72
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-15T06:35:15+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Well it appears that the whole png is split into two parts. Just merge models.png and models.pk1.png into a single png by running

```
copy /b models.png + models.pk1.png models_merged.png
```
 in CMD and try again.
## Post #73
- Username: Loki2210
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Mar 09, 2019 11:02 pm
- Post datetime: 2021-05-15T19:10:47+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Works like a charm! Thank you for the Help
## Post #74
- Username: Dara
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 20, 2021 8:54 am
- Post datetime: 2021-05-21T02:31:41+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Hi,
I tried to unzip the patch obb file but getting this error. I've tried to download the obb from different sources as well but still ended up the same. Anyone know why?
[Error.png](https://xentaxbackup.github.io/file/20175_Error.png)
## Post #75
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-21T03:53:57+00:00
- Post Title: Re: Dragon Raja Mesh Importor & Texture Convertor

Coz it's not a zip file. Read the first instruction in the first post.
