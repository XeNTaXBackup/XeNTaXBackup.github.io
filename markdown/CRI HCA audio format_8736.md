## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-09T23:24:33+00:00
- Post Title: CRI HCA audio format

Hello! I've just stubled upon audio files with an "HCA" identifier. They were extracted from a CRI cpk archive (Mahjongg Dream Club for X360). A look at the character distribution doesn't reveal anything because it's even.
Can anyone please take a look at this format? Here are some samples: [http://www.sendspace.com/file/pacyin](http://www.sendspace.com/file/pacyin)
Any help is appreciated!
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-04-09T23:32:15+00:00
- Post Title: CRI HCA audio format

I was just cranking through this again recently after a hiatus, but haven't gotten far yet, just finished with the header reading.  It's probably related to AAC low complexity, based on evidence for a 1024 sample frame (bytes A-B in the "loop" chunk are likely the number of samples to decode in the frame ending the loop, if there is no loop chunk it is set to 1024 in the internal structure) as well as CRI's claims of performance and quality.

This means that it is well beyond the complexity of anything I've dealt with before and it is purely speculative whether I'll actually be able to keep it together long enough to figure it out.
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-09T23:48:03+00:00
- Post Title: CRI HCA audio format

Phew, sounds nasty! I really wish you all the luck and endurance to crack it!
