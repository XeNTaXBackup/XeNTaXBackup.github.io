## Post #1
- Username: Matteius
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 27, 2017 7:57 am
- Post datetime: 2017-11-27T01:16:41+00:00
- Post Title: FFXIV Model importing bitangent issue

Hello,

I'm helping to work on a C# FFXIV model importer,and for the life of me I've hit a brick wall. The code is in place for all the conversions and everything from Collada to the SE MDL files, and imports in the game, is working, rigged, etc. So, the engine has a (from what I understand not common) issue with bitangents due to the models being flipped. I've spent every waking hour for the last four days working on this, I've managed to identify the flipped faces,  and ofcourse split out the importing of the left and right bitangents, however, even when the bitangents appear correctly flipped, light is never handled right on the right side. Originally even with the flipping there was a noticeable seam anywhere two different models intersected. The left half this is now resolved,but the right I have tried a countless number of equations, rotations, flips, yet any time it looks correct on it's own, in game the lighting is wrong.

Does anyone have any insight into what I might be missing?

In this example I've replaced the male body top:
[https://giphy.com/embed/3o6fJ6y9sK2VUX6v3a](https://giphy.com/embed/3o6fJ6y9sK2VUX6v3a)
