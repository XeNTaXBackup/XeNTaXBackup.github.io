## Post #1
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-12-28T15:18:51+00:00
- Post Title: Phantasy Star Collection [Saturn] (*ADP)

One of the features of this collection was re-arranged music for Phantasy Star I-IV. And it would be totally great to be able to listen to it.
The music is no longer in MIDI format how it was in originals. The format they used is ADP, and for example Phantasy Star 2's soundtrack consists of 25 ADP tracks, 52mb total. 
From the scarce info I found it looks like the format has something to do with CRI ADX or at least was made by CRI MiddleWare.
ADP is present in some Sega Saturn and Dreamcast titles. 

I've seen some mentioning of it on the web but there doesn't appear to be any sort of decoder/converter for it. 

The search lead to this tool: ACPK2AVI (ACPK2AVI Helper1.02)
[http://www.vector.co.jp/soft/dl/win95/art/se061882.html](http://www.vector.co.jp/soft/dl/win95/art/se061882.html)
It suppose to be able to convert Saturn ADP, and its menu shows the support for *.CPK/*.ADP, but it just doesn't
do anything to those ADP files.

Then there's this forum thread: [http://www.gamingforce.org/forums/behin ... post755495](http://www.gamingforce.org/forums/behind-music/40580-sega-saturn-p16-files.html#post755495)
Where he also mentions ACPK2AVI, but comes to a dead end.

A small insight here: [http://hcs64.com/mboard/forum.php?showthread=26331](http://hcs64.com/mboard/forum.php?showthread=26331)

Here are a couple of samples:
BGM_8AA.ADP
BGM_8BA.ADP
[http://www.sendspace.com/file/3djejx](http://www.sendspace.com/file/3djejx)
Please take a look.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2013-01-02T06:49:22+00:00
- Post Title: Phantasy Star Collection [Saturn] (*ADP)

It is headerless CD-XA. This is supported in vgmstream with the .xa extension.

I don't know this music too well, vgmstream defaults these files to 44100 Hz, but it seems like 37800 Hz (a more standard XA rate) might be more appropriate.
## Post #3
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2013-01-04T11:44:19+00:00
- Post Title: Phantasy Star Collection [Saturn] (*ADP)

Thanks a lot for your help, hcs. The solution turned out to be very simple. 

I'm not sure if 44100 Hz or 37800 Hz is more appropriate for this music, it sound about right either way. One thing is that in the original Genesis version of Phantasy Star II the music was slightly altered between Japanese and US/Europe releases.
The comparison sample is here: [http://tcrf.net/Phantasy_Star_II](http://tcrf.net/Phantasy_Star_II) 
It's the same tune as BGM_8BA.ADP, which I provided in the 1st post. 

Also I thought the music was suppose to be re-arranged for this Collection but it sounds the same as 16-bit Genesis counterpart. Maybe I misunderstood something but wiki said this: 
> Omake features were also included with the game, such as exclusive arranged music, art galleries, and Japanese commercials.[http://en.wikipedia.org/wiki/Phantasy_Star_Collection](http://en.wikipedia.org/wiki/Phantasy_Star_Collection)

It doesn't appear to be re-arranged as, for example, it was in remakes Phantasy Star Generation 1 & 2 [PS2]. But still, it's good to keep for collection purposes.
