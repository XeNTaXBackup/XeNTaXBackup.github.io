## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-22T02:29:41+00:00
- Post Title: Dekaron online

homepage: [http://dekaron.gamehi.com/](http://dekaron.gamehi.com/)



Unpackers and blender imports are already available for this game.

blender: 
[http://www.elitepvpers.com/forum/dekaro ... ost3957938](http://www.elitepvpers.com/forum/dekaron-private-server/430851-look-what-i-found.html#post3957938)

Never tried it. I only got it for reference.

unpacker:
[http://www.elitepvpers.com/forum/dekaro ... acker.html](http://www.elitepvpers.com/forum/dekaron-exploits-hacks-bots-tools-macros/331822-release-global-unpacker-packer.html)
## Post #2
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-22T10:25:16+00:00
- Post Title: Dekaron online

well yes is a old, this format is .mesh and can be imported into Blender 2.49 with this script, enjoy it and thanks a lot to Peter S. Stevens is author of it.
[Dekaron_importer.rar](https://xentaxbackup.github.io/file/4654_Dekaron_importer.rar)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-22T14:36:39+00:00
- Post Title: Dekaron online

I briefly skimmed it but it seems to skip a lot of stuff. Guess he only figured out that much?

EDIT: not a complaint, but it looks like it doesn't cover any of the weapons I'm working with, so most likely it is for a specific set of meshes, but it is good for reference cause I would've had no idea how to parse those face indices lol

They've got pretty nice weapons (but they won't load unless you change the script).

Particularly line 134:

```
dekaron_mesh_file_mesh_index_count = struct.unpack('<IIIII', dekaron_mesh_file.read(20))
```


Not only does that not make sense to me since it returns a tuple and it's comparing that to 0 afterwards, but it doesn't work for weapons.

There are only two ints, not 5. I can understand why people in the thread I posted were complaining about why it didn't work.
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-24T09:46:49+00:00
- Post Title: Dekaron online

well yes maybe you right, beacause I don't see any custom in this game never :S
## Post #5
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-10-25T07:52:19+00:00
- Post Title: Dekaron online

Hi
Here is a blender importer for skeleton ,skin, animation and texture.
It works only with Blender version 249 and Python version 2.6.
[Blender249[DekaronOnline][mesh][anim][2014-10-25].zip](https://xentaxbackup.github.io/file/7984_Blender249[DekaronOnline][mesh][anim][2014-10-25].zip)
## Post #6
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2014-10-25T15:53:00+00:00
- Post Title: Dekaron online

2 Szkaradek123
Have any chance to get Noesis python plugin for viewing meshes ?

thx ...
## Post #7
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2014-11-01T07:51:06+00:00
- Post Title: Dekaron online

Here noesis plugin for .mesh viewing ...

But have some issues, if anyone know how to fix it - post here 
1. Need press Face Cull (F4) on some models (samples here [http://rghost.net/58822731](http://rghost.net/58822731))
in import script material defined with mat.ZTRANS=True, how to do same in Noesis ?

```
			blendMat.mode |= Blender.Material.Modes.ZTRANSP
			blendMat.mode |= Blender.Material.Modes.TRANSPSHADOW 
			blendMat.alpha = 0.0 

```


2. Artifacts on some models (samples here [http://rghost.net/58822731](http://rghost.net/58822731))
i have no idea ;( In blender all ok, in noesis not, indices dump is similar ;(



UPDATE 2014-11-04
not open .mesh files with another ID BYTES - fixed, thx 2 shakotay2
UPDATE 2014-11-01
.tpack parser fixed ...
[fmt_dekaron_mesh.zip](https://xentaxbackup.github.io/file/8031_fmt_dekaron_mesh.zip)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-03T03:22:00+00:00
- Post Title: Dekaron online

> Reply from deltaone
>
> 
2. Not open .mesh files with another ID BYTES (Second format ?)
i have no idea, samples here  http://rghost.net/58830148
very simple:
IDBYTES = {'mesh': b'\x03\x03\x06\x20'}
size = 72

> 3. Artifacts on some models (samples here http://rghost.net/58822731)
>
> i have no idea ;( In blender all ok, in noesis not, indices dump is similar ;(
well, the 2 additional faces prob for the bat is harder to solve...

Seems that in Noesis there are two additional faces (which one of them disappears on face cull, F4).
 f 69 70 71
 f 72 71 70



bat_01_faces_comp.JPG (164.31 KiB) Viewed 280 times


You'll need some expert for triangle strip algos to solve this.
