## Post #1
- Username: sethhope
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 20, 2023 4:24 am
- Post datetime: 2023-09-22T18:33:50+00:00
- Post Title: Vision .model files

I've got some software at work that was "gifted" to me by the last guy. It was built on an old version of the Havok/Trinigy Vision engine and uses .model files made with vision sdk. I've tried to track down any version of Vision, but it seems to have disappeared off the internet. I've also found a few people here attempting to tear apart the model file.
I've used hex2obj to successfully sus out the basic model information (vertex, faces, uv, etc.) but the problem comes from all the data in-between. I'd like to make an exporter to be able to export TO the .model file so I can update the models in use, and as far as I can see no-one here has made heads or tails of the extra information beyond model basics. In the drive folder is one of the models I'm trying to deconstruct along with the hex2obj settings I've used. 

I'd like to start with the vertex block. The first 3 floats (4 bytes) are the X, Y, and Z values. Beyond that, the last 8 bytes are always 00. The total block size is 64 bytes
Any help putting together the pieces of this would be appreciated. 
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1WDJd5VpdK2eA8GVeKUHNMA4PfeKQlVl2?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-09-22T21:51:19+00:00
- Post Title: Vision .model files

> Reply from sethhope ↑Sat Sep 23, 2023 2:33 am at Sat Sep 23, 2023 2:33 am
>
> Beyond that, the last 8 bytes are always 00.Not always. At block offset 56 there's uvs:
.



point_model_uvs.png (40.26 KiB) Viewed 71 times



At block offset 12 there's normals. At offset 28 there might be another uv channel (wild guess).
## Post #3
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2023-09-23T08:55:25+00:00
- Post Title: Vision .model files

> Reply from sethhope ↑Sat Sep 23, 2023 2:33 am at Sat Sep 23, 2023 2:33 am
>
> 
I've got some software at work that was "gifted" to me by the last guy. It was built on an old version of the Havok/Trinigy Vision engine and uses .model files made with vision sdk. I've tried to track down any version of Vision, but it seems to have disappeared off the internet. I've also found a few people here attempting to tear apart the model file.
I've used hex2obj to successfully sus out the basic model information (vertex, faces, uv, etc.) but the problem comes from all the data in-between. I'd like to make an exporter to be able to export TO the .model file so I can update the models in use, and as far as I can see no-one here has made heads or tails of the extra information beyond model basics. In the drive folder is one of the models I'm trying to deconstruct along with the hex2obj settings I've used. 

I'd like to start with the vertex block. The first 3 floats (4 bytes) are the X, Y, and Z values. Beyond that, the last 8 bytes are always 00. The total block size is 64 bytes
Any help putting together the pieces of this would be appreciated. 
https://drive.google.com/drive/folders/ ... sp=sharing

You can open the .model files using the following programs:

- 3D Object Converter (Windows)
- i3DConverter (macOS)
- i3DConverter (Linux)

How to get the 3D Object Converter:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.

How to get the i3DConverter:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.

How to get the i3DConverter Linux:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
## Post #4
- Username: sethhope
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 20, 2023 4:24 am
- Post datetime: 2023-09-23T17:04:43+00:00
- Post Title: Vision .model files

> You can open the .model files using the following programs:
>
> 
>
> - 3D Object Converter (Windows)
>
> - i3DConverter (macOS)
>
> - i3DConverter (Linux)
>
> 
>
> How to get the 3D Object Converter:
>
> Download the 3D Object Converter from  http://3doc.i3dconverter.com and install it or download and use the portable version.
>
> 
>
> How to get the i3DConverter:
>
> Download the i3DConverter from  http://www.i3dconverter.com and install it.
>
> 
>
> How to get the i3DConverter Linux:
>
> Download the i3DConverter from  http://www.i3dconverter.com and install it.

Ive used i3dconverter to export the models just fine, the problem come with trying to compile NEW models in the format. I am trying to update the visuals of the program, and it only reads .model files. 
I am trying to come up with possibly a blender exporter or similar that can generate .model, and possibly once model is sorted, .vcolmesh files.

I came across an old archived version of trinigy vision sdk from '09 last night. It doesnt open the files, saying a block version is off. Ill be digging into the maya exporter and vMeshViewer throughout the weekend to try and find more information on the filetype.
