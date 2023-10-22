## Post #1
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-10T07:19:52+00:00
- Post Title: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

Alright, hello! 

I bet you're all going "oh god, not this again", but hold on, just give me a minute.

As you may know Sleeping Dogs Definitive Edition was released yesterday. It's basically the same game, only with MASSIVELY upgraded visuals, sounds, animations, and with several gameplay changes.

There have already been quite a few tools made for the original Sleeping Dogs, but they only worked half the time, and now they don't work at all. Let me break down all the parts using all the info I got:


ARCHIVES

Sleeping Dogs uses an engine that was custom-built by UFG specifically for this series. All files are compressed into .PERM.BIN/.TEMP.BIN files, which are packed into .BIG archives with a .BIX header.

[Ekey created an unpacker, and was nice enough to quickly update it for Definitive Edition compatibility.](http://forum.xentax.com/viewtopic.php?p=99296#p99296)

When you unpack a .BIG file, you'll end up with "../SleepingDogsDefinitiveEdition/*NameOfBig*/Data/". If you move the Data folder into the main game folder and remove the BIG file, the game will load the unpacked files directly. 

There are some issues with this though. The unpacker doesn't assign filenames to everything, so when the games tries to load the unnamed files it crashes.


SOUNDS

All sounds are stored in Audiokinetc Wwise .PCK and .BNK files. These can be extracted with Ravioli Game Tools.


MESHES

Model vertices, UVs, and weights are stored inside .PERM.BIN files. [Marcius Szkaradek created a Blender script](http://www.mediafire.com/download/d2agot53a31aai2/sdblenderscript_2.zip) that supports all of those, but it has some issues. Full compatibility list:

Characters
Intact mesh, Full UVs, Weights

Vehicles
Slightly scaled mesh, Full UVs, Weights ([decal UVs must be obtained with this modification.](http://www.mediafire.com/download/tbtfnghriull3i5/SDAltVehicleScript.py) Tires have no UVs at all.)

Props/Weapons
Intact mesh, UVs mixed. Some have UVs, some do not.

Buildings
Intact mesh, No UVs.


TEXTURES

.PERM.BIN files can also store textures. The .PERM.BIN file contains the names, and an accompanying .TEMP.BIN file contains the actual image.

[I managed to create an extractor](http://forum.xentax.com/viewtopic.php?f=18&t=12538), but some but be extracted by hand. [See below.](http://forum.xentax.com/viewtopic.php?p=100116#p100116)




BONES

This game uses the Havok Engine, and all the skeletons are stored in one file. Only [Shakotay](http://forum.xentax.com/memberlist.php?mode=viewprofile&u=41194) knows how to extract them.


ANIMATIONS

[The animations are in Havok format as well.](http://forum.xentax.com/viewtopic.php?f=21&t=11155) I've had five people offer to help with these, then promptly get bored and quit or simply ignore me. 

Also, interesting to note they they now use version 2013 instead of the previous 2011.




Most of the work is already done. All that's left is to just make the tools work with these new files.

The good news is, I've looked through files from all of the categories, and they seemed practically identical to the old ones. Only difference is a different header.


Forum rules prohibit posting links in public, so PM me for file samples.
## Post #2
- Username: Theuaredead`
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 10, 2014 9:55 pm
- Post datetime: 2014-10-10T14:01:47+00:00
- Post Title: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

Well apparently you don't have to pay cash to get in anymore, so I'll post regarding the TEMP.BINs and PERM.BINs
The textures above are not done by a hacky method, I used Intel GPA to rip those.

These I got out of a hacky method.





It appears that the TEMP.BINs are compressed the same way as the original Sleeping Dogs, it just seems the code to the PERM.BINs are slightly different so TEXRIPPER can't read them to extract the data.
## Post #3
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-10T14:40:30+00:00
- Post Title: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

> Reply from Theuaredead`
>
> Well apparently you don't have to pay cash to get in anymore, so I'll post regarding the TEMP.BINs and PERM.BINs
The textures above are not done by a hacky method, I used Intel GPA to rip those.

These I got out of a hacky method.
why would you even.. 

just open up the character bins they got textures
## Post #4
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-10T14:48:48+00:00
- Post Title: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

TextureFinder works, but only for the diffuse and specular maps. The normal maps are broken no matter what settings are used.

Also it's worth mentioning they changed the format of the normal maps. They are now just like regular normal maps, only with an inverted blue channel.
## Post #5
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-10T14:54:07+00:00
- Post Title: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

> Reply from SergeantJoe
>
> TextureFinder works, but only for the diffuse and specular maps, the normal maps are broken no matter what settings are used.
they aren't broken msg me a sample ill get it working
## Post #6
- Username: Theuaredead`
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 10, 2014 9:55 pm
- Post datetime: 2014-10-10T15:03:31+00:00
- Post Title: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

Do you want a normal exported VIA texture finder?

> Reply from cra0
>
> why would you even.. 

just open up the character bins they got textures

because its a pain in the ass to splice 2048x2048 and 1024x1024 textures back together with texture finder.
Plus I wanted to see how much of the format was the same.
## Post #7
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-10T15:03:48+00:00
- Post Title: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

there easy

ATI2N now i sleep
## Post #8
- Username: Theuaredead`
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 10, 2014 9:55 pm
- Post datetime: 2014-10-10T15:10:33+00:00
- Post Title: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

> Reply from cra0
>
> there easy

ATI2N now i sleep
now its forever a mystery! 
assuming sergeant joe didnt send cra0 a normal map from Intel GPA just to invert the blue channel
still gonna assume that there's something incorrect with the DXT Header for the normal maps.

oh i guess there's no spoiler tags

edit:
woah, getting some deja vu, alpha channel has apart of normal map. Sadly, I already know that the format probably doesn't do that by default, Intel GPA exports a Source Engine like normal with a inverted blue channel.
## Post #9
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-10T22:14:21+00:00
- Post Title: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

I just sent him a .temp.bin file. 

Also, apparently ATI2N is a type of compression format. I don't know of any programs that support it, so we'll just have to wait until he gets back.
## Post #10
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-11T04:33:26+00:00
- Post Title: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

As noted, the executable's PDB file was included in the game files, and after a conversion to human-readable format courtesy of cra0, I managed to dig up some interesting stuff.

```
enum hkxVertexDescription::DataUsage
{
  HKX_DU_NONE = 0x0,
  HKX_DU_POSITION = 0x1,
  HKX_DU_COLOR = 0x2,
  HKX_DU_NORMAL = 0x4,
  HKX_DU_TANGENT = 0x8,
  HKX_DU_BINORMAL = 0x10,
  HKX_DU_TEXCOORD = 0x20,
  HKX_DU_BLENDWEIGHTS = 0x40,
  HKX_DU_BLENDINDICES = 0x80,
  HKX_DU_USERDATA = 0x100,
};

/* 2854 */
enum hkxMaterial::TextureType
{
  TEX_UNKNOWN = 0x0,
  TEX_DIFFUSE = 0x1,
  TEX_REFLECTION = 0x2,
  TEX_BUMP = 0x3,
  TEX_NORMAL = 0x4,
  TEX_DISPLACEMENT = 0x5,
  TEX_SPECULAR = 0x6,
  TEX_SPECULARANDGLOSS = 0x7,
  TEX_OPACITY = 0x8,
  TEX_EMISSIVE = 0x9,
  TEX_REFRACTION = 0xA,
  TEX_GLOSS = 0xB,
  TEX_DOMINANTS = 0xC,
  TEX_NOTEXPORTED = 0xD,
};

/* 2856 */
enum hkxMaterial::UVMappingAlgorithm
{
  UVMA_SRT = 0x0,
  UVMA_TRS = 0x1,
  UVMA_3DSMAX_STYLE = 0x2,
  UVMA_MAYA_STYLE = 0x3,
};

/* 2859 */
enum hkxVertexDescription::DataType
{
  HKX_DT_NONE = 0x0,
  HKX_DT_UINT8 = 0x1,
  HKX_DT_INT16 = 0x2,
  HKX_DT_UINT32 = 0x3,
  HKX_DT_FLOAT = 0x4,
};

/* 2862 */
enum hkxIndexBuffer::IndexType
{
  INDEX_TYPE_INVALID = 0x0,
  INDEX_TYPE_TRI_LIST = 0x1,
  INDEX_TYPE_TRI_STRIP = 0x2,
  INDEX_TYPE_TRI_FAN = 0x3,
  INDEX_TYPE_MAX_ID = 0x4,
};

/* 2863 */
enum hkxVertexDescription::DataHint
{
  HKX_DH_NONE = 0x0,
  HKX_DH_LIGHTMAP = 0x1,
};

/* 2867 */
enum hkxMaterial::PropertyKey
{
  PROPERTY_MTL_TYPE_BLEND = 0x1,
  PROPERTY_MTL_UV_ID_STAGE0 = 0x100,
  PROPERTY_MTL_UV_ID_STAGE1 = 0x101,
  PROPERTY_MTL_UV_ID_STAGE2 = 0x102,
  PROPERTY_MTL_UV_ID_STAGE3 = 0x103,
  PROPERTY_MTL_UV_ID_STAGE4 = 0x104,
  PROPERTY_MTL_UV_ID_STAGE5 = 0x105,
  PROPERTY_MTL_UV_ID_STAGE6 = 0x106,
  PROPERTY_MTL_UV_ID_STAGE7 = 0x107,
  PROPERTY_MTL_UV_ID_STAGE8 = 0x108,
  PROPERTY_MTL_UV_ID_STAGE9 = 0x109,
  PROPERTY_MTL_UV_ID_STAGE10 = 0x10A,
  PROPERTY_MTL_UV_ID_STAGE11 = 0x10B,
  PROPERTY_MTL_UV_ID_STAGE12 = 0x10C,
  PROPERTY_MTL_UV_ID_STAGE13 = 0x10D,
  PROPERTY_MTL_UV_ID_STAGE14 = 0x10E,
  PROPERTY_MTL_UV_ID_STAGE15 = 0x10F,
  PROPERTY_MTL_UV_ID_STAGE_MAX = 0x110,
};

/* 2868 */
enum hkxMaterial::Transparency
{
  transp_none = 0x0,
  transp_alpha = 0x2,
  transp_additive = 0x3,
  transp_colorkey = 0x4,
  transp_subtractive = 0x9,
};
```


No idea how useful any of this is, but I thought it may be helpful.
## Post #11
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-29T08:07:12+00:00
- Post Title: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

cra0 finally explained how to extract textures!

In order to extract textures from Sleeping Dogs Definitive Edition we basically have to cut the texture bytes out of the .TEMP.BIN file and glue on a proper .DDS header.
It's a bit of a long and obnoxious process though, so bear with me.

You'll need: 
- [TextureFinder](http://web.archive.org/web/20101023115717/http://www.nba2kstuff.org/mua/TextureFinder.v21.zip)
- A hex editor [(I'll be using TinyHexer since it's free and readily available)](http://www.softpedia.com/get/Others/Miscellaneous/tiny-hexer.shtml)
- [WTV](http://www.nvidia.com/object/windows_texture_viewer.html)


1. Open the .temp.bin in TextureFinder and align the texture you want to the top-left corner.



Now, note the Width, Quad Format, and Offset.

For example, this is a 1024x1024 DXT5 texture that starts at offset 1398112.

2. Now that we know where it starts, we need to remove all the extra junk around it.

Open the .temp.bin in a hex editor and go to that offset.




That "ÿ" is where the texture starts. Now, delete everything before that point.




3. Once we've isolated the texture bytes, we now need to attach them to a valid [DDS header](http://puu.sh/cuJ4E/0383acba6a.zip). This is literally as simple as doing Select All, Ctrl-C, Ctrl-V.




Now the tricky part. The information in the header needs to match the format of the texture. There are three importants bits: 

Width


Height


Pitch



There is a lot of incredibly complicated math involved here, so here's a quick cheat sheet for the most common types/sizes.

```
Width/Height       = 02
Pitch (DXT1)       = 02
Pitch (DXT5/ATI2N) = 04

---------1024x1024---------
Width/Height       = 04
Pitch (DXT1)       = 08
Pitch (DXT5/ATI2N) = 10

---------2048x2048---------
Width/Height       = 08
Pitch (DXT1)       = 20
Pitch (DXT5/ATI2N) = 40
```

Make sure the header Width, Height, Pitch, and DXT format match those of the texture.

4. Once everything matches, save the file as .DDS, and you're done!




5. However, this is just the method for diffuse and specular maps.

Set TextureFinder to DXT5, then look for something like this:




This is the normal map. Note the height and offset, then follow the same process, only using the ATI2N header template in the link above.

Pitch calculation is identical to DXT5, so 02 for 512x512 and 10 for 1024x1024.

Only WTV is capable of previewing ATI2N files as far as I know.
## Post #12
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-31T01:41:40+00:00
- Post Title: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

Also, as it turns out, .TEMP.BIN files are just a bunch of plain .DDS files glued together!

Using a slight modification of the above method, it's finally possible to make texture mods for the game!





But only for cutscenes, not the actual gameplay itself.
## Post #13
- Username: Theuaredead`
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 10, 2014 9:55 pm
- Post datetime: 2014-10-31T01:56:19+00:00
- Post Title: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

I feel stupid for not realizing those were DDS data 

edit:

had some fun splicing in my beta Wei Shen remake
## Post #14
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-31T04:36:48+00:00
- Post Title: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

Quick update on the hex values list:

```
Width/Height       = 02
Pitch (DXT1)       = 02
Pitch (DXT5/ATI2N) = 04

---------1024x1024---------
Width/Height       = 04
Pitch (DXT1)       = 08
Pitch (DXT5/ATI2N) = 10

---------2048x2048---------
Width/Height       = 08
Pitch (DXT1)       = 20
Pitch (DXT5/ATI2N) = 40
```


And here's the forumla itself:

```

if (compressionFormat == 1)
{
	pitch *= 1; // Multiply by 1 for DXT1
}
else if (compressionFormat == 5)
{
	pitch *= 2; // Multiply by 2 for DXT5/ATI2N
}
```

This will give you the pitch value, but then you need to convert it to hex. I use a DDS script for 010 Editor.
## Post #15
- Username: Theuaredead`
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 10, 2014 9:55 pm
- Post datetime: 2014-10-31T22:05:22+00:00
- Post Title: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

Appears I found out the resolution header.

The header is about 3 lines after the mention of the name of the texture in the PERM.BIN


That's a 2048x2048 texture with the correct header from the DDS headers, 


Same here, but for the 1024x1024

Now I gotta figure out what tells it to be DXT1 and DXT5
## Post #16
- Username: Theuaredead`
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 10, 2014 9:55 pm
- Post datetime: 2014-11-01T16:02:00+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

2A 7A C6 13 appears to tell the game where the texture is in the TEMP.BIN


C0 AA 02 appears to be the location of the texture aswell (maybe end point?), but it might be to control the texture size,
this is what it does in-game when I edit C0 AA 02


Also, 55 50 might have something to do with the DXT readings, I put it on the head texture to see if any artifacting would happen, but it didn't appear so, I still need to test it on the normal maps to see if something changes, 55 50 appears to be for DXT5, A8 AA appears to be DXT1

EDIT:

Appears the 55 50 and A8 AA don't control the DXTes, Maybe it's in the .TEMP.BIN?
Still gotta look more at the PERM.BIN
## Post #17
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-01-23T22:54:59+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

> Reply from SergeantJoe
>
> In order to extract textures from Sleeping Dogs Definitive Edition we basically have to cut the texture bytes out of the .TEMP.BIN file and glue on a proper .DDS header.
It's a bit of a long and obnoxious process though, so bear with me.
Just a heads up, [I managed to create a program that automates this process](http://forum.xentax.com/viewtopic.php?f=18&t=12538). It's not perfect, but it certainly saves a lot of time.
## Post #18
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-01-28T12:22:58+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

Kinda off/on topic but does anyone have howfie's texture extractor from the original/old Sleeping Dogs because I don't have DE.
## Post #19
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-02-01T10:53:04+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

I already replied to your post on Facepunch but [here's the link again](http://www.mediafire.com/download/c4fffew4uw3d4ed/sdtexextractor.zip) just in case.
## Post #20
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-06-15T10:14:01+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

Gentlemen, today we have been given a gift from the gods themselves. 

Triad Wars, the third installment in the Sleeping Dogs series that's currently in open beta, ships with a tool that can convert textures to .bin format!

It uses the exact same engine as Definitive Edition, and another plus: all the BIG files are split into many parts. So, we can unpack one or more without the game crashing! 

Combine that with this new tool and we finally have the ability to make mods!








I've compared the generated .bin files, and they're EXACTLY the same as DE .bin files, with only a couple bytes difference in the .perm.bin.


However, we cannot pull the same trick with DE, because the BIG files contain a lot more. 

For example, Characters crashes the game when unpacked because of a few buggy unknowns at the beginning of the file. In TW those are in Characters 1.big, so we can safely unpack and modify Characters 2-4.big.
## Post #21
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2015-06-16T16:06:44+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

I am willing to use these tools but might I be able to rquest if  someone could get me the armored car and police bike files. I'll use these tools to do the translating myself. either way thank you all for your time.
## Post #22
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-06-16T21:25:30+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

Sure, no problem. [Here you go.](http://puu.sh/irtV8/1fcf9ccb4b.zip)
## Post #23
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-06-22T02:05:15+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

Definitive Edition compatibility confirmed!






But like I said, we can only edit cutscene models. The regular ones cannot be modified because of those buggy unknowns in Characters.

The good news is, I showed my TW mod to the devs, and they loved it! 
Here's hoping I'm able to persuade them to release a model converter as well. Fingers crossed!
## Post #24
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2015-06-23T00:49:05+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

> Reply from SergeantJoe
>
> Sure, no problem. Here you go.

thanks so much for the help. means a lot.
## Post #25
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2015-12-11T18:18:19+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

> Reply from SergeantJoe
>
> Gentlemen, today we have been given a gift from the gods themselves. 

Triad Wars, the third installment in the Sleeping Dogs series that's currently in open beta, ships with a tool that can convert textures to .bin format!

It uses the exact same engine as Definitive Edition, and another plus: all the BIG files are split into many parts. So, we can unpack one or more without the game crashing! 

Combine that with this new tool and we finally have the ability to make mods!


snip



I've compared the generated .bin files, and they're EXACTLY the same as DE .bin files, with only a couple bytes difference in the .perm.bin.


However, we cannot pull the same trick with DE, because the BIG files contain a lot more. 

For example, Characters crashes the game when unpacked because of a few buggy unknowns at the beginning of the file. In TW those are in Characters 1.big, so we can safely unpack and modify Characters 2-4.big.

hey there, i realize it's been a few months since this thread has seen any action but i was hoping you could help me out. it's about that tool that you're talking about that comes with Triad Wars, the "texturescriberpc64.exe". how do you actually use it? and can it also be used to extract textures from .bin files?

thanks in advance.
## Post #26
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2015-12-12T05:36:06+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

Oh, no problem. This community needs anything and everything we can get.

[Here, I've compiled a convenient download with all you need plus an example.](http://www.mediafire.com/download/5ofn35oz6f68btg/SDTextureWork.zip)

The basic process is this: place the texture files in the root folder, edit the .bat and .xml files (I've commented them) then run the .bat and it should create a Data folder with the new .bin pair inside.
I'm in a hurry right now but I'll write up a much more lengthy explanation when I get back.


> Reply from OriginOfWaves
>
> and can it also be used to extract textures from .bin files?
Sadly no, it only works one way. However, I made a program that can. I've included it in the above download.

Although it's pretty buggy since I'm not a good programmer.
## Post #27
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2015-12-12T13:48:25+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

thanks for the quick response. shame that this tool can't extract textures too. anyways i downloaded your little program and unfortunately i'm having some problems extracting textures. looks like if a .bin file has textures that are smaller then 512x512 the program reports an unsupported size and crashes. maybe you could look into adding support for smaller images, something like 256x256 and 128x128.

And if it's not too much of a problem could you reupload those valid dds headers. i can't seem to get working normal maps out of the .bin files. tried out a few ATI2 headers from some images i have on my HDD but none give me a good result.

Edit: oh and for some reason i can't import a single perm .bin from character and Character HD into blender 2.49 with that script you provided. i'm getting a memory error.
## Post #28
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-10-22T17:27:40+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

> Reply from SergeantJoe
>
> Here, I've compiled a convenient download with all you need plus an example.can you reupload this pls?
## Post #29
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2017-10-29T21:48:52+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

> Reply from Tosyk
>
> can you reupload this pls?
[Here you go!](http://www.mediafire.com/file/zc060c86ur9ekcn/SDTextureConverter.zip)

Just out of curiosity, what are you planning on using it for? After all this time, we still can't really modify anything worthwhile because of the archive unpack problems.
## Post #30
- Username: SilverEvo
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Mar 09, 2019 9:41 am
- Post datetime: 2023-02-15T03:09:14+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

I know I am beating a dead horse with a stick and I apologize for this, but any chance someone keeping the Triad Wars game files?
## Post #31
- Username: dfgsdfgdf13
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 02, 2023 7:02 pm
- Post datetime: 2023-08-02T11:04:46+00:00
- Post Title: Re: [REL/REQ] Sleeping Dogs Part 2: Definitive Edition

Someone is creating mod for it.
[https://www.youtube.com/watch?v=yfj7QFjdbDY](https://www.youtube.com/watch?v=yfj7QFjdbDY)
