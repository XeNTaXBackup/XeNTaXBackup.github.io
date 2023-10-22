## Post #1
- Username: Thanyaboi
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 07, 2022 3:27 pm
- Post datetime: 2022-09-12T08:10:19+00:00
- Post Title: Metal Gear Rising: Revengeance .wmb file open problem

Hello,  I need some help about how to open .wmb file 

Yesterday, I extracted .dat file by using PlatinumDat.exe and I got .wmb file.
Then I tried to open .wmb file by using software name 3D gamestudio, but 
an error show up, it’s description said ( for example I used monsoon em01a0.wmb )
“em01a0.wmb Bad format”.



I know it could be complicated, but I appreciate the help.

Additional related issues:

1. In Noesis, How can I install noesis_bayonetta_pc, when I dragged bayonetta_pc folder into plugins, It doesn’t show up
even I deleted the old one.
Plug-in source: [https://github.com/Kerilk/noesis_bayonetta_pc](https://github.com/Kerilk/noesis_bayonetta_pc)

2.How can I combine two meshes wmb format into one mesh
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-12T09:43:10+00:00
- Post Title: Metal Gear Rising: Revengeance .wmb file open problem

> Reply from Thanyaboi ↑Mon Sep 12, 2022 4:10 pm at Mon Sep 12, 2022 4:10 pm
>
> 
Hello,  I need some help about how to open .wmb file 

Yesterday, I extracted .dat file by using PlatinumDat.exe and I got .wmb file.Without said .dat file no one can help.

> 1. In Noesis, How can I install noesis_bayonetta_pcCopy the bayonetta.dll into the plugins folder. (The plugin needs a .dat file to be loaded, btw, not a .wmb.)

> 2.How can I combine two meshes wmb format into one meshWrong question. The correct one is: how can I convert a 3D model into wmb? There's some tedious work required to achieve this. For WMB4 you may start with Kerilk's bayonetta tools (linked here at the bottom):

> Reply from LeoFeroz ↑Thu Sep 08, 2022 11:59 am at Thu Sep 08, 2022 11:59 am
>
> 
Here's the WMB4 header from Kerilk's MBRR.h:

```
	char			id[4]; //WMB4
	unsigned int	u_a;
	unsigned int	vertexFormat;
	unsigned short	u_b;
	short			u_c;
	float			position1[3];
	float			position2[3];
	unsigned int	offsetVertexGroups;
	unsigned int	numVertexGroups;
	unsigned int	offsetBatches;
	unsigned int	numBatches;
	unsigned int	offsetBatchDescription;
	unsigned int	offsetBones;
	unsigned int	numBones;
	unsigned int	offsetBoneIndexTranslateTable;
	unsigned int	sizeBoneIndexTranslateTable;
	unsigned int	offsetBoneSets;
	unsigned int	numBoneSets;
	unsigned int	offsetMaterials;
	unsigned int	numMaterials;
	unsigned int	offsetTextures;
	unsigned int	numTextures;
	unsigned int	offsetMeshes;
	unsigned int	numMeshes;
} MGRRWmbHdr_t;

```
## Post #3
- Username: Thanyaboi
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 07, 2022 3:27 pm
- Post datetime: 2022-09-12T10:29:31+00:00
- Post Title: Metal Gear Rising: Revengeance .wmb file open problem

Thank you! I appreciated your support
