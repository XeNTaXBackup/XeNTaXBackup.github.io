## Post #1
- Username: HardRain
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 11, 2021 12:54 pm
- Post datetime: 2021-08-09T17:24:48+00:00
- Post Title: Resident Evil 4 PS2 .bin models

Hi there, guys.

I am creating a mod game of Resident Evil 4 from PS2 version, and I am trying to edit the 3d models, but I could not find a way to edit the .bin files.
There are some scripts and converters I found, but none of them seems to work with these files. 

There is a tool that can convert them to .obj, but it shows in a very different model (seems like the model lose the bones):
 
- - -
This is the real model in-game:

And also the tool cannot convert it back to .bin


So I am here to ask if someone could help me make a script or converter so I can edit them through 3ds max or blender and repack back to .bin.
Any help will be much appreciated.

Here are some samples:
[https://usaupload.com/file/KNJ/wep06_02.BIN](https://usaupload.com/file/KNJ/wep06_02.BIN) (Magnum)
[https://usaupload.com/file/KNN/wep13_03.BIN](https://usaupload.com/file/KNN/wep13_03.BIN) (Bazooka)
[https://usaupload.com/file/KNI/itm020.bin](https://usaupload.com/file/KNI/itm020.bin) (Ammo box)
[https://usaupload.com/file/KNL/itm006.bin](https://usaupload.com/file/KNL/itm006.bin) (Medicinal Herb)
## Post #2
- Username: HardRain
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 11, 2021 12:54 pm
- Post datetime: 2021-08-22T23:23:41+00:00
- Post Title: Resident Evil 4 PS2 .bin models

Update

In the Resident Evil 4 Ultimate HD edition, the .bin files are also present to do the same work: 3D models.
But a guy with a nickname of SonOfPersia made a .bin tool to extract the 3D models to a .OBJ file, coming also with .SMD and .MTL for the material.
Too bad he isn't active anymore, so I cannot make requests. And also this tool doesn't work with the PS2 .bin models, the sizes of the .bin are very different and the header seems to be different too.

I am a newbie at hex editing, I know only the basics.

This is the output for a .bin file from the UHD version:

Just do a double click on BIN_Extract.bat and it's done.

So I hope someone here can help me with this, by doing something similar and be able to edit and repack the models.

I will put the magnum .bin files here, for both versions of the game and the tool to extract/convert the .bin from the UHD version, so you can compare them and maybe find a solution.
I thank you for your attention.


[https://usaupload.com/file/4CfI/BIN_Tool.rar](https://usaupload.com/file/4CfI/BIN_Tool.rar) BIN tool
[https://usaupload.com/file/4CfH/wep06_03UHD.BIN](https://usaupload.com/file/4CfH/wep06_03UHD.BIN) Magnum 3D model from UHD
[https://usaupload.com/file/4CfG/wep06_03PS2.BIN](https://usaupload.com/file/4CfG/wep06_03PS2.BIN) Magnum 3D model from PS2
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-23T09:05:14+00:00
- Post Title: Resident Evil 4 PS2 .bin models

Usually I don't care for weapons.  

If you're asking for a solution for PS2, the model consists of many small submeshes. You'll need to collect them then fiddle around with auto creation of face indices (Noesis strips seem to work best so far).
.



PS2_ResEvil4_weap.png (31.27 KiB) Viewed 71 times
## Post #4
- Username: HardRain
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 11, 2021 12:54 pm
- Post datetime: 2021-08-23T13:51:25+00:00
- Post Title: Resident Evil 4 PS2 .bin models

Thank you very much for your reply, this will be useful to start identifying XYZ coordinates values.
