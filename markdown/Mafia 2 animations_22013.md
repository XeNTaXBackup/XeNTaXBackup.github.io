## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-04-15T10:18:53+00:00
- Post Title: Mafia 2 animations

Mafia 2 animation tool.
Works for both cutscenes and ingame animations.

Usage:
mafia2_anim <frameresource> <anim1> [anim2] ... [animN]

<frameresource> is a required file extracted from SDS by ExSDS tool, or any other tool for game archives.
<anim1>...[animN] are .animation2 files, at least one file is required

Tool will take skeleton for a particular character from <frameresource> and merge all the following animations onto it. This is needed because most ingame animations are split into 2 parts (top & bottom). Dont try merging animations that are not supposed to work together.

 

Example cutscene video with 2 characters:
[https://www.youtube.com/watch?v=3bCVsRjUGEk](https://www.youtube.com/watch?v=3bCVsRjUGEk)

Notes:
1. game is using linear interpolation, so after loading SMD, set it in your 3d editor, otherwise animations may not look correctly (especially for root motion, leading to "moonwalking" effects)
2. some animations have a few keys that don't correspond to keysframes. These will be merged to same keysframes.
3. some animations contain additional bones (like weapon attaches) which will not be exported, and print warnings.
4. additive animations (those with "DIFF" in their name etc) will be added to rest-pose on export, which will allow to watch them, but in most cases they will not look correct, because they are supposed to be added to other poses or animations in a different ways.
5. notification event lists will be output to console (sounds like footsteps and other events)
[mafia2_anim.rar](https://xentaxbackup.github.io/file/17930_mafia2_anim.rar)
## Post #2
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2020-04-23T03:25:45+00:00
- Post Title: Mafia 2 animations

Please explain an example
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-04-23T07:28:25+00:00
- Post Title: Mafia 2 animations

Example 1.

We have 000BDB0A.FrameResource extracted from vitod1.sds package (with Vito model)
Also we have sc_vito_lift_button.Animation2 cutscene animation file from distillery level.
The command to export this animation will be:

mafia2_anim 000BDB0A.FrameResource sc_vito_lift_button.Animation2

Example 2.

We have 000BDB0A.FrameResource extracted from vitod1.sds package (with Vito model)
Also we have animation files 00-CF_WALK_L-A.Animation2 & 00-CF_WALK_L-B.Animation2 from basic_anim.sds
These 2 animation files are lower and upper body animation parts which are designed to play together.
The command to export this animation will be:

mafia2_anim 000BDB0A.FrameResource 00-CF_WALK_L-A.Animation2 00-CF_WALK_L-B.Animation2
## Post #4
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2020-04-23T10:36:23+00:00
- Post Title: Mafia 2 animations

Thanks
## Post #5
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2021-02-08T07:13:33+00:00
- Post Title: Mafia 2 animations

> Reply from daemon1 ↑Thu Apr 23, 2020 3:28 pm at Thu Apr 23, 2020 3:28 pm
>
> 
Example 1.

We have 000BDB0A.FrameResource extracted from vitod1.sds package (with Vito model)
Also we have sc_vito_lift_button.Animation2 cutscene animation file from distillery level.
The command to export this animation will be:

mafia2_anim 000BDB0A.FrameResource sc_vito_lift_button.Animation2

Example 2.

We have 000BDB0A.FrameResource extracted from vitod1.sds package (with Vito model)
Also we have animation files 00-CF_WALK_L-A.Animation2 & 00-CF_WALK_L-B.Animation2 from basic_anim.sds
These 2 animation files are lower and upper body animation parts which are designed to play together.
The command to export this animation will be:

mafia2_anim 000BDB0A.FrameResource 00-CF_WALK_L-A.Animation2 00-CF_WALK_L-B.Animation2

hello where is the model ?
[mafia 2.png](https://xentaxbackup.github.io/file/19490_mafia 2.png)
## Post #6
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2021-02-08T07:17:19+00:00
- Post Title: Mafia 2 animations

> Reply from gamer1977 ↑Mon Feb 08, 2021 3:13 pm at Mon Feb 08, 2021 3:13 pm
>
> 
daemon1 wrote: ↑Thu Apr 23, 2020 3:28 pm
Example 1.

We have 000BDB0A.FrameResource extracted from vitod1.sds package (with Vito model)
Also we have sc_vito_lift_button.Animation2 cutscene animation file from distillery level.
The command to export this animation will be:

mafia2_anim 000BDB0A.FrameResource sc_vito_lift_button.Animation2

Example 2.

We have 000BDB0A.FrameResource extracted from vitod1.sds package (with Vito model)
Also we have animation files 00-CF_WALK_L-A.Animation2 & 00-CF_WALK_L-B.Animation2 from basic_anim.sds
These 2 animation files are lower and upper body animation parts which are designed to play together.
The command to export this animation will be:

mafia2_anim 000BDB0A.FrameResource 00-CF_WALK_L-A.Animation2 00-CF_WALK_L-B.Animation2


hello where is the model ?
[m.png](https://xentaxbackup.github.io/file/19491_m.png)
