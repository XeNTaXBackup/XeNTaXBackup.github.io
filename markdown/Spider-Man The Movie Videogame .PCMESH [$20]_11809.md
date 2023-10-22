## Post #1
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-08-19T14:52:43+00:00
- Post Title: Spider-Man The Movie Videogame .PCMESH [$20]

Alright so I have been able to extract from the PKG files, using Watto's Tools. But now I'm stuck on the PCMESH files. I figure these contain the 3D model data, but after doing some searching I have not found any program that will open them. Anyone here have an idea? Here's a sample. 
[https://www.sendspace.com/file/l724rt](https://www.sendspace.com/file/l724rt) There is also a ENT and ENX file in the folder with this, but I doubt they have much use.

I'll also do one better by paying someone $10 via Paypal if they can manage to get this one single model into a OBJ or 3DS format and send it via PM with their Paypal address.
## Post #2
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-08-21T00:36:58+00:00
- Post Title: Spider-Man The Movie Videogame .PCMESH [$20]

Really need help on this, bumping the paid offer up to $20 via Paypal and that's just for one model conversion.
## Post #3
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-08-22T16:40:27+00:00
- Post Title: Spider-Man The Movie Videogame .PCMESH [$20]

annoying format, dunno if I'm able to finish it or not
[http://puu.sh/b3kXZ.png](http://puu.sh/b3kXZ.png)
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-08-22T17:18:45+00:00
- Post Title: Spider-Man The Movie Videogame .PCMESH [$20]

Hm, format itself seems not so hard, but faces here are builded in a strange way (I think they are quads) It could be an interesting example to study
[gob.jpg](https://xentaxbackup.github.io/file/7701_gob.jpg)
## Post #5
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-08-22T17:21:32+00:00
- Post Title: Spider-Man The Movie Videogame .PCMESH [$20]

> Reply from zaramot
>
> Hm, format itself seems not so hard, but faces here are builded in a strange way (I think they are quads) It could be an interesting example to study
could you explain how you read the vertices?
## Post #6
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-08-22T20:39:32+00:00
- Post Title: Spider-Man The Movie Videogame .PCMESH [$20]

This is a very easy format, indices mixed with Face-index and UV-index!
I did it while I am watch TV! 


[PLRGOBLIN.rar](https://xentaxbackup.github.io/file/7702_PLRGOBLIN.rar)
## Post #7
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-08-23T06:27:34+00:00
- Post Title: Spider-Man The Movie Videogame .PCMESH [$20]

Cool! Fatduck you are the best, could you provide part of your code for face/uv section?

EDIT: Nintendude, could you send me more models via PM? Or maybe post them here.
## Post #8
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2014-08-23T13:07:47+00:00
- Post Title: Spider-Man The Movie Videogame .PCMESH [$20]

> Reply from Nintendude
>
> Well that's kind of depressing. Wonder why it didn't look like this. That's supposed to be this but now that I think about it, it's probably just a cinematic model. 
http://i1-news.softpedia-static.com/ima ... -large.jpg
Earlier this week I had already converted the model for Nintendude. I should have posted here about it, seems everyone is writing there own programs now lol

here is the PC demo of the game: (game was released in 2002, it runs off of dx8.1, and looks extremely dated)
[http://www.fileplanet.com/89532/80000/f ... Movie-Demo](http://www.fileplanet.com/89532/80000/fileinfo/Spider-Man:-The-Movie-Demo)

there are only about a dozen actual 3d characters in the game files, 80% of the game is made out of BIK video sequences :\

the models are packed in a PKG file, (PCMESH,TGA,ENT,ENX) are sub files
PCMESH -> geometry data
TGA -> Texture data
ENT -> Skeleton data
ENX -> ?? Hitbox data?

I've written a maxscript with handling for PKG unpacking and PCmesh importing

..my maxscript is attached below if your interested, the face format isnt anything special. the faces are interlaced together, the tip off was the fact there is UV data with a different count.. one would expect there to be face data for the UVs.. so where was it in a single face buffer? either at the half way point or its interlaced...




 PCMESH Tool by mariokart64n.zip
(3.14 KiB) Downloaded 149 times
## Post #9
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-08-23T13:51:47+00:00
- Post Title: Spider-Man The Movie Videogame .PCMESH [$20]

Ah, Corey thanks a lot for your script!  Now I adopted your code for my script, yesterday I briefly looked at this format. Didn't get what to do with faces lol So decided that, this is nice example to study (never met this before) Your amazing job saved me hours lol Thanks a lot again
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-20T07:30:26+00:00
- Post Title: Spider-Man The Movie Videogame .PCMESH [$20]

bms script for fun to extract the files from pkg  

```

get FOLDERS long
get FILES long
get TOTAL_DATA_SIZE long
for i = 0 < FOLDERS
    getdstring FOLDER 0x40
    putarray 0 i FOLDER
    get FILES_IN_FOLDER long
    for j = 0 < FILES_IN_FOLDER
        get FILE_INDEX long
    next j
next i
savepos TMP
xmath BASE_OFF "(FILES * 0x30) + TMP" 
for k = 0 < FILES
    getdstring NAME 0x28
    get SIZE long
    get OFFSET long
    savepos TMP2
    math OFFSET + BASE_OFF
    log NAME OFFSET SIZE
    goto TMP2
next k

```
## Post #11
- Username: GBA64
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 18, 2018 11:03 am
- Post datetime: 2019-03-08T06:48:48+00:00
- Post Title: Spider-Man The Movie Videogame .PCMESH [$20]

Hey, so I know this post is super old, but I was wondering if this script could be updated to import level geometry and maybe fix a few issues with some garbled polygons. Level geometry doesn't show a thing when imported, and some things like ARROWS_A.PCMESH just import as a mess.

This PCMESH is from "COMMON\MXTRAINING\ENTITIES"
## Post #12
- Username: joaovict
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 02, 2017 12:10 am
- Post datetime: 2020-02-03T22:22:14+00:00
- Post Title: Spider-Man The Movie Videogame .PCMESH [$20]

Hey, sorry for talking in such a old thread, but can anyone inform me if it's possible for someone create a export script for 3DS Max, atleast tell me how to do as such? I'm part of a modding community for the game, being able to export in the .PCMESH format would help out a lot!
