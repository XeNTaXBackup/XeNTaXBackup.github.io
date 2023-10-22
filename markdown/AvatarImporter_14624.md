## Post #1
- Username: robertshatty
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 09, 2016 1:54 pm
- Post datetime: 2016-07-09T17:16:05+00:00
- Post Title: AvatarImporter

How to use this blender script to load Avatar *.xbg models ??
## Post #2
- Username: robertshatty
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 09, 2016 1:54 pm
- Post datetime: 2016-07-09T17:24:13+00:00
- Post Title: AvatarImporter

Ooops ..continue this post from here
[viewtopic.php?f=16&t=4310&start=15](http://forum.xentax.com/viewtopic.php?f=16&t=4310&start=15)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-09T18:10:22+00:00
- Post Title: AvatarImporter

> Reply from robertshatty
>
> How to use this blender script to load Avatar *.xbg models ??Susposed you mean the script Avatar.py from the post as of Sun May 23, 2010 1:59 pm (updated last year) in your linked thread

> How use:
>
> 1. install Blender version 249b and Python version 26
>
> [unzip Avatar[PC].zip]
>
> 2. doubleclick file "Blender[...].blend" 
>
> 3. press alt+p in Blender Text Window and select [a model file]
When using Win7 and higher you might be required to copy the newGameLib folder into the folder where the blender.exe resides.

btw: use the edit button to avoid double postings
## Post #4
- Username: robertshatty
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 09, 2016 1:54 pm
- Post datetime: 2016-07-10T06:52:15+00:00
- Post Title: AvatarImporter

```
ImportError : No module named newGameLib
```
## Post #5
- Username: robertshatty
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 09, 2016 1:54 pm
- Post datetime: 2016-07-10T07:20:43+00:00
- Post Title: AvatarImporter

ImportError issue solved by setting PYTHONPATH to 
C:\Python26;C:\Python26\DLLs;C:\Python26\Lib;C:\Python26\LIB\Lib\lib-tk

now some model is not loading proper & getting python error

```
Checking for installed Python... got it!
--------------------------------------------------
--------------------------------------------------
E:\\James Cameron AVATAR THE GAME\ExtractPAK\gra
phics\av_vehicles_corp\scorpion\scorpion_pilotable.xbg
--------------------------------------------------
--------------------------------------------------
chunk: LTMR 44 (1, 425)
E:\\James Cameron AVATAR THE GAME\ExtractPAK\GRA
PHICS\_MATERIALS\SDORE-M-2009032051553103.xbm
DiffuseTexture1
0 E:\\James Cameron AVATAR THE GAME\ExtractPAK\g
raphics\av_vehicles_corp\dove_drivable\_textures\vehicle_light_halo_d.dds
E:\\James Cameron AVATAR THE GAME\ExtractPAK\GRA
PHICS\_MATERIALS\XPERREAULT-M-2009032441852636.xbm
DiffuseTexture1
1 E:\\James Cameron AVATAR THE GAME\ExtractPAK\g
raphics\av_vehicles_corp\samson_01\_textures\corp_vehicle_samson_alpha.dds
SpecularTexture1
1 E:\\James Cameron AVATAR THE GAME\ExtractPAK\g
raphics\av_vehicles_corp\samson_01\_textures\corp_vehicle_samson_alpha_s.dds
ReflectionTexture
1 E:\\James Cameron AVATAR THE GAME\ExtractPAK\g
raphics\av_environment\_rainforest\cubemap\rf_cm_sharp_01.dds
E:\\James Cameron AVATAR THE GAME\ExtractPAK\GRA
PHICS\_MATERIALS\XPERREAULT-M-2009060861432108.xbm
DiffuseTexture1
2 E:\\James Cameron AVATAR THE GAME\ExtractPAK\g
raphics\av_vehicles_corp\scorpion\_textures\corp_scorpion_01_cockpit_unlit.dds
E:\\James Cameron AVATAR THE GAME\ExtractPAK\GRA
PHICS\_MATERIALS\DLAJEUNESSE-M-2008080652289381.xbm
DiffuseTexture1
3 E:\\James Cameron AVATAR THE GAME\ExtractPAK\g
raphics\av_vehicles_corp\scorpion\_textures\corp_scorpion_gun_d.dds
NormalTexture1
3 E:\\James Cameron AVATAR THE GAME\ExtractPAK\g
raphics\av_vehicles_corp\scorpion\_textures\corp_scorpion_gun_n.dds
E:\\James Cameron AVATAR THE GAME\ExtractPAK\GRA
PHICS\_MATERIALS\JDAPRATO-M-2008090532566174.xbm
DiffuseTexture1
4 E:\\James Cameron AVATAR THE GAME\ExtractPAK\g
raphics\av_vehicles_corp\samson_01\_textures\corp_samson_01_helix_d.dds
NormalTexture1
4 E:\\James Cameron AVATAR THE GAME\ExtractPAK\g
raphics\av_vehicles_corp\samson_01\_textures\corp_samson_01_helix_n.dds
E:\\James Cameron AVATAR THE GAME\ExtractPAK\GRA
PHICS\_MATERIALS\DLAJEUNESSE-M-2008072260204500.xbm
DiffuseTexture1
5 E:\\James Cameron AVATAR THE GAME\ExtractPAK\g
raphics\av_vehicles_corp\scorpion\_textures\corp_scorpion_01_d.dds
SpecularTexture1
5 E:\\James Cameron AVATAR THE GAME\ExtractPAK\g
raphics\av_vehicles_corp\scorpion\_textures\corp_scorpion_01_s.dds
NormalTexture1
5 E:\\James Cameron AVATAR THE GAME\ExtractPAK\g
raphics\av_vehicles_corp\scorpion\_textures\corp_scorpion_01_n.dds
E:\\James Cameron AVATAR THE GAME\ExtractPAK\GRA
PHICS\_MATERIALS\DPAYNE-M-1812200841647821.xbm
DiffuseTexture1
6 E:\\James Cameron AVATAR THE GAME\ExtractPAK\g
raphics\av_weapons\corp\_textures\iconic_grey_d.dds
chunk: EDON 469 (1, 2930)
chunk: MB2O 3399 (1, 152)
chunk: DIKS 3551 (1, 224)
chunk: DNKS 3775 (1, 5660)
chunk: SDOL 9435 (1, 768549)
Traceback (most recent call last):
  File "Avatar.py", line 263, in Parser
    xbgParser(filename,g)
  File "Avatar.py", line 192, in xbgParser
    if chunk == 'SDOL':SDOL(g)
  File "Avatar.py", line 29, in SDOL
    g.seek(t+indiceSectionSize*2)
  File "D:\python\WatchDogs-2014-06-25\newGameLib\myLibraries\binaresLib.py", li
ne 312, in seek
IOError: [Errno 22] Invalid argument


```
## Post #6
- Username: robertshatty
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 09, 2016 1:54 pm
- Post datetime: 2016-07-11T18:09:49+00:00
- Post Title: AvatarImporter

Any clue ?? Wht error for ??
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-12T03:49:39+00:00
- Post Title: AvatarImporter

i suppose you waiting for Szkaradek123 to respond   
can you upload the sample that is throwing the error?
