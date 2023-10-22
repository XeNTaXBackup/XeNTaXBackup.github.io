## Post #1
- Username: Aeternal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 28, 2016 9:54 am
- Post datetime: 2017-05-02T22:29:00+00:00
- Post Title: Phantasy Star Universe - .nbl TMLL

Alright so, many of PSU's files are compressed in the .nbl archive format. Currently, thanks to essen, we can extract files from them. However, the file contains two headers, NMLL and TMLL. 
The tool he created extracts only the NMLL header leaving the TMLL data behind. What hides behind the TMLL header? My guess is that it is texture data. When extracting models from the archive you get the model and what I assume is the texture and particle data with it (models are .xnj's, textures are .xnt's, and data switches .xna's (some models instead come with particle data .xnv's)). Now I have only just begun researching the model's for the game and have succeeded. Problem is, now that I have the models, I need the textures. When extracted, the .xnt's display index data of the textures used on the model in .xvr format (PSOBB). However, the actual texture data is missing from them since we can't extract the TMLL data. Can anyone look into the .nbl format once more?

Essen's gasetools: [https://github.com/essen/gasetools](https://github.com/essen/gasetools) (.nbl)

Sample file: [https://mega.nz/#!EwUCGaiZ!ukvEdbr_LXMw ... vqgRW822QU](https://mega.nz/#!EwUCGaiZ!ukvEdbr_LXMw_ReR8gxvl5EHqvYdDnyqnvqgRW822QU)
