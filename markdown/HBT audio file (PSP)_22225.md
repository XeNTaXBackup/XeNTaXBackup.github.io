## Post #1
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2020-06-01T00:00:13+00:00
- Post Title: HBT audio file (PSP)

From a PSP game, the /sound folder had 2 types of files, at3 (bmg, already playable via vgmstream) and this one.
Does anyone know if there's any audio inside? looking at it via hex editor the format looks kinda strange.


 hbt.zip
samples (243.64 KiB) Downloaded 19 times
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-06-01T11:37:49+00:00
- Post Title: HBT audio file (PSP)

The whole file is split into various chunks.  

Offset 0 contains the start of the first set of chunks.
Offset 4 contains the start of the audio data section (in Playstation ADPCM format)
Offset 8 contains the start of the second chunk.

I'm not sure what most of the chunk data is, but the "PPVA" chunk stores the offsets and sizes of the audio files within the audio data section.
