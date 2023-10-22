## Post #1
- Username: goldenboy78
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Nov 23, 2014 9:07 am
- Post datetime: 2015-11-28T22:36:28+00:00
- Post Title: Game of Thrones - dds Android alphachannel different than pc

Hi. I'd like to port the textures with the quotations from the chapter selection screen from PC to Android, to get these also in my language.

But the problem is that alphachannel from Android texture looks like this:



and alphachannel from PC texture looks like this:




If I now use the texture from PC on my Adreno Android device, I get this result :



And that looks weird, because of the different alphachannel..

I wonder if someone experienced similar stuff, porting textures from PC to Android and could give me some advice handling this problem.

The .dds files are exported with RandomTBush's QuickBMS script from here: [viewtopic.php?f=16&t=11687&hilit=telltale+d3dtx](http://forum.xentax.com/viewtopic.php?f=16&t=11687&hilit=telltale+d3dtx)
And here are the graphic sample files, if anyone's interested and want to have a look at it: [GOT_textures.rar](http://www.file-upload.net/download-11080260/GOT_textures.rar.html)

Greetz
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-11-29T09:48:37+00:00
- Post Title: Game of Thrones - dds Android alphachannel different than pc

That's because mobile games typically use three of the following texture compressions: PVR (PowerVR), ETC (Ericsson Texture Compression), or ATC (ATI Texture Compression). DXT compression (the kind PC uses) is typically not used on mobile hardware.

The samples you provided are ATC, but the script exports them with a DXT1 header. To change this, you can open the DDS file in a hex editor (like HxD) and change "DXT1" in the header to "ATIC" then save.



Now you're going to need a tool that opens ATC textures ([The Compressonator](http://developer.amd.com/tools-and-sdks/archive/legacy-cpu-gpu-tools/the-compressonator/) is the only one I know of).

Open the texture in it, make sure "ATI 3Dc Compression" is selected at the top and click Compress.



For textures with alpha channel set the compression options like this:



After the compression is complete you will get the comparison between ATC and DXT (fortunately the recompression doesn't seem to degrade the quality in any instantly noticeable way)
Now go to File > Save Compressed and set the path for your DXT5 texture.
## Post #3
- Username: goldenboy78
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Nov 23, 2014 9:07 am
- Post datetime: 2015-11-30T15:41:04+00:00
- Post Title: Game of Thrones - dds Android alphachannel different than pc

Compressing it to ATCI with The Compressonator dit it. Thanks very much
