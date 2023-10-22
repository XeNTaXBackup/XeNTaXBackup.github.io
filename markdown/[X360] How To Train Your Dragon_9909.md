## Post #1
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2012-11-24T22:29:32+00:00
- Post Title: [X360] How To Train Your Dragon

Hello there, I could use a little help with this one. This game appeared here a few times already:

viewtopic.php?f=17&t=4584
viewtopic.php?f=17&t=5751
viewtopic.php?f=17&t=5752
viewtopic.php?f=21&t=5753
viewtopic.php?f=17&t=6320

Obviously, none of them provided more than some very basic information, if at all. The first thread seems to have most information, but some posts are deleted due to violation of the rules, which makes it very hard to follow the conversation. It seems that the meshes are made of triangle strips. But well, I'm trying to bring more light into this.

So this is what I know so far:

Developer is [Étranges Libellules](http://en.wikipedia.org/wiki/Etranges_Libellules). The game engine is apparently called (Xenon) KGame, the original PE file name is "XenonKGame_Tyd.exe" (Xenon is the code name for XBox 360).

File formats:
.KXE - Archive format (K Xenon). They are compressed with gzip and then xbcompress and need to be decompressed in reverse order with xbdecompress and an archive program that supports gzip. Doesn't seem to have a FourCC or FAT but some kind of French string list at the end of a file. Maybe these files don't have a structured file format at all and are rather loadable memory images, which could also explain the different file extensions for each platform.
.RWS - Segmented sound streams. Contains raw PCM data that can be imported in one piece after the header (usually ending with lots of 0xAB + 12 bytes) and the 2020 bytes long null-filled gaps are removed.
.VID - Plain Bink videos. Cutscenes have multiple audio tracks, one sound effect track and one track for each language.

File contents:

```
00GLC.KXE to 06GLC.KXE          Language files. Contain UTF8 strings and some weird data.
LVL001.KXE to LVL007.KXE        Level data. Also seem to contain most of the game resources that is stored redundantly for each level.
                                Each seems to contain an embedded archive with DDS textures and their names near the start of the file.
                                Textures are compressed as DXT1 (diffuse) or DXT4 (normal maps).
00LLC000.KXE to 06LLC007.KXE    Level-specific language files. Probably localized textures.
STR00100.KXE to STR00708.KXE    Unknown. Additional resources for some levels?
STRA0.RWS to STRA103.RWS        Music streams. 16 bit signed, big endian, stereo, 44100Hz.
0_XEN0.RWS to 6_XEN0.RWS        Voice streams. 16 bit signed, little endian, mono, 44100Hz.
XEN_000.VID to XEN_035.VID      Cutscenes and other videos.

```

Dragon code names:

```
========================
dgA    Night Fury
dgB    Gronkle
dgC    Monstrous Nightmare
dgD    Deadly Nadder
dgE    Hideous Zippleback
dgF    Grapple Grounder (referred as Didier in the game files)

```


I'm mostly concentrating on the KXE files and I was able to extract all DDS textures with a crude way by scanning the archive for the DDS header, then moving some bytes back to get the length and file name. Now I would like to get the meshes somehow, but no luck so far. Since I couldn't figure out any form of file table in the format yet, I can't even say which parts of the file belong together, unless they can clearly be identified by a header.

This here is the ominous string list near the end of a file: [http://i.imgur.com/4GZb4.png](http://i.imgur.com/4GZb4.png)

And there's a series of bytes that could be the header for the meshes or its parts:

```
FF FF FF FF CC CC CC CC
```


But I'm really unsure about that and should probably figure out the archive structure first. Someone with experiences with other games from Étranges Libellules could probably help me, in case the format is similar. I can upload some sample files via PM request, I guess that's the preferred way here without getting banned.
