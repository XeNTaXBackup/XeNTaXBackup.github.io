## Post #1
- Username: Cdavoy1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 12, 2021 9:49 am
- Post datetime: 2021-02-12T02:17:12+00:00
- Post Title: Panzer Paladin - [.pbn - .zpbn ]

Hello! I'm currently trying to extract the graphics and animations from a game called Panzer Paladin, however the files seem to be in an exclusive format (.pbn, zpbn. ; all the information I found looking for those extensions was related to some web-browser chess game); I have tried using the Game Extractor tools found at the wiki but not dice. (In fact, I can't even upload them here even though they average 4-3 Kb because the extension isn't recognized)
Could anybody help me out with this one?
Thanks a lot in advance
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-12T08:48:13+00:00
- Post Title: Panzer Paladin - [.pbn - .zpbn ]

You could pack samples to ZIP archive and then upload them here or use external services like mega.nz or google drive. 
Can you do that?
## Post #3
- Username: Cdavoy1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 12, 2021 9:49 am
- Post datetime: 2021-02-12T20:42:42+00:00
- Post Title: Panzer Paladin - [.pbn - .zpbn ]

Sure thing, here you go
[http://www.mediafire.com/folder/vnldlpkzr3b58/Content](http://www.mediafire.com/folder/vnldlpkzr3b58/Content)
Thanks for the help.
## Post #4
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-06-17T20:43:51+00:00
- Post Title: Panzer Paladin - [.pbn - .zpbn ]

I was helping a coleague in xentax chat, the new turtle have the same file.
.zpbn

its just a zlib/deflate compression

just use offzip.exe with -a -z -15 name of file, and should the compress all zpbn and zxnb files as well.
## Post #5
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-06-19T11:44:39+00:00
- Post Title: Panzer Paladin - [.pbn - .zpbn ]

The game is built with FNA, a reimplementation of Microsoft's retired .Net (C#/VB.Net) game development framework, XNA. The game has three main asset formats; json, pbn and xnb. As Rabatini said, the "z" file extension prefixed variants of these (zjson, zpbn, zxnb) are the same format, just ZLib compressed.

- Json is json
- XNB is XNA's binary serialization format
- PBN is the game's own binary serialization format

XNB files are "media" such as images, sounds, videos etc. This is where the game's textures are stored albeit in XNA's Texture2D format. There are a number of tools out there already for converting these back to common formats - mostly from the Stardew Valley and Terraria communities which are also XNA based games. [[1]](https://github.com/LeonBlade/xnbcli) [[2]](https://www.zenhax.com/viewtopic.php?t=13383) [[3]](https://stardewvalleywiki.com/Modding:Editing_XNB_files)

PBN files are serialized GameObjects. Each GameObject has it's own serializer class found in ParisSerializers.dll. The format starts with a "7 bit encoded" length-prefixed string (see [BinaryReader.ReadString](https://docs.microsoft.com/en-us/dotnet/api/system.io.binaryreader.readstring?view=net-6.0)) which is the serializer's class name. The game then hands the file to that serializer which in turn creates and populates the target object. Textures and sounds appear to be loaded separately and are linked via "foreign key" ID classes e.g. "SoundID" in the image.

[](https://ibb.co/hCrHtBc)
## Post #6
- Username: HartleySan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 31, 2023 9:13 pm
- Post datetime: 2023-08-31T13:23:56+00:00
- Post Title: Panzer Paladin - [.pbn - .zpbn ]

barncastle, thank you for that detailed response. Very, very helpful.

Currently, I'm trying to convert all the sprites in Teenage Mutant Ninja Turtles: Shredder's Revenge to PNG files, and I can convert the .zxnb files, but I'm running into issues with the .zpbn files.

I'm able to unzip the .zxnb files using the following:

```
offzip -z -15 -a path-to-zxnb-file offzip/packed 0
```


I can then use xnbcli to convert those .xnb files to .png files as follows:

```
xnbcli unpack offzip/packed/00000000.xnb xnbcli/unpacked
```


However, when I try to run offzip on .zpbn files, I get a .dat file instead of a .xnb file, and when I try to run xnbcli on that file, it seems to run without error (literally no output at all), but I don't get a .json or .png file as the output like I do with the .xnb files.

I also tried manually changing the .dat extension to .xnb before running xnbcli on the processed .zpbn files, but it makes no difference.

Any ideas? I tried searching via Google and this forum extensively on how to process .zpbn files, but no luck.
Thank you.
