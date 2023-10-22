## Post #1
- Username: RokkuDayo
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Feb 21, 2018 8:59 pm
- Post datetime: 2019-09-17T17:41:32+00:00
- Post Title: Gun Gun Pixies .BNC / .BTX (Nintendo Switch)

I've been looking on the file formats of the Nintendo Switch release of Gun Gun Pixies and I noticed that the game is using a format really similar to the one found in Danganronpa Another Episode: Despair Girls, but I couldn't get any of the tools available to work of these files, which was expected tbh.

I'll be leaving some samples here if anyone has any clue on how they can be converted into something usable.


Samples: [https://drive.google.com/file/d/1zS4LoX ... sp=sharing](https://drive.google.com/file/d/1zS4LoX-dJbnUnJStCRKRr433wEZ_2qk7/view?usp=sharing)
## Post #2
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2019-09-18T05:00:03+00:00
- Post Title: Gun Gun Pixies .BNC / .BTX (Nintendo Switch)

the BTX texture seems simple to extract... was able to locate mip count and possibly texture format. I'll dig more into it within the next few days.

the BNC is a model format, has skeleton data inside it, but half of the data is compressed?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-31T18:55:03+00:00
- Post Title: Gun Gun Pixies .BNC / .BTX (Nintendo Switch)

After "offzipping" the OBJ_CN_013_ClockA.bnc I'd say there's something in there but what?
.



GGP_whatIsIt.png (203.83 KiB) Viewed 288 times
## Post #4
- Username: RokkuDayo
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Feb 21, 2018 8:59 pm
- Post datetime: 2020-01-01T15:00:20+00:00
- Post Title: Gun Gun Pixies .BNC / .BTX (Nintendo Switch)

> Reply from shakotay2 ↑Wed Jan 01, 2020 2:55 am at Wed Jan 01, 2020 2:55 am
>
> 
After "offzipping" the OBJ_CN_013_ClockA.bnc I'd say there's something in there but what?
.
GGP_whatIsIt.png

That second "image" resembles a face to me, but it must be my imagination.

Again, all I know is that these models are similar to the format found in Danganronpa: Ultra Despair Girls, probably just an updated version.

The files I originally posted here are from the Switch version but recently the game was released on PC, I'll leave them here even though I couldn't find many differences between the files while looking with HxD. And thanks for looking into this, really thought it was long dead.

[https://drive.google.com/open?id=12qGAh ... VRkugPaDLg](https://drive.google.com/open?id=12qGAhaUKQEOVouGoiJO4KuVRkugPaDLg)
## Post #5
- Username: RokkuDayo
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Feb 21, 2018 8:59 pm
- Post datetime: 2020-01-01T15:59:11+00:00
- Post Title: Gun Gun Pixies .BNC / .BTX (Nintendo Switch)

I also found out that we can get the textures by using Scarlet ([https://github.com/xdanieldzd/Scarlet/releases](https://github.com/xdanieldzd/Scarlet/releases)) and dropping the decompressed output into TextureFinder.




Edit: there's a Noesis script for the textures already so there's no point in using this method ([https://zenhax.com/download/file.php?id=7562](https://zenhax.com/download/file.php?id=7562))
## Post #6
- Username: RokkuDayo
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2020-01-01T16:50:37+00:00
- Post Title: Gun Gun Pixies .BNC / .BTX (Nintendo Switch)

> Reply from ArthurLopes ↑Wed Jan 01, 2020 11:00 pm at Wed Jan 01, 2020 11:00 pm
>
> 
That second "image" resembles a face to me, but it must be my imagination.

I see faces in the image too, so it's at the least not only your imagination.
## Post #7
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-01-02T14:20:49+00:00
- Post Title: Gun Gun Pixies .BNC / .BTX (Nintendo Switch)

I remember this format, it was really weird. Anyway I checked the clock bnc. There seems to be 2 compressed chunks in the bnc file. Scarlet can be used to decompress those.

After that I merged the 2 chunks to load it in hex2obj and got the mesh. I will attach the decompressed/merged bnc file.



Still I think it won't be that easy for more complex and skinned models. I remember this format requiring you to transform vertices by the bone positions based on the given bone ids to get a proper mesh. Also vertex weights were weird too.

I might be able to modify my danganronpa plugin to work with this game, but dunno when I will have the time to do it.
[clock_merged.rar](https://xentaxbackup.github.io/file/17272_clock_merged.rar)
## Post #8
- Username: xperiagenerator
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 17, 2014 8:10 pm
- Post datetime: 2021-03-08T11:29:46+00:00
- Post Title: Gun Gun Pixies .BNC / .BTX (Nintendo Switch)

> Reply from akderebur ↑Thu Jan 02, 2020 10:20 pm at Thu Jan 02, 2020 10:20 pm
>
> 
I remember this format, it was really weird. Anyway I checked the clock bnc. There seems to be 2 compressed chunks in the bnc file. Scarlet can be used to decompress those.

After that I merged the 2 chunks to load it in hex2obj and got the mesh. I will attach the decompressed/merged bnc file.

using scarlet on "OBJ_CN_013_ClockA.bnc" i get only 1 decompressed file

how do you get the second chunk to merge?
