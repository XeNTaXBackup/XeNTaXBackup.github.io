## Post #1
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-09-02T08:35:05+00:00
- Post Title: Colin McRae Rally 3 .TAG and track model files

I know there has been research on the later games, but since this one uses a somewhat different format, can anyone look into these so I can convert the tracks, cars and characters to another game?

The archives can be opened and repacked using iRipper; it's the .TAG and .*TAG  models that doesn't appear to be cracked yet.

Auspod.zip (Australia Podium)
[https://www65.zippyshare.com/v/2VuX5CyA/file.html](https://www65.zippyshare.com/v/2VuX5CyA/file.html)

For_focw.zip (Ford Focus WRC?)
[https://www65.zippyshare.com/v/dZDJTvw4/file.html](https://www65.zippyshare.com/v/dZDJTvw4/file.html)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-02T12:17:25+00:00
- Post Title: Colin McRae Rally 3 .TAG and track model files

first submesh, not sure about uvs:



DamWheel-TAG.jpg (189.73 KiB) Viewed 156 times
## Post #3
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-09-02T12:43:35+00:00
- Post Title: Colin McRae Rally 3 .TAG and track model files

How complex is the format though?
## Post #4
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-09-09T00:07:51+00:00
- Post Title: Colin McRae Rally 3 .TAG and track model files

Anyone?
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-09T04:02:51+00:00
- Post Title: Colin McRae Rally 3 .TAG and track model files

The TAG/tag archive format is simple. 
Here's a BMS script to unpack the TAG/tag files:


 tagUnpacker.rar
(443 Bytes) Downloaded 26 times


Do you have problems with the *.big archives?
## Post #6
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-09-09T08:25:09+00:00
- Post Title: Colin McRae Rally 3 .TAG and track model files

> Reply from Bigchillghost
>
> The TAG/tag archive format is simple. 
Here's a BMS script to unpack the TAG/tag files:
The attachment tagUnpacker.rar is no longer available
Do you have problems with the *.big archives?
I don't have an issue with them .BIG files as iRipper can open them anyway. It's the .TAG and related model formats themselves (i.e. .BTAG, .CTAG, .ITAG, .STAG etc.) that are in need of reversing.
[tagfiles.zip](https://xentaxbackup.github.io/file/14826_tagfiles.zip)
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-09T08:46:06+00:00
- Post Title: Colin McRae Rally 3 .TAG and track model files

Some files actually use the same format as the big files even they're with a different extension, like all the files from your Auspod sample.
Just in case it's needed:


 bigfUnpacker.rar
big/bgx/PCX/TBF archives unpacker (409 Bytes) Downloaded 26 times


As for the models, it's really inconvenient to extract them with Hex2obj since they're unpacked as different part, also there's some face format that hex2obj can't deal with. But breaking the archive into smaller separate parts can help you research the format easily.
## Post #8
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-09-09T09:00:46+00:00
- Post Title: Colin McRae Rally 3 .TAG and track model files

> Reply from Bigchillghost
>
> Some files actually use the same format as the big files even they're with a different extension, like all the files from your Auspod sample.
Just in case it's needed:
bigfUnpacker.rar
As for the models, it's really inconvenient to extract them with Hex2obj since they're unpacked as different part, also there's some face format that hex2obj can't deal with. But breaking the archive into smaller separate parts can help you research the format easily.

Did you take a look at the samples I attached? I.e. the .STAG and others? They seem to be similar to the .P3D stuff Michael documented here (at least with the header):
[viewtopic.php?f=16&t=13670&p=143916#p143916](http://forum.xentax.com/viewtopic.php?f=16&t=13670&p=143916#p143916)

EDIT: I've also attached the .CMR mesh files extracted off the Citroen 2CV .big archive here:
[https://www111.zippyshare.com/v/Yftqndj1/file.html](https://www111.zippyshare.com/v/Yftqndj1/file.html)
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-09T09:19:20+00:00
- Post Title: Colin McRae Rally 3 .TAG and track model files

> Reply from huckleberrypie
>
> 
Did you take a look at the samples I attached? I.e. the .STAG and others?
No, I didn't. I just take a quick glance on the big archives and made a compatible unpacker. It's the tag format that interests me. And my research on its geometry format is done.

> Reply from huckleberrypie
>
> They seem to be similar to the .P3D stuff Michael documented here (at least with the header):
Maybe, since they're using the same magic number.
## Post #10
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-09-09T09:59:37+00:00
- Post Title: Colin McRae Rally 3 .TAG and track model files

> Reply from Bigchillghost
>
> huckleberrypie wrote:
Did you take a look at the samples I attached? I.e. the .STAG and others? 
No, I didn't. I just take a quick glance on the big archives and made a compatible unpacker. It's the tag format that interests me. And my research on its geometry format is done.
huckleberrypie wrote:They seem to be similar to the .P3D stuff Michael documented here (at least with the header):
Maybe, since they're using the same magic number.
Hmm, could you walk me through using the importer on that thread if you don't mind?
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-09T10:09:04+00:00
- Post Title: Colin McRae Rally 3 .TAG and track model files

Doesn't work with my Max version. Hadn't you tried that?
## Post #12
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-09-10T08:36:51+00:00
- Post Title: Colin McRae Rally 3 .TAG and track model files

> Reply from Bigchillghost
>
> Doesn't work with my Max version. Hadn't you tried that?
Couldn't seem to get it to work either. :/
## Post #13
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-09-12T09:30:04+00:00
- Post Title: Colin McRae Rally 3 .TAG and track model files

I removed macroscript part. work fine for me
[cmr5_r2018_09_12.zip](https://xentaxbackup.github.io/file/14838_cmr5_r2018_09_12.zip)
## Post #14
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-09-13T06:42:31+00:00
- Post Title: Colin McRae Rally 3 .TAG and track model files

That didn't work either. The file open dialogue shows up but importing the Colin and Nicky .STAG files was to no avail.
## Post #15
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-09-13T11:34:23+00:00
- Post Title: Colin McRae Rally 3 .TAG and track model files

> Reply from huckleberrypie
>
> That didn't work either. The file open dialogue shows up but importing the Colin and Nicky .STAG files was to no avail.I thought it doesn't work for you to open files this script was written for. I didn't added support for CMR3 files.
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-15T16:14:15+00:00
- Post Title: Re: Colin McRae Rally 3 .TAG and track model files

The models are of poor qualities:
[](https://imgur.com/7rtotdY)
and the submeshes would require bone parenting to reach to their correct positions.
It would be a really tedious task to support them so I'll just leave here the structures of the unpacked *.d files resulting from the tag model:

TriMesh (Non-stripped)

```
for (int i = 0; i < MeshCount; i++)
{
	ULONG64	Null;
	long		Vcount;
	long		FaceCount;
	for (int j = 0; j < Vcount; j++)
	{
		float	position[3];
		float	normals[3];
		float	texcoord[2];
		BYTE	 vertexColorRGBA[4];
	}
	for (int j = 0; j < FaceCount; j++)
	{
		long	AlignmentMark;
		long	TriangleIdx[3];
	}
}
```

TriMesh (Stripped)

```
for (int i = 0; i < MeshCount; i++)
{
	ULONG64	Null;
	long	 	Vcount;
	long	 	StrippedGroupCount;
	long	 	ChunkSize; //IndexChunk + VertexChunk + Header
	long	 	IndexChunkAndHeaderSize;
	float		Unknown[6];
	for (int j = 0; j < StrippedGroupCount; j++)
	{
		ULONG64		StrippedIndexCount;
		long			TriangleStrippedIdx[StrippedIndexCount];
	}
	for (int j = 0; j < Vcount; j++)
	{
		float	position[3];
		float	normals[3];
		float	texcoord[2];
		BYTE	 vertexColorRGBA[4];
	}
}
```

MaterialUV/MaterialUVStripped

```
for (int i = 0; i < MeshCount; i++)
{
	long	ChunkSize;
	long	Count;
	long	Vcount;
	long	Unknown[Count];
	for (int j = 0; j < Vcount; j++)
	{
		long	 isMaterialUV; // always == 1
		float	texcoord[2];
	}
}
```

Node

```
for (int i = 0; i < NodeCount; i++)
{
	long	 parentID;
	long	 Unknown1;
	long	 Unknown2;
	char	 NodeName[64];
	long	 NodeID; // Mapping to MeshID. Some nodes share the same ID
	float	Matrix4x4[16];
}
```

You'll also need the code from the tagUnpacker to get a full understand of the entire file structure.
## Post #17
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-09-16T01:38:17+00:00
- Post Title: Re: Colin McRae Rally 3 .TAG and track model files

What about the character models?
## Post #18
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-10-28T09:48:46+00:00
- Post Title: Re: Colin McRae Rally 3 .TAG and track model files

> Reply from huckleberrypie
>
> What about the character models?
Anyone?
