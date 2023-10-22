## Post #1
- Username: coolmib
- Rank: VIP member
- Number of posts: 19
- Joined date: Wed Jan 04, 2006 11:59 am
- Post datetime: 2006-02-13T05:53:28+00:00
- Post Title: Is it an image file?

I already used TrID-[http://mark0.net/soft-trid-e.html](http://mark0.net/soft-trid-e.html) (file Identifier) to identify this file to figure out whatever is it a image file or other (but have no luck). Anyone can Help me ??
   I extract this file from NexusTK (Kingdom of the wind) : Tile.Dat
there are 7 files : - sobj.tbl (176 KB)
                          - tile.epf (17,840 KB)
                          - tile.pal (157 KB)
                          - tile.tbl (56 KB)
                          - tilec.epf (15,542 KB)
                          - tilec.pal (134 KB)
                          - tilec.tbl (58 KB)
[TILE.EPF.zip](https://xentaxbackup.github.io/file/610_TILE.EPF.zip)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-02-15T15:10:34+00:00
- Post Title: Is it an image file?

Well, if I understand you correctly, and you extracted the seven files from the Tile.DAT file, then I would say they have something to do with graphics - in my experience, files ending with a .PAL extension are often coler palette files of some sort. I'm not sure of the other extensions, although from the size, I'd say that the .EPF files contain the actual information for the tiles (as I assume the contents to be, working from the names). You might have some luck searching them at [http://filext.com](http://filext.com), though.
## Post #3
- Username: coolmib
- Rank: VIP member
- Number of posts: 19
- Joined date: Wed Jan 04, 2006 11:59 am
- Post datetime: 2006-02-16T05:54:58+00:00
- Post Title: Is it an image file?

> Reply from Dinoguy1000
>
> You might have some luck searching them at http://filext.com, though.
Yes I do, before using TrID, filext.com is the 1st place I visited.
Actually I have a Map Editor, that have some similiar file inside 
Here is the links [Map Editor](http://nexia.delphi-id.org/4.0mapeditor.zip)
but there are still missing a lot of thing.
## Post #4
- Username: Omnilord
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 19, 2006 9:00 pm
- Post datetime: 2006-02-19T14:31:46+00:00
- Post Title: Is it an image file?

Any possibility that it is:

.tbl - describes the structure
.pal - describes the pallette
.epf - stores tile data as described in the .tbl and .pal files.
## Post #5
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-02-19T19:01:19+00:00
- Post Title: Is it an image file?

If you remove 12 byte header or pad that header with 12 empty bytes and then open front_tile .epf in GRAPHIC interface of hex editor in 24 bytes per row - you see those tiles clearly. I hope I am adding here something, or as it may happen, I do not quite understand what is all about.
## Post #6
- Username: coolmib
- Rank: VIP member
- Number of posts: 19
- Joined date: Wed Jan 04, 2006 11:59 am
- Post datetime: 2006-02-20T03:22:26+00:00
- Post Title: Is it an image file?

Yes... if I view using AXE it will be like this...

but since I'm not expert in this
I can't make the thing work... someone pls...
## Post #7
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-02-20T03:30:56+00:00
- Post Title: Is it an image file?

Nearly you are there. Just delete the 12 bytes of header right on the start of this file and all will allign 24x24 pixels. Do you have any informations about any palette here?
## Post #8
- Username: coolmib
- Rank: VIP member
- Number of posts: 19
- Joined date: Wed Jan 04, 2006 11:59 am
- Post datetime: 2006-02-20T04:06:39+00:00
- Post Title: Is it an image file?

Is this will help ? [Map Editor](http://nexia.delphi-id.org/4.0mapeditor.zip)
## Post #9
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-02-20T12:42:29+00:00
- Post Title: Is it an image file?

I have looked at the map editor but could not figure how to use it. Are the Tiles "A" and Tiles "B" of the editor the same tiles we see in the file we trying to open ?
## Post #10
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-02-20T12:52:28+00:00
- Post Title: Is it an image file?

Being the noob in this file exploration business, I use that AXE graphic editor shown above as one of my main tools.  I explore hex content ghraphically mainly looking for regularities , patterns and recognisable picel pictures. One of the main desire for AXE or other HexEditor is to have "adjust hex number per row" slaved to left /right arrow key so I can  change the width in one fluid motion just continuing to monitor for appearance of more meaniningfull and telling picture. 

Is such a feature implemented and used any of the known Hex Editor?
## Post #11
- Username: coolmib
- Rank: VIP member
- Number of posts: 19
- Joined date: Wed Jan 04, 2006 11:59 am
- Post datetime: 2006-02-21T04:54:46+00:00
- Post Title: Is it an image file?

> Reply from Xela
>
> I have looked at the map editor but could not figure how to use it. Are the Tiles "A" and Tiles "B" of the editor the same tiles we see in the file we trying to open ?

Here I attached a [Map File](http://nexia.delphi-id.org/TK000000.map) that created by using those Map Editor. This is a simple binary file.
The Structure is like this : 
- 1st 4 bytes is a Map size , 
- the rest is for tile and Object information 
  (1st-2nd byte = Tile, 3rd-4th byte = Object).
## Post #12
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-02-21T18:37:04+00:00
- Post Title: Is it an image file?

> I extract this file from NexusTK (Kingdom of the wind) : Tile.Dat 
>
> there are 7 files : - sobj.tbl (176 KB) 
>
> - tile.epf (17,840 KB) 
>
> - tile.pal (157 KB) 
>
> - tile.tbl (56 KB) 
>
> - tilec.epf (15,542 KB) 
>
> - tilec.pal (134 KB) 
>
> - tilec.tbl (58 KB)
This is how it all started here , but in attached zip you enclosed: 3 epf files only front_Tile.epf  back_Tile.epf and info_Tile.epf.  Where did they come from? 

Anyway, after looking at the editor and map all is clearer now, but there are in use several color palettes (do not misundertand and mix them with Tile palettes of the Editor) here which makes little difficult to open and view those  zipped files. 
The palettes are in *.pal format, however it is custom 256 values plus header and it is not standard MS pal format.  So we cannot load into the Photoshop to view the epf file opened in RAW mode and switched to indexed. 

Road map of different palettes in relation to epf is in *.tbl file which is easy to read but too time consuming to apply by hand. 

Tell me more what would you like to do with zipped epf files as they look to me as something " unfinished"  or not quite "fitting" to Map Editor which is very interesting tool for me by itself , so I thank you .
## Post #13
- Username: coolmib
- Rank: VIP member
- Number of posts: 19
- Joined date: Wed Jan 04, 2006 11:59 am
- Post datetime: 2006-02-22T03:16:57+00:00
- Post Title: Is it an image file?

Okay... I tell you the truth   
Currently I'm coding an emulator for this game,
the basic of emulator I got from [Here](http://www.kamikazeserver.com/forums)
They are using VB (Visual Basic) for this project.
Then I got an idea to Create one in Delphi (Just 4 fun/Education only)
I have 3 different version of client for this game (5.2, 5.33, 6.5)
now,the emulator only can run for client 5.33, if I using the other version
the graphic (map will appear in blank). So now I want to know the
secret inside the Tile.Dat. Maybe I can create a simple map Editor for each version
because The Current Map Editor only for client 5.33.

> Reply from Xela
>
> 
This is how it all started here , but in attached zip you enclosed: 3 epf files only front_Tile.epf  back_Tile.epf and info_Tile.epf.  Where did they come from? 
...
Tell me more what would you like to do with zipped epf files as they look to me as something " unfinished"  or not quite "fitting" to Map Editor which is very interesting tool for me by itself , so I thank you .

first time I think that tile.epf is a simply graphic file with a custom header
(now I know it's not so simple). So I attached the zip file (using filecutter) here
and hope someone can convert it into....maybe BMP format or else. This problem will be
easly if I can contact the Author of Map Editor
## Post #14
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-02-22T16:15:21+00:00
- Post Title: Is it an image file?

Omnilord wrote : 

> .tbl - describes the structure 
>
> .pal - describes the pallette 
>
> .epf - stores tile data as described in the .tbl and .pal files.

This is essence of all that. The only additional complication here is those multiple color palettes which are "road maped" in *.tbl file. But if anyone wanted to use that Map Editor for his/her own purpose, it can be done with just one single Color Palette *.pal  containing 256 colors and one Tile Palette *.epf containing  up to 256^2  tiles. Tiles can be stored in separate texture files. The product of Map Editor is the binary file listing labels of tiles which then can be keyed to textures. Size of the map unlimited (?) 

All in all very good tool for some hand mapping application. 

PS. this is good opportunity to list and discuss other Map and Terrain Editors which come with various games.
## Post #15
- Username: coolmib
- Rank: VIP member
- Number of posts: 19
- Joined date: Wed Jan 04, 2006 11:59 am
- Post datetime: 2006-02-27T08:06:09+00:00
- Post Title: Is it an image file?

hi Xela,
did you know any good forum that discuss about "Map and Terrain Editors" ?
## Post #16
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-02-27T13:13:06+00:00
- Post Title: 

> did you know any good forum that discuss about "Map and Terrain Editors" ?
Not per se, 
but I know little what is to know about that and gladly share with you here. In fact I have searched web a while ago, but the informations are very sketchy and I think there is no particular place which would address this issue in detail. 
But again I have some knowledge how the Terrain Editor suppose to work and actually I am interested in this subject too.
## Post #17
- Username: coolmib
- Rank: VIP member
- Number of posts: 19
- Joined date: Wed Jan 04, 2006 11:59 am
- Post datetime: 2006-03-24T05:07:49+00:00
- Post Title: 

Hey...I got this from monster.epf

Only need to find the right color on each pixel
## Post #18
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-03-24T15:09:34+00:00
- Post Title: 

Great goings  
this is true and best example of graphic representation of Hex Editor. Now you need PAL file which you can find among game files or knowing what are the values of index palette create manually yourself. 

You have to safe this file from hex editor as a RAW format and then in graphic editor convert to Indexed, but it will ask you for palette.
## Post #19
- Username: coolmib
- Rank: VIP member
- Number of posts: 19
- Joined date: Wed Jan 04, 2006 11:59 am
- Post datetime: 2006-03-31T08:49:56+00:00
- Post Title: 

I think someone already did it   
~~~ Sorry dead links ~~~~
## Post #20
- Username: coolmib
- Rank: VIP member
- Number of posts: 19
- Joined date: Wed Jan 04, 2006 11:59 am
- Post datetime: 2006-04-12T07:08:10+00:00
- Post Title: 

Here I created one. Can view image directly from Dat file

[Source Code](http://nexia.delphi-id.org/DatViewerSrc.zip)
[Binary](http://nexia.delphi-id.org/DatViewerBinary.zip)
## Post #21
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-12T07:51:48+00:00
- Post Title: 

Nice work!
