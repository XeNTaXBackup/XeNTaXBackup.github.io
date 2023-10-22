## Post #1
- Username: blaar
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Oct 03, 2011 3:12 pm
- Post datetime: 2013-12-16T15:18:21+00:00
- Post Title: Mechwarrior Tactics : Unity Browser Based game

I was wondering. Any one played a bit with Unity Browser Based games ?

I would love to get my paws on some Mechwarrior Tactics 3d meshes so that I can sit and convert them to paper models.

The game does not have a client that must be installed before one can play, but instead it is all streamed directly to PC. My guess is , that the downloaded data is stored in the browser's cache.

Any ideas ?

Thanks
## Post #2
- Username: Reinitialized
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 27, 2013 5:37 am
- Post datetime: 2013-12-26T22:15:24+00:00
- Post Title: Mechwarrior Tactics : Unity Browser Based game

I've been able to dump the assets of Unity Web Player games using the following tool:
[https://github.com/ata4/disunity](https://github.com/ata4/disunity)
with the command 'disunity -c dump <asset bundle path>'

The path to the cached asset bundles for a particular one of these games on my PC is:
%HOMEPATH%\AppData\LocalLow\Unity\WebPlayer\Cache\<game name>
## Post #3
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2013-12-28T14:30:08+00:00
- Post Title: Mechwarrior Tactics : Unity Browser Based game

Or you could use this MAXScript: [http://kotschopshop.com/topic/5134976](http://kotschopshop.com/topic/5134976)

It supports assets created with all Unity versions from 2.5.0f5 to 4.2.0f4 (4.3 will be added soon) and many platforms such as Web, PC, iOS, Android, Xbox 360, OSX and Linux.
Models are imported with complete hierarchy and transformations, materials, vertex normals, color, UV1 and UV2.

To get files from web-based games, you can use programs like URLsnooper to look for .unity3D files.
