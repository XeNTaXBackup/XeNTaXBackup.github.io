## Post #1
- Username: ByronT
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2014 3:58 pm
- Post datetime: 2021-08-31T09:05:41+00:00
- Post Title: Fable 2 EHF GHF Heightmap / Heightfield

Hello and welcome to the Fable 2 .ehf and .ghf heightmap / heightfield dissection thread!

The ultimate purpose of my research is to extract usable data which can be translated into either the Construction Set and/or the Creation Kit for use in a mod for Oblivion and Skyrim.

Apologies in advance if the following contains a lot of extraneous information as I'm very much thinking-out-loud as I try and learn more about these formats.

Below is a link to a sample .ehf from the Brightwood region, apparently a filler map, north of the main region.  This is an educated guess based on the naming conventions of the folders.
I chose this one since it's fairly small (379,058 bytes) and may not contain any extraneous information contained in the maps that are actually traversable by the Hero or his/her adoring NPCs...
Hopefully this is the case.

[https://www.mediafire.com/file/vq7rdeqy ... e.ehf/file](https://www.mediafire.com/file/vq7rdeqyvk0ad54/northfiller_id_e7a5b4be.ehf/file)

So as I understand it, heightmap files are either a 3d mesh with vertices and faces, or a bitmap/raw file with pixels denoting height based on colour information.

This .ehf file also contains texture file information around halfway through so I wonder if this is not strictly a heightmap file but may still contain data that can be exported and used AS a heightmap?

Anyway, I've started to look through the data in Hex Workshop, using my so-far limited skillset to try and find patterns and possible clues.

The first promising area of data starts at 0x22DD7:

```
42 F1 0A 18 43 5E DB E0 44 1E EF 2A 00 00 00 00 
43 C0 00 00 42 4B 26 83 00 00 00 00 43 C0 00 00
42 4B 26 83 00 00 00 00 43 C0 00 00 42 4B 26 83 
00 00 00 00 43 C0 00 00 42 4B 26 83 41 00 00 00 
43 C4 00 00 42 6B 8C FD 41 80 00 00 43 C4 00 00 
42 73 40 E7 41 00 00 00 43 C4 00 00 42 6B 8C FD 
41 00 00 00 43 C8 00 00 42 81 5A 9B 00 00 00 00 
43 17 9E C4 43 57 D7 64 44 20 35 F7 00 00 00 00
43 17 9E C4 43 57 D7 64 44 20 35 F7 00 00 00 00
7F 7F FF FF 7F 7F FF FF 7F 7F FF FF 00 00 00 00 
```


Which appears to be, from my tinkering with the .mdl files, (more to come on that topic!) vertex coordinates, but I could be wrong... Like I said I'm fairly new to this.

This chunk of data comes to an end at 0002ACEB
So approximately 202 160-byte chunks, although the last few repetitions of this structure seem a little different.

A list of 14 texture file names appears at 0002E077 - It's reasonable to assume that most, if not all the data in this .ehf file pertains to texture coords, which is why I have interpreted the above data sample as vertex coordinates as I believe they can be represented in similar ways - again, I apologise for any muddled terminology I use.

There are large chunks of data that I cannot spot a pattern in so far but I am continuing to look.

So I'll post this thread and hopefully someone with more experience can point me in the right direction, for which I'd be very grateful!  Next I will post an example of the .ghf file which more than likely contains the actual height map data.

Additional Info Regarding Fable 2 Landscape Files

I don't know how familiar people are with how Lionhead made Fable 2 but they used a proprietary game engine based heavily on the one used for Fable 1/TLC so the way it handles regions/maps but in very different ways.  In Fable 1 the actual landscape data was stored in a singular .stb file which was referenced by .tng and .lev files for each region/map, heightmap data could be read from the data within the .lev files though (as seen in the Albion Explorer utility.)  Fable 2 seems to have separate, multiple files for each region: 

From the Fable2Mod forum:

> AMA
>
> Related to height field data. "ADMP".
>
> AMM
>
> Related to height field data. "ADMP".
>
> AMR
>
> Related to height field data. "ADMP".
>
> EHF
>
> Related to height field data. "HeightFieldGraphicsFile".
>
> HDB
>
> Related to height field data.
>
> GENV
>
> Contains environment map data.  Link to thread
>
> GHF
>
> Related to height field data. First 4 bytes are 1F8B0808, but I don't think this is header info.
>
> LMP
>
> Might be related to height field data. Same header as the GHF files. The rest looks the same too.
>
> AI_CONFIG
>
> Related to path finding data. XML/plain text.
>
> AIM
>
> Related to path finding data. Kynogon Mesh.
>
> FDL
>
> Related to path finding data. Kynogon FindNearest Data.
>
> PDL
>
> Related to path finding data. Kynogon Spatial graph.
>
> PPD
>
> Related to path finding data.
>
> MIST
>
> Assuming it to determine where mist is.
>
> WATER
>
> Assuming it to determine where water is.
>
> DAT
>
> All named lightprobesdata.dat. Level lighting?
>
> ENGINE_DATA
>
> Not a clue except for the header. "EngineResourceList".
>
> ENGINE_LEVEL
>
> Stores links to other files such as heightmaps and flora models and has instancing data for flora. Link to thread.
>
> HAVOK_SCENARIO
>
> Level physics?
>
> SAVE
>
> XML/plain text. UIDs?
>
> TEXTURE_ATLAS
>
> Guessing that these determine what textures are used where on the maps.
## Post #2
- Username: ByronT
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2014 3:58 pm
- Post datetime: 2021-08-31T09:11:02+00:00
- Post Title: Fable 2 EHF GHF Heightmap / Heightfield

Analysis of .ghf heightfield file

Exhibit A: ch3heightfieldbigfarm_id_bb9cb8d1_1.ghf

[https://www.mediafire.com/file/5fax57vp ... 1.zip/file](https://www.mediafire.com/file/5fax57vp8g06zai/ch3heightfieldbigfarm_id_bb9cb8d1_1.zip/file)

Well this has been more fruitful.

I had a hunch, based on the fact that the ghf file was just a wall of data with no discernible pattern, that some sort of additional compression was going on - (on top of the fact that it was already compressed in TWO .bnk files!)

So I decided to open it with 7zip - and true enough there was another .ghf file inside the file architecture: export360/data/worlds/albion/brightwall/heightfields/ about 4 times larger.

When I looked at the data of this file - it did feature a repeating pattern of 14 bytes throughout the file, with small variances but crucially a pair of integers 769 and 769 which look suspiciously like the dimensions of a heightmap file...

So, I renamed the extracted file as a raw and with the following settings:

Dimensions
Width: 769
Height: 769

Channels
Count: 14
Interleaved: ✓
Depth: 8-bits

Header Size: 20 bytes

This emerged:



Look familiar...?:



It's not perfect so I'll keep tinkering, but as with the models (mdl) this looks like it will work with the TESAnnwyn landscape converter tool.

Next job will be either to create a converter or to manually convert everything - probably not as huge a job as it sounds as there are, maybe 20 at most, discreet levels.
## Post #3
- Username: ByronT
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2014 3:58 pm
- Post datetime: 2021-08-31T09:13:04+00:00
- Post Title: Fable 2 EHF GHF Heightmap / Heightfield

So I've managed to make some headway with these heightmap files so that I am now able to convert most of the .ghf files exported from levels.bnk into usable greyscale images*.

Brightwood (Spring):


This was achieved by renaming the uncompressed .ghf file to a .raw and opening in Photoshop with the settings I mentioned in the last post.

Selecting the Channels tab revealed 3 channels for RGB, in this case the greyscale channel was G, and there followed several other layers which seem to contain texture information and paths, which will probably be useful when creating world and local maps.

I then deleted every channel but the greyscale.  However, this still needed some work.
It seemed that at the midpoint (128)  maybe due to the way the file is structured/endianness(?)/decompression, with high and low points rendered as 0-255 separately:


So all I did here was select the darker portions first, paste to a new layer and lighten them, then darken the lighter portions.  Then I flipped vertically to get the first image in this post.

As you can see, there is still a little glitching at the bottom right but as this is not a traversable part of the Brightwood region, I can fix this either by smoothing in Photoshop before exporting the final .bmp or .raw file, or by smoothing the terrain in the Construction Set/Creation Kit.

Right, on to Fable 3 and the rest of the Fable 2 .mdls I need!

* - Not all of the .ghf files exported from levels.bnk were usable so I went into Hex Workshop and just exported them manually, which has so far worked fine with Westcliff and Wraithmarsh.
