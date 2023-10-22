## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-12T13:21:59+00:00
- Post Title: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Hey guys! I need help to get some models from the video game Ben 10 Ultimate Alien: Cosmic Destruction, 
which was powered by Vicious Engine. 



I really love this cartoon series so I'm about crazy for collecting their models.  

Well I've checked the forum and found a post about a game of Vicious Engine but didn't find much useful.
All I know so far is that for every version published on each platform some of its files were named in the
same way, for instance, xxx.ps3 on PS3, xxx.xbx on XBox 360 and xxx.wii on Wii, which implys they may
be in the same way of encryption. Besides, these models were created in 3Ds Max, but not sure if their
format is still max.



Screenshot From The Bonus Video .jpg (109.72 KiB) Viewed 1684 times



Below are some samples I extracted from the ISO file:

[XBox 360 Version](https://mega.nz/#!KdtnSDAC!rsg0yG-sHSlUmQ-4aM363nPftceweOW24sqZH1VCasY)
[PS3 Version](https://mega.nz/#!nBNRHTrC!W5ejYRR-sxnATWQg_vYzUPqGdr6xLHO2QeylV4YEo8c)
[Wii Version](https://mega.nz/#!3AMW2CbD!09WDJxP9NTM7P-e4qldgMaj3ntXIPKwSOBcJjxlutnQ)

Seems the scripts folder within stores their animation files, who knows! 

I know I can rip these models through Dolphin, but I'm more eager to get them from Xbox 360 and
PS3 versions, as there're some exclusive characters and they're of higher resources of course. So 
Wii version files are just for compare.

Any help is appreciated!
## Post #2
- Username: Bigchillghost
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-12-12T22:30:18+00:00
- Post Title: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

here are some textures from g_ad.ps3
looks like there is some kind of mesh data in there also.
might be this guy

[5.zip](https://xentaxbackup.github.io/file/12029_5.zip)
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-12T23:17:08+00:00
- Post Title: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from chrrox
>
> here are some textures from g_ad.ps3
looks like there is some kind of mesh data in there also.
might be this guy

Thanks a lot! It's Armodrillo's textures. Can you tell me how you extract them? And what about the model data?
Again thanks for your efforts. Cheers!
## Post #4
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-12-13T02:10:01+00:00
- Post Title: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

They are just dds files that have the wrong header
they start with hex 90 43 40 00
I just pasted a correct dds header on them.
The mesh data is in there you can see the different sections
just search for vaps
If you want the models I would read some of the tutorials around here and I am sure people would help you if you get stuck.
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-13T10:31:08+00:00
- Post Title: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from chrrox
>
> They are just dds files that have the wrong header
they start with hex 90 43 40 00
I just pasted a correct dds header on them.
The mesh data is in there you can see the different sections
just search for vaps
If you want the models I would read some of the tutorials around here and I am sure people would help you if you get stuck.

Thanks! I pasted a correct dds header on these textures as you told me, it worked for some textures but not all. Here the textures I extract from g_fa.ps3 for example.


 fourarms.rar
(196.73 KiB) Downloaded 93 times



How do you know these textures are dds files?  I mean could them be other formats? I tried to do the same with the g_ad.xbx but it didn't work. Neither their contents match.

Seems these files not only store textures & meshes data, but some character sounds as well. Then what am I supposed to do after finding vaps with hex editor? And yeah it would be great if you could read some tutorials here!
## Post #6
- Username: Bigchillghost
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-12-13T11:12:21+00:00
- Post Title: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

they all seem like normal dds files to me
just split them by searching for 90 43 40 00
start with this tutorial
[viewtopic.php?f=29&t=10894](http://forum.xentax.com/viewtopic.php?f=29&t=10894)
vaps are the different chunks of data in the file
just split the file on each vaps and you can see the different types.
I know they are dds files because they have the 0x80 header of a dds and also the data looks like dds data.
also you can see an image if you just look at the raw data as rgba32
[fa_orig.zip](https://xentaxbackup.github.io/file/12034_fa_orig.zip)
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-13T11:18:46+00:00
- Post Title: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

here is a zip file containing a generic bms script to split the textures from the *.ps3 or *.xbx archives   
and a Noesis python script to open the resulting *.ps3dxt or *.xbxdxt textures 


 Ben10_PS3_X360_texture_scripts.zip
(1.31 KiB) Downloaded 124 times
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-13T12:02:07+00:00
- Post Title: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from chrrox
>
> they all seem like normal dds files to me
just split them by searching for 90 43 40 00
start with this tutorial
viewtopic.php?f=29&t=10894
vaps are the different chunks of data in the file
just split the file on each vaps and you can see the different types.
I know they are dds files because they have the 0x80 header of a dds and also the data looks like dds data.
also you can see an image if you just look at the raw data as rgba32

Thank you chrrox! I exactly have no idea about dds files' features though and maybe I will know it better later. I'm covering the tutorial and if everything goes well, I may be able to do it myself!

Again thanks for your sincere help!
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-13T12:10:26+00:00
- Post Title: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from AceWell
>
> here is a generic bms script to split the textures from the *.ps3 archives  
Code: Select allfindloc OFFSET binary "\x90\x43\x40\x00"
do
    goto OFFSET
    get SKIP long
    findloc NEXT_OFFSET binary "\x90\x43\x40\x00" 0 ""
    if NEXT_OFFSET == ""
        get SIZE asize
    else
        math SIZE = NEXT_OFFSET
    endif
    math SIZE -= OFFSET
	get NAME basename
	string NAME + "_"
	string NAME + OFFSET
	string NAME + ".dxt"
    log NAME OFFSET SIZE
    math OFFSET = NEXT_OFFSET
while NEXT_OFFSET != ""


and a Noesis python script to open the resulting dxt textures
tex_Ben10UltimateAlienCosmicDestruction_PS3_dxt.zip

i have not looked at any xbox360 samples yet

Thanks a lot man! I was planning to write a tool myself in C language later but what you did just saved me lots of time 
so I can stick on working out the meshes data!
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-13T13:53:56+00:00
- Post Title: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

i updated my previous post with a zip file containing a better bms and
Noesis python script to handle both PS3 or X360 textures  
you can delete that one in your quote now, is obsolete
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-13T14:48:03+00:00
- Post Title: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from AceWell
>
> i updated my previous post with a zip file containing a better bms and
Noesis python script to handle both PS3 or X360 textures  
you can delete that one in your quote now, is obsolete

Great! Now I can successfully extract all textures from both XBox 360 & PS3 versions.
Thanks for the efforts dude!
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-14T16:11:27+00:00
- Post Title: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Models are simple 1-mesh models (at least from the first look)



Not sure if you need bones, but if not, you can get all models with hex2obj
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-14T16:36:07+00:00
- Post Title: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from daemon1
>
> Models are simple 1-mesh models (at least from the first look)



Not sure if you need bones, but if not, you can get all models with hex2obj

Bones are not a must if animations cannot be imported into 3D applications but it would be nice to have bones though. So is it hard to extract bones data? If it's not a practical idea I may just get the meshes with hex2obj.
Anyway thanks for your hints!
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-14T17:32:24+00:00
- Post Title: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from Bigchillghost
>
> So is it hard to extract bones data? If it's not a practical idea I may just get the meshes with hex2obj.
Anyway thanks for your hints!

Getting bones will require some programming even in simplest case.
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-14T23:06:09+00:00
- Post Title: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from daemon1
>
> Bigchillghost wrote:So is it hard to extract bones data? If it's not a practical idea I may just get the meshes with hex2obj.
Anyway thanks for your hints!

Getting bones will require some programming even in simplest case.

Well, then. Obviously I don't have such skill as programing to extract that, so it's OK for me to just extract the meshes.
## Post #16
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-15T12:11:30+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

from g_ad.xbx  



g_ad_xbx.png (57.95 KiB) Viewed 332 times


the same character in g_ad.ps3 has the same settings except for the start addresses
step1 start address = 11d0e0
step3 start address = e3220

the characters appear as one mesh but there is submeshes in the file,
i don't know if they are accessories or what though
## Post #17
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-15T15:09:45+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> from g_ad.xbx  
g_ad_xbx.png
the same character in g_ad.ps3 has the same settings except for the start addresses
step1 start address = 11d0e0
step3 start address = e3220

the characters appear as one mesh but there is submeshes in the file,
i don't know if they are accessories or what though

I've read the tutorial on hex2obj but didn't get the point how exactly to find the address. Even with the addresses you provided, I still don't know why they mark the start of the meshes. Moreover, there's gonna be plenty of work to get all the meshes by hand. Is it possible to write a tool with hex2obj built in to extract them automatically? If only I know what to do about it.
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-15T15:31:42+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> Moreover, there's gonna be plenty of work to get all the meshes by hand. Is it possible to write a tool with hex2obj built in to extract them automatically?

There are about 10 characters here. It will be MORE work to write a tool than to get all the meshes by hand.
## Post #19
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-15T16:00:21+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

i don't think this is a good way to learn Hex2obj either because you are looking 
in an archive for model data as opposed to a typically much smaller model file.
you should look through past model threads here on Xentax and practice with several
actual model file samples opened with a hex editor and compare the data you see, 
i think you will learn to find the correct data and patterns in no time.
## Post #20
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-15T16:57:51+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from daemon1
>
> There are about 10 characters here. It will be MORE work to write a tool than to get all the meshes by hand.

There're still other two games of Ben 10 powered by the same engine that I'd like to get models from.
Actually there are over 17 characters in this game, so plus the other two there're gonna be more.
I know it's much easier to get them by hand than to write a tool but honestly I don't have enough experience to handle it, let alone time's litmited for me the following days.
Maybe I should first learn it piece by piece with much more simple samples as AceWell suggested when get enough time. Sorry for asking for that much.
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-15T18:07:32+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> There're still other two games of Ben 10 powered by the same engine

Note that its possible in those other games format may be slightly different, and may require 3 different tools. I've seen that many times.

I'm not saying you're asking for too much, but understand, we also don't have much time.
## Post #22
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-17T13:31:12+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from daemon1
>
> Note that its possible in those other games format may be slightly different, and may require 3 different tools.

You're right. They are different, at least the textures no more start at 90 43 40 00. Well, it's getting harder for me then 
coz I have no idea about how to identify the start address of these textures when they're put into one xbx file. How am 
I supposed to do that? Is it really pure experience? There should be some reasons, right?
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-17T13:49:32+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> daemon1 wrote:I have no idea about how to identify the start address of these textures when they're put into one xbx file. How am 
I supposed to do that? Is it really pure experience? There should be some reasons, right?

The ways people store their data is very diverse. The only way is to learn how textures may look like, find some patterns inside of data, and then find a way to detect this.
## Post #24
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-17T14:19:22+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from daemon1
>
> The only way is to learn how textures may look like, find some patterns inside of data, and then find a way to detect this.

I can compare several dds files to figure out their common characteristics however these characteristics may only shared by the several files I compared. Namely I'm not likely to find out the real dds texture patterns. I really have done some research myself, by comparing dds maps with different sizes, but only find that they do have a 0x80 header like this:



0x80.jpg (44.13 KiB) Viewed 304 times


And the four bytes of 0x0000000C to 0x0000000D and 0x00000010 to 0x00000011 are the data of their sizes. But that's all I can do I'm afraid.
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-12-17T18:44:17+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> Is it possible to write a tool with hex2obj built in to extract them automatically? If only I know what to do about it.Such tool can be created using this project: [viewtopic.php?f=29&t=12756](http://forum.xentax.com/viewtopic.php?f=29&t=12756)

It requires that you do a format analysis and have some C coding skills.

There's some assumed pattern in g_ad.ps3 (B401581D00000000) which could hint to submeshes (10x?):



g_ad-ps3.JPG (119.07 KiB) Viewed 295 times


H2O file for 6th submesh (table at 0x129000):

0x12ABA0 1728
Vb1
20 12
0x1291C0 330
120000
0x0 255
## Post #26
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-20T13:07:06+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from daemon1
>
> Models are simple 1-mesh models (at least from the first look)

I've read the tutorial again and again and indeed I've learned a little more than before. However I'm still not quite good at this:
 


g_hm_ps3.jpg (228.35 KiB) Viewed 288 times


(Also tried the g_hm.xbx, with similar results)
Seems I'm on the right track of the trick. But how should I exactly identify the correct start address of the face indices ? I've tried almost every address of these zero bytes between the gap but the vertices are always wrong.
## Post #27
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-20T13:11:35+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

And here the result for the g_hm.xbx:



g_hm_xbx.jpg (224.21 KiB) Viewed 288 times
## Post #28
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-12-20T14:19:35+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> But how should I exactly identify the correct start address of the face indices ?
This is the code for *.ps3 files (pFBuf: pointer to file buffer):

```
            while (*pFBuf==0){
                pFBuf--; j-- ;
            } 
            addrFI = j - 2*dwFaceIndCnt[cnt] ; addrFI++ ;
```
where addr[] contains the addresses of the pattern I spoke of in a former post.

As you can see it's very simple code. So I'd suggest  to learn C (or any other programming or script  language).

Up to then you might try out this tool (for ps3 only) to create the H2O files for you:


 MakeH2O-bins-Ben10UA.zip
(66.5 KiB) Downloaded 53 times


btw: H2O file for the last submesh is always wrong; no time to care for that
(also tested on three *.ps3 files only)
## Post #29
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-20T14:31:07+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> 
g_hm.ps3  



g_hm_ps3.png (40.28 KiB) Viewed 281 times
## Post #30
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-20T17:17:51+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> 
g_hm.ps3  
g_hm_ps3.png

Thanks! Actually I did have tried that startaddr of the face indices, but using a wrong vertices startaddr. Since 4532*44(dec) equals 0x30af0, subtract it from 0x1b3b00 we get 0x183110. Then why should the correct address be 0x182fe0? And I'm still confused about the FVFsize and UV pos. How can I know the vertex block size is 44 bytes and get the correct UV pos? Is that acquired by trial 'n error? Or are there other ways to do that?
## Post #31
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-20T17:25:31+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from shakotay2
>
> As you can see it's very simple code. So I'd suggest  to learn C (or any other programming or script  language).
Up to then you might try out this tool (for ps3 only) to create the H2O files for you:
MakeH2O-bins-Ben10UA.zip
Thanks a lot mate! It works fine for almost all *.ps3 files. But as you've said, it requires knowledge about model analysis. So I still need to learn the basic before I can handle such thing as making an automatic tool.
## Post #32
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-20T19:16:29+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> Since 4532*44(dec) equals 0x30af0, subtract it from 0x1b3b00 we get 0x183110. Then why should the correct address be 0x182fe0?
i never do any of that math unless i'm writing a script   , don't over-think it,
i just locate a pattern and follow it to the beginning or end and record the offsets and length.


> Reply from Bigchillghost
>
> And I'm still confused about the FVFsize and UV pos. How can I know the vertex block size is 44 bytes and get the correct UV pos? Is that acquired by trial 'n error? Or are there other ways to do that?
FVFsize is just the number of bytes holding data for each vertex.
[http://www.toymaker.info/Games/html/fvf.html](http://www.toymaker.info/Games/html/fvf.html)
in your hex editor just expand the right side column width until you see
the bytes line up into a vertical pattern then check for a found pattern.
UV pos is always trial n error with me, unless there is some source specs around to look at.


also in g_hm.ps3 for that character the number of vertices is stored at 0x182e04
and the number of face indices is stored at 0x182e0c both in big endian 32bit integers.
## Post #33
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-21T15:37:38+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> i just locate a pattern and follow it to the beginning or end and record the offsets and length.

The question is how am I supposed to locate the correct pattern? That is, how can I know whether it's the pattern I'm looking for?
I've noticed that the pattern of g_ad.ps3 is B4 01 58 1D 00 00 00 00, while the one of g_hm.ps3 is B4 01 C8 13 00 00 00 00. Are their patterns always start with B4 01, with the latter four bytes as 00 00 00 00 in this case (or universally) ?

> Reply from AceWell
>
> also in g_hm.ps3 for that character the number of vertices is stored at 0x182e04
and the number of face indices is stored at 0x182e0c both in big endian 32bit integers.

With the correct pattern found, it's easy to get the face indices counts as well as the one of vertices, coz they seem always in the same position right before the pattern's offset. 

> Reply from AceWell
>
> in your hex editor just expand the right side column width until you see
the bytes line up into a vertical pattern then check for a found pattern.

What do you mean by "vertical pattern"? Is it something like this?



A.jpg (222.63 KiB) Viewed 283 times
## Post #34
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-12-21T17:36:11+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> I've noticed that the pattern of g_ad.ps3 is B4 01 58 1D 00 00 00 00, while the one of g_hm.ps3 is B4 01 C8 13 00 00 00 00. Are their patterns always start with B4 01, with the latter four bytes as 00 00 00 00 in this case (or universally) ?This should not be referred to as patterns (I feel guilty  ), since it's different from the ones, AceWell spoke of.

B4 01 is more some kind of signature bytes or markers to identify "magic tables" containing counts and (maybe) offsets. (But since me seems to be the only one who uses these terms you can ignore them.  )

B4 01 is the sequence I used in the Make_H2O tool combined with other checks (bytes to be zero, vertex count, FI count == values  that makes sense?). 

Nobody can tell you if it's always B4 01, I guess. But it obviously works for many models.
## Post #35
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-22T00:20:31+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from shakotay2
>
> This should not be referred to as patterns (I feel guilty  ), since it's different from the ones, AceWell spoke of.

Whoops, I thought a pattern was a piece of sequence differed from file to file, since you said it was some assumed pattern in your previous post. So what exactly does it means when it comes to a pattern? Is it a structure how archives are built just as its name implies?
## Post #36
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-12-22T11:13:17+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

Feel free to create your own "theory of patterns".  

What I tried to say was that there's a difference between the patterns (structures) to find FVF sizes which AceWell spoke of and the byte sequences to identify "magic tables".

Nothing more and nothing less.

(While for FVFsizes a good method is to divide the size of the vertices list by the vertex count.
Thing is that often it's unclear where the vertices list to end especially for half floats or words.)
## Post #37
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-22T16:49:39+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from shakotay2
>
> While for FVFsizes a good method is to divide the size of the vertices list by the vertex count.
Thing is that often it's unclear where the vertices list to end especially for half floats or words.

So even doing a calculation is not always working. Then what's the pattern AceWell spoke of? 
It really drives me crazy to still be stuck at finding the correct vertices startaddr, or anything hex2obj needed to perform its task. Maybe these so-called patterns would have some common features which could make it easier to find some in different files.
## Post #38
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-22T17:25:10+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> Then what's the pattern AceWell spoke of?
this post explains what i was talking about for patterns
[viewtopic.php?p=120284#p120284](http://forum.xentax.com/viewtopic.php?p=120284#p120284)

find the pattern, i find it easier to see on the text side
set the text column width to reveal a vertical pattern to see where it starts
follow that pattern to where it starts and you have your offset to test for
set the FVFsize in Hex2obj to the number of bytes you expanded the text column
test for point cloud to see if it is vertex data
play with endianess and float/short/halffloat until the point cloud makes sense

then you can look for face indices which look like a scrambled alphabet on the text side
then go to the hex side and put your cursor where you think that pattern starts and check
that offset in Hex2obj, worry about the precise step1 count last.

i just use HxD and windows calculator in scientific mode, nothing special
## Post #39
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-12-22T20:24:39+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> So even doing a calculation is not always working. Then what's the pattern AceWell spoke of? 
It really drives me crazy to still be stuck at finding the correct vertices startaddr, or anything hex2obj needed to perform its task. Maybe these so-called patterns would have some common features which could make it easier to find some in different files.yeah - I really like that spirit!  
Unlike many others you really want to know what you're doing.

I always wished to have a full "set of rules" how to analyse 3D model data.
Again this discussion showed me the importance of finding structures (or patterns, whatever  ).

Btw, once the FVF size is found creating/searching point clouds may be a good idea for a successful proceeeding.
So if you see a sphere for example you very likely hit the normals list in the 3D data.
## Post #40
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-23T05:36:46+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from shakotay2
>
> yeah - I really like that spirit!  
Unlike many others you really want to know what you're doing.

Well, I have to know that if I want to extract a mesh successfully myself.  
So that's nothing since I know I cannot always rely on others. But as a beginner, I know measly about this field and therefore I may
ask a lot of questions, which may seem ignorant to the experienced.
Howerer I sincerely appreciate that people like you and AceWell explained them patiently and I'm glad I've met you guys!
## Post #41
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-23T08:03:34+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> this post explains what i was talking about for patterns
viewtopic.php?p=120284#p120284

find the pattern, i find it easier to see on the text side
set the text column width to reveal a vertical pattern to see where it starts
follow that pattern to where it starts and you have your offset to test for
set the FVFsize in Hex2obj to the number of bytes you expanded the text column
test for point cloud to see if it is vertex data
play with endianess and float/short/halffloat until the point cloud makes sense

then you can look for face indices which look like a scrambled alphabet on the text side
then go to the hex side and put your cursor where you think that pattern starts and check
that offset in Hex2obj, worry about the precise step1 count last.

i just use HxD and windows calculator in scientific mode, nothing special

Awsome! With the images I easily understood your method however there always could be some problems for me like this:



Neither the addr of the symbol > (0xdf3e8) nor the one ot the ? (0xdf3e4) is the vertices startaddr, so I tried the one of the = (0xdf3e0) conbined with other possible FI startaddrs. I also found the addrs where FI count & vertices count are stored, the sequence no more starts as B4 01 though. And then I got this from g_ra.xbx:



Rath.jpg (81.42 KiB) Viewed 235 times


The first mesh I extracted aha. Of course it wasn't done at a go, and therefore I need to practice more to really get the hang of it.

Cheers!
## Post #42
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-23T08:51:00+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

Also another successful test of g_wh.ps3:  



g_wh_ps3.jpg (106.17 KiB) Viewed 235 times
## Post #43
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-12-23T12:03:12+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> Also another successful test of g_wh.ps3: 
yeah, see, there was a problem with the H2O-Maker. Also fixed the last submesh (quick fix only, may fail).
(A +/- 1 correction of the vertex count might be required because sometimes the value in the ps3 file
is different from the calculated one.)

(exe file only. Dlls from the post of 20th Dec, 3:19 pm, required)
[Make_H2O-Ben10.zip](https://xentaxbackup.github.io/file/12114_Make_H2O-Ben10.zip)
## Post #44
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-23T16:04:34+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> Neither the addr of the symbol > (0xdf3e8) nor the one ot the ? (0xdf3e4) is the vertices startaddr, so I tried the one of the = (0xdf3e0) conbined with other possible FI startaddrs.
yeah the repeating bytes aren't necessarily going to be a start address for the vertex block, 
only use that pattern to trace back to where it begins. after you adjust the column width it
is usually clear to see where the pattern begins and ends then you can start checking offsets.
## Post #45
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-24T16:49:43+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> i updated my previous post with a zip file containing a better bms and
Noesis python script to handle both PS3 or X360 textures

I've also successfully extracted some meshes from another Ben 10 related game, Cartoon Network Punch Time Explosion XL.
The textures' headers also start as 0x90 43 40 00, which can be splited by your bms script. However when I converted them to dds
in Noesis, the python script didn't work well. Seem these textures are different from those in Ben 10 UA.



Since I know quite a little about textures data analysis, I'm not able to fix them. Could you please update the python script so as to
support them?

Samples [here](https://mega.nz/#!WUtDTRqA!KBumHvoqwblDXstI38JETOmEoyHvYODJbsyZhcs71oA).
## Post #46
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-24T18:45:19+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

looks like an additional layer of tiling on top of the 360 untile, i don't know, can't make anything of it
its a different game from a different year so things probably change in development.
## Post #47
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-25T07:29:39+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> looks like an additional layer of tiling on top of the 360 untile, i don't know, can't make anything of it
its a different game from a different year so things probably change in development.

I dumped some textures from the Wii version with Dolphin and found they had the same content but only in different height
and width.



comparision.jpg (210.85 KiB) Viewed 303 times



I placed them into one image for a comparision. However the Wii version maps' resolutions (128x128) are too low for the XBox meshes.
I hope there're other ways to get them.
## Post #48
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-25T18:33:47+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

ah, had another closer look and the data offset is just different   try this Noesis python script for that game textures


 tex_Ben10CartoonNetworkPunchTimeExplosionXL_xbxdxt.zip
(747 Bytes) Downloaded 65 times
## Post #49
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-26T13:38:53+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> ah, had another closer look and the data offset is just different   try this Noesis python script for that game textures

Thanks! Textures extracted successfully now. But when I sorted out the maps I found some textures were missing, same as Ben 10 Ultimate Alien. Interestingly, these textures are exactly those I can't dump properly with Dolphin. There're some big files in the level folders which the BMS script couldn't split out anything. Maybe the missing textures could be contained in them, or still in the character files but with different headers, I dont't know. I grubbed every file but still found nothing. But that's not the point to worry about yet.  

I'm working on the last Vicious Engine game of Ben 10, Ben 10 Alien Force: Vilgax Attacks. Same as Cartoon Network Punch Time Explosion XL, the meshes are easy to obtain, while the textures not. Their header no longer start like before, but as 0x00 00 00 01 instead. Still I splited them into parts and used the Ultimate Alien python script which I changed the offset and the registered game name & format to convert them. (They still have the 0x80 headers)

But Noesis gave me an error saying bad params at line "data = rapi.imageUntile360DXT". Well I didn't expect it worked though.
This game is developed earlier than Ultimate Alien. Have no idea whether it's easier to get the textures or not. However there's a change of the way how meshes are stored. The characters models are contained in the files within the level folders this time rather than the global folder. Not quite sure whether the global folder include only textures or not, so I uploaded both it and other files which I got the meshes from.

[global](https://mega.nz/#!HQE2hJQD!eryHzfhZJJ3Ss8ZplolySeVDmz2_gfdzToqafiadO2U)

[l_bell](https://mega.nz/#!HQlDFDhR!4ESvTpnL8BX-dMuG_z-fluU4ICdCNQjYaxCoVzJi7Og)
## Post #50
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-27T01:25:56+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> I'm working on the last Vicious Engine game of Ben 10, Ben 10 Alien Force: Vilgax Attacks.
global
l_bell
here is a zip with a bms script to split the textures from the xbx files 
and a Noesis python script to open the resulting textures for that game 


 scripts.zip
(1.17 KiB) Downloaded 64 times



edit
i just realized Noesis won't use a particular script selected in the dropdown
list, alphabetical order seems to be the  priority factor for some reason.   
i guess you will have to move out the Ben 10 scripts from the python folder
you are not using at the time so there won't be a conflict.
## Post #51
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2016-12-27T03:05:30+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> here is a zip with a bms script to split the textures from the xbx files 
and a Noesis python script to open the resulting textures for that game

Wow, great! Thanks a lot!   

> Reply from AceWell
>
> i just realized Noesis won't use a particular script selected in the dropdown
list, alphabetical order seems to be the  priority factor for some reason.   
i guess you will have to move out the Ben 10 scripts from the python folder
you are not using at the time so there won't be a conflict.

Yeah, I also realized that since last time I converted the CNSR textures. Since there're three different scripts to convert the textures, I
just simply changed the output & input formats in both the BMS and the Noesis python scripts for each game so they're specific formats in Noesis. 
Anyway thanks for that!
## Post #52
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-01-15T17:15:04+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

@AceWell 

Sorry to bother you again.   
After finishing that three game I was going to extract meshes from Ben 10 Omniverse, another game of Ben 10 series powered by Vicious Engine 2. However the game structure
was totally different from its previous three games. While its files mainly named in hexadecimal characters I was trying to convert them to their ASCII codes but it still didn't 
make sense. So I guessed it could be something related to addresses.
Luckily I've figured out which folder stored the character meshes, except knowing what exactly the file name stands for though.
Whatever, I chose a large file there to start with, but every time I tried a possible FI address, no matter if I switched litE to bigE, or Word to DW, the vertices count I got then
was always nearly overflow. So yes, I was stuck there and didn't know what I did wrong.

So I was wondering if you could give me a hand with it.

[Samples link here](https://mega.nz/#!fQU1jbhA!6-o4SRiWbGmrMkhV8ga0wLu2uAkBSJbtu8gxa9K6d2w).

And please don't forget the textures if possible!
## Post #53
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-15T19:04:16+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

if i were you i'd take these big archives to zenhax and have aluigi make 
a bms script to split the files which would make them easier to work with.
## Post #54
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-01-16T14:08:14+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> if i were you i'd take these big archives to zenhax and have aluigi make 
a bms script to split the files which would make them easier to work with.

Well, have never noticed that forum before though. Maybe I can do some explorations there.
However as I know, splitting an archive could require a lot researches(or maybe just for me?  ).
So is it really a good idea to ask aluigi to do it?
Actually my first thought was asking you to have a quick look at these samples (could be a smaller one),
and see if there're any meshes (I did see some ''scrambled alphabets'' there) that Hex2Obj could handle. 
Since there're no zero bytes between the vertices & the face indices, it got tougher for me to identify
the correct offsets.

Smaller samples here should make it easier to work with:

[Ben 10 Omniverse EntityTemplates](https://mega.nz/#!aUcWAI7R!SJPYSK6LRUZoaxDek3eNg76otFHcyyKuTLf6j7SzScg)
## Post #55
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-17T00:43:57+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

there are a few erratic patterns and some readable text, but nothing consistent that makes sense to me. 
there may be other files that contain the models and textures that you have not discovered yet.
## Post #56
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-01-23T07:04:57+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> there may be other files that contain the models and textures that you have not discovered yet.

Most of the files in the EntityTemplates folder should contain models and textures. Only five characters have separate meshes and textures.
I replaced the textures of these characters and they look like this in the game:



As you can see their textures are missing. Even so it didn't make it easier for me to get the meshes. 

[Here](https://mega.nz/#!zUMClSjS!MrvYlrFUxlcD-RBmPURVX7hK7OGy6HgmdYMNJv3IDR8) I uploaded these files. I renamed them with meaningful words to help identify meshes and textures files. Files prefixed by "CHAR"
contain only meshes, while files prefixed by "SKIN" contain only textures. Could you have a look at them?
## Post #57
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-23T08:16:21+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

i don't know, if there is models and textures in these the data makes no sense to me, sorry
## Post #58
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-01-24T07:06:01+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

Sad to hear that.  
Seems these models are packed as max and ma formats.



shot.jpg (143.41 KiB) Viewed 204 times



Have you looked at the textures files? Maybe they ain't DDS files. Look like PNG files imho.
## Post #59
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-01-24T10:58:42+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> 
Most of the files in the EntityTemplates folder should contain models and textures. Only five characters have separate meshes and textures.
I replaced the textures of these characters and they look like this in the game:

Those files are definately compressed.
You can see the uncompressed size at offset 0x8
## Post #60
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-01-24T13:48:37+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from chrrox
>
> Those files are definately compressed.

Thanks for the infomation. Is there any way to uncompress these data?
## Post #61
- Username: g1g2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 27, 2017 7:31 pm
- Post datetime: 2017-01-27T12:02:34+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

hi there im a big ben10 fan myself so it would really be cool if you shared with us the models like zip/rar thanks everybody for contributing in this
## Post #62
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-02-18T00:47:03+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

is there any way to get these models with bones?
## Post #63
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-05-04T08:23:11+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> i don't know, if there is models and textures in these the data makes no sense to me

Hi! 
I'd done some research on the Ben 10 Omniverse files several months ago after I was told that the data
were compressed. But not untill recently did I figure out the way to decompress them. The size of the
umcompressed data recorded in the header helps me determine what algorithm it uses, and I got some
texts perfectly making sense. The model data is sequential，with notes in front of each type of data.
They're in order of $position, $normal, $uvatlas, $texcoord0, $tangent0, $binormal, $blendweight
and $blendindex. I tried to load the mesh with Hex2Obj but the point clouds were messed up like this:



wildvine.jpg (199.9 KiB) Viewed 304 times



It seems that the mesh is overlapped with several same meshes whose vertices were flattened
into orthogonal planes.
Tried with different face and vertice start addresses but nothing changed. 
Could you take a look at them?

Here're some samples of the umcompressed data: 

[uncompressed data samples](https://mega.nz/#!aQVgwYya!9QeXmmWTtiaf3tcuH_qxFtgCxVk0us8xT7vOxTwbxQs)

Files prefixed with "SKIN" should contain only textures otherwise they contain both textures
and meshes. The hexadecimal sequence is the original file name which is still in the umcompressed data.

Thanks in advance!
## Post #64
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-05-04T11:47:11+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

point cloud looks ok to me (if you use one at a time), problem is how to get suiting face indices
edit: got it



Wildvine-dmp.JPG (117.03 KiB) Viewed 300 times
## Post #65
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-05-04T22:09:02+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> I'd done some research on the Ben 10 Omniverse files several months ago after I was told that the data were compressed. But not untill recently did I figure out the way to decompress them. The size of the umcompressed data recorded in the header helps me determine what algorithm it uses, and I got some texts perfectly making sense.
care to share how you decompressed your samples?
## Post #66
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-05-05T08:38:56+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from shakotay2
>
> point cloud looks ok to me (if you use one at a time), problem is how to get suiting face indices
edit: got it

I'm so impressed that you still follow with interest this thread.  

I was using the same FI startaddr as you did in the pic, but using 12 bytes as FVFSize and 0x2330 as vertices startaddr.
And I used seq mode since the vertices and UVs & normals are at separated blocks.(Yeah, why is it a blocked model?)

So I changed it to VB mode and I got this:



Diamondhead.jpg (96.6 KiB) Viewed 281 times
## Post #67
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-05-05T08:57:09+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

This is what I got from my lastest research:



wildvine_analysis.jpg (224.22 KiB) Viewed 280 times



The face indices counts is always 0x2B bytes after the string "texcoord0" at its first occurence, which also appears in the texcoord
block. However the vertices counts is not always accurate which should be fixed by Hex2Obj.

So the texcoord0 block is its UVs, then what is the uvatlas for?
## Post #68
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-05-05T11:05:43+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> care to share how you decompressed your samples?

I'm glad that you're interested in it. Well, it's gonna be a "long" story, which took me several months... (Athough I put it aside for most of the time after I'd finished the analysis of the header.   )
Few months ago...
Chrrox said that the data were compressed. So I did some research about this format and this was what I'd discovered:



compress_analysis.jpg (252.77 KiB) Viewed 276 times



At first I searched the size of this file which is 0x1CEB6B. To avoid confusion I search for 001CEB6B and it led me to 0x178. That means these four bytes is an offset. And looked back for every four bytes I found that they had some same features that their first byte was always ZERO byte and they're decreasing backwards. So they might also be offsets, and what I needed to do was to find out where the first offset was stored. So just continuely moved backwards and you can see 00 00 01 7C, and another four bytes before is 00 00 00 5B. Since 0x5B is smaller than 0x178 (the offset of the end of this file), it can't be any offsets. So what is it for? I compared different files and found that the header was 8 bytes long and the values of the four bytes at 0xC differed from file to file.
The I picked the smallest file, which had only 2 Kb, to understand this four bytes more easily. Then I discovered that there were only two offsets from 0x10 to 0x17, and it chanced to be 0x00 00 00 02 at 0xC. They I come back to check this file and found it matched the number of these offsets. So it was the counts of the offsets, and the four bytes at 0x10 should be the start of the compressed data. So just jumped to 0x17C to see what would happen. It read 08 FA AF FA AF 00 00 00, same as other files. This comfirmed that it was the start of the compressed data since 0x8FAAFFA won't be an offset. At offset 0x8 these four bytes is larger than the archive so it should be the uncompressed size of the data. (I didn't notice that chrrox had reminded me about it later.  )
But I didn't know how to decompress them and chrrox didn't reply...

Few monthes went by...

One day I checked aluigi's site again and found a tutorial on the comtype scanner 2. (I didn't know how to get that script work before and was using only the bms script without the .bat file)
Then I tested it on a 2 Kb file which I removed the header & the stored offset. After the batch script finished its job, I filtered the files I didn't want with the assistance of the the uncompressed size stored inside the raw data. And then checked the results in HexEdit one by one to find the correct output. Therefore I discovered that it used LZF/LZFX compression, either result is the same. You can see that the decompressed file name like "Art\Characters\c_wildvine.max" which was uncompleted in the original file. I believed the data were decompressed correctly especially when I load it into hex2obj and saw the point cloud made sense. But what's interesting is that if I decompress it with BLOSC algorithm, the texts will still look correct while the model data would be totally different (with larger size), but the point cloud didn't change at all!
This is the BMS script I wrote to decompress the data:

```
#http://aluigi.altervista.org/quickbms.htm

idstring "\x2F\xA9\xC0\x56"
goto 0x8
get SIZE long
findloc OFFSET binary "\x08\xFA\xAF\xFA"
get ZSIZE asize
math ZSIZE - OFFSET
goto OFFSET
get NAME basename
string NAME + "_"
string NAME + OFFSET
string NAME + ".ucp"
comtype lzf
clog NAME OFFSET ZSIZE SIZE
```


It was written for the files I renamed manually. I can't get the getDstring command work. Can you help me improve it?
The original name (hexadecimal sequence) is four bytes before the name string, and the length of the name is
one byte (the symbol $) before it. The string doesn't end with null byte.
For example, the original name of the file CHAR_Wildvine is 91 FC 4C 91 5B 0D BE 44, while in the hex editor there is content like

```
   
91 FC 4C 91 5B 0D BE 44         20 0A         0D         24      43 48 41 52 5F 57 69 6C 64 76 69 6E 65      20
```


I added this piece of code to the begining of the script but it didn't work.

```
findloc OFFSET1 string ORIG_NAME
goto OFFSET1
get SKIP1 short
get LENGTH byte
get SKIP2 byte
getDstring NAME LENGTH
```
## Post #69
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-05-06T02:57:07+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> Can you help me improve it?
certainly  

```
comtype lzf //lzf,lzfx,BLOSC 
get ZSIZE asize
idstring "\x2F\xA9\xC0\x56\xCD\x33\x2E\x57"
get SIZE long
get NUM_OFFSETS long
get OFFSET long
math ZSIZE - OFFSET
xmath NAME_OFF "OFFSET + 0x33"
goto NAME_OFF
get NAME_LENGTH byte
get SKIP byte
getdstring NAME NAME_LENGTH  
string NAME + ".et_decomp"
clog NAME OFFSET ZSIZE SIZE

```


i think that offset table at the beginning is relevant for proper splitting though,
might need to research that a little more because the decompressed files look
like they contain multiple, like the texture files may have many textures etc.
## Post #70
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-05-06T09:37:00+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> 
certainly  
Code: Select allendian big
comtype lzf //lzf,lzfx,BLOSC 
get ZSIZE asize
idstring "\x2F\xA9\xC0\x56\xCD\x33\x2E\x57"
get SIZE long
get NUM_OFFSETS long
get OFFSET long
math ZSIZE - OFFSET
xmath NAME_OFF "OFFSET + 0x33"
goto NAME_OFF
get NAME_LENGTH byte
get SKIP byte
getdstring NAME NAME_LENGTH  
string NAME + ".et_decomp"
clog NAME OFFSET ZSIZE SIZE
Thanks! You'd just made it much more simple!

> Reply from AceWell
>
> i think that offset table at the beginning is relevant for proper splitting though,
might need to research that a little more because the decompressed files look
like they contain multiple, like the texture files may have many textures etc.

Yeah, I'd considered that possibility too. I'd also split few files from a texture archive before decompressing
them. But I didn't see any useful info at the header of these split files, same as in their decompressed data.

And I'd just written a script to split the file according to the offset table, and then decompressed them. 
It turned out that all the separated files except the last one have a fixed size 0x8000 (exactly 32 Kb) after 
being decompressed. 
Seems it uses multi-volume compression.

Here the split textures if you want to take a look at:
[SKIN_Arctiguana_Teen & SKIN_Wildvine_Young](https://mega.nz/#!PQsFWbQY!SiywrF-YjcHiFUcwYzV6EypfkgGVuRkh76RcTyHuj5w)
## Post #71
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-05-16T10:06:42+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> 
the decompressed files look like they contain multiple, like the texture files may have many textures etc.

The texture files contain diffuse and normal maps, as well as other smaller textures. I can't find a particular strings or sequences in front of the texture data to locate where it start, so instead I have to use the strings right after its name to locate the textures especially in meshes files(might need to change _d to _n to locate normal maps). The texture data look like dds format so I just add a 0x80 header to it and it looks like this:



texture_wildvine.jpg (122.22 KiB) Viewed 235 times



At least its colors match with the low-resolution map from Wii. I've tried your previous script for untile 360 DXT(after some necessary modifications), but the converted texture still looked the same. Really have no idea what to do next.
## Post #72
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-05-25T14:18:16+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

@AceWell

I guess either you're too busy or you havn't seen my post?     But I'm getting closer...

I extracted some textures from a Ben 10 iOS game some time ago, and got some large maps which I guess were taken directly from the Omniverse X360 game. 

Since the textures in the archives looks like DDS, I converted one of them to the target format and compared it with the same texture part of the model archive. I tried different dds formats untill I found them highly consistent, except that I noticed the data were swapped. So I used Noesis to swap the array again and end up with this:



textures.jpg (222.05 KiB) Viewed 220 times



The results of the normal maps were even worse.

I guess it's the best I can do. I really really need your help right now...   

Here're all the textures of the playable characters which I dumped from the archive. Their lengths should be enough to accommodate the actual image data as I split them according to the pointer inside the archives.

[Omniverse_Texture](https://mega.nz/#!7E9R3RSY!BpPUVzn-v1IjA_-yEWbChtIPXDbbvG0og1MYGolP4HE)

Oh, one more thing, the texture format is dxt1 with only RGB color, no Alpha channel.

Thank you for your kindness in advance!
## Post #73
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-05-25T15:01:21+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

This is the script I used:

```

def registerNoesisTypes():
    handle = noesis.register("Ben 10 Omniverse (X360)", ".omni")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadRGBA(handle, noepyLoadRGB)
    #noesis.logPopup()
    return 1

#check if it's this type based on the data
def noepyCheckType(data):
    bs = NoeBitStream(data)
    Magic = bs.readBytes(8)
    if Magic != b'\x00\x00\x00\x01\x00\x00\x00\x24':
        return 0
    return 1
	
def noepyLoadRGB(data, texList):
    datasize = len(data) - 0x70        
    bs = NoeBitStream(data, NOE_BIGENDIAN)
    bs.seek(0x3E, NOESEEK_ABS)
    imgWidth = bs.readUShort()            
    imgHeight = bs.readUShort()           
    bs.seek(0x70, NOESEEK_ABS)
    data = bs.readBytes(datasize)      
    data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 8)
    texFmt = noesis.NOESISTEX_DXT1
    texList.append(NoeTexture(rapi.getInputName(), imgWidth, imgHeight, data, texFmt))
    return 1
```


The four bytes after the 0x BB BB BB BB in the file is the original end offset of the texture data, which originally ended 
with 0x BE BE BE BE. Since there's an id string 0x 00 00 00 01 00 00 00 24 in front of every name string, I assumed it 
as the start of every file. This explanation should help avoid some confusions.
## Post #74
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-05-25T18:23:58+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost
>
> @AceWell
I guess either you're too busy or you havn't seen my post?     But I'm getting closer...
i don't know what you were asking for there   


> Reply from Bigchillghost
>
> Omniverse_Texture
it looks like you got this under control but here is a Noesis python script to open those samples   


 tex_Ben10Omniverse_omni.zip
(692 Bytes) Downloaded 51 times


always specify full game name and platform from which the sample are taken. 
you have samples coming from all over the place and from various games so it is a little confusing.
## Post #75
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-05-26T05:56:30+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> 
i don't know what you were asking for there

I didn't ask for anything at the post on the split files according to the offset table, but to see if my finding is correct or not from your experience, so that I can dig deeper. But obviously this finding is worthless, the offset table might just be used by the game to decompress data faster. 

In the other post I compared the two textures from XBox 360 and Wii, to show I was close to locate the texture data block, and the result looks like those from Cartoon Network Punch Time Explosion on XBox 360, which you've handled queerly. So I was hopping you can take a closer look at those samples, which are at the eighth post previous to that one, but still at this page. Well, it's indeed miles away especially since I've written that 'long story'. I should have attached the link there, my bad... I thought you would remember...  


> Reply from AceWell
>
> 
it looks like you got this under control but here is a Noesis python script to open those samples   
tex_Ben10Omniverse_omni.zip

Wow, the size of the header is 0x6d? I’d also tried with 0x6c before but nothing change, can’t believe it.   But thanks, it works fine! 
Now just need to find a way to split the textures from all the archives of this game. 

So in Noesis there’s no difference between RGB and ARGB pixel formats of DDS according to your script, right?   


> Reply from AceWell
>
> 
always specify full game name and platform from which the sample are taken. 
you have samples coming from all over the place and from various games so it is a little confusing.

I've never uploaded samples from this game of other platforms, but just use those smaller or same-resolution textures I grabbed from other games for a comparison on the sight. Sometimes I do compare the Wii data with those dumped by Dolphin, the Wii emulator, hoping to get a easy start. But I've never published the result, because it was totally futile efforts. I can't even extract one mesh from one of the Wii version of those game this thread has mentioned previously. I will always specify if the samples come from other platform or games, either in the text between the link, or the line before it (the link). 
As for the full name, since this whole thread is about Ben 10, I guess there's no need to write down Ben 10 Omniverse AGAIN rather than using Omniverse which we all can know what it refers to.

But just as you said, since I work with archives of the same game from all over the platforms (those "other game" are Unity games), it may indeed cause confusion. Actually sometime I just skip those details to avoid repeated statements. Anyway I will adopt your advice so there won't be any confusion next time.
## Post #76
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-05-27T15:40:22+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from AceWell
>
> 
it looks like you got this under control but here is a Noesis python script to open those samples   
tex_Ben10Omniverse_omni.zip

Seems this script works perfectly only with those samples. When I split other textures from different archives, their names and the solutions of the script are actually contrary. For example, some textures named with _d are dxt5 format instead, while some named with _n are dxt1. Also, there're a lot of other textures that have no _d or _n postfix. So I guess there must be a field inside the header of those files for identifing which format each texture uses. And I've worked it out: if the four bytes at 0x4C equals 0x 00 00 00 00, then it uses dxt1 format, if it's larger than 0 (currently known values include 0x1, 0x2 and 0x5), than it is dxt5 format. Good news is that this method works for 99% textures from Ben 10 Omniverse, Ben 10 Omniverse 2, and Ben 10 Galactic Racing for XBox360, which have the same archive format. Maybe there're more dxt formats represented by the values greater than 0. But those exceptions that method doesn't support are all environment, vfx or scene maps, which are not so important.

Here is the improved script changing the extension to .v2t: 

```

from inc_noesis import *

def registerNoesisTypes():
    handle = noesis.register("Vicious Engine 2 Ben 10 Series Games Textures", ".v2t")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadRGBA(handle, noepyLoadRGBA)
    return 1

def noepyCheckType(data):
    bs = NoeBitStream(data)
    Magic = bs.readBytes(4)
    if Magic != b'\x00\x00\x00\x01':
        return 0
    return 1

#check if it's this type based on the data
	
def noepyLoadRGBA(data, texList):
    datasize = len(data) - 0x6D        
    bs = NoeBitStream(data, NOE_BIGENDIAN)
    bs.seek(0x3E, NOESEEK_ABS)
    imgWidth = bs.readUShort()            
    imgHeight = bs.readUShort()
    bs.seek(0x4C, NOESEEK_ABS)
    DxtValue = bs.readUInt()
    bs.seek(0x6D, NOESEEK_ABS)
    data = bs.readBytes(datasize)
    if DxtValue == 0:
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 8)
        texFmt = noesis.NOESISTEX_DXT1
    elif DxtValue > 0:
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)
        texFmt = noesis.NOESISTEX_DXT5
    texList.append(NoeTexture(rapi.getInputName(), imgWidth, imgHeight, data, texFmt))
    return 1
```
## Post #77
- Username: Ar7579009
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Apr 28, 2019 10:28 pm
- Post datetime: 2019-05-05T11:31:00+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

HELLO BIGCHILLGHOST I AM SEARCHING FOR TONY STARK FACE FROM IRON MAN 2 GAME DO YOU HAVE SAVE FILE BECAUSE YOU POSTED A SCREENSHOT 2 YEARS AGO IF YOU HAVE PLEASE SEND ME OTHERWISE POST IT ON XENTAX FORUM
AND YES I LOVE BEN 10 3000
## Post #78
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-03-10T01:50:24+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

can you plz make a freestyle video tutorial so i can follow the process i cant do it without it i dont want to wast your time by asking to rip all models for me just make a video about ripping one model texture & mesh
## Post #79
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-03-10T01:54:56+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost ↑Thu Dec 15, 2016 7:06 am at Thu Dec 15, 2016 7:06 am
>
> 
daemon1 wrote:Bigchillghost wrote:So is it hard to extract bones data? If it's not a practical idea I may just get the meshes with hex2obj.
Anyway thanks for your hints!

Getting bones will require some programming even in simplest case.

Well, then. Obviously I don't have such skill as programing to extract that, so it's OK for me to just extract the meshes.

can you plz make a freestyle video tutorial so i can follow the process i cant do it without it i dont want to wast your time by asking to rip all models for me just make a video about ripping one model texture & mesh
## Post #80
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-03-13T02:54:35+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from shakotay2 ↑Fri Dec 23, 2016 8:03 pm at Fri Dec 23, 2016 8:03 pm
>
> 
Bigchillghost wrote:Also another successful test of g_wh.ps3:   
yeah, see, there was a problem with the H2O-Maker. Also fixed the last submesh (quick fix only, may fail).
(A +/- 1 correction of the vertex count might be required because sometimes the value in the ps3 file
is different from the calculated one.)

(exe file only. Dlls from the post of 20th Dec, 3:19 pm, required)

g_uec.ps3 is not still working
[posting.php?mode=smilies&f=16](https://forum.xentax.com/posting.php?mode=smilies&f=16)#
## Post #81
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-03-15T01:54:45+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Acewell ↑Tue Dec 27, 2016 9:25 am at Tue Dec 27, 2016 9:25 am
>
> 
Bigchillghost wrote:I'm working on the last Vicious Engine game of Ben 10, Ben 10 Alien Force: Vilgax Attacks.
global
l_bell
here is a zip with a bms script to split the textures from the xbx files 
and a Noesis python script to open the resulting textures for that game 
scripts.zip


edit
i just realized Noesis won't use a particular script selected in the dropdown
list, alphabetical order seems to be the  priority factor for some reason.   
i guess you will have to move out the Ben 10 scripts from the python folder
you are not using at the time so there won't be a conflict.

can you make (make h2o ben 10 alien force vilgax attacks) plz?
## Post #82
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-15T03:04:28+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from adragonballs ↑Sun Mar 15, 2020 9:54 am at Sun Mar 15, 2020 9:54 am
>
> 
can you make (make h2o ben 10 alien force vilgax attacks) plz?

First, nice necro. Second, you gotta provide samples.
## Post #83
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-03-18T01:04:50+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from shakotay2 ↑Fri Dec 23, 2016 8:03 pm at Fri Dec 23, 2016 8:03 pm
>
> 
Bigchillghost wrote:Also another successful test of g_wh.ps3:   
yeah, see, there was a problem with the H2O-Maker. Also fixed the last submesh (quick fix only, may fail).
(A +/- 1 correction of the vertex count might be required because sometimes the value in the ps3 file
is different from the calculated one.)

(exe file only. Dlls from the post of 20th Dec, 3:19 pm, required)

i admaier your work i tried useing your MakeH2O-bins-Ben10UA 
it work like cahrm i love, it has some issus that i really want you to look at i hope you wont get made

g_uec.ps3 is not making any model
first l_romd_d.ps3 boss cant get extracted properly
file starts with i_xxx_d.ps3 has more then 100 plz remove the limet 
ill give you samples if you please consider updating  MakeH2OBen10UA and plz make MakeH2OBen10AF vilgax attacks xbox.

please response as soon as possible

sir i want those models i love ben 10 but i cant have them with out you, to do what you best at could take me years but some one like you who has that much experience can consider helping a fan would be a dream come true. i cant do it but you can help me plz or at least let me know what you think.
## Post #84
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-18T07:53:03+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from adragonballs ↑Wed Mar 18, 2020 9:04 am at Wed Mar 18, 2020 9:04 am
>
> g_uec.ps3 is not making any modelIf I had the sample I could take a look at.
## Post #85
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-18T10:01:51+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from shakotay2 ↑Wed Mar 18, 2020 3:53 pm at Wed Mar 18, 2020 3:53 pm
>
> 
adragonballs wrote: ↑Wed Mar 18, 2020 9:04 amg_uec.ps3 is not making any modelIf I had the sample I could take a look at.

Since I'm also interested, I'll provide the samples [B10 UA samples](https://www.mediafire.com/file/g9ovx5h8aawc0ij/B10_UA_samples_global.7z/file) [B10 UA Bosses](https://www.mediafire.com/file/wt6jplbgk17i3ro/B10_UA_Boss.7z/file)
## Post #86
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-18T11:14:39+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

Thanx!
Some corrections are required. I'll look at that soon:
.



g_uec_p3.png (162.5 KiB) Viewed 149 times


(the created H2O files provide point clouds at least, need some corrections for getting the full mesh)
## Post #87
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-18T21:02:31+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from adragonballs ↑Wed Mar 18, 2020 9:04 am at Wed Mar 18, 2020 9:04 am
>
> g_uec.ps3 is not making any modelRead the How_to_use txt file.
(H2O files are being created which can be read by hex2obj's multimesh feature to create several obj files.)

> first l_romd_d.ps3 boss cant get extracted properlyDon't have that sample.

> file starts with i_xxx_d.ps3 has more then 100 plz remove the limetdone.
.


 MakeH2O-bins-Ben10UA_fix1.zip
(120.06 KiB) Downloaded 21 times


Made a fix for wrong detected FVFsize 20 (hopefully won't produce new bugs...  )

```
Usually you can rename them to .obj and load normally.

Some meshes will look spoiled. (Maybe still true after the fix because there's 2037 meshes in [i]l_romd_d.ps3[/i] to be checked...)
For the "above 500 vertices" meshes there's 226 ok; another 116 are named .objx (for save), only 4 of them are spoiled, afaics, so 112 usable as obj, great :D (didn't check the countless "below 500 vertices" meshes)

Some H2O files will result in [b]obj[/b] files containing[b] QNAN[/b]s ("not a number")
(-1.#QNAN0 for example)

To perform a multiple obj import into blender (use load_multi_obj_blender2.69.py)
you'll need to sort out all obj files containing "QNAN"s before.

(Use a tool capable of "search cross files".)
```
## Post #88
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-18T22:49:44+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from shakotay2 ↑Thu Mar 19, 2020 5:02 am at Thu Mar 19, 2020 5:02 am
>
> 
first l_romd_d.ps3 boss cant get extracted properlyDon't have that sample.
I shared it too, it's in the B10 UA bosses link, anyways thanks for your work.
## Post #89
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-03-19T01:24:33+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from shakotay2 ↑Thu Mar 19, 2020 5:02 am at Thu Mar 19, 2020 5:02 am
>
> 
adragonballs wrote: ↑Wed Mar 18, 2020 9:04 amg_uec.ps3 is not making any modelRead the How_to_use txt file.
(H2O files are being created which can be read by hex2obj's multimesh feature to create several obj files.)
first l_romd_d.ps3 boss cant get extracted properlyDon't have that sample.
file starts with i_xxx_d.ps3 has more then 100 plz remove the limet done.
.
MakeH2O-bins-Ben10UA.zip

i literally have no words to thank you, you can say i'm speechless and stunned but still thanks for being so humble YOU ARE JUST AMAZING thank you thank you...
## Post #90
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-03-19T01:27:03+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from shakotay2 ↑Wed Mar 18, 2020 7:14 pm at Wed Mar 18, 2020 7:14 pm
>
> 
Thanx!
Some corrections are required. I'll look at that soon:
.
g_uec_p3.png
(the created H2O files provide point clouds at least, need some corrections for getting the full mesh)

no bro no its all thanx to you
## Post #91
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-03-19T01:37:31+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from JosouKitsune ↑Sun Mar 15, 2020 11:04 am at Sun Mar 15, 2020 11:04 am
>
> 
adragonballs wrote: ↑Sun Mar 15, 2020 9:54 am
can you make (make h2o ben 10 alien force vilgax attacks) plz?


First, nice necro. Second, you gotta provide samples.

sorry i couldn't provide the samples, reason: i dont have the game yet i will provide samples as soon i get my hands on the game
by the way thanx for shearing interest.
## Post #92
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-03-21T01:29:10+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from JosouKitsune ↑Sun Mar 15, 2020 11:04 am at Sun Mar 15, 2020 11:04 am
>
> 
adragonballs wrote: ↑Sun Mar 15, 2020 9:54 am
can you make (make h2o ben 10 alien force vilgax attacks) plz?


First, nice necro. Second, you gotta provide samples.
[https://mega.nz/#!DzJilAII!j0PM_g9RT3U_ ... c-VA8iI14w](https://mega.nz/#!DzJilAII!j0PM_g9RT3U_W_wGbaxZLggSSr7MgOjtGc-VA8iI14w)

its a link to some sample of ben 10 alien force vilgax attacks xbox 360 game global
## Post #93
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-03-21T01:38:40+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

here is a link to ben 10 vilgax attacks game's global samples. they are from xbox 360's game 

[https://mega.nz/#!DzJilAII!j0PM_g9RT3U_ ... c-VA8iI14w](https://mega.nz/#!DzJilAII!j0PM_g9RT3U_W_wGbaxZLggSSr7MgOjtGc-VA8iI14w)

can someone make "make h2o ben 10 alien force vilgax attacks"??
## Post #94
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-03-25T16:13:34+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from adragonballs ↑Sat Mar 21, 2020 9:38 am at Sat Mar 21, 2020 9:38 am
>
> 
here is a link to ben 10 vilgax attacks game's global samples. they are from xbox 360's game 

https://mega.nz/#!DzJilAII!j0PM_g9RT3U_ ... c-VA8iI14w

can someone make "make h2o ben 10 alien force vilgax attacks"??

If I'm not mistaken, the models for this game are not in the global folder, I believe they are in the folders that start with "l_".
## Post #95
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-03-29T01:03:23+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

[https://mega.nz/#F!KjpCgI6D!Bt6-lVyziI98DqvJV8YGPQ](https://mega.nz/#F!KjpCgI6D!Bt6-lVyziI98DqvJV8YGPQ)


here are the samples of ben 10 vilgax attacks they are from xbox 360's game


can someone make "make h2o ben 10 alien force vilgax attacks"??
## Post #96
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-03-29T01:20:32+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

this guy is missing in l_romd_d.ps3 maxresdefault (1).jpg (100.58 KiB) Viewed 329 times


> Reply from shakotay2 ↑Thu Mar 19, 2020 5:02 am at Thu Mar 19, 2020 5:02 am
>
> 
adragonballs wrote: ↑Wed Mar 18, 2020 9:04 amg_uec.ps3 is not making any modelRead the How_to_use txt file.
(H2O files are being created which can be read by hex2obj's multimesh feature to create several obj files.)
first l_romd_d.ps3 boss cant get extracted properlyDon't have that sample.
file starts with i_xxx_d.ps3 has more then 100 plz remove the limet done.
.
MakeH2O-bins-Ben10UA.zip
Code: Select allTool creates H2O files - some of them will "produce" .objx files when using them with [i]hex2obj[/i]'s multi mesh feature.
Usually you can rename them to .obj and load normally.

Some meshes will look spoiled.

Some H2O files will result in obj files containing[b] QNAN[/b]s ("not a number")
(-1.#QNAN0 for example)

To perform a multiple obj import into blender (use load_multi_obj_blender2.69.py)
you'll need to sort out all obj files containing "QNAN"s before.

(Use a tool capable of "search cross files".)
## Post #97
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-03-29T01:21:26+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from adragonballs ↑Sun Mar 29, 2020 9:20 am at Sun Mar 29, 2020 9:20 am
>
> 
maxresdefault (1).jpgshakotay2 wrote: ↑Thu Mar 19, 2020 5:02 am
adragonballs wrote: ↑Wed Mar 18, 2020 9:04 amg_uec.ps3 is not making any modelRead the How_to_use txt file.
(H2O files are being created which can be read by hex2obj's multimesh feature to create several obj files.)
first l_romd_d.ps3 boss cant get extracted properlyDon't have that sample.
file starts with i_xxx_d.ps3 has more then 100 plz remove the limet done.
.
MakeH2O-bins-Ben10UA.zip
Code: Select allTool creates H2O files - some of them will "produce" .objx files when using them with [i]hex2obj[/i]'s multi mesh feature.
Usually you can rename them to .obj and load normally.

Some meshes will look spoiled.

Some H2O files will result in obj files containing[b] QNAN[/b]s ("not a number")
(-1.#QNAN0 for example)

To perform a multiple obj import into blender (use load_multi_obj_blender2.69.py)
you'll need to sort out all obj files containing "QNAN"s before.

(Use a tool capable of "search cross files".)
[https://mega.nz/#!Pip3CLxb!nxMMN-8F3F85 ... QHsujMIl88](https://mega.nz/#!Pip3CLxb!nxMMN-8F3F85EPWqkqry3fdm4BYWWlU03QHsujMIl88)

link to l_romd_d.ps3
## Post #98
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-03-29T05:17:19+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from adragonballs ↑Sun Mar 29, 2020 9:03 am at Sun Mar 29, 2020 9:03 am
>
> 
https://mega.nz/#F!KjpCgI6D!Bt6-lVyziI98DqvJV8YGPQ


here are the samples of ben 10 vilgax attacks they are from xbox 360's game


can someone make "make h2o ben 10 alien force vilgax attacks"??

There are other models in the same file.



l_bell_d.xbx.png (48.06 KiB) Viewed 323 times
## Post #99
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-03-29T05:26:17+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

If that helps, it seems that to find the other models, just search for "00 02 01 1B". In this block, you can also see the vertex count and the face count.



image.png (28.68 KiB) Viewed 320 times
## Post #100
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-29T06:57:46+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from adragonballs ↑Sun Mar 29, 2020 9:20 am at Sun Mar 29, 2020 9:20 am
>
> this guy is missing in l_romd_d.ps3There's about 2035 *.obj files created from l_romd_d.ps3. Did you import/check them all?

> Reply from reh ↑Sun Mar 29, 2020 1:26 pm at Sun Mar 29, 2020 1:26 pm
>
> 
If that helps, it seems that to find the other models, just search for "00 02 01 1B". In this block, you can also see the vertex count and the face count.
Here's a Noesis script for the first submesh. You may expand it with a loop to get all submeshes:
.

```
import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("GetBen10-UA-CDM",".xbx")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1
	
NOEPY_HEADER = "vap"

def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 3:
      return 0
   if bs.readBytes(3).decode("ASCII") != NOEPY_HEADER:
      print("'vaps' not found!")
      return 0
   return 1  

def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)
	bs.setEndian(NOE_BIGENDIAN)
	rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)
	addr=bs.tell()
	fileBuff = bs.data[addr:bs.dataSize]
	addr1= fileBuff.find(b'\x00\x02\x01\x1B')
	addr += addr1
	bs.seek(addr)
	bs.seek(4, NOESEEK_REL)# skip signature

	# counts
	vCnt = bs.readUInt()
	du = bs.readUInt()#dummy
	fCnt = bs.readUInt()
	bs.seek(22*16+4, NOESEEK_REL)# this offset maybe different for other model files
	print("vCnt, fCnt", vCnt,fCnt)
	FVFsize = int(44)
	offset= bs.tell()
	VBSize = vCnt * FVFsize
	print("verts at:", hex(offset), VBSize)
	VBuff = bs.readBytes(VBSize)
	rapi.rpgBindPositionBufferOfs(VBuff, noesis.RPGEODATA_FLOAT, FVFsize, 0)
	rapi.rpgBindUV1BufferOfs(VBuff, noesis.RPGEODATA_FLOAT, FVFsize, 36)
	bs.seek(16, NOESEEK_REL)
	offset= bs.tell()
	print("FIs at:", hex(offset))
	FBuff = bs.readBytes(fCnt*2)
	rapi.rpgCommitTriangles(FBuff, noesis.RPGEODATA_USHORT, fCnt, noesis.RPGEO_TRIANGLE, 1)

	mdl = rapi.rpgConstructModel()
	mdlList.append(mdl)
	
	rapi.rpgClearBufferBinds()
	return 1
```

btw: most important line for the bigendian thingie: 	rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)
Obviously using bs.setEndian(NOE_BIGENDIAN) is not sufficient - 
rapi.rpgCommitTriangles() must be "told" how to interpret the FBuff data by adding this line:
rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)

(This seems a little bit confusing to me since the script even works in case you place
rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1) AFTER
rapi.rpgBindPositionBufferOfs(VBuff, noesis.RPGEODATA_FLOAT, FVFsize, 0).

So rapi.rpgBindPositionBufferOfs()  "relies" on bs.setEndian(NOE_BIGENDIAN)!?)
.



l_bell_d-xbx.png (55.57 KiB) Viewed 308 times
## Post #101
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-30T10:27:10+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

I was asked to create that (above mentioned) loop, well, I really was in the hope, that you could do it for yourself.

As from me you only get it quick 'n dirty, as you may know  (so don't blame me).
I've limited it to 5 (out of 21) models from l_bell_d.xbx, because some come out ugly (require noesis.RPGEO_TRIANGLE_STRIP, and whatever other change):
.



l_bell_d-xbx_5_models.png (181.63 KiB) Viewed 230 times



```
import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("GetBen10-UA-CDM",".xbx")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1
	
NOEPY_HEADER = "vap"

def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 3:
      return 0
   if bs.readBytes(3).decode("ASCII") != NOEPY_HEADER:
      print("'vaps' not found!")
      return 0
   return 1  

def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)
	bs.setEndian(NOE_BIGENDIAN)
	#rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)

	addr=bs.tell(); addr1=0; cnt= 0
	#while addr != addr1 :
	while cnt < 5 :
		fileBuff = bs.data[addr:bs.dataSize]#todo: Size has to be reduced with each run
		addr1= fileBuff.find(b'\x00\x02\x01\x1B')
		addr += addr1
		bs.seek(addr)
		#offset= bs.tell()
		#print("sig at:", hex(offset))
		bs.seek(4, NOESEEK_REL)# skip signature

		# counts
		vCnt = bs.readUInt()
		du = bs.readUInt()#dummy
		fCnt = bs.readUInt()
		bs.seek(22*16+4, NOESEEK_REL)# this offset may be different for other model files
		print("vCnt, fCnt", vCnt,fCnt)
		# 
		FVFsize = int(44)
		offset= bs.tell()
		VBSize = vCnt * FVFsize
		print("verts at:", hex(offset), VBSize)
		VBuff = bs.readBytes(VBSize)
		#print(VBuff)
		rapi.rpgBindPositionBufferOfs(VBuff, noesis.RPGEODATA_FLOAT, FVFsize, 0)
		rapi.rpgBindUV1BufferOfs(VBuff, noesis.RPGEODATA_FLOAT, FVFsize, 36)
		bs.seek(16, NOESEEK_REL)
		offset= bs.tell()
		print("FIs at:", hex(offset))
		#return 1
		FBuff = bs.readBytes(fCnt*2)
		#print(FBuff)
		rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)
		rapi.rpgCommitTriangles(FBuff, noesis.RPGEODATA_USHORT, fCnt, noesis.RPGEO_TRIANGLE, 1)
		material = NoeMaterial("mat%03i"%cnt, "")
		rapi.rpgSetMaterial(material.name)
		addr += 1; cnt += 1

	mdl = rapi.rpgConstructModel()
	mdlList.append(mdl)
	
	#rapi.rpgClearBufferBinds()
	return 1

```

.
## Post #102
- Username: aquaamann333
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 15, 2020 12:57 pm
- Post datetime: 2020-05-15T05:06:54+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

I was wondering if any of you were able to extract all the cosmic destruction models. If so, could someone send me Amphibian, Water Hazard, Armodrillo, Rath, and Four Arms because I am unable to extract them myself.
## Post #103
- Username: CameronCarson
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Jan 25, 2020 8:53 am
- Post datetime: 2020-06-08T00:44:09+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost ↑Fri Dec 23, 2016 4:03 pm at Fri Dec 23, 2016 4:03 pm
>
> 
AceWell wrote:this post explains what i was talking about for patterns
http://forum.xentax.com/viewtopic.php?p=120284#p120284

find the pattern, i find it easier to see on the text side
set the text column width to reveal a vertical pattern to see where it starts
follow that pattern to where it starts and you have your offset to test for
set the FVFsize in Hex2obj to the number of bytes you expanded the text column
test for point cloud to see if it is vertex data
play with endianess and float/short/halffloat until the point cloud makes sense

then you can look for face indices which look like a scrambled alphabet on the text side
then go to the hex side and put your cursor where you think that pattern starts and check
that offset in Hex2obj, worry about the precise step1 count last.

i just use HxD and windows calculator in scientific mode, nothing special  

Awsome! With the images I easily understood your method however there always could be some problems for me like this:



Neither the addr of the symbol > (0xdf3e8) nor the one ot the ? (0xdf3e4) is the vertices startaddr, so I tried the one of the = (0xdf3e0) conbined with other possible FI startaddrs. I also found the addrs where FI count & vertices count are stored, the sequence no more starts as B4 01 though. And then I got this from g_ra.xbx:
Rath.jpg
The first mesh I extracted aha. Of course it wasn't done at a go, and therefore I need to practice more to really get the hang of it.

Cheers!

Hello!
I read all the pages of this discussion and managed to do the process in the * .ps3 models but the * .xbx do not open in hex2obj.
And as for the textures of the * .xbx format when I extract them they are damaged and in some models they are missing.
(Some in * .ps3 format are also missing)
Could someone help me, I need these models for an animation video important to me.
[g_ra_xbx_512out.png](https://xentaxbackup.github.io/file/18284_g_ra_xbx_512out.png)
## Post #104
- Username: CameronCarson
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Jan 25, 2020 8:53 am
- Post datetime: 2020-06-08T02:43:33+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

I extracted some basic models.

*Big Chill - mesh+textures
*Ultimate Big Chill - mesh+texture (Wing texture is missing)
*Echo Echo - mesh
*Ultimate Echo Echo - mesh+texture
*Hummongousaur - mesh+texture
*Ultimate Hummongousaur - mesh+textures
*Swampfire - mesh+textures
*Ultimate Swampfire - mesh+textures (I think there is still a texture missing)
*Spidermonkey - mesh+texture
*Ultimate Spidermonkey - mesh+textures
*Armadrillo - mesh+textures
*NRG - mesh+textures
*Terraspin - mesh+textures
*WaterHazard - mesh+texture
*Four Arms - mesh+texture

*Ben Tennyson - mesh
*Way Big - mesh
*Enoch - mesh
*Kooper - mesh
*Six Six - mesh
*Sunder - mesh
*Zombozo - mesh
*Way Big (Albedo) - mesh

*Ampfibian - texture

*Rath - I can't extract either the mesh or the texture
## Post #105
- Username: aquaamann333
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 15, 2020 12:57 pm
- Post datetime: 2020-06-20T22:20:37+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Mod

> Reply from Bigchillghost ↑Sun Dec 25, 2016 3:29 pm at Sun Dec 25, 2016 3:29 pm
>
> 
AceWell wrote:looks like an additional layer of tiling on top of the 360 untile, i don't know, can't make anything of it
its a different game from a different year so things probably change in development.  

I dumped some textures from the Wii version with Dolphin and found they had the same content but only in different height
and width.
comparision.jpg

I placed them into one image for a comparision. However the Wii version maps' resolutions (128x128) are too low for the XBox meshes.
I hope there're other ways to get them.

Could you put these textures up for download?
## Post #106
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-07-02T15:56:42+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Chromastone.zip
(146.54 KiB) Downloaded 67 times
## Post #107
- Username: aquaamann333
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 15, 2020 12:57 pm
- Post datetime: 2020-07-03T03:12:42+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

a
## Post #108
- Username: simp333
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 03, 2020 11:16 am
- Post datetime: 2020-07-03T03:22:23+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Could someone put up a download for the Alien X and Jetray models from Vilgax Attacks?
## Post #109
- Username: aquaamann333
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 15, 2020 12:57 pm
- Post datetime: 2020-07-04T05:46:32+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from reh ↑Thu Jul 02, 2020 11:56 pm at Thu Jul 02, 2020 11:56 pm
>
> 
Chromastone.zip

Hey thanks man. May you provide a png file for the model's texture because the obj won't open with the mtl
## Post #110
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-07-05T04:40:32+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from aquaamann333 ↑Sat Jul 04, 2020 1:46 pm at Sat Jul 04, 2020 1:46 pm
>
> 
Hey thanks man. May you provide a png file for the model's texture because the obj won't open with the mtl
I don't have the texture of this model, send it because it was in one of the sample files that provided in that topic
## Post #111
- Username: simp333
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 03, 2020 11:16 am
- Post datetime: 2020-07-07T05:30:41+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

If anyone has any of the Vilgax Attacks models can you contact me or put them up for download here because I can't seem to extract them
## Post #112
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-07-08T03:40:15+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from reh ↑Thu Jul 02, 2020 11:56 pm at Thu Jul 02, 2020 11:56 pm
>
> 
Chromastone.zip

plz make a tool for ben 10 VA
## Post #113
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-07-27T16:23:23+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from reh ↑Sun Jul 05, 2020 12:40 pm at Sun Jul 05, 2020 12:40 pm
>
> 
aquaamann333 wrote: ↑Sat Jul 04, 2020 1:46 pm
Hey thanks man. May you provide a png file for the model's texture because the obj won't open with the mtl

I don't have the texture of this model, send it because it was in one of the sample files that provided in that topic

where are the others
## Post #114
- Username: Mostafa360
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 05, 2020 8:26 pm
- Post datetime: 2020-08-05T12:51:47+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Any one have | Terraspin |
## Post #115
- Username: simp333
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 03, 2020 11:16 am
- Post datetime: 2020-08-15T04:38:03+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Has anyone extracted Eye Guy, Gravattack, or WIldvine from the omniverse game? If so can you put up the download link
## Post #116
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-08-20T04:44:48+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from Acewell ↑Tue Dec 27, 2016 9:25 am at Tue Dec 27, 2016 9:25 am
>
> 
Bigchillghost wrote:I'm working on the last Vicious Engine game of Ben 10, Ben 10 Alien Force: Vilgax Attacks.
global
l_bell
here is a zip with a bms script to split the textures from the xbx files 
and a Noesis python script to open the resulting textures for that game 
scripts.zip


edit
i just realized Noesis won't use a particular script selected in the dropdown
list, alphabetical order seems to be the  priority factor for some reason.   
i guess you will have to move out the Ben 10 scripts from the python folder
you are not using at the time so there won't be a conflict.

how did you rip mesh from Ben 10 Alien Force: Vilgax Attacks is it a tool or script link plz
## Post #117
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-20T06:12:13+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from adragonballs ↑Thu Aug 20, 2020 12:44 pm at Thu Aug 20, 2020 12:44 pm
>
> 
how did you rip mesh from Ben 10 Alien Force: Vilgax Attacks is it a tool or script link plz
Stop spamming the thread if you can't contribute anything!
## Post #118
- Username: simp333
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 03, 2020 11:16 am
- Post datetime: 2020-09-01T05:09:45+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from Bigchillghost ↑Thu Aug 20, 2020 2:12 pm at Thu Aug 20, 2020 2:12 pm
>
> 
adragonballs wrote: ↑Thu Aug 20, 2020 12:44 pm
how did you rip mesh from Ben 10 Alien Force: Vilgax Attacks is it a tool or script link plz

Stop spamming the thread if you can't contribute anything!

Hey I was just wondering if you could put up a link to a google drive or something to all the Ben 10 models you've extracted to help those of us who can't extract the models out
## Post #119
- Username: Larsqn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 05, 2020 10:09 am
- Post datetime: 2020-09-05T02:37:40+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Has anyone extrated ULTIMATE SPIDERMONKEY, ULTIMATE SWAMPFIRE, ULTIMATE BIGCHILL and ULTIMATE ECHO ECHO From Cosmic Destruction? Has anyone extracted Jetray, Goop, Brainstorm, Spidermonkey and Bigchill from Vilgax Attacks?
## Post #120
- Username: Mostafa360
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 05, 2020 8:26 pm
- Post datetime: 2020-09-08T14:58:30+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Any one have ultimate spider monkey and ultimate swamp fire
## Post #121
- Username: aquaamann333
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-09-09T15:57:29+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Any further spam will result in bans being handed out.
## Post #122
- Username: aquaamann333
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-09-09T20:54:16+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Bans handed out and posts removed.
## Post #123
- Username: Paniques
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 03, 2019 4:41 am
- Post datetime: 2020-09-10T13:36:16+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Hey, I'm a little bit late to the party, but I am at my wit's end trying to figure out how to decompress the files of Ben 10 Omniverse 1/2, and find where the character data is stored. I'd share samples, but I legitimately have no clue which file to share. Any assistance would be greatly appreciated.
## Post #124
- Username: Vasu10
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 23, 2020 6:27 pm
- Post datetime: 2020-09-23T10:30:52+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from Larsqn ↑Sat Sep 05, 2020 10:37 am at Sat Sep 05, 2020 10:37 am
>
> 
Has anyone extrated ULTIMATE SPIDERMONKEY, ULTIMATE SWAMPFIRE, ULTIMATE BIGCHILL and ULTIMATE ECHO ECHO From Cosmic Destruction? Has anyone extracted Jetray, Goop, Brainstorm, Spidermonkey and Bigchill from Vilgax Attacks?

I have ultimate swampfire and echo echo of cosmic destruction and Brainstorm, spider monkey of vilgax attack
## Post #125
- Username: adragonballs
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Mar 10, 2020 9:29 am
- Post datetime: 2020-10-05T11:13:54+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from Vasu10 ↑Wed Sep 23, 2020 6:30 pm at Wed Sep 23, 2020 6:30 pm
>
> 
Larsqn wrote: ↑Sat Sep 05, 2020 10:37 am
Has anyone extrated ULTIMATE SPIDERMONKEY, ULTIMATE SWAMPFIRE, ULTIMATE BIGCHILL and ULTIMATE ECHO ECHO From Cosmic Destruction? Has anyone extracted Jetray, Goop, Brainstorm, Spidermonkey and Bigchill from Vilgax Attacks?


I have ultimate swampfire and echo echo of cosmic destruction and Brainstorm, spider monkey of vilgax attack

can I have Brainstorm plz
## Post #126
- Username: Mostafa360
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 05, 2020 8:26 pm
- Post datetime: 2020-10-06T15:28:57+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Guys anyone know how to extract ben 10 vilgax Attacks 3d models
## Post #127
- Username: Mostafa360
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 05, 2020 8:26 pm
- Post datetime: 2020-10-06T15:34:11+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from reh ↑Thu Jul 02, 2020 11:56 pm at Thu Jul 02, 2020 11:56 pm
>
> 
Chromastone.zip

Do you have goop and jetray
## Post #128
- Username: TacticalNerd1963
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 13, 2020 11:04 am
- Post datetime: 2020-10-20T05:31:03+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

It might help to clarify to people like me coming to this thread for a shot at getting free ben 10 models for their own purposes-

this purpose of this thread is to ask for assistance with actually extracting models from the games being discussed (the kind of complex get-it-yourself way), NOT to ask others to give out models that they've successfully extracted without elaborating on their process of getting them (the easy get-it-from-the-person-that-did-the-hard-work way) 
Keep in mind, this thread is mainly meant to be a discussion about those processes, not the aftermath. Posts that differ from that can wind up making it harder to follow the original topic, and people who post asking for help on looking through files can get lost in a sea of posts saying stuff like "s3nd me jetr@y pl0x"
Asking for particular models seems to be the chunk of posts being considered "spam." I'm no admin, but if whatever you're about to say could fall under that criteria, please think twice about posting that, or an admin could catch on and   your post off like they seem to have already done with a few others. You can't get these models if you disregard discussion on how to actually do the legwork for them. 

kthxforthechromastonemodelbaiiii
## Post #129
- Username: beto2004rere
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 04, 2021 6:13 am
- Post datetime: 2021-01-10T22:45:56+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Hello, can please someone tell me step-by-step how to extract the models from ben 10 Ultimate Alien? Pleeasse!! I really wish to extract them but i didn't get it by far!! Thank you guys for your time and I really appreciate you guys!! I really need ben tennyson and the ultimatrix models!!
## Post #130
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2021-01-13T01:35:26+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from shakotay2 ↑Thu Apr 30, 2020 6:27 pm at Thu Apr 30, 2020 6:27 pm
>
> 
I was asked to create that (above mentioned) loop, well, I really was in the hope, that you could do it for yourself.

As from me you only get it quick 'n dirty, as you may know  (so don't blame me).
I've limited it to 5 (out of 21) models from l_bell_d.xbx, because some come out ugly (require noesis.RPGEO_TRIANGLE_STRIP, and whatever other change):
.
l_bell_d-xbx_5_models.png
Code: Select allfrom inc_noesis import *
import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("GetBen10-UA-CDM",".xbx")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1
	
NOEPY_HEADER = "vap"

def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 3:
      return 0
   if bs.readBytes(3).decode("ASCII") != NOEPY_HEADER:
      print("'vaps' not found!")
      return 0
   return 1  

def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)
	bs.setEndian(NOE_BIGENDIAN)
	#rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)

	addr=bs.tell(); addr1=0; cnt= 0
	#while addr != addr1 :
	while cnt < 5 :
		fileBuff = bs.data[addr:bs.dataSize]#todo: Size has to be reduced with each run
		addr1= fileBuff.find(b'\x00\x02\x01\x1B')
		addr += addr1
		bs.seek(addr)
		#offset= bs.tell()
		#print("sig at:", hex(offset))
		bs.seek(4, NOESEEK_REL)# skip signature

		# counts
		vCnt = bs.readUInt()
		du = bs.readUInt()#dummy
		fCnt = bs.readUInt()
		bs.seek(22*16+4, NOESEEK_REL)# this offset may be different for other model files
		print("vCnt, fCnt", vCnt,fCnt)
		# 
		FVFsize = int(44)
		offset= bs.tell()
		VBSize = vCnt * FVFsize
		print("verts at:", hex(offset), VBSize)
		VBuff = bs.readBytes(VBSize)
		#print(VBuff)
		rapi.rpgBindPositionBufferOfs(VBuff, noesis.RPGEODATA_FLOAT, FVFsize, 0)
		rapi.rpgBindUV1BufferOfs(VBuff, noesis.RPGEODATA_FLOAT, FVFsize, 36)
		bs.seek(16, NOESEEK_REL)
		offset= bs.tell()
		print("FIs at:", hex(offset))
		#return 1
		FBuff = bs.readBytes(fCnt*2)
		#print(FBuff)
		rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)
		rapi.rpgCommitTriangles(FBuff, noesis.RPGEODATA_USHORT, fCnt, noesis.RPGEO_TRIANGLE, 1)
		material = NoeMaterial("mat%03i"%cnt, "")
		rapi.rpgSetMaterial(material.name)
		addr += 1; cnt += 1

	mdl = rapi.rpgConstructModel()
	mdlList.append(mdl)
	
	#rapi.rpgClearBufferBinds()
	return 1

.
Amazing work! Hopefully someday somebody will finish the Noesis script, Looking to get some things out of the game myself
## Post #131
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-13T14:35:43+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

I wouldn't bet that someone will finish it.
It's not too hard to trick around with the script, the line in question is
while cnt < 5 :

For l_bell_d.xbx you can replace 5 by 21, but some sub meshes come out ugly then because they require noesis.RPGEO_TRIANGLE_STRIP
(So there must be a flag in the model data indicating which sort of triangles to be used, the harder part.)

From the first run with (noesis.RPGEO_TRIANGLE) you'll get 5 proper sub meshes (I hope).

You might try a "brute force" attempt/second run using strips for all 21 submeshes.
This way  you should get all submeshs (with superfluous faces, though).

Well, this was pretty simple (exported from Noesis as wavefront obj):
.



l_bell_d.jpg (119.23 KiB) Viewed 190 times


(Keep in mind that the first five objects should use "normal" triangles, not strips.)
## Post #132
- Username: FireBlaze
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 10, 2021 10:58 pm
- Post datetime: 2021-02-10T15:07:41+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

can u upload the script file again i cant download it
## Post #133
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-10T15:36:11+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from shakotay2 ↑Thu Apr 30, 2020 6:27 pm at Thu Apr 30, 2020 6:27 pm
>
>
## Post #134
- Username: GuiSauron
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 20, 2020 2:02 am
- Post datetime: 2021-02-27T06:25:17+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Hi, It's the first timing I'm writing here, thanks to the discussion I got the models from ben 10 AF, UA and CN punch explosion, I had problems with some textures but I'm gonna post about this later. Now I'm trying to get the Fastrack model from ben 10 Galactic Racing, but i'm not understanding the file, it's very different from the others, if someone can help me to rip the character and post a print from hex2obj, I'll be very thankful.  
Here are the samples of Fastrack and Cannonbolt 
[https://mega.nz/file/QnoWnA5a#36QcAzBpS ... 4j3pF-doZA](https://mega.nz/file/QnoWnA5a#36QcAzBpSeE0BbJJxBSxt2aeZy8wyhy5a4j3pF-doZA)
## Post #135
- Username: LuisarturoGamusic
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 23, 2021 6:15 am
- Post datetime: 2021-03-22T22:25:01+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

I have a idea, Why not we make a specie of Frosty Mod Manager and Frosty Editor, but with Vicious Engine, so no just can ripping Ben 10 games, otherwise others games made with Vicious Engine like Spy vs. Spy, Pac man and the ghostly adventures and others. Also, can add mods for example we can transform Ultimate Aliens in any level, or change textures or models and replace to other.

What do you think?
## Post #136
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-04-28T17:34:39+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

I'm new to XeNTaX, but how do I get the models from Ultimate Alien: Cosmic Destruction or Alien Force: Vilgax Attacks?
## Post #137
- Username: thekale
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 30, 2020 10:51 pm
- Post datetime: 2021-05-10T00:53:58+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from shakotay2 ↑Wed Jan 13, 2021 10:35 pm at Wed Jan 13, 2021 10:35 pm
>
> 
I wouldn't bet that someone will finish it.
It's not too hard to trick around with the script, the line in question is
while cnt < 5 :

For l_bell_d.xbx you can replace 5 by 21, but some sub meshes come out ugly then because they require noesis.RPGEO_TRIANGLE_STRIP
(So there must be a flag in the model data indicating which sort of triangles to be used, the harder part.)

From the first run with (noesis.RPGEO_TRIANGLE) you'll get 5 proper sub meshes (I hope).

You might try a "brute force" attempt/second run using strips for all 21 submeshes.
This way  you should get all submeshs (with superfluous faces, though).

Well, this was pretty simple (exported from Noesis as wavefront obj):
.
l_bell_d.jpg
(Keep in mind that the first five objects should use "normal" triangles, not strips.)
Thanks! 
Meshes extracted successfully   
I couldn't extract the original textures, so i used the wii ones
## Post #138
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-05-22T17:10:49+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from shakotay2 ↑Wed Jan 13, 2021 10:35 pm at Wed Jan 13, 2021 10:35 pm
>
> 
I wouldn't bet that someone will finish it.
It's not too hard to trick around with the script, the line in question is
while cnt < 5 :

For l_bell_d.xbx you can replace 5 by 21, but some sub meshes come out ugly then because they require noesis.RPGEO_TRIANGLE_STRIP
(So there must be a flag in the model data indicating which sort of triangles to be used, the harder part.)

From the first run with (noesis.RPGEO_TRIANGLE) you'll get 5 proper sub meshes (I hope).

You might try a "brute force" attempt/second run using strips for all 21 submeshes.
This way  you should get all submeshs (with superfluous faces, though).

Well, this was pretty simple (exported from Noesis as wavefront obj):
.
l_bell_d.jpg
(Keep in mind that the first five objects should use "normal" triangles, not strips.)

well, is there a download for those models? or the link for file?
## Post #139
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-23T07:31:25+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Xentax threads are for research, not to provide you with models. You'll need the game to get them. 

(Research is done, more or less, so no need to have working links to samples any more.)
## Post #140
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-05-23T16:51:22+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

I don't have a PC that has alot of gigabytes anymore but this time it is 28.0 GB so...
I wouldn't know why. I just never haven gotten the Ben model with the Omnitrix from Vilgax Attacks tho.
Not to be rude but, It's difficult getting the models 
Edit: Which file contains those models?
## Post #141
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-05-23T18:26:40+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from shakotay2 ↑Wed Jan 13, 2021 10:35 pm at Wed Jan 13, 2021 10:35 pm
>
> 
I wouldn't bet that someone will finish it.
It's not too hard to trick around with the script, the line in question is
while cnt < 5 :

For l_bell_d.xbx you can replace 5 by 21, but some sub meshes come out ugly then because they require noesis.RPGEO_TRIANGLE_STRIP
(So there must be a flag in the model data indicating which sort of triangles to be used, the harder part.)

From the first run with (noesis.RPGEO_TRIANGLE) you'll get 5 proper sub meshes (I hope).

You might try a "brute force" attempt/second run using strips for all 21 submeshes.
This way  you should get all submeshs (with superfluous faces, though).

Well, this was pretty simple (exported from Noesis as wavefront obj):
.
l_bell_d.jpg
(Keep in mind that the first five objects should use "normal" triangles, not strips.)

What addon do you use for those models?
## Post #142
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-05-24T21:59:39+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from shakotay2 ↑Sun May 23, 2021 3:31 pm at Sun May 23, 2021 3:31 pm
>
> 
Xentax threads are for research, not to provide you with models. You'll need the game to get them. 

(Research is done, more or less, so no need to have working links to samples any more.)

Hey, can I get a mediafire download link for those Ben 10 Vilgax Attacks models you got? I don't need the game and it's difficult to import those on a 32-bit laptop.
## Post #143
- Username: thekale
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 30, 2020 10:51 pm
- Post datetime: 2021-05-25T16:55:20+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

I was working on Ben 10 Alien force (wii), and got some entity templates files but i couldn't extracted them.
I also noticed that there's some bone data in the file.
If anyone can help me, I would really appreciate it.
## Post #144
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-05-25T17:23:09+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Oh dear. Can you try ripping the Ben Tennyson model from Ben 10 Alien Force: The Game for PSP with the textures and maybe show a screenshot?
(btw i can't rip any of the game models at the moment since i need a new pc that has loads of gigabytes though)
Edit: thekale, Did you rip the model and show screenshot yet?
[omnitrix.png](https://xentaxbackup.github.io/file/20213_omnitrix.png)
## Post #145
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-05-25T20:12:01+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from thekale ↑Wed May 26, 2021 12:55 am at Wed May 26, 2021 12:55 am
>
> 
I was working on Ben 10 Alien force (wii), and got some entity templates files but i couldn't extracted them.
I also noticed that there's some bone data in the file.
If anyone can help me, I would really appreciate it.

Hey my dude, could you try ripping the Ben Tennyson model from Ben 10: Alien Force for PS2, PSP or Wii? Then send the link and screenshot to Deviantart on chat?
## Post #146
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-05-27T16:08:54+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from thekale ↑Wed May 26, 2021 12:55 am at Wed May 26, 2021 12:55 am
>
> 
I was working on Ben 10 Alien force (wii), and got some entity templates files but i couldn't extracted them.
I also noticed that there's some bone data in the file.
If anyone can help me, I would really appreciate it.
Edit:  
I forgot to put the sample  
Sample

Y'know, you can do a sample of Ben Tennyson too so I can see the model and textures by download link?
## Post #147
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-01T19:59:39+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Good news! I got a model of Ben Tennyson from Ben 10: Alien Force for PSP!



Ben_Tennyson_model_pic.png (57.49 KiB) Viewed 195 times


I also might get a download link later
## Post #148
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-10T19:36:40+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from Bigchillghost ↑Mon Dec 12, 2016 9:21 pm at Mon Dec 12, 2016 9:21 pm
>
> 
Hey guys! I need help to get some models from the video game Ben 10 Ultimate Alien: Cosmic Destruction, 
which was powered by Vicious Engine. 



I really love this cartoon series so I'm about crazy for collecting their models.  

Well I've checked the forum and found a post about a game of Vicious Engine but didn't find much useful.
All I know so far is that for every version published on each platform some of its files were named in the
same way, for instance, xxx.ps3 on PS3, xxx.xbx on XBox 360 and xxx.wii on Wii, which implys they may
be in the same way of encryption. Besides, these models were created in 3Ds Max, but not sure if their
format is still max.
Screenshot From The Bonus Video .jpg

Below are some samples I extracted from the ISO file:

XBox 360 Version
PS3 Version
Wii Version

Seems the scripts folder within stores their animation files, who knows! 

I know I can rip these models through Dolphin, but I'm more eager to get them from Xbox 360 and
PS3 versions, as there're some exclusive characters and they're of higher resources of course. So 
Wii version files are just for compare.

Any help is appreciated!

Uhh...
Dude? When I go into the global download links, It gives me the file doesn't exist error.
## Post #149
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-14T17:22:38+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Hey Shakotay2, do you happen to have a download link for the GetBen10-UA-CDM file plugin so I can look at the models from Ben 10: Alien Force Vilgax Attacks?
Plus, I can't get the XBX files supported onto Noesis.
## Post #150
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-14T21:49:42+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Read from here, again (ignore the .ps3 part):

> Reply from shakotay2 ↑Sun Mar 29, 2020 2:57 pm at Sun Mar 29, 2020 2:57 pm
>
> 
----------------------------------------------------------------------------------

> Reply from lilyampykidYTXeNTaX ↑Tue Jun 15, 2021 1:22 am at Tue Jun 15, 2021 1:22 am
>
> Plus, I can't get the XBX files supported onto Noesis.Copy the script code for .xbx files in the above mentioned post(s) into a fmt_Ben10_xbx.py file (Windows Explorer -> New Text Document). Rename from .txt to .py
Then copy the .py file into Noesis' sub folder  \plugins\python

Start Noesis.exe:
.



Noesis_py_plugin.png (17.85 KiB) Viewed 130 times



AND, keep in mind, that I checked l_bell_d.xbx only, so don't blame me if the script doesn't work for other xbx files.
## Post #151
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-14T22:56:20+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Thank you!  I extracted some mesh!
## Post #152
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-15T13:06:26+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Btw, I am having trouble with getting some XBox 360 models from Ben 10: Alien Force: Vilgax Attacks, Can someone help me fix the issue with this file I am using with Hex2Obj?
The file is e_jr.xbx. Also you may wanna help me out but see if you downloaded the file called global.rar and had it unpacked?



issue on h2o.png (12.38 KiB) Viewed 70 times



Plus, I couldn't get the real model. or the texture neither. It gave me a blocked model
## Post #153
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-15T14:29:43+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Using a small model at the beginning of research usually is a good idea - but not in this case.
There is some ASCII code in there so you might try to convert that manually to .obj (with some basic understanding of wavefront obj format).

```
  <mesh name="mesh | data | jetray_laser_01" rendermode="shaded" time="0" numfaces="16" numverts="32" numtverts="36" numcverts="32" numcarrays="1">
   <material_reference>0</material_reference>
   <wire_color>0.6 0.894118 0.839216</wire_color>
   <vertices count="32">
    <vertex i="0">0.332081 0.00105145 -4.34921e-006</vertex>
    <vertex i="1">91.0313 0.000496327 -1.97285e-005</vertex>
    <vertex i="2">0.3321 0.00105439 29.3321</vertex>
    ...

```


Or better start with e_hm.xbx.
.



e_hm-xbx.png (104.18 KiB) Viewed 63 times


(My 15 min per model have expired so didn't check where the sub meshes to start and stop, if any. You need to get rid of the extra faces.)

(Start of face indices might be 0x15386, you need to fiddle around a little bit.)
## Post #154
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-15T14:48:44+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

I'll try that but, what file is the Jetray model in? I can't remember and I tried to look for the model.
## Post #155
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-15T15:46:35+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from shakotay2 ↑Tue Jun 15, 2021 10:29 pm at Tue Jun 15, 2021 10:29 pm
>
> 
Using a small model at the beginning of research usually is a good idea - but not in this case.
There is some ASCII code in there so you might try to convert that manually to .obj (with some basic understanding of wavefront obj format).


Or better start with e_hm.xbx.
.
e_hm-xbx.png
(My 15 min per model have expired so didn't check where the sub meshes to start and stop, if any. You need to get rid of the extra faces.)

(Start of face indices might be 0x15386, you need to fiddle around a little bit.)

What file is the Jetray model and texture in? I would need help.
## Post #156
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-15T16:47:35+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from shakotay2 ↑Tue Jun 15, 2021 10:29 pm at Tue Jun 15, 2021 10:29 pm
>
> 
Or better start with e_hm.xbx.
.
e_hm-xbx.png
(My 15 min per model have expired so didn't check where the sub meshes to start and stop, if any. You need to get rid of the extra faces.)

(Start of face indices might be 0x15386, you need to fiddle around a little bit.)

Plus, can you check all the files and add them into the Noesis Ben10UA-CDM plugin script in folders: global and l_bell and sub folders.
## Post #157
- Username: thekale
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 30, 2020 10:51 pm
- Post datetime: 2021-06-15T17:31:16+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from lilyampykidYTXeNTaX ↑Tue Jun 15, 2021 10:48 pm at Tue Jun 15, 2021 10:48 pm
>
> 
I'll try that but, what file is the Jetray model in? I can't remember and I tried to look for the model.

The models of the aliens are in "l_bell_d.xbx"
## Post #158
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-15T17:40:27+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from thekale ↑Wed Jun 16, 2021 1:31 am at Wed Jun 16, 2021 1:31 am
>
> 
lilyampykidYTXeNTaX wrote: ↑Tue Jun 15, 2021 10:48 pm
I'll try that but, what file is the Jetray model in? I can't remember and I tried to look for the model.


The models of the aliens are in "l_bell_d.xbx"
Thank you dude. What is the face index count for Jetray and the vertices count for Jetray?
And what's the texture for Jetray and the address for Jetray with Hex2obj?
## Post #159
- Username: thekale
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 30, 2020 10:51 pm
- Post datetime: 2021-06-15T17:44:20+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from lilyampykidYTXeNTaX ↑Tue Jun 15, 2021 9:06 pm at Tue Jun 15, 2021 9:06 pm
>
> 
Btw, I am having trouble with getting some XBox 360 models from Ben 10: Alien Force: Vilgax Attacks, Can someone help me fix the issue with this file I am using with Hex2Obj?
The file is e_jr.xbx. Also you may wanna help me out but see if you downloaded the file called global.rar and had it unpacked?
issue on h2o.png

Plus, I couldn't get the real model. or the texture neither. It gave me a blocked model
## Post #160
- Username: thekale
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 30, 2020 10:51 pm
- Post datetime: 2021-06-15T17:45:57+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from lilyampykidYTXeNTaX ↑Wed Jun 16, 2021 1:40 am at Wed Jun 16, 2021 1:40 am
>
> 
thekale wrote: ↑Wed Jun 16, 2021 1:31 am
lilyampykidYTXeNTaX wrote: ↑Tue Jun 15, 2021 10:48 pm
I'll try that but, what file is the Jetray model in? I can't remember and I tried to look for the model.


The models of the aliens are in "l_bell_d.xbx"

Thank you dude. What is the face index count for Jetray and the vertices count for Jetray?
And what's the texture for Jetray and the address for Jetray with Hex2obj?

Sorry but i couldn't get the textures
## Post #161
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-15T17:46:27+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from thekale ↑Wed Jun 16, 2021 1:44 am at Wed Jun 16, 2021 1:44 am
>
> 
lilyampykidYTXeNTaX wrote: ↑Tue Jun 15, 2021 9:06 pm
Btw, I am having trouble with getting some XBox 360 models from Ben 10: Alien Force: Vilgax Attacks, Can someone help me fix the issue with this file I am using with Hex2Obj?
The file is e_jr.xbx. Also you may wanna help me out but see if you downloaded the file called global.rar and had it unpacked?
issue on h2o.png

Plus, I couldn't get the real model. or the texture neither. It gave me a blocked model

There's a issue with that model though, Isn't the triangles gonna soon be fixed?
## Post #162
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-15T17:46:51+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from thekale ↑Wed Jun 16, 2021 1:45 am at Wed Jun 16, 2021 1:45 am
>
> 
lilyampykidYTXeNTaX wrote: ↑Wed Jun 16, 2021 1:40 am
thekale wrote: ↑Wed Jun 16, 2021 1:31 am


The models of the aliens are in "l_bell_d.xbx"

Thank you dude. What is the face index count for Jetray and the vertices count for Jetray?
And what's the texture for Jetray and the address for Jetray with Hex2obj?


Sorry but i couldn't get the textures

Very sad.

Will you extract the textures one time?
## Post #163
- Username: thekale
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 30, 2020 10:51 pm
- Post datetime: 2021-06-15T17:49:08+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from lilyampykidYTXeNTaX ↑Wed Jun 16, 2021 1:46 am at Wed Jun 16, 2021 1:46 am
>
> 
thekale wrote: ↑Wed Jun 16, 2021 1:45 am
lilyampykidYTXeNTaX wrote: ↑Wed Jun 16, 2021 1:40 am

Thank you dude. What is the face index count for Jetray and the vertices count for Jetray?
And what's the texture for Jetray and the address for Jetray with Hex2obj?


Sorry but i couldn't get the textures  


Very sad.

Will you extract the textures one time?

Ask shakotay2 if he can helps you.
## Post #164
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-15T17:49:59+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from thekale ↑Wed Jun 16, 2021 1:44 am at Wed Jun 16, 2021 1:44 am
>
> 
lilyampykidYTXeNTaX wrote: ↑Tue Jun 15, 2021 9:06 pm
Btw, I am having trouble with getting some XBox 360 models from Ben 10: Alien Force: Vilgax Attacks, Can someone help me fix the issue with this file I am using with Hex2Obj?
The file is e_jr.xbx. Also you may wanna help me out but see if you downloaded the file called global.rar and had it unpacked?
issue on h2o.png

Plus, I couldn't get the real model. or the texture neither. It gave me a blocked model

Done! I extracted Jetray!
Next is Cannonbolt?
But how do I extract textures from XBX files?
## Post #165
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-15T17:55:29+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Hey Shakotay2, may i get the texture of Jetray from Vilgax Attacks?
## Post #166
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-15T18:05:35+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from shakotay2 ↑Tue Jun 15, 2021 10:29 pm at Tue Jun 15, 2021 10:29 pm
>
> 
Or better start with e_hm.xbx.
.
e_hm-xbx.png
(My 15 min per model have expired so didn't check where the sub meshes to start and stop, if any. You need to get rid of the extra faces.)

(Start of face indices might be 0x15386, you need to fiddle around a little bit.)

Sorry if I double post, but can i get the Jetray texture out of l_bell_d.xbx?
## Post #167
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-15T18:10:35+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from lilyampykidYTXeNTaX ↑Wed Jun 16, 2021 1:55 am at Wed Jun 16, 2021 1:55 am
>
> 
Hey Shakotay2, may i get the texture of Jetray from Vilgax Attacks?Well, if you check my posts you'll see that I'm not the "texture man".  
I have no idea.

> Reply from lilyampykidYTXeNTaX ↑Wed Jun 16, 2021 1:46 am at Wed Jun 16, 2021 1:46 am
>
> There's a issue with that model though, Isn't the triangles gonna soon be fixed?use 268d2e as starting point for the faces indices:
.



jetray.png (65.19 KiB) Viewed 208 times



> Reply from lilyampykidYTXeNTaX ↑Wed Jun 16, 2021 2:05 am at Wed Jun 16, 2021 2:05 am
>
> Sorry if I double post,..well, you know that there's an edit button, don't you?  
And again, "no", usually I don't care for textures (except creating some dds headers from time to time).
## Post #168
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-15T18:14:49+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Next what have I got to do to fix the triangles if they are screwed up for Jetray and Cannonbolt?
Edit: Nvm, If you turn off Strip, there'll be no screw ups on the models.
## Post #169
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-15T19:23:56+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

What's the address for Cannonbolt model and the verts count with the face indices? I can't seem to get Cannonbolt next.
## Post #170
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-15T19:40:58+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from thekale ↑Wed Jun 16, 2021 1:49 am at Wed Jun 16, 2021 1:49 am
>
> 

Sorry but i couldn't get the textures

Do you mind giving me the addresses for the Brainstorm and Cannonbolt models? Thank you.
## Post #171
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-16T00:55:43+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Message got censored, so I got warned so and i had to censore it myself, Sorry for kidding!
## Post #172
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-16T07:15:02+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

I'm usually not acting on demand, sorry.

The more informations you collect about Get BEN 10 UA's textures/texture format the more likely someone might be able to help you out.

(When you take the time to check any thread on Xentax which got stuck/"died" you'll find that it's usually due to missing inputs.)

> Reply from lilyampykidYTXeNTaX ↑Wed Jun 16, 2021 8:55 am at Wed Jun 16, 2021 8:55 am
>
> Okay. I gotta be more careful, ...Telling us in a row of 4 subsequent posts of yours? You should avoid kidding people.
## Post #173
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-16T13:34:00+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Sorry.
## Post #174
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-16T15:47:08+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Plus, can someone make a copy of their global_PS3.rar or global_XBox360.rar for Ben 10: Ultimate Alien Cosmic Destruction? And hand the download links for both?
## Post #175
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-19T14:56:45+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

I guess thekale would soon give me Cannonbolt but I told kalezer on Deviantart that I won't share anyone that model.
## Post #176
- Username: thekale
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 30, 2020 10:51 pm
- Post datetime: 2021-06-21T15:37:28+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Can someone help me with this??  [l_romd_d](https://mega.nz/file/GNsEGYAS#nStyICumq3MX6oBXfRFPs36RoqMYbfgFJa-ZRKnx38s)
## Post #177
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-21T16:12:15+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from thekale ↑Mon Jun 21, 2021 11:37 pm at Mon Jun 21, 2021 11:37 pm
>
> 
Can someone help me with this??  l_romd_d

That one looks broken...
## Post #178
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-21T16:30:01+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

@lilyampykidYTXeNTaX: you really can't stop spamming this thread, can you?  
What's your reason for this useless quotation? (No, don't answer, pleease... it's a rhetorical question.)
------------------------------------------------------------------------

> Reply from thekale ↑Mon Jun 21, 2021 11:37 pm at Mon Jun 21, 2021 11:37 pm
>
> 
l_romd_d.ps3_4.h2o needs a correction; this happened because I didn't do a complete format analysis (as always  )
well, from a look at the log: 4. FI: 12102, v: 3104 (4c018) that's ok, why does the code proceed to 0x5e520 instead of 0x4C220?
(one year later, love it  ha, there's some strange "addr correction" which assumes an FVFsize of 20, too bad...  )
.



l_romd_d.ps3_4_h2o_correction.png (163.74 KiB) Viewed 105 times
## Post #179
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-21T16:35:27+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

OH MY... GOD!!!!!!! It is Vulkanus! Me and thekale think it is.
Edit: @shakotay2, I am so sorry for spamming quotation!
Edit 2: Plus. I can't view meshes within Hex2obj. (minor edit in edit 2)
Edit 3: .
## Post #180
- Username: thekale
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 30, 2020 10:51 pm
- Post datetime: 2021-06-21T16:51:18+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from shakotay2 ↑Tue Jun 22, 2021 12:30 am at Tue Jun 22, 2021 12:30 am
>
> 
@lilyampykidYTXeNTaX: you really can't stop spamming this thread, can you?  
What's your reason for this useless quotation? (No, don't answer, pleease... it's a rhetorical question.)
------------------------------------------------------------------------
thekale wrote: ↑Mon Jun 21, 2021 11:37 pm
l_romd_d.ps3_4.h2o needs a correction; this happened because I didn't do a complete format analysis (as always  )
.
l_romd_d.ps3_4_h2o_correction.png

Thanks dude!! you're the best
## Post #181
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-21T18:31:49+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

I am uploading c_kid_ben.ps3 sample. [c_kid_ben.ps3 sample](https://mega.nz/file/vEUnDIJC#ucJEJnvgtJDC7vJ5_R-552orHq7vNItymMC5GvkCWCo)
Enjoy!
## Post #182
- Username: thekale
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 30, 2020 10:51 pm
- Post datetime: 2021-06-21T18:48:37+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from lilyampykidYTXeNTaX ↑Tue Jun 22, 2021 2:31 am at Tue Jun 22, 2021 2:31 am
>
> 
I am uploading c_kid_ben.ps3 sample. c_kid_ben.ps3 sample
Enjoy!

I think there are four models in that file
## Post #183
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-21T18:51:55+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Ohh... Do you seem to have the one that contains the human form of Kid Ben?
Edit: Plus. Let's share people the entity templates of Humungousaur, Swampfire, Big Chill, Jetray and Spidermonkey (Ben 10 Alien Force Wii topic on Zenhax) Ok?
## Post #184
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-21T19:25:51+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

You're so enthusiastic so I couldn't resist to update the tool  :

> Reply from shakotay2 ↑Thu Mar 19, 2020 5:02 am at Thu Mar 19, 2020 5:02 am
>
> 
(Hopefully it doesn't introduce more bugs...  )
.



Ben10-l_rom_d-ps3_126_obj.png (205.54 KiB) Viewed 124 times


(Only objects with 500 verts and above (another 112 available) plus 1695 with vertex count <500 not cared for.)
## Post #185
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-21T19:36:54+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Tool update?! Wow! Can't wait to use .h2o files on Blender.
Edit: Hey @shakotay2 
Can you make Make_H2O_CNPTEXL and have it support .ps3 files?
## Post #186
- Username: thekale
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 30, 2020 10:51 pm
- Post datetime: 2021-06-21T19:56:06+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models


## Post #187
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-21T19:58:33+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Can you do heatblast.et next @thekale?
## Post #188
- Username: thekale
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 30, 2020 10:51 pm
- Post datetime: 2021-06-21T20:16:12+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from shakotay2 ↑Tue Jun 22, 2021 3:25 am at Tue Jun 22, 2021 3:25 am
>
> 
You're so enthusiastic so I couldn't resist to update the tool  :
shakotay2 wrote: ↑Thu Mar 19, 2020 5:02 am
(Hopefully it doesn't introduce more bugs...  )
.
Ben10-l_rom_d-ps3_126_obj.png
(Only objects with 500 verts and above (another 112 available) plus 1695 with vertex count <500 not cared for.)

Thanks!! it works now
## Post #189
- Username: thekale
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 30, 2020 10:51 pm
- Post datetime: 2021-06-21T20:17:35+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from lilyampykidYTXeNTaX ↑Tue Jun 22, 2021 3:58 am at Tue Jun 22, 2021 3:58 am
>
> 
Can you do heatblast.et next @thekale?

Done!! 
I'm not sure if it's possible create a tool (h2o) for Punch Time Explosion
## Post #190
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-21T20:18:30+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Oh. This is cool! I'll make a post for Ben 10 Galactic Racing (PS3) models!
## Post #191
- Username: thekale
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 30, 2020 10:51 pm
- Post datetime: 2021-06-21T20:30:44+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from shakotay2 ↑Tue Jun 22, 2021 3:25 am at Tue Jun 22, 2021 3:25 am
>
> 
You're so enthusiastic so I couldn't resist to update the tool  :
shakotay2 wrote: ↑Thu Mar 19, 2020 5:02 am
(Hopefully it doesn't introduce more bugs...  )
.
Ben10-l_rom_d-ps3_126_obj.png
(Only objects with 500 verts and above (another 112 available) plus 1695 with vertex count <500 not cared for.)
I got the vertices of Ben.et from Alien force (wii) but i couldn't find the face indices.
Would you give a hand?   
Sorry, i forgot to put the sample   [Ben.et](https://mega.nz/file/bF9kiazC#BZ2y1Z4FaGcaWFrU9uKF3cuNeiT6V1DQvWnNKFOj8vM)
## Post #192
- Username: thekale
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Nov 30, 2020 10:51 pm
- Post datetime: 2021-06-21T20:55:42+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from lilyampykidYTXeNTaX ↑Tue Jun 22, 2021 4:18 am at Tue Jun 22, 2021 4:18 am
>
> 
Oh. This is cool! I'll make a post for Ben 10 Galactic Racing (PS3) models!
Sounds good!!
## Post #193
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-21T21:22:44+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Did a new post for model ripping help.
## Post #194
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-22T18:29:20+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

I have some samples from Cartoon Network Punch Time Explosion XL, but I also have c_gwen.ps3 and c_kevin.ps3 and c_vilgax too.
I also have a stage sample pack. "l_fos3" is a folder for the multiplayer arena for Foster's Home for Imaginary Friends. This stage is called "Friends' Room" I couldn't extract some parts out of l_fos3_s.ps3 can someone help?
Edit: I forgot the sample of l_fos3_s.ps3   [l_fos3_s.ps3](https://mega.nz/file/I0hmyYqA#3DHqB_4SBROJcoOjLlUhHZ5BOoxNii7EBcG6g0vCzIk)
## Post #195
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-22T21:20:48+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

@shakotay2 Can I get the latest version of Blender's Hex2obj Addon?
## Post #196
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-22T21:29:43+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Dunno what you mean. There is no such thing like "Blender's Hex2obj Addon".
## Post #197
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-22T21:31:34+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Oh. The updated python file that uses Ben 10 UA CD's models?
## Post #198
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-22T21:38:07+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Oh and I have some Cartoon Network Punch Time Explosion XL models. Can you make MakeH2O_CartoonNetworkPunchTimeEXL?
Edit: Files are ps3.
Edit 2: I had to fix the program name.
## Post #199
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-22T21:46:20+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from lilyampykidYTXeNTaX ↑Wed Jun 23, 2021 5:31 am at Wed Jun 23, 2021 5:31 am
>
> 
Oh. The updated python file that uses Ben 10 UA CD's models?It's for Noesis - and the post/link is hard to find - because there's so many double posts in this thread. 

> Reply from shakotay2 ↑Wed Feb 10, 2021 11:36 pm at Wed Feb 10, 2021 11:36 pm
>
> 
----------------------------------------------------------------------------

> Reply from lilyampykidYTXeNTaX ↑Wed Jun 23, 2021 5:38 am at Wed Jun 23, 2021 5:38 am
>
> 
Oh and I have some Cartoon Network Punch Time Explosion XL models. Can you make MakeH2O_CTEPTEXL?"CTEPTEXL"? What is this? Textures? Make_H2O doesn't treat textures.
(Plus, I don't work on demand, sry.)
## Post #200
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-22T21:58:00+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Okay... I'll try programming a little, also sorry for demanding you.
## Post #201
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-22T22:00:00+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

wait i know what CNPTEXL means it's Cartoon Network Punch Time Explosion XL
## Post #202
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-26T16:09:28+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Today I am going to try and extract the Goop model from Ben 10 Alien Force: Vilgax Attacks (XBox 360).
## Post #203
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-26T20:24:40+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from shakotay2 ↑Wed Jun 23, 2021 5:29 am at Wed Jun 23, 2021 5:29 am
>
> 
Dunno what you mean. There is no such thing like "Blender's Hex2obj Addon".

Guess what? I got the Vilgax Attacks Bellwood textures. I got Brainstorm, Jetray, Goop and Chromastone's textures. Sound good now? I used Quickbms to do that.
Edit: Here's a example of one of the models using a texture, took screenshot from Blender, snipped model out of the background.


Jetray_model_NO_BG.png (30.58 KiB) Viewed 127 times
## Post #204
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-07-01T15:28:22+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

I have a sample of the Bellwood stage from Ben 10: Alien Force Vilgax Attacks (XBox 360) but, I can't extract the whole stage. Can I get help with the sample? If that's okay if you don't want to.
Edit: I forgot the file name, l_bell_s.xbx
## Post #205
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-01T16:00:41+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

I don't owe that game so have no idea what this is: "Bellwood stage" - you need to find it for yourself.
Read here:

> Reply from shakotay2 ↑Wed Jan 13, 2021 10:35 pm at Wed Jan 13, 2021 10:35 pm
>
> 
(Afair l_bell_d.xbx contains 21 models only, but not sure.)

I have no idea how many models are in l_bell_s.xbx and no time to check it, sorry.
Well, obviously that script will NOT work, "vaps" is missing at the beginning of the file. New script/research required.
(Or try to use hex2obj.)
## Post #206
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-07-01T17:16:13+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Okay, here we go! It's time to extract Goop.
## Post #207
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-01T19:22:28+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

whatever.

Using hex2obj with l_bell_s.xbx:
.



I_bell_s-xbx.png (36.04 KiB) Viewed 84 times


You might be required to split the file into 2 parts at 0x5D76BD0 in a hex editor for older versions of hex2obj (supporting file sizes < 124 MB only).
## Post #208
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-07-01T19:31:56+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Thanks, it should work. I'll try to use Hexedit, but I'm not good at it so. 
.
## Post #209
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-07-01T19:41:24+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Good news guys, I am going to make a PSP Ben 10 Vilgax Attacks Bellwood level textures mod, It will have XBox 360 textures. we'll see what they look like on them soon.
## Post #210
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-01T20:34:07+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

do whatever you need to do, §$%&()?! double poster  

Here's another Noesis script for .xbm files WITHOUT the vaps signature at file's beginning:
(don't forget to disable any other scripts handling .xbx files before using this one!)

```
import noesis
import rapi

def registerNoesisTypes():
	handle = noesis.register("GetBen10-UA-CDM",".xbx")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1
	
NOEPY_HEADER = "vap"

def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 3:
      return 0
   #if bs.readBytes(3).decode("ASCII") != NOEPY_HEADER:
   #   print("'vaps' not found!")
   #   return 0
   return 1  

def noepyLoadModel(data, mdlList):
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)
	bs.setEndian(NOE_BIGENDIAN)
	#rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)

	addr=bs.tell(); addr1=0; cnt= 0
	#while addr != addr1 :
	while cnt < 6 :
		fileBuff = bs.data[addr:bs.dataSize]#todo: Size has to be reduced with each run
		addr1= fileBuff.find(b'\xA6\x06\x00\x01\x08')
		addr += addr1
		bs.seek(addr)
		offset= bs.tell()
		print("sig at:", hex(offset))
		bs.seek(-12, NOESEEK_REL)#
		# counts
		vCnt = bs.readUShort()
		bs.seek(6, NOESEEK_REL)# skip
		fCnt = bs.readUShort()
		bs.seek(2, NOESEEK_REL)# skip dummy word
		bs.seek(6, NOESEEK_REL)# skip signature
		bs.seek(21*16+12, NOESEEK_REL)# this offset may be different for other model files
		print("vCnt, fCnt", vCnt,fCnt)
		# 
		FVFsize = int(20)
		offset= bs.tell()
		VBSize = vCnt * FVFsize
		print(cnt, ". Verts at:", hex(offset), VBSize)
		VBuff = bs.readBytes(VBSize)
		#print(VBuff)
		rapi.rpgBindPositionBufferOfs(VBuff, noesis.RPGEODATA_FLOAT, FVFsize, 0)
		rapi.rpgBindUV1BufferOfs(VBuff, noesis.RPGEODATA_FLOAT, FVFsize, 12)
		bs.seek(16+8, NOESEEK_REL)
		offset= bs.tell()
		print("FIs at:", hex(offset))
		#return 1
		FBuff = bs.readBytes(fCnt*2)
		#print(FBuff)
		rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)
		rapi.rpgCommitTriangles(FBuff, noesis.RPGEODATA_USHORT, fCnt, noesis.RPGEO_TRIANGLE, 1)
		#rapi.rpgCommitTriangles(FBuff, noesis.RPGEODATA_USHORT, fCnt, noesis.RPGEO_TRIANGLE_STRIP, 1)
		material = NoeMaterial("mat%03i"%cnt, "")
		rapi.rpgSetMaterial(material.name)
		addr += 1; cnt += 1

	mdl = rapi.rpgConstructModel()
	mdlList.append(mdl)
	
	#rapi.rpgClearBufferBinds()
	return 1

```
Works with I_bell_s.xbx and the first 5 sub meshes only, so don't blame me (well, 2 of those 5 are bogus  ).
Whoever wants to expand that script feel free to do so, I'm off for now...
.



5_sub_meshes_only_needs_(unfinished_script).png (26.86 KiB) Viewed 72 times
## Post #211
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-07-03T16:45:54+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

I got a file that's got the extension ".pak" and it's Ben 10: Alien Force's PSP game data. How can I only extract one file out of a pak?
## Post #212
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-04T22:09:45+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from lilyampykidYTXeNTaX ↑Fri Jul 02, 2021 3:31 am at Fri Jul 02, 2021 3:31 am
>
> 
Thanks, it should work. I'll try to use Hexedit, but I'm not good at it so.Usually it's a matter of learning.  Patience, etc.
The script from here

> Reply from shakotay2 ↑Fri Jul 02, 2021 4:34 am at Fri Jul 02, 2021 4:34 am
>
>  can create a log with params for more than 2000 models.
Some little changes need to be applied to that script, though. Same as above: "a matter of learning".
.

```
vCnt, fCnt 66 288
0 . Verts_at: 0x309a64 1320
FIs_at: 0x309fa4
-------- sig at: 0x30a222
vCnt, fCnt 12 36
1 . Verts_at: 0x30a384 240
FIs_at: 0x30a48c
-------- sig at: 0x30a532
vCnt, fCnt 4 6
2 . Verts_at: 0x30a694 80
FIs_at: 0x30a6fc
-------- sig at: 0x30a762
vCnt, fCnt 24 36
3 . Verts_at: 0x30a8c4 480
FIs_at: 0x30aabc
-------- sig at: 0x30ab72
vCnt, fCnt 50 102
4 . Verts_at: 0x30acd4 1000
FIs_at: 0x30b0d4
-------- sig at: 0x30b1e2
vCnt, fCnt 82 186
5 . Verts_at: 0x30b344 1640
FIs_at: 0x30b9c4
-------- sig at: 0x30bb72
vCnt, fCnt 310 600
6 . Verts_at: 0x30bcd4 6200
FIs_at: 0x30d524
-------- sig at: 0x30da22
vCnt, fCnt 26 36
7 . Verts_at: 0x30db84 520
FIs_at: 0x30dda4
-------- sig at: 0x30de32
vCnt, fCnt 34 132
8 . Verts_at: 0x30df94 680
FIs_at: 0x30e254
-------- sig at: 0x30e3a2
vCnt, fCnt 10 24
9 . Verts_at: 0x30e504 200
FIs_at: 0x30e5e4
-------- sig at: 0x30e652
vCnt, fCnt 70 156
10 . Verts_at: 0x30e7b4 1400
FIs_at: 0x30ed44
-------- sig at: 0x30eed2
#vCnt, fCnt 718 1197
11 . Verts_at: 0x30f034 14360
FIs_at: 0x312864
-------- sig at: 0x313212
vCnt, fCnt 30 114
12 . Verts_at: 0x313374 600
FIs_at: 0x3135e4
-------- sig at: 0x314ea2
vCnt, fCnt 38 60
13 . Verts_at: 0x315004 760
FIs_at: 0x315314
-------- sig at: 0x3153e2
vCnt, fCnt 26 36
14 . Verts_at: 0x315544 520
FIs_at: 0x315764
-------- sig at: 0x3157f2
vCnt, fCnt 58 90
15 . Verts_at: 0x315954 1160
FIs_at: 0x315df4
-------- sig at: 0x315ee2
vCnt, fCnt 24 36
16 . Verts_at: 0x316044 480
FIs_at: 0x31623c
-------- sig at: 0x3162f2
vCnt, fCnt 102 180
17 . Verts_at: 0x316454 2040
FIs_at: 0x316c64
-------- sig at: 0x318c22
vCnt, fCnt 204 612
18 . Verts_at: 0x318d84 4080
FIs_at: 0x319d8c
-------- sig at: 0x31a2b2
##vCnt, fCnt 1238 2652
19 . Verts_at: 0x31a414 24760
FIs_at: 0x3204e4
-------- sig at: 0x3219f2
vCnt, fCnt 20 42
20 . Verts_at: 0x321b54 400
FIs_at: 0x321cfc
-------- sig at: 0x321da2
vCnt, fCnt 224 456
21 . Verts_at: 0x321f04 4480
FIs_at: 0x32309c
-------- sig at: 0x323492
vCnt, fCnt 24 36
22 . Verts_at: 0x3235f4 480
FIs_at: 0x3237ec
-------- sig at: 0x3238a2
vCnt, fCnt 42 84
23 . Verts_at: 0x323a04 840
FIs_at: 0x323d64
-------- sig at: 0x323e52
vCnt, fCnt 12 36
24 . Verts_at: 0x323fb4 240
FIs_at: 0x3240bc
-------- sig at: 0x328a22
vCnt, fCnt 36 96
25 . Verts_at: 0x328b84 720
FIs_at: 0x328e6c
-------- sig at: 0x32fc02
vCnt, fCnt 314 504
26 . Verts_at: 0x32fd64 6280
FIs_at: 0x331604
-------- sig at: 0x331a32
vCnt, fCnt 100 336
27 . Verts_at: 0x331b94 2000
FIs_at: 0x33237c
-------- sig at: 0x332672
vCnt, fCnt 274 489
28 . Verts_at: 0x3327d4 5480
FIs_at: 0x333d54
-------- sig at: 0x334162
vCnt, fCnt 10 24
29 . Verts_at: 0x3342c4 200
FIs_at: 0x3343a4
-------- sig at: 0x334412
vCnt, fCnt 144 480
30 . Verts_at: 0x334574 2880
FIs_at: 0x3350cc
-------- sig at: 0x3354f2
vCnt, fCnt 72 195
31 . Verts_at: 0x335654 1440
FIs_at: 0x335c0c
-------- sig at: 0x335df2
##vCnt, fCnt 1252 2652
32 . Verts_at: 0x335f54 25040
FIs_at: 0x33c13c
-------- sig at: 0x33f9e2
#vCnt, fCnt 642 1416
33 . Verts_at: 0x33fb44 12840
FIs_at: 0x342d84
-------- sig at: 0x3438d2
vCnt, fCnt 10 24
34 . Verts_at: 0x343a34 200
FIs_at: 0x343b14
-------- sig at: 0x343e92
vCnt, fCnt 52 216
35 . Verts_at: 0x343ff4 1040
FIs_at: 0x34441c
-------- sig at: 0x344622
vCnt, fCnt 14 30
36 . Verts_at: 0x344784 280
FIs_at: 0x3448b4
-------- sig at: 0x344942
vCnt, fCnt 16 48
37 . Verts_at: 0x344aa4 320
FIs_at: 0x344bfc
-------- sig at: 0x345302
vCnt, fCnt 20 42
38 . Verts_at: 0x345464 400
FIs_at: 0x34560c
-------- sig at: 0x3456b2
vCnt, fCnt 26 36
39 . Verts_at: 0x345814 520
FIs_at: 0x345a34
-------- sig at: 0x345ac2
vCnt, fCnt 88 186
40 . Verts_at: 0x345c24 1760
FIs_at: 0x34631c
-------- sig at: 0x3464f2
vCnt, fCnt 74 120
41 . Verts_at: 0x346654 1480
FIs_at: 0x346c34
-------- sig at: 0x346d62
vCnt, fCnt 4 6
42 . Verts_at: 0x346ec4 80
FIs_at: 0x346f2c
-------- sig at: 0x346f92
vCnt, fCnt 44 96
43 . Verts_at: 0x3470f4 880
FIs_at: 0x34747c
-------- sig at: 0x347592
vCnt, fCnt 66 288
44 . Verts_at: 0x3476f4 1320
FIs_at: 0x347c34
-------- sig at: 0x347eb2
vCnt, fCnt 42 84
45 . Verts_at: 0x348014 840
FIs_at: 0x348374
-------- sig at: 0x348462
vCnt, fCnt 336 504
46 . Verts_at: 0x3485c4 6720
FIs_at: 0x34a01c
-------- sig at: 0x34a472
vCnt, fCnt 36 114
47 . Verts_at: 0x34a5d4 720
FIs_at: 0x34a8bc
-------- sig at: 0x34a9f2
vCnt, fCnt 130 390
48 . Verts_at: 0x34ab54 2600
FIs_at: 0x34b594
-------- sig at: 0x34b8e2
vCnt, fCnt 42 102
49 . Verts_at: 0x34ba44 840
FIs_at: 0x34bda4
-------- sig at: 0x34dec2
vCnt, fCnt 40 96
50 . Verts_at: 0x34e024 800
FIs_at: 0x34e35c
-------- sig at: 0x34e482
vCnt, fCnt 24 66
51 . Verts_at: 0x34e5e4 480
FIs_at: 0x34e7dc
-------- sig at: 0x34e8c2
vCnt, fCnt 40 96
52 . Verts_at: 0x34ea24 800
FIs_at: 0x34ed5c
-------- sig at: 0x34ee82
vCnt, fCnt 28 42
53 . Verts_at: 0x34efe4 560
FIs_at: 0x34f22c
-------- sig at: 0x34f9e2
vCnt, fCnt 40 144
54 . Verts_at: 0x34fb44 800
FIs_at: 0x34fe7c
-------- sig at: 0x350002
vCnt, fCnt 58 126
55 . Verts_at: 0x350164 1160
FIs_at: 0x350604
-------- sig at: 0x350742
vCnt, fCnt 98 192
56 . Verts_at: 0x3508a4 1960
FIs_at: 0x351064
-------- sig at: 0x3518a2
#vCnt, fCnt 516 936
57 . Verts_at: 0x351a04 10320
FIs_at: 0x35426c
-------- sig at: 0x354a12
vCnt, fCnt 24 36
58 . Verts_at: 0x354b74 480
FIs_at: 0x354d6c
-------- sig at: 0x354e22
vCnt, fCnt 156 354
59 . Verts_at: 0x354f84 3120
FIs_at: 0x355bcc
-------- sig at: 0x355ee2
vCnt, fCnt 24 30
60 . Verts_at: 0x356044 480
FIs_at: 0x35623c
-------- sig at: 0x3562e2
vCnt, fCnt 52 216
61 . Verts_at: 0x356444 1040
FIs_at: 0x35686c
-------- sig at: 0x3571c2
vCnt, fCnt 20 30
62 . Verts_at: 0x357324 400
FIs_at: 0x3574cc
-------- sig at: 0x357562
vCnt, fCnt 26 144
63 . Verts_at: 0x3576c4 520
FIs_at: 0x3578e4
-------- sig at: 0x357a42
vCnt, fCnt 24 36
64 . Verts_at: 0x357ba4 480
FIs_at: 0x357d9c
-------- sig at: 0x357e52
vCnt, fCnt 10 24
65 . Verts_at: 0x357fb4 200
FIs_at: 0x358094
-------- sig at: 0x358102
vCnt, fCnt 26 36
66 . Verts_at: 0x358264 520
FIs_at: 0x358484
-------- sig at: 0x358512
vCnt, fCnt 52 90
67 . Verts_at: 0x358674 1040
FIs_at: 0x358a9c
-------- sig at: 0x358ba2
vCnt, fCnt 54 90
68 . Verts_at: 0x358d04 1080
FIs_at: 0x359154
-------- sig at: 0x359252
vCnt, fCnt 118 342
69 . Verts_at: 0x3593b4 2360
FIs_at: 0x359d04
-------- sig at: 0x35a002
vCnt, fCnt 30 114
70 . Verts_at: 0x35a164 600
FIs_at: 0x35a3d4
-------- sig at: 0x35a502
vCnt, fCnt 492 942
71 . Verts_at: 0x35a664 9840
FIs_at: 0x35ccec
-------- sig at: 0x35d4a2
vCnt, fCnt 30 114
72 . Verts_at: 0x35d604 600
FIs_at: 0x35d874
-------- sig at: 0x35d9a2
##vCnt, fCnt 1162 1956
73 . Verts_at: 0x35db04 23240
FIs_at: 0x3635e4
-------- sig at: 0x364572
vCnt, fCnt 56 90
74 . Verts_at: 0x3646d4 1120
FIs_at: 0x364b4c
-------- sig at: 0x364c62
vCnt, fCnt 42 84
75 . Verts_at: 0x364dc4 840
FIs_at: 0x365124
-------- sig at: 0x365212
vCnt, fCnt 30 114
76 . Verts_at: 0x365374 600
FIs_at: 0x3655e4
-------- sig at: 0x365712
vCnt, fCnt 70 330
77 . Verts_at: 0x365874 1400
FIs_at: 0x365e04
-------- sig at: 0x3660e2
vCnt, fCnt 10 24
78 . Verts_at: 0x366244 200
FIs_at: 0x366324
-------- sig at: 0x366832
vCnt, fCnt 24 78
79 . Verts_at: 0x366994 480
FIs_at: 0x366b8c
-------- sig at: 0x366c92
vCnt, fCnt 40 111
80 . Verts_at: 0x366df4 800
FIs_at: 0x36712c
-------- sig at: 0x367272
vCnt, fCnt 12 36
81 . Verts_at: 0x3673d4 240
FIs_at: 0x3674dc
-------- sig at: 0x367582
vCnt, fCnt 30 114
82 . Verts_at: 0x3676e4 600
FIs_at: 0x367954
-------- sig at: 0x367a82
vCnt, fCnt 116 258
83 . Verts_at: 0x367be4 2320
FIs_at: 0x36850c
-------- sig at: 0x368762
vCnt, fCnt 396 666
84 . Verts_at: 0x3688c4 7920
FIs_at: 0x36a7cc
-------- sig at: 0x36d2c2
vCnt, fCnt 4 6
85 . Verts_at: 0x36d424 80
FIs_at: 0x36d48c
-------- sig at: 0x36d4f2
#vCnt, fCnt 514 936
86 . Verts_at: 0x36d654 10280
FIs_at: 0x36fe94
-------- sig at: 0x370622
#vCnt, fCnt 516 936
87 . Verts_at: 0x370784 10320
FIs_at: 0x372fec
-------- sig at: 0x373792
vCnt, fCnt 24 36
88 . Verts_at: 0x3738f4 480
FIs_at: 0x373aec
-------- sig at: 0x373ba2
vCnt, fCnt 148 408
89 . Verts_at: 0x373d04 2960
FIs_at: 0x3748ac
-------- sig at: 0x378502
vCnt, fCnt 290 600
90 . Verts_at: 0x378664 5800
FIs_at: 0x379d24
-------- sig at: 0x37a212
vCnt, fCnt 46 102
91 . Verts_at: 0x37a374 920
FIs_at: 0x37a724
-------- sig at: 0x37a842
vCnt, fCnt 54 132
92 . Verts_at: 0x37a9a4 1080
FIs_at: 0x37adf4
-------- sig at: 0x37f182
vCnt, fCnt 144 480
93 . Verts_at: 0x37f2e4 2880
FIs_at: 0x37fe3c
-------- sig at: 0x380262
vCnt, fCnt 52 216
94 . Verts_at: 0x3803c4 1040
FIs_at: 0x3807ec
-------- sig at: 0x3809f2
vCnt, fCnt 94 186
95 . Verts_at: 0x380b54 1880
FIs_at: 0x3812c4
-------- sig at: 0x381482
vCnt, fCnt 20 48
96 . Verts_at: 0x3815e4 400
FIs_at: 0x38178c
-------- sig at: 0x381842
vCnt, fCnt 66 120
97 . Verts_at: 0x3819a4 1320
FIs_at: 0x381ee4
-------- sig at: 0x382012
vCnt, fCnt 156 354
98 . Verts_at: 0x382174 3120
FIs_at: 0x382dbc
-------- sig at: 0x3830d2
vCnt, fCnt 20 54
99 . Verts_at: 0x383234 400
FIs_at: 0x3833dc
...
```

Start address of FIs usually needs a correction which I didn't apply. That's the reason why I couldn't create all the H2O files automatically. 
.



l_bell_s-xbx-5-models.png (90.75 KiB) Viewed 378 times

(some models seem to be identical)

H2O file for a car:

0xD48434 3417
Vb1
20 12
0xD40074 1685
120000
0x0 255

btw: there's a whole bunch of more models available in case you change the sig to be searched for (in the Noesis script) to:
b'\xA6\x06\x00\x02\x08'
## Post #213
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-07-05T16:37:51+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Looks nice. Thanks
Edit: Btw, what format should the script be so I might get the textures on the model. I used QuickBMS for the game's textures for Bellwood
Edit 2: Shakotay2, i think the 2nd line of a model dataset is missing a "Vb" or "VB"
Edit 3: Looking forward to see if I can get a l_bell_d script for models of Brainstorm and Goop only.
## Post #214
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-05T20:15:29+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

> Reply from lilyampykidYTXeNTaX ↑Tue Jul 06, 2021 12:37 am at Tue Jul 06, 2021 12:37 am
>
> 
Looks nice. Thanks
Edit: Btw, what format should the script be so I might get the textures on the model.I didn't really care for textures in Noesis scripts so far.
You'll have to search through the hundreds of Noesis scripts in this forum to find one where textures are applied, to see how it's done generally.
(Usually strings like setModelMaterials, NoeMaterial or rpgSetMaterial  are contained in such scripts.)

> Edit 2: Shakotay2, i think the 2nd line of a model dataset is missing a "Vb" or "VB"Yeah. No.
It's not complete H2O datasets, it's only counts and addresses as you may have noticed.
That's the reason why a posted an example in my previous post, H2O file for a car:

0xD48434 3417
Vb1
20 12
0xD40074 1685
120000
0x0 255

Also ignore the second parameter here (1320), it's datasize of vertexblock (66*20, vertexcount*FVFsize).
entry 0. Verts_at: 0x309a64 1320
## Post #215
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-07-24T18:34:18+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Hey Shakotay2, can I get help with CHAR_FourArms_WC.et_decomp? 
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1tbuR0_3KjO5_if6tNexO9jXdv3ktx0pe?usp=sharing)
The model in the image is here: 
Does it look like it?
## Post #216
- Username: AlexlexAlex
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 26, 2021 5:47 am
- Post datetime: 2021-07-25T21:49:54+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Ok I didn't get it. How can extract the iso and see the files? I only got the iso and I don't know how to extract them
## Post #217
- Username: jesserf
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 04, 2021 9:03 pm
- Post datetime: 2021-11-12T09:53:52+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

can some one help me to extract models of ben 10 from punch time explotion ps3
## Post #218
- Username: ben10x
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 10, 2022 3:10 pm
- Post datetime: 2022-04-10T07:25:34+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

Just want to say THANKS. This is what I'm searching for long long time
## Post #219
- Username: x03bie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 19, 2022 11:15 am
- Post datetime: 2022-06-19T03:32:37+00:00
- Post Title: Re: How to Get Ben 10 Ultimate Alien: Cosmic Destruction Models

guys is it possible: 
1-to import fourarms to the xbox game or rath to ps3 game?
2- staying in ultimate form mod?
