## Post #1
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-11-16T21:25:58+00:00
- Post Title: wii game bleach shattered blades TEX0 files : need help

here is what i get from raw file loading , not found any wiever / converter that is able to convert it correctly :





 wii_bleach_shateredbalde_nel_face.zip
the sample files (160.57 KiB) Downloaded 80 times
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-30T22:20:58+00:00
- Post Title: wii game bleach shattered blades TEX0 files : need help

The image data starts at 0x40.

```
// little endian

[4]     MW   TEX0
uint32  imagesize
uint32  number of images (3)
uint32  unknown
uint32  offset of image data (0x40)
uint32  channels (8)
etc


```


There is more info in the header. It seems these are 8-channel bitmaps of 512x170 that contain 3 images. one large and two identical smaller versions.



Untitled2.jpg (76.72 KiB) Viewed 529 times
## Post #3
- Username: shekofte
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-30T23:48:04+00:00
- Post Title: wii game bleach shattered blades TEX0 files : need help

This tool was not made by me.

[brtextobmp.rar](https://xentaxbackup.github.io/file/2577_brtextobmp.rar)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-01T06:47:07+00:00
- Post Title: wii game bleach shattered blades TEX0 files : need help

Nice find, chrrox.   Any word on the format of the TEX0 files then?
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-12-01T10:19:45+00:00
- Post Title: wii game bleach shattered blades TEX0 files : need help

what file posted is the tex 0 file?
all wii games use tpl files even these seem to be tpl files they are just renamed or have the pallet separated.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-01T10:51:49+00:00
- Post Title: wii game bleach shattered blades TEX0 files : need help

Ok, good. So I read that TEX0 files are actually TPL with altered headers. 

Here's what TPL should be.
[http://pabut.homeip.net:8000/yagcd/chap14.html#sec14.4](http://pabut.homeip.net:8000/yagcd/chap14.html#sec14.4)

Chrroxx you showed the picture, yet do not know which file it was? How did you get the picture in the first place then??
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-12-01T20:06:19+00:00
- Post Title: wii game bleach shattered blades TEX0 files : need help

sorry lol just use the tex 0 file also with an extension of brtex and then space the other file in the archive which is the pallet to get the bmp.
## Post #8
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-12-15T18:47:31+00:00
- Post Title: wii game bleach shattered blades TEX0 files : need help

oh my  i forgot this post , so i found also some good wii utilities form super smash brawl that work fine on all brres files (also the ones including tex0)
so i split the archive using an hex editor then load the brres and extact each texture from each file...

so here are a couple of usefull wii tools to play with brres files:
you need to edit the extracted wii files( using dolphin disk utility), first edit the file header so that it start by brres by removing a couple of bits, then rename the file as *.brres ,split it if it contains more than one brres in the archive (hex edition) then  load it using brawlbox and you will be able to see the textures and extract them as png, for the models you need to rename the file to *.brmdl , open it with the mdl0 viewer to see it

[http://pagesperso-orange.fr/dreamsoft/FBSL/BrawlBox.rar](http://pagesperso-orange.fr/dreamsoft/FBSL/BrawlBox.rar)
