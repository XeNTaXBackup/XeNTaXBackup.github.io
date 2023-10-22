## Post #1
- Username: Zenloup
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 20, 2019 5:12 am
- Post datetime: 2019-11-19T22:01:14+00:00
- Post Title: SSX 3 Character models (.mnf)

Hello,
I've been trying to find a way to rip SSX 3 models, if possible rigged. The only solution I was able to come up with was using ninja ripper via dolphin emulator. Here is how I did it: [https://www.youtube.com/watch?v=GIIMg9spqI4&t=297s](https://www.youtube.com/watch?v=GIIMg9spqI4&t=297s)

It would be a pain to get all the custom boltons this way, so I kindly want to ask if anybody here could have a look at the file and help me to create a noesis or quickbms script 

All of the games models are stored as .mnf files [*]

 deiter_Ponytail.rar
(4.38 KiB) Downloaded 20 times

 
I heard of a program called "ADAMS" which is supposed to be able to open these files, but I never found anything about it on google.

The uploaded file is a hair model of one of the games characters. They are split into many customisable parts.
Heres the textures for it:  And 

Thank you for reading !
## Post #2
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-11-20T20:40:40+00:00
- Post Title: SSX 3 Character models (.mnf)

Wow! With that script, we would be able to have fully customized ssx3 characters for other games!
## Post #3
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-11-27T23:08:44+00:00
- Post Title: SSX 3 Character models (.mnf)

*bump*
The sample .mnf has been downloaded 5 Times now. Did you guys have any success with them by now?
## Post #4
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-12-27T18:27:39+00:00
- Post Title: SSX 3 Character models (.mnf)

I managed to get some more sample files!
First would be nates head model:
[https://cdn.discordapp.com/attachments/ ... _HeadA.mnf](https://cdn.discordapp.com/attachments/628005960471805972/660182789672665118/rocco_HeadA.mnf)


And Second would be macs addons:


 Mac_Bolt-ons.zip
(9.27 KiB) Downloaded 15 times




It would be awesome if the mighty shakotay could give the .mnf files a try
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-27T20:00:01+00:00
- Post Title: SSX 3 Character models (.mnf)

> Reply from Henchman800 ↑Sat Dec 28, 2019 2:27 am at Sat Dec 28, 2019 2:27 am
>
> It would be awesome if the mighty shakotay could give the .mnf files a trySadly the "mighty shakotay" doesn't have a clue - all I see is a strange structure.  
(Problem is that the columns have this jump of one byte in a non regular manner.)
You might ask other mighties...
.



mnf.jpg (203.74 KiB) Viewed 269 times
## Post #6
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-12-27T20:08:39+00:00
- Post Title: SSX 3 Character models (.mnf)

> (Problem is that the columns have this jump of one byte in a non regular manner.)

does that mean, that ou always have to skip 1 byte in order to read the next vertex coordinates?

Frohe Weihnachten Shakotay!
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-27T20:23:00+00:00
- Post Title: SSX 3 Character models (.mnf)

I don't think that it's so simple- maybe the data is compressed somehow.

Frohe Weihnachten Henchman800!
## Post #8
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-12-28T14:10:30+00:00
- Post Title: SSX 3 Character models (.mnf)

Hey Shakotay,
I´ve seen that before! I had this issue with king of the route 66s models:
[viewtopic.php?f=16&t=21245&p=157037#p157037](https://forum.xentax.com/viewtopic.php?f=16&t=21245&p=157037#p157037)
Bigchillghost figured it out for me though 

I now have some more/different sample files for you:
[https://cdn.discordapp.com/attachments/ ... models.zip](https://cdn.discordapp.com/attachments/628005960471805972/660483580421472296/nate_models.zip)
Here you have a couple of nates submodels to test in both the ps2 and gamecube version

- .mpf  =  ps2-model
- .ssh   =  ps2-texture
- .mnf  =  gamecube-model
- .gsh   =  gamecube-texture

EDIT: theres also a different xbox Version of the files, if you guys need it 

I hope that the opportunity to compare both versions models may help you or bigchillghost figure out the compression!

thank you again big time for helping!
## Post #9
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-12-28T15:01:42+00:00
- Post Title: SSX 3 Character models (.mnf)

well. i dunno much cube. the textures are identical. i got no idea wth the compression is tho. there are plain float values in the ps2 model, but this is all scrambled. eye cancer. or i'd call it data puke. not fun to fiddle with it.
## Post #10
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-12-28T16:07:52+00:00
- Post Title: SSX 3 Character models (.mnf)

thx for replying!
hmmm not so good news :-/
do you think the xbox models could help, since its closer to windows/pc based?
## Post #11
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-01-01T18:16:23+00:00
- Post Title: SSX 3 Character models (.mnf)

Yo, Bigchillghost!
Could you have a look at this and give it a try? 
Your help would be much appretiated by the SSX community 

 HAPPY NEW YEAR EVERYBODY
## Post #12
- Username: Zenloup
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 20, 2019 5:12 am
- Post datetime: 2020-01-09T21:17:53+00:00
- Post Title: SSX 3 Character models (.mnf)

was anybody able to uncompressthe files?"
## Post #13
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-01-21T19:56:27+00:00
- Post Title: SSX 3 Character models (.mnf)

Yo guys, check this out:
a pre-alpha of ssx 3 has been discovered. Strangely EA used the .mpf format for their models in this one....at least thats what i think/see.....
Usually a .mpf goes with a .mus. the mus-file contains the actual audio and the mpf-file comes with info and offsets to start the song on certrain timecodes. In this particular case it seems to contain 3d info:

```
 HeadBoltA_H HandsA_NIS DummyA_NIS TopBoltD_M
 HeadBoltA_M TopBoltD_L
 HeadBoltA_L TopBoltD_Shdw BottomA_Shdw BootsA_Shdw
 HeadA_Shdw HandsA_Shdw HeadBoltA_Shdw HeadBoltD_H
 HeadBoltD2_H
 HeadBoltD_M
 HeadBoltD2_M
 HeadBoltD_L
 HeadBoltD2_L
 HeadBoltD_Shdw
 HeadBoltD2_Shdw
 SplitHair_H HeadBoltB4_H SplitHair_M HeadBoltB4_M SplitHair_L HeadBoltB4_L SplitHair_Shdw HeadBoltB4_Shdw
ë mY1YßÆ¦ PTQt
 mY1Y!9¦ PTQD
 mY1Y 3ZuD
 ?lowerspine ?middlespine ?upperspine
 ?clavicleleft ?bicepleft
 ?biceptwistleft
 ?forearmleft ?clavicleright ?bicepright
 ?biceptwistright ?forearmright
 ?handright
 ?thighleft ?thighright ?shinright ?footright
Á p$gAh6tAy)E
‘Á V=~Ah6tAy)E
 xR6AÈÂ 3B8G
 sec_hoodie
 aXA7V‚Àð F3B7F]A
Ù m,Ad}u@gG'BÙ m,Ad}u@gG'BX‡ GAqt
Ù m,Ad}u@gG'BÙ m,Ad}u@gG'BÙ m,Ad}u@gG'B
 aXA7V‚Àð F3BX‡ GAqt
 ?lowerspine ?middlespine ?upperspine
 ?clavicleleft ?bicepleft
 ?biceptwistleft
 ?forearmleft ?clavicleright ?bicepright
 ?biceptwistright ?forearmright
 ?handright
 ?thighleft ?thighright ?shinright ?footright
 sec_hoodie
À rTEB 5Ahm
 ?lowerspine ?middlespine ?upperspine
 ?clavicleleft ?bicepleft
 ?biceptwistleft
 ?forearmleft ?clavicleright ?bicepright
 ?biceptwistright ?forearmright
 ?handright
 ?thighleft ?thighright ?shinright ?footright
 sec_hoodie
 ?lowerspine ?middlespine ?upperspine
 ?clavicleleft ?bicepleft
 ?biceptwistleft
 ?forearmleft ?clavicleright ?bicepright
 ?biceptwistright ?forearmright
 ?handright
 ?thighleft ?thighright ?shinright ?footright
 sec_hoodie
```


So hopefully this info and the file itself help to get to its innerts and understand how EA is working their 2003 era models.
Heres a download to nates .mpf file:


 rocco.zip
Rooco is Nates ingame files name.... (151.72 KiB) Downloaded 13 times



I'll be looking into some need for speed stuff....maybe they use the same model containers and nfs extractors work on ssx aswell?
anybody got info or experience with that?
## Post #14
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-01-27T01:20:36+00:00
- Post Title: SSX 3 Character models (.mnf)

> Reply from episoder ↑Sat Dec 28, 2019 11:01 pm at Sat Dec 28, 2019 11:01 pm
>
> 
well. i dunno much cube. the textures are identical. i got no idea wth the compression is tho. there are plain float values in the ps2 model, but this is all scrambled. eye cancer. or i'd call it data puke. not fun to fiddle with it.

I just read that it seems to be easier to find the info on xbox models:
[viewtopic.php?f=16&t=19339](https://forum.xentax.com/viewtopic.php?f=16&t=19339)
Well...I hope that it applies to ssx 3 aswell...

Could you please have a look at these .mxf files?


 Mac_Small_models.zip
(7.49 KiB) Downloaded 14 times



I picked small sized files because i hope the data is easier to find since theres less data written in the file.
## Post #15
- Username: Zenloup
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 20, 2019 5:12 am
- Post datetime: 2020-01-27T02:28:50+00:00
- Post Title: SSX 3 Character models (.mnf)

Guys ! i saw some little information with final big when i tried to open the models , finalbig show me , this : ?lowerspine ?middlespine ?upperspine
 ?clavicleleft ?bicepleft
 ?biceptwistleft
 ?forearmleft ?clavicleright ?bicepright
 ?biceptwistright ?forearmright
 ?handright
 ?thighleft ?thighright ?shinright ?footright
 sec_hoodie
 ?lowerspine ?middlespine ?upperspine
 ?clavicleleft ?bicepleft
 ?biceptwistleft
 ?forearmleft ?clavicleright ?bicepright
 ?biceptwistright ?forearmright
 ?handright
 ?thighleft ?thighright ?shinright ?footright
 sec_hoodie
it's something like a armature(bones names) for the model 

I did some research on the .mpf format I found this (It's a binary data file, that's all we have found out. The file has a few characteristics of a SPS (SharkPort file) file.) i opened the .mpf file with this siteweb before using finalbig ([https://filext.com/file-extension/MPF](https://filext.com/file-extension/MPF) ) it's gave me some really interesting information , but i guess it's not going to help so much.
that's all i found for the moment
i guess the models are in several parts but in 1 armature(All bones in all the several part of the models).

i guess it didn't help so much , but that's all i found for the moment.
## Post #16
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-05-06T01:58:24+00:00
- Post Title: Re: SSX 3 Character models (.mnf)

Glad to See people still working on ssx 3:
[https://youtu.be/UeI6gKZdWw0](https://youtu.be/UeI6gKZdWw0)

He also must have been able to edit .ssh files. A Couple textures and effect sprites are changed.
