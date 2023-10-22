## Post #1
- Username: JackusCTB
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jan 21, 2016 11:25 pm
- Post datetime: 2016-01-21T16:27:20+00:00
- Post Title: Convert AW's CryEngine cgf or cga to obj or sth like that :)

Hello, I would like to convert some tanks and vehicles from the game "Armored Warfare" in a readable and workable format like WaveFront OBJ, autodesk max and similar file types. I found very little on the web and the only things which I found didn't work for me: I  could only get a black "bounding box" of the real shape. Not noesis nor the cgf conversion script worked.... Is there a way to convert these cryengine 3d models in a lossless way, without losing any information like normals and so on?
Thanks and have a nice day  !

Link of an example M1 abrams cannon with material and texture files: [http://www114.zippyshare.com/v/piv7mN49/file.html](http://www114.zippyshare.com/v/piv7mN49/file.html)
VT link: [https://www.virustotal.com/en/file/ffea ... 453393671/](https://www.virustotal.com/en/file/ffea13ee9cfb07d31a2d6b0e1d747423dcee7a765b62b7384aefb1c4ec40fb76/analysis/1453393671/)
## Post #2
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2016-01-21T21:53:38+00:00
- Post Title: Convert AW's CryEngine cgf or cga to obj or sth like that :)

Noesis with cryengine plugin (cryengine_cgf.dll) can read the meshes just fine.
As for the textures, I don't know! 

edit: I used DDSUnsplit for the textures, it just returns a huge solid red texture - No good.
## Post #3
- Username: JackusCTB
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jan 21, 2016 11:25 pm
- Post datetime: 2016-01-22T14:03:39+00:00
- Post Title: Convert AW's CryEngine cgf or cga to obj or sth like that :)

> Reply from lolwatt
>
> Noesis with cryengine plugin (cryengine_cgf.dll) can read the meshes just fine.
As for the textures, I don't know! 

edit: I used DDSUnsplit for the textures, it just returns a huge solid red texture - No good.
Hey, thanks for the reply!
DDSUnsplit gave me a red texture as well, not good  As for the noesis programme, I had some doubts about it after reading these lines:

> The current way of accessing modern Cryengine games was to use Noesis (by Mr Adults) with the cryengine_cgf.dll plug-in (by revelation). And this worked decently for most activities, but there were a number of limitations when used against the modern game files:
>
> 
>
> * Materials weren't referenced properly, so you had to manually create them and assign to the right vertex group (involved a lot of guesswork).
>
> * Didn't work with files newer than CE 3.4.
>
> * With some objects, the geometry was exploded and each component had to be manually placed.
>
> * Didn't recognize .cga files, although you could rename .cgf files to .cga.
>
> * The geometry was a bit haphazard, with tons of duplicate vertices.
>
> * UV maps weren't normalized.

from [viewtopic.php?f=33&t=13137](http://forum.xentax.com/viewtopic.php?f=33&t=13137)
That's why I asked the question! If you assure me it perfectly converts models from cgf to obj then i might give it a try! Do you know how to get the latest version of the cryengine dll?
## Post #4
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2016-01-24T22:08:56+00:00
- Post Title: Convert AW's CryEngine cgf or cga to obj or sth like that :)

Hey!

The mesh looks OK, but there are (a lot of) duplicated vertices, like it always happens. :/

You could try to import the cgf to CRYENGINE and File>Export from there, perhaps this works better.
