## Post #1
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2010-01-14T19:39:10+00:00
- Post Title: Clive Barker's Jericho Sm3+Psx model files

I've been trying to open Jericho model files for a while now. I strongly presume that it comes in two files - sm3 and psx. 
The sm3 seems to define the lod group, textures and most likely the mesh data itself.
The psx seems to be probably attached to the animation files which are cm3's

There also seem to be Lod versions of the sm3 - lod 2 and 3

Already tried the default sm3 application but that was a bogus direction. Any help in loading them would extremely welcome.
The files in question
Sm3 - [http://localhostr.com/files/137bea/cole.sm3](http://localhostr.com/files/137bea/cole.sm3)
Psx - [http://localhostr.com/files/cf35b4/cole.pxs](http://localhostr.com/files/cf35b4/cole.pxs)
cm3 - [http://localhostr.com/files/11eb55/cole_duckrelax1.cm3](http://localhostr.com/files/11eb55/cole_duckrelax1.cm3)
## Post #2
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2010-01-16T21:54:24+00:00
- Post Title: Clive Barker's Jericho Sm3+Psx model files

if anyone wants, I got the sm3 files out already. sadly I don't seem to recognise anything but what I presume is a linked bone structure in the hex.

assuming that that starts here

```

```


Before that there's a segment that that seems to list the textures and their attributes, interestingly in bmp while the original is in dds.

MD3D - I presume this indicates that a part of it was captured via laser scanning? 
LVfv - this segment tends to show up in the bone data as well

There's also a couple of interesting parts like this
CH_Cole_Cabeza-ojo_R.....Bip Cole Head
000e000000


That 000e000000 segment seems to be repeated pretty often. Always between what looks like a model part name and a bone name (cabeza is head in spanish, ojo eye, R should be selfexplanatory)

EDIT 
make that almost definitely a link between two bones as seen here Bip Cole L Finger2.....Bip Cole L Hand

moving onto normal mesh data?

This segment is getting repeated all the time there, every three lines to be precise
?..€?.. @..............€?............H

[3F 00 00 80 3F 00 00 A0 40 00 00 00 00 00 00 00 00 00 00 00 00 00 00 80 3F 00 00 00 00 00 00 00 00 00 00 00 00 48]

Overall this line seems to be on a constant repeat
80 3F 00 00 00 00

I'm not exactly sure where the bone data ends though

Hopefully it will ring a bell for someone
## Post #3
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-12-03T20:24:04+00:00
- Post Title: Clive Barker's Jericho Sm3+Psx model files

You can download the converted file using the following link
[url]http://kz_3d.tvn.hu/jericho_cole.sm3_to_obj.zip[/url]

I installed the Clive_Barker_s_Jericho_demo_single.exe (PC) demo and I extracted the Data00.packed file (about 271 MB) with the Quickbms script.
I googled into the .sm3 (and other) files and these are seems to be compressed or coded.

Can you tell me how did you get your .sm3 file ?
## Post #4
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2010-12-04T05:13:46+00:00
- Post Title: Clive Barker's Jericho Sm3+Psx model files

I have been waiting for these .sm3 files for some time now also,

I remember awhile back using gobread utility to extract all the sm3, dds cm3 data out.

this is exactly what I did:

To Extract files Navigate to folder where gobread and the *.packed file is and type

GOBREAD.exe Data00.packed  hit ENTER (Data00.packed contains the models, textures and their animations).

In DOS navigate to the dds folder and Batch rename all textures from .dds1 to .dds to have correct texture format.
i.e. rename *.dds1 *.dds

mesh and animation format yet to be discovered! 

Please if anyone discovers how to convert .sm3 to .obj (Church & Black especially) please do tell
## Post #5
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-12-05T11:58:43+00:00
- Post Title: Clive Barker's Jericho Sm3+Psx model files

Thank you for your tip, but unfortunately it did not help me.

The gobread.exe  it runs only 32bit OS only. I have a Vista 64bit OS at home and I did try to run the gobread.exe under dosbox emulator, but it did not work correctly. I did find an other Quickbms script and I extracted the files with it correctly.

I added the Mercury Steam Engine (Clive Barker's Jericho; Scrapland) *.msh loader module to the 3D Object Converter I released the v4.4432 now.

You can update your installed application (version>=4.0) quickly and easily using the auto-update function (Help/Check for updates…).
## Post #6
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2010-12-06T11:26:45+00:00
- Post Title: Clive Barker's Jericho Sm3+Psx model files

Wow, this is great will try this out now 

It Works Yeah!

I just donated to 3D Object Converter
## Post #7
- Username: Koshak
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 07, 2011 5:27 am
- Post datetime: 2011-01-08T11:58:00+00:00
- Post Title: Clive Barker's Jericho Sm3+Psx model files

After convert lost UV Map  in mesh model   3d object converter support UV Map convert?
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-01-08T12:28:54+00:00
- Post Title: Clive Barker's Jericho Sm3+Psx model files

> 3d object converter support UV Map convert?

Absolutely.

You can download the converted file using the following link
[url]http://kz_3d.tvn.hu/jericho_cole.sm3_to_obj.zip[/url]
## Post #9
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-01-22T22:04:19+00:00
- Post Title: Clive Barker's Jericho Sm3+Psx model files

The contents of this post was deleted because of possible forum rules violation.
[jerycho.jpg](https://xentaxbackup.github.io/file/3832_jerycho.jpg)
## Post #10
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-01-24T08:17:00+00:00
- Post Title: Clive Barker's Jericho Sm3+Psx model files

Szkaradek123, as always very good work!
and i have a 2 questions:

1 - can i use this script for converting other sm3 models, from castlevania and robots?
2 - how i can convert models from blender to 3ds max, for me:
    - dae_v1.3 - max crash
    - dae_v1.4 - no skin modifier
    - fbx - max crash
    - smd - need to exporting only in one mesh i supposed (but how?)
    - psk - need to exporting only in one mesh i supposed
    - i don't know any more way..
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2011-01-24T13:00:49+00:00
- Post Title: Clive Barker's Jericho Sm3+Psx model files

I do not know everything should work fine, I export to fbx, and all is well.
Thank you Szkaradek123!
[jericho.JPG](https://xentaxbackup.github.io/file/3837_jericho.JPG)
## Post #12
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2011-02-20T10:06:04+00:00
- Post Title: Clive Barker's Jericho Sm3+Psx model files

Any idea what's wrong...   

[](http://img121.imageshack.us/i/94883384.jpg/)

Same for Cole and Church and others...
## Post #13
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-02-20T11:50:12+00:00
- Post Title: Clive Barker's Jericho Sm3+Psx model files

The contents of this post was deleted because of possible forum rules violation.
[black.jpg](https://xentaxbackup.github.io/file/3950_black.jpg)
## Post #14
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2011-02-20T20:57:19+00:00
- Post Title: Clive Barker's Jericho Sm3+Psx model files

Well the PC version I own, this is how my Black folder looks

 

Tested the one you upload it, works fine, but what I have doesn't ... wtf?  

Edit : Tried by creating another folder just like yours, sm3 and .blend script but still the same error as above.
## Post #15
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-02-20T21:44:23+00:00
- Post Title: Clive Barker's Jericho Sm3+Psx model files

Use  gobread.exe to unpack game data.
If still dosn't work ,please send me your black.sm3 file.
## Post #16
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2011-02-23T07:22:47+00:00
- Post Title: Re: Clive Barker's Jericho Sm3+Psx model files

Well I used a bms script to unpack the files, since gobread.exe doesn't work for me, I'm on Win7x64 and doesn't support x64...

About your Black model, how I can texture the model, since the files are .dds1, tryied to rename them into .dds didn't work, also not opening in Photoshop.
## Post #17
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2021-01-11T03:08:31+00:00
- Post Title: Re: Clive Barker's Jericho Sm3+Psx model files

Can anyone share the max script that was shared? The link was removed for some reason.
## Post #18
- Username: timtim
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 21, 2012 2:49 am
- Post datetime: 2021-01-17T21:38:06+00:00
- Post Title: Re: Clive Barker's Jericho Sm3+Psx model files

> Reply from kingfisher13 ↑Mon Jan 11, 2021 11:08 am at Mon Jan 11, 2021 11:08 am
>
> 
Can anyone share the max script that was shared? The link was removed for some reason.

bump and vote for this. It would be great to have that Max or Blender script.
## Post #19
- Username: Glaster
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 10, 2022 11:26 pm
- Post datetime: 2022-04-17T10:15:11+00:00
- Post Title: Re: Clive Barker's Jericho Sm3+Psx model files

So, here's the .smd importing script for blender. Warning: this script is supported only by old Blender versions, because new Blender versions are using Python 3 for scripting, current script was coded with Python 2. 



And anybody knows, how to import .cm3 animations into blender? or convert them to .smd (HL/CS 1.6 etc) format?
[jericho_import.7z](https://xentaxbackup.github.io/file/22088_jericho_import.7z)
## Post #20
- Username: satsubatsu347
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 04, 2021 8:36 am
- Post datetime: 2022-05-03T03:17:04+00:00
- Post Title: Re: Clive Barker's Jericho Sm3+Psx model files

> Reply from Glaster ↑Sun Apr 17, 2022 6:15 pm at Sun Apr 17, 2022 6:15 pm
>
> 
So, here's the .smd importing script for blender. Warning: this script is supported only by old Blender versions, because new Blender versions are using Python 3 for scripting, current script was coded with Python 2. 



And anybody knows, how to import .cm3 animations into blender? or convert them to .smd (HL/CS 1.6 etc) format?

I can not get the plugin to work. Returns errors every time. Any ideas how to fix the problem?
I am running Blender 2.49.2 as in the example.

Console Readout:

====================================
Ababanili.sm3
====================================
(-421075456, -256, -867418624)
(-107081312.0, 2.8586488672226268e-43, 0.0, 5.6051938572992683e-45, 9.1842502650312836e-41, 2.5713938924237539e-38, 1.4012984643248171e-45, 5.6051938572992683e-45, 0.0, 12972196864.0, 0.0, 0.0, 4.2038953929744512e-45, 1.765732498352638e+22, 2.2139230726470061e-10)
num_mat = 1918986307
Traceback (most recent call last):
  File "import-jerycho-2011-0", line 421, in <module>
  File "import-jerycho-2011-0", line 313, in readdata
  File "import-jerycho-2011-0", line 207, in read_materials
MemoryError
## Post #21
- Username: Glaster
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 10, 2022 11:26 pm
- Post datetime: 2022-05-10T11:28:50+00:00
- Post Title: Re: Clive Barker's Jericho Sm3+Psx model files

Hm, did you try to use this converter with other models? Maybe something is wrong only with this one?
## Post #22
- Username: satsubatsu347
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 04, 2021 8:36 am
- Post datetime: 2022-05-10T22:35:19+00:00
- Post Title: Re: Clive Barker's Jericho Sm3+Psx model files

Yes, here are 4 more outputs.

====================================
arnold.sm3
====================================
(1096763459, 1819242098, 1816223588)
Traceback (most recent call last):
  File "import-jerycho-2011-0", line 421, in <module>
  File "import-jerycho-2011-0", line 309, in readdata
MemoryError

====================================
black.sm3
====================================
(1, 1398476032, 1919250549)
Traceback (most recent call last):
  File "import-jerycho-2011-0", line 421, in <module>
  File "import-jerycho-2011-0", line 309, in readdata
MemoryError

====================================
ross.sm3
====================================
(1663984489, 778396277, 7368034)
Traceback (most recent call last):
  File "import-jerycho-2011-0", line 421, in <module>
  File "import-jerycho-2011-0", line 311, in readdata
  File "import-jerycho-2011-0", line 13, in word
MemoryError

====================================
murielgreen.sm3
====================================
(1212364800, 1920290143, 543974761)
Traceback (most recent call last):
  File "import-jerycho-2011-0", line 421, in <module>
  File "import-jerycho-2011-0", line 309, in readdata
MemoryError
