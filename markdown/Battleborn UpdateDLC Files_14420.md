## Post #1
- Username: lowlines
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 16, 2011 10:17 pm
- Post datetime: 2016-06-03T04:31:56+00:00
- Post Title: Battleborn Update/DLC Files

So I've been working at extracting data from Battleborn on PC and I have determined that content updates that add new files to the game (ie Alani as a playable character) are being added as encrypted block files.

Note: All files mentioned can be found under /PoplarGame/CookedPCConsole

The TFCManifest.bin (which describes where unique textures are located in TFC files) makes multiple references to a PR__0002 and PR__0003 TFC file.

The RPManifest.bin also references a "GD_WaterMonk_DefaultSkin_SF" upk file which isn't present in the base files.

There are 2 files that start with PR__

```
PR__0003.encr
```


And a bunch of varying sized SR__ prefixed files. Missing sequenced files are possibly localized APK files.

```
English(US)/SR__0002.0001
SR__0002.0003
SR__0002.0004
SR__0002.0005
SR__0002.0006
SR__0002.0007
SR__0002.0008
SR__0002.0009
SR__0002.0010
SR__0002.0011
SR__0002.0012
SR__0002.0013
SR__0002.0014
SR__0002.0015
SR__0002.0016
SR__0002.0017
SR__0002.0018
SR__0002.0019
SR__0002.0020
SR__0002.0021
SR__0002.0022
SR__0002.0065
SR__0002.init00
English(US)/SR__0002.init01
SR__0002.init05
SR__0002.tfc00
SR__0003.0000
English(US)/SR__0003.0001
SR__0003.0003
SR__0003.0004
SR__0003.0005
SR__0003.0006
SR__0003.0007
SR__0003.0008
SR__0003.0009
SR__0003.0010
SR__0003.0011
SR__0003.0012
SR__0003.0013
SR__0003.0014
SR__0003.0015
SR__0003.0016
SR__0003.0017
SR__0003.0018
SR__0003.0019
SR__0003.0020
SR__0003.0021
SR__0003.0022
SR__0003.0023
SR__0003.0024
SR__0003.0025
SR__0003.0026
SR__0003.0027
SR__0003.0028
SR__0003.0029
SR__0003.0030
SR__0003.0031
SR__0003.0032
SR__0003.0033
SR__0003.0034
SR__0003.0035
SR__0003.0036
SR__0003.init00
SR__0003.tfc00
```


I think given the filesizes don't follow a sequenced pattern (ie same filesize until the last file in the sequence) and there are missing part numbers too, these are the actual missing UPK/APK files that have gone through a process that seems to have involved encrypting them. The "init" and "encr" files for both 0002 and 0003 batches are inconsistent sizes too so I'm not sure how to approach figuring out how to extract them. If anyone has any suggestions I'm all ears :/

There is a standard Patch001.tfc file too, which means there's at least 2 different update patterns being implemented in the game.

On another note, DPK files are a custom TFC format that will always have a UPK counterpart and will contain the textures used by it.

```
int32 headerSize,
int32 infoSize,
int32 entryCount,
TArray<infoBlock> infoData,
TArray<extraBlock> extraInfoData,
}
infoData {
int32 texOffset,
int32 checksum?,
int32 compType,
int32 compSize,
int32 uncompSize
}
extraInfoData {
int8 extraOffset, // always 2
int32 unknown, // hash?
int32 unknown2, // always 12
int32 zeroPadding,
int32 unknown3,
int32 unknown4,
int32 unknown5
...
}

```


Grabbing the data found at texOffset will return you the same 0xDD7478BB (.tx.) magic number as the chunks found in TFCs, which are individual texture images prefixed with a header. Not sure how Texture2Ds reference them though so I have to manually match them up after exporting :/

umodel currently crashes when you try to extract files since they might be referencing a custom external file and it seems unlikely that glidor will add support for Battleborn due to its highly customized structure :/
