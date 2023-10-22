## Post #1
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2014-10-25T19:37:06+00:00
- Post Title: The Guild 2 - model and animations (.nif /. kf)

To get model and animation you need some tools:

[http://niftools.sourceforge.net/wiki/NifSkope](http://niftools.sourceforge.net/wiki/NifSkope)
[http://sourceforge.net/projects/niftool ... x_plugins/](http://sourceforge.net/projects/niftools/files/max_plugins/)

Before importing animation you need prepare keyframe file (.kf) - split animation tacks into separate files (max importer restrictions).
Start NifScope, open .kf and use context menu option "Block->Crop To Branch" on needed animation track, then save new .kf for lather use ... 
In 3ds max on import use original .nif and fixed .kf ... And all be ok ...

P.S. If anyone have simpler workflow or how to deal with "Gamebryo File Format, Version 20.6.0.0" , please post your methods  ...
