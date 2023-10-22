## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-03-29T07:13:16+00:00
- Post Title: EA codec type 0x19 in Battlefield Hardline

I recently took a quick look at BF Hardline beta, and it has about 3000+ audio files, most of them in XAS ADPCM, but they also have 4 files with codec ID = 0x19, which is also seen in 2012 post about FIFA. They have an interesting repeating pattern in the middle. Any ideas about that codec since then?

----------------------------
EA codec types
----------------------------
2 - PCM
3 - Xbox XMA
4 - XAS ADPCM
5 - EALayer3 MPEG Layer 3
6 - EALayer3 variant 2
7 - EALayer3 variant 3
----------------------------
and the same with B header:
----------------------------
12 - PCM
13 - Xbox XMA
14 - XAS ADPCM
15 - EALayer3 MPEG Layer 3
16 - EALayer3 variant 2
17 - EALayer3 variant 3
19 - ???

Here's the start of a normal chunk, which has 0x1983 samples encoded to 0x238 bytes


And here's a silent chunk, which has 0x1900 samples encoded to only 0xA8 bytes
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2015-04-03T15:07:17+00:00
- Post Title: EA codec type 0x19 in Battlefield Hardline

Speex codec and that pattern has nothing to do with the codec on particular
