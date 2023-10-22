## Post #1
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2014-12-02T14:15:25+00:00
- Post Title: Gamebryo 2.6

Hi guys,

Has anyone had success in importing models/animations version 2.6? Unfortunately NifTools only supports version 2.3 (maybe 2.5) and can not import version 2.6

I have the original source code of the export plugin version 2.6, maybe it is useful for any scripter 3d?

Thanks,
Good Alfternoon!
## Post #2
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-02T17:56:03+00:00
- Post Title: Gamebryo 2.6

> Reply from ilovechii
>
> Hi guys,

Has anyone had success in importing models/animations version 2.6? Unfortunately NifTools only supports version 2.3 (maybe 2.5) and can not import version 2.6

I have the original source code of the export plugin version 2.6, maybe it is useful for any scripter 3d?

Thanks,
Good Alfternoon!
please click here：[viewtopic.php?f=16&t=12219](http://forum.xentax.com/viewtopic.php?f=16&t=12219)
## Post #3
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2014-12-02T18:14:03+00:00
- Post Title: Gamebryo 2.6

I Think Name of the Games is ( Devilian ).

and yeah. Noesis can't Import This Game.

To Baaaaaad......

Here Sample.

[www.mediafire.com/download/eu25f09i48wmdrt](http://www.mediafire.com/download/eu25f09i48wmdrt)
## Post #4
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2014-12-02T19:27:17+00:00
- Post Title: Gamebryo 2.6

> Reply from raykingnihong
>
> ilovechii wrote:Hi guys,

Has anyone had success in importing models/animations version 2.6? Unfortunately NifTools only supports version 2.3 (maybe 2.5) and can not import version 2.6

I have the original source code of the export plugin version 2.6, maybe it is useful for any scripter 3d?

Thanks,
Good Alfternoon!
please click here：viewtopic.php?f=16&t=12219

@raykingnihong
It does not work properly.

Example: [https://mega.co.nz/#!appiWIKJ!BaEmyw5FU ... 1kcEBnSRQ0](https://mega.co.nz/#!appiWIKJ!BaEmyw5FUrWS5kIj7aD-XHo-7ZM09pFBZ1kcEBnSRQ0)
## Post #5
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-03T08:37:49+00:00
- Post Title: Gamebryo 2.6

> Reply from ilovechii
>
> raykingnihong wrote:ilovechii wrote:Hi guys,

Has anyone had success in importing models/animations version 2.6? Unfortunately NifTools only supports version 2.3 (maybe 2.5) and can not import version 2.6

I have the original source code of the export plugin version 2.6, maybe it is useful for any scripter 3d?

Thanks,
Good Alfternoon!
please click here：viewtopic.php?f=16&t=12219

@raykingnihong
It does not work properly.

Example: https://mega.co.nz/#!appiWIKJ!BaEmyw5FU ... 1kcEBnSRQ0I also tested the game, is the new NIF format, there is no tool support, I suggest you build a Devilian game-themed, or everybody does not know is that the game, files cannot be tested. There is a sample file to upload, a total test
## Post #6
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-04T15:39:05+00:00
- Post Title: Gamebryo 2.6

Hi

Here is importer for models from Devilian game for blender users.
It requires Blender version 249 and Python 26.

Steps:
1.    unpack importer

2.    run Blender249.blend

3.    in Text Window press alt+p  and select nif file with 'base' name (filesize < 100kb)
It creates armature object with name 'pose'

4.    alt+p and select nif file with model. (file size > 100kb)
It creates meshes with "number" names and armatures with 'bind+number' names.

Now check, if rig is the same then parents all meshes to armature 'pose'.
If not: repeat all steps but first import models and than file with 'base' name
It should adjust meshes to armature 'pose'. 
Now parents meshes to 'pose' armature and delete all "bind" objects.

The game use nif version 20.6.0.1 and 20.6.0.2.
There are differences in NiMesh section and NiNode vs. 20.6.0.0.
Sorry for my bad english.
[Blender249[Devilian][PC][nif][2014-12-04].zip](https://xentaxbackup.github.io/file/8196_Blender249[Devilian][PC][nif][2014-12-04].zip)
## Post #7
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-05T07:07:05+00:00
- Post Title: Gamebryo 2.6

> Reply from Szkaradek123
>
> Hi

Here is importer for models from this game for blender users.
It requires Blender version 249 and Python 26.

Steps:
1.    unpack importer

2.    run Blender249.blend

3.    in Text Window press alt+p  and select nif file with 'base' name (filesize < 100kb)
It creates armature object with name 'pose'

4.    alt+p and select nif file with model. (file size > 100kb)
It creates meshes with "number" names and armatures with 'bind+number' names.

Now check, if rig is the same then parents all meshes to armature 'pose'.
If not: repeat all steps but first import models and than file with 'base' name
It should adjust meshes to armature 'pose'. 
Now parents meshes to 'pose' armature and delete all "bind" objects.

The game use nif version 20.6.0.1 and 20.6.0.2.
There are differences in NiMesh section and NiNode vs. 20.6.0.0.
Sorry for my bad english.Hello my friend, I tested the script runs perfectly, thank you very much for your help.
## Post #8
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2014-12-05T13:04:27+00:00
- Post Title: Gamebryo 2.6

@Szkaradek123
It works with my examples? I can import animations too?
## Post #9
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-05T13:24:19+00:00
- Post Title: Gamebryo 2.6

Hi 

@ilovechii
Use Noesis. You can import animations too. [http://www.richwhitehouse.com/index.php ... ojects.php](http://www.richwhitehouse.com/index.php?content=inc_projects.php)

Blender importer is for Devilian game(and works with nif version 20.6.0.1 and 20.6.0.2).
## Post #10
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2014-12-05T14:09:14+00:00
- Post Title: Gamebryo 2.6

@Szkaradek123
Hi,

I have a problem, texture of models are in .nif too and animations does not work correctly.

Thanks.
## Post #11
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-05T14:27:59+00:00
- Post Title: Gamebryo 2.6

@ilovechii

Please say, what game are models from and  which models you want to import ?
## Post #12
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2014-12-05T14:34:35+00:00
- Post Title: Gamebryo 2.6

@Szkaradek123

IRIS Online - using Gamebryo Version 20.6.0.0
## Post #13
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-06T09:01:30+00:00
- Post Title: Gamebryo 2.6

Hi

Here is importer for textured models from Iris Online game for blender users.
It requires Blender version 249 and Python 26.

Animations are not supported. They are too difficult for me.


It was tested on monster.pack and npc.pack
I can't unpack character.pack.

Steps:
1. unpack importer
2. run Blender249.blend
3. in Blender Text Window press alt+p and select  nif file.
4. else wrong please use Noesis for bind posed models
[Blender249[IrisOnline][PC][nif][2014-12-05].zip](https://xentaxbackup.github.io/file/8206_Blender249[IrisOnline][PC][nif][2014-12-05].zip)
## Post #14
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2014-12-06T11:47:21+00:00
- Post Title: Gamebryo 2.6

@Szkaradek123
I have source code of the plugins maya/max to export (real plugins GB 2.6), maybe this can help you?
## Post #15
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2016-08-18T11:22:52+00:00
- Post Title: Gamebryo 2.6

@Szkaradek123

It seems Devilian english version changed it's format a bit.I tested the latest version of Devilian with your Blender script.
With Blender 2.49 32 bit.
Python 2.62 32 bit.

I got error message like this


the latest Devilian Gamebryo version shows it's 2.6.0.2
I also tried latest version of blender with nightly dev build plugin,but no luck.It's still not supporting this game yet.

[http://niftools.sourceforge.net/forum/v ... =13&t=5823](http://niftools.sourceforge.net/forum/viewtopic.php?f=13&t=5823)

Latest Devilian samples.(english version)
[https://www.sendspace.com/file/7mmapp](https://www.sendspace.com/file/7mmapp)

If you have time please look it,TYVM.
## Post #16
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-08-18T12:07:34+00:00
- Post Title: Re: Gamebryo 2.6

it normal
## Post #17
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2016-08-18T13:16:37+00:00
- Post Title: Re: Gamebryo 2.6

@godskin

TYVM for testing,I found the problem.
The script works fine.
## Post #18
- Username: Ravio
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 18, 2016 8:04 pm
- Post datetime: 2016-09-30T19:41:58+00:00
- Post Title: Re: Gamebryo 2.6

Hey friends from Xentax ! (first of all sorry for my english it's not my native tongue) 

I've just download and umpack Devilian files and now i try to open .nif files in blender from the last version of Devilian. I've try with two differents ways but none of them works :

-One with the last niftool plugin for blender (2.76) but when i try to import a .nif file i've a traceback error in some lines (ex : "NIF version 20.6.0.2 not supported" )


-The one with Szkaradek123's .nif importer, but this time the python script fail... 

Can somone explain me step by step the way to read devilian .nif in blender ? 

@falconcool 

> the latest Devilian Gamebryo version shows it's 2.6.0.2
>
> I also tried latest version of blender with nightly dev build plugin,but no luck.It's still not supporting this game yet.
>
> 
>
> http://niftools.sourceforge.net/forum/v ... =13&t=5823
>
> 
>
> Latest Devilian samples.(english version)
>
> https://www.sendspace.com/file/7mmapp
>
> 
>
> If you have time please look it,TYVM.

I think i've the same problem as you, can you explain me your solution ? TYVM !
## Post #19
- Username: Ravio
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 18, 2016 8:04 pm
- Post datetime: 2016-10-01T13:47:05+00:00
- Post Title: Re: Gamebryo 2.6

Ok i've found a way (the only one i know) to extract .nif files from DO. (In fact to open .nif files in blender and export as .dae / .obj / .3ds).

First of all many thanks to Szkaradek123 for his importer. Before begin you need to have :

-Devilian Online
-Devilian Online PKG unpacker
-Python 2.5.2 (in 32 or 64 bits)
-Blender 2.49 (in 32 or 64 bits)
-Szkaradek123's Blender .nif importer

For Blender and Python make sure your system is in 32 or 64 bits and instal the right one. Maybe you'll need to uninstall newest version of Blender or Phython. For me that's why Szkaradek123's importer don't works.

1 / Download and Instal Blender 2.49 & Python 2.5.2 (old versions are available for both of them on their respective website)

2 / Download Szkaradek123's Blender .nif importer

3 / Download Devilian Online and Devilian Online PKG unpacker

4 / With Devilian Online PKG unpacker unpack .idx files, then it will create a directory and subdirectory for each .idx with .nif inner

5 / Open Szkaradek123's Blender .nif importer and check if the python consol is righ

6 / Now import .nif with ALT + P, choose a .nif file and open it with ENTER

7 / Export it to extension of your choice (.dae / .obj / .3ds)

Sorry for my bad language skills
## Post #20
- Username: benjamin77
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Apr 17, 2020 12:01 am
- Post datetime: 2020-07-04T12:45:36+00:00
- Post Title: Re: Gamebryo 2.6

> Reply from godskin ↑Thu Aug 18, 2016 8:07 pm at Thu Aug 18, 2016 8:07 pm
>
> 
it normal

Hello guys, I want to ask a question about importing nif from Devilian
I installed Blender 249 and Python 26.
Starting the blender and using the script to open the nif is invalid, do you have a way?
This is the sample file I provided, thank you

[https://drive.google.com/file/d/1_3dDuX ... sp=sharing](https://drive.google.com/file/d/1_3dDuXq_dHZii8WKHplKH9cHVKGCM0vF/view?usp=sharing)
[https://drive.google.com/file/d/1KRRlLU ... sp=sharing](https://drive.google.com/file/d/1KRRlLU-Op3bglJ9gpG3Au4haeBILIR97/view?usp=sharing)
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-07-04T14:14:11+00:00
- Post Title: Re: Gamebryo 2.6

> Reply from blackwaltzcq ↑Sat Jul 04, 2020 8:45 pm at Sat Jul 04, 2020 8:45 pm
>
> 
Hello guys, I want to ask a question about importing nif from Devilian
I installed Blender 249 and Python 26.
Starting the blender and using the script to open the nif is invalid, do you have a way?
This is the sample file I provided, thank youWith window 7 and later you have to copy the newGameLib folder into your blender directory.
.



NPC_Dragon-nif.png (95.19 KiB) Viewed 113 times
## Post #22
- Username: benjamin77
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Apr 17, 2020 12:01 am
- Post datetime: 2020-07-06T06:38:41+00:00
- Post Title: Re: Gamebryo 2.6

> Reply from shakotay2 ↑Sat Jul 04, 2020 10:14 pm at Sat Jul 04, 2020 10:14 pm
>
> 
blackwaltzcq wrote: ↑Sat Jul 04, 2020 8:45 pm
Hello guys, I want to ask a question about importing nif from Devilian
I installed Blender 249 and Python 26.
Starting the blender and using the script to open the nif is invalid, do you have a way?
This is the sample file I provided, thank youWith window 7 and later you have to copy the newGameLib folder into your blender directory.
.
NPC_Dragon-nif.png

shakotay2 you are awesome! solved!
## Post #23
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-07-14T13:11:35+00:00
- Post Title: Re: Gamebryo 2.6

> Reply from blackwaltzcq ↑Sat Jul 04, 2020 8:45 pm at Sat Jul 04, 2020 8:45 pm
>
> 
Hello guys, I want to ask a question about importing nif from Devilian
I installed Blender 249 and Python 26.
Starting the blender and using the script to open the nif is invalid, do you have a way?
This is the sample file I provided, thank you

Hi, could it be possible to upload a client of Devilian? The game was closed and I cannot find it.
