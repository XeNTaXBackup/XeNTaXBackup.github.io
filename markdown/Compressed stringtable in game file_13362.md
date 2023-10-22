## Post #1
- Username: piotruspan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 19, 2015 7:57 am
- Post datetime: 2015-09-24T20:41:22+00:00
- Post Title: Compressed stringtable in game file

I tried to get strings from game Warframe. Extracting files with Evolution Engine Cache Extractor went fine, searching for file with strings took a while but I found it: Languages.bin. Now in that file there are a lot of groups of strings. I cropped the file to small group that I could find all strings in-game.

(cropped file)
(Hex Workshop bookmarks screenshot)

I want to find a way to decrypt those strings. I can attach more languages if you want. As far as I know all strings are in UTF-8.
[en.zip](https://xentaxbackup.github.io/file/9778_en.zip)
## Post #2
- Username: xbeton0L
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Dec 16, 2011 10:40 pm
- Post datetime: 2015-09-29T14:10:11+00:00
- Post Title: Compressed stringtable in game file

It may not mean much, and my understanding only a tad limited, but I am eager to learn more about this.
## Post #3
- Username: piotruspan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 19, 2015 7:57 am
- Post datetime: 2015-11-14T15:50:08+00:00
- Post Title: Compressed stringtable in game file

According to [WFPackageParser](https://github.com/Deathmax/WFPackageParser/blob/master/Languages.cs) code the only thing that changed in file structure is that strings are now encrypted. Strings were previously separated by 0x00 (not sure if last string ended with 0x00 too). With this information I tried to find a group with all strings known to me. (/Lotus/Language/Factions/) See attachment.
[wf.zip](https://xentaxbackup.github.io/file/9804_wf.zip)
