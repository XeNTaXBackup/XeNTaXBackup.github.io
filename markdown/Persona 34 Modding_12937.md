## Post #1
- Username: ThatTrueStruggle
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 11, 2015 11:36 am
- Post datetime: 2015-06-13T03:18:47+00:00
- Post Title: Persona 3/4 Modding

======================Persona 3/4 Modding======================
(original thread can be found [here](http://www.romhacking.net/forum/index.php/topic,16217.0.html))
Skype chat for it can be found here: 
```
skype:?chat&blob=foNBv1W7iGxjlLfYQKLKeB21Pha9h__ONjzs6gWCEbAEIepliaIeYtYpy2NaKzWKxCGq_T4ZfswU6Q
```

This thread is to gather information known and not known about hacking Persona 3/4. We already have some knowledge on:


Texture Modding
Partial Animation Editing (can reorder and import animations but can't create them)
Mesh Editing
Sound and Music Editing
Editing Text
Editing Sprites
Swapping Models for others


However we do not know how to:


Import custom models
Edit game scripts
Edit animations



If you have any knowledge, Please share with us! Every bit counts! Below I share tutorials on different modding things.
## Post #2
- Username: ThatTrueStruggle
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 11, 2015 11:36 am
- Post datetime: 2015-06-13T03:19:10+00:00
- Post Title: Persona 3/4 Modding

List of relevant programs

TMXViewer - Views and exports TMX files to PNG. Supports BIN, SPR, TMX, EPL (some of them), and CVM (if it has some TMX files in it)
TMXEditor - A leftover TMX editor from Shin Megami Tensei: Nocturne. Can edit and create a TMX from a TGA image. Though it doesn't read from any archive, so you have to extract them using the SPR to TMX extractor.
SPR to TMX extractor - An exporter I wrote for extracting TMX files from SPR and BIN files. requires Python 2.7
TMX to SPR importer - An importer I wrote for importing them TMX files into existing SPR/BIN files. Kinda buggy though (probably going to fix). requires Python 2.7
--------------------------------
RMDEditor - An editor created by OfTheSeventh, development taken over by me. Currently at v1.4.5. It can edit RMD, and PAC files. Supports other formats, though no editing. 
RMDMeshTool - A tool that exports mesh data to obj and reimports it to new mesh data which can be reimported to the RMD
RMDViewer - A viewer for model data in RMD files. Can export model data and textures to .OBJ and .TGA respectively 
RMDMaxScript - A maxscript written by TGE to import RMD, PAC, P00, and FPC files into 3DSMax.
--------------------------------
PersonaInfoViewer - An unfinished text editor that never panned out. Currently can view Persona compendium info, but can't write it
--------------------------------
