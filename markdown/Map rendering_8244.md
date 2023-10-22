## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-10T07:16:21+00:00
- Post Title: Map rendering?

Some games store the entire map as a 3D model, but it probably isn't the most efficient way to do things.
I've seen games where the maps are constructed purely from tree algorithms, but those aren't too visually appealing either lol

What kind of techniques are used when rendering maps? Many times I look through map files I don't see anything that looks like a 3D model so it's probably using some set of algorithms to generate everything? And then just load up some map assets like a tree or a house or something I guess.
## Post #2
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2012-02-10T13:54:14+00:00
- Post Title: Map rendering?

From memory there's 3 main aproaches.
a) Heightmap based with various texturing means. In a lot of cases flat texture even. 
b) BSP, BSP with 3dmeshes.
c) made from 3dmesh segments so to speak. So the map isn't one entire 3dmesh but instead is made out of modular parts. This aproach is very typical for UE3 games. Though they can also use BSP
