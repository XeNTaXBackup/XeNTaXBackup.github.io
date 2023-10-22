## Post #1
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-09-18T20:33:38+00:00
- Post Title: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Hey guys, it's me again 
Thanks to you guys, and especially to Szkaradek123 for helping me out to rip backyard wrestlings 3d models.
I was able to successfully mod a few characters into THUG PRO and i got most of them waiting to be accepted at vg-resource, so anybody can download them if they want to 


Now i wanna do the same with marc eckos getting up character models (PC-Version)! Luckily the texture format (.st) has been figured out already:
[viewtopic.php?t=15491](https://forum.xentax.com/viewtopic.php?t=15491)
If you all remember albinoleopard and his ps23dformat wiki, you can probaply guess from where i got my spark to try to rip these models 
It seems that he figured out start and ending of vertecies and faces! (Copy of the page with lose file documentation in attatchment. Html)
Now i have it a shot with model researcher myself and got a nice pointcloud that showed a character in tpose. So the 3d model file seems to be the same on ps2 and PC, since i used the ps23dformat Information on the pc-files (tranes model files in attatchment aswell).
To be honest i didnt really have a clue what i was doing in model researcher but i was pretty proud of my little progress!
So again i kindly want to ask you dedicated forum members to help me convert the 3d files into something readable so i can mod a little and provide the original files to everybody that wants to have them 
Thank you for taking your time reading this.

P.s.: i found some russian blog that seemed to have some getting up models to download:

[http://candykond-sergio.blogspot.com/20 ... p.html?m=0](http://candykond-sergio.blogspot.com/2012/09/marc-eckos-getting-up.html?m=0)
[http://candykond-sergio.blogspot.com/20 ... s.html?m=1](http://candykond-sergio.blogspot.com/2012/10/happy-birthday-25-years.html?m=1)
Sadly the file is not available for download anymore :-/

Ohh and if you guys wanna get your hands in the games Graffiti-Art, i uploaded it here:
[https://www.textures-resource.com/plays ... ure/10280/](https://www.textures-resource.com/playstation_2/markeckosgettingupcontentsunderpressure/texture/10280/)

Thank you again for listening, if you made it till here 
[Marc_Ecko's_Getting_Up-Contents_Under_Pressure.zip](https://xentaxbackup.github.io/file/16776_Marc_Ecko's_Getting_Up-Contents_Under_Pressure.zip)
## Post #2
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-09-18T20:47:36+00:00
- Post Title: Marc Ecko's - Getting Up: 3d-Models (.msh file)

sorry for double Post, but it wouldnt let me attatch two files  Sendung all this from my phone.
So heres the .msh file
[FTrane_Act2.zip](https://xentaxbackup.github.io/file/16777_FTrane_Act2.zip)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-19T01:49:13+00:00
- Post Title: Marc Ecko's - Getting Up: 3d-Models (.msh file)

using hex2obj (view links in my sig):
.



Trane_Act2-msh.png (95.74 KiB) Viewed 524 times


It's oddities like such in the face indices list which make the sub meshes hard to detect:

```
f 705 707 706
f 706 707 2
f 707 1 2
f 2 1 708
f 1 726 708
f 708 726 1
...
```
## Post #4
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-09-22T19:46:03+00:00
- Post Title: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Sorry for taking so long to respond but i was super busy with work...we are doing the german dub-version of the NFL-games.
Anyway thank you very much for your reply and effort, shakotay2!

As you can see i was able to get a pleasing result with your help and this sweet hex2obj tool. The uvs had to be scaled by -1 on the y-axis and the mesh itself on the x-axis by -1 aswell.
Thanks for helping me till here!

My next question is:
Is it possible to co-search submeshes in hex2obj, too? Or do i have to look for all submeshes and export them as a single object and later combine them in blender?
I want to make a script, that exports all characters
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-22T20:58:53+00:00
- Post Title: Marc Ecko's - Getting Up: 3d-Models (.msh file)

> Reply from Henchman800 ↑Mon Sep 23, 2019 3:46 am at Mon Sep 23, 2019 3:46 am
>
> My next question is:
Is it possible to co-search submeshes in hex2obj, too? Or do i have to look for all submeshes and export them as a single object and later combine them in blender?That's the question here: how to find the 2nd submesh (SM). May require some trial 'n error. Getting them as one object produces a spoiled mesh.
From this list I'd guess the 2nd SM should start with f 708 1 726 or f 726 708 708 or something like this.
...
f 2 1 708
f 1 726 708
f 708 726 1
...

> I want to make a script, that exports all charactersFirst you need solve the above mentioned question. 

Here's another SM (destruction mesh, whatever) of Trane_Act2:

0x1AB4D 3387
Vb1
16 99
0x14DAB 1254
021000
0x0 255
## Post #6
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-09-26T23:49:49+00:00
- Post Title: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Another night dubbing NFL.....

I ran into a problem. Everytime i try to use your settings for the second submesh and try to save it, hex2obj crashes on me :-/
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-27T09:01:07+00:00
- Post Title: Marc Ecko's - Getting Up: 3d-Models (.msh file)

thx for reporting - my bad, seems I bugged something into the last released exe.

well, missed an important line:
pFIs = (BYTE*) pFBuf ;

fixed version hex2obj_0.24e1.zip:

> Reply from shakotay2 ↑Tue Oct 22, 2013 10:06 pm at Tue Oct 22, 2013 10:06 pm
>
>
## Post #8
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-10-02T17:56:50+00:00
- Post Title: Marc Ecko's - Getting Up: 3d-Models (.msh file)

I gotta thank you man   

So i gave the second submesh a try, to find out that this was the odd mesh i Got out of ninja ripper like 2 years ago...

I wonder what it is....
And interestingly enought its missing the Head and left arm plus fingers like the other model....but why would it make sence to Split a character in 2 submeshes like that? I also noticed that the .msh file for another character (Medium boss) is much smaller.

Spleen_01: 53 KB
Trane_Act2: 120 KB

(Spleen's .msh-file is in attatchment)

(Found this via Google "getting up spleen")
i Got the faceindecies start right with 0x94B9 it seems...nur i cant get the right vertecies start...

[Spleen_01.zip](https://xentaxbackup.github.io/file/16845_Spleen_01.zip)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-02T19:48:22+00:00
- Post Title: Marc Ecko's - Getting Up: 3d-Models (.msh file)

you can't start at 0x94b9 because of

f 1 2 3
f 2 4 3
f 3 4 5
f 4 6 5
f 5 6 19
f 6 20 19
f 19 20 21
f 20 22 21
f 21 22 29
f 22 30 29
f 29 30 31
f 30 32 31
f 31 32 39
f 32 40 39
f 39 40 41
f 40 42 41
f 41 42 43
f 42 44 43
f 43 44 45
f 44 46 45
f 45 46 1301 <<<<
f 46 1 1301 <<<<

correct start address of face indices is at 0x94ed:
f 1 2 3
f 2 4 3
f 5 6 7
f 6 8 7
...



spleen_01.png (128.04 KiB) Viewed 434 times

(got a superfluous face again)
## Post #10
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-10-02T20:29:19+00:00
- Post Title: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Thanks for the quick response man. Really appreciate your help on this   

I dont get it.....so my faceindecies was one Position too far...same with vertecies: my best guess was 128 but it was 127...


I put the resulting Spleen.obj into blender:
So although spleens file is way smaller he still carries another submesh with the missing fingers and head.
What could be the season in splitting every character in 2 parts like this? Why not head separate from Rest of Body instead?

Thank you very much again for your work and time with this 

EDIT:
could it be that tranes second submesh starts directly where the first one ends?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-03T07:51:45+00:00
- Post Title: Marc Ecko's - Getting Up: 3d-Models (.msh file)

> Reply from Henchman800 ↑Thu Oct 03, 2019 4:29 am at Thu Oct 03, 2019 4:29 am
>
> 
EDIT:
could it be that tranes second submesh starts directly where the first one ends?You need to try it out. There's face  indices counts before the submeshes (SM) start. For spleen 1300 precedes the fst one (so it's not 1305 as in my previous post).
For him I got a point cloud only for the 2nd SM.
.



spleen_01-mesh_hex.jpg (248.33 KiB) Viewed 414 times


(correction: in the above picture end of SM is before the 01)
## Post #12
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-10-03T14:59:09+00:00
- Post Title: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Awesome man thx!

I played around with the settings a little that you provided. 26 seems to be the right face count, since 27 boosts up the vertex count by so much.

But you obviously got the right amount of vertecies in the Shown point cloud (GREAT JOB! by the way). So does it mean that we might have the wrong start of faces?


IMPORTANT NODE:
it seems that Indiana Jones and tomb raider (slayer engine versions) use the same Format .msh
So we can probaply solve the issue for all these games
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-03T16:27:11+00:00
- Post Title: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Next face indices' (FIs) block at 0x61e7 + 361x36 (dec.) = 0x94ab
So there's a "wide range of guessing".  

The assumed start of face  indices usually is NOT the start here as you may have noticed.  
You need to look at the hex dump in my post as of Thu Oct 03, 2019 8:51 am to understand where the FIs' start to be located.

Look into the created test.obj files for the assumed start of FIs' block:

f 1 4 5
f 4 6 5
f 5 6 7
f 6 8 7
f 7 8 9
f 8 10 9
f 9 10 11
f 10 12 11
f 11 12 13
f 12 14 13
f 13 14 15
f 14 16 15
f 15 16 17
f 16 18 17
f 17 18 32
f 18 34 32
f 32 34 35
f 34 36 35
f 35 36 37
f 36 38 37
f 37 38 583 <<<
f 38 1 583
f 583 1 689
f 1 690 689
f 689 690 691
f 690 692 691
f 691 692 693
f 692 694 693
f 693 694 695
...

Looks as if 583 is the FI count here. So you need to find that 46 02 (hex of  (583-1)) in the hexeditor.
Problem is that the following FIs are bigger than 362. So sad...

But there's other data where it fits:
.



spleen_0xa6d2.png (61.66 KiB) Viewed 405 times
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-04T17:49:09+00:00
- Post Title: Marc Ecko's - Getting Up: 3d-Models (.msh file)

> Reply from shakotay2 ↑Thu Oct 03, 2019 3:51 pm at Thu Oct 03, 2019 3:51 pm
>
> For him I got a point cloud only for the 2nd SM.well, the trick is to keep the start of vertices of the first submesh:
.



spleen_01_SM02.png (102.3 KiB) Viewed 385 times


I assume there's still 75 vertices left (688 + 285 +75)

edit: well, I think I've got the scheme now how it's working... (FI count is 144, though)
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-04T21:29:16+00:00
- Post Title: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Trane, 2nd SM and bottle belt:
.



Trane_act2-2ndSM.png (98.37 KiB) Viewed 373 times
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-04T22:09:52+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Trane's head:
.



Trane's Head.png (93.76 KiB) Viewed 281 times
## Post #17
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-10-08T08:32:08+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

OOHHH MY GAWD!!!
wow! Thank you so much and congratulations on understanding the file structure now!  


Everything works perfectly fine now with trane and spleen  

What I've learned (from the mighty shakotay2):
-the game uses one list for all vertecies and Multiple ones for faceindecies
-although theres a .msh file for tranes head, the regular trane .msh file also contains one
-you have to do alot of guessing when it comes to finding start of vertecies and faces
-hex2obj is your friend!!!! Use it, read the tutorial and do alot of trial and Error with your models!
-be polite on xentax and Benefit of the members great knowledge!
(please feel free to correct me if im wrong  )

Thank you so much again! Its a dream to finally See trane fully ripped and not being screenprinted and scaled back and forth to somehow look like the original model.

My next quest would be to get/make a script that right on exports all characters....but im like lvl 0 on that :-/
So my questions are:
-can i continue this thread for the task of making a script or should i switch into a new Section with a new thread?
-is the Information we have enough to make a script?
-is it smarter to go for quickbms or noesis? (I kinda Prefer the noesis idea since it lets you view the files before export)


To kinda sum everything up i wanna give a fat ass thank you to shakotay2 again....it simply wouldnt have been possible without him!!! And i hope this thread showed you that YOU can do it! Get your game assets ripped! It takes dedication, time and a basic understanding (i did it on the train or when i had some time to Kill At work)...but it is possible for sure! And this is the right place to start out!

Thank you so much again
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-08T13:50:48+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

> Reply from Henchman800 ↑Tue Oct 08, 2019 4:32 pm at Tue Oct 08, 2019 4:32 pm
>
> 
-you have to do alot of guessing when it comes to finding start of vertecies and faceswell, you could use this tool to ease getting the params (not perfect, so some guessing remains...  ):
.


 Make_obj-MEcko'sGU.zip
(53.59 KiB) Downloaded 42 times


(attention: some lines in the logs are pure nonsense, for example for Trane: # 0 FIcnt: 65280, 0xe2
 But better than to lose important informations using a too low threshold.)

> My next quest would be to get/make a script that right on exports all characters....but im like lvl 0 on that :-/The above linked tool is what I can provide - someone else could make a script.

> So my questions are:
>
> -can i continue this thread for the task of making a script or should i switch into a new Section with a new thread?Feel free to do as you wish.

> -is it smarter to go for quickbms or noesis? (I kinda Prefer the noesis idea since it lets you view the files before export)Quickbms usually is for extracting/decompressing, so yes, Noesis is the better choice here, imho.
## Post #19
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-10-08T14:34:24+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Thanks for this neat looking tool!
Sadly i got this error:

this occured on both of tranes act1 variants (see attatchment). So does the tool give me (if everything works correctly) the adresses of every SM?
Best regards

....ohhh and by the way: "Kommst du rein zufällig aus Deutschland?" ^^
[Trane_Act1.zip](https://xentaxbackup.github.io/file/16872_Trane_Act1.zip)
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-08T15:59:13+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

> Reply from Henchman800 ↑Tue Oct 08, 2019 10:34 pm at Tue Oct 08, 2019 10:34 pm
>
> 
Thanks for this neat looking tool!
Sadly i got this error:you can ignore it - it's a warning only.

> So does the tool give me (if everything works correctly) the adresses of every SM?You never can be sure.  (The answer can only be given for a specific model where you assume some SM to be missing - I could have a look at then.)
In the log for Trane_Act1 this line
# 2 FIcnt: 65280, 0x14eb2
to be ignored - guess, that's where the 2nd FI count value doesn't match.
Same goes for ...Toy:
# 0 FIcnt: 65280, 0xcf
# 2 FIcnt: 65280, 0xd514

> ....ohhh and by the way: "Kommst du rein zufällig aus Deutschland?" ^^yep
## Post #21
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-10-17T14:11:07+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Ok I was finally able to give the tool a better try: I see now on how it gives me adresses at least^^
I tried a little with tranes act 1 "toy" version:

(I used the vertecies start of tranes act 2 model)
the faces seem to go crazy though, since it looks for vertecies around 53000.....and that seems a little too much. 
I hope theres a pattern to it and that not all models are patched together randomly. Both of tranes Act 1 models should be very similar...the only difference should be a bag that he loses in the middle of act 1.

TRANE ACT 1


TRANE ACT 1 "Toy"


The Head-Texture just adds a scar on the eyebrow in the "toy" version

ACT 1 ---> ACT 1 "Toy"
Thanks again man!

Ohhh.....und mir gefällt der Ausdruck Fettringe für die komische Submesh...haha das beschreibt es wohl am besten ^^
## Post #22
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-10-29T10:57:44+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

HELLO THERE AGAIN
I kindly wanted to ask Who here is able and willing to create a noesis / quickbms script out of the existing Information provided by shakotay2. Then we can export all getting up characters and make em do funny poses to create wallpapers that are like the freeze frame in friends intro
## Post #23
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-11-07T03:17:45+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Friendly bump
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-07T09:34:56+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

You're better off to use the parameters provided by the tool and combine them.

I'm sorry to say that trying to put that in a script is a waste of time and life for me as you may see from the picture:
.



Trane's params.png (55.51 KiB) Viewed 191 times
## Post #25
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-11-08T20:59:18+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Hey Shakotay,
I'm sorry, but I once need your wisdom to make this happen:


When I tried your tool the first time with sticking to the standard value of 58, it created a .obj-log with 1kb in my test folder. It didn't contain any information when i opened it with the editor.
I then again tried it with the vAddr start of tranes act 2 .mesh but the make_obj_log stays unaffected.

I'm sorry if I got the instructions wrong, but if you can make it step by step clear for me, I'll be happy to rip all the models I want with your awesome hex2obj and then provide the uploaded models here in this thread if thats cool 

Thank you very much again for your patience,
Best regards
## Post #26
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-09T08:31:10+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Forget about the 58 - it's for another format.

- load Trane_Act2.msh into Make_obj_ME-GU-log.exe
. close the warning window "FIcnt doesn't match 2nd value! (do we have a prob?)"
- close the app

Makeobj_log.obj contains

```
# 1 vAddr: 0xe738
# 2 vAddr: 0x12720
# 3 vAddr: 0x1370d
# 4 vAddr: 0x14212
# 0 FIcnt: 65280, 0xe2
# 1 FIcnt: 693, 0xdcec
# 2 FIcnt: 532, 0xe28c
# 3 FIcnt: 654, 0x1c5e9
# 5 vBlock(s) (4 FI block(s))

# further FIs?
# 0 FIcnt: 1332, 0xd23a
# 1 FIcnt: 905, 0x11f8a
# 2 FIcnt: 151, 0x13406
# 3 FIcnt: 144, 0x13f55
# 4 FIcnt: 144, 0x14aee
# 5 FIcnt: 3386, 0x1ab4d

```


Now you need to combine the values; there's no rules but
"generally the lowest vAddr is the base for some meshes"

Two working H2Os:

0xDCEC 693
Vb1
36 16
0x148 1100
021000
0x0 255

0xD23A 1333
Vb1
36 16
0x148 707
021000
0x0 255

You enter any FI address/FI count pair (0xDCEC 693 or 0xD23A 1333 for example) into hex2obj,
toggle the "noStr" button to "Strip", enter 36 as  an FVFsize value and press "go1".

> Then scroll down in the left lower list box
>
> to get the vertex count which has to be entered
>
> in the belonging editbox.

Use the lowest vertex address (0x148).

For other submeshes choosing a suiting vertex start address is trial 'n error,
head for example:

0x11F8A 905
Vb1
36 16
0xE738 399
021000
0x0 255

> (attention: some lines in the logs are pure nonsense, for example for Trane: # 0 FIcnt: 65280, 0xe2
>
> But better than to lose important informations using a too low threshold.)
## Post #27
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-11-11T14:13:16+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Holy Sh*t! It worked!!!
Thank you once again man! Your tool digs so deep it even ripped tranes grandma   

(...shes part of the game though^^)

Here are the characters I was able to rip so far:


As you can see Gabes first model (front row, left side) did not rip fully:

(I marked the adresses/counts that worked with hex2obj)
The tool will eventually crash when i try to load gabes model. it will just continue with the same adress forever.
Chief Hunts model doesnt even give me a log file. Is there any differences with the model? Or did I use wrong vertexblock settings (36 - 16). It would be awesome if you could have a look at them. Both model files for Hunt and Gabe are in the attatchment:


 Hunt_n_Gabe.zip
Models: Chief Hunt, Gabe_01 (57.23 KiB) Downloaded 18 times


Thank you very much for your patience and effort again killa! 

EDIT:
Never mind, hunt works  I just went off the regular workflow and messed something up.
Im still missing parts of gabes model though
## Post #28
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-11T17:18:02+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Thanks for reporting!
Gabe_01:

```
# 1 vAddr: 0x7eb9
# 0 FIcnt: -16777216, 0xbf
# 1 FIcnt: 304, 0x7bd5
# 2 FIcnt: 67, 0xbc49
# 3 FIcnt: 112, 0xda00
# 2 vBlock(s) (4 FI block(s))

# further FIs?
# 0 FIcnt: 1182, 0x7255
# 1 FIcnt: 783, 0xb5f7
# 2 FIcnt: 772, 0xd3d2
```
("-16777216" is nonsense, of course)
I've updated the zip here:

> Reply from shakotay2 ↑Tue Oct 08, 2019 9:50 pm at Tue Oct 08, 2019 9:50 pm
>
> 
(You should keep a backup of the previous exe in case the patch "breaks" the previous working msh files which I didn't check again.)
## Post #29
- Username: il capo di tutti
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jun 07, 2018 12:38 pm
- Post datetime: 2019-12-28T22:31:17+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Thank you very much Shakotay, your MakeObj script works so smooth, and  I always wanted to rip those models too. But hey, I'm having troubles with one specific mesh. When I click mesh, the 3d viewer doesn't load. 

It only happens with this one so far [https://www.upload.ee/files/10903433/MPA_01.msh.html](https://www.upload.ee/files/10903433/MPA_01.msh.html)
I was hoping you can save the day, again. Thx
## Post #30
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-29T08:41:36+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

> Reply from il capo di tutti ↑Sun Dec 29, 2019 6:31 am at Sun Dec 29, 2019 6:31 am
>
> When I click mesh, the 3d viewer doesn't load.The viewer simply refuses to load obj files with invalid vertices (QNANs, not a number):
v -1.#QNAN0 -704477396992.000000 34359738368.000000
This happens because some vertex/faceIndices address combinations are not allowed.
(Finding out which are valid is a trial 'n error so far.)
.



MPA_01.png (91.38 KiB) Viewed 112 times
## Post #31
- Username: il capo di tutti
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jun 07, 2018 12:38 pm
- Post datetime: 2019-12-30T04:33:25+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

> Reply from shakotay2 ↑Sun Dec 29, 2019 4:41 pm at Sun Dec 29, 2019 4:41 pm
>
> 
il capo di tutti wrote: ↑Sun Dec 29, 2019 6:31 amWhen I click mesh, the 3d viewer doesn't load. The viewer simply refuses to load obj files with invalid vertices (QNANs, not a number):
v -1.#QNAN0 -704477396992.000000 34359738368.000000
This happens because some vertex/faceIndices address combinations are not allowed.
(Finding out which are valid is a trial 'n error so far.)
.
MPA_01.png

You were right. Now I extracted two different heads, but I never got the body that's supposed to be there, somewhere. I mixed all the possible combinations and nothing.   damnit
Thx for ur time tho
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-30T08:35:34+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Some body addresses (ragdoll mesh? whatever) need to be found manually:
.



MPA_01-body.png (62.33 KiB) Viewed 96 times



extra body part:

0xE967 75
Vb1
16 99
0xCED9 322
021000
0x0 255
## Post #33
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-06-03T09:33:09+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

FOR ALL OF THOSE, THAT JUST NEED A SPECIFIC MODEL NOW:
[https://www.models-resource.com/pc_comp ... rpressure/](https://www.models-resource.com/pc_computer/markeckosgettingupcontentsunderpressure/)
They have finally been accepted  

JOIN THE GETTING UP DISCORD
[https://discord.gg/mvfRze3nVa](https://discord.gg/mvfRze3nVa)
Alot more stuff going on there
## Post #34
- Username: JasonVoorhees
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Nov 14, 2022 5:17 am
- Post datetime: 2023-04-06T12:47:56+00:00
- Post Title: Re: Marc Ecko's - Getting Up: 3d-Models (.msh file)

Could Someone Convert And Pass The .MSH Files Of The Videogame Called Indiana Jones And The Emperor's Tomb To The H20?
