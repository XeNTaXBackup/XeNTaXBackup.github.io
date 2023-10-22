## Post #1
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2016-05-22T20:20:47+00:00
- Post Title: Hitman 2016 textures

So after unpacking the rpkg files with the quick bms script from here : [viewtopic.php?f=10&t=14080&p=116983&hil ... an#p116983](http://forum.xentax.com/viewtopic.php?f=10&t=14080&p=116983&hilit=hitman#p116983) I figured out the .vap texture format used from the TEXD folder. I wrote a C++ program ( scripting is just not my thing  ) that extracts them. I currently can't tell the exact format for a specific file but 90% of them are either DXT1, BC5 or BC7 dds files.

I still need more research to finalize it but just in case anyone is interested I will release the software that extracts them soon.
## Post #2
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2016-05-27T20:48:57+00:00
- Post Title: Hitman 2016 textures

Link to tool : [https://drive.google.com/file/d/0BwDjq7 ... sp=sharing](https://drive.google.com/file/d/0BwDjq7lQ5oRBSEdfSFR1Ni0wdUk/view?usp=sharing)

Usage
Hitman_2016.exe input_folder output_folder

Works only under x64 windows and it may only work on Windows 10. Use at your own risk & stuff.

PS: Software that can read BC4-7 : Visual Studio 2015
## Post #3
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2016-06-26T10:53:31+00:00
- Post Title: Hitman 2016 textures

I have paused development and have no idea if I'll come back to it anytime soon, so I thought it would be nice to share the code that I have so far.

The code also contains info on how to extract some 3D models, however only the biggest files from the PRIM folder work correctly. The RE* dependencies are related to my engine and only contains minor importance code; you won't be able to find that code anywhere but you should be able to reimplement it using std.
[Hitman_2016.zip](https://xentaxbackup.github.io/file/11118_Hitman_2016.zip)
## Post #4
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-09-30T21:58:26+00:00
- Post Title: Hitman 2016 textures

> Reply from cippyboy
>
> I have paused development and have no idea if I'll come back to it anytime soon, so I thought it would be nice to share the code that I have so far.

The code also contains info on how to extract some 3D models, however only the biggest files from the PRIM folder work correctly. The RE* dependencies are related to my engine and only contains minor importance code; you won't be able to find that code anywhere but you should be able to reimplement it using std.

Hi, I appreciate you releasing the source. I'm trying to fill in the gaps of what is missing, and there is one aspect I'm finding a bit mysterious.

The Virtual file class, has both a Load() and a SaveLoad() function.  Load I think is self-explanatory, but what does SaveLoad() do?

Also with the DYNAMIC_ARRAY class, the constructor that takes two parameters, what is the purpose of both parameters?

Example:
  
```
        DYNAMIC_ARRAY<WORD2> Texcoords16(Block3.NumVertices, 4);

        ...

	DYNAMIC_ARRAY<uint16_t> Indices;
	DYNAMIC_ARRAY<Vector3d> Vertices;

	HMObject() :
		Indices(0, 1000),
		Vertices(0, 1000)
	{

	}

```


I'm guessing the first parameter is the initialization count, but what is the second, default value? or something else?
## Post #5
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-10-02T01:38:43+00:00
- Post Title: Hitman 2016 textures

Never mind about the C++ stuff. I figured it out.   

There was a bug in texture conversion, only affecting a fraction of the textures, due to a mishandling of a sub-block of data just under the header. I've fixed it, all seems to convert correctly now.  Version 1.01 attached.

Now to see what I can do about models...

*new version below*
## Post #6
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-10-02T21:46:18+00:00
- Post Title: Hitman 2016 textures

Here's version 1.02 of the texture converter.

I fixed a bug handling textures with missing MIP levels and added support for two new formats. enjoy.
[Hitman_2016v102.rar](https://xentaxbackup.github.io/file/11757_Hitman_2016v102.rar)
## Post #7
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-15T19:26:59+00:00
- Post Title: Hitman 2016 textures

And finally I finished the model importer for Blender (2.63 or above).

Same as pretty much all my importers. if you need to know how to install, see my previous tutorial here: [viewtopic.php?p=103131#p103131](http://forum.xentax.com/viewtopic.php?p=103131#p103131)

Model files are generally in the "PRIM" folder, and have the extension *.dat 




I came across many model formats, and added support for all. But I'm not 100% sure I have all, since it's impossible to test against every model file. If you find a model file that will not load, please let me know name and location. I'll try to add support.  Enjoy.
## Post #8
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2016-12-16T06:26:51+00:00
- Post Title: Hitman 2016 textures

Models are loading fine.

Few problems/issues I've come across. 

- UV's are broken sometimes (that's usually a given with RE'd models)
- LOD model issues. (Nobody will probably use the LOD meshes, so i'm not sure if there is a way to ignore this upon import)
- Sub object scaling issues.
- Overlapping Vert's

Other than that, huge huge thanks for working on this! Huge step forward.
## Post #9
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-16T07:11:33+00:00
- Post Title: Hitman 2016 textures

> Reply from hhchunter
>
> Models are loading fine.

Few problems/issues I've come across. 

- UV's are broken sometimes (that's usually a given with RE'd models)
- LOD model issues. (Nobody will probably use the LOD meshes, so i'm not sure if there is a way to ignore this upon import)
- Sub object scaling issues.

Other than that, huge huge thanks for working on this!

No problem. yeah I probably would have disabled the LOD models if I had a way to identify them, but for the time being I see no way to tell what is LOD0 and what is a lower LOD.

As for the scaling issue, can you point me to an example file?  I have to read the scale out of the model file and scale the resulting mesh, so if scaling is wrong, I want to see why and if I can fix it.  

Same for broken UV. I can't imagine a situation where it UV should be broken.
Thanks.
## Post #10
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2016-12-16T08:25:53+00:00
- Post Title: Hitman 2016 textures

Sorry for the late reply, I don't really use blender so I had to figure out how to view UV's in it.

UV Issues.
Model:
[https://i.imgur.com/7xSzx75.png](https://i.imgur.com/7xSzx75.png)

UV's:
[https://i.imgur.com/AXXJdoQ.png](https://i.imgur.com/AXXJdoQ.png)


I was wondering, if you could port this to executable so that it converts to FBX/OBJ
Or write a version for Maxscript as well
## Post #11
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-16T17:44:00+00:00
- Post Title: Hitman 2016 textures

> Reply from hhchunter
>
> Sorry for the late reply, I don't really use blender so I had to figure out how to view UV's in it.

UV Issues.
Model:
https://i.imgur.com/7xSzx75.png

UV's:
https://i.imgur.com/AXXJdoQ.png


I was wondering, if you could port this to executable so that it converts to FBX/OBJ
Or write a version for Maxscript as well

I'm sorry, I should have been more clear. I need the name and location of the source .dat file that created the bad mesh, so I can look at the data. But as for the first image, I don't see any scaling issue?

as for an exe, I maybe could, but i'd like to get the format nailed down first.
## Post #12
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-17T01:45:03+00:00
- Post Title: Hitman 2016 textures

I was able to find the filename from the picture, and locate the file in chunk0.

Don't know how I missed that UV format, but in any case, I added it.   

Also while poking around, I realized that the Destructible models were packaged together with all their debris in one mesh. I figured out how to designate all the parts with materials:


"Patio heater" with all it's blown up bits included.


the 'intact' material selected and mesh moved over.


After hitting 'p' to separate by selection.

Seems each color is a separate part, but in-game its' all one mesh with the various parts hidden until it's 'destroyed'.  or something along those lines anyway.  In any case, the importer will detect such meshes and add materials accordingly.

There's still the matter of meshes you mentioned have the wrong scale. if you can provide an example, i'll be happy to take a look.

Edit: Newer version attached below.
## Post #13
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2016-12-17T02:26:12+00:00
- Post Title: Hitman 2016 textures

> Reply from volfin
>
> 
Don't know how I missed that UV format, but in any case, I added it.  :keke: 

Also while poking around, I realized that the Destructible models were packaged together with all their debris in one mesh. I figured out how to designate all the parts with materials:

Awesome!

> Reply from volfin
>
> 
There's still the matter of meshes you mentioned have the wrong scale. if you can provide an example, i'll be happy to take a look.

The Jet from Chunk0 had this problem afaik.

0000000000006eca.dat

I moved the sub-objects to the side. The highest poly mesh scales correctly, while others don't.
[https://i.imgur.com/xDtzlIq.png](https://i.imgur.com/xDtzlIq.png)

Also some weirdness with the mesh possibly? Shown when Unwrapping.
[https://i.imgur.com/u6yJyFp.jpg](https://i.imgur.com/u6yJyFp.jpg)
## Post #14
- Username: YourImaginaryFriend
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Mar 14, 2016 5:57 pm
- Post datetime: 2016-12-17T10:52:41+00:00
- Post Title: Hitman 2016 textures

Huge thanks for the tool, Volfin.

In my testing heads, bodies and clothing use correct uvs.
There are some examples where I encountered problems though (all from chunk0)

Buildings (0000000000006979.dat) - [https://i.imgur.com/zLLoKkD.jpg](https://i.imgur.com/zLLoKkD.jpg)

Hair (000000000001e6f6,dat) - [https://i.imgur.com/G2Z2IAW.jpg](https://i.imgur.com/G2Z2IAW.jpg)

Foliage (0000000000005b09.dat) - [https://i.imgur.com/xrAaKXb.jpg](https://i.imgur.com/xrAaKXb.jpg)
## Post #15
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-17T17:57:05+00:00
- Post Title: Hitman 2016 textures

> Reply from YourImaginaryFriend
>
> Huge thanks for the tool, Volfin.

In my testing heads, bodies and clothing use correct uvs.
There are some examples where I encountered problems though (all from chunk0)

Buildings (0000000000006979.dat) - https://i.imgur.com/zLLoKkD.jpg

Hair (000000000001e6f6,dat) - https://i.imgur.com/G2Z2IAW.jpg

Foliage (0000000000005b09.dat) - https://i.imgur.com/xrAaKXb.jpg

Yeah actually those 3 examples you pictured, are correct.   

for the buildings they are just using a small section of a metal texture and it's repeated a lot, so they lay the uv sections on top of each other.  

Same for the hair, they re-use the same strip of hair texture over and over, so they lay each strip on top of each other.

And for the foliage, they use a repeating texture and for each leaf they move it around in UV space, for variation, why they are all over the place.

But it's all valid UV data, and just shows some of the tricks model creators use to make a low rez texture appear higher rez.
## Post #16
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-17T18:21:27+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from hhchunter
>
> volfin wrote:
Don't know how I missed that UV format, but in any case, I added it.   

Also while poking around, I realized that the Destructible models were packaged together with all their debris in one mesh. I figured out how to designate all the parts with materials:


Awesome!
volfin wrote:
There's still the matter of meshes you mentioned have the wrong scale. if you can provide an example, i'll be happy to take a look.


The Jet from Chunk0 had this problem afaik.

0000000000006eca.dat

I moved the sub-objects to the side. The highest poly mesh scales correctly, while others don't.
https://i.imgur.com/xDtzlIq.png

Also some weirdness with the mesh possibly? Shown when Unwrapping.
https://i.imgur.com/u6yJyFp.jpg

it's odd, I'm not seeing any problems with scale when I load that model. the Major LODs for the jet are on layer 1, layer 8, and layer 19, all seem scaled right. Then there's the cockpit interiors on layer 2, layer 5, and layer 15, also all 3 seems scaled right.  I can only think if you're seeing a scale issue, it's caused by some further conversion you're doing yourself. I noticed the images you took were in 3DsMax.

As for the UVs, they seem correct, however, it does seem more than one is being overlaid, there's a large square as you see here that goes to two tiny blocks in the cockpit.  



That seems to tell me there should be multiple materials on this model too, but my importer isn't detecting it. I'll have to look into it.

Well I gave it a hard look, I don't see any material data. I can only guess those two blocks are hidden when the cockpit piece is in place, so they didn't bother texturing them well. (lazy, lazy   )  it shouldn't hurt anything, at worst, maybe cut those two small blocks off.
## Post #17
- Username: YourImaginaryFriend
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Mar 14, 2016 5:57 pm
- Post datetime: 2016-12-18T04:37:58+00:00
- Post Title: Re: Hitman 2016 textures

Yeah, after checking respective textures uvs aligned well. Sorry for wrong information.

There seems to be a legit small issue - character heads have flipped vertical uvs, scaling and position are a bit off too. It can be easily fixed by hand though
## Post #18
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-18T05:19:50+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from YourImaginaryFriend
>
> Yeah, after checking respective textures uvs aligned well. Sorry for wrong information.

There seems to be a legit small issue - character heads have flipped vertical uvs, scaling and position are a bit off too. It can be easily fixed by hand though

I found a head, and yeah I see what you mean. Looking at shoes, I see similar, as far as being flipped. I think I forgot to check the UV against textures, I kind of got wrapped up. So all UVs are flipped on the Y axis. In fact now I found a model where X axis of UV is 1/2 of normal width. So think the UV format is even more complicated than I originally thought. i'll see what I can do to sort it out.

As for misalignment, I think that's because every head is unique, and you have to find the exact right texture for each head. They didn't make the textures generic and interchangeable. Which brings me to a problem I'd love to solve, how to match textures to models. Because right now, there's absolutely no way but to match by eye.
## Post #19
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-18T06:53:49+00:00
- Post Title: Re: Hitman 2016 textures

Ok here's a new version 1.02, which flips the UV for rigged items only (Heads/clothes/body parts). Static items seem to be the right orientation as far as I can tell. I'm still not sure on trees.

Two things, There are some models that may have squished UVs on the U axis, I can't see a way to detect that, you'll have to stretch it out manually (seems rare).  

And I have seen a few times when loading multiple models in the same scene, that models will appear with the wrong scale (it seems). But if you toggle one of the Dimension axis' a little higher then back down to where it was, the model will snap to the proper scale



I'm not sure why the scale transform isn't being applied, but the workaround seem to work. if I figure out how to make it scale more consistently I'll update again.

Edit: newer below.
## Post #20
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2016-12-19T11:32:51+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from volfin
>
> Ok here's a new version 1.02, which flips the UV for rigged items only.

Awesome, weighted Prim's seem mostly done then I'd guess.

I've had a few meshes be outright broken on the other hand however.

[https://i.imgur.com/Te7jQcq.png](https://i.imgur.com/Te7jQcq.png)

There seems to be Overlapping Verts on UV seams. I'm not sure if that's how the models are normally.
## Post #21
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-19T18:18:11+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from hhchunter
>
> volfin wrote:Ok here's a new version 1.02, which flips the UV for rigged items only.

Awesome, weighted Prim's seem mostly done then I'd guess.

I've had a few meshes be outright broken on the other hand however.

https://i.imgur.com/Te7jQcq.png

There seems to be Overlapping Verts on UV seams. I'm not sure if that's how the models are normally.

yes, that's a new mesh format I've not seen before. added it. If you run into any more let me know.

Edit: new version below.
## Post #22
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2017-01-04T16:44:52+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from volfin
>
> hhchunter wrote:volfin wrote:Ok here's a new version 1.02, which flips the UV for rigged items only.

Awesome, weighted Prim's seem mostly done then I'd guess.

I've had a few meshes be outright broken on the other hand however.

https://i.imgur.com/Te7jQcq.png

There seems to be Overlapping Verts on UV seams. I'm not sure if that's how the models are normally.

yes, that's a new mesh format I've not seen before. added it. If you run into any more let me know.

Hi, although it is off topic but.. did you ever know how to decrypt and encrypt text files?
## Post #23
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-04T18:30:41+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from adol365
>
> 
Hi, although it is off topic but.. did you ever know how to decrypt and encrypt text files?

As far as I know, nothing in the game has encryption. Only a couple files do, which aren't really needed for anything. As Ekey said "I found only encryption for config files (packagedefinition.txt and thumbs.dat). It's XTEA."

You can get his tool to decrypt those two files over at zenhax:

[http://www.zenhax.com/viewtopic.php?p=13735#p13735](http://www.zenhax.com/viewtopic.php?p=13735#p13735)  but everything else should be clean data. Making something to read/write that data, is a whole other story of course.
## Post #24
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2017-01-05T06:52:44+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from volfin
>
> adol365 wrote:
Hi, although it is off topic but.. did you ever know how to decrypt and encrypt text files?

As far as I know, nothing in the game has encryption. Only a couple files do, which aren't really needed for anything. As Ekey said "I found only encryption for config files (packagedefinition.txt and thumbs.dat). It's XTEA."

You can get his tool to decrypt those two files over at zenhax:

http://www.zenhax.com/viewtopic.php?p=13735#p13735  but everything else should be clean data. Making something to read/write that data, is a whole other story of course.

No, as far as I know.. Text files are encrypted.
This is my thread on zenhax. [http://zenhax.com/viewtopic.php?t=3399](http://zenhax.com/viewtopic.php?t=3399)
It also discussed in the xentax but no one can figure it out.
## Post #25
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-05T07:00:57+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from adol365
>
> volfin wrote:adol365 wrote:
Hi, although it is off topic but.. did you ever know how to decrypt and encrypt text files?

As far as I know, nothing in the game has encryption. Only a couple files do, which aren't really needed for anything. As Ekey said "I found only encryption for config files (packagedefinition.txt and thumbs.dat). It's XTEA."

You can get his tool to decrypt those two files over at zenhax:

http://www.zenhax.com/viewtopic.php?p=13735#p13735  but everything else should be clean data. Making something to read/write that data, is a whole other story of course.

No, as far as I know.. Text files are encrypted.
This is my thread on zenhax. http://zenhax.com/viewtopic.php?t=3399
It also discussed in the xentax but no one can figure it out.

Oh I don't know then. Seems silly to put encryption on something like that. This isn't exactly NSA secrets
## Post #26
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2017-01-05T07:30:24+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from volfin
>
> 
Oh I don't know then. Seems silly to put encryption on something like that. This isn't exactly NSA secrets

Well.. Square Enix likes encryption.
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-06T17:44:20+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from adol365
>
> It also discussed in the xentax but no one can figure it out.

It's not like "no one can figure it out", but the devs threatened people with lawsuits for decrypting their subtitles. So this must be not too hard to figure out, encryption must be the same, they prob. just changed the key, but nobody wants to mess with it anymore.
## Post #28
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-06T21:01:21+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from daemon1
>
> adol365 wrote:It also discussed in the xentax but no one can figure it out.

It's not like "no one can figure it out", but the devs threatened people with lawsuits for decrypting their subtitles. So this must be not too hard to figure out, encryption must be the same, they prob. just changed the key, but nobody wants to mess with it anymore.

Which in and of itself is silly, since that's like threatening to sue someone for reading a book to someone else, or some other analogy where someone is doing something that there's no laws against. 

I'd do it no problem, if A) I was into encryption (i'm not), and B) I had interest in doing translations (I don't).  But I certainly wouldn't care about some empty threat.

Someone could just type into notepad what every character says, and tada, you have the subtitles. They gonna sue then?
## Post #29
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2017-01-08T14:24:57+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from daemon1
>
> It's not like "no one can figure it out", but the devs threatened people with lawsuits for decrypting their subtitles. So this must be not too hard to figure out, encryption must be the same, they prob. just changed the key, but nobody wants to mess with it anymore.

You're right, but for me, it doesn't matter. The result says that no one will do it now.
## Post #30
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-01-12T08:21:46+00:00
- Post Title: Re: Hitman 2016 textures

Not sure if I've missed something here or elsewhere, but have skeletons been figured into the picture yet? I'm super familiar with volfin's Alien tools and am just getting around to this one and the Deus Ex one, so I figured I'd check...
## Post #31
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-12T17:54:39+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from trexjones
>
> Not sure if I've missed something here or elsewhere, but have skeletons been figured into the picture yet? I'm super familiar with volfin's Alien tools and am just getting around to this one and the Deus Ex one, so I figured I'd check...

Generally I don't do skeletons, it adds an order of magnitude of time and complexity. especially when like with DeusEx and Hitman, the skeleton is in a separate file from the model. I'll often import original weights if I figure out the format, but so far, I've been unable to decipher how they are stored for Hitman/DeusEx:MD
## Post #32
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-01-12T18:05:17+00:00
- Post Title: Re: Hitman 2016 textures

Ah! Thanks for the heads up! Hopefully someone with the know-how and time feels compelled to look into it!
## Post #33
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-27T02:39:01+00:00
- Post Title: Re: Hitman 2016 textures

Minor Update:
- Ensure Object mode is active before attempting import
- Validated functionality back to Blender version 2.70 (oldest supported)

Edit: newer version below.
## Post #34
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2017-01-30T03:19:54+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from volfin
>
> Minor Update:
- Ensure Object mode is active before attempting import
- Validated functionality back to Blender version 2.70 (oldest supported)

Hey Volfin, would you be able to update this to include support for these models.
[suitcase_box_a_00.zip](https://xentaxbackup.github.io/file/12342_suitcase_box_a_00.zip)
## Post #35
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-30T04:11:50+00:00
- Post Title: Re: Hitman 2016 textures

Can you tell me more about this model? Which chunk file did it come from, and what was the original directory/filename?  It's format is completely different than every other model in the game I've seen. Is it even from Hitman?
## Post #36
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2017-01-30T04:45:47+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from volfin
>
> Can you tell me more about this model? Which chunk file did it come from, and what was the original directory/filename?  It's format is completely different than every other model in the game I've seen. Is it even from Hitman?

It came from an Alpha Build of the game which came with hashes, thus the filename. Interesting to hear that's completely different.

It might help to include options on the original script to import file extensions .prim & .pc_prim, because I guess that's what the real file format is for .dat files extracted in the PRIM folder is?

I've included another example
[palace_exterior_main_entrance_a_00.prim.zip](https://xentaxbackup.github.io/file/12344_palace_exterior_main_entrance_a_00.prim.zip)
## Post #37
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-30T05:03:34+00:00
- Post Title: Re: Hitman 2016 textures

Ah that explains it then. Yeah it's not that far off, but several key blocks are missing data and have different sizes. They also stored vertices as integers instead of floats which isn't how any of the models were stored in the release. I think I can make something that will load them, but it may not be that stable, I'd have to basically research the whole format again hehe.
## Post #38
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-30T05:42:16+00:00
- Post Title: Re: Hitman 2016 textures

Ok this version adds support for Alpha version models (at least based on the two I saw.)

Enjoy.
[io_scene_Hitman2016.zip](https://xentaxbackup.github.io/file/12345_io_scene_Hitman2016.zip)
## Post #39
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2017-01-30T07:24:37+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from volfin
>
> Ok this version adds support for Alpha version models (at least based on the two I saw.)

Enjoy.

That was way faster than expected.
Adding extension support for .pc_prim would be helpful, saves mass renaming through command line.

EDIT: I have more work for you Volfin, seems like some sort of linked mesh file? Not sure what it contains :P
[pistol_blackballer_a_e3hackjob.linkedprim.zip](https://xentaxbackup.github.io/file/12346_pistol_blackballer_a_e3hackjob.linkedprim.zip)
## Post #40
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-30T19:01:58+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from hhchunter
>
> 
That was way faster than expected.
Adding extension support for .pc_prim would be helpful, saves mass renaming through command line.
I did: 

it will show those 3 extensions. And anyway if you just click the "Funnel" icon (filter), Blender will show all files. no need to rename anything.


> Reply from hhchunter
>
> 
EDIT: I have more work for you Volfin, seems like some sort of linked mesh file? Not sure what it contains
i'll take a look, if it's simple i'll add it, if it's off the wall, I probably don't have time. I mean most of this stuff should be in the release game anyway right?

EDIT: yeah this one is a strange mix of the old and the new, and there's simply no way to tell from the file what version of what to use. I'd have to write a standalone importer just for this 'alpha' and since I doubt many have it, it's a lot of work for one or two people's benefit. Sorry, but I just don't have the time to spend on this.
## Post #41
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2017-01-31T12:37:03+00:00
- Post Title: Re: Hitman 2016 textures

is the 2016 agent 47 model out yet?
because i can't find it on any 3d model site.
## Post #42
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2018-11-11T13:07:11+00:00
- Post Title: Re: Hitman 2016 textures

In lieu of HITMAN 2 being released and using the same texture format, but with a possibly slightly different header.

Quick analysis looks like it's dropped or moved around two bits?
    - Height & width looks to be @ 0xC & 0xE.

Some examples of the new texture format can be downloaded from [here](https://1drv.ms/f/s!AgLgPtiiLQdWhk4mDiOox7izs5nW)

I've started rewriting cippyboy's simple texture conversion tool, however I need help / still need to remove it's dependencies on his RE libraries and somehow replicate them using std or something simple. I believe Volfin had done this previously but there wasn't any source I could continue/update or investigate from  Makes it a bit of a hard task for someone who barely understands how to code.

[https://github.com/HHCHunter/HITMAN/tre ... /G2TexConv](https://github.com/HHCHunter/HITMAN/tree/master/G2TexConv)
## Post #43
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-11-11T17:24:51+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from hhchunter
>
> In lieu of HITMAN 2 being released and using the same texture format, but with a possibly slightly different header.

Quick analysis looks like it's dropped or moved around two bits?
    - Height & width looks to be @ 0xC & 0xE.

Some examples of the new texture format can be downloaded from here

I've started rewriting cippyboy's simple texture conversion tool, however I need help / still need to remove it's dependencies on his RE libraries and somehow replicate them using std or something simple. I believe Volfin had done this previously but there wasn't any source I could continue/update or investigate from  Makes it a bit of a hard task for someone who barely understands how to code.

https://github.com/HHCHunter/HITMAN/tre ... /G2TexConv

if you want the source code, all you have to do is ask. I mostly didn't give it out because it's an embarrassingly quick and dirty hack job, code is messy.

But you're welcome to the code if you want. Here's my version of Cippy's converter. The project is for Visual Studio 2017 but the code should work with older compilers.

 Note that it's still dependent on the Eigen Math Library:   [http://eigen.tuxfamily.org/index.php?title=Main_Page](http://eigen.tuxfamily.org/index.php?title=Main_Page)  (my version was from 2016 so hopefully newer versions still work fine)

[https://drive.google.com/file/d/1gjODb4 ... sp=sharing](https://drive.google.com/file/d/1gjODb4Y5ARYZcXPT00BWZUu1iQDymTrS/view?usp=sharing)

And yeah, looking at the files, I think the data offsets are all changed.
## Post #44
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2018-11-11T17:41:15+00:00
- Post Title: Re: Hitman 2016 textures

> if you want the source code, all you have to do is ask. I mostly didn't give it out because it's an embarrassingly quick and dirty hack job, code is messy.
>
> 
>
> But you're welcome to the code if you want. Here's my version of Cippy's converter. The project is for Visual Studio 2017 but the code should work with older compilers.
>
> 
>
> Note that it's still dependent on the Eigen Math Library: http://eigen.tuxfamily.org/index.php?title=Main_Page (my version was from 2016 so hopefully newer versions still work fine)
>
> 
>
> https://drive.google.com/file/d/1gjODb4 ... sp=sharing

Honestly was not expecting a reply that quick! Amazed you still have the files on hand.

Gonna have a read over this code and see if I can adapt it to detect HITMAN & HITMAN 2 textures.
## Post #45
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-11-11T17:51:47+00:00
- Post Title: Re: Hitman 2016 textures

I can tell you two differences I already see.  The top header used to have 16 bytes before the width/height, now it only has 12 bytes.

And the header overall used to be 92 bytes, the header_size could be found at byte 88 (stating header was 92 bytes)

But now the header is 144 bytes, with the header_size being found at byte 140 (stating header is 144 bytes)

If you make those two changes it may work. (or not, who knows what else has changed)
## Post #46
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-11-11T17:57:10+00:00
- Post Title: Re: Hitman 2016 textures

I made the changes in hitman.h


And it already works on one of the sample files:

The pattern seems too unique to be a mistake but then again, i don't know. It  coudl be a bad decode, or simply a noise texture. The other 3 it skipped over and wouldn't decode so there may be more work to do. but it's a start. if it's skipping over files, it means it doesn't know their format code, so it's possible (even likely) they have changed what the codes mean.
## Post #47
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2018-11-12T03:00:44+00:00
- Post Title: Re: Hitman 2016 textures

I'm going insane trying to build this. Definitely a me problem though.

The only thing I've changed is the line

From
#include <Eigen/Dense>
To
#include "Eigen/Dense"

And building a Release x86 won't reproduce a file of 28kb size, and when used it produces errors with the texture conversion.

:/
## Post #48
- Username: elijah786s1
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 12, 2018 10:51 pm
- Post datetime: 2019-01-19T21:38:14+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from volfin
>
> I made the changes in hitman.h


And it already works on one of the sample files:

The pattern seems too unique to be a mistake but then again, i don't know. It  coudl be a bad decode, or simply a noise texture. The other 3 it skipped over and wouldn't decode so there may be more work to do. but it's a start. if it's skipping over files, it means it doesn't know their format code, so it's possible (even likely) they have changed what the codes mean.

> Reply from hhchunter
>
> I'm going insane trying to build this. Definitely a me problem though.

The only thing I've changed is the line

From
#include <Eigen/Dense>
To
#include "Eigen/Dense"

And building a Release x86 won't reproduce a file of 28kb size, and when used it produces errors with the texture conversion.

:/

So no progress or update so far. I'm really looking forward for this updated tool, been waiting for like two months and still waiting. I hope someone is working on it. Any update on progress will be appreciated.
## Post #49
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-20T02:09:23+00:00
- Post Title: Re: Hitman 2016 textures

if you can post some samples i will try to make a Noesis python script.
## Post #50
- Username: elijah786s1
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 12, 2018 10:51 pm
- Post datetime: 2019-01-20T08:39:18+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from Acewell
>
> if you can post some samples i will try to make a Noesis python script.

Here's the link: [https://files.fm/u/j7xhur7e](https://files.fm/u/j7xhur7e)

Two two samples from two different chunks.
## Post #51
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-20T10:09:01+00:00
- Post Title: Re: Hitman 2016 textures

this Noesis python script will open your dat and vap samples.  
*script updated Jan 23, 2019*


 tex_Hitman2_PC_dat_vap.zip
(798 Bytes) Downloaded 111 times


supports R8G8(?), A8(?), BC1, BC3, BC4, BC5 and BC7, top level mip only.

since the file extensions are generic and the script has no proper type check
you may encounter an error if there is a script or plugin conflict, so move any
other dat or vap scripts out of plugins folder while using this one.
## Post #52
- Username: elijah786s1
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 12, 2018 10:51 pm
- Post datetime: 2019-01-21T08:43:36+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from Acewell
>
> this Noesis python script will open your dat and vap samples.  
tex_Hitman2_PC_dat_vap.zip
supports BC5 and BC7, top level mip only.
i assumed the game where your samples came from was "Hitman 2",
i'll need more samples to extend the script.
since the file extensions are generic and the script has no proper type check
you may encounter an error if there is a script or plugin conflict, so move any
other dat or vap scripts out of plugins folder while using this one.

Yup it's hitman 2.

Here are some texture samples : [https://files.fm/u/wfbvc2kb](https://files.fm/u/wfbvc2kb)

Normal maps are using ATI2, ATI1
Specular are using DX10 
and Textures are using DXT1

Also i'm getting export complete on some textures but the exported textures are not showing in the output folder.

Complete message:
tga - TGA Image
Output extension has set output file type 
Detected file type: Hitman 2 [PC]
1024 :imgWidth
1024 :imgHeight
0x49 :imgfmt
WARNING: Not enough texture data for specified image type!
## Post #53
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-21T12:48:45+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from elijah786s1
>
> Here are some texture samples : https://files.fm/u/wfbvc2kb
i need to examine unconverted dat/vap samples, i can do nothing with dds files.  

> Reply from elijah786s1
>
> 0x49 :imgfmt
there is no 0x49 format declared in the script, this is why i need more samples.
## Post #54
- Username: elijah786s1
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 12, 2018 10:51 pm
- Post datetime: 2019-01-22T06:28:56+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from Acewell
>
> elijah786s1 wrote:Here are some texture samples : https://files.fm/u/wfbvc2kb
i need to examine unconverted dat/vap samples, i can do nothing with dds files.  
elijah786s1 wrote:0x49 :imgfmt
there is no 0x49 format declared in the script, this is why i need more samples.

Here [https://files.fm/u/pnvdxhrf](https://files.fm/u/pnvdxhrf)

Samples4 are from chunk0 and Samples5 from chunk0patch. Let me know if you need more.
## Post #55
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-22T10:36:17+00:00
- Post Title: Re: Hitman 2016 textures

okay script updated here for BC1 and BC4   
[viewtopic.php?p=147704#p147704](http://forum.xentax.com/viewtopic.php?p=147704#p147704)
## Post #56
- Username: Notex
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Feb 18, 2017 10:12 pm
- Post datetime: 2019-01-22T12:08:10+00:00
- Post Title: Re: Hitman 2016 textures

Textures from TEXD\ seem to convert fine but all the textures in the TEXT\ folder have issues still. Here are some samples

Samples here: [https://i.notex.app/C2FZ8Jt.zip](https://i.notex.app/C2FZ8Jt.zip)

These were taken from chunk0patch2

Edit: Found one texture from the TEXD folder that doesn't convert: [https://i.notex.app/lzyVXQx.vap](https://i.notex.app/lzyVXQx.vap)
## Post #57
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-22T14:09:43+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from Notex
>
> Textures from TEXD\ seem to convert fine but all the textures in the TEXT\ folder have issues still. Here are some samples
my advice is stay out of that TEXT folder, the header info doesn't work with the data provided.
the only info that was correct was the format, the width/height/size info doesn't work.

example info in header from 000000000000000e.vap:
format stored 0x49 = BC1/DXT1 - this was correct
width and height = 1024x1024 - incorrect, actual size of largest stored mip is 128x128
mip 0 size stored = 0x80000 - incorrect, actual size of 128x128 dxt1 is 0x2000,
and only 0x2ab8 of image data is actually stored in the file 

those files may as well be headerless, you can still convert them by hand.   


> Reply from Notex
>
> Found one texture from the TEXD folder that doesn't convert: https://i.notex.app/lzyVXQx.vap
okay script updated here again to support BC3/DXT5.   
[viewtopic.php?p=147704#p147704](http://forum.xentax.com/viewtopic.php?p=147704#p147704)
## Post #58
- Username: Notex
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Feb 18, 2017 10:12 pm
- Post datetime: 2019-01-22T15:33:15+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from Acewell
>
> 
okay script updated here again to support BC3/DXT5.   
viewtopic.php?p=147704#p147704
Thanks so much 

Edit: Would it be possible at all to reconvert textures? I'm just curious, I've never used noesis before and it doesn't seem to have that functionality.
## Post #59
- Username: elijah786s1
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 12, 2018 10:51 pm
- Post datetime: 2019-01-22T18:53:04+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from Acewell
>
> Notex wrote:Textures from TEXD\ seem to convert fine but all the textures in the TEXT\ folder have issues still. Here are some samples
my advice is stay out of that TEXT folder, the header info doesn't work with the data provided.
the only info that was correct was the format, the width/height/size info doesn't work.

example info in header from 000000000000000e.vap:
format stored 0x49 = BC1/DXT1 - this was correct
width and height = 1024x1024 - incorrect, actual size of largest stored mip is 128x128
mip 0 size stored = 0x80000 - incorrect, actual size of 128x128 dxt1 is 0x2000,
and only 0x2ab8 of image data is actually stored in the file 

those files may as well be headerless, you can still convert them by hand.   

Notex wrote:Found one texture from the TEXD folder that doesn't convert: https://i.notex.app/lzyVXQx.vap
okay script updated here again to support BC3/DXT5.   
viewtopic.php?p=147704#p147704

Thanks and keep up the good work.    

> Reply from Notex
>
> Acewell wrote:
okay script updated here again to support BC3/DXT5.   
viewtopic.php?p=147704#p147704
Thanks so much 

Edit: Would it be possible at all to reconvert textures? I'm just curious, I've never used noesis before and it doesn't seem to have that functionality.

I think re-importing is possible through quickbms.
## Post #60
- Username: elijah786s1
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 12, 2018 10:51 pm
- Post datetime: 2019-01-22T19:39:39+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from Acewell
>
> okay script updated here again to support BC3/DXT5.   
viewtopic.php?p=147704#p147704
[https://files.fm/u/gunfa3t2](https://files.fm/u/gunfa3t2) These four files are not exporting.
## Post #61
- Username: Notex
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Feb 18, 2017 10:12 pm
- Post datetime: 2019-01-23T02:06:46+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from elijah786s1
>
> I think re-importing is possible through quickbms.
The texture would need to be reconverted back into it's original format before I could re-import it with QuickBMS.
## Post #62
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-23T03:00:44+00:00
- Post Title: Re: Hitman 2016 textures

okay script here updated to support 8bit alpha.   
[viewtopic.php?p=147704#p147704](http://forum.xentax.com/viewtopic.php?p=147704#p147704)

> Reply from Notex
>
> Would it be possible at all to reconvert textures?
that would classify as modding which is not my area, 
but you should be able to replace the image data with modified data
as long as its same size, format, dimensions and number of mips.
## Post #63
- Username: elijah786s1
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 12, 2018 10:51 pm
- Post datetime: 2019-01-23T11:35:44+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from Notex
>
> Would it be possible at all to reconvert textures?

> Reply from Acewell
>
> okay script here updated to support 8bit alpha.   
viewtopic.php?p=147704#p147704

that would classify as modding which is not my area, 
but you should be able to replace the image data with modified data
as long as its same size, format, dimensions and number of mips.

I tried the hex editor method found here: [https://www.reddit.com/r/HiTMAN/comment ... _tutorial/](https://www.reddit.com/r/HiTMAN/comments/62klik/hitman_texture_modding_tutorial/) 
You select and copy block of 92 from vap and replace 128 block of texture image with 92 and save it as vap. This method is not currently working on hitman 2, maybe we need to copy more or less.
## Post #64
- Username: Notex
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Feb 18, 2017 10:12 pm
- Post datetime: 2019-01-23T15:54:08+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from elijah786s1
>
> I tried the hex editor method found here: https://www.reddit.com/r/HiTMAN/comment ... _tutorial/ 
You select and copy block of 92 from vap and replace 128 block of texture image with 92 and save it as vap. This method is not currently working on hitman 2, maybe we need to copy more or less.
Managed to edit textures in-game.


What sections to replace:



> Reply from Acewell
>
> okay script here updated to support 8bit alpha.   
viewtopic.php?p=147704#p147704
Found another texture that doesn't convert
[https://i.notex.app/BjdGED6.dat](https://i.notex.app/BjdGED6.dat)
## Post #65
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-23T19:44:10+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from Notex
>
> Found another texture that doesn't convert
https://i.notex.app/BjdGED6.dat
i wasn't 100% sure about type 0x34, but r8g8 looks pretty good to me.   
script here updated to support r8g8
[viewtopic.php?p=147704#p147704](http://forum.xentax.com/viewtopic.php?p=147704#p147704)
## Post #66
- Username: Notex
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Feb 18, 2017 10:12 pm
- Post datetime: 2019-01-24T00:03:02+00:00
- Post Title: Re: Hitman 2016 textures

> Reply from Acewell
>
> Notex wrote:Found another texture that doesn't convert
https://i.notex.app/BjdGED6.dat
i wasn't 100% sure about type 0x34, but r8g8 looks pretty good to me.   
script here updated to support r8g8
viewtopic.php?p=147704#p147704
Thanks for putting your time into this script, it seems to be pretty much perfect now
## Post #67
- Username: venomousbeetle
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 14, 2019 12:01 am
- Post datetime: 2019-02-13T17:58:47+00:00
- Post Title: Re: Hitman 2016 textures

Having trouble finding the ninja disguise from Hokkaido, I've been through each texture ad didn't see one that I could reasonably identify as that disguise. Is there a way to view by model instead of flat textures like on the noesis download page?
## Post #68
- Username: Spotifychild
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 10, 2021 1:20 am
- Post datetime: 2021-04-09T17:26:47+00:00
- Post Title: Re: Hitman 2016 textures

Is there some tutorial for extracting textures?
## Post #69
- Username: Sinister
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 16, 2020 10:07 pm
- Post datetime: 2021-04-17T10:59:51+00:00
- Post Title: Re: Hitman 2016 textures

Hello all. Has anyone managed to extract Hitman 3 (2021) textures so far?
