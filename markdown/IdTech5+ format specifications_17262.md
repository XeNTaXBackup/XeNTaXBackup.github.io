## Post #1
- Username: slowcoder
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 07, 2017 8:20 pm
- Post datetime: 2017-11-07T12:31:44+00:00
- Post Title: IdTech5+ format specifications

Hello. I'm playing around with rendering game models in opengl and i wonder if there is any format specification for the models and other data files for idtech5+ engine based games. I only
seen converters but i wish to try to load them on my own and render them   .
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-11-07T18:07:27+00:00
- Post Title: IdTech5+ format specifications

You're makin renderer only to render id tech 5 formats? By me that's a huge waste of time. I'll give you an advice. 
Create your own format that will suit your needs or use common formats, my shot is on FBX or Collada (but they have large filesizes).

If you're creatin ID5 model viewer, then there are some topics for importers, where you can create your own parser based of them, just use search button please. 
Anyway ID5 uses megatextures, Im not sure how vmtr textures are handled, but they seems to have some weird compression, daemon1 made some tool for them. Thing is that you will need to make custom renderer to balance memory management since those textures are really big and loading them directly to memory heap would be overkill. Best way would be, to make some 2d octtrees (ya know, like voxels) based on camera view cone and load them from disk when needed (like engine uses). In addition ID6 uses voxels, they work exactly like megatextures but in 3d space, in addition they look really cool, I hope more engines will switch back to voxels soon.

Anyway, there is thing called RAGE Toolkit, here are needed tools for anything, but they are somehow user unfriendly, especially level editor, megatexture painter have much better UI (it wouldn't hurt them, if they combined them together).
## Post #3
- Username: slowcoder
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 07, 2017 8:20 pm
- Post datetime: 2017-11-07T19:17:34+00:00
- Post Title: IdTech5+ format specifications

Thanks PredatorCZ, i'm installing the Rage Toolkit now. I already played around with FBX so i wished to display something new like Doom 2016
