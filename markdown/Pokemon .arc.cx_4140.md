## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-02-14T14:51:39+00:00
- Post Title: Pokemon .arc.cx

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-14T17:02:18+00:00
- Post Title: Pokemon .arc.cx

This is the new LZH8 compression that Nintendo's been using recently.  You can use my lzh8_cmpdec tools to decompress this ([http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)), like so:

```
lzh8_dec pii_1-151_387-492.arc.cx pii_1-151_387-492.arc
```
The decompressed file (pii_1-151_387-492.arc) is a U8 archive that you can probably handle with the standard U8 tools.

edit: parse-u8 seems to handle it fine.  And lzh8_cmp recreates the original file almost perfectly, only difference is the original seems to be padded to 0x20 bytes at the end.  If you're going to be editing you may have to add that padding in for the replaced files to work.
## Post #3
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2013-05-30T19:21:28+00:00
- Post Title: Pokemon .arc.cx

> Reply from hcs
>
> This is the new LZH8 compression that Nintendo's been using recently.  You can use my lzh8_cmpdec tools to decompress this (http://hcs64.com/vgm_ripping.html), like so:
Code: Select alllzh8_dec pii_1-151_387-492.arc.cx pii_1-151_387-492.arcThe decompressed file (pii_1-151_387-492.arc) is a U8 archive that you can probably handle with the standard U8 tools.

edit: parse-u8 seems to handle it fine.  And lzh8_cmp recreates the original file almost perfectly, only difference is the original seems to be padded to 0x20 bytes at the end.  If you're going to be editing you may have to add that padding in for the replaced files to work.
I tried to use lzh8_dec to extract the pii_1-151_387-492.arc.cx but it doesn't decompress. How do you do it?
