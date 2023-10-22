## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-05T08:35:38+00:00
- Post Title: Final Fantasy Crystal Chronicles: The Crystal Bearers Tool

Tool for previewing/exporting skinned models from the game files. Supports geometry/skinning/materials.

Example exported models






How to use

Unpack
Game files are inside dvdimageA/B. You can unpack them with the bms script included in the download. There are no proper file and folder names. Everything will be prefixed "dir_" or "file_". Characters are mostly in dir_4 and monsters are mostly in dir_8.

Load

FILE: Loads a file_ if it is a valid model file. Most model files will contain multiple models. Change between models using the arrow keys.
Export

NUX: Exports the model to a custom binary format (.nux), intended to be loaded by Noesis. Noesis script for this format : NUX Script
Textures: Exports the textures in PNG format.
Note : Models and textures will be exported into the folder Export.
Download Tool : [https://www.mediafire.com/file/f4wwo2fq ... r.rar/file](https://www.mediafire.com/file/f4wwo2fq2dbl5t9/FFCCViewer.rar/file)
## Post #2
- Username: SwiftStarz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 30, 2022 10:12 am
- Post datetime: 2022-07-30T02:18:54+00:00
- Post Title: Final Fantasy Crystal Chronicles: The Crystal Bearers Tool

Thank you very much for this tool.  This is one of my favorite titles!  I was wondering if you could provide the source for the tool, or talk at all about the file format (extension/magic id, data format, etc), as I was hoping to write a script to extract all the textures from the game (and even just a way to extract the model textures would be very helpful).

I found that there is an [archive format called "FREB"](https://github.com/marco-calautti/FFCBEditor/blob/master/ffcbeditor/codelite/src/cblib/CBFREBArchive.h) but have not been able to find much other information.
## Post #3
- Username: spamzilla
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Sep 01, 2022 4:03 am
- Post datetime: 2022-09-07T21:19:30+00:00
- Post Title: Final Fantasy Crystal Chronicles: The Crystal Bearers Tool

This is a nice program and all but are there any plans to support animation?

Also, I think it should be noted that the .POS files are what you need to specify for the BMS script to dump the .DAT files.
