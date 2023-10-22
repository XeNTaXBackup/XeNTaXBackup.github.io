## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-21T20:49:18+00:00
- Post Title: Shumenol 3d model

Hello anyone can try to get the 3d model from this .eva file? I'm not sure about the start address of the vertices (using hex2obj) I have been checked the file but still don't figure it out, maybe someone can see the correct values. Thanks in advance.

[https://www.mediafire.com/file/nyfvi1yt ... 7.eva/file](https://www.mediafire.com/file/nyfvi1ytx73awrr/ride007.eva/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-21T22:00:07+00:00
- Post Title: Shumenol 3d model

I'd guess for animation data - even where you'd expect mesh vertex blocks, it's not. Annoying 01 instead and other unknown data (rectangled lightblue):
.



strangeOnes.png (46.76 KiB) Viewed 236 times


But, hey, those damn.. 01 follow a rule! 

edit: well, it's indeed vertices  , normals and uvs. After having skipped those 01 and other things.
## Post #3
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-21T22:43:08+00:00
- Post Title: Shumenol 3d model

> Reply from shakotay2 ↑Mon Nov 22, 2021 6:00 am at Mon Nov 22, 2021 6:00 am
>
> 
I'd guess for animation data - even where you'd expect mesh vertex blocks, it's not. Annoying 01 instead and other unknown data (rectangled lightblue):
.
strangeOnes.png
But, hey, those damn.. 01 follow a rule!

hahaha this file should contain meshes, bone data and also animations. Hope I can get the meshes at least. Thanks for the info about that weird pattern.
## Post #4
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-22T16:29:48+00:00
- Post Title: Shumenol 3d model

Hello I was gathering some models with their textures to try to get the models + UV's, seems that are models that have submeshes I were checking the ride020_1.eva. The values that I saw was the start address of the face indices 73381h but still not sure, also the end of the face indice list around  74DFCh. Are some blocks around this address that point to materials too and are three like the quantity of textures. (74DFEh  -  74F6Eh), (74F83h - 750D9h), (750EEh - 75244h). If someone have any suggestion about how to get the start address of vertices and uv would be great. Thanks for read.
 

[https://www.mediafire.com/file/jyees4ze ... S.zip/file](https://www.mediafire.com/file/jyees4ze3audl0u/SHUMENOL_EXAMPLES.zip/file)



shumenol_tiger.png (10.03 KiB) Viewed 216 times
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-22T17:49:47+00:00
- Post Title: Shumenol 3d model

My suggestion is to give the file(s) a structure, find out where's animation data and exclude those blocks from "your search for the mesh".
This is animation data, obviously:
.



ride020_1.png (37.04 KiB) Viewed 212 times


The count is 187, well 188 (BC000000), don't be pedantic  , so block size is 0x2340 (188x48 dec., maybe some are bigger, didn't check).
Those blocks after bone names should contain anim data.

So, last chance for a mesh: 0x75268? (welcome to the block of f.. 01  )
Since it looks regular you might extract some vertices from it.

Looks promissing, after 1.0: vertices, normals and uvs?

0 75268:  0.559510 -0.775976 0.291220   1.000000 9.119180 -2.769614 3.194836 0.604807 -0.566709 0.559508 
 0.121246 0.383082 

1 7529f:  0.523571 -0.574768 0.628900   1.000000 6.830144 -4.116294 3.307934 0.289418 -0.801320 0.523568 
 0.151153 0.416222 

2 752d6:  0.000003 -0.675775 0.737108   1.000000 7.287689 -4.669288 -0.000015 0.341165 -0.940003 -0.000000 
 0.108645 0.458235 

3 7530d:  0.000005 -0.953525 0.301313   1.000000 10.323507 -2.810081 -0.000009 0.764888 -0.644163 0.000002 
 0.057917 0.399914 

sadly it gives me a break after 16 lines; dunno what this means...
## Post #6
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-22T18:49:09+00:00
- Post Title: Shumenol 3d model

> Reply from shakotay2 ↑Tue Nov 23, 2021 1:49 am at Tue Nov 23, 2021 1:49 am
>
> 
My suggestion is to give the file(s) a structure, find out where's animation data and exclude those blocks from "your search for the mesh".
This is animation data, obviously:
ey Shakotay2 thanks for answer! I'm trying that, I was ignoring the last block (75268h) XD. Da.. still not getting any kind of mesh yet.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-22T19:16:31+00:00
- Post Title: Shumenol 3d model

You'll need to be a coder to get the vertices. But you could care for the face indices, I'm done with this point cloud:
.


 ride20-Point-cloud.zip
(39.39 KiB) Downloaded 18 times


(vertices and uvs contained; normals disabled by #)
edit: first block of FIs attached (which you can get from hex2obj).

(This 01 reminds me of another format - but don't remember, which it was.)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-22T19:47:46+00:00
- Post Title: Shumenol 3d model

Tiger.png (172.65 KiB) Viewed 189 times
## Post #9
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-22T19:52:30+00:00
- Post Title: Shumenol 3d model

> Reply from shakotay2 ↑Tue Nov 23, 2021 3:16 am at Tue Nov 23, 2021 3:16 am
>
> 
You'll need to be a coder to get the vertices. But you could care for the face indices, I'm done with this point cloud:
.
ride20-Point-cloud.zip
(vertices and uvs contained; normals disabled by #)
edit: first block of FIs attached (which you can get from hex2obj).

(This 01 reminds me of another format - but don't remember, which it was.)
So I will need a script, fu.. . It reminds me to the gunz models from time ago. Thanks!
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-23T11:31:31+00:00
- Post Title: Shumenol 3d model

All parts clumped together, too much work for me for such a lowpoly mesh:
.



boss143.jpg (114.77 KiB) Viewed 165 times
## Post #11
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-23T14:30:52+00:00
- Post Title: Shumenol 3d model

> Reply from shakotay2 ↑Tue Nov 23, 2021 7:31 pm at Tue Nov 23, 2021 7:31 pm
>
> 
All parts clumped together, too much work for me for such a lowpoly mesh:
.
boss143.jpg
You are getting this kind of meshes with hex2obj? Could you share your values?   . Some models are lowpoly, others seems way better.
## Post #12
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-11-23T16:18:06+00:00
- Post Title: Shumenol 3d model

If you are interested in ShumenOL models, there is a mobile version of the game using UNITY. Both models and animations are supported by AssetStudio.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-23T16:27:35+00:00
- Post Title: Shumenol 3d model

> Reply from moonpaladin ↑Tue Nov 23, 2021 10:30 pm at Tue Nov 23, 2021 10:30 pm
>
> You are getting this kind of meshes with hex2obj?No, read the first sentence here again:

> Reply from shakotay2 ↑Tue Nov 23, 2021 3:16 am at Tue Nov 23, 2021 3:16 am
>
> What I get using hex2obj is the face indices only, at 0x333EBA 5220.
(Results in a vertex count of 1176.)
## Post #14
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-23T16:44:19+00:00
- Post Title: Shumenol 3d model

> Reply from Drawing ↑Wed Nov 24, 2021 12:18 am at Wed Nov 24, 2021 12:18 am
>
> 
If you are interested in ShumenOL models, there is a mobile version of the game using UNITY. Both models and animations are supported by AssetStudio.
ey Hi Drawing! yep I saw them, but are some models that are not in there that's why I wanted to know how to get the meshes from the PC game.
## Post #15
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-23T16:48:00+00:00
- Post Title: Shumenol 3d model

> Reply from shakotay2 ↑Wed Nov 24, 2021 12:27 am at Wed Nov 24, 2021 12:27 am
>
> 
No, read the first sentence here
oh I see   (I was dreaming lol)  ,you were able to load the submeshes?
## Post #16
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-23T17:03:05+00:00
- Post Title: Re: Shumenol 3d model

> Reply from Drawing ↑Wed Nov 24, 2021 12:18 am at Wed Nov 24, 2021 12:18 am
>
> 
If you are interested in ShumenOL models, there is a mobile version of the game using UNITY. Both models and animations are supported by AssetStudio.

Like this one :p 



mount_model.png (241.81 KiB) Viewed 211 times
## Post #17
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-11-23T18:34:12+00:00
- Post Title: Re: Shumenol 3d model

> Reply from moonpaladin ↑Wed Nov 24, 2021 1:03 am at Wed Nov 24, 2021 1:03 am
>
> 
Drawing wrote: ↑Wed Nov 24, 2021 12:18 am
If you are interested in ShumenOL models, there is a mobile version of the game using UNITY. Both models and animations are supported by AssetStudio.


Like this one :p 
mount_model.png

I dunno if that one is in mobile version, I quickly see some mount but there are too many.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-23T21:11:07+00:00
- Post Title: Re: Shumenol 3d model

> Reply from moonpaladin ↑Wed Nov 24, 2021 12:48 am at Wed Nov 24, 2021 12:48 am
>
> 
oh I see   (I was dreaming lol)  ,you were able to load the submeshes?Check it for yourself, please.  
.


 boss143.zip
(119.9 KiB) Downloaded 22 times
## Post #19
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-23T22:01:06+00:00
- Post Title: Re: Shumenol 3d model

> Reply from shakotay2 ↑Wed Nov 24, 2021 5:11 am at Wed Nov 24, 2021 5:11 am
>
> 
moonpaladin wrote: ↑Wed Nov 24, 2021 12:48 am
oh I see   (I was dreaming lol)  ,you were able to load the submeshes?
Check it for yourself, please.  
.
boss143.zip

Oh well this one is the first mesh that is the body of the boos, the one missing should be the armor of this boos, anyways the uvs looks pretty well, sadly mesh not yet. thanks for ur time shakotay2
## Post #20
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2021-11-24T12:54:15+00:00
- Post Title: Re: Shumenol 3d model

I hope the game will be full supported.
I Search one year ago about help.

Thanks
## Post #21
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-24T14:15:06+00:00
- Post Title: Re: Shumenol 3d model

> Reply from KingJuls ↑Wed Nov 24, 2021 8:54 pm at Wed Nov 24, 2021 8:54 pm
>
> 
I hope the game will be full supported.
I Search one year ago about help.

Thanks

Really hope it too, I know that the models are low poly but you can increase the details in a 3d editor, hope someone take interest in it
## Post #22
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-25T05:01:21+00:00
- Post Title: Re: Shumenol 3d model

I found the superpanda mount      damnn I really like how it looks, if someone extract the mesh please attach to this post :'(.   

[https://www.mediafire.com/file/vpnrtm8g ... T.zip/file](https://www.mediafire.com/file/vpnrtm8gbz4xffg/PANDA_MOUNT.zip/file)
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-25T07:22:54+00:00
- Post Title: Re: Shumenol 3d model

> Reply from moonpaladin ↑Thu Nov 25, 2021 1:01 pm at Thu Nov 25, 2021 1:01 pm
>
> 
if someone extract the meshYeah, that unknown "someone" we're all waiting for... 

> please attach to this post :'(.Thing is that I have no idea how to identify the sub meshes for this layout.
.



Panda-point-cloud.png (67.23 KiB) Viewed 169 times
## Post #24
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-25T14:25:01+00:00
- Post Title: Re: Shumenol 3d model

> Reply from shakotay2 ↑Thu Nov 25, 2021 3:22 pm at Thu Nov 25, 2021 3:22 pm
>
> 
moonpaladin wrote: ↑Thu Nov 25, 2021 1:01 pm
if someone extract the mesh Yeah, that unknown "someone" we're all waiting for... 
please attach to this post :'(.   Thing is that I have no idea how to identify the sub meshes for this layout.
.
Panda-point-cloud.png

haha "someone"   , you are doing shakotay2!!!
## Post #25
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-26T18:00:22+00:00
- Post Title: Re: Shumenol 3d model

Unsurprisingly:



panda_mount.png (196.56 KiB) Viewed 149 times
## Post #26
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-26T18:06:56+00:00
- Post Title: Re: Shumenol 3d model

And at frame 85:



panda_mount_f85.png (183.78 KiB) Viewed 149 times
## Post #27
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-26T19:19:01+00:00
- Post Title: Re: Shumenol 3d model

> Reply from Bigchillghost ↑Sat Nov 27, 2021 2:06 am at Sat Nov 27, 2021 2:06 am
>
> 
And at frame 85:
panda_mount_f85.png

woowowwowoow
## Post #28
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2021-11-27T09:52:55+00:00
- Post Title: Re: Shumenol 3d model

> Reply from Bigchillghost ↑Sat Nov 27, 2021 2:06 am at Sat Nov 27, 2021 2:06 am
>
> 
And at frame 85:
panda_mount_f85.png

Can u share the plugin?
## Post #29
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-28T09:59:20+00:00
- Post Title: Re: Shumenol 3d model

Here, script for that sample file only:


 fmt_panda_mount_eva.zip
(1.26 KiB) Downloaded 33 times



Addresses are hard-coded, so don't bother to use the script on other files without modifications. If you want specific pose of the model at certain frame, change the value of the target frame id at line 49.
## Post #30
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2021-11-28T13:38:09+00:00
- Post Title: Re: Shumenol 3d model

> Reply from Bigchillghost ↑Sun Nov 28, 2021 5:59 pm at Sun Nov 28, 2021 5:59 pm
>
> 
Here, script for that sample file only:
fmt_panda_mount_eva.zip

Addresses are hard-coded, so don't bother to use the script on other files without modifications. If you want specific pose of the model at certain frame, change the value of the target frame id at line 49.

Thanks a lot!
Do we have a chance that one develops a general plugin?
## Post #31
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-28T15:40:00+00:00
- Post Title: Re: Shumenol 3d model

> Reply from KingJuls ↑Sun Nov 28, 2021 9:38 pm at Sun Nov 28, 2021 9:38 pm
>
> 
Do we have a chance that one develops a general plugin?That's not as simple as you may think of, for boss143 for example the layout is different.
With a slightly patched scripts (with Vcount= 1966 and rotMat not used) you get this:
.



boss143-partial.png (99.42 KiB) Viewed 213 times


So more work to be done.

Great script, btw, Bigchillghost!   Looks so short and simple, but contains more brain work than I can afford...
## Post #32
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-28T17:33:38+00:00
- Post Title: Re: Shumenol 3d model

> Reply from Bigchillghost ↑Sun Nov 28, 2021 5:59 pm at Sun Nov 28, 2021 5:59 pm
>
> 
Here, script for that sample file only:
fmt_panda_mount_eva.zip

Addresses are hard-coded, so don't bother to use the script on other files without modifications. If you want specific pose of the model at certain frame, change the value of the target frame id at line 49.

Thanks Bigchillghost !, I hope you can modify the script to support the other types of .eva, really hope soo! I can give more .eva files if is needed, again thanks for your time.
## Post #33
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-28T17:34:01+00:00
- Post Title: Re: Shumenol 3d model

> Reply from shakotay2 ↑Sun Nov 28, 2021 11:40 pm at Sun Nov 28, 2021 11:40 pm
>
> 
... but contains more brain work than I can afford...
I think we both know that's not true. 

> Reply from shakotay2 ↑Sun Nov 28, 2021 11:40 pm at Sun Nov 28, 2021 11:40 pm
>
> 
So more work to be done.
Indeed. And now it's getting ugly. 


 fmt_boss143_eva.zip
(1.31 KiB) Downloaded 32 times


[](https://ibb.co/FDSQV18)
## Post #34
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-28T17:49:34+00:00
- Post Title: Re: Shumenol 3d model

> Reply from Bigchillghost ↑Mon Nov 29, 2021 1:34 am at Mon Nov 29, 2021 1:34 am
>
> 
 And now it's getting ugly.  
fmt_boss143_eva.zip

haha damn what happen to his arm lol
## Post #35
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-29T22:14:13+00:00
- Post Title: Re: Shumenol 3d model

> Reply from shakotay2 ↑Sun Nov 28, 2021 11:40 pm at Sun Nov 28, 2021 11:40 pm
>
> 

With a slightly patched scripts (with Vcount= 1966 and rotMat not used) you get this:

ey! shakotay2!  I was practicing and I have been able to load models that have a single mesh, now I am reviewing those that have two meshes, and there are models that have 5 to 6 meshes so I assume that I will have to modify the script a bit. First,  I am trying to understand the values present in the script, could you tell me how you got the value of Vcount = 1966? thanks!  



ride001.png (100.3 KiB) Viewed 176 times
## Post #36
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-29T23:05:55+00:00
- Post Title: Re: Shumenol 3d model

> Reply from Bigchillghost ↑Mon Nov 29, 2021 1:34 am at Mon Nov 29, 2021 1:34 am
>
> 
Indeed. And now it's getting ugly.  
fmt_boss143_eva.zip
Bigchillghost, sorry for the pin xD, but please can you take a look at the script for the ride020_1.eva? the Vcount is empty xD, don't know how to get that value yet, but how about the others, or I'm totally wrong  and if you could explain my mistakes it would be great!  . thanks!


 fmt_ride020_1.zip
(1.36 KiB) Downloaded 21 times
## Post #37
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-30T09:38:35+00:00
- Post Title: Re: Shumenol 3d model

> Reply from moonpaladin ↑Tue Nov 30, 2021 6:14 am at Tue Nov 30, 2021 6:14 am
>
> ey! shakotay2!  I was practicing and I have been able to load models that have a single mesh,Unbelievable! 

> , could you tell me how you got the value of Vcount = 1966? thanks!That's a good question! I'm working intuitive and didn't make notes (as always). I remember having logged the actual address, it reached the end of the vertex block and from the sizeOfBlock I got the count. Like such, I guess.

I'd suggest to insert some "debug" lines such as
offs= bs.tell(); print("end of ... block at offs: ", hex(offs))
and try to understand the structure of that eva file.

edit: used a VCount833 for the first mesh:
.



Tiger_fstSub_mesh.png (52.99 KiB) Viewed 155 times



btw, the script you uploaded has indentation errors (for me).
Your ride001 picture shows a complete tiger (that's one mesh only?)

(It would be nice if you mentioned that the script is from Bigchillghost that you tried to patch.)
## Post #38
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-30T14:20:40+00:00
- Post Title: Re: Shumenol 3d model

> Reply from shakotay2 ↑Tue Nov 30, 2021 5:38 pm at Tue Nov 30, 2021 5:38 pm
>
> 

I'd suggest to insert some "debug" lines such as
offs= bs.tell(); print("end of ... block at offs: ", hex(offs))
and try to understand the structure of that eva file.

edit: used a VCount833 for the first mesh:
Gonna do that!ty

> Reply from shakotay2 ↑Tue Nov 30, 2021 5:38 pm at Tue Nov 30, 2021 5:38 pm
>
> 
btw, the script you uploaded has indentation errors (for me).
Your ride001 picture shows a complete tiger (that's one mesh only?)
  Yeah! is a model with one mesh only!

> Reply from shakotay2 ↑Tue Nov 30, 2021 5:38 pm at Tue Nov 30, 2021 5:38 pm
>
> 
(It would be nice if you mentioned that the script is from Bigchillghost that you tried to patch.)
of courseee is his script!!!! at the top of the script "#  ShumenOL ride020_1.eva importer by Bigchillghost" XD.
## Post #39
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-30T17:12:16+00:00
- Post Title: Re: Shumenol 3d model

> Reply from moonpaladin ↑Tue Nov 30, 2021 7:05 am at Tue Nov 30, 2021 7:05 am
>
> 
I suggest you take a few minutes to edit your quote next time to avoid unnecessary parts like attachment, images/links and redundant contexts.

> Reply from moonpaladin ↑Tue Nov 30, 2021 7:05 am at Tue Nov 30, 2021 7:05 am
>
> 
the Vcount is empty xD, don't know how to get that value yet
There's no vertex count in this file. Might just calculate it from the last index block.


 fmt_ride020_1.zip
(1.36 KiB) Downloaded 22 times



> Reply from shakotay2 ↑Tue Nov 30, 2021 5:38 pm at Tue Nov 30, 2021 5:38 pm
>
> 
(It would be nice if you mentioned that the script is from Bigchillghost that you tried to patch.)
That's not necessary in this situation. It's still in the same thread after all.
## Post #40
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-30T19:26:48+00:00
- Post Title: Re: Shumenol 3d model

> Reply from Bigchillghost ↑Wed Dec 01, 2021 1:12 am at Wed Dec 01, 2021 1:12 am
>
> 
There's no vertex count in this file. Might just calculate it from the last index block.
fmt_ride020_1.zip
Thanks alot! is working with models with 4-5 meshes! It took a while to identify the blocks but is just practice. Anyways I'm just changing values! you did all the work !   



ride6015.jpg (99.13 KiB) Viewed 135 times
## Post #41
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2021-12-03T13:35:43+00:00
- Post Title: Re: Shumenol 3d model

> Reply from moonpaladin ↑Mon Nov 22, 2021 4:49 am at Mon Nov 22, 2021 4:49 am
>
> 
Hello anyone can try to get the 3d model from this .eva file? I'm not sure about the start address of the vertices (using hex2obj) I have been checked the file but still don't figure it out, maybe someone can see the correct values. Thanks in advance.

https://www.mediafire.com/file/nyfvi1yt ... 7.eva/file


hi 

panda_mount.eva 

 Can you upload it to me? I also want to learn！
## Post #42
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-03T14:09:40+00:00
- Post Title: Re: Shumenol 3d model

> Reply from ptg1121 ↑Fri Dec 03, 2021 9:35 pm at Fri Dec 03, 2021 9:35 pm
>
> 
 Can you upload it to me? I also want to learn！

Hello! here you have [https://www.mediafire.com/file/s8ilzay2 ... 2.zip/file](https://www.mediafire.com/file/s8ilzay2rvb43y6/SHUMENOL_EXAMPLES_v2.zip/file)
## Post #43
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2021-12-04T10:00:51+00:00
- Post Title: Re: Shumenol 3d model

> Reply from moonpaladin ↑Fri Dec 03, 2021 10:09 pm at Fri Dec 03, 2021 10:09 pm
>
> 
ptg1121 wrote: ↑Fri Dec 03, 2021 9:35 pm
 Can you upload it to me? I also want to learn！


Hello! here you have https://www.mediafire.com/file/s8ilzay2 ... 2.zip/file

NEW TalismanOnline   data.evp There seems to be no new tool for this！


35 32 35 63 31 37 61 36 61 37 63 66 62 63 64 37
35 34 31 32 65 63 64 30 36 39 64 34 62 37 32 63
33 38 39 00 10 00 00 00 4E 4F 52 4D 41 4C 5F 50
41 43 4B 5F 54 59 50 45 66
## Post #44
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2021-12-04T10:26:52+00:00
- Post Title: Re: Shumenol 3d model

> Reply from moonpaladin ↑Wed Nov 24, 2021 12:44 am at Wed Nov 24, 2021 12:44 am
>
> 
Drawing wrote: ↑Wed Nov 24, 2021 12:18 am
If you are interested in ShumenOL models, there is a mobile version of the game using UNITY. Both models and animations are supported by AssetStudio.

ey Hi Drawing! yep I saw them, but are some models that are not in there that's why I wanted to know how to get the meshes from the PC game.

hi In fact, I have a model with the same structure. I guide its vertices and meshes, but I can't analyze the weight...
## Post #45
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2021-12-05T14:31:26+00:00
- Post Title: Re: Shumenol 3d model

> Reply from Bigchillghost ↑Wed Dec 01, 2021 1:12 am at Wed Dec 01, 2021 1:12 am
>
> 

The fbx generated by Noesis seems to have more (* _ end) bones if the name of the bone is different from that of the original file.
## Post #46
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2021-12-06T12:09:23+00:00
- Post Title: Re: Shumenol 3d model

> Reply from Bigchillghost ↑Wed Dec 01, 2021 1:12 am at Wed Dec 01, 2021 1:12 am
>
> 

HI Bigchillghost

I have two structures here, which are very similar to his engine, but I can't write noesis script. I haven't studied and understood your AXE yet. Can you help me?


[https://www.mediafire.com/file/lsn1cb](https://www.mediafire.com/file/lsn1cb)


A   

*.smz   BONE
*.ski   mesh
=======================================
B   
*.smz   BONE +mesh
## Post #47
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-06T15:00:44+00:00
- Post Title: Re: Shumenol 3d model

> Reply from ptg1121 ↑Mon Dec 06, 2021 8:09 pm at Mon Dec 06, 2021 8:09 pm
>
> 
I have two structures here, which are very similar to his engine
Yeah very similar indeed, in a manner of speaking. Except that they use Quaternion for rotations.

> Reply from ptg1121 ↑Mon Dec 06, 2021 8:09 pm at Mon Dec 06, 2021 8:09 pm
>
> 
but I can't write noesis script... Can you help me?
Sorry, no time for that.
## Post #48
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2021-12-07T10:47:41+00:00
- Post Title: Re: Shumenol 3d model

> Reply from Bigchillghost ↑Mon Dec 06, 2021 11:00 pm at Mon Dec 06, 2021 11:00 pm
>
> 

Thank you for your attention and wait for good news...
