## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-12T07:13:50+00:00
- Post Title: [Request] Ares

Ok another great game of company MGAME, the game have a lot different format, freaky formats, someone can take a look files.

<link removed due forum rules violation>
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T08:46:16+00:00
- Post Title: [Request] Ares

The files for the mobs are just skeleton/animation info.
I have seen n3cskin before in another game but don't remember which. It is not hard (well, meshes anyways)

Oh right, n3pmesh was used in HeroOnline and another MMO. It should be the same format as the ones here (same engine I guess)

n3cskin: [http://db.tt/WSlByAqp](http://db.tt/WSlByAqp)
Dxt textures: [http://db.tt/eXviPK0v](http://db.tt/eXviPK0v)

The n3cskin format is just

```
matName?

int32 numVerts
int32 numFaces
int32 numUV

vertex buffer (24 bytes each)
indices (numFace * 3)
UV buffer (8 bytes each)
UV indices (numFace * 3)

#more

```


I just don't know how to render that in noesis cause the UV is separate...



Maybe someone can tell me how to assign the UV's in this case?
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-12T09:05:02+00:00
- Post Title: [Request] Ares

you rock man, textures working fine.

PD: but how UV can work out? truth never amazes me to hear it, well I go to sleep, is 6:10 in the morning here, rest thank you very much for everything, I will try to watch some of that tomorrow.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-12T12:50:51+00:00
- Post Title: [Request] Ares

here is an example max script i have done where the uv's were per face rather then per vertex I just converted it so they were per vertex.
[League of Legends.rar](https://xentaxbackup.github.io/file/5054_League of Legends.rar)
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T16:01:44+00:00
- Post Title: [Request] Ares

Hmm, so per-face UV's can always be converted into per-vertex UV's?
Does that apply to normals as well?
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-12T16:05:57+00:00
- Post Title: [Request] Ares

yes
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T16:09:18+00:00
- Post Title: [Request] Ares

LOL I think I've asked this before and you posted the same script for reference.
