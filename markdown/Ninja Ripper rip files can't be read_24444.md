## Post #1
- Username: celticsamurai
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 02, 2021 2:32 pm
- Post datetime: 2021-09-02T06:34:29+00:00
- Post Title: Ninja Ripper rip files can't be read

Whenever I use the Ninja Ripper on games, I attempt to rip the models, the "all" function doesn't work so I have to use the force key. After this, the rip files cannot be read. The dds textures are fine. Is there something I'm doing wrong?
## Post #2
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2021-09-04T04:22:25+00:00
- Post Title: Ninja Ripper rip files can't be read

Well, aside of the common sense, if is a DX9, DX10 or DX11 game, if the question is related that the models are importing as broken sphere meshes, or structures instead of not even importing, you'll be needing to do a manual import at the tool of your desire(the 3DS Max plugin, or the Blender ones from Dummiesman and co.), when you switch from Auto to Manual, you will see a row of structures, 3 vertical blocks for each group, V, for vertex/vertices, N, for model normals, and TU and TV for UV map, the original order goes from [0/1/2, 3/4/5, 6/7]. but on UE4 games, the order is instead [8/9/10, 3/4/5, 11/12], other type of game and engines, like emulators which support DirectX, will suffer from the same logic, but using a different structure, so the thing, despite tedious, would be trying number values, until you would find the correct one, for importing the .rip files.
