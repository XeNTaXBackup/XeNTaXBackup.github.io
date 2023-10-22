## Post #1
- Username: Pandora
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 18, 2015 3:30 am
- Post datetime: 2017-02-03T12:25:18+00:00
- Post Title: Guitar Hero 3 PC - 3D Model Extract for Animation

Hello! I write this in order to ask if there is a way to extract the 3D Models from Guitar Hero 3 for PC with bones, rigging, animation, etc. I already was able to extract only the geometry of a model posed in A-Pose with Ninja Ripper and I posted on DeviantArt:

[http://lindsaypandora.deviantart.com/ar ... -659113226](http://lindsaypandora.deviantart.com/art/Vocalist-3D-Model-Guitar-Hero-3-659113226)


However, I want to know if there is a way to extract the 3D models with bones, rigging, and animations for use in Autodesk Maya 2017.

Of course, the files are packed (and maybe encrypted) in .PAK.XEN format.
The textures are in TEX.XEN format.
There is also a "SKIN.XEN" format.

Since there is a way to extract and edit songs in .FSB.XEN, I wonder if there is a way to decrypt and extract .PAK.XEN files in order to get the game 3D Models with Rig, Bones, Animation, etc.

I attach the files for the Singer (16MB)
[https://drive.google.com/file/d/0B2WPzY ... sp=sharing](https://drive.google.com/file/d/0B2WPzY22ohnYQnNOY3VhVFdzQjA/view?usp=sharing)

I hope you guys and girls can light me up and explain me how to do it. I don't have experience with Hexadecimal Editors or encrypting 

I appreciate your time and thank you in advance for anything ^^

Greetings
## Post #2
- Username: Pandora
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 18, 2015 3:30 am
- Post datetime: 2017-08-13T05:02:33+00:00
- Post Title: Guitar Hero 3 PC - 3D Model Extract for Animation

I have looked for more information, I had come with some things that might be useful to know.

I have read that the [.xen] thing might be a "placeholder" instead of a proper file extension. (Desertman123)

Source:
[http://www.scorehero.com/forum/viewtopi ... 462798a164](http://www.scorehero.com/forum/viewtopic.php?t=57239&sid=64ae8c8c266bad9d995fcc462798a164)

I think I could proof this, since I was messing around with GH Warriors Of Rock for Wii and in fact, the files end up with [.ngc] instead of [.xen]. So, I think that the [.xen] or [.ngc] thing just points out the console of the game. [.xen] would be for PC and Xbox, [.ngc] for Wii, [.ps2] for PS2, [.xbx] for Xbox too, etc.


As MaXkiller says: "The last extension is meaningless, they just represent the system not file format."
Source:
[http://www.scorehero.com/forum/viewtopi ... c&start=15](http://www.scorehero.com/forum/viewtopic.php?t=54009&postdays=0&postorder=asc&start=15)

I kept looking and I found the tool QuickBMS which supports a lot of games to be unpacked. However, I saw that Guitar Hero 3 or Aerosmith (Which uses similar GH3 engine) was not in the list and in the forums, people asked Luigi Aurema to create a script for X or Y games.

Anyone kindly willing to help to get the 3D models with animation or bones or rig from the GH3 from PC, maybe by helping me decrypting the pak.xen files, or maybe creating a script for QuickBMS which can decrypt pak.xen or something like that?

I am so sorry I do not understand much about reverse engineering or programming to talk with difficult words, but if there is something I can do, please tell me, since I have already looked around and I ran out of resources...
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-08-13T19:10:47+00:00
- Post Title: Guitar Hero 3 PC - 3D Model Extract for Animation

> Reply from Pandora
>
> I already was able to extract only the geometry of a model posed in A-Posehow did you get it? (using a 3d ripper?). There's some vertex data in the skin file but they appear to be flat (or uvs).

> Reply from Pandora
>
> Anyone kindly willing to help to get the 3D models with animation or bones or rig from the GH3 from PC,You really should start with the skeletal bones. Any animation is useless without having a skeleton with bones hierarchy
(though sometimes animation files contain the bone names ).

> maybe by helping me decrypting the pak.xen files,dunno what you mean exactly.
From what I see singer_male.skin.xen is just an excerpt from Singer_Male.pak.xen.

Anyways, this is some rough description of the matrix format in the skin file (but not sure whether it's animation frames):

384 frame(?) blocks of different size, the first one has 239 (0xEF) matrix blocks (size 56 bytes each)

start addr, first DWORD is big endian (matrix block) count 
0x30E60 000000EF 02000000 FACEF0 00 FACEF0 01 (16 bytes header)

0x30E70 + 0x3448 (239x56) = 0x342B8

0x342B8 000000 28 09000000 FACEF0 00 FACEF0 01
0x34B88 000000 0D 0A000000 FACEF0 00 FACEF0 01
...
...
end:
0xB4C78 000000 02 6A137000 FACEF0 00 FACEF0 01

The first two matrices:

0.026543 0.054824 -0.756638 
-0.753391 1.021934 -0.068304 
-0.647700 0.650703  0.101329 
0.996157 0.089352 0.094808 
1.000000 0.000000 

0.000175 0.137702 0.989281
-0.026633 1.092723 -0.330542
-0.000278 -0.930762 0.108428 
0.933692 -0.146021 -0.364653 
1.000000 0.000000

---------------------
(there's a count of 1116 at 0x3AEE8, too big for a bone count)
## Post #4
- Username: Pandora
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 18, 2015 3:30 am
- Post datetime: 2017-08-14T19:22:25+00:00
- Post Title: Guitar Hero 3 PC - 3D Model Extract for Animation

Thank you so much to Luigi Aurema for writing a script for QuickBMS to extract PAK.XEN and TEX.XEN files! I really appreciate it so much! 

[https://zenhax.com/viewtopic.php?f=5&t=3758&p=25523](https://zenhax.com/viewtopic.php?f=5&t=3758&p=25523)

I will post what I found and my other concerns ^^

In my first post, I attached 4 files:

Singer_Male.pak.xen
singer_male.skin.xen
singer_male.tex.xen
Singer_Male_Anims.pak.xen

Thanks to the script, I was able to extract 3 of the 4 files.

Singer_Male.pak.xen
singer_male.tex.xen
Singer_Male_Anims.pak.xen

The file "singer_male.skin.xen" returns the following error in QuickBMS.

```
Filesize: 4205492938
Filename: 000b4cd8
Error:

Incomplete input file C:\singer_male.skin.xen
Can't read 64 bytes from offset faabaca.
Anyway, don't worry, it's possible that the BMS script has been written
to exit in this way if it's reached the end of the archive so check it
or contact its author or verify that all the files have been extracted.
Please, check the following coverage information to know if it's OK.

Coverage file:
file 0 0% 36 740616 . offset faabaca

Last script line before the error or that produced the error:
48 log NAME OFFSET SIZE
```


I found this inside the following files using QuickBMS:

Singer_Male.pak.xen

```
Contains: 4 folders (5.428.818 bytes)
```


1º Folder's Name: 2cb3ef3b

```
0000000d.dat (4 bytes)

```


2º Folder's Name: 8bfa5e8e

```
Subfolder: 00002000

Subfolder 00002000 contains 11 DDS files (4.688.000 bytes):
0000000a.dds (1.398.240 bytes) [Normal Body DDS Texture]
0000000b.dds (11.056 bytes) [Specular Eyes DDS Texture]
00000001.dds (1.398.240 bytes) [Diffuse Body DDS Texture]
00000002.dds (174.896 bytes) [Specular Hair DDS Texture]
00000003.dds (699.184 bytes) [Diffuse Hair DDS Texture]
00000004.dds (816 bytes) [Diffuse Unknown DDS Texture]
00000005.dds (21.984 bytes) [Normal Eyes DDS Texture]
00000006.dds (174.896 bytes) [Normal Hair DDS Texture]
00000007.dds (699.184 bytes) [Specular Body DDS Texture]
00000008.dds (21.984 bytes) [Diffuse Eyes DDS Texture]
00000009.dds (87.520 bytes) [Diffuse Tatoo DDS Texture]
```


3º Folder's Name: 64112e85

```
0000000c.dat (740.616 bytes) [Presumably 3D Information?]
```


4º Folder's Name: a7f505c4

```
00000000.dat (198 bytes)
```

singer_male.tex.xen

```
00000000.dds (1.398.240 bytes) [Diffuse Body DDS Texture]
0000000a.dds (11.056 bytes) [Specular Eyes DDS Texture]
00000001.dds (174.896 bytes) [Specular Hair DDS Texture]
00000002.dds (699.184 bytes) [Diffuse Hair DDS Texture]
00000003.dds (816 bytes) [Diffuse Unknown DDS Texture]
00000004.dds (21.984 bytes) [Normal Eyes DDS Texture]
00000005.dds (174.896 bytes) [Normal Hair DDS Texture]
00000006.dds (699.184 bytes) [Specular Body DDS Texture]
00000007.dds (21.984 bytes) [Diffuse Eyes DDS Texture]
00000008.dds (87.520 bytes) [Diffuse Tatoo DDS Texture]
00000009.dds (1.398.240 bytes) [Normal Body DDS Texture]
```

Singer_Male_Anims.pak

```
Contains 3 folders (895.541 bytes)
```


1º Folder's Name: 2cb3ef3b

```
0000002a.dat (4 bytes)
```


2º Folder's Name: 745dcd45

```
Contains 41 DAT Files (895.528 bytes)
```


3º Folder's Name: a7f505c4

```
00000000.dat (9 bytes)

```


So, as you can see, both of the files "Singer_Male.pak.xen" and "singer_male.tex.xen" contain exactly the same DDS Textures for the model. However, the file "Singer_Male.pak.xen" may contain some other information about the model, which I can not interpret, since all files are just DAT files. Some DAT files are kind of big, some other DAT files just have 4 bytes in size. The same happens with "Singer_Male_Anims.pak". It only contains DAT files, which I can not open, since I don't know what type of file is each of one originally. I tried changing DAT file extension into FBX or OBJ without results. I think it has to be more difficult than just changing the file extension, right?

So, I would like to ask for your kind assistance again.

- Is there a way the file "singer_male.skin.xen" could be decrypted? Maybe another script for QuickBMS?
- How can I open those DAT files? How can I know what kind of original filetype it is? Is there any DAT file here that can be interpreted as 3D information, mesh, geometry, rigging, bones, animation, etc?

I attach the extracted files (21,7MB)
[https://drive.google.com/file/d/0B2WPzY ... sp=sharing](https://drive.google.com/file/d/0B2WPzY22ohnYcDVGVjZsOUVoVGc/view?usp=sharing)

I hope we can work this out together, and I thank you in advance for your time 

Thank you again and greetings
## Post #5
- Username: Pandora
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 18, 2015 3:30 am
- Post datetime: 2017-08-14T19:29:16+00:00
- Post Title: Guitar Hero 3 PC - 3D Model Extract for Animation

> Reply from shakotay2
>
> Pandora wrote:I already was able to extract only the geometry of a model posed in A-Posehow did you get it? (using a 3d ripper?). There's some vertex data in the skin file but they appear to be flat (or uvs).

Yes, in fact shakotay2. I used a Direct3D Injector program called Ninja Ripper in order to extract the geometry. Then, I used Guitar Hero Three Control Panel in order to extract the Textures from the game. After that, I tried to clean up the model with Autodesk Maya and apply the textures to it.

I wrote a post about my findings using Luigi Aurema's QuickBMS script for GH3 PAK.XEn files and TEX.XEN.
Is anything I can do to open or use those bunch of DAT files?

Thank you in advance
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-08-14T20:01:00+00:00
- Post Title: Guitar Hero 3 PC - 3D Model Extract for Animation

> Reply from Pandora
>
> The file "singer_male.skin.xen" returns the following error in QuickBMS.
It's because of this:

> Reply from shakotay2
>
> From what I see singer_male.skin.xen is just an excerpt from Singer_Male.pak.xen.To be more specific: it's the block 0x47AC00 - 0x52F909 in the pak file.

This is what the bms script does (besides getting the dds textures): it copies the above block into 0000000c.dat because it's not lzss0 compressed. (You wouldn't run the script again on that block, would you?)

Since the .dat files in the 745dcd45 folder are generated from the *_Anims.pak it's very likely that they contain animation frames.
(Filesize (big endian) DWORD at 0x0008)
## Post #7
- Username: Pandora
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 18, 2015 3:30 am
- Post datetime: 2017-08-14T20:23:07+00:00
- Post Title: Guitar Hero 3 PC - 3D Model Extract for Animation

Thank you for your reply.

I quite don't understand very well what is happening in the files, but I will assume that any file is a bunch of Hexadecimal codes and the QuickBMS script is replacing some Hexadecimal code into the files to extract them and make them readable.

What I would like to know is how can I open, use, or interpret those lots of DAT files. Do some of them contain 3D info?

Thank you in advance. ^^
