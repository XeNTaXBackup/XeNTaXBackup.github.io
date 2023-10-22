## Post #1
- Username: Genuline
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 22, 2020 5:21 pm
- Post datetime: 2020-03-22T10:26:45+00:00
- Post Title: Outbreak Room Exports

Hello, this is my first time posting here, so please forgive me if I mess up anywhere or don't get engaged enough.

I'm familiar with the Source engine and I've been interested in RE Outbreak for a while, so much so that I've been porting a bunch of the models to the GMod Workshop, whether for use in posing, creating screenshots or whatever else people wanna do with them, some examples below:
[https://steamcommunity.com/sharedfiles/ ... 1997074683](https://steamcommunity.com/sharedfiles/filedetails/?id=1997074683)
[https://steamcommunity.com/sharedfiles/ ... 2014297977](https://steamcommunity.com/sharedfiles/filedetails/?id=2014297977)
[https://steamcommunity.com/sharedfiles/ ... 2025039352](https://steamcommunity.com/sharedfiles/filedetails/?id=2025039352)

Once I finish porting the character and enemy models, I will get started on re-creating the scenarios as well, using as much content from Outbreak as possible to make it as accurate as possible. However, I've run into a couple of issues with exporting rooms and some other models which is preventing me from going forward with my ports / re-creations.
1. When I try to convert some models (From .NBD to .obj) either room or character models, they simply don't work (IE I can't edit or view them in any 3D modelling software) a couple of examples of models which I've tried to convert but don't work are (From File #2 disk):
- From romdata.afs, N15.nbd and N14.nbd (the hive scenario, supposedly being the High Poly Leech Men models)
- From r040.afs, r0401900 (wild things scenario, Path in front of the Observation Deck map)
2. When I do manage to export rooms, all of the models are automatically sent to the world origin point in whichever 3D modelling software I use, see image below:
[https://steamcommunity.com/sharedfiles/ ... 2031003032](https://steamcommunity.com/sharedfiles/filedetails/?id=2031003032)

In Outbreak, there is a variety of files which control particular aspects of a room, such as:
r0401900.NBD - The collection of models / meshes which the player can see in a room
e0401900.bin - Enemy placements in a room
w0401900.bin - Weapon placements in a room
R0401900.FOG - Fog controller
R0401900.LIG - Lighting controller
gr0401900.bin - Not sure about function
rr0401900.rdt - Not sure about function

One of these or even a few of these are responsible for the coordination of models in a room, which I'm currently trying to figure out. And even if I do find the correct file which relates to the coordination of models, I'm not sure how to get anything of substance from it. I currently use these tools below, so if I'm missing out on any, please let me know:
- AFSExplorer
- Noesis
- NBDTools

I was hesitant on creating this thread, but I've already exhausted all my options when researching into this. I've come here from the OBSRV Forums, since most of the modders aren't as active as they once were, so I was limited on help there. And as well as that, I've reached out to everyone I could and ultimately found myself here, even finding a thread asking the same question, but that thread is much more outdated it seems:
[viewtopic.php?t=9923](https://forum.xentax.com/viewtopic.php?t=9923)

Any and all direction is appreciated, thank you.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-22T11:07:20+00:00
- Post Title: Outbreak Room Exports

> Reply from Genuline ↑Sun Mar 22, 2020 6:26 pm at Sun Mar 22, 2020 6:26 pm
>
> 
In Outbreak, there is a variety of files which control particular aspects of a room, such as:
r0401900.NBD - The collection of models / meshes which the player can see in a room
[...]
One of these or even a few of these are responsible for the coordination of models in a room, which I'm currently trying to figure out. And even if I do find the correct file which relates to the coordination of models, I'm not sure how to get anything of substance from it.My solution is here:

> Reply from shakotay2 ↑Fri Jul 13, 2018 10:52 pm at Fri Jul 13, 2018 10:52 pm
>
> 
A little bit complicated, but worked, afair. Feel free to improve it.

(Don't miss to read my post as of Sun Jan 20, 2019 7:57 pm there.)
## Post #3
- Username: Genuline
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 22, 2020 5:21 pm
- Post datetime: 2020-03-23T03:27:12+00:00
- Post Title: Outbreak Room Exports

> Reply from shakotay2 ↑Sun Mar 22, 2020 7:07 pm at Sun Mar 22, 2020 7:07 pm
>
> 
My solution is here:
shakotay2 wrote: ↑Fri Jul 13, 2018 10:52 pm
A little bit complicated, but worked, afair. Feel free to improve it.

(Don't miss to read my post as of Sun Jan 20, 2019 7:57 pm there.)

Thanks for the info, I get the big picture but my primate brain is having difficulties understanding the process and a link is broken:
[https://ps23dformat.wikispaces.com/file ... o3dsUV.bms](https://ps23dformat.wikispaces.com/file/view/ResidentEvilOutbreak2AMOto3dsUV.bms)

With everything else however, I assume you complete the process with Noesis / NBDTools and QuickBMS open? Since it wasn't directly stated in most of the posts I've looked through (Or I most likely glossed over it)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-23T09:22:51+00:00
- Post Title: Outbreak Room Exports

> Reply from Genuline ↑Mon Mar 23, 2020 11:27 am at Mon Mar 23, 2020 11:27 am
>
> Thanks for the info, I get the big picture but my primate brain is having difficulties understanding the processI have a primate brain, too (we all have, as Charles Darwin said  ) but you'll need some "iron will" to succeed in the process.

> and a link is broken:
>
> https://ps23dformat.wikispaces.com/file ... o3dsUV.bms

Yes, but look carefully, the bms script code is here:

> Reply from FurryFan ↑Fri Jan 04, 2013 3:45 am at Fri Jan 04, 2013 3:45 am
>
> 

> Reply from Genuline ↑Mon Mar 23, 2020 11:27 am at Mon Mar 23, 2020 11:27 am
>
> With everything else however, I assume you complete the process with Noesis / NBDTools and QuickBMS open? Since it wasn't directly stated in most of the posts I've looked through (Or I most likely glossed over it)I only had one or two room samples (r0150100 for example) but from here it looks ok, doesn't it?

> Reply from shakotay2 ↑Fri Jul 13, 2018 10:52 pm at Fri Jul 13, 2018 10:52 pm
>
>
## Post #5
- Username: Genuline
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 22, 2020 5:21 pm
- Post datetime: 2020-03-24T13:17:38+00:00
- Post Title: Outbreak Room Exports

> Reply from shakotay2 ↑Mon Mar 23, 2020 5:22 pm at Mon Mar 23, 2020 5:22 pm
>
> 
I have a primate brain, too (we all have, as Charles Darwin said  ) but you'll need some "iron will" to succeed in the process.
[https://steamcommunity.com/sharedfiles/ ... 2033682297](https://steamcommunity.com/sharedfiles/filedetails/?id=2033682297)
Managed to get it working, thank you. I've got all the meshes separate which is good for convenience sake, but when I load them into Blender 2.79 ( Since .3ds isn't compatible with 2.8 ) they meet at 0,0,0 still. Did the corrected coordinates and rotation values go somewhere else or did I forget to do something? After this I really want to make this process easier.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-24T15:57:02+00:00
- Post Title: Outbreak Room Exports

> Reply from Genuline ↑Tue Mar 24, 2020 9:17 pm at Tue Mar 24, 2020 9:17 pm
>
> I've got all the meshes separate which is good for convenience sake, but when I load them into Blender 2.79 ( Since .3ds isn't compatible with 2.8 ) they meet at 0,0,0 still.Did you use the script move_0150100.py?
(It has to be "filled" with coordinates before. And they will be different for r0401600, btw. I'd recommend to perform the whole process as described, using room r0150100, maybe even using/installing blender 2.49b for the first go. Otherwise there's a high risk of failing.)
## Post #7
- Username: Genuline
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 22, 2020 5:21 pm
- Post datetime: 2020-03-25T06:42:51+00:00
- Post Title: Outbreak Room Exports

> Reply from shakotay2 ↑Tue Mar 24, 2020 11:57 pm at Tue Mar 24, 2020 11:57 pm
>
> 
Did you use the script move_0150100.py?

Nope, and that's probably where I messed up so I'll take a step back for now and trial run on r0150100 first. I've gotten everything right so far I hope, just that my Blender version isn't old enough and for some reason their website isn't letting me access the downloads. I got confused on the .smd and chg_bin part, since I didn't think you were meant to use Valve .smd as an export for the .ahi file. Making this post as a means of telling you that I haven't given up yet, instead I'll most likely come back with results or with another question
