## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-27T15:46:31+00:00
- Post Title: A Demonstration on Using AXE

This topic is intended for a demonstration on exploiting the main features of AXE, short for [Advanced Mesh Reaper - Xtreme Edition](viewtopic.php?f=16&t=23963). It's also served to be an extent on the topic [Analyzing and Extracting a Game Model](viewtopic.php?f=29&t=17890). The sample files used in this article can be found [here](https://mega.nz/file/LJtUiBba#pj-XhKzhRFL6ke2L-cAOViWGdPe4lw03K7ONeO1KU1w) in case you'd like to follow the procedure. A PDF version of this article can be downloaded [here](https://mega.nz/file/OUcjmYQT#lhyEQv98u_oJ0uBmhujjpOGx4We3S3iKFt8iSflstV8).
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-27T16:01:54+00:00
- Post Title: A Demonstration on Using AXE

Open the data file "skrull_skin_m.nif" in AXE by navigating to the "File" menu and select "Open".

First let's prepare the materials that are used by the model. This step can be taken at any point before the materials are referenced, but we'll do it first to keep things organized.
Since there's only 1 texture set being used by the model, we just need to create a single material object. Click the "Add" button within the "Materials" group box, and fill in the required info in the pop-up window as shown in Fig. 1.


Fig. 1

The most important info is the texture file name and the UV set it applies to, for each map channel. The file name of the texture can be specified by clicking the corresponding "Path" button and selected from a file dialog. Or you can just paste the file names to avoid references to the absolute paths. The program then assumes the path of the data source file(s) as the root directory where the textures reside in upon preview. You can even place them into a sub-folder if necessary. The diffuse and the normal maps are applied to the same UV as you can tell by looking at the textures so let's just leave the "UV Set" params as the default values. You can edit the material name and the material's base color as you like though. In this case we just picked the shared part of the texture names, and gave it a 100% green color. Click "OK" once you're satisfied with the settings, to make the changes effective.

Now we take care of the mesh data. Open the same nif file in HexEdit and jump to address 0x1B50, where you'll find some hint about the vertex layout as shown in Fig. 2.


Fig. 2
Base on this we know that the polygon indices come first, then the vertex attributes, which should be layout as texcoord, position, normal, binormal, tangent, blend indices, and blend weight. It also mentioned something called "bone palette" here, which is related to how the actual bone index is located by the "blend indices". We'll deal with that later.
From this point on, search for the byte sequence "00 01 02 15" in HexEdit, and we find the first match at address 0x6760, as shown in Fig. 3.


Fig. 3

As it was covered in the original tutorial, the 32 bytes from address 0x6740 are layout as:

```
INT32	zero-field
INT32	sub-mesh-count
struct
{
	INT32	first-array-index
	INT32	index-count
} index-group-info[sub-mesh-count]
INT32	marker-count
INT32	marker	

```
 
There're two index groups, and the index data chunk starts at address 0x6764. The summary info of each index group is listed in Table 1.

```
0		0x6764			0x340B / 13323			unsigned short
1		0xCF7A			0xC06 / 3078			unsigned short

```

Table 1

Skip the 0x8022 bytes of index data from address 0x6764, and we'll reach to the vertex info header at address 0xE786, as shown in Fig. 4.


Fig. 4

Again, as it was described in the original tutorial, the vertex info header from address 0xE787 is layout as:

```
INT32	zero-field
INT32	sub-mesh-count
struct
{
	INT32	first-array-index
	INT32	vertex-count
} vertex-group-info[sub-mesh-count]
INT32	marker-count
INT32	markers	[marker-count]

```


The summary info of each vertex group is listed in Table 2.

```
0		0xE7C3			0xA7E / 2686			48
1		0x2DF63			0x287 / 647			48

```

Table 2
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-27T16:04:05+00:00
- Post Title: A Demonstration on Using AXE

Set the number of columns to 48 in the hex editor, and each vertex element will be held exactly on 1 row. See Fig. 5.


Fig. 5

And combined with the previous hint, we get the definition of this vertex layout as listed in Table 3.

```
half-float	Texcoord[2]		0
half-float	Position[4]		4
half-float	Normal[4]		0xC
half-float	Binormal[4]		0x14
half-float	Tangent[4]		0x1C
byte		BlendIndices[4]		0x24
half-float	BlendWeights[4]		0x28

```

Table 3

Though it wrote 4 blend weights here, actually only the first 3 weights are valid, since the 4th is always 1.0.
Now let's make use of the info we have up to this point, to construct the meshes with all the attributes.

Click the "Big" button in the "Endianness" group box for big-endian data.
Input the address and index count in the corresponding edit box within the "Polygon Vertex Indices" group box. Leave the "Data Type" and the "Encoding" as the default settings since these are exactly the settings that we need. The params for polygon attributes is shown in Fig. 6. Then click the "Polygon Vertex Indices" button in the "Data Interpretation" group box to interpret the polygon vertex indices. The abstract info is shown in the "Digest" window at the lower right corner (see Fig. 7).

 
Fig. 6, Fig. 7

Check the "Material Groups" check box in the "Polygon Attributes" group box, then click the "Manage Parameters" button which should lead to the "Material Groups" dialog as shown in Fig. 8. There're currently two modes available for assigning materials to the polygons. Under the "By Polygon Ranges" mode, you can assign materials to a set of polygon groups by specifying the range of each polygon set and the used material. Whereas under the "By Polygon Material Index" mode, the material assigned to each polygon is specified by an individual material index, which is read from the same source data file as used by the polygon vertex indices. 


Fig. 8

In this case we'll just assign the material manually under the "By Polygon Ranges" mode. Click the "Add" button to create a polygon set. Specify the begin and the end polygon IDs for the range, where the polygon specified by the end ID is not included in that set of polygons. The end ID for the last polygon range must be the exact polygon count for current polygon parameter set. But if there's only 1 polygon set, you can either specify the actual end polygon ID (in this case, it's 4441 as shown in the digest message), or use the special value '1', to assign a material to all polygons in this polygon parameter set. Here we just use the default special value, then select a material from the "Using Material" combo box, as shown in Fig. 9. Click "OK" to save the settings. There should now be a polygon range item in the combo box in the "By Polygon Ranges" group box, as shown in Fig. 10. Click "OK" again to save the setting.

 
Fig. 9, Fig. 10

Once the interpretation on the polygon vertex indices is done, you can click the "Calculated" button in the "Vertex Count" group box to get the vertex count automatically, or just input the value explicitly.

Click the "Relative to" button in the "Address" group box in the "Vertex Attributes" group box to enable the relative address mode, then specify the values of the relative address and the layout positions for corresponding attributes. There's no vertex color attribute in this format but we can just re-use the vertex normal for demonstration. The program will automatically flip any negative values. Check the "All Same" check boxes in the "Stride" and the "Data Type" group boxes to use a shared stride and data type for all attributes except for the blend weights and the blend indices. Set the stride value to 48 and select "Half-float" in the combo box for the data type.

Generally, the address, the stride and the data type for skinning info is not affected by the relative address, the all-same stride and the all-same data type used by the other attributes. They must be specified individually. But it's still possible to share the relative address as the other attributes, by checking the "Relative Address" check box in the sub "Skinning Info" group box. The strides and data types however must be specified explicitly.

In this case, we'll enable the relative address mode for the blend attributes, and set the rest parameters properly. Uncheck the "Mapping Bone Indices" group box, and set the value of the "Per Vertex Bone Count" parameter to 3.

Now you should have the parameters set as shown in Fig. 11.


Fig. 11
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-27T16:06:56+00:00
- Post Title: A Demonstration on Using AXE

Click the corresponding buttons of the vertex attributes in the "Data Interpretation" group box to interpret them individually. Similarly, the abstract info will be shown in the "Digest" window.

As shown in Fig. 12 and Fig. 13, the blend indices and the blend weights now take 3 slots for each vertex, and some indices are just placeholders for data alignment as they have zero weights. You can check the "Hide Weightless Bone Indices" check box from the "Preference" settings under the "Options" menu to hide those indices with meaningless weights upon interpretation, as shown in the Fig. 14 and Fig. 15.

 
Fig. 12, Fig. 13

 
Fig. 14, Fig. 15

Now check the "Point Cloud" button in the "Preview" group box, then click the "Preview" button to preview the positions as point cloud, as shown in Fig. 16. Check the "Mesh" button and click the "Preview" button again to preview as mesh, as shown in Fig. 17. Check the "Vertex Colors" check box to preview the mesh with vertex color, as shown in Fig. 18.

 
Fig. 16, Fig. 17


Fig. 18

Uncheck the "Vertex Colors" check box, and select "TBN Vectors" from the combo box to preview the mesh with tangent, binormal and normal vectors, as shown in Fig. 19.


Fig. 19

Select "Texcoords" from the combo box to preview the UV, as shown in Fig. 20. As you can see the texture is applied incorrectly because the UV is upside down. Check the "Flip Vertical" check box in the "UV Channels" group box and click the "Preview" button again, the texture is now correctly applied to the UV, as shown in Fig. 21.


Fig. 20


Fig. 21
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-27T16:08:36+00:00
- Post Title: A Demonstration on Using AXE

Skipping these 0x270F0 bytes of the vertex data, there comes another "00 01 02 15" byte sequence. Yet it's not a polygon index block, though it shares the similar structure. This is the aforementioned "bone palette" territory. 
There're two primary index tables here, both of which contain 0x1E unsigned short indices, which are corresponding to the two sub-meshes, see Fig. 22.


Fig. 22

The info of the primary index tables is listed in Table 4.

```
0		0x358D8				0x1E | 30
1		0x35914				0x1E | 30

```

Table 4

At address 0x3599B there comes a secondary index table containing 0x29 int32 indices. This's how things work: a blend index in the vertex layout first references to the corresponding primary index table, and then uses that primary index for reference to the secondary index table to get the actual bone index. 

We need to dereference the primary index table and convert it into a direct mapping index table for actual bone indices in order to make use of this info. Navigate to the "Tools" menu and click on the "Data Reorganizer" entry. Specify the "Input File" and fill in the corresponding parameters for "Endianness", "Data" and "Reference Indices". Check the "Unsigned Int" button in the "Interpret Output" group box, and click the "Interpret" button to parse the output. The result will be shown in the edit box where the values are separated by commas. The parameters for the two sub-meshes are shown respectively in Fig. 23 and Fig. 24.


Fig. 23


Fig. 24

Back to the main window, check the "Mapping Bone Indices" group box and then the "Use User Defined Mapping Indices" check box, and paste the corresponding values string generated by the "Data Reorganizer" from previous step, as shown in Fig. 25.


Fig. 25

Now we have specified all the information for the first sub-mesh, let's save the params before dealing with the next sub-mesh. Click the "Add" button in the "Vertex Parameter Sets" group box to add the current vertex params to the vertex param list. Click the "Add" button in the "Polygon Parameter Sets" group box to add the current polygon params to the polygon param list. For the 2nd sub-mesh, check the "Zero Accumulation" check box in the "Polygon Vertex Indices" group box to set the base vertex index to the max vertex count required by previous polygon parameter sets, as shown in Fig. 26. This will allow the indices of each polygon parameter set to refer to corresponding vertex data block independently while keeping them as a single mesh object.


Fig. 26
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-27T16:12:13+00:00
- Post Title: A Demonstration on Using AXE

Search the "00 01 02 15" byte sequence from this point for the next mesh group, and apply similar procedures as shown above. The second mesh group is to be found at address 0x367C8 and the third at address 0x512A2. The third mesh group contains only one sub-mesh where its "bone palette" is located at address 0x71176, as shown in Fig. 27.


Fig. 27

As you can see there're 10 indices in the primary index table where each value is exactly the subscript of itself. In this case we can just use the secondary index table directly, as shown in Fig. 28.


Fig. 28

Up to this point you should have in total 5 sub-meshes saved into the vertex and the polygon parameter sets. The parameters of the 3rd to the 5th sub-meshes is shown respectively in Fig. 29, Fig. 30 and Fig. 31.


Fig. 29


Fig. 30


Fig. 31

And the "User Defined Mapping Bone Indices" for the 1st to the 4th sub-meshes are listed in Table 5.

```
1		12,38,39,40,74,78,104,107,171,173,174,175,13,15,16,17,18,34,36,23,25,26,27,28,12,12,12,12,12,12
2		175,176,178,179,180,184,185,186,190,191,192,193,197,198,199,204,205,206,12,12,12,12,12,12,12,12,12,12,12,12
3		40,42,44,46,48,52,54,56,58,60,64,66,68,70,72,74,76,78,80,82,84,86,90,92,94,96,98,100,102,104
4		50,62,88,40,40,40,40,40,40,40,40,40,40,40,40,40,40,40,40,40,40,40,40,40,40,40,40,40,40,40

```

Table 5

Though we have the skinning info for all sub-meshes, we don't have the proper skeleton to actually make use of it. Getting the skeleton data from different file formats is a much more advanced topic beyond the scope of this article. Luckily, AXE provides an easy-operating "Auto Bone Generation" system to automatically create a set of bone nodes for you. You can then edit the nodes and construct a skeleton from them easily.

To generate a bone list, you must have the skinning info prepared first. Since we've already done that, we can just move to the next step. Navigate to the "Tools" menu, and click on the "Auto Bone Generation" entry. There should be a set of bone nodes generated in the combo box in the "Skeleton" group box, as shown in Fig. 32.


Fig. 32
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-05-27T16:15:01+00:00
- Post Title: A Demonstration on Using AXE

Click on the "Preview Skeleton" entry under the "Options" menu to preview the bone nodes, as shown in Fig. 33. Click the "Preference" entry under the same menu, then check the "Display Bone Node Names" check box and click "OK", as shown in Fig. 34. Preview the bone nodes again and you can see the bone name label displayed near each bone node. Zoom in the camera on the red box area as shown in Fig. 35. As you can see from Fig. 36, "Bone-12" should be the parent of "Bone-13", "Bone-23" and "Bone-34".


Fig. 33


Fig. 34


Fig. 35


Fig. 36

Let's take "Bone-23" as an example. Click the "Manage List" button in the "Skeleton" group box, and select "Bone-23" from the tree view on the left of the "Bone Nodes" editor, as shown in Fig. 37. Select "Bone-12" from its "Parent Node" combo box and click "Apply", as shown in Fig. 38.


Fig. 37


Fig. 38

You'll see that "Bone-23" is then placed under the node "Bone-12", as shown in Fig. 39. Click the "OK" button to save the change, and preview the skeleton again, as shown in Fig. 40. As you can see the child bone is now connected to its parent and a limb has been drawn.


Fig. 39


Fig. 40

Perform similar operations on the rest of the bone nodes respectively, and you'll be able to construct the skeleton as shown in Fig. 41. You can adjust the size of the node name labels with the "Ctrl +" and the "Ctrl -" shortcut keys for a better observation if necessary.


Fig. 41

Click the "Preview All in List" entry under the "Options" menu to preview the whole mesh with the skeleton, and press the "W" key to examine how the skeleton match with the mesh under wireframe mode, as shown in Fig. 42 and Fig. 43.


Fig. 42


Fig. 43

These pretty much covered the main features of AXE. Thanks for reading!
## Post #8
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-06-12T14:23:52+00:00
- Post Title: A Demonstration on Using AXE

> Reply from Bigchillghost ↑Thu May 27, 2021 11:46 pm at Thu May 27, 2021 11:46 pm
>
> ...A PDF version of this article can be downloaded here.



PDF_ERROR.PNG (11.81 KiB) Viewed 688 times
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-12T17:50:13+00:00
- Post Title: A Demonstration on Using AXE

PDF is now updated.
## Post #10
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-15T01:41:15+00:00
- Post Title: A Demonstration on Using AXE

Read this a bit more today and was able to actually get the verts/faces/UVs working properly for a random SE4 model I tried for fun, if only bones were easier to recognize. It'd be awesome to eventually see a tutorial where the file doesn't give you a hint if you ever have a good amount of free time haha. Once again thanks for the awesome program.
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-15T03:57:32+00:00
- Post Title: A Demonstration on Using AXE

> Reply from dimis9138 ↑Tue Jun 15, 2021 9:41 am at Tue Jun 15, 2021 9:41 am
>
> It'd be awesome to eventually see a tutorial where the file doesn't give you a hint
The original tutorial Analyzing and Extracting a Game Model has revealed the process about analysing and reverse engineering the vertex layout already. This article is mainly for demonstration of the AXE features. So the details of analysing the layout and the unmentioned vertex attributes are omitted to save space. This format happens to contain the layout info which makes it easier for the readers. It's also an excelent example given that fact that there's already been a foundation tutorial about the same format. You can skip the details when reading this article, and dive into the analysis process in the other thread if you're interested. The analysing process is basically the same for most formats.
## Post #12
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-15T04:12:52+00:00
- Post Title: A Demonstration on Using AXE

> Reply from Bigchillghost ↑Tue Jun 15, 2021 11:57 am at Tue Jun 15, 2021 11:57 am
>
> 
dimis9138 wrote: ↑Tue Jun 15, 2021 9:41 amIt'd be awesome to eventually see a tutorial where the file doesn't give you a hint

The original tutorial Analyzing and Extracting a Game Model has revealed the process about analysing and reverse engineering the vertex layout already. This article is mainly for demonstration of the AXE features. So the details of analysing the layout and the unmentioned vertex attributes are omitted to save space. This format happens to contain the layout info which makes it easier for the readers. It's also an excelent example given that fact that there's already been a foundation tutorial about the same format. You can skip the details when reading this article, and dive into the analysis process in the other thread if you're interested. The analysing process is basically the same for most formats.

Thank you, I'm going to go read that now. One other thing I'd like to ask is if there's any good tutorial for reversing bones/skinning data from a model format that you could recommend. If not I'll read the one you've posted in this thread anyway but was wondering if there's any others out there that could be good to read up on.
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-15T04:27:36+00:00
- Post Title: A Demonstration on Using AXE

For bone formats refer to this topic.
[viewtopic.php?f=29&t=19429](viewtopic.php?f=29&t=19429)

The skinning info is merely about recognizing the blend indices and the blend weights which's not worthy for making another tutorial. Though there might be multi-level mapping bone indices tables but that's all.
## Post #14
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-16T00:48:38+00:00
- Post Title: A Demonstration on Using AXE

> Reply from Bigchillghost ↑Tue Jun 15, 2021 12:27 pm at Tue Jun 15, 2021 12:27 pm
>
> 
For bone formats refer to this topic.
viewtopic.php?f=29&t=19429

The skinning info is merely about recognizing the blend indices and the blend weights which's not worthy for making another tutorial. Though there might be multi-level mapping bone indices tables but that's all.

I'm assuming however for these you have to read this first: [viewtopic.php?f=29&t=19428](https://forum.xentax.com/viewtopic.php?f=29&t=19428) and then get into the actual samples you've posted and read how you parse it with your scripts? I suppose I gotta learn how to read the actual formats first although that became a lot easier after reading the very first guide you posted which also explains the terminology.
