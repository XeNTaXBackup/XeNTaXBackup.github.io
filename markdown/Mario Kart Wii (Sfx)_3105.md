## Post #1
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2008-07-29T00:21:35+00:00
- Post Title: Mario Kart Wii (Sfx)

Took a look at the brsar's of Mario Kart to find these audio files. I don't know anything about Nintendo audio files what so ever. All contain "RWAV" as first 4 chars. File also looks similar to a standard .wav. Anyone have any insight or experiences with Nintendo audio?
[MarioKart.zip](https://xentaxbackup.github.io/file/1599_MarioKart.zip)
## Post #2
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-07-31T16:46:47+00:00
- Post Title: Mario Kart Wii (Sfx)

> Reply from Silver
>
> Took a look at the brsar's of Mario Kart to find these audio files. I don't know anything about Nintendo audio files what so ever. All contain "RWAV" as first 4 chars. File also looks similar to a standard .wav. Anyone have any insight or experiences with Nintendo audio?This format isn't related to the Microsoft Wave format at all, but it still looks pretty simple, so it's just a matter of figuring out what audio codec it uses. I am not familiar with Nintendo's audio codecs at all, but there must someone who is (I'd like to be educated!  ).
## Post #3
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2008-08-01T07:40:49+00:00
- Post Title: Mario Kart Wii (Sfx)

The format looks like a expanded version of Nintendo DS WAV (SWAV).
[http://kiwi.ds.googlepages.com/sdat.html#swav](http://kiwi.ds.googlepages.com/sdat.html#swav)

Big endian byte order.

RWAV (first) block:

> 4 bytes - "RWAV" (Revolution WAV?)
>
> 4 bytes - Magic (0xFEFF0102).
>
> 4 bytes - Filesize
>
> 4 bytes - Size of this structure
>
> 4 bytes - Number of blocks
>
> 
>
> {for each block}
>
> 4 bytes - Block offset
>
> 4 bytes - Block size
>
> {/for each block}

INFO (second) block (NOT sure about this, since I haven't heard the audio, so I don't know).

> 4 bytes - "INFO" (Information)
>
> 4 bytes - Size of this structure
>
> 1 byte * 4 - Unknown (probably the first byte is the codec)
>
> 4 bytes - Frequency (Hz)
>
> 4 bytes - Bytes per channel, decoded to PCM (this would mean that uses 4-bit ADPCM).
>
> Anything else - No idea.

DATA (third block)

> 4 bytes - "DATA"
>
> 4 bytes - Size of this structure
>
> Remaining bytes - Encoded audio (probably with some Nintendo codec).
