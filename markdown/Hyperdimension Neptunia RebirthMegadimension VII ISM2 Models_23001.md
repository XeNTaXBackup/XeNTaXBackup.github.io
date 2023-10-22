## Post #1
- Username: XenoCHeart
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 14, 2020 1:38 am
- Post datetime: 2020-11-13T17:56:33+00:00
- Post Title: Hyperdimension Neptunia Rebirth/Megadimension VII ISM2 Models

Hello,

So I was able to find a blender script that imports an ISM2 model file into the program, however my problem comes in the search for the reverse. I've been searching for a way to export the modified model into an ISM2 file that the game can run. I'm currently using the PC port of the game on steam and Blender 2.83. I do know about RandomTBush's Maxscripts, however I do not own the program he uses (3D Max). 

Link to the ism2 model importer I found
[http://www.mediafire.com/file/26h3h178p ... 11.7z/file](http://www.mediafire.com/file/26h3h178pdkyj5m/io_import_compile_heart_ism2_20181111.7z/file)

Along with that, the DeviantArt (Yes you heard that correctly) to the page it's on. (It says to use many other programs but that process never worked for me)
[https://www.deviantart.com/wwwhhhoooaaa ... -773078010](https://www.deviantart.com/wwwhhhoooaaammmiii/journal/The-tools-I-use-773078010)

Note: When Importing, you do have to convert TID to PNG and load the textures in. Aside from that, Uvs are already mapped, which is always good.
## Post #2
- Username: nudgenudgenudge
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 06, 2016 11:31 am
- Post datetime: 2020-11-15T00:25:46+00:00
- Post Title: Hyperdimension Neptunia Rebirth/Megadimension VII ISM2 Models

You can't export the ism2 file directly from blender, so export the modified mesh to a text file and load it with another program to modify the ism2 file.

The tools on the linked page are old, so use the ones linked here.
[https://www.deviantart.com/wwwhhhoooaaa ... -853514506](https://www.deviantart.com/wwwhhhoooaaammmiii/journal/New-versions-of-mod-tools-853514506)

Use this to export mesh from blender.
[http://www.mediafire.com/file/aupm9fb8m ... 13.7z/file](http://www.mediafire.com/file/aupm9fb8m8a3wne/io_export_mesh_for_read_ism2_20200713.7z/file)

Use this to reflect the contents of the output text file in the ism2 file.
[http://www.mediafire.com/file/zbln01vr2 ... 28.7z/file](http://www.mediafire.com/file/zbln01vr2hrzx1o/read_ism2_20200828.7z/file)

First, select the modified mesh and execute File-> Export-> Mesh for read_ism2 from the menu to save it to a text file.
For example, output newmesh.cfg.
Don't forget to make all polygons triangular before exporting.

Then open a command prompt and execute the following command.
> read_ism2 002.ism2 -c newmesh.cfg -o new002.ism2

If there are no problems, new002.ism2 will be created reflecting the changed mesh.
You may see a lot of warnings, but most of them can be safely ignored.
## Post #3
- Username: XenoCHeart
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 14, 2020 1:38 am
- Post datetime: 2020-11-15T02:18:15+00:00
- Post Title: Hyperdimension Neptunia Rebirth/Megadimension VII ISM2 Models

Alright! I'll give it a try when I can.
## Post #4
- Username: nudgenudgenudge
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 06, 2016 11:31 am
- Post datetime: 2020-11-25T13:22:09+00:00
- Post Title: Hyperdimension Neptunia Rebirth/Megadimension VII ISM2 Models

I remembered that read_ism2.exe had one annoying limitation.
There is an upper limit to the number of bones (vertex groups in blender) that can be assigned per vertex, and an error will occur if it is exceeded.
For many ism2 files, the limit is four, and some are eight.
So you need to be careful not to exceed this limit when weight painting.
