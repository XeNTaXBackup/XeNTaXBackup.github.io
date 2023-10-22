## Post #1
- Username: kouka315
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 27, 2021 1:56 pm
- Post datetime: 2021-03-27T11:13:31+00:00
- Post Title: PC Age Of Wulin Online

Seek help! How to open Xmod file? Help me please！Thx！Thx！Thx！
[sword_0001.7z](https://xentaxbackup.github.io/file/19780_sword_0001.7z)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-23T11:15:40+00:00
- Post Title: PC Age Of Wulin Online

Mesh format is simple, using hex2obj (view link in my sig):
.



sword_0001-xmod.png (35.6 KiB) Viewed 710 times
## Post #3
- Username: takinsey
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 09, 2021 12:14 pm
- Post datetime: 2021-08-09T04:22:13+00:00
- Post Title: PC Age Of Wulin Online

> Reply from shakotay2 ↑Sun May 23, 2021 7:15 pm at Sun May 23, 2021 7:15 pm
>
> 
Mesh format is simple, using hex2obj (view link in my sig):
.
sword_0001-xmod.png

Thanks, very helpful
## Post #4
- Username: Lynix
- Rank: advanced
- Number of posts: 42
- Joined date: Wed Jul 01, 2015 10:11 pm
- Post datetime: 2021-08-12T21:59:26+00:00
- Post Title: PC Age Of Wulin Online

[https://drive.google.com/file/d/1dFHLg4 ... sp=sharing](https://drive.google.com/file/d/1dFHLg4N1VE4JbYoCQjbQm8qoLkhwAqGy/view?usp=sharing)
## Post #5
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-02T15:24:07+00:00
- Post Title: PC Age Of Wulin Online

> Reply from Lynix ↑Fri Aug 13, 2021 5:59 am at Fri Aug 13, 2021 5:59 am
>
> 
https://drive.google.com/file/d/1dFHLg4 ... sp=sharing
  Hello Lynix, your script works for taichi panda 3 too?
## Post #6
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-02T15:30:11+00:00
- Post Title: PC Age Of Wulin Online

> Reply from shakotay2 ↑Sun May 23, 2021 7:15 pm at Sun May 23, 2021 7:15 pm
>
> 
Mesh format is simple, using hex2obj (view link in my sig):

shakotay2!  , maybe could you help me with this model [https://www.mediafire.com/file/msdwd0w5 ... l.zip/file](https://www.mediafire.com/file/msdwd0w5nl44gbp/xmod_test_model.zip/file)
I'm using this values in hex2obj, btw! why in your photo appear that 100 below the tut button, it affects in something?    Thanks!



mon_xiniu.jpg (45.81 KiB) Viewed 552 times
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-02T17:12:59+00:00
- Post Title: PC Age Of Wulin Online

> Reply from moonpaladin ↑Thu Dec 02, 2021 11:30 pm at Thu Dec 02, 2021 11:30 pm
>
> I'm using this values in hex2obj, btw! why in your photo appear that 100 below the tut button, it affects in something?    Thanks!
mon_xiniu.jpgFrom the size of the vertex block and the count it's clear that FVFsize is 56 (uvs at offset 48).

(100 (hex) is the delta which the start of vertices address is changed by the +/- buttons, just for quicker research.)

btw, the 'h' you use for addresses is ignored by hex2obj (it automatically adds 0x internally, except for the counts which are treated as decimals.)

But this fake h will rule the world, I'm pretty sure, because people believe in what you show....
## Post #8
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-02T17:33:40+00:00
- Post Title: PC Age Of Wulin Online

> Reply from shakotay2 ↑Fri Dec 03, 2021 1:12 am at Fri Dec 03, 2021 1:12 am
>
> 
(100 (hex) is the delta which the start of vertices address is changed by the +/- buttons, just for quicker research.)
I have not the +/- buttons in my hex2obj xD!

> Reply from shakotay2 ↑Fri Dec 03, 2021 1:12 am at Fri Dec 03, 2021 1:12 am
>
> 
From the size of the vertex block and the count it's clear that FVFsize is 56 (uvs at offset 48).
I wanna know how to get these values xD still confused   show me if you can  

> Reply from shakotay2 ↑Fri Dec 03, 2021 1:12 am at Fri Dec 03, 2021 1:12 am
>
> 
btw, the 'h' you use for addresses is ignored by hex2obj (it automatically adds 0x internally, except for the counts which are treated as decimals.)

But this fake h will rule the world, I'm pretty sure, because people believe in what you show....
XD I know! is because I'm using 010 editor and just copy the address to hex2obj
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-02T17:56:04+00:00
- Post Title: PC Age Of Wulin Online

> Reply from moonpaladin ↑Fri Dec 03, 2021 1:33 am at Fri Dec 03, 2021 1:33 am
>
> I wanna know how to get these values xD still confused   show me if you canThat's no rocket science:
vertex count is 1106
size of vertex block (or whatever name it has):
0xF2BE -0xCF +1= 61936 (decimal)

FVFsize= 61936 / 1106= 56

For getting uvs offset

> Reply from shakotay2 ↑Wed Mar 24, 2021 3:45 am at Wed Mar 24, 2021 3:45 am
>
> 
(I usually don't tell twice.  )

And for the getting addresses: learning, experience, patience... required.
## Post #10
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-02T18:01:02+00:00
- Post Title: PC Age Of Wulin Online

> Reply from shakotay2 ↑Fri Dec 03, 2021 1:56 am at Fri Dec 03, 2021 1:56 am
>
> 
vertex count is 1106
size of vertex block (or whatever name it has):
0xF2BE -0xCF +1= 61936 (decimal)

FVFsize= 61936 / 1106= 56
THanks!!!
## Post #11
- Username: Lynix
- Rank: advanced
- Number of posts: 42
- Joined date: Wed Jul 01, 2015 10:11 pm
- Post datetime: 2021-12-08T17:53:36+00:00
- Post Title: PC Age Of Wulin Online

> Reply from moonpaladin ↑Thu Dec 02, 2021 11:24 pm at Thu Dec 02, 2021 11:24 pm
>
> 
Lynix wrote: ↑Fri Aug 13, 2021 5:59 am
https://drive.google.com/file/d/1dFHLg4 ... sp=sharing

  Hello Lynix, your script works for taichi panda 3 too?

Not that I know of... actually I even font know that game till now
## Post #12
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-08T21:47:01+00:00
- Post Title: PC Age Of Wulin Online

> Reply from Lynix ↑Thu Dec 09, 2021 1:53 am at Thu Dec 09, 2021 1:53 am
>
> 
Not that I know of... actually I even font know that game till now
It would be great if your script can support these models too, there is not much difference between age of wulin models   .   
[https://www.mediafire.com/file/zil5t4e9 ... S.zip/file](https://www.mediafire.com/file/zil5t4e9zngzorr/TAICHI_PANDA_EXAMPLES.zip/file)
## Post #13
- Username: Lynix
- Rank: advanced
- Number of posts: 42
- Joined date: Wed Jul 01, 2015 10:11 pm
- Post datetime: 2021-12-12T23:14:26+00:00
- Post Title: PC Age Of Wulin Online

> Reply from moonpaladin ↑Thu Dec 09, 2021 5:47 am at Thu Dec 09, 2021 5:47 am
>
> 
Lynix wrote: ↑Thu Dec 09, 2021 1:53 am
Not that I know of... actually I even font know that game till now

It would be great if your script can support these models too, there is not much difference between age of wulin models   .   
https://www.mediafire.com/file/zil5t4e9 ... S.zip/file

Yes it's the same file Format
## Post #14
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-13T14:34:27+00:00
- Post Title: PC Age Of Wulin Online

> Reply from Lynix ↑Mon Dec 13, 2021 7:14 am at Mon Dec 13, 2021 7:14 am
>
> 
Yes it's the same file Format

Would you mind in share your script?
## Post #15
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-12-13T18:29:07+00:00
- Post Title: PC Age Of Wulin Online


## Post #16
- Username: Lynix
- Rank: advanced
- Number of posts: 42
- Joined date: Wed Jul 01, 2015 10:11 pm
- Post datetime: 2021-12-14T23:23:02+00:00
- Post Title: Re: PC Age Of Wulin Online

> Reply from moonpaladin ↑Mon Dec 13, 2021 10:34 pm at Mon Dec 13, 2021 10:34 pm
>
> 
Lynix wrote: ↑Mon Dec 13, 2021 7:14 am
Yes it's the same file Format 


Would you mind in share your script?

erm "Yes it's the same file Format " means the posted script can use that files too... well the script isnt bugfree ... i have no time to finish it.. but it should work on a decent file amount for both games.
## Post #17
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-12-16T00:30:43+00:00
- Post Title: Re: PC Age Of Wulin Online

why create a topic if a ready-made solution [already exists](https://forum.xentax.com/viewtopic.php?f=16&t=12074&hilit=.xmod&start=15)
The Noesis plugin was created by me using a 3D script.
author 3d script:

> Reply from zaramot ↑Thu Oct 09, 2014 7:57 pm at Thu Oct 09, 2014 7:57 pm
>
> 

there are 3 versions in the archive: 
-only skeleton "fmt_xskt.py" in folder "only_skeleton_xskt"
-only mesh "fmt_xmod.py" in folder "only_mesh_xmod"
-and skeleton and mesh "fmt_xmod.py" in folder "mesh_and_skeleton" 
the file must be named "tpose.xskt" and be in the same folder as the mesh. Also loads a mesh without a skeleton. 

[plugin.zip](https://xentaxbackup.github.io/file/21406_plugin.zip)
## Post #18
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2021-12-16T07:27:54+00:00
- Post Title: Re: PC Age Of Wulin Online

> Reply from Durik256 ↑Thu Dec 16, 2021 8:30 am at Thu Dec 16, 2021 8:30 am
>
> 
why create a topic if a ready-made solution already exists
The Noesis plugin was created by me using a 3D script.
author 3d script:
zaramot wrote: ↑Thu Oct 09, 2014 7:57 pm

there are 3 versions in the archive: 
-only skeleton "fmt_xskt.py" in folder "only_skeleton_xskt"
-only mesh "fmt_xmod.py" in folder "only_mesh_xmod"
-and skeleton and mesh "fmt_xmod.py" in folder "mesh_and_skeleton" 
the file must be named "tpose.xskt" and be in the same folder as the mesh. Also loads a mesh without a skeleton.

Thanks for your work!
Any chance that u add gm2 file support from the same Game?
## Post #19
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-12-16T11:41:42+00:00
- Post Title: Re: PC Age Of Wulin Online


## Post #20
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2021-12-16T16:35:28+00:00
- Post Title: Re: PC Age Of Wulin Online

Idk, sorry 

Here some file example:

[https://mega.nz/file/lQtCTCIZ#EBENiR3cs ... hQzVIx3ous](https://mega.nz/file/lQtCTCIZ#EBENiR3csH5crqk8W4bPjU14S4UnmD2AXhQzVIx3ous)
## Post #21
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2021-12-21T12:15:54+00:00
- Post Title: Re: PC Age Of Wulin Online

> Reply from Durik256 ↑Thu Dec 16, 2021 7:41 pm at Thu Dec 16, 2021 7:41 pm
>
> 
KingJuls wrote: ↑Thu Dec 16, 2021 3:27 pm
add gm2 file support from the same Game?

why quote the entire post  
I do not have a game and these files

Any News Bro?
## Post #22
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-12-21T13:30:11+00:00
- Post Title: Re: PC Age Of Wulin Online


## Post #23
- Username: Lynix
- Rank: advanced
- Number of posts: 42
- Joined date: Wed Jul 01, 2015 10:11 pm
- Post datetime: 2022-01-02T12:33:32+00:00
- Post Title: Re: PC Age Of Wulin Online

the problem is (maybe).... it seems the unpacker isnt flawless OR at least "some" files act strange in a way that it COULD point to that the unpacker unpacks (partly) wrong...
## Post #24
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-25T17:14:09+00:00
- Post Title: Re: PC Age Of Wulin Online

> Reply from Durik256 ↑Thu Dec 16, 2021 8:30 am at Thu Dec 16, 2021 8:30 am
>
> 
Hello Durik256, thanks for the script! It works really well! I have found some models that have a problem maybe could you take a look? some throw error, one loads incomplete, others seems empty, and one looks just as points. Thanks alot!

[https://www.mediafire.com/file/qrbmz0f3 ... S.zip/file](https://www.mediafire.com/file/qrbmz0f3hseli90/ERROR_MODELS.zip/file)
## Post #25
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-26T17:19:43+00:00
- Post Title: Re: PC Age Of Wulin Online

> Reply from moonpaladin ↑Wed Jan 26, 2022 1:14 am at Wed Jan 26, 2022 1:14 am
>
> 
have a problem maybe could you take a look?
Yes they are different.
The file was parsed incorrectly.
objects have children at the end their number is indicated:

```
...
last int (count child)

```

But i do not see an explicit indication of the amount of materials, 
the presence of weights and bones. to load all the meshes you need to know this.
(I will not look for a difference in a few bytes and do many checks  )
if you load the first mesh, then everything is fine. only 3 files are incorrect.
 because they have a different grid type which I haven't checked:

no further research 
[fmt_xmod.zip](https://xentaxbackup.github.io/file/21675_fmt_xmod.zip)
## Post #26
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-01-26T17:24:35+00:00
- Post Title: Re: PC Age Of Wulin Online

> Reply from Durik256 ↑Thu Jan 27, 2022 1:19 am at Thu Jan 27, 2022 1:19 am
>
> 
if you load the first mesh, then everything is fine.
Thanks Durik!
## Post #27
- Username: numnumjuice
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 12, 2022 7:21 am
- Post datetime: 2022-12-21T01:42:52+00:00
- Post Title: Re: PC Age Of Wulin Online

> Reply from Durik256 ↑Thu Dec 16, 2021 8:30 am at Thu Dec 16, 2021 8:30 am
>
> 
why create a topic if a ready-made solution already exists
The Noesis plugin was created by me using a 3D script.
author 3d script:
zaramot wrote: ↑Thu Oct 09, 2014 7:57 pm

there are 3 versions in the archive: 
-only skeleton "fmt_xskt.py" in folder "only_skeleton_xskt"
-only mesh "fmt_xmod.py" in folder "only_mesh_xmod"
-and skeleton and mesh "fmt_xmod.py" in folder "mesh_and_skeleton" 
the file must be named "tpose.xskt" and be in the same folder as the mesh. Also loads a mesh without a skeleton.

On your previous gif I saw you were able to get the textures from the DDS files onto the XMOD mesh I was wondering how you were able to do that.
## Post #28
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-12-21T01:58:40+00:00
- Post Title: Re: PC Age Of Wulin Online

> Reply from numnumjuice ↑Wed Dec 21, 2022 9:42 am at Wed Dec 21, 2022 9:42 am
>
> 
how you were able to do that.
DragNDrop dds on preview Noesis and click 'No'
## Post #29
- Username: numnumjuice
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 12, 2022 7:21 am
- Post datetime: 2022-12-21T02:08:12+00:00
- Post Title: Re: PC Age Of Wulin Online

> Reply from Durik256 ↑Wed Dec 21, 2022 9:58 am at Wed Dec 21, 2022 9:58 am
>
> 
numnumjuice wrote: ↑Wed Dec 21, 2022 9:42 am
how you were able to do that.

DragNDrop dds on preview Noesis and click 'No'
Is it possible to export the model with the DDS texture on?
