## Post #1
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-24T09:54:07+00:00
- Post Title: Immortal Fenyx Rising .forge

[](https://imgbb.com/)

[](https://ibb.co/BZChMCp)

I know this isnt right but i was looking for away to unpack this game. I see it has the header "scimitar" and I tried using the script on the files but it turned up nothing but some raw data. Looking at it here in Archive Next I see it does read the names like the output files in the script but still cant parse the data. Is there any chance this could be modified to work. Seems like its not encrypted just  not being properly read. I am known to be wrong about this though. 
[](https://ibb.co/LgwBG3Q)
These files work with errors but the others in red fail entirely. Even the 1st one up top which i know sucks but i did upload for research along with a .forge that could read kinda with the scimitar script and Archive Next. The main ones seem to be 1GB to 3GB in size and all these small ones do have LOD0 in them but not sure if the others can be read the same. Any help is appreciated. I hope it is a title we are able to archive. 

Thank you.
## Post #2
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-10T04:27:17+00:00
- Post Title: Immortal Fenyx Rising .forge

ok after months i got something. 
[](https://ibb.co/VV1mYQX)
vertices 
[](https://ibb.co/HKFJq1V)
uv's
[](https://ibb.co/cbQCbFQ)
having issues with faces though. never seen them laid out this way if anyone could assist me ?
[12651.zip](https://xentaxbackup.github.io/file/21360_12651.zip)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-10T07:41:16+00:00
- Post Title: Immortal Fenyx Rising .forge

Dunno, which issues you could mean, it just looks like this for me:
.



Hair-12651.png (44.7 KiB) Viewed 381 times

(well, has to be mirrored horizontally, because it's cyclops' beard  )
Face indices count is 22434, count of vertices is 5074.
## Post #4
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-10T11:38:48+00:00
- Post Title: Immortal Fenyx Rising .forge

WOW. how did you find the correct face offset ? Thanks a lot for helping. I see my data was off by your counts. Do you think this is readable by Noesis script ?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-10T13:14:48+00:00
- Post Title: Immortal Fenyx Rising .forge

> Reply from Sharppy ↑Fri Dec 10, 2021 7:38 pm at Fri Dec 10, 2021 7:38 pm
>
> 
WOW. how did you find the correct face offset ?From the picture where you wrote "having issues with faces though." 

> Do you think this is readable by Noesis script ?I wouldn't see why not. But someone has to create it.
## Post #6
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-10T16:31:08+00:00
- Post Title: Immortal Fenyx Rising .forge

haha very nice! thank you so much.. wonder whos willing to do it   . i appreciate the reply.
[](https://ibb.co/BqXXQnH)
SAMPLE 2
[https://drive.google.com/file/d/1qTFXYT ... sp=sharing](https://drive.google.com/file/d/1qTFXYTNXPWzuWU-0CBxFcfisI1VSTEw6/view?usp=sharing)

Uv's seems to be a little buggy after some manual fixing
[](https://ibb.co/9n9bJVh)
## Post #7
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-12-10T20:14:21+00:00
- Post Title: Immortal Fenyx Rising .forge

This game can already be converted ever since demo using ACViewer tool, which is also posted here in the forum.
## Post #8
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-10T21:04:14+00:00
- Post Title: Immortal Fenyx Rising .forge

Thanks mono but this dont support skeletons does it ? and im not really sure how to load anything
[](https://ibb.co/WtVtyz4)
## Post #9
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-12-10T21:10:04+00:00
- Post Title: Immortal Fenyx Rising .forge

> Reply from Sharppy ↑Sat Dec 11, 2021 5:04 am at Sat Dec 11, 2021 5:04 am
>
> 
Thanks mono but this dont support skeletons does it ? and im not really sure how to load anything
You should join developers Discord channel from his thread, if you are looking for more answers.
## Post #10
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-11T09:01:37+00:00
- Post Title: Immortal Fenyx Rising .forge

That program crashes everytime i try to open a .dat file extracted with assasins_creed_raw.bms ? is that the script used to dump forges ?
[](https://ibb.co/cyQYKPY)

and truthfully if the data can be parsed outside of this program i would be much better off. manually doing each one is not something i have time to do but thank you for the program i never heard of this one. that would make around 6-7 tools i now have for assassins creed
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-11T12:32:53+00:00
- Post Title: Immortal Fenyx Rising .forge

> Reply from Sharppy ↑Sat Dec 11, 2021 5:01 pm at Sat Dec 11, 2021 5:01 pm
>
> manually doing each one is not something i have time to doI see.  
Try out this one (tested with 2 .dat files only so may fail on others):
.


 Make_H2O-ImmFenyxR.zip
(38.99 KiB) Downloaded 53 times


Doesn't work standalone, use with the dll files in the .zip from here:

> Reply from shakotay2 ↑Wed Dec 01, 2021 4:53 am at Wed Dec 01, 2021 4:53 am
>
> 

(Should create one H2O file for use with hex2obj.)

edit: updated for _CHB_UNI_316_PlayerBrother_Head_Caucasian_LOD0, _CHB_UNI_316_PlayerBrother_Hair_LOD0 (and maybe more)
## Post #12
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-11T13:00:20+00:00
- Post Title: Immortal Fenyx Rising .forge

Thank you i will do some test. Yah i tried to open with that AC Viewer and its all bugged or i dont know how to use it properly. So hopefully this leads me somewhere closer  
[](https://ibb.co/1Kj3r3g)

Here are a few samples cut from the new script
[https://drive.google.com/file/d/1qfqwXf ... sp=sharing](https://drive.google.com/file/d/1qfqwXfnP0dTxdBtC-Fid2HaPLEKQQVfg/view?usp=sharing)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-11T17:29:32+00:00
- Post Title: Immortal Fenyx Rising .forge

made an ugly fix to my previous upload
## Post #14
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-11T17:32:25+00:00
- Post Title: Immortal Fenyx Rising .forge

I tried using the tool i get a .h20 file with some data but when i load file then load into hex2obj i don't know how to use that GUI too well.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-11T18:21:55+00:00
- Post Title: Immortal Fenyx Rising .forge

yeah, sorry, too many fixes at a time, re-uploaded the fixed fix.  

File\Open model file, then File\Open H2O, press 'mesh' button.
## Post #16
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-11T18:56:46+00:00
- Post Title: Re: Immortal Fenyx Rising .forge

Sorry the files are tricky and the tools are not well known or in private servers. I talked to DKDave and he is making something i think to parse the data in Noesis. And if it works, it should be able to do all other assassins creeds that use Blacksmith or ACViewer. More to come thank you for your help but this still won't solve that batch issue we are faced in the community. I would still need to load each one and manually export. Thank you though truly. Your help is always appreciated. I really wish we could figure out that forza stuff    I will still save your tool as i did with wild arms   i did attempt though.  
[](https://ibb.co/k2TrFrY)
## Post #17
- Username: Arczi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 05, 2021 10:20 am
- Post datetime: 2021-12-15T21:51:04+00:00
- Post Title: Re: Immortal Fenyx Rising .forge

How did u unpacked those *.forge files?

Edit: Ah i see script
## Post #18
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2021-12-16T06:29:48+00:00
- Post Title: Re: Immortal Fenyx Rising .forge

> Reply from Sharppy ↑Sat Dec 11, 2021 5:04 am at Sat Dec 11, 2021 5:04 am
>
> 
Thanks mono but this dont support skeletons does it ? and im not really sure how to load anything

Haven't updated the schema for Fenyx in ACViewer in a long time. Will try to do that when I have time.
ACViewer do support skeleton and animations, but I need to tweak the code a bit for Fenyx.
## Post #19
- Username: forgeMaster
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Sep 03, 2020 8:56 am
- Post datetime: 2021-12-16T08:29:30+00:00
- Post Title: Re: Immortal Fenyx Rising .forge

Updated schema to last version (at time of writing 1.3.4). Can load worlds again without crashing.
No characters yet but I will take a look to see how easy it is to support.
[ORP.jpg](https://xentaxbackup.github.io/file/21408_ORP.jpg)
## Post #20
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-16T13:45:36+00:00
- Post Title: Re: Immortal Fenyx Rising .forge

That would be awesome can it batch extract or be ran through CMD ? DKDave made a script that can read files .dat but we renamed files to .ifrmesh and they seem to be readable but many do fail. And no skeletal support but bones are parsed. 
[](https://ibb.co/VxnJcNm)
## Post #21
- Username: Leo73
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Feb 18, 2019 5:06 am
- Post datetime: 2022-04-20T15:20:11+00:00
- Post Title: Re: Immortal Fenyx Rising .forge

Hey, 

just wondering if there are good news about the models and textures from Fenyx Rising? 

I actually only need the statues of the greek gods. AC Viewer in its current version crashes when trying to export to fbx unfortunately.  I even do not know how to unpack these forge files…

would be cool if someone would point me into the right direction. I would be willing to do the necessary steps for those few statues manually, just have no idea how and where to start. 

Thanks in Advance
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-19T09:06:13+00:00
- Post Title: Re: Immortal Fenyx Rising .forge

Those who need steps should start here

> Reply from shakotay2 ↑Sat Dec 11, 2021 8:32 pm at Sat Dec 11, 2021 8:32 pm
>
> 
then ask specific questions.

Use the .dat sample from here:

> Reply from Sharppy ↑Fri Dec 10, 2021 12:27 pm at Fri Dec 10, 2021 12:27 pm
>
> 

Load it into Make_H2O-ImmFenyxR.exe (get the .dlls before mentioned in first linked post):
The resulting H2O file is:

0x2d910 22434
Vb1
12 99
0xae0c 5074
020400
0xf7c 8

where first line is Face indices' address and count
and 4th line is vertices' address and count.

In hex2obj:
File\Open model file (.dat), then File\Open H2O, press 'mesh' button.

(Didn't handle textures because I don't have any.)
## Post #23
- Username: roabel8
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 26, 2023 1:10 pm
- Post datetime: 2023-08-26T05:13:16+00:00
- Post Title: Re: Immortal Fenyx Rising .forge

> Reply from Sharppy ↑Sun Dec 12, 2021 2:56 am at Sun Dec 12, 2021 2:56 am
>
> 
Sorry the files are tricky and the tools are not well known or in private servers. I talked to DKDave and he is making something i think to parse the data in Noesis. And if it works, it should be able to do all other assassins creeds that use Blacksmith or ACViewer. More to come thank you for your help but this still won't solve that batch issue we are faced in the community. I would still need to load each one and manually export. Thank you though truly. Your help is always appreciated. I really wish we could figure out that forza stuff    I will still save your tool as i did with wild arms   i did attempt though.

Hey! I've been looking for DKDave, do you know where I can find him? Would really appreciate it.
