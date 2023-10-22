## Post #1
- Username: JASGames
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 17, 2012 1:34 am
- Post datetime: 2012-07-16T18:38:40+00:00
- Post Title: Just Cause 2 Models for new Multiplayer Mod

Hi

I have written a .rbm exporter/importer for just cause 2 that converts to .obj files. Currently a game file can be converted and then opened with correct texture an uv's in a 3D program such as blender. A new model can then be exported to the game engine and viewed in the game. So far I have been able to successfully locate, vertex positions, vertex uv's, face indices and then textures for the model. 

The issue is that there are four an additional floats which I have can't work out what they might be and greatly affect the models shading. If i give them the same value when in the game the model from certain directions looks fully reflective while on another is shaded correctly. This made me think it was the vertex normal or environment mapping etc, however the values range from -60000 to 60000 each.

Here are a couple of examples:

30085.0      9541.219    64098.453     55353.27

10713.582  10713.582   -56277.523    56277.523

402.5078    402.5078    -27393.492    27393.492

I know that data means as much to you as it means to me, however I was wondering if anyone encounter normals being stored using four floats.

I had heard of them being able to be stored as just two floats however all four values have to be correct for it to render correctly in the game.

Here are some screens:








Just Wondering if someone could give me some hints on what this data might be, cause I have been stumped all day.

Thanks Jake
## Post #2
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-07-17T10:12:10+00:00
- Post Title: Just Cause 2 Models for new Multiplayer Mod

Seems good. What about skeletal models? Oh, and do you plan on making a 3DS Max script as well?
## Post #3
- Username: JASGames
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 17, 2012 1:34 am
- Post datetime: 2012-07-17T13:15:23+00:00
- Post Title: Just Cause 2 Models for new Multiplayer Mod

Right now I am focussing on vehicles but will hopefully get to characters soon, you can export from 3DS max using the .obj export option and then use the converter.
## Post #4
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-07-30T03:03:58+00:00
- Post Title: Just Cause 2 Models for new Multiplayer Mod

Anything new?
## Post #5
- Username: JASGames
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 17, 2012 1:34 am
- Post datetime: 2012-07-30T04:22:44+00:00
- Post Title: Just Cause 2 Models for new Multiplayer Mod

Nope still haven't got the shading to work correctly, I have tried about 2 or 3 different ways to store normals using 2 floats instead of 3 but still no luck. There are still a couple of other methods I haven't tried yet, but I still don't know if they are actually normals or some other important data. If I have a break through I'll let you know.
