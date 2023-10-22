## Post #1
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2015-08-31T19:16:29+00:00
- Post Title: Trine 1 / 2 / 3 .fbm .s3d model importer

Maxscript for import of Trine 1, 2 and 3 .fbm and .s3d models in 3D Studio Max. 
Tested with Trine 1, Trine 1 Enchanted Edition, Trine 2 Gobline Menace DLC, Trine 2 Complete Story and Trine 3 The Artifacts of Power v.1.01 (Build 2997)
This version of the script is for static meshes only, without bone geometry. Maybe next time the bones and the animations...
The script also contains Trine 3 texture converter. The convertion by maxscript is extremely slow: first uncompress, then reorder of sequences of the bits ( I'm created lz4 algorithm by my self  )   You can uncompress the .fbi files using fbi-to-lz4.bms script before the maxscript convertion.


 trine-tools.rar
(5.58 KiB) Downloaded 193 times
## Post #2
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2015-09-01T06:42:39+00:00
- Post Title: Trine 1 / 2 / 3 .fbm .s3d model importer

Thx,

But Some Error Model From Trine 3  Here:

[http://www.mediafire.com/download/sjcs8 ... /model.rar](http://www.mediafire.com/download/sjcs8tztu24pbk9/model.rar)
## Post #3
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2015-09-01T09:23:27+00:00
- Post Title: Trine 1 / 2 / 3 .fbm .s3d model importer

> Reply from lumekano
>
> Thx,

But Some Error Model From Trine 3  Here:

http://www.mediafire.com/download/sjcs8 ... /model.rar

The files are version 16 ( maybe from Early Access period (alpha, beta, etc. )
Sorry, but, they are not supported at the moment. Maybe later..

Supported versions (header magic number) are 4, 7, 11 and 18

(The models are testte with Trine 3 The Artifacts of Power v.1.01 (Build 2997))
## Post #4
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2015-09-01T10:22:04+00:00
- Post Title: Trine 1 / 2 / 3 .fbm .s3d model importer

> Reply from vallex
>
> lumekano wrote:Thx,

But Some Error Model From Trine 3  Here:

http://www.mediafire.com/download/sjcs8 ... /model.rar

The files are version 16 ( maybe from Early Access period (alpha, beta, etc. )
Sorry, but, they are not supported at the moment. Maybe later..

Supported versions (header magic number) are 4, 7, 11 and 18

(The models are testte with Trine 3 The Artifacts of Power v.1.01 (Build 2997))

Well This To Baaad , thanks for trying.
## Post #5
- Username: Macrae
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 06, 2014 10:25 am
- Post datetime: 2015-09-10T16:04:31+00:00
- Post Title: Trine 1 / 2 / 3 .fbm .s3d model importer

> Reply from vallex
>
> Maxscript for import of Trine 1, 2 and 3 .fbm and .s3d models in 3D Studio Max. 
Tested with Trine 1, Trine 1 Enchanted Edition, Trine 2 Gobline Menace DLC, Trine 2 Complete Story and Trine 3 The Artifacts of Power v.1.01 (Build 2997)
This version of the script is for static meshes only, without bone geometry. Maybe next time the bones and the animations...
The script also contains Trine 3 texture converter. The convertion by maxscript is extremely slow: first uncompress, then reorder of sequences of the bits ( I'm created lz4 algorithm by my self  )   You can uncompress the .fbi files using fbi-to-lz4.bms script before the maxscript convertion.
trine-tools.rar

Thanks man!
## Post #6
- Username: ItsMeLenny
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 17, 2016 8:00 am
- Post datetime: 2016-03-23T12:08:19+00:00
- Post Title: Trine 1 / 2 / 3 .fbm .s3d model importer

I'd like to make a Blender importer for Trine models. I have Trine 1, 2, TGM and 3. (Enchanted and what not).
I'm most interested in starting with Trine 2 and Trine 3. However I'm not so interested in having it automatically import textures or skeletons at this point in time, just starting with the mesh and the UV.
Blender uses Python which I am quite competent in, however I can't quite quite understand this maxscript.
I'm hoping an outline or a pseudo-code version of the mesh section of the importer can be written out, which I can then use as a guide to write the Blender script and then I can post it here.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-23T15:10:25+00:00
- Post Title: Trine 1 / 2 / 3 .fbm .s3d model importer

> Reply from ItsMeLenny
>
> just starting with the mesh and the UV.For the mesh you don't need the maxscript:



treemen_humanoid_enemy.jpg (146.93 KiB) Viewed 460 times



> I'm hoping an outline or a pseudo-code version of the mesh section of the importer can be written out,I'd be surprised if anyone could/would do that for you.

(But if you sent me a sample of an fbm model (version 4, 7, 11 or 18) you're dealing with I could create a listener log file with some kind of fingerprint of said model.)

(I can't use the above version 16 model for such because it's not loaded by the maxscript and I'm too lazy to patch it.)
## Post #8
- Username: ItsMeLenny
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 17, 2016 8:00 am
- Post datetime: 2016-03-25T09:44:34+00:00
- Post Title: Trine 1 / 2 / 3 .fbm .s3d model importer

I guess I'm confused as to what the maxscript actually does then, I thought it was an importer for the Trine mesh into which ever 3D program.

This mesh extractor, does it allow converting any models to obj? (based on selecting the correct parameters or what not).
[edit: Oh it's a windows thing. I'm on Linux.]
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-05T07:49:25+00:00
- Post Title: Trine 1 / 2 / 3 .fbm .s3d model importer

> Reply from ItsMeLenny
>
> I guess I'm confused as to what the maxscript actually does then, I thought it was an importer for the Trine mesh into which ever 3D program.maxscripts (as the name states) allow to import into 3dsmax - then you can export the model to obj, fbx, ... - whatever exporter plugins are installed in 3dsmax.

> This mesh extractor, does it allow converting any models to obj? (based on selecting the correct parameters or what not).that's what most of the downloaders expect  it do to.
Not any model, though, but most of them.
And yes, it depends on the correct parameters - and that's what most guys (except a handful of people)
lack in: understanding how to get them.

> [edit: Oh it's a windows thing. I'm on Linux.]you could try Wine, couldn't you?

edit: version 16 - well, I didn't expect adding version 16 to be so simple:
adding 3 lines in the for k=1 to meshnum do loop:

```
			if version == 16 and actor do fseek f 3 #seek_cur
			local numverts = readshort f #unsigned
			format ("numVerts: %\n") numverts
			local numfaces = if actor then 0 else readshort f #unsigned
			if version == 16 and actor do skip = readbyte f
			if version == 18 and actor do skip = readbyte f
```

in the "case version of" block replace 11 temporary by 16
(or copy the switch case 11 block and rename 11 to 16)

That's all; tested with ONE (actor?) file only, so don't blame me 



treemen_humanoid.jpg (179.37 KiB) Viewed 416 times

hahaha, just realized: my previous pic was just the head bottom up  

@vallex: great script! Like it.
## Post #10
- Username: ItsMeLenny
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 17, 2016 8:00 am
- Post datetime: 2016-05-19T15:13:30+00:00
- Post Title: Trine 1 / 2 / 3 .fbm .s3d model importer

I've actually made a bit of progress with the blender importer, using these max script tools as a guide.
I will probably start up a new thread for a blender importer exporter, however for the moment I am having a slight hiccup and I'm not sure what's causing it.
Importing the thief; her bow seems to be the right aspect ratio but she herself not so much, however I'm more concerned with the extra faces. (So I have manually resized in the picture, which I also resized the bow with it which didn't need to be changed but woops).
Also, which do each of the versions relate to? As in the 3, 4, 7, 11, & 18.
The files I'm testing seem to be detected as version 3 and they come from the steam Trine 2 Complete Story.
I should point out that I am uses the vertices and faces and blender is constructing the edges itself. I can't find the edges in the maxscript.



after manual resize Screenshot from 2016-05-20 01-06-29.png (90.31 KiB) Viewed 369 times
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-19T19:58:18+00:00
- Post Title: Trine 1 / 2 / 3 .fbm .s3d model importer

startaddress of face indices probably wrong - use 0x10B56 for the body, 0x173a3 for the bow
## Post #12
- Username: ItsMeLenny
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 17, 2016 8:00 am
- Post datetime: 2016-05-20T00:24:07+00:00
- Post Title: Trine 1 / 2 / 3 .fbm .s3d model importer

The __BEFOREFACES body starts at 68432 and the __BEFOREFACES bow starts at 95133.
Then "if actor" 3 shorts are read, that brings the position for the faces up to the correct number for the body at least, the thief is done before the bow and also recognised as an actor.

Ahhh, I got it just now, it was me adding +1 to mimick the ms file, however I'm assuming it's something to do with python counting from the 0, I assumed that max script starts counting from the 1, not 100% sure on that but I wrote my code in that way.

Now all I have is the body being stretched in the wrong directions that I have to figure out.
I still have to add the rotation and the UV map.

edit: also on closer inspection, some of her vertices arn't joined, I'm not sure if this is normal for these models whether they were done in segments, but that will be a thing to fix in blender or in blender scripting, there is a merge doubles in blender so I'm so that would do it

edit edit: fixed rotation, almost fixed aspect ratio ( have to figure out how to get the bounding box in blenders python api)
having major difficulty with the UV, partly because I don't know how to do it in blender python api,
hoping I can get it because it's part of the main reason I wanted to do this, I want to see the models up close.

edit edit edit: in these models "backface culling" has to be turned on, it appears that for material they placed the backs infront of the fronts.



almost got it Screenshot from 2016-05-21 11-13-22.jpg (89.28 KiB) Viewed 342 times
## Post #13
- Username: ItsMeLenny
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 17, 2016 8:00 am
- Post datetime: 2016-05-22T02:13:23+00:00
- Post Title: Trine 1 / 2 / 3 .fbm .s3d model importer

So are Trine 3 models themselves also compressed. I extracted them from the fbq which are now compressed in LZ4 instead of LZF, I believe the images are also compressed in LZ4.
My importer doesn't work with Trine 3 models (based off the code here), because for every model it seems to print out a completely different random version number.
## Post #14
- Username: ItsMeLenny
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 17, 2016 8:00 am
- Post datetime: 2016-05-24T08:23:18+00:00
- Post Title: Trine 1 / 2 / 3 .fbm .s3d model importer

I did get version 16 working with that treeman model, but as for any of the models from Trine 3 (from steam) they don't work, all of them begin with quite a large random number. I don't know where the error lies.
## Post #15
- Username: ItsMeLenny
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 17, 2016 8:00 am
- Post datetime: 2016-08-14T07:30:40+00:00
- Post Title: Trine 1 / 2 / 3 .fbm .s3d model importer

I finally got it all working (almost).
When I try to load the trine 3 models their heads dont load and I get a read error on that final bit of the mesh.
Still fiddling around with it.
## Post #16
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2021-04-10T10:11:58+00:00
- Post Title: Re: Trine 1 / 2 / 3 .fbm .s3d model importer

When will Trine 4 model and texture support be added?
## Post #17
- Username: duuke
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 30, 2015 1:10 pm
- Post datetime: 2021-04-14T18:39:15+00:00
- Post Title: Re: Trine 1 / 2 / 3 .fbm .s3d model importer

Hello, any ideas how to extact the models from trine 4 ? Thanks
