## Post #1
- Username: metapoodle
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 13, 2018 1:28 am
- Post datetime: 2018-07-01T04:02:06+00:00
- Post Title: FFXV Model Imports, Maya 2018 and vertex groups/weights

I’ve been having a couple of strange issues with FFXV models imported to Maya 2018.   Models exported from Noesis have to be scaled up by a factor 100. I managed to solve that problem while preserving the armature. However, when I loaded one of the Maya edited models into the game, the model’s midsection was stretching out to infinity. 

I’d actually seen this problem before with FFXV model swaps and several Blender users found a solution. If you look at the vertex groups, there were references to the “trans” bone that didn’t belong. If you delete that reference, it cures the problem—but only in Blender. I’ve looked at the hyper graph hierarchy and there is no similar reference that can be deleted.  In short, I have no idea how to fix this in Maya. 

I’m sorry if this isn’t completely clear—happy to update with more info and images. I’m just hoping someone here has seen a similar issue and might have advice. Thanks!!
## Post #2
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2018-07-07T00:13:50+00:00
- Post Title: FFXV Model Imports, Maya 2018 and vertex groups/weights

I would definitely need to see some images. Sounds very strange.
## Post #3
- Username: metapoodle
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 13, 2018 1:28 am
- Post datetime: 2018-07-12T15:53:58+00:00
- Post Title: FFXV Model Imports, Maya 2018 and vertex groups/weights

Thanks for the response!  I managed to figure this one out by fiddling with the "Rigging" workspace in Maya.  If you go to the paint weights tool panel, you can select vertices.  I just selected vertices that seemed to be broken and removed the trans influence.  The main issue is how different Maya and Blender work in terms of rigging.
