## Post #1
- Username: jontyc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 16, 2018 3:17 pm
- Post datetime: 2018-02-25T04:09:55+00:00
- Post Title: How to get sharedAssets into Unity w/o extraction

Hopefully someone can trigger my memory - but maybe Unity has changed. A few hours searching and trying things hasn't helped.

I used to get .unity3d bundles, decompress and extract them into three files - a .sharedAssets, a .resource and another extensionless one.

My notes from before indicated I would slap a .unity extension onto the extensionless file to make it a scene file, and copy it and the .sharedAssets to the root of a Unity project.

If I do that now, the scene file opens fine in Unity and populates the scene, but all the assets referenced by it in .sharedAssets file are missing (e.g. textures, scripts,...). So I'm thinking I made poor notes.

If I rename the .sharedAsset extension to .asset, I can then see its contents inside a container in the Unity asset folder, but the scene won't pick them up, nor can I drag them into the scene.

Any ideas?
