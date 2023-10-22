## Post #1
- Username: SillyWills
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 22, 2016 2:26 pm
- Post datetime: 2019-06-08T12:33:55+00:00
- Post Title: Guilty Gear PCK files (PS2)

I made a [thread](https://zenhax.com/viewtopic.php?f=6&t=11536) about this over at ZenHAX, but I figured I'd ask here, too. I'd like to extract the music archives for a couple PS2 entries of the Guilty Gear series, but I've had no luck so far. I posted the cut file data over at the ZenHAX thread, to help get an idea of what we're working with. Thanks in advance to anyone who can lend a hand!
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-08T16:39:20+00:00
- Post Title: Guilty Gear PCK files (PS2)

The audio in all those files in your attachment are 16-bit PCM (Little Endian), stereo, 44100 Hz, interleave 0x200

Each file is about 12 seconds long, so there must be some sort of index to be able to play them correctly.
## Post #3
- Username: SillyWills
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 22, 2016 2:26 pm
- Post datetime: 2019-06-08T20:34:17+00:00
- Post Title: Guilty Gear PCK files (PS2)

^Thanks for the info! Hm, so if some sort of index is needed, I'll give the games' data another comb-over. Would the IRX files suffice, maybe? Whatever I find, I'll post later.
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-08T21:48:41+00:00
- Post Title: Guilty Gear PCK files (PS2)

It's a tricky one this.  I've checked the files on the Isuka disc.  The MUSIC.PCK file is mostly raw PCM audio, but there are a few bits in it which look like small bits of data, so it's not just a pure audio file.

There are what looks like some tables in SLES_532.84, but I can't find anything that looks like it would match up with the .PCK file.  The table could also be stored somewhere inside the large .BIN file.

Once the table is found, it should be easy to then extract the individual music tracks.  I'll keep looking to see what I can find in the data.
