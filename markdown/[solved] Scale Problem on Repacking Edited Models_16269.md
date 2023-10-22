## Post #1
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2017-05-10T08:29:39+00:00
- Post Title: [solved] Scale Problem on Repacking Edited Models

Hello everyone,

This is more of a question on the common techniques in dealing with repacking edited models. First off, we all know that each 3D modelling software might use different default scale.

For example:

 I export the models to FBX through Noesis. (game character with bones and weights)
 I import it into 3DSmax. (the advance import options shows automatic scale or mm,cm,m...etc... I chose "1.0" cm)
 I make really small adjustments to the model, no scale changes.
 I export the model from 3DSmax to FBX again. (the advance export options show automatic scale or mm,cm,m...etc... I chose automatic "1.0" )
 I then import it into Noesis then export it back to the original game file.
 I enter the game and the objects become too small and sometimes if I choose different scale on import & export it becomes too big.

So, what are the common approaches to dealing with this? 

Facts about the game I'm modding:
- The game uses DirectX9.
- It's a Korean MMORPG. (maybe someone knows the common scale unit used by korean developers/modellers)
- It was made in 2001.

Any tips or ideas?
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-05-10T16:14:35+00:00
- Post Title: [solved] Scale Problem on Repacking Edited Models

Don't use FBX. Its a crap format and always had scale problems.
## Post #3
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2017-05-10T16:34:03+00:00
- Post Title: [solved] Scale Problem on Repacking Edited Models

Any suggestions?
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-05-10T16:45:07+00:00
- Post Title: [solved] Scale Problem on Repacking Edited Models

i'm not using max so dont know which formats it can import
## Post #5
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2017-05-10T16:49:14+00:00
- Post Title: [solved] Scale Problem on Repacking Edited Models

For blender perhaps?
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-05-10T16:52:42+00:00
- Post Title: [solved] Scale Problem on Repacking Edited Models

try collada dae
