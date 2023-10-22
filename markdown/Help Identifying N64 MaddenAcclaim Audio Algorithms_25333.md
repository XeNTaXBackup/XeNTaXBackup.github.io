## Post #1
- Username: SubDrag
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 23, 2015 8:49 pm
- Post datetime: 2022-05-08T14:41:21+00:00
- Post Title: Help Identifying N64 Madden/Acclaim Audio Algorithms

I've successfully decoded the audio, but don't know the algorithm.  I think EA Formats are mostly known, just not matching up which it is...can someone identify what they are?  The audio for Madden uses cos/sin, which made me curious.  Acclaim's is some kind of unique voice compression and is labeled "DEAN".

N64 Madden 99-2002 Floating Point algorithm of some kind
[https://github.com/jombo23/N64-Tools/bl ... .cpp#L1752](https://github.com/jombo23/N64-Tools/blob/master/N64%20Sound%20Tool/N64SoundListToolUpdated/N64SoundLibrary/MaddenAudioDecompression.cpp#L1752)

N64 Acclaim DEAN (MARK format is there too, but rather simple from last sample/predictor set):
[https://github.com/jombo23/N64-Tools/bl ... n.cpp#L900](https://github.com/jombo23/N64-Tools/blob/master/N64%20Sound%20Tool/N64SoundListToolUpdated/N64SoundLibrary/AcclaimDEANAudioDecompression.cpp#L900)
