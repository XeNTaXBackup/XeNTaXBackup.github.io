## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-09T05:40:52+00:00
- Post Title: yingxiong 3d models samples

Hello! after around two weeks   finally were able to gather all the meshes files decompressed related to this game, also found the skel file, sadly are some textures that are still compressed, but these samples are complete. (mesh+texture+skeleton). Any kind of help is welcome!    

[https://www.mediafire.com/file/n1oqhiuj ... l.zip/file](https://www.mediafire.com/file/n1oqhiuj90f6bze/3d_models_samples_%252B_skel.zip/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-09T06:08:54+00:00
- Post Title: yingxiong 3d models samples

You don't like half floats, do you?  
.



p1qz_s004-skin.png (155.8 KiB) Viewed 277 times
## Post #3
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-01-09T09:49:32+00:00
- Post Title: yingxiong 3d models samples

And here's a noesis script for the skeletons. The skinning info can be found in the buffers given by shakotay above. In the samples he showed you the layout is something like 
pos (half float) offset 0
norm coords (half float) offset 6
uv coords (half float) offset 12
joint indices (ubytes) offset 16 (always 4 ?)
joint weights (half float) offset 20 (last weight seems computed with weight4 = 1 - sum(other weights)

At least from a very quick look, there may be layout definitions, bonemaps etc but that should get you going.


 fmt_skel.zip
(595 Bytes) Downloaded 19 times
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-09T10:20:38+00:00
- Post Title: yingxiong 3d models samples

Using ASH + AXE (accessory bones ignored):



p1qz_skinned.png (221.75 KiB) Viewed 260 times
## Post #5
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-09T15:16:44+00:00
- Post Title: yingxiong 3d models samples

WOOOOW! Thank you very much shakotay2, Joschka and Bigchillghost! I will be reviewing the values to learn, again many thanks!
## Post #6
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-09T19:39:50+00:00
- Post Title: yingxiong 3d models samples

> Reply from Bigchillghost ↑Sun Jan 09, 2022 6:20 pm at Sun Jan 09, 2022 6:20 pm
>
> 
Hello Bigchillghost! after a while of testing, I was able to save the skel info of the pet010 sample using your ASH tool, now I'm trying to merge that skel info with the mesh data with your AXE tool, I have some doubts about these values (Blend Weights, Blend Indices and Mapping Bone Indices > Address), would you mind in clarify these a bit please? Thank you.
## Post #7
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-09T20:50:25+00:00
- Post Title: yingxiong 3d models samples

Also these skel files thrown error, or maybe I'm using wrong values   .

[https://www.mediafire.com/file/2nfnbeov ... R.zip/file](https://www.mediafire.com/file/2nfnbeovj46npsj/SKELETON_ERROR.zip/file)
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-10T12:07:26+00:00
- Post Title: yingxiong 3d models samples

> Reply from moonpaladin ↑Mon Jan 10, 2022 3:39 am at Mon Jan 10, 2022 3:39 am
>
> I have some doubts about these values (Blend Weights, Blend Indices and Mapping Bone Indices > Address), would you mind in clarify these a bit please?
You need to be more specific.

> Reply from moonpaladin ↑Mon Jan 10, 2022 4:50 am at Mon Jan 10, 2022 4:50 am
>
> 
Also these skel files thrown error, or maybe I'm using wrong values   .
Well, transformation's type is float.



z8a0_76.png (70.01 KiB) Viewed 217 times



Check the first 4 bytes for which type to use. If it's 1, try float; if it's 0x64 (100 in decimal), then half it is.
## Post #9
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-10T14:17:07+00:00
- Post Title: yingxiong 3d models samples

> Reply from Bigchillghost ↑Mon Jan 10, 2022 8:07 pm at Mon Jan 10, 2022 8:07 pm
>
> 
You need to be more specific.
Hello Bigchillghost!, well to be honest I don't know how to get that values.

> Reply from Bigchillghost ↑Mon Jan 10, 2022 8:07 pm at Mon Jan 10, 2022 8:07 pm
>
> 
transformation's type is float.  If it's 1, try float; if it's 0x64 (100 in decimal), then half it is.
Thank you!
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-10T14:42:58+00:00
- Post Title: yingxiong 3d models samples

> Reply from moonpaladin ↑Mon Jan 10, 2022 10:17 pm at Mon Jan 10, 2022 10:17 pm
>
> well to be honest I don't know how to get that values
The intention of that screenshot was for you to look into the binary file at the corresponding addresses, gain a sense of the corresponding vertex attribute data, and try to apply that intuition on other files. If the vertex stride is the same, then most possibly you should just use the same addresses for blend indices & weights. The count of the mapping bone indices was 4 bytes right before its start address, same as the vertices and the indices chunks.
## Post #11
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-10T15:26:16+00:00
- Post Title: yingxiong 3d models samples

> Reply from Bigchillghost ↑Mon Jan 10, 2022 10:42 pm at Mon Jan 10, 2022 10:42 pm
>
> 
Thank you Bigchillghost! it worked
## Post #12
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-22T19:42:13+00:00
- Post Title: yingxiong 3d models samples

I like these formats.
## Post #13
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-02-22T22:48:29+00:00
- Post Title: yingxiong 3d models samples

> Reply from Durik256 ↑Wed Feb 23, 2022 3:42 am at Wed Feb 23, 2022 3:42 am
>
> 
I like these formats.
Same as me, thats why I'm searching models in chinese Games
## Post #14
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-23T03:47:11+00:00
- Post Title: yingxiong 3d models samples

> Reply from moonpaladin ↑Wed Feb 23, 2022 6:48 am at Wed Feb 23, 2022 6:48 am
>
> 
Same as me, thats why I'm searching models in chinese Games
I meant the file format. (because it's simple)
## Post #15
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2022-02-25T11:15:55+00:00
- Post Title: yingxiong 3d models samples

> Reply from Durik256 ↑Wed Feb 23, 2022 11:47 am at Wed Feb 23, 2022 11:47 am
>
> 
moonpaladin wrote: ↑Wed Feb 23, 2022 6:48 am
Same as me, thats why I'm searching models in chinese Games  

I meant the file format. (because it's simple)

Hey Durik,

can u share your Script for the whole Community?
