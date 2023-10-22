## Post #1
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2016-09-15T07:19:13+00:00
- Post Title: Divinity Original Sin 2 .pak Files

While waiting for the official modding tools, I thought about some DOS2 datamining.

The extractor I posted in the other thread about DOSEE works, in extracting the files.

As of now, Icon textures are DDS and all audio is, sadly, .wem - wwsise galore, disaster.

Textures:
Icons are apparently stored in mammoth files, 64x64 being the maximum icon size, painted over an alpha channel.

Concerning weapons and armor, apparently the highest size is 1024x1024. 
At the highest level, armor textures are split into 3 types, identified by a suffix: _DM (I guess it's diffuse map) _NM (I guess it is normal map, but they are weird: yellow or blue, different from the purple of Bethesda or grey of Dragon Age) and _SM (I assume it's specular mask 

Weapon textures are more complicated: they either follow the above scheme (with some weapons lacking a normal map, like the Elven dagger) or featuring the suffix _PM and _BM, which I have absolutely no ide what they could mean.

Icon, weapon and armor textures are .dds with mipmaps.

I am keeping a parallel [thread](http://larian.com/forums/ubbthreads.php?ubb=showflat&Number=585574#Post585574) at the Larian forums here, will try to sync them.
## Post #2
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2016-09-16T07:05:54+00:00
- Post Title: Divinity Original Sin 2 .pak Files

Audio: as said before, all audio files are .wem (RIFF WaveFMT, some information can be viewed via RIFFpad).

Soundbanks, as expected, are .bnk format.

Before doing the usual ww2ogg route, I wonder if someone knows a reliable way to read .wem / .bnk file structure or metadata (specifically, loop points) as RIFFpad is old (16 years) and tends to be useless nowadays.
