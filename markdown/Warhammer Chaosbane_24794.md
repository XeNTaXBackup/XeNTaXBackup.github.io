## Post #1
- Username: Meria
- Rank: n00b
- Number of posts: 14
- Joined date: Mon May 17, 2021 9:09 am
- Post datetime: 2021-11-29T00:02:52+00:00
- Post Title: Warhammer Chaosbane

Hello! Has anyone figured out how to extract models from Chaosbane? I can't seem to find information anywhere and I haven't been able to figure it out on my own either. 
Ninjaripper works, but ninjaripper is also a pain in the ass.

Thanks for reading!
## Post #2
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-11-30T09:19:54+00:00
- Post Title: Warhammer Chaosbane

Posting samples would help people that are interested in assisting.
## Post #3
- Username: Meria
- Rank: n00b
- Number of posts: 14
- Joined date: Mon May 17, 2021 9:09 am
- Post datetime: 2021-12-14T14:12:30+00:00
- Post Title: Warhammer Chaosbane

> Reply from dimis9138 ↑Tue Nov 30, 2021 5:19 pm at Tue Nov 30, 2021 5:19 pm
>
> 
Posting samples would help people that are interested in assisting.

Mmmh! Good idea. Samples of what though? I'm not sure what you mean!
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-12-14T19:04:12+00:00
- Post Title: Warhammer Chaosbane

> Reply from Meria ↑Tue Dec 14, 2021 10:12 pm at Tue Dec 14, 2021 10:12 pm
>
> 
Mmmh! Good idea. Samples of what though? I'm not sure what you mean!

From the game.
## Post #5
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2021-12-28T04:35:22+00:00
- Post Title: Warhammer Chaosbane

GOG version does not pack the files.  There are many 2k textures and some very nice creature/scenery designs. PM for samples if interested

Edit:  Textures are just normal .dds files, with color/detail texture and normal map with specular map in alpha channel
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-12-31T16:49:45+00:00
- Post Title: Warhammer Chaosbane

I can extract the 3d geometry datas from the .p3m files, but I don't find the UV datas at all.




Warhammer_Chaosbane_Boots.jpg (66.44 KiB) Viewed 68 times
## Post #7
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-12-31T16:50:42+00:00
- Post Title: Warhammer Chaosbane

Sample .p3m file and its texture file are attached.
[Warhammer_Chaosbane_Boots.zip](https://xentaxbackup.github.io/file/21482_Warhammer_Chaosbane_Boots.zip)
## Post #8
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-12-31T21:07:04+00:00
- Post Title: Warhammer Chaosbane

Looks like the UVs are at offset 0x1a in each vertex stride - first one at 0x89d, also as Signed Shorts.  There's probably some submesh info, as it's all a mess on one mesh.  Oddly, they don't seem to match up with the texture either.
