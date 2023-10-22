## Post #1
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-30T15:07:05+00:00
- Post Title: How to detect raw ADPCM.

Ive ran some tests too analyze how different adpcm looks like,
and the conclusion is that all of them almost looks the same,
its just small differences, depending on the encoder.
(you have to see the data thru Points though, instead of the usual
line drawing most sample analyzers have, to detect this pattern.)

so, if you have an audio file with no header, that cannot be playedback
normally (like PCM), and it looks like the below picture, you most certain
are dealing with ADPCM Data.

Ive ran scans with MS-ADPCM, IMA ADPCM, Sony VAG, and then
one unknown music file from a game i had, and then i came to the conclusion
that it is actually possible to see if the data is ADPCM.
(something i didnt think was possible without actually trying to decode it).
[adpcm.gif](https://xentaxbackup.github.io/file/834_adpcm.gif)
## Post #2
- Username: FunteX
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 20, 2006 5:45 am
- Post datetime: 2006-08-30T15:31:07+00:00
- Post Title: How to detect raw ADPCM.

can you post some pictures of the analysis?

this topic sounds interresting...
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-30T15:47:21+00:00
- Post Title: How to detect raw ADPCM.

FunteX: I did, but you must be logged in to view them, but i will post some more of them now.
[imastereo.gif](https://xentaxbackup.github.io/file/835_imastereo.gif)
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-30T15:48:10+00:00
- Post Title: How to detect raw ADPCM.

weehaaa
[adpcm_mono.gif](https://xentaxbackup.github.io/file/836_adpcm_mono.gif)
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-30T18:32:27+00:00
- Post Title: How to detect raw ADPCM.

Interesting way of looking at this! Now for an interpreter that can read the format of the waves, and pinpoint the type of file format used?
## Post #6
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2006-08-30T23:04:41+00:00
- Post Title: How to detect raw ADPCM.

Just use Cool Edit Pro or any other advanced audio editor and you can load any sound file without a header.
## Post #7
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-31T06:00:11+00:00
- Post Title: How to detect raw ADPCM.

brienj: I think Mr.Mouse meant a scanner that detects automatically if
the data is ADPCM =D. that would be a bit harder though !
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-08-31T11:02:11+00:00
- Post Title: How to detect raw ADPCM.

looks nice
## Post #9
- Username: jpagac
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 18, 2006 5:10 am
- Post datetime: 2006-10-17T21:18:29+00:00
- Post Title: How to detect raw ADPCM.

I have some adpcm audio I'm trying to play.  Cooledit doesnt work.  I dont think its a standard format.  How can i decode it?
