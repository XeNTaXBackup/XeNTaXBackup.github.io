## Post #1
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-11T03:12:07+00:00
- Post Title: WRC 7 .P3D models

I know I've already started a thread about this a while back, but that was when I attempted to use Ninja Ripper on the game in vain. Turns out that aluigi wrote a script for WRC 7's PKG file formats and that using it reveals a surprisingly good amount of content, all conveniently labelled.

That being said, the .P3D and .PTX files use RIFF as a container, but I figured there's more to it than just that. Maybe some of you 3D experts could figure out how to break this down so that we could port these cars to some other game easily.

Here are sample files I extracted using the BMS scripts mentioned above:
[https://www73.zippyshare.com/v/vcUnAAjj/file.html](https://www73.zippyshare.com/v/vcUnAAjj/file.html)
[https://www73.zippyshare.com/v/AauPpLjC/file.html](https://www73.zippyshare.com/v/AauPpLjC/file.html)

EDIT: I opened the P3D and PTX files using Riffpad and the nodes seem neatly laid out and labelled (vertex positions, vertex normals, tangents, vertex uvs, indices...). Then again I'm not an expert with deciphering them floats and vert positions so I'll leave those to whoever can understand them:
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-11T18:34:20+00:00
- Post Title: WRC 7 .P3D models

P3D is not too hard:



wheel_grav-P3D.png (142.69 KiB) Viewed 284 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-11T19:09:26+00:00
- Post Title: WRC 7 .P3D models

toyota_yaris, fst submesh:



toyota_yaris-P3D.png (124.37 KiB) Viewed 282 times
## Post #4
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-11T22:43:48+00:00
- Post Title: WRC 7 .P3D models

Great, now all we need is a maxscript to automate this. I am glad that Kylotonn didn't over-engineer things and relied on a familiar file structure. Heck, you could end up writing an exporter and somehow inject custom cars to the game.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-12T10:45:04+00:00
- Post Title: WRC 7 .P3D models

> Reply from huckleberrypie
>
> Great, now all we need is a maxscript to automate this.Doing it in 'C' is easier, imho. Maybe in the Make_obj project, but the positions of the parts must be corrected:



Toyota_Yaris-P3D-all.png (194.43 KiB) Viewed 268 times



> Heck, you could end up writing an exporter and somehow inject custom cars to the game.Exporters generally require a full format analysis, which is tedious task.
## Post #6
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-12T11:10:55+00:00
- Post Title: WRC 7 .P3D models

> Reply from shakotay2
>
> huckleberrypie wrote:Great, now all we need is a maxscript to automate this.Doing it in 'C' is easier, imho. Maybe in the Make_obj project, but the positions of the parts must be corrected:
Toyota_Yaris-P3D-all.png
Whichever is more convenient lol. I can presume that some of the nodes do contain pivot positions and they seem to denote part and dummy/bone names as well.
Heck, you could end up writing an exporter and somehow inject custom cars to the game.Exporters generally require a full format analysis, which is tedious task.
Yeah, I know there's certainly more to it than a stream of verts and tris in a RIFF container.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-12T13:34:09+00:00
- Post Title: WRC 7 .P3D models

Can you export any infos from Riffpad, or does it create a logfile?

I'm too lazy guessing those positon offsets from the P3D file:

# 0. 2a 6a 6a , NodsNoHeX, Root
# 1. b6 69 6a , NodsNoHeZ, D_Main
# 2. cc 78 2 , NodsNoHe^, Piston_FR
0.967096 0.028186 -0.252846 
-0.027130 0.999603 0.007665 
0.252961 -0.000553 0.967476 
-0.534624 -1.300303 0.664300 

# 3. 5a 78 2 , MeLiMesh:
# 4. c 78 2 , GeLiGeom
# 5. ec 77 2 , SGLiSuGe
# 6. 9c 78 2 , NodsNoHe^, Piston_RR
# 7. 2a 78 2 , MeLiMesh:
# 8. dc 77 2 , GeLiGeom
# 9. bc 77 2 , SGLiSuGe
# 10. 40 2d , NodsNoHe^, D_Exhaust
# 11. 78 , NodsNoHed, D_Exhaust_Flash
## Post #8
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-12T13:48:46+00:00
- Post Title: WRC 7 .P3D models

> Reply from shakotay2
>
> Can you export any infos from Riffpad, or does it create a logfile?

I'm too lazy guessing those positon offsets from the P3D file:

# 0. 2a 6a 6a , NodsNoHeX, Root
# 1. b6 69 6a , NodsNoHeZ, D_Main
# 2. cc 78 2 , NodsNoHe^, Piston_FR
0.967096 0.028186 -0.252846 
-0.027130 0.999603 0.007665 
0.252961 -0.000553 0.967476 
-0.534624 -1.300303 0.664300 

# 3. 5a 78 2 , MeLiMesh:
# 4. c 78 2 , GeLiGeom
# 5. ec 77 2 , SGLiSuGe
# 6. 9c 78 2 , NodsNoHe^, Piston_RR
# 7. 2a 78 2 , MeLiMesh:
# 8. dc 77 2 , GeLiGeom
# 9. bc 77 2 , SGLiSuGe
# 10. 40 2d , NodsNoHe^, D_Exhaust
# 11. 78 , NodsNoHed, D_Exhaust_Flash
Not sure, I'll have to take a look.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-12T20:12:29+00:00
- Post Title: WRC 7 .P3D models

the positioning problem seems to be solved, but my current problem is
there's 71 nodes but I've  got 67 names only



movingTheDoor.png (109.28 KiB) Viewed 253 times
## Post #10
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-12T23:20:05+00:00
- Post Title: WRC 7 .P3D models

> Reply from shakotay2
>
> the positioning problem seems to be solved, but my current problem is
there's 71 nodes but I've  got 67 names only
movingTheDoor.png
Did you take a look at similarly-sized nodes though? I bet some of them may have been named crypticly or not at all.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-13T19:13:27+00:00
- Post Title: WRC 7 .P3D models

I don't know  - I searched for "NodsNoHe" which is contained 67 times.

There's also MeLiMesh (43x), GeLiGeom (71), SGLiSuGe (71) but guess that's different things.

Maybe I should use PA__Head, SCENE___ENDI, PCPhHe and something else for the missing 4 nodes?

There's numbers for "NodsNoHe" but they seem to define the hierarchy.
## Post #12
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-13T23:50:26+00:00
- Post Title: WRC 7 .P3D models

> Reply from shakotay2
>
> I don't know  - I searched for "NodsNoHe" which is contained 67 times.

There's also MeLiMesh (43x), GeLiGeom (71), SGLiSuGe (71) but guess that's different things.

Maybe I should use PA__Head, SCENE___ENDI, PCPhHe and something else for the missing 4 nodes?

There's numbers for "NodsNoHe" but they seem to define the hierarchy.
Maybe, I dunno. I do hope someone would be kind enough to do a script which can at least parse these models completely. I also do have a few other sample files e.g. skinned models for characters and so on.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-14T13:58:13+00:00
- Post Title: WRC 7 .P3D models

> Reply from huckleberrypie
>
> I do hope someone would be kind enough to do a script which can at least parse these models completely.yeah, maybe.
Me, I'm finished with this: [https://www63.zippyshare.com/v/Deke91Lr/file.html](https://www63.zippyshare.com/v/Deke91Lr/file.html)



Toyota_Yaris-P3D-undone.png (120.77 KiB) Viewed 221 times


Too tired to solve stupid naming puzzles like this one.  Keep in mind that the names DON'T match the parts.

You may try your luck moving the remaining displaced parts to their correct positions.
(Dunno why the bumpers don't fit, even after swapping rear and front ones.)

Rotation might be required, too, for the wipers, for example.

(upps, forgot to care for uvs...)
## Post #14
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-14T14:50:06+00:00
- Post Title: WRC 7 .P3D models

> Reply from shakotay2
>
> huckleberrypie wrote:I do hope someone would be kind enough to do a script which can at least parse these models completely.yeah, maybe.
Me, I'm finished with this: https://www63.zippyshare.com/v/Deke91Lr/file.html
Toyota_Yaris-P3D-undone.png
Too tired to solve stupid naming puzzles like this one.  Keep in mind that the names DON'T match the parts.

You may try your luck moving the remaining displaced parts to their correct positions.
(Dunno why the bumpers don't fit, even after swapping rear and front ones.)

Rotation might be required, too, for the wipers, for example.

(upps, forgot to care for uvs...)
Yeah, apologies for inconveniencing you. I could've done the dirty deed myself but I kinda' find floating point numbers a bit complex to wrap my head around. One thing though: Could you point me as to where the face indices can be found or how to find them in the RIFF node? The verts themselves seem straightforward, and I might as well try to do the other cars myself to save you the trouble.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-14T15:13:22+00:00
- Post Title: WRC 7 .P3D models

> Reply from huckleberrypie
>
> Yeah, apologies for inconveniencing you.what?  

> One thing though: Could you point me as to where the face indices can be found or how to find them in the RIFF node?# FIs at: 20504 47e2c 5151c 58a6c 7ad66 a268e aef2e ef17a 1271aa 16bfa8 17eaa2 184234 19e726 1a956e 1afbc6 1b2704 1ba284 1de366 1f3cd8 1fc1b4 1fde28 20062e 20a08a 2120ec 215ce6 231730 242a16 24aa78 24e672 26a0bc 29235a 29ce14 29e630 29f936 2a0bbe 2b383a 2bdde2 41b8d6 4aa13e 4b506e 4c91dc 4d06b8 5250ca 541ede 579b28 583bfe 5898e0 58c85c 59278a 595a4e 59e38e 5a248e 5ab374 5af474 5b7426 5bc4ce 5c4fb4 5ca05c 5d78ae 5dd0e8 5e2886 5efe1a 5f5654 5fac4e 622dea 631396 641382 66e372 689ac0 68e0cc 6a2118

> I might as well try to do the other cars myself to save you the trouble.As soon as the naming riddle is solved I'd release the Make_obj project (with C source).

doors
22 -> 37, this means D_B_Wing_L_22 (which is assigned to the left door mesh  ) needs position offset of Door_L(_37) block in P3D file
26 -> 38
25 -> 37
29 -> 38

36 -> 43
j_bumper
 0 -> 10
 4 -> 11
 1 -> 12
 5 -> 13
exhaust
 2 -> 6 or 4?

Wiper
 3 -> 28 (29?)
 6 -> 16 (17?)
engine
30 -> 39

bumper_F
67 -> 64
70 -> 65
Hud
35 -> 43
36 -> 44


Anyways, here's the zip with uvs contained:
[https://www7.zippyshare.com/v/3yF3IYqF/file.html](https://www7.zippyshare.com/v/3yF3IYqF/file.html)

Some uvs may need some scaling (1.5?) but the selected one in the picture obviously not:



Toyota_Yaris-P3D-uvs.png (151.87 KiB) Viewed 217 times
## Post #16
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2018-11-14T17:16:32+00:00
- Post Title: Re: WRC 7 .P3D models

> Reply from huckleberrypie
>
> 
One thing though: Could you point me as to where the face indices can be found or how to find them in the RIFF node?

See the indx chunk on your picture.
## Post #17
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-15T01:13:45+00:00
- Post Title: Re: WRC 7 .P3D models

> Reply from shakotay2
>
> 
Anyways, here's the zip with uvs contained:
https://www7.zippyshare.com/v/3yF3IYqF/file.html

Some uvs may need some scaling (1.5?) but the selected one in the picture obviously not:
Toyota_Yaris-P3D-uvs.png
I presume the Makeobj thingy you mentioned is for Blender, yes?

> Reply from Karpati
>
> huckleberrypie wrote:
One thing though: Could you point me as to where the face indices can be found or how to find them in the RIFF node?

See the indx chunk on your picture.
Alright, noted.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-15T11:20:27+00:00
- Post Title: Re: WRC 7 .P3D models

> Reply from huckleberrypie
>
> I presume the Makeobj thingy you mentioned is for Blender, yes?Output is (one) wavefront .obj with submeshes (see zip file) so any 3D app should do.
## Post #19
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-15T11:48:52+00:00
- Post Title: Re: WRC 7 .P3D models

> Reply from shakotay2
>
> huckleberrypie wrote:I presume the Makeobj thingy you mentioned is for Blender, yes?Output is (one) wavefront .obj with submeshes (see zip file) so any 3D app should do.
Yeah I know that. I was actually referring to the Make_obj project with C source code.
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-15T18:44:00+00:00
- Post Title: Re: WRC 7 .P3D models

> Reply from huckleberrypie
>
> Yeah I know that. I was actually referring to the Make_obj project with C source code.The Make_obj project is not blender specific, it creates wavefront obj outputs which can be read by most 3D apps.

(But it wouldn't help you that much if you don't know 'C'.)
## Post #21
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-16T14:36:31+00:00
- Post Title: Re: WRC 7 .P3D models

> Reply from shakotay2
>
> huckleberrypie wrote:Yeah I know that. I was actually referring to the Make_obj project with C source code.The Make_obj project is not blender specific, it creates wavefront obj outputs which can be read by most 3D apps.

(But it wouldn't help you that much if you don't know 'C'.)
I see, so it's a standalone application then.
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-16T15:47:57+00:00
- Post Title: Re: WRC 7 .P3D models

btw, we'd need a decent Riff viewer with the ability to export the hierarchy.

The one I have stops at node 32 for some unkn reason:

```
 1.                                  D_Main
 2.                                          Piston_FR
 3.                                          Piston_RR
 4.                                          D_Exhaust
 5.                                                  D_Exhaust_Flash
 6.                                                  Exhaust
 7.                                          HUD_INT
 8.                                          J_Boot_L
 9.                                          J_Boot_R
10.                                         J_Bumper_BL
11.                                         J_Bumper_BR
12.                                         J_Bumper_FL
13.                                         J_Bumper_FR
14.                                         J_Hood_L
15.                                         J_Hood_R
16.                                         J_Wiper_L
17.                                                 Wiper_L
18.                                         Piston_FL
19.                                         Piston_RL
20.                                         D_B_Bumper_F
21.                                         D_B_Bumper_B
22.                                         D_B_Wing_L
23.                                         J_Wing_L
24.                                         J_Wing_R
25.                                         D_B_Wing_R
26.                                         D_Wheel_F
27.                                         D_Wheel_R
28.                                         J_Wiper_R
29.                                                 Wiper_R
30.                                         Body
31.                                                 Body_LOD1
```
## Post #23
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-16T23:54:55+00:00
- Post Title: Re: WRC 7 .P3D models

> Reply from shakotay2
>
> btw, we'd need a decent Riff viewer with the ability to export the hierarchy.

The one I have stops at node 32 for some unkn reason:
Code: Select all 0.                          Root
 1.                                  D_Main
 2.                                          Piston_FR
 3.                                          Piston_RR
 4.                                          D_Exhaust
 5.                                                  D_Exhaust_Flash
 6.                                                  Exhaust
 7.                                          HUD_INT
 8.                                          J_Boot_L
 9.                                          J_Boot_R
10.                                         J_Bumper_BL
11.                                         J_Bumper_BR
12.                                         J_Bumper_FL
13.                                         J_Bumper_FR
14.                                         J_Hood_L
15.                                         J_Hood_R
16.                                         J_Wiper_L
17.                                                 Wiper_L
18.                                         Piston_FL
19.                                         Piston_RL
20.                                         D_B_Bumper_F
21.                                         D_B_Bumper_B
22.                                         D_B_Wing_L
23.                                         J_Wing_L
24.                                         J_Wing_R
25.                                         D_B_Wing_R
26.                                         D_Wheel_F
27.                                         D_Wheel_R
28.                                         J_Wiper_R
29.                                                 Wiper_R
30.                                         Body
31.                                                 Body_LOD1
What RIFF viewer are you using? Mine's RIFFPad but that one seems pretty spartan and lacking certain features.
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-19T14:43:57+00:00
- Post Title: Re: WRC 7 .P3D models

It's Riffview, but it misses the 2nd half of the nodes, too bad. So I decided to get a C# project from the inet, RiffparserDemo which allowed me to create some position2node list manually. There's some things I don't understand so far, so for example 
J_Bumper_BL_10, J_Bumper_BR_11,  J_Bumper_FL_12, J_Bumper_FR_13 which don't appear in that list.
Also the wipers need the rotation applied.



Yaris-P3D(wip).jpg (197.42 KiB) Viewed 124 times

(node names are still messed up but I'm too lazy to care for hierarchy.)
## Post #25
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-20T13:39:09+00:00
- Post Title: Re: WRC 7 .P3D models

> Reply from shakotay2
>
> It's Riffview, but it misses the 2nd half of the nodes, too bad. So I decided to get a C# project from the inet, RiffparserDemo which allowed me to create some position2node list manually. There's some things I don't understand so far, so for example 
J_Bumper_BL_10, J_Bumper_BR_11,  J_Bumper_FL_12, J_Bumper_FR_13 which don't appear in that list.
Also the wipers need the rotation applied.
Yaris-P3D(wip).jpg(node names are still messed up but I'm too lazy to care for hierarchy.)
The missing nodes could probably account for why I don't seem to be getting the high-quality windscreen, rear window and a few others.
## Post #26
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-20T20:15:27+00:00
- Post Title: Re: WRC 7 .P3D models

Problem is that some NoHe names don't seem to be connected to a mesh because they are "joints"
such as J_Bumper_BL for example.

I really don't have the patience to crawl through that damned hierarchy to decide how to assign the meshes to the "real" mesh names. 
As for example D_Exhaust, D_Exhaust_Flash and Exhaust seem to share one mesh.

D_B_Wing_L, D_B_Wing_R, D_Wheel_F/ _R don't have vpos sections.

Astonishingly I found a name sorting algo that's totally simple (so it may give faulty results):

```
   cnt=0 ;
   for (i=0;i<SMcnt;i++) {              //
        while (addrList_arr[cnt]<Vaddr_arr[i]) cnt++ ;
        cnt-- ;
        strcpy(szSM_Name[i], szSM_Name[cnt]) ;
        fprintf( stream, "# %d %s\n", i, szSM_Name[i]) ;
   }
```

From mesh number 58 to 70 everything is labeled Wing_L_58, that's probably wrong so rename them, please.
Also some meshes remain clumped in the middle.
[https://www12.zippyshare.com/v/SPQrd8rr/file.html](https://www12.zippyshare.com/v/SPQrd8rr/file.html)
## Post #27
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-22T02:27:24+00:00
- Post Title: Re: WRC 7 .P3D models

> Reply from shakotay2
>
> Problem is that some NoHe names don't seem to be connected to a mesh because they are "joints"
such as J_Bumper_BL for example.

I really don't have the patience to crawl through that damned hierarchy to decide how to assign the meshes to the "real" mesh names. 
As for example D_Exhaust, D_Exhaust_Flash and Exhaust seem to share one mesh.

D_B_Wing_L, D_B_Wing_R, D_Wheel_F/ _R don't have vpos sections.

Astonishingly I found a name sorting algo that's totally simple (so it may give faulty results):
Code: Select all   // assign names
   cnt=0 ;
   for (i=0;i<SMcnt;i++) {              //
        while (addrList_arr[cnt]<Vaddr_arr[i]) cnt++ ;
        cnt-- ;
        strcpy(szSM_Name[i], szSM_Name[cnt]) ;
        fprintf( stream, "# %d %s\n", i, szSM_Name[i]) ;
   }
From mesh number 58 to 70 everything is labeled Wing_L_58, that's probably wrong so rename them, please.
Also some meshes remain clumped in the middle.
https://www12.zippyshare.com/v/SPQrd8rr/file.html
That's 'swell. Is there anything else that's needed to be done? Might send some more samples when I have the time. And no worries if you don't have the patience to do the rest of the format either, I'm not in a rush for things anyway.
## Post #28
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-24T11:53:07+00:00
- Post Title: Re: WRC 7 .P3D models

In regards to part positions, Szkaradek123 over at Zenhax mentioned about the NoHe node containing the necessary bone/skeleton stuff:
[https://zenhax.com/viewtopic.php?f=5&t=8872](https://zenhax.com/viewtopic.php?f=5&t=8872)
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-24T12:52:49+00:00
- Post Title: Re: WRC 7 .P3D models

Not nice, huckleberrypie, to let people work in parallel, on zenhax and here on xentax.  
I'll stop my investigations.
## Post #30
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-24T14:17:15+00:00
- Post Title: Re: WRC 7 .P3D models

> Reply from shakotay2
>
> Not nice, huckleberrypie, to let people work in parallel, on zenhax and here on xentax.  
I'll stop my investigations.
Oh, sorry about that mate, I didn't mean to disappoint you on this one. If you no longer feel like working on this one, fine, but please, I really didn't mean to burst your bubble on this. All I did was ask for a second opinion and all, not to tick you off royally.
## Post #31
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-24T15:50:16+00:00
- Post Title: Re: WRC 7 .P3D models

Thing is, if you had told you opened the same thread on zenhax it would have spared me tons of lifetime.
That's a matter of respect, too. As simple as this.

Seems you don't know about cross-posting, do you?
"2. It wastes the time of those trying to help."

"Please don't cross-post questions on multiple forums at the same time (whether on multiple threads here, or on other forums). If you post on another forum and don't get the answer you need, please feel free to post it here after a reasonable length of time"
source: [https://www.lightroomqueen.com/communit ... rossposts/](https://www.lightroomqueen.com/community/help/crossposts/)

"Please avoid cross-posting your question, or mention the other site(s) with referral link(s) to avoid repetitive responses."
source: [https://www.home-barista.com/news/guide ... t1223.html](https://www.home-barista.com/news/guidelines-for-productive-online-discussion-t1223.html)
## Post #32
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-25T00:17:30+00:00
- Post Title: Re: WRC 7 .P3D models

> Reply from shakotay2
>
> Thing is, if you had told you opened the same thread on zenhax it would have spared me tons of lifetime.
That's a matter of respect, too. As simple as this.

Seems you don't know about cross-posting, do you?
"2. It wastes the time of those trying to help."

"Please don't cross-post questions on multiple forums at the same time (whether on multiple threads here, or on other forums). If you post on another forum and don't get the answer you need, please feel free to post it here after a reasonable length of time"
source: https://www.lightroomqueen.com/communit ... rossposts/

"Please avoid cross-posting your question, or mention the other site(s) with referral link(s) to avoid repetitive responses."
source: https://www.home-barista.com/news/guide ... t1223.html
Alright mate, I understand. Again I didn't mean to, it's just that I needed all the help in this one; I really did not intend to disrespect or talk smack at you or anyone else involved, so I really am sorry.
## Post #33
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-25T08:13:20+00:00
- Post Title: Re: WRC 7 .P3D models

I'll keep an eye on that thread: [https://zenhax.com/viewtopic.php?f=5&t=8872](https://zenhax.com/viewtopic.php?f=5&t=8872)
If there's no progress within one month maybe I'll give it another try next year.

btw: most  submesh positions of the Yaris in the zip I uploaded are correct without using a skeleton
but guess I'd need to apply some rotations (for the wipers for example)
## Post #34
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-25T10:57:31+00:00
- Post Title: Re: WRC 7 .P3D models

> Reply from shakotay2
>
> I'll keep an eye on that thread: https://zenhax.com/viewtopic.php?f=5&t=8872
If there's no progress within one month maybe I'll give it another try next year.

btw: most  submesh positions of the Yaris in the zip I uploaded are correct without using a skeleton
but guess I'd need to apply some rotations (for the wipers for example)
So I noticed. The latest OBJ dump you sent to me had some of the meshes merged, but oh well...
## Post #35
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-25T11:24:31+00:00
- Post Title: Re: WRC 7 .P3D models

> Reply from huckleberrypie
>
> The latest OBJ dump you sent to me had some of the meshes merged, but oh well...

> Reply from shakotay2
>
> From mesh number 58 to 70 everything is labeled Wing_L_58, that's probably wrong so rename them, please.
Also some meshes remain clumped in the middle.You need to rename a dozens of meshnames in the obj file.
(g submeshname_x in face indices section)
## Post #36
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-11-26T05:21:57+00:00
- Post Title: Re: WRC 7 .P3D models

> Reply from shakotay2
>
> huckleberrypie wrote:The latest OBJ dump you sent to me had some of the meshes merged, but oh well...
shakotay2 wrote:From mesh number 58 to 70 everything is labeled Wing_L_58, that's probably wrong so rename them, please.
Also some meshes remain clumped in the middle.You need to rename a dozens of meshnames in the obj file.
(g submeshname_x in face indices section)
Alright, noted.
