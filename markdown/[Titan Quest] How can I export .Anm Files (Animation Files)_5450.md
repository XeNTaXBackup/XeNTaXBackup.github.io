## Post #1
- Username: Walleck
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 24, 2010 1:01 am
- Post datetime: 2010-11-23T18:50:06+00:00
- Post Title: [Titan Quest] How can I export *.Anm Files (Animation Files)

Hi
I've used the ArcExplorer to unpack the Files (*.arc), that have the models, animations etc.
To view and extract the Textures (*.Tex), I used TextureViewer, to open, view and export the models files (*.msh) I used the 3D Object Converter, but that .anm files I cannot figure out how to open/export. 
Titan quest use a physics engine, I'm still looking for a way to export to 3dsmax, or any other animation file format.

Here is some of .anm files.
[http://www.megaupload.com/?d=FO51ZUC7](http://www.megaupload.com/?d=FO51ZUC7)
Does anyone can help?
## Post #2
- Username: toolieo
- Rank: veteran
- Number of posts: 123
- Joined date: Sun Mar 21, 2010 9:16 pm
- Post datetime: 2010-11-24T15:23:11+00:00
- Post Title: [Titan Quest] How can I export *.Anm Files (Animation Files)

I don't have the question about the game "Titan Quest"  

Test Drive Unlimited uses this format for in game animations. I would also like to know is there anything that can open/export them?
## Post #3
- Username: Walleck
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 24, 2010 1:01 am
- Post datetime: 2010-11-24T22:36:07+00:00
- Post Title: [Titan Quest] How can I export *.Anm Files (Animation Files)

@toolieo
Look, once time I found a .Anm Script for 3ds Max, but it didn't load my .anm file. Here's the plugin if you wants to try...
[http://www.megaupload.com/?d=542NR1WL](http://www.megaupload.com/?d=542NR1WL)

Also, there is a kind of Animation Editing Toolkit, made by Tamschi. I've tried this program but it didn't work with these .anm. If does anyone wants try, here is it.
[http://www.titanquest.net/tq-forum/thre ... ng-Toolkit](http://www.titanquest.net/tq-forum/threads/31826-Animation-Editing-Toolkit)

I tried this RW Analyze [http://www.steve-m.com/downloads/tools/rwanalyze/](http://www.steve-m.com/downloads/tools/rwanalyze/)
And I can open the file, but its a kind of Hex code.
And seems that will not work, because show a "Data format Unknow" msg.

```
00000014  4D 6F 76 65 41 58 49 53  MoveAXIS
0000001C  00 00 00 00 00 00 00 00  ........
00000024  00 00 00 00 00 00        ......
```


There is one more thing, I found this post talking about .Anm files, how to "decompile" it, I don't know.
[http://www.gtaforums.com/index.php?showtopic=262789](http://www.gtaforums.com/index.php?showtopic=262789)
Its seem that isn't only me that looking for a way to manage these files.
## Post #4
- Username: bluearms
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Oct 13, 2010 4:48 am
- Post datetime: 2010-11-25T05:39:10+00:00
- Post Title: [Titan Quest] How can I export *.Anm Files (Animation Files)

> Reply from Walleck
>
> @toolieo
Look, once time I found a .Anm Script for 3ds Max, but it didn't load my .anm file. Here's the plugin if you wants to try...
http://www.megaupload.com/?d=542NR1WL

Also, there is a kind of Animation Editing Toolkit, made by Tamschi. I've tried this program but it didn't work with these .anm. If does anyone wants try, here is it.
http://www.titanquest.net/tq-forum/thre ... ng-Toolkit

I tried this RW Analyze http://www.steve-m.com/downloads/tools/rwanalyze/
And I can open the file, but its a kind of Hex code.
And seems that will not work, because show a "Data format Unknow" msg.
Code: Select all0000000C  1E 00 00 00 08 00 00 00  ........
00000014  4D 6F 76 65 41 58 49 53  MoveAXIS
0000001C  00 00 00 00 00 00 00 00  ........
00000024  00 00 00 00 00 00        ......

There is one more thing, I found this post talking about .Anm files, how to "decompile" it, I don't know.
http://www.gtaforums.com/index.php?showtopic=262789
Its seem that isn't only me that looking for a way to manage these files.

Same extension does not mean they use same format in game. I think only the file from titanquest forum is valid.
3ds max exporter is for chrome engine [http://en.wikipedia.org/wiki/Chrome_Engine](http://en.wikipedia.org/wiki/Chrome_Engine)
Other stuffs are for GTA games.
## Post #5
- Username: Walleck
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 24, 2010 1:01 am
- Post datetime: 2010-11-26T04:16:12+00:00
- Post Title: [Titan Quest] How can I export *.Anm Files (Animation Files)

@bluearms
But I tried that Animation Editing Toolkit but I could not export the animations to other format or put it on any 3D software...
## Post #6
- Username: bluearms
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Oct 13, 2010 4:48 am
- Post datetime: 2010-11-26T14:01:57+00:00
- Post Title: [Titan Quest] How can I export *.Anm Files (Animation Files)

> Reply from Walleck
>
> @bluearms
But I tried that Animation Editing Toolkit but I could not export the animations to other format or put it on any 3D software...

It works but it does not give any valid format which can be used in 3d program. Read readme.txt.

anim_split <anm file> generates basic data files with extension ".boneanim" which is splited for each bones.
then use bonedata_info <boneanim> which gives the number of frames in each <simple float array file!>.

That's all. Other stuffs are for editing purpose (append, crop, repeat etc). The author(Tamschi) has made other stuffs like meshview, animation callback editor etc.

Reading [http://www.titanquest.net/tq-forum/thre ... tion-Edit!](http://www.titanquest.net/tq-forum/threads/31810-Successful-Animation-Edit!) may be helpful.  I think 14 floats foam a one frame data and there is a info about meaning of 14 floats.
## Post #7
- Username: Walleck
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 24, 2010 1:01 am
- Post datetime: 2010-11-27T00:23:03+00:00
- Post Title: [Titan Quest] How can I export *.Anm Files (Animation Files)

hmm
Thanks man, I'll try to do that.
