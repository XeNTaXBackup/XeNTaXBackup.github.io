## Post #1
- Username: herbalist
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 08, 2018 9:46 pm
- Post datetime: 2020-01-10T15:51:41+00:00
- Post Title: Koei Tecmo WBH/WBD Audio Containers

Koei Tecmo's engine uses a special audio container with the SED file extension (despite having a WHD magic)
This is a simple binary container for two files, a WBH and WBD magiced file.
The WBH has data commonly found in audio headers, but is dependent on a sub magic to determine the file type. WBD has the audio stream data. So I know how to get wbh, and wbd files from the .sed container however I need help figuring out how to reconstruct the audio header for the sound samples contained within.

The following link has 4 sed container samples with WBH/WBD data from Dissidia Final Fantasy NT PC, with the KWB2 subtype.
[https://mega.nz/#F!rJsE2KYT!LR1mUebfI_tNg4rTP1qpng](https://mega.nz/#F!rJsE2KYT!LR1mUebfI_tNg4rTP1qpng)

If anyone can help me out, it would be greatly appreciated!
