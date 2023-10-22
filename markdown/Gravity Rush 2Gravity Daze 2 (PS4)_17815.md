## Post #1
- Username: DillyDong
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 15, 2015 2:53 am
- Post datetime: 2018-03-13T23:22:01+00:00
- Post Title: Gravity Rush 2/Gravity Daze 2 (PS4)

Hey, I have gotten the game files and I'm trying to look up to extract their models.
The textures can be extracted and loaded up fine without problem through Noesis, since they are .gnf files
Here are examples:



The models (not 100% sure) seem to be in .gfx or .evd files. I could be wrong though, I'll post example files of them:
[http://www46.zippyshare.com/v/ko83yxAd/file.html](http://www46.zippyshare.com/v/ko83yxAd/file.html)

Thanks in advance.
## Post #2
- Username: Roflcopter
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 23, 2018 1:48 pm
- Post datetime: 2018-03-23T06:10:12+00:00
- Post Title: Gravity Rush 2/Gravity Daze 2 (PS4)

Hope this isn't too big of a necrobump, but the model files are in the gfx folder. I'm using Model Researcher to figure things out, and verts extract directly from the hex data.

The models are in ZYX format, but there's a good number of wild vertices coming up. I think the face and UV data is intermingled with the vertices.

az_tree_set_01.gfx looks like one of the plants in the Enchanted Zone:
[https://imgur.com/KXpHfSH](https://imgur.com/KXpHfSH)

and this is Kat in her Shifter 2.0 uniform:
[https://imgur.com/zisiIR7](https://imgur.com/zisiIR7)

They both seem to have a flat version of the main model, probably for shadows.

Finding the verts was easy enough, but it might be interesting figuring out how to get the faces and UV's working.

And thanks for the insight on the textures. I was hoping it was something someone's seen before.
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-23T11:31:22+00:00
- Post Title: Gravity Rush 2/Gravity Daze 2 (PS4)

The data you are reading is collection of vertex blocks. I am not familiar with Model Researcher, but you probably need to use the padding option. I will give you an example with hex2obj.

Here is the first mesh (kit01_base.gfx):



Vertex blocks are 32 bytes each. Like you said they are easy to see in the hex editor. 

For the first submesh after the end of the vertex blocks there are some 0s and then the face indices start. For another mesh I have seen that it starts right after the blocks end, with no 0s between. Still it seems to be right under the vertices. Shouldn't be hard to find.

UVs should probably be somewhere inside the vertex block, but I haven't checked that.
## Post #4
- Username: Roflcopter
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 23, 2018 1:48 pm
- Post datetime: 2018-03-24T00:41:33+00:00
- Post Title: Gravity Rush 2/Gravity Daze 2 (PS4)

Ok, sweet! That got me a lot further. Indeed, a padding of 20 gives me the verts I want, and I'm able to get faces, too. But I'm getting a bunch more faces than I want on ModelResearcher, and they're inverted. I'm using shorts, which seems to be the right size, but so far I'm thinking I need to cut down the count to get rid of the junk.

EDIT:
Got a smooth looking mesh with a count of 4509. Hard to notice the shift in numbers.


(hopefully the faces correct themselves as I continue.)
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-24T02:32:40+00:00
- Post Title: Gravity Rush 2/Gravity Daze 2 (PS4)

> Reply from Roflcopter
>
> 
Got a smooth looking mesh with a count of 4509. Hard to notice the shift in numbers.
Yes, hex2obj requires index count, while Mesh Researcher seems to require face count. Just do (index count/3) and you have the face count. 13524/3 = 4508

Also I looked at the files of Gravity Rush (first game) and they don't look very complex. I was able to get the skeleton and the weights too. 



It just has some slight problems with the weights. I will think of making a tool for exporting Gravity Rush models in the future. Maybe also for the second game, there seems to be just a couple of differences regarding the model data.
## Post #6
- Username: Roflcopter
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 23, 2018 1:48 pm
- Post datetime: 2018-03-24T11:15:35+00:00
- Post Title: Gravity Rush 2/Gravity Daze 2 (PS4)

Awesome. I don't have the first game's files yet, so I can't see the differences. Do you have some hex examples? 

> I will think of making a tool for exporting Gravity Rush models in the future. Maybe also for the second game, there seems to be just a couple of differences regarding the model data.
I'd be looking forward to that. It definitely beats getting one mesh at a time.

EDIT: Shifter 2.0 progress. Even got the faces worked out (had to flip the Z-axis, haha)! Speaking of faces, she has a whopping 40 expressions. I guess instead of rigging her face, they decided to make a new mesh for each of her expressions.

Now it's on to the UV's. They've been a pain to figure out so far, but I'm sure I'll get it pretty soon. Aside from the vertex and face data, there are two more alternating patterns near the end of the file. I haven't had any luck finding UV's alongside the vertex data, so maybe it's somewhere in there. Or I'm just not reading the vertex data correctly.
## Post #7
- Username: Roflcopter
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 23, 2018 1:48 pm
- Post datetime: 2018-03-29T00:35:33+00:00
- Post Title: Gravity Rush 2/Gravity Daze 2 (PS4)

Ok, so I found the UV's but...

I guess multiplying the V coordinate by 2 should do the trick. I'd love to know why it's like this, though. akderebur, have you been getting UV's like this?

As for the textures, the purist in me wants to know if there's a layered format we can export to, but I guess I'll just export to bmp. It's lossless and I haven't had trouble with it so far.
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-29T06:58:29+00:00
- Post Title: Gravity Rush 2/Gravity Daze 2 (PS4)

> Reply from Roflcopter
>
> akderebur, have you been getting UV's like this?
Edit:
I remembered that I actually didn't get the uvs for gr2, I got them for gr1. They were in the vertex block as half floats if I remember correctly. Also some of them were outside the 0.0 - 1.0 range but it is not a problem.

Looking at your image I see that it is a different result than what I have in gr1. I will take a look at the files when I have the time.
## Post #9
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2018-04-01T13:00:03+00:00
- Post Title: Gravity Rush 2/Gravity Daze 2 (PS4)

When texture coordinates are stored in Short, they need to be divided by a number in order to translate these coordinates into floating-point numbers. In the Model Researcher, this number is 0xffff. In this case, the calculated values are converted to texture sizes. To avoid this, you can use the script. I see from the screenshots that a Pro version. Change the value of dp to correctly apply the coordinates to the texture.
The texture can be loaded in the UVs tab so that it is also displayed when the script is run.
## Post #10
- Username: Roflcopter
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 23, 2018 1:48 pm
- Post datetime: 2018-04-02T01:02:55+00:00
- Post Title: Gravity Rush 2/Gravity Daze 2 (PS4)

Ah, ok! So the magic number for dp was of course 1024. And the script works nicely with the other textures.

Thanks for the help, you guys! That just leaves the skeleton/armature, as far as I can tell. But I can make an obj of Shifter 2.0 now.
## Post #11
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-02T08:01:20+00:00
- Post Title: Gravity Rush 2/Gravity Daze 2 (PS4)

> Reply from Roflcopter
>
> That just leaves the skeleton/armature, as far as I can tell.
I was able to get the skeleton in gr1 but couldn't find anything that looks like a mesh bone table. The bone ids in weights doesn't seem to be global, so there should be a data that tells which bones are used by a specific mesh. I will post a simple sample here, in case anyone wants to take a look: 

 dus01_base.rar
(22.93 KiB) Downloaded 25 times


This is the reason I haven't released my program actually. It can read the meshes fine, the skeleton and the weights too but that doesn't mean much if the bone indices are wrong.

Btw are there any other files that might be related to skeleton in gr2? I have checked "kit01_base.evd", it has some text that looks like bone names, but other data doesn't look very useful. I am wondering if there are other files with the extension ".skel", like in gr1.
## Post #12
- Username: Roflcopter
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 23, 2018 1:48 pm
- Post datetime: 2018-04-02T18:08:45+00:00
- Post Title: Gravity Rush 2/Gravity Daze 2 (PS4)

Yeah, in the eaf folder, I found a bunch of .mot files that look like actions, just judging from their names.

There are more evd files in the lua->chardefs->player folder. I see kit01.evd there.
## Post #13
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-02T19:55:02+00:00
- Post Title: Gravity Rush 2/Gravity Daze 2 (PS4)

> Reply from Roflcopter
>
> 
There are more evd files in the lua->chardefs->player folder. I see kit01.evd there.
If they are inside the lua folder they are probably not what we are looking for.

If you find anything with the extension ".skel" or any other file that you think might be related to skeleton data, please post it here. I don't have the gr2 files.
## Post #14
- Username: Roflcopter
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 23, 2018 1:48 pm
- Post datetime: 2018-04-02T21:11:03+00:00
- Post Title: Gravity Rush 2/Gravity Daze 2 (PS4)

Here are kat's .mot files; still haven't had a good chance to look at these myself. Thus far, all of the .evd files I've found were in the lua folder. And there don't seem to be any .skel files at all.

[http://www108.zippyshare.com/v/La3ptWpV/file.html](http://www108.zippyshare.com/v/La3ptWpV/file.html)

edit: after a quick glance, I'm seeing what look like vertex blocks in the files I sent.
## Post #15
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-02T21:41:33+00:00
- Post Title: Gravity Rush 2/Gravity Daze 2 (PS4)

It looks like they packed the animation and skeleton data into a single file. Still it is the right file. I can see some quaternions and float values together, they are probably bone transformations. I will look into it later.
## Post #16
- Username: Roflcopter
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 23, 2018 1:48 pm
- Post datetime: 2018-08-19T04:42:17+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

Pretty big update. I haven't been able to get anywhere significant with the animation data so far, so I decided to change pace and perfect the mesh scripts. I looked into the files a bit more, found some vertex and face counts, and once I finally understood how to read little endian (it's a miracle I got as far as I did before that), it was obvious that there was a pointer to the first vertex VERY early in the file. 

So armed with that info, I improved the Model Researcher script. I tried to test it thoroughly this time, so I'm fairly confident it'll work on nearly every model in the game. I'm only concerned that my uv maps don't always adapt to the numerous vertex sizes like they should, but I'll fix that soon enough. Anyway, here's the script; I threw in a .hbk bookmark file for anyone interested in my research (use it with kit01_base.gfx in Hex Workshop):

[https://www4.zippyshare.com/v/a3yFzcWL/file.html](https://www4.zippyshare.com/v/a3yFzcWL/file.html)

So with that said, now it's back to the animation data. I'm assuming the armature/skeleton doesn't change between files; it seems like it should be defined the same way every time. Aside from that, I only know I'm looking for floats that hopefully have some sense of order. 3 locations, rotations, and scales per bone, right?
The most likely locations:
-the .mot files, pretty early. There's a decent-sized section that I haven't been able to read that only changes if I'm looking at another character.
-the .skel section of the .mot files. This more likely handles the movement of the bones. Should be handy.
-There's a section after the mesh data in .gfx files, but I've only seen it on models that are definitely rigged. It could be unrelated to animation, but I don't think so.

I haven't been able to understand any of the above, but I was reading the files backwards until recently, so maybe I'll have better luck this time!
## Post #17
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2018-08-19T06:49:11+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

I think it's better to write scripts for Noesis, because not everyone has a Pro version. In addition, after adding animation support, the API functions may change slightly.
## Post #18
- Username: Roflcopter
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 23, 2018 1:48 pm
- Post datetime: 2018-08-19T17:02:56+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

Yeah, that makes a lot of sense... I'll knock that out real quick. It should be a good head start for the next few things I plan to do.
## Post #19
- Username: Roflcopter
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 23, 2018 1:48 pm
- Post datetime: 2018-08-27T16:21:17+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

Hey, guys. Made some progress getting the script to work with Noesis; I've managed to get all the meshes to show up in preview, but it looks like I can only export the first mesh. Does anybody know how I can fix this? Also, I tried using the rapi approach, but I kept getting crashes.

[https://www4.zippyshare.com/v/pYaj3NHb/file.html](https://www4.zippyshare.com/v/pYaj3NHb/file.html)
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-27T17:35:53+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

well, I don't understand the code very good, but it's simple:
a) introduce
meshes = []
before
while fileComplete == False:

b) comment out: #mdlList.append(NoeModel([msh], [], []))
use this:
meshes.append(msh)

c) at the end:
	mdl = NoeModel(meshes)
	mdlList.append(mdl)

	return 1

results in three Lods for me:



kit01_gs00_base-gfx.jpg (116.52 KiB) Viewed 393 times


remaining problem: uvs for highest lod are not flat, funny; no time to care for
## Post #21
- Username: Roflcopter
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 23, 2018 1:48 pm
- Post datetime: 2018-08-28T01:39:40+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

Thanks! I took a quick look into the UV issue, and I think the model you looked at was some sort of test model. It's looking for textures that aren't in the game, and it's not named like Kat's other models. Still strange to think they didn't unwrap the highest lod, but it seems to be the problem. 

On that note, I've learned more about the materials, but not enough to properly add them to the script. The most interesting thing is that some textures are mapped to very specific parts of the mesh (like the irises, those are animated). I don't have the slightest clue how I'll deal with that, even if I do it manually. But for now, it's on my list to just figure out how the materials are assigned. Of course, with the UV's exported, textures can be added manually. 

[https://www4.zippyshare.com/v/iUja1v0W/file.html](https://www4.zippyshare.com/v/iUja1v0W/file.html)
## Post #22
- Username: tttentadra
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 09, 2018 4:37 am
- Post datetime: 2018-10-08T21:28:18+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

Hi, I don't mean to intrude or anything but does anyone have the .gnf textures for Kat?

edit: Sorry, I was looking at the wrong place, I found them after I wrote the this message
## Post #23
- Username: Roflcopter
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Mar 23, 2018 1:48 pm
- Post datetime: 2018-11-02T01:39:29+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

Maybe this is a silly question, but could someone explain NoeBone's matrix parameter to me? I know I need a 4x3 matrix, but what's supposed to be in the matrix?
## Post #24
- Username: Roflcopter
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-11-02T01:54:57+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

the bone transform goes in there
the default matrix is
identityMat43Tuple = ( NoeVec3((1.0, 0.0, 0.0)), NoeVec3((0.0, 1.0, 0.0)), NoeVec3((0.0, 0.0, 1.0)), NoeVec3((0.0, 0.0, 0.0)) )
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-02T10:16:49+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

> Reply from Roflcopter
>
> I know I need a 4x3 matrix, but what's supposed to be in the matrix?from what chrrox wrote I assume, it's 3x3 for rotation and the last vector is position.
## Post #26
- Username: Incar1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 21, 2019 5:00 am
- Post datetime: 2019-07-20T21:04:21+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

So I realize that this thread is probably totally dead, but I was wondering if this ever got the the point that it was usable in VR chat? I know basically nothing about this kind of thing.
## Post #27
- Username: 203Null
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 04, 2019 5:24 am
- Post datetime: 2019-10-29T23:22:25+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

> Reply from Incar1 ↑Sun Jul 21, 2019 5:04 am at Sun Jul 21, 2019 5:04 am
>
> 
So I realize that this thread is probably totally dead, but I was wondering if this ever got the the point that it was usable in VR chat? I know basically nothing about this kind of thing.

I made one few months ago, [https://www.youtube.com/watch?v=uZpm2Np794U](https://www.youtube.com/watch?v=uZpm2Np794U). I didn't released it because it's still kind broken. Add me on discord NuLL#2372 if you wanna take it or help me work on it.
## Post #28
- Username: greenteasan1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 24, 2020 10:44 am
- Post datetime: 2020-01-24T02:52:26+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

Wait how did you manage to open gfx file in noesis? Everytime try to open the file in noesis it keeps saying "this file cannot be previewed"(this is the same for evd files) and I'm confused how do I open it in noesis? Can anyone help me with this problem? (Sorry I know I'm kinda late.)
## Post #29
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-02-21T15:51:19+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

Help I need the body textures for cecie  just  the   body textures.
## Post #30
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2021-03-28T15:19:42+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

hello  there one more model I  forgot to look at  from CrazyPotato  he has the tex  but not the model for  kit02 base.  can you send  me the model and thank you for hearing my request.
## Post #31
- Username: 203Null
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 04, 2019 5:24 am
- Post datetime: 2021-05-02T01:05:19+00:00
- Post Title: Re: Gravity Rush 2/Gravity Daze 2 (PS4)

Been a while since this thread has been updated but here's the latest update from Team Alua: [https://docs.google.com/document/d/1HIQ ... sp=sharing](https://docs.google.com/document/d/1HIQKqhsCgCAxNzrJjVF32g1C38k9lZ7KpdSam5FPfaE/edit?usp=sharing)

Team Alua is a research group of Gravity Rush. You can join our discord to follow up or help us: [https://discord.gg/P8pY2fv](https://discord.gg/P8pY2fv)
We are working on recreating/porting Gravity Rush 2 so we are gonna need a lot of help, any help is apperated.
