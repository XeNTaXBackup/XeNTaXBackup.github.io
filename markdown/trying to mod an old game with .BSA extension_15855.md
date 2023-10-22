## Post #1
- Username: BatmiteReturns
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 26, 2017 8:56 am
- Post datetime: 2017-02-10T09:08:50+00:00
- Post Title: trying to mod an old game with .BSA extension

Sorry I don't know where else to post this so I thought I would do it here since you guys seem to know a whole lot. As many of you know I am a huge bowling video game fan. I am trying to re-skin PBA Bowling 2 for windows XP. This game was made by Bethesda and all of the data files are in.BSA format. I googled that format and found a utility that was used for later games released by the software company called the bethesda Software extractor but it only works with newer games and not one that is this old. This game came out in 1999 I believe. Any help would be greatly appreciated. Thanks a lot

download.cnet.com/PBA-Bowling-2-demo/3000-2117_4-10034625.html

here is the demo
## Post #2
- Username: cxt
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 20, 2014 10:20 pm
- Post datetime: 2017-03-05T12:57:03+00:00
- Post Title: trying to mod an old game with .BSA extension

This is an [QuickBMS script](http://forum.xentax.com/viewtopic.php?f=13&t=4450).

unpbabsa.bms

```
# (c) CTPAX-X Team 2017
# http://www.ctpax-x.org/

ImpType Standard

Get HeadSize Long
Get FileCount Long

For I = 1 To FileCount
  Get FileNamePos Long
  Get FileSize Long
  Get FileOffs Long

  SavePos TOC

  Math FileOffs + HeadSize
  Math FileOffs + 8
  Math FileNamePos + 8
  GoTo FileNamePos
  Get FileName String

  Log FileName FileOffs FileSize

  GoTo TOC
Next I
```
