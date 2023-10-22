## Post #1
- Username: soullessita
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 01, 2022 8:55 pm
- Post datetime: 2022-10-01T13:10:20+00:00
- Post Title: Export back SKN and SKL file from blender (Leauge of Legends)

Hi guys, I've been trying to mod one of the base model for a League of Legends character.
The process so far has been smooth.

I export the base file from league with Obsidian and than used lol2gltf to have a gltf file to work with in blender (the file contains everything, mesh, skeleton, animations).
With the base model as reference I was able to made a new sculpt -> retopo -> uv/textures it.
I kept the base SKL and match it with my own (new) low poly model. I removed some bones because I didn't really need stuff like hairs (the model is wearing a hoody) or tail.
I fixed the weight and from the animation window my model run smoothly with no weird artifacts at all. Amazing.

Now. I already convert things like textures and load screen in DDS with photoshop/nvidia plugin.
My only problem here is export the model (and the updated skeleton, since is with less bones than the original) back to SKN and SKL.
I did try to export by FBX from blender with betterFBX addon, and importing it on Maya 2023 with lol_maya plugin (2023 version).
The problem is that when I try to export with Maya to SKN I got an error message over the weight (specifically says "Mesh contains 1255 vertices that have weight on 4+ influences").

Unfortunately I don't really work with Maya but I'm more a Blender user.
Is there any way to export things in Blender instead...? As I don't really know what is the problem with Maya or how to fix it...
I wont really mind drop a donation for the user which provides a working tool to do so.
