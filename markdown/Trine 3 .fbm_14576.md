## Post #1
- Username: ItsMeLenny
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 17, 2016 8:00 am
- Post datetime: 2016-06-27T10:27:38+00:00
- Post Title: Trine 3 *.fbm

On the forums here somebody had created what they claimed is a Trine 1, 2 & 3 importer for models via maxscript (which ever program uses this).
I've been converting this to python for blender. The importer does Trine 1 as .s3d, and then Trine 2 and up as .fbm different versions, those versions being 4, 7, 11, 16, & 18. 4 and 7 I think are Trine 2, 16 is some extra added format which is possibly from a Trine 3 beta, and I'm assuming Trine 3 is 18.
The problem is all the Trine 3 models I've uncompressed from their "LZ4" zip file start with a random large number, some of these numbers are the same as others, but a lot of different numbers all up.
I am unsure if these files themselves are compressed or encrypted. The textures for the models in Trine 3 are allegedly compressed with LZ4 compression (according to another post on this forum. I haven't tried uncompressing the textures myself but they arn't viewable in gimp or blender in their default format where as Trine 2 textures are).
I had a model of a version 16 file working fine, it was a tree man from Trine 3, however I am unsure where this file came from, it's not one I have and I don't know where to find any Trine 3 beta.

Related topics on a different forum is this: [http://zenhax.com/viewtopic.php?f=9&t=1 ... 018#p14018](http://zenhax.com/viewtopic.php?f=9&t=1065&p=14018#p14018)
Relating to how to uncompress the compressed folders. (Please remove the link if it's against policy to post links to other forums).

And this: [viewtopic.php?t=13269](http://forum.xentax.com/viewtopic.php?t=13269)
Relating to the import using maxscript.

Here are links to two Trine 3 models:
thief.fbm [https://drive.google.com/file/d/0B_kjh0 ... sp=sharing](https://drive.google.com/file/d/0B_kjh0L1etroUkw4RGh6OWRDZ2M/view?usp=sharing)
thief_01.fbm [https://drive.google.com/file/d/0B_kjh0 ... sp=sharing](https://drive.google.com/file/d/0B_kjh0L1etroT2xJaDE2YUFBbEU/view?usp=sharing)
I don't actually know what these will be, they relate to the thief character, however following the naming patterns of Trine 1 & 2, the second link (thief_01) I would assume is the model used in game. Maybe the first is for cut scenes.

I'm hoping someone can help me figure out how to open these models. Thanks for your help.
## Post #2
- Username: ItsMeLenny
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 17, 2016 8:00 am
- Post datetime: 2016-07-29T09:28:19+00:00
- Post Title: Trine 3 *.fbm

It turns out all along the python file I was using to extract the models was corrupting them in some way.
I had updated a python LZ2 trine script to do LZ4 trine files and it was only half doing them.
I ended up using quickbms and a script through Wine on Linux.
