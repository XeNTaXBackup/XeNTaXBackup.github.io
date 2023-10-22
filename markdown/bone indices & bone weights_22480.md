## Post #1
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2020-08-03T10:48:21+00:00
- Post Title: bone indices & bone weights

Hi,
I'm working on my noesis script and currently stuck at the last step: bone indices + weights. In the screenshots below, it seems like the binding is incorrect.


But in the vertice struct, those bytes are the only one I think that are bone indices and bone weights, following this struct:

```
byte	normal[4]
byte	boneId[4]
byte	weight[4]
float	position[3]
half	texcoord[2]

```


The file + my script: removed
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-08-03T14:13:12+00:00
- Post Title: bone indices & bone weights

Guess you'll get track of the problem as soon as you've found out why the ring finger of the right hand moves when the left arm moves:
.



ringfinger.jpg (38.13 KiB) Viewed 139 times
## Post #3
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2020-08-03T16:38:36+00:00
- Post Title: bone indices & bone weights

That problem is the reason I need help as is in the screenshot. Seems like all bone indices + weights in data are somehow wrong or my binding is not correct (I just read them straightforwardly without any complex step). Also in my screenshot, those two 'long' fingers seems like they were not binded to any bone. Since the skeleton is as same as your screenshot, I'm still thinking the issues are from original bone weights data .
## Post #4
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2020-08-03T20:16:40+00:00
- Post Title: bone indices & bone weights

you may have to remap bones. usually the rig/bones are stored in a way that the shaders can be loaded fast. means you have a maximum amount of bones that can be loaded into shader constants per drawcall. so.. you may have to figure out how many bones the engine loads per call, and then remap the rest to the next draw call and remap those again. it's a lil finicky tbh. but...
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-04T12:24:17+00:00
- Post Title: bone indices & bone weights

There're two bone index refference tables for submeshes before the vertices buffer.



indextbl.png (28.65 KiB) Viewed 104 times



A pretty much common workaround for per-byte bone index format.
## Post #6
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2020-08-04T13:09:02+00:00
- Post Title: bone indices & bone weights

yes. was just reading the same. this is not dummy data. there's also another table for the 48 bones. seems not related tho. and a bunch of more numbers and "vertex"counts and structures to add or shift around. finicky stuff.
## Post #7
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2020-08-04T18:47:32+00:00
- Post Title: bone indices & bone weights

Hi all, sorry didn't see the last 2 posts but I could figure out the same table like you guys mentioned  it worked, thanks for helping me, really appreciate it
