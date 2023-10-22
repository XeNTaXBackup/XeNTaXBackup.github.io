## Post #1
- Username: yohanc
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 12, 2016 1:59 am
- Post datetime: 2018-03-15T18:37:06+00:00
- Post Title: Mr Bean PC Game (.3df and .plf)

Hi guys, I want to rip the mini cooper from mr bean pc game


I found 2 file types, the .3df and .plf, but I believe the 3d models and textures is in the .3df file and the .plf file is probably the game script
I have attached both files, can you guys help me inspect it?
And what software should I use to extract the 3d model with its textures?
[http://www.mediafire.com/file/1vhf1wyuh3fzh5g/BEAN.zip](http://www.mediafire.com/file/1vhf1wyuh3fzh5g/BEAN.zip)
Other files
[http://www.mediafire.com/file/bdnq2yzo416jbth/OTHER.zip](http://www.mediafire.com/file/bdnq2yzo416jbth/OTHER.zip)
Thanks
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-16T11:07:22+00:00
- Post Title: Mr Bean PC Game (.3df and .plf)

you might try to get some point clouds:



Racing01-3DF.jpg (145.95 KiB) Viewed 119 times


This is the H2O file for it:

0x391350 1000
Vb1
80 99
0x3E220 43574
040000
0x0 255

Copy the 6 lines into a txt file and name it whatever.h2o.
Then load the racing01.3DF into hex2obj, same with the H2O file.

(You need to toggle the upper right button to PtCld then press the 'mesh' button to get the point cloud displayed.)

2nd test:

0x391350 1000
Vb1
12 99
0x2724 5425
040000
0x0 255

(face indices start address and count not valid)
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-16T11:52:17+00:00
- Post Title: Mr Bean PC Game (.3df and .plf)

> Reply from shakotay2
>
> You need to toggle the upper right button to PtCld then press the 'mesh' button to get the point cloud displayed.
Pretty much something like this:



RACING01.3DF - PtCld.jpg (187.66 KiB) Viewed 116 times



> Reply from yohanc
>
> I want to rip the mini cooper from mr bean pc game
Basically in both 3df files you uploaded, there're only track models. The car you're looking for should be in other file.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-16T12:30:33+00:00
- Post Title: Mr Bean PC Game (.3df and .plf)

yeah, I see:



racing01.jpg (98.66 KiB) Viewed 111 times



0x391350 213875
Vb1
40 99
0x3E220 87150
041000
0x0 255


(uvs maybe at offset 24, but look a little bit weird)
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-16T13:23:31+00:00
- Post Title: Mr Bean PC Game (.3df and .plf)

> Reply from shakotay2
>
> yeah, I see:
racing01.jpg
I tried tristrip on some meshes too but they look weird.

> Reply from shakotay2
>
> (uvs maybe at offset 24, but look a little bit weird)
I'm curious about what the rest two floats represent. Another UV?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-16T14:06:36+00:00
- Post Title: Mr Bean PC Game (.3df and .plf)

> Reply from Bigchillghost
>
> I tried tristrip on some meshes too but they look weird.Overall impression of racing01 looks ok to me with tristrips chosen. The extra faces might indicate that those tracks have some submesh dividing (just a wild guess). 
(Would be cool to have an automatic method of deleting those "superfluous faces" which I found in some other 3D formats, too.)

> I'm curious about what the rest two floats represent. Another UV?Seems the last float is always 1.0 (setting uvpos to 32, press go2)
## Post #7
- Username: yohanc
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 12, 2016 1:59 am
- Post datetime: 2018-03-16T15:25:46+00:00
- Post Title: Mr Bean PC Game (.3df and .plf)

Hi shakotay2 & Bigchillghost, thanks for the help
I have opened it with hex2obj and I managed to display the point cloud.
But how can I extract it into .obj and texture (.jpg or .tga)
My other question to shakotay2, the mini cooper, is it inside the racing1.3df or racing2.3df file?

P.S. I only need the mini cooper 3d model and textures
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-16T15:42:35+00:00
- Post Title: Mr Bean PC Game (.3df and .plf)

> Reply from yohanc
>
> But how can I extract it into .objFile SaveAs mesh

> and texture (.jpg or .tga)You'll need to search for the textures.

> the mini cooper, is it inside the racing1.3df or racing2.3df file?I think it's very unlikely to be found in a track file.

> P.S. I only need the mini cooper 3d model and texturesOwn efforts are required; you won't get them served on a silver tray...
## Post #9
- Username: yohanc
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 12, 2016 1:59 am
- Post datetime: 2018-03-16T16:08:14+00:00
- Post Title: Mr Bean PC Game (.3df and .plf)

Here is another files, that I think there is a mini cooper in it.
Can you help me inspect it again since I have no idea how to generate that .h20 file.
[http://www.mediafire.com/file/bdnq2yzo416jbth/OTHER.zip](http://www.mediafire.com/file/bdnq2yzo416jbth/OTHER.zip)

> File SaveAs mesh
I have imported the racing1.obj into my blender, but the .obj, there are just tons of vertices/dots, there is no face in the .obj file
and because of that there is no uv map too
(is it possible to rip the .obj with a perfect uv map?)

> You'll need to search for the textures
But where can I find it? in the .3df file? or the .plf file? (BTW there is no other files)
How to extract the textures?
(I think for the texture I can use ninjaripper for it)

Thanks
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-16T19:44:20+00:00
- Post Title: Mr Bean PC Game (.3df and .plf)

> Reply from yohanc
>
> Here is another files, that I think there is a mini cooper in it.too many files. Search for 'cooper' in the 3DF files using a hex editor which is capable of such.
(teddy is in Extras23.3DF)

> since I have no idea how to generate that .h20 file.read the tutorial,please ('tut' button)

> there is no face in the .obj file
>
> and because of that there is no uv map toothat's not correct.

You could insert some g submesh_x lines into the obj file (each 500 face index lines for example, for x use 1 to 25 or such).



submeshes_racing.jpg (204.86 KiB) Viewed 88 times



> But where can I find it? in the .3df file? or the .plf file? (BTW there is no other files)There seem to be texture data at the end of the 3DF files; you could import the 3DF as raw file into gimp or irfanview. Display as 8 bit grayscale, for example.
## Post #11
- Username: yohanc
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 12, 2016 1:59 am
- Post datetime: 2018-03-17T22:07:18+00:00
- Post Title: Mr Bean PC Game (.3df and .plf)

Hi I have use the HxD to search for the mini cooper, I search for "COOPER" but there is none, but it has "MINI"
I think, it is in the EXTRAS00.3DF (there is this line of code: MINI_BEAN-MAP, MINI_GLASS-MAP, MINI, MINI_WINDOWS) and other file EXTRAS24.3DF (there is this line of code: RACEHAYBAIL, RACETREE). But I believe it must be in the EXTRAS00.3DF.

I read your tutorial but I'm confuse, can you help me find the .h20 for the EXTRAS00.3DF?

> You could insert some g submesh_x lines into the obj file (each 500 face index lines for example, for x use 1 to 25 or such)
Using the hex2obj (I didn't see the "g submesh_x lines" in the software)? or blender?

> There seem to be texture data at the end of the 3DF files; you could import the 3DF as raw file into gimp or irfanview. Display as 8 bit grayscale, for example
I have opened it using GIMP but it failed to open
I click "Open" (all files)
The same goes with the irfanview, it failed to open
## Post #12
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-18T05:21:45+00:00
- Post Title: Mr Bean PC Game (.3df and .plf)

> Reply from yohanc
>
> But I believe it must be in the EXTRAS00.3DF.
It's in there for sure.



records.jpg (126.41 KiB) Viewed 68 times


It takes 372 bytes for each entry, with parent entry beginning at 0x4ECC. The first submesh start at 0xB980, while the face buffer comes right after the vertex chunk(FVFsize = 32). 
With an alignment of 0x10 bytes (alignedDataSize = 0x10 - currentPosition % 0x10), there comes the next submesh and so on. 

> Reply from yohanc
>
> I read your tutorial but I'm confuse, can you help me find the .h20 for the EXTRAS00.3DF?
Then ask people what you're confuse about. You cannot rely on others forever.
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-18T05:30:58+00:00
- Post Title: Mr Bean PC Game (.3df and .plf)

mini.jpg (94.33 KiB) Viewed 68 times


See? It's not that difficult at all.
## Post #14
- Username: yohanc
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 12, 2016 1:59 am
- Post datetime: 2018-03-18T09:45:14+00:00
- Post Title: Mr Bean PC Game (.3df and .plf)

I have read the tutorial like multiple times but I'm still confuse

> viewtopic.php?f=29&t=10894

I want to learn it but the tools is kinda advance for new user like me (I'm really clueless)
it is advance tool, lots of newbie found it confusing too
[viewtopic.php?f=29&t=14695](http://forum.xentax.com/viewtopic.php?f=29&t=14695)
[viewtopic.php?f=16&t=12524](http://forum.xentax.com/viewtopic.php?f=16&t=12524)

Can you give me step by step on how to get h2o until the final 3d model .obj (not just the vertices (point clouds), but full the .obj with full faces and the uv map)? (How to find face indices, finding the uv/vertices start address)

Can you give the example with the mini cooper (EXTRAS00.3DF)?

Thanks
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-18T10:19:17+00:00
- Post Title: Mr Bean PC Game (.3df and .plf)

> Reply from yohanc
>
> it is advance tool, lots of newbie found it confusing tooIf you don't get familiar with the hex2obj tutorial you might try out similar other programs which might serve your needs better:

from Lazov
[viewtopic.php?f=33&t=16163](http://forum.xentax.com/viewtopic.php?f=33&t=16163)
[viewtopic.php?f=29&t=16543](http://forum.xentax.com/viewtopic.php?f=29&t=16543)

from Herbert3000
[viewtopic.php?f=33&t=14648](http://forum.xentax.com/viewtopic.php?f=33&t=14648)
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-18T10:41:30+00:00
- Post Title: Re: Mr Bean PC Game (.3df and .plf)

OK, one after another:

> Reply from yohanc
>
> I have read the tutorial like multiple times but I'm still confuse
Yeah, so was I at the first place. The only thing I even understood by that time was to look at the ascii part of a binary file in the hex editor.

> Reply from yohanc
>
> I want to learn it but the tools is kinda advance for new user like me
That depends on whether you know how things work. Then you'll find everything quite simple.

> Reply from yohanc
>
> what software should i use to get the h2o file? hxd?
Hex2Obj of course.

> Reply from yohanc
>
> Can you give me step by step on how to get h2o until the final 3d model .obj (not just the vertices (point clouds), but full the .obj with full faces and the uv map)?
Thanks
I did plan on writting a easy tutorial for beginners before. But considering that there're many people who can already help themselves, while the others who don't just keep pouring new requests whereas there're a lot of references available showing them how to do it, plus writting a tutorial is a time consuming job, I just gave up. 
Is it still in need?
## Post #17
- Username: yohanc
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 12, 2016 1:59 am
- Post datetime: 2018-03-18T13:09:38+00:00
- Post Title: Re: Mr Bean PC Game (.3df and .plf)

> Is it still in need?
I've received your pm, thanks.

If you have a little spare time to write a tutorial that can be easy to understand for newbies that would be great and life saver for newbs like me.

I found this video about hex2obj
[https://www.youtube.com/watch?v=TT-UtvBRWt0](https://www.youtube.com/watch?v=TT-UtvBRWt0)

step1. start/ending of the face indices list (how come you know from the weird text in hex editor wheter it is the start/ending of the face indicies, in the video min 01:55 the guy didn't explain why it is 0000010002)

step2. vertex block (in the video min 03:23, he didn't explain why it is 40).

step3. finding the uv/vertices start address, I understand how he get the count min 03:28, but the guy forgot to get the uv/vertices start address.
## Post #18
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-18T14:11:05+00:00
- Post Title: Re: Mr Bean PC Game (.3df and .plf)

I think you need to understand what you are looking for first. Hex2obj just lets you visualize the model data that you have found. To find it you need to know how it should look like.

0000 0100 0200 is a pretty common start for indices. It is the first triangle with the vertices 0,1,2. If it is followed by integers with small increments (generally) you would assume it is the index data. It might even look like an alphabet in ASCII view like A.B.C.D. For example if you see a set of floats all in range of 0.0 - 1.0, you might assume they are the uv coordinates. 

Note that the data you are looking for may be represented differently depending on the format used. Still I believe that searching for some values/patterns that are generally used is better than staring at the hex editor with nothing in mind, and it might possibly save you some time.

So have a general idea of what you are searching and look for it in the hex editor. When you think that you have found it try visualizing it in hex2obj to see if you got it right. With some trial and error you will hopefully find the right data.
## Post #19
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-18T15:09:26+00:00
- Post Title: Re: Mr Bean PC Game (.3df and .plf)

> Reply from yohanc
>
> 
If you have a little spare time to write a tutorial that can be easy to understand for newbies that would be great and life saver for newbs like me.
Unfortunately I don't think I'll have much free time in the following three weeks. Got a personal project to work with.
But still I'll try to answer your question as soon as I can.

> Reply from yohanc
>
> I found this video about hex2obj
https://www.youtube.com/watch?v=TT-UtvBRWt0
I actually don't think it a good idea to use hex2obj before you truely know what you're doing. So I won't introduce it as the first step in 
my tutorial. Instead, start from setting up the basic concepts here:
[http://wiki.xentax.com/index.php/3D_Model_Glossary](http://wiki.xentax.com/index.php/3D_Model_Glossary)

Before your attempt on dealing with binary data, read this:
[http://wiki.xentax.com/index.php/DGTEFF](http://wiki.xentax.com/index.php/DGTEFF)
