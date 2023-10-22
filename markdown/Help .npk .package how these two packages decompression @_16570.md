## Post #1
- Username: byshiyi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 04, 2016 10:52 pm
- Post datetime: 2017-07-20T14:11:43+00:00
- Post Title: Help .npk .package how these two packages decompression? @

The two files, respectively, are Chinese games, one is the town of magic song mobile phone games (npk), one is Tai Chi Panda 3 mobile games (packages), would like to learn under their game art production methods, Help out! Thank you!

[http://zm.163.com/](http://zm.163.com/)

npk download link:[https://drive.google.com/open?id=0B5vXV ... FRlQlBnZ1k](https://drive.google.com/open?id=0B5vXVrwm0zRzaEVNcFRlQlBnZ1k)

[http://panda3.woniu.com/](http://panda3.woniu.com/)

packages download link:[https://drive.google.com/open?id=0B5vXV ... y1EWEZHSlE](https://drive.google.com/open?id=0B5vXVrwm0zRzMzlzZy1EWEZHSlE)

@ekey

I am not a programmer, so do not understand the principle of these unpacking, but want to learn, do not know how to start learning, so this time can only come to the forum to help you help!
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-02T03:47:10+00:00
- Post Title: Help .npk .package how these two packages decompression? @

for the "Town of Magic" npc.npk sample this bms script should extract the content 
[viewtopic.php?f=10&t=13147&p=108173&hilit=npk#p108173](http://forum.xentax.com/viewtopic.php?f=10&t=13147&p=108173&hilit=npk#p108173)

and for the "Tai Chi Panda 3" res3.package sample this bms script will extract the contents  

```

idstring "PCK0"
get UNK long
get UNK2 short
get FILES long
get DATA_START long
get UNK4 byte
for i = 0 < FILES
	get FLAG short
	get OFFSET long
	get ZERO long
	get SIZE long
	get ZSIZE long
	getdstring FLAGS 0x9
	get NAME string
	comtype zlib_dynamic
	clog NAME OFFSET ZSIZE SIZE
next i

```


you can open the *.pvr textures with Noesis
the one tga file is a rgb565 image
the *.xmod files are models it seems, don't know if a plugin exists already though

edit
finale00 has a couple of xmod Noesis python scripts but they don't work with your xmod samples,
could be a good base to start from though.
[http://himeworks.com/redirect.php?type= ... Wulin_xmod](http://himeworks.com/redirect.php?type=noesis&name=AgeOfWulin_xmod)
[http://himeworks.com/redirect.php?type= ... Club2_xmod](http://himeworks.com/redirect.php?type=noesis&name=MidnightClub2_xmod)
