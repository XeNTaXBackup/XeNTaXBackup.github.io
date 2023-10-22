## Post #1
- Username: Codeuser
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 30, 2008 1:36 pm
- Post datetime: 2008-07-30T22:52:03+00:00
- Post Title: Star Wars: Republic Commando models

I'm having trouble extracting some models from Star Wars: Republic Commando. I've tried using 3dvia, but that hasn't worked. I've used Game Extractor, but all I got were .pack files and different anims. Various tutorials for the Unreal engine have not worked for this game. Has anybody here successfully converted the models into a format readable by 3ds Max?
## Post #2
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2008-08-13T07:50:54+00:00
- Post Title: Star Wars: Republic Commando models

[out]
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2010-10-04T06:27:37+00:00
- Post Title: Star Wars: Republic Commando models

The newer versions of [Unreal Model Viewer](http://www.gildor.org/en/projects/umodel) can extract the [models, textures and animations etc](http://www.gildor.org/node/101) from the RC game packages. You can use the [ActorXImporter](http://www.gildor.org/projects/unactorx) script to import the models/animations into 3ds Max.

If you don't have 3ds Max then the free [Caligari trueSpace 7.61](http://www.caligari.com/) also has a [psk/psa import/export plugin](http://www.clintons3d.com/truespace/unrealImportExport/index.html) that might import the models/animations too but i have not tried it.
There is also a [psk import script for Blender](http://wiki.blender.org/index.php/Extensions:2.5/Py/Scripts/File_I-O/Unreal_psk_psa) but i think it is not complete. Also see [THIS](http://forums.epicgames.com/showthread.php?t=747452) forum.

EDIT
There is a new psk/psa importer for Blender [HERE](http://forum.xentax.com/viewtopic.php?f=16&t=5868) by Szkaradek123 which works really well.
I attached the script to this post as a backup:


 actorX-Blender249-importer.py.blend.zip
Blender psk/psa Importer (66.99 KiB) Downloaded 29 times



Noesis can also import Unreal *.psk and *.psa files.
