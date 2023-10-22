## Post #1
- Username: GoodDeva
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 20, 2019 8:57 am
- Post datetime: 2019-08-03T09:23:00+00:00
- Post Title: NeoX Engine animation data file format

Hello everyone

Recently I found a resource extractor tool of Netease NeoX game engine
GitHub Link Here: [https://github.com/zhouhang95/neox_tools](https://github.com/zhouhang95/neox_tools)
I extracted models and lots of .dat file, some of .dat file actually is animation data file of models.
Here is one example


After some struggles in the game's .so library I can determine the suffix name of these animation data files should be .sfx
However, although the starting section of these files are easy to determine that they are names of Animation and bones, the rest data are actually binary encoded.

Does anyone have idea of this file format and how to convert the animation data to other format like json or Unity AnimationClip file?
I attached some sfx files.


 sfx_examples.zip
(193.95 KiB) Downloaded 39 times


Thanks.
## Post #2
- Username: lenovotxwd
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 23, 2019 8:37 pm
- Post datetime: 2019-11-29T07:49:37+00:00
- Post Title: NeoX Engine animation data file format

I'm zhouhang95.
This game engine is the mixin of python and  C++.
The parse part is in python.

There are some thing about python part:
both in Chinese

this article have some hints.
[https://juejin.im/entry/58bacfec1b69e6006b1a9c65](https://juejin.im/entry/58bacfec1b69e6006b1a9c65)

and this repository readme
[https://github.com/YJBeetle/unnpk](https://github.com/YJBeetle/unnpk)
