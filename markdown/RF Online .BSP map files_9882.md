## Post #1
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2012-11-16T22:45:38+00:00
- Post Title: RF Online .BSP map files

I  got bored so i looked into the format - and with past experience with old source-code  -  and plugin that finally compiled (for 3dsmax to export ASCII .MAP files), the file extension .BSP  it looks a lot like  source engine (most likely modified).
a example of the .BSP:
[http://www.mediafire.com/?qo12dck8c0eaacl](http://www.mediafire.com/?qo12dck8c0eaacl)


So i digged around in the sourcecode again (well its quite old prealpha or so) and found enough info to put together somewhat usable header for it (for the Structorian tool [http://home.yole.ru/projects/structorian/](http://home.yole.ru/projects/structorian/)).

```

struct Header
{
	u32 BSP_Version;
	
	u32 offset_Cplanes;
	u32 size_Cplanes; 
	
	u32 offset_Cface_id;
	u32 size_Cface_id; 
	
	u32 offset_Node;
	u32 size_Node; 
	
	u32 offset_MatListInLeaf;
	u32 size_MatListInLeaf; 
	
	u32 offset_MatListInLeaf;
	u32 size_MatListInLeaf; 
//Animation-related.

	u32 offset_Object;
	u32 size_Object; 
	
	u32 offset_Track;
	u32 size_Track;
//Collision
	
	u32 offset_CFVertex;
	u32 size_CFVertex; 
	
	u32 offset_CFLine;
	u32 size_CFLine; 
	
	u32 offset_CFLineId;
	u32 size_CFLineId; 

	u32 offset_CFLeaf;
	u32 size_CFLeaf; 
	
	u32 offset_EntityList;
	u32 size_EntityList; 
	
	u32 offset_EntityID;
	u32 size_EntityID; 
	
	u32 offset_LeafEntityList;
	u32 size_LeafEntityList;
	
	u32 offset_SoundEntityID;
	u32 size_SoundEntityID;
	
	u32 offset_LeafSoundEntityList;
	u32 size_LeafSoundEntityList;
	
	u32 offset_EventObjectID;
	u32 size_EventObjectID;
	
repeat 26 {
	u32 offset_ReadSpare;
	u32 size_ReadSpare;
}
	u32 offset_BVertex;
	u32 size_BVertex;
	
	u32 offset_WVertex;
	u32 size_WVertex;
	
	u32 offset_FVertex;
	u32 size_FVertex;
	
	u32 offset_VertexColor;
	u32 size_VertexColor;
	
	u32 offset_UV;
	u32 size_UV;
	
	u32 offset_LgtUV;
	u32 size_LgtUV;
	
	u32 offset_Face;
	u32 size_Face;
	
	u32 offset_FaceId;
	u32 size_FaceId;
	
	u32 offset_VertexId;
	u32 size_VertexId;
	
	u32 offset_MatGroup;
	u32 size_MatGroup;

repeat 32{	
	u32 offset_FreeSpare;
	u32 size_FreeSpare;
}
}
```


Bu ofc the Korean comments are corrupted (someone saved it all in ANSI)

"Lumps are chunks of data, the offsets and lengths (in bytes) of which are defined in the file header, which may also contain the version of the BSP."

As you can see that's what header does, version, and offsets/sizes for data.

[http://www.mediafire.com/?aloq5cizii8scob](http://www.mediafire.com/?aloq5cizii8scob)
here is also source for the 3dsmax map exporter, the "map to bsp tool" and compiled versions. If that helps.
Also what seems to be a kind of "BSP viewer" tho i never got i compiled.
[http://www.mediafire.com/?l4ee9qmmtxxwu8d](http://www.mediafire.com/?l4ee9qmmtxxwu8d)

Perhaps anyone more familiar with the bsp format recognizes it and a minor header edit woudl make it usable in some existing tool?

PS!!! i noticed that the map exporter didnt work with new version.. it was compiled with SDK 9.. so i recompiled it with 3dsmax 2012 SDK 32bit:
[http://www.mediafire.com/?3t45svo8vmdu42m](http://www.mediafire.com/?3t45svo8vmdu42m)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-11-19T14:35:43+00:00
- Post Title: RF Online .BSP map files

not sure i can give any specific help but:

> Reply from djmauro
>
> Bu ofc the Korean comments are corrupted (someone saved it all in ANSI)

you mean localized! you can still change the character encoding in your text editor (or browser) to get the korean comments back
## Post #3
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2012-11-24T21:06:01+00:00
- Post Title: RF Online .BSP map files

Hi, dev of BSPSource here. As far as I can tell, the header is untypical for a Source engine BSP file. It doesn't start with "VBSP", some fields are missing and the structs for each lump have two instead of four fields. It seems to be more similar to the [Quake 2 BSP format](http://www.flipcode.com/archives/Quake_2_BSP_File_Format.shtml), but I also can't find any entity data plain text, which is mandatory for every Quake-based map file. EntityList seems to be empty in your example and points to the end of the file.

It seems very unlikely that these files can be made compatible with tools like BSPSource. But like WRS wrote, you can change the code page of the source files to Windows 949 or EUC-KR and then translate the Korean comments with Google.
