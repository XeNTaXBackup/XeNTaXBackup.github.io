## Post #1
- Username: QwePek
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 11, 2021 8:24 pm
- Post datetime: 2021-09-12T22:43:52+00:00
- Post Title: Scaleform Gfx SDK

Hi, 
I'm trying to get sprites from South Park The Stick Of Truth, and I know that they are stored in .gfx file format, I tried to turn them into .swf file, and then use SWF Decompiler, but all textures are in shade of red :/. So I read about opening those files with Scaleform Gfx SDK, but I can't find download link anywhere on the internet. 

Does anyone here have a download link to Scaleform Gfx SDK files?
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-13T09:21:18+00:00
- Post Title: Scaleform Gfx SDK

Did you try "Flash Decompiler Trillix"?
## Post #3
- Username: QwePek
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 11, 2021 8:24 pm
- Post datetime: 2021-09-13T12:53:07+00:00
- Post Title: Scaleform Gfx SDK

Yes, I have tried "Flash Decompiler Trillix" and the result was the same, all textures colored in shade of red. That's why I think that my only hope is Scaleform GFx SDK, but it disappeared from the internet
## Post #4
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2021-09-15T04:36:00+00:00
- Post Title: Scaleform Gfx SDK

Something to note, may not be directly helpful, and it's my personal opinion, which may be wrong

Scaleform was meant to use external atlases of textures. Among other things. The majority of games using scaleform I looked at did this. Unlikely they would be embedded... Not impossible, but unlikely...
As such, those red Sprite you see are meant to be placeholders. Those sprites in flash/as2/3 usually have some metadata, e.g. the name of the actual texture in the atlas/es.

Very likely you need to search for .tga/.dds/.png atlas texture files.

One final note: UDK (Unreal engine 3 developer kit) has some scaleform (sdk?) scripts you can look at, should you feel adventurous
