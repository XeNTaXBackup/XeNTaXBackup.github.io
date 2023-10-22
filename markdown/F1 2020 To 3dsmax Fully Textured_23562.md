## Post #1
- Username: vx110
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 05, 2020 6:13 am
- Post datetime: 2021-03-08T22:17:27+00:00
- Post Title: F1 2020 To 3dsmax Fully Textured

Hello

I have a question about 3dsmax and the exported F1 2020 Models of 3dsimed.

1) I can see the complete car correctly textured in 3dsimed. On the right side you can see the primary map which is the "paint" texture map and the secondary map which is called "decal" map.
[](https://abload.de/image.php?img=14jj49.jpg)

2) When I export in 3dsimed the model as a *.obj and I import it in 3dsmax... I can texture the whole car but not the decal map. In the material Editor there is only the primary texture and not in the paint texture a seconardy map id
[](https://abload.de/image.php?img=26lkgi.jpg)

3) When I try to apply the "decal" map in "paint" slot it looks like this
[](https://abload.de/image.php?img=3nkjba.jpg)


So how can I get the model completely textured in 3dsmax? Is there any solution? Can somebody help me please?
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-03-08T23:41:51+00:00
- Post Title: F1 2020 To 3dsmax Fully Textured

it difficult you have to make a custom shader, but it can probably be achieved using the composition shader and isolating the masks.
## Post #3
- Username: vx110
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 05, 2020 6:13 am
- Post datetime: 2021-03-09T09:45:31+00:00
- Post Title: F1 2020 To 3dsmax Fully Textured

> Reply from mariokart64n ↑Tue Mar 09, 2021 7:41 am at Tue Mar 09, 2021 7:41 am
>
> 
it difficult you have to make a custom shader, but it can probably be achieved using the composition shader and isolating the masks.

Hey:)

Can you please describe it for me more ?
## Post #4
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-03-09T10:14:41+00:00
- Post Title: F1 2020 To 3dsmax Fully Textured

I would need to see the assets maybe u can post a link here of the model and textures
## Post #5
- Username: vx110
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 05, 2020 6:13 am
- Post datetime: 2021-03-09T11:43:40+00:00
- Post Title: F1 2020 To 3dsmax Fully Textured

Hey:)

I sent a PM:)
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-03-10T05:17:18+00:00
- Post Title: F1 2020 To 3dsmax Fully Textured

You need to use something called [Blend material](http://help.autodesk.com/view/3DSMAX/2017/ENU/?guid=GUID-D2B59023-7D53-4E86-804F-7A037E787055) instead of Multi/Sub-Object material.
## Post #7
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-03-10T08:33:02+00:00
- Post Title: F1 2020 To 3dsmax Fully Textured

This model uses multi uv channels for decals,and the OBJ file that you sent me does not support multi channel which means there is no hope for that model. I tried akderebur's converter that exports a *.NEX file but the model was missing all material assignment data and I had to rebuild the material ids manually piece by piece O_O

[viewtopic.php?t=19711](https://forum.xentax.com/viewtopic.php?t=19711)

I'll PM the max file back to you but please understand it is not 100%  because I had to do much manual editing.

I recommend checking whatever software you are using to and check if you can export to FBX or glTF since they are the only formats that have support for multichannel UVs.

And as Bigchillghost stated the rest is just using image masks to blend the the diffuse and decals together... 

[](https://ibb.co/7kY8QCV)
## Post #8
- Username: vx110
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 05, 2020 6:13 am
- Post datetime: 2021-03-10T13:24:14+00:00
- Post Title: F1 2020 To 3dsmax Fully Textured

> Reply from mariokart64n ↑Wed Mar 10, 2021 4:33 pm at Wed Mar 10, 2021 4:33 pm
>
> 
This model uses multi uv channels for decals,and the OBJ file that you sent me does not support multi channel which means there is no hope for that model. I tried akderebur's converter that exports a *.NEX file but the model was missing all material assignment data and I had to rebuild the material ids manually piece by piece O_O

viewtopic.php?t=19711

I'll PM the max file back to you but please understand it is not 100%  because I had to do much manual editing.

I recommend checking whatever software you are using to and check if you can export to FBX or glTF since they are the only formats that have support for multichannel UVs.

And as Bigchillghost stated the rest is just using image masks to blend the the diffuse and decals together...

Hi:)

Oh I see it's a little bit more difficult than I imagined. I think I have to give up then because I dont really know how to rebuild the material id's piece by piece.

I used 3dSimEd to export the *.obj file but I can also export *.fbx but I couldnt find any slot for the decal aswell in 3dsmax.

So Thank u for helping me out even it was a lot of work for you:)
