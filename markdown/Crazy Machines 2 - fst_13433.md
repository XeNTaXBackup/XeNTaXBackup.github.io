## Post #1
- Username: iUltimateLP
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 11, 2014 12:24 am
- Post datetime: 2015-10-18T12:46:36+00:00
- Post Title: Crazy Machines 2 - fst?

Hey guys, I already have the QuickBMS script found for CM2s .fst files, so it seems like every fst file represenst one package containing textures, texts, materials, and all.
But If I extract for example on objects fst, I get only folders like
  FText
  FTexture
  FMaterial
  FMesh
  FGeometry
Those seem like paramters of the object. In every folder there are one or more files without extensions. The only I thing i got is that the files in FText are hex, so I can read it using hexed.it or something related.
BMS script: [http://aluigi.altervista.org/bms/crazymachines2.bms](http://aluigi.altervista.org/bms/crazymachines2.bms)
Example fst file: [https://docs.google.com/uc?authuser=0&i ... t=download](https://docs.google.com/uc?authuser=0&id=0B_kkwi64gdF7S2RYQzZYbkRReUU&export=download)

I hope anyone can figure out what those files represent. I'm mostly interested in the models and textures, but any progress would be cool, because I'm not that good at that topic either 
Thanks
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-18T17:29:05+00:00
- Post Title: Crazy Machines 2 - fst?

could not figure out the mesh - what I got looks like uvs:



SwitchButtonBaseMesh.JPG (140.67 KiB) Viewed 47 times
## Post #3
- Username: iUltimateLP
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 11, 2014 12:24 am
- Post datetime: 2015-10-19T08:14:15+00:00
- Post Title: Crazy Machines 2 - fst?

> Reply from shakotay2
>
> could not figure out the mesh - what I got looks like uvs:
Well thats interesting, I think you got those from the FTexture folder?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-19T09:31:33+00:00
- Post Title: Crazy Machines 2 - fst?

nope, the texture is.
The uvs are from from SwitchButtonBaseMesh in the FMesh folder.
