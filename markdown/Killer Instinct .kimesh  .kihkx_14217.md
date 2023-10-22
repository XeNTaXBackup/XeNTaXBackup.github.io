## Post #1
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-12T16:22:01+00:00
- Post Title: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #2
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2016-04-12T19:50:49+00:00
- Post Title: Killer Instinct .kimesh / .kihkx

So what is in the zip file? -> ok it is black orchid 

Did you check if the texture has an atlas header?

T.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-12T20:59:42+00:00
- Post Title: Killer Instinct .kimesh / .kihkx

Point cloud of kimesh is promising:



orchid_kimesh.jpg (41.12 KiB) Viewed 954 times
## Post #4
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-04-13T00:58:11+00:00
- Post Title: Killer Instinct .kimesh / .kihkx

You're in luck, kihkx is 100% normal HKX file. 

However, AssetCC gives us this:

```
Binary Packfile has the wrong endiannes or pointer size. Predicates won't be read.
```


This is probably because this game uses some crazy version called hk_2014.2.5-r1, while the only 2014 tools available are hk_2014.1.0-r1.

I can probably mess around with it some more but I'm still busy trying to fix 2011 files from SD.
## Post #5
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-04-13T04:44:04+00:00
- Post Title: Killer Instinct .kimesh / .kihkx

Here is the first sub-mesh (if it helps to understand the format)
[0101.jpg](https://xentaxbackup.github.io/file/10765_0101.jpg)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-13T15:42:39+00:00
- Post Title: Killer Instinct .kimesh / .kihkx

> Reply from luxox18
>
> (if it helps to understand the format)thx - the problem is to find the start of the next submesh.
If you set the face indices count to 2001 you'll see what I mean.
(1848 seems to be the correct value for the first submesh , without misfitting faces)

Dunno if there's a problem with hex2obj, I calculated the next addresses (just leaving the FI count as it was) and it works (one face missing, so 1854 is correct here):



orchid_2nd3rdSM.jpg (162.15 KiB) Viewed 908 times



edit: did the same for the 3rd SM but it's a tedious task.
(There are magic tables with 1842 and 1860, which are -6 and +6 off, so I'm a little bit confused.)
That would mean the FI's startaddress of the 2nd SM to be 0x5028 with a count of 1860.
## Post #7
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-13T19:34:32+00:00
- Post Title: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #8
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-04-14T15:15:59+00:00
- Post Title: Killer Instinct .kimesh / .kihkx

Hi

About orchid.kimesh

```


-- infolist of streams

offset 60	(0, 12048, 0, 16, 22, 185, 0, 0, 528, 0, 0, 0, 225780, 838452, 112890, 46810, 0, 0, 0, 0)
offset 140	(12048, 1496, 0, 16, 4, 19, 0, 0, 1056, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0)
offset 220	(13544, 225780, 35, 16, 1, 0, 0, 0, 1152, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0) - offset+3280+12,size for indice stream
offset 300	(239324, 468100, 40, 128, 1, 0, 0, 0, 1176, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0) - offset+3280+12,size for vertice stream
offset 380	(707424, 370352, 40, 128, 1, 0, 0, 0, 1200, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0) - offset+3280+12,size for skinweighting stream
offset 460	(1077776, 2112, 128, 16, 1, 0, 0, 0, 1224, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0)

-- infolist of meshes

offset 4804	(270816218, 270816218, 0, 0, 1776, 0 - indice ID start from indicestream, 614, 450 - vertex count, 2, 0, 1842 - indice count, 614, 0, 0, 0, 0, 0, 0, 0, 0)
offset 5236	(270816218, 270816218, 0, 0, 1776, 1842, 620, 362, 2, 0, 1860, 620, 0, 0, 0, 0, 0, 0, 0, 0)
offset 5668	(270816218, 270816218, 0, 0, 1776, 3702, 3590, 2316, 2, 0, 10770, 3590, 0, 0, 0, 0, 0, 0, 0, 0)
offset 6100	(270816218, 270816218, 0, 0, 1776, 14472, 7533, 5318, 2, 0, 22599, 7533, 0, 0, 0, 0, 0, 0, 0, 0)
offset 6532	(270816218, 270816218, 0, 0, 1776, 37071, 12, 12, 2, 0, 36, 12, 0, 0, 0, 0, 0, 0, 0, 0)
offset 6964	(270816218, 270816218, 0, 0, 1776, 37107, 13681, 8086, 2, 0, 41043, 13681, 0, 0, 0, 0, 0, 0, 0, 0)
offset 7396	(270816218, 270816218, 0, 0, 1776, 109278, 592, 380, 2, 0, 1776, 592, 0, 0, 0, 0, 0, 0, 0, 0)
offset 7828	(270816218, 270816218, 0, 0, 1584, 78150, 612, 326, 2, 0, 1836, 612, 0, 0, 0, 0, 0, 0, 0, 0)
offset 8260	(270816218, 270816218, 0, 0, 1776, 79986, 5247, 3270, 2, 0, 15741, 5247, 0, 0, 0, 0, 0, 0, 0, 0)
offset 8692	(270816218, 270816218, 0, 0, 1552, 111054, 612, 326, 2, 0, 1836, 612, 0, 0, 0, 0, 0, 0, 0, 0)
offset 9124	(270816218, 270816218, 0, 0, 1776, 95727, 4517, 2559, 2, 0, 13551, 4517, 0, 0, 0, 0, 0, 0, 0, 0)

-- infolist of vertice streams 

offset 14452	(20-stride, 0-first vertex offset in vertex stream, 0, 0, 0, 0, 0, 0, 0, 0, 16, 0, 0, 0, 0, 0, 0, 0, 0, 0)
offset 14532	(20, 9000, 0, 0, 0, 0, 0, 0, 0, 0, 16, 7200, 0, 0, 0, 0, 0, 0, 0, 0)
offset 14612	(20, 16240, 0, 0, 0, 0, 0, 0, 0, 0, 16, 12992, 0, 0, 0, 0, 0, 0, 0, 0)
offset 14692	(20, 62560, 0, 0, 0, 0, 0, 0, 0, 0, 16, 50048, 0, 0, 0, 0, 0, 0, 0, 0)
offset 14772	(20, 168920, 0, 0, 0, 0, 0, 0, 0, 0, 16, 135136, 0, 0, 0, 0, 0, 0, 0, 0)
offset 14852	(20, 169160, 0, 0, 0, 0, 0, 0, 0, 0, 16, 135328, 0, 0, 0, 0, 0, 0, 0, 0)
offset 14932	(20, 453980, 0, 0, 0, 0, 0, 0, 0, 0, 12, 363184, 0, 0, 0, 0, 0, 0, 0, 0)
offset 15012	(20, 330880, 0, 0, 0, 0, 0, 0, 0, 0, 8, 264704, 0, 0, 0, 0, 0, 0, 0, 0)
offset 15092	(20, 337400, 0, 0, 0, 0, 0, 0, 0, 0, 16, 269920, 0, 0, 0, 0, 0, 0, 0, 0)
offset 15172	(20, 461580, 0, 0, 0, 0, 0, 0, 0, 0, 8, 367744, 0, 0, 0, 0, 0, 0, 0, 0)
offset 15252	(20, 402800, 0, 0, 0, 0, 0, 0, 0, 0, 16, 322240, 0, 0, 0, 0, 0, 0, 0, 0)

offset 15332	(0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0)

-- used images and mesh names

offset 15404	characters/orchid/orchid
offset 15429	characters/orchid/blank_orchid_metal
offset 15466	characters/orchid/blank_orchid_skin
offset 15502	characters/orchid/blank_orchid_cloth
offset 15539	characters/orchid/blank_orchid_fullbright
offset 15581	characters/orchid/blank_orchid_eyelashes
offset 15622	characters/orchid/blank_orchid_eye
offset 15657	characters/orchid/retro/orchid_eye_ao_cover
offset 15701	characters/orchid/blank_orchid_face
offset 15737	orchid_mesh_dogtag
offset 15756	__CombinedMesh__
offset 15773	__CombinedMesh__

-- materials ???

offset 15792	(0, 0, 8, 0, 0, 0, 0, 0)
offset 15824	(0, 0, 8, 0, 0, 0, 0, 0)
offset 15856	(0, 0, 8, 0, 0, 0, 0, 0)
offset 15888	(0, 0, 8, 0, 0, 0, 0, 0)
offset 15920	(0, 0, 8, 0, 0, 0, 0, 0)
offset 15952	(0, 0, 8, 0, 0, 0, 0, 0)
offset 15984	(0, 0, 8, 0, 0, 0, 0, 0)
offset 16016	(0, 0, 7, 0, 0, 0, 0, 0)
offset 16048	(0, 0, 8, 0, 0, 0, 0, 0)
offset 16080	(0, 0, 7, 0, 0, 0, 0, 0)
offset 16112	(0, 0, 8, 0, 0, 0, 0, 0)

offset 16144	(0,)

-- which ID image use material ????

offset 16148	(0, 0, 2, 6, 7, 11, 8, 11, 0, 1, 4, 5, 5, 11, 6, 17)
offset 16212	(0, 0, 2, 6, 7, 11, 8, 11, 0, 1, 4, 5, 5, 11, 6, 17)
offset 16276	(0, 0, 2, 6, 7, 11, 8, 11, 0, 1, 4, 5, 5, 11, 6, 17)
offset 16340	(0, 0, 2, 6, 7, 11, 8, 11, 0, 1, 4, 5, 5, 11, 6, 17)
offset 16404	(0, 0, 2, 6, 7, 11, 8, 11, 0, 1, 4, 5, 5, 11, 6, 17)
offset 16468	(0, 0, 2, 6, 7, 11, 8, 11, 0, 1, 4, 5, 5, 11, 6, 17)
offset 16532	(0, 0, 2, 6, 7, 11, 8, 11, 0, 1, 4, 18, 5, 11, 6, 17)
offset 16596	(0, 0, 2, 6, 7, 11, 8, 11, 0, 1, 4, 18, 5, 17)
offset 16652	(0, 0, 2, 6, 7, 11, 8, 11, 0, 1, 4, 5, 5, 11, 6, 17)
offset 16716	(0, 0, 2, 6, 7, 11, 1, 11, 0, 1, 4, 18, 5, 17)
offset 16772	(0, 0, 2, 6, 7, 11, 8, 11, 0, 1, 4, 5, 5, 11, 6, 17)
```

[screen.jpg](https://xentaxbackup.github.io/file/10775_screen.jpg)
## Post #9
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-14T15:50:50+00:00
- Post Title: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #10
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-15T14:04:54+00:00
- Post Title: Killer Instinct .kimesh / .kihkx

Hey Szkaradek123!    I see you made great progress with Killer Instinct, are you going to finish it? I'm thinking to pick this game and try to solve model - import part, though if you're working on it I will pass over, you will do this better than me
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-16T07:17:49+00:00
- Post Title: Killer Instinct .kimesh / .kihkx

> Reply from zaramot
>
> Hey Szkaradek123!    [...] you will do this better than mebetter than everyone, I guess...  

> Reply from shakotay2
>
> Dunno if there's a problem with hex2objnope, it's just relative face indices, so you can't "merge" two adjacent submeshes with hex2obj

But I'm still having a problem with SM7 (..SM10):



orchid_submeshes.jpg (189.02 KiB) Viewed 805 times
## Post #12
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-16T10:24:55+00:00
- Post Title: Killer Instinct .kimesh / .kihkx

Cool, you're missing one array of values for correct vertex-stream offsets. Okay guys, I'm going to finish this one, so please if someone working on it or maybe in a "finish" state for import script/plugin. Write few words here, just don't want to waste some time, if anyone already doing this  I don't mind if anyone pick this up, I might switch to DOOM or any other game xD



File Aria.kimesh
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-16T17:05:21+00:00
- Post Title: Killer Instinct .kimesh / .kihkx

> Reply from zaramot
>
> Cool, you're missing one array of values for correct vertex-stream offsets.yep - I was in the hope to solve it without that vertex info list but for some unknown reason those nasty developer guys mixed the (address) order like this: 0,1,2,3,4,5, 9,6,7,10,8 so I've surrendered the idea of making a tutorial for it because my C code is very ugly now. 



orchid_SM8.jpg (81.71 KiB) Viewed 778 times
## Post #14
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-16T21:43:27+00:00
- Post Title: Killer Instinct .kimesh / .kihkx

Yeah, what a nasty developers   Though, I've met even more crazy things in 3d formats unfortunately, why they not making things easy xD? We just want models!   BTW, I want to ask topic creator for more .kimesh samples, all .kimeshes he provided importing fine with my correct "alpha" script, but I want to try more.

judge.kimesh
## Post #15
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-17T00:12:50+00:00
- Post Title: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #16
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-17T11:53:54+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Okay, thanks a lot for great pack of models. I have tried a lot of them and they imported fine. So, here's my "alpha" script which imports GEOMETRY only, no bones and weights yet, static models - not rigged. I'm going to implement rig soon, though if anyone would like to import and "play" with models a bit here you go xD


[Killer_Instinct_UPD1.7z](https://xentaxbackup.github.io/file/10796_Killer_Instinct_UPD1.7z)
## Post #17
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-18T02:03:11+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #18
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-18T13:03:03+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Here's my beta Noesis plugin for textures .kitex. You could try it out! I've had only textures for character "orchid", so other may not work xD but they should, I hope
## Post #19
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-18T15:52:51+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #20
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-19T03:12:17+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-19T06:27:45+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

UVB size is 24 for Aria:



ariaTex.jpg (203.76 KiB) Viewed 351 times

(2nd submesh)

UVB size is 11th entry in the lines of Mariusz' vertex stream infolist (16 or 8 for orchid.kimesh)

-- infolist of vertice streams 

offset 14452   (20-stride, 0-first vertex offset in vertex stream, 0, 0, 0, 0, 0, 0, 0, 0, 16, 0, 0, 0, 0, 0, 0, 0, 0, 0)
offset 14532   (20, 9000, 0, 0, 0, 0, 0, 0, 0, 0, 16, 7200, 0, 0, 0, 0, 0, 0, 0, 0)
## Post #22
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-19T07:00:33+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Yup, I know about this:) I fixed this in new tiny update, was going to post it later with some tests. Though, if you want those models very bad, you can try it out (I'm looking at the skeleton now) BTW, what about textures there? You able to convert them with Noesis plugin?
[Killer_Instinct_UPD1.7z](https://xentaxbackup.github.io/file/10794_Killer_Instinct_UPD1.7z)
## Post #23
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2016-04-19T10:22:46+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from zaramot
>
> Yup, I know about this:) I fixed this in new tiny update, was going to post it later with some tests. Though, if you want those models very bad, you can try it out (I'm looking at the skeleton now) BTW, what about textures there? You able to convert them with Noesis plugin?
I've noticed that some of the textures for Arbiter's Retro skins are corrupted, most of them being normal maps.
Not sure about the other characters though.
## Post #24
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-19T15:18:13+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #25
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-19T15:48:37+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

P.S. BTW, I wanted to ask you to pack some character's .kihkx, in order to verify my findings
[fmt_Killer_Instinct_KITEX.7z](https://xentaxbackup.github.io/file/10800_fmt_Killer_Instinct_KITEX.7z)
## Post #26
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-19T17:52:25+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #27
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2016-04-20T03:50:45+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from TFA
>
> All character-related HKX files:  https://feen.us/6fub9wjyk75fw4a016y8.zip

Edit:  It seems that in 3ds max 2012, it isn't grabbing all of the submeshes?  Up until now, I've been having a friend send files from their copy of max.  What version should I ideally be using?
I've been using 2015 and 16, and it's grabbed the meshes just fine.
## Post #28
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-20T05:40:37+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from TFA
>
> All character-related HKX files:  https://feen.us/6fub9wjyk75fw4a016y8.zip

Edit:  It seems that in 3ds max 2012, it isn't grabbing all of the submeshes?  Up until now, I've been having a friend send files from their copy of max.  What version should I ideally be using?

Thanks a lot again for great pack of .kihkx:) If everyone could provide such great samples when requested xD I'm using 3ds max 2009-2011, so in those ones everything should work fine for sure

EDIT: Bones and weights are working now, so I think I'm going to share maxscript today, maybe tomorrow.
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-20T11:32:10+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from TFA
>
> Edit:  It seems that in 3ds max 2012, it isn't grabbing all of the submeshes?talking about Sadira's missing head? Couldn't find it so far in the kimesh - it might be in a separate one.
## Post #30
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-20T14:29:12+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #31
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-20T16:28:29+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Well, can't check this ATM, though I don't think something is missing, just those parts are somewhere else. But I will check, anyway as I said script, that YOU have is in "alpha" stage, new one I have differs much from it xD
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-20T19:39:38+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from TFA
>
> shakotay2 wrote: When I try to import Aria myself, none of her limbs are there:  https://feen.us/cyc2usogrem29mfhjykg.png.As for her I can say that's what is in the aria.kimesh.
You can simply check that by using point clouds. From 0x93EDC up to end of file (more or less) there's the uv map.



AriaPtCld.jpg (203.42 KiB) Viewed 313 times
## Post #33
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-20T20:18:48+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #34
- Username: beterthnyu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 21, 2016 12:52 am
- Post datetime: 2016-04-21T14:48:50+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Just to help.

If your character loads in without some pieces, its probably due to the fact that that part is customizable in game. I found that out when I started ripping them into Maya. So that mesh is in another folder, and not included with the character itself.

Don't expect all the pieces to be in one place with this game, its structure is a mess.

I ripped out all of the sounds and converted them to mp3, and they are in pieces the same way.
## Post #35
- Username: Lordryu
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 22, 2016 6:11 am
- Post datetime: 2016-04-21T22:13:43+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

I'm honestly glad there's some work being done on making the best out of these models; I'm hoping for KI models to be released for XNALara and Source Filmmaker for the community.
## Post #36
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-22T17:52:40+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

With Aganos it's a little bit tedious to load all those kimesh files. So I decided to make use of the load multiple files snippet:
(post as of Sun Sep 27, 2015 5:16 pm)
[viewtopic.php?f=13&t=10744](http://forum.xentax.com/viewtopic.php?f=13&t=10744)

Adding it to zaramot's script results in this (maybe not all 80 kimesh should be merged together like such, dunno):



Aganos-multipleKimesh-load.JPG (87.35 KiB) Viewed 234 times
## Post #37
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-22T19:08:45+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

For sure not all, I tried this spooky guy. And a lot of mesh parts are duplicated or better to say mirrored, and I guess there's some kind of customization system in this game? Like some variants of changing appearance? 

BTW, here's script to import KI models with bones, first use script with word "bones", import skeleton of a character and then his models you would like to see xD Important thing, I haven't test it well because Battlefleet Gothic: Armada was released yesterday, and got all my attention   So, test it, and report errors here

P.S. Shakotay, always wanted to ask you about your signature. You're from Microsoft? I mean you're working there?  
[Killer_Instinct.7z](https://xentaxbackup.github.io/file/10820_Killer_Instinct.7z)
## Post #38
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-22T19:39:45+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #39
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-22T19:47:16+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Name of Aria's file? With her messed boots xD 

EDIT: Though, stop - better find more messed models and different errors:) So, I can fix them all at once
## Post #40
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-22T19:50:27+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #41
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-22T20:19:00+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from zaramot
>
> P.S. Shakotay, always wanted to ask you about your signature. You're from Microsoft? I mean you're working there?yep, I was assimilated in their early days just when I wanted to stick to Linux.

MS gave me a duster to push the dust from their lame pcs. Then I managed to escape into an abandoned room still hoping to be freed some day...but, attention, heard some suspicious noise out there - I've to interrupt the connection now!
## Post #42
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-23T04:17:33+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #43
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-23T08:17:28+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

aria_acc01_area_c.kimesh, mesh 1 is correct with zaramot's script -
but for mesh 2 (UVtype: 1648, Wstride: 16) shorts are to be read for the boots.
here's the parameters for mesh 0 (H2Os for mesh 1, mesh 2 below):



AriaBoots.jpg (185.71 KiB) Viewed 181 times


mesh 1, uvs: float

0x16B4 14286
Vb1
20 99
0xBA9C 2922
020000
0x2058C 24

mesh 2, uvs: shorts

0x8650 3052
Vb1
20 99
0x19EE4 1154
020300
0x3177C 16

(I don't have a proper Wstride/UVtype arbitration in my ugly 'C' code, so I have to do the float/WordUV (short) selection manually.)
## Post #44
- Username: Manters
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 23, 2016 2:11 am
- Post datetime: 2016-04-23T10:53:47+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

I've been looking around, and there doesn't seem to be any mention of a way to read .kitex files (Only about them not being renamed .dds files), though I think there is a picture with proof of that. So, how do you read the texture files? (Or am I just so noob I missed it in the conversation?)
## Post #45
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-23T12:23:06+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Read here, post as of Tue Apr 19, 2016 4:48 pm
(It's a python plugin for Noesis so you'll need to copy it into the noesis\plugins\python folder to make it work.)
## Post #46
- Username: Manters
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 23, 2016 2:11 am
- Post datetime: 2016-04-23T14:44:38+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from shakotay2
>
> Read here, post as of Tue Apr 19, 2016 4:48 pm

Can't find a post at the time, and I can't access any links in any posts that Neosis.
## Post #47
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-23T15:01:26+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from Manters
>
> shakotay2 wrote:Read here, post as of Tue Apr 19, 2016 4:48 pm

Can't find a post at the time,you're kidding me, aren't you?  
[viewtopic.php?f=16&t=14217&p=117951&hilit=pack#p117951](http://forum.xentax.com/viewtopic.php?f=16&t=14217&p=117951&hilit=pack#p117951)

> and I can't access any links in any posts that Neosis.
[http://richwhitehouse.com/index.php?con ... sv4177.zip](http://richwhitehouse.com/index.php?content=inc_projects.php&filemirror=noesisv4177.zip)
## Post #48
- Username: Manters
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 23, 2016 2:11 am
- Post datetime: 2016-04-23T17:15:36+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from shakotay2
>
> Manters wrote:
and I can't access any links in any posts that Neosis.
http://richwhitehouse.com/index.php?con ... sv4177.zip

Oh dear... I meant "I can't find any links to a Noesis plugin for kitex in all the posts in this topic" Damn it.
## Post #49
- Username: interloko
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 27, 2009 12:53 am
- Post datetime: 2016-04-23T17:40:41+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Hi guys great progress here!
I haven't tried yet, so I have a question...
How you manage to select the accesories? I mean, there are probably thousands of combination for a single character.
I can make a front end for the customization selection just in case you need it
## Post #50
- Username: Fireseed
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 22, 2016 12:20 pm
- Post datetime: 2016-04-24T08:14:02+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from interloko
>
> Hi guys great progress here!
I haven't tried yet, so I have a question...
How you manage to select the accesories? I mean, there are probably thousands of combination for a single character.
I can make a front end for the customization selection just in case you need it

That would be great however I feel like that would take a lot of time as their is currently no standardized formatting for the various accessory slots. For example on Fulgore his weapons parts are named "Fulgore_Weapon_hitech... Fulgore_Weapon_Military" But on Hisako it's "Hisako_acc01_area_a... Hisako _acc02_area_a"
## Post #51
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-24T14:25:54+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #52
- Username: interloko
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 27, 2009 12:53 am
- Post datetime: 2016-04-24T16:38:57+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

I need to know how the script Works. 
How the files loaded? Just grab all the files from a folder and load them all?
The idea is to make it user friendly. You will see the accesories just as in game and click on it to select
All the names will be stored in external text files
## Post #53
- Username: MisterNatal
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Sep 02, 2014 9:53 am
- Post datetime: 2016-04-25T07:16:06+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Can someone supply me the bone files? trying to port Orchid with the files TFA shared but they don't contain them, only mesh parts
## Post #54
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-25T14:39:58+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #55
- Username: MEGASEAN2812
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 27, 2016 8:15 am
- Post datetime: 2016-04-27T00:47:27+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

I can't open the links you are sending, they show up as question marks. i need the files for judge and retro judge.

To be more specific, i need the texture files for retro judge and judge, im able to open the model files, but i really need the textures and im seemingly unable to open any of the feen.us links
## Post #56
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2016-04-28T00:25:41+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from MEGASEAN2812
>
> I can't open the links you are sending, they show up as question marks. i need the files for judge and retro judge.

To be more specific, i need the texture files for retro judge and judge, im able to open the model files, but i really need the textures and im seemingly unable to open any of the feen.us links

I'm also having this problem. Nothing but a question mark image shows up for me.
## Post #57
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-04-28T14:52:27+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #58
- Username: Lordryu
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 22, 2016 6:11 am
- Post datetime: 2016-04-30T23:36:21+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Any updates, anybody?
## Post #59
- Username: 42tenthlick
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 28, 2016 10:46 am
- Post datetime: 2016-05-01T07:49:53+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Just wanted to say thanks to all those who worked on porting these!  I'm sure someone is already porting these to SFM so everyone can have access to them. 

Made this in Cycles.
## Post #60
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-01T07:57:58+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Great render 42tenthlick! I love it, about updates thanks to TFA who provided detailed report on broken UV's I'm fixing them ATM, after that I think you should get models without big problems, right?
## Post #61
- Username: Lordryu
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 22, 2016 6:11 am
- Post datetime: 2016-05-01T14:55:19+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from 42tenthlick
>
> Just wanted to say thanks to all those who worked on porting these!  I'm sure someone is already porting these to SFM so everyone can have access to them. 

Made this in Cycles.

Looks pretty good so far. Hopefully not long until they're brought into SFM in a mass.
## Post #62
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-05-03T19:19:57+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #63
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-06T10:47:55+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Here's new update, fixed files TFA reported with broken/missing uv's. Try it if anyone interested, lets hope I haven't spoiled uv's in other models - during fixing lol
[Killer_Instinct_UPD1.7z](https://xentaxbackup.github.io/file/10908_Killer_Instinct_UPD1.7z)
## Post #64
- Username: devilblades
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Nov 24, 2015 11:56 pm
- Post datetime: 2016-05-24T19:09:41+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Anyone know where to find Rash in the PAK files?
## Post #65
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2016-05-24T20:37:00+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

For some reason Classic Fulgore is missing his head, hands, and blades after he is imported into 3ds Max with the import script provided here. Any idea why?
## Post #66
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-24T21:28:34+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Script isn't at 100% perfect, maybe it's skipping some parts. Send me this Fulgore, maybe it's a quick fix only xD
## Post #67
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2016-05-25T02:35:39+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Can someone reupload the characters files pls??

Working with xnalara models is a pain in the ass when I have to relayer hair.

Zaramot, your scripts works quiet good in 3ds max 2008.
## Post #68
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2016-05-25T08:50:00+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Link of the game?
## Post #69
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2016-05-25T10:44:16+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from dswd2015
>
> Link of the game?

not really, there was a link with all the meshes of the game some pages behind but it's dead.
## Post #70
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2016-05-25T16:19:23+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Now I understand why I not found link download of this game anywhere.
## Post #71
- Username: filemon204
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 28, 2016 8:03 pm
- Post datetime: 2016-05-28T12:09:15+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Hello xentax friends, I am filemoncio from the Killer Instinct Ultra Combo forums.

Many days have passed since we got news about our beloved game's modding status. We have come here to kindly ask about the status of modding after one of your modders stopped posting in our forum, following a gentle warning from the mods that any kind of modding tutorial was forbidden, and cause of legal action.

We have to come to think that, even if the mods told us that posting images of the models and meshes is allowed, this refrained the modder (Whose name was in "Beterthnyu" our forum) from posting new material.

Can we declare KI modding as dead? We really don't have any other source for KI modding apart from your forum, and specifically this thread. 

Thanks,

Filemoncio
## Post #72
- Username: filemon204
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 28, 2016 8:03 pm
- Post datetime: 2016-06-02T18:15:18+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

anybody?
## Post #73
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2016-06-04T14:01:37+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

dswd2015 if you have Windows 10 go to the Microsoft store and you can download it there for free. Once you get the game it's very easy to extract the kimesh files from the packages. And yes filemoncio KI modding seems to be in it's death throes. Either that or the only characters people seem to be interested in (mainly the XNALara and SFM people) are the female characters, and I think most of us know why.
## Post #74
- Username: jcarl904
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Apr 12, 2010 11:08 pm
- Post datetime: 2016-06-19T12:03:04+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Awesome scripts, thank you guys.
Has anybody figured a way to fix the broken UVs on the broken meshes listed on the first post?
## Post #75
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2016-09-14T13:15:17+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Hey I'm having an issue with this script. I'm running Max 2011. Some of them are still missing UV's. Specifically so far Rash's head has no UV's.

[https://www.dropbox.com/s/y2y5jemu4sjkx6u/Rash.zip?dl=0](https://www.dropbox.com/s/y2y5jemu4sjkx6u/Rash.zip?dl=0)
## Post #76
- Username: Fiorenzone
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 28, 2016 2:42 am
- Post datetime: 2016-11-17T20:06:13+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Tried to apply textures on Arbiter but only  helmet and  face's textures are proper placed on the model, the others are just broken. I would be glad if you could check this out. I'm using 3DS MAX 2016 and Noesis Python plugin for textures.
[Immagine.png](https://xentaxbackup.github.io/file/11927_Immagine.png)
## Post #77
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-11-17T21:28:55+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Don't have his files, upload them here or send in PM
## Post #78
- Username: Fiorenzone
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 28, 2016 2:42 am
- Post datetime: 2016-11-18T15:03:28+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

here you are:  [https://mega.nz/#F!mEdUQCxI!ym7ZbbxO7Mh ... A!XEdziRRD](https://mega.nz/#F!mEdUQCxI!ym7ZbbxO7MhlhV890Dy_vA!XEdziRRD)
 judge.zip is the file I downloaded but now i'm trying other characters to see if the problem persist.

EDIT:ok I figured out how to apply textures on armor but now I see that the arbiter's body has no UV  D: so the result is this
Has TFA already checked arbiter's files? Because if you don't have any problem with them probably files I downloaded from MEGA are broken or something like that. Unfortunately I don't have W10 so I can't extract by myself the files I need.
[Immagine.png](https://xentaxbackup.github.io/file/11933_Immagine.png)
## Post #79
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-12-20T21:43:04+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Did anybody can upload all parts of judge(arbiter) model?
Thank you.
## Post #80
- Username: Fiorenzone
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 28, 2016 2:42 am
- Post datetime: 2016-12-20T22:49:06+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Nope I tried to implement it in Unreal Engine with rig and texture and I Can say the rig is absolutely bugged and unusable for everything. The good news is that if You just need the default model from KI you Can find It here:[https://sfmlab.com/item/1480/](https://sfmlab.com/item/1480/)
It has bones textures and also the weapon s model. 
You Can also search for halo 4's élites 
I tried both of them and I Can say the are good for everything from games to animation  or posing.
If you Need something else Just ask
## Post #81
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-12-21T07:01:19+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

I see. Thanks.
I wonder where this guy pulled out this model.
## Post #82
- Username: Fiorenzone
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 28, 2016 2:42 am
- Post datetime: 2016-12-21T17:36:50+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

This is exactly what I thought about when I saw that, probably he used a private software to extract It.Some time ago I asked about this in facepunch and someone told me that some killer instinct models can't be fully extracted but then  if you search in another thread you find a lot of pics where you see these models rendered and posed so wtf Just download it and enjoy xD
## Post #83
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-12-21T18:19:49+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Hey, I tried Arbiter's files and uv's looks fine, maybe you're suing old script. Anyway, here's the one I used, check it out


[Killer_Instinct_UPD.7z](https://xentaxbackup.github.io/file/12103_Killer_Instinct_UPD.7z)
## Post #84
- Username: Ceekur
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 05, 2017 9:31 pm
- Post datetime: 2017-01-06T11:04:41+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from zaramot
>
> Hey, I tried Arbiter's files and uv's looks fine,]

What is the proper way to apply UV and their textures onto the character and accessory mesh? I'm using Noesis and 3dsMax (and the scripts and resources provided in this thread). The meshes and skeleton import perfectly.
However they are textureless and require me to manually extract those using Noesis first. Also the texture files tend to have all costume variations and pieces mapped out in one file, but the meshes are considered separate objects, so applying the maps as is often off-sets the texture.
It doesn't help that I'm new to 3ds and it's likely deeper than Blender. Am I going about this incorrectly?
## Post #85
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-01-14T14:10:37+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from Nintendude
>
> dswd2015 if you have Windows 10 go to the Microsoft store and you can download it there for free. Once you get the game it's very easy to extract the kimesh files from the packages. And yes filemoncio KI modding seems to be in it's death throes. Either that or the only characters people seem to be interested in (mainly the XNALara and SFM people) are the female characters, and I think most of us know why.

Thank you very much for the information, I'm already downloading the game. Thanks.
## Post #86
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2017-07-29T01:16:10+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

--redacted--
## Post #87
- Username: imarceldoe
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jan 28, 2016 9:55 pm
- Post datetime: 2017-07-31T07:25:55+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from TFA
>
> snip

I have interest in this too, does anybody have any ideas?
## Post #88
- Username: AnimeBlaze
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 29, 2018 1:00 am
- Post datetime: 2018-04-30T15:51:32+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Can somebody fix the import script for the kimesh? 

I want to have rash his head with UVs. script doesn't recognize the head and face uvs.

The rest of the kimesh for that model works fine.
## Post #89
- Username: devilblades
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Nov 24, 2015 11:56 pm
- Post datetime: 2018-09-29T16:57:54+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from AnimeBlaze
>
> Can somebody fix the import script for the kimesh? 

I want to have rash his head with UVs. script doesn't recognize the head and face uvs.

The rest of the kimesh for that model works fine.

Did you ever get Rash's model and the textures?
## Post #90
- Username: devilblades
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Nov 24, 2015 11:56 pm
- Post datetime: 2018-09-30T00:05:54+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from Doctor Loboto
>
> Hey I'm having an issue with this script. I'm running Max 2011. Some of them are still missing UV's. Specifically so far Rash's head has no UV's.

https://www.dropbox.com/s/y2y5jemu4sjkx6u/Rash.zip?dl=0

Any luck with getting the Rash model and textures? I have been trying for a while with no luck.
## Post #91
- Username: jimmyyu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 24, 2019 1:44 am
- Post datetime: 2019-09-23T17:48:54+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Sorry to resurrect this thread, but does anyone have a copy of the original meshpack upload?
## Post #92
- Username: jimmyyu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 24, 2019 1:44 am
- Post datetime: 2019-09-23T17:51:10+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

> Reply from jimmyyu ↑Tue Sep 24, 2019 1:48 am at Tue Sep 24, 2019 1:48 am
>
> 
Sorry to resurrect this thread, but does anyone have a copy of the original meshpack upload?

Nevermind, I just saw the link on the previous page.  Keep up the great work guys!
## Post #93
- Username: Kupo603
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 21, 2021 2:20 am
- Post datetime: 2022-04-03T07:50:04+00:00
- Post Title: Re: Killer Instinct .kimesh / .kihkx

Hello I'm new to modding meshes/textures. I've messed with the kitex files and have made a bunch of cool custom skins in the past but now I wanna get into modding the meshes. How do I go about opening the mesh textures and reimporting them? Which programs do I use also? 

Sorry for all the questions thank you
