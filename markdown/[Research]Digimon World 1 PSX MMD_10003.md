## Post #1
- Username: Romsstar
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 03, 2012 6:30 pm
- Post datetime: 2013-01-03T12:30:47+00:00
- Post Title: [Research]Digimon World 1 PSX MMD

The PSX Game "Digimon World 1" uses MMD as a 3D Model Data Format.
I will try to research this format to build an extractor/viewer that reads the vertex+animation data.
Anyone who can help is appreciated.

from what I've seen so far in the uploaded sample

Agumon.MMD

HEADER
0x00         08 ->  What this number is about I can't figure out yet. It is always the same in every file.
0x01         00
0x04	       F44F -> An offset in little Endian. 0x4FF4 doesn't belong to the TMD part anymore and SEEMS to hold animation information.
0x06	        00
0x08	        41 -> Version of TMD
0x10		10 -> Number of Objects in the File.
Header End

-> This is presumably the Header so far. It seems light a slightly modified version of TMD and the key to solving it seems to me is figuring out what that offset at 0x04 is about.

Issues: When removing everything up to the version of the TMD we can perfectl import the file as a TMD in Milkshape. 
But every object gets the same coordinate making everything stored at 0,0,0 in 16 separate objects in this case.
[AGUM.rar](https://xentaxbackup.github.io/file/6110_AGUM.rar)
