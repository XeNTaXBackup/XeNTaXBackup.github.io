## Post #1
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2010-12-30T11:13:58+00:00
- Post Title: Oddworld Abes Oddysee - .LVL files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-30T13:47:23+00:00
- Post Title: Oddworld Abes Oddysee - .LVL files

only had a few minutes, which wasn't enough to write a script

```
uint 0
char blockid - "Indx"
uint 0
uint fileheaders
uint sectorsPerChunk (chunksize / 2048)
uint 0
uint 0

for each fileheaders

  char filename[12]
  uint sectorindex ( *= 2048 to get pos )
  uint sectorsused ( number of 2048 sectors used )
  uint realsize    (size of data)


blocks are handled differently

typically contain the realsize (uint64?) and the blockid

```
## Post #3
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2010-12-31T15:47:01+00:00
- Post Title: Oddworld Abes Oddysee - .LVL files

> Reply from StarQuake
>
> Could someone write me a QuickBMS script for Abes Oddysee .LVL files? I only need to be able to extract and reinsert the .VH and .VB files from them.

Hi, try these tools. 

 odd_tools.zip
(106.39 KiB) Downloaded 58 times
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-31T17:26:27+00:00
- Post Title: Oddworld Abes Oddysee - .LVL files

> Reply from merlinsvk
>
> Hi, try these tools.

Please consider updating the wiki page for this format: [http://wiki.xentax.com/index.php/Oddwor ... ddysee_LVL](http://wiki.xentax.com/index.php/Oddworld_Abes_Oddysee_LVL)
## Post #5
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-01-01T01:31:04+00:00
- Post Title: Oddworld Abes Oddysee - .LVL files

WRS, I can't. I'm not the tool's author, but I finally found author's forum topic. And it's still active   [http://www.oddworldforums.net/showthread.php?t=15680](http://www.oddworldforums.net/showthread.php?t=15680)
## Post #6
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2011-01-01T03:05:28+00:00
- Post Title: Oddworld Abes Oddysee - .LVL files

Whoops, I should have paid more attention, I'm following that topic. I must have overlooked this tool but thanks for the help anyway guys, If you want I'll ask the author to add to the wiki.
