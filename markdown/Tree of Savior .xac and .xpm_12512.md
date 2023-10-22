## Post #1
- Username: mumphster
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 17, 2015 7:46 am
- Post datetime: 2015-01-17T01:24:26+00:00
- Post Title: Tree of Savior .xac and .xpm

Any help would be appreciated. After some googling I've noticed a few games use formats with this extension but I have been unable to open these files using any of the tools I've found. The header contains info such as

3D Studio Max 8 (regular commercial version)....D:\R1_bg2\npc\npc_box.max....Dec  9 2008

which would lead me to believe this is some sort of packed 3dsmax format. Any help would be appreciated and I would love to get these converted to .OBJ

[https://www.dropbox.com/s/ytdhmu4om7yd5hz/box.xac?dl=0](https://www.dropbox.com/s/ytdhmu4om7yd5hz/box.xac?dl=0)
[https://www.dropbox.com/s/9jdcju1026muv ... f.xac?dl=0](https://www.dropbox.com/s/9jdcju1026muvpo/accessory_3dGlasses_hit_f.xac?dl=0)
[https://www.dropbox.com/s/q3fy9b8qal903 ... f.xpm?dl=0](https://www.dropbox.com/s/q3fy9b8qal903gq/accessory_3dGlasses_hit_f.xpm?dl=0)

Client can be found at [http://tosvod-nexon30.ktics.co.kr/launcher/launcher.exe](http://tosvod-nexon30.ktics.co.kr/launcher/launcher.exe)

Game is currently undergoing a closed beta test in korea and will be free to play.
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2015-01-17T16:16:30+00:00
- Post Title: Tree of Savior .xac and .xpm

Hi, could you please share the file city_roskilde_1box.dds
This is what I got so far:



box.png (23.42 KiB) Viewed 438 times
## Post #3
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2015-01-17T16:17:34+00:00
- Post Title: Tree of Savior .xac and .xpm

Here's the obj: 

 box.zip
(9.7 KiB) Downloaded 33 times
## Post #4
- Username: mumphster
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 17, 2015 7:46 am
- Post datetime: 2015-01-17T17:49:17+00:00
- Post Title: Tree of Savior .xac and .xpm

> Reply from herbert3000
>
> Here's the obj: box.zip

Wow awesome stuff man. Care to share how you got this going? Ill try to dig through some more of the archives and track down the texture.
## Post #5
- Username: thebreakdownprocess
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 18, 2015 5:52 am
- Post datetime: 2015-01-17T21:58:26+00:00
- Post Title: Tree of Savior .xac and .xpm

> Reply from herbert3000
>
> Hi, could you please share the file city_roskilde_1box.dds
This is what I got so far:
The attachment box.png is no longer available

I've attached the .dds file. How are you applying it in 3DS Max? Does it need to go into a certain location to apply on the .xac file automatically? Or is there a way to manually apply it?
[city_roskilde_1box.rar](https://xentaxbackup.github.io/file/8499_city_roskilde_1box.rar)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-19T14:02:03+00:00
- Post Title: Tree of Savior .xac and .xpm

you could use this .mtl file on obj import:
# Material Count: 1
newmtl None_city_roskilde_1box.dds
Ns 0
Ka 0.000000 0.000000 0.000000
Kd 0.8 0.8 0.8
Ks 0.8 0.8 0.8
d 1
illum 2
map_Kd city_roskilde_1box.dds

with the box.obj, box.mtl and .dds in the same folder

or you could apply a material to the imported obj:

[http://www.youtube.com/watch?v=EuBIkPcTH3g](http://www.youtube.com/watch?v=EuBIkPcTH3g)

box.xac to obj by hex2obj:



box_hex2obj.JPG (38.59 KiB) Viewed 410 times
## Post #7
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2015-01-19T19:55:03+00:00
- Post Title: Tree of Savior .xac and .xpm

Hey, hex2obj is a really neat tool, I'll definitely use that again in the future.

Ok, I did some more research on the file format and wrote a simple java program that extracts all 3d models (without textures) from a .xac file as obj's. If you want textured models, you'll have to create .mtl files yourself (see shakotay2's post). 

 box.zip
(100.09 KiB) Downloaded 73 times
## Post #8
- Username: thebreakdownprocess
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 18, 2015 5:52 am
- Post datetime: 2015-01-19T22:18:03+00:00
- Post Title: Tree of Savior .xac and .xpm

Thanks guys  I was finally able to do it. I just had to do some adjustments in the material editor.

Was able to export to obj+mtl and produce this:

[https://p3d.in/B7fQP](https://p3d.in/B7fQP)
[box.png](https://xentaxbackup.github.io/file/8523_box.png)
## Post #9
- Username: Nialcen
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Sep 04, 2015 5:59 pm
- Post datetime: 2015-09-04T10:58:33+00:00
- Post Title: Tree of Savior .xac and .xpm

Hello, 

I'm trying to do quite the same thing, but I have some difficulties with Hex2Obj tuto.

I would like to produce an .obj textured file from .xac and .dds I have, so I try to first transform .xac to .obj, then I will have to apply texture with 3dsMAx and then exportthe whole thing.

I'm trying to determine the face indices list start and end on the file I share bellow to understand, but i'm unable to determine them properly.

I tried the herbert box tool too, however java send me errors.

Thank you for any help you willbring me  !

EDIT : My last try Gave me start at 0057C37, end at 0068E57, so a result of 11220(hex) -> 70176(dec) / 4 = 17544 index count, but the next instructions get me nowhere in the end :/
[ext.rar](https://xentaxbackup.github.io/file/9681_ext.rar)
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-04T20:53:41+00:00
- Post Title: Tree of Savior .xac and .xpm

> Reply from Nialcen
>
> Hello, 

I'm trying to do quite the same thing, but I have some difficulties with Hex2Obj tuto.Hello,
it would be helpful if you could be more specific so that I could try to improve the tutorial.  

btw: although the format is rather simple I've to confess that it took me more than 15 minutes to get the proper obj file  



ext.JPG (93.37 KiB) Viewed 324 times
## Post #11
- Username: Nialcen
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Sep 04, 2015 5:59 pm
- Post datetime: 2015-09-05T16:17:49+00:00
- Post Title: Tree of Savior .xac and .xpm

Actualy, you can see that the values I choose as Start / End, and so the count etc... are not correct.
The tuto part to determine Start / End of face indice list, etc is quite hard to apply.

May I ask your help to understand the process ( something like 44 models to extract and texturize ) it would be just great 

I'll check the parameter you screen to try to understand, 

waiting to read you, and thank you !

Edit : I tried on another model, but I was unable to find float in the right bottom list
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-05T19:54:35+00:00
- Post Title: Tree of Savior .xac and .xpm

It's just a little bit trial 'n error (maybe there some table with offsets, dunno).



Faceindices_start_end.JPG (158.69 KiB) Viewed 317 times



But to be honest I don't see the problem how to get the start/ending addresses from the picture.

(You need to know that 29 5C 4F 3F might be a float value, of course. Then it's clear that it's no faceindex.
Also the value would be much too great for an FI, same as 0x060800, little endian.)

Just fiddle around a little bit with the FIs' start address and set the FIs' count to 500, 1000 or so at the beginning.
Then press the 'mesh' button to see the result.

(It took me some time to get experience but for nowadays generation I feel they seem to be a little bit too unpatient, aren't you?  )
## Post #13
- Username: Nialcen
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Sep 04, 2015 5:59 pm
- Post datetime: 2015-09-06T10:41:33+00:00
- Post Title: Tree of Savior .xac and .xpm

This screen help a lot ! 
Thanks !

But for nowaday generation I don't know, mut with my 30, I don't feel unpatient, just inexperimented, and 3D hex files are not something I will use often ^^
