## Post #1
- Username: lol2k12
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 27, 2013 11:47 pm
- Post datetime: 2013-11-18T12:31:09+00:00
- Post Title: Kingdom hearts 2 final mix animation files ?

hello i'v extracted kingdom hearts 2 final mix img files and then downloaded a plugin for exporting the mdlx files with noesis
and i'v exported all of the lion king models to fbx format
but i am looking for exporting the animation files to fbx format ..

is there a way to do that ?!
## Post #2
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2013-12-04T17:22:49+00:00
- Post Title: Kingdom hearts 2 final mix animation files ?

Yes. You need Revelation's version of khkh_xldMii, mediafire.com/download/xym4yaa75qjvdpt/Release.7z . Then for best results, download the latest version of khkh_xldMii,
[http://kkdf2.sakura.ne.jp/pcsx2lair/Release_13.7z](http://kkdf2.sakura.ne.jp/pcsx2lair/Release_13.7z) (password is 2). Replace the ef1Declib.dll from Release 13 with the dll from Revelation's version. Then, download Noesis from richwhitehouse.com/index.php?content=inc_projects.php . Then, download Revelation's special version of his KH2 plugins for Noesis at [https://github.com/RoadTrain/noesis-plu ... s_2_v2.zip](https://github.com/RoadTrain/noesis-plugins-official/tree/master/revelation/kingdom_hearts_2_v2.zip) and put them in Noesis's plugins folder. You can view animations with khkh_xldMii by dragging a MDLX into the program (as long as it has an MSET of the same name in that folder to animate it) and export them with the ASET exporter. You'll have to dig through all the MSETs until you find some that correspond to the model. You can also use ANB animations by converting them to MSETs with [http://kkdf2.sakura.ne.jp/pcsx2lair/expack1anbz2.7z](http://kkdf2.sakura.ne.jp/pcsx2lair/expack1anbz2.7z) (password is ][). Once the animations are in ASET format, load Noesis and view the model you just exported the ASET for. Noesis will automatically load the ASET of the same name as the MDLX you just opened if they're in the same folder. With Noesis's export function, you can then export the ASET animations to a variety of other animation formats.
In order to extract the most ANBs and MSETs, I'd suggest using the most sophisticated KH2FM file extractor, Govanify's KH2FM Toolkit at [https://github.com/GovanifY/KH2FM_Toolkit/](https://github.com/GovanifY/KH2FM_Toolkit/)
## Post #3
- Username: lol2k12
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 27, 2013 11:47 pm
- Post datetime: 2014-02-18T02:02:45+00:00
- Post Title: Kingdom hearts 2 final mix animation files ?

i cant manage to export ASET FILES Revelation's version of khkh_xldMii how to do that ?! i dont see any button to convert them ...

EDIT : 
i managed to get it to work . 

thanks for helping
## Post #4
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-06-14T09:50:11+00:00
- Post Title: Kingdom hearts 2 final mix animation files ?

Naaah, the most advanced KH2FM extractor is now mine, here's a quote from another subject:

> Reply from GovanifY
>
> I'm not sure if this is totally out of the subject but anyways.
I made a Toolkit for KH2FM, which contains an extractor(with a huge hashlist for now =D ), a patchmaker and a patcher. The patching process is longer than Xeeynamo's b\c it's rebuilding totally the IMG and the IDX(where Xeeynamo was just opening the IDX, finding the file, and replacing it. If a bigger file was selected, it will overwrite some files so that wasn't really a good solution. Anyways ya can found a demo of my Toolkit here: https://www.youtube.com/watch?v=V6XFdC9 ... XhBHpEpJEQ

Download links:
Executable: http://www.govanify.x10host.com/_files/ ... oolkit.exe

License: http://www.govanify.x10host.com/_files/ ... ICENSE.txt

If ya want more help do the command KH2FM_Toolkit -help, it will extract a Readme. It will require the .NET Framework too, normally shipped w/ windows so I think there will be not so much issues with that.

I'm not sure I'll work on KH1, but maybe I'll do a Toolkit for him, that's a possibility. The problem is I never really worked on kh1, and I don't really want to work on him^^
So, I want to say, we'll see

Btw, don't consider that like an ad, I personally don't want to be known, I just want my Toolkit to be known :p It's the best ya can found for now, so that's why^^
Last thing: the HashList isn't complete(there's still ~1.000 nonames for KH2FM), but I'm updating it pretty quickly, so I think the nonames will be an old story in not so long =D

Bye!, GovanifY

Enjoy
## Post #5
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2014-09-30T02:27:58+00:00
- Post Title: Kingdom hearts 2 final mix animation files ?

> Reply from GovanifY
>
> Naaah, the most advanced KH2FM extractor is now mine, here's a quote from another subject:

Enjoy

I tried your extractor, I got map mdl anim and many many, Thank for you great work.
## Post #6
- Username: skornedemon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 18, 2014 5:27 pm
- Post datetime: 2014-10-18T10:23:20+00:00
- Post Title: Kingdom hearts 2 final mix animation files ?

> Reply from lol2k12
>
> i cant manage to export ASET FILES Revelation's version of khkh_xldMii how to do that ?! i dont see any button to convert them ...

EDIT : 
i managed to get it to work . 

thanks for helping

How do you do it with the program?

Sorry for the bump.
## Post #7
- Username: Aiden35P
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 26, 2015 1:11 am
- Post datetime: 2015-08-25T19:13:54+00:00
- Post Title: Kingdom hearts 2 final mix animation files ?

I did everything that you said in this topic and it worked perfectly so thanks a lot for that  now how can i import the FBX animations that i converted with Noesis and maya fbx converter into Unreal Engine 4 ? If i try to drag and drop them it gave me an error that says that the import failed (i already imported the models; i tried as statical and as skeleton but it fails anyway). I'm a beginner in 3D animation but i feel that the problem is that i don't have a proper skeletal mesh. Thank you in advance for the help.
## Post #8
- Username: zamumillo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 14, 2015 12:20 am
- Post datetime: 2015-10-13T21:26:07+00:00
- Post Title: Kingdom hearts 2 final mix animation files ?

> Reply from Mirrorman95
>
> Yes. You need Revelation's version of khkh_xldMii, mediafire.com/download/xym4yaa75qjvdpt/Release.7z . Then for best results, download the latest version of khkh_xldMii,
http://kkdf2.sakura.ne.jp/pcsx2lair/Release_13.7z (password is 2). Replace the ef1Declib.dll from Release 13 with the dll from Revelation's version. Then, download Noesis from richwhitehouse.com/index.php?content=inc_projects.php . Then, download Revelation's special version of his KH2 plugins for Noesis at code.google.com/p/noesis-plugins-official/source/browse/trunk/revelation/kingdom_hearts_2_v2.zip and put them in Noesis's plugins folder. You can view animations with khkh_xldMii by dragging a MDLX into the program (as long as it has an MSET of the same name in that folder to animate it) and export them with the ASET exporter. You'll have to dig through all the MSETs until you find some that correspond to the model. You can also use ANB animations by converting them to MSETs with http://kkdf2.sakura.ne.jp/pcsx2lair/expack1anbz2.7z (password is ][). Once the animations are in ASET format, load Noesis and view the model you just exported the ASET for. Noesis will automatically load the ASET of the same name as the MDLX you just opened if they're in the same folder. With Noesis's export function, you can then export the ASET animations to a variety of other animation formats.
In order to extract the most ANBs and MSETs, I'd suggest using the most sophisticated KH2FM file extractor, Govanify's KH2FM Toolkit at http://www.govanify.com/_files/KH2FM_Toolkit/ .

I have followed these instructions:
- I extract the game files with Govonify KH2FM_Toolkit.
- Search Sora through the files and get the files P_EX100.mdlx and P_EX100.mset.
- I copied them into a new folder that I call SoraKH2FM on my desk.
- Open the Revelation's version of khkh_xldMii (with ef1Declib.dll from Release 13).
- Drag the P_EX100.mdlx file into the khkh_xldMii program and see the P_EX100.mdlx animations in the khkh_xldMii program.
- Select the first animation idle and export it as ASET.
- In the Revelation's version folder of khkh_xldMii find the file called P_EX100.ASET.
- Copy the file P_EX100.ASET to my folder SoraKH2FM where I also have the P_EX100.mdlx and P_EX100.mset files.
- Open NOESIS (witn kingdom_hearts_2_v2 plugin Added).
- Load the P_EX100.mdlx file that is inside my folder SoraKH2FM.
- Then I can see the model, their textures, their bones but I can not see his idle animation.
- So I export the character by FBX and open it with Maya and I see the same that I saw in NOESIS, the character is rigged but he has no animation key.

Have I skipped any step? Is there anything that I did wrong? What is the mistake?

I have installed Win7 64bits, is it possible that is because of this?


Thanks =)


Ok, I imported this plugin ([download/file.php?id=4632](http://forum.xentax.com/download/file.php?id=4632)) in Noesis and now work ^^
## Post #9
- Username: Apathy95
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 25, 2019 8:06 am
- Post datetime: 2019-12-25T00:14:37+00:00
- Post Title: Kingdom hearts 2 final mix animation files ?

> Reply from Mirrorman95 ↑Thu Dec 05, 2013 1:22 am at Thu Dec 05, 2013 1:22 am
>
> 
Yes. You need Revelation's version of khkh_xldMii, mediafire.com/download/xym4yaa75qjvdpt/Release.7z . Then for best results, download the latest version of khkh_xldMii,
http://kkdf2.sakura.ne.jp/pcsx2lair/Release_13.7z (password is 2). Replace the ef1Declib.dll from Release 13 with the dll from Revelation's version. Then, download Noesis from richwhitehouse.com/index.php?content=inc_projects.php . Then, download Revelation's special version of his KH2 plugins for Noesis at https://github.com/RoadTrain/noesis-plu ... s_2_v2.zip and put them in Noesis's plugins folder. You can view animations with khkh_xldMii by dragging a MDLX into the program (as long as it has an MSET of the same name in that folder to animate it) and export them with the ASET exporter. You'll have to dig through all the MSETs until you find some that correspond to the model. You can also use ANB animations by converting them to MSETs with http://kkdf2.sakura.ne.jp/pcsx2lair/expack1anbz2.7z (password is ][). Once the animations are in ASET format, load Noesis and view the model you just exported the ASET for. Noesis will automatically load the ASET of the same name as the MDLX you just opened if they're in the same folder. With Noesis's export function, you can then export the ASET animations to a variety of other animation formats.
In order to extract the most ANBs and MSETs, I'd suggest using the most sophisticated KH2FM file extractor, Govanify's KH2FM Toolkit at https://github.com/GovanifY/KH2FM_Toolkit/

Sorry to revisit an ancient thread

I've made it up too the Noesis step and cannot seem to import .ASET files for the life of me. Any chance it's plugin related?

Regards.
## Post #10
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2019-12-27T15:07:06+00:00
- Post Title: Kingdom hearts 2 final mix animation files ?

> Reply from Apathy95 ↑Wed Dec 25, 2019 8:14 am at Wed Dec 25, 2019 8:14 am
>
> 
Mirrorman95 wrote: ↑Thu Dec 05, 2013 1:22 am
Yes. You need Revelation's version of khkh_xldMii, mediafire.com/download/xym4yaa75qjvdpt/Release.7z . Then for best results, download the latest version of khkh_xldMii,
http://kkdf2.sakura.ne.jp/pcsx2lair/Release_13.7z (password is 2). Replace the ef1Declib.dll from Release 13 with the dll from Revelation's version. Then, download Noesis from richwhitehouse.com/index.php?content=inc_projects.php . Then, download Revelation's special version of his KH2 plugins for Noesis at https://github.com/RoadTrain/noesis-plu ... s_2_v2.zip and put them in Noesis's plugins folder. You can view animations with khkh_xldMii by dragging a MDLX into the program (as long as it has an MSET of the same name in that folder to animate it) and export them with the ASET exporter. You'll have to dig through all the MSETs until you find some that correspond to the model. You can also use ANB animations by converting them to MSETs with http://kkdf2.sakura.ne.jp/pcsx2lair/expack1anbz2.7z (password is ][). Once the animations are in ASET format, load Noesis and view the model you just exported the ASET for. Noesis will automatically load the ASET of the same name as the MDLX you just opened if they're in the same folder. With Noesis's export function, you can then export the ASET animations to a variety of other animation formats.
In order to extract the most ANBs and MSETs, I'd suggest using the most sophisticated KH2FM file extractor, Govanify's KH2FM Toolkit at https://github.com/GovanifY/KH2FM_Toolkit/


Sorry to revisit an ancient thread

I've made it up to the Noesis step and cannot seem to import .ASET files for the life of me. Any chance it's plugin related?

Regards.
I do believe you're right, the version of the plugin in the link I have listed is wrong since I recently had to replace a dead plugin link in that post. Try this one and tell me if that fixes it:
[kingdom_hearts_2.zip](https://xentaxbackup.github.io/file/17236_kingdom_hearts_2.zip)
## Post #11
- Username: Apathy95
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 25, 2019 8:06 am
- Post datetime: 2020-01-07T22:31:46+00:00
- Post Title: Kingdom hearts 2 final mix animation files ?

You are the human! I needed this for a small project I'm doing with some of the 2.8 models. Regards!
## Post #12
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2020-04-13T17:00:37+00:00
- Post Title: Kingdom hearts 2 final mix animation files ?

> Reply from Apathy95 ↑Wed Jan 08, 2020 6:31 am at Wed Jan 08, 2020 6:31 am
>
> 
You are the human! I needed this for a small project I'm doing with some of the 2.8 models. Regards!

What would this project be?
## Post #13
- Username: TheFutureTimeline
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 28, 2021 4:17 pm
- Post datetime: 2021-03-28T08:19:03+00:00
- Post Title: Kingdom hearts 2 final mix animation files ?

> Reply from lol2k12 ↑Tue Feb 18, 2014 10:02 am at Tue Feb 18, 2014 10:02 am
>
> 
i cant manage to export ASET FILES Revelation's version of khkh_xldMii how to do that ?! i dont see any button to convert them ...

EDIT : 
i managed to get it to work . 

thanks for helping

Hello!! Extremely sorry to bump an ancient thread because Ik how annoying that may be, but since I'm also using khkh_xldMii to extract anims, how did you do it? I still cant find an option

Edit, after a whole ass night of extensive research, I got it. Thanks y'all! Wondering if it's possible to rip KH1 animations the same way? Anyone have any ideas? Would love to rip attack anims
