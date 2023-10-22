## Post #1
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-06-17T20:35:40+00:00
- Post Title: Beyond: Two Souls - Texture Compression (JPEG & DDS)

chrrox found out Beyond probably uses jpeg to encode its textures.
From my ram dump we found out the engine itself uses DDS-DXT, the jpeg encoded textures weren't in the RAM, just the DDS streams.

Getting to the textures themselves is a little bit difficult, you really have to have a whole setup to parse the files.
Thusfar in development of my new tool, I can relatively easy get to the textures I want.

Quick rundown:
- BigFiles, contains concatenated files aligned to 0x800.
- Matching .idx files (encrypted to SDAT on disc versions, EDAT on PSN versions) define content groups, offsets, UIDs, sizes, and eventual extra sizes.
- Decompiling the Lua scripts we can get the linked script functions, characters and catalogs (everything is parsed as a Lua table, characters are empty, a catalog has to be
assigned to them).
- A catalog begins with a main entry, and after that come other archives which contain the mesh data and textures.
- The main entry of the catalogs consist of MESH_DATA, ENGINE_TEXTURE_FILE and other communicators.
- The texture file entries and such function as meta data. Before the actual communicator starts there's first a table with offsets into the other files after the main entry.
- For a texture file this table indexes the mipmaps.

The texture entries:
- Starts with a short header, then a table into what we think are jpeg chunks.
- The table provides offsets, compressed and decompressed sizes.
- The chunks are not compressed using:

ZLIB
LZO
LZMA
Lz
And probably nothing else as there's only references to Edge ZLIB in the executable, and that's not used here.
- When zsize == size the chunks are stored uncompressed as DDS-DXT (this is mostly for chunks < 60 bytes)
- Default decompressed sizes the textures are split up in seem to be mostly 0x6e00 and 0x20000
- The stored textures seem to be in some sort of jpeg format.

chrrox managed to get some part of this supposed jpeg format to show up:



If anyone wants samples I can provide all texture binaries from Jodie's Prologue/Navajo model and a DDS file ripped from the ram dump, just shoot a PM!

Thanks guys,

Hugo
## Post #2
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2014-09-09T08:36:12+00:00
- Post Title: Beyond: Two Souls - Texture Compression (JPEG & DDS)

Hello.

I started working on a QD engine a long time ago but I forced to stop any developments on it from time to time. Recently I continued my work again (especially, while seeing your big progress) and I've tried to catch up with you because I haven't done anything on meshes and textures before this. I've wrote an edge index decompressor and started to work on textures.

I can confirm that a texture compression is done in a custom SPURS module using Huffman/RLE/DCT algorithms which makes it similar to JPEG. There are a lot of commands inside this module, each command describes some steps to produce the final result. Also there is a DXT1/DXT5 encoder, so many commands produces DXT blocks which are DMAed to a RSX memory. There are no tables in textures themselves (JPEG images have them, however many JPEG encoders use standardized tables), but they are embedded in a SPU module. I have a lot of progress with it, for example, I can decompress some textures like Jodie's head texture. Now I need to test other commands and finish the code.
## Post #3
- Username: HugoPeters
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-09-09T08:47:11+00:00
- Post Title: Beyond: Two Souls - Texture Compression (JPEG & DDS)

> Reply from flatz
>
> Hello.

I started working on a QD engine a long time ago but I forced to stop any developments on it from time to time. Recently I continued my work again (especially, while seeing your big progress) and I've tried to catch up with you because I haven't done anything on meshes and textures before this. I've wrote an edge index decompressor and started to work on textures.

I can confirm that a texture compression is done in a custom SPURS module using Huffman/RLE/DCT algorithms which makes it similar to JPEG. There are a lot of commands inside this module, each command describes some steps to produce the final result. Also there is a DXT1/DXT5 encoder, so many commands produces DXT blocks which are DMAed to a RSX memory. There are no tables in textures themselves (JPEG images have them, however many JPEG encoders use standardized tables), but they are embedded in a SPU module. I have a lot of progress with it, for example, I can decompress some textures like Jodie's head texture. Now I need to test other commands and finish the code.

I'll send you a PM about this
