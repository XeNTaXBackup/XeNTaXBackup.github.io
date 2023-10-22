## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-07-20T05:34:27+00:00
- Post Title: Atelier Iris - Eternal Mana PCM files

Here's a sound file that I've been trying to play, but all options of playing it as raw sound has failed, getting mostly static. I get some voices but that's all I get.

Here's an example of one of these PCM files.
[AI1_VP1.VP.rar](https://xentaxbackup.github.io/file/2210_AI1_VP1.VP.rar)
## Post #2
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-07-21T01:07:23+00:00
- Post Title: Atelier Iris - Eternal Mana PCM files

Isn't this just PS2 ADPCM? It decodes fine in PSound.
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-07-21T04:04:29+00:00
- Post Title: Atelier Iris - Eternal Mana PCM files

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-07-21T19:34:54+00:00
- Post Title: Atelier Iris - Eternal Mana PCM files

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-07-21T20:17:54+00:00
- Post Title: Atelier Iris - Eternal Mana PCM files

> Reply from Zench
>
> It could possibly be interleaved in a strange way...

Hm... this is the format used for the game music.
## Post #6
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-07-29T10:21:21+00:00
- Post Title: Atelier Iris - Eternal Mana PCM files

yep its interleaved - pcm16bit little endian - interleaving is 200

Cut the header (the first 2048bytes) then you can open the file via MFAudio player -> freq:48000, interleave 200, stereo
