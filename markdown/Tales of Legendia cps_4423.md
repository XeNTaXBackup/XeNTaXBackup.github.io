## Post #1
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2010-05-04T01:11:09+00:00
- Post Title: Tales of Legendia cps

Any clues as to how to parse these files?
[map_pic_000.mcd.rar](https://xentaxbackup.github.io/file/3006_map_pic_000.mcd.rar)
## Post #2
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-05-04T09:10:16+00:00
- Post Title: Tales of Legendia cps

it's well compressed...it seems some LZSS variation
## Post #3
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2010-05-05T05:50:00+00:00
- Post Title: Tales of Legendia cps

Guess you're right
the header if the CPS seems to be

struct
{
   char[4] id; //always "CPS"
   int filesize; //size of the CPS file header + data
   int deflated size; //size of the uncompressed data
   int padding; //always 0
}

followed by the compressed data//
## Post #4
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-05-05T07:32:16+00:00
- Post Title: Tales of Legendia cps

yeah, the best thing you could do is to find the same file in a savestate because it will be decompressed and comparing it to the compressed one could bring us to the algo.
## Post #5
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2010-05-05T19:01:19+00:00
- Post Title: Tales of Legendia cps

I tried a generic Lzss algo on the compressed data and this was the result. It seems to be working as the expected filesize match trying to varify now if the uncompressed data is a swizzled image of an apple icon.
[menu_pic_item_apple.rar](https://xentaxbackup.github.io/file/3009_menu_pic_item_apple.rar)
## Post #6
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2010-05-06T03:22:40+00:00
- Post Title: Tales of Legendia cps

Ok one of the lzss compress algorithms posted on this site actually seemed to worked   

I did a test with a one of the lzss compressed battle.mid and I was able to get a playable midi in winamp and then in all players
if I remove the first 64 bytes which seems like game file header info.
[TOL_lzsstest.rar](https://xentaxbackup.github.io/file/3010_TOL_lzsstest.rar)
## Post #7
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-05-06T08:38:44+00:00
- Post Title: Tales of Legendia cps

very nice. Thank for the info, it will be useful for romahackers
