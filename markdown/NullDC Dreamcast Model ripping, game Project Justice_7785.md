## Post #1
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-12-01T05:15:21+00:00
- Post Title: NullDC Dreamcast Model ripping, game: Project Justice

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2011-12-01T20:30:58+00:00
- Post Title: NullDC Dreamcast Model ripping, game: Project Justice

Alright, I got this working. The game works fine on the emulator, and 3d ripper DX rips textures perfectly. The problem is, the mesh it rips is entirely flat. I didn't try the stereoscopic PVR plugin, maybe that's the next step. Can anyone else give us a hand? Is anyone else interested in this? The models look absolutely beautiful considering the technology at the time of their creation. below is a screenshot of my 3ds max window, showing the 2d mesh which should, when we are done, be 3d.
## Post #3
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2011-12-02T02:23:09+00:00
- Post Title: NullDC Dreamcast Model ripping, game: Project Justice

Have you tried using another emulator? Or is it just because of how the DC does things, i.e. like in the PS2?
## Post #4
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-12-02T03:04:48+00:00
- Post Title: NullDC Dreamcast Model ripping, game: Project Justice

Try using the drkpvr_lwr_stereo3dmod.
[http://devilmaster.altervista.org/dcutils.html](http://devilmaster.altervista.org/dcutils.html)
This is inaccurate.
## Post #5
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2011-12-02T05:06:43+00:00
- Post Title: NullDC Dreamcast Model ripping, game: Project Justice

@huckleberrypie:

I think it's just how DC does it, as you said, the same as ps2. 

@alon:
Thanks for the link, I will give it a try.
## Post #6
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-12-02T08:47:52+00:00
- Post Title: NullDC Dreamcast Model ripping, game: Project Justice

It is requires slight modification(X-axis=Red Line).
Here is the result.
## Post #7
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2011-12-02T14:19:15+00:00
- Post Title: NullDC Dreamcast Model ripping, game: Project Justice

?!

You pulled it off?!

YES!!!!

SWEET. I take it you used the stereoscopic plugin you mentioned... Now the only thing to do is see if the model contains UV mapping for the textures. This is freaking awesome, dude... I appreciate your help in making this project a reaility
## Post #8
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2011-12-03T19:09:25+00:00
- Post Title: NullDC Dreamcast Model ripping, game: Project Justice

Well I tested out the drkpvr_lwr_stereo3dmod with NullDC 1.6 and 3DRipperDX v1.8.1 with limited success. The games I tested were Star Wars Jedi Power Battles, Hydro Thunder, and Border Down. I was able to capture textures 100% of the time but the meshes were a bit messy. I had the most success getting geometry from Jedi Power Battles but the geometry is missing most of the back faces.  It seems the emulator culls the faces when rendering. I'm not sure how to overcome this problem. If there is a way to overcome this issue ripping meshes from Dreamcast games would be easy, so long as the emulator can run the game.

Update: It seems that the culling of faces is entirely controlled by each games' rendering engine. It has nothing to do with the emulator itself. Some games aggressively cull faces while others do not. I just tested out Star Wars Episode One Racer and was able to capture full scenes without much culling. It simply depends on the game engine. If we could find a way to disable culling in the game that would fix the problem. This is not very likely to happen and I'm not going to hold my breath for it.
## Post #9
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2011-12-04T15:15:46+00:00
- Post Title: NullDC Dreamcast Model ripping, game: Project Justice

Hmmmm.... well, the truth is, if a model is missing faces, there is no easy way to repair them. Most 3d modeling programs don't have a function for adding missing polygons, and even if they did, those new polygons wouldn't have the proper UV mapping for the textures. There is a way to work around this though: import the model into Google Sketchup, and simply create polygons where you need them (If you google it, there are tutorials on how to import 3d models into Sketchup with textures intact), then, using a texturing tool (again, google is the best source for this) you can assign UV mapping to the new polygons once you export the repaired model. It can be a real pain, but it may be the only way. Although, Rival Schools 2 didn't cull back faces... I don't think it is the emulator, it might be a game-to-game thing.
