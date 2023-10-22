## Post #1
- Username: Conniethacontour
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 03, 2021 2:07 pm
- Post datetime: 2022-09-14T03:32:30+00:00
- Post Title: Looking for help with some .DSP Audio formats

Hello! Ive been researching and "attempting" to understand this old games audio file formats, the title is Gladius by LucasArts for GC in particular. What ive gathered so far is that it uses scripts for handling the audio files that are .Flo files, they act as a translator of sorts for the games engine - to the audio files themselves. They audio files are a mixture of a .dsp .ds2, and .dsb files for the most part there are a few others as well. The .dsp's seem to fit that standard .dsp formating from what i can tell so far, currently ive been trying to understand the .ds2 files which are a "special" format of .dsp's from what ive gathered, i replaced one of the .ds2 files with a custom audio file that was just a standard .dsp and it does work in game but not correctly, the left channel starts outputting the end of the song first, as to the right channel starts at the actual correct point. I was hoping someone here may have some info on these .ds2 files, they appear to be possibly be a "mono" track that gets played like stereo, i was able to open them using a version of audacity that has GC DSPADPCM support, they show as 32khz mono. I exported one of them as a standard .dsp from audacity with matching audio properties and see that it is half the size of the original so its possible its truly a stereo file and audacity is just interpretting it incorrectly. Apologies in advanced im not particularly informed on audio codecs and how they operate so im sorry if my information above is not helpful.
