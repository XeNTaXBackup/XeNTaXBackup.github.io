## Post #1
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2018-05-13T18:46:59+00:00
- Post Title: [PC] Tales of Beseria - .dps, .dc5, and .dat files

The files are extracted from the .TLDAT file from a DLC pack, they could possibly be all model files.
[url=https://zenhax.com/download/file.php?mode=view&id=4574]TOB .dps, .dc5, and .dat files.rar[/url]
.dps files are found in TOMDLB_D folder, .dc5 and .dat files are found in TOMDLP_P folder.
The model itself is not the only thing I needed, the bones of the model are inside in one of the file types (.dps, .dc5, and .dat) and when the bones-like files are found, they have to be converted!
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-15T13:29:27+00:00
- Post Title: [PC] Tales of Beseria - .dps, .dc5, and .dat files

I was able to find the model data easily for some of the dat files, but no luck with ".dc5" files.

Here is "00000000000000a3.dat" for example.



For "00000000000000c6.dc5" these should be the correct values, but it doesn't work.



As you can from the ss, the first float is always NaN, and actually the next 2 floats look like uvs. Vertex positions might be somewhere else in the block, but I couldn't find them. The block size isn't that big anyway, so it might be that they are not floats.

I hope someone can help me with this.

Edit : 

I noticed this immediately after posting. For the first dat with 52 bytes blocks, the UVs are right after "FF FF FF FF". In the "dc5" files the blocks start with "FF FF FF FF" and like I said it is probably followed by uvs. 

So it is like the ".dc5" files have blocks that are missing the first 24 bytes. It felt relevant, so I wanted to note this.

Edit 2 : 

Nevermind, I got it working.



The format isn't that hard, but it is troublesome that the model data is scattered across multiple files. I have found the vertex positions/normals in the dpd file, and uvs/indices are in dc5.

Also vertex block lengths are chaotic in dpd files. It started out with 28 bytes, then switched to 32 bytes, and lastly 36 bytes. This is for the vertex blocks of a single object.

Maybe I can write a tool for this, but not many people seem to be interested in this game/series.
## Post #3
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-05-17T02:08:48+00:00
- Post Title: [PC] Tales of Beseria - .dps, .dc5, and .dat files

I'll probably make good use out of a tool that can extract models directly from the game. I already extracted all base models form the game using Ninja Ripper at the time, even rigged up the main cast customly with the help of a third party, though grabbing out the raws would be a definitely nice thing. At the very least I'd support someone doing such a thing.
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-17T08:17:32+00:00
- Post Title: [PC] Tales of Beseria - .dps, .dc5, and .dat files

> Reply from kurokairaku
>
> even rigged up the main cast customly with the help of a third party
That sounds like a lot of work. If I make a tool, I am planning to add skeleton support too.

I have some free time next week. So I will take a look, and might possibly start working on a tool.
## Post #5
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2018-05-25T23:48:59+00:00
- Post Title: [PC] Tales of Beseria - .dps, .dc5, and .dat files

> Reply from akderebur
>
> kurokairaku wrote:even rigged up the main cast customly with the help of a third party
That sounds like a lot of work. If I make a tool, I am planning to add skeleton support too.

I have some free time next week. So I will take a look, and might possibly start working on a tool.
It was been a week, is there any progress on that tool you are working on and the skeleton support?
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-26T08:34:07+00:00
- Post Title: [PC] Tales of Beseria - .dps, .dc5, and .dat files

> Reply from andree
>
> 
It was been a week, is there any progress on that tool you are working on and the skeleton support?
No progress atm. I didn't have the time to start working on a tool. I have been a bit busy and also working on another game.

I don't know when I will make a tool, but ToB is kind of high priority. I will get to it, when I have enough time.
## Post #7
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2018-08-01T22:49:47+00:00
- Post Title: [PC] Tales of Beseria - .dps, .dc5, and .dat files

It has been months waiting for this, and nothing happened
Well, gotta wait for someone to give out support for the bones.
## Post #8
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2018-08-12T23:42:17+00:00
- Post Title: [PC] Tales of Beseria - .dps, .dc5, and .dat files

I think I figured it out. I wrote a noesis script seems to work for the most part (Except everything is mirrored and face morphs don't work). Tales of Berseria Tools ([viewtopic.php?f=33&t=17346](http://forum.xentax.com/viewtopic.php?f=33&t=17346)) can extract Textures with names so that helps a little. Everything else is a mess which makes finding things a pain.

Select a TOMDLB_D and the script will ask you for the corresponding TOMDLP_P which will be the one next to it (Ex: 00003975_11fed272.TOMDLB_D and 00003976_11fe7099.TOMDLP_P are Velvet's Body) the script will then ask you for the TOMDLB_D that contains the Skeleton the model is built off of. This part will be rough if you need one that isn't 00001740_2eb14f7f.TOMDLB_D (That one works with Velvet's stuff) because otherwise you'll have to go datamining in 00001610_dde1b2fa.DAT and start matching model names to skeletons. If you pick the wrong skeleton the script will yell at you. 

I would have liked to streamline this process but this is the best I could come up with.
[fmt_TalesofBerseria_TOMDLP.zip](https://xentaxbackup.github.io/file/14735_fmt_TalesofBerseria_TOMDLP.zip)
## Post #9
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2019-09-15T17:25:50+00:00
- Post Title: [PC] Tales of Beseria - .dps, .dc5, and .dat files

> Reply from Simguy ↑Mon Aug 13, 2018 7:42 am at Mon Aug 13, 2018 7:42 am
>
> 
I think I figured it out. I wrote a noesis script seems to work for the most part (Except everything is mirrored and face morphs don't work). Tales of Berseria Tools (http://forum.xentax.com/viewtopic.php?f=33&t=17346) can extract Textures with names so that helps a little. Everything else is a mess which makes finding things a pain.

Select a TOMDLB_D and the script will ask you for the corresponding TOMDLP_P which will be the one next to it (Ex: 00003975_11fed272.TOMDLB_D and 00003976_11fe7099.TOMDLP_P are Velvet's Body) the script will then ask you for the TOMDLB_D that contains the Skeleton the model is built off of. This part will be rough if you need one that isn't 00001740_2eb14f7f.TOMDLB_D (That one works with Velvet's stuff) because otherwise you'll have to go datamining in 00001610_dde1b2fa.DAT and start matching model names to skeletons. If you pick the wrong skeleton the script will yell at you. 

I would have liked to streamline this process but this is the best I could come up with.
[https://anonymousfiles.io/yZHvcRkf/](https://anonymousfiles.io/yZHvcRkf/)
So, I tried using the script with the model files from Zestiria and it didn't work, Zestiria's model file format is similar to to Berseria's, can you try to add in compatibility with Zestiria's files please, I also included 00003473_dde1b2fa.DAT which I noticed it was similar to Berseria's 00001610_dde1b2fa.DAT.
## Post #10
- Username: Atlus
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 31, 2021 5:52 pm
- Post datetime: 2021-05-21T04:34:45+00:00
- Post Title: [PC] Tales of Beseria - .dps, .dc5, and .dat files

Any update for the tools, cause i can't figure out the correct model data value for the characters in the series between .TOMDLB_D and .TOMDLP_P..
## Post #11
- Username: Atlus
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 31, 2021 5:52 pm
- Post datetime: 2021-05-21T12:26:35+00:00
- Post Title: [PC] Tales of Beseria - .dps, .dc5, and .dat files

Can someone use AstroGrep to grap the character names and the skeleton reference from the model files?
## Post #12
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2022-04-15T07:27:30+00:00
- Post Title: [PC] Tales of Beseria - .dps, .dc5, and .dat files

> Reply from Simguy ↑Mon Aug 13, 2018 7:42 am at Mon Aug 13, 2018 7:42 am
>
> 
I think I figured it out. I wrote a noesis script seems to work for the most part (Except everything is mirrored and face morphs don't work). Tales of Berseria Tools (http://forum.xentax.com/viewtopic.php?f=33&t=17346) can extract Textures with names so that helps a little. Everything else is a mess which makes finding things a pain.

Select a TOMDLB_D and the script will ask you for the corresponding TOMDLP_P which will be the one next to it (Ex: 00003975_11fed272.TOMDLB_D and 00003976_11fe7099.TOMDLP_P are Velvet's Body) the script will then ask you for the TOMDLB_D that contains the Skeleton the model is built off of. This part will be rough if you need one that isn't 00001740_2eb14f7f.TOMDLB_D (That one works with Velvet's stuff) because otherwise you'll have to go datamining in 00001610_dde1b2fa.DAT and start matching model names to skeletons. If you pick the wrong skeleton the script will yell at you. 

I would have liked to streamline this process but this is the best I could come up with.

Thanks for your tool, bro!!
It's been a long time tho, may I ask whether you can modify this script to make it be compatible with Tales of Zesteria's models? If you need any sample to work on I can surely provide!
## Post #13
- Username: iloverdc22
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 21, 2020 2:56 pm
- Post datetime: 2023-02-19T01:01:36+00:00
- Post Title: [PC] Tales of Beseria - .dps, .dc5, and .dat files

> Reply from Simguy ↑Mon Aug 13, 2018 7:42 am at Mon Aug 13, 2018 7:42 am
>
> 
I think I figured it out. I wrote a noesis script seems to work for the most part (Except everything is mirrored and face morphs don't work). Tales of Berseria Tools (http://forum.xentax.com/viewtopic.php?f=33&t=17346) can extract Textures with names so that helps a little. Everything else is a mess which makes finding things a pain.

Select a TOMDLB_D and the script will ask you for the corresponding TOMDLP_P which will be the one next to it (Ex: 00003975_11fed272.TOMDLB_D and 00003976_11fe7099.TOMDLP_P are Velvet's Body) the script will then ask you for the TOMDLB_D that contains the Skeleton the model is built off of. This part will be rough if you need one that isn't 00001740_2eb14f7f.TOMDLB_D (That one works with Velvet's stuff) because otherwise you'll have to go datamining in 00001610_dde1b2fa.DAT and start matching model names to skeletons. If you pick the wrong skeleton the script will yell at you. 

I would have liked to streamline this process but this is the best I could come up with.

sorry for necroing this but i would like to see this work on Zestiria models too. Especially the dlc models.
