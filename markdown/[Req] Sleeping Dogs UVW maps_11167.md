## Post #1
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-01-28T09:19:03+00:00
- Post Title: [Req] Sleeping Dogs UVW maps

Hello, yes it's me again. I am aware that this game is pretty much done and dusted. Nearly everything is extractable except for animations. (but that's a [seperate thread](http://forum.xentax.com/viewtopic.php?f=21&t=11155))

Now, while the people who were working on this game were incredibly diligent in their efforts, they left one thing incomplete: the UV maps for meshes. 

Currently only characters have proper UVs, everything else is either borked or has no UVs at all. For example, [the vehicle UVs are the ones they use for damage mapping, not their actual texture.](http://puu.sh/6B9AD.png)
With the exception of characters, the broken vehicles, and a few weapons, everything else has absolutely no UVs. The actual meshes turn out just fine, but all UV coordinates are zero/nonexistent.

I realize it's a very slim chance, but is there anyone who could fix this?

Here's [several sample files](http://www.mediafire.com/download/p038uofa0cewuno/SDFileSamples.zip) of each type: Vehicle, Tire, Weapon, Prop, and Building. 

And here are all the already existing tools:
[Ekey's .BIG Unpacker](http://www.sendspace.com/file/vtisdf) (for any extra samples)
[Shakotay's Extractor](http://forum.xentax.com/viewtopic.php?f=16&t=10779) (mesh only)
[Howfie's .DDS Extractor](http://www.mediafire.com/download/3g22ki9qmjln0mi/SDTextureExtractor.zip) (textures only)
[Marisuz's Blender Importer](http://www.mediafire.com/download/jso6dhck1a8w1lu/SDBlenderScript.zip) (mesh, rigging, textures, UVs, materials)
## Post #2
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-29T06:33:21+00:00
- Post Title: [Req] Sleeping Dogs UVW maps

Both tools are compiled, so they cannot be edited by others.
You should speak with the people who created them, it's likely that cars simply need a second UV channel, which should be a very simple matter.
## Post #3
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-01-29T09:46:21+00:00
- Post Title: [Req] Sleeping Dogs UVW maps

Ekey, Howfie and Marisuz all got bored and quit a long time ago.

I already spoke to Shakotay, he wasn't able to figure it out. But you're right, maybe he'll be willing to share his source code.

And the blender importer is just a script, here's a [direct link](http://pastebin.com/ntz4cRFQ) for convenience.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-29T13:23:24+00:00
- Post Title: [Req] Sleeping Dogs UVW maps

> Reply from SergeantJoe
>
> But you're right, maybe he'll be willing to share his source code.That's not a problem of the source code. If I remember exactly it extracts most of the UVs. For the ones it does not it's a problem of where the uv data is stored in the model data and how it is structured.
Since this is not solved in the source code it wouldn't help you either.

> Reply from Chipicao
>
> [...]it's likely that cars simply need a second UV channel, which should be a very simple matter.Of course. Then can you tell me why Mariusz (Szkaradek, who has very best experiences in this) didn't implement it in his script?

Or even better: since this being "very simple" then why not improve Mariusz' script?
## Post #5
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-29T17:05:07+00:00
- Post Title: [Req] Sleeping Dogs UVW maps

> Reply from shakotay2
>
> That's not a problem of the source code. If I remember exactly it extracts most of the UVs. For the ones it does not it's a problem of where the uv data is stored in the model data and how it is structured.
Since this is not solved in the source code it wouldn't help you either.
The point was that even if someone else knew where's the other UV data and how it is structured, they couldn't just edit existing tools without their source code.
And for the record, the blender script in the 1st post was not plain text.
## Post #6
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-01-29T17:36:33+00:00
- Post Title: [Req] Sleeping Dogs UVW maps

> Reply from Chipicao
>
> The point was that even if someone else knew where's the other UV data and how it is structured, they couldn't just edit existing tools without their source code.
And for the record, the blender script in the 1st post was not plain text.
Well, true. I should've just uploaded the script by itself right away, but I wasn't sure if the .blend file had anything special in it.

> Reply from shakotay2
>
> Then can you tell me why Mariusz (Szkaradek, who has very best experiences in this) didn't implement it in his script?
He probably didn't even realize the problem was there. Only police vehicles, buses, etc have this issue. And besides, his comment said it was intended for characters only. Everything else still somewhat works, but they weren't his main focus.
## Post #7
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-29T21:47:41+00:00
- Post Title: [Req] Sleeping Dogs UVW maps

> Reply from shakotay2
>
> Of course. Then can you tell me why Mariusz (Szkaradek, who has very best experiences in this) didn't implement it in his script?

Or even better: since this being "very simple" then why not improve Mariusz' script?Maybe you should ask him instead of being a smartass.

UV2 mapping coords:
[](http://www.imagebam.com/image/2573ea304819321) 

In the sample file Klienod01.perm.bin, vertex buffer at offset 245440 contains 2 pairs of half floats. This is easy to spot because uint32 @offset 245324 is "8", indicating an 8byte vertex stride, instead of 4 like other UV vertex buffers.

So as I was saying, this should be a very simple matter, especially for someone "who has very best experiences in this". In Mariusz's defense, he probably didn't care - I mean no offence to him, he did a great job. But what's your excuse?


Question: doesn't either tool extract normals??
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-29T22:08:52+00:00
- Post Title: [Req] Sleeping Dogs UVW maps

> Reply from Chipicao
>
> But what's your excuse?I'm not here to quarrel with people.
So take over the work if you want and calm down.
But don't expect any comment from me on this matter. Thx.
## Post #9
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-29T22:15:09+00:00
- Post Title: [Req] Sleeping Dogs UVW maps

> Reply from shakotay2
>
> But don't expect any comment from me on this matter. Thx.Haha that boat has long sailed when you "commented" on my remark about how easy it should be to get UV2. You acted as if I was talking crap and now you say you don't want to quarrel with people?!

If however I misunderstood your first post in this topic, you have my apologies.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-29T23:03:21+00:00
- Post Title: [Req] Sleeping Dogs UVW maps

> Reply from Chipicao
>
> If however I misunderstood your first post in this topicObviously you did.
Also if you had tried my tool on Klienod you'd seen that it is capable of what you posted previously:
Klienod01_LOD_2.obj
# uv type: 8 
# 0x3BEC0-3D838
vt 0.756836 0.256836
vt 0.766602 0.283203
vt 0.725098 0.288086

It was just your starting with "very simple" what led to my response.

So take over the work or let it be.
## Post #11
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-30T00:04:25+00:00
- Post Title: [Req] Sleeping Dogs UVW maps

> Reply from shakotay2
>
> Also if you had tried my tool on Klienod you'd seen that it is capable of what you posted previously:
Klienod01_LOD_2.obj
# uv type: 8 
# 0x3BEC0-3D838
vt 0.756836 0.256836
vt 0.766602 0.283203
vt 0.725098 0.288086Excuse me but being capable of identifying a "type 8" UV block is not the same as actually reading both sets of UV coords, which is what the OP wants, which is what we've been talking about.

> Reply from shakotay2
>
> It was just your starting with "very simple" what led to my response.What part of reading 4 values instead of 2 isn't "very simple"?
Screw it, don't answer. I'm tired of this BS.
## Post #12
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-01-30T00:54:04+00:00
- Post Title: [Req] Sleeping Dogs UVW maps

Awesome find with second UV set! 

What about the rest of the stuff though? Everything else has only one set of UVs, but they must be in a different location or format or something if the existing tools can't pick them up.

As soon those errant UVs are caught we can finally be done with this once and for all.
## Post #13
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-02-02T10:46:41+00:00
- Post Title: [Req] Sleeping Dogs UVW maps

Any luck?

I tried to modify the Blender script myself based on the given information, but I'm afraid don't have nearly enough experience to make heads or tails of this whole business.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-02-02T12:47:44+00:00
- Post Title: [Req] Sleeping Dogs UVW maps

I replaced the dummy uvs in Klienod01_LOD_2.obj at 0x60B20:
[](http://www.pic-upload.de/view-22143366/Klienod01_LOD_2_new.jpg.html)

Imho it's not the 2nd uv channel - it's just the uvs for submesh_3_1.

Don't know whether they fit to the texture. If not that might be the reason I dummied them.
(As you know I closed this project some months ago.)

Did you have a look at Klienod01_LOD_0.obj, submemsh_1_1?
[](http://www.pic-upload.de/view-22144321/Klienod0.SM_1_-.jpg.html)
The uvs are slightly different from the ones for the submesh_1_1
in Klieno01_LOD_2.obj.
## Post #15
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-02-03T01:05:34+00:00
- Post Title: [Req] Sleeping Dogs UVW maps

Don't worry about it, Chipicao figured it out.

[Here's the fixed UV section of the Blender script](http://pastebin.com/wKwv1dMK). Unfortunately vehicle interiors still have no UVs, but those can be obtained with Shako's program.

> Reply from shakotay2
>
> I replaced the dummy uvs in Klienod01_LOD_2.obj at 0x60B20:


Imho it's not the 2nd uv channel - it's just the uvs for submesh_3_1.

Don't know whether they fit to the texture. If not that might be the reason I dummied them.
I think those were correct. They seem to fit [the texture](http://puu.sh/6I06B.jpg), only upside down.

Interestingly, your program manages to get the interior UVs for all models except the Klienod.


But that's just the vehicles. What about buildings/tires/weapons? Neither script nor the program can extract the UVs for those.

EDIT: Yeah, I'm pretty sure those use a different format. I'm looking at them in a text editor and there's [a clear difference](http://puu.sh/6I8A6.png) between the material data blocks. It doesn't even look like they have UVs at all!
## Post #16
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-02-05T11:32:36+00:00
- Post Title: Re: [Req] Sleeping Dogs UVW maps

Nothing? 
Ah well, I suppose I was already pushing everyone's patience by even bringing this up again.

Anyway, HUGE thanks to everyone for all their contributions. Without all your help we would still be stuck using borky 3D rippers, and look where we are now.

That's it for models/textures I suppose, but there's still plenty of other stuff. I recently discovered that the game CAN in fact run without archives, and [even created the very first mod](http://forums.sleepingdogs.net/viewtopic.php?f=11&t=4903). 
However, it's all pointless without an updated .BIG extractor, and the only person working on it quit a year ago.
Plus there's also the game's .skoo-bin script files, which can open up a whole world of possibilities if they can be decompressed.

But anyhow, thanks again guys. Hopefully people will actually care about this game when Triad Wars comes out.
## Post #17
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-05T12:46:11+00:00
- Post Title: Re: [Req] Sleeping Dogs UVW maps

Are you sure you can run the game unpacked?

Last year I did the same thing that guy in your link claims to have discovered
[viewtopic.php?p=86951#p86951](http://forum.xentax.com/viewtopic.php?p=86951#p86951)
I extracted only vehicles.big in \SleepingDogs\Data\ and deleted vehilces.big/bix. The game indeed started and worked for a while, but as soon as it had to load certain cars it crashed.
## Post #18
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-02-05T18:01:15+00:00
- Post Title: Re: [Req] Sleeping Dogs UVW maps

Yup, you were right.

I'm not quite sure what happens with Vehicles, but for all the other .BIGs it seems that the game was crashing because it was trying to load [these](http://puu.sh/6L2pq.png) files, but couldn't find them since the unpacker didn't assign them a filename. 

Try the same thing with CharactersHD or Animation, works flawlessly. All the others have unknown files and crash instantly.

Although for Vehicles, I think that may be, again, a problem with the unpacker. If you look at some of the police vehicles they seem to have corrupted textures.
## Post #19
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-04-26T00:36:39+00:00
- Post Title: Re: [Req] Sleeping Dogs UVW maps

Come on now, I know practically nobody is interested in this, but is there at least ONE person out there who can wrap this up? 

For the weapons and junk I can redo the UVs manually, but it's impossible with buildings. So much has already been done, but that one tiny detail is ruining a huge part of it.
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-07-29T12:17:10+00:00
- Post Title: Re: [Req] Sleeping Dogs UVW maps

due to a request of SJ concerning the crowbar here's the H2O files:

0x250 276
Vb1
12 99
0x550 114
020101
0xB80 8

0x1150 352
Vb1
12 99
0x14E0 129
020101
0x1BC0 8

copy each of the above 6 lines block into empty text files and rename them to crowbar_0.h2o resp. crowbar_1.h2o

Use hex2obj (view link in my sig) to load both, the CROWBAR001.perm.bin and one of the H2O files.



crowbar.JPG (46.38 KiB) Viewed 53 times



btw: I don't know why my SleepingDogs_MeshExtractor nor Mariusz blender script get these UVs and I won't bother examining it.
