## Post #1
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2014-10-22T11:09:46+00:00
- Post Title: Quickbms and Shadow of Mordor

first off, I'm not a bms-scriptor. end quote 

I've been working on this game lately, primarily writing batchfiles to ease export management (and some other similar stuff): see here ([viewtopic.php?f=10&t=12035&start=60](http://forum.xentax.com/viewtopic.php?f=10&t=12035&start=60)).

I was also interested to see if it could be possible to inject the embb-files back into the Arch05 files. Not that it would be important here, but I had [Watch Dogs] in mind. I had done some testing with that game, but needed some 'compressed' data info to get it going. And I thought that Quickbms could give me that info.

In short: I found what I needed, but now like to "extend" this a bit more.
Find attached a doc explaining what I did.

I just recap the questions/requests here:
1. can one redirect the "print" statement to a file (instead of screen now)
2. can one count/report the skipped chunk_blocks
3. why the difference of 8 bytes (offset address), and will it have an impact somewhere
4. can one derive the compression "settings/params" from an original compressed file
   (and not just for zlib as in this case, but also for xbox compress, lzma, etc)

thx in advance for any input,
p

UPDATE: with the help from #aluigi, I got the 'redirect' solved (pt 1.) (script added)
[SoM_Analysis.7z](https://xentaxbackup.github.io/file/8008_SoM_Analysis.7z)
## Post #2
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2014-10-31T05:25:32+00:00
- Post Title: Quickbms and Shadow of Mordor

great. thanks
