## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-02-19T11:30:58+00:00
- Post Title: Onechancara Models: Can Someone Make Vertex Dumper

can someone please code a simple float parser to output as obj?

A point or vertex dumper would be helpful, that way I can remodel them using the points as reference

/thx'n adv

File Sample:
[http://www.mediafire.com/file/zzzk2yomm ... ostume.zip](http://www.mediafire.com/file/zzzk2yomm5d/Aya%27s%20Lagacy%20Costume.zip)
## Post #2
- Username: LagDotCom
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Feb 19, 2009 5:06 am
- Post datetime: 2009-02-19T12:08:07+00:00
- Post Title: Onechancara Models: Can Someone Make Vertex Dumper

Doesn't that say 'oneechanbara'? Anyway.

[Here are](http://lag.thps3.net/temp/aya.can.txt) some quick notes. No, nothing like an extractor yet.
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-02-20T03:19:17+00:00
- Post Title: Onechancara Models: Can Someone Make Vertex Dumper

yeah CAN is a container that the game uses, and it is oneechanbara (little sister) ..but the northamerica release, the cover says onechanbara. ? donno why.

thanks for looking at the format a bit, least we have a general area of where the vertex data may be ^_^
## Post #4
- Username: LagDotCom
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Feb 19, 2009 5:06 am
- Post datetime: 2009-02-21T00:01:34+00:00
- Post Title: Onechancara Models: Can Someone Make Vertex Dumper

Turns out I'm actually a moron, who'd have thought? There's more than 2 files in that archive, dunno how I missed them the first time. The actual TGF file format doesn't seem too obscure. Working on it.
## Post #5
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2009-02-22T08:57:35+00:00
- Post Title: Onechancara Models: Can Someone Make Vertex Dumper

i found this the wii model version here (click on filefront link on this page)

[http://darkmatter2.de-coder.net/index.p ... #entry1080](http://darkmatter2.de-coder.net/index.php?s=c422c1154d8615e7ddfd6542b98562dc&showtopic=77&st=0&p=1080&#entry1080)

also i attached a float2txt converter just make a bat file with:

float2txt AyasLagacyCostume.can AyasLagacyCostume.txt 3
pause
[float2txt.rar](https://xentaxbackup.github.io/file/1888_float2txt.rar)
## Post #6
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-02-22T09:21:21+00:00
- Post Title: Onechancara Models: Can Someone Make Vertex Dumper

that's nice, but I was looking for something that I could import into 3DMax.

the txt I can't do much with. could you program OBJ output? ..actually I think OBJ just requires me to write a V statement before the x,y,z .. I might be able to use this.

also you linked to my own forum, and my own topic. I have ripped the Wii Models, but 360 has 3 models Wii doesn't have. Anna, the old chick, and the old version of reiko.

anyway thanks a ton for the float2txt, I hope to use this to rebuild the models. (wish me luck) ^_^

EDIT:
looks like my idea was a lost cause. 3dmax doesn't allow me to import vertices only through OBJ format. ironically it works in milkshape, but still with whatever format 3dmax doesn't allow for vertex only import. 


poop
## Post #7
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2009-02-22T14:14:24+00:00
- Post Title: Onechancara Models: Can Someone Make Vertex Dumper

You don't need all float because this tool convert all data of the file.
You need to found where is the vertex data into the file but i suppose the file contain other data like .dds .tga
I made some stuff on worms 4 mayhem with some héxadécimal tricks (dany25 i have multi pseudo).
[http://ffab.mypage.sk/viewtopic.php?t=51](http://ffab.mypage.sk/viewtopic.php?t=51)
## Post #8
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-02-22T16:21:28+00:00
- Post Title: Onechancara Models: Can Someone Make Vertex Dumper

nah, there's something fishy is going on. I did isolate the area where the floats where. but theres obviously something wrong. maybe the verts are stored a bit differently
## Post #9
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2009-05-01T02:04:38+00:00
- Post Title: Onechancara Models: Can Someone Make Vertex Dumper

"3F80" would be 1.0f. it looks like the file has 16bit floats but I don't have a program to read this type of float. it could be that or a picture but to be honest it does looks like it is using 16bit float(instead of 32 bits). may I ask where are the float you isolated?

Edit: my japanese is by no means perfect but from what I could tell its onee-chan. a familiar way to address ones elder sister. or in a colloquial way a young woman. the japanese cover has "bara" written in kana so I guess it is refers to be the sound of swords hitting each other. I have no idea how I would put that in english
## Post #10
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-05-03T15:29:10+00:00
- Post Title: Onechancara Models: Can Someone Make Vertex Dumper

I have a float2txt converter here , what is your idea about it ?
[viewtopic.php?f=21&t=3460&p=29131#p29131](http://forum.xentax.com/viewtopic.php?f=21&t=3460&p=29131#p29131)
## Post #11
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2009-05-08T03:09:51+00:00
- Post Title: Onechancara Models: Can Someone Make Vertex Dumper

Mario said he isolated the data that had the model vertices. I don't know where this is but the floats I DID find where in a non standard 16bit format.

The float2txt program converts standard 32bit floats but this file seems to have 16bit floats.

I would like to know where in the file is the data mario speaks of, in order to see if I can convert the floats into standard 32bit floats. If it works then I could code a obj exporter for this file and others. also if the face index data is not found or is not there then I could link up the vertices randomly so it can be imported into 3dsmax.
## Post #12
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-03-16T01:38:41+00:00
- Post Title: Onechancara Models: Can Someone Make Vertex Dumper

> Reply from alera
>
> Mario said he isolated the data that had the model vertices. I don't know where this is but the floats I DID find where in a non standard 16bit format.

The float2txt program converts standard 32bit floats but this file seems to have 16bit floats.

I would like to know where in the file is the data mario speaks of, in order to see if I can convert the floats into standard 32bit floats. If it works then I could code a obj exporter for this file and others. also if the face index data is not found or is not there then I could link up the vertices randomly so it can be imported into 3dsmax.

SOS!  

is the 3d models extracted from [Onechancara] game?

how to extract models ???
## Post #13
- Username: kekko
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Nov 01, 2008 9:26 pm
- Post datetime: 2010-04-06T12:49:34+00:00
- Post Title: Onechancara Models: Can Someone Make Vertex Dumper

I had a quick look at this; it should be an easy format to decode, and the girl must be pretty 
data is big-endian, vertices are standard [IEEE 754 half-float](http://en.wikipedia.org/wiki/Half_precision_floating-point_format)  here's the [(conversion routine)](http://pastebin.com/tKjajPfM)
[](http://i42.tinypic.com/6ypflf.png)

the CAN file is a container, which contains other CAN archive files and/or data files
every archive or data file is preceded by an header
in the file above, the first 0x80 bytes are three headers: 0x30 + 0x30 + 0x20 bytes; the file contains 2 archives, the first archive contains two more files, the first of them is a TGF.

```
// size does not include headers
// offsets are relative to current file/archive start


int header_size;

int file_size;
int file_name_offset;
int next_file_offset;

int file_size;
int file_name_offset;
int next_file_offset;
...

if next_archive_offset = 0xFFFFFFFF -> end of list

if header_size > 0x20 -> archive
if header_size = 0x20 -> file


```


here's the structure of TGF files

```
// TGF /////////////////////////////////////////

--header (32 bytes)
char magic[4];             // 'TGF '
int  number_of_mesh_entries;
int  mesh_list_offset;
int  texture_index_offset;
int  an_offset_right_after_texture_names;
int  size_of_something;
int  another_offset;
int  end_of_file;

--mesh list (number_of_entries * 12)
int unknown1;
int offset_to_mesh_data;
int unknown2;

-- mesh data
--- header (variable size)
TO DO. there is the number of vertices, the vertex data size and the number of triangles
---vertex data (vertex_data_size * number_of_vertices)
---triangle data (unsigned short list)

```
## Post #14
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2010-04-06T15:13:09+00:00
- Post Title: Onechancara Models: Can Someone Make Vertex Dumper

Well, doesn't really matter.

This is not Onechancara. correctly it can read Onechanbara (exactly chan and zzang middle pronunciation)

"O-ne''s meaning is elder sister
"chan" is a  lovely title with a close people
## Post #15
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-04-10T14:21:04+00:00
- Post Title: Onechancara Models: Can Someone Make Vertex Dumper

Hi, mind if I join in?
I've been working on the Oneechanbara files for some time now and still couldn't get past the deformation issue yet (pic below). But where there's life there's hope (or the other way around ??) so I'll continue digging.
Texture coords look correct though I don't have the texture data to check things, if someone could post them here then it would be nice.
I'll update you with the progress.
[oneechan.JPG](https://xentaxbackup.github.io/file/2918_oneechan.JPG)
## Post #16
- Username: kekko
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Nov 01, 2008 9:26 pm
- Post datetime: 2010-04-10T16:34:52+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

Hi Surveyor,
if you shift vertex start by (vertex_data_size-36)/3, you'll get the meshes in world coordinates:
[](http://i39.tinypic.com/ndx2ea.png)

deformed meshes depend by some vertices with one or two coordinates with apparently wrong values. There must be an explanation for this 
[](http://i41.tinypic.com/1217ghy.png)
## Post #17
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-10T18:16:24+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

the coordinates are based on the bones.
## Post #18
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-04-12T20:52:13+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

Hi everyone,
As Chrrox said, vertex positions relate to the bones and in a very bizzare manner, After hours of testing and out of desperation, I found a way to fix all this, by applying the most influesive matrix to each vertex (it turned out to be always the 1st matrix per vertex) vertices miraculously got back to normal, I can't explain why and I don't care (yet another japanese game craziness)
Skinning is under way and you can see in the pic below that it works almost perfectly, there are some issues though (hand nails and cowboy hat aren't influenced - not very visible here) and also I think some parts are missing, the hair for example.
The normals are junky as always (see the difference between the girl's back ?) I can't find any solution for this bug , I think I'll switch to collada since this format supports per vertex normals in max, then there are the bones that will give me headaches in this format, I'll need to study it further, not any soon though 
I want to check texture mapping so is it possible to post the texture files here? (I don't have the game)
[TheOneechan.JPG](https://xentaxbackup.github.io/file/2926_TheOneechan.JPG)
## Post #19
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-04-14T02:19:18+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

The contents of this post was deleted because of possible forum rules violation.
## Post #20
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-04-16T21:59:15+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

Hi,
There's some more progress on the Oneechanbara TGF models, I used collada and this format is very handy, the stupid normal bug isn't there anymore and I think the missing parts are now present, materials are displayed in viewport so you don't have to set them by hand (all the parameters are already set: diffuse, bumpmap and specular textures).
Still more work is still needed to perfection this converter, the material editor doesn't display the materials in use, this is annoying because some materials need an opactity setting (eyelashes and hair for example)
You can also notice some flipped faces here and there that need to be corrected (not by hand otherwise the normals get bugged)
And of course the skinning which is the most important feature of this converter.
I don't plan to post the converter in this state (before skinning) but if you want to test it like this then just let me know.
And as usual, your comments/suggestions are welcome.
[Collada.JPG](https://xentaxbackup.github.io/file/2932_Collada.JPG)
## Post #21
- Username: kekko
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Nov 01, 2008 9:26 pm
- Post datetime: 2010-04-17T08:56:46+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

nice work Surveyor. I'm looking forward to it.
## Post #22
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-04-26T21:38:34+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

Here you go, the oneechanbara model converter, it converts the models into collada, I found this format to be very handy (very hard too) since it handles most of what we need here.
In addtition to typing the filename, you will need to provide a user friendly name to be used in models names, using something like "aya" or "bastard" will help you navigate in max better than having all models named "pl00_00" or "boss_55_05". 
If you have the textures then put them in the "tex" directory right where the model is: if your model is "d:/test/model.dae" then place the textures in "d:/test/model/tex/" it's where 3ds max will look when you load the model.
Some faces are flipped wrongly, correct them by hand using "flip normals mode" then apply a MeshSmooth modifier with 0 iterations, wether you put the modifier before or after the skin modifier just doesn't matter.
Skinning looks perfect and I think there aren't any missed objects.
Enjoy!
[Oneechanbara.zip](https://xentaxbackup.github.io/file/2979_Oneechanbara.zip)
## Post #23
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-06-07T20:20:23+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

> Reply from Surveyor
>
> Here you go, the oneechanbara model converter, it converts the models into collada, I found this format to be very handy (very hard too) since it handles most of what we need here.
In addtition to typing the filename, you will need to provide a user friendly name to be used in models names, using something like "aya" or "bastard" will help you navigate in max better than having all models named "pl00_00" or "boss_55_05". 
If you have the textures then put them in the "tex" directory right where the model is: if your model is "d:/test/model.dae" then place the textures in "d:/test/model/tex/" it's where 3ds max will look when you load the model.
Some faces are flipped wrongly, correct them by hand using "flip normals mode" then apply a MeshSmooth modifier with 0 iterations, wether you put the modifier before or after the skin modifier just doesn't matter.
Skinning looks perfect and I think there aren't any missed objects.
Enjoy!


why is error?

look at:
## Post #24
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-07T21:14:16+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

don't use the autodesk dae importer use the one you download from the people who maintain collada.
## Post #25
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-06-08T08:54:44+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

> Reply from chrrox
>
> don't use the autodesk dae importer use the one you download from the people who maintain collada.
THANK YOU!

Hello everybody,
To download and install COLLADA software,Installing the 3ds Max COLLADA-Plugin

look at:
[http://update.multiverse.net/wiki/index ... _version_9](http://update.multiverse.net/wiki/index.php/Installing_the_3ds_Max_COLLADA_Plugin#3ds_Max_version_9)

Please help 3ds max error "can't open file[*.dae]"

look at:
## Post #26
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-08T11:42:58+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

> Reply from pceengied
>
> 
Please help 3ds max error "can't open file[*.dae]"
use [this collada](http://opencollada.org/download.html)
## Post #27
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-06-08T11:56:28+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

> Reply from Tosyk
>
> pceengied wrote:
Please help 3ds max error "can't open file[*.dae]"
use this collada

thank you
## Post #28
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-06-13T19:58:56+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

anyone upto cracking the TGF format? I want to put models into (DREAM C CLUB).
## Post #29
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-06-13T20:30:53+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

I used the Onechancara tool in the TGF file of Dream C Club game but doesn't works
## Post #30
- Username: luciasil
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Mar 24, 2010 9:48 am
- Post datetime: 2010-07-28T13:19:30+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

hi 

my english is fool
i need help

how to extract "Onechanbara" "Can" contaner file 2 tgf ?

i'm use bms script extraction can file 
but' only dds files how get model tgf files ?

i'm study Dx9 shader tech need some sample model
onechanbara model is very useful
## Post #31
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-08-23T02:40:36+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

The contents of this post was deleted because of possible forum rules violation.
## Post #32
- Username: luciasil
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Mar 24, 2010 9:48 am
- Post datetime: 2010-08-24T05:46:08+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

use Hex editor TGF extract

onechanbara can contaner 

bms script is only dds texture extract

TGF model extact only manualy
## Post #33
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-08-24T07:09:16+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

> Reply from luciasil
>
> use Hex editor TGF extract

onechanbara can contaner 

bms script is only dds texture extract

TGF model extact only manualy

Great, Thanks for the quick answer luciasil, I'm a noob in Hex edit but i will try!!
## Post #34
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-08-25T02:38:23+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

I'm a noobs in hex editor, It's easy find the Start but I don't know how to recognize the End of the TGF block.

Pic of saki HxD

[](http://imagefra.me/)

Please help guys
## Post #35
- Username: charlo020
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 26, 2010 12:50 am
- Post datetime: 2010-11-11T16:40:08+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

Hi to all,

Is there anyone who could upload the oneechanbara model ? I would really like to have it!

Thanks so much!
## Post #36
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2010-11-12T16:15:45+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

Hello all!

How extract models file Aya's Lagacy Costume.can?, I have a onechambara.ex but i dont now what do extract.
## Post #37
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2011-10-21T07:24:28+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

I have an idea (a long time ago) to RELEASE ALL models from Oneechanbara VorteX - I think somebody can convert into XNALara in future for example.
BUT! When I started to convert extracted TGF files into DAE I've got a serious problems: 
First and main - two models of the enemies - Legion and Misery TGF files can't be converted by utility (error with Legion's TGF and bad DAE file with Misery). Here's full pack (TGF+DDS) for this characters: Legion [http://www.megaupload.com/?d=N1K9A051](http://www.megaupload.com/?d=N1K9A051)
Misery [http://www.megaupload.com/?d=AS5CGUXV](http://www.megaupload.com/?d=AS5CGUXV)
If anybody can help me and convert this TGF files into correct DAE, PLEASE DO IT!
the second problem is not so serious, but I don't know how to fix it: almost all models have some bugs with normals (converted model looks fine into preview windows of MAX, but rendered image have a lot of inverted normals, which can't be fixed by simple flipping), but I can't fix it with usual methods in 3DS MAX. So if anyboby knows how to fix this problem or/and can help me correct it - I can upload all of my models (inc. all DLC models!) and place the link here.
## Post #38
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-10-21T20:46:57+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

this the compiled EXE your using or the maxscript?

I also wrote a script for 3dsmax for xnalara... are you sure the normals are bad?
## Post #39
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2011-10-21T22:13:40+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

I'm using compiled EXE.
About normals I wrote in [http://darkmatter2.gamersjudgement.com](http://darkmatter2.gamersjudgement.com) before closing with pictures: some characters like Aya or Saki are the most OK, but some like Annna is very very bad looking
Here's example:
Model in preview window: 
And this model rendered: 
Mariokart64n, you wrote a script for 3DS MAX for TGF import, as I understand?!
## Post #40
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-10-24T04:17:41+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

the maxscript was from fatduck, but since he sells them I can't post it.

also that model looks like it has bad face direction, not bad normals. 3dsmax isn't really capable of storing normals.. there always recalculated
## Post #41
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-10-24T07:50:33+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

Mario, where its the store of fatduck, have you link?
## Post #42
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-10-25T03:57:12+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

I lost the URL to his site, but last I heard his computer exploded into a trillion pieces.. so I donno if he's still even around?
## Post #43
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2011-10-28T11:46:48+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

> Reply from mariokart64n
>
> the maxscript was from fatduck, but since he sells them I can't post it.
Well, Mariokart64n, if he sells them and you can't post them, can you PLEASE just convert this two characters that I've uploaded (Misery and Legion) and upload the result MAX or another format files here?!

P.S: And tell me please which program except 3DS MAX I can use to get models without surface/normals glitches?
## Post #44
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-10-29T07:58:41+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

Well if its true the fatduck machine go to the hell, and he cant sell more the script and he also are not interested in made one more time the script, i think he dont have trobules with you shared the script.

But this its only a suposition, maybe fatduck can give bether answer for this question.
## Post #45
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2013-03-02T19:22:14+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

Now, when much time has passed I repeat my request - may anyone help me with 3DS MAX TGF script?
## Post #46
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2013-03-03T02:08:58+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

I want to document this format so I can mod the game... so eventually I'll be creating my own max-script and disclosing the structures for purposes of modding the game.
## Post #47
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2013-03-04T08:20:56+00:00
- Post Title: Re: Onechancara Models: Can Someone Make Vertex Dumper

Good news - I'm so hope that it will happen soon
