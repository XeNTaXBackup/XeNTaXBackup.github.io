## Post #1
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-05-04T15:27:34+00:00
- Post Title: Def Jam : FFNY PS2 *.o model

In this file should be the model for the trophy. Files with this extension are used as models in the games from EA for the PC, so I think the games on the PS2 also can view models.
Sorry for any mistakes, but I use translator.

[http://www.sendspace.com/file/d25sw9](http://www.sendspace.com/file/d25sw9)
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-07T02:05:41+00:00
- Post Title: Def Jam : FFNY PS2 *.o model

> Reply from grzesiek
>
> In this file should be the model for the trophy. Files with this extension are used as models in the games from EA for the PC, so I think the games on the PS2 also can view models.
Sorry for any mistakes, but I use translator.

http://www.sendspace.com/file/d25sw9
This games uses PS2 based tristripe meshes commonly used in PS2 games
The format of the sub mesh is roughly:
00 C0 01 6C XX .....
18 C0 XX 6C
4bytefloatVertexes(for X,Y,Z) + Weight
60 C0 XX 6C
4bytefloat UV (for U,V) Map + weight+ 00 00 00 00
A8 C0 XX 6E
1byteVertex color(for R,G,B) + 80

where XX is the number of vertexes

Also where each tristrip ends is unknown to me (usually it is done by having a Connection stop byte + 2bytefloat (not a typo) Weight as 00 80 80 3f or no floating point weight just 00 80 00 00 but in this game Weight is always 1.00 (ie 00 00 80 3f) maybe the game just knows not to render loose faces that are not double sided?

[http://ps23dformat.wikispaces.com/file/ ... mesh.blend](http://ps23dformat.wikispaces.com/file/view/statmesh.blend)
## Post #3
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-05-07T09:57:56+00:00
- Post Title: Def Jam : FFNY PS2 *.o model

> Reply from FurryFan
>
> grzesiek wrote:In this file should be the model for the trophy. Files with this extension are used as models in the games from EA for the PC, so I think the games on the PS2 also can view models.
Sorry for any mistakes, but I use translator.

http://www.sendspace.com/file/d25sw9
This games uses PS2 based tristripe meshes commonly used in PS2 games
The format of the sub mesh is roughly:
00 C0 01 6C XX .....
18 C0 XX 6C
4bytefloatVertexes(for X,Y,Z) + Weight
60 C0 XX 6C
4bytefloat UV (for U,V) Map + weight+ 00 00 00 00
A8 C0 XX 6E
1byteVertex color(for R,G,B) + 80

where XX is the number of vertexes

Also where each tristrip ends is unknown to me (usually it is done by having a Connection stop byte + 2bytefloat (not a typo) Weight as 00 80 80 3f or no floating point weight just 00 80 00 00 but in this game Weight is always 1.00 (ie 00 00 80 3f) maybe the game just knows not to render loose faces that are not double sided?

http://ps23dformat.wikispaces.com/file/ ... mesh.blend

each object block start with a 0x00000017

also this id just the sub chunk part of each drawcall, the 0x6c specify the type of dat as integer and 0x6E as float etc...
so :
18 C0 = chunk type (discribe if it is a color, a vertex, a matrix or else...)
xx = datacount
6E,6C etc.. specify the datatype to be read

also the tristrip degenerate faces and culling may be based on color depth buffer, i encountered the same problem in xenosaga 3 models
## Post #4
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-05-08T09:15:26+00:00
- Post Title: Def Jam : FFNY PS2 *.o model

This should be a model for Elephant Man. Once you open it in a hex editor, the header is slightly different. It seems to me that it is compressed.

Can you do a tutorial in which it is explained how to open those models in a blender?

[http://www.sendspace.com/file/hey4vn](http://www.sendspace.com/file/hey4vn)
## Post #5
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-24T17:42:03+00:00
- Post Title: Def Jam : FFNY PS2 *.o model

> Reply from grzesiek
>
> This should be a model for Elephant Man. Once you open it in a hex editor, the header is slightly different. It seems to me that it is compressed.

Can you do a tutorial in which it is explained how to open those models in a blender?

http://www.sendspace.com/file/hey4vn

This last file is not a model at all, as it appears to be part of the ELF file, used to boot up the game, as it has the letters "ELF" near the first line. In face even in the first model, there was still an ELF header.
I know the Ratchet and Clank series also uses bits and pieces of ELF in data files.
I get the models in blender by getting using a hex editor to copy the vertexes into Microsoft Word, where I remove all of the non-vertex data, and then I paste it into a blank OGRE 3d .mesh file which I can import into blender with a Ogre3d importer.
Can you give me a list of all of the files on the disc, or one of every type?
## Post #6
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-06-01T16:21:18+00:00
- Post Title: Def Jam : FFNY PS2 *.o model

I am confident that this is the model file. Is compressed. Models of EA PC model files also have the same header. On the game disc there is thousands of *.o files. They are just packed in VIV archives. They have a similar header. Here I put a list of all files from the game.

```
02072158 , E:\ASSETS\CINEMA\GF1A.VIV
02072736 , E:\ASSETS\CINEMA\GF1B1.VIV
02074064 , E:\ASSETS\CINEMA\GF1B2.VIV
02075387 , E:\ASSETS\CINEMA\GF1B3.VIV
02076713 , E:\ASSETS\CINEMA\GF1B4.VIV
02078035 , E:\ASSETS\CINEMA\GF1C.VIV
02080732 , E:\ASSETS\CINEMA\GF1D.VIV
02081586 , E:\ASSETS\CINEMA\GF2A.VIV
02085868 , E:\ASSETS\CINEMA\GF2B.VIV
02089029 , E:\ASSETS\CINEMA\GF2C.VIV
02091148 , E:\ASSETS\CINEMA\GF2D.VIV
02092815 , E:\ASSETS\CINEMA\GF2E.VIV
02093405 , E:\ASSETS\CINEMA\GF3A.VIV
02093722 , E:\ASSETS\CINEMA\GF3B.VIV
02094115 , E:\ASSETS\CINEMA\GF3C.VIV
02095308 , E:\ASSETS\CINEMA\SC00.VIV
02100155 , E:\ASSETS\CINEMA\SC01.VIV
02110258 , E:\ASSETS\CINEMA\SC02.VIV
02115161 , E:\ASSETS\CINEMA\SC03.VIV
02118248 , E:\ASSETS\CINEMA\SC04.VIV
02122027 , E:\ASSETS\CINEMA\SC05.VIV
02138763 , E:\ASSETS\CINEMA\SC06.VIV
02141121 , E:\ASSETS\CINEMA\SC07A.VIV
02148580 , E:\ASSETS\CINEMA\SC07B.VIV
02173213 , E:\ASSETS\CINEMA\SC08.VIV
02181758 , E:\ASSETS\CINEMA\SC09.VIV
02189564 , E:\ASSETS\CINEMA\SC10.VIV
02194389 , E:\ASSETS\CINEMA\SC11.VIV
02201537 , E:\ASSETS\CINEMA\SC12.VIV
02201792 , E:\ASSETS\CINEMA\SC13.VIV
02211046 , E:\ASSETS\CINEMA\SC14.VIV
02219395 , E:\ASSETS\CINEMA\SC15.VIV
02220233 , E:\ASSETS\CINEMA\SC16.VIV
02221427 , E:\ASSETS\CINEMA\SC17.VIV
02237200 , E:\ASSETS\CINEMA\SC18.VIV
02248275 , E:\ASSETS\CINEMA\SC19.VIV
02264637 , E:\ASSETS\CINEMA\SC20.VIV
02276205 , E:\ASSETS\CINEMA\SC21.VIV
02021095 , E:\ASSETS\IRRAD\IRRAD.VIV
02019728 , E:\ASSETS\SPYCAM\BARBER.SPY
02019729 , E:\ASSETS\SPYCAM\CLOTH.SPY
02019730 , E:\ASSETS\SPYCAM\CRIB.SPY
02019732 , E:\ASSETS\SPYCAM\CRPLAYER.SPY
02019733 , E:\ASSETS\SPYCAM\DEFAULT.SPY
02019734 , E:\ASSETS\SPYCAM\GYM.SPY
02019735 , E:\ASSETS\SPYCAM\JEW.SPY
02019736 , E:\ASSETS\SPYCAM\TATTOO.SPY
02019541 , E:\ASSETS\AKI_CFG.XML
02019542 , E:\ASSETS\BLINGFX.VIV
02019794 , E:\ASSETS\CINCROWD.VIV
01944111 , E:\ASSETS\COMBS.XML
01968842 , E:\ASSETS\DECALFX.VIV
02019552 , E:\ASSETS\DJV2.SOD
02019679 , E:\ASSETS\ENTITY.XML
01877191 , E:\ASSETS\FEPOSES.VIV
02019724 , E:\ASSETS\FETEXT.LOC
01944101 , E:\ASSETS\GAMECORE.XML
01969010 , E:\ASSETS\ICROWD.VIV
02019017 , E:\ASSETS\MISC.VIV
02019536 , E:\ASSETS\NIS.VIV
02066211 , E:\ASSETS\PROPS.VIV
01877595 , E:\ASSETS\SHOPS.VIV
02019790 , E:\ASSETS\SUBTITLE.VIV
02019737 , E:\ASSETS\TAUNT.XML
01968852 , E:\ASSETS\TEXANIM.VIV
02019747 , E:\ASSETS\TINT.SSH
01877205 , E:\ASSETS\TROPHIES.VIV
01944127 , E:\ASSETS\V2BG.VIV
02022084 , E:\ASSETS\V2BG_CIN.VIV
02017295 , E:\ASSETS\V2CM.VIV
01717359 , E:\ASSETS\V2CP_0.VIV
01721892 , E:\ASSETS\V2CP_1.VIV
01771396 , E:\ASSETS\V2CP_2.VIV
01811185 , E:\ASSETS\V2CP_3.VIV
02019764 , E:\ASSETS\V2GA.VIV
02003089 , E:\ASSETS\V2IP.VIV
02049867 , E:\ASSETS\V2IP_CIN.VIV
01197833 , E:\ASSETS\V2TA.VIV
02018255 , E:\ASSETS\V2WP.VIV
01943728 , E:\AUDIO\ANIMTAGS.DAT
01361446 , E:\AUDIO\MUSIC0.VIV
01427377 , E:\AUDIO\MUSIC1.VIV
01516954 , E:\AUDIO\MUSIC2.VIV
01599926 , E:\AUDIO\MUSIC3.VIV
01665129 , E:\AUDIO\MUSIC4.VIV
00960252 , E:\AUDIO\SFX0.VIV
00989393 , E:\AUDIO\SFX1.VIV
01092517 , E:\AUDIO\SFX2.VIV
01912105 , E:\AUDIO\SFX3.VIV
01271167 , E:\AUDIO\SPEECH1.VIV
01199301 , E:\AUDIO\SPEECH2.VIV
01890281 , E:\AUDIO\SPEECH3.VIV
01943960 , E:\AUDIO\TV.TXT
01943671 , E:\FONTS\BEFONTS.VIV
01824152 , E:\FONTS\FONTS.VIV
01943344 , E:\IOP\BOOT.VIV
01943401 , E:\IOP\IOPRP280.IMG
01943533 , E:\IOP\LIBSD.IRX
01943547 , E:\IOP\MCMAN.IRX
01943594 , E:\IOP\MCSERV.IRX
01943598 , E:\IOP\MTAPMAN.IRX
01943604 , E:\IOP\PADMAN.IRX
01943626 , E:\IOP\SIO2MAN.IRX
01943630 , E:\IOP\SNDDRV.IRX
02001906 , E:\MOTION\BASE00.VIV
02000500 , E:\MOTION\BLAZIN.VIV
02018946 , E:\MOTION\CAMERA.XML
01943962 , E:\MOTION\MAIN_ALL.DAT
01969168 , E:\MOTION\WRES_ALL.VIV
00902000 , E:\MOVIES\ATTRACT.MPC
00912013 , E:\MOVIES\EAGAMEFR.MPC
00912786 , E:\MOVIES\EAGAMES.MPC
00913695 , E:\MOVIES\EXTRA.MPC
00914725 , E:\MOVIES\INTRO.MPC
00935368 , E:\MOVIES\LOAD0.SSH
00935378 , E:\MOVIES\MOVIES.VIV
00958040 , E:\MOVIES\SOULTRAI.MPC
00959070 , E:\MOVIES\THX.MPC
00959676 , E:\MOVIES\THX_FR.MPC
01824344 , E:\SCREENS\FEFLOW.XML
01824358 , E:\SCREENS\SCREENS.VIV
01943310 , E:\CHARS.XML
01943314 , E:\FIGHTER.XML
01943337 , E:\GAMEDATA.XML
01943342 , E:\GCONFIG.XML
01941766 , E:\SLES_525.07
01941765 , E:\SYSTEM.CNF
01943300 , E:\VENUE.XML
```


Here is a model from the game FIFA 10. It seems that the format is similar.
[http://www.sendspace.com/file/dui6ap](http://www.sendspace.com/file/dui6ap)

Sorry for my bad english.
## Post #7
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-06-04T15:40:24+00:00
- Post Title: Def Jam : FFNY PS2 *.o model

Uncompressed model from FIFA 09:
[http://www.sendspace.com/file/5p6t56](http://www.sendspace.com/file/5p6t56)
## Post #8
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-07-23T19:56:57+00:00
- Post Title: Def Jam : FFNY PS2 *.o model

I tried to see model of trophy in blender. I copied raw verticles to model.mesh file, but Ogre3d importer doesnt open this file.

[http://www.sendspace.com/file/mkq5ec](http://www.sendspace.com/file/mkq5ec)
Uncompressed *.o file : [http://www.sendspace.com/file/rinaj5](http://www.sendspace.com/file/rinaj5)
Sorry for my english.
## Post #9
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-07-23T23:05:13+00:00
- Post Title: Def Jam : FFNY PS2 *.o model

> Reply from grzesiek
>
> I tried to see model of trophy in blender. I copied raw verticles to model.mesh file, but Ogre3d importer doesnt open this file.

http://www.sendspace.com/file/mkq5ec
Uncompressed *.o file : http://www.sendspace.com/file/rinaj5
Sorry for my english.
That is correct, you first have to convert the Ogre 3d .Mesh binary file to the Ogre 3d .mesh.xml Ascii format using the following steps:
Download the ogreXMLconverter from
[http://sourceforge.net/projects/ogre/fi ... i/download](http://sourceforge.net/projects/ogre/files/ogre-tools/1.6.0/OgreCommandLineTools_1.6.0.msi/download)
Then press the "Windows Start Button" and find the "Command Prompt"
(In windows Vista it is under Programs->Accessories-> Command Prompt
Type in the path to the ogrexmlconverter.exe (Hint just put the mesh in the default path for me it is C:\users\mike to avoid typing the full path) then type \ogrecommandlinetools\ogrexmlconverter blankmodel1.mesh
## Post #10
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-07-24T07:49:33+00:00
- Post Title: Def Jam : FFNY PS2 *.o model

Ogrexmlconverter seems not open this file. Maybe is something wrong with binary model.mesh.

```
09:48:20: Creating resource group Internal
09:48:20: Creating resource group Autodetect
09:48:20: Registering ResourceManager for type Mesh
09:48:20: Registering ResourceManager for type Material
09:48:20: Registering ResourceManager for type Skeleton
09:48:20: OGRE EXCEPTION(2:InvalidParametersException): Header chunk didn't match either endian: Corrupted stream? in Serializer::determineEndianness at ..\src\OgreSerializer.cpp (line 90)
09:48:20: Unregistering ResourceManager for type Skeleton
09:48:20: Unregistering ResourceManager for type Material
09:48:20: Unregistering ResourceManager for type Mesh

```
## Post #11
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-07-24T11:24:39+00:00
- Post Title: Def Jam : FFNY PS2 *.o model

Don't worry, I'll help you, its slightly more complicated than just pasting the vertexes at the beginning of the file, you have to paste them at a certain offset. I really want to make a program or script that will automatically find PS2 format tristrips and convert them automatically.
## Post #12
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-07-24T21:20:38+00:00
- Post Title: Def Jam : FFNY PS2 *.o model

model.mesh file is correct? Whats wrong with it?
## Post #13
- Username: leptos
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 10, 2021 12:14 pm
- Post datetime: 2021-02-18T01:48:26+00:00
- Post Title: Def Jam : FFNY PS2 *.o model

Is anyone still working on this? I'd like to get the models from FFNY.
## Post #14
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2021-02-19T17:07:07+00:00
- Post Title: Def Jam : FFNY PS2 *.o model

They are uploaded here:
[https://www.models-resource.com/playsta ... ornewyork/](https://www.models-resource.com/playstation_2/defjamfightfornewyork/)
