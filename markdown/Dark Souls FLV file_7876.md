## Post #1
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2011-12-17T15:02:25+00:00
- Post Title: Dark Souls FLV file

Hi there my grossly incandescent cooperators. Of course I have no idea what is what but I would like your expert opinions about the file format used by Dark Souls for its 3D models.

It is of course hard for me to say if these are parts, whole models, archived animation and bones, etc, but here is one smallish file. [http://xis9.com/000000ef.flv](http://xis9.com/000000ef.flv)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-13T21:18:20+00:00
- Post Title: Dark Souls FLV file

Script: [http://db.tt/GwzbET08](http://db.tt/GwzbET08)

Wasn't there another FLVER thread. Anyways, this format is big endian.
The offset to the indices section (followed by vert buffer) is given, but I don't really understand the indices.

You keep reading shorts until you see a -1. Then that is a face I guess.
Sometimes you read 3 indices.
Sometimes you read 4 indices.
Sometimes you read 5 or even 6 indices before you see a -1.

Are there any common schemes that do that?

The vertex buffer comes right after the index buffer, 36 bytes each.
I'll have to wait until I figure out how to bind buffers in big endian before I can verify that it is correct before proceeding.
## Post #3
- Username: Phrexeus
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 04, 2012 10:43 am
- Post datetime: 2012-02-14T20:23:04+00:00
- Post Title: Dark Souls FLV file

Also interested in this.  The flver files seem to be different for dark souls.  Looking at the files in a hex editor, I can't make much sense of them, but then I'm pretty noob to this.  The ascii looks nothing like numeric coordinates, but I'm probably just going about it in the wrong way.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T00:12:43+00:00
- Post Title: Dark Souls FLV file

Be careful with some of the strings because they use 2 bytes per character and most of it is just file paths and stuff rather than an index buffer.

At first if you sort of just skim through the format it looks like an index buffer but then if you look at what it represents you'll see it and move on quickly lol
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T20:48:55+00:00
- Post Title: Dark Souls FLV file

The files I'm working with are for Dark Soul 1 that hatyn uploaded in another thread
[viewtopic.php?p=65301#p65301](http://forum.xentax.com/viewtopic.php?p=65301#p65301)

It looks like the FLVER format is about the same for dark soul 2 and armored core. I might look at the FLVER import that was written. It might just be a different type.

Just some findings.

In general, you have something like

```
numMesh MeshInfo, providing info like numVerts, vertSize and stuff
numMesh MeshData, with the indices and vertices

```


Where MeshData appears to be face indices, followed by vertices, and repeat.

The header you can base it on the blender import for the other FLVER format. It is pretty much the same thing.

```
   char[6] "FLVER\x00"
   int16[3] ??
   int32 offset to start of mesh data
   int32 size of the mesh data
   int32 numBones?
   int32 numMat
   int32 numParts?
   int32 numMesh
   int32 count
   float[6] bbox?
   
   ....
} 

```


I don't know when the header ends.

I've found sections of the mesh info that provide vert counts and vert sizes, as well as offsets to the vertex data. All offsets are relative to the start of the mesh data (the one you read in the header)
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T22:51:56+00:00
- Post Title: Dark Souls FLV file

Ok I've gotten the general structure of the format out using the blender import for reference.

I will need FLVER files for all of the games that were listed (some gundam games were there...)

There are several different types of FLVER formats, which is determined by one (or more) of the values at the very top.

DS1 and DS2 both use the same format, however Armored Core has a different format. Some of the structs are the same, but for example in armored core I haven't figured out the entries for the vertices (numVerts, vertSize, vertOfs, etc)

For now I will focus on the dark soul format.



Script permalink: [http://db.tt/GwzbET08](http://db.tt/GwzbET08)
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-19T23:04:41+00:00
- Post Title: Dark Souls FLV file

finale00, stop right now. go out and find yourself a nice woman and have some fun for a change lol.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T23:08:17+00:00
- Post Title: Dark Souls FLV file

Hmph, but this is fun
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-19T23:11:35+00:00
- Post Title: Dark Souls FLV file

i'm just kidding with you .
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-20T00:03:37+00:00
- Post Title: Dark Souls FLV file

Wow noesis took that ugly face indexing scheme with all sorts of twists and turns and changing directions into a single call.
## Post #11
- Username: Phrexeus
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 04, 2012 10:43 am
- Post datetime: 2012-02-22T00:13:33+00:00
- Post Title: Dark Souls FLV file

Mother of God...... Finale, you're doing it... awesome!!!!  You got Ornstein as well, one of the coolest bosses.  I haven't got any of the armored core, gundam files, but hatyn might.  I have half of the dark souls stuff extracted though, the rest is still in an archive that current script from chrrox doesn't open.

I will play with your script tomorrow when i get on my main PC.  Assuming all the models can be imported fine, is it likely to be straight forward to link the texture files to the 3D files automatically?  And will UVs be preserved?  I might be able to work some of this stuff out myself, but you should keep going with your greater speed and experience.
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T00:31:46+00:00
- Post Title: Dark Souls FLV file

I didn't assign the UV's cause I don't have textures to test with, but the vert buffer is there so you just need to add one line to add the UV's.

Well, there's 5 vertex types so you'll probably have to add one line for each.
There's one vertex struct that's only 28 bytes....don't know what the other 4 floats might be.

I'm not sure if the materials are assigned per mesh or per face-group or per face.
Right now it should load each mesh separately. I also don't remember seeing any texture names...are they referenced separately?
## Post #13
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-02-25T22:31:26+00:00
- Post Title: Dark Souls FLV file

OH SNAP... im off to use this..bbl!
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-25T22:51:39+00:00
- Post Title: Dark Souls FLV file

Are there filenames?
Some textures would be nice.

I didn't parse the material names or anything though.
## Post #15
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-02-25T23:04:06+00:00
- Post Title: Dark Souls FLV file

The TPFs we got are named very simple like 000000ea.TPF or something, and I don't think they actually match up the names of the textures that the model is bound to in the FLV.

I seem to be getting some errors with the FLVER import..

exported from noesis


inside noesis
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-25T23:08:49+00:00
- Post Title: Re: Dark Souls FLV file

I don't know what the function actually does when it's drawing the faces. I just pass in the the index buffer and hope it works out lol.

So it's hard to trace where the problem might be coming from (vertices are wrong? Faces are wrong?)
Or maybe if the model just looks like that in-game lol

Maybe if there was something more obvious...
## Post #17
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-02-26T09:38:35+00:00
- Post Title: Re: Dark Souls FLV file

You are right, it could very well be like this in the game..The vertices look wrong in the areas I pointed out, but maybe they are made like that on purpose. For example if its some fake, texture lighting effects or something. I will look around more  

In any case you are a mega boss finale.
## Post #18
- Username: Phrexeus
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 04, 2012 10:43 am
- Post datetime: 2012-02-26T12:19:54+00:00
- Post Title: Re: Dark Souls FLV file

I've noticed that most if not all of the models display flipped, as in right-left flipped.  Seems to be the same for hatyn's ornstein pics holding the spear in the left hand.

I'm going to dig into the script later and see what i can do.  Maybe getting textures to display won't be too hard.  And batch exporting will be almost essential for what I want to do, so i'll have to look into that.
## Post #19
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-02-27T11:47:58+00:00
- Post Title: Re: Dark Souls FLV file

made some progress with texturing and rendering: 
[http://i.imgur.com/G4Jfl.jpg](http://i.imgur.com/G4Jfl.jpg)
[http://i.imgur.com/OQOPo.jpg](http://i.imgur.com/OQOPo.jpg)
the FLVs do reference textures; also TPF's store their name inside so matching them was easy in the end. UV's were a bit tricky. i try to make some sort of map but there are a lot of models which are not used in game. hoping now to find some map-meta information.



fs1.png (244.72 KiB) Viewed 313 times
## Post #20
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-02-28T14:20:59+00:00
- Post Title: Re: Dark Souls FLV file

progress! finally deciphered map information: the NEO's contain information about map-, character-, and object-models and their instances. rendering has still some bugs because it seems i don't fully understand the meaning of the vertex attributes. 

also transformations of individual instances seem to be a bit off sometimes (last image, barrels).

[http://imgur.com/a/ie5um](http://imgur.com/a/ie5um)
## Post #21
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-28T16:18:35+00:00
- Post Title: Re: Dark Souls FLV file

So a map basically defines where all of the objects should be loaded and stuff?
## Post #22
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-02-28T16:44:33+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from finale00
>
> So a map basically defines where all of the objects should be loaded and stuff?
yes, if by map you mean the neo-files.
## Post #23
- Username: Phrexeus
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 04, 2012 10:43 am
- Post datetime: 2012-02-28T17:37:41+00:00
- Post Title: Re: Dark Souls FLV file

@vlad Oh dude, you're like 10 steps ahead of me.  I'm also trying to load map sections.  You have UVs, textures, models loading in the right position and automated loading of big sections of the map?

Where did you find the world textures, as far as I know they are in the .bdf archives is that right?  And if so do you have a script to unpack them?  Right now I only have chrrox's script to get into the .bnd's which seem to contain almost no world textures.

Are you going to share the import script you are using, if not at least give more details so the rest of us can learn from what you are doing?  Really awesome to see it coming this far.
## Post #24
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-02-28T17:58:06+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Phrexeus
>
> @vlad Oh dude, you're like 10 steps ahead of me.  I'm also trying to load map sections.  You have UVs, textures, models loading in the right position and automated loading of big sections of the map?
pretty much although i'm not certain on some semantics of vertex attributes (like UVs for second diffuse texture, bumpmaps, lightmaps, ...) 

> Reply from Phrexeus
>
> Where did you find the world textures, as far as I know they are in the .bdf archives is that right?  And if so do you have a script to unpack them?  Right now I only have chrrox's script to get into the .bnd's which seem to contain almost no world textures.
extracting the files from the .bdf's is easy, the hard part is figuring out their names, which are stored in in the .bhf's. the first thing i did was matching .bhf's to .bdf's. i don't have a script, i coded all in c#.

> Reply from Phrexeus
>
> Are you going to share the import script you are using, if not at least give more details so the rest of us can learn from what you are doing?  Really awesome to see it coming this far.
'course i share all this stuff. problem is ... how? i could share (most of) my c# code for parsing FLVs, BHF/BDFs, TPFs and NEOs. also the vertex and fragment-shaders (GLSL) i use for rendering.
## Post #25
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-28T18:05:35+00:00
- Post Title: Re: Dark Souls FLV file

Any repository would probably work. github, google projects, ...
## Post #26
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-02-28T21:14:09+00:00
- Post Title: Re: Dark Souls FLV file

so basically the PC port is 25% completed
## Post #27
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-02-28T21:26:22+00:00
- Post Title: Re: Dark Souls FLV file

ok here it is: [https://code.google.com/p/dkstools/](https://code.google.com/p/dkstools/)

a command line program is included to extract the bdf/bhf's; i hope it's self-explanatory enough. 
also are included parsers for flv, tpf, and neos. information on UVs and texture types are following ...
## Post #28
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-28T23:09:40+00:00
- Post Title: Re: Dark Souls FLV file

Samples for these other files would be great.
## Post #29
- Username: Phrexeus
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 04, 2012 10:43 am
- Post datetime: 2012-02-29T14:31:19+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from vlad001
>
> ok here it is: https://code.google.com/p/dkstools/

a command line program is included to extract the bdf/bhf's; i hope it's self-explanatory enough. 
also are included parsers for flv, tpf, and neos. information on UVs and texture types are following ...
Thanks for this!  I now have the files extracted using dksextr.  Can the flver project be used in it's current state?  Because right now I'm not sure how to get it to run.

*edit* Also is the extractor supposed to extract everything, or just world textures?  Because I can't see characters, weapons, monsters etc.  Also no .flv or .flver were extracted.
## Post #30
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-02-29T17:15:58+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Phrexeus
>
> Can the flver project be used in it's current state?  Because right now I'm not sure how to get it to run.
in its current form it is not usable by itself. you can parse files and have the data in structured form, that's it. for example, use FLVParser to parse some flv then you can access geometry data, uv's, ... through the the FLVParser's member variables (e.g. Meshes, Materials, ...). if you tell me what you want to do with the data maybe i could (help you) write some exporter or so.

> Reply from Phrexeus
>
> *edit* Also is the extractor supposed to extract everything, or just world textures?  Because I can't see characters, weapons, monsters etc.  Also no .flv or .flver were extracted.
the bdf's only contain havok files and tpf's, so yes it extracts everything from the bdf's. 
i think the flv's can be directly extracted from the dvdbnd0.bdt/bhd5 (or similar); there is a [quickbms-script](http://forum.xentax.com/viewtopic.php?f=10&t=7852) from chrrox which does that.
## Post #31
- Username: Phrexeus
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 04, 2012 10:43 am
- Post datetime: 2012-02-29T18:44:16+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from vlad001
>
> in its current form it is not usable by itself. you can parse files and have the data in structured form, that's it. for example, use FLVParser to parse some flv then you can access geometry data, uv's, ... through the the FLVParser's member variables (e.g. Meshes, Materials, ...). if you tell me what you want to do with the data maybe i could (help you) write some exporter or so.
Help with writing stuff sounds great - my programming experience is very low, but I want to learn about this stuff.

I want to convert everything into a usable format like .obj for 3d, .bmp/png/jpg etc for the textures.  And I want each model to have the correct positioning data when it's imported.  My goal is to have a complete 3D map which could be viewed and explored.  I'm not too sure if a PC can handle the entire world loaded, but it probably isn't more than a few tens of millions of polys, in which case it may work.  If it's too big for realtime then I could at least do renders.

> Reply from vlad001
>
> the bdf's only contain havok files and tpf's, so yes it extracts everything from the bdf's. 
i think the flv's can be directly extracted from the dvdbnd0.bdt/bhd5 (or similar); there is a quickbms-script from chrrox which does that.
The dvdbnd0.bdt contains 1352 .flv files, but when I use chrrox's .bdf extractor I end up with thousands more .flver files.  So I'm pretty sure they are in the .bdf's.
## Post #32
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-02-29T20:32:43+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Phrexeus
>
> I want to convert everything into a usable format like .obj for 3d, .bmp/png/jpg etc for the textures.  And I want each model to have the correct positioning data when it's imported.  My goal is to have a complete 3D map which could be viewed and explored.  I'm not too sure if a PC can handle the entire world loaded, but it probably isn't more than a few tens of millions of polys, in which case it may work.  If it's too big for realtime then I could at least do renders.
this should be fun. 
converting textures is no big problem; we only need a dxt1/dxt5 decoder (the one i use is not free unfortunately; maybe google can help here).

having a 3d-map is also my intention. from what i've seen so far this will be a challenge, though. it's not like there is "one complete" world in the data. 
for example, you see demon ruins from the catacombs (ever wondered where this hole is? . but the dr-model used in the c-map is just a "downscaled" (in terms of geometry complexity) version of the real dr-map. so for most map-parts there are actually two or more models, depending for which map it's being used.
also, the illusion quickly breaks down if you zoom out and look at whole map areas ... be warned.

i had the hole geometry without textures in memory once ... obviously the framerate was low even compared to blighttown 

> Reply from Phrexeus
>
> The dvdbnd0.bdt contains 1352 .flv files, but when I use chrrox's .bdf extractor I end up with thousands more .flver files.  So I'm pretty sure they are in the .bdf's.
i think you confuse the .bdf's with the .bnd's (?) i haven't seen a flv in any of the bdf's *shrug*
off the top of my head:
bdt/bhd5 (with chrrox script) give flv, bdf/bhf, bnd, neo, map, mof, ...
bdf/bhd give hkx, tpf (world textures)
bnd (also with chrrox script?) gives flv+tpf (models+textures of characters, chests, barrels, ... small stuff) and some more non-model stuff
## Post #33
- Username: Azraille
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 06, 2012 6:39 pm
- Post datetime: 2012-03-06T10:49:36+00:00
- Post Title: Re: Dark Souls FLV file

oh...my...god... that just happened. I've been trying to get the elite knight armor set ripped pretty much since the game launched. I had since tried to recreate it myself and [http://i.imgur.com/q534T.jpg](http://i.imgur.com/q534T.jpg) is what I got. For the love of everything please tell me that we can get model rips now
## Post #34
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-03-06T17:43:33+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Azraille
>
> For the love of everything please tell me that we can get model rips now
well sort of. the helm piece in the picture looks a little bit damaged. that makes me think i do not understand the mesh data completely. maybe the models need real skinning to look ok.



ss0001.png (165.07 KiB) Viewed 261 times
## Post #35
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-03-06T17:44:52+00:00
- Post Title: Re: Dark Souls FLV file

here the helm piece again:



ss0003.png (217.87 KiB) Viewed 261 times
## Post #36
- Username: Azraille
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 06, 2012 6:39 pm
- Post datetime: 2012-03-06T18:54:37+00:00
- Post Title: Re: Dark Souls FLV file

wow, well If a model could be extracted I'm sure some editing would clear up any irregularities and such. Though it seems to me at least that it looks terribly different to the in game model for whatever reason
## Post #37
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-03-06T19:21:18+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Azraille
>
> Though it seems to me at least that it looks terribly different to the in game model for whatever reason
you mean color-wise? well, that's because shading in my application is not perfect. to make it look like it's rendered in-game you'd need proper lighting, mix in second diffuse texture, bump-mapping, specular highlight texture, probably tone-mapping and then post-processing like anti-aliasing and dof. personally, i think we won't have that in the near future ...
## Post #38
- Username: Azraille
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 06, 2012 6:39 pm
- Post datetime: 2012-03-06T19:26:20+00:00
- Post Title: Re: Dark Souls FLV file

not just that but the models themselves seem really low rez, almost as if you got a LOD version
## Post #39
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-03-06T19:42:16+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Azraille
>
> not just that but the models themselves seem really low rez, almost as if you got a LOD version
hm, you are probably right, i will check that.
## Post #40
- Username: Azraille
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 06, 2012 6:39 pm
- Post datetime: 2012-03-06T19:43:40+00:00
- Post Title: Re: Dark Souls FLV file

have you managed to find the elite knight set yet? I would be interested in seeing that as well
## Post #41
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-03-06T21:05:21+00:00
- Post Title: Re: Dark Souls FLV file

you were right, i uploaded a picture from a low-res mesh.

edit: i mean, the pic from BEFORE was low-res, THIS attached one should have proper resolution



2012-03-06-220037_698.png (114.5 KiB) Viewed 256 times
## Post #42
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-03-06T22:13:36+00:00
- Post Title: Re: Dark Souls FLV file

here are some of the sets: [http://imgur.com/a/2iElC](http://imgur.com/a/2iElC)
## Post #43
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-03-07T00:48:15+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from vlad001
>
> here are some of the sets: http://imgur.com/a/2iElChey vlad001, i can't find any tools for converting 
 flv models, you didn't release it yet?
## Post #44
- Username: Azraille
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 06, 2012 6:39 pm
- Post datetime: 2012-03-07T01:21:09+00:00
- Post Title: Re: Dark Souls FLV file

I would love you forever if you could either send me exports or tell me how to get them
## Post #45
- Username: Eiwo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Dec 21, 2011 10:06 am
- Post datetime: 2012-03-07T01:39:54+00:00
- Post Title: Re: Dark Souls FLV file

Vlad, that is amazing!
## Post #46
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-03-07T18:40:51+00:00
- Post Title: Re: Dark Souls FLV file

weapons and shields:
[http://imgur.com/a/M4N5Y](http://imgur.com/a/M4N5Y)
[http://imgur.com/a/JHelX](http://imgur.com/a/JHelX)

(edit: fixed imgur upload)
## Post #47
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-03-07T20:41:02+00:00
- Post Title: Re: Dark Souls FLV file

Win! I can't tell but, are you able to get the normal and other maps assigned too? I think there is a texture, normal map and reflection map on the models.

Anyway, I haven't tried your CS projects yet as I am not a golfer. Can your scripts spit out OBJs?
## Post #48
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-03-08T00:52:38+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from hatyn
>
> are you able to get the normal and other maps assigned too? I think there is a texture, normal map and reflection map on the models.
normals per vertex yes, bumpmaps no. not yet anyway. there are a lot of possible ways to implement bumpmapping ... so may be some time to figure out how it's done here. also second diffuse texture is not so easy as it seems. haven't tried specular maps or light maps. currently looking into material definitions; perhaps there are some hints on how to render stuff.

> Reply from hatyn
>
> Can your scripts spit out OBJs?
no, but that wouldn't be hard to implement, i think.
## Post #49
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-03-09T23:05:25+00:00
- Post Title: Re: Dark Souls FLV file

lighting with and without bump mapping: [http://imgur.com/a/DlKtg](http://imgur.com/a/DlKtg)
## Post #50
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-09T23:10:33+00:00
- Post Title: Re: Dark Souls FLV file

Wow bump maps make quite a difference.
## Post #51
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-03-10T19:14:34+00:00
- Post Title: Re: Dark Souls FLV file

some pics from my dark souls map: [http://imgur.com/a/2nZTo](http://imgur.com/a/2nZTo)
i ended up using the collision detection data for rendering because its less data; so no textures 'n stuff. instead i color-coded the areas.

the world is pretty much consistent geographically, except catacombs and tomb of the giants do not fit in so nicely. well, it's a great piece of artwork what from did there, anyhow.
## Post #52
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-03-11T13:13:13+00:00
- Post Title: Re: Dark Souls FLV file

oh damn so good..
## Post #53
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-04-03T08:32:33+00:00
- Post Title: Re: Dark Souls FLV file

OK I am back to dog you maniacs! About to use vlad's tools - I am anxious and thinking the neo's and UVs won't really be dealt with when using the extrator from the code dump. Will report back!

Vlad - thanks for making me download Visual Studio 

*HMM..so of course it maybe my mistake but the exe I ended up with only extracted TPFs, HKXs and some kind of broken XUI files. The TPFs can't be read by Noesis plugin we have for Dark Souls TPFs. If you are still around, please advise!
## Post #54
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-04-03T11:01:30+00:00
- Post Title: Re: Dark Souls FLV file

ok, are you using the ps3 or 360 version? there is a difference; i wrote the code for the 360 version as these discs are easier to rip.

i don't know about noesis but the tpf's are mostly just dxt-encoded textures. a texture with type 0x0000 is a dxt1 compressed tiled ARGB texture in big endian format, so: data -> byte-swap -> convert to linear -> dxt1 decode. there is code floating around in the internets which can do the last two steps (google for converttolinear decodedxt1 decodedxt5). 0x0500 is the same just with dxt5 compression. type 0x1800 is a dxt1 compressed bump map and uses only two components (X8Y8) instead of three (R5G6B5).

also, the exe is mostly useless. the code should just document my findings on the various file formats.
## Post #55
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-04-03T18:41:43+00:00
- Post Title: Re: Dark Souls FLV file

thanks for your answers! Its outta my league then!
## Post #56
- Username: DARKSETH
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 11, 2012 8:42 pm
- Post datetime: 2012-04-11T13:00:26+00:00
- Post Title: Re: Dark Souls FLV file

Damn I almost cried when I found this thread. Just got PLAT on my Ps3 version of Dark Souls    . I don't have a Blue-Ray drive in my PC. Would you guys maybe share the Characters/Shield and Weapons with me that you exported already. Pretty Please   

Like the forum.
## Post #57
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-04-11T13:04:11+00:00
- Post Title: Re: Dark Souls FLV file

Even if you had a BD drive, the contents would be encrypted. You need a PS3 to read the data for you from a a PS3 disc.
## Post #58
- Username: DARKSETH
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 11, 2012 8:42 pm
- Post datetime: 2012-04-11T13:45:44+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Rick
>
> Even if you had a BD drive, the contents would be encrypted. You need a PS3 to read the data for you from a a PS3 disc.
Thanks for the Info. That's why I asked If someone will share the files.
## Post #59
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-04-14T01:30:29+00:00
- Post Title: Re: Dark Souls FLV file

so here's my map viewer: [http://www.mediafire.com/file/js5j37v9c ... mv-0.1.exe](http://www.mediafire.com/file/js5j37v9c8cljjd/dksmv-0.1.exe)

very unpolished and somewhat ... ugly: no textures, no effects. i did not even use the real geometry but misused collision detection data.
well anyway, that's it for me and dark souls hacking.
## Post #60
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-14T02:03:13+00:00
- Post Title: Re: Dark Souls FLV file

I'm sure someone will find your code useful.
## Post #61
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-04-14T14:51:22+00:00
- Post Title: Re: Dark Souls FLV file

new version: [http://www.mediafire.com/file/ygjx2w93d ... mv-0.2.exe](http://www.mediafire.com/file/ygjx2w93dcefws9/dksmv-0.2.exe)

some fixes, and now needs only .net framework 2.0 (the other needed 4.0).
## Post #62
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-04-19T13:37:29+00:00
- Post Title: Re: Dark Souls FLV file

super cool! 

BUuuUuUT how much will you charge for a model exporter with UV and textures? Dying for OBJs with textures.
## Post #63
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-04-19T14:23:05+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from hatyn
>
> super cool! 

BUuuUuUT how much will you charge for a model exporter with UV and textures? Dying for OBJs with textures.

i wouldn't dare to charge a single dime  
i started working on an exporter for the 360 game data a while ago, but this costs time and i have not very much of that currently. but it will happen.
## Post #64
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-04-19T16:05:52+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from vlad001
>
> new version: http://www.mediafire.com/file/ygjx2w93d ... mv-0.2.exe
some fixes, and now needs only .net framework 2.0 (the other needed 4.0).can you reupload this? thanks
## Post #65
- Username: Phrexeus
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 04, 2012 10:43 am
- Post datetime: 2012-04-20T10:34:47+00:00
- Post Title: Re: Dark Souls FLV file

VLAAAAAAAADDDDDD  You are a freaking legend.  This 3D map viewer totally surpasses my wildest expectations!  I'm totally geeking out right now.

*edit* Toysk - try this link [http://www.mediafire.com/file/uxjdulq3x ... mv-0.2.exe](http://www.mediafire.com/file/uxjdulq3x43z0wu/dksmv-0.2.exe)

Vlad - the map viewer really needs a "fly" type of mode using WSAD.  Right now its kind of hard to view a level from inside.
## Post #66
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-04-21T15:57:30+00:00
- Post Title: Re: Dark Souls FLV file

someone has bdf/bhf unpacker? 'cause it seems vlad delete 'source code' for it from 'google projects'
## Post #67
- Username: Phrexeus
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jan 04, 2012 10:43 am
- Post datetime: 2012-04-21T18:08:08+00:00
- Post Title: Re: Dark Souls FLV file

There was one posted in the other dark souls thread.  Search in the game archive research forum.
## Post #68
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-04-21T18:22:59+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Phrexeus
>
> There was one posted in the other dark souls thread.  Search in the game archive research forum.already read all threads that relates to the 'dark souls' on xentax, but didn't found anything, show me, if you know
## Post #69
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-21T18:45:38+00:00
- Post Title: Re: Dark Souls FLV file

[viewtopic.php?f=10&t=7852&hilit=dark+souls](http://forum.xentax.com/viewtopic.php?f=10&t=7852&hilit=dark+souls)
## Post #70
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-04-22T11:19:28+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from vlad001
>
> hatyn wrote:super cool! 

BUuuUuUT how much will you charge for a model exporter with UV and textures? Dying for OBJs with textures.

i wouldn't dare to charge a single dime  
i started working on an exporter for the 360 game data a while ago, but this costs time and i have not very much of that currently. but it will happen.

I wonder if it is better to wait until the PC version comes out in August... Maybe it will be easier? Or at least, you will have a far wider audience for your tools. SHieeet, I wonder if we can actually edit the textures, making them very detailed or something.
## Post #71
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-04-22T11:32:53+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from chrrox
>
> viewtopic.php?f=10&t=7852&hilit=dark+souls
correct me if i'm wrong but none of these tools is not work with bdf/bhf files
## Post #72
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-22T12:41:02+00:00
- Post Title: Re: Dark Souls FLV file

send me a sample that does not work. a lot of the rips that floated around the internet were encrypted and ripped badly.
## Post #73
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-04-22T13:01:01+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from chrrox
>
> send me a sample that does not work. a lot of the rips that floated around the internet were encrypted and ripped badly.
pmed you
## Post #74
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-05-10T19:50:14+00:00
- Post Title: Re: Dark Souls FLV file

AUGHHH VLAD
## Post #75
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-05-10T19:56:48+00:00
- Post Title: Re: Dark Souls FLV file

I just noticed something...
## Post #76
- Username: snider029
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 11, 2012 8:26 am
- Post datetime: 2012-05-11T00:38:00+00:00
- Post Title: Re: Dark Souls FLV file

Okay Vlad this is amazing, and is there anyway way someone can upload all the models to 4shared or something I want to use the to make full size pepakura armor, then use said armor to make actual armor from the pepakura ones.
## Post #77
- Username: Coda
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 22, 2012 3:56 am
- Post datetime: 2012-05-21T20:00:30+00:00
- Post Title: Re: Dark Souls FLV file

By God, I've been browsing these forums for a long time but this, I had to join to say, I'd give you half the blood in my body for those models and textures.
## Post #78
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2012-05-24T07:53:59+00:00
- Post Title: Re: Dark Souls FLV file

Same here, I really want to port these armors to Skyrim or Oblivion, as well as Garry's Mod.
## Post #79
- Username: popyea
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 07, 2012 4:31 pm
- Post datetime: 2012-05-25T02:32:31+00:00
- Post Title: Re: Dark Souls FLV file

I just want to look at them in fine detail.
## Post #80
- Username: Outlander
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 13, 2012 12:19 pm
- Post datetime: 2012-07-13T05:21:36+00:00
- Post Title: Re: Dark Souls FLV file

Maybe I'm a little late for the party. I've been looking for some dark souls models to use with Pepakura. I saw the awesome renders that vlad001 was able to pull but I havn't found any actual models around the webs. Can anyone share the models with me? I'm specifically looking for ornstein or Lautrec, but I'd make due with whatever the community can help with.
## Post #81
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-13T05:30:03+00:00
- Post Title: Re: Dark Souls FLV file

Just get the game; then all the models are yours.
## Post #82
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2012-08-24T10:21:27+00:00
- Post Title: Re: Dark Souls FLV file

Now that the PC version is out, is anyone taking a look at the files? They seem a bit different than the console versions.
## Post #83
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-24T18:13:05+00:00
- Post Title: Re: Dark Souls FLV file

Don't have the game .Samples? Is it just different endian?
## Post #84
- Username: SonofUgly
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Feb 25, 2012 9:43 pm
- Post datetime: 2012-08-24T23:29:43+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from finale00
>
> Don't have the game .Samples? Is it just different endian?
Completely new to this, but here are some files I extracted from dvdbnd0.bdt: [Here.](http://www.mediafire.com/?jy9zx2611aqjayf)

Also I have tried using tools that you guys have made, but I can't get anything to work, and was wondering if someone could write up an easy to follow guide? And maybe upload a compiled version of vlad's dkstools.
## Post #85
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-25T00:07:44+00:00
- Post Title: Re: Dark Souls FLV file

lol, this is the header. Everything suddenly makes sense.

```
byte endian #"B" or "L"

```


The format is similar though.
## Post #86
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2012-08-25T16:50:12+00:00
- Post Title: Re: Dark Souls FLV file

Would love to see some research on this game with the PC version out. I am trying myself currently, but I am still a n00b.
## Post #87
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-08-26T14:50:54+00:00
- Post Title: Re: Dark Souls FLV file

[http://svn.gib.me/public/darksouls/trunk/](http://svn.gib.me/public/darksouls/trunk/)

Not model stuff, but unpacker/unbinders.

Also, the texture format has changed from PS3 version to PC. Every texture is now a nice DDS file wrapped in the TPF format.
## Post #88
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-26T20:53:51+00:00
- Post Title: Re: Dark Souls FLV file

Can someone send me some files with proper filenames (rick's code looks like there are actual names)

I would prefer a full set including material library as well as textures.

I'm wondering if the console versions also have a similar archive format with filenames.
## Post #89
- Username: haekb
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 14, 2011 11:16 am
- Post datetime: 2012-08-27T19:33:14+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from finale00
>
> Can someone send me some files with proper filenames (rick's code looks like there are actual names)

I would prefer a full set including material library as well as textures.

I'm wondering if the console versions also have a similar archive format with filenames.

Did you want something like this? 
[http://minus.com/mds7UKH06/](http://minus.com/mds7UKH06/)
## Post #90
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2012-08-29T16:58:55+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from haekb
>
> finale00 wrote:Can someone send me some files with proper filenames (rick's code looks like there are actual names)

I would prefer a full set including material library as well as textures.

I'm wondering if the console versions also have a similar archive format with filenames.

Did you want something like this? 
http://minus.com/mds7UKH06/

haekb, I see you beat it to me. Was going to provide some files as requested by finale00, thanks. The tree structure and file organisation is the same as for the PSX and XBOX 360.
## Post #91
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-03T04:57:46+00:00
- Post Title: Re: Dark Souls FLV file

PC version is the exact same format except everything is little endian.
## Post #92
- Username: whiteraven
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 17, 2012 4:20 am
- Post datetime: 2012-09-04T15:34:59+00:00
- Post Title: Re: Dark Souls FLV file

hey i am an avid 3d modeler and i primarily use blender, could anyone please upload some .objs? and texture files normal people can read >_<, i thank you guys for all your hard work. I mainly want the .obj of the elite knight set + textures, i want to make some hardcore aweseome renders and ill post what i make. Also im using this as research to create a dark souls mini HD movie with photorealistic CG, but to be really realistic i need the base file to go off of .
Once again thank you guys so much for your hard work.
## Post #93
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2012-09-13T13:56:14+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Rick
>
> http://svn.gib.me/public/darksouls/trunk/

Not model stuff, but unpacker/unbinders.

Also, the texture format has changed from PS3 version to PC. Every texture is now a nice DDS file wrapped in the TPF format.

Hi, does anyone have a compiled version of Rick's tools above that they can share? Also, what is the status of the tools for the FLV and TPF files for the PC version? Thanks!
## Post #94
- Username: nullvector
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 13, 2012 6:11 pm
- Post datetime: 2012-09-13T15:25:17+00:00
- Post Title: Re: Dark Souls FLV file

Compiled versions of his tools
[http://www.mediafire.com/?dxarranbataxrsa](http://www.mediafire.com/?dxarranbataxrsa)

I'm digging through the params and paramdef files now to figure those out.
If anyone knows anything about those, I would be grateful.
## Post #95
- Username: Silvist
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 31, 2011 1:30 pm
- Post datetime: 2012-09-13T17:48:22+00:00
- Post Title: Re: Dark Souls FLV file

Heyo everyone,

Just wanted to thank you guys for all the hard work.  Just tested the compiled tools that nullvector uploaded, and it worked like a charm.  Now I just gotta look through the files and find what I'm after 

Is it just the BDT and BHD that have the files inside of them?

What's really surprising to me is that each weapon seems to have its own havok animation included lol.

@zardalu - The compiled tools that nullvector has a tool inside that already converts the tpf to dds format.  

Now I just need a plugin for 3ds max, and I'm set lol.  Though typically I seen you guys build blender plugins..so guess I'll have to make do ;p
## Post #96
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-13T19:18:32+00:00
- Post Title: Re: Dark Souls FLV file

Actually I only know one person here that (exclusively) writes blender (2.49) scripts.
Most are 3dmax or noesis.
## Post #97
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-09-14T02:54:24+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nullvector
>
> Compiled versions of his tools
http://www.mediafire.com/?dxarranbataxrsaIf you want to correctly use these compiled tools, you'll need to grab the projects directory from the repo and drop it in that directory, or Unpack won't know any file names.

> Reply from nullvector
>
> I'm digging through the params and paramdef files now to figure those out.
If anyone knows anything about those, I would be grateful.I have boatloads of uncommitted code that can read the param/paramdef files, as well as the drb (UI) files. I'll get around to committing them soon.

Also, I'll add my darksouls repo to my autobuild system eventually, just have not gotten around to it yet.

Currently working on a model and map viewer to see how far I get, I can read 99% of the model file format now (though there are unknowns).

[](http://i.imgur.com/WnvB6.png)
## Post #98
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2012-09-15T22:34:33+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Rick
>
> nullvector wrote:Compiled versions of his tools
http://www.mediafire.com/?dxarranbataxrsa
If you want to correctly use these compiled tools, you'll need to grab the projects directory from the repo and drop it in that directory, or Unpack won't know any file names.

Thanks Rick, that got it working, great work!

> Reply from nullvector
>
> Currently working on a model and map viewer to see how far I get, I can read 99% of the model file format now (though there are unknowns).

Outstanding, there are some great models in this game.
## Post #99
- Username: Silvist
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 31, 2011 1:30 pm
- Post datetime: 2012-09-16T16:34:03+00:00
- Post Title: Re: Dark Souls FLV file

@finale00 - Well that's really good to know then.  For the short visits I've made on here (since this is the source of where it all begins ;p), I guess I just kept seeing blender plugs.

@Rick - Looks awesome, can't wait to see how it progresses next ^^
## Post #100
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2012-09-29T09:36:38+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Rick
>
> nullvector wrote:Compiled versions of his tools
http://www.mediafire.com/?dxarranbataxrsa
If you want to correctly use these compiled tools, you'll need to grab the projects directory from the repo and drop it in that directory, or Unpack won't know any file names.
nullvector wrote:I'm digging through the params and paramdef files now to figure those out.
If anyone knows anything about those, I would be grateful.I have boatloads of uncommitted code that can read the param/paramdef files, as well as the drb (UI) files. I'll get around to committing them soon.

Also, I'll add my darksouls repo to my autobuild system eventually, just have not gotten around to it yet.

Currently working on a model and map viewer to see how far I get, I can read 99% of the model file format now (though there are unknowns).

Wow, you've done really great so far. Keep up the good work! Definitely looking forward to when I can export models with rigging and put them into SFM or something.

edit: Just had an idea, how similar are the file formats between Demon's Souls and Dark Souls? I know they run on the same engine, but I'm curious to see if both game's model formats are similar. If they are you could possibly make the modelviewer and tools be able to view both Demon's and Dark Souls model files.
## Post #101
- Username: whiteraven
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 17, 2012 4:20 am
- Post datetime: 2012-10-16T15:02:29+00:00
- Post Title: Re: Dark Souls FLV file

lnk to download the files are broken. Can someone give a new link the the bvh files vlad had that he got all the armors from?
## Post #102
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2012-10-28T13:22:01+00:00
- Post Title: Re: Dark Souls FLV file

Does anyone have a compiled version of [https://code.google.com/p/dkstools/](https://code.google.com/p/dkstools/)? I'm trying out finale00's Noesis script right now but it doesn't seem to do bones and I'm wondering if vlad's tools do.
## Post #103
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2012-11-05T06:14:55+00:00
- Post Title: Re: Dark Souls FLV file

Well, I tried compiling vlad's stuff myself and it ended up being a complete waste of time since it just plain doesn't work, both programs throw errors in my face when I try to run them. Doesn't help that I don't know what the hell I'm doing, but the error is something about an index array being out of bounds and it refers to BDFparser.cs.

Would like some help trying to get this working or for someone who actually knows what they're doing to compile this, because I'm curious to see if his tools can even dump models of any kind. I'm basically at the end of my rope trying to get meshes out of this game, the existing Noesis script results in basically useless (to me) meshes as they contain no UVs or weights and I have yet to hear back from finale00 on what lines need to be added to the script in order to get them to load into Noesis with the mesh, and every other ripping method I've tried results in nothing usable.
## Post #104
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2012-11-30T08:12:48+00:00
- Post Title: Re: Dark Souls FLV file

So, has there been any progress on anyone's tools? Or is this thread just dead?
## Post #105
- Username: vlad001
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Feb 08, 2012 12:25 am
- Post datetime: 2012-12-03T16:19:44+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from TehDave
>
> So, has there been any progress on anyone's tools? Or is this thread just dead?
Well, my point of view is this: the code that I shared should be used as a reference on how the data is structured/parsed. I never intended to write an exporter for game data to any meaningful format.

The exception you get is most probably because of byte ordering issues. I wrote this stuff for the Xbox 360 version of the game files, which use big endian byte ordering, whereas you probably ran the tools against the PC version, which happen to be little endian.
## Post #106
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2012-12-04T07:28:50+00:00
- Post Title: Re: Dark Souls FLV file

The error happens when I tried to run the program, which probably has something to do me fucking up compiling it since I've never used visual studio before.

Hopefully someone uses the work you did to make some sort of importer or something.
## Post #107
- Username: burrowingbob
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 09, 2013 5:57 am
- Post datetime: 2013-02-08T22:40:39+00:00
- Post Title: Re: Dark Souls FLV file

Ok so for a noob like me who knows very little about programming, how do I extract the models and textures from the game? which tools do I use and how do I use them.

any help is greatly appreciated.
thanks in advance
## Post #108
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2013-04-09T23:03:16+00:00
- Post Title: Re: Dark Souls FLV file

This game uses havoc animation. I hate to sound greedy but if there is a way to extract the animation file  i think we can use the skyrim converter to extract the data into 3ds max
## Post #109
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2013-05-10T14:54:26+00:00
- Post Title: Re: Dark Souls FLV file

Heya guys, first of all, I would like to say thanks to everyone doing the research needed for this awesome, kudos to all of that and much appreciated!

I do have a couple of questions, I am using AlphaTwenty's BMS script for the PC/X360 version, and it keeps on returning me an error of "0 byte return of 4", and no matter what I try, it keeps the issue. Any solutions to that end?

I also tried complied version of Ricks tools, but they give me back .dcx files? Basically, a file ending in .BHND will become .BHND.dcx for some reason, ALL of them. To add to the issues, the files I get back are pretty...few. I don't see any TPF files other then maybe a couple of them, and they're not big enough to encompass ALL of the textures.

Also, I don't see any FLV/FLVER files, other then maybe a couple of them (a large part of them are bhnd, anim, etc).

So to that end, I have to ask, am I missing something? I was under the impression that you could extract the most basic of the mesh and texture for the models, AT LEAST the textures, but I can't seem to be able to no matter what.

Oh, also, I have the PC version of the game, could that be the issue? Although in my defense, all the tools I tried claimed to be PC version compatible.

I'm getting really frustrated, all I want to do is to retex a couple of armors with intricate details, dumping texture via DSFix hardly seems intuitive way to do that.

Cheers in advance!
## Post #110
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-05-12T20:53:11+00:00
- Post Title: Re: Dark Souls FLV file

.dcx means the file is wrapped in a compression format. When you unpack a bhd5+bdt pair with my tools, you will get lots of files. If the extension (if it has a .dcx extension, look at the extension before that, such as "m10_00_00_00.luabnd.dcx": the extension is "luabnd") of an extracted file includes "bnd" (as in "bind"), this means that file needs to be unpacked with the Unbind tool.
## Post #111
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2013-05-13T21:24:00+00:00
- Post Title: Re: Dark Souls FLV file

Ah, OK, got it. Didn't know how to use the unbind file before now.

Cheers!

EDIT: Can anyone confirm if the FLV Noesis plugin actually does spit out models with UV's?
## Post #112
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2013-05-17T02:35:10+00:00
- Post Title: Re: Dark Souls FLV file

The newest (edited) version of the script does, still no rigging though and some models crash Noesis now (Seath being one of them)

You can find that here: [http://www.mediafire.com/view/?zielsq0268il1yu](http://www.mediafire.com/view/?zielsq0268il1yu)
## Post #113
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2013-05-18T14:34:28+00:00
- Post Title: Re: Dark Souls FLV file

Nice, nice, nice, nice!  

Cheers for the update!
## Post #114
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-06-17T05:38:48+00:00
- Post Title: Re: Dark Souls FLV file

Hey guys, I've been lurking in the Dark Souls topics for some time now, working quietly on my own project, and just wanted to show you guys how far I've gotten, and start exchanging information with whomever else is working on this format.

First, a screenshot, then a description of what's in it:
[](http://imageshack.us/photo/my-images/6/0yn2.jpg/)

So I've written custom parsers for the following files to support what I have so far:

* .flver
* .mtd
* .dds
* .tpf
* .*bnd
* .bdt/bhd
* .bdt/bhd5

What this translates into is that it loads directly from the original archive files without any need to extract files or anything. Currently, this app is only for the PC version, but I have passive plans to extend support for other systems in the future; however this is very low on my priority list.

What you're seeing in the screenshot is the vertices/indices of the mesh, the diffuse, bump, and specular textures, the UVs, vertex colors, normals, and [bi]tangents. This also includes all LODs for the diffuse/bump/specular textures, as well as for the vertices/indices. Supporting that are 12 custom shaders that I wrote to render it all nicely. (I'd have used the compiled shaders that are in the Dark Souls archives since they're in a standard format, but the engine I'm using doesn't support directly putting compiled shaders into the render pipeline.)

I'm currently working on the bones so I can start posing the character, and then I'll be jumping into the animation system, which I suspect won't be too terrible to work with once I have the bones setup properly. Does anybody have any insight into the format of the bone information in the .flver file yet?

I'm planning to make another post in the not-too-distant future with some more technical details about the file format, for those interested.
## Post #115
- Username: burrowingbob
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 09, 2013 5:57 am
- Post datetime: 2013-06-17T19:22:24+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> Hey guys, I've been lurking in the Dark Souls topics for some time now, working quietly on my own project, and just wanted to show you guys how far I've gotten, and start exchanging information with whomever else is working on this format.

First, a screenshot, then a description of what's in it:


So I've written custom parsers for the following files to support what I have so far:

* .flver
* .mtd
* .dds
* .tpf
* .*bnd
* .bdt/bhd
* .bdt/bhd5

What this translates into is that it loads directly from the original archive files without any need to extract files or anything. Currently, this app is only for the PC version, but I have passive plans to extend support for other systems in the future; however this is very low on my priority list.

What you're seeing in the screenshot is the vertices/indices of the mesh, the diffuse, bump, and specular textures, the UVs, vertex colors, normals, and [bi]tangents. This also includes all LODs for the diffuse/bump/specular textures, as well as for the vertices/indices. Supporting that are 12 custom shaders that I wrote to render it all nicely. (I'd have used the compiled shaders that are in the Dark Souls archives since they're in a standard format, but the engine I'm using doesn't support directly putting compiled shaders into the render pipeline.)

I'm currently working on the bones so I can start posing the character, and then I'll be jumping into the animation system, which I suspect won't be too terrible to work with once I have the bones setup properly. Does anybody have any insight into the format of the bone information in the .flver file yet?

I'm planning to make another post in the not-too-distant future with some more technical details about the file format, for those interested.

fucking awesome dude! if you don't mind, can I use it?  I'm particularly interested in the silver knight helmet. man I've been looking for this thing for MONTHS now and it looks like it's finally here!!!
## Post #116
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-06-17T19:34:58+00:00
- Post Title: Re: Dark Souls FLV file

The silver knight shown in the picture isn't my own creation, nor is it the in-game one converted to another format -- it's the original files from the game, being displayed in my application.

That said, there's nothing really to give you beyond what you probably have already.
## Post #117
- Username: burrowingbob
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 09, 2013 5:57 am
- Post datetime: 2013-06-17T19:43:57+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> The silver knight shown in the picture isn't my own creation, nor is it the in-game one converted to another format -- it's the original files from the game, being displayed in my application.

That said, there's nothing really to give you beyond what you probably have already.

what do you mean what I have already? do you mean the files already linked in the comments here? well the thing is i don't know how to use most of those unfortunately
## Post #118
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-06-17T19:54:48+00:00
- Post Title: Re: Dark Souls FLV file

What I mean is that the silver knight shown in the screenshot is the file that came as part of Dark Souls. I haven't extracted it, or converted it, or anything- it's just the file that came with Dark Souls.
## Post #119
- Username: burrowingbob
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 09, 2013 5:57 am
- Post datetime: 2013-06-17T20:33:59+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> What I mean is that the silver knight shown in the screenshot is the file that came as part of Dark Souls. I haven't extracted it, or converted it, or anything- it's just the file that came with Dark Souls.
I see.
are you working on a converter? if yes, on what term can I and other people expect this?
## Post #120
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-06-17T20:49:52+00:00
- Post Title: Re: Dark Souls FLV file

Well, I'm working on a converter of sorts, however my official response to timeframe questions is "when it's ready". With programming in general, but even moreso with reverse engineering, it's quite difficult to even guess as to when something will be finished.

This application of mine still has a long ways to go before I would consider it worthy of release. But I digress- this thread is for talking about the file format, not my application.
## Post #121
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2013-06-18T11:26:51+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> I'm currently working on the bones so I can start posing the character, and then I'll be jumping into the animation system, which I suspect won't be too terrible to work with once I have the bones setup properly. Does anybody have any insight into the format of the bone information in the .flver file yet?

I'm planning to make another post in the not-too-distant future with some more technical details about the file format, for those interested.

I have the Skeleton struct form GUNDAM UC, and I recall it works on Dark Souls I & II as well !?
The bone data start right after material data and the format:

```
 float[3]	TranslateXYZ
 dword		ofsBoneName
 float[3]	RotationXYZ	//in radian
 word		ParentID
 word		Idx1?
 float[3]	ScaleXYZ
 word		Idx2?
 word		Idx3?
 float[20]      ?		//forgot what they are now!
}
```

hope these help.
## Post #122
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-06-18T12:03:10+00:00
- Post Title: Re: Dark Souls FLV file

Hmm, that's mostly what I've got too, although I haven't gotten to the point of inspecting the rotation on whether it's degrees or radians- I'll have to look into that!

I also have some notes on Idx1, Idx2, and Idx3, although it's all speculation at this point:
Idx1 I have labelled as "FirstChildIndex" because it always seems to be for a child bone, Idx2 I have labelled as "FirstSiblingIndex" because it always seems to be for a sibling bone, and Idx3 I have labelled as "CopyOfIndex" because it always seems to be for a somewhat related bone (say the shin vs thigh, or r_clavicle vs l_clavicle).

Also within that last array of floats, I have notes that elements 0-2 are the lower bounding box, and 5-7 are the upper bounding box, however these are based only on notes from vlad001's source code at this time.
## Post #123
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2013-06-19T00:28:50+00:00
- Post Title: Re: Dark Souls FLV file

Amazing work, nyxo. 

You should take a look at Demon's Souls after you finish with Dark Souls' file formats, the formats for Demon's Souls are pretty much identical to Dark Souls.
## Post #124
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-06-19T00:43:50+00:00
- Post Title: Re: Dark Souls FLV file

I'm mildly interested in that, but significantly moreso than that, I'm interested in Dark Souls 2, when it comes out! You can be sure I'll be poking at that when the time comes~ ^-^v
## Post #125
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-06-19T05:25:45+00:00
- Post Title: Re: Dark Souls FLV file

So here's some WIP structures that I'm currently looking at.

First, what appears to be matrices- these are stored before the materials, but I'm not 100% sure what they're really for, and a bunch of the values are speculation at best, as I haven't had a chance to map them across the actual mesh yet.

```
    Vector3_Float Row1;
    byte Unknown1;  //Always 0xFF
    byte UnknownID1;
    short Unknown2; //Always 0xFFFF or 0x0000
    Vector3_Float Row2;
    short UnknownID2;
    short UnknownID3;
    Vector3_Float Row3;
    short Unknown3;
    short Unknown4;
    byte Null[16];
} MatrixStruct;
```


Secondly, the bone data, as far as I've got it. The thing to note here tho, is that I haven't managed to get it perfectly set up with the mesh data- I'm fairly confident that my hierarchy isn't 100% correct, and it almost looks like a portion of it is actually rotated on one of the axes.

```
    Vector3_Float Translation;
    NameStruct Name;
    Vector3_Float Euler;
    ushort ParentIndex;
    ushort FirstChildIndex;
    Vector3_Float Scale;
    ushort FirstSiblingIndex;
    ushort CopyOfIndex;
    Vector3_Float BBLower;
    ushort IsNub;
    ushort Unknown6;
    Vector3_Float BBUpper;
    ushort Unknown7;
    ushort Unknown8;
    uint Unknown9[12];
} BoneStruct;
```


I've also been looking at the VertexDescriptors and Vertex data to try and find the bone assignments/weights, but haven't had huge luck with that yet. I'm relatively confident that VertexDescriptors with a DataType of 0x1A and 0x11 are the values we want to look at, but I haven't yet found a combination that works properly for all the bones. 'Course, the success of this relies partially on the bones actually being positioned correctly, hence the above speculations regarding the matrices and bones. ^-^

I'll look more into this tomorrow morning for a couple hours, but after that I won't have a chance until after work the day following. Sometime from then through the weekend I'm hoping to have a chance to put together a decent file description of the .flver format- although what I might do instead is just release my 010 Editor template, since it breaks the data all up beautifully not only in the editor, but in relatively easy-to-read C style structs.

Actually, now that I've typed that out, I'm pretty sure that's the way to go.  I also have 010 Editor templates for a bunch of the other formats, so that would be convenient.
## Post #126
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2013-06-19T14:09:22+00:00
- Post Title: Re: Dark Souls FLV file

First of all, I don't know what ver of FLV you are looking for:

```
 char[6]	PhyreID		//"FLVER\0"
 word		Endian
 word		Ver_Major
 word		Ver_Minor
 long		ofs...
 ...
}
```

That what I can remember ATM.

And Gundam UC use Ver 2.14.

Right after the header, there are a group of 0x40 bytes each data which I am pretty sure they are not related to bones!

then material and then bones data

all these bones data are in local coordinate which means you have to transform then with their parent coordinate.
I use thisBoneMatrix *= thisBone.parent.BoneMatrix to get the proper result. They are perfectly fine in Gundam UC.

About the the bones indices / skin weight data.
Do you know there is a chunk of vert-Info to tell you how the elements combine into a single vert(I call it vert Info).
It's something like:

```
 dword		ElementID
 dword		ofs_Single_VT
 dword		?
 dword		Element_Type	//0 = coordinate, 1 = weight, 2 = bone index, 4 = UV, 10 = VertColor
 dword		?
}
```
## Post #127
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-06-19T22:58:53+00:00
- Post Title: Re: Dark Souls FLV file

Hi fatduck! Thanks for the info!
The version bytes in the files I currently have open are 0x0C000200.
Yes, I could see that the bones are in relation to their parents, however I'm having issues properly forming the hierarchy of bones. The bone struct I have so far:

```
    Vector3_Float Translation;
    NameStruct Name;
    Vector3_Float Euler;
    ushort ParentIndex;
    ushort FirstChildIndex;
    Vector3_Float Scale;
    ushort FirstSiblingIndex;
    ushort CopyOfIndex;
    Vector3_Float BBLower;
    ushort IsNub;
    ushort Unknown6;
    Vector3_Float BBUpper;
    ushort Unknown7;
    ushort Unknown8;
    uint Unknown9[12];
} BoneStruct;
```


If I assume that the ParentIndex value is correct (and assuming that a value of -1 means "no parent"...), I can form something similar to the hierarchy I'm expecting. However, I'm finding that there is a very large number of bones that have no parent defined in this way.

Also, I'll have to look into it further, (won't have a chance until tomorrow morning at best) but my initial tests make it appear as if the lower half of the body (say, pelvis and down) is not only a separate hierarchy than the upper part, but they look like their axes are completely different than the upper part >_<;;  Like I said, I'll be looking into that again soon here.

What method did you use to construct your hierarchy for Gundam?

Yes, I'm aware of the vert-info (I call it VertexDescriptor) struct-- this is mine:

```
    uint StreamDescriptorCount;
    uint Unknown1;
    uint Unknown2;
    uint Offset;
    StreamDescriptorStruct StreamDescriptors[StreamDescriptorCount];
} VertexDescriptorStruct;
typedef struct {
    uint Unknown1;
    uint Offset;
    uint DataType;
    uint Semantic;
    uint Index;
} StreamDescriptorStruct;
```

I'm rather unsure of whether I should be using StreamDescriptorStruct.Semantic or StreamDescriptorStruct.DataType to determine what type the piece of data it's pointing to, but using either seems to give me the same results. In my example mesh, I've found that there's 2 "DataType" values that are as-yet undefined in my structure, 0x11 (4 bytes/vertex) and 0x1A (8 bytes/vertex).

Do you have any information about how I would parse these values into useable bone assignment/weights? I've tried a couple of the obvious things, such as straight up reading a byte and using that value as the bone index, but it seems to give incorrect bones. (For example, the vertices on the gauntlets of a character would then point at the "Spine" bone...)

Thoughts?
## Post #128
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-06-22T03:24:13+00:00
- Post Title: Re: Dark Souls FLV file

Okay guys, I've just got the bones loading in, as well as some sort of bounding boxes that accompany the bone information.
[](http://imageshack.us/photo/my-images/10/aovo.jpg/)

Some of this you can see in the screenshot:

There's a couple bones with strange parenting (maybe I'm not doing it right?), and there's got to be something I'm missing with a bunch of these bones, as there's 28 bones without a parent, all sitting down between his feet.
There's a couple that are named with some variation of "dummy", so I can't trust them to be correct, but there's a dozen that are named "<something>Nub", which I know to be a marker for the end of a bone chain, or something of the sort. This is further confirmed when I open the Havok skeleton with the havok tools, and I can see all the nubs in their correct locations.  So at the very least, I need to get those nubs in the right places.

But for the most part, I have the bones all loading correctly!
## Post #129
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-06-22T05:27:08+00:00
- Post Title: Re: Dark Souls FLV file

damn, you good, nyxo  
keep it up with a nice progress
cheers.
## Post #130
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2013-06-22T17:38:57+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> Okay guys, I've just got the bones loading in, as well as some sort of bounding boxes that accompany the bone information...[snip]...But for the most part, I have the bones all loading correctly!

Outstanding work!! Have you been looking at static mesh information as well?
## Post #131
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-06-22T17:55:30+00:00
- Post Title: Re: Dark Souls FLV file

What do you mean? Like props (barrels, crates, etc..) and map pieces?
## Post #132
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-06-23T01:47:00+00:00
- Post Title: Re: Dark Souls FLV file

Ok, I got bone weights in- I can pose meshes now!
[](http://imageshack.us/photo/my-images/24/zat7.jpg/)

Now I'm off to get animations in~ *meanders off*
## Post #133
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2013-06-25T00:34:52+00:00
- Post Title: Re: Dark Souls FLV file

Oh holy shit, my hype meter just exploded.
## Post #134
- Username: grenadier42
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 18, 2011 11:53 pm
- Post datetime: 2013-06-25T06:11:25+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from TehDave
>
> Oh holy shit, my hype meter just exploded.

No kidding. Fantastic work nyxo, can't wait to see the end result.
## Post #135
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2013-06-27T13:44:01+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> What do you mean? Like props (barrels, crates, etc..) and map pieces?

Yes, I was just curious about these things. Some of the static meshes are pretty nice. Either way this is amazing work so far,
## Post #136
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-06-27T22:34:37+00:00
- Post Title: Re: Dark Souls FLV file

Yeah, all the static meshes, and the map pieces are all in the same format.  So my app can load them all, as it stands right now.
## Post #137
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-06-29T05:01:58+00:00
- Post Title: Re: Dark Souls FLV file

Things are [moving](http://youtu.be/1ABkYeqzjkA) along nicely.
## Post #138
- Username: Mireneye
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 29, 2013 3:46 am
- Post datetime: 2013-06-29T06:16:08+00:00
- Post Title: Re: Dark Souls FLV file

When I saw your awesome progress I just had to get on these boards and congratulate you. (You and the joint effort of others on this thread just earned Xentax a 5, ^^)

Now, me coming from a 3d modelling background one thing I'm most curious about that I know by heart is not always possible because of other things getting in the way. Once you have sorted out the ins and outs of the format, are you far off being able to switch out meshes? like export a mesh from the archive, change it and then re-export it? 

Keep up the great work! This is super exciting for me ^^
## Post #139
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-06-29T17:19:59+00:00
- Post Title: Re: Dark Souls FLV file

That is the end goal, yes.  I've already posted a proof of concept in another thread: [viewtopic.php?f=10&t=10038](http://forum.xentax.com/viewtopic.php?f=10&t=10038) .  Although we're still a little ways off from automated repacking of the archives (and thus, being able to see our modified assets in-game), there's still progress being made in that direction.
## Post #140
- Username: Mireneye
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 29, 2013 3:46 am
- Post datetime: 2013-06-30T00:39:31+00:00
- Post Title: Re: Dark Souls FLV file

Very cool ^^ I will await patiently, if there is some mundane task I can help with.. do ask! I'm not well versed in programming and backwards engineering but I'm kind of good with thinking outside of boxes  

Thank you for your hard work and keep it up! 

^^
## Post #141
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-07-01T03:08:37+00:00
- Post Title: Re: Dark Souls FLV file

Here's an animation working for the Silver Knight:
[http://youtu.be/E_Mp_WJLGIE](http://youtu.be/E_Mp_WJLGIE)

Now that I have that working, I'm going to spend some time cleaning up some code that got dirty, and abstracting a bunch of it away so it's easier to extend in the future. I also have a whole stack of TODOs in my code that I'd like to take care of.

Then I have a few more unknowns to take a look at in the material definition files (.MTD), that probably tie into the FLVER files: It looks like there's support for detail diffuse, detail bump, and light maps, so I'd like to take a look and see what I can find in that respect.

I've technically mapped out 100% of the FLVER file now, but there's a bunch of that "mapped" area that's just marked down as unknown values, so I'd kinda like to explore that a little bit too.

Once I've kinda cleaned up all of that stuff, I'd like to look into these "NEO" files that vlad001 had mentioned previously in this thread-- I think those files may only exist in the Xbox360 version of the game, which is what he was using, as they don't appear to exist in my copy (PC), so I'll have to see what I can find regarding them.
## Post #142
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-01T03:13:38+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> Here's an animation working for the Silver Knight:
http://youtu.be/E_Mp_WJLGIE

Now that I have that working, I'm going to spend some time cleaning up some code that got dirty, and abstracting a bunch of it away so it's easier to extend in the future. I also have a whole stack of TODOs in my code that I'd like to take care of.

Then I have a few more unknowns to take a look at in the material definition files (.MTD), that probably tie into the FLVER files: It looks like there's support for detail diffuse, detail bump, and light maps, so I'd like to take a look and see what I can find in that respect.

I've technically mapped out 100% of the FLVER file now, but there's a bunch of that "mapped" area that's just marked down as unknown values, so I'd kinda like to explore that a little bit too.

Once I've kinda cleaned up all of that stuff, I'd like to look into these "NEO" files that vlad001 had mentioned previously in this thread-- I think those files may only exist in the Xbox360 version of the game, which is what he was using, as they don't appear to exist in my copy (PC), so I'll have to see what I can find regarding them.

Wow amazing, is this done in Noesis?
## Post #143
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-07-01T04:20:59+00:00
- Post Title: Re: Dark Souls FLV file

No, this is done in my own app. I'm not sure what the limitations of Noesis are, but at least a portion of this should be quite doable in Noesis. When I release my formats notes on the FLVER files, I'm sure somebody will update the existing Noesis script to work with whatever is possible ^^
## Post #144
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-01T04:48:54+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> No, this is done in my own app. I'm not sure what the limitations of Noesis are, but at least a portion of this should be quite doable in Noesis. When I release my formats notes on the FLVER files, I'm sure somebody will update the existing Noesis script to work with whatever is possible ^^

Ah I see, because I'm working on a Noesis script for a different game and am trying to parse bones and hopefully add animation support as well. Kinda stuck at the  moment, feel free to take a look in my topic. (Its in this section)

Amazing work btw, it looks really good. What language is it coded in? C#?
## Post #145
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-07-01T06:08:04+00:00
- Post Title: Re: Dark Souls FLV file

Does Noesis support bones and animations? I'm sorry, I'm not very familiar with the tool- I've only used it briefly.

With Dark Souls, the animations are stored in Havok .HKX files, which require a separate DLL to load (or manual parsing) - I'm not sure if Noesis provides a way to use an external DLL for anything...

My app is programmed partially in C++ and partially in C#. Although, I have a lot of supporting tools that I've written in a variety of other languages as well~
## Post #146
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-01T12:03:02+00:00
- Post Title: Re: Dark Souls FLV file

Noesis supports bones and animations. It would be trivial to load Havok files for a model, as it also allows native C++ plugin modules. There's already a native ODE implementation module that comes with it.
## Post #147
- Username: Mireneye
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 29, 2013 3:46 am
- Post datetime: 2013-07-03T09:38:30+00:00
- Post Title: Re: Dark Souls FLV file

Well I'm all for having a specific "souls" tool. Less confuing work for the end-user. There's a huge gap in accessability between what a programmer can do and what a 3d-modeler can do, me being the latter I have very little programming knowledge and I appriciate and encourage these great leaps in possebility and accesability. 

So thank you for your hard work! I hope you keep working on your own thing =)

But cheers for sharing information betweeen projects. It makes everything smoother.

(Just to make sure, I looked back at other posts, and certainly there's not a Noesis script as up to date as what you are working on now).

But as you said earlier.. Back to talking about deciphering data. 

Something really wicked just entered my mind. If you could get the Demon's Souls data packed, maybe Dark Souls engine could read it? IE, could get Demon's Soul's to run in the PC version? Huge maybe, concidering so many things have to be the same, scripts, audio etc, etc. Might need a pretty powerful converter and even then some of the programmed commands in the engine might not be the same. 

But hey.. one can dream, right? ^^
## Post #148
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2013-07-05T09:25:55+00:00
- Post Title: Re: Dark Souls FLV file

won't ever happen, mainly because Demon's Souls executable is compiled for the PS3's cell architecture, so it wouldn't run on an x86 system.

Best you can hope for is added support for the file version Demon's Souls uses so you can view and export the files just like Dark Souls files.

Although if he figures out how to repack the archive and have the game accept it, you could possibly mod Demon's Souls, repack it and then reburn the modded files to a BD so you can run a modded version of the game on a CFW'd PS3.

That's probably beyond what the author wants to do.

Speaking of exports, what formats will the finished product support for mesh export? PSK is pretty good for weighted meshes.
## Post #149
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-07-05T12:02:40+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from TehDave
>
> 
That's probably beyond what the author wants to do.
Actually, that's pretty much exactly what I've wanted to do right from the start (albeit, for Dark Souls, not Demon's Souls). I've already done this for a couple of games, and, assuming no debilitating roadblocks, Dark Souls will be no exception.

> Reply from TehDave
>
> 
Speaking of exports, what formats will the finished product support for mesh export? PSK is pretty good for weighted meshes.
Exports are very low on my priority list, if they're even on it in the first place. I gather Noesis can export, and since we'll have a script for that soon enough, there's no point in me reinventing that wheel. My primary interest with this project is to create a user friendly, visual tool to allow most anybody to make mods for Dark Souls.
## Post #150
- Username: Mireneye
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 29, 2013 3:46 am
- Post datetime: 2013-07-06T13:20:29+00:00
- Post Title: Re: Dark Souls FLV file

I'm confused.

All I'm saying is that if you can extract all the gamefiles and Dark Souls use the same gamefiles it MIGHT be possible to just insert scripts and everything and get Dark Souls engine to fire it up.

But that would like you say mean you have to figure out how to extract things from Demon's Souls. And yes, there is certainly the added difficulty of it being programmed for another system.

You guys know more then I do. I was just dreaming thinking if From Soft couldn't get Demon's Soul's to PC maybe "we" could. And hijacking Dark Souls engine (whatever it was named?) seemed like the easiest option. More so then building a separate engine that can read the Demon's Souls's file. 

I guess that this talk is borderline piracy sadly :/ But at least we 'can' talk about it.
## Post #151
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-07-07T03:07:23+00:00
- Post Title: Re: Dark Souls FLV file

Ok, I've got lightmaps working, you can check it out in [this video](http://www.youtube.com/watch?v=aBF3OAuZQ4E).
You can see that in the corners are some stationary yellow lights- those are the lightmaps. Near the middle of the room is a lightbulb icon moving in a circular pattern- that is a dynamic light I added for effect, it's not part of the FLVER file.

Every time I implement something new for rendering, it doubles the number of shaders that I have (currently at 24), so I'm starting now to understand why the game has hundreds and hundreds (thousands?) of shaders in the archives... >_>;;
## Post #152
- Username: Mireneye
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 29, 2013 3:46 am
- Post datetime: 2013-07-08T16:23:47+00:00
- Post Title: Re: Dark Souls FLV file

Amazing work! ^^ can't wait to play around with this. Keep it up!
## Post #153
- Username: Mireneye
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 29, 2013 3:46 am
- Post datetime: 2013-07-21T14:59:10+00:00
- Post Title: Re: Dark Souls FLV file

How's the progress?
## Post #154
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-07-24T00:14:22+00:00
- Post Title: Re: Dark Souls FLV file

So I've managed to parse the .MSB files for the most part now, which provides me with information about which map pieces are used where, as well as which enemies & props to position, and where.

Here's a [simple video](http://youtu.be/JYXrGED11cY) that shows the map piece loading in action.
## Post #155
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2013-07-24T10:04:35+00:00
- Post Title: Re: Dark Souls FLV file

That's actually really cool. Doesn't seem to load the water meshes though.
## Post #156
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-07-25T00:23:07+00:00
- Post Title: Re: Dark Souls FLV file

The water meshes are actually separate FLVERs. The order they files are loading in the video is just the order they appear in the .MSB files. At some point, it'd eventually get around to the water, I'd assume.
## Post #157
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2013-07-25T05:38:38+00:00
- Post Title: Re: Dark Souls FLV file

Any chance to skeletal and animations export for public?
## Post #158
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-07-25T06:09:05+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Skykila
>
> Any chance to skeletal and animations export for public?there will be no option to export any type of resources. 
only documented formats, as far as i recall.
## Post #159
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2013-07-25T08:34:00+00:00
- Post Title: Re: Dark Souls FLV file

With all the format documentation from this though it'd be pretty easy to write a script for Noesis to do all of that.
## Post #160
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-07-25T11:50:29+00:00
- Post Title: Re: Dark Souls FLV file

The skeletons, skeletal animations, and collision data are all stored in standard havok format (.HKX). The Havok Physics & Animation SDK is free to use, so technically all of this is already exported in a public format.
## Post #161
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2013-07-25T18:18:13+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> The skeletons, skeletal animations, and collision data are all stored in standard havok format (.HKX). The Havok Physics & Animation SDK is free to use, so technically all of this is already exported in a public format.
Thanks for info.
## Post #162
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2013-07-26T08:49:41+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> The skeletons, skeletal animations, and collision data are all stored in standard havok format (.HKX). The Havok Physics & Animation SDK is free to use, so technically all of this is already exported in a public format.
I meant getting the actual meshes with weights, uvs, and all that.
## Post #163
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2013-07-28T06:37:39+00:00
- Post Title: Re: Dark Souls FLV file

Hey can anyone send me the 3d model of Solaire? I want to 3d print his armor for 2013 October Comic-con.
## Post #164
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-07-31T04:50:58+00:00
- Post Title: Re: Dark Souls FLV file

My app can load a lot more stuff now - check out [this video](http://youtu.be/2Q2uY3je7xg) to see some of it in action. Note that some of the stuff you see in the video isn't how it appears in-game. This is because I have placeholder stuff there while I figure out the rest of the data-- it's all described in the video description.

I'm getting close to having all the info I want in some of my templates, so once I have that all in order, I'd like to post those for the community. My template list is getting quite large now:

FLVER (95%)
BDT (100%)
BHD (100%)
BHD5 (100%)
BND (99%)
HKX (60%) - this is temporary as it may not be needed in the future
FFX (3%)
MSB (80%)
MTD (87%)
TAE (84%)
TPF (100%)

I might also take a look at the Noesis plugin to update it, but no promises there.

Here's a rundown on the files, and what they're used for:
FLVER: Mesh, Binding Pose, LODs, and references to material definitions & textures
BDT: Archive data. Just a bunch of data stuck together without any information about how to read it- that info is in one of the header files, below. However for any given "file" of data within the archive, if it's compressed, the compression header info is in this file.
BHD: Archive header with filenames. Contains offsets, sizes, file names, etc.. about the files that are in the associated BDT file
BHD5: Archive header without filenames. Contains offsets, sizes, filename hashes, etc.. about the files that are in the associated BDT file
BND: Single file archive. Contains all the header information as well as data for a group of same-file-type files.
HKX: Havok binary file. May contain any combination of a huge variety of data - sometimes skeleton data, sometimes collision meshes, sometimes animation data.
FFX: Particle effect file. Defines everything about rendering one specific instance of a particle effect. As far as I can tell, the only "configurable" value for a particle effect is it's position and rotation on the map.
MSB: Map Studio Binary. It's like the "glue" for a map. Contains all the info required to put all the proper map piece, entity, and object FLVERs together to create a specific zone of the world.
MTD: Material Type Definition. Contains a variety of constant values to be passed to a shader for rendering, and a few configurable values to be passed on - these always appear to be textures, and are passed in by the FLVER.
TAE: Animation set file. Contains a variety of information pertaining to animations, their IDs (for referencing externally), etc..
TPF: Texture Package Format. Contains a group of textures that always need to be loaded together.

There's other filetypes I know about, and what they're for, but they're not on my template list, so it's not convenient for me to write about them right now.
## Post #165
- Username: Mireneye
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 29, 2013 3:46 am
- Post datetime: 2013-08-05T09:21:20+00:00
- Post Title: Re: Dark Souls FLV file

Wish I had anything more than "Claps!!!, amazing progress!"
## Post #166
- Username: XiNAVRO
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 23, 2010 1:39 am
- Post datetime: 2013-08-10T02:02:54+00:00
- Post Title: Re: Dark Souls FLV file

Fantastic work. Now, if the bone weighting / skeleton works with Noesis (or your custom application I gather?) then it would be much easier to use them for other stuff.
i.e. Garry's Mod, XNALara, Skyrim mods, etc...
## Post #167
- Username: Mireneye
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 29, 2013 3:46 am
- Post datetime: 2013-09-15T20:03:15+00:00
- Post Title: Re: Dark Souls FLV file

Sorry to bother but... no news of this?
## Post #168
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-09-19T00:38:43+00:00
- Post Title: Re: Dark Souls FLV file

I've updated my signature to have a link to my twitter feed- that is where you can see more frequent updates on DSMODT, my Dark Souls Mod Tool. I'll still post here with major updates, but I don't want to hijack this thread- the topic should still remain about the file formats.

Alas, I realize that I haven't been posting much information about any file formats as of late, but that will come with time. My templates are in a constant state of flux, generally speaking. I'm not a big fan of having to frequently amend old documents, so I'd like to submit them in as finished a state as I can, so when they get to that point (or close enough) I'll be posting them for all to see. At the rate I've been going, I'm going to end up parsing ALL of the files used by the game. Most frequently, I've added the font files to my list of semi-parsed file formats.

Edit: Theoretically, with my templates that I eventually release, somebody could use them to modify the existing Noesis plugin to support bones/etc.
## Post #169
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2013-10-01T12:53:30+00:00
- Post Title: Re: Dark Souls FLV file

When i Use Rick's unpacker all i get are a bunch of unknowns

```
"C:\Program Files (x86)\NAMCO BANDAI Games\DarkSouls\Tools\New folder\Gibbed.DarkSouls.Unpack\bin\Release\Gibbed.DarkSouls.Unpack.exe" -v dvdbnd0.bdt dvdbnd0
pause

```


When i use any other command i get

> Warning: no active project loaded.?
## Post #170
- Username: whiteraven
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 17, 2012 4:20 am
- Post datetime: 2013-10-24T18:29:01+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from JohnHudeski
>
> When i Use Rick's unpacker all i get are a bunch of unknowns
Code: Select all@echo off
"C:\Program Files (x86)\NAMCO BANDAI Games\DarkSouls\Tools\New folder\Gibbed.DarkSouls.Unpack\bin\Release\Gibbed.DarkSouls.Unpack.exe" -v dvdbnd0.bdt dvdbnd0
pause


When i use any other command i get
Warning: no active project loaded.?
 I am getting the same, thing he said to put the directories in the repo but i have no idea what that means
## Post #171
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-10-26T12:59:12+00:00
- Post Title: Re: Dark Souls FLV file

Copy/move bin\projects to to Gibbed.DarkSouls.Unpack\bin\Release\projects or build the solution in Debug rather than Release so you get all of the executables in bin\.
## Post #172
- Username: whiteraven
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 17, 2012 4:20 am
- Post datetime: 2013-10-29T15:49:09+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Rick
>
> Copy/move bin\projects to to Gibbed.DarkSouls.Unpack\bin\Release\projects or build the solution in Debug rather than Release so you get all of the executables in bin\.

Okay so i got it to work, heres what you have to do.
first Download all his tools here "[http://www.mediafire.com/?dxarranbataxrsa](http://www.mediafire.com/?dxarranbataxrsa)"
unzip them

goto "[http://svn.gib.me/public/darksouls/trunk/bin/](http://svn.gib.me/public/darksouls/trunk/bin/)"
and make a copy of everything there in a file called projects. MAKE SURE TO KEEP THE SAME FILESTRUCTURE.. and then run your batch file.
After that find the file you want to look at and tell windows to open with the unbind.exe and that will create a file uncompressed
## Post #173
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-12-28T22:04:34+00:00
- Post Title: Re: Dark Souls FLV file

So I've developed this tool to help me with my development of DSMODT, and have been using it privately for a very long time now, but it seems to me that there's potential it can be quite useful to the general public as well. I've called it DSExplore, and the purpose of it is to provide a user-friendly means thru which to extract files from Dark Souls.

No command line, just double click the icon (you'll need to download/install the .NET 4.0 framework, if you don't have it already, to use it). Then select File | Open and browse to any Dark Souls archive or alternatively drag & drop a file from windows explorer onto the window.

Either select the file you want to extract (hold Ctrl to select multiple files), right click on one of them and select "Extract"; or click the "Extract All" button. Select a location to store the files, and let the program do the rest.

This works with *.BDT/*.BHD5, *.BDT/*.BHD, *.*BND, and *.TPF files.

Since this is a pre-release copy of the program, it's being provided "as-is", with no guarantee about it's ability to work in any way whatsoever, however at a later point, I hope to have it more polished up to make a more official and supported release.

[Download here](https://app.box.com/s/zv2cvd8q26afc59patf5)
## Post #174
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2014-01-13T15:21:09+00:00
- Post Title: Re: Dark Souls FLV file

Thanks nyxo, DSExplore works great! I'm looking forward to the release of DSMODT.  

In the meantime, I figured out a lame [workaround](http://forum.xentax.com/viewtopic.php?f=10&t=7852&hilit=dark+souls&start=30) for the textures since I couldn't get chrrox's script to run, but I have an issue:

Does anyone know if there is a way to look at different UV channels in Noesis?  I think that the UV channel that gets loaded with the current version of the Dark Souls flver plugin for Noesis is possibly the light map channel.
## Post #175
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2014-01-19T18:52:32+00:00
- Post Title: Re: Dark Souls FLV file

Thanks nyxo, any kind of 3ds max importer possible?
## Post #176
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-01-27T05:42:55+00:00
- Post Title: Re: Dark Souls FLV file

DSExplore is intended only to "explore" (hence the name) the Dark Souls archives, not to allow importing.
I'm working on cleaning up the DSMODT code so I can make a "viewer only" release of it, and then I'll continue my work of implementing the ability to save out custom Dark Souls Archives (it's partially complete, but I thought a "viewer" release would be appreciated while I finish that off...)
## Post #177
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2014-01-27T12:23:50+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> DSExplore is intended only to "explore" (hence the name) the Dark Souls archives, not to allow importing.
I'm working on cleaning up the DSMODT code so I can make a "viewer only" release of it, and then I'll continue my work of implementing the ability to save out custom Dark Souls Archives (it's partially complete, but I thought a "viewer" release would be appreciated while I finish that off...)

Good news. Will the "viewer only" release include the ability to export meshes with UV (to obj)?
## Post #178
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-01-27T14:18:26+00:00
- Post Title: Re: Dark Souls FLV file

No, it will act only only as a means to view the contents within the tool itself. I'm still working on making all of the data "savable", so anything that involves writing the data back out to your hard drive in any way will be a future release.
## Post #179
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2014-01-28T13:06:03+00:00
- Post Title: Re: Dark Souls FLV file

Eagerly waitin on the savable part nyxo
## Post #180
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-03-02T09:45:29+00:00
- Post Title: Re: Dark Souls FLV file

My stupid brain finally found a way to use Skyrim's animation modification system to extract and convert Dark souls animations

I needed to include the character's skeleton per animation package

> hkxcmd exportkf "Skeleton.hkx" "a00" "a00_out"
## Post #181
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2014-03-07T14:10:45+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from JohnHudeski
>
> My stupid brain finally found a way to use Skyrim's animation modification system to extract and convert Dark souls animations

I needed to include the character's skeleton per animation package

hkxcmd exportkf "Skeleton.hkx" "a00" "a00_out"
 how did you extract the skeleton and the animations from those anibnd files?
## Post #182
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-03-08T04:06:19+00:00
- Post Title: Re: Dark Souls FLV file

You can use the DSExplore tool I released earlier in this thread.
## Post #183
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2014-03-08T12:49:55+00:00
- Post Title: Re: Dark Souls FLV file

hey yeah thanks i did that and got some KF files, any reason why they dont load up into 3ds max? i got the KF/NIF plugin that is used to import skyrim stuff but it gives me "improper file format"
## Post #184
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-03-08T20:12:10+00:00
- Post Title: Re: Dark Souls FLV file

Because the plugin you're using is designed for Skyrim files. Merely having the same file extension doesn't mean the actual data in the file is compatible between games. (although it's sometimes true..)
## Post #185
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-04-01T03:27:38+00:00
- Post Title: Re: Dark Souls FLV file

I'm making my viewer only release of DSMODT available to the public now. >>[Download](https://dl.dropboxusercontent.com/u/38150185/DSMODT/DSMODT%20v0.2a.zip)<<
Enjoy!

||||| README |||||


DSMODT: Dark Souls MOD Tool
Version 0.2 "Viewer-only"


==Introduction==
This is the "viewer-only" release of my Dark Souls 2 MOD Tool, DSMODT. It is being provided "as-is" with no promise that it will work in any way whatsoever, for any purpose.
I am not currently providing support for this tool, however bug reports and realistic change/feature requestions are welcome, as I am continuing to work on it.


==Features==
View all meshes directly from your Dark Souls installation
* Maps
* Entities
* Objects
Meshes render with 95% similarity to the actual game
* Diffuse textures
* Bumpmaps (and detail bumpmaps)
* Specularity maps
* Lightmaps
* Colored vertices
* Bone weights/Animations
Maps
* All pieces are put together- on a rare occassion, this can cause some overlap, usually in areas where lower quality meshes were used when viewing a particular part of the map from a distance.
* Maps have icons marking the location of entities, objects, particle systems, audio sources, and a variety of other things.


==Known Issues==
The lighting isn't quite right
* I haven't quite figured out a really nice algorithm that properly balances lightmaps, ambient lighting, and dynamic lights while keeping relative brightness values similar to in-game. Sorry 

Low resolution textures and low LoDs (qualities) are showing in many areas of the maps.
* This is because DSMODT currently assumes that the first faceset for any given mesh is the highest LoD. This is correct more often than not.
* It is currently unknown how Dark Souls determines which faceset to use for which LoD, so all I can do at this time is pick one and go with it.

In Oolacile, there's a copy of the Kalameet battle area floating above the original
* I have no idea why this is there, but I manually looked at the file, and it actually does contain a copy there.

Maps don't show meshes for entities or objects
* This is technically possible, and it was working in an older version, but most maps would cause DSMODT to run out of memory and crash, so it was removed for now.


==History==
Verson 0.2
First release!
## Post #186
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2014-04-01T13:34:39+00:00
- Post Title: Re: Dark Souls FLV file

Great news nyxo, I have been looking forward to this for awhile!

I hestitate to run any programs on April 1st, but I went for it and when I tried running the program, I keep getting "Dark Souls install directory not found. Cannot continue." ...no matter which directory I choose. My install directory is:
C:\Program Files\NAMCO BANDAI Games\DarkSouls
## Post #187
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-04-01T22:57:56+00:00
- Post Title: Re: Dark Souls FLV file

DSMODT can give you that error in one of two ways:
1) You cancelled the dialog where you are supposed to select your install directory.
2) DSMODT looks for the following files in the directory you selected. If even one of them is missing, it will then append "/DATA/" to the directory you selected and try to find them again. If any one of them is missing again, it will give you that error.
    * dvdbnd0.bhd5
    * dvdbnd0.bdt
    * dvdbnd1.bhd5
    * dvdbnd1.bdt
    * dvdbnd2.bhd5
    * dvdbnd2.bdt
    * dvdbnd3.bhd5
    * dvdbnd3.bdt

Please check and make sure that you are selecting a directory that contains all of those files, or are selecting a directory that contains the "/DATA/" directory that contains all of those files.
Also, altho silly, please make sure you're not cancelling the dialog instead of accepting it.

If you are still having issues, please let me know and I can try to help further.

Also, as a side question: Is that directory the default directory it installed to, or did you choose a custom location?
## Post #188
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2014-04-02T20:58:52+00:00
- Post Title: Re: Dark Souls FLV file

Thanks for the reply Nyxo!  That directory was custom for me although if I remember correctly it is also the default location.

The reason for the failure was that I had these files in the install directory:
dvdbnd0.bhd5
dvdbnd0.bdt
dvdbnd1.bhd5
dvdbnd1.bdt
...but not dvdbnd2.bhd5, dvdbnd2.bdt, dvdbnd3.bhd5, and dvdbnd3.bdt because I had been monkeying around with the files earlier when trying to extract files. I put them back, now DSMODT works perfectly! Awesome job
## Post #189
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-04-03T04:16:24+00:00
- Post Title: Re: Dark Souls FLV file

I got a new PC and windows 8.1 has not been the stalwart of stability i had hoped for. That said i have been able to use your program a few times. Loading maps makes the system crawl and the controls are not fine enough to navigate  smoothly through the area (I blame my pc). But that said it is still an amazing reproduction. No bugs of note. Except it could not find my install folder. i had to manually do this each time. Maybe an external save file for last opened folder.

what is the goal of the program? To make a clone of the game?
## Post #190
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-04-03T04:55:19+00:00
- Post Title: Re: Dark Souls FLV file

Yes, it seems that it's not loading the previously saved directory, at least when you've manually selected one. I've reworked that section, but I'm not sure if it fixes that problem.

Where is your Dark Souls installation? Also, was it the default installation location, or did you select something else when you installed Dark Souls?

The current iteration is intended to act just as a means thru which to view the game's content. Ultimately, the intent is to provide moddability.
## Post #191
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-04-04T10:54:36+00:00
- Post Title: Re: Dark Souls FLV file

C:\Program Files (x86)\NAMCO BANDAI Games\DarkSouls

I want to add a new "null" weapon that does karate. I was wondering if you have attempted animation changes?
## Post #192
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-04-06T07:34:21+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> Because the plugin you're using is designed for Skyrim files. Merely having the same file extension doesn't mean the actual data in the file is compatible between games. (although it's sometimes true..)

That is equally strange cos all havok animations should be of similar structure. Is there any chance you would consider making a havok to unity animation converter since you are already doing it
## Post #193
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-04-06T15:58:56+00:00
- Post Title: Re: Dark Souls FLV file

No, Havok files won't all be in a similar structure, for 2 reasons:
1) There's different versions of Havok, which can have different versions of Havok files.
2) There's an option provided by Havok that allows users to store custom information in Havok files (in a custom format), and when that exists, Havok will fail to load the file unless you provide a proper "custom information loader" for it to use when loading the Havok file. (This is used by Dark Souls at least, and I wouldn't be surprised if Skyrim did the same)
## Post #194
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-04-07T20:00:24+00:00
- Post Title: Re: Dark Souls FLV file

Custom data means some of the data would be stripped.  There is a standardized way for the raw animation data to be saved or  you would not be able to use the assest in Havok's other supporting tools. EG Havok behaviour and content tools. Considering i am able to load skyrim, Dark souls and Pro Evolution soccer data with the same lines of code which are identical to the hkxcmd, as well as run them in the afore mentioned tools i see no reason why it would not work.

Bla.

PS: i just found out the files are version tagged and you need to be using the a version of the sdk newer or same as the file
## Post #195
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-04-07T23:08:04+00:00
- Post Title: Re: Dark Souls FLV file

Yes, there is a standardized way for animations to be stored, however you can't know if the havok (.hkx) file you're loading even HAS animation data in it. Havok files are somewhat generic (as they're just scene data) in what they contain, and can contain animations, skeletons, collision data, etc..  It can have any combination of any of them, and for each one of them, there's potential to have custom data embedded within them.

All of that said, the Dark Souls animation-specific .HKX files don't contain any custom data, so they load just fine in any of Havok's other content tools, as I'm sure you've tried and seen, but if you tried to load the collision-specific .HKX files for the maps, they have custom data, so even Havok's own content tools cannot load those files, because it has no concept of what that custom data is, and how it might affect the rest of the loading process.
## Post #196
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-04-08T08:13:10+00:00
- Post Title: Re: Dark Souls FLV file

And i am guessing this is implemented through the havok patches. PS may i use your dll?
## Post #197
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-04-08T22:56:11+00:00
- Post Title: Re: Dark Souls FLV file

That's not my permission to give, since my DLL is just Havok's DLL. Just grab the free version of Havok and use it.
## Post #198
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-04-09T03:51:36+00:00
- Post Title: Re: Dark Souls FLV file

I was having problems with it then all of a sudden mine worked.
## Post #199
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-04-13T01:39:19+00:00
- Post Title: Re: Dark Souls FLV file

So I just put out a new update to DSMODT. [Download!](http://bit.ly/1sTTwB4) Mostly internal improvements and more options available.  But now that that's out of the way, the next thing I'll be working on is cleaning up/making available my 010 Editor Templates. This is long overdue, so I wanna get this out there pretty ASAP.
## Post #200
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-04-13T06:38:04+00:00
- Post Title: Re: Dark Souls FLV file

As promised, I'm releasing my 010 Templates-- at least the ones that are somewhat useful. I have a couple of others that are composed entirely of "unknown" values, which won't help anybody with anything (myself included) until I do some more work on them.

>>[Download!](https://dl.dropboxusercontent.com/s/sefv56sjxetfmm7/Dark%20Souls%20Templates%20v1.zip)<<

These have been indispensable to me during the development of DSMODT~  ^-^

Included in the zip:
* BDT: Archive Data (Template also has a movable bookmark for a DCX [compressed] entry)
* BHD: Archive Header (Internal)
* BHD5: Archive Header (External)
* BND: Archive
* CCM: Font Definition
* DDS: PC Texture
* FLVER: Mesh
* MSB: Map Zone Layout
* MTD: Material Definition
* TAE: Animation Listing
* TPF: Texture Package
## Post #201
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-05-04T06:13:12+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> So I just put out a new update to DSMODT. Download! Mostly internal improvements and more options available.  But now that that's out of the way, the next thing I'll be working on is cleaning up/making available my 010 Editor Templates. This is long overdue, so I wanna get this out there pretty ASAP.

Im sorry but your tool V0.2c does not work for X360 version but your V0.1 does, i guess you made wrong step  here.. Can you please at least release soruce ?
## Post #202
- Username: tpcrew
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jan 08, 2012 7:36 pm
- Post datetime: 2014-05-06T17:03:45+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> So I just put out a new update to DSMODT. Download! Mostly internal improvements and more options available.  But now that that's out of the way, the next thing I'll be working on is cleaning up/making available my 010 Editor Templates. This is long overdue, so I wanna get this out there pretty ASAP.

Hi, 
Thanks for you Modtools, but...it Only works with Dark Souls 1 or 2 too?

Pd. how I can unpack DS 2 .bdt files?

Regards
## Post #203
- Username: Swennet
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 22, 2013 4:50 am
- Post datetime: 2014-05-08T16:45:25+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from tpcrew
>
> how I can unpack DS 2 .bdt files?

I would like to know this as well. Especially looking for the Audio files
## Post #204
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-06-04T13:51:36+00:00
- Post Title: Re: Dark Souls FLV file

I went reading through the last page of the thread regarding porting the animations into max, and it seems that it does actually work and produces usable kf files that would work in Oblivion/Skyrim/whatever once you imported into max and exported it out again via the niftools plugin. the problem is, there's no way to get the actual bones out of skeleton.hkx (hkxcmd won't turn it into a kf as it has no animation) and thus you will always end up with 'improper file format' trying to import the animation because you have no skeleton to bind the animation to. With Skyrim this is no issue, as there is a skeleton mesh file you can easily import, but Dark Souls simply uses another HKX file and therein lies the issue, there's no way to get those bones into Max as far as I know.
## Post #205
- Username: Negikun
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jul 10, 2011 7:09 pm
- Post datetime: 2014-06-10T00:11:14+00:00
- Post Title: Re: Dark Souls FLV file

Hello guys !

I am looking for some way to extract texture files from .bdt files of Dark Souls (1). Cause I found some pack with all armors and stuff but, there are no specular maps. (there [http://facepunch.com/showthread.php?t=1262653](http://facepunch.com/showthread.php?t=1262653))
So I would know how to get them by myself.

Which tool(s) do it need, and how do I need to use them to get some files readable by Neosis (I already know the next steps then) from the .bdt files?
## Post #206
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-06-21T08:09:03+00:00
- Post Title: Re: Dark Souls FLV file

I've mostly been ignoring this thread, because I didn't care about Demon's Souls/Dark Souls. But I decided to experience the horrible masochism myself a little while ago (just Demon's Souls, I'm not sure I'm ready to surrender more of my life to DS/DS2), so it re-caught my attention. nyxo, are you still planning to produce a Noesis plugin from your work? Or is anyone? I haven't looked at those 010 specs above yet, so no idea how complete the info is.

Also, you're the same guy that wrote those SotN zone specs, aren't you? I was just reading over those the other day and thinking about doing a Noesis SotN plugin.
## Post #207
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-06-21T08:25:52+00:00
- Post Title: Re: Dark Souls FLV file

I was writing maxscripts for Dark Soul 1/2 games, also Demon Souls. I have all set, but there's something weird with bone matrix there, it's in euler angles but they must be multiplied in some way (y*z*x) or smt. I didn't get right position for some skeleton's. Some of them looks right, but if skeleton have a lot of bones (extra bones like wings, tails) then skeleton appears to be broken.
## Post #208
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-06-28T02:29:24+00:00
- Post Title: Re: Dark Souls FLV file

@MrAdults
Hey- nice to see you've dipped your toe into the horrible masochism that is the Souls franchise!
I don't have any direct plans to release a Noesis plugin for Dark Souls, however some other folks here have already released something that covers the basics (vertex positions/indices, diffuse UVs..). It doesn't, however, contain anything fancy like bumpmaps, specular maps, colored vertices, bones, or animations (which require Havok, btw)
The 010 specs I released contain all the info you need to get Noesis doing what DSMODT does already. My local version of these files have since been updated, but only in minor ways, and the updated info don't provide anything that would be required for a Noesis plugin.

Yes, I'm the guy who wrote the SotN zone specs. The only problem I can see with writing a Noesis plugin for that game is that it's written for PSX, so is based around indexed-color graphics and coordinate-based video ram access. I had to write a custom shader that simulated the PSX video card in order to display maps in my SotN map viewing application.

@zaramot
In the comments of my 010 templates, I describe the order of multiplication to get the correct bone orientations:

> Vector3_Float EulerRadian;  //When generating a quaternion: y * z * x (order matters!)
This has given me, as far as I can tell, 100% accurate bone orientations. Check for yourself in DSMODT, which uses exactly that multiplication.
## Post #209
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-06-28T21:35:28+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> I don't have any direct plans to release a Noesis plugin for Dark Souls, however some other folks here have already released something that covers the basics (vertex positions/indices, diffuse UVs..). It doesn't, however, contain anything fancy like bumpmaps, specular maps, colored vertices, bones, or animations (which require Havok, btw)
I see. Well, Noesis shouldn't have trouble supporting any of those things, so I hope whoever is taking up that effort circles back on them. For animations, if you're working in Python land, you're probably going to want to just make a native plugin instead so you can link directly to whatever Havok SDK version you want, unless you want to just reverse engineer those formats too and completely remove the Havok dependency. Exporting should likewise not be a problem, if enough of the formats are charted out to allow it.

> Reply from nyxo
>
> Yes, I'm the guy who wrote the SotN zone specs. The only problem I can see with writing a Noesis plugin for that game is that it's written for PSX, so is based around indexed-color graphics and coordinate-based video ram access. I had to write a custom shader that simulated the PSX video card in order to display maps in my SotN map viewing application.
Very nice. I didn't have any trouble getting it into Noesis over the course of an afternoon. Noesis already supports import+export of all kinds of old paletted image data, and has a plethora of functions to help. Although if I were to have a modern go at SotN using the old data, I'd probably bake each room into uncompressed RGBA textures instead of eating the extra fragment cycles to do palette indexing, which will kill you on a lot of modern hardware/platforms. (not that you'll usually notice unless you try to do a lot of blending with the technique at really high resolutions, or you try it on hardware that cares about things like dependent texture reads and/or having to read out of memory uniforms in the fragment pipe) The texture memory usage is still pretty minimal even if you wanted to 4x filter it on bake, given SotN's room sizes and how many rooms are ever in memory concurrently, which makes it favorable on most hardware these days.

Noesis also has a partially-implemented R5900 CPU emulator, which is used for processing data for some PS2 games by running their own code. (especially handy when developers leave symbol names intact) This gives me cause to consider adding R3000 as well, although I feel like I'm probably just re-traveling a well-traveled road there. Sorry, this has nothing to do with DS, so I'll shut up about it. Probably never going to get around to it anyway, unless I find myself in early retirement.
## Post #210
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-07-03T02:52:15+00:00
- Post Title: Re: Dark Souls FLV file

Good news guys-- I've not only got all archive type (.*BND, .*BHD/.*BDT, .BHD5/.BDT) repacking working, but also .FLVER file rebuilding (within scope of the data we know) partially working as well. I'm in the process of finishing off the .FLVER rebuilding part right now, but I've already managed to make deliberate changes to meshes, skeletons, etc.. and have them show up in-game. Most of this happens with just a couple clicks in my local copy of DSMODT.

There's still a bunch of work I need to do before I can release it to the public, but I wanted to let you know that good things are coming! I'll post screenshots when I have something worth showing~
## Post #211
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-07-07T04:18:54+00:00
- Post Title: Re: Dark Souls FLV file

Some simple replacements that were [mostly] automated by my tool, DSMODT:
[](http://imgur.com/BlnR895)

Things that changed:
1) These are Silver Knights in the Depths. They still use the Hollows' AI, so they're pretty stupid, but they look/animate like Silver Knights. This is because I replaced all the graphics/animations for the Hollows with the Silver Knights', in the game's archives.
2) There are simple red lines scribbled onto the Silver Knights' capes/shoulders/chests. (You'll probably have to click the image to see the full version to see this) This is because I manually changed those textures and saved them into the game's archives.

Still a bunch of work to make this user-friendly. There's a bunch of hard-coded stuff I need to fix up, but it's coming along nicely-- DSMODT will actually take whatever mesh/textures you currently see in it, and save it out to Dark Souls' format, so I just need to provide a way for the user to replace the meshes/textures they see, which should be simple(ish).
## Post #212
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-07-09T06:04:35+00:00
- Post Title: Re: Dark Souls FLV file

Wonder if it'll ever be feasible to add completely new worldspaces to the game. New levels and that sort of thing.

The model replacement is nice though, I imagine Nexus will be filled to the brim with nude models though.
## Post #213
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-07-09T12:59:02+00:00
- Post Title: Re: Dark Souls FLV file

ATM, I don't see why replacing an existing zone completely can't be done, however the possibility of completely adding a new zone (and, say, modifying an existing one, to make an entrance..) is unknown at this time.
## Post #214
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2014-07-15T23:41:54+00:00
- Post Title: Re: Dark Souls FLV file

does anybody know where i could locate pricilla in the files?

ive extracted all of the files.
## Post #215
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-07-23T23:53:24+00:00
- Post Title: Re: Dark Souls FLV file

I've got my local copy of DSMODT working for repacking files, with custom mesh support. At this time, I have no means to import custom meshes, so all I can do is load in an existing Dark Souls mesh and then save it out as a "custom mesh". So while it doesn't -look- custom, with what the code does, it is custom, I assure you!

[Youtube video of Proof-of-Concept Dark Souls modding](https://www.youtube.com/watch?v=Q8FsI5thLl4)

I still have much work to do before I make it public, but everything is coming along nicely~
## Post #216
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2014-07-29T09:39:52+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from nyxo
>
> I've got my local copy of DSMODT working for repacking files, with custom mesh support. At this time, I have no means to import custom meshes, so all I can do is load in an existing Dark Souls mesh and then save it out as a "custom mesh". So while it doesn't -look- custom, with what the code does, it is custom, I assure you!

Youtube video of Proof-of-Concept Dark Souls modding

I still have much work to do before I make it public, but everything is coming along nicely~

sorry but I think I can add external models from the game? I can do that is to create new weapons or replaces the old model with a new one?
## Post #217
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-08-04T05:24:10+00:00
- Post Title: Re: Dark Souls FLV file

The video shows that that is possible with my private copy of DSMODT, yes.
The public version cannot do any of that yet.
## Post #218
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-08-29T04:43:06+00:00
- Post Title: Re: Dark Souls FLV file

Not sure if you guys saw, but I put Diablo3's Skeleton King into Dark Souls the other day- it even made it on to Kotaku: [http://kotaku.com/bonkers-mod-puts-diab ... 1626994309](http://kotaku.com/bonkers-mod-puts-diablos-skeleton-king-in-dark-souls-1626994309)

That said, I'm currently polishing up DSMODT and making it a much nicer user experience, but I'm hoping to release it to the public soon with custom mesh capabilities.
## Post #219
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-08-29T05:38:48+00:00
- Post Title: Re: Dark Souls FLV file

Great stuff! Keep up the good work!   

Looking forward to your release here.
## Post #220
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-08-29T08:55:46+00:00
- Post Title: Re: Dark Souls FLV file

Oh god, that's cool as hell.

So the tools can spit out a mesh/skeleton for you to edit now?
## Post #221
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-08-29T20:40:05+00:00
- Post Title: Re: Dark Souls FLV file

At the moment, there's no support for editing skeletons, as that gets into Havok territory. And as we all know, being able to -read- a file format is definitely very different than being able to -write- that same file format.

Once I have Havok under control tho, there will be almost nothing we can't mod in Dark Souls.
## Post #222
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-08-30T00:53:58+00:00
- Post Title: Re: Dark Souls FLV file

I meant when you export model to edit, does it also give you the skeleton so you have something to weight to?
## Post #223
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-08-30T01:09:13+00:00
- Post Title: Re: Dark Souls FLV file

Technically there's no exporting of the meshes at this time. DSMODT currently only supports importing meshes, not exporting them.
## Post #224
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-08-30T02:24:53+00:00
- Post Title: Re: Dark Souls FLV file

So wait, how did you weight Leoric to Artorias' skeleton then?
## Post #225
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2014-08-30T04:09:27+00:00
- Post Title: Re: Dark Souls FLV file

DSMODT has a rudimentary bone-mapper in it. So long as you provide a mesh that's weighted to a skeleton with bone names that match those on the skeleton of the enemy it's being applied to, the bone weights transfer over.

So all I did is wrote a program that took the Skeleton King file and "rebuilt" portions of it to fit on Artorias, such as changing bone names, deleting some bones, adding others, and appropriately moving around bone weights as required with those changes; and then saved it as a collada (.DAE) file to be imported into DSMODT.
## Post #226
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-08-31T01:36:01+00:00
- Post Title: Re: Dark Souls FLV file

Oh okay. would be cool to eventually get support for exporting an actual skeleton or model and then importing back into the game though.
## Post #227
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2014-11-17T05:26:58+00:00
- Post Title: Re: Dark Souls FLV file

Okay, simple question I haven't found the answer to thus far. How does one export the models of the enemies WITH UV's? The Noesis script outputs the OBJ's pretty much perfectly save for a few that just cough up errors upon loading. Specifically I've managed to get Pinwheel extracted as well as Gwyn, but neither have UV's. I'd like to have them for good reference and renders. I don't need bones or animations, just the UV's. I've got the textures extracted properly as well...so can anyone help?

Basically, I want to convert the models without bones or animations and just the basic mesh and textures applied. How do I do this?
## Post #228
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-11-19T11:21:02+00:00
- Post Title: Re: Dark Souls FLV file

It should export with UVs, as it will display the textures correctly if they are present in the same folder as the model.
## Post #229
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2014-11-20T20:43:15+00:00
- Post Title: Re: Dark Souls FLV file

Really? I can't seem to make it work. The textures never show on the model in Noesis and I can't figure out what extension they need to be after extracting them properly. They end up as DDS files and they're able to be viewed with a standard image editor with that capability. Can someone inform me on how to get the textures to show and export correctly in Noesis? Am I using an outdated script?

Or do you mean the 010 templates? Unfortunately I have no idea how to export OBJ's with them after I run the templates on flver files...I really need some help.
## Post #230
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2015-01-16T19:34:03+00:00
- Post Title: Re: Dark Souls FLV file

Okay...been a while. I hate to double post but I've gotten absolutely nowhere with any means of extraction when it comes to having UV's for the models. I can get the models themselves, and textures, but no such luck with applying them together. Could someone PLEASE educate me on how to do so? If you want to keep it a secret though, this whole issue for me would be simple as giving me the model of Gwyn, Lord of Cinder, via PM or something...
## Post #231
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2015-02-03T16:58:52+00:00
- Post Title: Re: Dark Souls FLV file

This isn't a conspiracy to keep anything secret^^
It's more an issue of people having the time to go in-depth with explanations that have, to my knowledge, been mostly done already, or to do the actual extracting that you're requesting.

Also, since I'm here and posting, an update on DSMODT:
I'm hoping within the next couple months to do the next release. Some highlights of what's been added (this is not even close to an exhaustive list):
* Viewing of characters composed of "parts" (this includes the player character, and most NPCs) - this allows you to "dress up" an avatar to see what it'd look like wearing certain armour pieces, without having to get them in-game.
* Really basic editing functionality. This is deliberately being restricted to simple things so that I can focus my bug fixing efforts on the basics before I expose more functionality and complicate matters. I'm going to want a couple of serious beta testers for this feature before I make this release. However I don't need them right -now-. I'll likely put out the call on twitter, but I might come here and post as well~
* Automatic loading of in-game names for much of the content.

Once I have all of the viewing features in, I'm hoping to make much more frequent releases as I iterate on the editing functionality based on community feedback and my own testing. On that note, once this release is out, almost all of the viewing features I want will be implemented, however I'm considering audio.

On a similar note, once I've gotten all of the viewing features I want in, I'll probably put together another package of 010 Editor Templates, as many of the templates have been updated, and there are a few new ones as well.
## Post #232
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2015-02-05T09:35:10+00:00
- Post Title: Re: Dark Souls FLV file

Looking forward to it! Model replacements should be fun to mess with, I hope it's as user friendly as binding a custom mesh to whatever skeleton in a 3D modelling program, and then inserting it into the game. Porting Demon's Souls stuff to Dark Souls should be great fun.
## Post #233
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2015-02-15T17:31:49+00:00
- Post Title: Re: Dark Souls FLV file

Yeah, I'm hoping to make it as user-friendly as possible.
## Post #234
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-07-06T22:12:02+00:00
- Post Title: Re: Dark Souls FLV file

I have a question for zaramot. you happen to have a script similar to that for demons souls but that does not create the error with the skeleton? I managed to find a way to have animations.
## Post #235
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-07-07T19:59:35+00:00
- Post Title: Re: Dark Souls FLV file

You mean script for Dark Souls 1 PC version? I've had for xbox-360, I guess PC version is the same except endianness. So, if you send me few PC files, then I can try to figure out something
## Post #236
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-07-07T23:12:14+00:00
- Post Title: Re: Dark Souls FLV file

perfect. I can send you all PC files you want if you are interested.
## Post #237
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-07-08T19:28:51+00:00
- Post Title: Re: Dark Souls FLV file

Sure, no need for all of them lol But few characters models and monsters would be great xD
## Post #238
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-07-10T05:47:23+00:00
- Post Title: Re: Dark Souls FLV file

here are all models of the game. I took them all because some can not I import them but I do not remember what! I hope you have help! [http://www.mediafire.com/download/r6xjl ... part+1.rar](http://www.mediafire.com/download/r6xjlk611mfzmcy/dark+souls+part+1.rar)
## Post #239
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-07-13T22:18:32+00:00
- Post Title: Re: Dark Souls FLV file

any news?
## Post #240
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-07-16T18:37:44+00:00
- Post Title: Re: Dark Souls FLV file

I would not be insistent zaramot, but I need that script as soon as possible! and if I ask, have you solved the problems with the script of demons' soul? you managed to do in the way that the skeleton has errors?
## Post #241
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-07-16T19:08:41+00:00
- Post Title: Re: Dark Souls FLV file

Ah, that's sad, since I don't have time for that now. And by errors you mean wrong rotations of bones? If yes, then I didn't solve this issue yet for all models, some are fine some are not xD
## Post #242
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-07-16T21:29:02+00:00
- Post Title: Re: Dark Souls FLV file

if I can still ask for one thing, you may only download files? it took me a long time to load and I do not think it was useless .... [http://www.mediafire.com/download/r6xjl ... part+1.rar](http://www.mediafire.com/download/r6xjlk611mfzmcy/dark+souls+part+1.rar)
## Post #243
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-07-21T09:51:42+00:00
- Post Title: Re: Dark Souls FLV file

a question about dark souls 2, there is someone who is able to open their archives file version pc? I start to get some model!
## Post #244
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2015-07-21T20:00:45+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from zaramot
>
> Ah, that's sad, since I don't have time for that now. And by errors you mean wrong rotations of bones? If yes, then I didn't solve this issue yet for all models, some are fine some are not xD

Yeah, weights are still fine on most Demon's Souls models, but bones are out of position like Dragon God's wings. the bones are also named randomly based on what order the script process imports the bones in, so even if you import the same mesh into two different max files the bone names will be different, and as you can imagine this makes piecing together armor sets a hassle because you get overlapping bones due to the same bones in each mesh you import into the scene being named differently. 

So fixing those alone would be a massive improvement. Kind of wish I had the time and knowhow to do this sort of thing myself.
## Post #245
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-07-28T16:11:46+00:00
- Post Title: Re: Dark Souls FLV file

I found the map files of dark souls. I wish I could upload to 3d studio max. there is a way to do it?
## Post #246
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-08-04T13:03:15+00:00
- Post Title: Re: Dark Souls FLV file

zaramot would have time to devote to what I asked you?
## Post #247
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2015-09-03T05:49:26+00:00
- Post Title: Re: Dark Souls FLV file

It's taken me a really long time, but I finally got DSMODT to the point where it can be used by the general public.

Right now, it's deliberately restricted to editing weapon meshes/textures only, but this will be expanded upon now that the core framework is in place.

Download here: [https://dl.dropboxusercontent.com/u/381 ... T_v0.4.zip](https://dl.dropboxusercontent.com/u/38150185/DSMODT/DSMODT_v0.4.zip)
## Post #248
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-09-03T10:15:45+00:00
- Post Title: Re: Dark Souls FLV file

very interesting section cosplay but there are problems with the faces of the NPC. there is always basic and without eyes. can you solve it?
## Post #249
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2015-09-03T14:45:28+00:00
- Post Title: Re: Dark Souls FLV file

Fixing that would require integrating with FaceGen, the technology used to morph the face during character creation. That would be a very involved endeavour with very small take-away, so I have deliberately left that undone, however it _is_ on my TODO list as a lower priority item.
## Post #250
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-09-03T15:31:27+00:00
- Post Title: Re: Dark Souls FLV file

I understand .... I'm looking for the model from the flask but can not find it! you know what it's called in the data store? and plan to place in the future of the model information? for example the name on? I would make a list of weapons so they do not have to waste time in looking at them one by one
## Post #251
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2015-09-03T17:11:43+00:00
- Post Title: Re: Dark Souls FLV file

I've never thought about the flask, or where it's stored. Since it doesn't fall under any of the categories that DSMODT supports, I suppose it must be stored elsewhere. I've never looked~

In the future I plan to add more information about models, such as vertex count, bone information, etc..

What do you mean "make a list of weapons so they do not have to waste time in looking at them one by one"? DSMODT lists all weapons by their in-game names (if they have one), which should make them as easy as possible to find...
## Post #252
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-09-03T17:53:20+00:00
- Post Title: Re: Dark Souls FLV file

when I take a model of a weapon from the game, are written type WP_a_0100 etc ... and so I have to open them one by one to find the weapon that I want!
## Post #253
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2015-09-03T22:16:01+00:00
- Post Title: Re: Dark Souls FLV file

Where are you getting the WP_A_0100 value from, that you're trying to cross-reference it with the real name shown in DSMODT?
## Post #254
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-09-03T22:48:08+00:00
- Post Title: Re: Dark Souls FLV file

your program tells me the name they have in the game, but I want the name that the programming that.
## Post #255
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2015-09-04T01:05:07+00:00
- Post Title: Re: Dark Souls FLV file

And what I'm saying is that you shouldn't _need_ that. Hence why I'm asking where you're getting it from? There is very possibly another solution to this.
## Post #256
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-09-04T05:22:20+00:00
- Post Title: Re: Dark Souls FLV file

my intention is to do something like this:[https://docs.google.com/spreadsheets/d/ ... edit#gid=0](https://docs.google.com/spreadsheets/d/1AdlhpYFITAGnKVAIBMVverQ_E5m5xA19m0rG0Diyixs/edit#gid=0) 
but in their place on the weapons!
## Post #257
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2015-10-28T17:13:21+00:00
- Post Title: Re: Dark Souls FLV file

Hi!

NOESIS PLUGIN:
I'm uploading a v1.0 noesis plugin I made for dark souls flver models, seeing as no one seems to have shared one that handles uvs correctly on map flver's. I used nyxo's 010 templates (awesome guy), you can find his 010 templates on xentax, as well as his insanely cool DSMODT.

I'll be working on exporting boneweights etc from flver files, so I'll update once thats working.

You'll have to flip the normals on the models, as they're mirrored in x, I tried flipping normals to no avail (at least you won't have to mirror them, not perfect, but eh).

Batch exporting as fbx (no additional options) works great for me, scale should be good, if not, you can try changing the scale values in the .py

BOSS/MAP TEXTURE UNPACK:
Nasty .tpfbdt/.tpfhd and .chrtpfbdt/.chrtpfbhd files contain precious boss/map textures. I wrote a tool to 'unpack' them (thanks again nyxo), using the 010 templates. You should get a folder with tpf files.
You'll need to drag the xml files I provide over on the tpfbdt.exe/chrtpfbdt.exe (this works only if the xml files are in the same folder as the .tpfbdt/.tpfhd or .chrtpfbdt/.chrtpfbhd)

Example:
Extract chr/c4100.chrbnd.dcx (Artorias) with BinderTool.exe
Unbind with Gibbed.DarkSouls.Unbind.exe
Copy chr/c4100.chrtpfbdt and c4100.xml into this folder: "~\dvdbnd0_unpack\chr\c4100.chrbnd\c4100_unpack\FRPG\data\INTERROOT_win32\chr\c4100\"
Extract c4100.xml with chrtpfbdt.exe
In the same folder will now be .tpf.dcx files, extract with BinderTool.exe!
Unbind tpf's with Gibbed.DarkSouls.TextureConvert.exe
Rejoice!

Reminder: make sure to remove the old darksouls_flver.py from your noesis plugins

Download: [https://www.mediafire.com/?bdxbfh8jedt8byd](https://www.mediafire.com/?bdxbfh8jedt8byd)

Edit: wording


---------------------------------------------------- the above information is DEPRECATED ^
see https://github.com/Danilodum/dark_souls_hkx/releases
## Post #258
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-10-30T12:29:40+00:00
- Post Title: Re: Dark Souls FLV file

Snaz if you are interested to get the skeletons and skins original, I can go to the scritp 3d studio max importing models with skin and skeletons. Unfortunately, the author has no more interest on these scripts and then do not work well. I advise you to start with the script of demon's souls because that has fewer problems than others, for example, has the bone of his right arm inverted and vice versa, also because the models of demon souls are the same size of dark souls, except that a different version. But I do not understand what the problem with the mapping.It is a long time since I work and I have never had any problems, except if I used programs like ninja ripper. 

link:[http://www.mediafire.com/download/l7ccu ... dibe+2.rar](http://www.mediafire.com/download/l7ccum9ad7zmj59/script+dibe+2.rar)
## Post #259
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2015-10-31T19:47:01+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from dibe91
>
> Snaz if you are interested to get the skeletons and skins original, I can go to the scritp 3d studio max importing models with skin and skeletons. Unfortunately, the author has no more interest on these scripts and then do not work well. I advise you to start with the script of demon's souls because that has fewer problems than others, for example, has the bone of his right arm inverted and vice versa, also because the models of demon souls are the same size of dark souls, except that a different version. But I do not understand what the problem with the mapping.It is a long time since I work and I have never had any problems, except if I used programs like ninja ripper. 

link:http://www.mediafire.com/download/l7ccu ... dibe+2.rar

Thanks for letting me know I'll have a look!

It seems the bdt texture extractor didn't work too well, so here's a newer version tested on windows 7 and 10, see if that works.

Download: [https://www.dropbox.com/s/0o9af1yxi210u ... 1.zip?dl=0](https://www.dropbox.com/s/0o9af1yxi210ucc/bdtTextureExtractorv1.1.zip?dl=0)

Edit: updated link (again)


---------------------------------------------------- the above information is DEPRECATED ^
see https://github.com/Danilodum/dark_souls_hkx/releases
## Post #260
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2015-11-09T18:53:46+00:00
- Post Title: Re: Dark Souls FLV file

Hey a couple of questions:

Artorias' animations have a skeleton which contains 130 bones, while his flv contains information on 178 bones. There are bone indices referring to bones (in the flv) which are not in the animation skeleton. For artorias these are for example BD_A_9700 or LG_M_9700_A. These bones are being weighted to most of the model, like mesh12, which are his legs, are weighted to LG_M_9700_A, which sounds great, but the animation doesn't have this bone?? As a result his thigh, calf, toe etc bones are not weighted.

To my knowledge the flv is the only place where the weights are defined, I really don't get this.

Here's a link to a noesis plugin which (despite a type error you can ignore) properly reads in artorias' skeleton (as well as several others')

q1: Nyxo's flver 010 template states how converting the eulerradians on the bones to quat required a y*z*x order, which doesn't really work for me.. right now I'm using x*z*y, while also flipping the signs on y and z in quat(x,y,z,w). Anyone any clues why my method works some of the time? (I'm not really knowledgeable on quats..)

q2: What is the easiest way to mirror a skeleton that's in bone space in x (or on the yz plane)? *

q3: Anyone got any clues regarding those bone weights?

thanks!

Download: [https://www.dropbox.com/s/ws2su13f3hesg ... le.py?dl=0](https://www.dropbox.com/s/ws2su13f3hesggv/fmt_darksouls_flver_stable.py?dl=0)

* the following code accurately 'mirrors' the skeleton

```
mat = mat.swapHandedness()
```


---------------------------------------------------- the above information is DEPRECATED ^
see https://github.com/Danilodum/dark_souls_hkx/releases
## Post #261
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-11-10T06:27:50+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Snaz
>
> Hey a couple of questions:

Artorias' animations have a skeleton which contains 130 bones, while his flv contains information on 178 bones. There are bone indices referring to bones (in the flv) which are not in the animation skeleton. For artorias these are for example BD_A_9700 or LG_M_9700_A. These bones are being weighted to most of the model, like mesh12, which are his legs, are weighted to LG_M_9700_A, which sounds great, but the animation doesn't have this bone?? As a result his thigh, calf, toe etc bones are not weighted.

To my knowledge the flv is the only place where the weights are defined, I really don't get this.

Here's a link to a noesis plugin which (despite a type error you can ignore) properly reads in artorias' skeleton (as well as several others')

q1: Nyxo's flver 010 template states how converting the eulerradians on the bones to quat required a y*z*x order, which doesn't really work for me.. right now I'm using x*z*y, while also flipping the signs on y and z in quat(x,y,z,w). Anyone any clues why my method works some of the time? (I'm not really knowledgeable on quats..)

q2: What is the easiest way to mirror a skeleton that's in bone space in x (or on the yz plane)? *

q3: Anyone got any clues regarding those bone weights?

thanks!

Download: https://www.dropbox.com/s/ws2su13f3hesg ... le.py?dl=0

* the following code accurately 'mirrors' the skeleton
Code: Select allmat = mat.swapHandedness()

I can try your script? I want to see if it works
## Post #262
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2015-11-10T09:49:27+00:00
- Post Title: Re: Dark Souls FLV file

You can, but it doesn't. I have tried one of the maxscripts you linked, which almost worked, so I'll be looking at that
## Post #263
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-11-10T19:27:12+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Snaz
>
> You can, but it doesn't. I have tried one of the maxscripts you linked, which almost worked, so I'll be looking at that

I see. I would like to be the first to test your progress. I have to make the models for my friend and he needs as soon as possible !!!!
## Post #264
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-11-14T12:36:13+00:00
- Post Title: Re: Dark Souls FLV file

I have not seen a script for running the models, I decided to see one by one to make a list of the models.It took so long XP

> c1000=forrest grotesque
>
> c1010=Kobold
>
> c1020=Hollow Soldier
>
> c1021=Royal Soldier
>
> c1030=Hollow Infantry
>
> c1031=Infantry
>
> c1050=Amana Shrine Maiden
>
> c1060=Dark Cleric
>
> c1062=Dark Priestess
>
> c1070=Parasitized Undead
>
> c1080=Hollow Rouge
>
> c1130=Varangian Sailor
>
> c1150=Undead Traveler
>
> c1170=Stone Soldie
>
> c1180=Hollow Mage1
>
> c1182=Hollow Mage2
>
> c1210=gigant
>
> c1230=Suspicious Shadows
>
> c1240=Manikin
>
> c1250=Rupturing Hollow
>
> c1270=Abandoned Hollow
>
> c1271=Abandoned Hollow1
>
> c1290=Witchtree
>
> c1292=Witchtree2
>
> c1310=Lindelt Cleric
>
> c1320=skeleton
>
> c1330=skeleton2
>
> c1340=Gyrm
>
> c1350=Gyrm warrior
>
> c1370=Aldia Warlock
>
> c1380=Torturer
>
> c1390=Artificial Undead
>
> c1400=oniflex
>
> c1410=Undead Aberration
>
> c1460=Headless Vengarl
>
> c1470=?????
>
> c1480=undead peasan
>
> c1490=Undead Steelworker
>
> c1500=Stone Knight
>
> c1510=Ironclad Soldier
>
> c1520=royal soldier
>
> c1530=Syan Soldier
>
> c1540=The Skeleton Lords
>
> c1550=Lizard Man
>
> c1570=skeletons boos
>
> c2011=small pig
>
> c2020=big pig
>
> c2021=big pig 2
>
> c2030=Parasite Spider
>
> c2040=poison moth
>
> c2050=Poison Brumer 
>
> c2051=Poison Brumer1
>
> c2060=Cragslipper
>
> c2090=Swollen Mongrel
>
> c2100=Basilisk
>
> c2120=dragon
>
> c2130=cristal lizard
>
> c2131=cristal lizard2
>
> c2140=more big pig
>
> c2170=Dark Stalker
>
> c2200=big Poison Brumer 
>
> c2230=Mongrel Rat 
>
> c2240=Darksucker
>
> c2250=unknow
>
> c2260=Hunting Rat
>
> c2261=Hunting Rat1
>
> c2262=Hunting Rat2
>
> c2263=Hunting Rat3
>
> c2270=Stray Dog
>
> c2271=Stray Dog1
>
> c3000=ogre
>
> c3010=Heide Knight
>
> c3020=Gaoler
>
> c3033=Flexile Sentry
>
> c3040=nifanito
>
> c3050=Smelter Demon
>
> c3052=Smelter Demon2
>
> c3060=captain knight
>
> c3070=vergard body
>
> c3071=vergard
>
> c3080=Lion Clan Warrior
>
> c3081=Lion Clan Warrior1
>
> c3090=Giant Warrior
>
> c3096=The Last Giant
>
> c3097=Giant Lord
>
> c3110=Banedigger
>
> c3120=Grave Warden
>
> c3130=Hollow Falconer
>
> c3140=Hollow Primal Knight
>
> c3150=Primal Knight
>
> c3160=Desert Sorceress
>
> c3170=Dragon Acolyte
>
> c3180=The Pursuer
>
> c3190=alonne knight
>
> c3210=mimic
>
> c3240=Belfry Gargoyles
>
> c3250=Ruin Sentinels
>
> c3260=The Rotten
>
> c3270=dragon bones
>
> c3300=Old Knight 
>
> c3310=Drakekeeper
>
> c3330=Velstadt, The Royal Aegis
>
> c3340=Throne Defender
>
> c3370=Abandoned Hollow 
>
> c5000=Covetous Demon
>
> c5001=Covetous Demon1
>
> c5010=Mytha, the Baneful Queen
>
> c5020=Manscorpion Tark
>
> c5030=Scorpioness Najka
>
> c5040=Looking Glass Knight
>
> c5061=Darklurker1
>
> c5062=????
>
> c5065=Grave Warden Agdayne
>
> c5090=Leydia  
>
> c5110=Imperious Knight
>
> c5120=Leydia Witch
>
> c5146=hollow Vendrick
>
> c6000=Ancient Dragon
>
> c6010=Flame Lizard
>
> c6020=Rampart Hedgehog
>
> c6030=The Duke's Dear Freja
>
> c6070=Old Iron King
>
> c6080=Rotten Vermin
>
> c6110=Dragonrider
>
> c6115=Dragonrider1
>
> c6191=Executioner's Chariot
>
> c6250=Old Dragonslayer
>
> c6260=Lost Sinner
>
> c6270=Nashandra
>
> c6280=Royal Rat Authority
>
> c6500=Iron Warrior
>
> c6510=Fume Sorcerer
>
> c6530=Ashen Warrior
>
> c6540=Ashen Crawler
>
> c6560=Possessed Armor
>
> c6570=Barrel Carrier
>
> c6580=Retainer Rouge
>
> c6590=Rampart Golem 
>
> c6600=Crystal Golem
>
> c6610=Frozen Reindeer
>
> c6620=Rampart Hedgehog
>
> c6630=Rampart Spearman
>
> c6650=Sanctum Knight
>
> c6660=Sanctum soldier
>
> c6700=Sanctum Priestess
>
> c6710=Poison Statue Cluster
>
> c6711=Poison Statue Cluster1
>
> c6720=Corrosive Egg Crawlers
>
> c6740=creazy tree
>
> c6750=Fume Knight
>
> c6770=Retainer Sorceror
>
> c6780=Mastodon Halberd Archdrake
>
> c6790=tiger
>
> c6791=tiger1
>
> c6800=ser alonne
>
> c6810=Sinh, the Slumbering Dragon
>
> c6820=Elana, Squalid Queen
>
> c6830=The Imperfect
>
> c6840=Vendrick
>
> c6880=Loyce Knight
>
> c6890=Charred Loyce Knight
>
> c6900=Burnt Ivory King
>
> c7005=Shanalotte
>
> c7015=unknow
>
> c7036=Nashandra human
>
> c7045=Laddersmith Gilligan
>
> c7050=Strowen
>
> c7051=Morrel
>
> c7053=Griant
>
> c7055=Strowen1
>
> c7056=Griant
>
> c7058=Griant
>
> c7210=Chancellor Wellager
>
> c7230=Milibeth 
>
> c7240=Captain Drummond
>
> c7250=Darkdiver Grandahl
>
> c7300=phantom
>
> c7310=phantom1
>
> c7420=Creighton the Wanderer
>
> c7430=Benhart of Jugo
>
> c7440=Mild Mannered Pate
>
> c7600=milfanito
>
> c7601=milfanito1
>
> c7602=milfanito2
>
> c7620=Stone Trader Chloanne
>
> c7640=Blacksmith Lenigrast
>
> c7643=Steady Hand McDuff
>
> c7680=Straid of Olaphis
>
> c7690=Licia of Lindeldt
>
> c7700=Felkin the Outcast
>
> c7710=Royal Sorcerer Navlaan
>
> c7770=Sweet Shalquoir
>
> c7830=Titchy Gren
>
> c7850=Blue Sentinel Targray
>
> c8050=unknow
## Post #265
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2015-11-24T12:35:28+00:00
- Post Title: Re: Dark Souls FLV file

So for whoever wants it, I've got the original weights down thanks to nyxo's 010 templates (and his comments actually  ).

There are some issues with the rotations using the skeleton in the file, I've got this hackish way to make artorias look fine, but quadrupedal is completely off, and don't even think about opening Manus' file, here you go: [https://www.dropbox.com/s/hixzxvti7dbbc ... ED.py?dl=0](https://www.dropbox.com/s/hixzxvti7dbbce0/fmt_darksouls_flver_fileskel_SKINNED.py?dl=0)

Should you know why this is happening, I'd gladly hear it.

Then there is the other method which uses the skeleton from the animations, which loads in perfectly. See [https://facepunch.com/showthread.php?t= ... st49142853](https://facepunch.com/showthread.php?t=1262653&p=49142853&viewfull=1#post49142853) for more information. Download:
[https://www.dropbox.com/s/ecxcyqdzh8d8x ... ML.py?dl=0](https://www.dropbox.com/s/ecxcyqdzh8d8x8n/fmt_darksouls_flver_XML.py?dl=0)

---------------------------------------------------- the above information is DEPRECATED ^
see https://github.com/Danilodum/dark_souls_hkx/releases
## Post #266
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2015-12-03T18:45:22+00:00
- Post Title: Re: Dark Souls FLV file

So, it seems some folks are having issues with having to use a bunch of different tools to extract files for Dark Souls. I posted my tool, DSExplore, earlier in this thread, however I've got an experimental new version that not only fixes a bug or two, but also has limited support for rebuilding some of the archives. DSExplore will allow you to extract files from BHD5/BDT, BHD/BDT, *BND, and TPF files. It can also save modifications to all of those archive files. It has legacy support to read Dark Souls 2 BHD/BDT, *BND, and TPF files, however I'm not upkeeping that code and only leaving it in because there's no need to remove it yet. This is not a fully tested program, and is being released with a "It might not work and I don't care" clause -- if there's problems with it, there's a really high chance that I won't fix them in any hurry, if at all.

Basic usage:
Drag + Drop a supported archive file onto the window (while no other archive is open!) to open it.
* Drag + Drop a file onto the window (while an archive is open!) to add that file as an entry.
* Select an entry in the list to see editable fields for the entry at the bottom of the window.
** You can change these values to modify the selected entry.
** You can press the delete key on your keyboard to remove the selected entry.
* Select File -> Save to save the archive with your changes.

You can download it here: [DSExplore v0.1a](https://dl.dropboxusercontent.com/u/38150185/DSExplore/DSExplore_v0.1a.zip).

Also worth noting, I see somebody went thru some painful work trying to document a bunch of chr codes -- I recommend you check out this google doc that has been in work for a very long time now: [https://docs.google.com/spreadsheets/d/ ... 0rG0Diyixs](https://docs.google.com/spreadsheets/d/1AdlhpYFITAGnKVAIBMVverQ_E5m5xA19m0rG0Diyixs)
## Post #267
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2015-12-14T14:38:13+00:00
- Post Title: Re: Dark Souls FLV file

So I got the animations working on a model, and even though the path to retrieving a simple animation is really shitty, I still wanted to share it before I go about looking for a better way.

So here goes:
1. run 
```
hkxcmd convert *folder to .hkx* *(optional) destination folder*
```

2. run 
```
hkxcmd exportkf *path to model skeleton* *path to animations .hkx* *destination folder*
```

3. download [http://www.nexusmods.com/skyrim/mods/56 ... 5622&pUp=1](http://www.nexusmods.com/skyrim/mods/5622/?tab=2&navtag=http%3A%2F%2Fwww.nexusmods.com%2Fskyrim%2Fajax%2Fmodfiles%2F%3Fid%3D5622&pUp=1) 3ds max nif/kf importer (use the manual method of applying the plugin, not the installer, that didn't work for me).
4. use [https://www.dropbox.com/s/wcfjbs0m0qcqg ... im.py?dl=0](https://www.dropbox.com/s/wcfjbs0m0qcqguc/fmt_darksouls_flver_XML_for_anim.py?dl=0) this noesis plugin to export a model as fbx. The model will be non-flipped, in other words, mirrored.
5. import the fbx in max with (add) to scene.
7. import an animation (.kf file).
8. run [https://www.dropbox.com/s/6fzo2w8btxa46 ... dl.ms?dl=0](https://www.dropbox.com/s/6fzo2w8btxa466p/flipmdl.ms?dl=0) this script.

Getting the flipped model requires a different plugin, like [https://www.dropbox.com/s/ecxcyqdzh8d8x ... ML.py?dl=0](https://www.dropbox.com/s/ecxcyqdzh8d8x8n/fmt_darksouls_flver_XML.py?dl=0) this one.

Please see if this works for you.

Does anyone have any thoughts on how to obtain the havok sdk 2012.2? The download is down, and I'd actually like to create a noesis plugin instead of use this hacky (and cumbersome) way.

Edit: toying around a bit, I found that applying a corrected animation to a flipped model just messes everything up, while this doesn't happen when applying the animation to the non-flipped model (where artorias would (visually) have his sword in his left hand instead of his right).


---------------------------------------------------- the above information is DEPRECATED ^
see https://github.com/Danilodum/dark_souls_hkx/releases
## Post #268
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-12-15T11:05:09+00:00
- Post Title: Re: Dark Souls FLV file

Ideally, you wouldn't need to deal with flipping at all and could just embed the desired "handedness" in the FBX to convey to the scene renderer. I don't like the idea of modifying the data itself to compensate. Unfortunately, I'm not aware of any way to do this without modifying actual transforms and/or geo.

They took down the free Havok PC binaries? That's sad.
## Post #269
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2015-12-22T02:44:06+00:00
- Post Title: Re: Dark Souls FLV file

So I was wondering if anyone ever figured out a working method for Dark Souls 2: Scholar of the First Sin edition. I was able to use a program called BinderTool to unpack the BDT/BHD files, then use the same tool on the newly created BND files. The textures are fine, but the issue is that any importer for 3DS Max and Noesis plugin makes the model meshes look something like this:

Whereas DS1 models simply needed the Y-UV flipped, the entire mesh of the DS2:SotFS is screwed up. Does anyone know of a workaround? I've tried Rick's Gibbed tools but to no avail.
## Post #270
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-01-23T19:09:37+00:00
- Post Title: Re: Dark Souls FLV file

I hate to bump again, but I realized something about Scholar of the First Sin models: the original release of DS2 is 32-bit, while SotFS is 64-bit, so the models are written differently. Does anyone have experience in writing Maxscript? I've been using a DS2 maxscript I found but since it's for 32-bit it doesn't work properly on SotFS.

Any help is really appreciated!
## Post #271
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-02-29T04:53:45+00:00
- Post Title: Re: Dark Souls FLV file

Noesis plugin + hkx converter
[https://github.com/Danilodum/dark_souls_hkx/releases](https://github.com/Danilodum/dark_souls_hkx/releases)

correctly exports dark souls animations  

-- instructions in release notes
## Post #272
- Username: Alexstr525
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 22, 2016 7:06 am
- Post datetime: 2016-02-29T19:52:39+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Snaz
>
> Noesis plugin + hkx converter
https://github.com/Danilodum/dark_souls_hkx/releases

correctly exports dark souls animations  

-- instructions in release notes

I'm glad the SDK i sent worked perfectly!
## Post #273
- Username: Thiedent
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 04, 2016 7:50 pm
- Post datetime: 2016-03-05T01:03:10+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Snaz
>
> Noesis plugin + hkx converter
https://github.com/Danilodum/dark_souls_hkx/releases

correctly exports dark souls animations  

-- instructions in release notes

After following all of your instructions i have gotten up to the point where i have the artorias .flyver loaded in noesis with his skeleton and a folder with all of his converted .damnhavok animations and both the required skeleton-out. 

Both the dll and python plugins are in their respective plugin folders in noesis 4.77, but for some reason i can't get noesis to recognize the damnhavok files at all no matter if i drag and drop, open manually or open the flyver file with them in the same folder.

I am at a loss and would very much appreciate if you could please help me with this.
## Post #274
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-03-05T09:21:28+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Thiedent
>
> Snaz wrote:Noesis plugin + hkx converter
https://github.com/Danilodum/dark_souls_hkx/releases

correctly exports dark souls animations  

-- instructions in release notes

After following all of your instructions i have gotten up to the point where i have the artorias .flyver loaded in noesis with his skeleton and a folder with all of his converted .damnhavok animations and both the required skeleton-out. 

Both the dll and python plugins are in their respective plugin folders in noesis 4.77, but for some reason i can't get noesis to recognize the damnhavok files at all no matter if i drag and drop, open manually or open the flyver file with them in the same folder.

I am at a loss and would very much appreciate if you could please help me with this.

I updated the dll, it should work now. I can't really test it on another machine right now, but I'm confident this change will work. If you're able, please try it on windows 10.

Also, bear in mind that movement on the root bone is currently not being preserved, I'm working on it!
## Post #275
- Username: Thiedent
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 04, 2016 7:50 pm
- Post datetime: 2016-03-05T10:21:55+00:00
- Post Title: Re: Dark Souls FLV file

Just tested it and it's working perfectly now, thank you so much. This is such great work you've done i can't thank you enough for helping me to get it working.
## Post #276
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-03-05T12:05:00+00:00
- Post Title: Re: Dark Souls FLV file

Extraction of root motion on dark souls animations:

I updated the plugin dll at [https://github.com/Danilodum/dark_souls ... s/tag/v1.0](https://github.com/Danilodum/dark_souls_hkx/releases/tag/v1.0) .

Be sure to read the release notes again.

TL;DR
convert all the .hkx files to -out.hkx if you want root motion

Update: forgot about rotation, will be putting that in, first try didn't work tho
## Post #277
- Username: Glarkon
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Jul 28, 2015 6:36 am
- Post datetime: 2016-03-11T21:48:40+00:00
- Post Title: Re: Dark Souls FLV file

the texture extractor (chrtpfbdt.exe) displays an error whenever I drag an XML file on top of it. It worked in windows 8.1 but no longer works with windows 10

```
16
FILE LOADED
FILE LOADED
found name: ulong EntryCount
ENTRYCOUNT NUMBER IS: 9
found entries
NUMBER 0 is \c4500\c4500.tpf.dcx
found name: ulong Size1
found name: ulong Offset
NUMBER 1 is \c4500\c4500_s.tpf.dcx
found name: ulong Size1
found name: ulong Offset
NUMBER 2 is \c4500\c4500_n.tpf.dcx
found name: ulong Size1
found name: ulong Offset
NUMBER 3 is \c4500\c4500_Scroll.tpf.dcx
found name: ulong Size1
found name: ulong Offset
NUMBER 4 is \c4500\c4500_Scroll_s.tpf.dcx
found name: ulong Size1
found name: ulong Offset
NUMBER 5 is \c4500\c4500_Scroll_n.tpf.dcx
found name: ulong Size1
found name: ulong Offset
NUMBER 6 is \c4500\c4500_WP_A_0921.tpf.dcx
found name: ulong Size1
found name: ulong Offset
NUMBER 7 is \c4500\c4500_WP_A_0921_n.tpf.dcx
found name: ulong Size1
found name: ulong Offset
NUMBER 8 is \c4500\c4500_WP_A_0921_s.tpf.dcx
found name: ulong Size1
found name: ulong Offset
F.ENTRIES LENGTH IS EQUAL TO: 9
C:\Users\spong_000\Desktop\test\c4500.xml

Could not open specified file
```
## Post #278
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-03-11T22:22:21+00:00
- Post Title: Re: Dark Souls FLV file

Make sure you have the latest version [https://github.com/Danilodum/dark_souls ... orv1.1.zip](https://github.com/Danilodum/dark_souls_hkx/releases/download/v0.0/bdtTextureExtractorv1.1.zip)
## Post #279
- Username: Glarkon
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Jul 28, 2015 6:36 am
- Post datetime: 2016-03-12T03:49:48+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from Snaz
>
> Make sure you have the latest version https://github.com/Danilodum/dark_souls ... orv1.1.zip

I just used that one but it's still giving me that error
## Post #280
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-03-12T13:53:03+00:00
- Post Title: Re: Dark Souls FLV file

It's been developed and tested on windows 10... I'm sorry, it's working for me. What it does is read an xml version of chrtpfbhd and separate the files, nothing fancy. There's 010 templates in this thread that will let view the structure of the bhd header files and see in how many pieces the chrtpfbdt is divided, also not sure if dsexplore (also in this thread) can open this kind of file, but its very likely

Or find yourself another computer
## Post #281
- Username: illincrux
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 16, 2010 11:46 pm
- Post datetime: 2016-03-29T11:19:19+00:00
- Post Title: Re: Dark Souls FLV file

Does anyone know the name and location of the skeletons for the male and female player characters?
## Post #282
- Username: Jasper
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 11, 2016 12:30 pm
- Post datetime: 2016-05-11T04:38:20+00:00
- Post Title: Re: Dark Souls FLV file

I started working on my own web-based viewer for Dark Souls maps at [http://magcius.github.io/dunky.js/](http://magcius.github.io/dunky.js/) -- works best in Chrome right now. Giant thanks to nyxo for his 010 Templates, which my work was heavily based on.

I haven't implemented a lot of materials properly yet, which is why everything looks so flat.

However, I noticed that the game often has low-poly models overlapping the bigger ones. I was curious if anybody figured out what determines a low-poly model from the high-poly model. I imagine it has something to do with the Unknown fields in Parts, but I haven't seen a pattern to that. Either that, or the game has load/unload triggers with the Events/Points fields.

Has anybody figured anything with that out yet?
## Post #283
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-05-17T09:35:00+00:00
- Post Title: Re: Dark Souls FLV file

Is there nothing on that in the mtd files? (This file type is in the 010 templates as well). I believe it contains data on map lighting, npc placement, that kind of stuff. Also nyxo's done everything what you've done with dsmod as far as I can tell, regarding the map viewer - not to say you shouldn't carry on doing what you're doing! It looks really cool!
## Post #284
- Username: Jasper
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 11, 2016 12:30 pm
- Post datetime: 2016-05-17T16:00:02+00:00
- Post Title: Re: Dark Souls FLV file

.mtd isn't a file format? Are you thinking of .msb? The Parts as I was mentioning are part of the .msb file.

DSMODT doesn't seem to filter out low-poly models either. You can see the overlap of the three Sunbro Ledges for instance, which FROM forgot to line up properly: [http://i.imgur.com/5DsthkW.jpg](http://i.imgur.com/5DsthkW.jpg)
## Post #285
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-05-17T16:03:19+00:00
- Post Title: Re: Dark Souls FLV file

The low poly meshes are probably just landscape LOD to make the rendering easier for areas that are a certain distance away from the player (AKA too far to really see the details).
## Post #286
- Username: Jasper
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 11, 2016 12:30 pm
- Post datetime: 2016-05-17T16:09:02+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from HunterAP
>
> The low poly meshes are probably just landscape LOD to make the rendering easier for areas that are a certain distance away from the player (AKA too far to really see the details).

Yeah, that's what they're designed for, but I have no idea how the game engine determines that they are LOD models at all, or at what distance they should be shown. That's the bizarre thing I'm trying to work out. There are several unknown flags fields, however I've found both high-poly and low-poly models that have the same flags.

I think what it might be is that hitboxes toggle on and off certain parts, at which point it's super difficult to filter out "only the high-poly models"
## Post #287
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-05-17T16:55:05+00:00
- Post Title: Re: Dark Souls FLV file

mtd was off the top of my head haha, msb is indeed the file I was thinking of. I see. There must be some kind of way to discern the LOD meshes... Please share if you find a solution!
## Post #288
- Username: pl4sma
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Oct 19, 2013 9:24 pm
- Post datetime: 2016-06-17T15:45:16+00:00
- Post Title: Re: Dark Souls FLV file

@Snaz

Thanks a lot for your work, you rock !

Everything seems to work fine for me except one thing

I can see the flver in Noesis without problem:


I can see the animation of the Skeleton in Noesis also:


But I cannot seem to find a way to connect the 3d mesh to the animation skeleton
Is there a way to see the animation with the mesn in Noesis ?

Or a way to link the FBX animation exported to the FBX mesh exported. 
I feel I missed a skinning part no ?
## Post #289
- Username: pl4sma
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Oct 19, 2013 9:24 pm
- Post datetime: 2016-06-17T16:28:20+00:00
- Post Title: Re: Dark Souls FLV file

Haha, I searched during 10 hours before posting, and of course 2min after posting I find the way

Ok i had the wrong xml version of darksouls_hkx.dll in nesois, when i exported on Max, there was no bones
It's fixed now ! 

Thanks a lot again
## Post #290
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-06-17T19:54:45+00:00
- Post Title: Re: Dark Souls FLV file

Glad you got it working!
## Post #291
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-06-18T08:56:42+00:00
- Post Title: Re: Dark Souls FLV file

Snaz! you're alive then! how about working on models Dark Souls 2? XD
## Post #292
- Username: pl4sma
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Oct 19, 2013 9:24 pm
- Post datetime: 2016-06-18T18:15:54+00:00
- Post Title: Re: Dark Souls FLV file

@Snaz

I have a last little problem  Maybe you can help, i can't merge the 4 part of the armor and then apply the animation on it

Here is what I can do:
With your tools we can extract every piece of an Armor of Dark Souls
If we extract the right flver with the Skeleton-out in the directory and we import it in 3DS Max we see the Skeleton with the piece of armor, here the BP of 9570



If we add the animation to the BP, it works <-- good !


BUT is there a way to merge the 4 parts of the Armor in one file and then apply the animation ?

I am sure it's possible but I don't know how
DSMODT [http://www.rivernyxx.com/](http://www.rivernyxx.com/) does it when you click on COSPLAY
## Post #293
- Username: Glarkon
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Jul 28, 2015 6:36 am
- Post datetime: 2016-06-18T18:59:18+00:00
- Post Title: Re: Dark Souls FLV file

For some reason, the .anibnd.dcx file for c5200 can't be extracted using Gibbed.DarkSouls.Unbind.exe 
This tool works on almost every other anibnd.dcx file. 

Here's the .anibnd file: [https://www.dropbox.com/s/o172g37vzqyhm ... d.dcx?dl=0](https://www.dropbox.com/s/o172g37vzqyhm1v/c5200.anibnd.dcx?dl=0)

Here's the Gibbed.DarkSouls file (includes Gibbed.DarkSouls.Unbind.exe): [https://www.dropbox.com/s/u1cyks13l8v7n ... r.zip?dl=0](https://www.dropbox.com/s/u1cyks13l8v7nas/GibbedBinder.zip?dl=0)
## Post #294
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-06-18T19:31:31+00:00
- Post Title: Re: Dark Souls FLV file

nyxo's DSexplore opens all the files just fine. use that.

I don't know how that is done in 3ds max.
## Post #295
- Username: pl4sma
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Oct 19, 2013 9:24 pm
- Post datetime: 2016-06-20T21:54:45+00:00
- Post Title: Re: Dark Souls FLV file

Damn, thanks anyway Saz

If anybody knows how to merge the 4 part of an armor and then see the animation with the full armor i would love to know
## Post #296
- Username: Glarkon
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Jul 28, 2015 6:36 am
- Post datetime: 2016-06-21T23:19:04+00:00
- Post Title: Re: Dark Souls FLV file

Thanks for the help snaz. I've tried opening c0000.flver with the noesis script, but it displayed an error. Here's the file: 
[https://www.dropbox.com/s/vhdebflj8r84i ... flver?dl=0](https://www.dropbox.com/s/vhdebflj8r84izp/c0000.flver?dl=0)

This is the error displayed: 
Is there anyway to fix it?
## Post #297
- Username: newwwwbe
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jul 20, 2016 10:18 pm
- Post datetime: 2016-07-26T12:10:08+00:00
- Post Title: Re: Dark Souls FLV file

Hello, I have a problem such like [https://facepunch.com/showthread.php?t=1262653&page=31](https://facepunch.com/showthread.php?t=1262653&page=31)

Although I searched post in "Facepunch", I couldn't understand Snaz's reply
Is there anybody explain me more detail
## Post #298
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-26T13:29:14+00:00
- Post Title: Re: Dark Souls FLV file

Snaz suggested to check the scale in the flver py script and in 3dsmax.
Where's the point you can't follow?
## Post #299
- Username: newwwwbe
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jul 20, 2016 10:18 pm
- Post datetime: 2016-07-26T13:45:54+00:00
- Post Title: Re: Dark Souls FLV file

I don't know how to check the scale in the flver py script and in 3d max, I just put in proper folder
## Post #300
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-26T14:45:35+00:00
- Post Title: Re: Dark Souls FLV file

that's kinda funny - since you're working with all that stuff, Noesis, 3dsmax and so on.

Anyways:
here's the line in the flver python script for Noesis to deal with:
SCALE = 1000
## Post #301
- Username: newwwwbe
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jul 20, 2016 10:18 pm
- Post datetime: 2016-07-26T22:12:12+00:00
- Post Title: Re: Dark Souls FLV file

What a kindly, thanks
## Post #302
- Username: newwwwbe
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jul 20, 2016 10:18 pm
- Post datetime: 2016-07-27T12:50:29+00:00
- Post Title: Re: Dark Souls FLV file

Oh I have a problem about 


such dibe91's problem [https://facepunch.com/showthread.php?t=1262653&page=27](https://facepunch.com/showthread.php?t=1262653&page=27)


I follow the solution like hkxcmd.exe convert c4100.hkx Skeleton-out.hkx,
but working isn' t good like picture
So, what I miss ? and Is it editing fmt_darksouls_flver_XML_for_anim?
## Post #303
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-27T14:45:34+00:00
- Post Title: Re: Dark Souls FLV file

As from the posts as of November 25th 2015 on facepunch it looks as if the problem with the nubs was not solved.
You should ask Snaz or dib91 there to get answers.

What are the names of those nubs?
What happens if you ignore/delete them?

You should be more precise/detailed in your explanations.
("working isn' t good like picture" doesn't really help)
## Post #304
- Username: newwwwbe
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jul 20, 2016 10:18 pm
- Post datetime: 2016-07-27T23:12:59+00:00
- Post Title: Re: Dark Souls FLV file

OK, first, asked why is stand animation is fine but other animation is strange as in the view 
and I guess because of nubs or  python
 

Second many DS character have nubs looked bad on feet and
'silver knight' skeletone is bad


I found facepunch,  dib91 say " I tried to test your(Snuz) script "fmt_darksouls_flver_XML_for_anim.py". there are no more bones out of place" 
[https://facepunch.com/showthread.php?t=1262653&page=27](https://facepunch.com/showthread.php?t=1262653&page=27)
so, I tried to check py but I couldn't because I did't know where I check in py and my bad python skill
and I tried to follow like "hkxcmd.exe convert cXXXX.hkx Skeleton-out.hkx"
but It was still, not change
## Post #305
- Username: newwwwbe
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jul 20, 2016 10:18 pm
- Post datetime: 2016-07-27T23:30:24+00:00
- Post Title: Re: Dark Souls FLV file

AS you say, Here is nubs names:
## Post #306
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-07-28T00:07:41+00:00
- Post Title: Re: Dark Souls FLV file

You guys keep going on about some nubs, but as far as I know, they don't matter for the final animation. The skeleton in the .flver has nubs, yes, but the skeleton in the Skeleton.hkx file does not, which is the one used for animation.

Basically, if you end up with nubs data, you're working with an old, outdated version, which was part of my attempt to extract the skeleton from the .flver . As you can see, the black knight skeleton is wrong, kalameet, nito and several others will be wrong as well. Follow the thread, and you will find the answers, surely... I even updated some older posts, saying that the information and links they contain are outdated..

Anyway, using the newer methods as explained here: [https://github.com/Danilodum/dark_souls_hkx/releases](https://github.com/Danilodum/dark_souls_hkx/releases) will work. Please take a look if you haven't already. Primarily, replace the old .py script (delete the old one).
## Post #307
- Username: newwwwbe
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jul 20, 2016 10:18 pm
- Post datetime: 2016-07-28T00:59:08+00:00
- Post Title: Re: Dark Souls FLV file

I don't know what py give me matter, I really followed [https://github.com/Danilodum/dark_souls_hkx/releases](https://github.com/Danilodum/dark_souls_hkx/releases) and change new py
so I could play well animation in noesis and 3ds max 
but if I import both the mesh+skeleton and the animation to 3ds max , weapon is upside  down
perhaps you teach me what I  should delete  

or other way
## Post #308
- Username: newwwwbe
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jul 20, 2016 10:18 pm
- Post datetime: 2016-07-28T08:39:35+00:00
- Post Title: Re: Dark Souls FLV file

I'm sorry annoying, but please check the process what I missed

1. Use rick's tool to unpack, unbind  dvdbnd1 and cXXXXbnd
(some file didn't ex) c2260.anibnd  c5200.anibnd ~other anibnds)

2.Search skeleton.hkx in unbind anibnd, 

3.Use hkxcmd to convert skeleton,hkx to skeleton-out.hkx

3.5. Convert hkx file in hkxwin32 folder to .kf, but fbx + kf = fail


4.Use SSADF.exe to convert hkx file to damnhavoke, so they work good in noesis)

5.Thank to "shakotay2", I adjust scale 100 in fmt_darksouls_flver_fileskel_SKINNED because I don't know adjust damnhavokk
so I can't adjust scale 1000

6.Use noesis to convert .flver and .damnhavoke  to .fbx
(some flver file have even bad skeleton folded ex) c410, c2550~ etc)

6.5.To solve skeleton problem, I set hkxcmd and skeleton-out.hkx in cXXXX.flver side
 ,command "hkxcmd.exe convert cXXXX.hkx Skeleton-out.hkx",  open the cXXXX.flver in noesis
but it was still folded and sticked out = FAill

7.import both fbx file....work, but is not good
character hold weapon upside down and throw away the weapon

*py in noesis
## Post #309
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-07-28T14:23:43+00:00
- Post Title: Re: Dark Souls FLV file

All those files that start with "fmt_darksouls_flver" are not meant to be there. You should have just ONE. So:

1. In the folder 'noesis/plugins/python' -> Delete all the files that start with "fmt_darksouls_flver".
2. In the folder 'noesis/plugins -> Delete all the files that start with 'darksouls'.
3. see that you have ONE file here: 
. Here's a link to the correct file [https://github.com/Danilodum/dark_souls ... ls_hkx.dll](https://github.com/Danilodum/dark_souls_hkx/releases/download/v2.0/darkdouls_hkx.dll)
4. see that you have ONE file here: 
. Here's a link to the correct file [https://github.com/Danilodum/dark_souls ... th_root.py](https://github.com/Danilodum/dark_souls_hkx/releases/download/v2.0/fmt_darksouls_flver_XML_with_root.py)
5. convert Skeleton.hkx or cXXXX.hkx (which can sometime be found in the same folder as cXXXX.flver) to Skeleton-out.hkx.
6. Put Skeleton-out.hkx next to cXXXX.flver
7. Now you can open and export .flver files as fbx, and import that in your 3d program (3ds max for example).

For the animations to work:
8. Follow the steps here: [https://github.com/Danilodum/dark_souls ... s/tag/v1.0](https://github.com/Danilodum/dark_souls_hkx/releases/tag/v1.0) CAUTION! step 3 on that page says -> "copy the dll to your noesis plugins folder (where the other dll's are)". You have already done this in step 2 above.
9. when you now open noesis, you will be able to see .damnhavok files. These files can be opened, and you will see the animations.
10. export the animations as fbx. NOTE: you can do this 1 by 1. Noesis also has a batch process function that can be found in the menu -> tools -> batch process [1]
11. import the .flver fbx in 3d program (3ds max)
12. import a .damnhavok animation fbx in 3d program (3ds max). make sure you choose 'update animation' as import method.
13. play the animation, do whatever you want

[1] quick batch process guide:
1. navigate to a folder that contains .damnhavok files
2. go to tools -> batch process
3. set the input extension as damnhavok
4. set the output extension as fbx
5. press folder batch
6. press export
## Post #310
- Username: newwwwbe
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jul 20, 2016 10:18 pm
- Post datetime: 2016-07-28T22:39:32+00:00
- Post Title: Re: Dark Souls FLV file

It's work! thanks a lot 
god bless you
## Post #311
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-07-29T17:55:50+00:00
- Post Title: Re: Dark Souls FLV file

I have a question, how do you extract the files from the archive of dark souls? the binder tool can extract only the Dark Souls 2 and Dark Souls 3 archives!
## Post #312
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-07-30T06:41:33+00:00
- Post Title: Re: Dark Souls FLV file

I have a problem with the textures of the boss, I can not remove them! I always see this error:
## Post #313
- Username: Glarkon
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Jul 28, 2015 6:36 am
- Post datetime: 2016-07-30T22:13:10+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from dibe91
>
> I have a problem with the textures of the boss, I can not remove them! I always see this error:


the .xml and .chrtpfbdt need to be in the same folder as chrtpfbdt.exe.
## Post #314
- Username: newwwwbe
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jul 20, 2016 10:18 pm
- Post datetime: 2016-08-01T22:13:35+00:00
- Post Title: Re: Dark Souls FLV file

> Reply from dibe91
>
> I have a question, how do you extract the files from the archive of dark souls? the binder tool can extract only the Dark Souls 2 and Dark Souls 3 archives!
rick's tool = dark souls 1 binder tool (but some anibnd can't be unpack such like c2240.anibnd~etc)
## Post #315
- Username: zweihard
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 24, 2017 7:18 am
- Post datetime: 2017-03-23T23:20:46+00:00
- Post Title: Re: Dark Souls FLV file

Hey,

Is it possible to edit these animations and use them in Dark Souls?

Thanks in advance
## Post #316
- Username: BloatheadSorcerer
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Jan 16, 2015 5:10 am
- Post datetime: 2017-04-03T15:03:18+00:00
- Post Title: Re: Dark Souls FLV file

Can anyone please help me? I want to mirror the skeleton or model but all the dropbox links are dead.
## Post #317
- Username: lomiki
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 24, 2017 5:02 am
- Post datetime: 2017-05-24T23:23:15+00:00
- Post Title: Re: Dark Souls FLV file

Hello everyone! I want to export player animations, but i didn't get how to do it. I can export animations from mobs based on this method [https://github.com/Danilodum/dark_souls_hkx/releases](https://github.com/Danilodum/dark_souls_hkx/releases). But when i'm trying open player *.damnhavok in noesis (for example from c0000_a00_hi.anibnd) i got error. How can i fix this problem and get player animations?
## Post #318
- Username: jdrc8
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 23, 2017 5:42 am
- Post datetime: 2019-04-22T18:39:21+00:00
- Post Title: Re: Dark Souls FLV file

Im interested in getting the player animations. Anyone can help?
