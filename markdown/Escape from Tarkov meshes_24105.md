## Post #1
- Username: Vertex88
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 05, 2018 7:28 pm
- Post datetime: 2021-06-24T09:38:27+00:00
- Post Title: Escape from Tarkov meshes

I tried to export the mesh "weapon_glock_glock_17_gen3_9x19_LOD0" using [AssetsBundleExtractor_2.2stableb](https://community.7daystodie.com/topic/1871-unity-assets-bundle-extractor/) and got the error "Unable to read the mesh asset! (Unknowing asset format)". It doesn't matter if I choose "Export to .dae" or "Export to .obl".
This problem occurs not only with the Glock 17 mesh, but also when exporting meshes of any other weapon. All weapon modules and all textures are exported without problems.
I would appreciate any advice on how to get the weapon mesh.

Here are the bundle files that contain the Glock 17 mesh - [https://mega.nz/folder/eZ4ghAhQ#Je0wKuxuuw9y0YDDTqC8rg](https://mega.nz/folder/eZ4ghAhQ#Je0wKuxuuw9y0YDDTqC8rg)
## Post #2
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2021-06-29T22:48:08+00:00
- Post Title: Escape from Tarkov meshes

Use [AssetStudio](https://github.com/Perfare/AssetStudio/releases), it can extract meshes and animations.



print.png (100.61 KiB) Viewed 126 times
## Post #3
- Username: Vertex88
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 05, 2018 7:28 pm
- Post datetime: 2021-12-15T21:52:00+00:00
- Post Title: Escape from Tarkov meshes

> Reply from reh ↑Wed Jun 30, 2021 6:48 am at Wed Jun 30, 2021 6:48 am
>
> 
Use AssetStudio, it can extract meshes and animations.

Hey, reh! I really hope you come back to this topic. 
First of all I want to thank you for the advice on how to get the weapon meshes. It helped me a lot. 
But now I have another question, how to extract animations? Could you please explain how to do this.
I can see files whose type is AnimationClip and the container is FBX. The Preview window says that this file "Can be exported with Animator or Objects". I choose the "Export selected assets" command (as I do with meshes), but the Preview window says, "Nothing exported. 1 assets skipped (not extractable or files already exist)".
Moreover, I am more interested in character animations. These are the animations I would like to extract from the file "character_animations.bundle" - [https://mega.nz/file/zJ5QXDoK#jCrKwE8zy ... hKnmBFSyVI](https://mega.nz/file/zJ5QXDoK#jCrKwE8zyzX4ehDkVDTCVOJZQ3DGsQbSphKnmBFSyVI)
[Nothing exported.jpg](https://xentaxbackup.github.io/file/21405_Nothing exported.jpg)
## Post #4
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2021-12-22T16:25:16+00:00
- Post Title: Escape from Tarkov meshes

You must select the corresponding files of type AnimationClip + Animatior in order to export the animations.
