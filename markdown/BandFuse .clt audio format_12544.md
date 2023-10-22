## Post #1
- Username: trojannemo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 19, 2011 12:46 pm
- Post datetime: 2015-01-26T16:10:44+00:00
- Post Title: BandFuse .clt audio format?

Has anyone come across the .CLT audio format before?
BandFuse uses it and I can't find any existing tools that seem to work with it.

The header always starts with BFAD. The files are stereo audio files, and in sizes that indicate high compression like 128Kbps MP3 or Ogg Vorbis saved with quality 1 or 2.

We know from what one of the game devs said on Twitter that they're encrypted, but have no idea what kind of encryption is used.

I'll continue to look through the binary and see if I notice anything else, but thought I'd ask on here in the offchance anyone has come across either .CLT or another audio format that uses BFAD in the header.

Thanks.
## Post #2
- Username: maxton
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 13, 2011 12:29 am
- Post datetime: 2015-04-08T04:55:35+00:00
- Post Title: BandFuse .clt audio format?

Harmonix was involved with the development of BandFuse, so it's quite possible that whatever encryption is on the .clt files would be similar to that which is used on .mogg files. I don't have a copy of BandFuse, though, so I can't check this out for myself.
## Post #3
- Username: raynebc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 15, 2016 6:07 pm
- Post datetime: 2016-05-15T10:18:36+00:00
- Post Title: BandFuse .clt audio format?

If an experienced game file analyzer has time to look into furthering Bandfuse game file analysis (audio format and file indexing in particular), I can ship a (legit) copy of the game to him/her to analyze.
## Post #4
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-05-15T21:12:08+00:00
- Post Title: BandFuse .clt audio format?

> Reply from raynebc
>
> If an experienced game file analyzer has time to look into furthering Bandfuse game file analysis (audio format and file indexing in particular), I can ship a copy of the game to him/her to analyze.
But by shipping a copy of the game to someone, you are breaking this rule:

> 3. Do not publicly share any illegal content.
or for a simplified version, "3. Do not upload or link to copyrighted materials."

So I don't think doing that will actually "help" in the process of researching files so if anyone is willing to research Bandfuse's file formats, I suggest them to pick the game themselves.
## Post #5
- Username: raynebc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 15, 2016 6:07 pm
- Post datetime: 2016-05-15T21:21:53+00:00
- Post Title: BandFuse .clt audio format?

You misunderstood.  I proposed nothing illegal, I would be shipping (notice I didn't use a term like "uploading") a legitimately purchased game.
## Post #6
- Username: maxton
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 13, 2011 12:29 am
- Post datetime: 2017-12-19T06:27:35+00:00
- Post Title: BandFuse .clt audio format?

For anyone coming here looking for a solution, I'll direct you to [BFForever](https://github.com/PikminGuts92/BFForever). I figured out the CLT encryption (AES in ECB mode with a 256-bit key), and PikminGuts92 figured out the encoding (custom container with CELT (Opus) codec).
