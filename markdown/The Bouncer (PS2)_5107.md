## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-28T23:01:30+00:00
- Post Title: The Bouncer (PS2)

Here is a bms to extract the bin files from this game.
website [http://na.square-enix.com/games/bouncer/](http://na.square-enix.com/games/bouncer/)

```
get ftbl long
set filetable 0x800
set filebase 0x800
savepos offtable
for i = 0 < files
goto offtable
get offset long
math offset * 0x800
savepos offtable
get size long
math size * 0x800
goto filetable
get nameoff long
savepos filetable
math nameoff + filebase
goto nameoff
get name string
if size == 0
get size asize
endif
math size - offset
log name offset size
next i

```
## Post #2
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2010-11-09T02:14:24+00:00
- Post Title: The Bouncer (PS2)

I'm very interested for extract 3D models from this game
## Post #3
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-11-28T22:04:41+00:00
- Post Title: The Bouncer (PS2)

easy format  
[o_eki_2md_.jpg](https://xentaxbackup.github.io/file/3647_o_eki_2md_.jpg)
## Post #4
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-11-29T09:41:05+00:00
- Post Title: The Bouncer (PS2)

Hm, looks like you might be missing a scale and/or bias, unless your image's aspect ratio is just messed up, or I'm totally misremembering what those assets looked like. I haven't actually looked at this format at all, but it's on my long-term to-look-at list. (The Bouncer was my first PS2 game, so I added it to the list on a complete whim)
## Post #5
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-11-29T11:19:15+00:00
- Post Title: The Bouncer (PS2)

yup you are right ,there may be a bounding box or else to rescale the mesh correctly i already have seen such system in resident evil 5 , also the mesh format is quite simple , it is really like the Appleseed ex machina ps2 one (for info), the only differences are some header differences here and there + the vertex def storage that match it
## Post #6
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-11-30T18:47:52+00:00
- Post Title: The Bouncer (PS2)

finished texture format , fixed mesh aspect ratio using bounding box info, the only missing infos are the grouping (if there is) and the texture id to use on each group that i can't actually find 
the mesh are in *.fe files (95% done)
the skeleton in *.sk files (not yet worked on it but look simple)
the textures in *.tex that is a binary container (format also reversed)
## Post #7
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2010-12-01T01:34:45+00:00
- Post Title: The Bouncer (PS2)

WOW!!!!
shadowmoy I hope you can fix the skeleton and release a tool (maybe with md5 support    )
## Post #8
- Username: MadReaper
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 15, 2011 7:46 pm
- Post datetime: 2011-01-30T01:10:08+00:00
- Post Title: The Bouncer (PS2)

good code , but a guide for the extractet bin files would be nice.
## Post #9
- Username: stodds90
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 18, 2011 4:53 am
- Post datetime: 2011-02-18T03:30:39+00:00
- Post Title: The Bouncer (PS2)

I must say, this is an excellent game, and still is.
## Post #10
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-03-09T03:04:20+00:00
- Post Title: The Bouncer (PS2)

This game is now supported by the new Noesis, with recursive .bin unpacking, and viewing of textures and models, with full skeleton+weights. Also, the very high-poly (for the time, ~1300 triangles just in the face was quite a lot) models are the same format. Take a look.
[](http://img638.imageshack.us/i/bouncehigh.jpg/)
However, these files are in compressed .bin files. I still haven't figured out the compression method. The files are loaded in memory with headers and all, though, so I was able to just direct-dump them from PCSX2 by memory dumping during an in-game cutscene, then view the dump in Noesis.

Here is the loader code for shadowmoy and anyone else interested: [http://pastebin.com/Bz6L393D](http://pastebin.com/Bz6L393D)
## Post #11
- Username: Esppiral
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Aug 14, 2014 11:39 pm
- Post datetime: 2014-08-20T15:29:34+00:00
- Post Title: The Bouncer (PS2)

Sorry to bump this thread from the limbo, but how did you exactly dumped the memory in order to extract the Hig polycount models?

Thanks.
