## Post #1
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-01-07T11:28:43+00:00
- Post Title: Ninety nine nights - bm files

Hi there, i used a quickbms script given by fatduck (Thanks fatduck !) and extracted datas from the game.
the extracted files look the same as the ones used in "kingdom under fire circle of doom" 
i used Codeman's tool to extract the textures from the 36T files and it works perfectly. Then i tried to use chrrox's maxscript used for  

"Kingdom under fire" game to extract bm files to get meshes but unfortunatly it didn't work.

Maybe someone can adapt that script to make one that could work for the N3 game

Thanx in advance



here is the link for "kingdom under fire" topic you can find the maxscipt used to convert bm files to meshes
[viewtopic.php?f=16&t=4387&p=38957&hilit ... ire#p38957](http://forum.xentax.com/viewtopic.php?f=16&t=4387&p=38957&hilit=kingdom+under+fire#p38957)

ninety nine nights bm files attached below :
[http://www.sendspace.com/file/3h99op](http://www.sendspace.com/file/3h99op)
## Post #2
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-01-16T01:06:46+00:00
- Post Title: Ninety nine nights - bm files

anyone please ?
## Post #3
- Username: karry
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 06, 2010 2:16 am
- Post datetime: 2011-01-16T15:10:54+00:00
- Post Title: Ninety nine nights - bm files

hello! noazett!!
n3 game quickbms script upload please!!
## Post #4
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-01-16T15:53:14+00:00
- Post Title: Ninety nine nights - bm files

here is the bms script given by Fatduck

```
# by fatduck     Aug09
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

endian big
get CSIZE asize
math CSIZE -= 0x800
get USIZE long
clog MEMORY_FILE 0x800 CSIZE USIZE

get NUMRES long MEMORY_FILE
for i = 0 < NUMRES
    getdstring RESNAME 260 MEMORY_FILE
    get OFSRES long MEMORY_FILE
    get RESLENGTH long MEMORY_FILE
    log RESNAME OFSRES RESLENGTH MEMORY_FILE
next i
```
## Post #5
- Username: karry
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 06, 2010 2:16 am
- Post datetime: 2011-01-17T06:15:24+00:00
- Post Title: Ninety nine nights - bm files

thank you! noazett!!
## Post #6
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-03-09T15:17:22+00:00
- Post Title: Ninety nine nights - bm files

...anyone?
## Post #7
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-03-28T17:28:49+00:00
- Post Title: Ninety nine nights - bm files

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-28T17:55:27+00:00
- Post Title: Ninety nine nights - bm files

Szkaradek123, great! but where i can find a textures for characters?
## Post #9
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-03-29T09:45:30+00:00
- Post Title: Ninety nine nights - bm files

Many thanks Szkaradek123, i was waiting for this for long.
Tosyk, just use the 99Nights_Dot36T_exporter.exe tool to convert 36t files into tga 
you should find the 36t files in the same folder as the bm and ba files once you have extracted  the data with the bm script.
## Post #10
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-01-08T17:16:10+00:00
- Post Title: Ninety nine nights - bm files

Can someone reupload the tool for blender pls??
## Post #11
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2012-01-08T21:58:28+00:00
- Post Title: Ninety nine nights - bm files

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-01-08T22:51:08+00:00
- Post Title: Ninety nine nights - bm files

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-08T23:22:23+00:00
- Post Title: Ninety nine nights - bm files

Better to just attach it.
If a filehost deletes it due to inactivity we can't blame anyone.
Now the tool is slightly bigger. Maybe we should request larget attachments  
[import-n3-2011-03-27.7z](https://xentaxbackup.github.io/file/4967_import-n3-2011-03-27.7z)
