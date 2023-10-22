## Post #1
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2014-07-10T04:11:26+00:00
- Post Title: Help Macross 30 MLD

I can not open this with conventional tools, the format seems similar to Valkyria Chronicles also dynasty warriors 7, any help would be appreciated thanks


Here is a sample [https://dl.dropboxusercontent.com/u/128 ... s%2030.rar](https://dl.dropboxusercontent.com/u/12804628/Temp/konig%20monster%20macross%2030.rar) The extension is "MLD" but the header is HLDM.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-07-10T15:16:11+00:00
- Post Title: Help Macross 30 MLD

since there are too many submeshes I made a tool:
[http://www.uploadmb.com/dw.php?id=1405005143](http://www.uploadmb.com/dw.php?id=1405005143)



mb_b61.JPG (117.44 KiB) Viewed 629 times



There were some smaller submeshes which seemed to have a vertex block size of 24 instead of 28.
Those are excluded (depending on the threshold of 54 vertices (lower right editbox value)).

Interestingly teb61_01.dds seems to be used for several models:
[](http://www.pic-upload.de/view-23849011/mb_b61-tex.jpg.html)
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-07-10T22:30:11+00:00
- Post Title: Help Macross 30 MLD

I have had a beta tool for this for quite some time, but don't intend to finish it because all veritech models are in like 200 little pieces that are randomly placed all over the place. Maybe someone can figure out how the animation data to see how the data transformed. Kind of lost interest in this one.
[beta.7z](https://xentaxbackup.github.io/file/7567_beta.7z)
## Post #4
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2014-07-10T22:35:23+00:00
- Post Title: Help Macross 30 MLD

That is amazing, The models being in pieces is an easy fix. it takes a lot of time, but it is so worth it, once I have the model in blender I join it all and subdivide
 it into the pieces it once was, it takes me a very long time, but the end result is worth it.
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-07-10T22:39:28+00:00
- Post Title: Help Macross 30 MLD

this is how bad it is lol



source code for shakotay if he wants to complete it:


 macross30.7z
(9.57 KiB) Downloaded 157 times



it extracts i believe all models and most textures, but misses out on a few non-square morton textures.
## Post #6
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2014-07-10T22:41:41+00:00
- Post Title: Help Macross 30 MLD

Didn't see that coming. Uh, okay with a lot more patience than a saint someone could put that back together again. But that's really strange, the script for the koing extracted it almost perfectly, it was just grouped weird.
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-07-10T22:44:27+00:00
- Post Title: Help Macross 30 MLD

i tried shakotay's script on data/ms/000/gb_000.obj and it output a blank obj.

anyways, if you have already used offzip, i recommend using my ripper to extract the archives at least as it puts stuff in actual folders.
## Post #8
- Username: Rygdea
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Aug 16, 2010 7:27 pm
- Post datetime: 2014-07-10T22:49:08+00:00
- Post Title: Help Macross 30 MLD

shakotay's script worked on the konig (ms/b61) fine here, the model came intact but sadly on what else I tried it hasn't.
## Post #9
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2014-07-10T22:49:39+00:00
- Post Title: Help Macross 30 MLD

Yes it was very useful, now every thing is in folders and ready to go. you spoke about a script you had that converted the files of last frontier into obj's in bulk ? but the links are all dead.
A picture of the koing loaded into blender.
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-07-10T22:55:31+00:00
- Post Title: Help Macross 30 MLD

I'm very sorry I don't have The Last Frontier ripper anymore.
## Post #11
- Username: Chthonic
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 23, 2012 4:08 am
- Post datetime: 2014-07-10T23:28:48+00:00
- Post Title: Help Macross 30 MLD

> Reply from howfie
>
> I'm very sorry I don't have The Last Frontier ripper anymore.

You're a GOOD man Howfie and to prove I'm not a bad guy here's the source you gave me two years ago

[https://www.dropbox.com/s/iri98z9x96jbu ... ontier.cpp](https://www.dropbox.com/s/iri98z9x96jbup9/ps3_macross_frontier.cpp)
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-07-10T23:38:58+00:00
- Post Title: Help Macross 30 MLD

sorry i couldn't complete this... after i ran into those nasty veritech meshes, i gave up on this. if shakotay wants to try and solve the problems with these meshes, i posted my source code. hopefully it will save him some time.
## Post #13
- Username: Chthonic
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 23, 2012 4:08 am
- Post datetime: 2014-07-10T23:41:00+00:00
- Post Title: Help Macross 30 MLD

> Reply from howfie
>
> sorry i couldn't complete this... after i ran into those nasty veritech meshes, i gave up on this. if shakotay wants to try and solve the problems with these meshes, i posted my source code. hopefully it will save him some time.
That was that coding script we talked about, but hey it's what happens.
## Post #14
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2014-07-10T23:42:30+00:00
- Post Title: Help Macross 30 MLD

Oh that's fine howfie. was just a question. it seems your new ripper is even better any ways!
 the models are in pieces but still, reconstructing them just takes time.
## Post #15
- Username: Rygdea
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Aug 16, 2010 7:27 pm
- Post datetime: 2014-07-11T00:40:20+00:00
- Post Title: Help Macross 30 MLD

Vajra work fine also with Howfie's.... but oh man the Valks lol, so messy.

Wonder why it comes up like that, I mean both the Konig and to a lesser extent Vajra also transform ingame if it's an issue to how the game handles that.
## Post #16
- Username: Chthonic
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 23, 2012 4:08 am
- Post datetime: 2014-07-11T00:53:58+00:00
- Post Title: Re: Help Macross 30 MLD

> Reply from Rygdea
>
> Vajra work fine also with Howfie's.... but oh man the Valks lol, so messy.

Wonder why it comes up like that, I mean both the Konig and to a lesser extent Vajra also transform ingame if it's an issue to how the game handles that.

It's goes back to the original VF-X game for PSX. It's the transformation animation that has been hardcoded into the game, all variable fighters are like this, can't escape it.
## Post #17
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2014-07-11T07:47:12+00:00
- Post Title: Re: Help Macross 30 MLD

Or you know, you could always reveal to the class how you managed to make your models come out like this.  [http://www.macrossworld.com/mwf/index.p ... opic=37914](http://www.macrossworld.com/mwf/index.php?showtopic=37914) (scroll down he post pictures)

I got the models into blender as OBJ's they are not nearly as bad as I thought they would be, but my friend discovered something interesting, the models are not complete, the game script transforms them but (in mid animation) swapping out a new model part for the transformation, that's why there are three model types, MB/MF and MG I have started rebuilding the VF-27, I will work on the VF-25 next, it takes a hell of a lot of time, but the models UV map is still intact and the textures look amazing on it. i did see something, it looks like the model is squished symmetrically, I think the model is to big, when it gets converted to OBJ it needs to shrink the model, cause I think blender is the thing squishing the model because it's outside the grid. I also looked into the animations, when converting in the text box it says something interesting. "This object has weights" appears every time it converts something. this means that it's weighted to a bone like a skeleton that's not being imported with it.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-07-11T08:24:33+00:00
- Post Title: Re: Help Macross 30 MLD

> Reply from howfie
>
> source code for shakotay if he wants to complete it:thank you - but I don't want to dig too deep into this. Also I don't have the include files (X_GAME library?) to perform a quick compile.

> Reply from howfie
>
> i tried shakotay's script on data/ms/000/gb_000.obj and it output a blank obj.the konig tool was made on the base of mb_b61, mf_b61, mg_b61 mdl files.

But gb_000.mdl is working, too (it's from a VF0 folder sent to me). At least I don't see an error (don't know how the model's looking ingame):



gb_000.JPG (130.56 KiB) Viewed 347 times
## Post #19
- Username: Chthonic
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 23, 2012 4:08 am
- Post datetime: 2014-07-11T09:20:24+00:00
- Post Title: Re: Help Macross 30 MLD

> Reply from shakotay2
>
> howfie wrote:source code for shakotay if he wants to complete it:thank you - but I don't want to dig too deep into this. Also I don't have the include files (X_GAME library?) to perform a quick compile.
howfie wrote:i tried shakotay's script on data/ms/000/gb_000.obj and it output a blank obj.the konig tool was made on the base of mb_b61, mf_b61, mg_b61 mdl files.

But gb_000.mdl is working, too (it's from a VF0 folder sent to me). At least I don't see an error (don't know how the model's looking ingame):
gb_000.JPG

I'm curious if you could look at these two folders, the convertor distorts the conversion and the it doesn't render the models. 

[https://www.dropbox.com/s/craig1dfy9sdf3h/300.rar](https://www.dropbox.com/s/craig1dfy9sdf3h/300.rar)
[https://www.dropbox.com/s/jkkt199f5n0oe98/maq.rar](https://www.dropbox.com/s/jkkt199f5n0oe98/maq.rar)
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-07-11T12:46:17+00:00
- Post Title: Re: Help Macross 30 MLD

well, I see, it's a matter of vertex buffer format.

konig tool is just a quickhack.

Since there is a "near to perfect" (98%) solution from howfie
you should consider to use the included smcimport.py script with blender 2.49
to import the smc created by his tool.

Use xentax.exe to convert mb_maq.mdl to an smc file.
Then open a text window in blender, load the aforementioned py script (alt-o) , 
press alt-p to import mb_maq.smc. Works like a charm.
## Post #21
- Username: Chthonic
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 23, 2012 4:08 am
- Post datetime: 2014-07-11T22:57:50+00:00
- Post Title: Re: Help Macross 30 MLD

Use xentax.exe to convert mb_maq.mdl to an smc file.
Then open a text window in blender, load the aforementioned py script (alt-o) , 
press alt-p to import mb_maq.smc. Works like a charm.[/quote]

Thanks for the tip, I'm very good with Blender, but I don't see in XENTAX.EXE how you can convert *.MDL to a *.SMC File? Unless I'm messing something?
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-07-12T02:12:31+00:00
- Post Title: Re: Help Macross 30 MLD

Select Game: Macross 30
Select Path, 'Ok' button
Process DAT: No
Process FST: No
Process GFP: No
Process MDL: Yes

creates these files: mtl, obj (0 bytes), smc and txt
for any mdl in the specified path
## Post #23
- Username: ardenness
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Dec 04, 2016 5:20 pm
- Post datetime: 2017-05-05T01:26:16+00:00
- Post Title: Re: Help Macross 30 MLD

> Reply from shakotay2
>
> Select Game: Macross 30
Select Path, 'Ok' button
Process DAT: No
Process FST: No
Process GFP: No
Process MDL: Yes

creates these files: mtl, obj (0 bytes), smc and txt
for any mdl in the specified path

Maybe it's too late to ask some question to you? I recently tried to open .mdl with xentax.exe and Konig posted here but both are not working and stopped.
I'm using Windows 10 64bit, probably this is the reason. Is there any fix for it? Thx.
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-05-05T09:03:16+00:00
- Post Title: Re: Help Macross 30 MLD

> Reply from ardenness
>
> I recently tried to open .mdl with xentax.exe and Konig posted here but both are not working and stopped.
I'm using Windows 10 64bit, probably this is the reason.could also depend on the model, you used, dunno. I tried both exe files under Win7, 64 bit with gb_25a.mdl and they create outputs:



gb_25a-Win7.jpg (174.26 KiB) Viewed 216 times


(konig's obj output (right part of pic) required replacing of QNANs and cutting several overflowed values)

You might try out a VM to start XP or Win7 ("in a box"), just as a thought.
## Post #25
- Username: ardenness
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Dec 04, 2016 5:20 pm
- Post datetime: 2017-05-09T21:38:40+00:00
- Post Title: Re: Help Macross 30 MLD

> Reply from shakotay2
>
> ardenness wrote:I recently tried to open .mdl with xentax.exe and Konig posted here but both are not working and stopped.
I'm using Windows 10 64bit, probably this is the reason.could also depend on the model, you used, dunno. I tried both exe files under Win7, 64 bit with gb_25a.mdl and they create outputs:
The attachment gb_25a-Win7.jpg is no longer available
(konig's obj output (right part of pic) required replacing of QNANs and cutting several overflowed values)

You might try out a VM to start XP or Win7 ("in a box"), just as a thought.

Thank you. I installed Win7 on VM and successfully extracted obj and smc files. As you mentioned here, obj is terribly messed up, so I tried to open smc on blender 2.49.
And here's another problem. When open text window - select smcinport.py - run script, it shows error message then stopped working. Umm.
[Cap 2017-05-10 06-33-11-378.png](https://xentaxbackup.github.io/file/12873_Cap 2017-05-10 06-33-11-378.png)
## Post #26
- Username: ardenness
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Dec 04, 2016 5:20 pm
- Post datetime: 2017-05-09T21:44:42+00:00
- Post Title: Re: Help Macross 30 MLD

> Reply from shakotay2
>
> ardenness wrote:I recently tried to open .mdl with xentax.exe and Konig posted here but both are not working and stopped.
I'm using Windows 10 64bit, probably this is the reason.could also depend on the model, you used, dunno. I tried both exe files under Win7, 64 bit with gb_25a.mdl and they create outputs:
The attachment gb_25a-Win7.jpg is no longer available
(konig's obj output (right part of pic) required replacing of QNANs and cutting several overflowed values)

You might try out a VM to start XP or Win7 ("in a box"), just as a thought.

And here's the smc file that I want to open. Could you please, if you don't mind,  show me it works on you or not? Thank you.
[gb_210.7z](https://xentaxbackup.github.io/file/12874_gb_210.7z)
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-05-10T02:56:25+00:00
- Post Title: Re: Help Macross 30 MLD

> Reply from ardenness
>
> I tried to open smc on blender 2.49.
And here's another problem. When open text window - select smcinport.py - run script, it shows error message then stopped working. Umm.you need to show the console message.



gb_210.jpg (125.92 KiB) Viewed 216 times

(using python 2.6.2; script fails on python 3.0)
## Post #28
- Username: ardenness
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Dec 04, 2016 5:20 pm
- Post datetime: 2017-05-10T05:45:34+00:00
- Post Title: Re: Help Macross 30 MLD

> Reply from shakotay2
>
> ardenness wrote:I tried to open smc on blender 2.49.
And here's another problem. When open text window - select smcinport.py - run script, it shows error message then stopped working. Umm.you need to show the console message.
The attachment gb_210.jpg is no longer available(using python 2.6.2; script fails on python 3.0)

The error shown as below. Also the smc you attached seems messed same as obj, not so different. Sad. 
I may have to try arrange them one by one with obj. Deep thanks for your help.
[Cap 2017-05-10 06-32-52-482.png](https://xentaxbackup.github.io/file/12878_Cap 2017-05-10 06-32-52-482.png)
## Post #29
- Username: gmproxy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 01, 2021 12:02 am
- Post datetime: 2021-08-19T16:43:34+00:00
- Post Title: Re: Help Macross 30 MLD

Well, I've come to revive this.
## Post #30
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-19T17:34:00+00:00
- Post Title: Re: Help Macross 30 MLD

You can't revive "dead horses".  (You may try, of course, but usually it doesn't work.  )

At least this is the 2nd decent textured model I see...
## Post #31
- Username: gmproxy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 01, 2021 12:02 am
- Post datetime: 2021-08-19T19:50:05+00:00
- Post Title: Re: Help Macross 30 MLD

It was a ride, given that most of the information has years and it's definitely not recent.

While it's true that it's still a tedious quest, things have been shortened out. For instance, when importing to blender 2.X > 2.49, you can just select geometry>split by group, so that you don't need to go back to that ancient blender build. From there, you can give it the texture the txt (that appears after using the program to extract them) says, and from there, make the "lego without instructions experience".

While we couldn't get the name of all the units, we did find that gb usually stands for battroid mode, mg for fighter mode, and gf for gerwalk mode. This might not be news for any here, but since this wasn't documented at all, I might as well do it. 

The models are now in hands of the Gundam modelling discord from that thread in knockout chat website, so expect to see a few models outside at least. Sure, It'd be better if the tool was finished, and I intend to look into that next, but for now, it's better than nothing

F*ing good macross models are so damn hard to find
## Post #32
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2021-08-21T12:57:59+00:00
- Post Title: Re: Help Macross 30 MLD

Indeed, we got similar roads on this aspect, as originally i had suggested from Shatokay's help about the model structure of other game, and instead of begin a "beggar" that unfortunately some game research fans are, i took some of my free time at learning Hex2obj until i found the structure for retrieve the model correctly, and a script begin made later with the basis of my information, despite is still not 100% as some models suffer issues when importing, and the "lego without instructions" apply for landing gears as example thanks to lack of skeleton retrieval, at least isn't 50% more painful compared to Macross 30 models because begin battroid, or fighter, the transforming mechanism requires the model begin divided into a spread of parts by the game logistics.

As a minimum note, after finding out a good Vita decompressor, the recent Artdink game scripts worked like a charm for Delta Scramble models, but indeed aside of good model smoothing and all of them begin rigged on their original skeleton, the quality may be a left off compared to some models of 30 which indeed, got a higher quality without discussion, the only thing it sucks is 30 using a very old architeture of their workflow, which wasn't well documented compared to their newest one for models.

Not sure if the Gundam discord you mentioned, the plans of the people helping included the fighter mode models, which is something common at Macross, but isn't too common in other mecha gernes, but lowkey, would be interresed at downloading those models at some point, the thing is, unsure how the discord name would be to find the correct server. but yeah, looking forward for the contributions of the team, despite i agree 100% it'll be a painful task for sure, as a friend of mine offered long time ago at rebuilding YF-27 Lucifer as an example, and it took in total 2 to 4 days for just assembling the fighter mode.
## Post #33
- Username: GreenTrafficLight
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Apr 26, 2021 6:54 am
- Post datetime: 2022-08-03T00:20:32+00:00
- Post Title: Re: Help Macross 30 MLD

So, I don't get it, is there a actual finished script to import the models ? [Because I've made a ( unfinished ) Blender script to import the models.](https://github.com/GreenTrafficLight/Macross-30-Blender-Addon) Problem is, I didn't manage to import the normals ( I don't get the operation behind the 10 11 11 bit normals ).
## Post #34
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2022-08-03T17:22:00+00:00
- Post Title: Re: Help Macross 30 MLD

> Reply from GreenTrafficLight ↑Wed Aug 03, 2022 8:20 am at Wed Aug 03, 2022 8:20 am
>
> 
So, I don't get it, is there a actual finished script to import the models ? Because I've made a ( unfinished ) Blender script to import the models. Problem is, I didn't manage to import the normals ( I don't get the operation behind the 10 11 11 bit normals ).

How do you use the script??
## Post #35
- Username: GreenTrafficLight
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Apr 26, 2021 6:54 am
- Post datetime: 2022-08-03T17:50:34+00:00
- Post Title: Re: Help Macross 30 MLD

> Reply from Darko ↑Thu Aug 04, 2022 1:22 am at Thu Aug 04, 2022 1:22 am
>
> 
How do you use the script??

Download the zip and [install it in Blender](https://www.cgchan.com/static/doc/sceneskies/1.1/installation.html). After that it should be in File > Import > Macross 30
## Post #36
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2022-08-06T06:06:05+00:00
- Post Title: Re: Help Macross 30 MLD

> Reply from GreenTrafficLight ↑Wed Aug 03, 2022 8:20 am at Wed Aug 03, 2022 8:20 am
>
> 
So, I don't get it, is there a actual finished script to import the models ? Because I've made a ( unfinished ) Blender script to import the models. Problem is, I didn't manage to import the normals ( I don't get the operation behind the 10 11 11 bit normals ).

Huh, interesing, August indeed turned out to be the month for news about research efforts as other game i had interest got some news too.

About your question, in parts we had a "script", it worked as a external tool called "Steven Gas Machine" by XNAlara members, which was a suite made for a lot of games in general. it had a function for Macross 30 that it would convert the models in both .smc and .obj, but the state of them was very WIP, due both fighter, battroid and gearwalk models would be shuffled. from your look, the script already does a better job, no visible skeleton/armatures, but no shuffling either, is already a huge step compared to the previous one, even more i was looking for getting the fighter models.

Will be testing out in some hours, as i would need to get again the folder where i extracted the models and download the script.
## Post #37
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2022-08-06T07:26:42+00:00
- Post Title: Re: Help Macross 30 MLD

(image embeds removed due to Imgur's recent ToS changes about inactive photos)

Tested out, using 2.92 which is my current Blender version to work(i was testing 3.1 before, but the plugin compatbility was one of the main reasons i decided to downgrade), and indeed, is a very nice suprise for sure, even if is unfinished.

Tested with both models i had interest(the VFs in both Battroid, Gearwalk and Fighter modes), but also with other ones, like the Koeingmonster which was one of the testbeds of the old thread that Steven Gas Machine went developed, a Varja, Reguloid, and the SDF-1 Macross itself, which was one of the models that got different results, as some of the decal textures imported, but the rest of the material not, but isn't such a huge issue either due it can be solved manually in few seconds.

Clear Scene indeed is dependent for importing the models, as trying to import multiple models would broke due it makes callback to the armature data files, i tested out trying to import both Chronos and Durandral at the same scene, but Durandral broke by making the callback to Chronos' rest pose instead. also, by doing Ctrl + Z it results on a instant crash, due it would be the same as trying to trigger the script action again but without the selected model callback.

The models got armature data translated too, despite not on the traditional way but using sockets instead, as i tested out with some MGSV TPP models a friend of mine sent to me before(Salenhantropus to be specific), despite is a bit weird coming from a user that works with the other type of armatures, is still suprising to see it was possible to retrieve the armature data, as most users tend to avoid by begin a complex data to translate when writing scripts.

Also checked your Github page, and you got a interesing portifolio also, aside of this script you worked on import scripts for the Initial D Arcade Stage games, along for Ridge Racer(6, 7 and Vita i guess due to Fengo/Nenkai thread at Xentax), but overall, nice work in general even for a unfinished script(in parts imo, due it translates well most of the important models well), and nice to see it came out, despite years later as most people almost forget the existance and interest.
## Post #38
- Username: GreenTrafficLight
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Apr 26, 2021 6:54 am
- Post datetime: 2022-08-06T21:39:10+00:00
- Post Title: Re: Help Macross 30 MLD

> Reply from RythusOmega ↑Sat Aug 06, 2022 2:06 pm at Sat Aug 06, 2022 2:06 pm
>
> 
About your question, in parts we had a "script", it worked as a external tool called "Steven Gas Machine" by XNAlara members,

> Reply from RythusOmega ↑Sat Aug 06, 2022 3:26 pm at Sat Aug 06, 2022 3:26 pm
>
> 
Clear Scene indeed is dependent for importing the models, as trying to import multiple models would broke due it makes callback to the armature data files, i tested out trying to import both Chronos and Durandral at the same scene, but Durandral broke by making the callback to Chronos' rest pose instead.

Ah thanks for mentionning the script name, I looked up the source code and managed to get the right normals. Also I think I managed to fix the second problem. So I highly recommand to redownload the script.

> Reply from RythusOmega ↑Sat Aug 06, 2022 3:26 pm at Sat Aug 06, 2022 3:26 pm
>
> 
nice to see it came out, despite years later as most people almost forget the existance and interest.

Yeah I was surprised that nobody made at least a fix of the shuffled parts considering the source code is well documented. Still didn't find anything about how bones work in this game ( like I didn't found any bone indices or weights ). Also like in the second pic, I don't know why, but some UV maps doesn't have the plane texture, only the decals. Edit : Nevermind, the plane had different UV Maps, one for the decal and one for the body.

Its mostly picked up my interest because of how the Ace Combat 7 modding community seems to have been more active right now, so now they can also have access to Macross models. Also cool mecha planes woohoo
## Post #39
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2022-08-07T01:43:58+00:00
- Post Title: Re: Help Macross 30 MLD

> Reply from GreenTrafficLight ↑Sun Aug 07, 2022 5:39 am at Sun Aug 07, 2022 5:39 am
>
> 
Ah thanks for mentionning the script name, I looked up the source code and managed to get the right normals. Also I think I managed to fix the second problem. So I highly recommand to redownload the script.

Glad to indeed help on the process, will be redownloading later to check out. and yes, i would mention that, aside of different UVs, they would make use of alpha channels. at least this is what i would say about the black parts of the wing section, and i got a notion on fixing it in few steps

> Reply from GreenTrafficLight ↑Sun Aug 07, 2022 5:39 am at Sun Aug 07, 2022 5:39 am
>
> 
Yeah I was surprised that nobody made at least a fix of the shuffled parts considering the source code is well documented. Still didn't find anything about how bones work in this game ( like I didn't found any bone indices or weights ). Also like in the second pic, I don't know why, but some UV maps doesn't have the plane texture, only the decals. Edit : Nevermind, the plane had different UV Maps, one for the decal and one for the body.

Its mostly picked up my interest because of how the Ace Combat 7 modding community seems to have been more active right now, so now they can also have access to Macross models. Also cool mecha planes woohoo

Indeed, is ironic to a extent, as yeah, i'm an AC7 modder since from the beginning(currently i'm more of a ex-modder, i may continue in service yet, but not in SNS interactions, as i deleted those to focus and give more attention to my IRL), and Macross 30 was one of my wishlist of models of interest at porting to the game. Chronos was one of the priorities as i did a skin mod based on it for the CFA-44 for ACAH before and people really liked, previously i would try out to reassemble from scratch due i found out Delta Scramble to a extent uses the Macross 30 models, but with few details and some differences because of the PSVITA hardware. but indeed, is something one of my modding pupil, and one of his friend will make good use of it, not such confident if i will develop something with from my part. as because of IRL, my workflow rymthm is totally different so is possible the more active people may apply the ideas first before i came with something, and there's nothing wrong either, due at least i'm glad AC7 modding got a lot of content creators, which from the ACAH modding times, aside of one user or another i was the one that went with the most pressure at delivering the content most people wanted

Still on the topic, not sure if it would be an inconvinience or not, but due you mentioned AC7 you indeed show interest for the franchise, you can notice it on my Xentax profile, but most of the activity and keypoints was made on Zenhax on the link below :

[https://zenhax.com/viewtopic.php?f=5&t=14942](https://zenhax.com/viewtopic.php?f=5&t=14942)

Part from my memory dump research and debugging efforts, along of reversing the model format was able into a script for AC6, ACAH and ACI begin developed, currently this script raised a huge interest due aside of the existing content from AC6 and ACAH, ACI got the most interessing assets of the format, including some fictional aircraft that two currently are in development into AC7 mods

The script works fine for most assets, but not all of them, examples begin the human character models, some map props(Stauros Warhead is one of them, and is avaiable on the thread), one or other weapon mesh broken(as i tested out), and other uses of the NUD model format that goes distinct from the one used for aircraft, weapons, and components similar to aircraft like the flying fortress from AC6

The only main issue, and by far begin one of the headaches of the moment, it can import the meshes fine, with one or other broken normals exception, but it will suffer from the same issue of the Macross 30 models on the old script, shuffled models. for some aircraft, manual assemble works to a extent, but for other stuff, including weapon bays and landing gears are the most problematic components by the degree of their shuffling. even with a workaround i explained on a mini guide, part of the effort is very tedious, summed up to "40" aircraft to assemble, is a bit too much at doing such task without taking out months to finish 1 to 2 models at best

The last posts of the thread by the user wood5568 shared some interessing information of the model format used, seeing this information was used on SmashForge(which got source code available), but the NUD format from Smash and other Namco games that got scripts developed, differs from the one used on the AC games, the basis is the same, just the data ordering is different from the analysis, which is why it wasn't a easy task at first sight

Seeing a source code of the format exists, and you used to improve your version of the Macross 30 script, if it wouldn't be asking too much, could be possible to at least translate the root pivots of the script to their original positions? is the current roadblock at the moment from my research, and one of the most plausible next step compared to the other ideas like reversing animation files or making a "SmashForge version that supports AC models and could be import, and exported". only this would be a gamechanger already, as aside of modding, the original models would help also for reference in skin modding, despite an revival for ACI is still distant, ACAH to a extent can make good use of it(despite unlisted at Steam)

Well, this is all for now from my offtopic comment, if indeed calls your attention, feel free to drop the contributions to the thread on Xentax for not deraling this thread more that i already did, once again, sorry for any inconvinience this post may generate after begin posted, as yeah, begging is indeed an annoying component from game research scenario. and learned that by following Xentax/Zenhax through the years and understanding better, but when a research is possible by information and knowledge available, and both share the same interest in common, it doesn't hurt on try to seek help
## Post #40
- Username: GreenTrafficLight
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Apr 26, 2021 6:54 am
- Post datetime: 2022-09-04T21:00:05+00:00
- Post Title: Re: Help Macross 30 MLD

> Reply from RythusOmega ↑Sun Aug 07, 2022 9:43 am at Sun Aug 07, 2022 9:43 am
>
> 
The only main issue, and by far begin one of the headaches of the moment, it can import the meshes fine, with one or other broken normals exception, but it will suffer from the same issue of the Macross 30 models on the old script, shuffled models. for some aircraft, manual assemble works to a extent, but for other stuff, including weapon bays and landing gears are the most problematic components by the degree of their shuffling. even with a workaround i explained on a mini guide, part of the effort is very tedious, summed up to "40" aircraft to assemble, is a bit too much at doing such task without taking out months to finish 1 to 2 models at best

Seeing a source code of the format exists, and you used to improve your version of the Macross 30 script, if it wouldn't be asking too much, could be possible to at least translate the root pivots of the script to their original positions? is the current roadblock at the moment from my research, and one of the most plausible next step compared to the other ideas like reversing animation files or making a "SmashForge version that supports AC models and could be import, and exported". only this would be a gamechanger already, as aside of modding, the original models would help also for reference in skin modding, despite an revival for ACI is still distant, ACAH to a extent can make good use of it(despite unlisted at Steam)

So I'm a least writing this so you don't get left in the dark. But I tried with the FHM of Ace Combat Assault Horizon ( Not ACI for the moment ) and I managed to find that MNT is the armature data and MOT2 probably the animations/shapekeys. But there a few problems

The problem is that the script might work only for the planes / helicopters since from what I've seen on the others FHM, there are more NDXR than MNT and I don't know how to organize that. Also helicopters have one less transformation than the amount of empty in the MNT data, I don't know how to fix that. There also a problem with normals with the Tornado gr4 ( but It doesn't seem that big of a problem from what I've seen ).

As for the animations, I never worked on animation reverse engineering so I don't know how its actually work. But from what I've seen, they're maybe compressed ( aka quantized ) because most of them are float.

I also didn't touch the materials data.

So I'm leaving the addon at this state ( not abandonning it, just less working on it for now, I will see what can I do with the models from ACI since they are not FHM ). I'm also thinking of writing a thread about this in the future, but I think it's not gonna get responses. BTW ignore the bones, they don't do anything.

[https://github.com/GreenTrafficLight/Ac ... nder-Addon](https://github.com/GreenTrafficLight/Ace-Combat-Blender-Addon)



> Reply from RythusOmega ↑Sun Aug 07, 2022 9:43 am at Sun Aug 07, 2022 9:43 am
>
> 
sorry for any inconvinience this post may generate after begin posted, as yeah, begging is indeed an annoying component from game research scenario. and learned that by following Xentax/Zenhax through the years and understanding better, but when a research is possible by information and knowledge available, and both share the same interest in common, it doesn't hurt on try to seek help

Nothing wrong with that since you brought useful information like Smash Forge.
## Post #41
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2022-09-06T20:25:53+00:00
- Post Title: Re: Help Macross 30 MLD

Wow, i'm speechless, and indeed very grateful

Seeing my last reply, by the silence at first i through it wouldn't go forward, which i won't deny that my constant "flow of dialogue" is something a few people get annonyed. i'm always looking to fix this with the time, but based on the experience i had on November of last year and few cases, having issues with mental health makes my grammar and structuring more poor, which postponed at taking seriously to going forward with my personal improvements

But yeah, time is a virtue, and is always good to begin patient for efforts made, which results would came in the future, and indeed it was what happend

About the script, will be testing out the FHM version for ACAH after writing this post, but seeing you mentioned about the "differences" from FHM and the ACI files, i can explain it right now most of those "differences", which aren't complex. glad to see MNT are important files indeed, MOT/MOP2 i also got a notion it would be indeed for animations, despite i didn't tested using the tools for modding ACAH to comfirm if they are or not, but anyway :

> -FHM are the container to store multiple files with different headers, the FHM is indeed important in ACAH due it contains some data hashes that would be required to make each model to work, which isn't easy to backport ACI models to the game because of that, below that it would start listing the row of NDXR models, until it reaches to the MNT and the other files, the end of the files will be always located by refering to the aircraft id(ex : p_f04e, which would refer to the player model of the F-4E)
>
> 
>
> -With ACI, the logic would work the same, but instead of NDXR, it would use NDP3 models instead, and it would lack the FHM data, due on my memory dump research, this data is shown different compared to the one that is used on the ACAH FHM, making it impossible to dump correctly, but from the NDXR rows first, then getting the MNT and the rest on a separate range and merging, the structure can be built similar
>
> 
>
> -Another difference would be Endianess if i'm correct, NDXR would focus on Little Endian because ACAH was released on PC and AC6 also uses it due Xbox 360 works on that structure, when the NDP3 models would use Big Endian instead because of the PS3
>
> 
>
> -Depending of the memory dump which can be build omitting some data, the order from the NDP3 models from ACI goes like this(when comparing, you can notice is similar to ACAH, except some aircraft will exclude some details(ex : R-101), and the memory dump can get some optional data on the same range) :
>
> *0x - illustrative number count
>
> 
>
> -01(the main mesh)
>
> -02(cockpit mesh)
>
> -03(the model of the aircraft used at the cockpit view)
>
> -04(nozzles, which was problematic with the old script)
>
> -*05(landing gear)
>
> -*06(aircraft shadow)
>
> -*07-08[...]11(dupes, *09 is the second set of the model used at cockpit view, but includes nozzles)
>
> -*12-15(special weapon main mesh, can be dumped optionaly)
>
> -*16-19[...](the four LOD levels of the special weapons, can be dumped optionaly)
>
> -*20(simple meshes that would be used to mask the emblems used by customization, can be dumped optionaly)

Hope those details can help out on understanding better the formats, about the few details like some broken normals, lack of materials and the animations, don't worry about, due by the huge progress you made already, is indeed what i wanted and is already enough. the other structures like o_f04e(CPU aircraft, different headers exist, and some can be animated) or d_f04e(Damage model), the weapons(unless some include animations like on AC7), mostly they are static models, so they lack bones due most of the components is handled by fewer meshes. about the other data which i would suppose the NDXR/NDP3 structure is different like some map props and character models, they aren't the main priority, however i would like the compatbility of some meshes to be included, which would be of the MPBM, which is the one of the SPW that broke on the old script(probably because of animation), the Stauros warhead(broken UVs) and the prop Su-33 model(not separated correctly), dumped from AC6, the later three begin NDXR, but unsure if they'll work with the current script

Will be linking a memory dump from the Su-33 for the research, not sure if one model would be enough to all begin compatible, but if issues begin reported, i will be looking on at least making the memory dump for all the aircraft of the game which was on my plans originally, but in general, i'm really glad to finally see my research going forward after one or two year of silence since last progress, when the ACI support went finished, i'll be quoting you on my Xentax thread, along posting on the Zenhax one, giving credits and updating the workflow and information

[https://www.dropbox.com/s/z3y1ygoi2e9kl ... ps.7z?dl=0](https://www.dropbox.com/s/z3y1ygoi2e9kl3h/ACI-AC6%20Memory%20Dumps.7z?dl=0)

Is the best suprise i could receive, seeing the beginning of this year wasn't one of the most happier periods of my life, things are better now on the mid-to-end period, but i'm still abstent from SNS for the moment, to give more attention to my IRL, at least, i still work with Ace Combat as a hobby when i got free time available
## Post #42
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2022-09-07T20:19:39+00:00
- Post Title: Re: Help Macross 30 MLD

(image embeds removed due to Imgur's recent ToS changes about inactive photos)

After the enthusiasm of yesterday, finally did the overall test-drive of the current version of the script, will be giving some of my feedback

In fact, the results are impressive, and indeed, you already understood most of the structure of the player aircraft, i made that table based from the information i had with the previous script, but the way you did,  things are more cleaner now, so based on the ACAH order, but with the correct names :




> -01 : _body
>
> -02 : _c1
>
> -03 : _c2
>
> -04 : BINE_BONE
>
> -*05 : _gear
>
> -*06 : _psel
>
> -*07-11(_sh dupes/BINE_BONE.002)
>
> **Optional data(like the ones from ACI dumps)
>
> **Exlcuded models depending of the file/dump(ex : a130 with only shbody and shgear)

To my suprise, i was already expecting the correct pivots using the armature data, but you also managed to include the "sockets" as empties(yeah, i know isn't like on AC7, probably on the three games they work in a different way, but the conception is the same, nametags are also equal, despite some aren't used in AC7), which is useful for modding as we can retrieve the original data of some stuff like gun, missile, afterburner pivots, etc...




As the tagline of the script mentions, it also works with the non-aircraft models, like the Helicopters, tested also with AC-130 Spooky(at the time i did those screenshots i forgot about B-1B and B-2A), and they work like a charm also, but as expected, the script at the moment only works with the player aircraft, trying to import the other data extracted with QDF Tool would result in nothing, and when loading the memory dumps, the tool will crash by having a notion, but the structure is still not supported 100%



Considering the ACI dump i sent, but few of AC6 focused on CPU units, along in general, we could consider AC6, ACAH and ACI as a native trilogy by both using the same assets and same engine(despite one was made in X360, and later backported to the PS3), took some of my time to make some additional dumps of AC6, focused on their correct structure. includes 4 player aircraft(AC6 in general includes most aircraft it debuted on ACAH and ACI), two weapons samples(Bomblet Dispenser, LASM, and ECMP pods from Tornado GR.4), and the P-1112 Aigaion, which is one of the few o_ models which includes armature information, the overview from what i analyzed :
[https://www.dropbox.com/s/rxkjn26jyh8jt ... ps.7z?dl=0](https://www.dropbox.com/s/rxkjn26jyh8jtjm/AC6%20Playable%20Memory%20Dumps.7z?dl=0)

> -Unlike the ACI memory dumps, AC6 memory dumps includes the FHM header information as the starting point on the same range
>
> 
>
> -Despite begin a FHM with NDXR assets, it got some considerable differences, like the id tag at the end begin located at the beginning of the first header
>
> 
>
> -MNT is also included on the range, however headerless, couldn't find by MNT, but when checking the structure of bone names, is technically the same
>
> 
>
> -the FHM structure can vary, as it can include few meshes, and some NTXR header leftovers, not all models will have those, but is still noticeable
>
> 
>
> -from data flow, it works the same, as the previous script could import the AC6 models without issues

In general, this script got a huge potential for sure, the only suggestions i would give is that aside of the current structure, an option to import the o_/d_ models, weapon models, and some of the problematic dumps like the Stauros Warhead, Su-33 prop and MPBM, this could be implemented as a function the script could look for standalone NDXR/NDP3 data on files/dumps, even if it lacks MNT data, the models would still be imported like how it works on mario's script, it's useful when you want to checkout some models compatible even without all the required data

example of the issues on the MPBM model using mariokart64n's script

And yeah, when the tool got the support to ACI and AC6, still it may suffer issues depending of the models, which can't be revised unless the dumps begin tested and reported, ACI will be a considerable progress by begin the most extensive(15 aircraft in AC6, vs "238" aircraft in ACI, due the dupes include some different model data), but in case i'll be supportive at doing this effort to the research, which i can later share the link with all of them from my resources repository hosted on Onedrive

Will be awaiting for the future changes, i know it won't be for now, as you mentioned isn't you priority at the moment, if interested, you could post your research on the Xentax thread i did about ACI, due aside of the information i gave from the Hex2obj, Mario was the one that posted the old script on it, along you already posted the Ridge Racer and Initial D on their respective threads also, well, i hope i didn't generate inconvinience for the Xentax staff or the Macross fans of "hijacking one thread for other topic"
