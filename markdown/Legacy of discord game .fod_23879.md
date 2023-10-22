## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-05-15T21:51:46+00:00
- Post Title: Legacy of discord game .fod

Hello! I was checking some info about decompress the .fod file that come with this game because it contain everything related to models! I found a bms script for open this kind of file but it fail at some point of the extraction and to be honest don't know where should I change to it can continue the extraction without throw that error, maybe anyone encountered this kind of error before and could help me with this? I'm gonna attach the .fod file and some other files that are in the game like a .foc file and the launcher. Thanks!   
[https://www.mediafire.com/file/i0wgth6s ... r.zip/file](https://www.mediafire.com/file/i0wgth6shuqbnyb/legacy_of_discord_launcher.zip/file)
[https://www.mediafire.com/file/vhryjl5r ... d.zip/file](https://www.mediafire.com/file/vhryjl5rdwwnu33/data_legacy_of_discord.zip/file)
BMS SCRIPT: [http://aluigi.org/bms/fancy3d.bms](http://aluigi.org/bms/fancy3d.bms)



legacyofdiscord.jpg (97.44 KiB) Viewed 380 times
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-20T18:07:17+00:00
- Post Title: Legacy of discord game .fod

Did you try to ask author for the script update?
## Post #3
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-05-20T19:22:13+00:00
- Post Title: Legacy of discord game .fod

> Reply from ikskoks ↑Fri May 21, 2021 2:07 am at Fri May 21, 2021 2:07 am
>
> 
Did you try to ask author for the script update?
Hello, yep. Sadly seems like him is not insterested, but he confirmed that the file is not encrypted.  :
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-06T16:16:04+00:00
- Post Title: Legacy of discord game .fod

> Reply from moonpaladin ↑Sun May 16, 2021 5:51 am at Sun May 16, 2021 5:51 am
>
> I found a bms script for open this kind of file but it fail at some point of the extraction and to be honest don't know where should I change to it can continue the extraction without throw that error
You'll need more than just changing a few lines of code. The contents extracted using that script usually don't match with their actual names coz they're not placed in the same order. So the script must be rewritten for this archive.
## Post #5
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-06-14T19:30:54+00:00
- Post Title: Legacy of discord game .fod

> Reply from Bigchillghost ↑Mon Jun 07, 2021 12:16 am at Mon Jun 07, 2021 12:16 am
>
> 
moonpaladin wrote: ↑Sun May 16, 2021 5:51 amI found a bms script for open this kind of file but it fail at some point of the extraction and to be honest don't know where should I change to it can continue the extraction without throw that error

You'll need more than just changing a few lines of code. The contents extracted using that script usually don't match with their actual names coz they're not placed in the same order. So the script must be rewritten for this archive.

ey Hello Bigchillghost! maybe that was the reason because Aluigi says he will not do it xD, at least the archive is not encrypted.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-15T17:33:16+00:00
- Post Title: Legacy of discord game .fod

Here's a BMS script for extracting the assets from the fod archive. It'll re-calculate the assets' hashes and try to match them with those recorded in the corresponding foc file. If it failed to find the matched hash, it'll try to match the file by its size. If none of these workarounds worked, the un-referenced assets in the fod will be extracted into an individual folder called "no_match". Just remember to pick the foc as input.
[lodUnpacker.zip](https://xentaxbackup.github.io/file/20309_lodUnpacker.zip)
## Post #7
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-06-27T17:44:34+00:00
- Post Title: Legacy of discord game .fod

> Reply from Bigchillghost ↑Wed Jun 16, 2021 1:33 am at Wed Jun 16, 2021 1:33 am
>
> 
Here's a BMS script for extracting the assets from the fod archive. It'll re-calculate the assets' hashes and try to match them with those recorded in the corresponding foc file. If it failed to find the matched hash, it'll try to match the file by its size. If none of these workarounds worked, the un-referenced assets in the fod will be extracted into an individual folder called "no_match". Just remember to pick the foc as input.

omggg, gonna try right now!!!!!    thank you
## Post #8
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-12T06:58:26+00:00
- Post Title: Legacy of discord game .fod

> Reply from Bigchillghost ↑Wed Jun 16, 2021 1:33 am at Wed Jun 16, 2021 1:33 am
>
> 
Hello Bigchillghost, I have been able to extract the assets from other fancy3d game, it have an foc and fod file too, but I saw that some models are not complete (just the textures and animation files),  not mesh (.skn). I searched in the "no_match" folder but nothing, is weird that is not in there because it appear in the game without problems, so dunno what exactly could be the problem. Is there any way I can download that file trought the cdn? because I were trying but seems that Im not pointing the correct direction. Please take a look when you have a spare time :') thanks for your time.  

[https://www.mediafire.com/file/fooqv3mi ... D.zip/file](https://www.mediafire.com/file/fooqv3mi06gxnu7/FANCY3D.zip/file)
## Post #9
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-04T07:01:33+00:00
- Post Title: Legacy of discord game .fod

> Reply from Bigchillghost ↑Wed Jun 16, 2021 1:33 am at Wed Jun 16, 2021 1:33 am
>
> 
Hello Bigchillghost!, could you please check this .skn models?, DKDave made a script for load this models and it work pretty well, my problem is that I encounter many models that are not in T-pose, so don't know if is possible to tweak a bit the script, like your shumenol script to load the model in certain frame, or that the script can load the skeleton that is in the .skl file, hope it can be possible, cause are some models that are in really weird position and is hard to put them in rest pose.    . Thanks in advance for your time! I'm attaching some samples + the script.

[https://www.mediafire.com/file/0xui3k31 ... S.zip/file](https://www.mediafire.com/file/0xui3k31hzgh41s/LOD_EXAMPLES.zip/file)
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-04T14:18:44+00:00
- Post Title: Legacy of discord game .fod

> Reply from moonpaladin ↑Tue Jan 04, 2022 3:01 pm at Tue Jan 04, 2022 3:01 pm
>
> 
cause are some models that are in really weird position and is hard to put them in rest pose
Don't know what you meant by "weird". Anyway here's one way to handle the skeleton data using ASH.



v_r002_skl.png (55.02 KiB) Viewed 208 times
## Post #11
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-04T15:57:48+00:00
- Post Title: Legacy of discord game .fod

> Reply from Bigchillghost ↑Tue Jan 04, 2022 10:18 pm at Tue Jan 04, 2022 10:18 pm
>
> 
Don't know what you meant by "weird".
I meant that in the rest pose, it appears as if it is jumping or running, things like that. 
I just used the tool you mention and it loads the skeleton  :surprise: , is any way to load the mesh bone weights? I could do it one by one if is necessary   . Thanks!
## Post #12
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2022-01-04T16:03:23+00:00
- Post Title: Legacy of discord game .fod

Thanks to Bigchillhhost's info, I've added the bones to my script.  Should do the weights correctly.  Still a few things to do, but that bit should work correctly now.


 legacy_of_discord_skn.zip
(1.57 KiB) Downloaded 31 times
## Post #13
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-04T16:13:27+00:00
- Post Title: Legacy of discord game .fod

> Reply from DKDave ↑Wed Jan 05, 2022 12:03 am at Wed Jan 05, 2022 12:03 am
>
> 
Thanks to Bigchillhhost's info, I've added the bones to my script.  Should do the weights correctly.  Still a few things to do, but that bit should work correctly now.

legacy_of_discord_skn.zip

Thanks alot DKDave!
## Post #14
- Username: Cyn
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 03, 2022 11:12 am
- Post datetime: 2022-11-07T05:48:18+00:00
- Post Title: Legacy of discord game .fod

Hello

I wanted to add my light-research on the .san files that are used to store animation data.
Each .san file contains data for 1 specific animation, they do not reference vertex groups by name, the do however describe each individual vertex group, the number of timestamps/keyframes, and defines 1 Vector (Translation XYZ) and 2 quarternions (One is surely rotation, not sure what the other two bytes are doing. For example: "model_90001_lv4" being our model in question currently defines 34 bones, only 22 groups are referenced. in the "std" (Stand) animation there are 5 keys for each group, and each group is only referenced by an index.

This index appears to be built right after the actual bone data. There are only 22 groups seemingly due to the "mirrored" bones in the structure, it seems to be implied (i believe on a flag before the bone names) when bones are "linked" and share animations on a mirrored axis, this may make automatic generation of animations difficult, thankfully the .san files seem to be fairly simple
## Post #15
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-03-30T06:29:19+00:00
- Post Title: Legacy of discord game .fod

> Reply from DKDave ↑Wed Jan 05, 2022 12:03 am at Wed Jan 05, 2022 12:03 am
>
> 
Thanks to Bigchillhhost's info, I've added the bones to my script.
Hello DKDave! sorry for the pin   , I have updated the game and tried to get some models and seems that have been changed a bit, would you mind in update the script please?, It doesn't throw error but the model looks invisible, like it is miscalculating a value.  

[https://www.mediafire.com/file/84eb77xw ... ES.7z/file](https://www.mediafire.com/file/84eb77xwn6hlu33/LOD_UPDATE_SAMPLES.7z/file)
## Post #16
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-09-16T00:45:19+00:00
- Post Title: Re: Legacy of discord game .fod

> Reply from DKDave ↑Wed Jan 05, 2022 12:03 am at Wed Jan 05, 2022 12:03 am
>
> 
Thanks to Bigchillhhost's info, I've added the bones to my script.  Should do the weights correctly.
Hello DKDave! could you please take a look at the new samples?
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-09-19T18:48:28+00:00
- Post Title: Re: Legacy of discord game .fod

He moved to the discord server, didn't he?
## Post #18
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-09-20T13:57:56+00:00
- Post Title: Re: Legacy of discord game .fod

> Reply from shakotay2 ↑Wed Sep 20, 2023 2:48 am at Wed Sep 20, 2023 2:48 am
>
> 
He moved to the discord server, didn't he?
Like the majority, yes, then they wonder why the forum is not active, oh well.
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-09-21T07:46:10+00:00
- Post Title: Re: Legacy of discord game .fod

> Reply from mono24 ↑Wed Sep 20, 2023 9:57 pm at Wed Sep 20, 2023 9:57 pm
>
> 
, then they wonder why the forum is not active, oh well.I don't think it's simple "cause and effect". For some reason discords are very popular nowadays among the young folks while forums start to die.
So what I mean: the forums start to die and discords were a welcome substitute.

Plus, I guess, discords require less efforts.
## Post #20
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-09-22T01:59:19+00:00
- Post Title: Re: Legacy of discord game .fod

> Reply from shakotay2 ↑Wed Sep 20, 2023 2:48 am at Wed Sep 20, 2023 2:48 am
>
> 
He moved to the discord server, didn't he?
Hi shakotay2, he post on forum too! but maybe he is busy
