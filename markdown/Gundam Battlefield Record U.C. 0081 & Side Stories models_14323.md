## Post #1
- Username: ByStander23
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun May 08, 2016 2:31 pm
- Post datetime: 2016-05-08T07:28:02+00:00
- Post Title: Gundam Battlefield Record U.C. 0081 & Side Stories models

Hello, i would like if someone could make a noesis or bms script to convert to .obj or see the model files for these 2 games.
No need for textures, bones or animations, only the models.
I saw a similar post only for gundam side stories but i really don't know anything about hex nor i expect to understand it(no patience at looking for random numbers, sorry).

Here's all the model files for each game:

Gundam Side Stories(.BIN files)
[http://www.mediafire.com/download/4sc70l0j3ta1y5a/1.rar](http://www.mediafire.com/download/4sc70l0j3ta1y5a/1.rar)

M.S.Battlefield Record U.C. 0081(.fpk/epk files)
[http://www.mediafire.com/download/4z15th799gb7ctc/2.rar](http://www.mediafire.com/download/4z15th799gb7ctc/2.rar)

It would be really appreciated if someone could decompress these files.
Thank you for your time.

Edit5/13/16:

Szkaradek123 already made a blender import plugin, thank you Szkaradek123 very much.
## Post #2
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2016-05-12T00:51:42+00:00
- Post Title: Gundam Battlefield Record U.C. 0081 & Side Stories models

Here is Gundam Side Stories file format by Szkaradek123

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
## Post #3
- Username: Strife1989
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jan 12, 2012 9:52 pm
- Post datetime: 2016-05-15T11:01:23+00:00
- Post Title: Gundam Battlefield Record U.C. 0081 & Side Stories models

Can someone rip the textures from the texture.bin files ?
## Post #4
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2016-05-15T15:37:38+00:00
- Post Title: Gundam Battlefield Record U.C. 0081 & Side Stories models

> Reply from Strife1989
>
> Can someone rip the textures from the texture.bin files ?
Here[viewtopic.php?p=118648#p118648](http://forum.xentax.com/viewtopic.php?p=118648#p118648)
