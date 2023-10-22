## Post #1
- Username: Dark Watcher
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Dec 09, 2021 7:40 am
- Post datetime: 2021-12-11T16:12:03+00:00
- Post Title: Solution to the problem of exporting MGS3 models using Noesis with Jayveer plugin

Jayveer's Noesis script has a serious export problem. When you use Noesis to export MGS3 models, the models come out with inverted Normals on some polygons. But I managed to solve the problem (using 3DS Max) and the solution is as follows: just select the polygons that have inverted normals (with the help of renderings to visualize where the texture doesn't appear), use the "Normals" modifier and select the "Flip Normals" option. To save the changes, just right-click the "Normals" modifier in Stack, select the "Collapse to" option and then "Yes" in the dialog box that appears. This process requires you to spend time that varies depending on the complexity of the model.

In other words, models with a lot of polygons have a lot of polygons with inverted Normals after exporting using Noesis with Jayveer plugin. This is probably an error in the plugin itself, as Noesis rarely presents this type of error.

Another bug is exporting textures without the alpha channel. I still can't figure out how to export with this channel, but when I do I'll update the post.

Most likely this subject should be almost extinct, but I decided to post this to help those who are still ripping MGS3 and have the same problem.
[Render.png](https://xentaxbackup.github.io/file/21374_Render.png)
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-12-12T00:42:36+00:00
- Post Title: Solution to the problem of exporting MGS3 models using Noesis with Jayveer plugin

> Reply from Dark Watcher ↑Sun Dec 12, 2021 12:12 am at Sun Dec 12, 2021 12:12 am
>
> 
Jayveer's Noesis script has a serious export problem. When you use Noesis to export MGS3 models, the models come out with inverted Normals on some polygons. But I managed to solve the problem and the solution is as follows: just select the polygons that have inverted normals (with the help of renderings to visualize where the texture doesn't appear), use the "Normals" modifier and select the "Flip Normals" option. To save the changes, just right-click the "Normals" modifier in Stack, select the "Collapse to" option and then "Yes" in the dialog box that appears. This process requires you to spend time that varies depending on the complexity of the model.

In other words, models with a lot of polygons have a lot of polygons with inverted Normals after exporting using Noesis with Jayveer plugin. This is probably an error in the plugin itself, as Noesis rarely presents this type of error.

Another bug is exporting textures without the alpha channel. I still can't figure out how to export with this channel, but when I do I'll update the post.

Most likely this subject should be almost extinct, but I decided to post this to help those who are still ripping MGS3 and have the same problem.

Nice job fixing the issue, wanted to add a few quick things that might save you time in future.

It isn't an MGS3 specific problem, it a problem with normals facing directions that sometimes occur on 3D Models, just happens a lot in the MGS exports for some reason (which is odd given that they display ok in noesis, but display and convert are quite different so I guess thats where the issue happens).

For anyone wondering about other alternative fixes for other software:

In Maya you'd disable backface culling, enable double sided lighting, and set normals to Face, the blackness is usually caused by the smoothing angle of the normal being weird and not visible at the correct angle. To resolve correctly in maya (or max or blender etc) you'd want to select those faces and flip the normals (or invert). Another quick way to do it could potentially be to invert the entire models normals in 1 go, that'd make the ones that were previously broken, look fine, but everything else would be invisible. From there select all the faces (I assume Max has a way to tell it not to select backfaces) then invert those, then reinvert the entire model, and now everything faces the correct direction. The last method would be by far the fastest approach, provided the user can find an option to disable accidently selecting backfaces.

If someone is familiar with 3d modelling in general, they'll know right away how to fix the issue, but for anyone who isn't, the above method should point you in the right direction.
## Post #3
- Username: Dark Watcher
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Dec 09, 2021 7:40 am
- Post datetime: 2021-12-12T01:11:34+00:00
- Post Title: Solution to the problem of exporting MGS3 models using Noesis with Jayveer plugin

> Reply from lionheartuk ↑Sun Dec 12, 2021 8:42 am at Sun Dec 12, 2021 8:42 am
>
> 
Dark Watcher wrote: ↑Sun Dec 12, 2021 12:12 am
Jayveer's Noesis script has a serious export problem. When you use Noesis to export MGS3 models, the models come out with inverted Normals on some polygons. But I managed to solve the problem and the solution is as follows: just select the polygons that have inverted normals (with the help of renderings to visualize where the texture doesn't appear), use the "Normals" modifier and select the "Flip Normals" option. To save the changes, just right-click the "Normals" modifier in Stack, select the "Collapse to" option and then "Yes" in the dialog box that appears. This process requires you to spend time that varies depending on the complexity of the model.

In other words, models with a lot of polygons have a lot of polygons with inverted Normals after exporting using Noesis with Jayveer plugin. This is probably an error in the plugin itself, as Noesis rarely presents this type of error.

Another bug is exporting textures without the alpha channel. I still can't figure out how to export with this channel, but when I do I'll update the post.

Most likely this subject should be almost extinct, but I decided to post this to help those who are still ripping MGS3 and have the same problem.


Nice job fixing the issue, wanted to add a few quick things that might save you time in future.

It isn't an MGS3 specific problem, it a problem with normals facing directions that sometimes occur on 3D Models, just happens a lot in the MGS exports for some reason (which is odd given that they display ok in noesis, but display and convert are quite different so I guess thats where the issue happens).

For anyone wondering about other alternative fixes for other software:

In Maya you'd disable backface culling, enable double sided lighting, and set normals to Face, the blackness is usually caused by the smoothing angle of the normal being weird and not visible at the correct angle. To resolve correctly in maya (or max or blender etc) you'd want to select those faces and flip the normals (or invert). Another quick way to do it could potentially be to invert the entire models normals in 1 go, that'd make the ones that were previously broken, look fine, but everything else would be invisible. From there select all the faces (I assume Max has a way to tell it not to select backfaces) then invert those, then reinvert the entire model, and now everything faces the correct direction. The last method would be by far the fastest approach, provided the user can find an option to disable accidently selecting backfaces.

If someone is familiar with 3d modelling in general, they'll know right away how to fix the issue, but for anyone who isn't, the above method should point you in the right direction.

Excellent contribution!! This definitely solves the problem. The last issue I noticed was that some models that have non-boxed faces, ie single polygons that are textured to look 3D, have only one face textured, and the other face invisible. Is it possible to duplicate the Normal from one face to another?
## Post #4
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-12-12T10:34:36+00:00
- Post Title: Solution to the problem of exporting MGS3 models using Noesis with Jayveer plugin

> Reply from Dark Watcher ↑Sun Dec 12, 2021 9:11 am at Sun Dec 12, 2021 9:11 am
>
> 
Excellent contribution!! This definitely solves the problem. The last issue I noticed was that some models that have non-boxed faces, ie single polygons that are textured to look 3D, have only one face textured, and the other face invisible. Is it possible to duplicate the Normal from one face to another?

Most 3D software have a transfer normals option, but if the mesh topology isn't the same, and the vertices aren't in the same location, it doesn't usually work.
I don't know how to do this in 3DS Max unfortunately, only Maya.
## Post #5
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-12-12T11:24:09+00:00
- Post Title: Solution to the problem of exporting MGS3 models using Noesis with Jayveer plugin

The problem is that mgs3 does something weird to determine the winding order when constructing a mesh and I don't know how it's calculated. So in noesis I just make it a double sided mesh for now. I did spend some time trying to figure it out but haven't managed to do so yet and I don't know when I'll return to it.
## Post #6
- Username: Dark Watcher
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Dec 09, 2021 7:40 am
- Post datetime: 2021-12-12T16:39:02+00:00
- Post Title: Solution to the problem of exporting MGS3 models using Noesis with Jayveer plugin

> Reply from lionheartuk ↑Sun Dec 12, 2021 6:34 pm at Sun Dec 12, 2021 6:34 pm
>
> 
Dark Watcher wrote: ↑Sun Dec 12, 2021 9:11 am
Excellent contribution!! This definitely solves the problem. The last issue I noticed was that some models that have non-boxed faces, ie single polygons that are textured to look 3D, have only one face textured, and the other face invisible. Is it possible to duplicate the Normal from one face to another?


Most 3D software have a transfer normals option, but if the mesh topology isn't the same, and the vertices aren't in the same location, it doesn't usually work.
I don't know how to do this in 3DS Max unfortunately, only Maya.

Yes. Apparently the 3DS Max 2018 does not. I'm going to look for a plugin. Normals Thief does not work in 2018.
## Post #7
- Username: Dark Watcher
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Dec 09, 2021 7:40 am
- Post datetime: 2021-12-12T16:42:43+00:00
- Post Title: Solution to the problem of exporting MGS3 models using Noesis with Jayveer plugin

> Reply from JayK ↑Sun Dec 12, 2021 7:24 pm at Sun Dec 12, 2021 7:24 pm
>
> 
The problem is that mgs3 does something weird to determine the winding order when constructing a mesh and I don't know how it's calculated. So in noesis I just make it a double sided mesh for now. I did spend some time trying to figure it out but haven't managed to do so yet and I don't know when I'll return to it.

I am also trying to solve this. Very strangely, my 3DS Max shuts down on its own when I try to clone a polygon to put it in the same place as the other and try to create a single polygon with two normals resulting from the union of the two.
