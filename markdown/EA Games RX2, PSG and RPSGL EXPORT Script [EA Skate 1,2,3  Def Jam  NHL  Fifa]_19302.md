## Post #1
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-11T13:37:48+00:00
- Post Title: EA Games RX2, PSG and RPSGL EXPORT Script [EA Skate 1,2,3 / Def Jam / NHL / Fifa]

Hello!
I made a semi-universal exporting script for rx2, rpsgl and psg files for NOESIS.

SUPPORTS:

Xbox 360:
Skate 1 Models - 100% + Multi model support
Skate 2 Models - 100% + Multi model support
Skate 3 Models - 100% + Multi model support

Skate 1 Textures - 100% + Multi texture support
Skate 2 Textures - 100% + Multi texture support
Skate 3 Textures - 100% + Multi texture support
NHL Legacy (Unknown amount  of support)

Model Support Xbox 360:
Supports all vert types and UV types. [short, ushort, halffloat and float]
Supports up to 3 UVs (maximum for EA Skate) (I can add further support for other games if you find any that has more than 3 UV layers)
Supports visualization of Bone matrices (not yet complete)
Supports visualization of Simulation / collision data (not yet complete)

Texture Support Xbox 360:
Supports 100% of single texture for all EA Skate games (probably many more RW4 games)
Supports 100% of multi texture files for all EA Skate games (probably many more RW4 games)
Supports DXT1, DXT3, DXT5, FOURCC_DXT5, FOURCC_ATI2, FOURCC_DXT1NORMAL, "a8r8g8b8", "b5g6r5" and "A8" type textures.

---------------------------------------------------------------------------------------------------------------------------------

Playstation 3:
Skate 1 Textures - 100% + Finally Multi texture support! 
Skate 2 Textures - 100% + Finally  Multi texture support! 
Skate 3 Textures - 100% + Finally  Multi texture support! 
Def Jam: Icon (Unknown amount of support)
NHL Legacy (Unknown amount  of support)
Fifa 2009 (Unknown amount  of support)

Texture Support Playstation 3:
Supports 100% of single texture for all EA Skate games (probably many more RW4 games)
Supports DXT1, DXT3, DXT5, RGBA32,  Ambient Occlusion ( _ao / 0x81 type ) and cubemaps ( 0x85 )

Model Support Playstation 3:
-Being worked on!

Last Update: October 28th 2021
-------------------------------------------------------------------

Full map loaded in Noesis (SKATE 3):


Texture of Big Black  (SKATE 3):


NHL Legacy Jersey:


Def Jam: Icon Diffuse:


Def Jam: Icon AO / Ambient Occlusion:


Credits: 
Beedy : for the Skate 3 level script that I worked off of to add complete model support.
Acewell : for help in the past with texture formats.
Joschka : for help with bones. (this will be worked on an implemented in the future)
DKDave: for help with AO / 0x81 imgFmt rpsgl textures
Edness: for help with AO / 0x02 imgFmt rx2 textures

Latest download: You can find it in the attachments.

Noesis Download: [https://www.richwhitehouse.com/index.ph ... project=91](https://www.richwhitehouse.com/index.php?content=inc_projects.php&showproject=91)

Have fun!
[mdl_EA_SKATE_4_6_6.zip](https://xentaxbackup.github.io/file/21085_mdl_EA_SKATE_4_6_6.zip)
## Post #2
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-01-12T09:13:54+00:00
- Post Title: EA Games RX2, PSG and RPSGL EXPORT Script [EA Skate 1,2,3 / Def Jam / NHL / Fifa]

Nice job man! Single textures works but many of textures has packed in "texlib.rx2" which contains more than one texture in NHL and my script support texture names also. However first texture in "texlib" works perfect.  I will check if I can fix my NHL script more easier to understand.

Keep going on, you have done nice work with skate 3! 
Ea has released open source code for some products including skate 3 and you may be interested:
[https://gpl.ea.com](https://gpl.ea.com)
## Post #3
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-12T09:54:16+00:00
- Post Title: EA Games RX2, PSG and RPSGL EXPORT Script [EA Skate 1,2,3 / Def Jam / NHL / Fifa]

> Reply from Beedy
>
> Nice job man! Single textures works but many of textures has packed in "texlib.rx2" which contains more than one texture in NHL and my script support texture names also. However first texture in "texlib" works perfect.  I will check if I can fix my NHL script more easier to understand.

Keep going on, you have done nice work with skate 3! 
Ea has released open source code for some products including skate 3 and you may be interested:
https://gpl.ea.com

That's pretty neat  I didn't know about that. I can take a look.
Yeah I didn't think names was going to be necessary because I made the script for Skate 1,2,3 only at first, and they only ever contain 1 texture per file and they are also called the exact same thing as the rx2 files x) So it didn't matter on those files. But yeah maybe if you want to take a look at my script and make it work with names and multiple files?  I only started learning Python 2 weeks ago, so it's difficult for me to understand the way you are doing your script. I only know c++ and some c#.
## Post #4
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-01-12T10:52:36+00:00
- Post Title: EA Games RX2, PSG and RPSGL EXPORT Script [EA Skate 1,2,3 / Def Jam / NHL / Fifa]

I started learnig two years ago without any experiment of programming and thats why my script looks weird    but it’s not straightforward header. We have different scripts which works perfectly with different games so it isn’t necessary to bring it together but I will take a look. It takes time but it’s funny   

How do you use your mods in Xbox 360? Do you have rgh-modded console and is it possible to play a game with extracted archives? I have xkey and textures need to be  compress to chunklzx-format and re-import in .big archive and then inject modded big In to iso file. Thats so complex. Can you test if it’s possible to play Nhl with extracted files?
## Post #5
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-13T04:34:08+00:00
- Post Title: EA Games RX2, PSG and RPSGL EXPORT Script [EA Skate 1,2,3 / Def Jam / NHL / Fifa]

> Reply from Beedy
>
> I started learnig two years ago without any experiment of programming and thats why my script looks weird    but it’s not straightforward header. We have different scripts which works perfectly with different games so it isn’t necessary to bring it together but I will take a look. It takes time but it’s funny   

How do you use your mods in Xbox 360? Do you have rgh-modded console and is it possible to play a game with extracted archives? I have xkey and textures need to be  compress to chunklzx-format and re-import in .big archive and then inject modded big In to iso file. Thats so complex. Can you test if it’s possible to play Nhl with extracted files?

Yes I run the games from unpacked archives and the big files in Skate 3 run fine like that, so Sure I can try  I don't think it will work tho. Skate 1 and 2 doesn't work unpacked for the very reason that they use a .BH file that seem to require the files to be in .big format to read them. (maybe this can be worked around)
But I can give it a go and see if it runs!

Also, something I noticed with ALL EA Skate games is that the Levels textures, 3d models and collision data is packed in a large container and they have the header for each file and it looks like I should be able to open them with any of our scripts, but none of them come out as a texture or even the models doesn't even seem like model data. :/ So I am thinking it may be the headers are uncompressed but the data itself is compressed. Is there anything like this in the NHL or Fifa games? I have tried figuring it out for the longest time and can't find anything about it.
## Post #6
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2019-01-19T00:56:37+00:00
- Post Title: EA Games RX2, PSG and RPSGL EXPORT Script [EA Skate 1,2,3 / Def Jam / NHL / Fifa]

Good job! Is it possible to export models from Def Jam Icon?
## Post #7
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-20T11:45:09+00:00
- Post Title: EA Games RX2, PSG and RPSGL EXPORT Script [EA Skate 1,2,3 / Def Jam / NHL / Fifa]

> Reply from JimmyJ
>
> Good job! Is it possible to export models from Def Jam Icon?

I have no files to test with, so if you could provide one, I'll give it a go.

Edit: I got my hands on the game and extracted some Def Jam Icon rx2 files and played around with them and yes, you can export models from them.
## Post #8
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-28T08:34:52+00:00
- Post Title: EA Games RX2, PSG and RPSGL EXPORT Script [EA Skate 1,2,3 / Def Jam / NHL / Fifa]

> Reply from Beedy
>
> I started learnig two years ago without any experiment of programming and thats why my script looks weird    but it’s not straightforward header. We have different scripts which works perfectly with different games so it isn’t necessary to bring it together but I will take a look. It takes time but it’s funny   

How do you use your mods in Xbox 360? Do you have rgh-modded console and is it possible to play a game with extracted archives? I have xkey and textures need to be  compress to chunklzx-format and re-import in .big archive and then inject modded big In to iso file. Thats so complex. Can you test if it’s possible to play Nhl with extracted files?

I am downloading NHL 2013 now and hoping there is these same filetypes in there. I can't find NHL07 anywhere online for Xbox 360 for download. 
So I am going to try to run the game off unpacked files as a test. Would be really cool if that worked. I still really want to find NHL 07 tho. I played that a lot with my friends back in the day and it's the only NHL I have played, so would be a blast from the past haha.
## Post #9
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-01-28T10:36:05+00:00
- Post Title: EA Games RX2, PSG and RPSGL EXPORT Script [EA Skate 1,2,3 / Def Jam / NHL / Fifa]

Thanks! I’d like to know if it’s possible and then I may upgrade my console to rgh-modded instead of xkey which allows only modded Iso-files. Iso modifications works 99% perfect but I want to add a few  extra textures in game. That isn’t possible because there is unknown Hash or CRC for names in the big-archive and files will not appear in game with wrong crc. I can still rebuild bigs with files which is already in archive.


Big-archive format is different between NHL 07-10 and newer versions. There is .big files with .bh header file in 07-10 and newer has only big-archive without bh-file. The type is same as Skate 3 has.

I have NHL 07 and it’s awful with 30fps gameplay
## Post #10
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-28T12:17:43+00:00
- Post Title: EA Games RX2, PSG and RPSGL EXPORT Script [EA Skate 1,2,3 / Def Jam / NHL / Fifa]

> Reply from Beedy
>
> Thanks! I’d like to know if it’s possible and then I may upgrade my console to rgh-modded instead of xkey which allows only modded Iso-files. Iso modifications works 99% perfect but I want to add a few  extra textures in game. That isn’t possible because there is unknown Hash or CRC for names in the big-archive and files will not appear in game with wrong crc. I can still rebuild bigs with files which is already in archive.


Big-archive format is different between NHL 07-10 and newer versions. There is .big files with .bh header file in 07-10 and newer has only big-archive without bh-file. The type is same as Skate 3 has.

I have NHL 07 and it’s awful with 30fps gameplay

I downloaded 2014 instead because the server for that was faster, and it works!  You can play from unpacked files. I unpacked all the BIG files containing audio, video, 3D models and Textures and 
it plays perfectly fine ^^ So my guess would be that it works for all the games with Big files without BH files. I have a FTP server set up on my PC, so I am streaming the files from my PC harddrive to the xbox, so I can mod the files while the game is running, go out in the menu and then load a new game and the modded file is now loaded haha.
So maybe it would be worth it to get your hands on a RGH console?
## Post #11
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-01-28T18:50:46+00:00
- Post Title: EA Games RX2, PSG and RPSGL EXPORT Script [EA Skate 1,2,3 / Def Jam / NHL / Fifa]

> Reply from GHFear
>
> 
I downloaded 2014 instead because the server for that was faster, and it works!  You can play from unpacked files. I unpacked all the BIG files containing audio, video, 3D models and Textures and 
it plays perfectly fine ^^ So my guess would be that it works for all the games with Big files without BH files. I have a FTP server set up on my PC, so I am streaming the files from my PC harddrive to the xbox, so I can mod the files while the game is running, go out in the menu and then load a new game and the modded file is now loaded haha.
So maybe it would be worth it to get your hands on a RGH console?
 Thank you, very cool. That's a reason to rgh-mod my console.
## Post #12
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-01-29T10:51:43+00:00
- Post Title: EA Games RX2, PSG and RPSGL EXPORT Script [EA Skate 1,2,3 / Def Jam / NHL / Fifa]

> Reply from Beedy
>
> Nice job man! Single textures works but many of textures has packed in "texlib.rx2" which contains more than one texture in NHL and my script support texture names also. However first texture in "texlib" works perfect.  I will check if I can fix my NHL script more easier to understand.

Keep going on, you have done nice work with skate 3! 
Ea has released open source code for some products including skate 3 and you may be interested:
https://gpl.ea.com

Is it possible to see 3d file from rx2 noesis?
## Post #13
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-01-29T16:34:37+00:00
- Post Title: EA Games RX2, PSG and RPSGL EXPORT Script [EA Skate 1,2,3 / Def Jam / NHL / Fifa]

> Reply from mita996
>
> 
Is it possible to see 3d file from rx2 noesis?
Not yet, It should write a python script for rx2. That isn't so easy and takes a time, but maybe sometimes I will try.
## Post #14
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2021-10-19T02:24:39+00:00
- Post Title: EA Games RX2, PSG and RPSGL EXPORT Script [EA Skate 1,2,3 / Def Jam / NHL / Fifa]

New update to this script!

4.5.8:
-Added multi-texture support for Playstation 3 PSG Textures.
-Added multi texture support for RPSGL format.
-Added debug printing of material names in the debug log. (Open debug menu by clicking on "Tools->Reload plugins")
-Made a bunch of logic changes to how textures are handled.
-Now supports some NHL titles like NHL Legacy and NHL 2010 type rx2 textures.
-Now supports Def Jam: Icon rx2 Textures.
-Added support for Ambient Occlusion textures for Playstation 3 PSG and RPSGL formats for the first time!  -Thanks to DKDave
-Probably much more I forgot about.

4.6.0:
-Added further support for RPSGL textures (Fifa09 and other games with the same format).
-Fixed the rpsgl Ambient Occlusion maps, so now it should give you the proper texture for _ao occlusion maps.
-Added support for rx2 (Xbox 360) Occlusion Maps with format "D3DFMT_A8". (Thanks to Edness on Xentax)
-many small rx2 texture loading fixes.
-many small rpsgl texture loading fixes.

4.6.1:
-Added a temporary fix to the script for an issue that broke many PS3 / psg / rpsgl textures.
To open early Fifa rpsgl textures open the python script and set the GAME_SPECIFIC option to "FIFA09". 


4.6.2:
-Fixed a critical issue with both Xbox and PS3 multi texture files. They should now work just fine! 
-Added playstation 3 support for 0x85 Cubemaps

4.6.3:
-Added Support for FOURCC_DXT5 textures for Xbox 360 rx2.
-Several small bugfixes related to issues with texture format recognition and texture size.

4.6.4:
-Now gives proper Meshnames when possible 
-Many small fixes. (report to me if something is broken)

4.6.5:
-Now gives Materialnames when possible 
-Now you need to set "USE_MESH_NAMES" to 1 to try to get Mesh Names.
-Now you need to set "USE_MATERIAL_NAMES" to 1 to try to get Material Names.


4.6.6:
-Added support for a new DXT5 texture type found in Skate 2 DLC (\data\fe\source\images\map)
