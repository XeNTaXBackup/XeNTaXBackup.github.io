## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-01-15T18:13:27+00:00
- Post Title: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

Good evening fellow Xentax users! I have extracted a PS3 ISO of Splinter Cell Chaos Theory HD a while ago and got my hands on the Unreal Engine files for the static and skeletal meshes as well as the animations! 

The main problem in question is that Umodel is incompatible with Splinter Cell Chaos Theory, therefore I cannot import, export or preview any of the files...

Here is the list of file extensions:
Skeletal Meshes (with animations included): .ukx
Static Meshes: .usx
Textures: .utx

I uploaded all of my findings here:
[https://mega.nz/#!0d5WCQza!vNiNHY1bekti ... ZCSVQmV7gw](https://mega.nz/#!0d5WCQza!vNiNHY1bektibXPgxn1iJFO9idRDjsq9QZCSVQmV7gw)
[https://mega.nz/#!BVwQEIKD!_YEazQ97NeEA ... QYqFRztUQA](https://mega.nz/#!BVwQEIKD!_YEazQ97NeEA9mA_c8JWjZY2odGUhiKeXQYqFRztUQA)



Thank you for your attention and I am looking forward to all of your replies!
All the best, Xentax!
## Post #2
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-01-15T18:27:10+00:00
- Post Title: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

Update: I've managed to extract the .ukx files and got some files such as:
.MeshAnimation
.SkeletalMesh
.AnimNotify_Sound

I cannot seem to import them in Noesis, 3ds Max or anything though... Any ideas?

Here are samples from an extracted .ukx file:
[https://mega.nz/#!tcpDjCJS!dTRBjPmqyVO0 ... t-8KClnqrQ](https://mega.nz/#!tcpDjCJS!dTRBjPmqyVO02SgJLXbHJ9kPXh7XgBNb4t-8KClnqrQ)

> With a quick glance at "SamA.SkeletalMesh" I noticed this vertex/index block
>
> It seems like strip resets are required
>
> Integers before the index block might be related to that
## Post #3
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2020-01-16T13:37:40+00:00
- Post Title: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

Hey there,

Is there a reason you used the PS3 ISO? Does PC not work?

I have done research on a few ubisoft games that modify the animation format. "MeshAnimation" at first is the generic container for UE2 Animations, though its def modified. I wanted to go through the splinter cell games and add support for them, the research however is quite time consuming.
## Post #4
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-01-16T16:33:36+00:00
- Post Title: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from Highflex ↑Thu Jan 16, 2020 9:37 pm at Thu Jan 16, 2020 9:37 pm
>
> 
Hey there,

Is there a reason you used the PS3 ISO? Does PC not work?

I have done research on a few ubisoft games that modify the animation format. "MeshAnimation" at first is the generic container for UE2 Animations, though its def modified. I wanted to go through the splinter cell games and add support for them, the research however is quite time consuming.

Hey! The reason I chose PS3 out of all versions is due to how the archives are more 'open-source' than the other counterparts such as PC, which has everything baked into .SCL archives that need to be decompressed first, then extracted. Plus, I think this could work for the Versus files as well, since they are .UKX, .USX and .UTX as well.

Here are the Versus files from PC:
[https://mega.nz/#!8VJhGIYY!NkF_igDzTQJB ... llwkpTQ_VY](https://mega.nz/#!8VJhGIYY!NkF_igDzTQJBqbaVdQ1TmdgUxQm0khkX3llwkpTQ_VY)
## Post #5
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-01-18T13:15:58+00:00
- Post Title: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

Sorry for the bump, I wanted to ask if there is a difference in files (PC and PS3 versions) of the .UKX, .UTX and .USX, or if they all are universally viable to be used by an export script or something.
## Post #6
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-06-06T19:56:47+00:00
- Post Title: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

Hi!! Anyone can take a look at this sample please? 
[https://www.mediafire.com/file/t66g7xs2 ... lMesh/file](https://www.mediafire.com/file/t66g7xs2ab3cgcj/mesh_zsnpc7.SkeletalMesh/file)
Im using this values hex2obj:
face indices 18d0e - 2364
uvs  x  - 99
vertices indices 1773e - 558
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-06T20:27:02+00:00
- Post Title: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

Did you notice that the section you claimed to contain vertices is like so: "float float word"? So it's more likely to hold the texture coordinates.

Try 1b29b for the start of vertices.
.



zsnpc7.png (6.6 KiB) Viewed 259 times
## Post #8
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-06-07T01:14:50+00:00
- Post Title: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from shakotay2 ↑Wed Jun 07, 2023 4:27 am at Wed Jun 07, 2023 4:27 am
>
> 
Did you notice that the section you claimed to contain vertices is like so: "float float word"? So it's more likely to hold the texture coordinates.
  at first I thought it was part of the UV   , thanks for the help
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-08T19:44:12+00:00
- Post Title: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

Found another start of vertices: 0x5f1e, count: 675, FVFsize: 16

(Face indices (at 0x8978) give strange character/partial match only)
Another set of FIs at 0x15938 (max FI= 558).

Partial match looks like so, too confusing to me:
.



partialMatch.png (37.56 KiB) Viewed 194 times



(Point cloud skinner: "this case is uncertain, not implemented yet." )
## Post #10
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-06-08T20:41:14+00:00
- Post Title: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from shakotay2 ↑Fri Jun 09, 2023 3:44 am at Fri Jun 09, 2023 3:44 am
>
> 
Found another start of vertices: 0x5f1e, count: 675, FVFsize: 16

(Face indices (at 0x8978) give strange character/partial match only)
Another set of FIs at 0x15938 (max FI= 558).

Partial match looks like so, too confusing to me:
(Point cloud skinner: "this case is uncertain, not implemented yet." )
Thanks! Gonna be checking too!
## Post #11
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-06-09T01:21:01+00:00
- Post Title: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from shakotay2 ↑Fri Jun 09, 2023 3:44 am at Fri Jun 09, 2023 3:44 am
>
> 
Found another start of vertices: 0x5f1e, count: 675, FVFsize: 16
Could be that this mesh can't be obtained with hex2obj? because cannot add a padding value?
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-09T04:24:34+00:00
- Post Title: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from moonpaladin ↑Fri Jun 09, 2023 9:21 am at Fri Jun 09, 2023 9:21 am
>
> 
Could be that this mesh can't be obtained with hex2obj? because cannot add a padding value?Depends on. For vertices I didn't ever need it, because FVFsize usually does the trick. (But I'd need to think about it.)

For face indices you can enter a "padding value" in the edit box below the "noPtC" button. I.e. if there's 0000 0100 0200 0000 0100 0200 0300 0000 you would enter 2 to skip the bold two zeroes (padding would be 8, I guess, but I chose to use the offset only).
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-06-09T07:24:54+00:00
- Post Title: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from shakotay2 ↑Wed Jun 07, 2023 4:27 am at Wed Jun 07, 2023 4:27 am
>
> 
Did you notice that the section you claimed to contain vertices is like so: "float float word"? So it's more likely to hold the texture coordinates.
Huh, another call for the data reorganizer. 



mesh_zsnpc7.png (207.95 KiB) Viewed 165 times
## Post #14
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-06-10T03:15:40+00:00
- Post Title: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from Bigchillghost ↑Fri Jun 09, 2023 3:24 pm at Fri Jun 09, 2023 3:24 pm
>
> 
Huh, another call for the data reorganizer.
Hi Bigchillghost, first time I see this tool! I manage to get the mesh +uv's  , there is a way to reduce the process a bit?  .
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-06-10T04:49:59+00:00
- Post Title: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from moonpaladin ↑Sat Jun 10, 2023 11:15 am at Sat Jun 10, 2023 11:15 am
>
> 
there is a way to reduce the process a bit?  .
No, I don't think so. The reorganizer was designed only for validation purpose so you're gona need a script for that. But if you have anything in mind as to "reduce the process a bit", I'd be glad to hear it.
## Post #16
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-06-10T05:32:12+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from Bigchillghost ↑Sat Jun 10, 2023 12:49 pm at Sat Jun 10, 2023 12:49 pm
>
> 
No, I don't think so. The reorganizer was designed only for validation purpose so you're gona need a script for that. But if you have anything in mind as to "reduce the process a bit", I'd be glad to hear it.
At first I thought of a script that generates the values of the reorganizer but thinking about it better I still get to see them when taking out the other values.   . Sadly are some models that are not in rest pose, but I have found another kind of file that it have bone info and seems it have mesh info too, all merge   , but seems it need the reorganizer tool too  Would you mind in take a look please? [https://www.mediafire.com/file/bdxfmdx7 ... 1.ukx/file](https://www.mediafire.com/file/bdxfmdx7z9t8amy/mesh_hsq_00000001.ukx/file)
## Post #17
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-06-10T09:23:36+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from moonpaladin ↑Sat Jun 10, 2023 1:32 pm at Sat Jun 10, 2023 1:32 pm
>
> 
Sadly are some models that are not in rest pose, but I have found another kind of file that it have bone info and seems it have mesh info too, all merge   , but seems it need the reorganizer tool too
Same format as your previous sample. Actually, there're 0x1007 bytes at the front missing in that file. Unfortunately, it's not possible to handle the blend indices/weights of this format with AXE as the number of weight slots per vertex is not constant. Besides, the skeleton doesn't align with the mesh either.



mesh_hsq_skel.png (70.38 KiB) Viewed 190 times
## Post #18
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-06-10T15:15:33+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from Bigchillghost ↑Sat Jun 10, 2023 5:23 pm at Sat Jun 10, 2023 5:23 pm
>
> 
Unfortunately, it's not possible to handle the blend indices/weights of this format with AXE as the number of weight slots per vertex is not constant. Besides, the skeleton doesn't align with the mesh either.
Oh, I understand!Thanks for checking it out!.
## Post #19
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2023-06-11T17:23:31+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

When will you guys learn how to read the Unreal Engine package?
## Post #20
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-06-12T04:16:42+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from Bigchillghost ↑Sat Jun 10, 2023 5:23 pm at Sat Jun 10, 2023 5:23 pm
>
> 
Same format as your previous sample.
Hello Bigchillghost! I have a file that seems compressed because cannot find any kind of indices   , Would you mind in take a look please?  
[https://www.mediafire.com/file/khqfipjr ... 29.7z/file](https://www.mediafire.com/file/khqfipjry32h0f9/mesh%25282%2529.7z/file)
## Post #21
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-06-12T16:57:59+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from moonpaladin ↑Mon Jun 12, 2023 12:16 pm at Mon Jun 12, 2023 12:16 pm
>
> 
compressed
looklike zlib, [78 **], use offzip
## Post #22
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-06-12T19:08:26+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from Durik256 ↑Tue Jun 13, 2023 12:57 am at Tue Jun 13, 2023 12:57 am
>
> 
looklike zlib, [78 **], use offzip
Hii Durik! I have used it, I was checking the output files and still cannot identify the headers  to get a mesh
## Post #23
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2023-06-13T19:22:11+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from Bigchillghost ↑Sat Jun 10, 2023 5:23 pm at Sat Jun 10, 2023 5:23 pm
>
> 
...
Besides, the skeleton doesn't align with the mesh either.
...

It's because you are using skeleton from one of the animation data.

Offsets:
5495 -> RefSkeleton (95 bones)
421071 -> RawVerts (3430)
462237 -> RawWedges (4091)
503153 -> RawFaces (1594)
522283 -> RawInfluences (5342)
## Post #24
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-06-14T02:16:21+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from VendorX ↑Wed Jun 14, 2023 3:22 am at Wed Jun 14, 2023 3:22 am
>
> 
Offsets:
5495 -> RefSkeleton (95 bones)
421071 -> RawVerts (3430)
462237 -> RawWedges (4091)
503153 -> RawFaces (1594)
522283 -> RawInfluences (5342)
Hello VendorX, you was able to export the model with the bone info?
## Post #25
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2023-06-14T18:19:27+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

Not yet, but (as you can see on the image above) I know package format - so it's only question of writing an exporter.
## Post #26
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2023-06-17T21:33:57+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

Update:


So as you see everything is OK with this mesh. ... no animations data in this package.
## Post #27
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-06-18T07:50:48+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from VendorX ↑Sun Jun 18, 2023 5:33 am at Sun Jun 18, 2023 5:33 am
>
> 
So as you see everything is OK with this mesh. ... no animations data in this package.
COOL!! There is not export option on that program that loads the package ?
## Post #28
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2023-06-18T15:52:37+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

I need more samples (with animations) - especially package with animation for the mesh_hsq - so maybe animation will work also.
## Post #29
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-06-18T17:13:43+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from VendorX ↑Sun Jun 18, 2023 11:52 pm at Sun Jun 18, 2023 11:52 pm
>
> 
I need more samples (with animations) - especially package with animation for the mesh_hsq - so maybe animation will work also.
Here are the animations of that model : [https://www.mediafire.com/file/hvpwg9za ... ms.7z/file](https://www.mediafire.com/file/hvpwg9za6acr1qn/Anims.7z/file)
## Post #30
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2023-07-02T15:41:06+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

> Reply from moonpaladin ↑Mon Jun 19, 2023 1:13 am at Mon Jun 19, 2023 1:13 am
>
> 
VendorX wrote: ↑Sun Jun 18, 2023 11:52 pm
I need more samples (with animations) - especially package with animation for the mesh_hsq - so maybe animation will work also.

Here are the animations of that model : https://www.mediafire.com/file/hvpwg9za ... ms.7z/file

Hey, just wanted to ask: what game are these models from? Do they share the same structure as the Chaos Theory files?
## Post #31
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2023-07-02T20:15:51+00:00
- Post Title: Re: [PC/PS3] Splinter Cell Chaos Theory - How to convert Skeletal Meshes and Animations

It's a different game ... as for SCCT - like I said on Zenhax - I can write SkeletalMesh exporter.
StaticMesh and MeshAnimation is no go so far due to unknown compression algorithm.
