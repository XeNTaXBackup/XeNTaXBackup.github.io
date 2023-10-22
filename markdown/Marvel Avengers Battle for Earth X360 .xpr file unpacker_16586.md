## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-07-24T08:28:09+00:00
- Post Title: Marvel Avengers: Battle for Earth X360 .xpr file unpacker

A BMS script and a Noesis script written for the Xbox 360 version of Marvel Avengers: Battle for Earth. 

BMS script for unpacking while Noesis python script for textures handling.

Great thanks to AceWell for his effort on opening textures correctly!  

Note that some files are shared by different .xpr archives so if you're asked what action to take when using the same output path overwrite or just skip them.


 MABfE_Scripts.rar
(1.75 KiB) Downloaded 69 times



An Obj Converter can be found [here](http://forum.xentax.com/viewtopic.php?f=16&t=16931)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-24T18:56:42+00:00
- Post Title: Marvel Avengers: Battle for Earth X360 .xpr file unpacker

> Reply from Bigchillghost
>
> The normal maps always look wrong
could be ATI2 or something
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-07-25T03:46:07+00:00
- Post Title: Marvel Avengers: Battle for Earth X360 .xpr file unpacker

> Reply from AceWell
>
> could be ATI2 or something

Currently I'm only able to handle some simple DXT1 or DXT5 pixel format images and have little knowledge of other stuffs.
Maybe you want to have a look?   
[.xpr samples](http://www.datafilehost.com/d/7931da09)
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-28T20:51:27+00:00
- Post Title: Marvel Avengers: Battle for Earth X360 .xpr file unpacker

ok here is a Noesis python script that can open all the textures in your xpr sample files  


 tex_MarvelAvengersBattleforEarth_X360_xpr.zip
(1.24 KiB) Downloaded 51 times



supports dxt1, dxt5, dxt1 packed normal map, and raw
the script mostly consist of converted parts of your bms script and chrrox's xpr Noesis script here
[viewtopic.php?f=18&t=8102](http://forum.xentax.com/viewtopic.php?f=18&t=8102)


a couple of things:
1. if a texture has transparency, the viewport will always display it and a texture may appear invisible
if the alpha covers the whole image, press F11 to toggle viewport transparency.

2. if you export all the textures from the xpr (or any library), the first texture exported is always named the 
same of the library that contained the image regardless of the name assigned by the script, i think this is 
a long standing quirk of the program and i know no way to correct this either.
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-07-29T04:41:21+00:00
- Post Title: Marvel Avengers: Battle for Earth X360 .xpr file unpacker

> Reply from AceWell
>
> ok here is a Noesis python script that can open all the textures in your xpr sample files
Um, nice script! I bet I can learn a lot about tex formats from this example then. Thanks!

> Reply from AceWell
>
> 2. if you export all the textures from the xpr (or any library), the first texture exported is always named the 
same of the library that contained the image regardless of the name assigned by the script, i think this is 
a long standing quirk of the program and i know no way to correct this either.
I've updated the bms script, and simplified your python script to handle directly .bfe files, where I added the 0x40-byte entry to texture data as their headers.
So this problem is solved now.
