## Post #1
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-11-21T14:15:31+00:00
- Post Title: [Request]Ratchet & Clank: into the Nexus

So Iv'e taken a look at some of the R&C:N files and the models seem like they could be in these mobys.dat files with textures in textures.dat files.

This is how the mobys.dat files look. the clankpuzzles mobys.dat is shown here.


Here are some file that I got off of the pre-alpha disk
[https://www.dropbox.com/sh/pyc1trdk6ojlrej/IdFGiBLDpo](https://www.dropbox.com/sh/pyc1trdk6ojlrej/IdFGiBLDpo)
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-11-22T08:42:00+00:00
- Post Title: [Request]Ratchet & Clank: into the Nexus

> Reply from o0DemonBoy0o
>
> So Iv'e taken a look at some of the R&C:N files and the models seem like they could be in these mobys.dat files with textures in textures.dat files.

This is how the mobys.dat files look. the clankpuzzles mobys.dat is shown here.


Here are some file that I got off of the pre-alpha disk
https://www.dropbox.com/sh/pyc1trdk6ojlrej/IdFGiBLDpo

Wow nice their format hasn't changed since Resistance 2. Pretty straight forward structure sadly I can't help right now got exams on and busy with other stuff  

```
// Insomniac Games ???? ????
// Stored in 2 files header.dat and texel.dat

// Header.dat
struct IGHW_header {
	int32 header_define; // IGHW Header identifier (IGHW)						(const)
	int32 unknown_var1; // unknown												(const)
	int32 unknown_var2; // identifier1	(sound 0x3) (image data 0x2)									
	int32 unknown_var3; // identifier2	(sound 0x50) (image data 0x40)		
	};
```


what i've figured out previously
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-26T16:50:40+00:00
- Post Title: [Request]Ratchet & Clank: into the Nexus

Some models should be handled by hex2obj, v0.2 now.
## Post #4
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-11-27T00:34:23+00:00
- Post Title: [Request]Ratchet & Clank: into the Nexus

> Reply from shakotay2
>
> Some models should be handled by hex2obj, v0.2 now.

That's pretty great Shatokay, but I still don't know how to use hex2obj even after I read the tutorial.

Edit:

Nevermind, I think I figured it out.

It doesn't seem to help to much with models that have multiple meshes, unless there is something i'm doing wrong.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-27T07:32:28+00:00
- Post Title: [Request]Ratchet & Clank: into the Nexus

If you told me at which address of your 35 MB mobys.dat you're in trouble I could have a look at.

This is the first model:
0xA00 4164
VB1
28 16
0x2B00 1208
1204

'cut' must be enabled.

[](http://www.pic-upload.de/view-21954201/R-CNexusMobys.jpg.html)

Submeshes have to be handled one by one. (Iirc this model consists of one mesh only.)
## Post #6
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-11-27T08:50:41+00:00
- Post Title: [Request]Ratchet & Clank: into the Nexus

Actually I just cut out Ratchet's model data. you can find it here. 

[https://www.dropbox.com/s/fwzgs3hcmc60b ... tnexus.dat](https://www.dropbox.com/s/fwzgs3hcmc60b7d/ratchetnexus.dat)

This is what I used and all I could get was his eye mesh. If I tried anything else all I get a jumbled mess roughly in the shape of his head.
His model contains way more than one mesh.

0x9E00 3456
VB1
28 16
0xA9800 654
1204
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-27T12:13:06+00:00
- Post Title: [Request]Ratchet & Clank: into the Nexus

yep. That's the difficult part.  

to be honest: that's the annoying part (which always wasted my lifetime when trying to code universal extractors).
So I finally decided to create hex2obj and leave this part to the customers.

Possible start addresses of face index lists are easy to be found: 0xB900, 0xC440, 0x11AA4, 0x14A50 etc.

But where to find the suiting start addr. of the vertex blocks?
I would try searching for 00 00 00 FF 00 00 00 and get the gaps.
Since for one continous mesh the delta between the findings has to be 0x1C (=28, Vertex Block size).

After a gap a new (sub)mesh should begin.
But that's mere theory...

Anyway, next address of vertices should be 0xA9800 + 654x28= 0xADF88 but seems is not.

edit: [](http://www.pic-upload.de/view-21456388/justAQuestionOfPatience.jpg.html)

0xB900 12498
VB1
28 16
0xADF88 2042
1204
## Post #8
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-11-27T21:08:16+00:00
- Post Title: [Request]Ratchet & Clank: into the Nexus

Alright I figured it out. 

Your math was right, just the count on step 1 was wrong. It was supposed to be 1440 which would make it

0xB900 1440
VB1
28 16
0xADF88 146
1204

Not really much there though, so moving on to the next mesh using the same math I got 

0xC440 11058
VB1
28 16
0xAEF80 2042
1204

and that got me his face mesh



The only thing needed now seems to be UVs.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-27T21:51:15+00:00
- Post Title: [Request]Ratchet & Clank: into the Nexus

> Reply from o0DemonBoy0o
>
> and that got me his face meshSeems you got the trick.  

> The only thing needed now seems to be UVs.Well, looks like this:
[](http://www.pic-upload.de/view-21462484/head_UVs_QM.jpg.html)
Not sure what's going wrong. I'll need some cubic or square object to understand what's going on here.
## Post #10
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-11-27T22:39:15+00:00
- Post Title: [Request]Ratchet & Clank: into the Nexus

Well here is what should be one of the crate models.

[https://www.dropbox.com/s/xxlze6m3kamd9 ... oCrate.dat](https://www.dropbox.com/s/xxlze6m3kamd9sj/NexusAmmoCrate.dat)

I tried to convert it to an obj using the same method as before but all i get is a jumbled mess. 

Is this a different kind of model from Ratchet?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-27T23:19:31+00:00
- Post Title: [Request]Ratchet & Clank: into the Nexus

> Reply from o0DemonBoy0o
>
> Is this a different kind of model from Ratchet?VBsize is different.
0x1480 2304
VB1
20 8
0xA300 535
1204

[](http://www.pic-upload.de/view-21463055/AmmoCrate.jpg.html) Still not sure about the UVs - is there a simpler box or chest without ornaments?

(Or the texture of the crate could help, too.)
## Post #12
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-11-28T00:10:29+00:00
- Post Title: [Request]Ratchet & Clank: into the Nexus

I couldn't find the texture for the ammo crate but I did get the bolt crate.

[https://www.dropbox.com/s/rz6wic8u7ko8r ... tCrate.dat](https://www.dropbox.com/s/rz6wic8u7ko8rq8/NexusBoltCrate.dat)

This is about as simple as it gets. I can't think of anything better than that.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-28T00:30:59+00:00
- Post Title: [Request]Ratchet & Clank: into the Nexus

Thx.
[](http://www.pic-upload.de/view-21463401/BoltCrate.jpg.html) Looks o.k. to me.

Didn't cra0 make a texture tool?
Would be helpful if we had the texture of the AmmoCrate.

But iirc I had the texture of clanks head. Will have a look at it tomorrow. Good night...

edit: hmm, head UV not very similar to the one above:
[](http://www.pic-upload.de/view-21470844/head_UV.jpg.html)
## Post #14
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2013-12-02T12:53:07+00:00
- Post Title: [Request]Ratchet & Clank: into the Nexus

> Reply from shakotay2
>
> 
Didn't cra0 make a texture tool?

Nope. Not that I know of anyway.

I've gotten the hang of extracting the models, it's just the textures that are giving me problems. About half of them I cannot view correctly. That includes most of the player and npc textures.

I can get you Clank's raw model and texture though if it would help.
## Post #15
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-01-13T09:34:10+00:00
- Post Title: [Request]Ratchet & Clank: into the Nexus

Thought I would bump to see if any new progress was made.
## Post #16
- Username: Flamingspaz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Dec 28, 2013 7:39 pm
- Post datetime: 2014-01-16T09:24:16+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

Well , I've ripped most of the textures including npcs and playable characters.. let me know if you need them in the mean time
## Post #17
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-01-16T17:42:11+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

Well Ratchet and Vendra and Neftin Prog's textures would be nice. 
How do you rip the textures? My way isn't very effective.
## Post #18
- Username: Flamingspaz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Dec 28, 2013 7:39 pm
- Post datetime: 2014-01-16T17:46:30+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

I have ratchet's (ill pm you) , IDK which one of those is neftin's -,- or vendra's -,- hmm could you send me the UVs
## Post #19
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-01-16T17:51:30+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

I don't have the models with UVs. 
shakotay2 was the only one to almost get them, but never said anything after his last post.
## Post #20
- Username: Flamingspaz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Dec 28, 2013 7:39 pm
- Post datetime: 2014-01-16T18:30:36+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

> Reply from o0DemonBoy0o
>
> How do you rip the textures? My way isn't very effective.
hmm, What kind of way do you use?, may I ask.
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-16T19:45:25+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

> Reply from o0DemonBoy0o
>
> shakotay2 was the only one to almost get them, but never said anything after his last post.As I wrote somewhere my spare time is limited a little bit.
So I won't waste more than let's say 15 minutes on a model.

When looking at this pic I don't get a clue what the problem is. Maybe the correct UVs are located in a separate uv data block.
[](http://www.pic-upload.de/view-21970909/mobyWeirdUVs.jpg.html)

Since R&C models aren't the ones I'm really interested in it may take some time 'till I'll give it another try.
## Post #22
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-01-16T23:15:54+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

> Reply from Flamingspaz
>
> o0DemonBoy0o wrote:How do you rip the textures? My way isn't very effective.
hmm, What kind of way do you use?, may I ask.
I just use texture finder on everything. :/

> Reply from shakotay2
>
> o0DemonBoy0o wrote:shakotay2 was the only one to almost get them, but never said anything after his last post.As I wrote somewhere my spare time is limited a little bit.
So I won't waste more than let's say 15 minutes on a model.

When looking at this pic I don't get a clue what the problem is. Maybe the correct UVs are located in a separate uv data block.


Since R&C models aren't the ones I'm really interested in it may take some time 'till I'll give it another try.

Ah alright then. UVs aren't a huge deal as long as I can get the textures.
## Post #23
- Username: luxox18
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-08-30T15:26:18+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

Ok, I spent some time re-writing the Noesis importer for the better.....

It is not finished and there are possibly some bugs....

I had some issues with finding what vertices were weighted to what bones for mesh type 0x0. For some reason the info is not stored within the vertices themselves like it is for mesh type 0x1. Normals aren't supported and Weights since I haven't really taken an in depth look. Lots of that stuff is just left as placeholders but the bones, UVs, mesh scale info and probably more is all there.

I spent some time looking at textures but due to the complexity I did not add support for them. This script is completely discontinued so someone else could probably pickup where I left off!

The meshes are stored within mobys.dat. There was a quickbms script which extracted all the meshes but I cannot seem to find it so someone may need to write a new one or find where that old one came from. It should also support some Resitance 2 models.. The format is just the same...

Cheers.
[fmt_ratchetandclank_irb_1_2.zip](https://xentaxbackup.github.io/file/7760_fmt_ratchetandclank_irb_1_2.zip)
## Post #24
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-09-01T12:33:13+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

Thanks again Gh0stBlade.

Can someone try taking a look at these textures?
Here is a color map
[https://www.dropbox.com/s/cotubexdk3t1j ... rDiff?dl=0](https://www.dropbox.com/s/cotubexdk3t1j8w/ArmorDiff?dl=0)

and a normal map
[https://www.dropbox.com/s/fquvnmx3fna17 ... rNorm?dl=0](https://www.dropbox.com/s/fquvnmx3fna17d5/ArmorNorm?dl=0)

These are Ratchet's armor textures from FFA/Q-Force.

For some reason about half of the textures are in a different format than the rest, which are usually DDS.
These are two examples.

Any help with this is greatly appreciated as there are a lot of character models that I would like, but can't use because of this texture problem.
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-01T16:20:12+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

seems the uv issue is being solved. Thx, Gh0stBlade!



ratchetNexus_head_uvs.JPG (61.74 KiB) Viewed 163 times



got a problem with an irb - "solved" it like this

```
				entryCount=100
			if entryType in irbEntryTypeList:
```

Wasn't sure which value to set the entryCount to. If it's too big you'll get duplicate submeshes.
## Post #26
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-09-01T17:47:58+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

> Reply from shakotay2
>
> seems the uv issue is being solved. Thx, Gh0stBlade!
ratchetNexus_head_uvs.JPG

got a problem with an irb - "solved" it like this
Code: Select all			if entryCount>39:	# suppress some MeshInfo when count too big
				entryCount=100
			if entryType in irbEntryTypeList:
Wasn't sure which value to set the entryCount to. If it's too big you'll get duplicate submeshes.

Yeah the UVs look great! I think some of them are scaled though, I might have found scale info in the old script. Doesn't look like I've implemented it on this one but I have not seen any problems so far...

I think I understand what you mean. The actual entry count for the meshInfo is correct. It just loads every single mesh specified in the meshInfo. The cause of duplicated meshes is probably due to different lods if my memory is correct! If you remove some of the entries like the way you did, it might not have all the sub meshes the model is intended to have. I do recall seeing some index pointing to what model each sub mesh belongs to. It should be a very easy fix!

The textures are related to the shaders apparently... It should be possible to unpack them all manually. I believe the actual size info was found in assetlookup or some file with a similar name..

Cheers.
## Post #27
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-09-03T17:46:57+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

Maybe this will help someone with getting textures
[https://www.dropbox.com/s/qng6s3wwoz5yxl0/patch.7z?dl=0](https://www.dropbox.com/s/qng6s3wwoz5yxl0/patch.7z?dl=0)

This folder was in one of the patch updates for FFA/Q-Force that added some new mp skins.
It has a shaders.dat, textures.dat, assetlookup.dat, highmips.dat, and mobys.dat.
## Post #28
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-09-10T18:20:04+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

I got something from one of the textures from Nexus.
[https://www.dropbox.com/s/j6758xjei83mu ... fur_c?dl=0](https://www.dropbox.com/s/j6758xjei83muyn/rcn_fur_c?dl=0)

Using PVRTexTool I wrapped this texture as pvrtc 2bpp and got this

 
(Resized down from 4096x4096)

The colors are all wrong, but you can see what the texture is.

I also tried wrapping it as an uncompressed ARGB8888 and got this

(Resized down from  1024x1024)

The colors seem to be right but everything else is wrong

This is about as far as I can get with the textures and i'm not sure what else to do
## Post #29
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-09-11T00:59:46+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

I recall having the same issue with some of the colours being messed up. Could be wrong DDS type etc.. The texture files are definitely DDS files though...

Anyways it's not a good idea to extract a texture manually. You need to find some way of extracting the textures which is the reason why I didn't add support for them. I believe it's something to do with assetlookup.dat... I think it had the size and offset info from my memory..

Hope it helps!
## Post #30
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-09-11T02:53:44+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

> Reply from Gh0stBlade
>
> I recall having the same issue with some of the colours being messed up. Could be wrong DDS type etc.. The texture files are definitely DDS files though...

Anyways it's not a good idea to extract a texture manually. You need to find some way of extracting the textures which is the reason why I didn't add support for them. I believe it's something to do with assetlookup.dat... I think it had the size and offset info from my memory..

Hope it helps!

Are you sure? I tried reading it as just about every kind of DDS and didn't get anything that even resembled what the texture is supposed to be.

Edit:

I did it! The textures were PVR images and not DDS
Using the CL version of pvrtextool, I converted an image using 
pvrtextool -f8888 -border -ifacetest.png
and applied the header of that image to the rcn_fur_c image I linked above and I was able to view it after some messing around with the color channels. Blue was switched with alpha, and red was switched with green
## Post #31
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-09-14T12:19:55+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

I did some messing around and thought I would share what I found out about the textures.

The levels shaders.dat looks to have the names of all the textures found in that levels textures.dat and highmips.dat with each set of textures having their own section separated with "IGHW".

After the first set of padding, which looks like it is always "PAD0PAD1PAD2PAD3" Is a set of 8 bytes for each texture listed in that section. 
I found out that you can take those first 4 bytes and search for them in the assetlookup.dat and there are always 2 results.
I think those last 4 bits are the texture type

00 00 55 80 = DXT1
00 00 AB 00 = DXT5
00 55 55 80 = PVRTC 8888
00 2A AB 00 = PVRTC 88


The first result in the assetlookup.dat is for the textures.dat and the second is for the highmips.dat

The 4 bytes after the search in the assetlookup.dat is the start of that texture data and the 4 bytes after that is the size.

that last thing I found out is that in every *.irb is a section of text that looks something like this

```
built/tuids/f70/f705a4a51f94b562/.built/tuids/d94/d9425ed81f94b4b4/.built/tuids/035/0351bfd91f94b5a5/.
```


You can those 16 numbers/letters after every "built/tuids/XXX/" and search for it as hex in the shaders.dat and it will take you to the textures it is referencing, although there are a couple times where the textures are not always found.

Maybe someone can use this information to make some kind of extractor.
## Post #32
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-09-15T23:35:17+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

This will probably be my last post in this thread.

I found out that there are irb files in every levels ties.dat
They are structured differently from the moby irb files and don't load at all with the plugin Gh0stBlade gave.
I was going to ask him to take a look at these, but he said he was done with the format so I didn't want to bother him.

Anyway, here are some samples if anyone wants to take a look
[https://www.dropbox.com/s/56bqcqagelnjb ... p.zip?dl=0](https://www.dropbox.com/s/56bqcqagelnjb7f/tiedatsamp.zip?dl=0)


The ties looks to be the same as mobys except it has the data switch around. 
Also ties are completely static with no bones.
I can get the models from these tie irb files with hex2obj, but like before it has those same problems with the UVs being stretched and meshes not always coming out right
## Post #33
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-09-16T05:02:07+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

> Reply from o0DemonBoy0o
>
> This will probably be my last post in this thread.

I found out that there are irb files in every levels ties.dat
They are structured differently from the moby irb files and don't load at all with the plugin Gh0stBlade gave.
I was going to ask him to take a look at these, but he said he was done with the format so I didn't want to bother him.

Anyway, here are some samples if anyone wants to take a look
https://www.dropbox.com/s/56bqcqagelnjb ... p.zip?dl=0


The ties looks to be the same as mobys except it has the data switch around. 
Also ties are completely static with no bones.
I can get the models from these tie irb files with hex2obj, but like before it has those same problems with the UVs being stretched and meshes not always coming out right

For obtain uvs with hex2obj in models like resistence, killzone and others you need to export two meshes. one in worldall (mesh) and other in HF_all (uv) then save the uv from the HF_all model and fit it in worldall model. use the same uv size , index count , vertex count , etc. (is not a definitive method but works fine)

about textures in ratchet and clank .... in hightmips the textures files have padding 00 between them. is more easy to export than resistance.
## Post #34
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-09-16T06:37:54+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

> Reply from luxox18
>
> 

For obtain uvs with hex2obj in models like resistence, killzone and others you need to export two meshes. one in worldall (mesh) and other in HF_all (uv) then save the uv from the HF_all model and fit it in worldall model. use the same uv size , index count , vertex count , etc. (is not a definitive method but works fine)

Thanks, but that doesn't fix the problem where the meshes don't always fit right.
Here is an old example of what I mean

When I import all the meshes together they usually have gaps between them like this.

> about textures in ratchet and clank .... in hightmips the textures files have padding 00 between them. is more easy to export than resistance.
That isn't true. I've extracted textures from all the ps3 Ratchet games and I have seen no padding of any kind between the textures in the highmips.dat. 
Maybe you are thinking about textures.dat where there is usually padding between them?
## Post #35
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-16T15:34:59+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

> Reply from o0DemonBoy0o
>
> Here is an old example of what I mean
[...]
When I import all the meshes together they usually have gaps between them like this.sure, you didn't miss some face indices?

I don't have time to check a model with all his submeshes (mc_statue_zungo_entity.irb seems to contain 17 of them for example).

If you uploaded the H2O files (for your "old example" it shouldn't be more than 5, I guess - for the head only) I could have a look at.
## Post #36
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-09-16T16:13:53+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

> Reply from shakotay2
>
> sure, you didn't miss some face indices?

I don't have time to check a model with all his submeshes (mc_statue_zungo_entity.irb seems to contain 17 of them for example).

If you uploaded the H2O files (for your "old example" it shouldn't be more than 5, I guess - for the head only) I could have a look at.

I'm pretty sure I didn't. I usually double check to make sure I did everything right if there are some problems with the model.

I actually don't have the h20 files for the image i posted above anymore, but mc_statue_tachyon.entity.irb has the same issues stated above. It's visible under and around the back of the head.
Here are the H20 files for that model
[tachyonstatueh20.zip](https://xentaxbackup.github.io/file/7825_tachyonstatueh20.zip)
## Post #37
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-16T19:07:04+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

thx for the H2Os. Not to bother you but that tachyon-irb is not contained in the zip you uploaded (you know that I don't owe the game:)).
## Post #38
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-09-16T22:14:01+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

Ok, I just took a quick look. Looks like the actual header and file table structure is the same. The problem is that they use different flags. I'm guessing it's different for static meshes. I'll probably fit it in soon.
## Post #39
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-09-16T23:33:20+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

> Reply from shakotay2
>
> thx for the H2Os. Not to bother you but that tachyon-irb is not contained in the zip you uploaded (you know that I don't owe the game:)).
Whoops, I could have sworn that it was one of the meshes I included. 
I've been up quite a while messing with these models

> Reply from Gh0stBlade
>
> Ok, I just took a quick look. Looks like the actual header and file table structure is the same. The problem is that they use different flags. I'm guessing it's different for static meshes. I'll probably fit it in soon.
Neat! Thanks Gh0stBlade
[mc_statue_tachyon.entity.zip](https://xentaxbackup.github.io/file/7828_mc_statue_tachyon.entity.zip)
## Post #40
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-17T00:26:54+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

the H2Os are like I would have done it (uvs as HF in a 2nd step as u know).
Only irregularity I can see is with the first submesh: this strange "blade of a sword", right?

Then I separated it roughly from the mesh and seems it's a sword with the hilt missing:



tachyon.jpg (88.21 KiB) Viewed 81 times
## Post #41
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-09-17T00:41:54+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

That's actually part of his head fin thing. Just take those vertices that are at the bottom for whatever reason, and move them up

The right side of his head is like this for me
## Post #42
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-17T01:02:13+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

mean the gap between the two tris? Not sure, may be a problem of precision. Hex2obj is using 6 digits only (float precision).
## Post #43
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-09-17T01:20:22+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

Ah, alright. I guess i'll just wait until Gh0stBlade adds support for these then.
## Post #44
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-09-18T04:08:49+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

I have added *partial* support for those meshes. But to ensure compatibility. Could you please provide:

1. A couple of normal meshes (ones currently supported)
2. A couple of these new meshes which are not supported by the old script. Edit: Larger meshes would be great for testing because they could use multiple vertex formats which is something I need to check.

I'm currently having to alter the script slightly and I don't have any files from this game to test. Therefore, I can't merge the scripts yet.
## Post #45
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-09-18T04:27:05+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

Here you go, I added 15 mobys and 15 ties irbs
[https://www.dropbox.com/s/kzfa1upv11gd3 ... p.zip?dl=0](https://www.dropbox.com/s/kzfa1upv11gd325/IRBSamp.zip?dl=0)
## Post #46
- Username: o0DemonBoy0o
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-09-18T05:23:11+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

This should work on the files you uploaded. I didn't find any additional vert types for the new files. The script merge was a success.. It's a little ugly though but should work.

Enjoy!

Edit: Woops, fixed crash issue.
[fmt_ratchetandclank_irb_1_5.zip](https://xentaxbackup.github.io/file/7836_fmt_ratchetandclank_irb_1_5.zip)
## Post #47
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-09-18T06:12:31+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

Thanks again GhostBlade! It works perfectly.
## Post #48
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-05-16T01:39:03+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

Heya, So I recently found out that there are models in the textures.dat files in ToD and QfB.
I can get most fine with Hex2Obj, but I am running into the same errors when I used it to get the models from the other games in the beginning (Stretched meshes on some models, and stretched UVs).

Would there be any way to get the models and fix these errors or would I just have to manually fix them?

Here is the section of data I cut from the viper_caverns textures.dat from QfB
[https://www.dropbox.com/s/eowz54rum0do2 ... x.zip?dl=0](https://www.dropbox.com/s/eowz54rum0do209/QfBViperCaversTex.zip?dl=0)
After this section of data it's just normal textures.


This is a model from the textures_1.dat file
## Post #49
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-16T04:37:59+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

(btw: you really should update to the latest version of hex2obj)

> Reply from o0DemonBoy0o
>
> Would there be any way to get the models and fix these errors or would I just have to manually fix them?Don't think it's an error. It's just a matter of scaling. 

You can do that using a python script (blender 2.69 or higher).
For the mesh (scale x by 2.5) in object mode:
import bpy

bpy.ops.transform.resize(value=(2.5, 1, 1), constraint_axis=(True, False, False), constraint_orientation='GLOBAL', 
mirror=False, proportional='DISABLED', proportional_edit_falloff='SMOOTH', 
proportional_size=1, snap=False, snap_target='CLOSEST', snap_point=(0, 0, 0), 
snap_align=False, snap_normal=(0, 0, 0), texture_space=False, release_confirm=False)

For the uvs it's a little bit harder (modified from [http://blender.stackexchange.com/questi ... cted-items](http://blender.stackexchange.com/questions/7526/python-move-uv-for-selected-items)):

```

#+ grab the current area
original_area = bpy.context.area.type

scene = bpy.context.scene
for count, ob in enumerate(bpy.context.selected_objects):
    if ob.type == 'MESH':
        scene.objects.active = ob
        #+ switch to the image editor to perform transforms etc
        bpy.context.area.type = 'IMAGE_EDITOR'
        bpy.ops.object.mode_set(mode='EDIT', toggle=False)

        bpy.ops.mesh.reveal()
        bpy.ops.mesh.select_all(action='SELECT')
        #+ select the uvs
        bpy.ops.uv.select_all(action='SELECT')

        bpy.ops.transform.resize(value=(2.5, 1, 1), constraint_axis=(True, False, False), constraint_orientation='GLOBAL', 
        mirror=False, proportional='DISABLED', proportional_edit_falloff='SMOOTH', 
        proportional_size=1, snap=False, snap_target='CLOSEST', snap_point=(0, 0, 0), 
        snap_align=False, snap_normal=(0, 0, 0), texture_space=False, release_confirm=False)

        #+ return to the original mode where the script was run
        bpy.context.area.type = original_area
        bpy.ops.object.mode_set(mode='OBJECT', toggle=False)
```

(If you perform it in edit mode in the uv editor the uvs seem to vanish. But it's just a switch to object mode.
Which in this case is not the 'original' one as claimed by the script.  )



QfB_armor.JPG (137.73 KiB) Viewed 318 times



As always execute the script in blender's text window with alt-p.
## Post #50
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-05-16T05:43:03+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

Thanks, but the problem with the UVs still remain.
This is the texture they are supposed to fit


The UVs are still a bit stretched vertically
## Post #51
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-16T08:02:11+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

ok, then you'd to do it manually by dividing the texture up into a lower and an upper part for example and treat them seperately:



QfB_Armor_.JPG (196.67 KiB) Viewed 315 times


Guess this would be easier if you found submeshes (not the ones created automatically every 500 faces by hex2obj).
## Post #52
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-05-16T12:29:08+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

Ah, alright then. Guess I have to still do that part manually.

I wonder how Gh0stBlade fixed that with his irb importer.

Edit:

It seems that the UVs are Half Float but the Mesh is Short All. Any way to do this with hex2obj?
## Post #53
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-16T13:17:30+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

> Reply from o0DemonBoy0o
>
> It seems that the UVs are Half Float but the Mesh is Short All.Aaaaaaaaargh, yeah, I always forget about that.

> Any way to do this with hex2obj?save the mesh in two ways, first as ShortAll then as HF_UV (or HF_all). In the first obj do a replacement of 'vt' by '#vt'. 
In the (HF_UV) obj do a replacement of 'v ' by '#v '. Don't forget the space here.

Then copy all vts (without the face indices) into the (ShortAll) obj.
(Yeah, pretty annoying, I know.)

Why not adapt GhostBLade's script for QfB? Should not be too hard.
## Post #54
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2015-05-16T13:59:14+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

> Reply from shakotay2
>
> Why not adapt GhostBLade's script for QfB? Should not be too hard.

I tried, but I just don't understand any of it. 

Ah well i'm fine with doing things this way. Thanks again shakotay!
## Post #55
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2016-03-06T20:28:41+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

So I was messing around with Gh0stBlade's script and I think I almost got bone weights to work.
About 95% of the model seems to have the correct weights and i'm not sure how to fix that.

I was using this model
[https://www.dropbox.com/s/72hkiq3byhkrj ... 1.irb?dl=0](https://www.dropbox.com/s/72hkiq3byhkrjzh/ratchet_nc1.irb?dl=0)

and the line I changed was
rapi.rpgBindBoneWeightBuffer(vertBuff, noesis.RPGEODATA_HALFFLOAT, 0x1C, 0xC)

to
rapi.rpgBindBoneWeightBuffer(vertBuff, noesis.RPGEODATA_FLOAT, 0x1C, 0x2)

I would really like some help with this as I have absolutely no idea what I am doing.
## Post #56
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-03-09T23:27:20+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

> Reply from o0DemonBoy0o
>
> So I was messing around with Gh0stBlade's script and I think I almost got bone weights to work.
About 95% of the model seems to have the correct weights and i'm not sure how to fix that.

I was using this model
https://www.dropbox.com/s/72hkiq3byhkrj ... 1.irb?dl=0

and the line I changed was
rapi.rpgBindBoneWeightBuffer(vertBuff, noesis.RPGEODATA_HALFFLOAT, 0x1C, 0xC)

to
rapi.rpgBindBoneWeightBuffer(vertBuff, noesis.RPGEODATA_FLOAT, 0x1C, 0x2)

I would really like some help with this as I have absolutely no idea what I am doing.
Hmm that's not correct unfortunately. The first mesh type has an issue with weighting. This is because there is no bone index information within the vertex data. I'm guessing they did something else to animate those parts of the models.
## Post #57
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2016-03-15T08:06:03+00:00
- Post Title: Re: [Request]Ratchet & Clank: into the Nexus

> Reply from Gh0stBlade
>
> 
Hmm that's not correct unfortunately. The first mesh type has an issue with weighting. This is because there is no bone index information within the vertex data. I'm guessing they did something else to animate those parts of the models.
Ah, that's unfortunate. It looks like Type 1 meshes are usually bound to a single bone anyway so it's not that hard to fix.

Speaking of animations, would it be possible to get those in a usable format?

Here are some samples from ToD and CiT
[https://www.dropbox.com/s/337auj05gman0 ... m.zip?dl=0](https://www.dropbox.com/s/337auj05gman04k/ToDAnim.zip?dl=0)
[https://www.dropbox.com/s/u89do5340pa2s ... m.zip?dl=0](https://www.dropbox.com/s/u89do5340pa2ssm/CiTAnim.zip?dl=0)

And irb files for the characters if needed
[https://www.dropbox.com/s/8c2o7itdo2fg6 ... B.zip?dl=0](https://www.dropbox.com/s/8c2o7itdo2fg6fm/ToDIRB.zip?dl=0)
[https://www.dropbox.com/s/gyxub0fnwu4a7 ... B.zip?dl=0](https://www.dropbox.com/s/gyxub0fnwu4a7vh/CiTIRB.zip?dl=0)


I also changed the bind weight buffer again to 
rapi.rpgBindBoneWeightBuffer(vertBuff, noesis.RPGEODATA_UBYTE, 0x1C, 0x1)

And it seems to work for the most part



ratchet.png (133.09 KiB) Viewed 237 times
