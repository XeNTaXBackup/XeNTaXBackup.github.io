## Post #1
- Username: Johny233
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 28, 2018 6:38 am
- Post datetime: 2019-01-20T13:43:18+00:00
- Post Title: The Simpsons Game PS3 - txd files

Hey there, i've managed to extract the .str files with aluigi's quickbms script for .str extraction. Which then it extracted some files were extracted as .txd which are the texture files. I've tried gta's txd editors and none of them recognized the format, some of them would only show what's inside the txd but wouldn't extract or show the textures, just the names. Anyone could help me out? 

Using ViceTXD i'am able only to see the names of the files. Can't see the textures or extract em.
[https://imgur.com/a/mBOXhfP](https://imgur.com/a/mBOXhfP)



Example Files: [https://files.fm/u/p4tvwqkb](https://files.fm/u/p4tvwqkb)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-21T04:08:22+00:00
- Post Title: The Simpsons Game PS3 - txd files

here is Noesis python script to open your txd samples.  


 tex_TheSimpsonsGame_PS3_txd.zip
(991 Bytes) Downloaded 138 times


supports dxt1, dxt3, dxt5, morton swizzled rgba, top level mip only
i wasn't 100% sure about type 0x2 but i only saw one of those in all your samples.
## Post #3
- Username: Johny233
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 28, 2018 6:38 am
- Post datetime: 2019-01-21T13:14:24+00:00
- Post Title: The Simpsons Game PS3 - txd files

Thank you very much haha! Didin't expect a reply so soon. It works perfectly!
## Post #4
- Username: ftpjif
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 31, 2019 11:03 pm
- Post datetime: 2019-08-31T17:06:42+00:00
- Post Title: The Simpsons Game PS3 - txd files

hey, im looking to do the same thing, can this be achieved the same way on an Xbox360 version? if so, where can i find the .txd's. I'm able to extract .str's with QuickBMS but navigating through The Simpsons Game's folders is such a hassle.

thanks!
## Post #5
- Username: Edness
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 11, 2018 7:26 pm
- Post datetime: 2022-05-22T14:33:16+00:00
- Post Title: The Simpsons Game PS3 - txd files

(Sorry for the 3 year bump)

> Reply from Acewell ↑Mon Jan 21, 2019 12:08 pm at Mon Jan 21, 2019 12:08 pm
>
> 
[...] i wasn't 100% sure about type 0x2 but i only saw one of those in all your samples.
I've seen texture format 0x2 in other RenderWare games, and depending on how it's stored, it can either have an accompanying palette with an 8-bit bitmap where the palette is stored as a separate 0x86 (32-bit) formatted texture with an identical filename, or it's simply an A8 formatted texture.  Some games like [Burnout Revenge](https://github.com/EdnessP/scripts/blob/main/burnout/fmt_Burnout3LRD.py#L777) use both 

> Reply from ftpjif ↑Sun Sep 01, 2019 1:06 am at Sun Sep 01, 2019 1:06 am
>
> 
hey, im looking to do the same thing, can this be achieved the same way on an Xbox360 version? if so, where can i find the .txd's. I'm able to extract .str's with QuickBMS but navigating through The Simpsons Game's folders is such a hassle.
Here is a plugin for the Xbox 360 version!  It uses a different data layout, and an .ITXD extension.
[https://github.com/EdnessP/scripts/blob ... _NewGen.py](https://github.com/EdnessP/scripts/blob/main/simpsons-game/tex_TheSimpsonsGame_NewGen.py)

Edit: Hope you don't mind, I wrote my own implementation of PS3 textures in the above script, because the filenames in the original script were being cut off at 16 characters for whatever bizarre reason, and during batch exports it'd be very noticeably slow, likely due to needlessly reading and processing all the mipmaps.
## Post #6
- Username: ColROSSal
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 13, 2023 6:09 pm
- Post datetime: 2023-07-14T15:43:17+00:00
- Post Title: The Simpsons Game PS3 - txd files

Hi, so I’m trying to work on making a vrchat model of a Simpsons game character but, when I try to get the texture for the specific character it only shows one color or one texture


Example:
[image.png](https://xentaxbackup.github.io/file/24075_image.png)
## Post #7
- Username: sr20det
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 26, 2023 9:17 pm
- Post datetime: 2023-07-26T21:49:31+00:00
- Post Title: The Simpsons Game PS3 - txd files

I'm still not able to get mine to load textures in blender. Can load the models just fine but not the textures. Anyone else have this issue?


Edit: Didn't realize this post was 4 years old... Sorry
