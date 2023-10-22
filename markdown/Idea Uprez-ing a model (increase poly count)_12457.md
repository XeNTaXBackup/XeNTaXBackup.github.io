## Post #1
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-01-01T23:44:11+00:00
- Post Title: Idea: Uprez-ing a model (increase poly count)

I was wondering if anyone has heard of a way or a tool to increase the quality of old models
I know current game models have showed off real time subdivision
I really don't know how they re-calculate new UVs and bone weights in real time (Maybe they use it only for non-skinned meshes)

I don't know if there is a good algorithm that keeps sharp edges sharp and rounds out only specific edges

I'm just dreaming here
## Post #2
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2015-01-02T00:02:23+00:00
- Post Title: Idea: Uprez-ing a model (increase poly count)

With game models I just do a re-topology with a subsurf/turbosmooth in 3DS Max or ZBrush to give the model a higher polycount while keeping the edges sharp. I'm sure there are other ways of doing it. Of course this is with non-skinned meshes, you would lose textures by increasing the polycount so you would have to figure a way around this.
## Post #3
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-01-02T00:19:17+00:00
- Post Title: Idea: Uprez-ing a model (increase poly count)

I tried something like that once and it wrecked the edges of the model I was using at the time
I would prefer to do this in code so I can interpolate UV Value as well as  bone weights
