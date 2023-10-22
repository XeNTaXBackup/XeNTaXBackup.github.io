## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-25T12:54:35+00:00
- Post Title: [Request] RedBlood Online

Hello, a very cool and graphic game with engine of Gamebryo File Format Version 30.0.0.2, ok I try open files and with Gamebryo can be opened, but with nif importer not, maybe finale can take a look info of this files and update nif script?




Script Error in Noesis

```
503316482
Traceback (most recent call last):
  File "C:\Program Files\Noesis 3.82\plugins\python\fmt_Gamebryo_nif.py", line 26, in noepyLoadModel
    mdl = rapi.rpgConstructModel()
RuntimeError: Failed to construct model from rpgeo context.
Cleaned 8.00MB (in 2 pools).
```


Format: NIF
Version: 30.0.0.2

[RedBlood Online 2D-3D Samples](http://www.mediafire.com/download.php?xcsei9whutd8y0a)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-25T13:45:38+00:00
- Post Title: [Request] RedBlood Online

> Gamebryo can be opened

You mean nifskope?
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-25T13:56:11+00:00
- Post Title: [Request] RedBlood Online

no Gamebryo.

[http://www.gamebryo.com/](http://www.gamebryo.com/)
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-25T14:57:17+00:00
- Post Title: [Request] RedBlood Online

Well, I would expect gamebryo to load their own models lol

I want to at least finish one version of gamebryo (at least textured meshes) before looking at others.
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-25T15:49:25+00:00
- Post Title: [Request] RedBlood Online

ok thanks for support anyway
## Post #6
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-06T06:07:20+00:00
- Post Title: [Request] RedBlood Online

For the meshes it's 'fairly' easy.
[http://pastebin.com/AetYa1RY](http://pastebin.com/AetYa1RY)
(don't replace your existing nif script, just rename or move it)
This is a real ugly hack, just don't know enough about python and noesis yet.



Hey finale00, how you get noesis to show and export all the sub models? 
Or even change the base orientation and shading?

Edit: change the last part of the script to

```
            #mdlList.append(mdl)
                
            i = i+1            
            offset += size
    mdlList.append(mdl)

    return 1

```
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-06T07:11:36+00:00
- Post Title: [Request] RedBlood Online

You wanted to bind all of the buffers before constructing the model?
Don't accidentally remove the constructmodel at the end lol

But nice work with this version.

It looks like it's not as ugly as 20.6.x with all of the references?
## Post #8
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-03-06T10:02:40+00:00
- Post Title: [Request] RedBlood Online

well thanks a lot ninja, but any time I open Noesis get it "ImportError: No module named nif_30.0.0.2", I try change name of file and anyway the error still there.
## Post #9
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-06T17:09:50+00:00
- Post Title: [Request] RedBlood Online

Rename it to fmt_Gamebryo_nif.py (after moving or renaming your older version), then reload the plugins.
only reason it would say nif_30.0.0.2 is because of the file name.
Meant it for copy and paste, not download, do better next time.
(will repost when I get the textures to load correctly without using such a bad hack.)

Lol - like i know what i'm doing 
Wanted to do it using the classes but couldn't get the damn thing to access the mdl and mdlList from within the class, was quicker to write it from scratch in the end. Actually just needed to access the mdl - bah.
Did try adding all the vertices to the same buffer and incrementing the triangle indices correctly within a single buffer, worked on small models but crashed it on larger ones. So guessed the buffer size is limited.

Had a look at a 20.6.x from the thread, it's got NiDataStream.0.19.......
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-06T17:26:11+00:00
- Post Title: [Request] RedBlood Online

Lol there are many different data stream chunk.
In catherine and microvolts I think the blender import had like at least 7 different NiDataStream chunks (124, 128, 24, 30, ....)

I wouldn't mind updating nifskope's XML file to parse the new structs, but...well, sort of lazy to read docs.

For constructing the model, the observation I've made is that you can bind all of the buffers first and then later construct model. Only when the context is reset does it seem to clear the bindings.

That's why I construct the model outside of my parser class (also because its a parser, it should only be parsing, so technically I shouldn't be binding my buffers in there for good style)
## Post #11
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-03-06T17:47:27+00:00
- Post Title: [Request] RedBlood Online

for any reason when I change name, never load, try many times and now it worked, maybe some mistakes with names, thanks Ninja and finale00.
