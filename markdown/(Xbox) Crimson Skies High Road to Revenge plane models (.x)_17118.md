## Post #1
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2017-10-10T14:22:03+00:00
- Post Title: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

I´m extracting Crimson skies plane models to unity (right now).
The models are in the game iso in an airplanes.zip file with each plane in a bin packaged file.
It can be extracted (textures & model files) with this quickbms script [http://aluigi.org/bms/crimson_skies.bms](http://aluigi.org/bms/crimson_skies.bms)

Textures are DXT5/DXT1 with some xbox swizzled images and some *~a.tga file that i don´t know the format.

I imported all the plane models with texture into Unity, they are .x files but they aren´t DIRECTX binary files:



Geometry of the planes are in Vertexblocks of 32 bytes:
12 bytesfor vertex
4 bytes for packed normals
4* 4 bytes of UV (each mesh can have up to 4 textures so they have up to 4 uv definitions)

My problem is that i really don´t know how to unpack the uv values. 
U: 2 bytes from 0 to 65536
V: 2 bytes from 0 to 65536

The usual way should be value/65536, but i get correct UV shapes with wrong dimensions (~1/4 size)


Then i divided the value by 16384, and i get mostly correct uvs but in some cases they are not (0,16384,46152...):



i´ve even tried to mask the value: (u & 16383) / 16384f


These are the Vertex Blocks of one of the propellers (the black squares with a red circle)

```
C8 7A 1A 3F 91 02 1C 3F 14 E3 85 BF 00 00 40 80 56 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
64 7A 1A BF 1B 39 1C BF 3A D9 85 BF 00 00 40 80 AA 3F 00 C0 00 00 00 00 00 00 00 00 00 00 00 00
9C 2F 1B 3F 91 85 1B BF 40 D9 85 BF 00 00 40 80 31 00 25 C0 00 00 00 00 00 00 00 00 00 00 00 00
64 7A 1A BF 1B 39 1C BF 3A D9 85 BF 00 00 C0 7F AA 3F 00 C0 00 00 00 00 00 00 00 00 00 00 00 00
9C 2F 1B 3F 91 85 1B BF 40 D9 85 BF 00 00 C0 7F 31 00 25 C0 00 00 00 00 00 00 00 00 00 00 00 00
A4 2F 1B BF 54 4E 1B 3F 0C E3 85 BF 00 00 C0 7F CF 3F DB FF 00 00 00 00 00 00 00 00 00 00 00 00
C8 7A 1A 3F 91 02 1C 3F 14 E3 85 BF 00 00 C0 7F 56 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00

```


Position 1AFB7 of this file
[https://www.dropbox.com/s/edsugfb9b7wak ... yro.x?dl=0](https://www.dropbox.com/s/edsugfb9b7wak5j/airplanepf_minigyro.x?dl=0)




Any help??? I'm really desperate about this, i don´t how many hours i´ve worked in this problem 

Thanks
## Post #2
- Username: ThunderOwl
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 24, 2018 7:52 pm
- Post datetime: 2018-09-24T12:50:04+00:00
- Post Title: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

Hello. Could you be so helpful to tell more about how to import .x files into any program. Yes, i have tried Blender26 .x import, and also LithUnwrap, but those does not work. As you said - those are not really DirextX files I guess. Can you tell please about Crimson Skies .x importing? Or, maybe share plane models (no matter UV condition) in some usual format?
Thank You in advance!
## Post #3
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2018-09-25T11:23:04+00:00
- Post Title: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

I´ve attached a really fast and incomplete noesis plugin for crimson skies planes .x

It´s very incomplete and without normals,uvs or texture support.

Probably you want it for 3d printing or something like that, your main problem with this plugin it´s that some submeshes need to be repositioned by a position matrix and i don´t know howto do it with noesis.





edit: i´ve found howto position the submesh by matrix

[CrimsonSkies_Xbox_X.zip](https://xentaxbackup.github.io/file/14914_CrimsonSkies_Xbox_X.zip)
## Post #4
- Username: ThunderOwl
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 24, 2018 7:52 pm
- Post datetime: 2018-09-25T12:38:18+00:00
- Post Title: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

IronArthur, Thanks a lot! Later tonight I will try how it goes, I have been using Noesis before, including already for textures from Crimson Skies. It looks like it will be more than enough for my curiosity  Thing is, I started to learn UE4 last year, and i am all about sci-fi aerial combat. Well, lack of such games in past years is main reason why I started. Terminal Velocity, Rogue Squadron 3D, Crimson Skies - kind of cornerstones for me  Will try to use these exports as references or bases for some UE4 flying models. Just personal learning for now.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-25T17:43:20+00:00
- Post Title: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

> Reply from IronArthur
>
> It´s very incomplete and without normals,uvs or texture support.Getting uvs:
rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 32, 20)
(uvs2 assumed to be located at 24).

This is the sample where uvs are correct? I didn't get your size problem; you'd need to upload the concerning sample and its texture(s).

Would make sense to separate the submeshes into groups, btw.

Here's uvs for main mesh:



minigyro.jpg (128.02 KiB) Viewed 278 times
## Post #6
- Username: ThunderOwl
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 24, 2018 7:52 pm
- Post datetime: 2018-09-25T21:17:13+00:00
- Post Title: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

@IronArthur - Thanks one more time! I got Noesis plugin doing its thing, but, I had to delete line 30 in it, about textures path. There was error about "os", i was lazy to properly find fix, just deleted that  I attach screenshots what i got - I guess that is a good basis for "further investigations":)



CrimsonPlane1.jpg (255.84 KiB) Viewed 273 times
## Post #7
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2018-09-26T12:09:48+00:00
- Post Title: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

> Reply from shakotay2
>
> IronArthur wrote:It´s very incomplete and without normals,uvs or texture support.Getting uvs:
rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 32, 20)
(uvs2 assumed to be located at 24).

This is the sample where uvs are correct? I didn't get your size problem; you'd need to upload the concerning sample and its texture(s).

Would make sense to separate the submeshes into groups, btw.

Here's uvs for main mesh:
minigyro.jpg

I didn´t know howto make a submesh in noesis it was my first time doing a plugin and first time in python, i only copied stuff from others plugin. There is any documentation??

I´ve tried a lot of different options to divide the UV shorts
var uaux = (reader.ReadInt16());
var vaux = (reader.ReadInt16());
u = (float)uaux / 65536f;
v = (float)vaux / 65536f;


var uaux = (reader.ReadInt16());
var vaux = (reader.ReadInt16());
u = (float)uaux / 32768f;
v = (float)vaux / 32768f;



This one it´s pretty much accurate but has some cases that has errors:
var uaux = (reader.ReadInt16());
var vaux = (reader.ReadInt16());
u = (float)uaux / 16384f;
v = (float)vaux / 16384f;



Right now in Unity i´ve mostly correct uvs and i doing this ugly stuff:
var uaux = (reader.ReadInt16()); //Signed short
if (uaux > 16384f || uaux < -16384f)
    u = ((float)(uaux & 16383) / 16384f);
else
    u = ((float)(uaux) / 16384f);



I´ve uploaded one of the most problematic model the Cinematic model for the Devastator model (the right one in previous screenshots)
[https://www.dropbox.com/s/36ozeub6dlqow ... tor.x?dl=0](https://www.dropbox.com/s/36ozeub6dlqow53/AirplaneHR_Devastator.x?dl=0)

In Hex2Obj i look for the prop_fast_1 object.


This mesh should be the circular propeller in the airplanes with a yellow strip.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-26T17:47:03+00:00
- Post Title: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

> Reply from IronArthur
>
> I didn´t know howto make a submesh in noesis it was my first time doing a plugin and first time in python, i only copied stuff from others plugin. There is any documentation??Not for details, afaik. There's 
noesis\plugins\python\__NPReadMe.txt
noesis\plugins\python\__NPExample.txt
and a header file (for 'C', but descriptions of functions and constants are important to know)
noesis\pluginsource\pluginshare.h

> Right now in Unity i´ve mostly correct uvs and i doing this ugly stuff:
>
> var uaux = (reader.ReadInt16()); //Signed short
>
> if (uaux > 16384f || uaux < -16384f)
>
>     u = ((float)(uaux & 16383) / 16384f);
>
> else
>
>     u = ((float)(uaux) / 16384f);Well, just cutting off the higher 2 bits doesn*t make you lose texture parts?

> This mesh should be the circular propeller in the airplanes with a yellow strip.you can press the 'UVs' button to check whether it's "proper".

Do you have separate submeshes in unity?

I've put some g sm_x lines into the obj created by Noesis and loaded it into blender (body uv2 scaled by 2.75):
edit: well, I used the wrong uv set, uv1: offset 20, uv2: offset 24; IronArthur found a set the suiting one uv1 at offset 16, depends on the submesh



Devastator.jpg (225.32 KiB) Viewed 253 times


(Without the texture for the body I can't tell more. Could be a matter of 2nd uvs?)

Here's the details for building submeshes:
(example for submesh 84, last vSum was 1821, current vSum= 2925: 
f  1821/1821/1821 1820/1820/1820 1818/1818/1818
g sm_1
f  1824/1824/1824 1823/1823/1823 1822/1822/1822
...
f  2924/2924/2924 2925/2925/2925 2917/2917/2917
g sm_2
f  2928/2928/2928 2927/2927/2927 2926/2926/2926
)
1. SM, vCnt: 4, vSum 4 (0x2e5 TrisBuff)
2. SM, vCnt: 16, vSum 20 (0x5b3)
3. SM, vCnt: 16, vSum 36 (0x8ff)
4. SM, vCnt: 16, vSum 52 (0xc4b)
5. SM, vCnt: 34, vSum 86 (0x11d7)
6. SM, vCnt: 24, vSum 110 (0x1690)
7. SM, vCnt: 36, vSum 146 (0x1ca5)
8. SM, vCnt: 38, vSum 184 (0x231c)
9. SM, vCnt: 20, vSum 204 (0x2797)
10. SM, vCnt: 21, vSum 225 (0x2b64)
11. SM, vCnt: 21, vSum 246 (0x3027)
12. SM, vCnt: 144, vSum 390 (0x4514)
13. SM, vCnt: 8, vSum 398 (0x4c20)
14. SM, vCnt: 8, vSum 406 (0x4e15)
15. SM, vCnt: 28, vSum 434 (0x52e9)
16. SM, vCnt: 64, vSum 498 (0x5d0b)
17. SM, vCnt: 28, vSum 526 (0x6339)
18. SM, vCnt: 20, vSum 546 (0x6774)
19. SM, vCnt: 20, vSum 566 (0x6bf7)
20. SM, vCnt: 14, vSum 580 (0x6f09)
21. SM, vCnt: 14, vSum 594 (0x71f4)
22. SM, vCnt: 44, vSum 638 (0x789e)
23. SM, vCnt: 64, vSum 702 (0x82d6)
24. SM, vCnt: 20, vSum 722 (0x8964)
25. SM, vCnt: 14, vSum 736 (0x8c74)
26. SM, vCnt: 14, vSum 750 (0x8f5d)
27. SM, vCnt: 44, vSum 794 (0x9605)
28. SM, vCnt: 64, vSum 858 (0xa02d)
29. SM, vCnt: 20, vSum 878 (0xa694)
30. SM, vCnt: 20, vSum 898 (0xaa49)
31. SM, vCnt: 14, vSum 912 (0xad58)
32. SM, vCnt: 14, vSum 926 (0xb040)
33. SM, vCnt: 44, vSum 970 (0xb6e7)
34. SM, vCnt: 64, vSum 1034 (0xc10e)
35. SM, vCnt: 20, vSum 1054 (0xcb0c)
36. SM, vCnt: 20, vSum 1074 (0xd2e8)
37. SM, vCnt: 38, vSum 1112 (0xe061)
38. SM, vCnt: 38, vSum 1150 (0xeed4)
39. SM, vCnt: 18, vSum 1168 (0xf70b)
40. SM, vCnt: 18, vSum 1186 (0xfe46)
41. SM, vCnt: 117, vSum 1303 (0x10e23)
42. SM, vCnt: 117, vSum 1420 (0x1242a)
43. SM, vCnt: 28, vSum 1448 (0x13490)
44. SM, vCnt: 28, vSum 1476 (0x13f28)
45. SM, vCnt: 43, vSum 1519 (0x1461a)
46. SM, vCnt: 18, vSum 1537 (0x14f27)
47. SM, vCnt: 18, vSum 1555 (0x15658)
48. SM, vCnt: 18, vSum 1573 (0x15d89)
49. SM, vCnt: 18, vSum 1591 (0x164ba)
50. SM, vCnt: 18, vSum 1609 (0x16beb)
51. SM, vCnt: 18, vSum 1627 (0x1731c)
52. SM, vCnt: 18, vSum 1645 (0x17a4d)
53. SM, vCnt: 18, vSum 1663 (0x1817e)
54. SM, vCnt: 12, vSum 1675 (0x186d1)
55. SM, vCnt: 15, vSum 1690 (0x18cbc)
56. SM, vCnt: 12, vSum 1702 (0x191c9)
57. SM, vCnt: 15, vSum 1717 (0x197b4)
58. SM, vCnt: 4, vSum 1721 (0x19986)
59. SM, vCnt: 4, vSum 1725 (0x19ab7)
60. SM, vCnt: 4, vSum 1729 (0x19beb)
61. SM, vCnt: 4, vSum 1733 (0x19d1f)
62. SM, vCnt: 4, vSum 1737 (0x19e53)
63. SM, vCnt: 4, vSum 1741 (0x19f87)
64. SM, vCnt: 4, vSum 1745 (0x1a0bb)
65. SM, vCnt: 4, vSum 1749 (0x1a1ef)
66. SM, vCnt: 4, vSum 1753 (0x1a323)
67. SM, vCnt: 4, vSum 1757 (0x1a457)
68. SM, vCnt: 4, vSum 1761 (0x1a58b)
69. SM, vCnt: 4, vSum 1765 (0x1a6bd)
70. SM, vCnt: 4, vSum 1769 (0x1a7f2)
71. SM, vCnt: 4, vSum 1773 (0x1a927)
72. SM, vCnt: 4, vSum 1777 (0x1aa5c)
73. SM, vCnt: 4, vSum 1781 (0x1ab91)
74. SM, vCnt: 4, vSum 1785 (0x1acc5)
75. SM, vCnt: 4, vSum 1789 (0x1adf9)
76. SM, vCnt: 4, vSum 1793 (0x1af2d)
77. SM, vCnt: 4, vSum 1797 (0x1b061)
78. SM, vCnt: 4, vSum 1801 (0x1b195)
79. SM, vCnt: 4, vSum 1805 (0x1b2c9)
80. SM, vCnt: 4, vSum 1809 (0x1b3fd)
81. SM, vCnt: 4, vSum 1813 (0x1b531)
82. SM, vCnt: 4, vSum 1817 (0x1b66b)
83. SM, vCnt: 4, vSum 1821 (0x1b7a7)
84. SM, vCnt: 1104, vSum 2925 (0x311b4) <<<
85. SM, vCnt: 65, vSum 2990 (0x34f95)
86. SM, vCnt: 200, vSum 3190 (0x36cbc)  <<
87. SM, vCnt: 70, vSum 3260 (0x37db6)
88. SM, vCnt: 971, vSum 4231 (0x3f93a) <<<
89. SM, vCnt: 675, vSum 4906 (0x467d7) <<<
90. SM, vCnt: 120, vSum 5026 (0x487d6)
91. SM, vCnt: 204, vSum 5230 (0x4a508)  <<
92. SM, vCnt: 43, vSum 5273 (0x4b02a)
93. SM, vCnt: 4, vSum 5277 (0x4b43a)
94. SM, vCnt: 4, vSum 5281 (0x4b5e6)
95. SM, vCnt: 4, vSum 5285 (0x4b792)
96. SM, vCnt: 4, vSum 5289 (0x4b8c9)
97. SM, vCnt: 4, vSum 5293 (0x4ba02)
98. SM, vCnt: 4, vSum 5297 (0x4bbb1 TrisBuff)
## Post #9
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-09-26T21:17:29+00:00
- Post Title: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

You should put these up on the Models Resource, they come in handy: [https://www.models-resource.com/](https://www.models-resource.com/)
## Post #10
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2018-09-26T21:46:49+00:00
- Post Title: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

> Reply from shakotay2
>
> 
Right now in Unity i´ve mostly correct uvs and i doing this ugly stuff:
var uaux = (reader.ReadInt16()); //Signed short
if (uaux > 16384f || uaux < -16384f)
    u = ((float)(uaux & 16383) / 16384f);
else
    u = ((float)(uaux) / 16384f);Well, just cutting off the higher 2 bits doesn*t make you lose texture parts?
This mesh should be the circular propeller in the airplanes with a yellow strip.you can press the 'UVs' button to check whether it's "proper".

Do you have separate submeshes in unity?

I've put some g sm_x lines into the obj created by Noesis and loaded it into blender (body uv1 scaled by 2.75):
Devastator.jpg
(Without the texture for the body I can't tell more. Could be a matter of 2nd uvs?)

I don´t know if i lose some info about uvs, but if use short/65k the texture is like 1/4 of the full model.

I´ve every submesh and object in Unity. it´s really easy when you are on a full game engine:


I´ve uploaded two main textures of that model 
[https://www.dropbox.com/s/8undw9x8amhft ... r.png?dl=0](https://www.dropbox.com/s/8undw9x8amhft6a/devastator.png?dl=0) MainTexture
[https://www.dropbox.com/s/2qf19vm4fizlc ... r.png?dl=0](https://www.dropbox.com/s/2qf19vm4fizlcwq/prop_devastator.png?dl=0) Propellers texture

the 2nd 3rd and 4th uv are used with extra Mask textures for damage and normal texture.


In hex2obj i see the uv:
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-27T07:13:00+00:00
- Post Title: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

> Reply from IronArthur
>
> I´ve every submesh and object in Unity. it´s really easy when you are on a full game engine:That's cool!  

> I´ve uploaded two main textures of that modelThanks!

> In hex2obj i see the uv:yeah, I'd to zoom (and rotate it) to make it fit the texture:



prop.jpg (167.9 KiB) Viewed 240 times
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-27T07:18:32+00:00
- Post Title: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

And here's what I got for the body:



devastator-body.jpg (207.98 KiB) Viewed 238 times


the H2O file:

0x311B4 4080
Vb1
32 16
0x1B89F 1104
020300
0x0 255

You could add texture/submesh support to Noesis; I remember having done this using materials:
matName = ["0", "1", "2", "3", "4", "5", "6", "7", "8", "9", "10", "11", "12", "13", "14", "15"]
(Where you can replace the numbers by texturenames.)

        rapi.rpgSetMaterial(matName[j])
## Post #13
- Username: ThunderOwl
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 24, 2018 7:52 pm
- Post datetime: 2018-09-27T07:33:17+00:00
- Post Title: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

Guys, could you tell (share) is at this point some more "advanced" (fixed) Noesis plugin usable, than that posted above?  Thing is, I try to follow, but I don't know all nuanses about sub-meshes and stuff  Thank You in advance!
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-27T07:40:51+00:00
- Post Title: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

For me, I simply added this line
rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 32, 16)
where I have to change uv1 offset (16) manually. Don't have the time to change the code to automatically detect the offset
(sometimes uv1 offset is 20). At 24 maybe other channel, such as for destruction texture.

(I also had to scale up the uv1 for the body in my previous post with 5.5; with Noesis obj output it's 2.75)
## Post #15
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2018-12-01T05:29:58+00:00
- Post Title: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

I'd like the updated version of this noesis plugin since I have no idea what to do. I'm making a mod for a game and these models extracted w/ textures would help amazingly.
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-01T10:21:13+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

In the CrimsonSkies_Xbox_X.py script in [Noesis_folder]/plugins/python add the line like this:

```
	rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 32, 16)
	#rapi.rpgBindUV1BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 32, 20)
	#rapi.rpgBindUV2BufferOfs(VertBuff, noesis.RPGEODATA_SHORT, 32, 24)
	rapi.rpgCommitTriangles(TrisBuff, noesis.RPGEODATA_USHORT, numTris, noesis.RPGEO_TRIANGLE, 1)

```
Take care for the indents! Don't mix tabs and blanks!

(I generally don't upload scripts from other authors; I just offer patches.)
## Post #17
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2018-12-04T05:34:06+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

Did that. What exactly should it change? It doesn't appear to show textures or uvs or anything. This is my screen:



Should be placed here, right?
## Post #18
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2018-12-04T06:07:55+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

I got the UVS extracted in Nosesis, about to try with Blender.

EDIT:

I don't think this is working.
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-04T20:15:03+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

> Reply from Mrblue630
>
> It doesn't appear to show textures or uvs or anything.Tested it with Devastator only and it work: [viewtopic.php?f=16&t=17118&p=144462&hil ... B4#p144462](http://forum.xentax.com/viewtopic.php?f=16&t=17118&p=144462&hilit=+0x311B4#p144462)

Other models might need different offsets, whatever.
## Post #20
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2018-12-04T22:02:26+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

I'm using Noesis only to extract the model and uvs, not hex2obj.
I'm trying to extract the cinematic HR Devastator.

I tried to use hex2obj on both devastator models and they only got the fuselage bit, not the cockpit or engine props or anything.

Is there any way to make noesis extract each submesh grouped under the main mesh or even individually so I can remove the landing gear and the weird ass thing jutting from the side of the devastator without manually having to delete it all in blender? Mind you, I tried that texture/submesh support thing for noesis that you suggested adding in the python in the last page, but it kept spewing out an error about the letter j or something.
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-04T22:53:25+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

> Reply from Mrblue630
>
> I'm trying to extract the cinematic HR Devastator.I have the AirplaneHR_Devastator.x only.

> Is there any way to make noesis extract each submeshShould be possible

> without manually having to delete it all in blender?dunno, what you tried exactly, so can't tell.

> Mind you, I tried that texture/submesh support thing for noesis that you suggested adding in the python in the last page, but it kept spewing out an error about the letter j or something.You need some basic understanding of Noesis python scripting; you'll need a loop which introduces the variable 'j' (or i, whatever)
for j in range(0, maxMatNumber):

(If maxMatNumber isn't defined by your script you might use 2, 3 or 4 in a first approach.)
## Post #22
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2018-12-05T02:54:55+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

The airplanehr_devastator.x is the cinematic devastator.

How would you go about making it possible to extract submeshes in noesis?

The intention is to have the meshes in a hierachy: the main mesh (the fuselage) as the parent with the other stuff (rotors, the light fx submeshes, landing gear, etc.) sorted under it as a child. I'm happy to have it extract all submeshes individually/one-by-one though however if that's possible.
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-05T08:19:53+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

> Reply from Mrblue630
>
> How would you go about making it possible to extract submeshes in noesis?
read here for example:
[viewtopic.php?f=16&t=12070&p=99276&hili ... nge#p99276](http://forum.xentax.com/viewtopic.php?f=16&t=12070&p=99276&hilit=submeshes+script+range#p99276)

I wouldn't do it in Noesis, though. Here I used simple "C":
[viewtopic.php?f=16&t=17118&p=144446&hil ... ng#p144446](http://forum.xentax.com/viewtopic.php?f=16&t=17118&p=144446&hilit=submeshes+building#p144446)

> The intention is to have the meshes in a hierachy: the main mesh (the fuselage) as the parent with the other stuff (rotors, the light fx submeshes, landing gear, etc.) sorted under it as a child. I'm happy to have it extract all submeshes individually/one-by-one though however if that's possible.yeah, you need to expand the script then, lots of work with this hierarchy:

Detected file type: Crimson Skies (Xbox)
MeshName  Model_Root
Obj : AirplaneHR_Devastator numMeshes 0 numChildsInObj 5
Obj : AirplaneHR_Devastator_dmg0 numMeshes 0 numChildsInObj 28
Obj : rocket_launcher numMeshes 0 numChildsInObj 14
rocket_launcher.tga MaterialName

-------------------------------------
Abbreviations:
nM 1 nC 0: numMeshes 1 numChildsInObj 0
nCiO: numChildsInObj
pS: polySurface
-------------------------------------
4 numBlocks
0x252  VertBuff
6 numTris
0x2e5 TrisBuff
Obj : pPlane1 nM 1 nC 0
rocket_launcher.tga MatName
16 numBlocks
0x3a0  VertBuff
33 numTris
0x5b3 TrisBuff
Obj : pCylinder13 nM 1 nC 0
rocket_launcher.tga MatName
16 numBlocks
0x6ec  VertBuff
33 numTris
0x8ff TrisBuff
Obj : pCylinder12 nM 1 nC 0
rocket_launcher.tga MatName
16 numBlocks
0xa38  VertBuff
33 numTris
0xc4b TrisBuff
Obj : pCylinder11 nM 1 nC 0
rocket_launcher.tga MatName
34 numBlocks
0xd84  VertBuff
84 numTris
0x11d7 TrisBuff
Obj : pCylinder10 nM 1 nC 0
rocket_launcher.tga MatName
24 numBlocks
0x137d  VertBuff
36 numTris
0x1690 TrisBuff
Obj : pCube5 nM 1 nC 0
rocket_launcher.tga MatName
36 numBlocks
0x1812  VertBuff
60 numTris
0x1ca5 TrisBuff
Obj : pCylinder9 nM 1 nC 0
rocket_launcher.tga MatName
38 numBlocks
0x1e49  VertBuff
60 numTris
0x231c TrisBuff
Obj : pCube4 nM 1 nC 0
rocket_launcher.tga MatName
20 numBlocks
0x2504  VertBuff
30 numTris
0x2797 TrisBuff
Obj : pCube3 nM 1 nC 0
rocket_launcher.tga MatName
21 numBlocks
0x28b1  VertBuff
66 numTris
0x2b64 TrisBuff
Obj : pCylinder6 nM 1 nC 0
rocket_launcher.tga MatName
21 numBlocks
0x2d74  VertBuff
66 numTris
0x3027 TrisBuff
Obj : pCylinder5 nM 1 nC 0
Obj : pCylinder1 numMeshes 0 nCiO 2
Obj : pS1 numMeshes 0 nCiO 1
rocket_launcher.tga MatName
144 numBlocks
0x3301  VertBuff
390 numTris
0x4514 TrisBuff
Obj : pS5 nM 1 nC 0
Obj : pS2 numMeshes 0 nCiO 2
rocket_launcher.tga MatName
8 numBlocks
0x4b0d  VertBuff
18 numTris
0x4c20 TrisBuff
Obj : pS3 nM 1 nC 0
rocket_launcher.tga MatName
8 numBlocks
0x4d02  VertBuff
18 numTris
0x4e15 TrisBuff
Obj : pS4 nM 1 nC 0
Obj : pCube2 numMeshes 0 nCiO 3
rocket_launcher.tga MatName
28 numBlocks
0x4f56  VertBuff
60 numTris
0x52e9 TrisBuff
Obj : pS6 nM 1 nC 0
Obj : pS7 numMeshes 0 nCiO 1
rocket_launcher.tga MatName
64 numBlocks
0x54f8  VertBuff
138 numTris
0x5d0b TrisBuff
Obj : pS9 nM 1 nC 0
rocket_launcher.tga MatName
28 numBlocks
0x5fa6  VertBuff
60 numTris
0x6339 TrisBuff
Obj : pS10 nM 1 nC 0
rocket_launcher.tga MatName
20 numBlocks
0x64e1  VertBuff
30 numTris
0x6774 TrisBuff
Obj : pCube1 nM 1 nC 0
Obj : landing_gear numMeshes 0 nCiO 3
Obj : WingL_land_gear numMeshes 0 nCiO 1
devastator_landgear.tga MatName
20 numBlocks
0x6964  VertBuff
48 numTris
0x6bf7 TrisBuff
Obj : WingL_strut_top nM 1 nC 0 2
devastator_landgear.tga MatName
14 numBlocks
0x6d36  VertBuff
36 numTris
0x6f09 TrisBuff
Obj : WingL_support nM 1 nC 0
devastator_landgear.tga MatName
14 numBlocks
0x7021  VertBuff
36 numTris
0x71f4 TrisBuff
Obj : WingL_strut_bottom nM 1 nC 0 1
devastator_landgear.tga MatName
44 numBlocks
0x730b  VertBuff
108 numTris
0x789e TrisBuff
Obj : WingL_wheel_cover nM 1 nC 0 1
devastator_landgear.tga MatName
64 numBlocks
0x7ac3  VertBuff
228 numTris
0x82d6 TrisBuff
Obj : WingL_wheel nM 1 nC 0
Obj : WingR_land_gear numMeshes 0 nCiO 1
devastator_landgear.tga MatName
20 numBlocks
0x86d1  VertBuff
48 numTris
0x8964 TrisBuff
Obj : WingR_strut_top nM 1 nC 0 2
devastator_landgear.tga MatName
14 numBlocks
0x8aa1  VertBuff
36 numTris
0x8c74 TrisBuff
Obj : WingR_support nM 1 nC 0
devastator_landgear.tga MatName
14 numBlocks
0x8d8a  VertBuff
36 numTris
0x8f5d TrisBuff
Obj : WingR_strut_bottom nM 1 nC 0 1
devastator_landgear.tga MatName
44 numBlocks
0x9072  VertBuff
108 numTris
0x9605 TrisBuff
Obj : WingR_wheel_cover nM 1 nC 0 1
devastator_landgear.tga MatName
64 numBlocks
0x981a  VertBuff
228 numTris
0xa02d TrisBuff
Obj : WingR_wheel nM 1 nC 0
Obj : Nose_land_gear numMeshes 0 nCiO 1
devastator_landgear.tga MatName
20 numBlocks
0xa401  VertBuff
30 numTris
0xa694 TrisBuff
Obj : Nose_Base nM 1 nC 0 1
devastator_landgear.tga MatName
20 numBlocks
0xa7b6  VertBuff
48 numTris
0xaa49 TrisBuff
Obj : Nose_strut_top nM 1 nC 0 2
devastator_landgear.tga MatName
14 numBlocks
0xab85  VertBuff
36 numTris
0xad58 TrisBuff
Obj : Nose_support nM 1 nC 0
devastator_landgear.tga MatName
14 numBlocks
0xae6d  VertBuff
36 numTris
0xb040 TrisBuff
Obj : Nose_strut_bottom nM 1 nC 0 1
devastator_landgear.tga MatName
44 numBlocks
0xb154  VertBuff
108 numTris
0xb6e7 TrisBuff
Obj : Nose_wheel_cover nM 1 nC 0 1
devastator_landgear.tga MatName
64 numBlocks
0xb8fb  VertBuff
228 numTris
0xc10e TrisBuff
Obj : Nose_wheel nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
20 numBlocks
0xc4b7  VertBuff
36 numTris
0xcb0c TrisBuff
Obj : aileron_r_1 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
20 numBlocks
0xcc93  VertBuff
36 numTris
0xd2e8 TrisBuff
Obj : aileron_l_1 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
38 numBlocks
0xd46c  VertBuff
132 numTris
0xe061 TrisBuff
Obj : rudder_1 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
38 numBlocks
0xe2df  VertBuff
132 numTris
0xeed4 TrisBuff
Obj : rudder_2 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
18 numBlocks
0xf156  VertBuff
36 numTris
0xf70b TrisBuff
Obj : elevator_r_1 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
18 numBlocks
0xf891  VertBuff
36 numTris
0xfe46 TrisBuff
Obj : elevator_l_1 nM 1 nC 0
Prop_devastator.tga MatName
117 numBlocks
0xff70  VertBuff
522 numTris
0x10e23 TrisBuff
Obj : prop_still_1 nM 1 nC 0
Prop_devastator.tga MatName
117 numBlocks
0x11577  VertBuff
522 numTris
0x1242a TrisBuff
Obj : prop_still_2 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
28 numBlocks
0x12bbb  VertBuff
66 numTris
0x13490 TrisBuff
Obj : aileron_r_2 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
28 numBlocks
0x13653  VertBuff
66 numTris
0x13f28 TrisBuff
Obj : aileron_l_2 nM 1 nC 0
Prop_devastator.tga MatName
43 numBlocks
0x140a7  VertBuff
108 numTris
0x1461a TrisBuff
Obj : prop_fast_1 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
18 numBlocks
0x14972  VertBuff
48 numTris
0x14f27 TrisBuff
Obj : cowl_1 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
18 numBlocks
0x150a3  VertBuff
48 numTris
0x15658 TrisBuff
Obj : cowl_2 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
18 numBlocks
0x157d4  VertBuff
48 numTris
0x15d89 TrisBuff
Obj : cowl_3 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
18 numBlocks
0x15f05  VertBuff
48 numTris
0x164ba TrisBuff
Obj : cowl_4 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
18 numBlocks
0x16636  VertBuff
48 numTris
0x16beb TrisBuff
Obj : cowl_5 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
18 numBlocks
0x16d67  VertBuff
48 numTris
0x1731c TrisBuff
Obj : cowl_6 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
18 numBlocks
0x17498  VertBuff
48 numTris
0x17a4d TrisBuff
Obj : cowl_7 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
18 numBlocks
0x17bc9  VertBuff
48 numTris
0x1817e TrisBuff
Obj : cowl_8 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
12 numBlocks
0x182fc  VertBuff
18 numTris
0x186d1 TrisBuff
Obj : flap_l_2 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
15 numBlocks
0x187f7  VertBuff
21 numTris
0x18cbc TrisBuff
Obj : flap_l_1 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
12 numBlocks
0x18df4  VertBuff
18 numTris
0x191c9 TrisBuff
Obj : flap_r_2 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
15 numBlocks
0x192ef  VertBuff
21 numTris
0x197b4 TrisBuff
Obj : flap_r_1 nM 1 nC 0
Obj : hidden numMeshes 0 nCiO 26
4 numBlocks
0x198f3  VertBuff
6 numTris
0x19986 TrisBuff
Obj : wepC_1 nM 1 nC 0
4 numBlocks
0x19a24  VertBuff
6 numTris
0x19ab7 TrisBuff
Obj : wepC_2 nM 1 nC 0
4 numBlocks
0x19b58  VertBuff
6 numTris
0x19beb TrisBuff
Obj : collide_1 nM 1 nC 0
4 numBlocks
0x19c8c  VertBuff
6 numTris
0x19d1f TrisBuff
Obj : collide_2 nM 1 nC 0
4 numBlocks
0x19dc0  VertBuff
6 numTris
0x19e53 TrisBuff
Obj : collide_3 nM 1 nC 0
4 numBlocks
0x19ef4  VertBuff
6 numTris
0x19f87 TrisBuff
Obj : collide_4 nM 1 nC 0
4 numBlocks
0x1a028  VertBuff
6 numTris
0x1a0bb TrisBuff
Obj : collide_5 nM 1 nC 0
4 numBlocks
0x1a15c  VertBuff
6 numTris
0x1a1ef TrisBuff
Obj : wep_pri_1 nM 1 nC 0
4 numBlocks
0x1a290  VertBuff
6 numTris
0x1a323 TrisBuff
Obj : wep_pri_2 nM 1 nC 0
4 numBlocks
0x1a3c4  VertBuff
6 numTris
0x1a457 TrisBuff
Obj : wep_pri_3 nM 1 nC 0
4 numBlocks
0x1a4f8  VertBuff
6 numTris
0x1a58b TrisBuff
Obj : wep_pri_4 nM 1 nC 0
4 numBlocks
0x1a62a  VertBuff
6 numTris
0x1a6bd TrisBuff
Obj : wep_sec nM 1 nC 0
4 numBlocks
0x1a75f  VertBuff
6 numTris
0x1a7f2 TrisBuff
Obj : contrail_1 nM 1 nC 0
4 numBlocks
0x1a894  VertBuff
6 numTris
0x1a927 TrisBuff
Obj : contrail_2 nM 1 nC 0
4 numBlocks
0x1a9c9  VertBuff
6 numTris
0x1aa5c TrisBuff
Obj : contrail_3 nM 1 nC 0
4 numBlocks
0x1aafe  VertBuff
6 numTris
0x1ab91 TrisBuff
Obj : contrail_4 nM 1 nC 0
4 numBlocks
0x1ac32  VertBuff
6 numTris
0x1acc5 TrisBuff
Obj : exhaust_1 nM 1 nC 0
4 numBlocks
0x1ad66  VertBuff
6 numTris
0x1adf9 TrisBuff
Obj : exhaust_2 nM 1 nC 0
4 numBlocks
0x1ae9a  VertBuff
6 numTris
0x1af2d TrisBuff
Obj : exhaust_3 nM 1 nC 0
4 numBlocks
0x1afce  VertBuff
6 numTris
0x1b061 TrisBuff
Obj : exhaust_4 nM 1 nC 0
4 numBlocks
0x1b102  VertBuff
6 numTris
0x1b195 TrisBuff
Obj : exhaust_5 nM 1 nC 0
4 numBlocks
0x1b236  VertBuff
6 numTris
0x1b2c9 TrisBuff
Obj : exhaust_6 nM 1 nC 0
4 numBlocks
0x1b36a  VertBuff
6 numTris
0x1b3fd TrisBuff
Obj : exhaust_7 nM 1 nC 0
4 numBlocks
0x1b49e  VertBuff
6 numTris
0x1b531 TrisBuff
Obj : exhaust_8 nM 1 nC 0
4 numBlocks
0x1b5d8  VertBuff
6 numTris
0x1b66b TrisBuff
Obj : fx1_strobe_red1 nM 1 nC 0
4 numBlocks
0x1b714  VertBuff
6 numTris
0x1b7a7 TrisBuff
Obj : fx2_strobe_green1 nM 1 nC 0
devastator.tga MatName
Airplane_dmg_2.tga MatName
Airplane_dmg_3.tga MatName
devastator~n.tga MatName
1104 numBlocks
0x1b89f  VertBuff
4080 numTris
0x311b4 TrisBuff
devastator_spinner.tga MatName
65 numBlocks
0x34762  VertBuff
336 numTris
0x34f95 TrisBuff
devastatorHR.tga MatName
200 numBlocks
0x353a9  VertBuff
624 numTris
0x36cbc TrisBuff
70 numBlocks
0x374e3  VertBuff
102 numTris
0x37db6 TrisBuff
devastatorHR_Cage.tga MatName
971 numBlocks
0x37fc7  VertBuff
1722 numTris
0x3f93a TrisBuff
Devastator_cockpit.tga MatName
675 numBlocks
0x41364  VertBuff
1080 numTris
0x467d7 TrisBuff
Devastator_Seatback.tga MatName
SH_grime01.tga MatName
120 numBlocks
0x478c3  VertBuff
228 numTris
0x487d6 TrisBuff
aagun_player_flak.tga MatName
aagun_player_flak~a.tga MatName
204 numBlocks
0x48b75  VertBuff
336 numTris
0x4a508 TrisBuff
Obj : devastator numMeshes 8 nCiO 0
Prop_devastator.tga MatName
43 numBlocks
0x4aab7  VertBuff
108 numTris
0x4b02a TrisBuff
Obj : prop_fast_2 nM 1 nC 0
Obj : AirplaneHR_Devastator_dmg1 numMeshes 0 nCiO 1
4 numBlocks
0x4b3a7  VertBuff
6 numTris
0x4b43a TrisBuff
Obj : fx_enginefire2 nM 1 nC 0
Obj : AirplaneHR_Devastator_dmg2 numMeshes 0 nCiO 1
4 numBlocks
0x4b553  VertBuff
6 numTris
0x4b5e6 TrisBuff
Obj : fx_enginefire1 nM 1 nC 0
Obj : AirplaneHR_Devastator_dmg3 numMeshes 0 nCiO 3
4 numBlocks
0x4b6ff  VertBuff
6 numTris
0x4b792 TrisBuff
Obj : fx_enginefire2 nM 1 nC 0
4 numBlocks
0x4b836  VertBuff
6 numTris
0x4b8c9 TrisBuff
Obj : fx_wingfire3 nM 1 nC 0
4 numBlocks
0x4b96f  VertBuff
6 numTris
0x4ba02 TrisBuff
Obj : fx_enginefire3 nM 1 nC 0
Obj : AirplaneHR_Devastator_dmg4 numMeshes 0 nCiO 1
4 numBlocks
0x4bb1e  VertBuff
6 numTris
0x4bbb1 TrisBuff
Obj : fx_plane_dev_dmg4 nM 1 nC 0
## Post #24
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2018-12-05T10:08:00+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

Sorry to say, TMI for me. Too much to take in, and I'm pretty horrible when it comes to scripting, C or otherwise. I've noticed you've already got the plane body w/ textures and uvs applied in Blender

> Reply from shakotay2
>
> And here's what I got for the body:
devastator-body.jpg
Do you think you could just send me that .blend / .dae/obj file? If so, that'd be amazing.
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-05T10:31:58+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

here you go:


 AirplaneHR_Devastatorout uvs16.zip
(114.5 KiB) Downloaded 30 times


(scale uvs with 2.75)
## Post #26
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2018-12-05T21:08:34+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

UVs are broken.
This is what it looks like:
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-05T22:14:33+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

yeah, sorry, that was the second uv channel, or whatever.

I've updated the zip in my previous post.

Here's the blender file (picture/texture not included) which I created from the hex2obj outputs, iirc:


 devastator-body.zip
(125.19 KiB) Downloaded 33 times
## Post #28
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2018-12-05T23:52:10+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

Got it working, but I had to mess with a bunch of the UVS since they didn't fit properly for some reason. Cockpit and interior uvs are fucked since I had to reposition them, and they look ugly now but meh.
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-06T06:53:58+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

All I hear from you are complaints.
So go your own way then.
## Post #30
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2018-12-06T22:05:22+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

Just saying I got it working at the cost of the uv issues. Thanks, I guess?
## Post #31
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2018-12-11T14:54:54+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

I´m still haven´t found the universal way of reading the uvs from the game. It works in most models (at least with my strange way of doing) but has some exceptions like the Cinematic Devastator.

@Mrblue630
I´ve attached the pandora zep model like you pm'ed me, it´s a gltf file because that´s the only exporting option i´ve installed on my Unity. This models are embedded in Scene files and i haven´t really finished reading the 100% scene file, it works on static models (buildings) but moveable models they are not placed on the scene BIN file.

[https://www.dropbox.com/s/3g9g4vftdca1u ... a.zip?dl=0](https://www.dropbox.com/s/3g9g4vftdca1u4g/ZepPandora.zip?dl=0)




In the (0.0.0) position of this screenshot are most of the models you requested, but only parts of the Starker Sturm :



Edit: You´ve been lucky, the sturm is in other scene file (Final_boss.bin) there is the model but it has more parts than it should have because i don´t know what parts are from the boss and what parts are from other models

[https://www.dropbox.com/s/k6hqmagxvve8i ... m.zip?dl=0](https://www.dropbox.com/s/k6hqmagxvve8iz2/Sturm.zip?dl=0)
## Post #32
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2018-12-15T09:25:06+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

I know which models are which parts.
ZepEater_Doors.x
ZepEater_Teeth.x
ZepEater_Arms.x
And all the x's under the name ss_boss (SS is short for lit. Starker Sturm)
Starker Sturm uses a lot of parts from the Zepeater for the side jaws mounted on it.
Wait...
Is that Chicago in the first picture?
Could you send me that? I'd be really interested in taking a look at that since I heard there was a lot of unused content with the level, I'm curious if any of it is in the geometry.

I also did a lot of research into the games development and the models: It appears models were all done and exported with Autodesk Maya 2003. It may be possible to read the models using Maya.
## Post #33
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2018-12-15T10:09:40+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

They are regular models, you could read them in any program you want you don't need Maya. 

If you extract a mission file like the planes bin file, you have every model used in the scene. 

When I have some time I will export you the city but I warn you that some of the models are not placed in their positions. And some buildings uvs are just wrong.
## Post #34
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2018-12-15T22:38:07+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

Fine by me. What I mean though is that all the models were exported to .x using Maya, so it may be possible to find an .x importer for Maya that just does all the hard work, importing the UVS, textures, etc.
## Post #35
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2018-12-15T22:49:05+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

Oh, another thing! You don't need to export them all as gltf. Just bundle them in UnityPackages, I have unity. I can export scenes (w/ hierachy) into OBJ. With GLTF and me converting to OBJ I lose the hierachy so it all becomes one mesh.

If you could actually do this with the Pandora and Starker Sturm that'd be great so I can tinker with them in Unity before pushing ahead.

And another note, if you have Discord, please add me on there. I'm afraid I'm not notified when this thread gets updated and I may be out of contact for a couple days, but I'll be able to use Discord on my phone. Overall easier to keep in touch.

Revolver Ocelot#6732
## Post #36
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2019-04-08T08:57:50+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

> Reply from Cosmas47Mon Apr 08, 2019 7:29 am at Mon Apr 08, 2019 7:29 am
>
> 
Hi Arthur,
I registered today just to ask you about this! I've been reading your post https://forum.xentax.com/viewtopic.php?f=16&t=17118, looks like you've been making great progress. I'm actually interested in porting the original Crimson Skies to Unity myself. By any chance have you figured out how to extract the ZBD format files?

Philip

Hi, i´ll post here so everyone can read it.

If i´m not mistaken, zdb files are from the PC version of Crimson Skies. This post it´s about Crimson skies from the Xbox.

I´ve never looked into the PC version (even if it´s way better game than the xbox version). Maybe i´ll look into it.

Bye
## Post #37
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2019-04-09T09:40:21+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

I tried to reverse some of the ZBD files.

interp.zbd it´s a really easy "pak" file, uncompressed and unencrypted.



interpZBD.PNG (95.01 KiB) Viewed 122 times



The structure is first a definition/index array of files and an offset of the same file, in this case the file is like a hash of words or actions to take like an script language:  "GameZReadZBDFile: %MissionZBDFile%"

But it seems like this is only one type of zbd file, the are other type of zbd files with similar but different structure to pak files like textures or whatever. they seem to be nor compressed nor encrypted.

bye,
## Post #38
- Username: Cosmas47
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 08, 2019 7:18 am
- Post datetime: 2019-04-10T18:08:45+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

Are you kidding?!?! That's awesome, I'll give that a try this week. With any luck I can export all the game contents. Not that it helps you any but it'll put us closer to a potential port.  Thanks so much for checking that out, I really appreciate it.
## Post #39
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2019-04-11T08:09:49+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

Sadly ZBD files are very different between them.

interop.zbd it´s easy as you see.

*textures*.zbd are also easy and the only problem it´s each texture format, most of them are 16bits images (R5G6B5). i´ll post the formatter but it´s very similar of the interop.

games.zbd and cam_anim.zbd are variants of interop, scripts and the likes. But i think this files need to have some meshes for terrain...

planes.zbd it´s my nemesis right now. it should have some structure of a mesh ( vertices,indices/tris and uvs or the like), but the only thing i see on that file it´s floats everywhere.

Mechwarrior 3 has the same files, but sadly no one has uploaded info about them on the internet.
[knight1.png](https://xentaxbackup.github.io/file/16017_knight1.png)
## Post #40
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2019-08-14T22:07:33+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

Sorry to bump an oldish thread, but I've been working with this script and the like and managed to get the 3d models into blender and extract everything, but something strange is the TGA texture files the QUICK BMS script are corrupted, they can't be opened or converted in any program, did I do something wrong along the lines? I haven't seen the problem before.
I'm working on a Crimson skies mod for Atlas, and I would really appreciate some assistance with this.
## Post #41
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2019-08-16T06:51:56+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

With what textures are you getting errors?

I think most of them are "easy" DXT5/DXT3 or "xbox swizzled", but i think some flare textures had some errors with those importers.
## Post #42
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2019-08-16T15:14:43+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

Oh hey there, I wasn't expecting a reply, I'm actually getting errors with every texture, not just the flares, no program can open them, they aren't TGA I think, is there a special way I need to convert them? I'm excited to try and mod these planes into atlas to create a crimson skies conversion using their base aircraft programming and zepplin. if you still have them, it might be a lot to ask but do you think you could send me the models you managed to extract? mainly the plans and zeppelins.
## Post #43
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2019-08-17T01:26:13+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

> Reply from Xr79 ↑Fri Aug 16, 2019 11:14 pm at Fri Aug 16, 2019 11:14 pm
>
> 
Oh hey there, I wasn't expecting a reply, I'm actually getting errors with every texture, not just the flares, no program can open them, they aren't TGA I think, is there a special way I need to convert them? I'm excited to try and mod these planes into atlas to create a crimson skies conversion using their base aircraft programming and zepplin. if you still have them, it might be a lot to ask but do you think you could send me the models you managed to extract? mainly the plans and zeppelins.

First thing, you are talking about Crimsom skies for PC or Crimsom skies High Road to Revenge XBOX?

If it´s the Xbox Crimson Skies, the QUICKBMS file on the first post should extract most of the textures.

If it´s the PC Crimson, the textures are 16bits images (R5G6B5), i don´t think there is some script to extract them.

I haven´t extracted the models/textures because i´ve only made an importer of the models to Unity, i really don´t know what´s a good Model format to extract a full model with the correct texture settings.

I think in one the post of this thread i posted a link for the a zepellin model and the final boss of the game.
## Post #44
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2019-08-17T03:28:49+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

Hm, its the x box crimson skies and I did use the quick BMS script, darn I wonder why it didn't work. it did extract the textures but they are all completely unreadable. 
I'm sorry I thought I saw you posed a picture of all the planes in unity, unity can save as any number of files types including OBJ that would be perfect, or if you sent me the unity file I could export them  myself from that. 
thank you for trying to help me.
## Post #45
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2019-08-19T06:52:42+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (

i forgot that the quickbms script only extracted the packed files.

The textures are DXT5/DXT3 and xbox swizzled (that´s why you can´t open them as they are), i´ve attached a noesis script plugin that opens them so you can export them to the format you need.
[tex_CrimsonSkies_Xbox_tga.zip](https://xentaxbackup.github.io/file/16627_tex_CrimsonSkies_Xbox_tga.zip)
## Post #46
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2019-08-19T09:31:45+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

Oh thank you so so much that's very kind of you! I searched everywhere with no luck.
## Post #47
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2019-08-19T09:56:32+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

I got it to work finally, I noticed the UV maps are pretty screwed on most of them, I can manually fix them but I thought I read about a fix for the UV map? maybe I'm wrong. I can do it by hand but it's a little tough. 
it looks like the UV map is to small and some of the sub mesh UV maps are misplaced?
## Post #48
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2019-08-19T10:31:28+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

> Reply from Xr79 ↑Mon Aug 19, 2019 5:56 pm at Mon Aug 19, 2019 5:56 pm
>
> 
I got it to work finally, I noticed the UV maps are pretty screwed on most of them, I can manually fix them but I thought I read about a fix for the UV map? maybe I'm wrong. I can do it by hand but it's a little tough. 
it looks like the UV map is to small and some of the sub mesh UV maps are misplaced?

In this post the user shakotay2 made some changes on the plugin to scale the uv1 map [viewtopic.php?f=16&t=17118&sid=f8882f6d ... 10#p144464](https://forum.xentax.com/viewtopic.php?f=16&t=17118&sid=f8882f6da493e2a591889b0200053510#p144464)

I haven´t tested myself, this plugin was my first adventure with python so i´m out my environment.

Actually this post was about me asking for help to try to solve my UVs issues
## Post #49
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2019-11-19T11:44:23+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

> Reply from IronArthur ↑Mon Aug 19, 2019 6:31 pm at Mon Aug 19, 2019 6:31 pm
>
> 
Xr79 wrote: ↑Mon Aug 19, 2019 5:56 pm
I got it to work finally, I noticed the UV maps are pretty screwed on most of them, I can manually fix them but I thought I read about a fix for the UV map? maybe I'm wrong. I can do it by hand but it's a little tough. 
it looks like the UV map is to small and some of the sub mesh UV maps are misplaced?


In this post the user shakotay2 made some changes on the plugin to scale the uv1 map viewtopic.php?f=16&t=17118&sid=f8882f6d ... 10#p144464

I haven´t tested myself, this plugin was my first adventure with python so i´m out my environment.

Actually this post was about me asking for help to try to solve my UVs issues
Few months on and I'm still actually having problems myself. Do you happen to have Discord so I can talk to you on there? Don't tend to check around here.
## Post #50
- Username: DesertPlah
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 24, 2019 2:03 pm
- Post datetime: 2019-12-24T06:10:31+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

Hi!

I'm resurrecting this topic because I'm a big fan of CS, and also own a 3d printer.  Can you guess what I'm going to all next?

Can anyone share some of the work they've done so far re: models?
## Post #51
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2019-12-26T08:18:40+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

I don´t know if someone has extracted all the models and store them. 

I haven´t done it.

You could try to export them with the noesis plugin. Shouldn´t be difficult as you don´t need UVs at all.
## Post #52
- Username: Kerberos
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 27, 2019 11:54 am
- Post datetime: 2020-01-19T18:04:39+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

Does anyone have the models from Crimson Skies here?
And or the scrips that were used to extract them?

Hit me up if you do.
## Post #53
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2020-01-21T12:23:48+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

The scripts are in this thread.

Sorry i don´t extract and store the models
## Post #54
- Username: Unknownskymaster
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 08, 2019 5:22 am
- Post datetime: 2020-10-05T22:36:04+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

is there any chance i can get a folder of all aircraft texture wraps as png or just plain images
## Post #55
- Username: Trekeyus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 30, 2020 1:15 am
- Post datetime: 2020-12-29T17:36:24+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

Thanks for the obj version of the Devastator I had been looking all over the internet for one for 3d printing. Looks like it will need a bit of clean up work but Atleast it's a starting point.
## Post #56
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2021-01-04T08:21:15+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

If you print it, post a picture!
## Post #57
- Username: Trekeyus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 30, 2020 1:15 am
- Post datetime: 2021-01-12T20:31:34+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

Will do. Gona need a lot more clean up then I thought. But should still be doable. Been trying to figure out how to design the Contra rotating prop in a way that it would actually work and spin by a tiny electronic motor. thinking about designing it in such a way that the devastator is one of those ceiling planes on a string that spins around in a circle and has the propeller pushing it.
## Post #58
- Username: muahbarbossa
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 07, 2021 7:30 pm
- Post datetime: 2021-07-07T11:55:54+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

Hi all is there anyway to get a DAE. File fr Second Life?
## Post #59
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2021-07-21T11:23:07+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

Massive update!
I now got access to the .pdb files of CS, dated 2 months prior to release. This should make it far more easy to reverse engineer the model formats, so I hope that some work here will be done.

Whoever manages to get the plugins improved through this; I'll love you forever.
[MEGA link due to filesize limit](https://mega.nz/file/W8tWmBRB#Wts4njE_vO0enNuSOlpq-kqdLLn3wzaWSXKNmgrxJsk)
## Post #60
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2021-07-21T11:47:08+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

I not going to ask how you got access to those files... (any mechassault ones?¿)

Unfortunately i don´t have any knowledge using a pdb file to debug a Xbox Classic game so...
## Post #61
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2021-07-21T11:50:07+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

Just found them on Twitter. Hope someone puts them to good use to get these formats better!
## Post #62
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2021-07-23T02:47:22+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

Bump, read end of Page 4 for .pdb files which most likely give info on how to better reverse engineer the CS:HRTR .x models
## Post #63
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2021-07-23T07:09:09+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

> Reply from Mrblue630 ↑Fri Jul 23, 2021 10:47 am at Fri Jul 23, 2021 10:47 am
>
> 
Bump, read end of Page 4 for .pdb files which most likely give info on how to better reverse engineer the CS:HRTR .x models

What software do you use to read the pdb content?
## Post #64
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2021-07-23T14:26:59+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

Any text editor program seems to work, shows symbols and function names. I think you're meant to attach it to the executable for CS HRTR to use for debugging, though I'd have no idea how
## Post #65
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2021-07-23T16:38:23+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

Ok. 

I've been trying to extract structures with some pdb dumpers with no luck so far, that's why I was asking. 

I'll look into it if there is something interesting.
## Post #66
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-23T17:10:59+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

Afaik .pdb is the symbol table, you load the exe into a debugger (windbg, IDA, OllyDbg) then usually the symbol table is loaded and you can see data types, set break points, etc.
Here are the symbols of a 3D tools of mine in x32dbg (successor of OllyDbg?) :
.



pdb-symbols.png (75.57 KiB) Viewed 106 times
## Post #67
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2021-07-23T22:38:57+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

I get how you do it with an exe file, but what file you open on a debugger (ida or ghidra) of an xbox1 game?
## Post #68
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2021-07-24T11:52:49+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

> Reply from shakotay2 ↑Sat Jul 24, 2021 1:10 am at Sat Jul 24, 2021 1:10 am
>
> 
Afaik .pdb is the symbol table, you load the exe into a debugger (windbg, IDA, OllyDbg) then usually the symbol table is loaded and you can see data types, set break points, etc.
Here are the symbols of a 3D tools of mine in x32dbg (successor of OllyDbg?) :
.
pdb-symbols.png

Would this be useful for refining existing model plugins/converters for CS?
## Post #69
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-24T13:49:59+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

> Reply from IronArthur ↑Sat Jul 24, 2021 6:38 am at Sat Jul 24, 2021 6:38 am
>
> , but what file you open on a debugger (ida or ghidra) of an xbox1 game?well, I guess you'll need the XBox360 SDK?

------------------------------

> Reply from Mrblue630 ↑Sat Jul 24, 2021 7:52 pm at Sat Jul 24, 2021 7:52 pm
>
> Would this be useful for refining existing model plugins/converters for CS?Usually we don't have access to the .pdb files of those plugins/converters. You'll need the source code, if any (from github or other repos).
## Post #70
- Username: Mrblue630
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 01, 2018 1:15 pm
- Post datetime: 2021-07-25T11:09:16+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

I've got the CS HRTR xbe, which is what it's meant for. plus noesis plugin for model importers, so could that be used to refine said plugin?
## Post #71
- Username: DeeAreEss
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 29, 2021 1:56 am
- Post datetime: 2021-07-30T06:39:56+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

> Reply from DesertPlah ↑Tue Dec 24, 2019 2:10 pm at Tue Dec 24, 2019 2:10 pm
>
> 
Hi!

I'm resurrecting this topic because I'm a big fan of CS, and also own a 3d printer.  Can you guess what I'm going to all next?

Can anyone share some of the work they've done so far re: models?

Same here (well, 3d printing and using them in Tabletop Simulator...)

Being a sucker for dirigibles in general, the zeppelins in CS:HRTR are what I'm particularly interested in.  I've looked through the thread and tried to replicate the steps to get the various .x and .tga files from the various scene files like what IronArthur did with Chicago.  Each zeppelin's .x file contains the data for the main envelop, rudder fins, and gondola; there's a stock selection of engines and gun turrets in separate .x files that are then added on as needed.  From what I can gather instructions for assembling all the pieces correctly are kept in the corresponding .db files located in the data folder.  I've started going through them in my hex editor, but if anyone already knows the .db file specification that would greatly help.

Of course if anyone's already gotten all the zeps extracted and assembled, please let me know before I needlessly reinvent any wheels.  Cheers!
## Post #72
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2021-07-30T11:04:20+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

The same as the last time someone asked if i have a dump of all the models no i don´t have any backup or something like that.

I´m digging through my all code that extracted the CS game files (4 years ago at least), and i think the structure of a map bin file is "easy", it´s a package of items:

typedef struct{
    int TypeOfItem; //1 Object 2 Texture 4 Animation 5 Cinematics 6 Audio
    int FilenameLength;
    BYTE Filename[FilenameLength];
    int size;
    byte dataofitem[size];
} entry;

For the items itself you only need the .x files ( type 1) and textures (type 2). The type 1 file already have the position/rotation matrix defined on the file.

So to extract all the zeppelin's models you need to find a map that has the zeppelin with the correct attachments and the extract that part of the bin file.

I may try at some point to upgrade the noesis plugins to include the map bin files, but i don't know how it will behave with that many submodels. My current reader it's made with Unity.
## Post #73
- Username: DeeAreEss
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 29, 2021 1:56 am
- Post datetime: 2021-07-31T00:43:10+00:00
- Post Title: Re: (Xbox) Crimson Skies High Road to Revenge plane models (.x)

> Reply from IronArthur ↑Fri Jul 30, 2021 7:04 pm at Fri Jul 30, 2021 7:04 pm
>
> 
I´m digging through my all code that extracted the CS game files (4 years ago at least), and i think the structure of a map bin file is "easy", it´s a package of items:

> Reply from IronArthur ↑Fri Jul 30, 2021 7:04 pm at Fri Jul 30, 2021 7:04 pm
>
> 
For the items itself you only need the .x files ( type 1) and textures (type 2). The type 1 file already have the position/rotation matrix defined on the file.

So to extract all the zeppelin's models you need to find a map that has the zeppelin with the correct attachments and the extract that part of the bin file.

Just to make sure I'm understanding you correctly: Are you saying that the zeppelin .x file would have the position/rotation matrices for all its attachments, or that the .bin file is handling creating all the instances of these component models then setting each one's position/rotation values relative to the zeppelin to which it's attached?
