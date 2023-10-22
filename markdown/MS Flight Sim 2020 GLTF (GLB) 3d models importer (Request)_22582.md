## Post #1
- Username: Trophi Hunter
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 09, 2015 2:50 pm
- Post datetime: 2020-08-23T03:02:26+00:00
- Post Title: MS Flight Sim 2020 GLTF (GLB) 3d models importer (Request)

Hey so the new sim just released and they don't have any Liveries for the planes. I can create some 1:1 perfect sets but I need a way to import the models into 3ds max or Noesis. Noesis does import them but the UVS are broken. The SDK has a lot of documentation on how it exports the models but the sim compiles the GLTF models and changes the data a bit. I really would just need the 3d vertex and face data + uvs intact if possible.
I added the A320 neo model as an attachment to poke around.

[3D Models](https://drive.google.com/file/d/1x33RdkHovJvGghazW0vE1PgDp7Ku9PGg/view?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-08-23T08:31:13+00:00
- Post Title: MS Flight Sim 2020 GLTF (GLB) 3d models importer (Request)

> Reply from Trophi Hunter ↑Sun Aug 23, 2020 11:02 am at Sun Aug 23, 2020 11:02 am
>
> Noesis does import them but the UVS are broken.What does that mean exactly? Looks better than expected:
.



Lever_Elevatortrim.png (33.63 KiB) Viewed 117 times


(Maybe a swap between half floats and shorts required, or vice versa, dunno, because the code is hidden in a dll.)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-08-23T11:44:51+00:00
- Post Title: MS Flight Sim 2020 GLTF (GLB) 3d models importer (Request)

uvs_halfFloats.png (97.74 KiB) Viewed 111 times


So the uvs of the submesh here are half floats - mesh format doesn't look too hard but I usually don't care when solutions already exist.

(Too sad that the code is burried in a dll without source.)
## Post #4
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2020-08-23T16:25:43+00:00
- Post Title: MS Flight Sim 2020 GLTF (GLB) 3d models importer (Request)

Plane models seem a bit more broken.
## Post #5
- Username: Trophi Hunter
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 09, 2015 2:50 pm
- Post datetime: 2020-08-24T02:09:36+00:00
- Post Title: MS Flight Sim 2020 GLTF (GLB) 3d models importer (Request)

@CosmicDreams yeah that has to do with the bone rotation being wrong but upon export there is a optimize phase called RichPGeo and that might be the reason the uvs break, again i'm not sure but @shakotay2, plz if you could make a max script or a proper Noesis plugin i'll paypal you $10
## Post #6
- Username: CosmicDreams
- Rank: advanced
- Number of posts: 46
- Joined date: Fri Oct 13, 2017 1:04 am
- Post datetime: 2020-08-24T13:16:05+00:00
- Post Title: MS Flight Sim 2020 GLTF (GLB) 3d models importer (Request)

> Reply from Trophi Hunter ↑Mon Aug 24, 2020 10:09 am at Mon Aug 24, 2020 10:09 am
>
> 
@CosmicDreams yeah that has to do with the bone rotation being wrong but upon export there is a optimize phase called RichPGeo and that might be the reason the uvs break, again i'm not sure but @shakotay2, plz if you could make a max script or a proper Noesis plugin i'll paypal you $10

UV's are broken even in noesis i think.
