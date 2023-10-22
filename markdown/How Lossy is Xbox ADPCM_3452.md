## Post #1
- Username: John Connor
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 21, 2008 6:16 am
- Post datetime: 2009-04-30T12:39:42+00:00
- Post Title: How Lossy is Xbox ADPCM?

I ask the above question as I have many audio files from my xbox discs which are adpcm .wavs and I know adpcm is lossy but just how lossy is it? Is it better than CBR 320 mp3 or worse?

They were quite large so I compressed tham using the FLAC codec (to preserve quality) but can I use another lossy codec that will preserve the original quality?

Any help would be highly appreciated
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-04-30T14:53:05+00:00
- Post Title: How Lossy is Xbox ADPCM?

> Reply from John Connor
>
> I know adpcm is lossy but just how lossy is it? Is it better than CBR 320 mp3 or worse?
It should compress worse than mp3 but preserve more quality I think.

> They were quite large so I compressed tham using the FLAC codec (to preserve quality) but can I use another lossy codec that will preserve the original quality?
You always loose quality if you encode using a lossy codec. Is it that important for you to have the exact same quality as the original?
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-20T13:53:27+00:00
- Post Title: How Lossy is Xbox ADPCM?

xbox adpcm compresses the original data of about 3.6 times:
xbox adpcm block: 36 bytes
uncompressed block: 130 bytes
## Post #4
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-05-23T00:43:27+00:00
- Post Title: How Lossy is Xbox ADPCM?

ADPCM means: "Adaptive Differential Pulse Code Modulation".

It is a very good compression method to reduce not audible dynamic ranges by storing differences between samples using a DEZIBEL scale. It reduces Audio-CD used 16-bit-samples to 4 bits using a standardized conversion table which is adapted to the human ear.

In my opinion don't reconvert between MP3/ADPCM. In any case you will achieve quality losses because MP3 is much worse in quality than ADPCM, especially if you use the bad compressor "LAME".

For more information look here:

[http://de.wikipedia.org/wiki/ADPCM](http://de.wikipedia.org/wiki/ADPCM)
[http://en.wikipedia.org/wiki/ADPCM](http://en.wikipedia.org/wiki/ADPCM)
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-23T11:34:09+00:00
- Post Title: How Lossy is Xbox ADPCM?

```
especially if you use the bad compressor "LAME"
```

ehmmm are you sure of the meaning of this sentence?
or you meant something else?
maybe you referred to the choosing of a particular LAME option and not to the LAME encoder which is considered the best encoder for quality.
