## Post #1
- Username: Puxtril
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 24, 2018 5:13 am
- Post datetime: 2022-05-05T04:00:41+00:00
- Post Title: Warframe Animations

I've managed to fully map the data from Warframe's animation files so I can read from beginning-to-end of every file (~10 had errors), I'm confident the files are divided up properly. Problem is, I've never dealt with animation data before, so I don't know how make sense of the body data 

Animation Header

This is mostly understandable, and I've gotten the data needed from here to read the body. I've attached the binary template (struct for 010 hex editor). Here are 2 examples - StealthHit_anim.fbx has 3 skeletons and SkiffCrashRockDebris_anim.fbx has multiple UnkSkeleStructs. 

StealthHit_anim.fbx


SkiffCrashRockDebris_anim.fbx



Animation Body

This is what I'm struggling with. I've found some Matrices (equal to the amount of bones - starting position I assume), a time scale (floats increasing from 0.0 to 1.0), and some pairs of numbers. The big goal is to understand "unk" chunk of data. It's divisible by the timescale count, but other than that I have no idea. Any help is appreciated here.

This is the code for reading the body

```
{
	const AnimationSkeletonExternal& curSkel = extHeader.getSkeletons()[x];
	
	bodyReader->seek(curSkel.getFrameDataLen(), std::ios_base::cur); // Unk Data
	
	for (uint32_t y = 0; y < curSkel.getUnkSkip().size(); y++)
	{
		uint32_t curSkip = curSkel.getUnkSkip()[y];

		bodyReader->seek(curSkel.getBones().size() * 16 * 4, std::ios_base::cur); // Matrices
		bodyReader->seek(curSkel.getBones().size() * 4, std::ios_base::cur);  // Pairs
		bodyReader->seek(curSkip * 4, std::ios_base::cur); // TimeScale
	}
}

```


And the same examples again:

StealthHit_anim.fbx


SkiffCrashRockDebris_anim.fbx

[WarframeExamples.zip](https://xentaxbackup.github.io/file/22192_WarframeExamples.zip)
