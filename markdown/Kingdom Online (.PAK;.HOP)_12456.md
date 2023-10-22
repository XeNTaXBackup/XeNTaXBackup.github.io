## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-01-01T19:33:36+00:00
- Post Title: Kingdom Online (*.PAK;*.HOP)

Official Site: [here](http://kingdom.nttgame.com)
Screenshots: [here](http://kingdom.nttgame.com/media)
Download: [here](http://clientdownload.nttgame.com/kingdom/install/186/kingdom_setup_tr_service.exe)

For unpack open HOP files.

```
# 
# Written by Ekey (h4x0r)
#
# script for QuickBMS http://quickbms.aluigi.org

open FDDE "HOP" 0
open FDDE "PAK" 1

get HSIZE ASIZE

do
   get NSIZE short 0
   math NSIZE *= 2
   getdstring UNAME NSIZE 0
   set NAME UNICODE UNAME 0
   get OFFSET long 0
   get ZSIZE long 0
   get SIZE long 0
   get DUMMY long 0 # always 0xF4E38E00
   savepos HEND 0
   
   if ZSIZE == 0
       log NAME OFFSET SIZE 1
   else
       clog NAME OFFSET ZSIZE SIZE 1
   endif
while HEND != HSIZE
```
## Post #2
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-01-02T18:29:00+00:00
- Post Title: Kingdom Online (*.PAK;*.HOP)

Hi 
Here is a model and animation importer for this game. 
It requires Blender version 249 and Python 26.

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select file:
-nls - xml file with info about used meshes, skeleton and textures
-xact - animation file

This game format use many variables, so not all is 100% imported.

[http://www.mediafire.com/view/655c3dq6y ... incess.jpg](http://www.mediafire.com/view/655c3dq6y1ximmq/princess.jpg)
[Blender249[KingdomOnline][nls][xact][2015-01-02].zip](https://xentaxbackup.github.io/file/8414_Blender249[KingdomOnline][nls][xact][2015-01-02].zip)
## Post #3
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-01-03T00:58:40+00:00
- Post Title: Kingdom Online (*.PAK;*.HOP)

Thank you for these tools. Might have to download yet another game tonight   

@Szkaradek123 Thanks for uploading that picture of the model. Looks like models have a nice skeleton to work with. Question: do the models not have facial bones or is that particular model sparse due to the mask?
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-03-11T05:52:30+00:00
- Post Title: Kingdom Online (*.PAK;*.HOP)

> Reply from ssringo
>
> Thank you for these tools. Might have to download yet another game tonight   

@Szkaradek123 Thanks for uploading that picture of the model. Looks like models have a nice skeleton to work with. Question: do the models not have facial bones or is that particular model sparse due to the mask?well I don't know what doing wrong ,every file I try import I got error Characters '*?:"<>\/`a example, so what happen here?
