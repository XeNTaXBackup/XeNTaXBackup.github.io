## Post #1
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2014-05-25T19:02:49+00:00
- Post Title: Bound by Flame (PC) *pgz

The game's data containers turned out to be no problem, simply renamed SPK to RAR and all good. Unfortunately audio isn't solved by renaming to ogg or mp3 or something :>
All files in music folder are with *pgz extension. I scanned them with a couple of scanners but came up with nothing. 

Here's a sample, please take a look: [NVM]

EDIT: Bah, turns out PGZ can be renamed to ZIP and also extracted further, which gives a file with no extension. And then simply renaming it to OGG does the trick. Solved.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-05-26T10:27:18+00:00
- Post Title: Bound by Flame (PC) *pgz

The SPK archives are just 7zip archives.

The PGZ files are just compressed with GZip. Use VGMToolbox to decompress and you will get the filenames
## Post #3
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2014-05-26T18:44:44+00:00
- Post Title: Bound by Flame (PC) *pgz

Yep I just went more old fashioned way without using VGMtoolbox. The end result still had proper filenames, it just didn't have any file extension at all. And the way I found out it was Ogg is by looking through Hex editor (in which I'm no expert at all) - the first couple lines of text said something about Ogg, so I thought "why not?".
