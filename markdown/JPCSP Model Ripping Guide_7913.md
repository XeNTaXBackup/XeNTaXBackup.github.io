## Post #1
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-12-22T04:50:48+00:00
- Post Title: JPCSP Model Ripping Guide

Good news everyone! I've discovered a way to rip entire model geometries from Birth By Sleep, and from JPCSP games in general, without needing to attenuate for the Y-Axis! To prove it, here is the geometry of Radiant Garden's Outer Gates: [http://www.brickshelf.com/gallery/mirro ... a.3399.obj](http://www.brickshelf.com/gallery/mirrorman95/PMOs/java.3399.obj)
And this is Castle Oblivion: [http://www.brickshelf.com/gallery/mirro ... a.3399.obj](http://www.brickshelf.com/gallery/mirrorman95/PMOs/java.3399.obj)

Now for this to work, you need at least 2 GB of RAM and it's recommended you have a decent graphics card.

Step 1: Download JPCSP
Step 2: Download GLXtractor
Step 3: Download JRE6 or 7 and choose that folder's java.exe in GLXtractor
Step 4: Upload your SAVEDATA folder to JPCSP's SAVEDATA folder (JPCSP revisions after r2099 will require Save Game Deemer's decrypted saves)
Step 5: Put your ISO in JPCSP's UMDimages folder and load GLXtractor and then JPCSP
Step 6: Run JPCSP, go to the desired location, and press CTRL+SHIFT+F
The OBJ will be in the JPCSP folder and the textures will be in your My Documents/Xtracted folder

EDIT: In case anyone is still using this guide, please note that it is obsolete, as JPCSP has a built-in model ripping function now. This could be useful for extracting some of the missing textures, but really GLXtractor is completely unnecessary now.
## Post #2
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-12-22T05:05:42+00:00
- Post Title: JPCSP Model Ripping Guide

You rock man, this help a lot to save time.
## Post #3
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2011-12-22T07:05:07+00:00
- Post Title: JPCSP Model Ripping Guide

Oh awesome! Thanks for the information, Mirrorman95. This will be very helpful along with some animation hacking.
## Post #4
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2011-12-22T12:28:53+00:00
- Post Title: JPCSP Model Ripping Guide

wht's different using 3d printscreen via
## Post #5
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2011-12-22T14:02:07+00:00
- Post Title: JPCSP Model Ripping Guide

Is it work for every game JPCSP support? I have try with it but i got fail. I use lamb plugin to rip model and JPCSP debugger to get textures. I try rip Fate Extra with lamb and model crash because of bone or animation
## Post #6
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-12-23T02:16:57+00:00
- Post Title: JPCSP Model Ripping Guide

does this work with the 64 bit version of JPCSP
## Post #7
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-12-23T08:27:20+00:00
- Post Title: JPCSP Model Ripping Guide

To answer some questions, neither have I tried this with other games nor with 64 bit JPCSP, but 64 bit JPCSP should still work, and the difference between this and printscreen is that it doesn't output as such a rare format as 3dxml. Since it dropped free DAE conversion support, all that can really convert it is 3DS Max, and it costs a lot. Also, the folks at models-resource told me it doesn't export UVs.
## Post #8
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-12-23T15:45:30+00:00
- Post Title: JPCSP Model Ripping Guide

thank you I will test it on ace combat
## Post #9
- Username: FRANKASTER
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 06, 2011 12:32 pm
- Post datetime: 2012-01-05T22:28:52+00:00
- Post Title: JPCSP Model Ripping Guide

> Reply from Mirrorman95
>
> To answer some questions, neither have I tried this with other games nor with 64 bit JPCSP, but 64 bit JPCSP should still work, and the difference between this and printscreen is that it doesn't output as such a rare format as 3dxml. Since it dropped free DAE conversion support, all that can really convert it is 3DS Max, and it costs a lot. Also, the folks at models-resource told me it doesn't export UVs.

which one dosen't import uv's  printscreen (which never worked with me) or your method... and do you have a recommended jpcsp gfx settings because i still got 0KB .obj files
(tryng to rip stuff from mgs peacwalker and portable ops and kratos from soul calibur.)

It might also be good to know the os used xp,vista,7?

i tried again changed sattings and still got that empty .obj file
## Post #10
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2012-01-06T23:21:32+00:00
- Post Title: JPCSP Model Ripping Guide

> Reply from FRANKASTER
>
> Mirrorman95 wrote:To answer some questions, neither have I tried this with other games nor with 64 bit JPCSP, but 64 bit JPCSP should still work, and the difference between this and printscreen is that it doesn't output as such a rare format as 3dxml. Since it dropped free DAE conversion support, all that can really convert it is 3DS Max, and it costs a lot. Also, the folks at models-resource told me it doesn't export UVs.

which one dosen't import uv's  printscreen (which never worked with me) or your method... and do you have a recommended jpcsp gfx settings because i still got 0KB .obj files
(tryng to rip stuff from mgs peacwalker and portable ops and kratos from soul calibur.)

It might also be good to know the os used xp,vista,7?

i tried again changed sattings and still got that empty .obj file
This method is the one that doesn't output UVs.
I don't know what your OS and graphics settings are, but I use a 500GB 2011 iMac with 4 GB of RAM running JPCSP r2099 x86 under Bootcamp Windows 7.
If you need to figure out what graphics card you should get, I recommend [http://www.hwcompare.com/5545/geforce-9 ... n-hd-6750/](http://www.hwcompare.com/5545/geforce-9600-gt-512mb-vs-radeon-hd-6750/) .
## Post #11
- Username: FRANKASTER
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 06, 2011 12:32 pm
- Post datetime: 2012-01-07T00:14:12+00:00
- Post Title: JPCSP Model Ripping Guide

well thanks icpu is win 7 32 bit, geforce 250 gts and 6gb on ram
anyways... since im a noob i don't know how to uv stuff so i'll continue working
with lamb psp plugin, still is amazing that the ripping from the emulator is possible
whatever rips uv' or not, because dragon is done with that thing and he won't developing it anymore, shame becuase the uv's are pretty cool, but supports few games but is better than nothing.
peace walker models!
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-07T02:08:34+00:00
- Post Title: JPCSP Model Ripping Guide

ha ha ha the lady on the right looks like she went to the wrong doctor for a hair transplant lol!
## Post #13
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2012-01-07T02:17:36+00:00
- Post Title: JPCSP Model Ripping Guide

> Reply from FRANKASTER
>
> well thanks icpu is win 7 32 bit, geforce 250 gts and 6gb on ram
anyways... since im a noob i don't know how to uv stuff so i'll continue working
with lamb psp plugin, still is amazing that the ripping from the emulator is possible
whatever rips uv' or not, because dragon is done with that thing and he won't developing it anymore, shame becuase the uv's are pretty cool, but supports few games but is better than nothing.
peace walker models!
http://fc04.deviantart.net/fs71/f/2012/ ... 4lggq9.png
I never got lamb plugin to work. Does it only allow 2000 and 3000?
## Post #14
- Username: FRANKASTER
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 06, 2011 12:32 pm
- Post datetime: 2012-01-07T03:39:46+00:00
- Post Title: JPCSP Model Ripping Guide

> Reply from Mirrorman95
>
> 
I never got lamb plugin to work. Does it only allow 2000 and 3000?

i don't think i have tried it on a 1000, but on my 2000 (cfw 5.5o gen d3) and 3000 6.36 LME 9.7 works fine, but game support is limited, i wish i could code stuff like that because i really wanted a kratos model
## Post #15
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2012-01-07T05:51:32+00:00
- Post Title: JPCSP Model Ripping Guide

Aren't there methods to copy the UVs from one model to another? Assuming the two have identical model structures.
## Post #16
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-01-07T11:23:48+00:00
- Post Title: Re: JPCSP Model Ripping Guide

> Reply from Friedslick6
>
> Aren't there methods to copy the UVs from one model to another? Assuming the two have identical model structures.

Absolutely yes u can use a lot of 3d software to do it. One solution is to use milkshape or 3ds max 
with the Unwrap UVW command > edit > export/import map.
Remember that the model must have an identical structure, with the same polygon number, etc.
## Post #17
- Username: BolinhaRedonda
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 12, 2011 10:26 am
- Post datetime: 2012-02-04T03:53:52+00:00
- Post Title: Re: JPCSP Model Ripping Guide

I have a problem. When i try to rip i get the .obj file but it has 0kb and nothing in it. What is wrong?
## Post #18
- Username: kratos1612
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 19, 2012 6:35 am
- Post datetime: 2012-02-18T22:42:40+00:00
- Post Title: Re: JPCSP Model Ripping Guide

Hello to all. 
I have a problem with the glxtractor and it is that I cannot execute me a window of mistake appears when I select the java.exe jre6/jre7, the jpcsp works only well but I do not manage to initiate it with the glxtractor they might help me.

Or probably a guide puts with images in order that mas persons deal in advance thank you for everything.
## Post #19
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2012-02-18T23:22:55+00:00
- Post Title: Re: JPCSP Model Ripping Guide

how do you guys rip textures by jpcsp?
## Post #20
- Username: kratos1612
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 19, 2012 6:35 am
- Post datetime: 2012-02-25T03:54:05+00:00
- Post Title: Re: JPCSP Model Ripping Guide

Hello again everyone, I was finally able to run and ontener obj file, import it but with 3d max I get an error of vertices, I could say any program to open the model you want is kratos from god of war
## Post #21
- Username: RAWTalent
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jul 08, 2011 8:39 pm
- Post datetime: 2012-03-11T15:30:41+00:00
- Post Title: Re: JPCSP Model Ripping Guide

I have everything working except getting GLE to recognise JPCSP, how do I make that link? IE where ti says "choose app"?
## Post #22
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2012-03-11T22:55:55+00:00
- Post Title: Re: JPCSP Model Ripping Guide

I'm having trouble recognizing your problems, people. Visual aids would be most helpful to helping you.
## Post #23
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2012-03-12T02:05:33+00:00
- Post Title: Re: JPCSP Model Ripping Guide

> Step 1: Download JPCSP from here http://jpcsp.org/
>
> 
>
> Step 2: Download GLXtractor from here http://members.chello.at/alexan/ or http://www.mediafire.com/?f8259dcq15fcl12
>
> 
>
> Step 3: Download JRE6 or 7 (the java runtime environment) from here http://www.oracle.com/technetwork/java/ ... index.html and choose that folder's java.exe in GLXtractor
>
> 
>
> 
>
> 
>
> Step 4: Upload your SAVEDATA folder to JPCSP's SAVEDATA folder (JPCSP revisions after r2099 will require Save Game Deemer's decrypted saves)
>
> 
>
> Step 5: Put your ISO in JPCSP's UMDimages folder (here a tutorial made by scanseng11 : http://www.youtube.com/watch?v=-SJ8kePnKaA) and load GLXtractor and then JPCSP
>
> 
>
> Step 6: Run JPCSP, go to the desired location, and press CTRL+SHIFT+F
>
> 
>
> The OBJ will be in the JPCSP folder and the textures will be in your My Documents/Xtracted folder

I have followed the tutorial and tried to capture the cube from the "cube.iso" but doesn't capture anything
## Post #24
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2012-06-15T16:57:56+00:00
- Post Title: Re: JPCSP Model Ripping Guide

> Reply from FEATHER
>
> Step 1: Download JPCSP from here http://jpcsp.org/

Step 2: Download GLXtractor from here http://members.chello.at/alexan/ or http://www.mediafire.com/?f8259dcq15fcl12

Step 3: Download JRE6 or 7 (the java runtime environment) from here http://www.oracle.com/technetwork/java/ ... index.html and choose that folder's java.exe in GLXtractor



Step 4: Upload your SAVEDATA folder to JPCSP's SAVEDATA folder (JPCSP revisions after r2099 will require Save Game Deemer's decrypted saves)

Step 5: Put your ISO in JPCSP's UMDimages folder (here a tutorial made by scanseng11 : http://www.youtube.com/watch?v=-SJ8kePnKaA) and load GLXtractor and then JPCSP

Step 6: Run JPCSP, go to the desired location, and press CTRL+SHIFT+F

The OBJ will be in the JPCSP folder and the textures will be in your My Documents/Xtracted folder 

I have followed the tutorial and tried to capture the cube from the "cube.iso" but doesn't capture anything

Should I click on "Start Application" Button to initiate it?... becuz when I start it, opens java and instatly it closes... instead of opening JPCSP. and without starting the app, it doesn't rip anything, even if I perform CTRL+SHIFT+F
What should I do?
## Post #25
- Username: Spira1&He1ix
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jun 24, 2012 11:44 pm
- Post datetime: 2012-06-24T15:50:32+00:00
- Post Title: Re: JPCSP Model Ripping Guide

Sorry for bump a dead thread,but with Jpcsp 2572 you no need for another plugin to rip model,because the developer of this emu has make it own ripper and export in .obj file,see my link for decription:[http://buildbot.orphis.net/jpcsp/](http://buildbot.orphis.net/jpcsp/)
## Post #26
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-06-24T21:50:58+00:00
- Post Title: Re: JPCSP Model Ripping Guide

> Reply from Spira1&He1ix
>
> Sorry for bump a dead thread,but with Jpcsp 2572 you no need for another plugin to rip model,because the developer of this emu has make it own ripper and export in .obj file,see my link for decription:http://buildbot.orphis.net/jpcsp/

Awesome, that'll save some time
## Post #27
- Username: Spira1&He1ix
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jun 24, 2012 11:44 pm
- Post datetime: 2012-06-25T02:01:28+00:00
- Post Title: Re: JPCSP Model Ripping Guide

> Reply from GDL
>
> Spira1&He1ix wrote:Sorry for bump a dead thread,but with Jpcsp 2572 you no need for another plugin to rip model,because the developer of this emu has make it own ripper and export in .obj file,see my link for decription:http://buildbot.orphis.net/jpcsp/

Awesome, that'll save some time

Yes,I'm success ripping from Ghost of War: Ghost of sparta,and another awesome function of this version is that you can change texture on the fly,no need to change texture in iso file for modding game.I love Jpcsp
