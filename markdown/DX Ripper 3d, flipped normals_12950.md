## Post #1
- Username: buddygz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 15, 2015 9:49 am
- Post datetime: 2015-06-15T02:18:31+00:00
- Post Title: DX Ripper 3d, flipped normals

I know this is an ongoing unavoidable problem with dx ripper, but i have seemed to have tried everything in the book to fix it.
I am ripping levels/scenes from the gamecube version of Sonic Adventure DX using dolphin and DX Ripper 3d, because it is the only ripper that seems to work consistently.
(I understand there are level rippers for the pc version, but they don't rip all of the models and architecture i need, and are missing a lot of key components).
While the models it rips seem to be complete, the some of the surface normals are ripping flipped, including very small details, leaving large black holes throughout the mesh.


 I am using 3ds max 9 to import the frames, in order to take advantage of the 3dr plugin, but i have access to pretty much any modeling software.
I have tried everything, from 3ds max's unify normals/flip normals, modifier, to blender's recalculate normals feature, to importing two seperate meshes, flipping all of the normals on one, and combinding the two, but it doesn't seem to fix alot of the holes.

I would flip each normal surface one by one, but it would take FOREVER on a lot of the smaller objects.
I know that the mesh is importing in full, because when i render "flat" to my viewport, its full:


also, when i disable culling in unity (where i am using these levels, for personal use, not commercial), the model is full, but because of the way lighting and normals work, the mesh becomes uneven in its lighting, AKA BAD lighting. it looks terrible.

I guess i am asking, is there ANY thing i can do to fix my rips/rip correctly?
I am using the newest version of dx ripper, along with both the newest dolphin (that uses x86 versions of windows) and a rev6115 version of dolphin, both rendering in dx9.
is their a plugin or maxscript that i am missing that can fix this? a different, better ripper?(i have tried ninja and 3dvia, both with problems)
is there anything i can do?
