## Post #1
- Username: josejl1987
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 28, 2011 3:52 am
- Post datetime: 2016-08-11T12:59:50+00:00
- Post Title: IT3 files from Ys Memories of Celceta

Hello everyone.

I'm making a mod for the PC version of Ys Celceta, and it turns out I need to edit the vertex normals for solving some lighting issues.

There's the IT3 converter ([http://www.pokanchan.jp/dokuwiki/_media ... 3cnv03.zip](http://www.pokanchan.jp/dokuwiki/_media/software/it3cnv03.zip)), that outputs to OBJ/Mtl , but there is no source code for that, besides that it doesn't output all the data. Of course, I am interested in the actual format specification, in order to make edits possible.
I know that the game's renderer uses the following vertex data structure for all 3D models, no matter if they're static or skinned.

Float4 Position;
Float4 Normal;
Float4 texCoords ; 
Float4 diffuseColor;
Float4 specularColor;
Float4 boneWeight;
Float4 boneIndex;

Presumably,the IT3 format is based on RIFF, there are quite a few different sections (the game accounts for 45), but the vertex data seems to be in the VPA8 section.I have tried to reverse the loading code, but it's really convoluted,and I don't quite understand the data.It seems to be packed in some way.

Does anyone know how to tackle this one? I can give more details if needed.

Thanks.
[tes2202.rar](https://xentaxbackup.github.io/file/11545_tes2202.rar)
## Post #2
- Username: delguoqing
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 12, 2014 9:55 am
- Post datetime: 2016-08-27T17:06:20+00:00
- Post Title: IT3 files from Ys Memories of Celceta

hi, do you have any progress by now?
If not, I might be willing to look at this. I'm myself a big fan of ys series.
By the way, what is RIFF? And can I ask what kind of mod are you trying to make? Just curious.
## Post #3
- Username: josejl1987
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 28, 2011 3:52 am
- Post datetime: 2016-09-01T18:22:53+00:00
- Post Title: IT3 files from Ys Memories of Celceta

Yeah, actually I have, but it's far from done. 

[http://www.heroesoflegend.org/forums/vi ... 2455#p2455](http://www.heroesoflegend.org/forums/viewtopic.php?f=22&p=2455#p2455)

The vertex format is almost figured out (missing on that page is the format of the vertex normals, I thought it was a RGB color, but instead they were the normals  in -128/127 range ),and the indices too.

IT3 files are containers basically, there are lots of stuff in there.

BBOX Model bounding box
BON3 Skeleton bone info
KAN6 Animation keyframes, I think
,and lots more.

My mod basically makes the game run at 60 fps (the english fan translation had an earlier,less polished system for that, it wasn't easy),and adds shadows back. The problem is that some of the level geometry has  wrong normals,and the shadow casting is all wrong.
