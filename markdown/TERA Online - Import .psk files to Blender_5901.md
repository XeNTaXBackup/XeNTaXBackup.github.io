## Post #1
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-01-24T17:46:05+00:00
- Post Title: TERA Online - Import .psk files to Blender

The Unreal Model Editor will unpack the Tera Online archives, however the .psk files contain in them do not open in most programs. If you use the ActorX import script for 3DS Max, you can import the files, but both 3DObject Converter and the Blender Unreal scene importer error out on these files.

I'm not sure what the problem is with 3D Object Converter, but I've fixed the problem with the Blender import script and have attached a fixed version that will import the TERA Online .psk files. It looks like the scripts assume that every material has at least one texture, but for the TERA online .psk files, that's not usually true. I'm not sure if that means the texture data is stored differently, or what. You do lose the texture in the import, but it's easy enough to re-map the images.

Since this script ships as part of Blender, it's a little tricky getting it to take the new version. It stores a compiled version of the script, so simply re-adding it or replacing the original version won't necessarily cause it to use the changed version. You may have to delete the original version of the script (which is delivered with Blender) and then re-add it using the Add-On interface in user preferences. Alternatively, you can just open this script in a Script window and run it. If you do the latter, it will add a second .psk option to your import menu - just use the new one, which should be the last one in the import menu.

Tested with Blender 2.5 beta 6a.
[io_import_scene_unreal_psk.py.zip](https://xentaxbackup.github.io/file/3841_io_import_scene_unreal_psk.py.zip)
## Post #2
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-02-01T15:24:14+00:00
- Post Title: TERA Online - Import .psk files to Blender

The 3D Object Converter does not support the .psk file format.
