## Post #1
- Username: bas
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 06, 2010 8:38 am
- Post datetime: 2010-04-08T02:15:16+00:00
- Post Title: [Request] James Cameron Avatar the game models

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-04-28T19:20:17+00:00
- Post Title: [Request] James Cameron Avatar the game models

The vertexes are stored as signed16byte integers, There is also a face index when I tried to view it after using some microsoft excel formulas the vertexes appearead fine, but when I added a face list the faces do not align properly. Here is a picture, I will do more work on this later this week.
## Post #3
- Username: bas
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 06, 2010 8:38 am
- Post datetime: 2010-05-15T21:50:57+00:00
- Post Title: [Request] James Cameron Avatar the game models

great thanks; 

almost gave up on this

dunno if you still plan to continue on this;
but I would appreciate it very much if you could share with me what you have found so I can continue working with it

Edit: got 2 coords of the vertices (side view of the model is correctly) but the 3rd is still a mess
## Post #4
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2010-05-18T16:42:38+00:00
- Post Title: [Request] James Cameron Avatar the game models

It is a part of python script in blender.

for i in range(numverts):
        xyz = struct.unpack(3*'h',plik.read(6))
        v1 = xyz[0]*2**-12
        v2 = xyz[1]*2**-12
        v3 = xyz[2]*2**-12        
        vertexy.append([v1,-v2,v3])
        uv = struct.unpack(3*'H',plik.read(6))
        u = uv[1]*2**-10 #???
        v = uv[2]*2**-10 #???
        uvcoord.append([u,v])
        plik.read(28)

numfaces = struct.unpack('i',plik.read(4))[0]
print struct.unpack('i',plik.read(4))

for i in range(numfaces/3):
         f= struct.unpack('HHH',plik.read(3*2))
         faceslist.append([f[0],f[1],f[2]])
[avatar.jpg](https://xentaxbackup.github.io/file/3051_avatar.jpg)
## Post #5
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-18T17:38:29+00:00
- Post Title: [Request] James Cameron Avatar the game models

> Reply from Szkaradek123
>
> It is a part of python script in blender.

for i in range(numverts):
        xyz = struct.unpack(3*'h',plik.read(6))
        v1 = xyz[0]*2**-12
        v2 = xyz[1]*2**-12
        v3 = xyz[2]*2**-12        
        vertexy.append([v1,-v2,v3])
        uv = struct.unpack(3*'H',plik.read(6))
        u = uv[1]*2**-10 #???
        v = uv[2]*2**-10 #???
        uvcoord.append([u,v])
        plik.read(28)

numfaces = struct.unpack('i',plik.read(4))[0]
print struct.unpack('i',plik.read(4))

for i in range(numfaces/3):
         f= struct.unpack('HHH',plik.read(3*2))
         faceslist.append([f[0],f[1],f[2]])

Thats great can you tell me how to use this script in blender , if for example I have 3 files, one with the 32bitVertexes, one with the UV, and one with the Face index. Where would I insert the number of vertexes into the script?
## Post #6
- Username: elypter
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 19, 2010 6:44 pm
- Post datetime: 2010-05-19T21:25:58+00:00
- Post Title: [Request] James Cameron Avatar the game models

i would also like to know how to do this
## Post #7
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2010-05-20T17:20:16+00:00
- Post Title: [Request] James Cameron Avatar the game models

The contents of this post was deleted because of possible forum rules violation.
[thanator.jpg](https://xentaxbackup.github.io/file/3056_thanator.jpg)
## Post #8
- Username: elypter
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 19, 2010 6:44 pm
- Post datetime: 2010-05-21T15:07:33+00:00
- Post Title: [Request] James Cameron Avatar the game models

thats cool.
i hope you can modify this script to import other models as well.
if not generally possible could you please post instructions on how to modify the script for other models
## Post #9
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2010-05-23T12:59:35+00:00
- Post Title: [Request] James Cameron Avatar the game models

The contents of this post was deleted because of possible forum rules violation.


Update 2014-06-30:

[http://www.mediafire.com/download/18g3f ... BPC%5D.zip](http://www.mediafire.com/download/18g3fq3gpjshx9m/Avatar%5BPC%5D.zip)
## Post #10
- Username: elypter
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 19, 2010 6:44 pm
- Post datetime: 2010-05-23T19:02:06+00:00
- Post Title: [Request] James Cameron Avatar the game models

many thanks.
thats awsome !

but i still have a little problem:
i don't get any textures.

in the console some xbm and xbt files are listed, so it seems to find the files.

```
corp_samson_01_closeddoor.xbg
=============================================================
HSEM
(42, 6, 4571, 59310, 0, 0, 0, 0, 55178, 14, 0, 0, 10, 0)
LTMR
CORP_SAMSON_EXTERIOR
graphics\av_vehicles_corp\samson_01\_textures\corp_vehicle_samson_exterior.xbt
graphics\av_vehicles_corp\samson_01\_textures\corp_vehicle_samson_exterior_s.xbt

graphics\av_vehicles_corp\samson_01\_textures\corp_vehicle_samson_exterior_n.xbt

CORP_SAMSON_ALPHA_HELLSGATE
graphics\av_vehicles_corp\samson_01\_textures\corp_vehicle_samson_alpha.xbt
graphics\av_vehicles_corp\samson_01\_textures\corp_vehicle_samson_alpha_s.xbt
graphics\av_environment\_rainforest\cubemap\rf_cm_blur_01.xbt
SAMSON_INTERIOR_PROPS
graphics\av_vehicles_corp\samson_01\_textures\corp_vehicle_samson_interior_d.xbt

graphics\av_vehicles_corp\samson_01\_textures\corp_vehicle_samson_id1_s.xbt
EDON
numbones =  1
DIKS
DNKS
SULC
SDOL
(1, 0, 53106, 14, 53086, 14, 0, 0, 4, 0, 0, 16928, 1, 0, 3018, 0, 32, 0, 13060,
0)
(0, 3)
numvertices 13060
(0, 0, 0, 0, 11656, 0, 0)
(0, 0, 1, 24168, 12169, 373024, 0)
(0, 0, 2, 25860, 13059, 389440, 0)
(128, 96, 6, 0)
3
(3, 2, 1)
2064
419984
numfaces 9408
11
(11, 10, 9, 8, 7, 6, 5, 4, 3, 2, 1)
476448
  ûB

```


maybe i just don't know how to handle blender correctly. i'm an absolute noob.

heres a screenshot:
[blender.jpg](https://xentaxbackup.github.io/file/3067_blender.jpg)
## Post #11
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2010-05-23T20:10:47+00:00
- Post Title: [Request] James Cameron Avatar the game models

Thanks for reply.
Blender import materials and textures but they are not joint with objects,
because i have problem with UV coord for meshes.
To see textures:
1. in 3d view select object
2. in buttons window select material button and click on existing materials.
[samson.jpg](https://xentaxbackup.github.io/file/3068_samson.jpg)
## Post #12
- Username: elypter
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 19, 2010 6:44 pm
- Post datetime: 2010-05-23T22:47:50+00:00
- Post Title: [Request] James Cameron Avatar the game models

thanks again! now it works.

if i see it correctly, the converted mesh originaly consisted out of several different meshes and also out of different textures (3 in the case of corp_samson_01_closeddoor.xbg). could it be, that the textures should only be applied to the individual meshes? i hope this is a solvable problem.

In the case, that this is not scriptable but still only a problem of texturescaling, is there a practical way to correct this by hand? I tried to tweak "sizeX" and "sizeY" by hand 0.10 each every step but havn't found anything good looking between 0.00 and 5.00
Is there a script that can run through this, where you can press stop if you think it looks correct? other question: is the ration between scaleX and scaleY 1:1 at all?

i made a screenshot with activated "shadeless" option to see the texture better.
[blender21.jpg](https://xentaxbackup.github.io/file/3070_blender21.jpg)
## Post #13
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-23T23:19:08+00:00
- Post Title: [Request] James Cameron Avatar the game models

I see someone has beat me to it.    The problem with the way I was doing it, was that my Excel formulas used were off by an offset.
## Post #14
- Username: bas
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 06, 2010 8:38 am
- Post datetime: 2010-05-24T00:47:00+00:00
- Post Title: [Request] James Cameron Avatar the game models

cool thanks;

was very close to solve it myself, but easier if someone else does it
## Post #15
- Username: elypter
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 19, 2010 6:44 pm
- Post datetime: 2010-05-26T19:04:15+00:00
- Post Title: [Request] James Cameron Avatar the game models

i hope someone is working on the uv coordinate problem.
it would be so cool to have correct textures.
thanks again for all the work and research.
## Post #16
- Username: Dez
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 09, 2007 1:41 pm
- Post datetime: 2010-05-29T14:04:25+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

Awesome stuff, please continue on this, thanks!
## Post #17
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2010-05-31T01:23:58+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

Any tool for convert xbt texture in png/dds?
## Post #18
- Username: maxnuke
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 28, 2010 4:36 am
- Post datetime: 2010-06-27T20:58:23+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

To begin I  would like to thank for the tool. The problem with multi-uv mapping is very annoying.
I'd like to know if it's possible to import skeleton and animation too.
sorry for my english ^^
## Post #19
- Username: Maxunit
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 28, 2010 7:49 am
- Post datetime: 2010-06-28T22:49:50+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

maxnuke, how did you manage to get the uvmap being correctly assigned to the model?

If I import the Thanator model with the script, then the UVMap is not correct :/

Greetings,

Maxunit
## Post #20
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2010-06-29T07:24:31+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

excuse me for asking this question here !
how should i extract the content of avatar packages ?
## Post #21
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-06-29T12:53:08+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

> Reply from shekofte
>
> excuse me for asking this question here !
how should i extract the content of avatar packages ?

please go to sir aluigi's site and there's the script you need to extract the game data, it's below
[http://aluigi.org/papers/bms/avatar.bms](http://aluigi.org/papers/bms/avatar.bms)
## Post #22
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2010-06-29T16:33:31+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

yes i saw it , but :

> # Avatar: The Game (0.1a not 100% supported)
whether you extracted only part of packages ?
i want to access to all of data !
## Post #23
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-06-29T17:06:43+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

what version of quickbms are you using? please download the latest version, mesh/anim/tex files are located on data.pak
and take note that the script only works for pc and 360 pak files  

goodluck
## Post #24
- Username: McGregor II
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jun 29, 2010 8:21 am
- Post datetime: 2010-07-05T15:27:41+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

Can someone tell me how to pack extracted files back to the pak file.

EDIT: I also have problem with my language version. When i change the value in ini file from english to polish game starting normally but I see just objects without text, I also have extracted data.pak and  I look into polish lang file and I see my lang file is difference from english, spanish and few others and I'm not mean in english file is You Won and polish is Wygrałeś I mean the structure of the whole file is difference. Can anyone help me with this problem. If it''ll be needed I'll upload this files.
## Post #25
- Username: maxnuke
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 28, 2010 4:36 am
- Post datetime: 2010-07-13T19:41:07+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

> Reply from Maxunit
>
> maxnuke, how did you manage to get the uvmap being correctly assigned to the model?

If I import the Thanator model with the script, then the UVMap is not correct :/

Greetings,

Maxunit

Sorry for the late reply. The UVmap was not imported correctly: I repair it manually, but I don't know how to do with multi-uvmap. I use maya.
## Post #26
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2010-10-09T08:43:50+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

blender script now exists for importing virtually all xbg models, also unpacks textures to .dds files
## Post #27
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2010-10-11T14:11:14+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

> Reply from rmezatang
>
> blender script now exists for importing virtually all xbg models, also unpacks textures to .dds files

Any love for 3DSMax and this script?
## Post #28
- Username: ashkanhsj
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Mar 17, 2010 5:42 am
- Post datetime: 2010-11-28T23:19:53+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

Guys, are there any fixes for UV mapping?
## Post #29
- Username: Maxunit
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 28, 2010 7:49 am
- Post datetime: 2010-12-26T20:53:53+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

Sorry for bumping,

is anyone still working on the Blender script or has work been abandoned? Would be sad, because now there are finally proper working unpack and re-pack tools, only either Blender or Maxscripts are missing, so that we can import the models, maybe modify them, MAYBE!? re-export them and implement them into Avatar.

I hope anyone is still up to work on the Blender script or even on a Maxscript.

Greetings,

Maxunit
## Post #30
- Username: psychclw
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 26, 2012 11:23 pm
- Post datetime: 2013-01-09T06:44:23+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

> Reply from rmezatang
>
> blender script now exists for importing virtually all xbg models, also unpacks textures to .dds files
exists where? can someone post script?
## Post #31
- Username: Kirin
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 01, 2017 7:12 am
- Post datetime: 2019-02-19T23:15:43+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

Hi there, I have problem with import this file into a Blender. Is it possible to solve this problem?

```
low_tree.xbg
--------------------------------------------------
--------------------------------------------------
chunk: LTMR 44 (1, 136)
d:\James Cameron`s Avatar - The Game\GRAPHICS\_MATERIALS\SSEAUT-M-20090402311697
34.xbm
DiffuseTexture1
0 d:\James Cameron`s Avatar - The Game\graphics\av_environment\_rainforest\tree\
_textures\rf_willow_tree_leaf_01_d.dds
NormalTexture1
0 d:\James Cameron`s Avatar - The Game\graphics\av_environment\_rainforest\zrt_t
extures\rt_willow_leaf_a_n.dds
IlluminationTexture
0 d:\James Cameron`s Avatar - The Game\graphics\av_environment\_rainforest\tree\
_textures\rf_willow_tree_leaf_01_d.dds
d:\James Cameron`s Avatar - The Game\GRAPHICS\_MATERIALS\SSEAUT-M-20090401536106
23.xbm
DiffuseTexture2
1 d:\James Cameron`s Avatar - The Game\graphics\av_environment\_rainforest\tree\
_textures\rft_tree_bark_mossy_01b_d.dds
DiffuseTexture1
1 d:\James Cameron`s Avatar - The Game\graphics\av_environment\_rainforest\tree\
_textures\rft_ecorces_willow_tree_01_d.dds
NormalTexture1
1 d:\James Cameron`s Avatar - The Game\graphics\av_environment\_rainforest\tree\
_textures\rft_ecorces_willow_tree_01_n.dds
chunk: EDON 180 (1, 10569)
chunk: MB2O 10749 (1, 6040)
chunk: DIKS 16789 (1, 104)
chunk: DNKS 16893 (1, 1964)
chunk: SDOL 18857 (1, 290845)
Traceback (most recent call last):
  File "Avatar.py", line 263, in Parser
    xbgParser(filename,g)
  File "Avatar.py", line 192, in xbgParser
    if chunk == 'SDOL':SDOL(g)
  File "Avatar.py", line 25, in SDOL
    indiceSectionSize = g.i(1)[0]
  File "D:\python\WatchDogs-2014-06-25\newGameLib\myLibraries\binaresLib.py", li
ne 100, in i
struct.error: unpack requires a string argument of length 4
```


Here is file - [http://www.mediafire.com/file/0jut2j41k ... e.zip/file](http://www.mediafire.com/file/0jut2j41kxsqi1y/navi_willow_tree.zip/file)
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-20T10:31:52+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

I've made a small patch:

```
		x=g.tell()
		g.seek(x+16)
		mesh=Mesh()
```


but as you can see there's the next hurdle in PMCU chunk. Don't have the time to fix this so you might wait for the author.

console output:
Avatar[PC]\navi_willow_tree.xbg
--------------------------------------------------
--------------------------------------------------
chunk: LTMR 44 (1, 136)
x:\Avatar[PC]\navi_willow_tree.xbgGRAPHICS\_MATERIALS\
SSEAUT-M-2009040231169734.xbm
x:\Avatar[PC]\navi_willow_tree.xbgGRAPHICS\_MATERIALS\
SSEAUT-M-2009040153610623.xbm
chunk: EDON 180 (1, 10569)
chunk: MB2O 10749 (1, 6040)
chunk: DIKS 16789 (1, 104)
chunk: DNKS 16893 (1, 1964)
chunk: SDOL 18857 (1, 290845)
chunk: XOBB 309702 (1, 44)
chunk: HPSB 309746 (1, 36)
chunk: DOL 309782 (1, 28)
chunk: PMCP 309810 (1, 28)
chunk: PMCU 309838 (1, 28)
[(1, 1062, 1062, 3186, 32, 666, 3018), (-1, -1, -1, -1, -1, -1, -1, -1, -1, -1,
-1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1,
-1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1)]
Traceback (most recent call last):
  File "Avatar-dbg.py", line 268, in Parser
  File "Avatar-dbg.py", line 235, in xbgParser
IndexError: tuple index out of range
##############################



navi_willow_tree.png (50.01 KiB) Viewed 204 times
## Post #33
- Username: Kirin
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 01, 2017 7:12 am
- Post datetime: 2019-02-20T15:25:58+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

Thank you, I will wait for the author.
## Post #34
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-26T19:55:41+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

Problem is that vertex stride is 32 for the first submesh; script is very hard to debug for me.

```
-1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1,
-1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1)]
[(1, 3745, 3745, 11235, 40, 2521, 3034), (1, 2, 3, 4, 5, 6, 7, 8, 53, 54, 55, 56
, 57, 58, 59, 60, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,
 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1)]
[(0, 478, 478, 1434, 40, 356, 3034), (10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 10
, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10
, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10)]
[(0, 518, 518, 1554, 40, 388, 3034), (21, 22, 23, 24, 25, 26, 27, 28, 29, 21, 21
, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21
, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21, 21)]
[(0, 574, 574, 1722, 40, 428, 3034), (62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 62
, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62
, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62, 62)]
[(0, 374, 374, 1122, 40, 280, 3034), (73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 73
, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73
, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73, 73)]
[(0, 478, 478, 1434, 40, 356, 3034), (32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 32
, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32
, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32, 32)]
```




navi_willow_tree-xbg.jpg (158.92 KiB) Viewed 180 times
## Post #35
- Username: Kirin
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 01, 2017 7:12 am
- Post datetime: 2019-03-02T19:33:57+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

Is there a way to get mesh from this file?
## Post #36
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-02T19:41:16+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

Using hex2obj (view link in my sig) you need to load the xbg, enter the parameters from the picture in my previous post then File/SaveAs mesh and you're done.

You can also copy the following lines into a text file, rename it to whatever.H2O and load it with File/Open H2O :

0x406D4 22899
Vb1
40 12
0x9E40 5425
020400
0x0 255
## Post #37
- Username: VirtualTurtle
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 03, 2017 8:58 am
- Post datetime: 2019-06-02T16:09:22+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

I've attempted to use both the blender script and hex2obj with no luck. the blender script is having difficulty finding newGameLib, even when the folder is in the same directory. Someone who's done this before, how did you get it to work? Hex2Obj was a bit too technical for me, I loaded the .H2O file and tried a .xbg file, but it said something about the vertex count. I'm looking for anything that'll work here.
## Post #38
- Username: Ironcarnage101
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 31, 2021 7:45 am
- Post datetime: 2021-10-29T08:54:04+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

How would I use the files provided? I've tried to install the Avatar.py addon to my Blender but it won't work. Also is there a safe download of the game so I can rip what I want from the game's files?
## Post #39
- Username: odocha0986
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 21, 2023 12:13 am
- Post datetime: 2023-03-20T16:19:54+00:00
- Post Title: Re: [Request] James Cameron Avatar the game models

> Reply from omfgpota ↑Tue Jun 29, 2010 8:53 pm at Tue Jun 29, 2010 8:53 pm
>
> 
shekofte wrote:excuse me for asking this question here !
how should i extract the content of avatar packages ?

please go to sir aluigi's site and there's the script you need to extract the game data, it's below
http://aluigi.org/papers/bms/avatar.bms

not work when reimport it into a pak file again, is there any other method?
