## Post #1
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2010-03-31T07:47:12+00:00
- Post Title: Champions Online FSB4

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-03-31T11:05:02+00:00
- Post Title: Champions Online FSB4

Try fsb_mpeg ( [http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html) ).  I just tried the file you posted with 0.9:

```
fsb_mpeg.exe 3.fsb -p 4
```
FSB can have MPEG audio with varying padding applied to the frames, and sometimes the padding has bogus MPEG headers in it, which throws off decoders. fsb_mpeg deal with this (though you sometimes need to give it the padding explicitly, thus the -p 4 option here).

... although the padding doesn't seem to matter at all for this file, just extracting the data with the padding intact (as in the mp3 you provided) seems to work as a normal MP3.  If your decoder didn't work with that it's because it has trouble with frame syncs.
## Post #3
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2010-04-03T08:18:29+00:00
- Post Title: Champions Online FSB4

Problem solved. Some work with and without the padding option, like you said. But all is well. Thank you for the help.
