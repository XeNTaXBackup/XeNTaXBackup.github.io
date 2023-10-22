## Post #1
- Username: Barut
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 08, 2015 9:56 am
- Post datetime: 2015-05-08T22:50:52+00:00
- Post Title: Weird format DDS

Can anyone help me decode these dds files to a normal dds? The game files and the extracted dds are from a new upcoming very popular MMO Skyforge.

I have included also the binaries from the game in case they are needed.

[https://mega.co.nz/#!r1QjGRiS!76K3mZqFH ... ISMX3_SLIw](https://mega.co.nz/#!r1QjGRiS!76K3mZqFHNkFSHbmHglOvVLe7ltJhcnCCISMX3_SLIw)
[https://mega.co.nz/#!ulxSmBaC!MGugGaVDL ... VD-hBnwyYs](https://mega.co.nz/#!ulxSmBaC!MGugGaVDLDT8MQ9sdAIyo1otlcE_77LhAVD-hBnwyYs)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-05-14T21:33:05+00:00
- Post Title: Weird format DDS

These look encrypted.
## Post #3
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2016-08-22T19:54:33+00:00
- Post Title: Weird format DDS

Not sure if textures are encrypted. i managed to extract them using Texture Finder. they were all DTX5 with alpha channels, but they aren't exactly conventional textures besides the diffuse texture. this is what i got from TF.

as you can see, there's no specular, gloss or ambient occlusion maps. the control map i think is used for gloss and spec values in the game and tells the engine which materials to apply to the models. not sure why mask and emissive maps are together thought. the strangest thing is that the diffuse alpha channel and the control alpha channel when combined in photoshop make the normal map. the Diffuse alpha is the red channel, control alpha is green and the blue channel is empty. has anyone encountered this before?
