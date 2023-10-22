## Post #1
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2018-03-23T21:40:53+00:00
- Post Title: Yakuza 6 (PS4) .gmd

I was wondering if someone could help with extracting models from Yakuza 6, the file structure is relatively similar to the previous games in the sense that they use .par packing and .gmds for characters, props and maps, however, since they are now using the Dragon Engine the previous tools do not work for .gmds. Textures can be extracted since pars can still be opened with the previous script though. Below are some samples I've provided for some characters and props, if any other samples are needed please let me know.

[https://mega.nz/#F!ZZlAFDiQ!sucGttq_tiAFF5B1HmButQ](https://mega.nz/#F!ZZlAFDiQ!sucGttq_tiAFF5B1HmButQ)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-25T12:44:42+00:00
- Post Title: Yakuza 6 (PS4) .gmd

some kind of quickhack using hex2obj (view link in my sig):



car0640_ambulance.jpg (180.9 KiB) Viewed 1204 times



(You'll need to insert some g sm_xx lines into the obj file, faces section, where xx=00..99 to understand how the submeshes work.)
## Post #3
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2018-03-31T22:02:20+00:00
- Post Title: Yakuza 6 (PS4) .gmd

> Reply from shakotay2
>
> some kind of quickhack using hex2obj (view link in my sig):
car0640_ambulance.jpg

(You'll need to insert some g sm_xx lines into the obj file, faces section, where xx=00..99 to understand how the submeshes work.)

Any chance an example can be done using one of the characters such as Kiryu?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-31T22:27:32+00:00
- Post Title: Yakuza 6 (PS4) .gmd

I wouldn't know why not.
You'll have to deal with the face indices and uvs, though:



c_am_kiryu_DEMO.jpg (98.6 KiB) Viewed 1161 times



well, that's funny, an FVF size of 72 is also an option with a vertex count of 7077.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-31T22:46:36+00:00
- Post Title: Yakuza 6 (PS4) .gmd

hands.jpg (73.84 KiB) Viewed 1159 times
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-04-01T19:50:37+00:00
- Post Title: Yakuza 6 (PS4) .gmd

I really get confused by the face indices (FIs) which seem to have some oddities such as the change between standard FIs and triangle strips.



c_am_kiryu_DEMO_.jpg (89.23 KiB) Viewed 1134 times



I also would have expected the next vertex start (corresponding to the changed FIs start address) to be located at 0x2A870 (0xFB40 + 36x3052 dec.) but it isn't.
## Post #7
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2018-06-02T01:22:39+00:00
- Post Title: Yakuza 6 (PS4) .gmd

[https://mega.nz/#!0QN0Bbab!sUfzAzBE_ade ... YQvXpyJjjU](https://mega.nz/#!0QN0Bbab!sUfzAzBE_adewKF4U4PhmTj0yWxEdPzWJYQvXpyJjjU)

Here's some character samples from Hokuto Ga Gotoku, it runs on the Kiwami/0/Ishin engine, however it may be using the same new format of .gmd as 6. It can't be opened by the current Blender script.
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-02T10:44:33+00:00
- Post Title: Yakuza 6 (PS4) .gmd

I got a nice point cloud, but no luck with the indices. File used : c_cc_kiryu.gmd



Still I was able to spot some offsets and counts, that I think will be helpful for people who want to give it a try. So first of all there are important offsets and entry counts right at the beginning. 



For example the red ones are indices start offset and number of indices. The green ones are offset to a table right before the vertex blocks and again number of entries.

The table that the green offset points to looks like this.



I think the most important stuff here is the count of the first entry which is actually the vertex count. Also there are byte lengths too, so byte length / entry count = vertex block length

With this you basically get all the data you need, but I am not sure how the indices are handled. I tried using triangle strips, but it came out pretty broken. Maybe someone can fix it.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-02T13:23:06+00:00
- Post Title: Yakuza 6 (PS4) .gmd

seems it's a matter of submeshing; you can extract ugly submeshes and fine ones, which need some combining:



c_cc_kiryu-gmd.jpg (233.76 KiB) Viewed 1038 times

(g submesh_x line every 1000 faces in the test.obj file)
(The tricky part would be where to place the g submesh_x lines exactly.)
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-03T14:50:58+00:00
- Post Title: Yakuza 6 (PS4) .gmd

I have just found out that Szkaradek's Yakuza 5 blender script actually works for these files too. Looks like they haven't changed the format. I haven't checked if the skeleton and vertex weights are okay, but at least the meshes are loaded fine. 



You can download it here : [viewtopic.php?p=118080#p118080](http://forum.xentax.com/viewtopic.php?p=118080#p118080) . Just change the endianness, and it works fine.
## Post #11
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2018-06-03T23:06:52+00:00
- Post Title: Yakuza 6 (PS4) .gmd

> Reply from akderebur
>
> I have just found out that Szkaradek's Yakuza 5 blender script actually works for these files too. Looks like they haven't changed the format. I haven't checked if the skeleton and vertex weights are okay, but at least the meshes are loaded fine. 



You can download it here : viewtopic.php?p=118080#p118080 . Just change the endianness, and it works fine.

I took a look at the models, looks like the UVs aren't working for the models. The models from 6 (and I presume Kiwami 2) can be extracted, however they also suffer from the same UV issue and the rigging seems to be completely broken.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-06-24T08:47:14+00:00
- Post Title: Yakuza 6 (PS4) .gmd

Yakuza 6/Kiwami 2/Hokuto ga Gotoku PS4 tools:

[viewtopic.php?f=16&t=18276](http://forum.xentax.com/viewtopic.php?f=16&t=18276)
## Post #13
- Username: bobcan
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 26, 2007 11:12 am
- Post datetime: 2018-06-25T19:31:44+00:00
- Post Title: Yakuza 6 (PS4) .gmd

> Reply from shakotay2
>
> The attachment hands.jpg is no longer available

How to open files in gmd  in Noesis 3.94

look at



[download/file.php?mode=view&id=14517](http://forum.xentax.com/download/file.php?mode=view&id=14517)
[3d01.jpg](https://xentaxbackup.github.io/file/14517_3d01.jpg)
