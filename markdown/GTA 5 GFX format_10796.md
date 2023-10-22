## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-09-22T14:43:03+00:00
- Post Title: GTA 5 GFX format

Hi all,

can anyone please help out with font format.... A few ppl working on it, but no luck yet 

EDIT : Im able to display the font but not edit yet..

```
https://dl.dropboxusercontent.com/u/38234344/GTA5_fonts.rar
```
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-22T21:23:31+00:00
- Post Title: GTA 5 GFX format

GTAV have 2 types of GFX - Compressed and Uncompressed.

For Uncompressed you need change header > GFX to FWS
For Compressed you need change header > CFX to CWS

PS: font_lib_XXXXX do not include fonts
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-09-23T04:48:03+00:00
- Post Title: GTA 5 GFX format

> Reply from Ekey
>
> GTAV have 2 types of GFX - Compressed and Uncompressed.

For Uncompressed you need change header > GFX to FWS
For Compressed you need change header > CFX to CWS

PS: font_lib_XXXXX do not include fonts

Ekey, im afraid, you  are wrong  mate.... i have fonts from font_lib_ ..... today we are gonna try to make possible to add,replace,delete a new chars... as i said I can display them now(no edit yet), fonts are truly from Autodesk Scaleform and reason why normal decompilers does not show them is coz Autodesk SWF files using special tags which are never used in normal swf's files.

Proof :
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-23T12:49:56+00:00
- Post Title: GTA 5 GFX format

Well okay need update decompilers to newest version
## Post #5
- Username: HAIDER6222354
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Jul 04, 2012 12:19 pm
- Post datetime: 2013-11-11T07:08:57+00:00
- Post Title: GTA 5 GFX format

@michalss  , can you give me path files font 
using LibertyV ?
## Post #6
- Username: camila
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 29, 2014 6:51 pm
- Post datetime: 2014-08-29T11:01:23+00:00
- Post Title: GTA 5 GFX format

Thanks for your continued support of ForgeX and related programs. Your efforts are truly appreciated. I hear that you are looking into supporting multiplayer models from AC3. I am very much looking forward to when you are able to complete that. Best of luck to you!
## Post #7
- Username: rugaviyahu
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 20, 2014 1:48 am
- Post datetime: 2015-04-21T14:37:50+00:00
- Post Title: GTA 5 GFX format

> Reply from michalss
>
> 
Ekey, im afraid, you  are wrong  mate.... i have fonts from font_lib_ ..... today we are gonna try to make possible to add,replace,delete a new chars... as i said I can display them now(no edit yet), fonts are truly from Autodesk Scaleform and reason why normal decompilers does not show them is coz Autodesk SWF files using special tags which are never used in normal swf's files.
There is any progress? 
UPD: I used Flash Decompiler Trillix to reverse PC version GFX fonts and understood, that font data in font_lib_sc.gfx and font_lib_efigs_pc.gfx begins from 7F FB, but any flash files and gfxfontlib.gfx uses FF 12 for it. Any ideas? Maybe there is amature specification of SWF files?
## Post #8
- Username: BANDIT
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 13, 2011 4:19 am
- Post datetime: 2015-04-21T21:44:11+00:00
- Post Title: GTA 5 GFX format

JPEXS Free Flash Decompiler works great with PC GTA 5 GFX format.
