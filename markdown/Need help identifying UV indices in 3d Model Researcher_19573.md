## Post #1
- Username: zerenium
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 29, 2018 10:32 am
- Post datetime: 2019-03-01T05:47:42+00:00
- Post Title: Need help identifying UV indices in 3d Model Researcher

I'm trying to get these UVs to fit on a texture for a helmet in a game I'm modding. I've had no other problems with other models, as none have required UV indices. I think the helmets require UV indices, and the model researcher tutorial isn't very helpful in identifying these. The polygons are supposed to fit onto the curved white stripes. Any insights?

Here's the polygons with texture and UV parameters:



Here's what it looks like on the model with mesh parameters:



Here's the files I'm using:
Model file: [http://www.mediafire.com/file/38b30qn72 ... L.xpr/file](http://www.mediafire.com/file/38b30qn723qkfvw/HELMETFACEMASKSALL.xpr/file)
Texture file: [http://www.mediafire.com/file/5m06558oi ... t.tga/file](http://www.mediafire.com/file/5m06558oi5ko55m/PURDUE_HELMET_2007_GOLD_HELMETBAKED_COLout.tga/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-01T06:32:49+00:00
- Post Title: Need help identifying UV indices in 3d Model Researcher

What do you mean with " the helmets require UV indices"?
why not scale ty? 



scale_y_tex.png (46.46 KiB) Viewed 108 times
## Post #3
- Username: zerenium
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 29, 2018 10:32 am
- Post datetime: 2019-03-01T15:43:28+00:00
- Post Title: Need help identifying UV indices in 3d Model Researcher

How did you scale that? I'm using the free version of Model Researcher, but I'm assuming you did that in blender?

I used the model researcher guide to figure out all of this stuff. The guide used a cow as an example. When the UV map didn't align with the texture file, you could fill in UV indices to get everything looking right, but the guide didn't explain this very well. I'm hoping to edit and reinject these textures and I just wanted to use a model to make sure it all looks good. Scaling the Y is a good work around, thanks!
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-01T15:50:51+00:00
- Post Title: Need help identifying UV indices in 3d Model Researcher

import obj to blender; in UV/Image Editor 
a ctrl my <ENTER>
(select all, invert uvs vertically)

sy <ENTER>
(scale y)

> Reply from zerenium ↑Fri Mar 01, 2019 11:43 pm at Fri Mar 01, 2019 11:43 pm
>
> Scaling the Y is a good work around, thanks!It's no "workaround", it's THE solution.
## Post #5
- Username: zerenium
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 29, 2018 10:32 am
- Post datetime: 2019-03-01T16:27:01+00:00
- Post Title: Need help identifying UV indices in 3d Model Researcher

Noob question: How do you get the UV map visualized on top of the texture?

EDIT: Figured it out, never mind!
## Post #6
- Username: zerenium
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 29, 2018 10:32 am
- Post datetime: 2019-03-01T16:57:39+00:00
- Post Title: Need help identifying UV indices in 3d Model Researcher

It's looking great now! Thank you so much for your help!
