## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-08T01:37:26+00:00
- Post Title: Tales of Fantasy

Homepage & client download: [http://tof.igg.com/](http://tof.igg.com/)

Screenshot:



Formats: meshes (skem, sm), textures (qtx), animations (anim)
Notes: each folder of .sm models contains a (plain) text file called "GeomTriList.txt". In it contains a list of entries that resemble the model names and has a number beside it

> Caijt_I_Fushi02=116 2006/7/26 13:43:35
>
> Caijt_I_Fushi03=120 2006/7/26 13:43:35
>
> Caijt_I_Jiangshi02=44 2006/7/26 13:43:35
>
> Caijt_I_Mamian02=344 2006/7/26 13:43:37
>
> Cai_I_dunpai2=128 2006/7/26 13:43:37
>
> Cai_I_fazhang01=468 2006/7/26 13:43:49
>
> Cai_I_futou01=242 2006/7/26 13:43:51

Maybe it's the number of faces in the model, but it would be quite annoying to have to parse this file to get it.

Formats don't seem to complicated.
It's just that each property in the vertex struct is grouped sequentially, so it'll say "70 coords" followed by all 70 coords, and then "70 normals" followed by 70 normals, and then "70 UV" followed by 70 UV, etc.

There's a lot of values I'm not sure what they are, though they are all grouped nicely.

For sm files, the groups are

float_3 coords
float_3 ??? (normals?)
float_2 uv
float_3 ???

Two additional groups appear for skem models, which are in a folder called "skelmesh" so presumably these deal with weights and...some other thing.

float_4 ???
float_4 ???

There are also a lot of stuff with the faces as well...no clue what they are.

Don't know what the last 3 might be.
If you run a find-all for the numVerts, you'll get that number.

Samples attached (sm, skem, qtx)
[Tales of Fantasy.7z](https://xentaxbackup.github.io/file/4446_Tales of Fantasy.7z)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-08T02:00:00+00:00
- Post Title: Tales of Fantasy

Basic geometry has been sorted out.
Now just need to figure out the unknown values and figure out how to deal with the textures.
## Post #3
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-07-09T07:47:14+00:00
- Post Title: Tales of Fantasy

```
dword[a] = 4 bytes*a
word[a]  = 2 bytes*a
float[a] = 4 bytes*a



dword[1] - nBodyPartType(hands,heads,hair,...)
nBodyPartType x {
dword[1] - ?
dword[1] - nBodyPartPerType(hair1,hair2,hair3,...,heads1.heads2,heads3,...)
nBodyPartPerType x {
word[1] - nChar
string[nChar] - name body part
dword[1] - ?
dword[1] - nVertexCoord
nVertexCoord x {
float[3]
}
dword[1] - nUnknow1(normals ?)
nUnknow1 x {
float[3]
}
dword[1] - nUvCoord
nUvCoord x {
float[2]
}
dword[1] - nUnknow2
nUnknow2 x {
float[3]
}
dword[1] - nVertexWeight
nVertexWeight x {
float[4]
}
dword[1] - nVertexIndices
nVertexIndices x {
float[4] as integer[4]
}
dword[1] - nFacesIndices
nFaces = nFacesIndices/3
nFaces x {
word[3]
}
dword[4] - unknow
byte[1]  - unknow
dword[1] - uUnknow3
nUnknow3 x {
word[1]
}
dword[1] - uUnknow4
nUnknow4 x {
dword[3]
}
} - end BodyPartPerType
} - end BodyPartType

=======================================================

format .anim files in game [PC]Tales of Fantasy

dword[1] - nAnimation
nAnimation x {
dword[1] - nBones
dword[1] - nFrames
nBones x {
nFrames x {
float[4] - quat
float[3] - pos
} - end frames
} - end bones
} - end Animation






```

[import-tales-of-fantasy.zip](https://xentaxbackup.github.io/file/4459_import-tales-of-fantasy.zip)
## Post #4
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-09T18:27:14+00:00
- Post Title: Tales of Fantasy

Skara rocks....
## Post #5
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-11T01:45:18+00:00
- Post Title: Tales of Fantasy

Something advace in load .sm (models) and .qtx Texture files?
## Post #6
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2011-07-11T02:37:27+00:00
- Post Title: Tales of Fantasy

Anyway to convert .qtx to png or tga , everyone ?
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-11T02:47:37+00:00
- Post Title: Tales of Fantasy

[viewtopic.php?f=18&t=6936](http://forum.xentax.com/viewtopic.php?f=18&t=6936)

Chrrox says to just add the header, but I don't know if there's a way to do it automatically.

Also, SM format is very similar to SKEM format except it doesn't have the two structs with 4 floats each, so you can just take out the code that iterates over those two structs. Don't know if he parsed anything else though.
## Post #8
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2011-07-11T05:22:31+00:00
- Post Title: Tales of Fantasy

@finale00 Thank for your link. I will try to modify .qtx header
## Post #9
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-11T20:32:06+00:00
- Post Title: Tales of Fantasy

Something quick.bms to convert the whole textrues to .dds? and conert the models .sm to .skem? cause a lot are sm. Thanks. i read this answer of tosyk abouth fix textures, but how to know the size of the images? 256x256 or 128x128, something area in the texture file tell this?
i search this but i cant found. Also how to changue the header? cause the file its fully encripted and its not posible for me found where the header start and finish.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-15T02:10:38+00:00
- Post Title: Tales of Fantasy

Basically it doesn't have a header. Chrrox gave an example of inserting a dxt1 header and attached it in the graphics thread.

All you really have to do is figure out which bytes represent the dimensions and then actually figure out what the dimensions might be. Use texturefinder to speed up the process and maybe a pattern can be found (load up a qtx file in texturefinder and then switch between dxt1, dxt3, and dxt5. One of them will probably show up fine; that's the type you want. It also gives you the width...seems like the only way to get the height is to export it and then look at it o.O

Though I haven't actually looked into it yet.

Comparing various dds files from various images, it seems like the only things that differ are the dimensions and the dxt type (dxt1, dxt3, dxt5 seem to be the most common so far, based on what kind of information they can store).

So once you get the dimensions, you just have to try each type until the texture looks right I guess.
There might be a pattern in the filename that you could take advantage of, or perhaps some patterns in how textures are assigned in one of the data files in order to automate it, but so far I have not seen any.

Also about SM files, this is the Sanae script that I use
I basically took my SKEM parser and took away a couple loops here and there. Modifying the blender importer would probably be the same.
[talesOfFantasy_sm.7z](https://xentaxbackup.github.io/file/4490_talesOfFantasy_sm.7z)
## Post #11
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-23T01:27:14+00:00
- Post Title: Tales of Fantasy

Thanks man but this its a very slow way, something idea abouth make bms converter one for each image size? its posible put all the textures in one folder then use bms to convert 128x128 all textures?, and use another bms to convert to redeable texture 256x256 all the textures in one folder?, with preview .dds its posible see in the fact how textures are really 128x128, 256X256 and 512x512, cause open and convert all textures its a crazy job. Bad for me i dont know make .bms files
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-23T02:17:23+00:00
- Post Title: Tales of Fantasy

From what I've read, each pixel format uses a specific number of bits for each pixel. It may be possible to guess which pixel format is used by taking the size of the data and dividing that by the dimensions and then examining the size of each pixel.

But then you don't know what the dimensions are.

I haven't spent much time with graphics files yet.
## Post #13
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-23T02:31:32+00:00
- Post Title: Tales of Fantasy

[quote="Szkaradek123"][/quote]error with script when execute.
[Script Error.jpg](https://xentaxbackup.github.io/file/4528_Script Error.jpg)
## Post #14
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-25T23:40:21+00:00
- Post Title: Tales of Fantasy

The textures can come with 3 or 4 variants it think, maybe its posible make the bms to make all the textures with all the variants, 1 of this size variants its right and the others are bad files, if its posible make the batch to convert all the textures to all the posible sizes or formats i think its very easy on this way only see with DDS preview and delete the bad files in windows and keep the right files.
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-25T23:50:17+00:00
- Post Title: Tales of Fantasy

The next question would then be, how do we best guess the dimensions based on the filesize.
Use some probabilistic methods and then output 4-5 different variations on top of the pixel format variations?
## Post #16
- Username: illian
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Feb 05, 2012 8:36 pm
- Post datetime: 2012-12-30T23:00:05+00:00
- Post Title: Re: Tales of Fantasy

> Reply from finale00
>
> The next question would then be, how do we best guess the dimensions based on the filesize.
Use some probabilistic methods and then output 4-5 different variations on top of the pixel format variations?

Seems to be the only right way to do it :/
If you try to convert every .qtx, you will besome.... crazy!
## Post #17
- Username: troll1981
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 10, 2014 2:28 am
- Post datetime: 2014-06-27T11:02:54+00:00
- Post Title: Re: Tales of Fantasy

sorry for questions, but how i open qtx Texture Files ? its 2014!

In Noesis i see the mesh in white with no textures, the same texture has the same meshname but its .qtx File, how i can export in dds or tga ?
## Post #18
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-11-22T11:11:59+00:00
- Post Title: Re: Tales of Fantasy

The 3D Object Converter v6.0 supports the following formats:

Tales of Fantasy *.QTX texture format

Tales of Fantasy / QQXY *.SM (Load)
Tales of Fantasy / QQXY *.SKEM (Load)

The textured mode will load the .qtx file automatically if it exists in same place as the .sm or .skem file.
(If the model file is 123.skem it will search for the 123_d.qtx file automatically.)

You can export the loaded texture files (bitmap) using the Tools/Export the material table's textures to .bmp files function.


You can add the texture file to the material table by hand using the following procedure:
- open your model
- (Click on the textured view icon)
- click on the Object and Material selector on the toolbar (from right the first icon)
- click on the Materials line
- right click on the Material* line
- browse the texture file. (The texture files must be in same directory than the geometry files) .
- OK
- Use the Tools/Export the material table's textures to .bmp files function.

[http://3doc.i3dconverter.com/](http://3doc.i3dconverter.com/)
## Post #19
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-11-22T13:26:03+00:00
- Post Title: Re: Tales of Fantasy

> Reply from Karpati
>
> The 3D Object Converter v6.0 supports the following formats:

Tales of Fantasy *.QTX texture format

Tales of Fantasy / QQXY *.SM (Load)
Tales of Fantasy / QQXY *.SKEM (Load)

The textured mode will load the .qtx file automatically if it exists in same place as the .sm or .skem file.
(If the model file is 123.skem it will search for the 123_d.qtx file automatically.)

You can export the loaded texture files (bitmap) using the Tools/Export the material table's textures to .bmp files function.


You can add the texture file to the material table by hand using the following procedure:
- open your model
- (Click on the textured view icon)
- click on the Object and Material selector on the toolbar (from right the first icon)
- click on the Materials line
- right click on the Material* line
- browse the texture file. (The texture files must be in same directory than the geometry files) .
- OK
- Use the Tools/Export the material table's textures to .bmp files function.

http://3doc.i3dconverter.com/This game has been a long time, even the official client can not find the download, what we can provide the client to test , thank you
## Post #20
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-11-23T13:24:10+00:00
- Post Title: Re: Tales of Fantasy

> Reply from raykingnihong
>
> Karpati wrote:The 3D Object Converter v6.0 supports the following formats:

Tales of Fantasy *.QTX texture format

Tales of Fantasy / QQXY *.SM (Load)
Tales of Fantasy / QQXY *.SKEM (Load)

The textured mode will load the .qtx file automatically if it exists in same place as the .sm or .skem file.
(If the model file is 123.skem it will search for the 123_d.qtx file automatically.)

You can export the loaded texture files (bitmap) using the Tools/Export the material table's textures to .bmp files function.


You can add the texture file to the material table by hand using the following procedure:
- open your model
- (Click on the textured view icon)
- click on the Object and Material selector on the toolbar (from right the first icon)
- click on the Materials line
- right click on the Material* line
- browse the texture file. (The texture files must be in same directory than the geometry files) .
- OK
- Use the Tools/Export the material table's textures to .bmp files function.

http://3doc.i3dconverter.com/This game has been a long time, even the official client can not find the download, what we can provide the client to test , thank you
weññ buddy if you stop for a moment and go to google, in 5 seconds I found that u.u

[http://www.gamershell.com/download_56486.shtml](http://www.gamershell.com/download_56486.shtml)
[http://www.gamershell.com/download_57814.shtml](http://www.gamershell.com/download_57814.shtml)
[http://www.gamershell.com/download_56758.shtml](http://www.gamershell.com/download_56758.shtml)
[http://www.gamershell.com/download_57664.shtml](http://www.gamershell.com/download_57664.shtml)
[http://www.gamershell.com/download_68836.shtml](http://www.gamershell.com/download_68836.shtml)

[http://www.atomicgamer.com/files/99702/ ... ee-to-play](http://www.atomicgamer.com/files/99702/tales-of-fantasy-full-client-v0-2-180-free-to-play)
[http://www.ausgamers.com/files/download ... ent-v02180](http://www.ausgamers.com/files/download/68046/tales-of-fantasy-closed-beta-client-v02180)

PS: Latest version I found is 0.2.180, but maybe if you keep searching found another new one, have fun.
