## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2016-03-03T02:38:23+00:00
- Post Title: FMOD .bank format

New format variant, which has FSB/FEV-like data in one container with single RIFF header. Found in Defunct, Flame In The Flood.

First block is FEV-like data, second is FSB5 header data

fsbext thinks its encrypted, fsb_aud_extr|fmod_extr cant handle them. 

Samples - [http://www.multiupfile.com/f/f15b3e8a](http://www.multiupfile.com/f/f15b3e8a)

Interesting in extracting.
## Post #2
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2016-03-03T11:06:07+00:00
- Post Title: FMOD .bank format

Use [fsb5 dumper](http://zenhax.com/viewtopic.php?p=6506#p6506) to get valid fsb file and then fsb_aud_extr to get playable .wav's.
