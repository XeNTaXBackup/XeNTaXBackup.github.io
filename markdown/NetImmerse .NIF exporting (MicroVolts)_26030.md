## Post #1
- Username: gateaupxs
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 24, 2022 6:19 am
- Post datetime: 2022-11-23T23:37:00+00:00
- Post Title: NetImmerse .NIF exporting (MicroVolts)

The game is MicroVolts Surge (renamed to MicroVolts Recharged) and it's made on GameByro Engine. Same engine as Skyrim Obvlion if I'm not mistaken.

I'm trying to wrap my head around extracting .NIF files. I'm using Norsis 4.6, Nifskope dev10, Blender Nif Plugin, Game Extractor, QuickBMS and I even installed GameByro Engine just to try to extract game files.  So far, QuickBMS was my biggest friend and I manage to extract some .dat files successfully, but I got some problems:

- I can visualize .NIF files, but I found no good way to export to a human format
.NIF models can be previewed using GameByro's AssetViewer and NifSkope, they can also be exported to .OBJ and .FBX using Norsis, but I would say it's not quite there, the UVs are not preserved either, perhaps using another format that can be read by Blender or C4D?

map005 in NifSkope
[](https://ibb.co/yP5C60J)

Blender Nif Import doesn't work for me. I installed latest version of Blender and the latest version of the plugin, all it appears to know about the file it's the general position of the objects, but the mesh itself it's not there.
[](https://ibb.co/s3Cnvt1)

- Found no way to export NiBinaryExtraData
In data/audio/SFX/Instant.nif allegedly has all the one-shot audio files that plays in the game, opening it in AssetViewer give me nothing, but checking in the node proprieties, the files are clearly there:
[](https://imgbb.com/)

Same in NifSkope
[](https://imgbb.com/)

The WAV files are clearly there, but I found no way to get them out of there.
"You can look but you can't touch"

- Conclusion
I have looked through the forum about the exporting MicroVolts .NIFs, but I have reached more far than the only post that exists here about the game. I appreciate any help, here some things I've tried:

Exporting .NIF models to .OBJ:    work, but textures UVs are not preserved, models are rigged to joint/bones
Exporting .NIF models to .FBX:    work, but textures UVs are not correct, can be manually adjusted
Exporiting Instant.nif to .OBJ:     doesn't extract audio files, file size goes from 140MB to 39KB [duh] 
Renaming Instant.nif to Instant.zip:     doesn't work [duh]
Opening Instant.nif with GameExtractor:  doesn't recognize format
Using QuickBMS in Instant.nif:   unsupported compression method 17952
## Post #2
- Username: OGSapphire
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 08, 2023 11:01 pm
- Post datetime: 2023-06-08T15:06:50+00:00
- Post Title: NetImmerse .NIF exporting (MicroVolts)

Hello i saw your post and the Blender addon for nif files is still in work but the newest version of it works really well, just join the discord server if ur version has any problems and you'll most likely get a response

Heres the link [https://drive.google.com/file/d/1DnXDeH ... sp=sharing](https://drive.google.com/file/d/1DnXDeH6t6xTG4RiBRu3bH188ZYY5-C7j/view?usp=sharing)
## Post #3
- Username: MrStreeet
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 13, 2023 12:12 am
- Post datetime: 2023-09-12T16:15:52+00:00
- Post Title: NetImmerse .NIF exporting (MicroVolts)

Which QuickBMS script did you use for extracting the files? I am really lookin into it and nothing works for me
