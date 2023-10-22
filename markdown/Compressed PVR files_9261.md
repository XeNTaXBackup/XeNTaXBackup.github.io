## Post #1
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2012-07-13T12:50:52+00:00
- Post Title: Compressed PVR files

Hi, 

I extracted from a game (Megarun, for iPad, free to download from [here](http://itunes.apple.com/us/app/mega-run-redfords-adventure/id521906541?mt=8))  several PVR files. There were 2 kinds of PVR files: Compressed and uncompressed. The uncompressed ones where easy to convert with the PVR tool. For the compressed, I really have no idea what method they used. I believe it should be a standard one (zip or something similar) but since I have no idea on how to use QuickBMS to uncompress files... maybe someone here can lend me a hand with a small bms script?

You can download a sample file from [here](http://www.extremefx.com.ar/temp/blueto_atlas-hd.pvr.zip) (so you don't have to download the game).

Thanks in advance!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-13T13:30:20+00:00
- Post Title: Compressed PVR files

```
idstring "CCZ!"
get DUMMY long
get DUMMY long
get SIZE long
savepos OFFSET
get ZSIZE asize
math ZSIZE -= OFFSET
get NAME basename
clog NAME OFFSET ZSIZE SIZE
```
## Post #3
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2016-07-06T21:07:49+00:00
- Post Title: Compressed PVR files

Hey @aluigi, can you take a look at this one? It seems that they changed the compression scheme. Of course I already did the easy thing: try changing the signature in your script :p and of course, it doesn't works. (Same game, newer version).
[achievement_ingame_sheet.pvr.zip](https://xentaxbackup.github.io/file/11257_achievement_ingame_sheet.pvr.zip)
