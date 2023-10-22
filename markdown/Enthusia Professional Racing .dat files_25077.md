## Post #1
- Username: markerfede
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 15, 2019 9:19 pm
- Post datetime: 2022-02-21T20:07:50+00:00
- Post Title: Enthusia Professional Racing .dat files

I have been trying to find a way to extract the .dat files from a Konami game, Enthusia Professional Racing. I'm trying to find a way of getting access to the 3d models that the game uses (cars in particular). I have tried other ways of getting the models like PCSX2's capture feature and other utilities for capturing the render. However none of these methods have worked properly. Even when setting up a separate PCSX2 0.9.8 instance with the right GS settings and set up it with PS2 model converter produced badly skewed and unusable results in 3ds Max.  

With all of these attempts not working, I figure I may be able to access them from the files directly. So I used a bms script that extracted the two of the larger and what I'm guessing are bin files that contain music, video and geometry. Either D000.BIN or D001.BIN file unpacked are the same sized .dat files. Searching around I found and have tried using the Konami DAT Utility program. However, it doesn't work with these kinds of .dat files: "This is not a compatible dat file".

Would there be a way to figure out how to extract the .dat files from this game at all? I'm trying to find a way to extract these 3d models. I have the files from the .bin already extracted. I uploaded a sample folder of what I can assume is geometry or something large enough to take up space on a disc like that. But seeing as I can't read these files properly it is just a guess for now... unless someone can help me along?  

SAMPLE FOLDER with link:
Enthusia - Professional Racing (USA).iso/ENTHUSIA/D000.bin/d000/1000fc87/0000007e/
0000026a.csl (564 KB)
0000026b.csl (1 KB)
0000026c.csl (6 KB)
0000026d.csl (1 KB)
0000026e.csl (3 KB)
0000026f.csl (45 KB)
00000267.dat (8478 KB) *What I'm assuming may be the file of interest?
00000268.pos (1 KB)
00000269.dat (1 KB)
00000270.pvc (183 KB)
00000271.svd (7 KB)

[https://drive.google.com/file/d/1EH6P5r ... sp=sharing](https://drive.google.com/file/d/1EH6P5rNXCf-czdiWy1G3C0gnEojxhXUx/view?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-21T20:20:05+00:00
- Post Title: Enthusia Professional Racing .dat files

Found some assumed point clouds with 59 vertices each in 00000267.dat. But I don't like to fiddle around any more.
(Looking at this thread you may understand, why:
[viewtopic.php?f=16&t=23973&p=174965&hilit=vif#p174965](https://forum.xentax.com/viewtopic.php?f=16&t=23973&p=174965&hilit=vif#p174965))
.



Konami.png (8.34 KiB) Viewed 324 times


There's 11713 so called "Vif tags", iirc. So have fun.

If the format is more like this one
[viewtopic.php?f=16&t=24738&p=179658&hilit=vif#p179618](https://forum.xentax.com/viewtopic.php?f=16&t=24738&p=179658&hilit=vif#p179618)
I could give it a try.
## Post #3
- Username: markerfede
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 15, 2019 9:19 pm
- Post datetime: 2022-02-21T21:03:03+00:00
- Post Title: Enthusia Professional Racing .dat files

What a quick response! Ah, that's a shame though. It could be that particular file... there are quite a few that I have but they might be the same. They are all around the same size too.

I could not find any .LZ (LZSS) files, unfortunately. I don't think this game uses them. I'm sure these are the right files though... being the only sizable files in this .iso.

I'm going to upload the extracted D000.BIN here if anyone gets curious enough:
[https://drive.google.com/file/d/1EH6P5r ... sp=sharing](https://drive.google.com/file/d/1EH6P5rNXCf-czdiWy1G3C0gnEojxhXUx/view?usp=sharing)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-22T13:37:13+00:00
- Post Title: Enthusia Professional Racing .dat files

Gathered some of the previous mentioned point clouds - problem is, vertices are too similar, my best guess would be: it's an array of bounding boxes  

# H2O parameter file: 00000267.dat_0064.h2o      (H_Float: 0)
# 0x63f50: verts= 60
v -126.233009 360.029022 -2481.398193
v -126.586006 359.666016 -2477.878174

v -121.733009 360.068024 -2480.574219
v -122.313004 359.698029 -2477.349121

v -121.733009 360.068024 -2480.574219
v -122.313004 359.698029 -2477.349121

v -117.277008 360.108032 -2479.595215
v -118.088005 359.728027 -2476.490234

v -117.277008 360.108032 -2479.595215
v -118.088005 359.728027 -2476.490234

v -112.877007 360.155029 -2478.370117
v -113.938004 359.764008 -2475.303223

v -112.877007 360.155029 -2478.370117
v -113.938004 359.764008 -2475.303223

v -108.573006 360.209015 -2476.813232
v -109.887009 359.804016 -2473.796143
v -108.573006 360.209015 -2476.813232
v -109.887009 359.804016 -2473.796143
v -104.396004 360.285004 -2474.922119
v -105.978004 359.866028 -2471.943115
v -104.396004 360.285004 -2474.922119
v -105.978004 359.866028 -2471.943115
v -100.376007 360.381012 -2472.702148
v -102.202003 359.949005 -2469.827148
v -96.543007 360.483032 -2470.157227
v -98.564003 360.042023 -2467.462158
v -96.543007 360.483032 -2470.157227
v -98.564003 360.042023 -2467.462158
v -94.708008 360.533020 -2468.766113
v -96.840004 360.089020 -2466.143066
v -94.708008 360.533020 -2468.766113
v -96.840004 360.089020 -2466.143066
v -91.221001 360.645020 -2465.755127
v -93.622002 360.198029 -2463.229004
v -88.041008 360.776031 -2462.422119
v -90.532005 360.330017 -2460.178223
v -88.041008 360.776031 -2462.422119
v -90.532005 360.330017 -2460.178223
v -85.186005 360.920013 -2458.813232
v -87.688004 360.476013 -2456.888184
v -85.186005 360.920013 -2458.813232
v -87.688004 360.476013 -2456.888184
v -82.625008 361.074005 -2455.000000
v -85.173004 360.633026 -2453.338135
v -82.625008 361.074005 -2455.000000
v -85.173004 360.633026 -2453.338135
...
## Post #5
- Username: markerfede
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 15, 2019 9:19 pm
- Post datetime: 2022-02-22T15:59:27+00:00
- Post Title: Enthusia Professional Racing .dat files

Are other games as difficult as this? I'm assuming just Konami developed games.   I wish I could help in some way... I feel kind of bad for sending you down a rabbit hole haha.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-23T11:20:24+00:00
- Post Title: Enthusia Professional Racing .dat files

yeah, big hole, 300k vertices, maybe some offset to be subtracted:
.



300k_vertices.png (6.05 KiB) Viewed 269 times
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-23T13:12:20+00:00
- Post Title: Enthusia Professional Racing .dat files

> Reply from shakotay2 ↑Tue Feb 22, 2022 9:37 pm at Tue Feb 22, 2022 9:37 pm
>
> 
00000267.dat
if load (00000267.dat) as point cloud.

I chose at random file (00000d77.dat).
and loads too as point cloud >> offset 8272 and vert count 22000
look like it is 3 cars and wheels 
[sss.png](https://xentaxbackup.github.io/file/21850_sss.png)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-23T13:28:50+00:00
- Post Title: Enthusia Professional Racing .dat files

yeah, see, missed to unclipp in blender (I have no idea, why this isn't 'default')
.



track.png (41.37 KiB) Viewed 261 times
## Post #9
- Username: markerfede
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 15, 2019 9:19 pm
- Post datetime: 2022-02-23T13:45:35+00:00
- Post Title: Enthusia Professional Racing .dat files

Woah so much progress.   What kind of process are you all using to do this? What programs should I download and give this a try?
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-23T14:44:38+00:00
- Post Title: Enthusia Professional Racing .dat files

you might try this if you're unpatient. (Or wait for Durik.)
.


 Make_obj-Konami_dat.zip
typos corrected (58.86 KiB) Downloaded 18 times


You'll need to download hex2obj zip for it (see link in my sig) and the process involves use of a .py script to load 11k submeshes into blender.
(surely a good idea to "remove doubles" in blender)

After execution of the script in a blender text window switch clipping (ctrl-N, Clip End=100000 in blender versions < 2.80)
## Post #11
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-23T19:32:13+00:00
- Post Title: Enthusia Professional Racing .dat files

> Reply from shakotay2 ↑Wed Feb 23, 2022 10:44 pm at Wed Feb 23, 2022 10:44 pm
>
> 
(Or wait for Durik.)
 
(submesh search by leading bytes)
(header "50 43 00 02" its car?)

(I don't think I will continue)
to find all the cars you can use my script(click up arrow):

> Reply from Durik256 ↑Thu Jan 27, 2022 8:10 am at Thu Jan 27, 2022 8:10 am
>
> 
you can also use this script to rename all files that have a head "50 43 00 02".
for example, in (.rip_mesh).
replacing <<data.find('[MeshSerializer_v1.40]'.encode())>> with <<data.find(b'\x50\x43\x00\x02')>> inside script.
[fmt_EPRacing.zip](https://xentaxbackup.github.io/file/21853_fmt_EPRacing.zip)
## Post #12
- Username: markerfede
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 15, 2019 9:19 pm
- Post datetime: 2022-02-24T01:07:32+00:00
- Post Title: Enthusia Professional Racing .dat files

Your script managed to sort the files out into folders with the particular header. How do you view them? What's the viewer you're using? I placed the fmt_EPRacing 'plugin' you have there in the plugin folder of Neosis. It worked! Tried 00000d77.dat and I'm surprised the file size is quiet small considering. I suppose they are just point clouds.

I'm just trying to figure out how to take these points and turn them into a mesh... (I'm a bit slow)
## Post #13
- Username: markerfede
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 15, 2019 9:19 pm
- Post datetime: 2022-02-25T15:31:16+00:00
- Post Title: Enthusia Professional Racing .dat files

> Reply from shakotay2 ↑Tue Feb 22, 2022 9:37 pm at Tue Feb 22, 2022 9:37 pm
>
> 
Gathered some of the previous mentioned point clouds - problem is, vertices are too similar, my best guess would be: it's an array of bounding boxes  

# H2O parameter file: 00000267.dat_0064.h2o      (H_Float: 0)
# 0x63f50: verts= 60
v -126.233009 360.029022 -2481.398193
v -126.586006 359.666016 -2477.878174

v -121.733009 360.068024 -2480.574219
v -122.313004 359.698029 -2477.349121

v -121.733009 360.068024 -2480.574219
v -122.313004 359.698029 -2477.349121

v -117.277008 360.108032 -2479.595215
v -118.088005 359.728027 -2476.490234

v -117.277008 360.108032 -2479.595215
v -118.088005 359.728027 -2476.490234

v -112.877007 360.155029 -2478.370117
v -113.938004 359.764008 -2475.303223

v -112.877007 360.155029 -2478.370117
v -113.938004 359.764008 -2475.303223

v -108.573006 360.209015 -2476.813232
v -109.887009 359.804016 -2473.796143
v -108.573006 360.209015 -2476.813232
v -109.887009 359.804016 -2473.796143
v -104.396004 360.285004 -2474.922119
v -105.978004 359.866028 -2471.943115
v -104.396004 360.285004 -2474.922119
v -105.978004 359.866028 -2471.943115
v -100.376007 360.381012 -2472.702148
v -102.202003 359.949005 -2469.827148
v -96.543007 360.483032 -2470.157227
v -98.564003 360.042023 -2467.462158
v -96.543007 360.483032 -2470.157227
v -98.564003 360.042023 -2467.462158
v -94.708008 360.533020 -2468.766113
v -96.840004 360.089020 -2466.143066
v -94.708008 360.533020 -2468.766113
v -96.840004 360.089020 -2466.143066
v -91.221001 360.645020 -2465.755127
v -93.622002 360.198029 -2463.229004
v -88.041008 360.776031 -2462.422119
v -90.532005 360.330017 -2460.178223
v -88.041008 360.776031 -2462.422119
v -90.532005 360.330017 -2460.178223
v -85.186005 360.920013 -2458.813232
v -87.688004 360.476013 -2456.888184
v -85.186005 360.920013 -2458.813232
v -87.688004 360.476013 -2456.888184
v -82.625008 361.074005 -2455.000000
v -85.173004 360.633026 -2453.338135
v -82.625008 361.074005 -2455.000000
v -85.173004 360.633026 -2453.338135
...

Using Durik's method I notice that there are vertices that are in the same spot. I found that importing it into 3ds Max I can weld the verts that are in the same spot together. Would there be a way to then export the fixed mesh out and convert it into a mesh?
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-26T07:33:08+00:00
- Post Title: Enthusia Professional Racing .dat files

> Reply from markerfede ↑Fri Feb 25, 2022 11:31 pm at Fri Feb 25, 2022 11:31 pm
>
> Would there be a way to then export the fixed mesh outThere's exporters in 3dsmax, afair  , so why not? But I have no idea whether they support point clouds. Should be possible to use an ms script to export points.

> and convert it into a mesh?You mean, by adding face indices? Automatically created faces showed a mess. Might be a matter of grouping the vertices in some unknown way.

Running the sub meshes shown here

> Reply from shakotay2 ↑Tue Feb 22, 2022 4:20 am at Tue Feb 22, 2022 4:20 am
>
> 
with a point cloud skinner could reveal some results. (But there's thousands of those small sub meshes in the file I dealed with.)
