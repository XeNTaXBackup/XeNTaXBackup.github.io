## Post #1
- Username: zerenium
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 29, 2018 10:32 am
- Post datetime: 2020-06-04T14:42:32+00:00
- Post Title: Reimporting 3D models edited in blender

Hi all,

I'm looking for someone to nudge me in the right direction here. I've used model researcher to extract .obj files and have edited those models in Blender. I'd ultimately like to reimport this new model into the game. How would I go about doing this? I've tried looking into converting vertices into hex (essentially reversing what model researcher does) but I haven't had any luck.

Thank you!


EDIT:
I actually figured out how the hex values are converted to vertices.

For example, the vertex 0.7227 converts to 00 B6.
00 indicates the number before the decimal is 0. (if this were 255 then the value would be negative, if it were 254 then -1, etc.)
B6 to decimal is 185. 185/256 = .7227.

I'm going to start working on a script that converts vertices to the hex values so hopeful I can just replace it in the original file and reimport using quickbms.

Please let me know if this won't work or if there's already a program that can do this! Thanks!
