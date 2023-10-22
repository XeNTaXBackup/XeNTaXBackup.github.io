## Post #1
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2015-12-26T09:45:06+00:00
- Post Title: PS3 BFMDL header

Hi,
I really want to know how to convert .bin to obj files from Gundam Battle Operation Next.

```
42 46 4D 44 4C 48 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
```

Here is the sample
[https://www.mediafire.com/?am0pkq5tjm7wspt](https://www.mediafire.com/?am0pkq5tjm7wspt)]
## Post #2
- Username: Shine
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 23, 2014 1:15 am
- Post datetime: 2015-12-27T09:54:00+00:00
- Post Title: PS3 BFMDL header

how do you extract those *_models.bin from game_cpk.sdat?
## Post #3
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2015-12-27T12:38:06+00:00
- Post Title: PS3 BFMDL header

> Reply from Shine
>
> how do you extract those *_models.bin from game_cpk.sdat?
I tried to use TrueAncestor EDAT Rebuilder
## Post #4
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2015-12-30T19:39:05+00:00
- Post Title: PS3 BFMDL header

Hope to find a response!
There are some more data[https://www.mediafire.com/?6gbvww6pua87vk5](https://www.mediafire.com/?6gbvww6pua87vk5)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-30T21:01:29+00:00
- Post Title: PS3 BFMDL header

using hex2obj (view link in my sig):



r00_00_3-fpk.jpg (160.58 KiB) Viewed 249 times
## Post #6
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2016-05-12T10:58:59+00:00
- Post Title: PS3 BFMDL header

```


bones
.....
offset 11984   BFMDLNODE
offset 12000   (1.0, 1.0, 1.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0)
offset 12048   (55 - bone parent ID, 57, -1, -1, -32768, 256, -1, -1)
offset 12064   (1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, -2.7999999523162842, 0.0, 1.0) - relative bone matrice (to parent bone)
offset 12128   (1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 2.2999999523162842, -5.0, -0.0, 1.0) - absolute bone matrice (to root bone)
offset 12192   BFMDLNODE
offset 12208   (1.0, 1.0, 1.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0)
offset 12256   (56, 58, -1, -1, -32768, 256, -1, -1)
offset 12272   (1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, -2.5999999046325684, 0.0, 1.0)
offset 12336   (1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 2.2999999523162842, -2.4000000953674316, -0.0, 1.0)
offset 12400   BFMDLNODE
offset 12416   (1.0, 1.0, 1.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0)
offset 12464   (57, 59, -1, -1, -32768, 256, -1, -1)
offset 12480   (1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, -1.2000000476837158, 1.3999999761581421, 1.0)
offset 12544   (1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 2.2999999523162842, -1.2000000476837158, -1.3999999761581421, 1.0)

.....

models

We have groups of submeshes called BFMDLMESH. It is used  to split meshes for LODs and collision meshes.

offset 15520   BFMDLMESH
offset 15536   (65535, 64, 0 - mesh ID from mesh list , 14 - count meshes from mesh list, 30, 0, 0, 64)
offset 15552   (-5.4198698997497559, 5.4198708534240723, -1.0809969902038574, 19.107189178466797, -5.0378251075744629, 5.5907959938049316, 20.632902145385742)
offset 15580   (224, 0, 0, 0)
offset 15584   BFMDLMESH
offset 15600   (65535, 67, 14, 14, 30, 60, 1, 67)
offset 15616   (-5.4198698997497559, 5.4198708534240723, -1.0809969902038574, 19.107189178466797, -5.078700065612793, 5.5907959938049316, 20.632902145385742)
offset 15644   (224, 0, 0, 0)
offset 15648   BFMDLMESH
offset 15664   (65535, 70, 28, 5, 20, 120, 2, 70)
offset 15680   (-5.4078149795532227, 5.4078149795532227, -0.009442061185836792, 18.997819900512695, -5.0117058753967285, 5.3677759170532227, 20.468870162963867)
offset 15708   (224, 0, 0, 0)

......

mesh list

offset 15712   BFMDLSUBMESH
offset 15728   (49220, 0, 0, 0, 5507 - type of vertex, 3584, 0, 0)
offset 15744   (-3.8009049892425537, 3.8009049892425537, 7.5199751853942871, 19.107189178466797, -5.0378251075744629, 5.5907959938049316)
offset 15768   (3151 - triangle count, 6787 - vertice count, 5632, 0)
offset 15776   (0 - offset to indice stream in *_vertex.bin file, 18944 - offset to vertice stream in *_vertex.bin file, 131075, 65536, 18950, 18954, 18962, 18944, 18944, 18944, 18944, 18944, 0, 18944, 18944, 0, 0, 0, 0, 0)
offset 15856   BFMDLSUBMESH
offset 15872   (49172, 0, 0, 0, 4099, 3584, 0, 0)
offset 15888   (-0.48192709684371948, 0.48192739486694336, 10.243570327758789, 11.235159873962402, 2.8643069267272949, 3.0743091106414795)
offset 15912   (28, 52, 4608, 0)
offset 15920   (168320, 168576, 1507327, -1, 168576, 168582, 168590, 168576, 168576, 168576, 168576, 168576, 127616, 127872, 168576, 0, 0, 0, 0, 0)

```
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-14T11:31:30+00:00
- Post Title: PS3 BFMDL header

> Reply from leyme
>
> agg_00_model.bin
[..]
offset 15768   3151 - triangle count, 6787 - vertice countI don't find these values in the file.

This list doesn't help very much without the suiting fpk file, does it?

Also I'm not very motivated to restart with this topic half a year later.
What about the seriousness you pursue your own request with?
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-05-14T16:52:49+00:00
- Post Title: PS3 BFMDL header

don't bother, Szkaradek123 already solve this days ago but OP didn't update the thread
[http://zenhax.com/viewtopic.php?p=13256#p13256](http://zenhax.com/viewtopic.php?p=13256#p13256)
