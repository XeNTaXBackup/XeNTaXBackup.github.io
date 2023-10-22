## Post #1
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-06-13T18:30:20+00:00
- Post Title: [UNITY] Mu archangel encrypted assets

Download apk: [https://full-ggp.mua.webzen.com/2021051 ... .0.1_2.apk](https://full-ggp.mua.webzen.com/20210513/signed_gxs_jpnandroidtrd_live_2.0.1_2.apk)

This is a mobile game that seems to use unity. I was able to load and extract textures with AssetStudio. Anyway I was not able to load models and animation that have not the classic Unity Header, nor have it somewhere...( enctrypted?   ).

Here samples, wish someone could take a look  

[https://www.mediafire.com/file/sh8xjzjv ... e.rar/file](https://www.mediafire.com/file/sh8xjzjv4unhllr/sample.rar/file)
## Post #2
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-06-15T16:57:34+00:00
- Post Title: [UNITY] Mu archangel encrypted assets

up
## Post #3
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2021-06-16T01:26:11+00:00
- Post Title: [UNITY] Mu archangel encrypted assets

pre_baishizi_v4.png (98.19 KiB) Viewed 167 times
## Post #4
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-06-16T14:49:26+00:00
- Post Title: [UNITY] Mu archangel encrypted assets

> Reply from reh ↑Wed Jun 16, 2021 9:26 am at Wed Jun 16, 2021 9:26 am
>
> 

Thanks reh for taking a look and answering. Since the game use unity I wish/hope to get skeletal mesh and animations for modding purposes, that oc means to have a decrypter and someone willing to work on it. I know there are plenty of Mu mobile game whose assets are rippable and this request sounds more like a whim than a need; by the way the models of this game were remade and have a better quality compared to previous Mu mobile. 

Anyway if it won't happen I will consider getting at least static mesh such as weapon,wing and objects with ME.
## Post #5
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-06-17T13:49:09+00:00
- Post Title: [UNITY] Mu archangel encrypted assets

Here some little news ( Thanks to Ekey ) :

Animations seems to use zlib compression , offzip works well with them although decompressed files cannot be loaded in AssetStudio that doesn't recognize them. 

Decompressed animation header:
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-06-23T17:23:32+00:00
- Post Title: [UNITY] Mu archangel encrypted assets

pre_baishizi.jpg (78.97 KiB) Viewed 104 times
## Post #7
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-06-25T18:29:24+00:00
- Post Title: [UNITY] Mu archangel encrypted assets

I have added the MU Archangel .37 file format loader module to the following programs:

- 3D Object Converter v8.008	(Windows)
- i3DConverter v4.005		(macOS)
- i3DConverter v2.005		(Linux)

How to get the 3D Object Converter v8.008:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v8.008.

How to get the i3DConverter macOS v4.005:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v4.005.

How to get the i3DConverter Linux v2.005:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v2.005.


The .37 file has not references to the external texture files, that is why I can’t assign it to the material table.


You can add the texture file to the material table by hand using the following procedure

- open your 3d model (file)
- click on the Object, Bone, Material selector on the toolbar (from right the 1st icon on the toolbar)
- click on the Materials line
- right click on the Material* line
- browse the texture file. (The texture files must be in same directory than the geometry files) .
- OK

- (Click on the textured view icon.)
