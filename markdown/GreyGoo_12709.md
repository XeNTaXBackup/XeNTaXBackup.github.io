## Post #1
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2015-03-22T15:46:22+00:00
- Post Title: GreyGoo

I try convert this game's models by this posts [viewtopic.php?f=16&t=7303&hilit=alo](http://forum.xentax.com/viewtopic.php?f=16&t=7303&hilit=alo) ,BTW thank chrrox  verymuch!
use that bms script can export model & texture files, textures are dds, models are "ALO"
but I couldn't converted those models by used chrrox's ms script. then I tried NinjaRipper , snaped models + textures were fine.
I upload some sample files ,hope can get some help from mosters,thank U all
[http://www.mediafire.com/download/7q3bm ... sample.zip](http://www.mediafire.com/download/7q3bmvp4229m59k/GreyGoo_sample.zip)




未标题-1.jpg (181.98 KiB) Viewed 239 times
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-22T18:34:54+00:00
- Post Title: GreyGoo

wow!
What a great script made by chrrox!

But updating it really gobbles up my time.  

edit: well, see the main prob: vertex stride of 0x58 is handled as "default", but there are two superfluous "append" lines,
which spoiled the mesh

(hex2obj as a first approach)



ST_Human_Air_tech_00_ext.JPG (196.88 KiB) Viewed 206 times
## Post #3
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-03-25T06:57:31+00:00
- Post Title: GreyGoo

Hi
Here is a script for import rigged and textured models from this game.
It requires Blender version 249 and Python 266.
How to use.
1.double click Blender249.blend
2.in Blender Text Window press alt+p and select :
- gem - for unpack archives . Use for MODELS.MEG and TEXTURES.MEG
- alo - for import rigged and textured models. Use for files from  'ART' folder.

Blender don't like long strings, so when is problem with bone names change line 6: boneNameFlag=1 to boneNameFlag=0 and save blend.
[Blender249[GreyGoo][PC][meg][alo][2015-03-25].zip](https://xentaxbackup.github.io/file/8879_Blender249[GreyGoo][PC][meg][alo][2015-03-25].zip)
## Post #4
- Username: ravage
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 13, 2014 1:39 am
- Post datetime: 2015-08-05T17:35:03+00:00
- Post Title: GreyGoo

> Reply from Szkaradek123
>
> Hi
Here is a script for import rigged and textured models from this game.
It requires Blender version 249 and Python 266.
How to use.
1.double click Blender249.blend
2.in Blender Text Window press alt+p and select :
- gem - for unpack archives . Use for MODELS.MEG and TEXTURES.MEG
- alo - for import rigged and textured models. Use for files from  'ART' folder.

Blender don't like long strings, so when is problem with bone names change line 6: boneNameFlag=1 to boneNameFlag=0 and save blend.

hi is there any scripts that can batch convert EndofNations/GreyGoo ALO models to other format like .X? thanks
## Post #5
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2019-01-24T18:31:28+00:00
- Post Title: GreyGoo

> Reply from Szkaradek123
>
> Hi
Here is a script for import rigged and textured models from this game.
It requires Blender version 249 and Python 266.
How to use.
1.double click Blender249.blend
2.in Blender Text Window press alt+p and select :
- gem - for unpack archives . Use for MODELS.MEG and TEXTURES.MEG
- alo - for import rigged and textured models. Use for files from  'ART' folder.

Blender don't like long strings, so when is problem with bone names change line 6: boneNameFlag=1 to boneNameFlag=0 and save blend.

Hello Szkaradek

Thanks for the script, I have tried it with blender 249 and python 2.6.6, it gets the skeleton but not the mesh and fails with the error "AttributeError: Mesh instance has no attribute 'vertStreamOffset'".

I am guessing that this is due to a change with the game as this happens for any ALO file I try.
See error log below:

```

 512 32768 8
     513 0 16
     514 32768 152
         515 0 160
         518 0 174
     514 32768 242
         515 0 250
         518 0 272
     514 32768 340
         515 0 348
         518 0 373
     514 32768 441
         515 0 449
         518 0 478
     514 32768 546
         515 0 554
         518 0 578
     514 32768 646
         515 0 654
         518 0 678
     514 32768 746
         515 0 754
         518 0 780
     514 32768 848
         515 0 856
         518 0 886
     514 32768 954
         515 0 962
         518 0 987
     514 32768 1055
         515 0 1063
         518 0 1088
     514 32768 1156
         515 0 1164
         518 0 1186
     514 32768 1254
         515 0 1262
         518 0 1284
     514 32768 1352
         515 0 1360
         518 0 1384
     514 32768 1452
         515 0 1460
         518 0 1484
     514 32768 1552
         515 0 1560
         518 0 1589
     514 32768 1657
         515 0 1665
         518 0 1694
     514 32768 1762
         515 0 1770
         518 0 1798
     514 32768 1866
         515 0 1874
         518 0 1899
     514 32768 1967
         515 0 1975
         518 0 2005
     514 32768 2073
         515 0 2081
         518 0 2111
     514 32768 2179
         515 0 2187
         518 0 2217
     514 32768 2285
         515 0 2293
         518 0 2322
     514 32768 2390
         515 0 2398
         518 0 2424
     514 32768 2492
         515 0 2500
         518 0 2531
     514 32768 2599
         515 0 2607
         518 0 2627
     514 32768 2695
         515 0 2703
         518 0 2734
     514 32768 2802
         515 0 2810
         518 0 2834
     514 32768 2902
         515 0 2910
         518 0 2930
     514 32768 2998
         515 0 3006
         518 0 3046
     514 32768 3114
         515 0 3122
         518 0 3143
     514 32768 3211
         515 0 3219
         518 0 3235
 1024 32768 3303
     1025 0 3311
     1028 0 3332
     1029 0 3353
     65792 32768 3489
         65793 0 3497
         65798 0 3527
         65798 0 3565
         65798 0 3604
         65798 0 3647
         65798 0 3684
         65797 0 3722
         65795 0 3778
         65797 0 3813
         65797 0 3867
         65798 0 3918
         65795 0 3960
         65795 0 3996
         65797 0 4037
         65795 0 4089
         65795 0 4123
         65795 0 4151
         65795 0 4179
     65536 32768 4209
         65537 0 4217
         65538 0 4233
         65546 3 4266
         65540 0 206834
         65542 0 223966
 1024 32768 224070
     1025 0 224078
     1028 0 224097
     1029 0 224118
     65792 32768 224254
         65793 0 224262
         65798 0 224289
     65536 32768 224324
         65537 0 224332
         65538 0 224348
         65546 0 224368
         65540 0 224952
         4608 32768 225032
             4609 0 225040
             4610 0 225102
             4611 0 225240
 1536 32768 225272
     1537 0 225280
     1538 0 225365
     1538 0 225385
     25 32768 225405
         26 0 225413
     25 32768 225452
         26 0 225460
   BaseTexture ve_human_godel_00_diff_00.dds
e:\steam\steamapps\common\greygoo\data\data\art\textureshdr\srgb\ve_human_godel_00_diff_00.dds False
   SpecularTexture ve_human_51_01_spec.dds
e:\steam\steamapps\common\greygoo\data\data\art\textureshdr\srgb\ve_human_51_01_spec.dds False
   EmissiveTexture fx_glowscroll_03.dds
   NormalTexture ve_human_51_01_norm.dds
e:\steam\steamapps\common\greygoo\data\data\art\textureshdr\linear\ve_human_51_01_norm.dds False
alD3dVertB4I4NU2U3U3U2C
alD3dVertN
Traceback (most recent call last):
  File "greygoo.py", line 310, in openFile
  File "greygoo.py", line 291, in Parser
  File "greygoo.py", line 219, in decParser
AttributeError: Mesh instance has no attribute 'vertStreamOffset'

```
