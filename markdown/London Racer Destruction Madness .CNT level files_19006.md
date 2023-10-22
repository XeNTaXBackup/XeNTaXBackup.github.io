## Post #1
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-11-02T16:51:00+00:00
- Post Title: London Racer: Destruction Madness *.CNT level files

Hi all, i asked already about cnt files from that game in that thread: [viewtopic.php?f=16&t=17119](http://forum.xentax.com/viewtopic.php?f=16&t=17119). 
And i figured that game is using similar to carmageddon mobile game engine (stainless engine) and even noesis have support for most of files from here. Noesis can open vehicle cnt files fine but problem is with level files,it can open them but models placed a bit wrong or have wrong scale.
Im not really sure how to fix it and cant find script file in noesis,it build in program itself i suppose,i hope somebody could help me with it.

Map look like this in noesis:

Closer look at some parts:
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-02T21:31:16+00:00
- Post Title: London Racer: Destruction Madness *.CNT level files

which format did you choose from Noesis' format list?
(Without a .cnt level file it's impossible to help you.
If it's an internal format, it's not possible, too, imho.)
## Post #3
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-11-02T21:43:19+00:00
- Post Title: London Racer: Destruction Madness *.CNT level files

> Reply from shakotay2
>
> which format did you choose from Noesis' format list?
(Without a .cnt level file it's impossible to help you.
If it's an internal format, it's not possible, too, imho.)
Oh,sorry i forgot about examples,my bad  
Here is that level from pic [https://mega.nz/#!QhMxlIpR!dU8Bt6T2Yifg ... vbV1R4cyDs](https://mega.nz/#!QhMxlIpR!dU8Bt6T2YifgSfpRNbE-th4rgbyPfsIT6vbV1R4cyDs) you need to load LEVEL.CNT file and it will catch all mdl models.
And its stainless cnt in noesis,i saw post about adding support for that in noesis but cant find it now.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-02T22:57:39+00:00
- Post Title: London Racer: Destruction Madness *.CNT level files

here you go: [viewtopic.php?f=33&t=4582&p=81288&hilit ... ess#p81288](http://forum.xentax.com/viewtopic.php?f=33&t=4582&p=81288&hilit=stainless#p81288)
But I can't find a plugin handling .cnt files.

As you can see from the thread you've linked in your opening post about the classiccoupe the offsets of submeshes are to be found in the cnt file.
Not sure if it works for levels but for the bonnet of the car it did.
## Post #5
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-11-02T23:06:37+00:00
- Post Title: London Racer: Destruction Madness *.CNT level files

> Reply from shakotay2
>
> here you go: viewtopic.php?f=33&t=4582&p=81288&hilit ... ess#p81288
But I can't find a plugin handling .cnt files.

As you can see from the thread you've linked in your opening post about the classiccoupe the offsets of submeshes are to be found in the cnt file.
Not sure if it works for levels but for the bonnet of the car it did.
That noesis plugin is already in program by default you dont need to install it and it can open vehicles cnt files fine. Its only a problem with levels. Maybe model scale itself wrong,idk.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-02T23:41:11+00:00
- Post Title: London Racer: Destruction Madness *.CNT level files

> Reply from dropoff
>
> That noesis plugin is already in program by default you dont need to install ityes, I know.  

What I wanted to say is that I didn't find a plugin source (to patch it concerning the offsets).

Anyways, <you> can try to fix the offsets manually for a handful of submeshes to see whether it works.
For example "cs euro office top 14  01" and the "bot".
(If so I could create code for it.)

Here's the offset of the "cs euro office bot 14b 01" at 0x33b69in the level.cnt:
C678B2C3 E926B13D A1B28744 (You can convert it to floats using hex2obj, see the "car thread".)



cnt-offsets.png (87.5 KiB) Viewed 81 times


Both parts (top/bot) have the same offsets which makes sense.

(I've included the car for comparison only!)
## Post #7
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-11-03T00:04:32+00:00
- Post Title: London Racer: Destruction Madness *.CNT level files

> Reply from shakotay2
>
> dropoff wrote:That noesis plugin is already in program by default you dont need to install ityes, I know.  

What I wanted to say is that I didn't find a plugin source (to patch it concerning the offsets).

Anyways, <you> can try to fix the offsets manually for a handful of submeshes to see whether it works.
For example "cs euro office top 14  01" and the "bot".
(If so I could create code for it.)

Here's the offset of the "cs euro office bot 14b 01" at 0x33b69in the level.cnt:
C678B2C3 E926B13D A1B28744 (You can convert it to floats using hex2obj, see the "car thread".)
cnt-offsets.png
Both parts (top/bot) have the same offsets which makes sense.

(I've included the car for comparison only!) 
I found program that can load that format aswell and with same result. Here: [https://github.com/MaxxWyndham/Flummery](https://github.com/MaxxWyndham/Flummery) I compared coords that it gives me with ones from file and they are pretty close
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-03T13:44:27+00:00
- Post Title: London Racer: Destruction Madness *.CNT level files

> Reply from dropoff
>
> I found program that can load that format aswell and with same result.What does that mean? The Flummery loads the Level.cnt, applies the offsets and the meshes are misplaced, though?

btw: did you manage to compile the Flummery project? (I'm using Net 4.5, updating to Net 4.6 always broke some C# projects, so I restored 4.5; didn't get LibSquishNet working under Net 4.5)

Another problem:
"The referenced project '..\Flummery.Plugin\Flummery.Plugin.csproj' does not exist."
## Post #9
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-11-03T14:05:38+00:00
- Post Title: London Racer: Destruction Madness *.CNT level files

> Reply from shakotay2
>
> dropoff wrote:I found program that can load that format aswell and with same result.What does that mean? The Flummery loads the Level.cnt, applies the offsets and the meshes are misplaced, though?

btw: did you manage to compile the Flummery project? (I'm using Net 4.5, updating to Net 4.6 always broke some C# projects, so I restored 4.5; didn't get LibSquishNet working under Net 4.5)

Another problem:
"The referenced project '..\Flummery.Plugin\Flummery.Plugin.csproj' does not exist."
I mean it can load it with same problem as noesis,models misplaced in same way. I was able to compile it with vs2017 with net 4.6 or newer(i dont remember which version flummery require). There is also compiled versions on github page available. Also in last source version fbx export option is broken for some reason so i cant get anything out of it,and it cant load boundary.mdl because it have null texture,but you can just replace it with different model to load level. I think its actually wrong scale,because if you load map,you can see that boundary model is much smaller than level.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-03T14:43:34+00:00
- Post Title: London Racer: Destruction Madness *.CNT level files

> Reply from dropoff
>
> I mean it can load it with same problem as noesis,models misplaced in same way.That's strange, since from your "details window" in your post as of 1:04 am the position of the submesh (sm) is identical to the offset given in Level.cnt. Are you sure that sm is displaced? (Maybe it's only caused by wrong scaling?)

Refer to the bonnet of the car, I mentioned. Applying the offset from the carbody.cnt to the bonnet of the classiccoupe made it "move"  to the right place, iirc.

Can you tell me where to find Flummery.Plugin.csproj? Couldn't find it in Flummery-master.zip  from Github.
## Post #11
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-11-03T15:56:29+00:00
- Post Title: London Racer: Destruction Madness *.CNT level files

> Reply from shakotay2
>
> dropoff wrote:I mean it can load it with same problem as noesis,models misplaced in same way.That's strange, since from your "details window" in your post as of 1:04 am the position of the submesh (sm) is identical to the offset given in Level.cnt. Are you sure that sm is displaced? (Maybe it's only caused by wrong scaling?)

Refer to the bonnet of the car, I mentioned. Applying the offset from the carbody.cnt to the bonnet of the classiccoupe made it "move"  to the right place, iirc.

Can you tell me where to find Flummery.Plugin.csproj? Couldn't find it in Flummery-master.zip  from Github.
I mean like they are on correct coordinates but they look like misplaced and yeah it could be caused by wrong scale i think,i will try to do something with scales. And everything work like it should with cars. Also its weird,i had no problems with Flummery.Plugin.csproj file,i will check for it when i will be on my pc.
## Post #12
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-11-03T17:49:25+00:00
- Post Title: London Racer: Destruction Madness *.CNT level files

Hmm,i dont have such file. I pm'ed you link to source i have shakotay.
## Post #13
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-11-03T19:09:51+00:00
- Post Title: London Racer: Destruction Madness *.CNT level files

So,it looks better with 4x scale for each model,but now here is another problem. Just scale doesnt work too good for some models like buildings etc.
## Post #14
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-02-17T11:24:11+00:00
- Post Title: London Racer: Destruction Madness *.CNT level files

Well, seems like its harder to fix than i thought. Not sure if i can do that without noesis plugin source and i even still not sure how.  

P.S. Well yeah plugin is part of noesis_misc.dll which source is unavailable.
