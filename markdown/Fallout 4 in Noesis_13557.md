## Post #1
- Username: artworkplay
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-11-22T03:11:53+00:00
- Post Title: Fallout 4 in Noesis

Noesis v4.171 has support for Fallout 4 archives/textures/NIFs. I guess people have been working on this stuff for weeks/months already, but no one is sharing anything, so here's what I got after half a day.
 
 
There'll certainly be stuff that's unimplemented/unsupported still, but I don't plan on working on this anymore until I actually finish playing the game myself.  If you've been secretly working on this and have more info than I do, please feel free to help out. The Noesis NIF implementation is in Python, so all of this is already open to anyone. There's certainly enough there to write a usable exporter (just pick a vertex format and reuse the flags) so that the awful monsters making their furry nude mods don't have to use a hex editor anymore.

In order to get everything working like it should, you should extract all of the texture archives to a common directory like so:

Once this is done, you'll have something over 20 gigs of loose textures sitting there. Now point Noesis at the directory you extracted the textures to (and the Textures directory under it, as NIF's seem to like using relative paths on both) for its automatic texture loading, like so:


Once you've done this, the textures will be auto-loaded for albedo/normal/etc. Additionally, many character models have a flattened skeleton, and reference another file (usually called skeleton.nif) with proper hierarchy. The skeleton in those models will look like this:

To address this, use -nifloadskel <filename> (where filename would be the full path to the appropriate file, like skeleton.nif) and you'll get this instead:


Ok then, have fun.
## Post #2
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-11-22T06:15:23+00:00
- Post Title: Fallout 4 in Noesis

When MrAdults surprises, he surprises big. Thank you sir for this awesome addition to Noesis.
## Post #3
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2015-11-22T14:30:23+00:00
- Post Title: Fallout 4 in Noesis

Amazing work!!! Now i can create a proper animation rig with good geometry  thank you so much
## Post #4
- Username: jimhsu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 08, 2015 3:17 am
- Post datetime: 2015-11-22T16:26:52+00:00
- Post Title: Fallout 4 in Noesis

Oh nice. I've been on all the major TES/FO forums watching this stuff. An exporter would definitely be of great public interest.

What format are you extracting the normals/speculars to - ATI2N?
## Post #5
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2015-11-22T17:19:07+00:00
- Post Title: Fallout 4 in Noesis

Thank you for this! Works like a charm.
There's just one thing unclear to me. Where can i find the function to use "-nifloadskel <filename>"? 
I mean how could i open a mesh with parameters such as this? Is there a button or flag i missed?
Thanks again!
## Post #6
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-11-22T19:53:01+00:00
- Post Title: Fallout 4 in Noesis

> Reply from TheMask85
>
> Thank you for this! Works like a charm.
There's just one thing unclear to me. Where can i find the function to use "-nifloadskel <filename>"? 
I mean how could i open a mesh with parameters such as this? Is there a button or flag i missed?
Thanks again!
You can add the function to the Data Viewer Default preview commands respectively export it as well with Advanced options set to that function.
## Post #7
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-11-22T23:06:29+00:00
- Post Title: Fallout 4 in Noesis

> Reply from jimhsu
>
> Oh nice. I've been on all the major TES/FO forums watching this stuff. An exporter would definitely be of great public interest.

What format are you extracting the normals/speculars to - ATI2N?
The archive itself stores the image information including the DXGI format, so when I'm writing out the DDS files, I'm just constructing DX10 headers and relaying the DXGI format directly.

When Noesis loads DX10 DDS files, it's still assuming that BC5 wants to have z derived followed by renormalization, which is only right if it's a normal map. They're using BC5 a lot to store roughness/smoothness + metalness, so Noesis is trying to normalize those things. I'll get a fix out for that momentarily.

They're also using BC5 to store single-channel spec maps where green and red are the same, which makes no sense at all. They should be using BC4 for those, but typically aren't. It would be exactly the same data at half the size.

Edit: 4.172 is up, which adds a -ddsati2nonorm command. Like artworkplay mentioned above, you can specify it when exporting or as part of your default preview command list. It's safe to always use this option for Fallout 4, because Noesis already derives z using the non-splayed method and renormalizes in its lighting shaders when sampling normal maps. So it will still handle all of the normal maps correctly, and it will stop trying to treat spec/roughness/metalness as normals.
## Post #8
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2015-11-23T00:08:34+00:00
- Post Title: Fallout 4 in Noesis

Half a day, that's impressive.

> but no one is sharing anything
Thank you for sharing the code, when you could have just done the same as the other people.
## Post #9
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2015-11-23T00:46:41+00:00
- Post Title: Fallout 4 in Noesis

Trying to load the full human skeleton before loading any parts like MaleBody.nif is just not working for me.

I tried adding ( -nifloadskel FULLPATH ) to the default commandline when starting the preview and also as export option, any idea why?
## Post #10
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-11-23T03:58:56+00:00
- Post Title: Fallout 4 in Noesis

> Reply from Highflex
>
> Trying to load the full human skeleton before loading any parts like MaleBody.nif is just not working for me.
-nifloadskel remaps hierarchy, as you can see:

```
			if object.isBone is True:
				if object.name in skelNifBoneObjects:
					skelObject = skelNifBoneObjects[object.name]
					#see if the parent is also a bone, and if so, transfer the parent index
					if skelObject.parentIndex >= 0:
						skelParentObject = skelNif.objects[skelObject.parentIndex]
						if skelParentObject.isBone and skelParentObject.name in nifBoneObjectIndicesByName:
							#for now, we only transfer transforms for non-root objects. otherwise, we'd need to transform up the hierarchy before grabbing,
							#in case there are parents in the skeleton nif not reflected in the nif we're mapping to.
							object.matrix = skelObject.matrix
							object.scale = skelObject.scale
							object.parentIndex = nifBoneObjectIndicesByName[skelParentObject.name]
```

It doesn't import new skeleton nodes or rebase root transforms for hierarchies not present in the destination nif. (which you wouldn't really want for what you're probably trying to do anyway, you want to keep the relative transform intact) If you want to piece together parts on a skeleton, it's easiest to just export them all and the skeleton separately as something like FBX, then plant the pieces onto the skeleton (match by node names) in your modeler of choice. Also keep in mind -nifnotransform for any geometry you're exporting that doesn't contain the necessary nodes for skinning.

> Reply from Bastien
>
> Half a day, that's impressive.
Yeah, when I tried to google for BSTriShape to see if someone else might've already done some work on it, I saw a lot of people saying they "totally redid the NIF format", which is a load of nonsense. As you can see in the Noesis script, the core of what's new there is just a few object types, including a couple of new (and much simpler) shape objects with embedded geometry data. The new bone reference and inverse pose data is very minimal too. Even the material system has very few meaningful changes that depart from Skyrim, with the majority of the core material values and the texture sets remaining mostly the same despite the addition of PBR. So as much as I love to make people think I'm smarter than I am, there wasn't much new stuff to be done.
## Post #11
- Username: dracosfire83
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 13, 2015 7:48 am
- Post datetime: 2015-11-23T08:07:42+00:00
- Post Title: Fallout 4 in Noesis

Love the work you put into this but I do have one question. Is there anyway to export the file with the textures still intact?
## Post #12
- Username: throttlekitty
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 24, 2015 1:18 pm
- Post datetime: 2015-11-24T05:24:40+00:00
- Post Title: Fallout 4 in Noesis

Thanks for sharing, MrAdults, you knocked that out quick!

NifSkope has an update for fo4 now as well if you wanted to take a look.
[http://niftools.sourceforge.net/forum/v ... =31&t=6305](http://niftools.sourceforge.net/forum/viewtopic.php?f=31&t=6305)

Also, my working code/math skills are pretty low, I really don't understand how you're handling inverse skin transforms. (that's what led me to this thread) Looking at your py, you seem to move the verts instead of a global mesh transform, is that right?
## Post #13
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-11-24T14:46:39+00:00
- Post Title: Fallout 4 in Noesis

No mention of Noesis, that's a shame. Have to wonder about the timing, especially given how simple and obvious the vertex flags are, but that's the only thing he seems to be having trouble with and the only thing I didn't bother fleshing out and documenting in the script. Maybe just a coincidence, I suppose.

All Noesis is doing with the bindpose mats is moving the actual bind pose to match the node space. Since it converts the position data up to 32 bits in the process, there's no reason for the bind pose given to exist anymore. This means that the node space pose now equals the bind pose. The ideal bind pose can also easily be recalculated on export by fitting joints into a more ideal precision range for FP16, then transforming geo with (newInvBindPose * fittedPose).
## Post #14
- Username: devilblades
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Nov 24, 2015 11:56 pm
- Post datetime: 2015-11-24T16:04:34+00:00
- Post Title: Fallout 4 in Noesis

This is my 1st time using Noesis, I see the models, and exporting textures right now. But I do have a question, under the Power armor folder, all the files are 1K  How do I load the power armor like you did? I would like to get the helmet that is on the cover of the game. I just need a little help finding that, and the rest of the armor for it. Thank you.
## Post #15
- Username: jonwd7
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 25, 2015 5:51 am
- Post datetime: 2015-11-24T22:55:49+00:00
- Post Title: Fallout 4 in Noesis

> Reply from MrAdults
>
> No mention of Noesis, that's a shame. Have to wonder about the timing, especially given how simple and obvious the vertex flags are, but that's the only thing he seems to be having trouble with and the only thing I didn't bother fleshing out and documenting in the script. Maybe just a coincidence, I suppose.
Why would we mention you?  We had no idea what Noesis was until after we already had 99% of files parsing, and I had models loading in NifSkope [over a week ago](http://afkmods.iguanadons.net/index.php?/topic/4136-nifskope-20-dev/?p=158077). ([Link #2](http://niftools.sourceforge.net/forum/viewtopic.php?f=10&t=6295#p31864))   In fact, we were pretty sure you were simply working off of our 010 templates, which were publicly pushed to GitHub daily since the 11th, hence extremely easy for you to find with a code search.  (You admitted to searching for 'BSTriShape' for example.) 

I don't know what you're referring to me having trouble with exactly.  It seems like you're talking about vertex flags, but I know that you couldn't possibly be.  You're not handling them correctly either.   I checked out certain problem meshes and you assumed many things incorrectly.   The vertex flags are not simple OR obvious.  Look at maleeyesshade.nif  in Actors/Character/CharacterAssets/FaceParts.  You get that one totally wrong, assuming the body has normals for example.   We've analyzed all the vertex flags with 010 and there are 17 unique vertex flags across all NIF files.  Currently nif.xml only handles most of them, not because we don't know how to handle the outliers (we do), but because doing so would make nif.xml very messy.  

Anyway, since we found out about this,  we've found your pompous attitude very offputting, so I personally don't have a desire to interface with you any further.  Your figuring out *anything* in a "half a day" was highly suspect too, since we'd already published everything by that point.   From our point of view,  you don't seem to know anything we didn't know a week ago,  save for displaying skinned models correctly.  And at least for me that's simply because I know nothing about skinning and haven't even bothered to look into it.  Figment on the other hand had skinned models imported into 3ds Max long before your Noesis update too.   

I think maybe what you're not understanding is that what you've done in "half a day" is fine for Noesis, but not for the actual tools.  We need to treat the format rigorously, and it's clear you're not doing so.  Doing things correctly takes time, and we took longer to release because we were doing the responsible thing by not handing out tools which will create broken NIFs. 

I guess before I go I'll leave you with a quiz regarding the vertex format:

```
  2: 02 00 00 00 | 00 10 00 00 | 00000010 00000000 00000000 00000000 | 00000000 00010000 00000000 00000000
  3: 03 00 02 00 | 00 90 00 00 | 00000011 00000000 00000010 00000000 | 00000000 10010000 00000000 00000000
  3: 03 02 00 00 | 00 30 00 00 | 00000011 00000010 00000000 00000000 | 00000000 00110000 00000000 00000000
  4: 04 00 02 03 | 00 90 02 00 | 00000100 00000000 00000010 00000011 | 00000000 10010000 00000010 00000000
  4: 04 02 00 03 | 00 30 02 00 | 00000100 00000010 00000000 00000011 | 00000000 00110000 00000010 00000000
  4: 04 02 03 00 | 00 b0 00 00 | 00000100 00000010 00000011 00000000 | 00000000 10110000 00000000 00000000
  5: 05 02 03 04 | 00 b0 02 00 | 00000101 00000010 00000011 00000100 | 00000000 10110000 00000010 00000000
  5: 05 02 43 00 | 00 b0 01 00 | 00000101 00000010 01000011 00000000 | 00000000 10110000 00000001 00000000
  6: 06 02 00 30 | 00 30 04 00 | 00000110 00000010 00000000 00110000 | 00000000 00110000 00000100 00000000
  6: 06 02 43 05 | 00 b0 03 00 | 00000110 00000010 01000011 00000101 | 00000000 10110000 00000011 00000000
  7: 07 02 00 43 | 00 30 06 00 | 00000111 00000010 00000000 01000011 | 00000000 00110000 00000110 00000000
  8: 08 02 43 50 | 00 b0 05 00 | 00001000 00000010 01000011 01010000 | 00000000 10110000 00000101 00000000
  8: 08 02 43 50 | 20 b0 05 00 | 00001000 00000010 01000011 01010000 | 00100000 10110000 00000101 00000000
  9: 09 02 43 65 | 00 b0 07 00 | 00001001 00000010 01000011 01100101 | 00000000 10110000 00000111 00000000
  9: 09 02 43 65 | 20 b0 07 00 | 00001001 00000010 01000011 01100101 | 00100000 10110000 00000111 00000000
 10: 0a 02 43 65 | 90 b0 17 00 | 00001010 00000010 01000011 01100101 | 10010000 10110000 00010111 00000000
```

(1st number is the first byte of the flags in dec.  Rest is 8 bytes of flags in hex and binary)

1)  Which format is found exclusively in male eyes?
2)  Which format(s) are exclusive to BTR files?
3)  Which formats have normals but no tangents?
4)  Which formats are found only in files under /facegeom/?
5)  Which format has normals, no tangents, and vertex colors?
6)  Which formats describe a half float after the vertex, and which have a ushort instead?

And a lightning round question:

1)  Do you know where the bitangent is located?  (Hint:  It's a doozy)

... and no cheating.  Some of this information is already public!  


P.S.  Don't flatter yourself,  I haven't looked at your source.  I'm not sure if our IRC logs are available somewhere, but they will attest to that.  I'll let you know if our IRC logs are available somewhere and you will be free to look over the past two weeks and see for yourself that you had absolutely zero to do with our work.
## Post #16
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-11-24T23:30:13+00:00
- Post Title: Re: Fallout 4 in Noesis

> Reply from jonwd7
>
> In fact, we were pretty sure you were simply working off of our 010 templates, which were publicly pushed to GitHub daily since the 11th, hence extremely easy for you to find with a code search.  (You admitted to searching for 'BSTriShape' for example.)
[https://www.google.com/?gws_rd=ssl#q=%22BSTriShape%22](https://www.google.com/?gws_rd=ssl#q=%22BSTriShape%22)
Oh, is that so? Sure don't see your article there! And no, I haven't seen any of your templates or any reference material, or I would've happily credited you as I credit everyone in the Noesis readme.txt any time I use any of their material.

> Reply from jonwd7
>
> I don't know what you're referring to me having trouble with exactly.  It seems like you're talking about vertex flags, but I know that you couldn't possibly be.  You're not handling them correctly either.
I explicitly noted that the current public release doesn't do this, and that your post, linked above, explicitly mentions you haven't got it figured it out. I don't see how you couldn't have it figured out if you spent more than a day with the format, you simply need to take the time to go through and relate the flags being used to known vertex buffer configurations, and xor'ing flags between known buffers makes this pretty easy.

> Reply from jonwd7
>
> The vertex flags are not simple OR obvious.
Yes they are. 

> Reply from jonwd7
>
> We've analyzed all the vertex flags with 010 and there are 17 unique vertex flags across all NIF files.
That's not very many, as model formats go.

> Reply from jonwd7
>
> Anyway, since we found out about this,  we've found your pompous attitude very offputting, so I personally don't have a desire to interface with you any further.
I merely pointed out the questionable timing and the fact that your above linked post mentions issues with the things I didn't bother spec'ing out in the script. You're the one being a total asshole here instead of simply posting and saying "Nope, just coincidence - no hard feelings."

> Reply from jonwd7
>
> Your figuring out *anything* in a "half a day" was highly suspect too, since we'd already published everything by that point.
Oh, horse shit. I've reverse engineered games 1000 times more complex than this. These NIF chunks were incredibly simple to eyeball.

> Reply from jonwd7
>
> From our point of view,  you don't seem to know anything we didn't know a week ago,  save for displaying skinned models correctly.  And at least for me that's simply because I know nothing about skinning and haven't even bothered to look into it.
Well, congratulations, I guess? I certainly didn't find it by googling.

> Reply from jonwd7
>
> I think maybe what you're not understanding is that what you've done in "half a day" is fine for Noesis, but not for the actual tools.  We need to treat the format rigorously, and it's clear you're not doing so.
I'm glad you've suddenly decided to believe my timeline now. Your release is already pretty half-assed and incomplete, apparently, so I don't see how that's at all "rigorous" either.

> Reply from jonwd7
>
> I guess before I go I'll leave you with a quiz regarding the vertex format:
This is another load of horse shit. You wouldn't have approached this thread in the way you have if you weren't a complete tool, so I'm not going to answer questions to "prove" anything to you when the catalog of hundreds of more complex games I've reversed speaks pretty well for me.

> Reply from jonwd7
>
> ... and no cheating.  Some of this information is already public!
God, you're an idiot.

> Reply from jonwd7
>
> P.S.  Don't flatter yourself,  I haven't looked at your source.
Based on your psychotic reaction, either you have severe Asperger's, or you're lying. I'm willing to believe the former, I suppose.

> Reply from jonwd7
>
> I'm not sure if our IRC logs are available somewhere, but they will attest to that.  I'll let you know if our IRC logs are available somewhere and you will be free to look over the past two weeks and see for yourself that you had absolutely zero to do with our work.
I guess at least I can get an ego boost out of multiple people spending two weeks on something that took half a day, then?
## Post #17
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-11-24T23:49:10+00:00
- Post Title: Re: Fallout 4 in Noesis

And if you want to talk about something that should take 2 weeks, this shit should take 2 weeks: [http://www.richwhitehouse.com/index.php?postid=68](http://www.richwhitehouse.com/index.php?postid=68) And it did. In real life time, anyway. I have a job and a family.

A few new, incredibly small, NIF objects? Yeah, no, not 2 fuckin' weeks. So I could accept the possibility that you didn't actually look at the Noesis script, but you're just making it harder with your reaction. But I can also accept that you're just butthurt because you spent a lot of time on it because you're new to this. So that's fine too. I reserve my judgment there, so don't make me hate you any more than I already do.
## Post #18
- Username: throttlekitty
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 24, 2015 1:18 pm
- Post datetime: 2015-11-25T01:48:09+00:00
- Post Title: Re: Fallout 4 in Noesis

> Reply from MrAdults
>
> No mention of Noesis, that's a shame. Have to wonder about the timing, especially given how simple and obvious the vertex flags are, but that's the only thing he seems to be having trouble with and the only thing I didn't bother fleshing out and documenting in the script. Maybe just a coincidence, I suppose.

I hadn't heard of it until a few days ago, pretty neat app you've got, It's something I sure could've used a few years ago.

> All Noesis is doing with the bindpose mats is moving the actual bind pose to match the node space. Since it converts the position data up to 32 bits in the process, there's no reason for the bind pose given to exist anymore. This means that the node space pose now equals the bind pose. The ideal bind pose can also easily be recalculated on export by fitting joints into a more ideal precision range for FP16, then transforming geo with (newInvBindPose * fittedPose).

I *think* I get it now, thanks. NifSkope has similar code already for the previous formats, but the inverse was stored directly prior to fo4 and I think we just ran off that.

jon are you being fucking serious right now. I see how his tone is boastful but certainly not threatening. clam yo tits.
Sure, we aim for a more complete/proper tool, but Noesis isn't necessarily that. Just pointing out that we had verts down pretty quick too but ran around trying to figure out what all the off-cases were with the flags.
## Post #19
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-11-25T02:17:57+00:00
- Post Title: Re: Fallout 4 in Noesis

> Reply from throttlekitty
>
> I *think* I get it now, thanks. NifSkope has similar code already for the previous formats, but the inverse was stored directly prior to fo4 and I think we just ran off that.
Yeah, it's a pretty traditional Gamebryo concept (you'll notice the other geo paths in Noesis do similar things too), but it's particularly important in FO4 for the bind pose to be centered at 0 to make the best use of FP16 precision. It seems they decided to capitalize on the cruel Gamebryo legacy of "EVERYTHING HAS A TRANSFORM", which was not a bad idea at all.  They could have squeezed even a bit more precision out of it by relying on a non-uniform bind pose in order to quantize to FP16 with maximum precision utilization, then bake that inverse non-uniform transform right into the pose matrices so it would be back in uniform space by the time you concatenated anything to the transform. But they seem to have done pretty well either way, I didn't see any nasty cracks or anything as a result of FP16 positions and it's an elegant way to handle the need for a scale + bias.

> Reply from throttlekitty
>
> jon are you being fucking serious right now. I see how his tone is boastful but certainly not threatening. clam yo tits.
Sure, we aim for a more complete/proper tool, but Noesis isn't necessarily that. Just pointing out that we had verts down pretty quick too but ran around trying to figure out what all the off-cases were with the flags.
Oh, I didn't realize you worked on this as well. That eases my initial suspicion, as you don't seem at all like a flaming dickface.
## Post #20
- Username: throttlekitty
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 24, 2015 1:18 pm
- Post datetime: 2015-11-25T03:26:59+00:00
- Post Title: Re: Fallout 4 in Noesis

> Reply from MrAdults
>
> Yeah, it's a pretty traditional Gamebryo concept (you'll notice the other geo paths in Noesis do similar things too), but it's particularly important in FO4 for the bind pose to be centered at 0 to make the best use of FP16 precision. It seems they decided to capitalize on the cruel Gamebryo legacy of "EVERYTHING HAS A TRANSFORM", which was not a bad idea at all.  They could have squeezed even a bit more precision out of it by relying on a non-uniform bind pose in order to quantize to FP16 with maximum precision utilization, then bake that inverse non-uniform transform right into the pose matrices so it would be back in uniform space by the time you concatenated anything to the transform. But they seem to have done pretty well either way, I didn't see any nasty cracks or anything as a result of FP16 positions and it's an elegant way to handle the need for a scale + bias.

I'm used to seeing it for heads because of the prior use of FaceGen, but they aren't really using that now. NetImmerse/Gamebryo files have always been considered 'scene snapshots' rather than 'just a model'. One game had title/main menu/options/char select in a single big .nif, which was a... creative use after seeing most games done modular.

I've spoken with others who complained that their games had big FP seam issues on large meshes, I was surprised to see Bethesda do it, given their style.

> Oh, I didn't realize you worked on this as well. That eases my initial suspicion, as you don't seem at all like a flaming dickface.

Honestly I've done little for this round, they had the easy stuff done before I had the time or game. (again with the lack of proper skills for much of this, I'm more an artist, and less protective of my work/discoveries) I'll probably spend the weekend horsing around with shader flags and values.
## Post #21
- Username: Relzaz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 28, 2015 8:57 pm
- Post datetime: 2015-11-28T17:51:42+00:00
- Post Title: Re: Fallout 4 in Noesis

hello, i am new ( and i don't speak english very well) i want to have the armor model but  i don't know how to find it .
If   someone can help me i will be very happy
## Post #22
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-11-28T22:58:58+00:00
- Post Title: Re: Fallout 4 in Noesis

> Reply from Relzaz
>
> hello, i am new ( and i don't speak english very well) i want to have the armor model but i don't know how to find it .
If someone can help me i will be very happy
If you're talking about the one in the screenshot, it's just one of the loading screen models.

> Reply from throttlekitty
>
> I'm used to seeing it for heads because of the prior use of FaceGen, but they aren't really using that now. NetImmerse/Gamebryo files have always been considered 'scene snapshots' rather than 'just a model'. One game had title/main menu/options/char select in a single big .nif, which was a... creative use after seeing most games done modular.
The significant downside of (ab)using the bind transform in this way is that it adds another step to the transform process. A lot of older games, and even some newer ones (the popular example is Doom 3) will put skinned verts in local space so that the need to compute a skinning matrix from the inverse bind pose is eliminated, making the "bind" pose is effectively identity. When normals/etc. come along for the ride, this represents a further deterioration if you're just doing a linear transform, though.

> Reply from jonwd7
>
> 1) Do you know where the bitangent is located? (Hint: It's a doozy)
I just noticed this one when this thread got juggled back up. Now, I haven't even looked back at FO4 (I meant it when I said I wasn't going to work on it again until I fnished playing it, and then the Bloodborne DLC came out), but pretty much no one stores binormals/bitangents, and we always store the sign to restore after the CP. Typically in the position, normal, or tangent w, but it can be anywhere you feel like packing it. This behavior is so common that Noesis supports it by default (and has for years), along with a variety of flipping and transform modes, when providing the tan4 type. So I really hope that's what you thought was a "doozy".  Additionally, it's also very common to use one of the specialized formats like 10-10-10-2 to maximize precision and store the sign in 2 bits. Noesis also supports a variety of these types natively. The world, shockingly, doesn't consist only of Bethesda games, so, welcome to 3D graphics circa 2006. Medium fish, tiny pond.

Sorry, had to get that off my chest, just glancing through that pile of ignorance-arrogance special-blend again was irritating.
## Post #23
- Username: Relzaz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 28, 2015 8:57 pm
- Post datetime: 2015-11-29T13:29:07+00:00
- Post Title: Re: Fallout 4 in Noesis

I finally understand  =     
Thanks
## Post #24
- Username: Relzaz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 28, 2015 8:57 pm
- Post datetime: 2015-11-29T16:00:36+00:00
- Post Title: Re: Fallout 4 in Noesis

actually I don't understand...
## Post #25
- Username: devilblades
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Nov 24, 2015 11:56 pm
- Post datetime: 2015-12-06T17:49:31+00:00
- Post Title: Re: Fallout 4 in Noesis

So, not all of my textures are loading any idea what is going on, or how to get them all to load? Here is an example, some textures will load, while others wont.
## Post #26
- Username: throttlekitty
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 24, 2015 1:18 pm
- Post datetime: 2015-12-07T03:06:17+00:00
- Post Title: Re: Fallout 4 in Noesis

Check your texture pathing? file paths sometimes start with textures\ and sometimes they don't. (ie textures\cat\catbody.dds vs cat\catbody.dds)
## Post #27
- Username: yukitairo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 14, 2014 9:46 pm
- Post datetime: 2015-12-13T21:18:05+00:00
- Post Title: Re: Fallout 4 in Noesis

Thanks! For this, but idk what's the problem here?



That happens with every models when I use the -nifskel thing
## Post #28
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-12-15T11:07:22+00:00
- Post Title: Re: Fallout 4 in Noesis

Regarding no textures, what throttlekitty said, or they're just unhandled material refs. Regarding the skeleton error, try an absolute path.
## Post #29
- Username: yukitairo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 14, 2014 9:46 pm
- Post datetime: 2015-12-15T23:29:51+00:00
- Post Title: Re: Fallout 4 in Noesis

thanx, but..yea I'm kinda new to noesis. lol
absolute path?
## Post #30
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-01-18T09:35:09+00:00
- Post Title: Re: Fallout 4 in Noesis

I was pleasantly surprised to see Noesis had support for Fallout 4 so quickly. Awesome job. 

I did run into a curious problem though. I exported a model from Noesis in FBX format, and tried to load it into Blender using their FBX importer. However, their Importer is complaining about the FBX version. The error says "Version 6100 not supported, Must be 7100 or later."

Is there an easy way to change an FBX's version #, or can Noesis save in newer FBX formats?  Thanks
## Post #31
- Username: volfin
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-01-19T04:19:19+00:00
- Post Title: Re: Fallout 4 in Noesis

I'd consider that a failing of the blender importer, but you can use 
> -fbxnewexport - exports current fbx format instead of legacy.
## Post #32
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-01-26T08:10:04+00:00
- Post Title: Re: Fallout 4 in Noesis

I notice that Noesis importer crashes on any meshes generated by the Fallout 4 version of Bodyslide: 

[http://www.nexusmods.com/fallout4/mods/25/](http://www.nexusmods.com/fallout4/mods/25/)?

Meshes usually crash with this error:
Detected file type: Gamebryo NIF
NIF version: 20 2 0 7
User version: 0 0 0 12
FO4 mode.
An error occurred when parsing the type table, trying to find it manually.
Found Ni: 155
Traceback (most recent call last):
  File "D:\Unpackers\Noesis\plugins\python\fmt_gamebryo_nif.py", line 2131, in nifLoadModel
    mdl = nifConstructModelFromNif(nif)
  File "D:\Unpackers\Noesis\plugins\python\fmt_gamebryo_nif.py", line 2081, in nifConstructModelFromNif
    nif.rpgCommitBsShapes(noeBones, bindCorrectionBones, noeMatList, noeTexList)
  File "D:\Unpackers\Noesis\plugins\python\fmt_gamebryo_nif.py", line 1917, in rpgCommitBsShapes
    rapi.rpgCommitTriangles(triShape.triData, noesis.RPGEODATA_USHORT, triShape.numTris * 3, noesis.RPGEO_TRIANGLE, 1)			
RuntimeError: Position buffer would have been read out of bounds by provided indices.

I'm guessing Bodyslide does something a bit non-standard for it's output. FYI
## Post #33
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-28T11:33:39+00:00
- Post Title: Re: Fallout 4 in Noesis

> Reply from volfin
>
> I notice that Noesis importer crashes on any meshes generated by the Fallout 4 version of Bodyslide: 
[..]
I'm guessing Bodyslide does something a bit non-standard for it's output. FYIBodyslide doesn't come with nifs/meshes - it uses those from the CBBE mod for example.
Which nif did you use?

I used FemaleBody.nif (curvy) from CBBE (without using BodySlide) and got this error in Noesis:
RuntimeError: Index buffer was not valid for drawing.

So I assume it's not (only) caused by the BodySlide changes but by the nifs themselves (just a wild guess).

Anyway, the mesh in the nif from CBBE is simple to load (UVpos offset is 8 ):



FemaleBody(curvy).jpg (173.65 KiB) Viewed 336 times



So it would be really helpful if you uploaded a sample nif which you modified using BodySlide.

The script calculates vertSize= 20 for this nif.
While FVFsize is 726656 (vertDataSize?) / 22708 vertices = 32 but dunno if vertSize is meant to be the same.

yep, this works. (Maybe gpuBufferSize was set wrongly in the nif?)
## Post #34
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-01-30T00:31:02+00:00
- Post Title: Re: Fallout 4 in Noesis

Yes, Bodyslide doesn't come with it's own meshes, but it generates meshes based on your body slider settings. Those generated meshes wont' load, for any outfit I've tried.  Here's an example of the pre-war dress which was processed by Bodyslide.

[http://sta.sh/0iu65ddj9lt](http://sta.sh/0iu65ddj9lt)
## Post #35
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-30T10:29:53+00:00
- Post Title: Re: Fallout 4 in Noesis

thx. For the 3rd submesh a problem arises as described above.
If you can't wait for Rick's fix you can try this ugly patch (works for a vertSize of 32 only!):

```
        #[...]
        indexDataSize = 2 * 3 * self.numTris
        vertDataSize = self.gpuBufferSize - indexDataSize
        self.vertSize = vertDataSize // self.numVerts

        if self.vertSize != 32:
                self.vertSize = 32
                vertDataSize = self.numVerts*self.vertSize
```

(as always with python: pay attention to the indents!)



PrewarDress_nif.JPG (27.92 KiB) Viewed 316 times
## Post #36
- Username: volfin
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-01-31T11:07:46+00:00
- Post Title: Re: Fallout 4 in Noesis

I've had FO4 on hold for a while, feeling that it's generally quite pointless as I've lost most motivation to share any improvements via script only to have any new discoveries quietly or indirectly leveraged by that jonwd twat. You'd just need to calculate the vertex size properly from those flags, which isn't a big problem, and if you really hate looking at vertex structures and using xor, supposedly that info is already public somewhere.

Having a fucked gpuBufferSize may not matter for PC, but it'll certainly break on PS4/XB1, so someone should tell the author of the software producing those broken NIF's to fix it.
## Post #37
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-02-08T19:18:51+00:00
- Post Title: Re: Fallout 4 in Noesis

Excuse me, but how it works with the skeletons? where I have to use the command?
## Post #38
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2016-02-12T05:34:27+00:00
- Post Title: Re: Fallout 4 in Noesis

ok, I get it, so... MR Adults isn't as disappeared as I believed since the closure of Señor Casaroja oasis or wathever it was the page where he used to show up his Noesis project, during that time even I only had received some fixes instead of support of new formats.

I may admit a mistake when doing, but perhaps if you would say something like "I won't quit from updating Noesis" on that post where I replied really pissed off about Noesis, I would not be embarrased right now!   

sometimes, I had to pay attention at Models Resource, because there they do something you don't (Ripping models from nintendo 3DS and Nintendo WiiU, even somebody has managed to get a few models from PS Vita)
all those freaking rules about no posting anything with copyright has become that this comunity is closed to as many interesting games and made me lost the dreams of having a bestiary of plenty of monsters/Creatures/Animals from the games I got my interest.

About Fallout 4, at least I can say... I will get that goddamn dog... FINALLY!!!!   

but honestly, maybe probably a little bit of contribution here and a little more there.
and not putting freaking rules about copyright stuff. and just only forbids any kind of nudity...
That's the only rule I will obey no matter what since I have nudities.
probably a plenty of nintendo and sony games will be decrypted.

at least, on Models Resource they weren't so strict, the only problem is that there's a very few people who are capable of doing
ripping.

I can only find two choices.

1- I would gladly be happy if you contribute by including support for formats the community of Models Resource had done so far like BCH, BRRES, BFRES, BRMDL and others in Noesis, instead of using programs that don't work and only fills Disk space for nothing.

or

2- the ones that had contributed on the ripping of models of computer games and are focusing on consoles, or the ones who had experience on complex formats that requires on QUICKBMS/Python/3ds Max scripts, contribute to help on Models Resource as well.
because it seems we had lost about over a half of the help we would need.

It's only a petition, Maybe it sounds rude, but honestly. I got tired of just waiting months just to rely only on unfinished projects.
if I were to know about that *censored* stuff of C,C+,C#,Lua, and other languages. I wouldn't be here saying *censored* about this. 
the main problem is that Xentax had become too strict that if I ever send ripped stuff from a game like Five nights at freddy's, I get permabanned for violating a rule of copyright.

I was interested of sending TO YOU... Models of TORIKO GOURMET SURVIVAL for PSP. And you know what? Is copyrighted.
so the question is... WHY?, Why shouldn't I have Toriko Gourmet survival models ripped, Rigged and ready to use them?
Just because of an evil thing that is called... COPYRIGHT... Becuz you all are TOO scared of that thing. believing you'll burn on the eternal flames of hell for just ripping models from a game that is flagged as copyrighted.

Since when Xentax had become like Youtube?

So I hope you really understand this, MR Adults. Why I am so pissed off with all those delays from getting models. specially from stuff I was expecting so much like J Star Victory VS, Diablo 3, Kingdom Hearts Dream Drop Distance, Atlantica Online, Ether Saga Online, and so on.
I cannot life just of thin air, and I waited 10 months for a thing that might sound irrelevant and I won't tell it, but is really
related with the reason behind getting models from those games, because I cannot get it on Real Life anymore.
Just the only thing you must know is, I must get ALL the monster/animal/creature models from as many games as possible. that's all.
## Post #39
- Username: RoadTrain
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-02-12T12:56:42+00:00
- Post Title: Re: Fallout 4 in Noesis

> Reply from Farlavor
>
> sometimes, I had to pay attention at Models Resource, because there they do something you don't
Well, now, that simply isn't true. Noesis has even had support for a certain Vita game for about a year now. 

> Reply from Farlavor
>
> I was interested of sending TO YOU... Models of TORIKO GOURMET SURVIVAL for PSP. And you know what? Is copyrighted.
If it makes you feel any better, I wouldn't look at them anyway.

> Reply from Farlavor
>
> So I hope you really understand this, MR Adults. Why I am so pissed off with all those delays from getting models. specially from stuff I was expecting so much like J Star Victory VS, Diablo 3, Kingdom Hearts Dream Drop Distance, Atlantica Online, Ether Saga Online, and so on.
I'm sorry you've had to live such a tough life of waiting for people to do things for you.

> Reply from Farlavor
>
> I cannot life just of thin air, and I waited 10 months for a thing that might sound irrelevant and I won't tell it, but is really
related with the reason behind getting models from those games, because I cannot get it on Real Life anymore.
Just the only thing you must know is, I must get ALL the monster/animal/creature models from as many games as possible. that's all.
I'm not certain what you're trying to say here, but I think you should consider therapy.
## Post #40
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2016-02-12T15:58:07+00:00
- Post Title: Re: Fallout 4 in Noesis

@Farlavor Do you realize these guys have lives/jobs/responsibilities which aren't sitting around and babying you? You sound beyond entitled like they're here to service you - THEY AREN'T. Be happy that you're even a member and allowed to view anything without contributing. Be happy this isn't a closed source forum where you have to contribute to be a member. A petition to get someone to pay more attention to you specifically? Are you effin' serious? And of course they don't want to be legally reprimanded for the actions of idiots on the forums selling copyrighted material.

Please think before you post.
## Post #41
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-02-12T18:29:14+00:00
- Post Title: Re: Fallout 4 in Noesis

I ask for help MrAdults. I can not run the command to get the skeleton without any problems. you can write me an example of what COMPLETE must write?
## Post #42
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-02-21T18:35:12+00:00
- Post Title: Re: Fallout 4 in Noesis

I finally managed to get the models with skeletons. to do this we must fae as there all'nizio forum: C: \ FO4_INST \ Data \ Mehes \ and then put the path where the model skeleton. Now I have another problem. I was trying to take the robots can not figure out which is the right one. I get this error:
## Post #43
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-04-03T05:59:08+00:00
- Post Title: Re: Fallout 4 in Noesis

I'm looking for this model. you know where it is? [http://fallout.wikia.com/wiki/Unnamed_tank](http://fallout.wikia.com/wiki/Unnamed_tank)
## Post #44
- Username: Sakuraba
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Mar 14, 2016 4:23 am
- Post datetime: 2019-04-15T19:58:59+00:00
- Post Title: Re: Fallout 4 in Noesis

Someone has managed to get this, I have enough interest in getting it.
[FO76_Excavator_Power_Armor.jpg](https://xentaxbackup.github.io/file/16041_FO76_Excavator_Power_Armor.jpg)
## Post #45
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-07-08T00:50:26+00:00
- Post Title: Re: Fallout 4 in Noesis

Will there be Fallout 76 Support?
