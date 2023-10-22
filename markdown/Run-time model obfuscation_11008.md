## Post #1
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2013-12-01T00:27:58+00:00
- Post Title: Run-time model obfuscation?

Is this sort of thing possible? I've managed to load models from Driver: Parallel Lines, but no words can describe the shock that came to me when I saw THIS:






Apparently this is something that happens when you try to rip models from the game. I've cleaned out the model format 100% and know every little bit of information, so it's not something in there. The only other thing that exists really is a "GPU Shader", and there's one for every car/character in the game. I've found that regular objects, such as building interiors, do not have this kind of strange obfuscation. Those are objects that do not have any form of obfuscation.

So my question is, can you manipulate models in real-time with DirectX shaders that modifies the scale before rendering it? The cars share similarities in the parts being obfuscated, so maybe it's as easy as scaling every nth specific model? I really don't know. All I know is this is absolutely bizarre, and apparently exists in other games found on the Wii. I have yet to load any models from these as they are big-endian, but the model format is very similar.

Thanks to any of those who can help.
