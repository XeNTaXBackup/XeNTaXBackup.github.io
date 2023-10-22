## Post #1
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2021-10-29T08:53:05+00:00
- Post Title: Fallout 4 To Unreal Engine 5 Drumlin Diner, automatically ported

After I'm done tooting my own horn, I actually have some questions about NIFs, and some other stuff, any technical artist that loves Fallout and Unreal available for some brainstorming, hit me up

For a while now I poked around to find some ways to automatically port Fallout 4 Commonwealth map into Unreal Engine 5, primarily to test World Partitions feature from UE5

And it got to a point where it is technically functional, including visually, here is an example

Link to video example
[https://www.youtube.com/watch?v=Uoph3T9iW6U](https://www.youtube.com/watch?v=Uoph3T9iW6U)

The parser technically ported, or is able to port, the entirety of Commonwealth map, I'm thinking Cambridge Police Department as the next example, assuming you have some ideas about Fallout 4, and you know it's the place where you meet Danse the first time 

Anyways the technical expertise I can brainstorm about (In the unreal editor using C++, not at runtime)

Specific to NIF. In my tests I focused on Commonwealth, which is an exterior map, and I needed to port about 12,000 static meshes. About 99.5% were successful, but the rest had some problems. I used 3DS Max Nif [https://www.nexusmods.com/skyrim/mods/84041](https://www.nexusmods.com/skyrim/mods/84041) for exporting to FBX.
The meshes that failed to convert, failed in both 3DS Max Nif and Blender Nif. In Noesis, it did not fail but it rendered only one layer, see this

Perhaps someone has some ideas of how to improve any of these plug-ins, to be able to export the missing meshes properly

Some other stuff to brainstorm about, as I'm not a technical artist
-how to improve materials. e.g. figure out which material belongs to which material slot, currently my C++ code creates the basic materials correctly, because the majority of textures end with _d/_n/_s, but I can see many materials being assigned to the wrong slot in the static mesh, And then I have to manually shuffle them around, and there are about 30,000 materials 

-how to deform landscape. e.g. Some static meshes are in the correct transforms, but they don't look as anchored in the landscape compared to the original Fallout, so I'm guessing Creation Engine by Bethesda does some local deforms to snap the static meshes and the landscape together, or something like that

anything else to improve this automated port, I'm drawing a blank at the moment, I may add more later...

Well, let me know. I asked similar stuff on some other forums but if you have some ideas, I'm all ears

Thanks!
## Post #2
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2021-11-07T07:45:43+00:00
- Post Title: Fallout 4 To Unreal Engine 5 Drumlin Diner, automatically ported

Red Rocket and skeletal outfits example, automated





Video 
[https://www.youtube.com/watch?v=BfHrBS3sCok](https://www.youtube.com/watch?v=BfHrBS3sCok)
## Post #3
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2021-12-02T14:03:48+00:00
- Post Title: Fallout 4 To Unreal Engine 5 Drumlin Diner, automatically ported

All right, did some more stuff, primarily:

1. Basic materials! ~6700 of them, with diffuse, normal, specular
2. created some merged foliage actors from individual meshes in each cell, it improved the overall frame rate
Code:

```
MeshUtilities.MergeComponentsToStaticMesh(ComponentsToMerge, World, MeshMergingSettings, nullptr, nullptr, PackageName, AssetsToSync, ZeroVector, ScreenAreaSize, true);
```

The above line from the Unreal source code really saved the day when automatically creating merged foliage meshes

This is how it currently looks

the original Vault 111 Exit


the automatically recreated Vault 111 Exit


I need a tech artist to improve some stuff, so hit me up if interested. Also, we may need to brainstorm about porting Papyrus scripts to Unreal, so some philosophical discussions about an interpreter may be useful, unlikely we need a compiler
