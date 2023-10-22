## Post #1
- Username: zzz
- Rank: beginner
- Number of posts: 21
- Joined date: Wed May 21, 2014 9:36 pm
- Post datetime: 2014-09-14T10:42:15+00:00
- Post Title: Playstation 3 SDK compressed index buffers info?

Still working on trying to get UE3 PS3 games to co-operate. Gildor took a look and said:

> I've spent a few hours trying to support static meshes from Dust 514. Unfortunately I'm stuck: the loaded static mesh has empty index buffer. I believe this game uses ps3's compressed index buffers for rendering, (which is a part of PS3 SDK).

Is there a way to obtain this data for him to use? Thanks.
## Post #2
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-09-14T11:52:11+00:00
- Post Title: Playstation 3 SDK compressed index buffers info?

its edge compressed index buffer most likely.
you can read them with this data.
[https://code.google.com/p/noesis-plugin ... treader.py](https://code.google.com/p/noesis-plugins-official/source/browse/trunk/revelation/bitreader.py)
and
[https://code.google.com/p/noesis-plugin ... eta/psa.py](https://code.google.com/p/noesis-plugins-official/source/browse/trunk/chrrox/import/beta/psa.py)
## Post #3
- Username: zzz
- Rank: beginner
- Number of posts: 21
- Joined date: Wed May 21, 2014 9:36 pm
- Post datetime: 2014-09-14T19:22:23+00:00
- Post Title: Playstation 3 SDK compressed index buffers info?

Gildor replied with:

> I don't see anything related to Edge index buffer there. I believe if chrrox would write that, he would inform me about that, because we has a discussion about ps3 compressed indices a few years ago.
## Post #4
- Username: daiesy23
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 11, 2017 3:27 pm
- Post datetime: 2017-08-11T07:36:46+00:00
- Post Title: Playstation 3 SDK compressed index buffers info?

Hello,

Has anyone seen this console? I'm barely Nintendo collector and this piece was found in a pawn shop. Took it just for curiosity. But has no knowledge about these. Already found, that it should play all PS1, PS2, PS3 games without a regional lockout. Is it true? Has no old games to test it.
Appreciate any info.
