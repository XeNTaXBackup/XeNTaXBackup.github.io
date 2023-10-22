## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-03T06:18:29+00:00
- Post Title: Hover mount! model with many submeshes

Hi! I would like to know if anyone has had any kind of experience with a 3d model like this, because it contains several mounts and in a certain way you can get some, but there are others that no, as much as I have been trying to get the second face block index I have not had luck, but the model is there, just that I am not using the correct values, because as you can see increasing the value of the vertices you can preview the shape of the mount that I want to get. Please, if anyone has any advice or where to keep checking to get the model, leave your comment. Thanks in advance.  

[https://www.mediafire.com/file/zugy6spz ... M.bin/file](https://www.mediafire.com/file/zugy6spzo5af3a1/MountHoverboard_DECOM.bin/file)




test.jpg (119.38 KiB) Viewed 179 times
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-04-03T13:00:34+00:00
- Post Title: Hover mount! model with many submeshes

Using AMR:



MountHoverboard_2ndMesh.png (155.66 KiB) Viewed 166 times
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-04-03T13:18:03+00:00
- Post Title: Hover mount! model with many submeshes

Or these params for H2O:



MountHoverboard_2ndMesh_H2O.png (92.86 KiB) Viewed 163 times
## Post #4
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-03T13:42:51+00:00
- Post Title: Hover mount! model with many submeshes

> Reply from Bigchillghost ↑Sat Apr 03, 2021 9:18 pm at Sat Apr 03, 2021 9:18 pm
>
> 
Or these params for H2O:
MountHoverboard_2ndMesh_H2O.png

wow!! thanks alot!
## Post #5
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-03T13:50:01+00:00
- Post Title: Hover mount! model with many submeshes

> Reply from Bigchillghost ↑Sat Apr 03, 2021 9:18 pm at Sat Apr 03, 2021 9:18 pm
>
> 
Or these params for H2O:
MountHoverboard_2ndMesh_H2O.png

Bigchillghost, would you mind in explain a bit why you use those values in star vertices, face indices, and the count indices?   and thanks again! I'm really happy to finally see that mount!!!
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-04-03T17:14:40+00:00
- Post Title: Hover mount! model with many submeshes

> Reply from moonpaladin ↑Sat Apr 03, 2021 9:50 pm at Sat Apr 03, 2021 9:50 pm
>
> 
Bigchillghost, would you mind in explain a bit why you use those values in star vertices, face indices, and the count indices?
I assume you have no question about the fact that the whole vertex data chunk begins at offset 8 and the whole index data chunk begins at offset 0x238AA4.

For face indices, since most usually their values are in an increasing order, it's rather plain and easy to locate the first index of the next mesh by looking for a point where the index value dropped dramatically, which I referenced as a "jump discontinuity". Set the number of columns to 6 in your hex editor, hence there'd be one triangle on each row. Place your cursor at the position before the 1st index of the first mesh, then scroll down and look for the said area at the same column. As a result you'll notice that the indices increased overall and suddenly dropped at address 0x27025C, where the value changed from 0x8D79 to 0xD7B.



idx_addr.png (6.7 KiB) Viewed 133 times



Therefore you get the index counts for the two meshes:
(0x27025C - 0x238AA4) / 2 = 113628
(0x2A1258 - 0x27025C) / 2 = 100350 or (0x687B4 / 2) - 113628 = 100350

Interpret these two index chunks individually and you'll get the min & max index values and the required vertex counts of them:
1st: min value: 0 | max value: 36218, required vertex count: 36219
2nd: min value: 3451 | max value: 31932, required vertex count: 31933

Note that in Hex2Obj index values begin from 1 whereas in AMR they interpreted as is.

There're (0x238A94 / 36) = 64701 vertices and the 1st mesh takes 36219, hence there're (64701 - 36219) = 28482 vertices left. But the 2nd mesh requires 31933 vertices to construct the mesh, while its min index value is 3451, meaning that the previous 3451 vertices are not used, no mater where its vertices begin. So the actual required vertex amount would be (31932 - 3451) + 1 = 28482, exactly the amount of the vertices left. Now depends on how you'd like to construct the mesh there'd be two sets of params you could use:

1. Keep the face indices untouched and adjust the base vertex address:
Calculate the subscript of the 1st vertex of the 2nd mesh in the entire vertex array as: (64701 - 31933) = 32768, which obviously is a special value. 

Then you can obtain the start address: (32768 * 36) + 8 = 0x120008. This set of params can be used in both AMR and Hex2Obj. The shortcoming of this handling is that there'd be extra unused vertices in the mesh.

2. Reset the base of the face indices by subtracting the min value from all these indices, which is referenced as "Zero Calibration" in AMR. An adjust to the base vertex address is also required though: (36219 * 36) + 8 = 0x13E554.

With the "Zero Calibration" option checked in AMR, you'll be able to construct the mesh without these unused vertices.

As you may have noticed, this file has a rather simple layout:

```
long	chunkSize
byte	chunkData[chunkSize]

```

And there're no available reference info to the data chunks. So you really should check other files for the info you need, instead of trying to apply the above method for every file. Though you can use that as a basis.
## Post #7
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-03T17:45:57+00:00
- Post Title: Hover mount! model with many submeshes

> Reply from moonpaladin ↑Sat Apr 03, 2021 9:50 pm at Sat Apr 03, 2021 9:50 pm
>
> 
Bigchillghost, would you mind in explain a bit why you use those values in star vertices, face indices, and the count indices?

Huge thanks Bigchillghost! So detailed response !
## Post #8
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-03T21:35:22+00:00
- Post Title: Hover mount! model with many submeshes

> 2. Reset the base of the face indices by subtracting the min value from all these indices, which is referenced as "Zero Calibration" in AMR. An adjust to the base vertex address is also required though: (36219 * 36) + 8 = 0x13E554.
>
> 
>
> With the "Zero Calibration" option checked in AMR, you'll be able to construct the mesh without these unused vertices.

Hell yeah! it works pretty well!



dragon.png (26.48 KiB) Viewed 114 times



Bigchillghost, a question about the AMR tool, is there be a way to export the model  but in submeshes like hex2obj does?   Thanks!
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-04-04T02:37:57+00:00
- Post Title: Hover mount! model with many submeshes

> Reply from moonpaladin ↑Sun Apr 04, 2021 5:35 am at Sun Apr 04, 2021 5:35 am
>
> a question about the AMR tool, is there be a way to export the model  but in submeshes like hex2obj does?
If you mean stripping the mesh per 500 triangles, then no.
## Post #10
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-04T03:20:36+00:00
- Post Title: Hover mount! model with many submeshes

> Reply from Bigchillghost ↑Sun Apr 04, 2021 10:37 am at Sun Apr 04, 2021 10:37 am
>
> 
moonpaladin wrote: ↑Sun Apr 04, 2021 5:35 ama question about the AMR tool, is there be a way to export the model  but in submeshes like hex2obj does? 

If you mean stripping the mesh per 500 triangles, then no.

I see! I was trying to divide it haha, by the way when you have a little time, can you take a look to this weapon model? It looks completely different to the standard format. It is possible to extract with hex2obj or AMR? or need to use another tool for this kind of format. Thanks for your time Bigchillghost.
[https://www.mediafire.com/file/5yop0ep3 ... S.zip/file](https://www.mediafire.com/file/5yop0ep37adjl5t/FILES.zip/file)
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-04-04T11:08:39+00:00
- Post Title: Hover mount! model with many submeshes

> Reply from moonpaladin ↑Sun Apr 04, 2021 11:20 am at Sun Apr 04, 2021 11:20 am
>
> 
I was trying to divide it haha
I've already said that you need to look for the required info in other files for proper submesh division. If you knew the polygon count of each submesh you can assign a material group to each of them, then you can split them by material groups in your 3D app if you'd like to.

> Reply from moonpaladin ↑Sun Apr 04, 2021 11:20 am at Sun Apr 04, 2021 11:20 am
>
> It looks completely different to the standard format. It is possible to extract with hex2obj or AMR? or need to use another tool for this kind of format.
For the mesh it is possible by specifying the Excess Bytes params in AMR:
(WEP/katana_eSkatana.elu)



katana_eSkatana.png (115.75 KiB) Viewed 82 times



But the UVs are stored as per-polygon vertex texture coordinates along in the polygon struct like this:

```
for i = 0 < polygonCount
{
	long	polygonVertexIndices[3]
	float	polygonVertex1UVW[3]
	float	polygonVertex2UVW[3]
	float	polygonVertex3UVW[3]
	long	unknown[2]
}

```

This situation is beyond AMR's capability and you can't handle it without a customized script or something like that.
## Post #12
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-04T16:02:13+00:00
- Post Title: Hover mount! model with many submeshes

> For the mesh it is possible by specifying the Excess Bytes params in AMR:
Could you tell me how did you decide to put the number 44?   

> But the UVs are stored as per-polygon vertex texture coordinates along in the polygon struct like this:
>
> Code: Select alllong	polygonCount
>
> for i = 0 < polygonCount
>
> {
>
> 	long	polygonVertexIndices[3]
>
> 	float	polygonVertex1UVW[3]
>
> 	float	polygonVertex2UVW[3]
>
> 	float	polygonVertex3UVW[3]
>
> 	long	unknown[2]
>
> }
>
> 
>
> This situation is beyond AMR's capability and you can't handle it without a customized script or something like that.

ouch so sad to hear it, those are custom models of gunz the duel, a custom script like the noesis script right? I'm gonna be checking how to or examples, because didn't encounter a file that requiere a script only for UV's. Thanks for your time Bigchillghost.
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-04-04T16:17:54+00:00
- Post Title: Hover mount! model with many submeshes

> Reply from moonpaladin ↑Mon Apr 05, 2021 12:02 am at Mon Apr 05, 2021 12:02 am
>
> 
Could you tell me how did you decide to put the number 44?
As shown in the layout: 12 * 3 + 8 = 44.

```
for i = 0 < polygonCount
{
	long	polygonVertexIndices[3]
	float	polygonVertex1UVW[3] // 12 bytes
	float	polygonVertex2UVW[3] // 12 bytes
	float	polygonVertex3UVW[3] // 12 bytes
	long	unknown[2] // 8 bytes
}

```


> Reply from moonpaladin ↑Mon Apr 05, 2021 12:02 am at Mon Apr 05, 2021 12:02 am
>
> 
a custom script like the noesis script right?
A script, or a standalone program depending on the programming language you used.
## Post #14
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-04T18:19:04+00:00
- Post Title: Hover mount! model with many submeshes

> As shown in the layout: 12 * 3 + 8 = 44.

It works!now I need to check if it have submeshes, I don't remenber if it is only a body or a complete set, and also need to know how to make that script for UV's XD! .I understanded alot with your image of the values     . Thanks Bigchillghost.



body-test.png (64.28 KiB) Viewed 66 times
