## Post #1
- Username: Ultraplayer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 27, 2017 1:15 am
- Post datetime: 2019-09-14T09:11:47+00:00
- Post Title: Double/Triple same meshes in models

I have noob question: why in some games models has a couple of same meshes? Sometimes twice, sometime triple?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-14T09:19:56+00:00
- Post Title: Double/Triple same meshes in models

Look at the vertex count - in case it's different it's assumed to be differend LODs (level of details).
They are used for matter of performance in 3D games. Objects in the background don't need to be rendered in full detail - the games usually use the lowest LOD models for such (where highest lod might be named lod0, lower lods being lod1, lod 2 then).
