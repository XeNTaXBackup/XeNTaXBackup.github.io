## Post #1
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2017-07-18T10:14:49+00:00
- Post Title: Terminator 2 3D Chinese Mobile game format

Hey all,

 Well this weird chinese only mmorpg based off the terminator has finally been released to the general public (of china) I found a copy and cracked her apk open.

THIS ISN'T UNITY. as the website states it's a "self-developed 3D engine NeoX"   and so while a lot of data is downloaded when you boot up the apk on your android device (or emulator) seems the games basic assets are in the .apk itself.

 now the format in the file I am providing is ".npk" and again this is a new mobile game engine so I don't know what all to expect. but I have things like vehicles,props and weapons that are also all ".npk" I'd be interested to see if anyone can crack this format so I can look at the assets in like a 3d max or something. anyways here is the file and thank you all for your time.

[http://www.mediafire.com/file/dbf2cup21 ... racter.zip](http://www.mediafire.com/file/dbf2cup21hs7s34/character.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-18T16:17:29+00:00
- Post Title: Terminator 2 3D Chinese Mobile game format

you can unpack the npk with this bms script 
[http://aluigi.altervista.org/bms/nxpk.bms](http://aluigi.altervista.org/bms/nxpk.bms)

and some of those dat files look like they have models, this is from 000000a2.dat  



000000a2_dat.png (46.33 KiB) Viewed 452 times



edit
run this bms script on the extracted files to give a meaningful extension to the ktx textures and meshes

```
get NAME filename
get MAGIC long
if MAGIC == 0x58544bab
	string NAME - dat
	string NAME + ktx
	log NAME 0 SIZE
elif MAGIC == 0xbbc88034
	string NAME - dat
	string NAME + mesh
	log NAME 0 SIZE
endif

```

the Mali Texture Compression tool can open the ktx textures
[https://developer.arm.com/products/soft ... ssion-tool](https://developer.arm.com/products/software-development-tools/graphics-development-tools/mali-texture-compression-tool)
## Post #3
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-07-18T17:48:16+00:00
- Post Title: Terminator 2 3D Chinese Mobile game format

The 3D Object Converter v6.510 supports the NeoX Engine .MESH / .GIM / .MTG files.

How to get the 3D Object Converter v6.510 (currently v6.514):

Please download the 3D Object Converter from [http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v6.514.


I attached some converted files.
[mesh_to_obj.zip](https://xentaxbackup.github.io/file/13115_mesh_to_obj.zip)
## Post #4
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2017-07-19T01:15:04+00:00
- Post Title: Terminator 2 3D Chinese Mobile game format

This why I love this community the most. all of you tend to actually help people and be friendly about. I don't wish to go into why that means so much to me lately but I just want to take the time to say thanks and that I am greatful for this community and it's contributors. I'll work with the tools you guys have suggested and Objectconverter is on my list to buy so that I can use it to it's full potential so thanks for the heads up on all this it's greatly appreciated.
## Post #5
- Username: Aldo Pratama P
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 07, 2017 2:44 pm
- Post datetime: 2017-12-07T06:57:02+00:00
- Post Title: Terminator 2 3D Chinese Mobile game format

Hy All,

Sorry For My Bad English...
The Game Is Strong Graphic 

i try search the data on my internal storage(Android).
yeah actually i find the ".npk' files from internal storage.

but my problem is when i play the game, is not to smooth graphic or lag.
hopefully can i edit npk files.
so, can i edit the ".npk' files?
what tools recommended for open or edit npk files?
like an effect grass or something else like effect/graphic.

Thanks Before
