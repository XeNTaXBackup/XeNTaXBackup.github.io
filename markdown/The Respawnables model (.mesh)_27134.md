## Post #1
- Username: KantoLemon
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 25, 2021 10:30 pm
- Post datetime: 2023-08-24T09:43:58+00:00
- Post Title: The Respawnables model (.mesh)

Hello folks, I am attempting to extract models and textures from an Android game called The Respawnables that was long delisted, since the game has got some really cool looking models. I recall someone trying to do this some time ago in Zenhax forums, and Luigi actually made a quickbms script to decompile the game archives (pakd, pakh format, the quickbms script is 8kap). After extracting the pakd and pakh files, I got a bunch of .mesh which I could not work out how to use.

If anyone experienced at converting meshes can lend me a hand, I will really appreciate it.

Thanks in advance.

(I figured out the textures thanks to piken, thread is under "Graphic file formats")

A sample mesh + texture:
[https://drive.google.com/file/d/1PTdvts ... sp=sharing](https://drive.google.com/file/d/1PTdvtsTqJswjQMBJQy5iiyCtdJnCjdxI/view?usp=sharing)

The whole archive extracted using quickbms script:
[https://drive.google.com/file/d/16OW2W9 ... sp=sharing](https://drive.google.com/file/d/16OW2W9g188hjEvrldlrvGbyLUchcDCue/view?usp=sharing)
## Post #2
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-09-03T06:11:40+00:00
- Post Title: The Respawnables model (.mesh)

> Reply from KantoLemon ↑Thu Aug 24, 2023 5:43 pm at Thu Aug 24, 2023 5:43 pm
>
> 
Hello folks, I am attempting to extract models and textures from an Android game called The Respawnables...

I found something with Model Researcher but I am not sure if it is correct:



I hope this helps but I don't know where faces data is...
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-09-03T16:45:33+00:00
- Post Title: The Respawnables model (.mesh)

Result using a point cloud skinner:
.



werebat_armor_pt_cloud_skinned.jpg (203.38 KiB) Viewed 247 times
## Post #4
- Username: KantoLemon
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 25, 2021 10:30 pm
- Post datetime: 2023-09-05T13:05:11+00:00
- Post Title: The Respawnables model (.mesh)

Hello again folks, thanks for the replies and help! Really appreciate it!

> Reply from roocker666 ↑Sun Sep 03, 2023 2:11 pm at Sun Sep 03, 2023 2:11 pm
>
> 
KantoLemon wrote: ↑Thu Aug 24, 2023 5:43 pm
Hello folks, I am attempting to extract models and textures from an Android game called The Respawnables...


I found something with Model Researcher but I am not sure if it is correct:



I hope this helps but I don't know where faces data is...

This does look correct! The vertices are definitely on point, I've tried looking for the faces, but can't seem to find it either. The UVs seem to resemble the texture too (attached below).

When extracting the file, there are actually a bunch of ".Obj" (yes, capital 'O'), one of each of the mesh. These Obj files cannot be opened directly in Blender, so I didn't think too much of it. There's also one for this mesh in particular, wonder if it contains something?

Link to ".Obj" for this mesh: [https://drive.google.com/file/d/1-cgij1 ... sp=sharing](https://drive.google.com/file/d/1-cgij1FNCQ4erQ2IXvv39NFLCh8SE6f1/view?usp=sharing)
[Capture.JPG](https://xentaxbackup.github.io/file/24312_Capture.JPG)
## Post #5
- Username: KantoLemon
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 25, 2021 10:30 pm
- Post datetime: 2023-09-05T13:05:39+00:00
- Post Title: The Respawnables model (.mesh)

> Reply from shakotay2 ↑Mon Sep 04, 2023 12:45 am at Mon Sep 04, 2023 12:45 am
>
> 
Result using a point cloud skinner:
.
werebat_armor_pt_cloud_skinned.jpg

Thanks for the response, didn't know such a thing existed, though the result doesn't look right
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-09-05T15:40:53+00:00
- Post Title: The Respawnables model (.mesh)

> Reply from KantoLemon ↑Tue Sep 05, 2023 9:05 pm at Tue Sep 05, 2023 9:05 pm
>
> 

..., though the result doesn't look rightIt covers about 80% of the faces. So what do you expect? Really. 

(You'll need to delete extra faces, of course. But that's not my job.  )
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-09-08T07:23:34+00:00
- Post Title: The Respawnables model (.mesh)

Using AXE with decoded indices (first submesh):



mesh.png (127.48 KiB) Viewed 192 times



Python code to decode the indices:

```

fp = open('shooter_male_werebat_shooter_male_werebat.Mesh', 'rb')
fp.seek(0x1328)
idxCount = 0x2148
data = fp.read(idxCount*2)
idxList = list(struct.unpack('<%dh'%idxCount, data))
for i in range(1, idxCount):
    idxList[i] += idxList[i-1]
fp.close()

fp = open('idxData', 'wb')
data2 = struct.pack('<%dh'%idxCount, *idxList)
fp.write(data2)
fp.close()

```
## Post #8
- Username: KantoLemon
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 25, 2021 10:30 pm
- Post datetime: 2023-09-11T10:20:19+00:00
- Post Title: The Respawnables model (.mesh)

> Reply from Bigchillghost ↑Fri Sep 08, 2023 3:23 pm at Fri Sep 08, 2023 3:23 pm
>
> 
Using AXE with decoded indices (first submesh):
mesh.png

Python code to decode the indices:
Code: Select allimport struct

fp = open('shooter_male_werebat_shooter_male_werebat.Mesh', 'rb')
fp.seek(0x1328)
idxCount = 0x2148
data = fp.read(idxCount*2)
idxList = list(struct.unpack('<%dh'%idxCount, data))
for i in range(1, idxCount):
    idxList[i] += idxList[i-1]
fp.close()

fp = open('idxData', 'wb')
data2 = struct.pack('<%dh'%idxCount, *idxList)
fp.write(data2)
fp.close()
Holy smokes! Thank you so much for the program, and showing that it's possible! Now to spend some time learning how it works...
## Post #9
- Username: KantoLemon
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 25, 2021 10:30 pm
- Post datetime: 2023-09-13T04:35:22+00:00
- Post Title: The Respawnables model (.mesh)

Update:
Did it! All thanks to the good folks around here! (Especially Bigchillghost, awesome program!) Work here is done manually (looking through hex to find offsets), but works flawlessly. Not that I'm knowledgeable enough to automate the process, but it's super nice when your efforts are fruitful



Capture.JPG (106.33 KiB) Viewed 116 times
## Post #10
- Username: 2012Z
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Mar 12, 2012 3:31 am
- Post datetime: 2023-09-14T14:20:20+00:00
- Post Title: The Respawnables model (.mesh)

Hello, do you have a tutorial on how you get this mesh on AXE? Also, were you get that idx data?
## Post #11
- Username: KantoLemon
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 25, 2021 10:30 pm
- Post datetime: 2023-09-14T19:06:30+00:00
- Post Title: The Respawnables model (.mesh)

Look for where data starts, can't really teach you this, it's better to learn from experience reading the mesh in hex. But so far looking for positions and texcoords are pretty easy. 

Try to look for the idxCount value in the sample mesh file (remember to use little endian, so it goes 48 21), it will give you a hint on where to look for the count for other meshes. Vertices count is also in there for sanity check.
## Post #12
- Username: 2012Z
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Mar 12, 2012 3:31 am
- Post datetime: 2023-09-15T05:57:25+00:00
- Post Title: The Respawnables model (.mesh)

ohh. bummer. thanks anyway.
