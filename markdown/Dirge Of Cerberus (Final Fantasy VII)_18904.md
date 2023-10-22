## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-07T18:17:39+00:00
- Post Title: Dirge Of Cerberus (Final Fantasy VII)

Tool for Dirge Of Cerberus (Final Fantasy VII).
It can currently extract textures & skeletal models with bones, weights, UVs, etc.

(before converting models you have to extract files from game archive
you can do this with Luigi's BMS script for FF13, or with noesis)

Drop model/texture file onto the tool and it will output models as OBJ & SMD, textures as TGA
OBJ will just have geometry. SMD will have everything.
If you use it on static model, it will output empty files.






[FF7.rar](https://xentaxbackup.github.io/file/15024_FF7.rar)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-07T19:04:39+00:00
- Post Title: Dirge Of Cerberus (Final Fantasy VII)


## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-08T07:41:48+00:00
- Post Title: Dirge Of Cerberus (Final Fantasy VII)

materials applied
## Post #4
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2018-10-09T17:45:52+00:00
- Post Title: Dirge Of Cerberus (Final Fantasy VII)

Brilliant!!!
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-09T19:03:34+00:00
- Post Title: Dirge Of Cerberus (Final Fantasy VII)

Tool released.
## Post #6
- Username: obesebear
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 10, 2018 11:04 pm
- Post datetime: 2018-10-10T15:11:05+00:00
- Post Title: Dirge Of Cerberus (Final Fantasy VII)

I can't tell you how many dozens of hours I have spent using 3dripperdx and photoshop and 3dsmax to get poorly ripped models with poorly ripped textures and attempt to piecemeal it all together.  Thank you for this.

EDIT:
If you don't mind me asking, where did you get the textures from?  Dragging and dropping does create .obj and .smd files, and models load properly into noesis and 3dsmax, but there are no accompanying texture files.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-11T15:33:24+00:00
- Post Title: Dirge Of Cerberus (Final Fantasy VII)

> Reply from obesebear
>
> I can't tell you how many dozens of hours I have spent using 3dripperdx and
I can imagine that after reading the old FF7 thread. People here tried many things to get models in years 

Textures here are standard PS2 swizzled 8-bit palette images. So i used old existing tools for PS2. If nobody will come out with a quick and easy way to batch convert them, I'll do some tool for it myself.
## Post #8
- Username: obesebear
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 10, 2018 11:04 pm
- Post datetime: 2018-10-11T15:48:29+00:00
- Post Title: Dirge Of Cerberus (Final Fantasy VII)

For the models I "ripped" years ago I used a tool with pcsx2 where you individually scroll through all currently displayed textures on the screen and export one by one then switch its rgb channels. 

Maybe the process isn't so bad now
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-12T15:57:34+00:00
- Post Title: Dirge Of Cerberus (Final Fantasy VII)

Note:

before converting models you have to extract files from game archive
you can do this with Luigi's BMS script for FF13, or with noesis
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-13T20:01:47+00:00
- Post Title: Dirge Of Cerberus (Final Fantasy VII)

added texture export - same tool
just drop texture package onto it, it will export all images as TGA (uncompressed RGB with alpha)
## Post #11
- Username: obesebear
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 10, 2018 11:04 pm
- Post datetime: 2018-10-19T20:52:35+00:00
- Post Title: Dirge Of Cerberus (Final Fantasy VII)

I've been going through all the models and trying to organize and categorize, but I've come across some issues. One is Rosso's weapon texture is nowhere to be found. Galian beast has some incorrect vertices.

I'll upload the galian beast model later tonight unless I figure out the issue
## Post #12
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-10-27T09:17:50+00:00
- Post Title: Dirge Of Cerberus (Final Fantasy VII)

please help
I extracted the iso using noesis then  I renamed  the files just like the instruction here

"Noesis 4.03 is out with VIFcode unpacking exposed to Python. Also, if you do the trick of renaming FILELIST.BIN to FILELIST_scru.x360.BIN and renaming KEL.DAT to white_scru.x360.bin, Noesis will extract them with proper filenames and paths. Although the decompressed filelist still uses blank names for lots of the RFD's, they'll still get the right extension."

but noesis was unable to extract the renamed files.   I then used aluig's bms.  The files were extracted,. however  all the mod files I checked produced obj with the size 0 and smd with the size 0f 1.


1.why noesis could not extract my renamed files
2.could you tell me the name of the file that contains azul, so I can verify whether  the files that i extracted using ff13 were corrupted or not
## Post #13
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2018-10-27T10:59:58+00:00
- Post Title: Dirge Of Cerberus (Final Fantasy VII)

> Reply from tone
>
> (...)
1.why noesis could not extract my renamed files
2.could you tell me the name of the file that contains azul, so I can verify whether  the files that i extracted using ff13 were corrupted or not

1. Noesis should be able to extract them when you double click the one named Filelist. If your main archive file isn't named properly it will open a window where you can select it (KEL.dat). However the model files you want won't have names with either method.

2. Aluigis bms is recommended because it will group the models and textures together. A LOT of them are static objects, not supported by the tool. I recommend you make a batch so it processes all .mod files at once, then filter in Noesis for .smd files and sort them by size. The biggest files will be the cutscene models of main characters. If you found the one you want remember its filename, search it in your filebrowser and the .tex files after it will be its textures.
## Post #14
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-10-28T19:51:49+00:00
- Post Title: Dirge Of Cerberus (Final Fantasy VII)

thank you daemon and crofty, it works now
## Post #15
- Username: TheArk
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 03, 2013 12:12 am
- Post datetime: 2019-03-18T01:23:41+00:00
- Post Title: Dirge Of Cerberus (Final Fantasy VII)

So, if most of the files that don't convert properly are static objects, then why is it I can't seem to find certain Deepground Models? I have some of them but I'm not having luck when trying to find the Deepground Sergeant, Commander or Elite? Everything else converted. All the files are named like 0000000000002fd0 not with their specific names.

Any help?
## Post #16
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2020-01-06T19:02:15+00:00
- Post Title: Re: Dirge Of Cerberus (Final Fantasy VII)

Question by a newb. How would you extract the raw files needed to drag and drop onto this tool in the first place?
## Post #17
- Username: Caleb123459
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Nov 29, 2019 8:54 am
- Post datetime: 2021-06-30T23:44:07+00:00
- Post Title: Re: Dirge Of Cerberus (Final Fantasy VII)

I'm sorry to bump, but has anyone ever figured out how to get animations from DoC? I've been searching for a way to get them but there hasn't been any luck. Any help would be appreciated! ^^
