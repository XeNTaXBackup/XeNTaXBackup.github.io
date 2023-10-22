## Post #1
- Username: modelsarequitenice
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Dec 24, 2018 10:19 am
- Post datetime: 2018-12-24T03:53:39+00:00
- Post Title: gameplay3d format .gpb

Hi there, I'm wondering if anyone can figure out this format using hex2obj or something similar (not worried about UV's), I have tried so far and can't figure out the correct values. Gameplay3d is quite common in chinese apps. Here is a link to an example file -  [http://www.mediafire.com/file/lxkvycsjh ... t.rar/file](http://www.mediafire.com/file/lxkvycsjhxazh1y/heat.rar/file)

Any ideas to point in the right direction would be appreciated.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-24T11:16:06+00:00
- Post Title: gameplay3d format .gpb

format is a little bit tricky because you might think of big endian data at a first glance, but isn't:



heat-gpb.png (149.72 KiB) Viewed 108 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-25T13:59:30+00:00
- Post Title: gameplay3d format .gpb

FVFsize may be 64, too:



gpb-FVFsize 64.png (97.91 KiB) Viewed 88 times
## Post #4
- Username: modelsarequitenice
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Dec 24, 2018 10:19 am
- Post datetime: 2018-12-26T07:13:08+00:00
- Post Title: gameplay3d format .gpb

> Reply from shakotay2
>
> FVFsize may be 64, too:
gpb-FVFsize 64.png

Thank you, a few questions. May I ask how you found the vertices start address for this one, In your hex2obj tut is shows how to calculate for seq, or is it the same for vb? And how come the bottom part of step 2 is greyed out for you? And finally, in files where there are multiple models inside - (I believe that one has multiple models but you only extracted one part for example 2018ca, and 292bcc) is there a way with hex2obj to extract the other parts and maintain the correct scale. It should resemble a robot head
thanks again for your help
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-12-26T13:36:45+00:00
- Post Title: gameplay3d format .gpb

> Reply from modelsarequitenice
>
> May I ask how you found the vertices start address for this oneAfter you have the face indices blocks, you get the vertex count. assumed vertex start address: face_indices_startaddress - vertexcount x FVFsize,
is about 0x297F, then some trial and error and you're done.

> In your hex2obj tut is shows how to calculate for seq, or is it the same for vb?'seq' is obsolete; you can use 'vb' for any format; if it's sequential with floats use 'vb' with a FVFsize of 12.

> And how come the bottom part of step 2 is greyed out for you?Should be greyed out for UVpos!=99.
If it's equal to 99 uvs are assumed to be in a separate block (with uv start address and size UVB).
There's a small bug with unfinished 0.24e though; toggle 'VB' button to "ungrey" the mentioned editbox.

> And finally, in files where there are multiple models inside - (I believe that one has multiple models but you only extracted one partI always do one submesh only, leaving the rest to the customers.  
You should write code to get multiple submeshes (see my Make_obj project with C source).

> is there a way with hex2obj to extract the other partsWouldn't know why not; but too busy atm. Simply do binary a search for 000001000200, it's contained 31 times.



otherSubmesh.jpg (85.05 KiB) Viewed 66 times



> and maintain the correct scale.dunno what the correct scale is; I usually adjust it manually in blender.
## Post #6
- Username: modelsarequitenice
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Dec 24, 2018 10:19 am
- Post datetime: 2018-12-26T22:12:25+00:00
- Post Title: gameplay3d format .gpb

You are amazing! Thank you so much for the explanation, especially about finding the vert start address. Finally starting to get the different pieces
