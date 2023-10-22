## Post #1
- Username: SxnnyB
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 25, 2020 4:15 pm
- Post datetime: 2020-12-02T19:02:57+00:00
- Post Title: Updated MAXScript Juiced (2005)

I have picked up development of the Import/Export MAXScript originally made by Martin_SW of r.e.g. forums.

I have fixed aftermarket rims/exhausts import and various other cases of models not importing.

I've also added writing of shadows/neon data, although for now size of projections will have to be adjusted manually in a hex editor after exporting and before repacking.

To enable shadows, on chassis model only, select checkbox for Chassis on export.

Hex values locations for length and width are provided in image. These are found in the last 44 bytes of the chassis file.



Currently still adding features to correct things on export. Expect future updates.

These scripts work on both Acclaim and THQ versions.

I've also adapted the import as a seperate script to import Xbox original models and included it as well.

Models can be found by extracting the .dats with Juiced Archive Ripper. 

*car*.dat is the track/in race version
*car*_ui.dat is the version used for any non race rendering.
Models for aftermarket rims and exhaust can be found in carmesh.dat
Addition models found in mesh.dat

I've also discovered files can be ran externally from the .dat files provided they are named correctly and have associated files and are placed in the correct folders.

For info on this and more please join the Juiced Modding Discord at: [https://discord.gg/pu2jdxR](https://discord.gg/pu2jdxR)

These have been tested up to 3ds Max 2009, they may need adapted for anything above Max 2009. Would love to see these rewritten for blender 2.8 though.


 Juiced Maxscripts 2020.zip
(9.83 KiB) Downloaded 23 times
## Post #2
- Username: SxnnyB
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 25, 2020 4:15 pm
- Post datetime: 2020-12-07T00:21:34+00:00
- Post Title: Updated MAXScript Juiced (2005)

I have found the 4 byte "unknown" section in the vertex data allows deformation, if anyone can help me to implement assigning this value per vertex in the MaxScript it would be much appreciated.

I have a plan for how it should function in ui but not sure how to get there scripting wise.
