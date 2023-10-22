## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-04-11T23:44:50+00:00
- Post Title: Keeper 2 texture format, compression?!

Seems to use compression, a 128x128 texture with only 5KB must be compressed somehow.

```
    int resx;
    int resy;
    int size; // size of the whole file - 12
    short resx;
    short resy;
    int uk; // = 0x75 -> compression identifier?
}

```

Here are some sample files, any help is appreciated. 

Edit: If you need more example files and have DK2 or the demo, you can grab my Texture Extractor [here](http://forum.xentax.com/viewtopic.php?t=2583)
[Imp textures.rar](https://xentaxbackup.github.io/file/1119_Imp textures.rar)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-04-24T13:17:51+00:00
- Post Title: Keeper 2 texture format, compression?!

Dungeon Keeper 1 uses RNC compression, maybe something like that is used here, too?
[http://www.yoda.arachsys.com/dk/](http://www.yoda.arachsys.com/dk/)
[http://www.devrs.com/gb/files/rnc.zip](http://www.devrs.com/gb/files/rnc.zip)
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-21T08:05:46+00:00
- Post Title: Keeper 2 texture format, compression?!

Still wondering what compression is used here.
I already reversed a decompression routine used in DK2's archive files -> [viewtopic.php?f=21&t=2855](http://forum.xentax.com/viewtopic.php?f=21&t=2855)
But this seems to be yet another technique, doesn't it?
## Post #4
- Username: dedesite
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 17, 2010 6:47 am
- Post datetime: 2010-04-18T13:02:40+00:00
- Post Title: Keeper 2 texture format, compression?!

Hi, 
I know that this is an old post, but I'm trying to read DKII textures (and other DKII format).
I was making your texture extractor when I found your post Rheini .

Have you succed to read DKII Textures. Your post on gameformats.de doesn't exist anymore, can you give me informations that you found on the compression method?
Other question :
* Do you know why Creature textures are in the GUI folder?
* What is MM0, MM1 etc. MipMapping textures? Does thoses techniques exists in 1999.  There seems to be MipMap for every texture, why? You don't need mipmap for Gui Texture, or maybe it is for manage different resolution?
* Do you know anything about the other DKII file formats (kmf, kcs, kwd, kld...)? 

Hope you will read my post 

EDIT : I found your post on KMF, it will really helps me thanks a lot!!
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-04-18T18:30:24+00:00
- Post Title: Keeper 2 texture format, compression?!

[http://durchschuss.du.funpic.de/index.p ... k2textures](http://durchschuss.du.funpic.de/index.php?cat=games&site=dk2textures)
## Post #6
- Username: dedesite
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 17, 2010 6:47 am
- Post datetime: 2010-04-26T18:06:21+00:00
- Post Title: Keeper 2 texture format, compression?!

Thank you for the link.
Now I try to load kmf file and when I can be able to load 3D model, anim and uv into a ogre3D app, I'll look at the textures.

Hope they'll find a solution here:
[http://forum.keeperklan.com/dk2-texture ... e575c406b1](http://forum.keeperklan.com/dk2-texture-format-t220.html?s=9b487528d10d9a02f8d889e575c406b1)&

There is also the "wine" solution .

Greetings,
Andreas
## Post #7
- Username: SkolarSLO
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 27, 2011 1:57 am
- Post datetime: 2011-01-27T07:31:10+00:00
- Post Title: Keeper 2 texture format, compression?!

Hi guys, so could someone help me... i would like to try making a HD version of DK2. But I would need the textures, and all i found are the files without a file format(as you already mentioned here).. theyve seem to open it somehow (on some other forum that were linked all togeather) but i dont know what the hell do all of these codes mean... So if someone with a better knowledge of breaking these files could help me... that would be nice

PS. I know its a old post but i might get some help.
## Post #8
- Username: dedesite
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 17, 2010 6:47 am
- Post datetime: 2011-01-27T08:11:37+00:00
- Post Title: Keeper 2 texture format, compression?!

Hi, 

I'm not a "binary format hacker" so I quickly give up reading DKII's files (both animated mesh and textures...).
But I'm a game developper so I know how to make a game and really love to make a DKII remake, so if you found some interesting infos, maybe I can help you .

Also, I don't know if I'll have enough time.

Greetings,
Andreas

P.S : I still think that running the game through wine and sniffing what is send to DirectX could be a good way to retrieve textures infos. I know a bit about wine (I follow the wine-devel list) so I may look at it sometime.
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2011-01-27T17:23:40+00:00
- Post Title: Keeper 2 texture format, compression?!

There's no point in working on this for a DK2 remake.
DK2 uses vertex animation, you wouldn't want to use that nowadays.
And its textures are way too small for good graphics.

Plus we have much better models by now :
[](http://www.keeperklan.com/threads/172-Blutonium-s-3D-Model-Thread)
[http://www.keeperklan.com/threads/172-B ... del-Thread](http://www.keeperklan.com/threads/172-Blutonium-s-3D-Model-Thread)
## Post #10
- Username: dedesite
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 17, 2010 6:47 am
- Post datetime: 2011-01-27T23:07:18+00:00
- Post Title: Keeper 2 texture format, compression?!

OOh, you're working on a DKII Remake, cool!!

I know that DKII uses vertex animation and that the textures are damn small but I don't care, I just want to have those resources to start making the remake (if I found the time to work on it).

The models you're showing didn't seems to be made for real time, is there any low poly version on which you gonna beck the high res mesh? Aren't the textures to big? Are all the mesh rig, skin and animated? It's a lot of work to do that and with the original ressources this work is already done. Even if it's a bit "old school" we can easily scale the textures and re work a bit on them. For the meshes it's harder since they use vertex animation we can't work on the mesh and keep skeleton animation datas...

If I ever start a DKII remake (which I doubt regarding my schedules), I'll only focus on coding the game and the editor that came with, if there is a stable technical basis, resources will come with no problems.

The most important thing is that the game must be playable, then we could talk about graphics quality (IMHO).

I don't know how advanced is your project but I which you all the best.

Greetings,
Andreas
## Post #11
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2011-01-29T20:47:10+00:00
- Post Title: Keeper 2 texture format, compression?!

Then good luck.
Texture compression technique is still unknown and the model format is very complex.
I already reversed a lot of it in another thread here but especially animations are hard.
