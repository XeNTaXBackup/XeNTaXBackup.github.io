## Post #1
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-03-05T15:51:23+00:00
- Post Title: Buffer problem

I started making exporter with this importer scripr for noesis but no have luck 
If export have buffer problem how to fix this and wich need to buffer?
The buffer error Says triying to export without buffer but what mean buffer?
[fmt_fmlb.zip](https://xentaxbackup.github.io/file/23491_fmt_fmlb.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-05T17:19:21+00:00
- Post Title: Buffer problem

1) The script you've uploaded is an fmlb import script (who is the author?)
(It uses NoeMesh() in some basic/raw way, I guess.)

```
mesh = NoeMesh(indices, vert, name, "mat_0")
```


2) I don't see code lines for exporting.

(Noesis,File/Export allows to export to different formats, fbx, obj, etc. But not to fmlb.)

3) btw, buffers are used to collect vertices, uvs or face indices, for example.
Using the  rapi.rpg interface is recommended, afaik.
Example:

```
		VBuff = bs.readBytes(VCount*FVFsize)
		rapi.rpgBindPositionBufferOfs(VBuff, noesis.RPGEODATA_FLOAT, FVFsize, 0)
```


Also see inc_noesis.py
"#it's recommended that you use the rapi.rpg interface if you want a convenient means to convert different data/primitive types into a NoeModel with NoeMeshes."
## Post #3
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-03-05T19:34:23+00:00
- Post Title: Buffer problem

the script is by Durik256
and the exporter tried to make is the fmt_fmlb.py on this reply
and screnshot of buffer problem
[Captura de pantalla 2023-03-05 202254.png](https://xentaxbackup.github.io/file/23495_Captura de pantalla 2023-03-05 202254.png)
## Post #4
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-03-05T19:35:08+00:00
- Post Title: Buffer problem

new script
[fmt_fmlb.zip](https://xentaxbackup.github.io/file/23496_fmt_fmlb.zip)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-05T20:29:05+00:00
- Post Title: Buffer problem

def searchString(bs): and class SubMesh: are contained twice.

Is that the original script?

Did you add/change or delete lines?
## Post #6
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-03-05T20:43:25+00:00
- Post Title: Buffer problem

I am copied handler load and changed to write
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-05T20:56:29+00:00
- Post Title: Buffer problem

So def noepyWriteModel(data, mdlList) was written by you? Or by Durik?

Made some "progress":

---------------------------
Noesis Python Error
---------------------------
Traceback (most recent call last):
  File "D:\noesisv4466\plugins\python\fmt_fmlb (2).py", line 148, in noepyWriteModel
    mdlList.append(NoeModel([mesh]))
AttributeError: 'NoeBitStream' object has no attribute 'append'
## Post #8
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-03-05T21:00:06+00:00
- Post Title: Buffer problem

Yes i writed and thanks yes i am learning and viewed of other exporters wich diference of import and export
Ok y try to atribute append and the submeshes and others is not necesary for export ?
## Post #9
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-03-05T21:05:57+00:00
- Post Title: Buffer problem

Oooo i opened again and says append not defined i try to define
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-05T21:20:57+00:00
- Post Title: Buffer problem

> Reply from Dani ↑Mon Mar 06, 2023 5:00 am at Mon Mar 06, 2023 5:00 am
>
> 
Yes i writed and thanks yes i am learning and viewed of other exporters wich diference of import and exportI never knew that there's Noesis exporters with source.
Can you please give the link to one of them?
.

> Ok y try to atribute append and the submeshes and others is not necesary for export ?I never used a self written exporter in Noesis, so no, I have no idea...

For some reason mdlList.append(mdl) is not accepted/causes an error on export.
Without that line: no error, but no fmlb, too:
.



no_error_no_fmlb.png (20.07 KiB) Viewed 157 times

I reduced the count of objects to 37, thus cutting the process after the first two sub meshes.
## Post #11
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-03-05T21:22:40+00:00
- Post Title: Buffer problem

> Reply from shakotay2 ↑Mon Mar 06, 2023 5:20 am at Mon Mar 06, 2023 5:20 am
>
> 
export

he just duplicated the import method(by changing the method name) and thinks it will export 

*(and created a new topic again)
## Post #12
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-03-05T21:26:11+00:00
- Post Title: Buffer problem

Yes but i think fail bacouse i dont Know whta need wirte to fix and export
## Post #13
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-03-05T21:42:54+00:00
- Post Title: Buffer problem

I have idea i try to write only exporter and without that line
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-05T22:19:37+00:00
- Post Title: Buffer problem

> Reply from Dani ↑Mon Mar 06, 2023 5:42 am at Mon Mar 06, 2023 5:42 am
>
> 
I have idea i try to write only exporter and without that lineWell, have you ever written an importer for Noesis? Exporters tend to be much harder to be written.
Also you wouldn't start with a 2 MB fmlb file. That's doomed to failure.  

Even the CarrotRunner is much too big. Believe it or not.

So where to start? A book, a shelf or a box. And you'll need a full format description.
And when I write "full" then I mean full. You need to know the meaning of every byte in a .fmlb file.
A static button might be a good start: IconBoostButton!.fmlb
.



IconBoostButton.png (17.19 KiB) Viewed 89 times



> Reply from proposals-faded-in-the-wind
>
> You need to realize that an obj_to_some3DFormat converter is very time consuming to create. It's not that simple as you might think of.

Converting some3DFormat to obj usually takes 15 minutes (first submesh only) for simple formats.
That's probably the reason why some guys believe the vice versa way is similar. But it is not.

You may read here to better understand, why:[viewtopic.php?f=16&t=13184&hilit=vkm](https://forum.xentax.com/viewtopic.php?f=16&t=13184&hilit=vkm)

Above quote is from here:

> Reply from shakotay2 ↑Wed Feb 12, 2020 5:34 pm at Wed Feb 12, 2020 5:34 pm
>
> 

>>> Using Durik's fmlb import script you get the basic structure of IconBoostButton fmlb:

```
count: 47 offset: 4192 unk: 27264
type 102 hi_HUD_IconBoostButton 4192
type 103 tex_Glow 11328
type 103 tex_Icon_Flame 11536
type 103 tex_boost_button 11744
type 103 tex_default 11952
type 103 tex_defaultnm 12160
type 103 tex_diffusewarp 12368
type 103 tex_icon_cowboy 12576
type 103 tex_icon_jump@2x 12784
type 103 tex_icon_laser 12992
type 104 mat_Glow 13200
type 104 mat_IconBoostBUtton 13536
type 104 mat_icon_cowboy 13872
type 104 mat_icon_flame 14208
type 104 mat_icon_laser 14544
type 104 mat_iconjump 14880
type 107 geo_sh_blastericon 15216
type 107 geo_sh_booticon 15504
type 107 geo_sh_buttonOff 15792
type 107 geo_sh_buttonOn 16080
type 107 geo_sh_button_guage 16368
type 107 geo_sh_buttonoutline 19440
type 107 geo_sh_cowboyhaticon 19728
type 107 geo_sh_flameicon 20016
type 107 geo_sh_glow 20304
type 108 prim_sh_blastericon 20592
type 108 prim_sh_booticon 21456
type 108 prim_sh_buttonOff 22320
type 108 prim_sh_buttonOn 23184
type 108 prim_sh_button_guage 24048
type 108 prim_sh_buttonoutline 24912
type 108 prim_sh_cowboyhaticon 25776
type 108 prim_sh_flameicon 26640
type 108 prim_sh_glow 27504
type 113 Clip_Button_Active 28368
type 113 Clip_Button_Charge 29632
type 113 Clip_Button_Inactive 30160
type 114 anim_hi_HUD_IconBoostButton 30576
type 123 c_IconBoostButton0 30736
type 123 c_IconBoostButton1 30816
type 123 c_IconBoostButton2 30896
type 123 c_IconBoostButton3 30976
type 123 c_IconBoostButton4 31056
type 123 c_IconBoostButton5 31136
type 123 c_IconBoostButton6 31216
type 123 c_IconBoostButton7 31296
type 123 c_IconBoostButton8 31376
15216
geo_sh_blastericon iCount 6 vCount 4 1 24424
15504
geo_sh_booticon iCount 6 vCount 4 1 0
15792
geo_sh_buttonOff iCount 6 vCount 4 1 24424
16080
geo_sh_buttonOn iCount 6 vCount 4 1 4441
16368
geo_sh_button_guage iCount 384 vCount 130 1 24424
19440
geo_sh_buttonoutline iCount 6 vCount 4 1 0
19728
geo_sh_cowboyhaticon iCount 6 vCount 4 1 12336
20016
geo_sh_flameicon iCount 6 vCount 4 1 0
20304
geo_sh_glow iCount 6 vCount 4 1 352
20576
```
If geo_sh_xxx means sub mesh then we have 9 of them here.
## Post #15
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-03-05T23:39:22+00:00
- Post Title: Buffer problem

Ok i undestrad export is much difficult of import 
I think my problem is Know wich code use for any byte of fmlb but idk wich need to use i want to you make exporter but i don't want to you angry with me thats is the reason i want to make myself i don't want to tell you write me a exporter for fmlb i watched you writed a exporter of other topic of vkm for other person but i don't want to get you time for my wants thats is the end i ended with fmlb bye bye fmlb exporter 😭
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-06T05:49:47+00:00
- Post Title: Re: Buffer problem

> Reply from Dani ↑Mon Mar 06, 2023 7:39 am at Mon Mar 06, 2023 7:39 am
>
> ... thats is the end i ended with fmlb bye bye fmlb exporterWell, I only wanted to tell what works, imho, and what does not, probably.
If I were you I'd try to gain some basic knowledge for example by replacing Bugs Bunnys head by Daffys. Something like that.

It's a matter of copying vertices and face indices and their counts (assumed Bugs head having more verts than Daffys- Otherwise Daffys head to be replaced by Bunnys)
